---
title: "&lt;assemblyBinding&gt;元素&lt;运行时&gt;"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/runtime/assemblyBinding
helpviewer_keywords:
- <assemblyBinding> element
- assemblyBinding element
- container tags, <assemblyBinding> element
ms.assetid: 964cbb35-ab49-4498-8471-209689e5dada
caps.latest.revision: "13"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: fdf2bc90c496c9906b5d31bad0065e01bdb47942
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="ltassemblybindinggt-element-for-ltruntimegt"></a><span data-ttu-id="2a0e5-102">&lt;assemblyBinding&gt;元素&lt;运行时&gt;</span><span class="sxs-lookup"><span data-stu-id="2a0e5-102">&lt;assemblyBinding&gt; Element for &lt;runtime&gt;</span></span>
<span data-ttu-id="2a0e5-103">包含有关程序集版本重定向和程序集位置的信息。</span><span class="sxs-lookup"><span data-stu-id="2a0e5-103">Contains information about assembly version redirection and the locations of assemblies.</span></span>  
  
 <span data-ttu-id="2a0e5-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="2a0e5-104">\<configuration></span></span>  
<span data-ttu-id="2a0e5-105">\<运行时 ></span><span class="sxs-lookup"><span data-stu-id="2a0e5-105">\<runtime></span></span>  
<span data-ttu-id="2a0e5-106">\<assemblyBinding ></span><span class="sxs-lookup"><span data-stu-id="2a0e5-106">\<assemblyBinding></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2a0e5-107">语法</span><span class="sxs-lookup"><span data-stu-id="2a0e5-107">Syntax</span></span>  
  
```xml  
      <assemblyBinding    
   xmlns="urn:schemas-microsoft-com:asm.v1" appliesTo="v1.0.3705">  
</assemblyBinding>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="2a0e5-108">特性和元素</span><span class="sxs-lookup"><span data-stu-id="2a0e5-108">Attributes and Elements</span></span>  
 <span data-ttu-id="2a0e5-109">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="2a0e5-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="2a0e5-110">特性</span><span class="sxs-lookup"><span data-stu-id="2a0e5-110">Attributes</span></span>  
  
|<span data-ttu-id="2a0e5-111">特性</span><span class="sxs-lookup"><span data-stu-id="2a0e5-111">Attribute</span></span>|<span data-ttu-id="2a0e5-112">描述</span><span class="sxs-lookup"><span data-stu-id="2a0e5-112">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="2a0e5-113">**xmlns**</span><span class="sxs-lookup"><span data-stu-id="2a0e5-113">**xmlns**</span></span>|<span data-ttu-id="2a0e5-114">必需的特性。</span><span class="sxs-lookup"><span data-stu-id="2a0e5-114">Required attribute.</span></span><br /><br /> <span data-ttu-id="2a0e5-115">指定程序集绑定所需的 XML 命名空间。</span><span class="sxs-lookup"><span data-stu-id="2a0e5-115">Specifies the XML namespace required for assembly binding.</span></span> <span data-ttu-id="2a0e5-116">使用字符串“urn: 架构-microsoft-com:asm.v1”作为值。</span><span class="sxs-lookup"><span data-stu-id="2a0e5-116">Use the string "urn:schemas-microsoft-com:asm.v1" as the value.</span></span>|  
|<span data-ttu-id="2a0e5-117">**appliesTo**</span><span class="sxs-lookup"><span data-stu-id="2a0e5-117">**appliesTo**</span></span>|<span data-ttu-id="2a0e5-118">指定 .NET Framework 程序集重定向适用的运行时版本。</span><span class="sxs-lookup"><span data-stu-id="2a0e5-118">Specifies the runtime version the .NET Framework assembly redirection applies to.</span></span> <span data-ttu-id="2a0e5-119">此可选特性用 .NET Framework 版本号来指示其适用的版本。</span><span class="sxs-lookup"><span data-stu-id="2a0e5-119">This optional attribute uses a .NET Framework version number to indicate what version it applies to.</span></span> <span data-ttu-id="2a0e5-120">如果没有指定 appliesTo 特性，\<assemblyBinding> 元素将适用于 .NET Framework 的所有版本。</span><span class="sxs-lookup"><span data-stu-id="2a0e5-120">If no **appliesTo** attribute is specified, the **\<assemblyBinding>** element applies to all versions of the .NET Framework.</span></span> <span data-ttu-id="2a0e5-121">**AppliesTo** .NET Framework 1.1 版中引入了属性; 它由.NET Framework 1.0 版将被忽略。</span><span class="sxs-lookup"><span data-stu-id="2a0e5-121">The **appliesTo** attribute was introduced in .NET Framework version 1.1; it is ignored by the .NET Framework version 1.0.</span></span> <span data-ttu-id="2a0e5-122">这意味着，即使指定了 appliesTo 特性，在使用 .NET Framework 1.0 版时所有的 \<assemblyBinding> 元素也都适用。</span><span class="sxs-lookup"><span data-stu-id="2a0e5-122">This means that all **\<assemblyBinding>** elements are applied when using the .NET Framework version 1.0, even if an **appliesTo** attribute is specified.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="2a0e5-123">子元素</span><span class="sxs-lookup"><span data-stu-id="2a0e5-123">Child Elements</span></span>  
  
|<span data-ttu-id="2a0e5-124">元素</span><span class="sxs-lookup"><span data-stu-id="2a0e5-124">Element</span></span>|<span data-ttu-id="2a0e5-125">描述</span><span class="sxs-lookup"><span data-stu-id="2a0e5-125">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="2a0e5-126">\<dependentAssembly></span><span class="sxs-lookup"><span data-stu-id="2a0e5-126">\<dependentAssembly></span></span>](../../../../../docs/framework/configure-apps/file-schema/runtime/dependentassembly-element.md)|<span data-ttu-id="2a0e5-127">封装程序集的绑定策略和程序集位置。</span><span class="sxs-lookup"><span data-stu-id="2a0e5-127">Encapsulates binding policy and assembly location for an assembly.</span></span> <span data-ttu-id="2a0e5-128">使用一个 **\<dependentAssembly >**标记每个程序集。</span><span class="sxs-lookup"><span data-stu-id="2a0e5-128">Use one **\<dependentAssembly>** tag for each assembly.</span></span>|  
|[<span data-ttu-id="2a0e5-129">\<probing></span><span class="sxs-lookup"><span data-stu-id="2a0e5-129">\<probing></span></span>](../../../../../docs/framework/configure-apps/file-schema/runtime/probing-element.md)|<span data-ttu-id="2a0e5-130">指定加载程序集时公共语言运行时搜索的子目录。</span><span class="sxs-lookup"><span data-stu-id="2a0e5-130">Specifies subdirectories the common language runtime searches when loading assemblies.</span></span>|  
|[<span data-ttu-id="2a0e5-131">\<publisherPolicy></span><span class="sxs-lookup"><span data-stu-id="2a0e5-131">\<publisherPolicy></span></span>](../../../../../docs/framework/configure-apps/file-schema/runtime/publisherpolicy-element.md)|<span data-ttu-id="2a0e5-132">指定运行时是否使用发布者策略。</span><span class="sxs-lookup"><span data-stu-id="2a0e5-132">Specifies whether the runtime applies publisher policy.</span></span>|  
|[<span data-ttu-id="2a0e5-133">\<qualifyAssembly></span><span class="sxs-lookup"><span data-stu-id="2a0e5-133">\<qualifyAssembly></span></span>](../../../../../docs/framework/configure-apps/file-schema/runtime/qualifyassembly-element.md)|<span data-ttu-id="2a0e5-134">指定使用部分名称时应动态加载的程序集全名。</span><span class="sxs-lookup"><span data-stu-id="2a0e5-134">Specifies the full name of the assembly that should be dynamically loaded when a partial name is used.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="2a0e5-135">父元素</span><span class="sxs-lookup"><span data-stu-id="2a0e5-135">Parent Elements</span></span>  
  
|<span data-ttu-id="2a0e5-136">元素</span><span class="sxs-lookup"><span data-stu-id="2a0e5-136">Element</span></span>|<span data-ttu-id="2a0e5-137">描述</span><span class="sxs-lookup"><span data-stu-id="2a0e5-137">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="2a0e5-138">公共语言运行时和 .NET Framework 应用程序所使用的每个配置文件中的根元素。</span><span class="sxs-lookup"><span data-stu-id="2a0e5-138">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="2a0e5-139">包含有关程序集绑定和垃圾回收的信息。</span><span class="sxs-lookup"><span data-stu-id="2a0e5-139">Contains information about assembly binding and garbage collection.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="2a0e5-140">示例</span><span class="sxs-lookup"><span data-stu-id="2a0e5-140">Example</span></span>  
 <span data-ttu-id="2a0e5-141">下面的示例显示如何将一个程序集版本重定向到另一个版本并提供基本代码。</span><span class="sxs-lookup"><span data-stu-id="2a0e5-141">The following example shows how to redirect one assembly version to another and provide a codebase.</span></span>  
  
```xml  
<configuration>  
   <runtime>  
      <assemblyBinding xmlns="urn:schemas-microsoft-com:asm.v1">  
         <dependentAssembly>  
            <assemblyIdentity name="myAssembly"  
                              publicKeyToken="32ab4ba45e0a69a1"  
                              culture="neutral" />  
            <bindingRedirect oldVersion="1.0.0.0"  
                             newVersion="2.0.0.0"/>  
            <codeBase version="2.0.0.0"  
                      href="http://www.litwareinc.com/myAssembly.dll"/>  
         </dependentAssembly>  
      </assemblyBinding>  
   </runtime>  
</configuration>  
```  
  
 <span data-ttu-id="2a0e5-142">下面的示例演示如何使用**appliesTo**属性重定向.NET Framework 程序集的绑定。</span><span class="sxs-lookup"><span data-stu-id="2a0e5-142">The following example shows how to use the **appliesTo** attribute to redirect binding of a .NET Framework assembly.</span></span>  
  
```xml  
<runtime>  
   <assemblyBinding xmlns="urn:schemas-microsoft-com:asm.v1" appliesTo="v1.0.3705">  
      <dependentAssembly>   
         <assemblyIdentity name="mscorcfg" publicKeyToken="b03f5f7f11d50a3a" culture=""/>  
         <bindingRedirect oldVersion="0.0.0.0-65535.65535.65535.65535" newVersion="1.0.3300.0"/>  
      </dependentAssembly>  
   </assemblyBinding>  
</runtime>  
```  
  
## <a name="see-also"></a><span data-ttu-id="2a0e5-143">另请参阅</span><span class="sxs-lookup"><span data-stu-id="2a0e5-143">See Also</span></span>  
 [<span data-ttu-id="2a0e5-144">运行时设置架构</span><span class="sxs-lookup"><span data-stu-id="2a0e5-144">Runtime Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/runtime/index.md)  
 [<span data-ttu-id="2a0e5-145">配置文件架构</span><span class="sxs-lookup"><span data-stu-id="2a0e5-145">Configuration File Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/index.md)  
 [<span data-ttu-id="2a0e5-146">重定向程序集版本</span><span class="sxs-lookup"><span data-stu-id="2a0e5-146">Redirecting Assembly Versions</span></span>](../../../../../docs/framework/configure-apps/redirect-assembly-versions.md)
