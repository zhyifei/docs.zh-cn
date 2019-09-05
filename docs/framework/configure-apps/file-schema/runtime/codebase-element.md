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
ms.openlocfilehash: bd170b817c5ccc337711f8f79968653c29f3eda4
ms.sourcegitcommit: 4e2d355baba82814fa53efd6b8bbb45bfe054d11
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/04/2019
ms.locfileid: "70252741"
---
# <a name="codebase-element"></a><span data-ttu-id="41ddd-102">\<codeBase > 元素</span><span class="sxs-lookup"><span data-stu-id="41ddd-102">\<codeBase> Element</span></span>

<span data-ttu-id="41ddd-103">指定公共语言运行时可在何处找到程序集。</span><span class="sxs-lookup"><span data-stu-id="41ddd-103">Specifies where the common language runtime can find an assembly.</span></span>

<span data-ttu-id="41ddd-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="41ddd-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="41ddd-105">&nbsp;&nbsp;[ **\<运行时 >** ](runtime-element.md)</span><span class="sxs-lookup"><span data-stu-id="41ddd-105">&nbsp;&nbsp;[**\<runtime>**](runtime-element.md)</span></span>\
<span data-ttu-id="41ddd-106">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<assemblyBinding >** ](assemblybinding-element-for-runtime.md)</span><span class="sxs-lookup"><span data-stu-id="41ddd-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<assemblyBinding>**](assemblybinding-element-for-runtime.md)</span></span>\
<span data-ttu-id="41ddd-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<dependentAssembly >** ](dependentassembly-element.md)</span><span class="sxs-lookup"><span data-stu-id="41ddd-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<dependentAssembly>**](dependentassembly-element.md)</span></span>\
<span data-ttu-id="41ddd-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<codeBase>**</span><span class="sxs-lookup"><span data-stu-id="41ddd-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<codeBase>**</span></span>

## <a name="syntax"></a><span data-ttu-id="41ddd-109">语法</span><span class="sxs-lookup"><span data-stu-id="41ddd-109">Syntax</span></span>

```xml
   <codeBase
        version="Assembly version"
        href="URL of assembly"/>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="41ddd-110">特性和元素</span><span class="sxs-lookup"><span data-stu-id="41ddd-110">Attributes and Elements</span></span>

<span data-ttu-id="41ddd-111">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="41ddd-111">The following sections describe attributes, child elements, and parent elements.</span></span>

### <a name="attributes"></a><span data-ttu-id="41ddd-112">特性</span><span class="sxs-lookup"><span data-stu-id="41ddd-112">Attributes</span></span>

|<span data-ttu-id="41ddd-113">特性</span><span class="sxs-lookup"><span data-stu-id="41ddd-113">Attribute</span></span>|<span data-ttu-id="41ddd-114">描述</span><span class="sxs-lookup"><span data-stu-id="41ddd-114">Description</span></span>|
|---------------|-----------------|
|`href`|<span data-ttu-id="41ddd-115">必需的特性。</span><span class="sxs-lookup"><span data-stu-id="41ddd-115">Required attribute.</span></span><br /><br /> <span data-ttu-id="41ddd-116">指定运行时可在其中找到程序集的指定版本的 URL。</span><span class="sxs-lookup"><span data-stu-id="41ddd-116">Specifies the URL where the runtime can find the specified version of the assembly.</span></span>|
|`version`|<span data-ttu-id="41ddd-117">必需的特性。</span><span class="sxs-lookup"><span data-stu-id="41ddd-117">Required attribute.</span></span><br /><br /> <span data-ttu-id="41ddd-118">指定基本代码所应用的程序集的版本。</span><span class="sxs-lookup"><span data-stu-id="41ddd-118">Specifies the version of the assembly the codebase applies to.</span></span> <span data-ttu-id="41ddd-119">程序集版本号的格式为 "主要版本. 次要版本. 内部版本.*修订*版本"。</span><span class="sxs-lookup"><span data-stu-id="41ddd-119">The format of an assembly version number is *major.minor.build.revision*.</span></span>|

## <a name="version-attribute"></a><span data-ttu-id="41ddd-120">version 特性</span><span class="sxs-lookup"><span data-stu-id="41ddd-120">version Attribute</span></span>

|<span data-ttu-id="41ddd-121">值</span><span class="sxs-lookup"><span data-stu-id="41ddd-121">Value</span></span>|<span data-ttu-id="41ddd-122">描述</span><span class="sxs-lookup"><span data-stu-id="41ddd-122">Description</span></span>|
|-----------|-----------------|
|<span data-ttu-id="41ddd-123">版本号的每个部分的有效值为0至65535。</span><span class="sxs-lookup"><span data-stu-id="41ddd-123">Valid values for each part of the version number are 0 to 65535.</span></span>|<span data-ttu-id="41ddd-124">不适用。</span><span class="sxs-lookup"><span data-stu-id="41ddd-124">Not applicable.</span></span>|

### <a name="child-elements"></a><span data-ttu-id="41ddd-125">子元素</span><span class="sxs-lookup"><span data-stu-id="41ddd-125">Child Elements</span></span>

<span data-ttu-id="41ddd-126">无。</span><span class="sxs-lookup"><span data-stu-id="41ddd-126">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="41ddd-127">父元素</span><span class="sxs-lookup"><span data-stu-id="41ddd-127">Parent Elements</span></span>

|<span data-ttu-id="41ddd-128">元素</span><span class="sxs-lookup"><span data-stu-id="41ddd-128">Element</span></span>|<span data-ttu-id="41ddd-129">描述</span><span class="sxs-lookup"><span data-stu-id="41ddd-129">Description</span></span>|
|-------------|-----------------|
|`buildproviders`|<span data-ttu-id="41ddd-130">定义用于编译自定义资源文件的生成提供程序的集合。</span><span class="sxs-lookup"><span data-stu-id="41ddd-130">Defines a collection of build providers used to compile custom resource files.</span></span> <span data-ttu-id="41ddd-131">您可以拥有任意数量的生成提供程序。</span><span class="sxs-lookup"><span data-stu-id="41ddd-131">You can have any number of build providers.</span></span>|
|`compilation`|<span data-ttu-id="41ddd-132">配置 ASP.NET 使用的所有编译设置。</span><span class="sxs-lookup"><span data-stu-id="41ddd-132">Configures all the compilation settings that ASP.NET uses.</span></span>|
|`configuration`|<span data-ttu-id="41ddd-133">公共语言运行时和 .NET Framework 应用程序所使用的每个配置文件中的根元素。</span><span class="sxs-lookup"><span data-stu-id="41ddd-133">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|
|`System.web`|<span data-ttu-id="41ddd-134">为 ASP.NET 配置节指定根元素。</span><span class="sxs-lookup"><span data-stu-id="41ddd-134">Specifies the root element for the ASP.NET configuration section.</span></span>|

## <a name="remarks"></a><span data-ttu-id="41ddd-135">备注</span><span class="sxs-lookup"><span data-stu-id="41ddd-135">Remarks</span></span>

<span data-ttu-id="41ddd-136">为了使运行时使用计算机配置文件或发布服务器策略文件中的 **\<codeBase >** 设置，该文件还必须重定向程序集版本。</span><span class="sxs-lookup"><span data-stu-id="41ddd-136">For the runtime to use the **\<codeBase>** setting in a machine configuration file or publisher policy file, the file must also redirect the assembly version.</span></span> <span data-ttu-id="41ddd-137">应用程序配置文件可以具有基本代码设置，而不会重定向程序集版本。</span><span class="sxs-lookup"><span data-stu-id="41ddd-137">Application configuration files can have a codebase setting without redirecting the assembly version.</span></span> <span data-ttu-id="41ddd-138">确定要使用的程序集版本后，运行时将从确定版本的文件应用基本代码设置。</span><span class="sxs-lookup"><span data-stu-id="41ddd-138">After determining which assembly version to use, the runtime applies the codebase setting from the file that determines the version.</span></span> <span data-ttu-id="41ddd-139">如果未指定基本代码，则运行时以常规方式探测程序集。</span><span class="sxs-lookup"><span data-stu-id="41ddd-139">If no codebase is indicated, the runtime probes for the assembly in the usual way.</span></span>

<span data-ttu-id="41ddd-140">如果程序集具有强名称，则基本代码设置可以是本地 intranet 或 Internet 上的任何位置。</span><span class="sxs-lookup"><span data-stu-id="41ddd-140">If the assembly has a strong name, the codebase setting can be anywhere on the local intranet or the Internet.</span></span> <span data-ttu-id="41ddd-141">如果程序集是私有程序集，则 codebase 设置必须是相对于应用程序目录的路径。</span><span class="sxs-lookup"><span data-stu-id="41ddd-141">If the assembly is a private assembly, the codebase setting must be a path relative to the application's directory.</span></span>

<span data-ttu-id="41ddd-142">对于没有强名称的程序集，版本会被忽略，并且加载程序在 dependentAssembly \<> 内\<使用基本代码 > 的第一种外观。</span><span class="sxs-lookup"><span data-stu-id="41ddd-142">For assemblies without a strong name, version is ignored and the loader uses the first appearance of \<codebase> inside \<dependentAssembly>.</span></span> <span data-ttu-id="41ddd-143">如果应用程序配置文件中存在重定向绑定到另一个程序集的条目，则即使程序集版本与绑定请求不匹配，重定向也将优先。</span><span class="sxs-lookup"><span data-stu-id="41ddd-143">If there is an entry in the application configuration file that redirects binding to another assembly, the redirection will take precedence even if the assembly version doesn't match the binding request.</span></span>

## <a name="example"></a><span data-ttu-id="41ddd-144">示例</span><span class="sxs-lookup"><span data-stu-id="41ddd-144">Example</span></span>

<span data-ttu-id="41ddd-145">下面的示例演示如何指定运行时在何处可以找到程序集。</span><span class="sxs-lookup"><span data-stu-id="41ddd-145">The following example shows how to specify where the runtime can find an assembly.</span></span>

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

## <a name="see-also"></a><span data-ttu-id="41ddd-146">请参阅</span><span class="sxs-lookup"><span data-stu-id="41ddd-146">See also</span></span>

- [<span data-ttu-id="41ddd-147">运行时设置架构</span><span class="sxs-lookup"><span data-stu-id="41ddd-147">Runtime Settings Schema</span></span>](index.md)
- [<span data-ttu-id="41ddd-148">配置文件架构</span><span class="sxs-lookup"><span data-stu-id="41ddd-148">Configuration File Schema</span></span>](../index.md)
- [<span data-ttu-id="41ddd-149">指定程序集的位置</span><span class="sxs-lookup"><span data-stu-id="41ddd-149">Specifying an Assembly's Location</span></span>](../../specify-assembly-location.md)
- [<span data-ttu-id="41ddd-150">运行时如何定位程序集</span><span class="sxs-lookup"><span data-stu-id="41ddd-150">How the Runtime Locates Assemblies</span></span>](../../../deployment/how-the-runtime-locates-assemblies.md)
