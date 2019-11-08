---
title: x:Static 标记扩展
ms.date: 03/30/2017
f1_keywords:
- StaticExtension
- xStatic
- x:Static
helpviewer_keywords:
- x:Static markup extension [XAML Services]
- Static markup extension in XAML [XAML Services]
- XAML [XAML Services], x:Static markup extension
ms.assetid: 056aee79-7cdd-434f-8174-dfc856cad343
ms.openlocfilehash: bf94f1d61ee3080c9d3582e55e0695b269801c80
ms.sourcegitcommit: 22be09204266253d45ece46f51cc6f080f2b3fd6
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/07/2019
ms.locfileid: "73733358"
---
# <a name="xstatic-markup-extension"></a><span data-ttu-id="302d2-102">x:Static 标记扩展</span><span class="sxs-lookup"><span data-stu-id="302d2-102">x:Static Markup Extension</span></span>
<span data-ttu-id="302d2-103">引用以符合公共语言规范（CLS）的方式定义的任何静态按值的代码实体。</span><span class="sxs-lookup"><span data-stu-id="302d2-103">References any static by-value code entity that is defined in a Common Language Specification (CLS)–compliant way.</span></span> <span data-ttu-id="302d2-104">引用的静态属性可用于在 XAML 中提供属性的值。</span><span class="sxs-lookup"><span data-stu-id="302d2-104">The static property that is referenced can be used to provide the value of a property in XAML.</span></span>  
  
## <a name="xaml-attribute-usage"></a><span data-ttu-id="302d2-105">XAML 属性用法</span><span class="sxs-lookup"><span data-stu-id="302d2-105">XAML Attribute Usage</span></span>  
  
```xaml  
<object property="{x:Static prefix:typeName.staticMemberName}" .../>  
```  
  
## <a name="xaml-values"></a><span data-ttu-id="302d2-106">XAML 值</span><span class="sxs-lookup"><span data-stu-id="302d2-106">XAML Values</span></span>  
  
| | |  
|-|-|  
|`prefix`|<span data-ttu-id="302d2-107">可选。</span><span class="sxs-lookup"><span data-stu-id="302d2-107">Optional.</span></span> <span data-ttu-id="302d2-108">引用映射的非默认 XAML 命名空间的前缀。</span><span class="sxs-lookup"><span data-stu-id="302d2-108">A prefix that refers to a mapped, non-default XAML namespace.</span></span> <span data-ttu-id="302d2-109">由于很少引用来自默认 XAML 命名空间的静态属性，因此在用法中显式显示了 `prefix`。</span><span class="sxs-lookup"><span data-stu-id="302d2-109">`prefix` is shown explicitly in the usage because you rarely reference static properties that come from a default XAML namespace.</span></span> <span data-ttu-id="302d2-110">请参阅“备注”。</span><span class="sxs-lookup"><span data-stu-id="302d2-110">See Remarks.</span></span>|  
|`typeName`|<span data-ttu-id="302d2-111">必须的。</span><span class="sxs-lookup"><span data-stu-id="302d2-111">Required.</span></span> <span data-ttu-id="302d2-112">定义所需静态成员的类型的名称。</span><span class="sxs-lookup"><span data-stu-id="302d2-112">The name of the type that defines the desired static member.</span></span>|  
|`staticMemberName`|<span data-ttu-id="302d2-113">必须的。</span><span class="sxs-lookup"><span data-stu-id="302d2-113">Required.</span></span> <span data-ttu-id="302d2-114">所需的静态值成员的名称（常量、静态属性、字段或枚举值）。</span><span class="sxs-lookup"><span data-stu-id="302d2-114">The name of the desired static value member (a constant, a static property, a field, or an enumeration value).</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="302d2-115">备注</span><span class="sxs-lookup"><span data-stu-id="302d2-115">Remarks</span></span>  

<span data-ttu-id="302d2-116">引用的代码实体必须是以下项之一：</span><span class="sxs-lookup"><span data-stu-id="302d2-116">The code entity that is referenced must be one of the following:</span></span>  
  
- <span data-ttu-id="302d2-117">常量</span><span class="sxs-lookup"><span data-stu-id="302d2-117">A constant</span></span>  
- <span data-ttu-id="302d2-118">静态属性</span><span class="sxs-lookup"><span data-stu-id="302d2-118">A static property</span></span>  
- <span data-ttu-id="302d2-119">一个字段</span><span class="sxs-lookup"><span data-stu-id="302d2-119">A field</span></span>  
- <span data-ttu-id="302d2-120">枚举值</span><span class="sxs-lookup"><span data-stu-id="302d2-120">An enumeration value</span></span>

<span data-ttu-id="302d2-121">如果指定任何其他代码实体（如非静态属性），则会导致编译时错误，如果已编译了 XAML 或 XAML 加载时分析异常，则会引发编译时错误。</span><span class="sxs-lookup"><span data-stu-id="302d2-121">Specifying any other code entity, such as a nonstatic property, causes a compile-time error if the XAML is markup compiled, or a XAML load-time parse exception.</span></span>  

<span data-ttu-id="302d2-122">您可以对当前 XAML 文档的默认 XAML 命名空间中不是的静态字段或属性进行 `x:Static` 引用;但是，这需要前缀映射。</span><span class="sxs-lookup"><span data-stu-id="302d2-122">You can make `x:Static` references to static fields or properties that are not in the default XAML namespace for the current XAML document; however, this requires a prefix mapping.</span></span> <span data-ttu-id="302d2-123">XAML 命名空间几乎始终在 XAML 文档的根元素上定义。</span><span class="sxs-lookup"><span data-stu-id="302d2-123">XAML namespaces are almost always defined on the root element of the XAML document.</span></span>  

<span data-ttu-id="302d2-124">当 XAML 服务及其 XAML 读取器和 XAML 编写器运行时，可 .NET Framework 通过默认的 XAML 架构上下文来执行静态属性的查找操作。</span><span class="sxs-lookup"><span data-stu-id="302d2-124">The lookup operations for static properties can be performed by .NET Framework XAML Services and its XAML readers and XAML writers, when they are running with the default XAML schema context.</span></span> <span data-ttu-id="302d2-125">此 XAML 架构上下文可以使用 CLR 反射为对象图构造提供必要的静态值。</span><span class="sxs-lookup"><span data-stu-id="302d2-125">This XAML schema context can use CLR reflection to provide the necessary static values for object graph construction.</span></span> <span data-ttu-id="302d2-126">指定的 `typeName` 实际上是 XAML 类型名称，而不是 CLR 类型名称，不过，在使用默认 XAML 架构上下文或使用所有基于 CLR 的现有 XAML 实现框架时，这些名称本质上是相同的名称。</span><span class="sxs-lookup"><span data-stu-id="302d2-126">The `typeName` you specify is actually a XAML type name, not a CLR type name, although these are essentially the same name when using the default XAML schema context or when using all existing CLR-based XAML-implementing frameworks.</span></span>  

<span data-ttu-id="302d2-127">当你 `x:Static` 不直接是属性值的类型的引用时，请小心。</span><span class="sxs-lookup"><span data-stu-id="302d2-127">Use caution when you make `x:Static` references that are not directly the type of a property's value.</span></span> <span data-ttu-id="302d2-128">在 XAML 处理序列中，从标记扩展提供的值不会调用其他值转换。</span><span class="sxs-lookup"><span data-stu-id="302d2-128">In the XAML processing sequence, provided values from a markup extension do not invoke additional value conversion.</span></span> <span data-ttu-id="302d2-129">即使 `x:Static` 引用创建了文本字符串，并且基于文本字符串的属性值的值转换通常出现在该特定成员或返回类型的任何成员值中时，也是如此。</span><span class="sxs-lookup"><span data-stu-id="302d2-129">This is true even if your `x:Static` reference creates a text string, and a value conversion for attribute values based on text string typically occurs either for that specific member or for any member values of the return type.</span></span>  

<span data-ttu-id="302d2-130">特性语法是最常用于该标记扩展的语法。</span><span class="sxs-lookup"><span data-stu-id="302d2-130">Attribute syntax is the most common syntax used with this markup extension.</span></span> <span data-ttu-id="302d2-131">在 `x:Static` 标识符字符串之后提供的字符串标记被指定为基础 <xref:System.Windows.Markup.StaticExtension.Member%2A> 扩展类的 <xref:System.Windows.Markup.StaticExtension> 值。</span><span class="sxs-lookup"><span data-stu-id="302d2-131">The string token provided after the `x:Static` identifier string is assigned as the <xref:System.Windows.Markup.StaticExtension.Member%2A> value of the underlying <xref:System.Windows.Markup.StaticExtension> extension class.</span></span>  

<span data-ttu-id="302d2-132">还有其他两个在技术上可能的 XAML 用法。</span><span class="sxs-lookup"><span data-stu-id="302d2-132">There are two other XAML usages that are technically possible.</span></span> <span data-ttu-id="302d2-133">不过，这些用法不太常见，因为它们不太必要：</span><span class="sxs-lookup"><span data-stu-id="302d2-133">However, these usages are less common because they are unnecessarily verbose:</span></span>  

1. <span data-ttu-id="302d2-134">对象元素语法。</span><span class="sxs-lookup"><span data-stu-id="302d2-134">Object element syntax.</span></span>

    ```xaml
    <x:Static Member="prefix:typeName.staticMemberName" ... />
    ```

2. <span data-ttu-id="302d2-135">带有用于初始化字符串的显式成员属性的特性语法。</span><span class="sxs-lookup"><span data-stu-id="302d2-135">Attribute syntax with explicit Member property for initialization string.</span></span>

    ```xaml
    <object property="{x:Static Member=prefix:typeName.staticMemberName}" ... />
    ```

<span data-ttu-id="302d2-136">在 .NET Framework XAML 服务实现中，对此标记扩展的处理由 <xref:System.Windows.Markup.StaticExtension> 类定义。</span><span class="sxs-lookup"><span data-stu-id="302d2-136">In the .NET Framework XAML Services implementation, the handling for this markup extension is defined by the <xref:System.Windows.Markup.StaticExtension> class.</span></span>  

<span data-ttu-id="302d2-137">`x:Static` 是标记扩展。</span><span class="sxs-lookup"><span data-stu-id="302d2-137">`x:Static` is a markup extension.</span></span> <span data-ttu-id="302d2-138">XAML 中的所有标记扩展在其特性语法中使用 `{` 和 `}` 字符，这是 XAML 处理器识别标记扩展必须提供值的约定。</span><span class="sxs-lookup"><span data-stu-id="302d2-138">All markup extensions in XAML use the `{` and `}` characters in their attribute syntax, which is the convention by which a XAML processor recognizes that a markup extension must provide a value.</span></span> <span data-ttu-id="302d2-139">有关标记扩展的详细信息，请参阅 [Markup Extensions for XAML Overview](markup-extensions-for-xaml-overview.md)。</span><span class="sxs-lookup"><span data-stu-id="302d2-139">For more information about markup extensions, see [Markup Extensions for XAML Overview](markup-extensions-for-xaml-overview.md).</span></span>  
  
## <a name="wpf-usage-notes"></a><span data-ttu-id="302d2-140">WPF 使用说明</span><span class="sxs-lookup"><span data-stu-id="302d2-140">WPF Usage Notes</span></span>  
 <span data-ttu-id="302d2-141">用于 WPF 编程的默认 XAML 命名空间不包含很多有用的静态属性，并且大多数有用的静态属性都具有支持，如可在不需要 `{x:Static}` 的情况下使用的类型转换器。</span><span class="sxs-lookup"><span data-stu-id="302d2-141">The default XAML namespace you use for WPF programming does not contain many useful static properties, and most of the useful static properties have support such as type converters that facilitate the usage without requiring `{x:Static}` .</span></span> <span data-ttu-id="302d2-142">对于静态属性，如果满足以下条件之一，则必须映射 XAML 命名空间的前缀：</span><span class="sxs-lookup"><span data-stu-id="302d2-142">For static properties, you must map a prefix for a XAML namespace if one of the following is true:</span></span>  
  
- <span data-ttu-id="302d2-143">引用的类型存在于 WPF 中，但它不是 WPF 的默认 XAML 命名空间的一部分（`http://schemas.microsoft.com/winfx/2006/xaml/presentation`）。</span><span class="sxs-lookup"><span data-stu-id="302d2-143">You are referencing a type that exists in WPF but is not part of the default XAML namespace for WPF (`http://schemas.microsoft.com/winfx/2006/xaml/presentation`).</span></span> <span data-ttu-id="302d2-144">这是使用 `x:Static`的一种非常常见的方案。</span><span class="sxs-lookup"><span data-stu-id="302d2-144">This is a fairly common scenario for using `x:Static`.</span></span> <span data-ttu-id="302d2-145">例如，你可以使用 `x:Static` 引用，其中包含到 <xref:System> CLR 命名空间和 mscorlib 程序集的 XAML 命名空间映射，以便引用 <xref:System.Environment> 类的静态属性。</span><span class="sxs-lookup"><span data-stu-id="302d2-145">For example, you might use an `x:Static` reference with a XAML namespace mapping to the <xref:System> CLR namespace and mscorlib assembly in order to reference the static properties of the <xref:System.Environment> class.</span></span>  
  
- <span data-ttu-id="302d2-146">正在从自定义程序集引用类型。</span><span class="sxs-lookup"><span data-stu-id="302d2-146">You are referencing a type from a custom assembly.</span></span>  
  
- <span data-ttu-id="302d2-147">正在引用 WPF 程序集中存在的类型，但该类型位于未映射到 WPF 默认 XAML 命名空间的一部分的 CLR 命名空间中。</span><span class="sxs-lookup"><span data-stu-id="302d2-147">You are referencing a type that exists in a WPF assembly, but that type is within a CLR namespace that was not mapped to be part of the WPF default XAML namespace.</span></span> <span data-ttu-id="302d2-148">CLR 命名空间到 WPF 的默认 XAML 命名空间的映射由各种 WPF 程序集中的定义执行（有关此概念的详细信息，请参阅[WPF xaml 的 Xaml 命名空间和命名空间映射](../wpf/advanced/xaml-namespaces-and-namespace-mapping-for-wpf-xaml.md)）。</span><span class="sxs-lookup"><span data-stu-id="302d2-148">The mapping of CLR namespaces into the default XAML namespace for WPF is performed by definitions in the various WPF assemblies (for more information about this concept, see [XAML Namespaces and Namespace Mapping for WPF XAML](../wpf/advanced/xaml-namespaces-and-namespace-mapping-for-wpf-xaml.md)).</span></span> <span data-ttu-id="302d2-149">如果 CLR 命名空间主要由通常不适用于 XAML 的类定义组成，如 <xref:System.Windows.Threading>，则可能存在非映射 CLR 命名空间。</span><span class="sxs-lookup"><span data-stu-id="302d2-149">Non-mapped CLR namespaces can exist if that CLR namespace is composed mostly of class definitions that are not typically intended for XAML, such as <xref:System.Windows.Threading>.</span></span>  
  
 <span data-ttu-id="302d2-150">有关如何对 WPF 使用前缀和 XAML 命名空间的详细信息，请参阅[WPF xaml 的 XAML 命名空间和命名空间映射](../wpf/advanced/xaml-namespaces-and-namespace-mapping-for-wpf-xaml.md)。</span><span class="sxs-lookup"><span data-stu-id="302d2-150">For more information on how to use prefixes and XAML namespaces for WPF, see [XAML Namespaces and Namespace Mapping for WPF XAML](../wpf/advanced/xaml-namespaces-and-namespace-mapping-for-wpf-xaml.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="302d2-151">请参阅</span><span class="sxs-lookup"><span data-stu-id="302d2-151">See also</span></span>

- [<span data-ttu-id="302d2-152">x:Type 标记扩展</span><span class="sxs-lookup"><span data-stu-id="302d2-152">x:Type Markup Extension</span></span>](x-type-markup-extension.md)
- [<span data-ttu-id="302d2-153">从 WPF 迁移到 System.Xaml 的类型</span><span class="sxs-lookup"><span data-stu-id="302d2-153">Types Migrated from WPF to System.Xaml</span></span>](types-migrated-from-wpf-to-system-xaml.md)
