---
title: "x:Static 标记扩展"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- StaticExtension
- xStatic
- x:Static
helpviewer_keywords:
- x:Static markup extension [XAML Services]
- Static markup extension in XAML [XAML Services]
- XAML [XAML Services], x:Static markup extension
ms.assetid: 056aee79-7cdd-434f-8174-dfc856cad343
caps.latest.revision: "25"
author: wadepickett
ms.author: wpickett
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 647bfed7b321a949090f6da047f9b8105d335101
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="xstatic-markup-extension"></a><span data-ttu-id="275f5-102">x:Static 标记扩展</span><span class="sxs-lookup"><span data-stu-id="275f5-102">x:Static Markup Extension</span></span>
<span data-ttu-id="275f5-103">引用任何静态的按值代码实体中定义[!INCLUDE[TLA#tla_cls](../../../includes/tlasharptla-cls-md.md)]– 遵守法规的方法。</span><span class="sxs-lookup"><span data-stu-id="275f5-103">References any static by-value code entity that is defined in a [!INCLUDE[TLA#tla_cls](../../../includes/tlasharptla-cls-md.md)]–compliant way.</span></span> <span data-ttu-id="275f5-104">引用的静态属性可用来提供 XAML 中的属性的值。</span><span class="sxs-lookup"><span data-stu-id="275f5-104">The static property that is referenced can be used to provide the value of a property in XAML.</span></span>  
  
## <a name="xaml-attribute-usage"></a><span data-ttu-id="275f5-105">XAML 属性用法</span><span class="sxs-lookup"><span data-stu-id="275f5-105">XAML Attribute Usage</span></span>  
  
```xaml  
<object property="{x:Static prefix:typeName.staticMemberName}" .../>  
```  
  
## <a name="xaml-values"></a><span data-ttu-id="275f5-106">XAML 值</span><span class="sxs-lookup"><span data-stu-id="275f5-106">XAML Values</span></span>  
  
|||  
|-|-|  
|`prefix`|<span data-ttu-id="275f5-107">可选。</span><span class="sxs-lookup"><span data-stu-id="275f5-107">Optional.</span></span> <span data-ttu-id="275f5-108">指映射、 非默认 XAML 命名空间前缀。</span><span class="sxs-lookup"><span data-stu-id="275f5-108">A prefix that refers to a mapped, non-default XAML namespace.</span></span> <span data-ttu-id="275f5-109">`prefix`所示显式使用由于很少引用来自默认 XAML 命名空间的静态属性。</span><span class="sxs-lookup"><span data-stu-id="275f5-109">`prefix` is shown explicitly in the usage because you rarely reference static properties that come from a default XAML namespace.</span></span> <span data-ttu-id="275f5-110">请参阅“备注”。</span><span class="sxs-lookup"><span data-stu-id="275f5-110">See Remarks.</span></span>|  
|`typeName`|<span data-ttu-id="275f5-111">必须的。</span><span class="sxs-lookup"><span data-stu-id="275f5-111">Required.</span></span> <span data-ttu-id="275f5-112">定义的所需的静态成员的类型的名称。</span><span class="sxs-lookup"><span data-stu-id="275f5-112">The name of the type that defines the desired static member.</span></span>|  
|`staticMemberName`|<span data-ttu-id="275f5-113">必须的。</span><span class="sxs-lookup"><span data-stu-id="275f5-113">Required.</span></span> <span data-ttu-id="275f5-114">所需的静态值成员 （常量、 静态属性、 字段或枚举值） 的名称。</span><span class="sxs-lookup"><span data-stu-id="275f5-114">The name of the desired static value member (a constant, a static property, a field, or an enumeration value).</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="275f5-115">备注</span><span class="sxs-lookup"><span data-stu-id="275f5-115">Remarks</span></span>  
 <span data-ttu-id="275f5-116">引用的代码实体必须是以下项之一：</span><span class="sxs-lookup"><span data-stu-id="275f5-116">The code entity that is referenced must be one of the following:</span></span>  
  
-   <span data-ttu-id="275f5-117">常量</span><span class="sxs-lookup"><span data-stu-id="275f5-117">A constant</span></span>  
  
-   <span data-ttu-id="275f5-118">静态属性</span><span class="sxs-lookup"><span data-stu-id="275f5-118">A static property</span></span>  
  
-   <span data-ttu-id="275f5-119">字段</span><span class="sxs-lookup"><span data-stu-id="275f5-119">A field</span></span>  
  
-   <span data-ttu-id="275f5-120">一个枚举值</span><span class="sxs-lookup"><span data-stu-id="275f5-120">An enumeration value</span></span>  
  
 <span data-ttu-id="275f5-121">如果 XAML 是标记编译或 XAML 的加载时间分析异常，指定任何其他代码实体，例如非静态属性，会导致编译时错误。</span><span class="sxs-lookup"><span data-stu-id="275f5-121">Specifying any other code entity, such as a nonstatic property, causes a compile-time error if the XAML is markup compiled, or a XAML load-time parse exception.</span></span>  
  
 <span data-ttu-id="275f5-122">你可以`x:Static`对静态字段或属性不在当前的 XAML 文档中; 默认 XAML 命名空间的引用但是，这需要的前缀映射。</span><span class="sxs-lookup"><span data-stu-id="275f5-122">You can make `x:Static` references to static fields or properties that are not in the default XAML namespace for the current XAML document; however, this requires a prefix mapping.</span></span> <span data-ttu-id="275f5-123">几乎总是 XAML 文档的根元素上定义的 XAML 命名空间。</span><span class="sxs-lookup"><span data-stu-id="275f5-123">XAML namespaces are almost always defined on the root element of the XAML document.</span></span>  
  
 <span data-ttu-id="275f5-124">可以由.NET Framework XAML 服务和其 XAML 读取器和 XAML 编写器执行对于静态属性的查找操作，它们是在运行时与默认 XAML 架构上下文。</span><span class="sxs-lookup"><span data-stu-id="275f5-124">The lookup operations for static properties can be performed by .NET Framework XAML Services and its XAML readers and XAML writers, when they are running with the default XAML schema context.</span></span> <span data-ttu-id="275f5-125">此 XAML 架构上下文可用于 CLR 反射提供所需的静态值为对象图构造。</span><span class="sxs-lookup"><span data-stu-id="275f5-125">This XAML schema context can use CLR reflection to provide the necessary static values for object graph construction.</span></span> <span data-ttu-id="275f5-126">`typeName`你指定实际是 XAML 类型名称，不是 CLR 类型名称，虽然这些是实质上是相同的名称，当使用默认 XAML 架构上下文或当使用所有现有的基于 CLR 的 XAML 实现框架。</span><span class="sxs-lookup"><span data-stu-id="275f5-126">The `typeName` you specify is actually a XAML type name, not a CLR type name, although these are essentially the same name when using the default XAML schema context or when using all existing CLR-based XAML-implementing frameworks.</span></span>  
  
 <span data-ttu-id="275f5-127">当你进行时要格外小心`x:Static`它们不直接是属性的值的类型的引用。</span><span class="sxs-lookup"><span data-stu-id="275f5-127">Use caution when you make `x:Static` references that are not directly the type of a property's value.</span></span> <span data-ttu-id="275f5-128">在 XAML 处理序列中，从标记扩展提供的值不调用其他值的转换。</span><span class="sxs-lookup"><span data-stu-id="275f5-128">In the XAML processing sequence, provided values from a markup extension do not invoke additional value conversion.</span></span> <span data-ttu-id="275f5-129">这是 true 即使你`x:Static`引用创建文本字符串，且通常基于文本字符串的属性值的值转换发生时针对特定成员或为返回类型的所有成员值。</span><span class="sxs-lookup"><span data-stu-id="275f5-129">This is true even if your `x:Static` reference creates a text string, and a value conversion for attribute values based on text string typically occurs either for that specific member or for any member values of the return type.</span></span>  
  
 <span data-ttu-id="275f5-130">特性语法是最常用于该标记扩展的语法。</span><span class="sxs-lookup"><span data-stu-id="275f5-130">Attribute syntax is the most common syntax used with this markup extension.</span></span> <span data-ttu-id="275f5-131">在 `x:Static` 标识符字符串之后提供的字符串标记被指定为基础 <xref:System.Windows.Markup.StaticExtension.Member%2A> 扩展类的 <xref:System.Windows.Markup.StaticExtension> 值。</span><span class="sxs-lookup"><span data-stu-id="275f5-131">The string token provided after the `x:Static` identifier string is assigned as the <xref:System.Windows.Markup.StaticExtension.Member%2A> value of the underlying <xref:System.Windows.Markup.StaticExtension> extension class.</span></span>  
  
 <span data-ttu-id="275f5-132">有两个还从技术上讲可能有其他 XAML 用法。</span><span class="sxs-lookup"><span data-stu-id="275f5-132">There are two other XAML usages that are technically possible.</span></span> <span data-ttu-id="275f5-133">但是，这些用法并不常见，因为它们是冗长:</span><span class="sxs-lookup"><span data-stu-id="275f5-133">However, these usages are less common because they are unnecessarily verbose:</span></span>  
  
 <span data-ttu-id="275f5-134">**对象元素语法：** `<x:Static Member="` `prefix` `:` `typeName` `.` `staticMemberName``" .../>`</span><span class="sxs-lookup"><span data-stu-id="275f5-134">**Object element syntax:** `<x:Static Member="` `prefix` `:` `typeName` `.` `staticMemberName` `" .../>`</span></span>  
  
 <span data-ttu-id="275f5-135">**属性具有显式成员属性的初始化字符串的语法：** `<` `object`  ``  `property` `="{x:Static Member=` `prefix` `:` `typeName` `.` `staticMemberName``}" .../>`</span><span class="sxs-lookup"><span data-stu-id="275f5-135">**Attribute syntax with explicit Member property for initialization string:** `<` `object` `` `property` `="{x:Static Member=` `prefix` `:` `typeName` `.` `staticMemberName` `}" .../>`</span></span>  
  
 <span data-ttu-id="275f5-136">在.NET Framework XAML 服务实现中，对此标记扩展的处理由定义<xref:System.Windows.Markup.StaticExtension>类。</span><span class="sxs-lookup"><span data-stu-id="275f5-136">In the .NET Framework XAML Services implementation, the handling for this markup extension is defined by the <xref:System.Windows.Markup.StaticExtension> class.</span></span>  
  
 <span data-ttu-id="275f5-137">`x:Static` 是标记扩展。</span><span class="sxs-lookup"><span data-stu-id="275f5-137">`x:Static` is a markup extension.</span></span> <span data-ttu-id="275f5-138">XAML 使用中的所有标记扩展`{`和`}`其属性的语法，这是 XAML 处理器识别标记扩展，必须提供一个值所依据的约定中的字符。</span><span class="sxs-lookup"><span data-stu-id="275f5-138">All markup extensions in XAML use the `{` and `}` characters in their attribute syntax, which is the convention by which a XAML processor recognizes that a markup extension must provide a value.</span></span> <span data-ttu-id="275f5-139">有关标记扩展的详细信息，请参阅 [Markup Extensions for XAML Overview](../../../docs/framework/xaml-services/markup-extensions-for-xaml-overview.md)。</span><span class="sxs-lookup"><span data-stu-id="275f5-139">For more information about markup extensions, see [Markup Extensions for XAML Overview](../../../docs/framework/xaml-services/markup-extensions-for-xaml-overview.md).</span></span>  
  
## <a name="wpf-usage-notes"></a><span data-ttu-id="275f5-140">WPF 用法说明</span><span class="sxs-lookup"><span data-stu-id="275f5-140">WPF Usage Notes</span></span>  
 <span data-ttu-id="275f5-141">将用于 WPF 编程的默认 XAML 命名空间不包含许多有用的静态属性，并且有用的静态属性大多具有支持，例如促进而无需使用的类型转换器`{x:Static}`。</span><span class="sxs-lookup"><span data-stu-id="275f5-141">The default XAML namespace you use for WPF programming does not contain many useful static properties, and most of the useful static properties have support such as type converters that facilitate the usage without requiring `{x:Static}` .</span></span> <span data-ttu-id="275f5-142">对于静态属性，必须映射 XAML 命名空间的前缀，如果下列其中一项为 true:</span><span class="sxs-lookup"><span data-stu-id="275f5-142">For static properties, you must map a prefix for a XAML namespace if one of the following is true:</span></span>  
  
-   <span data-ttu-id="275f5-143">所引用的类型，存在于 WPF，但不是 WPF 的默认 XAML 命名空间的一部分 ([!INCLUDE[TLA#tla_wpfxmlnsv1](../../../includes/tlasharptla-wpfxmlnsv1-md.md)])。</span><span class="sxs-lookup"><span data-stu-id="275f5-143">You are referencing a type that exists in WPF but is not part of the default XAML namespace for WPF ([!INCLUDE[TLA#tla_wpfxmlnsv1](../../../includes/tlasharptla-wpfxmlnsv1-md.md)]).</span></span> <span data-ttu-id="275f5-144">这是一个非常常见方案用于使用`x:Static`。</span><span class="sxs-lookup"><span data-stu-id="275f5-144">This is a fairly common scenario for using `x:Static`.</span></span> <span data-ttu-id="275f5-145">例如，你可能使用`x:Static`XAML 命名空间映射到引用<xref:System>CLR 命名空间和 mscorlib 程序集以引用的静态属性<xref:System.Environment>类。</span><span class="sxs-lookup"><span data-stu-id="275f5-145">For example, you might use an `x:Static` reference with a XAML namespace mapping to the <xref:System> CLR namespace and mscorlib assembly in order to reference the static properties of the <xref:System.Environment> class.</span></span>  
  
-   <span data-ttu-id="275f5-146">从自定义程序集，所引用的类型。</span><span class="sxs-lookup"><span data-stu-id="275f5-146">You are referencing a type from a custom assembly.</span></span>  
  
-   <span data-ttu-id="275f5-147">所引用存在于 WPF 程序集的类型，但该类型位于未映射的 WPF 默认 XAML 命名空间一部分的 CLR 命名空间。</span><span class="sxs-lookup"><span data-stu-id="275f5-147">You are referencing a type that exists in a WPF assembly, but that type is within a CLR namespace that was not mapped to be part of the WPF default XAML namespace.</span></span> <span data-ttu-id="275f5-148">WPF 默认 XAML 命名空间到 CLR 命名空间的映射由各种 WPF 程序集中定义 (有关这一概念的详细信息，请参阅[XAML 命名空间和 WPF XAML Namespace 映射](../../../docs/framework/wpf/advanced/xaml-namespaces-and-namespace-mapping-for-wpf-xaml.md))。</span><span class="sxs-lookup"><span data-stu-id="275f5-148">The mapping of CLR namespaces into the default XAML namespace for WPF is performed by definitions in the various WPF assemblies (for more information about this concept, see [XAML Namespaces and Namespace Mapping for WPF XAML](../../../docs/framework/wpf/advanced/xaml-namespaces-and-namespace-mapping-for-wpf-xaml.md)).</span></span> <span data-ttu-id="275f5-149">如果该 CLR 命名空间主要组成一般不应为 XAML，如的类定义非映射 CLR 命名空间可以存在<xref:System.Windows.Threading>。</span><span class="sxs-lookup"><span data-stu-id="275f5-149">Non-mapped CLR namespaces can exist if that CLR namespace is composed mostly of class definitions that are not typically intended for XAML, such as <xref:System.Windows.Threading>.</span></span>  
  
 <span data-ttu-id="275f5-150">有关如何为 WPF 使用前缀和 XAML 命名空间的详细信息，请参阅[XAML 命名空间和 Namespace 映射为 WPF XAML](../../../docs/framework/wpf/advanced/xaml-namespaces-and-namespace-mapping-for-wpf-xaml.md)。</span><span class="sxs-lookup"><span data-stu-id="275f5-150">For more information on how to use prefixes and XAML namespaces for WPF, see [XAML Namespaces and Namespace Mapping for WPF XAML](../../../docs/framework/wpf/advanced/xaml-namespaces-and-namespace-mapping-for-wpf-xaml.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="275f5-151">请参阅</span><span class="sxs-lookup"><span data-stu-id="275f5-151">See Also</span></span>  
 [<span data-ttu-id="275f5-152">x:Type 标记扩展</span><span class="sxs-lookup"><span data-stu-id="275f5-152">x:Type Markup Extension</span></span>](../../../docs/framework/xaml-services/x-type-markup-extension.md)  
 [<span data-ttu-id="275f5-153">从 WPF 迁移到 System.Xaml 的类型</span><span class="sxs-lookup"><span data-stu-id="275f5-153">Types Migrated from WPF to System.Xaml</span></span>](../../../docs/framework/xaml-services/types-migrated-from-wpf-to-system-xaml.md)
