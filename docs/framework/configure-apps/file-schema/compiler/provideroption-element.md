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
ms.openlocfilehash: a6718173e84ecffc4ba0641f6e865e777aa6b1a4
ms.sourcegitcommit: 7f8eeef060ddeb2cabfa52843776faf652c5a1f5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/14/2019
ms.locfileid: "74088676"
---
# <a name="provideroption-element"></a><span data-ttu-id="e9ae2-102">\<providerOption > 元素</span><span class="sxs-lookup"><span data-stu-id="e9ae2-102">\<providerOption> Element</span></span>
<span data-ttu-id="e9ae2-103">指定语言提供程序的编译器版本特性。</span><span class="sxs-lookup"><span data-stu-id="e9ae2-103">Specifies the compiler version attributes for a language provider.</span></span>  

<span data-ttu-id="e9ae2-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="e9ae2-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="e9ae2-105">\<&nbsp;&nbsp;[ **>** ](system-codedom-element.md)</span><span class="sxs-lookup"><span data-stu-id="e9ae2-105">&nbsp;&nbsp;[**\<system.codedom>**](system-codedom-element.md)</span></span>\
<span data-ttu-id="e9ae2-106">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<编译器 >** ](compilers-element.md)</span><span class="sxs-lookup"><span data-stu-id="e9ae2-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<compilers>**](compilers-element.md)</span></span>\
<span data-ttu-id="e9ae2-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;\<[**编译器 >** ](compiler-element.md)</span><span class="sxs-lookup"><span data-stu-id="e9ae2-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<compiler>**](compiler-element.md)</span></span>\
<span data-ttu-id="e9ae2-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<providerOption >**</span><span class="sxs-lookup"><span data-stu-id="e9ae2-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<providerOption>**</span></span>

## <a name="syntax"></a><span data-ttu-id="e9ae2-109">语法</span><span class="sxs-lookup"><span data-stu-id="e9ae2-109">Syntax</span></span>  
  
```xml  
<providerOption  
  name="option-name"  
  value="option-value"  
/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="e9ae2-110">特性和元素</span><span class="sxs-lookup"><span data-stu-id="e9ae2-110">Attributes and Elements</span></span>  
 <span data-ttu-id="e9ae2-111">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="e9ae2-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="e9ae2-112">特性</span><span class="sxs-lookup"><span data-stu-id="e9ae2-112">Attributes</span></span>  
  
|<span data-ttu-id="e9ae2-113">特性</span><span class="sxs-lookup"><span data-stu-id="e9ae2-113">Attribute</span></span>|<span data-ttu-id="e9ae2-114">描述</span><span class="sxs-lookup"><span data-stu-id="e9ae2-114">Description</span></span>|  
|---------------|-----------------|  
|`name`|<span data-ttu-id="e9ae2-115">必需的特性。</span><span class="sxs-lookup"><span data-stu-id="e9ae2-115">Required attribute.</span></span><br /><br /> <span data-ttu-id="e9ae2-116">指定选项的名称;例如 "CompilerVersion"。</span><span class="sxs-lookup"><span data-stu-id="e9ae2-116">Specifies the name of the option; for example, "CompilerVersion".</span></span>|  
|`value`|<span data-ttu-id="e9ae2-117">必需的特性。</span><span class="sxs-lookup"><span data-stu-id="e9ae2-117">Required attribute.</span></span><br /><br /> <span data-ttu-id="e9ae2-118">指定选项的值;例如，"v 3.5"。</span><span class="sxs-lookup"><span data-stu-id="e9ae2-118">Specifies the value for the option; for example, "v3.5".</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="e9ae2-119">子元素</span><span class="sxs-lookup"><span data-stu-id="e9ae2-119">Child Elements</span></span>  
 <span data-ttu-id="e9ae2-120">无。</span><span class="sxs-lookup"><span data-stu-id="e9ae2-120">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="e9ae2-121">父元素</span><span class="sxs-lookup"><span data-stu-id="e9ae2-121">Parent Elements</span></span>  
  
|<span data-ttu-id="e9ae2-122">元素</span><span class="sxs-lookup"><span data-stu-id="e9ae2-122">Element</span></span>|<span data-ttu-id="e9ae2-123">描述</span><span class="sxs-lookup"><span data-stu-id="e9ae2-123">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="e9ae2-124">\<configuration> 元素</span><span class="sxs-lookup"><span data-stu-id="e9ae2-124">\<configuration> Element</span></span>](../configuration-element.md)|<span data-ttu-id="e9ae2-125">公共语言运行库和 .NET Framework 应用程序所使用的每个配置文件中的根元素。</span><span class="sxs-lookup"><span data-stu-id="e9ae2-125">The root element in every configuration file that is used by the common language runtime and .NET Framework applications.</span></span>|  
|[<span data-ttu-id="e9ae2-126">\<system.object > 元素</span><span class="sxs-lookup"><span data-stu-id="e9ae2-126">\<system.codedom> Element</span></span>](system-codedom-element.md)|<span data-ttu-id="e9ae2-127">指定可用语言提供程序的编译器配置设置。</span><span class="sxs-lookup"><span data-stu-id="e9ae2-127">Specifies compiler configuration settings for available language providers.</span></span>|  
|[<span data-ttu-id="e9ae2-128">\<编译器 > 元素</span><span class="sxs-lookup"><span data-stu-id="e9ae2-128">\<compilers> Element</span></span>](compilers-element.md)|<span data-ttu-id="e9ae2-129">编译器配置元素的容器;包含零个或多个 `<compiler>` 元素。</span><span class="sxs-lookup"><span data-stu-id="e9ae2-129">Container for compiler configuration elements; contains zero or more `<compiler>` elements.</span></span>|  
|[<span data-ttu-id="e9ae2-130">\<compiler> Element</span><span class="sxs-lookup"><span data-stu-id="e9ae2-130">\<compiler> Element</span></span>](compiler-element.md)|<span data-ttu-id="e9ae2-131">指定语言提供程序的编译器配置属性。</span><span class="sxs-lookup"><span data-stu-id="e9ae2-131">Specifies the compiler configuration attributes for a language provider.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="e9ae2-132">备注</span><span class="sxs-lookup"><span data-stu-id="e9ae2-132">Remarks</span></span>  
 <span data-ttu-id="e9ae2-133">在 .NET Framework 版本3.5 中，代码文档对象模型（CodeDOM）代码提供程序可以使用 `<providerOption>` 元素支持特定于提供程序的选项。</span><span class="sxs-lookup"><span data-stu-id="e9ae2-133">In the .NET Framework version 3.5, Code Document Object Model (CodeDOM) code providers can support provider-specific options by using the `<providerOption>` element.</span></span>  
  
 <span data-ttu-id="e9ae2-134">3\.5 .NET Framework 包括更新的 .NET Framework 2.0 程序集，并提供包含新类型的3.5 版本的新程序集。</span><span class="sxs-lookup"><span data-stu-id="e9ae2-134">The .NET Framework 3.5 includes updated .NET Framework 2.0 assemblies and provides new version 3.5 assemblies that contain new types.</span></span> <span data-ttu-id="e9ae2-135">Microsoft C#和 Visual Basic 代码提供程序包含在 .NET Framework 2.0 程序集中，但已更新为支持版本3.5 编译器。</span><span class="sxs-lookup"><span data-stu-id="e9ae2-135">The Microsoft C# and Visual Basic code providers are contained in .NET Framework 2.0 assemblies but have been updated to support version 3.5 compilers.</span></span> <span data-ttu-id="e9ae2-136">默认情况下，更新的代码提供程序为版本2.0 编译器生成代码。</span><span class="sxs-lookup"><span data-stu-id="e9ae2-136">By default, the updated code providers generate code for version 2.0 compilers.</span></span> <span data-ttu-id="e9ae2-137">您可以使用 `<providerOption>` 元素将目标编译器版本更改为3.5。</span><span class="sxs-lookup"><span data-stu-id="e9ae2-137">You can use the `<providerOption>` element to change the target compiler version to 3.5.</span></span> <span data-ttu-id="e9ae2-138">为此，请为 `name` 属性指定 "CompilerVersion"，并为 `value` 属性指定 "v 3.5"。</span><span class="sxs-lookup"><span data-stu-id="e9ae2-138">To do this, specify "CompilerVersion" for the `name` attribute and "v3.5" for the `value` attribute.</span></span> <span data-ttu-id="e9ae2-139">必须在版本号前面加上小写 "v"。</span><span class="sxs-lookup"><span data-stu-id="e9ae2-139">You must precede the version number with a lower-case "v".</span></span>  
  
 <span data-ttu-id="e9ae2-140">可以通过将 `<providerOption>` 元素添加到 .NET Framework 2.0 Machine.config 或根 web.config 文件来使版本规范成为全局版本。</span><span class="sxs-lookup"><span data-stu-id="e9ae2-140">You can make the version specification global by adding the `<providerOption>` element to the .NET Framework 2.0 Machine.config or root Web.config file.</span></span> <span data-ttu-id="e9ae2-141">如果在 machine.config 文件中将默认编译器版本更新为3.5，则可以通过使用应用程序配置文件中的 `<providerOption>` 元素，将其更改为每个应用程序2.0。</span><span class="sxs-lookup"><span data-stu-id="e9ae2-141">If you update the default compiler version to 3.5 in the Machine.config file, you can change it back to 2.0 on a per-application basis by using the `<providerOption>` element in the application configuration file.</span></span>  
  
 <span data-ttu-id="e9ae2-142">CodeDOM 代码提供程序实现者可以通过提供采用 <xref:System.Collections.Generic.IDictionary%602>类型的 `providerOptions` 参数的构造函数来处理自定义选项。</span><span class="sxs-lookup"><span data-stu-id="e9ae2-142">CodeDOM code provider implementers can process custom options by providing a constructor that takes a `providerOptions` parameter of type <xref:System.Collections.Generic.IDictionary%602>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="e9ae2-143">示例</span><span class="sxs-lookup"><span data-stu-id="e9ae2-143">Example</span></span>  
 <span data-ttu-id="e9ae2-144">下面的示例演示如何指定应该使用C#代码提供程序的3.5 版。</span><span class="sxs-lookup"><span data-stu-id="e9ae2-144">The following example demonstrates how to specify that version 3.5 of the C# code provider should be used.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="e9ae2-145">请参阅</span><span class="sxs-lookup"><span data-stu-id="e9ae2-145">See also</span></span>

- <xref:System.CodeDom.Compiler.CompilerInfo>
- <xref:System.CodeDom.Compiler.CodeDomProvider>
- [<span data-ttu-id="e9ae2-146">配置文件架构</span><span class="sxs-lookup"><span data-stu-id="e9ae2-146">Configuration File Schema</span></span>](../index.md)
- [<span data-ttu-id="e9ae2-147">\<编译器 > 元素</span><span class="sxs-lookup"><span data-stu-id="e9ae2-147">\<compilers> Element</span></span>](compilers-element.md)
- [<span data-ttu-id="e9ae2-148">指定完全限定的类型名称</span><span class="sxs-lookup"><span data-stu-id="e9ae2-148">Specifying Fully Qualified Type Names</span></span>](../../../reflection-and-codedom/specifying-fully-qualified-type-names.md)
- <span data-ttu-id="e9ae2-149">[用于编译的编译器的编译器元素（ASP.NET 设置架构）](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/a15ebt6c(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="e9ae2-149">[compiler Element for compilers for compilation (ASP.NET Settings Schema)](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/a15ebt6c(v=vs.100))</span></span>
