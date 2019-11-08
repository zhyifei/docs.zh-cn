---
title: 如何：在数据绑定中使用 XML 命名空间
ms.date: 03/30/2017
helpviewer_keywords:
- XML [WPF], namespaces
- data binding [WPF], XML namespaces
- namespaces [WPF], XML
ms.assetid: a47c832f-dc84-48f2-96d5-cde18fc4284b
ms.openlocfilehash: f6e6e042fa5583fcf91bd15c524537490fb6670c
ms.sourcegitcommit: 22be09204266253d45ece46f51cc6f080f2b3fd6
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/07/2019
ms.locfileid: "73740576"
---
# <a name="how-to-use-xml-namespaces-in-data-binding"></a><span data-ttu-id="42920-102">如何：在数据绑定中使用 XML 命名空间</span><span class="sxs-lookup"><span data-stu-id="42920-102">How to: Use XML Namespaces in Data Binding</span></span>
## <a name="example"></a><span data-ttu-id="42920-103">示例</span><span class="sxs-lookup"><span data-stu-id="42920-103">Example</span></span>
 <span data-ttu-id="42920-104">此示例演示如何处理 XML 绑定源中指定的命名空间。</span><span class="sxs-lookup"><span data-stu-id="42920-104">This example shows how to handle namespaces specified in your XML binding source.</span></span>

 <span data-ttu-id="42920-105">如果 XML 数据具有以下 XML 命名空间定义：</span><span class="sxs-lookup"><span data-stu-id="42920-105">If your XML data has the following XML namespace definition:</span></span>

 `<rss version="2.0" xmlns:dc="http://purl.org/dc/elements/1.1/">`

 <span data-ttu-id="42920-106">您可以使用 <xref:System.Windows.Data.XmlNamespaceMapping> 元素将命名空间映射到 <xref:System.Windows.Data.XmlNamespaceMapping.Prefix%2A>，如下面的示例中所示。</span><span class="sxs-lookup"><span data-stu-id="42920-106">You can use the <xref:System.Windows.Data.XmlNamespaceMapping> element to map the namespace to a <xref:System.Windows.Data.XmlNamespaceMapping.Prefix%2A>, as in the following example.</span></span> <span data-ttu-id="42920-107">然后，可以使用 <xref:System.Windows.Data.XmlNamespaceMapping.Prefix%2A> 引用 XML 命名空间。</span><span class="sxs-lookup"><span data-stu-id="42920-107">You can then use the <xref:System.Windows.Data.XmlNamespaceMapping.Prefix%2A> to refer to the XML namespace.</span></span> <span data-ttu-id="42920-108">本示例中的 <xref:System.Windows.Controls.ListBox> 显示每个*项目*的*标题*和*dc：日期*。</span><span class="sxs-lookup"><span data-stu-id="42920-108">The <xref:System.Windows.Controls.ListBox> in this example displays the *title* and *dc:date* of each *item*.</span></span>

 [!code-xaml[XmlnsBindSnippet#XmlNamespaceMapping](~/samples/snippets/csharp/VS_Snippets_Wpf/XmlnsBindSnippet/CS/Window1.xaml#xmlnamespacemapping)]

 <span data-ttu-id="42920-109">请注意，您指定的 <xref:System.Windows.Data.XmlNamespaceMapping.Prefix%2A> 不必与 XML 源中使用的相同;如果 XML 源中的前缀发生更改，则映射仍可正常工作。</span><span class="sxs-lookup"><span data-stu-id="42920-109">Note that the <xref:System.Windows.Data.XmlNamespaceMapping.Prefix%2A> you specify does not have to match the one used in the XML source; if the prefix changes in the XML source your mapping still works.</span></span>

 <span data-ttu-id="42920-110">在此特定示例中，XML 数据来自 web 服务，但 <xref:System.Windows.Data.XmlNamespaceMapping> 元素也适用于嵌入文件中的内联 XML 或 XML 数据。</span><span class="sxs-lookup"><span data-stu-id="42920-110">In this particular example, the XML data comes from a web service, but the <xref:System.Windows.Data.XmlNamespaceMapping> element also works with inline XML or XML data in an embedded file.</span></span>

## <a name="see-also"></a><span data-ttu-id="42920-111">请参阅</span><span class="sxs-lookup"><span data-stu-id="42920-111">See also</span></span>

- [<span data-ttu-id="42920-112">使用 XMLDataProvider 和 XPath 查询绑定到 XML 数据</span><span class="sxs-lookup"><span data-stu-id="42920-112">Bind to XML Data Using an XMLDataProvider and XPath Queries</span></span>](how-to-bind-to-xml-data-using-an-xmldataprovider-and-xpath-queries.md)
- [<span data-ttu-id="42920-113">数据绑定概述</span><span class="sxs-lookup"><span data-stu-id="42920-113">Data Binding Overview</span></span>](../../../desktop-wpf/data/data-binding-overview.md)
- [<span data-ttu-id="42920-114">帮助主题</span><span class="sxs-lookup"><span data-stu-id="42920-114">How-to Topics</span></span>](data-binding-how-to-topics.md)
