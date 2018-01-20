---
title: "&lt;编译器&gt;元素"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#compiler
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.codedom/compilers/compiler
helpviewer_keywords:
- compiler configuration elements, <compiler> element
- <compiler> element
- compiler configuration attributes
- compiler element
ms.assetid: 7a151659-b803-4c27-b5ce-1c4aa0d5a823
caps.latest.revision: "20"
author: mcleblanc
ms.author: markl
manager: markl
ms.workload: dotnet
ms.openlocfilehash: 547c08e324066b872abb8df8b8b780ab3e4644a7
ms.sourcegitcommit: c0dd436f6f8f44dc80dc43b07f6841a00b74b23f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/19/2018
---
# <a name="ltcompilergt-element"></a><span data-ttu-id="1a7bd-102">&lt;编译器&gt;元素</span><span class="sxs-lookup"><span data-stu-id="1a7bd-102">&lt;compiler&gt; Element</span></span>
<span data-ttu-id="1a7bd-103">指定语言提供程序的编译器配置属性。</span><span class="sxs-lookup"><span data-stu-id="1a7bd-103">Specifies the compiler configuration attributes for a language provider.</span></span>  
  
 <span data-ttu-id="1a7bd-104">\<配置元素 ></span><span class="sxs-lookup"><span data-stu-id="1a7bd-104">\<configuration Element></span></span>  
<span data-ttu-id="1a7bd-105">\<system.codedom Element></span><span class="sxs-lookup"><span data-stu-id="1a7bd-105">\<system.codedom Element></span></span>  
<span data-ttu-id="1a7bd-106">\<编译器元素 ></span><span class="sxs-lookup"><span data-stu-id="1a7bd-106">\<compilers Element></span></span>  
<span data-ttu-id="1a7bd-107">\<编译器 > 元素</span><span class="sxs-lookup"><span data-stu-id="1a7bd-107">\<compiler> Element</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1a7bd-108">语法</span><span class="sxs-lookup"><span data-stu-id="1a7bd-108">Syntax</span></span>  
  
```xml  
<compiler  
  language="languageName[;...;...]"  
  extension="fileExtension[;...;...]"  
  type="typeName, assemblyName"  
  warningLevel="number"  
  compilerOptions="option1 option2"  
/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="1a7bd-109">特性和元素</span><span class="sxs-lookup"><span data-stu-id="1a7bd-109">Attributes and Elements</span></span>  
 <span data-ttu-id="1a7bd-110">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="1a7bd-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="1a7bd-111">特性</span><span class="sxs-lookup"><span data-stu-id="1a7bd-111">Attributes</span></span>  
  
|<span data-ttu-id="1a7bd-112">特性</span><span class="sxs-lookup"><span data-stu-id="1a7bd-112">Attribute</span></span>|<span data-ttu-id="1a7bd-113">描述</span><span class="sxs-lookup"><span data-stu-id="1a7bd-113">Description</span></span>|  
|---------------|-----------------|  
|`compilerOptions`|<span data-ttu-id="1a7bd-114">可选特性。</span><span class="sxs-lookup"><span data-stu-id="1a7bd-114">Optional attribute.</span></span><br /><br /> <span data-ttu-id="1a7bd-115">指定用于编译的其他编译器特定参数。</span><span class="sxs-lookup"><span data-stu-id="1a7bd-115">Specifies additional compiler-specific arguments for compilation.</span></span> <span data-ttu-id="1a7bd-116">值`compilerOptions`属性通常编译器编译器选项主题中列出。</span><span class="sxs-lookup"><span data-stu-id="1a7bd-116">The values for the `compilerOptions` attribute are typically listed in a compiler options topic for the compiler.</span></span> <span data-ttu-id="1a7bd-117">在 Visual Studio 2005 文档中，你可以通过查找索引中的"编译器选项"中找到编译器选项。</span><span class="sxs-lookup"><span data-stu-id="1a7bd-117">In the Visual Studio 2005 documentation, you can locate the options for the compiler by looking for "compiler options" in the index.</span></span>|  
|`extension`|<span data-ttu-id="1a7bd-118">必需的特性。</span><span class="sxs-lookup"><span data-stu-id="1a7bd-118">Required attribute.</span></span><br /><br /> <span data-ttu-id="1a7bd-119">提供以分号分隔的文件使用的源的语言提供程序的文件扩展名的列表。</span><span class="sxs-lookup"><span data-stu-id="1a7bd-119">Provides a semicolon-separated list of file name extensions used by source files for the language provider.</span></span> <span data-ttu-id="1a7bd-120">例如，".cs"。</span><span class="sxs-lookup"><span data-stu-id="1a7bd-120">For example, ".cs".</span></span>|  
|`language`|<span data-ttu-id="1a7bd-121">必需的特性。</span><span class="sxs-lookup"><span data-stu-id="1a7bd-121">Required attribute.</span></span><br /><br /> <span data-ttu-id="1a7bd-122">提供的语言提供程序支持的语言名称之间用分号分隔的列表。</span><span class="sxs-lookup"><span data-stu-id="1a7bd-122">Provides a semicolon-separated list of language names supported by the language provider.</span></span> <span data-ttu-id="1a7bd-123">例如，"c#; cs; csharp"。</span><span class="sxs-lookup"><span data-stu-id="1a7bd-123">For example, "c#;cs;csharp".</span></span>|  
|`type`|<span data-ttu-id="1a7bd-124">必需的特性。</span><span class="sxs-lookup"><span data-stu-id="1a7bd-124">Required attribute.</span></span><br /><br /> <span data-ttu-id="1a7bd-125">指定语言提供程序，包括包含的提供程序实现的程序集名称的类型名称。</span><span class="sxs-lookup"><span data-stu-id="1a7bd-125">Specifies the type name of the language provider, including the name of the assembly containing the provider implementation.</span></span> <span data-ttu-id="1a7bd-126">类型名称必须满足中定义的要求[指定完全限定的类型名称](../../../../../docs/framework/reflection-and-codedom/specifying-fully-qualified-type-names.md)。</span><span class="sxs-lookup"><span data-stu-id="1a7bd-126">The type name must meet the requirements defined in [Specifying Fully Qualified Type Names](../../../../../docs/framework/reflection-and-codedom/specifying-fully-qualified-type-names.md).</span></span>|  
|`warningLevel`|<span data-ttu-id="1a7bd-127">可选特性。</span><span class="sxs-lookup"><span data-stu-id="1a7bd-127">Optional attribute.</span></span><br /><br /> <span data-ttu-id="1a7bd-128">指定默认的编译器警告等级;确定在该语言提供程序将编译警告视为错误的级别。</span><span class="sxs-lookup"><span data-stu-id="1a7bd-128">Specifies the default compiler warning level; determines the level at which the language provider treats compilation warnings as errors.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="1a7bd-129">子元素</span><span class="sxs-lookup"><span data-stu-id="1a7bd-129">Child Elements</span></span>  
  
|<span data-ttu-id="1a7bd-130">元素</span><span class="sxs-lookup"><span data-stu-id="1a7bd-130">Element</span></span>|<span data-ttu-id="1a7bd-131">描述</span><span class="sxs-lookup"><span data-stu-id="1a7bd-131">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="1a7bd-132">\<providerOption > 元素</span><span class="sxs-lookup"><span data-stu-id="1a7bd-132">\<providerOption> Element</span></span>](../../../../../docs/framework/configure-apps/file-schema/compiler/provideroption-element.md)|<span data-ttu-id="1a7bd-133">指定语言提供程序的编译器版本特性。</span><span class="sxs-lookup"><span data-stu-id="1a7bd-133">Specifies compiler version attributes for a language provider.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="1a7bd-134">父元素</span><span class="sxs-lookup"><span data-stu-id="1a7bd-134">Parent Elements</span></span>  
  
|<span data-ttu-id="1a7bd-135">元素</span><span class="sxs-lookup"><span data-stu-id="1a7bd-135">Element</span></span>|<span data-ttu-id="1a7bd-136">描述</span><span class="sxs-lookup"><span data-stu-id="1a7bd-136">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="1a7bd-137">\<configuration> 元素</span><span class="sxs-lookup"><span data-stu-id="1a7bd-137">\<configuration> Element</span></span>](../../../../../docs/framework/configure-apps/file-schema/configuration-element.md)|<span data-ttu-id="1a7bd-138">公共语言运行时和 .NET Framework 应用程序所使用的每个配置文件中的根元素。</span><span class="sxs-lookup"><span data-stu-id="1a7bd-138">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|[<span data-ttu-id="1a7bd-139">\<system.codedom> Element</span><span class="sxs-lookup"><span data-stu-id="1a7bd-139">\<system.codedom> Element</span></span>](../../../../../docs/framework/configure-apps/file-schema/compiler/system-codedom-element.md)|<span data-ttu-id="1a7bd-140">指定可用语言提供程序的编译器配置设置。</span><span class="sxs-lookup"><span data-stu-id="1a7bd-140">Specifies compiler configuration settings for available language providers.</span></span>|  
|[<span data-ttu-id="1a7bd-141">\<编译器 > 元素</span><span class="sxs-lookup"><span data-stu-id="1a7bd-141">\<compilers> Element</span></span>](../../../../../docs/framework/configure-apps/file-schema/compiler/compilers-element.md)|<span data-ttu-id="1a7bd-142">编译器配置元素，则容器包含零个或多`<compiler>`元素。</span><span class="sxs-lookup"><span data-stu-id="1a7bd-142">Container for compiler configuration elements; contains zero or more `<compiler>` elements.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="1a7bd-143">备注</span><span class="sxs-lookup"><span data-stu-id="1a7bd-143">Remarks</span></span>  
 <span data-ttu-id="1a7bd-144">每个`<compiler>`元素指定特定的语言提供程序的编译器配置特性。</span><span class="sxs-lookup"><span data-stu-id="1a7bd-144">Each `<compiler>` element specifies the compiler configuration attributes for a specific language provider.</span></span> <span data-ttu-id="1a7bd-145">提供程序扩展<xref:System.CodeDom.Compiler.CodeDomProvider?displayProperty=nameWithType>类特定的语言;`<compiler>`元素定义的编译器和语言提供程序的代码生成器设置。</span><span class="sxs-lookup"><span data-stu-id="1a7bd-145">The provider extends the <xref:System.CodeDom.Compiler.CodeDomProvider?displayProperty=nameWithType> class for a specific language; the `<compiler>` element defines the compiler and code generator settings for the language provider.</span></span>  
  
 <span data-ttu-id="1a7bd-146">.NET Framework 在计算机配置文件 (Machine.config) 中定义初始编译器设置。</span><span class="sxs-lookup"><span data-stu-id="1a7bd-146">The .NET Framework defines the initial compiler settings in the machine configuration file (Machine.config).</span></span> <span data-ttu-id="1a7bd-147">开发人员和编译器供应商可以添加新 <xref:System.CodeDom.Compiler.CodeDomProvider> 实现的配置设置。</span><span class="sxs-lookup"><span data-stu-id="1a7bd-147">Developers and compiler vendors can add configuration settings for a new <xref:System.CodeDom.Compiler.CodeDomProvider> implementation.</span></span> <span data-ttu-id="1a7bd-148">使用 <xref:System.CodeDom.Compiler.CodeDomProvider.GetAllCompilerInfo%2A?displayProperty=nameWithType> 方法，以编程方式枚举计算机上的语言提供程序和编译器配置设置。</span><span class="sxs-lookup"><span data-stu-id="1a7bd-148">Use the <xref:System.CodeDom.Compiler.CodeDomProvider.GetAllCompilerInfo%2A?displayProperty=nameWithType> method to programmatically enumerate language provider and compiler configuration settings on a computer.</span></span>  
  
 <span data-ttu-id="1a7bd-149">在应用程序或 Web 配置文件的编译器元素可以补充或重写计算机配置文件中的设置。</span><span class="sxs-lookup"><span data-stu-id="1a7bd-149">Compiler elements in the application or Web configuration file can supplement or override the settings in the machine configuration file.</span></span> <span data-ttu-id="1a7bd-150">如果为相同的语言名称或相同的文件扩展名配置了多个提供程序实现，最后一个匹配的配置将覆盖任何以前的配置提供程序对这种语言名称或文件扩展名。</span><span class="sxs-lookup"><span data-stu-id="1a7bd-150">If more than one provider implementation is configured for the same language name or the same file extension, the last matching configuration overrides any previous configured providers for that language name or file extension.</span></span>  
  
## <a name="configuration-file"></a><span data-ttu-id="1a7bd-151">配置文件</span><span class="sxs-lookup"><span data-stu-id="1a7bd-151">Configuration File</span></span>  
 <span data-ttu-id="1a7bd-152">计算机配置文件和应用程序配置文件中，可以使用此元素。</span><span class="sxs-lookup"><span data-stu-id="1a7bd-152">This element can be used in the machine configuration file and the application configuration file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="1a7bd-153">示例</span><span class="sxs-lookup"><span data-stu-id="1a7bd-153">Example</span></span>  
 <span data-ttu-id="1a7bd-154">以下示例说明典型的编译器配置元素。</span><span class="sxs-lookup"><span data-stu-id="1a7bd-154">The following example illustrates a typical compiler configuration element.</span></span>  
  
```xml  
<configuration>  
  <system.codedom>  
    <compilers>  
      <!-- zero or more compiler elements -->  
      <compiler  
        language="c#;cs;csharp"  
        extension=".cs"  
        type="Microsoft.CSharp.CSharpCodeProvider, System,   
          Version=2.0.3600.0, Culture=neutral,   
          PublicKeyToken=b77a5c561934e089"  
        compilerOptions="/optimize"  
        warningLevel="1" />  
    </compilers>  
  </system.codedom>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="1a7bd-155">请参阅</span><span class="sxs-lookup"><span data-stu-id="1a7bd-155">See Also</span></span>  
 <xref:System.CodeDom.Compiler.CompilerInfo>  
 <xref:System.CodeDom.Compiler.CodeDomProvider>  
 [<span data-ttu-id="1a7bd-156">配置文件架构</span><span class="sxs-lookup"><span data-stu-id="1a7bd-156">Configuration File Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/index.md)  
 [<span data-ttu-id="1a7bd-157">\<编译器 > 元素</span><span class="sxs-lookup"><span data-stu-id="1a7bd-157">\<compilers> Element</span></span>](../../../../../docs/framework/configure-apps/file-schema/compiler/compilers-element.md)  
 [<span data-ttu-id="1a7bd-158">指定完全限定的类型名称</span><span class="sxs-lookup"><span data-stu-id="1a7bd-158">Specifying Fully Qualified Type Names</span></span>](../../../../../docs/framework/reflection-and-codedom/specifying-fully-qualified-type-names.md)  
 [<span data-ttu-id="1a7bd-159">编译器进行编译 （ASP.NET 设置架构） 使用的编译器元素</span><span class="sxs-lookup"><span data-stu-id="1a7bd-159">compiler Element for compilers for compilation (ASP.NET Settings Schema)</span></span>](http://msdn.microsoft.com/library/f7d6b078-5d42-4134-b3f7-62e1aba1df1e)
