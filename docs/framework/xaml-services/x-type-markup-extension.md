---
title: x:Type 标记扩展
ms.date: 03/30/2017
f1_keywords:
- x:TypeExtension
- Type
- x:Type
- xType
- TypeExtension
helpviewer_keywords:
- x:Type markup extension [XAML Services]
- XAML [XAML Services], x:Type markup extension
- XAML [XAML Services], TargetType attribute
- TargetType attribute [XAML Services]
- Type markup extension in XAML [XAML Services]
ms.assetid: e0e0ce6f-e873-49c7-8ad7-8b840eb353ec
ms.openlocfilehash: e4d56c5b5deda0bd1df8827020e0b76cc6276c1c
ms.sourcegitcommit: 6eac9a01ff5d70c6d18460324c016a3612c5e268
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/15/2018
ms.locfileid: "45649234"
---
# <a name="xtype-markup-extension"></a><span data-ttu-id="ec4df-102">x:Type 标记扩展</span><span class="sxs-lookup"><span data-stu-id="ec4df-102">x:Type Markup Extension</span></span>
<span data-ttu-id="ec4df-103">提供 CLR<xref:System.Type>是指定的 XAML 类型的基础类型的对象。</span><span class="sxs-lookup"><span data-stu-id="ec4df-103">Supplies the CLR <xref:System.Type> object that is the underlying type for a specified XAML type.</span></span>  
  
## <a name="xaml-attribute-usage"></a><span data-ttu-id="ec4df-104">XAML 属性用法</span><span class="sxs-lookup"><span data-stu-id="ec4df-104">XAML Attribute Usage</span></span>  
  
```xaml  
<object property="{x:Type prefix:typeNameValue}" .../>  
```  
  
## <a name="xaml-object-element-usage"></a><span data-ttu-id="ec4df-105">XAML 对象元素用法</span><span class="sxs-lookup"><span data-stu-id="ec4df-105">XAML Object Element Usage</span></span>  
  
```xaml  
<x:Type TypeName="prefix:typeNameValue"/>  
```  
  
## <a name="xaml-values"></a><span data-ttu-id="ec4df-106">XAML 值</span><span class="sxs-lookup"><span data-stu-id="ec4df-106">XAML Values</span></span>  
  
|||  
|-|-|  
|`prefix`|<span data-ttu-id="ec4df-107">可选。</span><span class="sxs-lookup"><span data-stu-id="ec4df-107">Optional.</span></span> <span data-ttu-id="ec4df-108">将非默认 XAML 命名空间映射前缀。</span><span class="sxs-lookup"><span data-stu-id="ec4df-108">A prefix that maps a non-default XAML namespace.</span></span> <span data-ttu-id="ec4df-109">指定前缀经常是不必要。</span><span class="sxs-lookup"><span data-stu-id="ec4df-109">Specifying a prefix is frequently not necessary.</span></span> <span data-ttu-id="ec4df-110">请参阅“备注”。</span><span class="sxs-lookup"><span data-stu-id="ec4df-110">See Remarks.</span></span>|  
|`typeNameValue`|<span data-ttu-id="ec4df-111">必须的。</span><span class="sxs-lookup"><span data-stu-id="ec4df-111">Required.</span></span> <span data-ttu-id="ec4df-112">类型名称解析为当前的默认 XAML 命名空间;或指定的映射前缀如果`prefix`提供。</span><span class="sxs-lookup"><span data-stu-id="ec4df-112">A type name resolvable to the current default XAML namespace; or the specified mapped prefix if `prefix` is supplied.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="ec4df-113">备注</span><span class="sxs-lookup"><span data-stu-id="ec4df-113">Remarks</span></span>  
 <span data-ttu-id="ec4df-114">`x:Type`标记扩展有函数相似`typeof()`C# 中的运算符或`GetType`运算符在 Microsoft Visual Basic。</span><span class="sxs-lookup"><span data-stu-id="ec4df-114">The `x:Type` markup extension has a similar function to the `typeof()` operator in C# or the `GetType` operator in Microsoft Visual Basic.</span></span>  
  
 <span data-ttu-id="ec4df-115">`x:Type`标记扩展提供接受类型的属性从字符串转换行为<xref:System.Type>。</span><span class="sxs-lookup"><span data-stu-id="ec4df-115">The `x:Type` markup extension supplies a from-string conversion behavior for properties that take the type <xref:System.Type>.</span></span> <span data-ttu-id="ec4df-116">输入是 XAML 类型。</span><span class="sxs-lookup"><span data-stu-id="ec4df-116">The input is a XAML type.</span></span> <span data-ttu-id="ec4df-117">输入的 XAML 类型和 CLR 的输出之间的关系<xref:System.Type>是输出<xref:System.Type>是<xref:System.Xaml.XamlType.UnderlyingType%2A>输入的<xref:System.Xaml.XamlType>，查找所需的后<xref:System.Xaml.XamlType>基于 XAML 架构上下文和<xref:System.Windows.Markup.IXamlTypeResolver>上下文提供的服务。</span><span class="sxs-lookup"><span data-stu-id="ec4df-117">The relationship between the input XAML type and the output CLR <xref:System.Type> is that the output <xref:System.Type> is the <xref:System.Xaml.XamlType.UnderlyingType%2A> of the input <xref:System.Xaml.XamlType>, after looking up the necessary <xref:System.Xaml.XamlType> based on XAML schema context and the <xref:System.Windows.Markup.IXamlTypeResolver> service the context provides.</span></span>  
  
 <span data-ttu-id="ec4df-118">在.NET Framework XAML 服务中，对此标记扩展的处理由定义<xref:System.Windows.Markup.TypeExtension>类。</span><span class="sxs-lookup"><span data-stu-id="ec4df-118">In .NET Framework XAML Services, the handling for this markup extension is defined by the <xref:System.Windows.Markup.TypeExtension> class.</span></span>  
  
 <span data-ttu-id="ec4df-119">在特定的框架实现中，某些属性，采用<xref:System.Type>值可直接接受类型的名称 (该类型的字符串值`Name`)。</span><span class="sxs-lookup"><span data-stu-id="ec4df-119">In specific framework implementations, some properties that take <xref:System.Type> as a value can accept the name of the type directly (the string value of the type `Name`).</span></span> <span data-ttu-id="ec4df-120">但是，实现此行为是复杂的方案。</span><span class="sxs-lookup"><span data-stu-id="ec4df-120">However, implementing this behavior is a complex scenario.</span></span> <span data-ttu-id="ec4df-121">有关示例，请参阅后面的"WPF 用法说明"部分。</span><span class="sxs-lookup"><span data-stu-id="ec4df-121">For examples, see the "WPF Usage Notes" section that follows.</span></span>  
  
 <span data-ttu-id="ec4df-122">特性语法是最常用于该标记扩展的语法。</span><span class="sxs-lookup"><span data-stu-id="ec4df-122">Attribute syntax is the most common syntax used with this markup extension.</span></span> <span data-ttu-id="ec4df-123">在 `x:Type` 标识符字符串之后提供的字符串标记被指定为基础 <xref:System.Windows.Markup.TypeExtension.TypeName%2A> 扩展类的 <xref:System.Windows.Markup.TypeExtension> 值。</span><span class="sxs-lookup"><span data-stu-id="ec4df-123">The string token provided after the `x:Type` identifier string is assigned as the <xref:System.Windows.Markup.TypeExtension.TypeName%2A> value of the underlying <xref:System.Windows.Markup.TypeExtension> extension class.</span></span> <span data-ttu-id="ec4df-124">在.NET Framework XAML 服务，基于 CLR 类型的默认 XAML 架构上下文下，此属性的值是<xref:System.Reflection.MemberInfo.Name%2A>所需的类型，或包含的<xref:System.Reflection.MemberInfo.Name%2A>跟在非默认 XAML 命名空间的前缀映射。</span><span class="sxs-lookup"><span data-stu-id="ec4df-124">Under the default XAML schema context for .NET Framework XAML Services, which is based on CLR types, the value of this attribute is either the <xref:System.Reflection.MemberInfo.Name%2A> of the desired type, or contains that <xref:System.Reflection.MemberInfo.Name%2A> preceded by a prefix for a non-default XAML namespace mapping.</span></span>  
  
 <span data-ttu-id="ec4df-125">`x:Type`可以在对象元素语法中使用标记扩展。</span><span class="sxs-lookup"><span data-stu-id="ec4df-125">The `x:Type` markup extension can be used in object element syntax.</span></span> <span data-ttu-id="ec4df-126">在这种情况下，指定的值<xref:System.Windows.Markup.TypeExtension.TypeName%2A>正确初始化该扩展所需的属性。</span><span class="sxs-lookup"><span data-stu-id="ec4df-126">In this case, specifying the value of the <xref:System.Windows.Markup.TypeExtension.TypeName%2A> property is required to properly initialize the extension.</span></span>  
  
 <span data-ttu-id="ec4df-127">`x:Type`标记扩展还可以用作详细属性; 但是此，请使用不是典型： `<object property="{x:Type TypeName=typeNameValue}" .../>`</span><span class="sxs-lookup"><span data-stu-id="ec4df-127">The `x:Type` markup extension can also be used as a verbose attribute; however this use is not typical: `<object property="{x:Type TypeName=typeNameValue}" .../>`</span></span>  
  
## <a name="wpf-usage-notes"></a><span data-ttu-id="ec4df-128">WPF 用法说明</span><span class="sxs-lookup"><span data-stu-id="ec4df-128">WPF Usage Notes</span></span>  
  
### <a name="default-xaml-namespace-and-type-mapping"></a><span data-ttu-id="ec4df-129">默认 XAML Namespace 和类型映射</span><span class="sxs-lookup"><span data-stu-id="ec4df-129">Default XAML Namespace and Type Mapping</span></span>  
 <span data-ttu-id="ec4df-130">WPF 编程的默认 XAML 命名空间包含大部分所需的典型 XAML 方案; XAML 类型因此，引用 XAML 类型的值时，通常可以避免前缀。</span><span class="sxs-lookup"><span data-stu-id="ec4df-130">The default XAML namespace for WPF programming contains most of the XAML types you need for typical XAML scenarios; therefore, you can often avoid prefixes when referencing XAML type values.</span></span> <span data-ttu-id="ec4df-131">您可能需要，如果所引用的类型，从自定义程序集或类型存在于 WPF 程序集中，但来自未映射到默认 XAML 命名空间的 CLR 命名空间映射前缀。</span><span class="sxs-lookup"><span data-stu-id="ec4df-131">You might need to map a prefix if you are referencing a type from a custom assembly or for types that exist in a WPF assembly but are from a CLR namespace that was not mapped to the default XAML namespace.</span></span> <span data-ttu-id="ec4df-132">有关前缀、 XAML 命名空间和映射 CLR 命名空间的详细信息，请参阅[XAML 命名空间和 WPF XAML 的 Namespace 映射](../../../docs/framework/wpf/advanced/xaml-namespaces-and-namespace-mapping-for-wpf-xaml.md)。</span><span class="sxs-lookup"><span data-stu-id="ec4df-132">For more information about prefixes, XAML namespaces, and mapping CLR namespaces, see [XAML Namespaces and Namespace Mapping for WPF XAML](../../../docs/framework/wpf/advanced/xaml-namespaces-and-namespace-mapping-for-wpf-xaml.md).</span></span>  
  
### <a name="type-properties-that-support-typename-as-string"></a><span data-ttu-id="ec4df-133">类型属性的支持类型名称作为-字符串</span><span class="sxs-lookup"><span data-stu-id="ec4df-133">Type Properties That Support Typename-as-String</span></span>  
 <span data-ttu-id="ec4df-134">WPF 支持技术，使指定类型的某些属性的值<xref:System.Type>而无需`x:Type`标记扩展用法。</span><span class="sxs-lookup"><span data-stu-id="ec4df-134">WPF supports techniques that enable specifying the value of some properties of type <xref:System.Type> without requiring an `x:Type` markup extension usage.</span></span> <span data-ttu-id="ec4df-135">相反，您可以指定为的类型命名的字符串的值。</span><span class="sxs-lookup"><span data-stu-id="ec4df-135">Instead, you can specify the value as a string that names the type.</span></span> <span data-ttu-id="ec4df-136">示例包括<xref:System.Windows.Controls.ControlTemplate.TargetType%2A?displayProperty=nameWithType>和<xref:System.Windows.Style.TargetType%2A?displayProperty=nameWithType>。</span><span class="sxs-lookup"><span data-stu-id="ec4df-136">Examples of this are <xref:System.Windows.Controls.ControlTemplate.TargetType%2A?displayProperty=nameWithType> and <xref:System.Windows.Style.TargetType%2A?displayProperty=nameWithType>.</span></span> <span data-ttu-id="ec4df-137">通过类型转换器或标记扩展不提供此行为的支持。</span><span class="sxs-lookup"><span data-stu-id="ec4df-137">Support for this behavior is not provided through either type converters or markup extensions.</span></span> <span data-ttu-id="ec4df-138">相反，这是通过实现延迟行为<xref:System.Windows.FrameworkElementFactory>。</span><span class="sxs-lookup"><span data-stu-id="ec4df-138">Instead, this is a deferral behavior implemented through <xref:System.Windows.FrameworkElementFactory>.</span></span>  
  
 <span data-ttu-id="ec4df-139">Silverlight 支持类似的约定。</span><span class="sxs-lookup"><span data-stu-id="ec4df-139">Silverlight supports a similar convention.</span></span> <span data-ttu-id="ec4df-140">事实上，Silverlight 目前不支持`{x:Type}`XAML 语言支持，并且不接受`{x:Type}`之外，旨在支持 WPF Silverlight XAML 迁移在某些环境下的用法。</span><span class="sxs-lookup"><span data-stu-id="ec4df-140">In fact, Silverlight does not currently support `{x:Type}` in its XAML language support, and does not accept `{x:Type}` usages outside of a few circumstances that are intended to support WPF-Silverlight XAML migration.</span></span> <span data-ttu-id="ec4df-141">因此，类型名称作为字符串行为是内置于所有 Silverlight 本机属性评估其中<xref:System.Type>的值。</span><span class="sxs-lookup"><span data-stu-id="ec4df-141">Therefore, the typename-as-string behavior is built-in to all Silverlight native property evaluation where a <xref:System.Type> is the value.</span></span>  
  
## <a name="xaml-2009"></a><span data-ttu-id="ec4df-142">XAML 2009</span><span class="sxs-lookup"><span data-stu-id="ec4df-142">XAML 2009</span></span>  
 <span data-ttu-id="ec4df-143">XAML 2009 提供额外支持泛型类型，并修改的功能行为`x:TypeArguments`和`x:Type`能够提供此支持。</span><span class="sxs-lookup"><span data-stu-id="ec4df-143">XAML 2009 provides additional support for generic types and modifies the feature behavior of `x:TypeArguments` and `x:Type` to provide this support.</span></span>  
  
-   <span data-ttu-id="ec4df-144">`x:TypeArguments` 并且，泛型对象实例化的关联的对象元素可在根以外的其他元素。</span><span class="sxs-lookup"><span data-stu-id="ec4df-144">`x:TypeArguments` and the associated object element for a generic object instantiation can be on elements other than the root.</span></span> <span data-ttu-id="ec4df-145">有关详细信息，请参阅"XAML 2009"一节[X:typearguments 指令](../../../docs/framework/xaml-services/x-typearguments-directive.md)。</span><span class="sxs-lookup"><span data-stu-id="ec4df-145">For more information, see the "XAML 2009" section of [x:TypeArguments Directive](../../../docs/framework/xaml-services/x-typearguments-directive.md).</span></span>  
  
-   <span data-ttu-id="ec4df-146">XAML 2009 支持用于在标记中指定的泛型类型约束的语法。</span><span class="sxs-lookup"><span data-stu-id="ec4df-146">XAML 2009 supports a syntax for specifying a generic type's constraint in markup.</span></span> <span data-ttu-id="ec4df-147">这可由`x:TypeArguments`，也可由`x:Type`，或结合使用的两个功能。</span><span class="sxs-lookup"><span data-stu-id="ec4df-147">This can be used by `x:TypeArguments`, by `x:Type`, or by the two features in combination.</span></span>  
  
-   <span data-ttu-id="ec4df-148">WPF XAML 实现的负载也将此功能添加到使用类型的某些 framework 属性的隐式类型转换行为处理 XAML 2009 时<xref:System.Type>。</span><span class="sxs-lookup"><span data-stu-id="ec4df-148">WPF XAML implementation when processing XAML 2009 for load also adds this capability to the implicit type conversion behavior for certain framework properties that use type <xref:System.Type>.</span></span>  
  
 <span data-ttu-id="ec4df-149">在 WPF 中，可以使用 XAML 2009 功能但仅针对松散 XAML (未标记编译的 XAML) 中。</span><span class="sxs-lookup"><span data-stu-id="ec4df-149">In WPF, you can use XAML 2009 features but only for loose XAML (XAML that is not markup-compiled).</span></span> <span data-ttu-id="ec4df-150">WPF 的已编译标记的 XAML 以及 XAML 的 BAML 形式当前不支持 XAML 2009 关键字和功能。</span><span class="sxs-lookup"><span data-stu-id="ec4df-150">Markup-compiled XAML for WPF and the BAML form of XAML do not currently support the XAML 2009 keywords and features.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ec4df-151">请参阅</span><span class="sxs-lookup"><span data-stu-id="ec4df-151">See Also</span></span>  
 <xref:System.Windows.Style>  
 [<span data-ttu-id="ec4df-152">样式设置和模板化</span><span class="sxs-lookup"><span data-stu-id="ec4df-152">Styling and Templating</span></span>](../../../docs/framework/wpf/controls/styling-and-templating.md)  
 [<span data-ttu-id="ec4df-153">XAML 概述 (WPF)</span><span class="sxs-lookup"><span data-stu-id="ec4df-153">XAML Overview (WPF)</span></span>](../../../docs/framework/wpf/advanced/xaml-overview-wpf.md)  
 [<span data-ttu-id="ec4df-154">标记扩展和 WPF XAML</span><span class="sxs-lookup"><span data-stu-id="ec4df-154">Markup Extensions and WPF XAML</span></span>](../../../docs/framework/wpf/advanced/markup-extensions-and-wpf-xaml.md)
