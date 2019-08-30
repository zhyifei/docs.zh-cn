---
title: <compiler> 元素
ms.date: 08/14/2018
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#compiler
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.codedom/compilers/compiler
helpviewer_keywords:
- compiler configuration elements, <compiler> element
- <compiler> element
- compiler configuration attributes
- compiler element
ms.assetid: 7a151659-b803-4c27-b5ce-1c4aa0d5a823
ms.openlocfilehash: a19cf8182cdb338fd8596ef38311916de0daae37
ms.sourcegitcommit: 1b020356e421a9314dd525539da12463d980ce7a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/30/2019
ms.locfileid: "70168945"
---
# <a name="compiler-element"></a><span data-ttu-id="6c04f-102">\<编译器 > 元素</span><span class="sxs-lookup"><span data-stu-id="6c04f-102">\<compiler> Element</span></span>

<span data-ttu-id="6c04f-103">指定语言提供程序的编译器配置属性。</span><span class="sxs-lookup"><span data-stu-id="6c04f-103">Specifies the compiler configuration attributes for a language provider.</span></span>

[<span data-ttu-id="6c04f-104"> **\<configuration>** </span><span class="sxs-lookup"><span data-stu-id="6c04f-104">**\<configuration>**</span></span>](../configuration-element.md)  
<span data-ttu-id="6c04f-105">&nbsp;&nbsp;[ **\<system.object >** ](system-codedom-element.md)</span><span class="sxs-lookup"><span data-stu-id="6c04f-105">&nbsp;&nbsp;[**\<system.codedom>**](system-codedom-element.md)</span></span>  
<span data-ttu-id="6c04f-106">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<编译器 >** ](compilers-element.md)</span><span class="sxs-lookup"><span data-stu-id="6c04f-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<compilers>**](compilers-element.md)</span></span>  
<span data-ttu-id="6c04f-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<编译器 >**</span><span class="sxs-lookup"><span data-stu-id="6c04f-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<compiler>**</span></span>  

## <a name="syntax"></a><span data-ttu-id="6c04f-108">语法</span><span class="sxs-lookup"><span data-stu-id="6c04f-108">Syntax</span></span>

```xml
<compiler
  language="languageName[;...;...]"
  extension="fileExtension[;...;...]"
  type="typeName, assemblyName"
  warningLevel="number"
  compilerOptions="option1 option2"
/>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="6c04f-109">特性和元素</span><span class="sxs-lookup"><span data-stu-id="6c04f-109">Attributes and Elements</span></span>

<span data-ttu-id="6c04f-110">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="6c04f-110">The following sections describe attributes, child elements, and parent elements.</span></span>

### <a name="attributes"></a><span data-ttu-id="6c04f-111">特性</span><span class="sxs-lookup"><span data-stu-id="6c04f-111">Attributes</span></span>

|<span data-ttu-id="6c04f-112">特性</span><span class="sxs-lookup"><span data-stu-id="6c04f-112">Attribute</span></span>|<span data-ttu-id="6c04f-113">描述</span><span class="sxs-lookup"><span data-stu-id="6c04f-113">Description</span></span>|
|---------------|-----------------|
|`compilerOptions`|<span data-ttu-id="6c04f-114">可选特性。</span><span class="sxs-lookup"><span data-stu-id="6c04f-114">Optional attribute.</span></span><br /><br /> <span data-ttu-id="6c04f-115">为编译指定其他特定于编译器的参数。</span><span class="sxs-lookup"><span data-stu-id="6c04f-115">Specifies additional compiler-specific arguments for compilation.</span></span> <span data-ttu-id="6c04f-116">`compilerOptions`特性的值通常在编译器的编译器选项主题中列出。</span><span class="sxs-lookup"><span data-stu-id="6c04f-116">The values for the `compilerOptions` attribute are typically listed in a compiler options topic for the compiler.</span></span>|
|`extension`|<span data-ttu-id="6c04f-117">必需的特性。</span><span class="sxs-lookup"><span data-stu-id="6c04f-117">Required attribute.</span></span><br /><br /> <span data-ttu-id="6c04f-118">提供语言提供程序的源文件所使用的文件扩展名的分号分隔列表。</span><span class="sxs-lookup"><span data-stu-id="6c04f-118">Provides a semicolon-separated list of file name extensions used by source files for the language provider.</span></span> <span data-ttu-id="6c04f-119">例如, ".cs"。</span><span class="sxs-lookup"><span data-stu-id="6c04f-119">For example, ".cs".</span></span>|
|`language`|<span data-ttu-id="6c04f-120">必需的特性。</span><span class="sxs-lookup"><span data-stu-id="6c04f-120">Required attribute.</span></span><br /><br /> <span data-ttu-id="6c04f-121">提供语言提供程序支持的语言名称的分号分隔列表。</span><span class="sxs-lookup"><span data-stu-id="6c04f-121">Provides a semicolon-separated list of language names supported by the language provider.</span></span> <span data-ttu-id="6c04f-122">例如, "c #; cs; csharp"。</span><span class="sxs-lookup"><span data-stu-id="6c04f-122">For example, "c#;cs;csharp".</span></span>|
|`type`|<span data-ttu-id="6c04f-123">必需的特性。</span><span class="sxs-lookup"><span data-stu-id="6c04f-123">Required attribute.</span></span><br /><br /> <span data-ttu-id="6c04f-124">指定语言提供程序的类型名称, 包括包含提供程序实现的程序集的名称。</span><span class="sxs-lookup"><span data-stu-id="6c04f-124">Specifies the type name of the language provider, including the name of the assembly containing the provider implementation.</span></span> <span data-ttu-id="6c04f-125">类型名称必须满足[指定完全限定的类型名称](../../../reflection-and-codedom/specifying-fully-qualified-type-names.md)中定义的要求。</span><span class="sxs-lookup"><span data-stu-id="6c04f-125">The type name must meet the requirements defined in [Specifying Fully Qualified Type Names](../../../reflection-and-codedom/specifying-fully-qualified-type-names.md).</span></span>|
|`warningLevel`|<span data-ttu-id="6c04f-126">可选特性。</span><span class="sxs-lookup"><span data-stu-id="6c04f-126">Optional attribute.</span></span><br /><br /> <span data-ttu-id="6c04f-127">指定默认编译器警告等级;确定语言提供程序将编译警告视为错误的级别。</span><span class="sxs-lookup"><span data-stu-id="6c04f-127">Specifies the default compiler warning level; determines the level at which the language provider treats compilation warnings as errors.</span></span>|

### <a name="child-elements"></a><span data-ttu-id="6c04f-128">子元素</span><span class="sxs-lookup"><span data-stu-id="6c04f-128">Child Elements</span></span>

|<span data-ttu-id="6c04f-129">元素</span><span class="sxs-lookup"><span data-stu-id="6c04f-129">Element</span></span>|<span data-ttu-id="6c04f-130">描述</span><span class="sxs-lookup"><span data-stu-id="6c04f-130">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="6c04f-131">\<providerOption > 元素</span><span class="sxs-lookup"><span data-stu-id="6c04f-131">\<providerOption> Element</span></span>](provideroption-element.md)|<span data-ttu-id="6c04f-132">指定语言提供程序的编译器版本特性。</span><span class="sxs-lookup"><span data-stu-id="6c04f-132">Specifies compiler version attributes for a language provider.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="6c04f-133">父元素</span><span class="sxs-lookup"><span data-stu-id="6c04f-133">Parent Elements</span></span>

|<span data-ttu-id="6c04f-134">元素</span><span class="sxs-lookup"><span data-stu-id="6c04f-134">Element</span></span>|<span data-ttu-id="6c04f-135">描述</span><span class="sxs-lookup"><span data-stu-id="6c04f-135">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="6c04f-136">\<configuration> 元素</span><span class="sxs-lookup"><span data-stu-id="6c04f-136">\<configuration> Element</span></span>](../configuration-element.md)|<span data-ttu-id="6c04f-137">公共语言运行时和 .NET Framework 应用程序所使用的每个配置文件中的根元素。</span><span class="sxs-lookup"><span data-stu-id="6c04f-137">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|
|[<span data-ttu-id="6c04f-138">\<system.object > 元素</span><span class="sxs-lookup"><span data-stu-id="6c04f-138">\<system.codedom> Element</span></span>](system-codedom-element.md)|<span data-ttu-id="6c04f-139">指定可用语言提供程序的编译器配置设置。</span><span class="sxs-lookup"><span data-stu-id="6c04f-139">Specifies compiler configuration settings for available language providers.</span></span>|
|[<span data-ttu-id="6c04f-140">\<编译器 > 元素</span><span class="sxs-lookup"><span data-stu-id="6c04f-140">\<compilers> Element</span></span>](compilers-element.md)|<span data-ttu-id="6c04f-141">编译器配置元素的容器;包含零个或`<compiler>`多个元素。</span><span class="sxs-lookup"><span data-stu-id="6c04f-141">Container for compiler configuration elements; contains zero or more `<compiler>` elements.</span></span>|

## <a name="remarks"></a><span data-ttu-id="6c04f-142">备注</span><span class="sxs-lookup"><span data-stu-id="6c04f-142">Remarks</span></span>

<span data-ttu-id="6c04f-143">每`<compiler>`个元素指定特定语言提供程序的编译器配置特性。</span><span class="sxs-lookup"><span data-stu-id="6c04f-143">Each `<compiler>` element specifies the compiler configuration attributes for a specific language provider.</span></span> <span data-ttu-id="6c04f-144">提供程序为特定<xref:System.CodeDom.Compiler.CodeDomProvider?displayProperty=nameWithType>语言扩展了类`<compiler>` ; 元素定义了语言提供程序的编译器和代码生成器设置。</span><span class="sxs-lookup"><span data-stu-id="6c04f-144">The provider extends the <xref:System.CodeDom.Compiler.CodeDomProvider?displayProperty=nameWithType> class for a specific language; the `<compiler>` element defines the compiler and code generator settings for the language provider.</span></span>

<span data-ttu-id="6c04f-145">.NET Framework 在计算机配置文件 (Machine.config) 中定义初始编译器设置。</span><span class="sxs-lookup"><span data-stu-id="6c04f-145">The .NET Framework defines the initial compiler settings in the machine configuration file (Machine.config).</span></span> <span data-ttu-id="6c04f-146">开发人员和编译器供应商可以添加新 <xref:System.CodeDom.Compiler.CodeDomProvider> 实现的配置设置。</span><span class="sxs-lookup"><span data-stu-id="6c04f-146">Developers and compiler vendors can add configuration settings for a new <xref:System.CodeDom.Compiler.CodeDomProvider> implementation.</span></span> <span data-ttu-id="6c04f-147">使用 <xref:System.CodeDom.Compiler.CodeDomProvider.GetAllCompilerInfo%2A?displayProperty=nameWithType> 方法，以编程方式枚举计算机上的语言提供程序和编译器配置设置。</span><span class="sxs-lookup"><span data-stu-id="6c04f-147">Use the <xref:System.CodeDom.Compiler.CodeDomProvider.GetAllCompilerInfo%2A?displayProperty=nameWithType> method to programmatically enumerate language provider and compiler configuration settings on a computer.</span></span>

<span data-ttu-id="6c04f-148">应用程序或 Web 配置文件中的编译器元素可以补充或覆盖计算机配置文件中的设置。</span><span class="sxs-lookup"><span data-stu-id="6c04f-148">Compiler elements in the application or Web configuration file can supplement or override the settings in the machine configuration file.</span></span> <span data-ttu-id="6c04f-149">如果为相同的语言名称或相同的文件扩展名配置了多个提供程序实现, 则最后一个匹配配置会重写该语言名称或文件扩展名的任何以前配置的提供程序。</span><span class="sxs-lookup"><span data-stu-id="6c04f-149">If more than one provider implementation is configured for the same language name or the same file extension, the last matching configuration overrides any previous configured providers for that language name or file extension.</span></span>

## <a name="configuration-file"></a><span data-ttu-id="6c04f-150">配置文件</span><span class="sxs-lookup"><span data-stu-id="6c04f-150">Configuration File</span></span>

<span data-ttu-id="6c04f-151">此元素可在计算机配置文件和应用程序配置文件中使用。</span><span class="sxs-lookup"><span data-stu-id="6c04f-151">This element can be used in the machine configuration file and the application configuration file.</span></span>

## <a name="example"></a><span data-ttu-id="6c04f-152">示例</span><span class="sxs-lookup"><span data-stu-id="6c04f-152">Example</span></span>

<span data-ttu-id="6c04f-153">下面的示例演示了一个典型的编译器配置元素:</span><span class="sxs-lookup"><span data-stu-id="6c04f-153">The following example illustrates a typical compiler configuration element:</span></span>

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

## <a name="see-also"></a><span data-ttu-id="6c04f-154">请参阅</span><span class="sxs-lookup"><span data-stu-id="6c04f-154">See also</span></span>

- <xref:System.CodeDom.Compiler.CompilerInfo>
- <xref:System.CodeDom.Compiler.CodeDomProvider>
- [<span data-ttu-id="6c04f-155">配置文件架构</span><span class="sxs-lookup"><span data-stu-id="6c04f-155">Configuration File Schema</span></span>](../index.md)
- [<span data-ttu-id="6c04f-156">\<编译器 > 元素</span><span class="sxs-lookup"><span data-stu-id="6c04f-156">\<compilers> Element</span></span>](compilers-element.md)
- [<span data-ttu-id="6c04f-157">指定完全限定的类型名称</span><span class="sxs-lookup"><span data-stu-id="6c04f-157">Specifying Fully Qualified Type Names</span></span>](../../../reflection-and-codedom/specifying-fully-qualified-type-names.md)
- <span data-ttu-id="6c04f-158">[用于编译的编译器的编译器元素 (ASP.NET 设置架构)](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/a15ebt6c(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="6c04f-158">[compiler Element for compilers for compilation (ASP.NET Settings Schema)](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/a15ebt6c(v=vs.100))</span></span>
