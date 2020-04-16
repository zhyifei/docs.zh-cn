---
title: x:XData 内部 XAML 类型
ms.date: 03/30/2017
f1_keywords:
- x:XData
- XData
- xXData
helpviewer_keywords:
- XAML [XAML Services], x:XData directive element
- XData in XAML [XAML Services]
- x:XData XAML directive element [XAML Services]
ms.assetid: 7ce209c2-621b-4977-b643-565f7e663534
ms.openlocfilehash: b7f0954158988db107feb4a6c51ba81d5db11dcb
ms.sourcegitcommit: c2d9718996402993cf31541f11e95531bc68bad0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/27/2020
ms.locfileid: "81432790"
---
# <a name="xxdata-intrinsic-xaml-type"></a><span data-ttu-id="0888a-102">x:XData 内部 XAML 类型</span><span class="sxs-lookup"><span data-stu-id="0888a-102">x:XData Intrinsic XAML Type</span></span>
<span data-ttu-id="0888a-103">支持在 XAML 生产中放置 XML 数据孤岛。</span><span class="sxs-lookup"><span data-stu-id="0888a-103">Enables placement of XML data islands within a XAML production.</span></span> <span data-ttu-id="0888a-104">XAML`x:XData`处理器不应将其中的 XML 元素视为代理默认 XAML 命名空间或任何其他 XAML 命名空间的一部分。</span><span class="sxs-lookup"><span data-stu-id="0888a-104">XML elements within `x:XData` should not be treated by XAML processors as if they are a part of the acting default XAML namespace or any other XAML namespace.</span></span> <span data-ttu-id="0888a-105">`x:XData`可以包含任意格式良好的 XML。</span><span class="sxs-lookup"><span data-stu-id="0888a-105">`x:XData` can contain arbitrary well-formed XML.</span></span>

## <a name="xaml-object-element-usage"></a><span data-ttu-id="0888a-106">XAML 对象元素用法</span><span class="sxs-lookup"><span data-stu-id="0888a-106">XAML Object Element Usage</span></span>

```xaml
<x:XData>
  <elementDataRoot>
    [elementData]
  </elementDataRoot>
</x:XData>
```

## <a name="xaml-values"></a><span data-ttu-id="0888a-107">XAML 值</span><span class="sxs-lookup"><span data-stu-id="0888a-107">XAML Values</span></span>

|||
|-|-|
|`elementDataRoot`|<span data-ttu-id="0888a-108">封闭数据岛的单根元素。</span><span class="sxs-lookup"><span data-stu-id="0888a-108">The single root element of the enclosed data island.</span></span> <span data-ttu-id="0888a-109">对于大多数最终使用者，没有单个根的 XML 被视为无效。</span><span class="sxs-lookup"><span data-stu-id="0888a-109">For most eventual consumers, XML that does not have a single root is considered invalid.</span></span> <span data-ttu-id="0888a-110">特别是，如果`x:XData`用作 WPF 的 XML 数据源或使用 XML 源进行数据绑定的许多其他技术，则需要单个根。</span><span class="sxs-lookup"><span data-stu-id="0888a-110">In particular, a single root is required if the `x:XData` is intended as an XML data source for WPF or many other technologies that use XML sources for data binding.</span></span>|
|`[elementData]`|<span data-ttu-id="0888a-111">可选。</span><span class="sxs-lookup"><span data-stu-id="0888a-111">Optional.</span></span> <span data-ttu-id="0888a-112">表示 XML 数据的 XML。</span><span class="sxs-lookup"><span data-stu-id="0888a-112">XML that represents the XML data.</span></span> <span data-ttu-id="0888a-113">任意数量的元素可以包含在元素数据中，嵌套元素可以包含在其他元素中;但是，XML 的一般规则适用。</span><span class="sxs-lookup"><span data-stu-id="0888a-113">Any number of elements can be contained as element data and nested elements can be contained in other elements; however, the general rules of XML apply.</span></span>|

## <a name="remarks"></a><span data-ttu-id="0888a-114">备注</span><span class="sxs-lookup"><span data-stu-id="0888a-114">Remarks</span></span>

<span data-ttu-id="0888a-115">`x:XData`对象中的 XML 元素可以重新声明数据中包含 XMLDOM 的所有可能的命名空间和前缀。</span><span class="sxs-lookup"><span data-stu-id="0888a-115">The XML elements within an `x:XData` object can re-declare all possible namespaces and prefixes of the containing XMLDOM within the data.</span></span>

<span data-ttu-id="0888a-116">在 .NET XAML 服务中可以通过`x:XData`<xref:System.Windows.Markup.XData>类对 XML 数据和内在 XAML 类型进行编程访问。</span><span class="sxs-lookup"><span data-stu-id="0888a-116">Programmatic access to XML data and the `x:XData` intrinsic XAML type is possible in .NET XAML Services through the <xref:System.Windows.Markup.XData> class.</span></span>

## <a name="wpf-usage-notes"></a><span data-ttu-id="0888a-117">WPF 用法说明</span><span class="sxs-lookup"><span data-stu-id="0888a-117">WPF Usage Notes</span></span>

<span data-ttu-id="0888a-118">该`x:XData`对象主要用作<xref:System.Windows.Data.XmlDataProvider>的子对象，或者用作属性的<xref:System.Windows.Data.XmlDataProvider.XmlSerializer%2A?displayProperty=nameWithType>子对象（在 XAML 中，这通常用属性元素语法表示）。</span><span class="sxs-lookup"><span data-stu-id="0888a-118">The `x:XData` object is primarily used as a child object of an <xref:System.Windows.Data.XmlDataProvider>, or alternatively, as the child object of the <xref:System.Windows.Data.XmlDataProvider.XmlSerializer%2A?displayProperty=nameWithType> property (in XAML, this is typically expressed in property element syntax).</span></span>

<span data-ttu-id="0888a-119">数据通常应重新定义数据孤岛中的基本 XML 命名空间，作为新的默认 XML 命名空间（设置为空字符串）。</span><span class="sxs-lookup"><span data-stu-id="0888a-119">The data should typically redefine the base XML namespace within the data island to be a new default XML namespace (set to an empty string).</span></span> <span data-ttu-id="0888a-120">对于简单的数据孤岛来说，这很容易，<xref:System.Windows.Data.Binding.XPath%2A>因为用于引用和绑定到数据的表达式可以避免包含前缀。</span><span class="sxs-lookup"><span data-stu-id="0888a-120">This is easiest for simple data islands because the <xref:System.Windows.Data.Binding.XPath%2A> expressions that are used to reference and bind to the data can avoid inclusion of prefixes.</span></span> <span data-ttu-id="0888a-121">更复杂的数据孤岛可能为数据定义多个前缀，并使用根目录的 XML 命名空间的特定前缀。</span><span class="sxs-lookup"><span data-stu-id="0888a-121">More complex data islands might define multiple prefixes for the data and use a specific prefix for the XML namespace at the root.</span></span> <span data-ttu-id="0888a-122">在这种情况下，所有<xref:System.Windows.Data.Binding.XPath%2A>表达式引用都应包含适当的命名空间映射前缀。</span><span class="sxs-lookup"><span data-stu-id="0888a-122">In this case, all <xref:System.Windows.Data.Binding.XPath%2A> expression references should include the appropriate namespace-mapped prefix.</span></span> <span data-ttu-id="0888a-123">有关详细信息，请参阅 [数据绑定概述](../data/data-binding-overview.md)。</span><span class="sxs-lookup"><span data-stu-id="0888a-123">For more information, see [Data Binding Overview](../data/data-binding-overview.md).</span></span>

<span data-ttu-id="0888a-124">从技术上讲，`x:XData`可用作任何类型<xref:System.Xml.Serialization.IXmlSerializable>属性的内容。</span><span class="sxs-lookup"><span data-stu-id="0888a-124">Technically, `x:XData` can be used as the content of any property of type <xref:System.Xml.Serialization.IXmlSerializable>.</span></span> <span data-ttu-id="0888a-125">然而，<xref:System.Windows.Data.XmlDataProvider.XmlSerializer%2A?displayProperty=nameWithType>是唯一突出的实现。</span><span class="sxs-lookup"><span data-stu-id="0888a-125">However, <xref:System.Windows.Data.XmlDataProvider.XmlSerializer%2A?displayProperty=nameWithType> is the only prominent implementation.</span></span>

## <a name="see-also"></a><span data-ttu-id="0888a-126">请参阅</span><span class="sxs-lookup"><span data-stu-id="0888a-126">See also</span></span>

- <xref:System.Windows.Data.XmlDataProvider>
- [<span data-ttu-id="0888a-127">数据绑定概述</span><span class="sxs-lookup"><span data-stu-id="0888a-127">Data Binding Overview</span></span>](../data/data-binding-overview.md)
- [<span data-ttu-id="0888a-128">绑定标记扩展</span><span class="sxs-lookup"><span data-stu-id="0888a-128">Binding Markup Extension</span></span>](../../framework/wpf/advanced/binding-markup-extension.md)
