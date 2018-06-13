---
title: '&lt;基本代码&gt;元素'
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#codeBase
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/runtime/assemblyBinding/dependentAssembly/codeBase
helpviewer_keywords:
- <codeBase> element
- container tags, <codeBase> element
- codeBase element
ms.assetid: d48a3983-2297-43ff-a14d-1f29d3995822
author: mcleblanc
ms.author: markl
manager: markl
ms.openlocfilehash: 3b614546e8ed23cc1a5e169a33fb5878695037ae
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/03/2018
ms.locfileid: "32745989"
---
# <a name="ltcodebasegt-element"></a><span data-ttu-id="6f37f-102">&lt;基本代码&gt;元素</span><span class="sxs-lookup"><span data-stu-id="6f37f-102">&lt;codeBase&gt; Element</span></span>
<span data-ttu-id="6f37f-103">指定公共语言运行时可在其中找到程序集。</span><span class="sxs-lookup"><span data-stu-id="6f37f-103">Specifies where the common language runtime can find an assembly.</span></span>  
  
 <span data-ttu-id="6f37f-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="6f37f-104">\<configuration></span></span>  
<span data-ttu-id="6f37f-105">\<运行时 ></span><span class="sxs-lookup"><span data-stu-id="6f37f-105">\<runtime></span></span>  
<span data-ttu-id="6f37f-106">\<assemblyBinding ></span><span class="sxs-lookup"><span data-stu-id="6f37f-106">\<assemblyBinding></span></span>  
<span data-ttu-id="6f37f-107">\<dependentAssembly ></span><span class="sxs-lookup"><span data-stu-id="6f37f-107">\<dependentAssembly></span></span>  
<span data-ttu-id="6f37f-108">\<基本代码 ></span><span class="sxs-lookup"><span data-stu-id="6f37f-108">\<codeBase></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6f37f-109">语法</span><span class="sxs-lookup"><span data-stu-id="6f37f-109">Syntax</span></span>  
  
```xml  
   <codeBase    
version="Assembly version"  
href="URL of assembly"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="6f37f-110">特性和元素</span><span class="sxs-lookup"><span data-stu-id="6f37f-110">Attributes and Elements</span></span>  
 <span data-ttu-id="6f37f-111">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="6f37f-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="6f37f-112">特性</span><span class="sxs-lookup"><span data-stu-id="6f37f-112">Attributes</span></span>  
  
|<span data-ttu-id="6f37f-113">特性</span><span class="sxs-lookup"><span data-stu-id="6f37f-113">Attribute</span></span>|<span data-ttu-id="6f37f-114">描述</span><span class="sxs-lookup"><span data-stu-id="6f37f-114">Description</span></span>|  
|---------------|-----------------|  
|`href`|<span data-ttu-id="6f37f-115">必需的特性。</span><span class="sxs-lookup"><span data-stu-id="6f37f-115">Required attribute.</span></span><br /><br /> <span data-ttu-id="6f37f-116">指定运行时可在其中找到程序集的指定的版本的 URL。</span><span class="sxs-lookup"><span data-stu-id="6f37f-116">Specifies the URL where the runtime can find the specified version of the assembly.</span></span>|  
|`version`|<span data-ttu-id="6f37f-117">必需的特性。</span><span class="sxs-lookup"><span data-stu-id="6f37f-117">Required attribute.</span></span><br /><br /> <span data-ttu-id="6f37f-118">指定基本代码适用于程序集的版本。</span><span class="sxs-lookup"><span data-stu-id="6f37f-118">Specifies the version of the assembly the codebase applies to.</span></span> <span data-ttu-id="6f37f-119">程序集版本号的格式是*major.minor.build.revision*。</span><span class="sxs-lookup"><span data-stu-id="6f37f-119">The format of an assembly version number is *major.minor.build.revision*.</span></span>|  
  
## <a name="version-attribute"></a><span data-ttu-id="6f37f-120">版本属性</span><span class="sxs-lookup"><span data-stu-id="6f37f-120">version Attribute</span></span>  
  
|<span data-ttu-id="6f37f-121">值</span><span class="sxs-lookup"><span data-stu-id="6f37f-121">Value</span></span>|<span data-ttu-id="6f37f-122">描述</span><span class="sxs-lookup"><span data-stu-id="6f37f-122">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="6f37f-123">每个部分的版本号的有效值为 0 到 65535。</span><span class="sxs-lookup"><span data-stu-id="6f37f-123">Valid values for each part of the version number are 0 to 65535.</span></span>|<span data-ttu-id="6f37f-124">不适用。</span><span class="sxs-lookup"><span data-stu-id="6f37f-124">Not applicable.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="6f37f-125">子元素</span><span class="sxs-lookup"><span data-stu-id="6f37f-125">Child Elements</span></span>  
 <span data-ttu-id="6f37f-126">无。</span><span class="sxs-lookup"><span data-stu-id="6f37f-126">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="6f37f-127">父元素</span><span class="sxs-lookup"><span data-stu-id="6f37f-127">Parent Elements</span></span>  
  
|<span data-ttu-id="6f37f-128">元素</span><span class="sxs-lookup"><span data-stu-id="6f37f-128">Element</span></span>|<span data-ttu-id="6f37f-129">描述</span><span class="sxs-lookup"><span data-stu-id="6f37f-129">Description</span></span>|  
|-------------|-----------------|  
|`buildproviders`|<span data-ttu-id="6f37f-130">定义用于编译自定义资源文件的生成提供程序的集合。</span><span class="sxs-lookup"><span data-stu-id="6f37f-130">Defines a collection of build providers used to compile custom resource files.</span></span> <span data-ttu-id="6f37f-131">您可以拥有任意数量的生成提供程序。</span><span class="sxs-lookup"><span data-stu-id="6f37f-131">You can have any number of build providers.</span></span>|  
|`compilation`|<span data-ttu-id="6f37f-132">配置 ASP.NET 使用的所有编译设置。</span><span class="sxs-lookup"><span data-stu-id="6f37f-132">Configures all the compilation settings that ASP.NET uses.</span></span>|  
|`configuration`|<span data-ttu-id="6f37f-133">公共语言运行时和 .NET Framework 应用程序所使用的每个配置文件中的根元素。</span><span class="sxs-lookup"><span data-stu-id="6f37f-133">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`System.web`|<span data-ttu-id="6f37f-134">为 ASP.NET 配置节指定根元素。</span><span class="sxs-lookup"><span data-stu-id="6f37f-134">Specifies the root element for the ASP.NET configuration section.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="6f37f-135">备注</span><span class="sxs-lookup"><span data-stu-id="6f37f-135">Remarks</span></span>  
 <span data-ttu-id="6f37f-136">若要使用运行时**\<基本代码 >** 设置的计算机配置文件或发布服务器策略文件中，该文件还必须重定向程序集版本。</span><span class="sxs-lookup"><span data-stu-id="6f37f-136">For the runtime to use the **\<codeBase>** setting in a machine configuration file or publisher policy file, the file must also redirect the assembly version.</span></span> <span data-ttu-id="6f37f-137">应用程序配置文件可以具有的基本代码设置，而无需将程序集版本重定向。</span><span class="sxs-lookup"><span data-stu-id="6f37f-137">Application configuration files can have a codebase setting without redirecting the assembly version.</span></span> <span data-ttu-id="6f37f-138">确定要使用的程序集版本时后, 运行时将应用于确定的版本的文件的基本代码设置。</span><span class="sxs-lookup"><span data-stu-id="6f37f-138">After determining which assembly version to use, the runtime applies the codebase setting from the file that determines the version.</span></span> <span data-ttu-id="6f37f-139">如果指示没有基本代码，运行时探测程序集按照通常的方式。</span><span class="sxs-lookup"><span data-stu-id="6f37f-139">If no codebase is indicated, the runtime probes for the assembly in the usual way.</span></span>  
  
 <span data-ttu-id="6f37f-140">如果集具有强名称，可以任意位置是基本代码设置，本地 intranet 或 Internet 上。</span><span class="sxs-lookup"><span data-stu-id="6f37f-140">If the assembly has a strong name, the codebase setting can be anywhere on the local intranet or the Internet.</span></span> <span data-ttu-id="6f37f-141">如果程序集私有程序集，基本代码设置必须是相对于应用程序的目录的路径。</span><span class="sxs-lookup"><span data-stu-id="6f37f-141">If the assembly is a private assembly, the codebase setting must be a path relative to the application's directory.</span></span>  
  
 <span data-ttu-id="6f37f-142">对于没有强名称程序集，将忽略版本和加载程序将使用出现的第一个\<基本代码 > 内\<dependentAssembly >。</span><span class="sxs-lookup"><span data-stu-id="6f37f-142">For assemblies without a strong name, version is ignored and the loader uses the first appearance of \<codebase> inside \<dependentAssembly>.</span></span> <span data-ttu-id="6f37f-143">如果将绑定重定向到另一个程序集的应用程序配置文件中有一个条目，因此重定向即使程序集版本不匹配绑定请求将优先。</span><span class="sxs-lookup"><span data-stu-id="6f37f-143">If there is an entry in the application configuration file that redirects binding to another assembly, the redirection will take precedence even if the assembly version doesnt match the binding request.</span></span>  
  
## <a name="example"></a><span data-ttu-id="6f37f-144">示例</span><span class="sxs-lookup"><span data-stu-id="6f37f-144">Example</span></span>  
 <span data-ttu-id="6f37f-145">下面的示例演示如何指定运行时可在其中找到程序集。</span><span class="sxs-lookup"><span data-stu-id="6f37f-145">The following example shows how to specify where the runtime can find an assembly.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="6f37f-146">请参阅</span><span class="sxs-lookup"><span data-stu-id="6f37f-146">See Also</span></span>  
 [<span data-ttu-id="6f37f-147">运行时设置架构</span><span class="sxs-lookup"><span data-stu-id="6f37f-147">Runtime Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/runtime/index.md)  
 [<span data-ttu-id="6f37f-148">配置文件架构</span><span class="sxs-lookup"><span data-stu-id="6f37f-148">Configuration File Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/index.md)  
 [<span data-ttu-id="6f37f-149">指定程序集的位置</span><span class="sxs-lookup"><span data-stu-id="6f37f-149">Specifying an Assembly's Location</span></span>](../../../../../docs/framework/configure-apps/specify-assembly-location.md)  
 [<span data-ttu-id="6f37f-150">运行时如何定位程序集</span><span class="sxs-lookup"><span data-stu-id="6f37f-150">How the Runtime Locates Assemblies</span></span>](../../../../../docs/framework/deployment/how-the-runtime-locates-assemblies.md)
