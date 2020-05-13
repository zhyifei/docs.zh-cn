---
title: 默认探测 - .NET Core
description: 用于定位依赖项的 .NET Core 的 System.Runtime.Loader.AssemblyLoadContext.Default 探测逻辑的概述。
ms.date: 08/09/2019
author: sdmaclea
ms.author: stmaclea
ms.openlocfilehash: 1e347c716c2d739a1bd03be056b57fdbda6c678f
ms.sourcegitcommit: d9c7ac5d06735a01c1fafe34efe9486734841a72
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/06/2020
ms.locfileid: "82859509"
---
# <a name="default-probing"></a><span data-ttu-id="3a24c-103">默认探测</span><span class="sxs-lookup"><span data-stu-id="3a24c-103">Default probing</span></span>

<span data-ttu-id="3a24c-104"><xref:System.Runtime.Loader.AssemblyLoadContext.Default%2A?displayProperty=nameWithType> 实例负责定位程序集的依赖项。</span><span class="sxs-lookup"><span data-stu-id="3a24c-104">The <xref:System.Runtime.Loader.AssemblyLoadContext.Default%2A?displayProperty=nameWithType> instance is responsible for locating an assembly's dependencies.</span></span> <span data-ttu-id="3a24c-105">本文介绍 <xref:System.Runtime.Loader.AssemblyLoadContext.Default%2A?displayProperty=nameWithType> 实例的探测逻辑。</span><span class="sxs-lookup"><span data-stu-id="3a24c-105">This article describes the <xref:System.Runtime.Loader.AssemblyLoadContext.Default%2A?displayProperty=nameWithType> instance's probing logic.</span></span>

## <a name="host-configured-probing-properties"></a><span data-ttu-id="3a24c-106">主机配置的探测属性</span><span class="sxs-lookup"><span data-stu-id="3a24c-106">Host configured probing properties</span></span>

<span data-ttu-id="3a24c-107">运行时启动时，运行时主机提供一组命名的探测属性，这些属性可配置 <xref:System.Runtime.Loader.AssemblyLoadContext.Default%2A?displayProperty=nameWithType> 探测路径。</span><span class="sxs-lookup"><span data-stu-id="3a24c-107">When the runtime is started, the runtime host provides a set of named probing properties that configure <xref:System.Runtime.Loader.AssemblyLoadContext.Default%2A?displayProperty=nameWithType> probe paths.</span></span>

<span data-ttu-id="3a24c-108">每个探测属性均可选。</span><span class="sxs-lookup"><span data-stu-id="3a24c-108">Each probing property is optional.</span></span> <span data-ttu-id="3a24c-109">如果存在，则每个属性都是一个字符串值，其中包含绝对路径的分隔列表。</span><span class="sxs-lookup"><span data-stu-id="3a24c-109">If present, each property is a string value that contains a delimited list of absolute paths.</span></span> <span data-ttu-id="3a24c-110">在 Windows 上，分隔符为“;”，在所有其他平台上，分隔符为“:”。</span><span class="sxs-lookup"><span data-stu-id="3a24c-110">The delimiter is ';' on Windows and ':' on all other platforms.</span></span>

|<span data-ttu-id="3a24c-111">属性名</span><span class="sxs-lookup"><span data-stu-id="3a24c-111">Property Name</span></span>                 |<span data-ttu-id="3a24c-112">描述</span><span class="sxs-lookup"><span data-stu-id="3a24c-112">Description</span></span>  |
|------------------------------|---------|
|`TRUSTED_PLATFORM_ASSEMBLIES`   | <span data-ttu-id="3a24c-113">平台和应用程序程序集文件路径的列表。</span><span class="sxs-lookup"><span data-stu-id="3a24c-113">List of platform and application assembly file paths.</span></span> |
|`PLATFORM_RESOURCE_ROOTS`       | <span data-ttu-id="3a24c-114">用于搜索附属资源程序集的目录路径的列表。</span><span class="sxs-lookup"><span data-stu-id="3a24c-114">List of directory paths to search for satellite resource assemblies.</span></span> |
|`NATIVE_DLL_SEARCH_DIRECTORIES` | <span data-ttu-id="3a24c-115">用于搜索非托管（本机）库的目录路径的列表。</span><span class="sxs-lookup"><span data-stu-id="3a24c-115">List of directory paths to search for unmanaged (native) libraries.</span></span>        |
|`APP_PATHS`                     | <span data-ttu-id="3a24c-116">用于搜索托管程序集的目录路径的列表。</span><span class="sxs-lookup"><span data-stu-id="3a24c-116">List of directory paths to search for managed assemblies.</span></span> |
|`APP_NI_PATHS`                  | <span data-ttu-id="3a24c-117">用于搜索托管程序集的本机映像的目录路径的列表。</span><span class="sxs-lookup"><span data-stu-id="3a24c-117">List of directory paths to search for native images of managed assemblies.</span></span> |

### <a name="how-are-the-properties-populated"></a><span data-ttu-id="3a24c-118">如何填充属性？</span><span class="sxs-lookup"><span data-stu-id="3a24c-118">How are the properties populated?</span></span>

<span data-ttu-id="3a24c-119">填充属性有两个主要方案，具体取决于 \<myapp>.deps.json 文件是否存在  。</span><span class="sxs-lookup"><span data-stu-id="3a24c-119">There are two main scenarios for populating the properties depending on whether the *\<myapp>.deps.json* file exists.</span></span>

- <span data-ttu-id="3a24c-120">当 \*.deps.json 文件存在时，将对其进行分析以填充探测属性  。</span><span class="sxs-lookup"><span data-stu-id="3a24c-120">When the *\*.deps.json* file is present, it's parsed to populate the probing properties.</span></span>
- <span data-ttu-id="3a24c-121">如果 \*.deps.json  文件不存在，则假定应用程序的目录以包含所有依赖项。</span><span class="sxs-lookup"><span data-stu-id="3a24c-121">When the *\*.deps.json* file isn't present, the application's directory is assumed to contain all the dependencies.</span></span> <span data-ttu-id="3a24c-122">目录的内容用于填充探测属性。</span><span class="sxs-lookup"><span data-stu-id="3a24c-122">The directory's contents are used to populate the probing properties.</span></span>

<span data-ttu-id="3a24c-123">此外，也会对任何引用框架的 \*.deps.json  文件进行类似的分析。</span><span class="sxs-lookup"><span data-stu-id="3a24c-123">Additionally, the *\*.deps.json* files for any referenced frameworks are similarly parsed.</span></span>

<span data-ttu-id="3a24c-124">最后，可使用环境变量 `ADDITIONAL_DEPS` 添加其他依赖项。</span><span class="sxs-lookup"><span data-stu-id="3a24c-124">Finally the environment variable `ADDITIONAL_DEPS` can be used to add additional dependencies.</span></span>

<span data-ttu-id="3a24c-125">默认不会填充 `APP_PATHS` 和 `APP_NI_PATHS` 属性，大多数应用程序都省略了它们。</span><span class="sxs-lookup"><span data-stu-id="3a24c-125">The `APP_PATHS` and `APP_NI_PATHS` properties are not populated by default and are omitted for most applications.</span></span>

### <a name="how-do-i-see-the-probing-properties-from-managed-code"></a><span data-ttu-id="3a24c-126">如何查看托管代码中的探测属性？</span><span class="sxs-lookup"><span data-stu-id="3a24c-126">How do I see the probing properties from managed code?</span></span>

<span data-ttu-id="3a24c-127">通过使用上表中的属性名称调用 <xref:System.AppContext.GetData(System.String)?displayProperty=nameWithType> 函数，可查看每个属性。</span><span class="sxs-lookup"><span data-stu-id="3a24c-127">Each property is available by calling the <xref:System.AppContext.GetData(System.String)?displayProperty=nameWithType> function with the property name from the table above.</span></span>

### <a name="how-do-i-debug-the-probing-properties-construction"></a><span data-ttu-id="3a24c-128">如何调试探测属性的构造？</span><span class="sxs-lookup"><span data-stu-id="3a24c-128">How do I debug the probing properties' construction?</span></span>

<span data-ttu-id="3a24c-129">启用某些环境变量后，.NET Core 运行时主机将输出有用的跟踪消息：</span><span class="sxs-lookup"><span data-stu-id="3a24c-129">The .NET Core runtime host will output useful trace messages when certain environment variables are enabled:</span></span>

|<span data-ttu-id="3a24c-130">环境变量</span><span class="sxs-lookup"><span data-stu-id="3a24c-130">Environment Variable</span></span>        |<span data-ttu-id="3a24c-131">描述</span><span class="sxs-lookup"><span data-stu-id="3a24c-131">Description</span></span>  |
|----------------------------|---------|
|`COREHOST_TRACE=1`          |<span data-ttu-id="3a24c-132">启用跟踪。</span><span class="sxs-lookup"><span data-stu-id="3a24c-132">Enables tracing.</span></span>|
|`COREHOST_TRACEFILE=<path>` |<span data-ttu-id="3a24c-133">跟踪文件路径而不是默认 `stderr`。</span><span class="sxs-lookup"><span data-stu-id="3a24c-133">Traces to a file path instead of the default `stderr`.</span></span>|
|`COREHOST_TRACE_VERBOSITY`  |<span data-ttu-id="3a24c-134">将详细程度设置为从 1（最低）到 4（最高）。</span><span class="sxs-lookup"><span data-stu-id="3a24c-134">Sets the verbosity from 1 (lowest) to 4 (highest).</span></span>|

## <a name="managed-assembly-default-probing"></a><span data-ttu-id="3a24c-135">托管程序集默认探测</span><span class="sxs-lookup"><span data-stu-id="3a24c-135">Managed assembly default probing</span></span>

<span data-ttu-id="3a24c-136">当探测以定位托管程序集时，<xref:System.Runtime.Loader.AssemblyLoadContext.Default%2A?displayProperty=nameWithType> 会按以下顺序查找：</span><span class="sxs-lookup"><span data-stu-id="3a24c-136">When probing to locate a managed assembly, the <xref:System.Runtime.Loader.AssemblyLoadContext.Default%2A?displayProperty=nameWithType> looks in order at:</span></span>

- <span data-ttu-id="3a24c-137">与 `TRUSTED_PLATFORM_ASSEMBLIES` 中的 <xref:System.Reflection.AssemblyName.Name?displayProperty=nameWithType> 匹配的文件（在删除文件扩展名之后）。</span><span class="sxs-lookup"><span data-stu-id="3a24c-137">Files matching the <xref:System.Reflection.AssemblyName.Name?displayProperty=nameWithType> in `TRUSTED_PLATFORM_ASSEMBLIES` (after removing file extensions).</span></span>
- <span data-ttu-id="3a24c-138">包含公共文件扩展名的 `APP_NI_PATHS` 中的本机映像程序集文件。</span><span class="sxs-lookup"><span data-stu-id="3a24c-138">Native image assembly files in `APP_NI_PATHS` with common file extensions.</span></span>
- <span data-ttu-id="3a24c-139">包含公共文件扩展名的 `APP_PATHS` 中的程序集文件。</span><span class="sxs-lookup"><span data-stu-id="3a24c-139">Assembly files in `APP_PATHS` with common file extensions.</span></span>

## <a name="satellite-resource-assembly-probing"></a><span data-ttu-id="3a24c-140">附属（资源）程序集探测</span><span class="sxs-lookup"><span data-stu-id="3a24c-140">Satellite (resource) assembly probing</span></span>

<span data-ttu-id="3a24c-141">若要查找特定区域性的附属程序集，请构造一组文件路径。</span><span class="sxs-lookup"><span data-stu-id="3a24c-141">To find a satellite assembly for a specific culture, construct a set of file paths.</span></span>

<span data-ttu-id="3a24c-142">对于 `PLATFORM_RESOURCE_ROOTS` 和 `APP_PATHS` 中的每个路径，附加 <xref:System.Globalization.CultureInfo.Name?displayProperty=nameWithType> 字符串、目录分隔符、<xref:System.Reflection.AssemblyName.Name?displayProperty=nameWithType> 字符串和扩展名“.dll”。</span><span class="sxs-lookup"><span data-stu-id="3a24c-142">For each path in `PLATFORM_RESOURCE_ROOTS` and then `APP_PATHS`, append the <xref:System.Globalization.CultureInfo.Name?displayProperty=nameWithType> string, a directory separator, the <xref:System.Reflection.AssemblyName.Name?displayProperty=nameWithType> string, and the extension '.dll'.</span></span>

<span data-ttu-id="3a24c-143">如果存在任何匹配的文件，请尝试加载并返回该文件。</span><span class="sxs-lookup"><span data-stu-id="3a24c-143">If any matching file exists, attempt to load and return it.</span></span>

## <a name="unmanaged-native-library-probing"></a><span data-ttu-id="3a24c-144">非托管（本机）库探测</span><span class="sxs-lookup"><span data-stu-id="3a24c-144">Unmanaged (native) library probing</span></span>

<span data-ttu-id="3a24c-145">当探测以查找非托管库时，将搜索 `NATIVE_DLL_SEARCH_DIRECTORIES` 以查找匹配库。</span><span class="sxs-lookup"><span data-stu-id="3a24c-145">When probing to locate an unmanaged library, the `NATIVE_DLL_SEARCH_DIRECTORIES` are searched looking for a matching library.</span></span>
