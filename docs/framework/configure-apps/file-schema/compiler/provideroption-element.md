---
title: <providerOption> 元素
ms.date: 03/30/2017
f1_keywords:
- provideroption
helpviewer_keywords:
- <provideroption> element
- providerOptions
- provideroption element
ms.assetid: 014f2e0b-c0b5-4fc4-92d3-73f02978b2a1
ms.openlocfilehash: 9c69ea7bf95b311a796ec29d90410a77b748c3c6
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "61705319"
---
# <a name="provideroption-element"></a><span data-ttu-id="f63cb-102">\<providerOption > 元素</span><span class="sxs-lookup"><span data-stu-id="f63cb-102">\<providerOption> Element</span></span>
<span data-ttu-id="f63cb-103">指定语言提供程序的编译器版本特性。</span><span class="sxs-lookup"><span data-stu-id="f63cb-103">Specifies the compiler version attributes for a language provider.</span></span>  
  
 <span data-ttu-id="f63cb-104">\<配置元素 ></span><span class="sxs-lookup"><span data-stu-id="f63cb-104">\<configuration Element></span></span>  
<span data-ttu-id="f63cb-105">\<system.codedom 元素 ></span><span class="sxs-lookup"><span data-stu-id="f63cb-105">\<system.codedom Element></span></span>  
<span data-ttu-id="f63cb-106">\<compilers 元素 ></span><span class="sxs-lookup"><span data-stu-id="f63cb-106">\<compilers Element></span></span>  
<span data-ttu-id="f63cb-107">\<编译器 > 元素</span><span class="sxs-lookup"><span data-stu-id="f63cb-107">\<compiler> Element</span></span>  
<span data-ttu-id="f63cb-108">\<providerOption > 元素</span><span class="sxs-lookup"><span data-stu-id="f63cb-108">\<providerOption> Element</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f63cb-109">语法</span><span class="sxs-lookup"><span data-stu-id="f63cb-109">Syntax</span></span>  
  
```xml  
<providerOption  
  name="option-name"  
  value="option-value"  
/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="f63cb-110">特性和元素</span><span class="sxs-lookup"><span data-stu-id="f63cb-110">Attributes and Elements</span></span>  
 <span data-ttu-id="f63cb-111">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="f63cb-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="f63cb-112">特性</span><span class="sxs-lookup"><span data-stu-id="f63cb-112">Attributes</span></span>  
  
|<span data-ttu-id="f63cb-113">特性</span><span class="sxs-lookup"><span data-stu-id="f63cb-113">Attribute</span></span>|<span data-ttu-id="f63cb-114">描述</span><span class="sxs-lookup"><span data-stu-id="f63cb-114">Description</span></span>|  
|---------------|-----------------|  
|`name`|<span data-ttu-id="f63cb-115">必需的特性。</span><span class="sxs-lookup"><span data-stu-id="f63cb-115">Required attribute.</span></span><br /><br /> <span data-ttu-id="f63cb-116">指定的选项; 的名称例如，"CompilerVersion"。</span><span class="sxs-lookup"><span data-stu-id="f63cb-116">Specifies the name of the option; for example, "CompilerVersion".</span></span>|  
|`value`|<span data-ttu-id="f63cb-117">必需的特性。</span><span class="sxs-lookup"><span data-stu-id="f63cb-117">Required attribute.</span></span><br /><br /> <span data-ttu-id="f63cb-118">指定选项; 的值例如，"v3.5"。</span><span class="sxs-lookup"><span data-stu-id="f63cb-118">Specifies the value for the option; for example, "v3.5".</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="f63cb-119">子元素</span><span class="sxs-lookup"><span data-stu-id="f63cb-119">Child Elements</span></span>  
 <span data-ttu-id="f63cb-120">无。</span><span class="sxs-lookup"><span data-stu-id="f63cb-120">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="f63cb-121">父元素</span><span class="sxs-lookup"><span data-stu-id="f63cb-121">Parent Elements</span></span>  
  
|<span data-ttu-id="f63cb-122">元素</span><span class="sxs-lookup"><span data-stu-id="f63cb-122">Element</span></span>|<span data-ttu-id="f63cb-123">描述</span><span class="sxs-lookup"><span data-stu-id="f63cb-123">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="f63cb-124">\<configuration> 元素</span><span class="sxs-lookup"><span data-stu-id="f63cb-124">\<configuration> Element</span></span>](../../../../../docs/framework/configure-apps/file-schema/configuration-element.md)|<span data-ttu-id="f63cb-125">公共语言运行库和 .NET Framework 应用程序所使用的每个配置文件中的根元素。</span><span class="sxs-lookup"><span data-stu-id="f63cb-125">The root element in every configuration file that is used by the common language runtime and .NET Framework applications.</span></span>|  
|[<span data-ttu-id="f63cb-126">\<system.codedom > 元素</span><span class="sxs-lookup"><span data-stu-id="f63cb-126">\<system.codedom> Element</span></span>](../../../../../docs/framework/configure-apps/file-schema/compiler/system-codedom-element.md)|<span data-ttu-id="f63cb-127">指定可用语言提供程序的编译器配置设置。</span><span class="sxs-lookup"><span data-stu-id="f63cb-127">Specifies compiler configuration settings for available language providers.</span></span>|  
|[<span data-ttu-id="f63cb-128">\<编译器 > 元素</span><span class="sxs-lookup"><span data-stu-id="f63cb-128">\<compilers> Element</span></span>](../../../../../docs/framework/configure-apps/file-schema/compiler/compilers-element.md)|<span data-ttu-id="f63cb-129">编译器配置元素; 容器包含零个或多`<compiler>`元素。</span><span class="sxs-lookup"><span data-stu-id="f63cb-129">Container for compiler configuration elements; contains zero or more `<compiler>` elements.</span></span>|  
|[<span data-ttu-id="f63cb-130">\<compiler> Element</span><span class="sxs-lookup"><span data-stu-id="f63cb-130">\<compiler> Element</span></span>](../../../../../docs/framework/configure-apps/file-schema/compiler/compiler-element.md)|<span data-ttu-id="f63cb-131">指定语言提供程序的编译器配置属性。</span><span class="sxs-lookup"><span data-stu-id="f63cb-131">Specifies the compiler configuration attributes for a language provider.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="f63cb-132">备注</span><span class="sxs-lookup"><span data-stu-id="f63cb-132">Remarks</span></span>  
 <span data-ttu-id="f63cb-133">在.NET Framework 版本 3.5 中，代码文档对象模型 (CodeDOM) 的代码提供程序可以支持特定于提供程序的选项通过使用`<providerOption>`元素。</span><span class="sxs-lookup"><span data-stu-id="f63cb-133">In the .NET Framework version 3.5, Code Document Object Model (CodeDOM) code providers can support provider-specific options by using the `<providerOption>` element.</span></span>  
  
 <span data-ttu-id="f63cb-134">.NET Framework 3.5 包括更新的.NET Framework 2.0 程序集，并提供包含新类型的新版本 3.5 程序集。</span><span class="sxs-lookup"><span data-stu-id="f63cb-134">The .NET Framework 3.5 includes updated .NET Framework 2.0 assemblies and provides new version 3.5 assemblies that contain new types.</span></span> <span data-ttu-id="f63cb-135">Microsoft C# 和 Visual Basic 代码提供程序包含在.NET Framework 2.0 程序集，但已更新，以支持版本 3.5 编译器。</span><span class="sxs-lookup"><span data-stu-id="f63cb-135">The Microsoft C# and Visual Basic code providers are contained in .NET Framework 2.0 assemblies but have been updated to support version 3.5 compilers.</span></span> <span data-ttu-id="f63cb-136">默认情况下，更新后的代码提供程序生成为版本 2.0 编译器的代码。</span><span class="sxs-lookup"><span data-stu-id="f63cb-136">By default, the updated code providers generate code for version 2.0 compilers.</span></span> <span data-ttu-id="f63cb-137">可以使用`<providerOption>`元素更改目标编译器版本为 3.5。</span><span class="sxs-lookup"><span data-stu-id="f63cb-137">You can use the `<providerOption>` element to change the target compiler version to 3.5.</span></span> <span data-ttu-id="f63cb-138">若要执行此操作，指定"CompilerVersion"对于`name`属性和"v3.5"为`value`属性。</span><span class="sxs-lookup"><span data-stu-id="f63cb-138">To do this, specify "CompilerVersion" for the `name` attribute and "v3.5" for the `value` attribute.</span></span> <span data-ttu-id="f63cb-139">必须在之前使用小写字母"v"的版本号。</span><span class="sxs-lookup"><span data-stu-id="f63cb-139">You must precede the version number with a lower-case "v".</span></span>  
  
 <span data-ttu-id="f63cb-140">您可以使版本规范全局通过添加`<providerOption>`到.NET Framework 2.0 Machine.config 或根 Web.config 文件的元素。</span><span class="sxs-lookup"><span data-stu-id="f63cb-140">You can make the version specification global by adding the `<providerOption>` element to the .NET Framework 2.0 Machine.config or root Web.config file.</span></span> <span data-ttu-id="f63cb-141">默认编译器版本更新至 3.5 在 Machine.config 文件中时，如果您可以将其更改回为 2.0 基于每个应用程序使用`<providerOption>`应用程序配置文件中的元素。</span><span class="sxs-lookup"><span data-stu-id="f63cb-141">If you update the default compiler version to 3.5 in the Machine.config file, you can change it back to 2.0 on a per-application basis by using the `<providerOption>` element in the application configuration file.</span></span>  
  
 <span data-ttu-id="f63cb-142">CodeDOM 代码提供程序实施者可以通过提供的构造函数来处理自定义选项`providerOptions`类型的参数<xref:System.Collections.Generic.IDictionary%602>。</span><span class="sxs-lookup"><span data-stu-id="f63cb-142">CodeDOM code provider implementers can process custom options by providing a constructor that takes a `providerOptions` parameter of type <xref:System.Collections.Generic.IDictionary%602>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="f63cb-143">示例</span><span class="sxs-lookup"><span data-stu-id="f63cb-143">Example</span></span>  
 <span data-ttu-id="f63cb-144">下面的示例演示如何指定应使用 3.5 版的 C# 代码提供程序。</span><span class="sxs-lookup"><span data-stu-id="f63cb-144">The following example demonstrates how to specify that version 3.5 of the C# code provider should be used.</span></span>  
  
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
        warningLevel="1" >  
          <providerOption  
            name="CompilerVersion"  
            value="v3.5" />  
      </compiler>  
    </compilers>  
  </system.codedom>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="f63cb-145">请参阅</span><span class="sxs-lookup"><span data-stu-id="f63cb-145">See also</span></span>

- <xref:System.CodeDom.Compiler.CompilerInfo>
- <xref:System.CodeDom.Compiler.CodeDomProvider>
- [<span data-ttu-id="f63cb-146">配置文件架构</span><span class="sxs-lookup"><span data-stu-id="f63cb-146">Configuration File Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/index.md)
- [<span data-ttu-id="f63cb-147">\<编译器 > 元素</span><span class="sxs-lookup"><span data-stu-id="f63cb-147">\<compilers> Element</span></span>](../../../../../docs/framework/configure-apps/file-schema/compiler/compilers-element.md)
- [<span data-ttu-id="f63cb-148">指定完全限定的类型名称</span><span class="sxs-lookup"><span data-stu-id="f63cb-148">Specifying Fully Qualified Type Names</span></span>](../../../../../docs/framework/reflection-and-codedom/specifying-fully-qualified-type-names.md)
- <span data-ttu-id="f63cb-149">[（ASP.NET 设置架构） compilation 的 compilers 的 compiler 元素](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/a15ebt6c(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="f63cb-149">[compiler Element for compilers for compilation (ASP.NET Settings Schema)](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/a15ebt6c(v=vs.100))</span></span>
