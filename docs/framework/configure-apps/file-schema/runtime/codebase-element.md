---
title: <codeBase> 元素
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#codeBase
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/runtime/assemblyBinding/dependentAssembly/codeBase
helpviewer_keywords:
- <codeBase> element
- container tags, <codeBase> element
- codeBase element
ms.assetid: d48a3983-2297-43ff-a14d-1f29d3995822
ms.openlocfilehash: a06daa0b2aa5374c9959cbbe778d62856819a40e
ms.sourcegitcommit: cdf67135a98a5a51913dacddb58e004a3c867802
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/21/2019
ms.locfileid: "69663863"
---
# <a name="codebase-element"></a><span data-ttu-id="78d98-102">\<codeBase > 元素</span><span class="sxs-lookup"><span data-stu-id="78d98-102">\<codeBase> Element</span></span>

<span data-ttu-id="78d98-103">指定公共语言运行时可在何处找到程序集。</span><span class="sxs-lookup"><span data-stu-id="78d98-103">Specifies where the common language runtime can find an assembly.</span></span>

<span data-ttu-id="78d98-104">\<configuration > \<运行时\<> assemblyBinding \<> dependentAssembly \<> codeBase ></span><span class="sxs-lookup"><span data-stu-id="78d98-104">\<configuration> \<runtime> \<assemblyBinding> \<dependentAssembly> \<codeBase></span></span>

## <a name="syntax"></a><span data-ttu-id="78d98-105">语法</span><span class="sxs-lookup"><span data-stu-id="78d98-105">Syntax</span></span>

```xml
   <codeBase
        version="Assembly version"
        href="URL of assembly"/>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="78d98-106">特性和元素</span><span class="sxs-lookup"><span data-stu-id="78d98-106">Attributes and Elements</span></span>

<span data-ttu-id="78d98-107">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="78d98-107">The following sections describe attributes, child elements, and parent elements.</span></span>

### <a name="attributes"></a><span data-ttu-id="78d98-108">特性</span><span class="sxs-lookup"><span data-stu-id="78d98-108">Attributes</span></span>

|<span data-ttu-id="78d98-109">特性</span><span class="sxs-lookup"><span data-stu-id="78d98-109">Attribute</span></span>|<span data-ttu-id="78d98-110">描述</span><span class="sxs-lookup"><span data-stu-id="78d98-110">Description</span></span>|
|---------------|-----------------|
|`href`|<span data-ttu-id="78d98-111">必需的特性。</span><span class="sxs-lookup"><span data-stu-id="78d98-111">Required attribute.</span></span><br /><br /> <span data-ttu-id="78d98-112">指定运行时可在其中找到程序集的指定版本的 URL。</span><span class="sxs-lookup"><span data-stu-id="78d98-112">Specifies the URL where the runtime can find the specified version of the assembly.</span></span>|
|`version`|<span data-ttu-id="78d98-113">必需的特性。</span><span class="sxs-lookup"><span data-stu-id="78d98-113">Required attribute.</span></span><br /><br /> <span data-ttu-id="78d98-114">指定基本代码所应用的程序集的版本。</span><span class="sxs-lookup"><span data-stu-id="78d98-114">Specifies the version of the assembly the codebase applies to.</span></span> <span data-ttu-id="78d98-115">程序集版本号的格式为 "主要版本. 次要版本. 内部版本.*修订*版本"。</span><span class="sxs-lookup"><span data-stu-id="78d98-115">The format of an assembly version number is *major.minor.build.revision*.</span></span>|

## <a name="version-attribute"></a><span data-ttu-id="78d98-116">version 特性</span><span class="sxs-lookup"><span data-stu-id="78d98-116">version Attribute</span></span>

|<span data-ttu-id="78d98-117">值</span><span class="sxs-lookup"><span data-stu-id="78d98-117">Value</span></span>|<span data-ttu-id="78d98-118">描述</span><span class="sxs-lookup"><span data-stu-id="78d98-118">Description</span></span>|
|-----------|-----------------|
|<span data-ttu-id="78d98-119">版本号的每个部分的有效值为0至65535。</span><span class="sxs-lookup"><span data-stu-id="78d98-119">Valid values for each part of the version number are 0 to 65535.</span></span>|<span data-ttu-id="78d98-120">不适用。</span><span class="sxs-lookup"><span data-stu-id="78d98-120">Not applicable.</span></span>|

### <a name="child-elements"></a><span data-ttu-id="78d98-121">子元素</span><span class="sxs-lookup"><span data-stu-id="78d98-121">Child Elements</span></span>

<span data-ttu-id="78d98-122">无。</span><span class="sxs-lookup"><span data-stu-id="78d98-122">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="78d98-123">父元素</span><span class="sxs-lookup"><span data-stu-id="78d98-123">Parent Elements</span></span>

|<span data-ttu-id="78d98-124">元素</span><span class="sxs-lookup"><span data-stu-id="78d98-124">Element</span></span>|<span data-ttu-id="78d98-125">描述</span><span class="sxs-lookup"><span data-stu-id="78d98-125">Description</span></span>|
|-------------|-----------------|
|`buildproviders`|<span data-ttu-id="78d98-126">定义用于编译自定义资源文件的生成提供程序的集合。</span><span class="sxs-lookup"><span data-stu-id="78d98-126">Defines a collection of build providers used to compile custom resource files.</span></span> <span data-ttu-id="78d98-127">您可以拥有任意数量的生成提供程序。</span><span class="sxs-lookup"><span data-stu-id="78d98-127">You can have any number of build providers.</span></span>|
|`compilation`|<span data-ttu-id="78d98-128">配置 ASP.NET 使用的所有编译设置。</span><span class="sxs-lookup"><span data-stu-id="78d98-128">Configures all the compilation settings that ASP.NET uses.</span></span>|
|`configuration`|<span data-ttu-id="78d98-129">公共语言运行时和 .NET Framework 应用程序所使用的每个配置文件中的根元素。</span><span class="sxs-lookup"><span data-stu-id="78d98-129">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|
|`System.web`|<span data-ttu-id="78d98-130">为 ASP.NET 配置节指定根元素。</span><span class="sxs-lookup"><span data-stu-id="78d98-130">Specifies the root element for the ASP.NET configuration section.</span></span>|

## <a name="remarks"></a><span data-ttu-id="78d98-131">备注</span><span class="sxs-lookup"><span data-stu-id="78d98-131">Remarks</span></span>

<span data-ttu-id="78d98-132">为了使运行时使用计算机配置文件或发布服务器策略文件中的 **\<codeBase >** 设置, 该文件还必须重定向程序集版本。</span><span class="sxs-lookup"><span data-stu-id="78d98-132">For the runtime to use the **\<codeBase>** setting in a machine configuration file or publisher policy file, the file must also redirect the assembly version.</span></span> <span data-ttu-id="78d98-133">应用程序配置文件可以具有基本代码设置, 而不会重定向程序集版本。</span><span class="sxs-lookup"><span data-stu-id="78d98-133">Application configuration files can have a codebase setting without redirecting the assembly version.</span></span> <span data-ttu-id="78d98-134">确定要使用的程序集版本后, 运行时将从确定版本的文件应用基本代码设置。</span><span class="sxs-lookup"><span data-stu-id="78d98-134">After determining which assembly version to use, the runtime applies the codebase setting from the file that determines the version.</span></span> <span data-ttu-id="78d98-135">如果未指定基本代码, 则运行时以常规方式探测程序集。</span><span class="sxs-lookup"><span data-stu-id="78d98-135">If no codebase is indicated, the runtime probes for the assembly in the usual way.</span></span>

<span data-ttu-id="78d98-136">如果程序集具有强名称, 则基本代码设置可以是本地 intranet 或 Internet 上的任何位置。</span><span class="sxs-lookup"><span data-stu-id="78d98-136">If the assembly has a strong name, the codebase setting can be anywhere on the local intranet or the Internet.</span></span> <span data-ttu-id="78d98-137">如果程序集是私有程序集, 则 codebase 设置必须是相对于应用程序目录的路径。</span><span class="sxs-lookup"><span data-stu-id="78d98-137">If the assembly is a private assembly, the codebase setting must be a path relative to the application's directory.</span></span>

<span data-ttu-id="78d98-138">对于没有强名称的程序集, 版本会被忽略, 并且加载程序在 dependentAssembly \<> 内\<使用基本代码 > 的第一种外观。</span><span class="sxs-lookup"><span data-stu-id="78d98-138">For assemblies without a strong name, version is ignored and the loader uses the first appearance of \<codebase> inside \<dependentAssembly>.</span></span> <span data-ttu-id="78d98-139">如果应用程序配置文件中存在重定向绑定到另一个程序集的条目, 则即使程序集版本与绑定请求不匹配, 重定向也将优先。</span><span class="sxs-lookup"><span data-stu-id="78d98-139">If there is an entry in the application configuration file that redirects binding to another assembly, the redirection will take precedence even if the assembly version doesn't match the binding request.</span></span>

## <a name="example"></a><span data-ttu-id="78d98-140">示例</span><span class="sxs-lookup"><span data-stu-id="78d98-140">Example</span></span>

<span data-ttu-id="78d98-141">下面的示例演示如何指定运行时在何处可以找到程序集。</span><span class="sxs-lookup"><span data-stu-id="78d98-141">The following example shows how to specify where the runtime can find an assembly.</span></span>

```xml
<configuration>
   <runtime>
      <assemblyBinding xmlns="urn:schemas-microsoft-com:asm.v1">
         <dependentAssembly>
            <assemblyIdentity name="myAssembly"
                              publicKeyToken="32ab4ba45e0a69a1"
                              culture="neutral" />
            <codeBase version="2.0.0.0"
                      href="http://www.litwareinc.com/myAssembly.dll"/>
         </dependentAssembly>
      </assemblyBinding>
   </runtime>
</configuration>
```

## <a name="see-also"></a><span data-ttu-id="78d98-142">请参阅</span><span class="sxs-lookup"><span data-stu-id="78d98-142">See also</span></span>

- [<span data-ttu-id="78d98-143">运行时设置架构</span><span class="sxs-lookup"><span data-stu-id="78d98-143">Runtime Settings Schema</span></span>](index.md)
- [<span data-ttu-id="78d98-144">配置文件架构</span><span class="sxs-lookup"><span data-stu-id="78d98-144">Configuration File Schema</span></span>](../index.md)
- [<span data-ttu-id="78d98-145">指定程序集的位置</span><span class="sxs-lookup"><span data-stu-id="78d98-145">Specifying an Assembly's Location</span></span>](../../specify-assembly-location.md)
- [<span data-ttu-id="78d98-146">运行时如何定位程序集</span><span class="sxs-lookup"><span data-stu-id="78d98-146">How the Runtime Locates Assemblies</span></span>](../../../deployment/how-the-runtime-locates-assemblies.md)
