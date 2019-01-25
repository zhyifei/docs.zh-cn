---
title: x:Array 标记扩展
ms.date: 03/30/2017
f1_keywords:
- x:Array
- xArray
helpviewer_keywords:
- x:Array [XAML Services]
- XAML [XAML Services], x:Array markup extension
ms.assetid: c5358e14-d24c-44c7-b5eb-6062a4fd981c
ms.openlocfilehash: e94928f17a31cdadae11f69c37a4f148452b5d2f
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54699735"
---
# <a name="xarray-markup-extension"></a><span data-ttu-id="057c9-102">x:Array 标记扩展</span><span class="sxs-lookup"><span data-stu-id="057c9-102">x:Array Markup Extension</span></span>
<span data-ttu-id="057c9-103">有关在 XAML 中通过标记扩展的对象的数组，提供了常规支持。</span><span class="sxs-lookup"><span data-stu-id="057c9-103">Provides general support for arrays of objects in XAML through a markup extension.</span></span> <span data-ttu-id="057c9-104">这对应于`x:ArrayExtension`[MS-XAML] 中的 XAML 类型。</span><span class="sxs-lookup"><span data-stu-id="057c9-104">This corresponds to the `x:ArrayExtension` XAML type in [MS-XAML].</span></span>  
  
## <a name="xaml-object-element-usage"></a><span data-ttu-id="057c9-105">XAML 对象元素用法</span><span class="sxs-lookup"><span data-stu-id="057c9-105">XAML Object Element Usage</span></span>  
  
```  
<x:Array Type="typeName">  
  arrayContents  
</x:Array>  
```  
  
## <a name="xaml-values"></a><span data-ttu-id="057c9-106">XAML 值</span><span class="sxs-lookup"><span data-stu-id="057c9-106">XAML Values</span></span>  
  
|||  
|-|-|  
|`typeName`|<span data-ttu-id="057c9-107">类型的名称，你`x:Array`将包含。</span><span class="sxs-lookup"><span data-stu-id="057c9-107">The name of the type that your `x:Array` will contain.</span></span> <span data-ttu-id="057c9-108">`typeName` 可能会 （并且通常为） 作为前缀的 XAML 命名空间包含 XAML 的类型定义。</span><span class="sxs-lookup"><span data-stu-id="057c9-108">`typeName` may be (and often is) prefixed for a XAML namespace that contains the XAML type definitions.</span></span>|  
|`arrayContents`|<span data-ttu-id="057c9-109">分配给该内部函数的项内容`ArrayExtension.Items`属性。</span><span class="sxs-lookup"><span data-stu-id="057c9-109">The items content that is assigned to the intrinsic `ArrayExtension.Items` property.</span></span> <span data-ttu-id="057c9-110">通常情况下，这些项被指定为中包含的一个或多个对象元素`x:Array`开始和结束标记。</span><span class="sxs-lookup"><span data-stu-id="057c9-110">Typically, these items are specified as one or more object elements contained within the `x:Array` opening and closing tags.</span></span> <span data-ttu-id="057c9-111">此处应为可分配给中指定的 XAML 类型的指定对象`typeName`。</span><span class="sxs-lookup"><span data-stu-id="057c9-111">Objects specified here are expected to be assignable to the XAML type specified in `typeName`.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="057c9-112">备注</span><span class="sxs-lookup"><span data-stu-id="057c9-112">Remarks</span></span>  
 <span data-ttu-id="057c9-113">`Type` 为所有的必需的属性`x:Array`对象元素。</span><span class="sxs-lookup"><span data-stu-id="057c9-113">`Type` is a required attribute for all `x:Array` object elements.</span></span> <span data-ttu-id="057c9-114">一个`Type`参数值不需要使用`x:Type`标记扩展; 短类型的名称是 XAML 类型，这可以指定为字符串。</span><span class="sxs-lookup"><span data-stu-id="057c9-114">A `Type` parameter value does not need to use an `x:Type` markup extension; the short name of the type is   a XAML type, which can be specified as a string.</span></span>  
  
 <span data-ttu-id="057c9-115">在.NET Framework XAML 服务实现中，输入的 XAML 类型和 CLR 的输出之间的关系<xref:System.Type>创建数组的会影响服务上下文的标记扩展。</span><span class="sxs-lookup"><span data-stu-id="057c9-115">In the .NET Framework XAML Services implementation, the relationship between the input XAML type and the output CLR <xref:System.Type> of the created array is influenced by service context for markup extensions.</span></span> <span data-ttu-id="057c9-116">输出<xref:System.Type>是<xref:System.Xaml.XamlType.UnderlyingType%2A>后查找所需的输入的 XAML 类型<xref:System.Xaml.XamlType>基于 XAML 架构上下文和<xref:System.Windows.Markup.IXamlTypeResolver>上下文提供的服务。</span><span class="sxs-lookup"><span data-stu-id="057c9-116">The output <xref:System.Type> is the <xref:System.Xaml.XamlType.UnderlyingType%2A> of the input XAML type, after looking up the necessary <xref:System.Xaml.XamlType> based on XAML schema context and the <xref:System.Windows.Markup.IXamlTypeResolver> service the context provides.</span></span>  
  
 <span data-ttu-id="057c9-117">处理时，将数组内容分配给`ArrayExtension.Items`内部属性。</span><span class="sxs-lookup"><span data-stu-id="057c9-117">When processed, the array contents are assigned to the `ArrayExtension.Items` intrinsic property.</span></span> <span data-ttu-id="057c9-118">在中<xref:System.Windows.Markup.ArrayExtension>实现中，这由<xref:System.Windows.Markup.ArrayExtension.Items%2A?displayProperty=nameWithType>。</span><span class="sxs-lookup"><span data-stu-id="057c9-118">In the <xref:System.Windows.Markup.ArrayExtension> implementation, this is represented by <xref:System.Windows.Markup.ArrayExtension.Items%2A?displayProperty=nameWithType>.</span></span>  
  
 <span data-ttu-id="057c9-119">在.NET Framework XAML 服务实现中，对此标记扩展的处理由定义<xref:System.Windows.Markup.ArrayExtension>类。</span><span class="sxs-lookup"><span data-stu-id="057c9-119">In the .NET Framework XAML Services implementation, the handling for this markup extension is defined by the <xref:System.Windows.Markup.ArrayExtension> class.</span></span> <span data-ttu-id="057c9-120"><xref:System.Windows.Markup.ArrayExtension> 未密封，并且无法用作自定义的数组类型的标记扩展插件实现的基础。</span><span class="sxs-lookup"><span data-stu-id="057c9-120"><xref:System.Windows.Markup.ArrayExtension> is not sealed, and could be used as the basis for a markup extension implementation for a custom array type.</span></span>  
  
 <span data-ttu-id="057c9-121">`x:Array` 是的详细信息适用于常规 XAML 语言可扩展性。</span><span class="sxs-lookup"><span data-stu-id="057c9-121">`x:Array` is more intended for general language extensibility in XAML.</span></span> <span data-ttu-id="057c9-122">但`x:Array`还可用于指定 XAML 的 XAML 支持的集合作为其结构化的属性内容某些属性的值。</span><span class="sxs-lookup"><span data-stu-id="057c9-122">But `x:Array` can also be useful for specifying XAML values of certain properties that take XAML-supported collections as their structured property content.</span></span> <span data-ttu-id="057c9-123">例如，可以指定的内容<xref:System.Collections.IEnumerable>具有属性`x:Array`使用情况。</span><span class="sxs-lookup"><span data-stu-id="057c9-123">For example, you could specify the contents of an <xref:System.Collections.IEnumerable> property with an `x:Array` usage.</span></span>  
  
 <span data-ttu-id="057c9-124">`x:Array` 是标记扩展。</span><span class="sxs-lookup"><span data-stu-id="057c9-124">`x:Array` is a markup extension.</span></span> <span data-ttu-id="057c9-125">当要求转义特性值应为非文本值或非处理程序名称时，通常会实现标记扩展，相对于只在某些类型或属性上放置类型转换器而言，此需求更具有全局性。</span><span class="sxs-lookup"><span data-stu-id="057c9-125">Markup extensions are typically implemented when there is a requirement to escape attribute values to be other than literal values or handler names, and the requirement is more global than just putting type converters on certain types or properties.</span></span> <span data-ttu-id="057c9-126">`x:Array` 部分是该规则的例外，因为而不是提供替代属性值处理`x:Array`另类处理其内部文本内容。</span><span class="sxs-lookup"><span data-stu-id="057c9-126">`x:Array` is partially an exception to that rule because instead of providing alternative attribute value handling, `x:Array` provides alternative handling of its inner text content.</span></span> <span data-ttu-id="057c9-127">此行为使现有的内容模型以进行分组到一个数组和更高版本在代码隐藏中引用的访问已命名的数组; 可能不支持的类型您可以调用<xref:System.Array>方法来获取个人数组项。</span><span class="sxs-lookup"><span data-stu-id="057c9-127">This behavior enables types that might not be supported by an existing content model to be grouped into an array and referenced later in code-behind by accessing the named array; you can call <xref:System.Array> methods to get individual array items.</span></span>  
  
 <span data-ttu-id="057c9-128">在 XAML 中的所有标记扩展都使用大括号 ({,} `)`在其特性语法，该命令是依据 XAML 处理器认定标记扩展必须处理的属性值的约定。</span><span class="sxs-lookup"><span data-stu-id="057c9-128">All markup extensions in XAML use the braces ({,}`)` in their attribute syntax, which is the convention by which a XAML processor recognizes that a markup extension must process the attribute value.</span></span> <span data-ttu-id="057c9-129">有关通常的标记扩展的详细信息，请参阅[Type Converters and Markup Extensions for XAML](../../../docs/framework/xaml-services/type-converters-and-markup-extensions-for-xaml.md)。</span><span class="sxs-lookup"><span data-stu-id="057c9-129">For more information about markup extensions in general, see [Type Converters and Markup Extensions for XAML](../../../docs/framework/xaml-services/type-converters-and-markup-extensions-for-xaml.md).</span></span>  
  
 <span data-ttu-id="057c9-130">在 XAML 2009 年，`x:Array`定义为一种语言基元而不是标记扩展。</span><span class="sxs-lookup"><span data-stu-id="057c9-130">In XAML 2009, `x:Array` is defined as a language primitive instead of a markup extension.</span></span> <span data-ttu-id="057c9-131">有关详细信息，请参阅[常见 XAML 语言基元的内置类型](../../../docs/framework/xaml-services/built-in-types-for-common-xaml-language-primitives.md)。</span><span class="sxs-lookup"><span data-stu-id="057c9-131">For more information, see [Built-in Types for Common XAML Language Primitives](../../../docs/framework/xaml-services/built-in-types-for-common-xaml-language-primitives.md).</span></span>  
  
## <a name="wpf-usage-notes"></a><span data-ttu-id="057c9-132">WPF 用法说明</span><span class="sxs-lookup"><span data-stu-id="057c9-132">WPF Usage Notes</span></span>  
 <span data-ttu-id="057c9-133">通常情况下，填充的对象元素`x:Array`不是元素中存在的[!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)]XAML 命名空间，并且需要对非默认 XAML 命名空间的前缀映射。</span><span class="sxs-lookup"><span data-stu-id="057c9-133">Typically, the object elements that populate an `x:Array` are not elements that exist in the [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] XAML namespace, and require a prefix mapping to a non-default XAML namespace.</span></span>  
  
 <span data-ttu-id="057c9-134">例如，以下是两个字符串的简单数组与`sys`前缀 (以及`x`) 数组的级别定义。</span><span class="sxs-lookup"><span data-stu-id="057c9-134">For example, the following is a simple array of two strings, with the `sys` prefix (and also `x`) defined at the level of the array.</span></span>  
  
 <span data-ttu-id="057c9-135">[xaml]</span><span class="sxs-lookup"><span data-stu-id="057c9-135">[xaml]</span></span>  
  
 `<x:Array Type="sys:String" xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"`  
  
 `xmlns:sys="clr-namespace:System;assembly=mscorlib">`  
  
 `<sys:String>Hello</sys:String>`  
  
 `<sys:String>World</sys:String>`  
  
 `</x:Array>`  
  
 <span data-ttu-id="057c9-136">对于用作数组元素的自定义类型，类还必须支持在 XAML 中作为对象元素实例化的要求。</span><span class="sxs-lookup"><span data-stu-id="057c9-136">For custom types that are used as array elements, the class must also support the requirements for being instantiated in XAML as object elements.</span></span> <span data-ttu-id="057c9-137">有关详细信息，请参阅[XAML 及 WPF 的自定义类](../../../docs/framework/wpf/advanced/xaml-and-custom-classes-for-wpf.md)。</span><span class="sxs-lookup"><span data-stu-id="057c9-137">For more information, see [XAML and Custom Classes for WPF](../../../docs/framework/wpf/advanced/xaml-and-custom-classes-for-wpf.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="057c9-138">请参阅</span><span class="sxs-lookup"><span data-stu-id="057c9-138">See also</span></span>
- [<span data-ttu-id="057c9-139">标记扩展和 WPF XAML</span><span class="sxs-lookup"><span data-stu-id="057c9-139">Markup Extensions and WPF XAML</span></span>](../../../docs/framework/wpf/advanced/markup-extensions-and-wpf-xaml.md)
- [<span data-ttu-id="057c9-140">从 WPF 迁移到 System.Xaml 的类型</span><span class="sxs-lookup"><span data-stu-id="057c9-140">Types Migrated from WPF to System.Xaml</span></span>](../../../docs/framework/xaml-services/types-migrated-from-wpf-to-system-xaml.md)
