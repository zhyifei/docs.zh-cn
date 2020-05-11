---
title: 附属程序集加载算法 - .NET Core
description: .NET Core 中附属程序集加载算法的详细说明
ms.date: 08/09/2019
author: sdmaclea
ms.author: stmaclea
ms.openlocfilehash: 17f29a9aca79019daa91736e586bf1b6b753a9ec
ms.sourcegitcommit: d9c7ac5d06735a01c1fafe34efe9486734841a72
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/06/2020
ms.locfileid: "82859529"
---
# <a name="satellite-assembly-loading-algorithm"></a><span data-ttu-id="bfba2-103">附属程序集加载算法</span><span class="sxs-lookup"><span data-stu-id="bfba2-103">Satellite assembly loading algorithm</span></span>

<span data-ttu-id="bfba2-104">使用附属程序集来存储为语言和区域性自定义的本地化资源。</span><span class="sxs-lookup"><span data-stu-id="bfba2-104">Satellite assemblies are used to store localized resources customized for language and culture.</span></span>

<span data-ttu-id="bfba2-105">附属程序集使用不同于常规托管程序集的加载算法。</span><span class="sxs-lookup"><span data-stu-id="bfba2-105">Satellite assemblies use a different loading algorithm than general managed assemblies.</span></span>

## <a name="when-are-satellite-assemblies-loaded"></a><span data-ttu-id="bfba2-106">何时加载附属程序集？</span><span class="sxs-lookup"><span data-stu-id="bfba2-106">When are satellite assemblies loaded?</span></span>

<span data-ttu-id="bfba2-107">加载本地化资源时加载附属程序集。</span><span class="sxs-lookup"><span data-stu-id="bfba2-107">Satellite assemblies are loaded when loading a localized resource.</span></span>

<span data-ttu-id="bfba2-108">加载本地化资源的基本 API 是 <xref:System.Resources.ResourceManager?displayProperty=fullName> 类。</span><span class="sxs-lookup"><span data-stu-id="bfba2-108">The basic API to load localized resources is the <xref:System.Resources.ResourceManager?displayProperty=fullName> class.</span></span> <span data-ttu-id="bfba2-109">最后，<xref:System.Resources.ResourceManager> 类将为每个 <xref:System.Globalization.CultureInfo.Name?displayProperty=nameWithType> 调用 <xref:System.Reflection.Assembly.GetSatelliteAssembly%2A> 方法。</span><span class="sxs-lookup"><span data-stu-id="bfba2-109">Ultimately the <xref:System.Resources.ResourceManager> class will call the <xref:System.Reflection.Assembly.GetSatelliteAssembly%2A> method for each <xref:System.Globalization.CultureInfo.Name?displayProperty=nameWithType>.</span></span>

<span data-ttu-id="bfba2-110">较高级别的 API 可能会提取低级别 API。</span><span class="sxs-lookup"><span data-stu-id="bfba2-110">Higher-level APIs may abstract the low-level API.</span></span>

## <a name="algorithm"></a><span data-ttu-id="bfba2-111">算法</span><span class="sxs-lookup"><span data-stu-id="bfba2-111">Algorithm</span></span>

<span data-ttu-id="bfba2-112">.NET Core 资源回退进程包含以下步骤：</span><span class="sxs-lookup"><span data-stu-id="bfba2-112">The .NET Core resource fallback process involves the following steps:</span></span>

1. <span data-ttu-id="bfba2-113">确定 `active` <xref:System.Runtime.Loader.AssemblyLoadContext> 实例。</span><span class="sxs-lookup"><span data-stu-id="bfba2-113">Determine the `active` <xref:System.Runtime.Loader.AssemblyLoadContext> instance.</span></span> <span data-ttu-id="bfba2-114">在所有情况下，`active` 实例都是执行程序集的 <xref:System.Runtime.Loader.AssemblyLoadContext>。</span><span class="sxs-lookup"><span data-stu-id="bfba2-114">In all cases, the `active` instance is the executing assembly's <xref:System.Runtime.Loader.AssemblyLoadContext>.</span></span>

2. <span data-ttu-id="bfba2-115">`active` 实例尝试通过以下方式按优先级排序来加载请求的区域性的附属程序集：</span><span class="sxs-lookup"><span data-stu-id="bfba2-115">The `active` instance attempts to load a satellite assembly for the requested culture in priority order by:</span></span>
    - <span data-ttu-id="bfba2-116">检查其缓存。</span><span class="sxs-lookup"><span data-stu-id="bfba2-116">Checking its cache.</span></span>
    - <span data-ttu-id="bfba2-117">检查当前正在执行程序集的目录，查找与请求的 <xref:System.Globalization.CultureInfo.Name?displayProperty=nameWithType>（例如 `es-MX`）匹配的子目录。</span><span class="sxs-lookup"><span data-stu-id="bfba2-117">Checking the directory of the currently executing assembly for a subdirectory that matches the requested <xref:System.Globalization.CultureInfo.Name?displayProperty=nameWithType> (for example `es-MX`).</span></span>

        > [!NOTE]
        > <span data-ttu-id="bfba2-118">3\.0 版之前的 .NET Core 中未实现此功能。</span><span class="sxs-lookup"><span data-stu-id="bfba2-118">This feature was not implemented in .NET Core before 3.0.</span></span>
        >
        > [!NOTE]
        > <span data-ttu-id="bfba2-119">在 Linux 和 macOS 上，子目录区分大小写，并且必须是以下两种情况之一：</span><span class="sxs-lookup"><span data-stu-id="bfba2-119">On Linux and macOS, the subdirectory is case-sensitive and must either:</span></span>
        >
        > - <span data-ttu-id="bfba2-120">完全匹配大小写。</span><span class="sxs-lookup"><span data-stu-id="bfba2-120">Exactly match case.</span></span>
        > - <span data-ttu-id="bfba2-121">为小写。</span><span class="sxs-lookup"><span data-stu-id="bfba2-121">Be in lower case.</span></span>

    - <span data-ttu-id="bfba2-122">如果 `active` 是 <xref:System.Runtime.Loader.AssemblyLoadContext.Default?displayProperty=nameWithType> 实例，则通过运行[默认附属（资源）程序集探测](default-probing.md#satellite-resource-assembly-probing)逻辑。</span><span class="sxs-lookup"><span data-stu-id="bfba2-122">If `active` is the <xref:System.Runtime.Loader.AssemblyLoadContext.Default?displayProperty=nameWithType> instance, by running the [default satellite (resource) assembly probing](default-probing.md#satellite-resource-assembly-probing) logic.</span></span>

    - <span data-ttu-id="bfba2-123">调用 <xref:System.Runtime.Loader.AssemblyLoadContext.Load%2A?displayProperty=nameWithType> 函数。</span><span class="sxs-lookup"><span data-stu-id="bfba2-123">Calling the <xref:System.Runtime.Loader.AssemblyLoadContext.Load%2A?displayProperty=nameWithType> function.</span></span>

    - <span data-ttu-id="bfba2-124">引发 <xref:System.Runtime.Loader.AssemblyLoadContext.Resolving?displayProperty=nameWithType> 事件。</span><span class="sxs-lookup"><span data-stu-id="bfba2-124">Raising the <xref:System.Runtime.Loader.AssemblyLoadContext.Resolving?displayProperty=nameWithType> event.</span></span>

    - <span data-ttu-id="bfba2-125">引发 <xref:System.AppDomain.AssemblyResolve?displayProperty=nameWithType> 事件。</span><span class="sxs-lookup"><span data-stu-id="bfba2-125">Raising the <xref:System.AppDomain.AssemblyResolve?displayProperty=nameWithType> event.</span></span>

3. <span data-ttu-id="bfba2-126">如果加载附属程序集：</span><span class="sxs-lookup"><span data-stu-id="bfba2-126">If a satellite assembly is loaded:</span></span>
   - <span data-ttu-id="bfba2-127">引发 <xref:System.AppDomain.AssemblyLoad?displayProperty=nameWithType> 事件。</span><span class="sxs-lookup"><span data-stu-id="bfba2-127">The <xref:System.AppDomain.AssemblyLoad?displayProperty=nameWithType> event is raised.</span></span>
   - <span data-ttu-id="bfba2-128">将搜索程序集以查找请求的资源。</span><span class="sxs-lookup"><span data-stu-id="bfba2-128">The assembly is searched it for the requested resource.</span></span> <span data-ttu-id="bfba2-129">如果运行时在程序集中找到该资源，则使用它。</span><span class="sxs-lookup"><span data-stu-id="bfba2-129">If the runtime finds the resource in the assembly, it uses it.</span></span> <span data-ttu-id="bfba2-130">如果找不到该资源，将继续搜索。</span><span class="sxs-lookup"><span data-stu-id="bfba2-130">If it doesn't find the resource, it continues the search.</span></span>

    > [!NOTE]
    > <span data-ttu-id="bfba2-131">要在附属程序集中查找资源，运行时将搜索 <xref:System.Resources.ResourceManager> 为当前 <xref:System.Globalization.CultureInfo.Name?displayProperty=nameWithType> 请求的资源文件。</span><span class="sxs-lookup"><span data-stu-id="bfba2-131">To find a resource within the satellite assembly, the runtime searches for the resource file requested by the <xref:System.Resources.ResourceManager> for the current <xref:System.Globalization.CultureInfo.Name?displayProperty=nameWithType>.</span></span> <span data-ttu-id="bfba2-132">在资源文件中，它搜索请求的资源名称。</span><span class="sxs-lookup"><span data-stu-id="bfba2-132">Within the resource file, it searches for the requested resource name.</span></span> <span data-ttu-id="bfba2-133">如果找不到上述任何一个，则资源将被视为未找到。</span><span class="sxs-lookup"><span data-stu-id="bfba2-133">If either is not found, the resource is treated as not found.</span></span>

4. <span data-ttu-id="bfba2-134">接下来，运行时通过许多潜在级别搜索父区域性程序集，每次均重复步骤 2 和 3。</span><span class="sxs-lookup"><span data-stu-id="bfba2-134">The runtime next searches the parent culture assemblies through many potential levels, each time repeating steps 2 & 3.</span></span>

    <span data-ttu-id="bfba2-135">每个区域性只有一个父级，由 <xref:System.Globalization.CultureInfo.Parent%2A?displayProperty=nameWithType> 属性定义。</span><span class="sxs-lookup"><span data-stu-id="bfba2-135">Each culture has only one parent, which is defined by the <xref:System.Globalization.CultureInfo.Parent%2A?displayProperty=nameWithType> property.</span></span>

    <span data-ttu-id="bfba2-136">当区域性的 <xref:System.Globalization.CultureInfo.Parent%2A> 属性为 <xref:System.Globalization.CultureInfo.InvariantCulture?displayProperty=nameWithType> 时，父区域性搜索将停止。</span><span class="sxs-lookup"><span data-stu-id="bfba2-136">The search for parent cultures stops when a culture's <xref:System.Globalization.CultureInfo.Parent%2A> property is <xref:System.Globalization.CultureInfo.InvariantCulture?displayProperty=nameWithType>.</span></span>

    <span data-ttu-id="bfba2-137">对于 <xref:System.Globalization.CultureInfo.InvariantCulture>，我们不会返回到步骤 2 和 3，而是继续执行步骤 5。</span><span class="sxs-lookup"><span data-stu-id="bfba2-137">For the <xref:System.Globalization.CultureInfo.InvariantCulture>, we don't return to steps 2 & 3, but rather continue with step 5.</span></span>

5. <span data-ttu-id="bfba2-138">如果仍未找到资源，则使用默认（回退）区域性的资源。</span><span class="sxs-lookup"><span data-stu-id="bfba2-138">If the resource is still not found, the resource for the default (fallback) culture is used.</span></span>

   <span data-ttu-id="bfba2-139">通常，默认区域性的资源包含在主应用程序集中。</span><span class="sxs-lookup"><span data-stu-id="bfba2-139">Typically, the resources for the default culture are included in the main application assembly.</span></span> <span data-ttu-id="bfba2-140">不过，可以为 <xref:System.Resources.NeutralResourcesLanguageAttribute.Location?displayProperty=nameWithType> 属性指定 <xref:System.Resources.UltimateResourceFallbackLocation.Satellite?displayProperty=nameWithType>。</span><span class="sxs-lookup"><span data-stu-id="bfba2-140">However, you can specify <xref:System.Resources.UltimateResourceFallbackLocation.Satellite?displayProperty=nameWithType> for the <xref:System.Resources.NeutralResourcesLanguageAttribute.Location?displayProperty=nameWithType> property.</span></span> <span data-ttu-id="bfba2-141">此值指示资源的最终回退位置是附属程序集，而不是主程序集。</span><span class="sxs-lookup"><span data-stu-id="bfba2-141">This value indicates that the ultimate fallback location for resources is a satellite assembly rather than the main assembly.</span></span>

    > [!NOTE]
    > <span data-ttu-id="bfba2-142">默认区域性为最终回退。</span><span class="sxs-lookup"><span data-stu-id="bfba2-142">The default culture is the ultimate fallback.</span></span> <span data-ttu-id="bfba2-143">因此，建议在默认资源文件中始终包含一组详尽的资源。</span><span class="sxs-lookup"><span data-stu-id="bfba2-143">Therefore, we recommend that you always include an exhaustive set of resources in the default resource file.</span></span> <span data-ttu-id="bfba2-144">这有助于防止引发异常。</span><span class="sxs-lookup"><span data-stu-id="bfba2-144">This helps prevent exceptions from being thrown.</span></span> <span data-ttu-id="bfba2-145">通过拥有详尽资源集，可为所有资源提供回退，并确保始终向用户呈现至少一种资源，即使该资源不是特定于区域性的。</span><span class="sxs-lookup"><span data-stu-id="bfba2-145">By having an exhaustive set, you provide a fallback for all resources and ensure that at least one resource is always present for the user, even if it is not culturally specific.</span></span>

6. <span data-ttu-id="bfba2-146">最后，</span><span class="sxs-lookup"><span data-stu-id="bfba2-146">Finally,</span></span>
   - <span data-ttu-id="bfba2-147">如果运行时找不到默认（回退）区域性的资源文件，将引发 <xref:System.Resources.MissingManifestResourceException> 或 <xref:System.Resources.MissingSatelliteAssemblyException> 异常。</span><span class="sxs-lookup"><span data-stu-id="bfba2-147">If the runtime doesn't find a resource file for a default (fallback) culture, a <xref:System.Resources.MissingManifestResourceException> or <xref:System.Resources.MissingSatelliteAssemblyException> exception is thrown.</span></span>
   - <span data-ttu-id="bfba2-148">如果找到资源文件但是请求的资源不存在，则请求返回 `null`。</span><span class="sxs-lookup"><span data-stu-id="bfba2-148">If the resource file is found but the requested resource isn't present, the request returns `null`.</span></span>
