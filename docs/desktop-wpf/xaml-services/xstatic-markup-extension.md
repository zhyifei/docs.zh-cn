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
ms.openlocfilehash: fb9ee6807135f17fd9e0c799533bba28b369ebe2
ms.sourcegitcommit: 99b153b93bf94d0fecf7c7bcecb58ac424dfa47c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/25/2020
ms.locfileid: "81433264"
---
# <a name="xstatic-markup-extension"></a><span data-ttu-id="aaf9a-102">x:Static 标记扩展</span><span class="sxs-lookup"><span data-stu-id="aaf9a-102">x:Static Markup Extension</span></span>

<span data-ttu-id="aaf9a-103">引用以通用语言规范 （CLS） 兼容方式定义的任何静态按值代码实体。</span><span class="sxs-lookup"><span data-stu-id="aaf9a-103">References any static by-value code entity that is defined in a Common Language Specification (CLS)–compliant way.</span></span> <span data-ttu-id="aaf9a-104">引用的静态属性可用于在 XAML 中提供属性的值。</span><span class="sxs-lookup"><span data-stu-id="aaf9a-104">The static property that is referenced can be used to provide the value of a property in XAML.</span></span>

## <a name="xaml-attribute-usage"></a><span data-ttu-id="aaf9a-105">XAML 属性用法</span><span class="sxs-lookup"><span data-stu-id="aaf9a-105">XAML Attribute Usage</span></span>

```xaml
<object property="{x:Static prefix:typeName.staticMemberName}" .../>
```

## <a name="xaml-values"></a><span data-ttu-id="aaf9a-106">XAML 值</span><span class="sxs-lookup"><span data-stu-id="aaf9a-106">XAML Values</span></span>

| | |
|-|-|
|`prefix`|<span data-ttu-id="aaf9a-107">可选。</span><span class="sxs-lookup"><span data-stu-id="aaf9a-107">Optional.</span></span> <span data-ttu-id="aaf9a-108">指映射的非默认 XAML 命名空间的前缀。</span><span class="sxs-lookup"><span data-stu-id="aaf9a-108">A prefix that refers to a mapped, non-default XAML namespace.</span></span> <span data-ttu-id="aaf9a-109">`prefix`在用法中显式显示，因为很少引用来自默认 XAML 命名空间的静态属性。</span><span class="sxs-lookup"><span data-stu-id="aaf9a-109">`prefix` is shown explicitly in the usage because you rarely reference static properties that come from a default XAML namespace.</span></span> <span data-ttu-id="aaf9a-110">请参阅“备注”。</span><span class="sxs-lookup"><span data-stu-id="aaf9a-110">See Remarks.</span></span>|
|`typeName`|<span data-ttu-id="aaf9a-111">必需。</span><span class="sxs-lookup"><span data-stu-id="aaf9a-111">Required.</span></span> <span data-ttu-id="aaf9a-112">定义所需静态成员的类型的名称。</span><span class="sxs-lookup"><span data-stu-id="aaf9a-112">The name of the type that defines the desired static member.</span></span>|
|`staticMemberName`|<span data-ttu-id="aaf9a-113">必需。</span><span class="sxs-lookup"><span data-stu-id="aaf9a-113">Required.</span></span> <span data-ttu-id="aaf9a-114">所需静态值成员（常量、静态属性、字段或枚举值）的名称。</span><span class="sxs-lookup"><span data-stu-id="aaf9a-114">The name of the desired static value member (a constant, a static property, a field, or an enumeration value).</span></span>|

## <a name="remarks"></a><span data-ttu-id="aaf9a-115">备注</span><span class="sxs-lookup"><span data-stu-id="aaf9a-115">Remarks</span></span>

<span data-ttu-id="aaf9a-116">引用的代码实体必须是以下类型之一：</span><span class="sxs-lookup"><span data-stu-id="aaf9a-116">The code entity that is referenced must be one of the following:</span></span>

- <span data-ttu-id="aaf9a-117">常量</span><span class="sxs-lookup"><span data-stu-id="aaf9a-117">A constant</span></span>
- <span data-ttu-id="aaf9a-118">静态属性</span><span class="sxs-lookup"><span data-stu-id="aaf9a-118">A static property</span></span>
- <span data-ttu-id="aaf9a-119">字段</span><span class="sxs-lookup"><span data-stu-id="aaf9a-119">A field</span></span>
- <span data-ttu-id="aaf9a-120">枚举值</span><span class="sxs-lookup"><span data-stu-id="aaf9a-120">An enumeration value</span></span>

<span data-ttu-id="aaf9a-121">如果编译了 XAML，或者 XAML 加载时间分析异常，则指定任何其他代码实体（如非静态属性）会导致编译时错误。</span><span class="sxs-lookup"><span data-stu-id="aaf9a-121">Specifying any other code entity, such as a nonstatic property, causes a compile-time error if the XAML is markup compiled, or a XAML load-time parse exception.</span></span>

<span data-ttu-id="aaf9a-122">您可以`x:Static`引用当前 XAML 文档的默认 XAML 命名空间中未包含的静态字段或属性;但是，这需要前缀映射。</span><span class="sxs-lookup"><span data-stu-id="aaf9a-122">You can make `x:Static` references to static fields or properties that are not in the default XAML namespace for the current XAML document; however, this requires a prefix mapping.</span></span> <span data-ttu-id="aaf9a-123">XAML 命名空间几乎总是在 XAML 文档的根元素上定义。</span><span class="sxs-lookup"><span data-stu-id="aaf9a-123">XAML namespaces are almost always defined on the root element of the XAML document.</span></span>

<span data-ttu-id="aaf9a-124">静态属性的查找操作可以由 .NET XAML 服务及其 XAML 读取器和 XAML 编写器执行，当它们使用默认的 XAML 架构上下文运行时。</span><span class="sxs-lookup"><span data-stu-id="aaf9a-124">The lookup operations for static properties can be performed by .NET XAML Services and its XAML readers and XAML writers, when they are running with the default XAML schema context.</span></span> <span data-ttu-id="aaf9a-125">此 XAML 架构上下文可以使用 CLR 反射为对象图形构造提供必要的静态值。</span><span class="sxs-lookup"><span data-stu-id="aaf9a-125">This XAML schema context can use CLR reflection to provide the necessary static values for object graph construction.</span></span> <span data-ttu-id="aaf9a-126">`typeName`您指定的实际上是一个 XAML 类型名称，而不是 CLR 类型名称，尽管在使用默认 XAML 架构上下文或使用所有基于 CLR 的 XAML 实现框架时，这些名称本质上是相同的名称。</span><span class="sxs-lookup"><span data-stu-id="aaf9a-126">The `typeName` you specify is actually a XAML type name, not a CLR type name, although these are essentially the same name when using the default XAML schema context or when using all existing CLR-based XAML-implementing frameworks.</span></span>

<span data-ttu-id="aaf9a-127">当您进行`x:Static`不是属性值类型的引用时，应小心谨慎。</span><span class="sxs-lookup"><span data-stu-id="aaf9a-127">Use caution when you make `x:Static` references that are not directly the type of a property's value.</span></span> <span data-ttu-id="aaf9a-128">在 XAML 处理序列中，从标记扩展提供的值不会调用附加值转换。</span><span class="sxs-lookup"><span data-stu-id="aaf9a-128">In the XAML processing sequence, provided values from a markup extension do not invoke additional value conversion.</span></span> <span data-ttu-id="aaf9a-129">即使引用`x:Static`创建了文本字符串，也是如此，并且通常针对该特定成员或返回类型的任何成员值对基于文本字符串的属性值进行值转换。</span><span class="sxs-lookup"><span data-stu-id="aaf9a-129">This is true even if your `x:Static` reference creates a text string, and a value conversion for attribute values based on text string typically occurs either for that specific member or for any member values of the return type.</span></span>

<span data-ttu-id="aaf9a-130">特性语法是最常用于该标记扩展的语法。</span><span class="sxs-lookup"><span data-stu-id="aaf9a-130">Attribute syntax is the most common syntax used with this markup extension.</span></span> <span data-ttu-id="aaf9a-131">在 `x:Static` 标识符字符串之后提供的字符串标记被指定为基础 <xref:System.Windows.Markup.StaticExtension.Member%2A> 扩展类的 <xref:System.Windows.Markup.StaticExtension> 值。</span><span class="sxs-lookup"><span data-stu-id="aaf9a-131">The string token provided after the `x:Static` identifier string is assigned as the <xref:System.Windows.Markup.StaticExtension.Member%2A> value of the underlying <xref:System.Windows.Markup.StaticExtension> extension class.</span></span>

<span data-ttu-id="aaf9a-132">技术上可能还有其他两个 XAML 用法。</span><span class="sxs-lookup"><span data-stu-id="aaf9a-132">There are two other XAML usages that are technically possible.</span></span> <span data-ttu-id="aaf9a-133">但是，这些用法不太常见，因为它们是不必要的冗长：</span><span class="sxs-lookup"><span data-stu-id="aaf9a-133">However, these usages are less common because they are unnecessarily verbose:</span></span>

01. <span data-ttu-id="aaf9a-134">对象元素语法。</span><span class="sxs-lookup"><span data-stu-id="aaf9a-134">Object element syntax.</span></span>

    ```xaml
    <x:Static Member="prefix:typeName.staticMemberName" ... />
    ```

02. <span data-ttu-id="aaf9a-135">具有显式成员属性的属性语法，用于初始化字符串。</span><span class="sxs-lookup"><span data-stu-id="aaf9a-135">Attribute syntax with explicit Member property for initialization string.</span></span>

    ```xaml
    <object property="{x:Static Member=prefix:typeName.staticMemberName}" ... />
    ```

<span data-ttu-id="aaf9a-136">在 .NET XAML 服务实现中，此标记扩展的处理由<xref:System.Windows.Markup.StaticExtension>类定义。</span><span class="sxs-lookup"><span data-stu-id="aaf9a-136">In .NET XAML Services implementation, the handling for this markup extension is defined by the <xref:System.Windows.Markup.StaticExtension> class.</span></span>

<span data-ttu-id="aaf9a-137">`x:Static` 是标记扩展。</span><span class="sxs-lookup"><span data-stu-id="aaf9a-137">`x:Static` is a markup extension.</span></span> <span data-ttu-id="aaf9a-138">XAML 中的所有标记扩展在其属性语法中使用`{``}`和 字符，这是 XAML 处理器识别标记扩展必须提供值的约定。</span><span class="sxs-lookup"><span data-stu-id="aaf9a-138">All markup extensions in XAML use the `{` and `}` characters in their attribute syntax, which is the convention by which a XAML processor recognizes that a markup extension must provide a value.</span></span> <span data-ttu-id="aaf9a-139">有关标记扩展的详细信息，请参阅 [Markup Extensions for XAML Overview](markup-extensions-overview.md)。</span><span class="sxs-lookup"><span data-stu-id="aaf9a-139">For more information about markup extensions, see [Markup Extensions for XAML Overview](markup-extensions-overview.md).</span></span>

## <a name="wpf-usage-notes"></a><span data-ttu-id="aaf9a-140">WPF 用法说明</span><span class="sxs-lookup"><span data-stu-id="aaf9a-140">WPF Usage Notes</span></span>

<span data-ttu-id="aaf9a-141">用于 WPF 编程的默认 XAML 命名空间不包含许多有用的静态属性，并且大多数有用的静态属性都支持，例如类型转换器，无需即可`{x:Static}`方便使用。</span><span class="sxs-lookup"><span data-stu-id="aaf9a-141">The default XAML namespace you use for WPF programming does not contain many useful static properties, and most of the useful static properties have support such as type converters that facilitate the usage without requiring `{x:Static}` .</span></span> <span data-ttu-id="aaf9a-142">对于静态属性，如果以下原因之一为 true，则必须映射 XAML 命名空间的前缀：</span><span class="sxs-lookup"><span data-stu-id="aaf9a-142">For static properties, you must map a prefix for a XAML namespace if one of the following is true:</span></span>

- <span data-ttu-id="aaf9a-143">您引用的类型存在于 WPF 中，但不是 WPF （ 的`http://schemas.microsoft.com/winfx/2006/xaml/presentation`默认 XAML 命名空间的一部分）。</span><span class="sxs-lookup"><span data-stu-id="aaf9a-143">You are referencing a type that exists in WPF but is not part of the default XAML namespace for WPF (`http://schemas.microsoft.com/winfx/2006/xaml/presentation`).</span></span> <span data-ttu-id="aaf9a-144">这是使用`x:Static`的相当常见的方案。</span><span class="sxs-lookup"><span data-stu-id="aaf9a-144">This is a fairly common scenario for using `x:Static`.</span></span> <span data-ttu-id="aaf9a-145">例如，可以使用具有`x:Static`XAML 命名空间映射到<xref:System>CLR 命名空间和 mscorlib 程序集的引用，以便引用类的<xref:System.Environment>静态属性。</span><span class="sxs-lookup"><span data-stu-id="aaf9a-145">For example, you might use an `x:Static` reference with a XAML namespace mapping to the <xref:System> CLR namespace and mscorlib assembly in order to reference the static properties of the <xref:System.Environment> class.</span></span>

- <span data-ttu-id="aaf9a-146">您正在引用自定义程序集中的类型。</span><span class="sxs-lookup"><span data-stu-id="aaf9a-146">You are referencing a type from a custom assembly.</span></span>

- <span data-ttu-id="aaf9a-147">您引用的类型存在于 WPF 程序集中，但该类型位于未映射到 WPF 默认 XAML 命名空间的 CLR 命名空间中。</span><span class="sxs-lookup"><span data-stu-id="aaf9a-147">You are referencing a type that exists in a WPF assembly, but that type is within a CLR namespace that was not mapped to be part of the WPF default XAML namespace.</span></span> <span data-ttu-id="aaf9a-148">CLR 命名空间映射到 WPF 的默认 XAML 命名空间由各种 WPF 程序集中的定义执行（有关此概念的详细信息，请参阅[WPF XAML 的 XAML 命名空间和命名空间映射](../../framework/wpf/advanced/xaml-namespaces-and-namespace-mapping-for-wpf-xaml.md)）。</span><span class="sxs-lookup"><span data-stu-id="aaf9a-148">The mapping of CLR namespaces into the default XAML namespace for WPF is performed by definitions in the various WPF assemblies (for more information about this concept, see [XAML Namespaces and Namespace Mapping for WPF XAML](../../framework/wpf/advanced/xaml-namespaces-and-namespace-mapping-for-wpf-xaml.md)).</span></span> <span data-ttu-id="aaf9a-149">如果 CLR 命名空间主要由通常不用于 XAML 的类定义组成，则存在非映射 CLR 命名空间，例如<xref:System.Windows.Threading>。</span><span class="sxs-lookup"><span data-stu-id="aaf9a-149">Non-mapped CLR namespaces can exist if that CLR namespace is composed mostly of class definitions that are not typically intended for XAML, such as <xref:System.Windows.Threading>.</span></span>

<span data-ttu-id="aaf9a-150">有关如何为 WPF 使用前缀和 XAML 命名空间的详细信息，请参阅[WPF XAML 的 XAML 命名空间和命名空间映射](../../framework/wpf/advanced/xaml-namespaces-and-namespace-mapping-for-wpf-xaml.md)。</span><span class="sxs-lookup"><span data-stu-id="aaf9a-150">For more information on how to use prefixes and XAML namespaces for WPF, see [XAML Namespaces and Namespace Mapping for WPF XAML](../../framework/wpf/advanced/xaml-namespaces-and-namespace-mapping-for-wpf-xaml.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="aaf9a-151">请参阅</span><span class="sxs-lookup"><span data-stu-id="aaf9a-151">See also</span></span>

- [<span data-ttu-id="aaf9a-152">x:Type 标记扩展</span><span class="sxs-lookup"><span data-stu-id="aaf9a-152">x:Type Markup Extension</span></span>](xtype-markup-extension.md)
- [<span data-ttu-id="aaf9a-153">从 WPF 迁移到 System.Xaml 的类型</span><span class="sxs-lookup"><span data-stu-id="aaf9a-153">Types Migrated from WPF to System.Xaml</span></span>](../../framework/wpf/advanced/types-migrated-from-wpf-to-system.md)
