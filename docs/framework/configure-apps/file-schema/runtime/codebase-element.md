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
ms.openlocfilehash: b5825efcc613689e73fb56b6695fe7c75ff09136
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "61674189"
---
# <a name="codebase-element"></a><span data-ttu-id="9d96f-102">\<b a s e > 元素</span><span class="sxs-lookup"><span data-stu-id="9d96f-102">\<codeBase> Element</span></span>

<span data-ttu-id="9d96f-103">指定公共语言运行时在哪里可以找到程序集。</span><span class="sxs-lookup"><span data-stu-id="9d96f-103">Specifies where the common language runtime can find an assembly.</span></span>

<span data-ttu-id="9d96f-104">\<configuration> \<runtime> \<assemblyBinding> \<dependentAssembly> \<codeBase></span><span class="sxs-lookup"><span data-stu-id="9d96f-104">\<configuration> \<runtime> \<assemblyBinding> \<dependentAssembly> \<codeBase></span></span>

## <a name="syntax"></a><span data-ttu-id="9d96f-105">语法</span><span class="sxs-lookup"><span data-stu-id="9d96f-105">Syntax</span></span>

```xml
   <codeBase
        version="Assembly version"
        href="URL of assembly"/>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="9d96f-106">特性和元素</span><span class="sxs-lookup"><span data-stu-id="9d96f-106">Attributes and Elements</span></span>

<span data-ttu-id="9d96f-107">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="9d96f-107">The following sections describe attributes, child elements, and parent elements.</span></span>

### <a name="attributes"></a><span data-ttu-id="9d96f-108">特性</span><span class="sxs-lookup"><span data-stu-id="9d96f-108">Attributes</span></span>

|<span data-ttu-id="9d96f-109">特性</span><span class="sxs-lookup"><span data-stu-id="9d96f-109">Attribute</span></span>|<span data-ttu-id="9d96f-110">描述</span><span class="sxs-lookup"><span data-stu-id="9d96f-110">Description</span></span>|
|---------------|-----------------|
|`href`|<span data-ttu-id="9d96f-111">必需的特性。</span><span class="sxs-lookup"><span data-stu-id="9d96f-111">Required attribute.</span></span><br /><br /> <span data-ttu-id="9d96f-112">指定运行时在哪里可以找到程序集的指定的版本的 URL。</span><span class="sxs-lookup"><span data-stu-id="9d96f-112">Specifies the URL where the runtime can find the specified version of the assembly.</span></span>|
|`version`|<span data-ttu-id="9d96f-113">必需的特性。</span><span class="sxs-lookup"><span data-stu-id="9d96f-113">Required attribute.</span></span><br /><br /> <span data-ttu-id="9d96f-114">指定基本代码适用于程序集的版本。</span><span class="sxs-lookup"><span data-stu-id="9d96f-114">Specifies the version of the assembly the codebase applies to.</span></span> <span data-ttu-id="9d96f-115">程序集版本号的格式*major.minor.build.revision*。</span><span class="sxs-lookup"><span data-stu-id="9d96f-115">The format of an assembly version number is *major.minor.build.revision*.</span></span>|

## <a name="version-attribute"></a><span data-ttu-id="9d96f-116">版本属性</span><span class="sxs-lookup"><span data-stu-id="9d96f-116">version Attribute</span></span>

|<span data-ttu-id="9d96f-117">“值”</span><span class="sxs-lookup"><span data-stu-id="9d96f-117">Value</span></span>|<span data-ttu-id="9d96f-118">描述</span><span class="sxs-lookup"><span data-stu-id="9d96f-118">Description</span></span>|
|-----------|-----------------|
|<span data-ttu-id="9d96f-119">每个部分的版本号的有效值为 0 到 65535。</span><span class="sxs-lookup"><span data-stu-id="9d96f-119">Valid values for each part of the version number are 0 to 65535.</span></span>|<span data-ttu-id="9d96f-120">不适用。</span><span class="sxs-lookup"><span data-stu-id="9d96f-120">Not applicable.</span></span>|

### <a name="child-elements"></a><span data-ttu-id="9d96f-121">子元素</span><span class="sxs-lookup"><span data-stu-id="9d96f-121">Child Elements</span></span>

<span data-ttu-id="9d96f-122">无。</span><span class="sxs-lookup"><span data-stu-id="9d96f-122">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="9d96f-123">父元素</span><span class="sxs-lookup"><span data-stu-id="9d96f-123">Parent Elements</span></span>

|<span data-ttu-id="9d96f-124">元素</span><span class="sxs-lookup"><span data-stu-id="9d96f-124">Element</span></span>|<span data-ttu-id="9d96f-125">描述</span><span class="sxs-lookup"><span data-stu-id="9d96f-125">Description</span></span>|
|-------------|-----------------|
|`buildproviders`|<span data-ttu-id="9d96f-126">定义用于编译自定义资源文件的生成提供程序的集合。</span><span class="sxs-lookup"><span data-stu-id="9d96f-126">Defines a collection of build providers used to compile custom resource files.</span></span> <span data-ttu-id="9d96f-127">您可以拥有任意数量的生成提供程序。</span><span class="sxs-lookup"><span data-stu-id="9d96f-127">You can have any number of build providers.</span></span>|
|`compilation`|<span data-ttu-id="9d96f-128">配置 ASP.NET 使用的所有编译设置。</span><span class="sxs-lookup"><span data-stu-id="9d96f-128">Configures all the compilation settings that ASP.NET uses.</span></span>|
|`configuration`|<span data-ttu-id="9d96f-129">公共语言运行时和 .NET Framework 应用程序所使用的每个配置文件中的根元素。</span><span class="sxs-lookup"><span data-stu-id="9d96f-129">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|
|`System.web`|<span data-ttu-id="9d96f-130">为 ASP.NET 配置节指定根元素。</span><span class="sxs-lookup"><span data-stu-id="9d96f-130">Specifies the root element for the ASP.NET configuration section.</span></span>|

## <a name="remarks"></a><span data-ttu-id="9d96f-131">备注</span><span class="sxs-lookup"><span data-stu-id="9d96f-131">Remarks</span></span>

<span data-ttu-id="9d96f-132">运行时要使用 **\<b a s e >** 设置计算机配置文件或发布服务器策略文件中，该文件还必须重定向程序集版本。</span><span class="sxs-lookup"><span data-stu-id="9d96f-132">For the runtime to use the **\<codeBase>** setting in a machine configuration file or publisher policy file, the file must also redirect the assembly version.</span></span> <span data-ttu-id="9d96f-133">应用程序配置文件而无需将程序集版本重定向有基本代码设置。</span><span class="sxs-lookup"><span data-stu-id="9d96f-133">Application configuration files can have a codebase setting without redirecting the assembly version.</span></span> <span data-ttu-id="9d96f-134">在确定要使用的程序集版本之后, 运行时应用确定版本的文件的基本代码设置。</span><span class="sxs-lookup"><span data-stu-id="9d96f-134">After determining which assembly version to use, the runtime applies the codebase setting from the file that determines the version.</span></span> <span data-ttu-id="9d96f-135">如果指示没有基本代码，运行时探测程序集以通常的方式。</span><span class="sxs-lookup"><span data-stu-id="9d96f-135">If no codebase is indicated, the runtime probes for the assembly in the usual way.</span></span>

<span data-ttu-id="9d96f-136">如果该程序集具有强名称，基本代码设置可以是任意位置在本地 intranet 或 Internet 上。</span><span class="sxs-lookup"><span data-stu-id="9d96f-136">If the assembly has a strong name, the codebase setting can be anywhere on the local intranet or the Internet.</span></span> <span data-ttu-id="9d96f-137">如果程序集私有程序集，基本代码设置必须为应用程序的目录的相对路径。</span><span class="sxs-lookup"><span data-stu-id="9d96f-137">If the assembly is a private assembly, the codebase setting must be a path relative to the application's directory.</span></span>

<span data-ttu-id="9d96f-138">对于没有强名称程序集，则忽略版本和加载程序将使用出现的第一个\<o d e b > 内\<dependentAssembly >。</span><span class="sxs-lookup"><span data-stu-id="9d96f-138">For assemblies without a strong name, version is ignored and the loader uses the first appearance of \<codebase> inside \<dependentAssembly>.</span></span> <span data-ttu-id="9d96f-139">如果在将绑定重定向到另一个程序集的应用程序配置文件中没有条目，因此重定向即使程序集版本不匹配绑定请求将优先。</span><span class="sxs-lookup"><span data-stu-id="9d96f-139">If there is an entry in the application configuration file that redirects binding to another assembly, the redirection will take precedence even if the assembly version doesn't match the binding request.</span></span>

## <a name="example"></a><span data-ttu-id="9d96f-140">示例</span><span class="sxs-lookup"><span data-stu-id="9d96f-140">Example</span></span>

<span data-ttu-id="9d96f-141">下面的示例演示如何指定运行时在何处可以找到程序集。</span><span class="sxs-lookup"><span data-stu-id="9d96f-141">The following example shows how to specify where the runtime can find an assembly.</span></span>

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

## <a name="see-also"></a><span data-ttu-id="9d96f-142">请参阅</span><span class="sxs-lookup"><span data-stu-id="9d96f-142">See also</span></span>

- [<span data-ttu-id="9d96f-143">运行时设置架构</span><span class="sxs-lookup"><span data-stu-id="9d96f-143">Runtime Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/runtime/index.md)
- [<span data-ttu-id="9d96f-144">配置文件架构</span><span class="sxs-lookup"><span data-stu-id="9d96f-144">Configuration File Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/index.md)
- [<span data-ttu-id="9d96f-145">指定程序集的位置</span><span class="sxs-lookup"><span data-stu-id="9d96f-145">Specifying an Assembly's Location</span></span>](../../../../../docs/framework/configure-apps/specify-assembly-location.md)
- [<span data-ttu-id="9d96f-146">运行时如何定位程序集</span><span class="sxs-lookup"><span data-stu-id="9d96f-146">How the Runtime Locates Assemblies</span></span>](../../../../../docs/framework/deployment/how-the-runtime-locates-assemblies.md)
