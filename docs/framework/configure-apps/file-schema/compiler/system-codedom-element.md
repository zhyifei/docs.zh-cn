---
title: < System.codedom > 元素
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.codedom
- http://schemas.microsoft.com/.NetConfiguration/v2.0#system.codedom
helpviewer_keywords:
- compiler configuration elements, <system.codedom> element
- system.codedom element
- <system.codedom> element
ms.assetid: 672a68f7-e69f-4479-ac30-e980085ec4fe
ms.openlocfilehash: e2c65044b99e2d5fda7025f24d1d4c4082ded4ec
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/30/2019
ms.locfileid: "55268218"
---
# <a name="systemcodedom-element"></a><span data-ttu-id="092b8-102">\<system.codedom > 元素</span><span class="sxs-lookup"><span data-stu-id="092b8-102">\<system.codedom> Element</span></span>
<span data-ttu-id="092b8-103">指定可用语言提供程序的编译器配置设置。</span><span class="sxs-lookup"><span data-stu-id="092b8-103">Specifies compiler configuration settings for available language providers.</span></span>  
  
 <span data-ttu-id="092b8-104">\<配置 > 元素</span><span class="sxs-lookup"><span data-stu-id="092b8-104">\<configuration> Element</span></span>  
<span data-ttu-id="092b8-105">\<system.codedom > 元素</span><span class="sxs-lookup"><span data-stu-id="092b8-105">\<system.codedom> Element</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="092b8-106">语法</span><span class="sxs-lookup"><span data-stu-id="092b8-106">Syntax</span></span>  
  
```xml  
<system.codedom>  
  <compilers> ... </compilers>  
</system.codedom>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="092b8-107">特性和元素</span><span class="sxs-lookup"><span data-stu-id="092b8-107">Attributes and Elements</span></span>  
 <span data-ttu-id="092b8-108">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="092b8-108">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="092b8-109">特性</span><span class="sxs-lookup"><span data-stu-id="092b8-109">Attributes</span></span>  
 <span data-ttu-id="092b8-110">无。</span><span class="sxs-lookup"><span data-stu-id="092b8-110">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="092b8-111">子元素</span><span class="sxs-lookup"><span data-stu-id="092b8-111">Child Elements</span></span>  
  
|<span data-ttu-id="092b8-112">元素</span><span class="sxs-lookup"><span data-stu-id="092b8-112">Element</span></span>|<span data-ttu-id="092b8-113">描述</span><span class="sxs-lookup"><span data-stu-id="092b8-113">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="092b8-114">\<compilers></span><span class="sxs-lookup"><span data-stu-id="092b8-114">\<compilers></span></span>](../../../../../docs/framework/configure-apps/file-schema/compiler/compilers-element.md)|<span data-ttu-id="092b8-115">编译器配置元素的容器；包含零个或多个 [\<compiler>](../../../../../docs/framework/configure-apps/file-schema/compiler/compiler-element.md) 元素。</span><span class="sxs-lookup"><span data-stu-id="092b8-115">Container for compiler configuration elements; contains zero or more [\<compiler>](../../../../../docs/framework/configure-apps/file-schema/compiler/compiler-element.md) elements.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="092b8-116">父元素</span><span class="sxs-lookup"><span data-stu-id="092b8-116">Parent Elements</span></span>  
  
|<span data-ttu-id="092b8-117">元素</span><span class="sxs-lookup"><span data-stu-id="092b8-117">Element</span></span>|<span data-ttu-id="092b8-118">描述</span><span class="sxs-lookup"><span data-stu-id="092b8-118">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="092b8-119">\<configuration></span><span class="sxs-lookup"><span data-stu-id="092b8-119">\<configuration></span></span>](../../../../../docs/framework/configure-apps/file-schema/configuration-element.md)|<span data-ttu-id="092b8-120">公共语言运行时和 .NET Framework 应用程序所使用的每个配置文件中的根元素。</span><span class="sxs-lookup"><span data-stu-id="092b8-120">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="092b8-121">备注</span><span class="sxs-lookup"><span data-stu-id="092b8-121">Remarks</span></span>  
  
## <a name="net-framework-version-20"></a><span data-ttu-id="092b8-122">.NET framework 2.0 版</span><span class="sxs-lookup"><span data-stu-id="092b8-122">.NET Framework Version 2.0</span></span>  
 <span data-ttu-id="092b8-123">[ \<System.codedom >](../../../../../docs/framework/configure-apps/file-schema/compiler/system-codedom-element.md)元素包含除了如安装.NET Framework 中，使用的默认提供程序的计算机上安装的语言提供程序的编译器配置设置<xref:Microsoft.CSharp.CSharpCodeProvider>和<xref:Microsoft.VisualBasic.VBCodeProvider>。</span><span class="sxs-lookup"><span data-stu-id="092b8-123">The [\<system.codedom>](../../../../../docs/framework/configure-apps/file-schema/compiler/system-codedom-element.md) element contains compiler configuration settings for language providers installed on a computer in addition to the default providers that are installed with the .NET Framework, such as the <xref:Microsoft.CSharp.CSharpCodeProvider> and the <xref:Microsoft.VisualBasic.VBCodeProvider>.</span></span> <span data-ttu-id="092b8-124">[\<编译器 >](../../../../../docs/framework/configure-apps/file-schema/compiler/compilers-element.md)元素包含零个或多[\<编译器 >](../../../../../docs/framework/configure-apps/file-schema/compiler/compiler-element.md)元素。</span><span class="sxs-lookup"><span data-stu-id="092b8-124">The [\<compilers>](../../../../../docs/framework/configure-apps/file-schema/compiler/compilers-element.md) element contains zero or more [\<compiler>](../../../../../docs/framework/configure-apps/file-schema/compiler/compiler-element.md) elements.</span></span> <span data-ttu-id="092b8-125">每个[\<编译器 >](../../../../../docs/framework/configure-apps/file-schema/compiler/compiler-element.md)元素指定特定的语言提供程序的编译器配置属性。</span><span class="sxs-lookup"><span data-stu-id="092b8-125">Each [\<compiler>](../../../../../docs/framework/configure-apps/file-schema/compiler/compiler-element.md) element specifies the compiler configuration attributes for a specific language provider.</span></span>  
  
 <span data-ttu-id="092b8-126">开发人员和编译器供应商可以将配置设置添加到计算机配置文件 (Machine.config) 用于新<xref:System.CodeDom.Compiler.CodeDomProvider>实现。</span><span class="sxs-lookup"><span data-stu-id="092b8-126">Developers and compiler vendors can add configuration settings to the machine configuration file (Machine.config) for a new <xref:System.CodeDom.Compiler.CodeDomProvider> implementation.</span></span> <span data-ttu-id="092b8-127">使用<xref:System.CodeDom.Compiler.CodeDomProvider.GetAllCompilerInfo%2A?displayProperty=nameWithType>方法以编程方式枚举的默认语言提供程序和语言提供程序标识的计算机上的编译器配置设置。</span><span class="sxs-lookup"><span data-stu-id="092b8-127">Use the <xref:System.CodeDom.Compiler.CodeDomProvider.GetAllCompilerInfo%2A?displayProperty=nameWithType> method to programmatically enumerate both the default language providers and language providers identified by the compiler configuration settings on a computer.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="092b8-128">在.NET framework 1.0 和 1.1 中，在标识提供程序由.NET Framework 提供的默认语言[\<编译器 >](../../../../../docs/framework/configure-apps/file-schema/compiler/compilers-element.md)元素。</span><span class="sxs-lookup"><span data-stu-id="092b8-128">In the .NET Framework versions 1.0 and 1.1, the default language providers supplied by the .NET Framework are identified in the [\<compilers>](../../../../../docs/framework/configure-apps/file-schema/compiler/compilers-element.md) element.</span></span> <span data-ttu-id="092b8-129">在.NET Framework 2.0 版中，默认语言提供程序不识别中[\<编译器 >](../../../../../docs/framework/configure-apps/file-schema/compiler/compilers-element.md)元素，但可以使用枚举<xref:System.CodeDom.Compiler.CodeDomProvider.GetAllCompilerInfo%2A>方法。</span><span class="sxs-lookup"><span data-stu-id="092b8-129">In the .NET Framework version 2.0, the default language providers are not identified in the [\<compilers>](../../../../../docs/framework/configure-apps/file-schema/compiler/compilers-element.md) element, but can be enumerated using the <xref:System.CodeDom.Compiler.CodeDomProvider.GetAllCompilerInfo%2A> method.</span></span>  
  
## <a name="net-framework-versions-10-and-11"></a><span data-ttu-id="092b8-130">.NET framework 1.0 和 1.1 版</span><span class="sxs-lookup"><span data-stu-id="092b8-130">.NET Framework Versions 1.0 and 1.1</span></span>  
 <span data-ttu-id="092b8-131">[ \<System.codedom >](../../../../../docs/framework/configure-apps/file-schema/compiler/system-codedom-element.md)元素包含的计算机上的语言提供程序的编译器配置设置。</span><span class="sxs-lookup"><span data-stu-id="092b8-131">The [\<system.codedom>](../../../../../docs/framework/configure-apps/file-schema/compiler/system-codedom-element.md) element contains the compiler configuration settings for language providers on a computer.</span></span> <span data-ttu-id="092b8-132">[\<编译器 >](../../../../../docs/framework/configure-apps/file-schema/compiler/compilers-element.md)元素包含零个或多[\<编译器 >](../../../../../docs/framework/configure-apps/file-schema/compiler/compiler-element.md)元素。</span><span class="sxs-lookup"><span data-stu-id="092b8-132">The [\<compilers>](../../../../../docs/framework/configure-apps/file-schema/compiler/compilers-element.md) element contains zero or more [\<compiler>](../../../../../docs/framework/configure-apps/file-schema/compiler/compiler-element.md) elements.</span></span> <span data-ttu-id="092b8-133">每个[\<编译器 >](../../../../../docs/framework/configure-apps/file-schema/compiler/compiler-element.md)元素指定特定的语言提供程序的编译器配置属性。</span><span class="sxs-lookup"><span data-stu-id="092b8-133">Each [\<compiler>](../../../../../docs/framework/configure-apps/file-schema/compiler/compiler-element.md) element specifies the compiler configuration attributes for a specific language provider.</span></span>  
  
 <span data-ttu-id="092b8-134">.NET Framework 在计算机配置文件 (Machine.config) 中定义初始编译器设置。</span><span class="sxs-lookup"><span data-stu-id="092b8-134">The .NET Framework defines the initial compiler settings in the machine configuration file (Machine.config).</span></span> <span data-ttu-id="092b8-135">开发人员和编译器供应商可以添加新 <xref:System.CodeDom.Compiler.CodeDomProvider> 实现的配置设置。</span><span class="sxs-lookup"><span data-stu-id="092b8-135">Developers and compiler vendors can add configuration settings for a new <xref:System.CodeDom.Compiler.CodeDomProvider> implementation.</span></span> <span data-ttu-id="092b8-136">使用 <xref:System.CodeDom.Compiler.CodeDomProvider.GetAllCompilerInfo%2A?displayProperty=nameWithType> 方法，以编程方式枚举计算机上的语言提供程序和编译器配置设置。</span><span class="sxs-lookup"><span data-stu-id="092b8-136">Use the <xref:System.CodeDom.Compiler.CodeDomProvider.GetAllCompilerInfo%2A?displayProperty=nameWithType> method to programmatically enumerate language provider and compiler configuration settings on a computer.</span></span>  
  
## <a name="configuration-file"></a><span data-ttu-id="092b8-137">配置文件</span><span class="sxs-lookup"><span data-stu-id="092b8-137">Configuration File</span></span>  
 <span data-ttu-id="092b8-138">计算机配置文件和应用程序配置文件中，可以使用此元素。</span><span class="sxs-lookup"><span data-stu-id="092b8-138">This element can be used in the machine configuration file and the application configuration file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="092b8-139">示例</span><span class="sxs-lookup"><span data-stu-id="092b8-139">Example</span></span>  
 <span data-ttu-id="092b8-140">下面的示例演示了典型的编译器配置。</span><span class="sxs-lookup"><span data-stu-id="092b8-140">The following example illustrates a typical compiler configuration.</span></span>  
  
```xml  
<configuration>  
  <system.codedom>  
    <compilers>  
      <!-- zero or more compiler elements -->  
      <compiler   
        language="c#;cs;csharp"  
        extension=".cs"  
        type="Microsoft.CSharp.CSharpCodeProvider, System,   
          Version=1.0.5000.0, Culture=neutral,   
          PublicKeyToken=b77a5c561934e089"  
        compilerOptions=""  
        warningLevel="1" />  
    </compilers>  
  </system.codedom>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="092b8-141">请参阅</span><span class="sxs-lookup"><span data-stu-id="092b8-141">See also</span></span>
- <xref:System.CodeDom.Compiler.CompilerInfo>
- <xref:System.CodeDom.Compiler.CodeDomProvider>
- [<span data-ttu-id="092b8-142">配置文件架构</span><span class="sxs-lookup"><span data-stu-id="092b8-142">Configuration File Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/index.md)
- [<span data-ttu-id="092b8-143">编译器和语言提供程序设置架构</span><span class="sxs-lookup"><span data-stu-id="092b8-143">Compiler and Language Provider Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/compiler/index.md)
- [<span data-ttu-id="092b8-144">\<compiler> Element</span><span class="sxs-lookup"><span data-stu-id="092b8-144">\<compiler> Element</span></span>](../../../../../docs/framework/configure-apps/file-schema/compiler/compiler-element.md)
