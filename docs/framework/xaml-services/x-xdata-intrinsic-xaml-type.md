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
ms.openlocfilehash: c8044bc341ded6ef7b03bbdf701e724654460d54
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/08/2019
ms.locfileid: "59125154"
---
# <a name="xxdata-intrinsic-xaml-type"></a><span data-ttu-id="7f564-102">x:XData 内部 XAML 类型</span><span class="sxs-lookup"><span data-stu-id="7f564-102">x:XData Intrinsic XAML Type</span></span>
<span data-ttu-id="7f564-103">启用 XAML 生产中的 XML 数据岛的布局。</span><span class="sxs-lookup"><span data-stu-id="7f564-103">Enables placement of XML data islands within a XAML production.</span></span> <span data-ttu-id="7f564-104">中的 XML 元素`x:XData`如同它们是使其执行操作默认 XAML 命名空间的一部分或任何其他 XAML 命名空间不应由 XAML 处理器处理。</span><span class="sxs-lookup"><span data-stu-id="7f564-104">XML elements within `x:XData` should not be treated by XAML processors as if they are a part of the acting default XAML namespace or any other XAML namespace.</span></span> `x:XData` <span data-ttu-id="7f564-105">可以包含任意格式正确的 XML。</span><span class="sxs-lookup"><span data-stu-id="7f564-105">can contain arbitrary well-formed XML.</span></span>  
  
## <a name="xaml-object-element-usage"></a><span data-ttu-id="7f564-106">XAML 对象元素用法</span><span class="sxs-lookup"><span data-stu-id="7f564-106">XAML Object Element Usage</span></span>  
  
```  
<x:XData>  
  <elementDataRoot>  
    [elementData]  
  </elementDataRoot>  
</x:XData>  
```  
  
## <a name="xaml-values"></a><span data-ttu-id="7f564-107">XAML 值</span><span class="sxs-lookup"><span data-stu-id="7f564-107">XAML Values</span></span>  
  
|||  
|-|-|  
|`elementDataRoot`|<span data-ttu-id="7f564-108">包含的数据岛的单个根元素。</span><span class="sxs-lookup"><span data-stu-id="7f564-108">The single root element of the enclosed data island.</span></span> <span data-ttu-id="7f564-109">对于大多数最终用户来说，不具有单个根的 XML 被视为无效。</span><span class="sxs-lookup"><span data-stu-id="7f564-109">For most eventual consumers, XML that does not have a single root is considered invalid.</span></span> <span data-ttu-id="7f564-110">具体而言，单个根是必需的如果`x:XData`用作 XML 数据源适用于 WPF 或 XML 源用于数据绑定的许多其他技术。</span><span class="sxs-lookup"><span data-stu-id="7f564-110">In particular, a single root is required if the `x:XData` is intended as an XML data source for WPF or many other technologies that use XML sources for data binding.</span></span>|  
|`[elementData]`|<span data-ttu-id="7f564-111">可选。</span><span class="sxs-lookup"><span data-stu-id="7f564-111">Optional.</span></span> <span data-ttu-id="7f564-112">表示 XML 数据的 XML。</span><span class="sxs-lookup"><span data-stu-id="7f564-112">XML that represents the XML data.</span></span> <span data-ttu-id="7f564-113">可以包含任意数量的元素作为元素数据和其他元素，则中可包含嵌套的元素但是，XML 的常规规则适用。</span><span class="sxs-lookup"><span data-stu-id="7f564-113">Any number of elements can be contained as element data and nested elements can be contained in other elements; however, the general rules of XML apply.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="7f564-114">备注</span><span class="sxs-lookup"><span data-stu-id="7f564-114">Remarks</span></span>  
 <span data-ttu-id="7f564-115">中的 XML 元素`x:XData`所有可能的命名空间和前缀的数据中包含的 XMLDOM 对象可以重新声明。</span><span class="sxs-lookup"><span data-stu-id="7f564-115">The XML elements within an `x:XData` object can re-declare all possible namespaces and prefixes of the containing XMLDOM within the data.</span></span>  
  
 <span data-ttu-id="7f564-116">以编程方式访问 XML 数据并`x:XData`是通过.NET Framework XAML 服务中可能存在内部 XAML 类型<xref:System.Windows.Markup.XData>类。</span><span class="sxs-lookup"><span data-stu-id="7f564-116">Programmatic access to XML data and the `x:XData` intrinsic XAML type is possible in .NET Framework XAML Services through the <xref:System.Windows.Markup.XData> class.</span></span>  
  
## <a name="wpf-usage-notes"></a><span data-ttu-id="7f564-117">WPF 用法说明</span><span class="sxs-lookup"><span data-stu-id="7f564-117">WPF Usage Notes</span></span>  
 <span data-ttu-id="7f564-118">`x:XData`主要的子对象的形式使用对象<xref:System.Windows.Data.XmlDataProvider>，或子对象的形式或者<xref:System.Windows.Data.XmlDataProvider.XmlSerializer%2A?displayProperty=nameWithType>属性 （在 XAML，这通常都表示在属性元素语法中）。</span><span class="sxs-lookup"><span data-stu-id="7f564-118">The `x:XData` object is primarily used as a child object of an <xref:System.Windows.Data.XmlDataProvider>, or alternatively, as the child object of the <xref:System.Windows.Data.XmlDataProvider.XmlSerializer%2A?displayProperty=nameWithType> property (in XAML, this is typically expressed in property element syntax).</span></span>  
  
 <span data-ttu-id="7f564-119">数据通常应重定义为新的默认 XML 命名空间 （设置为空字符串） 的数据岛中的基本 XML 命名空间。</span><span class="sxs-lookup"><span data-stu-id="7f564-119">The data should typically redefine the base XML namespace within the data island to be a new default XML namespace (set to an empty string).</span></span> <span data-ttu-id="7f564-120">这是最简单的简单数据岛因为<xref:System.Windows.Data.Binding.XPath%2A>用于引用和绑定到数据的表达式可以避免包含前缀。</span><span class="sxs-lookup"><span data-stu-id="7f564-120">This is easiest for simple data islands because the <xref:System.Windows.Data.Binding.XPath%2A> expressions that are used to reference and bind to the data can avoid inclusion of prefixes.</span></span> <span data-ttu-id="7f564-121">更复杂的数据岛可能会使用特定前缀的根处的 XML 命名空间和定义的数据的多个前缀。</span><span class="sxs-lookup"><span data-stu-id="7f564-121">More complex data islands might define multiple prefixes for the data and use a specific prefix for the XML namespace at the root.</span></span> <span data-ttu-id="7f564-122">在这种情况下，所有<xref:System.Windows.Data.Binding.XPath%2A>表达式引用应包括相应的命名空间映射前缀。</span><span class="sxs-lookup"><span data-stu-id="7f564-122">In this case, all <xref:System.Windows.Data.Binding.XPath%2A> expression references should include the appropriate namespace-mapped prefix.</span></span> <span data-ttu-id="7f564-123">有关详细信息，请参阅[数据绑定概述](../wpf/data/data-binding-overview.md)。</span><span class="sxs-lookup"><span data-stu-id="7f564-123">For more information, see [Data Binding Overview](../wpf/data/data-binding-overview.md).</span></span>  
  
 <span data-ttu-id="7f564-124">从技术上讲，`x:XData`可以用作类型的任何属性的内容<xref:System.Xml.Serialization.IXmlSerializable>。</span><span class="sxs-lookup"><span data-stu-id="7f564-124">Technically, `x:XData` can be used as the content of any property of type <xref:System.Xml.Serialization.IXmlSerializable>.</span></span> <span data-ttu-id="7f564-125">但是，<xref:System.Windows.Data.XmlDataProvider.XmlSerializer%2A?displayProperty=nameWithType>是唯一突出的实现。</span><span class="sxs-lookup"><span data-stu-id="7f564-125">However, <xref:System.Windows.Data.XmlDataProvider.XmlSerializer%2A?displayProperty=nameWithType> is the only prominent implementation.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7f564-126">请参阅</span><span class="sxs-lookup"><span data-stu-id="7f564-126">See also</span></span>

- <xref:System.Windows.Data.XmlDataProvider>
- [<span data-ttu-id="7f564-127">数据绑定概述</span><span class="sxs-lookup"><span data-stu-id="7f564-127">Data Binding Overview</span></span>](../wpf/data/data-binding-overview.md)
- [<span data-ttu-id="7f564-128">绑定标记扩展</span><span class="sxs-lookup"><span data-stu-id="7f564-128">Binding Markup Extension</span></span>](../wpf/advanced/binding-markup-extension.md)
