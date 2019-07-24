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
ms.openlocfilehash: 9fa9e51e66af6df4d1a6b1ec94c5010651bbb21d
ms.sourcegitcommit: 24a4a8eb6d8cfe7b8549fb6d823076d7c697e0c6
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/23/2019
ms.locfileid: "68401511"
---
# <a name="xstatic-markup-extension"></a><span data-ttu-id="0d8da-102">x:Static 标记扩展</span><span class="sxs-lookup"><span data-stu-id="0d8da-102">x:Static Markup Extension</span></span>
<span data-ttu-id="0d8da-103">引用以符合公共语言规范 (CLS) 的方式定义的任何静态按值的代码实体。</span><span class="sxs-lookup"><span data-stu-id="0d8da-103">References any static by-value code entity that is defined in a Common Language Specification (CLS)–compliant way.</span></span> <span data-ttu-id="0d8da-104">引用的静态属性可用于在 XAML 中提供属性的值。</span><span class="sxs-lookup"><span data-stu-id="0d8da-104">The static property that is referenced can be used to provide the value of a property in XAML.</span></span>  
  
## <a name="xaml-attribute-usage"></a><span data-ttu-id="0d8da-105">XAML 属性用法</span><span class="sxs-lookup"><span data-stu-id="0d8da-105">XAML Attribute Usage</span></span>  
  
```xaml  
<object property="{x:Static prefix:typeName.staticMemberName}" .../>  
```  
  
## <a name="xaml-values"></a><span data-ttu-id="0d8da-106">XAML 值</span><span class="sxs-lookup"><span data-stu-id="0d8da-106">XAML Values</span></span>  
  
| | |  
|-|-|  
|`prefix`|<span data-ttu-id="0d8da-107">可选。</span><span class="sxs-lookup"><span data-stu-id="0d8da-107">Optional.</span></span> <span data-ttu-id="0d8da-108">引用映射的非默认 XAML 命名空间的前缀。</span><span class="sxs-lookup"><span data-stu-id="0d8da-108">A prefix that refers to a mapped, non-default XAML namespace.</span></span> <span data-ttu-id="0d8da-109">`prefix`用法中显式显示, 因为很少引用默认 XAML 命名空间中的静态属性。</span><span class="sxs-lookup"><span data-stu-id="0d8da-109">`prefix` is shown explicitly in the usage because you rarely reference static properties that come from a default XAML namespace.</span></span> <span data-ttu-id="0d8da-110">请参阅“备注”。</span><span class="sxs-lookup"><span data-stu-id="0d8da-110">See Remarks.</span></span>|  
|`typeName`|<span data-ttu-id="0d8da-111">必需。</span><span class="sxs-lookup"><span data-stu-id="0d8da-111">Required.</span></span> <span data-ttu-id="0d8da-112">定义所需静态成员的类型的名称。</span><span class="sxs-lookup"><span data-stu-id="0d8da-112">The name of the type that defines the desired static member.</span></span>|  
|`staticMemberName`|<span data-ttu-id="0d8da-113">必需。</span><span class="sxs-lookup"><span data-stu-id="0d8da-113">Required.</span></span> <span data-ttu-id="0d8da-114">所需的静态值成员的名称 (常量、静态属性、字段或枚举值)。</span><span class="sxs-lookup"><span data-stu-id="0d8da-114">The name of the desired static value member (a constant, a static property, a field, or an enumeration value).</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="0d8da-115">备注</span><span class="sxs-lookup"><span data-stu-id="0d8da-115">Remarks</span></span>  

<span data-ttu-id="0d8da-116">引用的代码实体必须是以下项之一:</span><span class="sxs-lookup"><span data-stu-id="0d8da-116">The code entity that is referenced must be one of the following:</span></span>  
  
- <span data-ttu-id="0d8da-117">常量</span><span class="sxs-lookup"><span data-stu-id="0d8da-117">A constant</span></span>  
- <span data-ttu-id="0d8da-118">静态属性</span><span class="sxs-lookup"><span data-stu-id="0d8da-118">A static property</span></span>  
- <span data-ttu-id="0d8da-119">一个字段</span><span class="sxs-lookup"><span data-stu-id="0d8da-119">A field</span></span>  
- <span data-ttu-id="0d8da-120">枚举值</span><span class="sxs-lookup"><span data-stu-id="0d8da-120">An enumeration value</span></span>

<span data-ttu-id="0d8da-121">如果指定任何其他代码实体 (如非静态属性), 则会导致编译时错误, 如果已编译了 XAML 或 XAML 加载时分析异常, 则会引发编译时错误。</span><span class="sxs-lookup"><span data-stu-id="0d8da-121">Specifying any other code entity, such as a nonstatic property, causes a compile-time error if the XAML is markup compiled, or a XAML load-time parse exception.</span></span>  

<span data-ttu-id="0d8da-122">可以`x:Static`引用当前 xaml 文档的默认 xaml 命名空间中不是的静态字段或属性; 但是, 这需要前缀映射。</span><span class="sxs-lookup"><span data-stu-id="0d8da-122">You can make `x:Static` references to static fields or properties that are not in the default XAML namespace for the current XAML document; however, this requires a prefix mapping.</span></span> <span data-ttu-id="0d8da-123">XAML 命名空间几乎始终在 XAML 文档的根元素上定义。</span><span class="sxs-lookup"><span data-stu-id="0d8da-123">XAML namespaces are almost always defined on the root element of the XAML document.</span></span>  

<span data-ttu-id="0d8da-124">当 XAML 服务及其 XAML 读取器和 XAML 编写器运行时, 可 .NET Framework 通过默认的 XAML 架构上下文来执行静态属性的查找操作。</span><span class="sxs-lookup"><span data-stu-id="0d8da-124">The lookup operations for static properties can be performed by .NET Framework XAML Services and its XAML readers and XAML writers, when they are running with the default XAML schema context.</span></span> <span data-ttu-id="0d8da-125">此 XAML 架构上下文可以使用 CLR 反射为对象图构造提供必要的静态值。</span><span class="sxs-lookup"><span data-stu-id="0d8da-125">This XAML schema context can use CLR reflection to provide the necessary static values for object graph construction.</span></span> <span data-ttu-id="0d8da-126">指定`typeName`的实际上是 XAML 类型名称, 而不是 CLR 类型名称, 不过, 在使用默认 XAML 架构上下文或使用所有基于 CLR 的现有 XAML 实现框架时, 这些名称本质上是相同的名称。</span><span class="sxs-lookup"><span data-stu-id="0d8da-126">The `typeName` you specify is actually a XAML type name, not a CLR type name, although these are essentially the same name when using the default XAML schema context or when using all existing CLR-based XAML-implementing frameworks.</span></span>  

<span data-ttu-id="0d8da-127">当你进行`x:Static`不直接是属性值的类型的引用时, 请小心。</span><span class="sxs-lookup"><span data-stu-id="0d8da-127">Use caution when you make `x:Static` references that are not directly the type of a property's value.</span></span> <span data-ttu-id="0d8da-128">在 XAML 处理序列中, 从标记扩展提供的值不会调用其他值转换。</span><span class="sxs-lookup"><span data-stu-id="0d8da-128">In the XAML processing sequence, provided values from a markup extension do not invoke additional value conversion.</span></span> <span data-ttu-id="0d8da-129">即使您`x:Static`的引用创建一个文本字符串, 并且基于文本字符串的属性值的值转换通常出现在该特定成员或返回类型的任何成员值中, 也是如此。</span><span class="sxs-lookup"><span data-stu-id="0d8da-129">This is true even if your `x:Static` reference creates a text string, and a value conversion for attribute values based on text string typically occurs either for that specific member or for any member values of the return type.</span></span>  

<span data-ttu-id="0d8da-130">特性语法是最常用于该标记扩展的语法。</span><span class="sxs-lookup"><span data-stu-id="0d8da-130">Attribute syntax is the most common syntax used with this markup extension.</span></span> <span data-ttu-id="0d8da-131">在 `x:Static` 标识符字符串之后提供的字符串标记被指定为基础 <xref:System.Windows.Markup.StaticExtension.Member%2A> 扩展类的 <xref:System.Windows.Markup.StaticExtension> 值。</span><span class="sxs-lookup"><span data-stu-id="0d8da-131">The string token provided after the `x:Static` identifier string is assigned as the <xref:System.Windows.Markup.StaticExtension.Member%2A> value of the underlying <xref:System.Windows.Markup.StaticExtension> extension class.</span></span>  

<span data-ttu-id="0d8da-132">还有其他两个在技术上可能的 XAML 用法。</span><span class="sxs-lookup"><span data-stu-id="0d8da-132">There are two other XAML usages that are technically possible.</span></span> <span data-ttu-id="0d8da-133">不过, 这些用法不太常见, 因为它们不太必要:</span><span class="sxs-lookup"><span data-stu-id="0d8da-133">However, these usages are less common because they are unnecessarily verbose:</span></span>  

1. <span data-ttu-id="0d8da-134">对象元素语法。</span><span class="sxs-lookup"><span data-stu-id="0d8da-134">Object element syntax.</span></span>

    ```xaml
    <x:Static Member="prefix:typeName.staticMemberName" ... />
    ```

2. <span data-ttu-id="0d8da-135">带有用于初始化字符串的显式成员属性的特性语法。</span><span class="sxs-lookup"><span data-stu-id="0d8da-135">Attribute syntax with explicit Member property for initialization string.</span></span>

    ```xaml
    <object property="{x:Static Member=prefix:typeName.staticMemberName}" ... />
    ```

<span data-ttu-id="0d8da-136">在 .NET Framework XAML 服务实现中, 对此标记扩展的处理由<xref:System.Windows.Markup.StaticExtension>类定义。</span><span class="sxs-lookup"><span data-stu-id="0d8da-136">In the .NET Framework XAML Services implementation, the handling for this markup extension is defined by the <xref:System.Windows.Markup.StaticExtension> class.</span></span>  

<span data-ttu-id="0d8da-137">`x:Static` 是标记扩展。</span><span class="sxs-lookup"><span data-stu-id="0d8da-137">`x:Static` is a markup extension.</span></span> <span data-ttu-id="0d8da-138">Xaml 中的`{`所有标记扩展在其`}`特性语法中使用和字符, 这是 xaml 处理器识别标记扩展必须提供值的约定。</span><span class="sxs-lookup"><span data-stu-id="0d8da-138">All markup extensions in XAML use the `{` and `}` characters in their attribute syntax, which is the convention by which a XAML processor recognizes that a markup extension must provide a value.</span></span> <span data-ttu-id="0d8da-139">有关标记扩展的详细信息，请参阅 [Markup Extensions for XAML Overview](markup-extensions-for-xaml-overview.md)。</span><span class="sxs-lookup"><span data-stu-id="0d8da-139">For more information about markup extensions, see [Markup Extensions for XAML Overview](markup-extensions-for-xaml-overview.md).</span></span>  
  
## <a name="wpf-usage-notes"></a><span data-ttu-id="0d8da-140">WPF 使用说明</span><span class="sxs-lookup"><span data-stu-id="0d8da-140">WPF Usage Notes</span></span>  
 <span data-ttu-id="0d8da-141">用于 WPF 编程的默认 XAML 命名空间不包含很多有用的静态属性, 并且大多数有用的静态属性都具有支持, 如可以方便使用`{x:Static}`的类型转换器。</span><span class="sxs-lookup"><span data-stu-id="0d8da-141">The default XAML namespace you use for WPF programming does not contain many useful static properties, and most of the useful static properties have support such as type converters that facilitate the usage without requiring `{x:Static}` .</span></span> <span data-ttu-id="0d8da-142">对于静态属性, 如果满足以下条件之一, 则必须映射 XAML 命名空间的前缀:</span><span class="sxs-lookup"><span data-stu-id="0d8da-142">For static properties, you must map a prefix for a XAML namespace if one of the following is true:</span></span>  
  
- <span data-ttu-id="0d8da-143">引用的类型存在于 WPF 中, 但不是 WPF 的默认 XAML 命名空间的一部分 ([!INCLUDE[TLA#tla_wpfxmlnsv1](../../../includes/tlasharptla-wpfxmlnsv1-md.md)])。</span><span class="sxs-lookup"><span data-stu-id="0d8da-143">You are referencing a type that exists in WPF but is not part of the default XAML namespace for WPF ([!INCLUDE[TLA#tla_wpfxmlnsv1](../../../includes/tlasharptla-wpfxmlnsv1-md.md)]).</span></span> <span data-ttu-id="0d8da-144">这是使用`x:Static`的一种非常常见的方案。</span><span class="sxs-lookup"><span data-stu-id="0d8da-144">This is a fairly common scenario for using `x:Static`.</span></span> <span data-ttu-id="0d8da-145">例如, 你可以将`x:Static`具有 XAML 命名空间映射<xref:System>的引用用于 CLR 命名空间和 mscorlib 程序集, 以便引用<xref:System.Environment>类的静态属性。</span><span class="sxs-lookup"><span data-stu-id="0d8da-145">For example, you might use an `x:Static` reference with a XAML namespace mapping to the <xref:System> CLR namespace and mscorlib assembly in order to reference the static properties of the <xref:System.Environment> class.</span></span>  
  
- <span data-ttu-id="0d8da-146">正在从自定义程序集引用类型。</span><span class="sxs-lookup"><span data-stu-id="0d8da-146">You are referencing a type from a custom assembly.</span></span>  
  
- <span data-ttu-id="0d8da-147">正在引用 WPF 程序集中存在的类型, 但该类型位于未映射到 WPF 默认 XAML 命名空间的一部分的 CLR 命名空间中。</span><span class="sxs-lookup"><span data-stu-id="0d8da-147">You are referencing a type that exists in a WPF assembly, but that type is within a CLR namespace that was not mapped to be part of the WPF default XAML namespace.</span></span> <span data-ttu-id="0d8da-148">CLR 命名空间到 WPF 的默认 XAML 命名空间的映射由各种 WPF 程序集中的定义执行 (有关此概念的详细信息, 请参阅[WPF xaml 的 Xaml 命名空间和命名空间映射](../wpf/advanced/xaml-namespaces-and-namespace-mapping-for-wpf-xaml.md))。</span><span class="sxs-lookup"><span data-stu-id="0d8da-148">The mapping of CLR namespaces into the default XAML namespace for WPF is performed by definitions in the various WPF assemblies (for more information about this concept, see [XAML Namespaces and Namespace Mapping for WPF XAML](../wpf/advanced/xaml-namespaces-and-namespace-mapping-for-wpf-xaml.md)).</span></span> <span data-ttu-id="0d8da-149">如果 CLR 命名空间主要由通常不适用于 XAML 的类定义组成, 则不映射的 CLR 命名空间可能会存在, <xref:System.Windows.Threading>例如。</span><span class="sxs-lookup"><span data-stu-id="0d8da-149">Non-mapped CLR namespaces can exist if that CLR namespace is composed mostly of class definitions that are not typically intended for XAML, such as <xref:System.Windows.Threading>.</span></span>  
  
 <span data-ttu-id="0d8da-150">有关如何对 WPF 使用前缀和 XAML 命名空间的详细信息, 请参阅[WPF xaml 的 XAML 命名空间和命名空间映射](../wpf/advanced/xaml-namespaces-and-namespace-mapping-for-wpf-xaml.md)。</span><span class="sxs-lookup"><span data-stu-id="0d8da-150">For more information on how to use prefixes and XAML namespaces for WPF, see [XAML Namespaces and Namespace Mapping for WPF XAML](../wpf/advanced/xaml-namespaces-and-namespace-mapping-for-wpf-xaml.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0d8da-151">请参阅</span><span class="sxs-lookup"><span data-stu-id="0d8da-151">See also</span></span>

- [<span data-ttu-id="0d8da-152">x:Type 标记扩展</span><span class="sxs-lookup"><span data-stu-id="0d8da-152">x:Type Markup Extension</span></span>](x-type-markup-extension.md)
- [<span data-ttu-id="0d8da-153">从 WPF 迁移到 System.Xaml 的类型</span><span class="sxs-lookup"><span data-stu-id="0d8da-153">Types Migrated from WPF to System.Xaml</span></span>](types-migrated-from-wpf-to-system-xaml.md)
