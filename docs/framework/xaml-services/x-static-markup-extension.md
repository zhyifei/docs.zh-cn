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
ms.openlocfilehash: 8a14b00fe762d325028072cd0ea3eecf9b9206e3
ms.sourcegitcommit: fb78d8abbdb87144a3872cf154930157090dd933
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/27/2018
ms.locfileid: "47235330"
---
# <a name="xstatic-markup-extension"></a><span data-ttu-id="b6572-102">x:Static 标记扩展</span><span class="sxs-lookup"><span data-stu-id="b6572-102">x:Static Markup Extension</span></span>
<span data-ttu-id="b6572-103">引用中定义的任何静态的值的代码实体[!INCLUDE[TLA#tla_cls](../../../includes/tlasharptla-cls-md.md)]– 合规的方式。</span><span class="sxs-lookup"><span data-stu-id="b6572-103">References any static by-value code entity that is defined in a [!INCLUDE[TLA#tla_cls](../../../includes/tlasharptla-cls-md.md)]–compliant way.</span></span> <span data-ttu-id="b6572-104">引用的静态属性可以用于提供在 XAML 中属性的值。</span><span class="sxs-lookup"><span data-stu-id="b6572-104">The static property that is referenced can be used to provide the value of a property in XAML.</span></span>  
  
## <a name="xaml-attribute-usage"></a><span data-ttu-id="b6572-105">XAML 属性用法</span><span class="sxs-lookup"><span data-stu-id="b6572-105">XAML Attribute Usage</span></span>  
  
```xaml  
<object property="{x:Static prefix:typeName.staticMemberName}" .../>  
```  
  
## <a name="xaml-values"></a><span data-ttu-id="b6572-106">XAML 值</span><span class="sxs-lookup"><span data-stu-id="b6572-106">XAML Values</span></span>  
  
| | |  
|-|-|  
|`prefix`|<span data-ttu-id="b6572-107">可选。</span><span class="sxs-lookup"><span data-stu-id="b6572-107">Optional.</span></span> <span data-ttu-id="b6572-108">指的是一个映射的非默认的 XAML 命名空间前缀。</span><span class="sxs-lookup"><span data-stu-id="b6572-108">A prefix that refers to a mapped, non-default XAML namespace.</span></span> <span data-ttu-id="b6572-109">`prefix` 所示显式使用因为很少引用来自默认 XAML 命名空间的静态属性。</span><span class="sxs-lookup"><span data-stu-id="b6572-109">`prefix` is shown explicitly in the usage because you rarely reference static properties that come from a default XAML namespace.</span></span> <span data-ttu-id="b6572-110">请参阅“备注”。</span><span class="sxs-lookup"><span data-stu-id="b6572-110">See Remarks.</span></span>|  
|`typeName`|<span data-ttu-id="b6572-111">必须的。</span><span class="sxs-lookup"><span data-stu-id="b6572-111">Required.</span></span> <span data-ttu-id="b6572-112">定义的所需的静态成员的类型的名称。</span><span class="sxs-lookup"><span data-stu-id="b6572-112">The name of the type that defines the desired static member.</span></span>|  
|`staticMemberName`|<span data-ttu-id="b6572-113">必须的。</span><span class="sxs-lookup"><span data-stu-id="b6572-113">Required.</span></span> <span data-ttu-id="b6572-114">所需的静态值成员 （一个常量、 静态属性、 字段或枚举值） 的名称。</span><span class="sxs-lookup"><span data-stu-id="b6572-114">The name of the desired static value member (a constant, a static property, a field, or an enumeration value).</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="b6572-115">备注</span><span class="sxs-lookup"><span data-stu-id="b6572-115">Remarks</span></span>  

<span data-ttu-id="b6572-116">引用的代码实体必须是以下值之一：</span><span class="sxs-lookup"><span data-stu-id="b6572-116">The code entity that is referenced must be one of the following:</span></span>  
  
-   <span data-ttu-id="b6572-117">一个常量</span><span class="sxs-lookup"><span data-stu-id="b6572-117">A constant</span></span>  
-   <span data-ttu-id="b6572-118">静态属性</span><span class="sxs-lookup"><span data-stu-id="b6572-118">A static property</span></span>  
-   <span data-ttu-id="b6572-119">一个字段</span><span class="sxs-lookup"><span data-stu-id="b6572-119">A field</span></span>  
-   <span data-ttu-id="b6572-120">一个枚举值</span><span class="sxs-lookup"><span data-stu-id="b6572-120">An enumeration value</span></span>

<span data-ttu-id="b6572-121">指定任何其他代码实体，例如非静态属性，会导致编译时错误，如果 XAML 标记编译或 XAML 加载时间分析异常。</span><span class="sxs-lookup"><span data-stu-id="b6572-121">Specifying any other code entity, such as a nonstatic property, causes a compile-time error if the XAML is markup compiled, or a XAML load-time parse exception.</span></span>  

<span data-ttu-id="b6572-122">可以进行`x:Static`对静态字段或属性不在当前的 XAML 文档; 的默认 XAML 命名空间中的引用但是，这需要的前缀映射。</span><span class="sxs-lookup"><span data-stu-id="b6572-122">You can make `x:Static` references to static fields or properties that are not in the default XAML namespace for the current XAML document; however, this requires a prefix mapping.</span></span> <span data-ttu-id="b6572-123">几乎总是 XAML 文档的根元素上定义的 XAML 命名空间。</span><span class="sxs-lookup"><span data-stu-id="b6572-123">XAML namespaces are almost always defined on the root element of the XAML document.</span></span>  

<span data-ttu-id="b6572-124">与默认 XAML 架构上下文中运行时，可以通过.NET Framework XAML 服务及其 XAML 读取器和 XAML 编写器执行查找操作对于静态属性。</span><span class="sxs-lookup"><span data-stu-id="b6572-124">The lookup operations for static properties can be performed by .NET Framework XAML Services and its XAML readers and XAML writers, when they are running with the default XAML schema context.</span></span> <span data-ttu-id="b6572-125">此 XAML 架构上下文中可以使用 CLR 反射对象关系图构造为提供所需的静态值。</span><span class="sxs-lookup"><span data-stu-id="b6572-125">This XAML schema context can use CLR reflection to provide the necessary static values for object graph construction.</span></span> <span data-ttu-id="b6572-126">`typeName`你指定为实际的 XAML 类型名称，不是 CLR 类型名称，尽管这些是实质上是相同的名称，或使用所有现有的基于 CLR 的 XAML 实现框架时使用的默认 XAML 架构上下文。</span><span class="sxs-lookup"><span data-stu-id="b6572-126">The `typeName` you specify is actually a XAML type name, not a CLR type name, although these are essentially the same name when using the default XAML schema context or when using all existing CLR-based XAML-implementing frameworks.</span></span>  

<span data-ttu-id="b6572-127">进行时要格外小心`x:Static`不直接类型的属性的值的引用。</span><span class="sxs-lookup"><span data-stu-id="b6572-127">Use caution when you make `x:Static` references that are not directly the type of a property's value.</span></span> <span data-ttu-id="b6572-128">在 XAML 处理序列中，从标记扩展提供的值不调用其他值的转换。</span><span class="sxs-lookup"><span data-stu-id="b6572-128">In the XAML processing sequence, provided values from a markup extension do not invoke additional value conversion.</span></span> <span data-ttu-id="b6572-129">这是 true 即使你`x:Static`引用创建文本字符串，并通常基于文本的字符串的属性值的值转换发生的特定成员或返回类型的任何成员值。</span><span class="sxs-lookup"><span data-stu-id="b6572-129">This is true even if your `x:Static` reference creates a text string, and a value conversion for attribute values based on text string typically occurs either for that specific member or for any member values of the return type.</span></span>  

<span data-ttu-id="b6572-130">特性语法是最常用于该标记扩展的语法。</span><span class="sxs-lookup"><span data-stu-id="b6572-130">Attribute syntax is the most common syntax used with this markup extension.</span></span> <span data-ttu-id="b6572-131">在 `x:Static` 标识符字符串之后提供的字符串标记被指定为基础 <xref:System.Windows.Markup.StaticExtension.Member%2A> 扩展类的 <xref:System.Windows.Markup.StaticExtension> 值。</span><span class="sxs-lookup"><span data-stu-id="b6572-131">The string token provided after the `x:Static` identifier string is assigned as the <xref:System.Windows.Markup.StaticExtension.Member%2A> value of the underlying <xref:System.Windows.Markup.StaticExtension> extension class.</span></span>  

<span data-ttu-id="b6572-132">有两个从技术上讲可能其他 XAML 用法。</span><span class="sxs-lookup"><span data-stu-id="b6572-132">There are two other XAML usages that are technically possible.</span></span> <span data-ttu-id="b6572-133">但是，这些用法并不常见，因为它们是不必要地详细：</span><span class="sxs-lookup"><span data-stu-id="b6572-133">However, these usages are less common because they are unnecessarily verbose:</span></span>  

1.  <span data-ttu-id="b6572-134">对象元素语法。</span><span class="sxs-lookup"><span data-stu-id="b6572-134">Object element syntax.</span></span>

    ```xaml
    <x:Static Member="prefix:typeName.staticMemberName" ... />
    ```

2.  <span data-ttu-id="b6572-135">特性具有显式成员属性的初始化字符串的语法。</span><span class="sxs-lookup"><span data-stu-id="b6572-135">Attribute syntax with explicit Member property for initialization string.</span></span>

    ```xaml
    <object property="{x:Static Member=prefix:typeName.staticMemberName}" ... />
    ```

<span data-ttu-id="b6572-136">在.NET Framework XAML 服务实现中，对此标记扩展的处理由定义<xref:System.Windows.Markup.StaticExtension>类。</span><span class="sxs-lookup"><span data-stu-id="b6572-136">In the .NET Framework XAML Services implementation, the handling for this markup extension is defined by the <xref:System.Windows.Markup.StaticExtension> class.</span></span>  

<span data-ttu-id="b6572-137">`x:Static` 是标记扩展。</span><span class="sxs-lookup"><span data-stu-id="b6572-137">`x:Static` is a markup extension.</span></span> <span data-ttu-id="b6572-138">在 XAML 使用的所有标记扩展`{`和`}`约定所依据的 XAML 处理器识别标记扩展，必须提供一个值，其特性语法中的字符。</span><span class="sxs-lookup"><span data-stu-id="b6572-138">All markup extensions in XAML use the `{` and `}` characters in their attribute syntax, which is the convention by which a XAML processor recognizes that a markup extension must provide a value.</span></span> <span data-ttu-id="b6572-139">有关标记扩展的详细信息，请参阅 [Markup Extensions for XAML Overview](../../../docs/framework/xaml-services/markup-extensions-for-xaml-overview.md)。</span><span class="sxs-lookup"><span data-stu-id="b6572-139">For more information about markup extensions, see [Markup Extensions for XAML Overview](../../../docs/framework/xaml-services/markup-extensions-for-xaml-overview.md).</span></span>  
  
## <a name="wpf-usage-notes"></a><span data-ttu-id="b6572-140">WPF 用法说明</span><span class="sxs-lookup"><span data-stu-id="b6572-140">WPF Usage Notes</span></span>  
 <span data-ttu-id="b6572-141">用于 WPF 编程的默认 XAML 命名空间不包含许多有用的静态属性和有用的静态属性大多具有支持类型转换器，可协助而无需使用如`{x:Static}`。</span><span class="sxs-lookup"><span data-stu-id="b6572-141">The default XAML namespace you use for WPF programming does not contain many useful static properties, and most of the useful static properties have support such as type converters that facilitate the usage without requiring `{x:Static}` .</span></span> <span data-ttu-id="b6572-142">对于静态属性，必须映射 XAML 命名空间的前缀，如果以下项之一为 true:</span><span class="sxs-lookup"><span data-stu-id="b6572-142">For static properties, you must map a prefix for a XAML namespace if one of the following is true:</span></span>  
  
-   <span data-ttu-id="b6572-143">所引用的类型存在于 WPF 中但不是 WPF 默认 XAML 命名空间的一部分 ([!INCLUDE[TLA#tla_wpfxmlnsv1](../../../includes/tlasharptla-wpfxmlnsv1-md.md)])。</span><span class="sxs-lookup"><span data-stu-id="b6572-143">You are referencing a type that exists in WPF but is not part of the default XAML namespace for WPF ([!INCLUDE[TLA#tla_wpfxmlnsv1](../../../includes/tlasharptla-wpfxmlnsv1-md.md)]).</span></span> <span data-ttu-id="b6572-144">这是相当普遍使用`x:Static`。</span><span class="sxs-lookup"><span data-stu-id="b6572-144">This is a fairly common scenario for using `x:Static`.</span></span> <span data-ttu-id="b6572-145">例如，可以使用`x:Static`XAML 命名空间映射到引用<xref:System>CLR 命名空间和 mscorlib 程序集引用的静态属性以<xref:System.Environment>类。</span><span class="sxs-lookup"><span data-stu-id="b6572-145">For example, you might use an `x:Static` reference with a XAML namespace mapping to the <xref:System> CLR namespace and mscorlib assembly in order to reference the static properties of the <xref:System.Environment> class.</span></span>  
  
-   <span data-ttu-id="b6572-146">从自定义程序集引用类型。</span><span class="sxs-lookup"><span data-stu-id="b6572-146">You are referencing a type from a custom assembly.</span></span>  
  
-   <span data-ttu-id="b6572-147">正在引用存在于 WPF 程序集中的类型，但该类型是未映射到 WPF 默认 XAML 命名空间的一部分的 CLR 命名空间中。</span><span class="sxs-lookup"><span data-stu-id="b6572-147">You are referencing a type that exists in a WPF assembly, but that type is within a CLR namespace that was not mapped to be part of the WPF default XAML namespace.</span></span> <span data-ttu-id="b6572-148">WPF 默认 XAML 命名空间到 CLR 命名空间的映射由中各种 WPF 程序集的定义 (有关这一概念的详细信息，请参阅[XAML 命名空间和 WPF XAML 的 Namespace 映射](../../../docs/framework/wpf/advanced/xaml-namespaces-and-namespace-mapping-for-wpf-xaml.md))。</span><span class="sxs-lookup"><span data-stu-id="b6572-148">The mapping of CLR namespaces into the default XAML namespace for WPF is performed by definitions in the various WPF assemblies (for more information about this concept, see [XAML Namespaces and Namespace Mapping for WPF XAML](../../../docs/framework/wpf/advanced/xaml-namespaces-and-namespace-mapping-for-wpf-xaml.md)).</span></span> <span data-ttu-id="b6572-149">如果该 CLR 命名空间主要是组成通常不适用于 XAML，如类定义非映射 CLR 命名空间可存在<xref:System.Windows.Threading>。</span><span class="sxs-lookup"><span data-stu-id="b6572-149">Non-mapped CLR namespaces can exist if that CLR namespace is composed mostly of class definitions that are not typically intended for XAML, such as <xref:System.Windows.Threading>.</span></span>  
  
 <span data-ttu-id="b6572-150">有关如何为 WPF 使用前缀和 XAML 命名空间的详细信息，请参阅[XAML 命名空间和 WPF XAML Namespace 映射](../../../docs/framework/wpf/advanced/xaml-namespaces-and-namespace-mapping-for-wpf-xaml.md)。</span><span class="sxs-lookup"><span data-stu-id="b6572-150">For more information on how to use prefixes and XAML namespaces for WPF, see [XAML Namespaces and Namespace Mapping for WPF XAML](../../../docs/framework/wpf/advanced/xaml-namespaces-and-namespace-mapping-for-wpf-xaml.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b6572-151">请参阅</span><span class="sxs-lookup"><span data-stu-id="b6572-151">See Also</span></span>  
 [<span data-ttu-id="b6572-152">x:Type 标记扩展</span><span class="sxs-lookup"><span data-stu-id="b6572-152">x:Type Markup Extension</span></span>](../../../docs/framework/xaml-services/x-type-markup-extension.md)  
 [<span data-ttu-id="b6572-153">从 WPF 迁移到 System.Xaml 的类型</span><span class="sxs-lookup"><span data-stu-id="b6572-153">Types Migrated from WPF to System.Xaml</span></span>](../../../docs/framework/xaml-services/types-migrated-from-wpf-to-system-xaml.md)
