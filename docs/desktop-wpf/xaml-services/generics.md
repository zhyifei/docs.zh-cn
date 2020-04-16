---
title: XAML 中的泛型
ms.date: 03/30/2017
helpviewer_keywords:
- generics [XAML Services]
ms.assetid: 835bfed7-585c-4216-ae67-b674edab8b92
ms.openlocfilehash: 9354f74b978652c36df28a91a6b9db5cfff4bb1e
ms.sourcegitcommit: c2d9718996402993cf31541f11e95531bc68bad0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/27/2020
ms.locfileid: "81432958"
---
# <a name="generics-in-xaml"></a><span data-ttu-id="04afd-102">XAML 中的泛型</span><span class="sxs-lookup"><span data-stu-id="04afd-102">Generics in XAML</span></span>

<span data-ttu-id="04afd-103">.NET XAML 服务（<xref:System.Xaml?displayProperty=fullName>如实现）支持使用通用 CLR 类型。</span><span class="sxs-lookup"><span data-stu-id="04afd-103">.NET XAML Services as implemented in <xref:System.Xaml?displayProperty=fullName> provides support for using generic CLR types.</span></span> <span data-ttu-id="04afd-104">此支持包括指定泛型的约束作为类型参数，并通过调用泛型集合案例的适当`Add`方法来强制执行约束。</span><span class="sxs-lookup"><span data-stu-id="04afd-104">This support includes specifying the constraints of generics as a type argument and enforcing the constraint by calling the appropriate `Add` method for generic collection cases.</span></span> <span data-ttu-id="04afd-105">本主题介绍在 XAML 中使用和引用泛型类型的方面。</span><span class="sxs-lookup"><span data-stu-id="04afd-105">This topic describes aspects of using and referencing generic types in XAML.</span></span>

## <a name="xtypearguments"></a><span data-ttu-id="04afd-106">x：类型参数</span><span class="sxs-lookup"><span data-stu-id="04afd-106">x:TypeArguments</span></span>

<span data-ttu-id="04afd-107">`x:TypeArguments`是由 XAML 语言定义的指令。</span><span class="sxs-lookup"><span data-stu-id="04afd-107">`x:TypeArguments` is a directive defined by the XAML language.</span></span> <span data-ttu-id="04afd-108">当它用作由泛型类型支持的 XAML 类型的成员时，`x:TypeArguments`将泛型的约束类型参数传递给支持构造函数。</span><span class="sxs-lookup"><span data-stu-id="04afd-108">When it is used as a member of a XAML type that is backed by a generic type, `x:TypeArguments` passes constraining type arguments of the generic to the backing constructor.</span></span> <span data-ttu-id="04afd-109">有关 与 .NET XAML 服务使用 相关的`x:TypeArguments`引用语法，其中包括语法示例，请参阅[x：TypeArguments 指令](xtypearguments-directive.md)。</span><span class="sxs-lookup"><span data-stu-id="04afd-109">For reference syntax that pertains to .NET XAML Services use of `x:TypeArguments`, which includes syntax examples, see [x:TypeArguments Directive](xtypearguments-directive.md).</span></span>

<span data-ttu-id="04afd-110">由于`x:TypeArguments`采用字符串，并且具有类型转换器支持，因此通常在 XAML 用法中声明为属性。</span><span class="sxs-lookup"><span data-stu-id="04afd-110">Because `x:TypeArguments` takes a string, and has type converter backing, it is typically declared in XAML usage as an attribute.</span></span>

<span data-ttu-id="04afd-111">在 XAML 节点流中，可以从节点`x:TypeArguments`流中`StartObject`的位置获取<xref:System.Xaml.XamlType.TypeArguments%2A?displayProperty=nameWithType>声明的信息。</span><span class="sxs-lookup"><span data-stu-id="04afd-111">In the XAML node stream, the information declared by `x:TypeArguments` can be obtained from <xref:System.Xaml.XamlType.TypeArguments%2A?displayProperty=nameWithType> at a `StartObject` position in the node stream.</span></span> <span data-ttu-id="04afd-112">的返回值<xref:System.Xaml.XamlType.TypeArguments%2A?displayProperty=nameWithType>是值的列表<xref:System.Xaml.XamlType>。</span><span class="sxs-lookup"><span data-stu-id="04afd-112">The return value of <xref:System.Xaml.XamlType.TypeArguments%2A?displayProperty=nameWithType> is a list of <xref:System.Xaml.XamlType> values.</span></span> <span data-ttu-id="04afd-113">可以通过调用<xref:System.Xaml.XamlType.IsGeneric%2A?displayProperty=nameWithType>确定 XAML 类型是否表示泛型类型。</span><span class="sxs-lookup"><span data-stu-id="04afd-113">Determination of whether a XAML type represents a generic type can be made by calling <xref:System.Xaml.XamlType.IsGeneric%2A?displayProperty=nameWithType>.</span></span>

## <a name="rules-and-syntax-conventions-for-generics-in-xaml"></a><span data-ttu-id="04afd-114">XAML 中泛型的规则和语法约定</span><span class="sxs-lookup"><span data-stu-id="04afd-114">Rules and Syntax Conventions for Generics in XAML</span></span>

<span data-ttu-id="04afd-115">在 XAML 中，泛型类型必须始终表示为受约束的泛型。</span><span class="sxs-lookup"><span data-stu-id="04afd-115">In XAML, a generic type must always be represented as a constrained generic.</span></span> <span data-ttu-id="04afd-116">无约束泛型永远不会存在于 XAML 类型系统或 XAML 节点流中，并且不能在 XAML 标记中表示。</span><span class="sxs-lookup"><span data-stu-id="04afd-116">An unconstrained generic is never present in the XAML type system or a XAML node stream and cannot be represented in XAML markup.</span></span> <span data-ttu-id="04afd-117">泛型可以在 XAML 属性语法中引用，用于对于泛型是 被`x:TypeArguments`引用的泛型的嵌套类型约束的情况，或者对于`x:Type`为泛型类型提供 CLR 类型引用的情况。</span><span class="sxs-lookup"><span data-stu-id="04afd-117">A generic can be referenced within XAML attribute syntax for cases where it is a nested type constraint of a generic being referenced by `x:TypeArguments`, or for cases where `x:Type` supplies a CLR type reference for a generic type.</span></span> <span data-ttu-id="04afd-118">通过 .NET XAML<xref:System.Xaml.Schema.XamlTypeTypeConverter>服务定义的类支持引用泛型。</span><span class="sxs-lookup"><span data-stu-id="04afd-118">Referencing generics is supported through the <xref:System.Xaml.Schema.XamlTypeTypeConverter> class defined by .NET XAML Services.</span></span>

<span data-ttu-id="04afd-119">XAML 属性语法窗体通过<xref:System.Xaml.Schema.XamlTypeTypeConverter>更改典型的 MSIL/ CLR 语法约定而启用，该约定使用角度括号来表示泛型的类型和约束，而是替换约束容器的括号。</span><span class="sxs-lookup"><span data-stu-id="04afd-119">The XAML attribute syntax form enabled by <xref:System.Xaml.Schema.XamlTypeTypeConverter> alters the typical MSIL / CLR syntax convention that uses angle brackets for types and constraints of generics, and instead substitutes parentheses for the constraint container.</span></span> <span data-ttu-id="04afd-120">例如，请参阅[x：Type参数指令](xtypearguments-directive.md)。</span><span class="sxs-lookup"><span data-stu-id="04afd-120">For an example, see [x:TypeArguments Directive](xtypearguments-directive.md).</span></span>

## <a name="generics-and-xaml-2009-features"></a><span data-ttu-id="04afd-121">泛型和 XAML 2009 功能</span><span class="sxs-lookup"><span data-stu-id="04afd-121">Generics and XAML 2009 Features</span></span>

<span data-ttu-id="04afd-122">如果使用 XAML 2009 而不是映射 CLR 基类型以获取通用语言基元中的 XAML 类型，则可以使用[XAML 2009 内置类型](types-for-primitives.md)作为 中`x:TypeArguments`的信息项。</span><span class="sxs-lookup"><span data-stu-id="04afd-122">If you use XAML 2009 instead of mapping the CLR base types to obtain XAML types for common language primitives, you can use [XAML 2009 built-in types](types-for-primitives.md) as information items in `x:TypeArguments`.</span></span> <span data-ttu-id="04afd-123">例如，您可以声明以下内容（未显示前缀映射，但`x`XAML 语言 XAML 2009 的命名空间）：</span><span class="sxs-lookup"><span data-stu-id="04afd-123">For example, you could declare the following (prefix mappings not shown, but `x` is the XAML language XAML namespace for XAML 2009):</span></span>

```xaml
<my:BusinessObject x:TypeArguments="x:String,x:Int32"/>
```

## <a name="generics-support-in-wpf"></a><span data-ttu-id="04afd-124">WPF 中的通用支持</span><span class="sxs-lookup"><span data-stu-id="04afd-124">Generics Support in WPF</span></span>

<span data-ttu-id="04afd-125">对于专门针对 WPF 的 XAML 2006 用法，x：class 还必须[x:Class](xclass-directive.md)提供`x:TypeArguments`与 的元素，并且该元素必须是 XAML 文档中的根元素。</span><span class="sxs-lookup"><span data-stu-id="04afd-125">For XAML 2006 usage when specifically targeting WPF, [x:Class](xclass-directive.md) must also be provided on the same element as `x:TypeArguments`, and that element must be the root element in a XAML document.</span></span> <span data-ttu-id="04afd-126">根元素必须映射到具有至少一个类型参数的泛型类型。</span><span class="sxs-lookup"><span data-stu-id="04afd-126">The root element must map to a generic type with at least one type argument.</span></span> <span data-ttu-id="04afd-127">示例为 <xref:System.Windows.Navigation.PageFunction%601>。</span><span class="sxs-lookup"><span data-stu-id="04afd-127">An example is <xref:System.Windows.Navigation.PageFunction%601>.</span></span>

<span data-ttu-id="04afd-128">支持泛型用法的可能解决方法包括定义可以返回泛型类型的自定义标记扩展，或提供从泛型类型派生但在其自己的类定义中平展泛型约束的换行类定义。</span><span class="sxs-lookup"><span data-stu-id="04afd-128">Possible workarounds to support generic usages include defining a custom markup extension that can return generic types, or providing a wrapping class definition that derives from a generic type but flattens the generic constraint in its own class definition.</span></span>

<span data-ttu-id="04afd-129">在 WPF 中，您可以将 XAML 2009 功能与 一起使用`x:TypeArguments`，但仅适用于松散的 XAML（未标记编译的 XAML）。</span><span class="sxs-lookup"><span data-stu-id="04afd-129">In WPF you can use XAML 2009 features together with `x:TypeArguments`, but only for loose XAML (XAML that is not markup-compiled).</span></span> <span data-ttu-id="04afd-130">WPF 的已编译标记的 XAML 以及 XAML 的 BAML 形式当前不支持 XAML 2009 关键字和功能。</span><span class="sxs-lookup"><span data-stu-id="04afd-130">Markup-compiled XAML for WPF and the BAML form of XAML do not currently support the XAML 2009 keywords and features.</span></span>

<span data-ttu-id="04afd-131">.NET 框架 3.5 的 Windows 工作流基础中的自定义工作流不支持通用的 XAML 使用。</span><span class="sxs-lookup"><span data-stu-id="04afd-131">Custom workflows in Windows Workflow Foundation for .NET Framework 3.5 do not support generic XAML usage.</span></span>

## <a name="see-also"></a><span data-ttu-id="04afd-132">请参阅</span><span class="sxs-lookup"><span data-stu-id="04afd-132">See also</span></span>

- [<span data-ttu-id="04afd-133">x:TypeArguments 指令</span><span class="sxs-lookup"><span data-stu-id="04afd-133">x:TypeArguments Directive</span></span>](xtypearguments-directive.md)
- [<span data-ttu-id="04afd-134">x:Class 指令</span><span class="sxs-lookup"><span data-stu-id="04afd-134">x:Class Directive</span></span>](xclass-directive.md)
- [<span data-ttu-id="04afd-135">常见 XAML 语言基元的内置类型</span><span class="sxs-lookup"><span data-stu-id="04afd-135">Built-in Types for Common XAML Language Primitives</span></span>](types-for-primitives.md)
