---
title: <runtime> 的 <assemblyIdentity> 元素
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/runtime/assemblyBinding/dependentAssembly/assemblyIdentity
- http://schemas.microsoft.com/.NetConfiguration/v2.0#assemblyIdentity
helpviewer_keywords:
- <assemblyIdentity> element
- container tags, <assemblyIdentity> element
- assemblyIdentity element
ms.assetid: cea4d187-6398-4da4-af09-c1abc6a349c1
ms.openlocfilehash: b026dafbde796bbd8726de56b532ed6710ba2290
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2020
ms.locfileid: "79154304"
---
# <a name="assemblyidentity-element-for-runtime"></a><span data-ttu-id="c0862-102">\<用于运行时>的\<程序集标识>元素</span><span class="sxs-lookup"><span data-stu-id="c0862-102">\<assemblyIdentity> Element for \<runtime></span></span>
<span data-ttu-id="c0862-103">包含有关程序集的标识信息。</span><span class="sxs-lookup"><span data-stu-id="c0862-103">Contains identifying information about the assembly.</span></span>  
  
<span data-ttu-id="c0862-104">[**\<配置>**](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="c0862-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="c0862-105">&nbsp;&nbsp;[**\<运行时>**](runtime-element.md)</span><span class="sxs-lookup"><span data-stu-id="c0862-105">&nbsp;&nbsp;[**\<runtime>**](runtime-element.md)</span></span>\
<span data-ttu-id="c0862-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<程序集绑定>**](assemblybinding-element-for-runtime.md)</span><span class="sxs-lookup"><span data-stu-id="c0862-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<assemblyBinding>**](assemblybinding-element-for-runtime.md)</span></span>\
<span data-ttu-id="c0862-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<从属装配>**](dependentassembly-element.md)</span><span class="sxs-lookup"><span data-stu-id="c0862-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<dependentAssembly>**](dependentassembly-element.md)</span></span>\
<span data-ttu-id="c0862-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<程序集标识>**</span><span class="sxs-lookup"><span data-stu-id="c0862-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<assemblyIdentity>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c0862-109">语法</span><span class="sxs-lookup"><span data-stu-id="c0862-109">Syntax</span></span>  
  
```xml  
   <assemblyIdentity
name="assembly name"  
publicKeyToken="public key token"  
culture="assembly culture"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="c0862-110">特性和元素</span><span class="sxs-lookup"><span data-stu-id="c0862-110">Attributes and Elements</span></span>  
 <span data-ttu-id="c0862-111">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="c0862-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="c0862-112">属性</span><span class="sxs-lookup"><span data-stu-id="c0862-112">Attributes</span></span>  
  
|<span data-ttu-id="c0862-113">Attribute</span><span class="sxs-lookup"><span data-stu-id="c0862-113">Attribute</span></span>|<span data-ttu-id="c0862-114">说明</span><span class="sxs-lookup"><span data-stu-id="c0862-114">Description</span></span>|  
|---------------|-----------------|  
|`name`|<span data-ttu-id="c0862-115">必需的特性。</span><span class="sxs-lookup"><span data-stu-id="c0862-115">Required attribute.</span></span><br /><br /> <span data-ttu-id="c0862-116">程序集的名称</span><span class="sxs-lookup"><span data-stu-id="c0862-116">The name of the assembly</span></span>|  
|`culture`|<span data-ttu-id="c0862-117">可选特性。</span><span class="sxs-lookup"><span data-stu-id="c0862-117">Optional attribute.</span></span><br /><br /> <span data-ttu-id="c0862-118">指定程序集的语言和国家/区域的字符串。</span><span class="sxs-lookup"><span data-stu-id="c0862-118">A string that specifies the language and country/region of the assembly.</span></span>|  
|`publicKeyToken`|<span data-ttu-id="c0862-119">可选特性。</span><span class="sxs-lookup"><span data-stu-id="c0862-119">Optional attribute.</span></span><br /><br /> <span data-ttu-id="c0862-120">指定程序集的强名称的十六进制值。</span><span class="sxs-lookup"><span data-stu-id="c0862-120">A hexadecimal value that specifies the strong name of the assembly.</span></span>|  
|`processorArchitecture`|<span data-ttu-id="c0862-121">可选特性。</span><span class="sxs-lookup"><span data-stu-id="c0862-121">Optional attribute.</span></span><br /><br /> <span data-ttu-id="c0862-122">值"x86"、"amd64"、"msil"或"ia64"的值之一，指定包含特定于处理器代码的程序集的处理器体系结构。</span><span class="sxs-lookup"><span data-stu-id="c0862-122">One of the values "x86", "amd64", "msil", or "ia64", specifying the processor architecture for an assembly that contains processor-specific code.</span></span> <span data-ttu-id="c0862-123">这些值不区分大小写。</span><span class="sxs-lookup"><span data-stu-id="c0862-123">The values are not case-sensitive.</span></span> <span data-ttu-id="c0862-124">如果为该属性分配了任何其他值，则忽略`<assemblyIdentity>`整个元素。</span><span class="sxs-lookup"><span data-stu-id="c0862-124">If the attribute is assigned any other value, the entire `<assemblyIdentity>` element is ignored.</span></span> <span data-ttu-id="c0862-125">请参阅 <xref:System.Reflection.ProcessorArchitecture>。</span><span class="sxs-lookup"><span data-stu-id="c0862-125">See <xref:System.Reflection.ProcessorArchitecture>.</span></span>|  
  
## <a name="processorarchitecture-attribute"></a><span data-ttu-id="c0862-126">处理器体系结构属性</span><span class="sxs-lookup"><span data-stu-id="c0862-126">processorArchitecture Attribute</span></span>  
  
|<span data-ttu-id="c0862-127">值</span><span class="sxs-lookup"><span data-stu-id="c0862-127">Value</span></span>|<span data-ttu-id="c0862-128">说明</span><span class="sxs-lookup"><span data-stu-id="c0862-128">Description</span></span>|  
|-----------|-----------------|  
|`amd64`|<span data-ttu-id="c0862-129">仅限 AMD x86-64 架构。</span><span class="sxs-lookup"><span data-stu-id="c0862-129">AMD x86-64 architecture only.</span></span>|  
|`ia64`|<span data-ttu-id="c0862-130">仅限英特尔 Itanium 架构。</span><span class="sxs-lookup"><span data-stu-id="c0862-130">Intel Itanium architecture only.</span></span>|  
|`msil`|<span data-ttu-id="c0862-131">不特定于处理器和每字位数。</span><span class="sxs-lookup"><span data-stu-id="c0862-131">Neutral with respect to processor and bits-per-word.</span></span>|  
|`x86`|<span data-ttu-id="c0862-132">32 位 x86 处理器，本机处理器或 Windows 上 Windows （WOW） 环境中的 64 位平台。</span><span class="sxs-lookup"><span data-stu-id="c0862-132">A 32-bit x86 processor, either native or in the Windows on Windows (WOW) environment on a 64-bit platform.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="c0862-133">子元素</span><span class="sxs-lookup"><span data-stu-id="c0862-133">Child Elements</span></span>  
 <span data-ttu-id="c0862-134">无。</span><span class="sxs-lookup"><span data-stu-id="c0862-134">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="c0862-135">父元素</span><span class="sxs-lookup"><span data-stu-id="c0862-135">Parent Elements</span></span>  
  
|<span data-ttu-id="c0862-136">元素</span><span class="sxs-lookup"><span data-stu-id="c0862-136">Element</span></span>|<span data-ttu-id="c0862-137">说明</span><span class="sxs-lookup"><span data-stu-id="c0862-137">Description</span></span>|  
|-------------|-----------------|  
|`assemblyBinding`|<span data-ttu-id="c0862-138">包含有关程序集版本重定向和程序集位置的信息。</span><span class="sxs-lookup"><span data-stu-id="c0862-138">Contains information about assembly version redirection and the locations of assemblies.</span></span>|  
|`configuration`|<span data-ttu-id="c0862-139">公共语言运行时和 .NET Framework 应用程序所使用的每个配置文件中的根元素。</span><span class="sxs-lookup"><span data-stu-id="c0862-139">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`dependentAssembly`|<span data-ttu-id="c0862-140">封装每个程序集的绑定策略和程序集位置。</span><span class="sxs-lookup"><span data-stu-id="c0862-140">Encapsulates binding policy and assembly location for each assembly.</span></span> <span data-ttu-id="c0862-141">为每个程序集`<dependentAssembly>`使用一个元素。</span><span class="sxs-lookup"><span data-stu-id="c0862-141">Use one `<dependentAssembly>` element for each assembly.</span></span>|  
|`runtime`|<span data-ttu-id="c0862-142">包含有关程序集绑定和垃圾回收的信息。</span><span class="sxs-lookup"><span data-stu-id="c0862-142">Contains information about assembly binding and garbage collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="c0862-143">备注</span><span class="sxs-lookup"><span data-stu-id="c0862-143">Remarks</span></span>  
 <span data-ttu-id="c0862-144">每个**\<从属程序集>** 元素必须具有一个**\<程序集标识>** 子元素。</span><span class="sxs-lookup"><span data-stu-id="c0862-144">Every **\<dependentAssembly>** element must have one **\<assemblyIdentity>** child element.</span></span>  
  
 <span data-ttu-id="c0862-145">如果存在该`processorArchitecture`属性，则`<assemblyIdentity>`该元素仅适用于具有相应处理器体系结构的程序集。</span><span class="sxs-lookup"><span data-stu-id="c0862-145">If the `processorArchitecture` attribute is present, the `<assemblyIdentity>` element applies only to the assembly with the corresponding processor architecture.</span></span> <span data-ttu-id="c0862-146">如果属性`processorArchitecture`不存在，则`<assemblyIdentity>`元素可以应用于具有任何处理器体系结构的程序集。</span><span class="sxs-lookup"><span data-stu-id="c0862-146">If the `processorArchitecture` attribute is not present, the `<assemblyIdentity>` element can apply to an assembly with any processor architecture.</span></span>  
  
 <span data-ttu-id="c0862-147">下面的示例显示了两个具有相同名称的程序集的配置文件，该文件针对的是两个不同的两个不同的处理器体系结构，并且其版本尚未同步维护。当应用程序在 x86 平台上执行时，将`<assemblyIdentity>`应用第一个元素，忽略另一个元素。</span><span class="sxs-lookup"><span data-stu-id="c0862-147">The following example shows a configuration file for two assemblies with the same name that target two different two processor architectures, and whose versions have not been maintained in synch. When the application executes on the x86 platform the first `<assemblyIdentity>` element applies and the other is ignored.</span></span> <span data-ttu-id="c0862-148">如果应用程序在 x86 或 ia64 以外的平台上执行，则两者都将被忽略。</span><span class="sxs-lookup"><span data-stu-id="c0862-148">If the application executes on a platform other than x86 or ia64, both are ignored.</span></span>  
  
```xml  
<configuration>  
   <runtime>  
      <assemblyBinding xmlns="urn:schemas-microsoft-com:asm.v1">  
         <dependentAssembly>  
            <assemblyIdentity name="MyAssembly"  
                  publicKeyToken="14a739be0244c389"  
                  culture="neutral"  
                  processorArchitecture="x86" />  
            <bindingRedirect oldVersion= "1.0.0.0"
                  newVersion="1.1.0.0" />  
         </dependentAssembly>  
         <dependentAssembly>  
            <assemblyIdentity name="MyAssembly"  
                  publicKeyToken="14a739be0244c389"  
                  culture="neutral"
                  processorArchitecture="ia64" />  
            <bindingRedirect oldVersion="1.0.0.0"
                  newVersion="2.0.0.0" />  
         </dependentAssembly>  
      </assemblyBinding>  
   </runtime>  
</configuration>  
```  
  
 <span data-ttu-id="c0862-149">如果配置文件包含没有`<assemblyIdentity>``processorArchitecture`属性的元素，并且不包含与平台匹配的元素，则使用没有该`processorArchitecture`属性的元素。</span><span class="sxs-lookup"><span data-stu-id="c0862-149">If a configuration file contains an `<assemblyIdentity>` element with no `processorArchitecture` attribute, and does not contain an element that matches the platform, the element without the `processorArchitecture` attribute is used.</span></span>  
  
## <a name="example"></a><span data-ttu-id="c0862-150">示例</span><span class="sxs-lookup"><span data-stu-id="c0862-150">Example</span></span>  
 <span data-ttu-id="c0862-151">下面的示例演示如何提供有关程序集的信息。</span><span class="sxs-lookup"><span data-stu-id="c0862-151">The following example shows how to provide information about an assembly.</span></span>  
  
```xml  
<configuration>  
   <runtime>  
      <assemblyBinding xmlns="urn:schemas-microsoft-com:asm.v1">  
         <dependentAssembly>  
            <assemblyIdentity name="myAssembly"  
                              publicKeyToken="32ab4ba45e0a69a1"  
                              culture="neutral" />  
            <!--Redirection and codeBase policy for myAssembly.-->  
         </dependentAssembly>  
      </assemblyBinding>  
   </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="c0862-152">另请参阅</span><span class="sxs-lookup"><span data-stu-id="c0862-152">See also</span></span>

- [<span data-ttu-id="c0862-153">运行时设置架构</span><span class="sxs-lookup"><span data-stu-id="c0862-153">Runtime Settings Schema</span></span>](index.md)
- [<span data-ttu-id="c0862-154">配置文件架构</span><span class="sxs-lookup"><span data-stu-id="c0862-154">Configuration File Schema</span></span>](../index.md)
- [<span data-ttu-id="c0862-155">重定向程序集版本</span><span class="sxs-lookup"><span data-stu-id="c0862-155">Redirecting Assembly Versions</span></span>](../../redirect-assembly-versions.md)
