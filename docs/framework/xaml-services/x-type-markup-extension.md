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
ms.openlocfilehash: df0b3fe53cb8f284fc6e2d79a9b2cea86318d701
ms.sourcegitcommit: 944ddc52b7f2632f30c668815f92b378efd38eea
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/03/2019
ms.locfileid: "73459916"
---
# <a name="xtype-markup-extension"></a><span data-ttu-id="b017d-102">x:Type 标记扩展</span><span class="sxs-lookup"><span data-stu-id="b017d-102">x:Type Markup Extension</span></span>
<span data-ttu-id="b017d-103">为指定的 XAML 类型的基础类型 <xref:System.Type> 提供 CLR。</span><span class="sxs-lookup"><span data-stu-id="b017d-103">Supplies the CLR <xref:System.Type> object that is the underlying type for a specified XAML type.</span></span>  
  
## <a name="xaml-attribute-usage"></a><span data-ttu-id="b017d-104">XAML 属性用法</span><span class="sxs-lookup"><span data-stu-id="b017d-104">XAML Attribute Usage</span></span>  
  
```xaml  
<object property="{x:Type prefix:typeNameValue}" .../>  
```  
  
## <a name="xaml-object-element-usage"></a><span data-ttu-id="b017d-105">XAML 对象元素用法</span><span class="sxs-lookup"><span data-stu-id="b017d-105">XAML Object Element Usage</span></span>  
  
```xaml  
<x:Type TypeName="prefix:typeNameValue"/>  
```  
  
## <a name="xaml-values"></a><span data-ttu-id="b017d-106">XAML 值</span><span class="sxs-lookup"><span data-stu-id="b017d-106">XAML Values</span></span>  
  
|||  
|-|-|  
|`prefix`|<span data-ttu-id="b017d-107">可选。</span><span class="sxs-lookup"><span data-stu-id="b017d-107">Optional.</span></span> <span data-ttu-id="b017d-108">映射非默认 XAML 命名空间的前缀。</span><span class="sxs-lookup"><span data-stu-id="b017d-108">A prefix that maps a non-default XAML namespace.</span></span> <span data-ttu-id="b017d-109">通常不需要指定前缀。</span><span class="sxs-lookup"><span data-stu-id="b017d-109">Specifying a prefix is frequently not necessary.</span></span> <span data-ttu-id="b017d-110">请参阅“备注”。</span><span class="sxs-lookup"><span data-stu-id="b017d-110">See Remarks.</span></span>|  
|`typeNameValue`|<span data-ttu-id="b017d-111">必须的。</span><span class="sxs-lookup"><span data-stu-id="b017d-111">Required.</span></span> <span data-ttu-id="b017d-112">可解析为当前默认 XAML 命名空间的类型名称;如果提供 `prefix`，则为指定的映射前缀。</span><span class="sxs-lookup"><span data-stu-id="b017d-112">A type name resolvable to the current default XAML namespace; or the specified mapped prefix if `prefix` is supplied.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="b017d-113">备注</span><span class="sxs-lookup"><span data-stu-id="b017d-113">Remarks</span></span>  
 <span data-ttu-id="b017d-114">`x:Type` 标记扩展在C# `typeof()` 运算符与 Microsoft Visual Basic 中的 `GetType` 运算符具有类似的函数。</span><span class="sxs-lookup"><span data-stu-id="b017d-114">The `x:Type` markup extension has a similar function to the `typeof()` operator in C# or the `GetType` operator in Microsoft Visual Basic.</span></span>  
  
 <span data-ttu-id="b017d-115">`x:Type` 标记扩展为采用类型 <xref:System.Type>的属性提供 from 字符串转换行为。</span><span class="sxs-lookup"><span data-stu-id="b017d-115">The `x:Type` markup extension supplies a from-string conversion behavior for properties that take the type <xref:System.Type>.</span></span> <span data-ttu-id="b017d-116">输入为 XAML 类型。</span><span class="sxs-lookup"><span data-stu-id="b017d-116">The input is a XAML type.</span></span> <span data-ttu-id="b017d-117">输入 XAML 类型和输出 CLR <xref:System.Type> 之间的关系是，输出 <xref:System.Type> 是输入 <xref:System.Xaml.XamlType>的 <xref:System.Xaml.XamlType.UnderlyingType%2A>，在基于 XAML 架构上下文和上下文提供的 <xref:System.Xaml.XamlType> 服务查找必需的 <xref:System.Windows.Markup.IXamlTypeResolver> 之后。</span><span class="sxs-lookup"><span data-stu-id="b017d-117">The relationship between the input XAML type and the output CLR <xref:System.Type> is that the output <xref:System.Type> is the <xref:System.Xaml.XamlType.UnderlyingType%2A> of the input <xref:System.Xaml.XamlType>, after looking up the necessary <xref:System.Xaml.XamlType> based on XAML schema context and the <xref:System.Windows.Markup.IXamlTypeResolver> service the context provides.</span></span>  
  
 <span data-ttu-id="b017d-118">在 .NET Framework XAML 服务中，此标记扩展的处理由 <xref:System.Windows.Markup.TypeExtension> 类定义。</span><span class="sxs-lookup"><span data-stu-id="b017d-118">In .NET Framework XAML Services, the handling for this markup extension is defined by the <xref:System.Windows.Markup.TypeExtension> class.</span></span>  
  
 <span data-ttu-id="b017d-119">在特定的框架实现中，某些采用作为值 <xref:System.Type> 的属性可以直接接受类型的名称（`Name`的字符串值）。</span><span class="sxs-lookup"><span data-stu-id="b017d-119">In specific framework implementations, some properties that take <xref:System.Type> as a value can accept the name of the type directly (the string value of the type `Name`).</span></span> <span data-ttu-id="b017d-120">但是，实现此行为是一种复杂的方案。</span><span class="sxs-lookup"><span data-stu-id="b017d-120">However, implementing this behavior is a complex scenario.</span></span> <span data-ttu-id="b017d-121">有关示例，请参阅后面的 "WPF 用法说明" 部分。</span><span class="sxs-lookup"><span data-stu-id="b017d-121">For examples, see the "WPF Usage Notes" section that follows.</span></span>  
  
 <span data-ttu-id="b017d-122">特性语法是最常用于该标记扩展的语法。</span><span class="sxs-lookup"><span data-stu-id="b017d-122">Attribute syntax is the most common syntax used with this markup extension.</span></span> <span data-ttu-id="b017d-123">在 `x:Type` 标识符字符串之后提供的字符串标记被指定为基础 <xref:System.Windows.Markup.TypeExtension.TypeName%2A> 扩展类的 <xref:System.Windows.Markup.TypeExtension> 值。</span><span class="sxs-lookup"><span data-stu-id="b017d-123">The string token provided after the `x:Type` identifier string is assigned as the <xref:System.Windows.Markup.TypeExtension.TypeName%2A> value of the underlying <xref:System.Windows.Markup.TypeExtension> extension class.</span></span> <span data-ttu-id="b017d-124">在基于 CLR 类型 .NET Framework XAML 服务的默认 XAML 架构上下文下，此属性的值是所需类型的 <xref:System.Reflection.MemberInfo.Name%2A>，或包含 <xref:System.Reflection.MemberInfo.Name%2A> 前面带有非默认 XAML 命名空间映射的前缀。</span><span class="sxs-lookup"><span data-stu-id="b017d-124">Under the default XAML schema context for .NET Framework XAML Services, which is based on CLR types, the value of this attribute is either the <xref:System.Reflection.MemberInfo.Name%2A> of the desired type, or contains that <xref:System.Reflection.MemberInfo.Name%2A> preceded by a prefix for a non-default XAML namespace mapping.</span></span>  
  
 <span data-ttu-id="b017d-125">可以在对象元素语法中使用 `x:Type` 标记扩展。</span><span class="sxs-lookup"><span data-stu-id="b017d-125">The `x:Type` markup extension can be used in object element syntax.</span></span> <span data-ttu-id="b017d-126">在这种情况下，必须指定 <xref:System.Windows.Markup.TypeExtension.TypeName%2A> 属性的值才能正确地初始化扩展。</span><span class="sxs-lookup"><span data-stu-id="b017d-126">In this case, specifying the value of the <xref:System.Windows.Markup.TypeExtension.TypeName%2A> property is required to properly initialize the extension.</span></span>  
  
 <span data-ttu-id="b017d-127">`x:Type` 标记扩展还可用作详细特性;但这种用法并不典型： `<object property="{x:Type TypeName=typeNameValue}" .../>`</span><span class="sxs-lookup"><span data-stu-id="b017d-127">The `x:Type` markup extension can also be used as a verbose attribute; however this use is not typical: `<object property="{x:Type TypeName=typeNameValue}" .../>`</span></span>  
  
## <a name="wpf-usage-notes"></a><span data-ttu-id="b017d-128">WPF 使用说明</span><span class="sxs-lookup"><span data-stu-id="b017d-128">WPF Usage Notes</span></span>  
  
### <a name="default-xaml-namespace-and-type-mapping"></a><span data-ttu-id="b017d-129">默认 XAML 命名空间和类型映射</span><span class="sxs-lookup"><span data-stu-id="b017d-129">Default XAML Namespace and Type Mapping</span></span>  
 <span data-ttu-id="b017d-130">WPF 编程的默认 XAML 命名空间包含典型 XAML 方案所需的大多数 XAML 类型;因此，在引用 XAML 类型值时，通常可以避免前缀。</span><span class="sxs-lookup"><span data-stu-id="b017d-130">The default XAML namespace for WPF programming contains most of the XAML types you need for typical XAML scenarios; therefore, you can often avoid prefixes when referencing XAML type values.</span></span> <span data-ttu-id="b017d-131">如果引用的是自定义程序集的类型或存在于 WPF 程序集中的类型，但却来自未映射到默认 XAML 命名空间的 CLR 命名空间，则可能需要映射前缀。</span><span class="sxs-lookup"><span data-stu-id="b017d-131">You might need to map a prefix if you are referencing a type from a custom assembly or for types that exist in a WPF assembly but are from a CLR namespace that was not mapped to the default XAML namespace.</span></span> <span data-ttu-id="b017d-132">有关前缀、XAML 命名空间和映射 CLR 命名空间的详细信息，请参阅[WPF xaml 的 XAML 命名空间和命名空间映射](../wpf/advanced/xaml-namespaces-and-namespace-mapping-for-wpf-xaml.md)。</span><span class="sxs-lookup"><span data-stu-id="b017d-132">For more information about prefixes, XAML namespaces, and mapping CLR namespaces, see [XAML Namespaces and Namespace Mapping for WPF XAML](../wpf/advanced/xaml-namespaces-and-namespace-mapping-for-wpf-xaml.md).</span></span>  
  
### <a name="type-properties-that-support-typename-as-string"></a><span data-ttu-id="b017d-133">支持类型为字符串的类型属性</span><span class="sxs-lookup"><span data-stu-id="b017d-133">Type Properties That Support Typename-as-String</span></span>  
 <span data-ttu-id="b017d-134">WPF 支持用于指定 <xref:System.Type> 类型的某些属性的值，而无需 `x:Type` 标记扩展用法的技术。</span><span class="sxs-lookup"><span data-stu-id="b017d-134">WPF supports techniques that enable specifying the value of some properties of type <xref:System.Type> without requiring an `x:Type` markup extension usage.</span></span> <span data-ttu-id="b017d-135">相反，你可以将值指定为命名类型的字符串。</span><span class="sxs-lookup"><span data-stu-id="b017d-135">Instead, you can specify the value as a string that names the type.</span></span> <span data-ttu-id="b017d-136"><xref:System.Windows.Controls.ControlTemplate.TargetType%2A?displayProperty=nameWithType> 和 <xref:System.Windows.Style.TargetType%2A?displayProperty=nameWithType>示例。</span><span class="sxs-lookup"><span data-stu-id="b017d-136">Examples of this are <xref:System.Windows.Controls.ControlTemplate.TargetType%2A?displayProperty=nameWithType> and <xref:System.Windows.Style.TargetType%2A?displayProperty=nameWithType>.</span></span> <span data-ttu-id="b017d-137">不通过类型转换器或标记扩展提供对此行为的支持。</span><span class="sxs-lookup"><span data-stu-id="b017d-137">Support for this behavior is not provided through either type converters or markup extensions.</span></span> <span data-ttu-id="b017d-138">相反，这是通过 <xref:System.Windows.FrameworkElementFactory>实现的延迟行为。</span><span class="sxs-lookup"><span data-stu-id="b017d-138">Instead, this is a deferral behavior implemented through <xref:System.Windows.FrameworkElementFactory>.</span></span>  
  
 <span data-ttu-id="b017d-139">Silverlight 支持类似的约定。</span><span class="sxs-lookup"><span data-stu-id="b017d-139">Silverlight supports a similar convention.</span></span> <span data-ttu-id="b017d-140">事实上，Silverlight 目前不支持其 XAML 语言支持 `{x:Type}`，并且在用于支持 WPF Silverlight XAML 迁移的少数情况下，不接受 `{x:Type}` 使用。</span><span class="sxs-lookup"><span data-stu-id="b017d-140">In fact, Silverlight does not currently support `{x:Type}` in its XAML language support, and does not accept `{x:Type}` usages outside of a few circumstances that are intended to support WPF-Silverlight XAML migration.</span></span> <span data-ttu-id="b017d-141">因此，类型名称字符串行为内置于所有 Silverlight 本机属性评估中，其中 <xref:System.Type> 是值。</span><span class="sxs-lookup"><span data-stu-id="b017d-141">Therefore, the typename-as-string behavior is built-in to all Silverlight native property evaluation where a <xref:System.Type> is the value.</span></span>  
  
## <a name="xaml-2009"></a><span data-ttu-id="b017d-142">XAML 2009</span><span class="sxs-lookup"><span data-stu-id="b017d-142">XAML 2009</span></span>  
 <span data-ttu-id="b017d-143">XAML 2009 提供对泛型类型的其他支持，并修改 `x:TypeArguments` 和 `x:Type` 的功能行为以提供此支持。</span><span class="sxs-lookup"><span data-stu-id="b017d-143">XAML 2009 provides additional support for generic types and modifies the feature behavior of `x:TypeArguments` and `x:Type` to provide this support.</span></span>  
  
- <span data-ttu-id="b017d-144">泛型对象实例化的 `x:TypeArguments` 和关联的对象元素可以位于根以外的元素上。</span><span class="sxs-lookup"><span data-stu-id="b017d-144">`x:TypeArguments` and the associated object element for a generic object instantiation can be on elements other than the root.</span></span> <span data-ttu-id="b017d-145">有关详细信息，请参阅[X:TypeArguments 指令](x-typearguments-directive.md)的 "XAML 2009" 一节。</span><span class="sxs-lookup"><span data-stu-id="b017d-145">For more information, see the "XAML 2009" section of [x:TypeArguments Directive](x-typearguments-directive.md).</span></span>  
  
- <span data-ttu-id="b017d-146">XAML 2009 支持用于在标记中指定泛型类型的约束的语法。</span><span class="sxs-lookup"><span data-stu-id="b017d-146">XAML 2009 supports a syntax for specifying a generic type's constraint in markup.</span></span> <span data-ttu-id="b017d-147">这可由 `x:TypeArguments`、`x:Type`或组合的两个功能使用。</span><span class="sxs-lookup"><span data-stu-id="b017d-147">This can be used by `x:TypeArguments`, by `x:Type`, or by the two features in combination.</span></span>  
  
- <span data-ttu-id="b017d-148">当处理 XAML 2009 for load 时，WPF XAML 实现还会将此功能添加到使用类型 <xref:System.Type>的某些框架属性的隐式类型转换行为。</span><span class="sxs-lookup"><span data-stu-id="b017d-148">WPF XAML implementation when processing XAML 2009 for load also adds this capability to the implicit type conversion behavior for certain framework properties that use type <xref:System.Type>.</span></span>  
  
 <span data-ttu-id="b017d-149">在 WPF 中，可以使用 XAML 2009 功能，但仅适用于松散 XAML （未进行标记编译的 XAML）。</span><span class="sxs-lookup"><span data-stu-id="b017d-149">In WPF, you can use XAML 2009 features but only for loose XAML (XAML that is not markup-compiled).</span></span> <span data-ttu-id="b017d-150">WPF 的已编译标记的 XAML 以及 XAML 的 BAML 形式当前不支持 XAML 2009 关键字和功能。</span><span class="sxs-lookup"><span data-stu-id="b017d-150">Markup-compiled XAML for WPF and the BAML form of XAML do not currently support the XAML 2009 keywords and features.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b017d-151">请参阅</span><span class="sxs-lookup"><span data-stu-id="b017d-151">See also</span></span>

- <xref:System.Windows.Style>
- [<span data-ttu-id="b017d-152">样式设置和模板化</span><span class="sxs-lookup"><span data-stu-id="b017d-152">Styling and Templating</span></span>](../wpf/controls/styling-and-templating.md)
- [<span data-ttu-id="b017d-153">XAML 概述 (WPF)</span><span class="sxs-lookup"><span data-stu-id="b017d-153">XAML Overview (WPF)</span></span>](../../desktop-wpf/fundamentals/xaml.md)
- [<span data-ttu-id="b017d-154">标记扩展和 WPF XAML</span><span class="sxs-lookup"><span data-stu-id="b017d-154">Markup Extensions and WPF XAML</span></span>](../wpf/advanced/markup-extensions-and-wpf-xaml.md)
