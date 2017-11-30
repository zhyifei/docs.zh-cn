---
title: "XAML 中的泛型"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: generics [XAML Services]
ms.assetid: 835bfed7-585c-4216-ae67-b674edab8b92
caps.latest.revision: "8"
author: wadepickett
ms.author: wpickett
manager: wpickett
ms.openlocfilehash: 05eaab4497949231d32ceab0ba696b9f252d67ad
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="generics-in-xaml"></a><span data-ttu-id="41526-102">XAML 中的泛型</span><span class="sxs-lookup"><span data-stu-id="41526-102">Generics in XAML</span></span>
<span data-ttu-id="41526-103">.NET Framework XAML 服务在 System.Xaml 中实现提供对使用泛型的 CLR 类型的支持。</span><span class="sxs-lookup"><span data-stu-id="41526-103">The .NET Framework XAML Services as implemented in System.Xaml provides support for using generic CLR types.</span></span> <span data-ttu-id="41526-104">这种支持包括作为类型参数指定的泛型约束和通过调用适当强制约束`Add`泛型集合用例的方法。</span><span class="sxs-lookup"><span data-stu-id="41526-104">This support includes specifying the constraints of generics as a type argument and enforcing the constraint by calling the appropriate `Add` method for generic collection cases.</span></span> <span data-ttu-id="41526-105">本主题描述使用和引用 XAML 中的泛型类型的方面。</span><span class="sxs-lookup"><span data-stu-id="41526-105">This topic describes aspects of using and referencing generic types in XAML.</span></span>  
  
## <a name="xtypearguments"></a><span data-ttu-id="41526-106">x: TypeArguments</span><span class="sxs-lookup"><span data-stu-id="41526-106">x:TypeArguments</span></span>  
 <span data-ttu-id="41526-107">`x:TypeArguments`由 XAML 语言定义的指令。</span><span class="sxs-lookup"><span data-stu-id="41526-107">`x:TypeArguments` is a directive defined by the XAML language.</span></span> <span data-ttu-id="41526-108">当使用作为泛型类型，由支持的 XAML 类型的成员`x:TypeArguments`约束类型的泛型后备构造函数的参数传递。</span><span class="sxs-lookup"><span data-stu-id="41526-108">When it is used as a member of a XAML type that is backed by a generic type, `x:TypeArguments` passes constraining type arguments of the generic to the backing constructor.</span></span> <span data-ttu-id="41526-109">有关适用于.NET Framework XAML 服务的引用语法用法的`x:TypeArguments`，其中包括语法示例，请参阅[X:typearguments 指令](../../../docs/framework/xaml-services/x-typearguments-directive.md)。</span><span class="sxs-lookup"><span data-stu-id="41526-109">For reference syntax that pertains to .NET Framework XAML Services use of `x:TypeArguments`, which includes syntax examples, see [x:TypeArguments Directive](../../../docs/framework/xaml-services/x-typearguments-directive.md).</span></span>  
  
 <span data-ttu-id="41526-110">因为`x:TypeArguments`接收一个字符串，并具有类型转换器支持，通常将其声明中作为特性的 XAML 用法。</span><span class="sxs-lookup"><span data-stu-id="41526-110">Because `x:TypeArguments` takes a string, and has type converter backing, it is typically declared in XAML usage as an attribute.</span></span>  
  
 <span data-ttu-id="41526-111">在 XAML 节点流中，通过声明`x:TypeArguments`可以从获取<xref:System.Xaml.XamlType.TypeArguments%2A?displayProperty=nameWithType>在`StartObject`节点流中的位置。</span><span class="sxs-lookup"><span data-stu-id="41526-111">In the XAML node stream, the information declared by `x:TypeArguments` can be obtained from <xref:System.Xaml.XamlType.TypeArguments%2A?displayProperty=nameWithType> at a `StartObject` position in the node stream.</span></span> <span data-ttu-id="41526-112">返回值<xref:System.Xaml.XamlType.TypeArguments%2A?displayProperty=nameWithType>是一份<xref:System.Xaml.XamlType>值。</span><span class="sxs-lookup"><span data-stu-id="41526-112">The return value of <xref:System.Xaml.XamlType.TypeArguments%2A?displayProperty=nameWithType> is a list of <xref:System.Xaml.XamlType> values.</span></span> <span data-ttu-id="41526-113">可以通过调用来发出的 XAML 类型是否表示泛型类型的决定<xref:System.Xaml.XamlType.IsGeneric%2A?displayProperty=nameWithType>。</span><span class="sxs-lookup"><span data-stu-id="41526-113">Determination of whether a XAML type represents a generic type can be made by calling <xref:System.Xaml.XamlType.IsGeneric%2A?displayProperty=nameWithType>.</span></span>  
  
## <a name="rules-and-syntax-conventions-for-generics-in-xaml"></a><span data-ttu-id="41526-114">规则和 XAML 中的泛型的语法约定</span><span class="sxs-lookup"><span data-stu-id="41526-114">Rules and Syntax Conventions for Generics in XAML</span></span>  
 <span data-ttu-id="41526-115">在 XAML 中，泛型类型必须始终表示为受约束的泛型;不受约束的泛型根本不在 XAML 类型系统或 XAML 节点流中存在且不能在 XAML 标记中表示。</span><span class="sxs-lookup"><span data-stu-id="41526-115">In XAML, a generic type must always be represented as a constrained generic; an unconstrained generic is never present in the XAML type system or a XAML node stream and cannot be represented in XAML markup.</span></span> <span data-ttu-id="41526-116">可以在其所在的被引用的泛型的嵌套的类型约束的情况下用于 XAML 特性语法中引用泛型`x:TypeArguments`，或用例其中`x:Type`提供泛型类型的 CLR 类型引用。</span><span class="sxs-lookup"><span data-stu-id="41526-116">A generic can be referenced within XAML attribute syntax, for cases where it is a nested type constraint of a generic being referenced by `x:TypeArguments`, or for cases where `x:Type` supplies a CLR type reference for a generic type.</span></span> <span data-ttu-id="41526-117">通过支持这种情况<xref:System.Xaml.Schema.XamlTypeTypeConverter>由.NET Framework XAML 服务定义的类。</span><span class="sxs-lookup"><span data-stu-id="41526-117">This is supported through the <xref:System.Xaml.Schema.XamlTypeTypeConverter> class defined by .NET Framework XAML Services.</span></span>  
  
 <span data-ttu-id="41526-118">XAML 属性语法形式由启用<xref:System.Xaml.Schema.XamlTypeTypeConverter>改变典型 MSIL / 使用角度的 CLR 语法约定的类型和泛型，约束方括号，改为将约束容器的括号。</span><span class="sxs-lookup"><span data-stu-id="41526-118">The XAML attribute syntax form enabled by <xref:System.Xaml.Schema.XamlTypeTypeConverter> alters the typical MSIL / CLR syntax convention that uses angle brackets for types and constraints of generics, and instead substitutes parentheses for the constraint container.</span></span> <span data-ttu-id="41526-119">有关示例，请参阅[X:typearguments 指令](../../../docs/framework/xaml-services/x-typearguments-directive.md)。</span><span class="sxs-lookup"><span data-stu-id="41526-119">For an example, see [x:TypeArguments Directive](../../../docs/framework/xaml-services/x-typearguments-directive.md).</span></span>  
  
## <a name="generics-and-xaml-2009-features"></a><span data-ttu-id="41526-120">泛型和 XAML 2009 功能</span><span class="sxs-lookup"><span data-stu-id="41526-120">Generics and XAML 2009 Features</span></span>  
 <span data-ttu-id="41526-121">如果使用 XAML 2009 而不是将 CLR 映射基类型，用于获取的公共语言基元的 XAML 类型转换，则可以使用[XAML 2009 内置类型](../../../docs/framework/xaml-services/built-in-types-for-common-xaml-language-primitives.md)信息在中作为项`x:TypeArguments`。</span><span class="sxs-lookup"><span data-stu-id="41526-121">If you use XAML 2009 instead of mapping the CLR base types to obtain XAML types for common language primitives, you can use [XAML 2009 built-in types](../../../docs/framework/xaml-services/built-in-types-for-common-xaml-language-primitives.md) as information items in `x:TypeArguments`.</span></span> <span data-ttu-id="41526-122">例如，可以声明以下 (前缀映射未显示，但`x`是 XAML 2009 的 XAML 语言 XAML 命名空间):</span><span class="sxs-lookup"><span data-stu-id="41526-122">For example, you could declare the following (prefix mappings not shown, but `x` is the XAML language XAML namespace for XAML 2009):</span></span>  
  
```xaml  
<my:BusinessObject x:TypeArguments="x:String,x:Int32"/>  
```  
  
## <a name="generics-support-in-wpf-and-other-v35-frameworks"></a><span data-ttu-id="41526-123">WPF 和其他 v3.5 框架中的泛型支持</span><span class="sxs-lookup"><span data-stu-id="41526-123">Generics Support in WPF and Other v3.5 Frameworks</span></span>  
 <span data-ttu-id="41526-124">有关 XAML 2006 用法时特别面向 WPF 中， [X:class](../../../docs/framework/xaml-services/x-class-directive.md)还必须在与位于同一元素上提供`x:TypeArguments`，并且该元素必须在 XAML 文档的根元素。</span><span class="sxs-lookup"><span data-stu-id="41526-124">For XAML 2006 usage when specifically targeting WPF, [x:Class](../../../docs/framework/xaml-services/x-class-directive.md) must also be provided on the same element as `x:TypeArguments`, and that element must be the root element in a XAML document.</span></span> <span data-ttu-id="41526-125">根元素必须映射到具有至少一个类型参数的泛型类型。</span><span class="sxs-lookup"><span data-stu-id="41526-125">The root element must map to a generic type with at least one type argument.</span></span> <span data-ttu-id="41526-126">一个示例是<xref:System.Windows.Navigation.PageFunction%601>。</span><span class="sxs-lookup"><span data-stu-id="41526-126">An example is <xref:System.Windows.Navigation.PageFunction%601>.</span></span>  
  
 <span data-ttu-id="41526-127">可能的解决方法，以支持泛型用法包括定义自定义标记扩展可以返回的泛型类型，或提供一个包装类定义派生自泛型类型，但将在其自己的类定义中的泛型约束平展开。</span><span class="sxs-lookup"><span data-stu-id="41526-127">Possible workarounds to support generic usages include defining a custom markup extension that can return generic types, or providing a wrapping class definition that derives from a generic type but flattens the generic constraint in its own class definition.</span></span>  
  
 <span data-ttu-id="41526-128">在 WPF 和目标确定[!INCLUDE[net_v40_short](../../../includes/net-v40-short-md.md)]，你可以使用 XAML 2009 功能以及`x:TypeArguments`，但仅针对宽松 XAML (未标记编译的 XAML)。</span><span class="sxs-lookup"><span data-stu-id="41526-128">In WPF and targeting [!INCLUDE[net_v40_short](../../../includes/net-v40-short-md.md)], you can use XAML 2009 features together with `x:TypeArguments`, but only for loose XAML (XAML that is not markup-compiled).</span></span> <span data-ttu-id="41526-129">WPF 的已编译标记的 XAML 以及 XAML 的 BAML 形式当前不支持 XAML 2009 关键字和功能。</span><span class="sxs-lookup"><span data-stu-id="41526-129">Markup-compiled XAML for WPF and the BAML form of XAML do not currently support the XAML 2009 keywords and features.</span></span>  
  
 <span data-ttu-id="41526-130">中的自定义工作流[!INCLUDE[TLA#tla_workflow](../../../includes/tlasharptla-workflow-md.md)]为[!INCLUDE[net_v35_short](../../../includes/net-v35-short-md.md)]不支持泛型 XAML 用法。</span><span class="sxs-lookup"><span data-stu-id="41526-130">Custom workflows in [!INCLUDE[TLA#tla_workflow](../../../includes/tlasharptla-workflow-md.md)] for [!INCLUDE[net_v35_short](../../../includes/net-v35-short-md.md)] do not support generic XAML usage.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="41526-131">另请参阅</span><span class="sxs-lookup"><span data-stu-id="41526-131">See Also</span></span>  
 [<span data-ttu-id="41526-132">x:TypeArguments 指令</span><span class="sxs-lookup"><span data-stu-id="41526-132">x:TypeArguments Directive</span></span>](../../../docs/framework/xaml-services/x-typearguments-directive.md)  
 [<span data-ttu-id="41526-133">x:Class 指令</span><span class="sxs-lookup"><span data-stu-id="41526-133">x:Class Directive</span></span>](../../../docs/framework/xaml-services/x-class-directive.md)  
 [<span data-ttu-id="41526-134">常见 XAML 语言基元的内置类型</span><span class="sxs-lookup"><span data-stu-id="41526-134">Built-in Types for Common XAML Language Primitives</span></span>](../../../docs/framework/xaml-services/built-in-types-for-common-xaml-language-primitives.md)
