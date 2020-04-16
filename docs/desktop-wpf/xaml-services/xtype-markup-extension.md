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
ms.openlocfilehash: f75d4e30dc41bbce995e466466c96c1a2830949b
ms.sourcegitcommit: c2d9718996402993cf31541f11e95531bc68bad0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/27/2020
ms.locfileid: "81432634"
---
# <a name="xtype-markup-extension"></a><span data-ttu-id="ecd67-102">x:Type 标记扩展</span><span class="sxs-lookup"><span data-stu-id="ecd67-102">x:Type Markup Extension</span></span>

<span data-ttu-id="ecd67-103">提供 CLR<xref:System.Type>对象，该对象是指定 XAML 类型的基础类型。</span><span class="sxs-lookup"><span data-stu-id="ecd67-103">Supplies the CLR <xref:System.Type> object that is the underlying type for a specified XAML type.</span></span>

## <a name="xaml-attribute-usage"></a><span data-ttu-id="ecd67-104">XAML 属性用法</span><span class="sxs-lookup"><span data-stu-id="ecd67-104">XAML Attribute Usage</span></span>

```xaml
<object property="{x:Type prefix:typeNameValue}" .../>
```

## <a name="xaml-object-element-usage"></a><span data-ttu-id="ecd67-105">XAML 对象元素用法</span><span class="sxs-lookup"><span data-stu-id="ecd67-105">XAML Object Element Usage</span></span>

```xaml
<x:Type TypeName="prefix:typeNameValue"/>
```

## <a name="xaml-values"></a><span data-ttu-id="ecd67-106">XAML 值</span><span class="sxs-lookup"><span data-stu-id="ecd67-106">XAML Values</span></span>

|||
|-|-|
|`prefix`|<span data-ttu-id="ecd67-107">可选。</span><span class="sxs-lookup"><span data-stu-id="ecd67-107">Optional.</span></span> <span data-ttu-id="ecd67-108">映射非默认 XAML 命名空间的前缀。</span><span class="sxs-lookup"><span data-stu-id="ecd67-108">A prefix that maps a non-default XAML namespace.</span></span> <span data-ttu-id="ecd67-109">通常不需要指定前缀。</span><span class="sxs-lookup"><span data-stu-id="ecd67-109">Specifying a prefix is frequently not necessary.</span></span> <span data-ttu-id="ecd67-110">请参阅“备注”。</span><span class="sxs-lookup"><span data-stu-id="ecd67-110">See Remarks.</span></span>|
|`typeNameValue`|<span data-ttu-id="ecd67-111">必需。</span><span class="sxs-lookup"><span data-stu-id="ecd67-111">Required.</span></span> <span data-ttu-id="ecd67-112">可解析为当前默认 XAML 命名空间的类型名称;或指定的映射前缀（如果`prefix`提供）。</span><span class="sxs-lookup"><span data-stu-id="ecd67-112">A type name resolvable to the current default XAML namespace; or the specified mapped prefix if `prefix` is supplied.</span></span>|

## <a name="remarks"></a><span data-ttu-id="ecd67-113">备注</span><span class="sxs-lookup"><span data-stu-id="ecd67-113">Remarks</span></span>

<span data-ttu-id="ecd67-114">标记`x:Type`扩展具有与 C# 中的`typeof()`运算符或 Microsoft Visual `GetType` Basic 中的运算符类似的功能。</span><span class="sxs-lookup"><span data-stu-id="ecd67-114">The `x:Type` markup extension has a similar function to the `typeof()` operator in C# or the `GetType` operator in Microsoft Visual Basic.</span></span>

<span data-ttu-id="ecd67-115">标记`x:Type`扩展为采用 类型<xref:System.Type>的属性提供从字符串转换行为。</span><span class="sxs-lookup"><span data-stu-id="ecd67-115">The `x:Type` markup extension supplies a from-string conversion behavior for properties that take the type <xref:System.Type>.</span></span> <span data-ttu-id="ecd67-116">输入是 XAML 类型。</span><span class="sxs-lookup"><span data-stu-id="ecd67-116">The input is a XAML type.</span></span> <span data-ttu-id="ecd67-117">输入 XAML<xref:System.Type>类型和输出 CLR 之间的关系是输出<xref:System.Type>是输入<xref:System.Xaml.XamlType.UnderlyingType%2A><xref:System.Xaml.XamlType>的输出，在根据 XAML 架构<xref:System.Xaml.XamlType>上下文和<xref:System.Windows.Markup.IXamlTypeResolver>上下文提供的服务查找必要的结果后。</span><span class="sxs-lookup"><span data-stu-id="ecd67-117">The relationship between the input XAML type and the output CLR <xref:System.Type> is that the output <xref:System.Type> is the <xref:System.Xaml.XamlType.UnderlyingType%2A> of the input <xref:System.Xaml.XamlType>, after looking up the necessary <xref:System.Xaml.XamlType> based on XAML schema context and the <xref:System.Windows.Markup.IXamlTypeResolver> service the context provides.</span></span>

<span data-ttu-id="ecd67-118">在 .NET XAML 服务中，此标记扩展的处理由<xref:System.Windows.Markup.TypeExtension>类定义。</span><span class="sxs-lookup"><span data-stu-id="ecd67-118">In .NET XAML Services, the handling for this markup extension is defined by the <xref:System.Windows.Markup.TypeExtension> class.</span></span>

<span data-ttu-id="ecd67-119">在特定框架实现中，某些作为<xref:System.Type>值的属性可以直接接受类型的名称（类型的`Name`字符串值）。</span><span class="sxs-lookup"><span data-stu-id="ecd67-119">In specific framework implementations, some properties that take <xref:System.Type> as a value can accept the name of the type directly (the string value of the type `Name`).</span></span> <span data-ttu-id="ecd67-120">但是，实现此行为是一个复杂的方案。</span><span class="sxs-lookup"><span data-stu-id="ecd67-120">However, implementing this behavior is a complex scenario.</span></span> <span data-ttu-id="ecd67-121">有关示例，请参阅后面的"WPF 使用说明"部分。</span><span class="sxs-lookup"><span data-stu-id="ecd67-121">For examples, see the "WPF Usage Notes" section that follows.</span></span>

<span data-ttu-id="ecd67-122">特性语法是最常用于该标记扩展的语法。</span><span class="sxs-lookup"><span data-stu-id="ecd67-122">Attribute syntax is the most common syntax used with this markup extension.</span></span> <span data-ttu-id="ecd67-123">在 `x:Type` 标识符字符串之后提供的字符串标记被指定为基础 <xref:System.Windows.Markup.TypeExtension.TypeName%2A> 扩展类的 <xref:System.Windows.Markup.TypeExtension> 值。</span><span class="sxs-lookup"><span data-stu-id="ecd67-123">The string token provided after the `x:Type` identifier string is assigned as the <xref:System.Windows.Markup.TypeExtension.TypeName%2A> value of the underlying <xref:System.Windows.Markup.TypeExtension> extension class.</span></span> <span data-ttu-id="ecd67-124">在基于 CLR 类型的 .NET XAML 服务的默认 XAML 架构上下文中，此属性的值是<xref:System.Reflection.MemberInfo.Name%2A>所需类型的，或者包含<xref:System.Reflection.MemberInfo.Name%2A>非默认 XAML 命名空间映射的前缀。</span><span class="sxs-lookup"><span data-stu-id="ecd67-124">Under the default XAML schema context for .NET XAML Services, which is based on CLR types, the value of this attribute is either the <xref:System.Reflection.MemberInfo.Name%2A> of the desired type, or contains that <xref:System.Reflection.MemberInfo.Name%2A> preceded by a prefix for a non-default XAML namespace mapping.</span></span>

<span data-ttu-id="ecd67-125">标记`x:Type`扩展可用于对象元素语法。</span><span class="sxs-lookup"><span data-stu-id="ecd67-125">The `x:Type` markup extension can be used in object element syntax.</span></span> <span data-ttu-id="ecd67-126">在这种情况下，需要指定<xref:System.Windows.Markup.TypeExtension.TypeName%2A>属性的值才能正确初始化扩展。</span><span class="sxs-lookup"><span data-stu-id="ecd67-126">In this case, specifying the value of the <xref:System.Windows.Markup.TypeExtension.TypeName%2A> property is required to properly initialize the extension.</span></span>

<span data-ttu-id="ecd67-127">标记`x:Type`扩展也可以用作详细属性;但是，此用途并不常见：`<object property="{x:Type TypeName=typeNameValue}" .../>`</span><span class="sxs-lookup"><span data-stu-id="ecd67-127">The `x:Type` markup extension can also be used as a verbose attribute; however this use is not typical: `<object property="{x:Type TypeName=typeNameValue}" .../>`</span></span>

## <a name="wpf-usage-notes"></a><span data-ttu-id="ecd67-128">WPF 用法说明</span><span class="sxs-lookup"><span data-stu-id="ecd67-128">WPF Usage Notes</span></span>

### <a name="default-xaml-namespace-and-type-mapping"></a><span data-ttu-id="ecd67-129">默认 XAML 命名空间和类型映射</span><span class="sxs-lookup"><span data-stu-id="ecd67-129">Default XAML Namespace and Type Mapping</span></span>

<span data-ttu-id="ecd67-130">WPF 编程的默认 XAML 命名空间包含典型 XAML 方案所需的大多数 XAML 类型;因此，在引用 XAML 类型值时，通常可以避免前缀。</span><span class="sxs-lookup"><span data-stu-id="ecd67-130">The default XAML namespace for WPF programming contains most of the XAML types you need for typical XAML scenarios; therefore, you can often avoid prefixes when referencing XAML type values.</span></span> <span data-ttu-id="ecd67-131">如果要从自定义程序集引用类型或 WPF 程序集中存在但来自未映射到默认 XAML 命名空间的 CLR 命名空间的类型，则可能需要映射前缀。</span><span class="sxs-lookup"><span data-stu-id="ecd67-131">You might need to map a prefix if you are referencing a type from a custom assembly or for types that exist in a WPF assembly but are from a CLR namespace that was not mapped to the default XAML namespace.</span></span> <span data-ttu-id="ecd67-132">有关前缀、XAML 命名空间和映射 CLR 命名空间的详细信息，请参阅[WPF XAML 的 XAML 命名空间和命名空间映射](../../framework/wpf/advanced/xaml-namespaces-and-namespace-mapping-for-wpf-xaml.md)。</span><span class="sxs-lookup"><span data-stu-id="ecd67-132">For more information about prefixes, XAML namespaces, and mapping CLR namespaces, see [XAML Namespaces and Namespace Mapping for WPF XAML](../../framework/wpf/advanced/xaml-namespaces-and-namespace-mapping-for-wpf-xaml.md).</span></span>

### <a name="type-properties-that-support-typename-as-string"></a><span data-ttu-id="ecd67-133">类型属性支持类型名称作为字符串</span><span class="sxs-lookup"><span data-stu-id="ecd67-133">Type Properties That Support Typename-as-String</span></span>

<span data-ttu-id="ecd67-134">WPF 支持启用指定某些类型<xref:System.Type>属性的值而无需`x:Type`标记扩展用的技术。</span><span class="sxs-lookup"><span data-stu-id="ecd67-134">WPF supports techniques that enable specifying the value of some properties of type <xref:System.Type> without requiring an `x:Type` markup extension usage.</span></span> <span data-ttu-id="ecd67-135">相反，您可以将该值指定为命名类型的字符串。</span><span class="sxs-lookup"><span data-stu-id="ecd67-135">Instead, you can specify the value as a string that names the type.</span></span> <span data-ttu-id="ecd67-136">这方面的示例是<xref:System.Windows.Controls.ControlTemplate.TargetType%2A?displayProperty=nameWithType>和<xref:System.Windows.Style.TargetType%2A?displayProperty=nameWithType>。</span><span class="sxs-lookup"><span data-stu-id="ecd67-136">Examples of this are <xref:System.Windows.Controls.ControlTemplate.TargetType%2A?displayProperty=nameWithType> and <xref:System.Windows.Style.TargetType%2A?displayProperty=nameWithType>.</span></span> <span data-ttu-id="ecd67-137">不支持此行为不会通过类型转换器或标记扩展提供。</span><span class="sxs-lookup"><span data-stu-id="ecd67-137">Support for this behavior is not provided through either type converters or markup extensions.</span></span> <span data-ttu-id="ecd67-138">相反，这是通过<xref:System.Windows.FrameworkElementFactory>实现的延迟行为。</span><span class="sxs-lookup"><span data-stu-id="ecd67-138">Instead, this is a deferral behavior implemented through <xref:System.Windows.FrameworkElementFactory>.</span></span>

<span data-ttu-id="ecd67-139">银光支持类似的约定。</span><span class="sxs-lookup"><span data-stu-id="ecd67-139">Silverlight supports a similar convention.</span></span> <span data-ttu-id="ecd67-140">事实上，Silverlight 目前不支持`{x:Type}`其 XAML 语言支持，并且不接受`{x:Type}`用于支持 WPF-Silverlight XAML 迁移的少数情况以外的用法。</span><span class="sxs-lookup"><span data-stu-id="ecd67-140">In fact, Silverlight does not currently support `{x:Type}` in its XAML language support, and does not accept `{x:Type}` usages outside of a few circumstances that are intended to support WPF-Silverlight XAML migration.</span></span> <span data-ttu-id="ecd67-141">因此，类型名称即字符串行为内置于所有 Silverlight 本机属性计算中， <xref:System.Type></span><span class="sxs-lookup"><span data-stu-id="ecd67-141">Therefore, the typename-as-string behavior is built-in to all Silverlight native property evaluation where a <xref:System.Type> is the value.</span></span>

## <a name="xaml-2009"></a><span data-ttu-id="ecd67-142">XAML 2009</span><span class="sxs-lookup"><span data-stu-id="ecd67-142">XAML 2009</span></span>

<span data-ttu-id="ecd67-143">XAML 2009 为泛型类型提供了其他支持，并修改了`x:TypeArguments`和`x:Type`的功能行为，并提供此支持。</span><span class="sxs-lookup"><span data-stu-id="ecd67-143">XAML 2009 provides additional support for generic types and modifies the feature behavior of `x:TypeArguments` and `x:Type` to provide this support.</span></span>

- <span data-ttu-id="ecd67-144">`x:TypeArguments`泛型对象实例化的关联对象元素可以位于根以外的元素上。</span><span class="sxs-lookup"><span data-stu-id="ecd67-144">`x:TypeArguments` and the associated object element for a generic object instantiation can be on elements other than the root.</span></span> <span data-ttu-id="ecd67-145">有关详细信息，请参阅[x：Type参数指令](xtypearguments-directive.md)的"XAML 2009"部分。</span><span class="sxs-lookup"><span data-stu-id="ecd67-145">For more information, see the "XAML 2009" section of [x:TypeArguments Directive](xtypearguments-directive.md).</span></span>

- <span data-ttu-id="ecd67-146">XAML 2009 支持用于在标记中指定泛型类型约束的语法。</span><span class="sxs-lookup"><span data-stu-id="ecd67-146">XAML 2009 supports a syntax for specifying a generic type's constraint in markup.</span></span> <span data-ttu-id="ecd67-147">这可以通过`x:TypeArguments`、由`x:Type`或两个要素组合使用。</span><span class="sxs-lookup"><span data-stu-id="ecd67-147">This can be used by `x:TypeArguments`, by `x:Type`, or by the two features in combination.</span></span>

- <span data-ttu-id="ecd67-148">处理 XAML 2009 负载时实现的 WPF XAML 也会将此功能添加到使用 类型 的某些<xref:System.Type>框架属性的隐式类型转换行为中。</span><span class="sxs-lookup"><span data-stu-id="ecd67-148">WPF XAML implementation when processing XAML 2009 for load also adds this capability to the implicit type conversion behavior for certain framework properties that use type <xref:System.Type>.</span></span>

<span data-ttu-id="ecd67-149">在 WPF 中，可以使用 XAML 2009 功能，但仅适用于松散的 XAML（未标记编译的 XAML）。</span><span class="sxs-lookup"><span data-stu-id="ecd67-149">In WPF, you can use XAML 2009 features but only for loose XAML (XAML that is not markup-compiled).</span></span> <span data-ttu-id="ecd67-150">WPF 的已编译标记的 XAML 以及 XAML 的 BAML 形式当前不支持 XAML 2009 关键字和功能。</span><span class="sxs-lookup"><span data-stu-id="ecd67-150">Markup-compiled XAML for WPF and the BAML form of XAML do not currently support the XAML 2009 keywords and features.</span></span>

## <a name="see-also"></a><span data-ttu-id="ecd67-151">请参阅</span><span class="sxs-lookup"><span data-stu-id="ecd67-151">See also</span></span>

- <xref:System.Windows.Style>
- [<span data-ttu-id="ecd67-152">样式设置和模板化</span><span class="sxs-lookup"><span data-stu-id="ecd67-152">Styling and Templating</span></span>](../fundamentals/styles-templates-overview.md)
- [<span data-ttu-id="ecd67-153">XAML 概述 (WPF)</span><span class="sxs-lookup"><span data-stu-id="ecd67-153">XAML Overview (WPF)</span></span>](../fundamentals/xaml.md)
- [<span data-ttu-id="ecd67-154">标记扩展和 WPF XAML</span><span class="sxs-lookup"><span data-stu-id="ecd67-154">Markup Extensions and WPF XAML</span></span>](../../framework/wpf/advanced/markup-extensions-and-wpf-xaml.md)
