---
title: 如何：在数据绑定中使用 XML 命名空间
ms.date: 03/30/2017
helpviewer_keywords:
- XML [WPF], namespaces
- data binding [WPF], XML namespaces
- namespaces [WPF], XML
ms.assetid: a47c832f-dc84-48f2-96d5-cde18fc4284b
ms.openlocfilehash: 38bf6e8f88b0325193d49148cd6c33031f7b0a6d
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "61931906"
---
# <a name="how-to-use-xml-namespaces-in-data-binding"></a><span data-ttu-id="eb208-102">如何：在数据绑定中使用 XML 命名空间</span><span class="sxs-lookup"><span data-stu-id="eb208-102">How to: Use XML Namespaces in Data Binding</span></span>
## <a name="example"></a><span data-ttu-id="eb208-103">示例</span><span class="sxs-lookup"><span data-stu-id="eb208-103">Example</span></span>  
 <span data-ttu-id="eb208-104">本示例演示如何处理在 [!INCLUDE[TLA#tla_xml](../../../../includes/tlasharptla-xml-md.md)] 绑定源中指定的命名空间。</span><span class="sxs-lookup"><span data-stu-id="eb208-104">This example shows how to handle namespaces specified in your [!INCLUDE[TLA#tla_xml](../../../../includes/tlasharptla-xml-md.md)] binding source.</span></span>  
  
 <span data-ttu-id="eb208-105">如果 [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] 数据具有以下 [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] 命名空间定义：</span><span class="sxs-lookup"><span data-stu-id="eb208-105">If your [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] data has the following [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] namespace definition:</span></span>  
  
 `<rss version="2.0" xmlns:dc="http://purl.org/dc/elements/1.1/">`  
  
 <span data-ttu-id="eb208-106">可以使用<xref:System.Windows.Data.XmlNamespaceMapping>元素将映射到命名空间<xref:System.Windows.Data.XmlNamespaceMapping.Prefix%2A>，如下面的示例。</span><span class="sxs-lookup"><span data-stu-id="eb208-106">You can use the <xref:System.Windows.Data.XmlNamespaceMapping> element to map the namespace to a <xref:System.Windows.Data.XmlNamespaceMapping.Prefix%2A>, as in the following example.</span></span> <span data-ttu-id="eb208-107">然后，可以使用<xref:System.Windows.Data.XmlNamespaceMapping.Prefix%2A>来指代[!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)]命名空间。</span><span class="sxs-lookup"><span data-stu-id="eb208-107">You can then use the <xref:System.Windows.Data.XmlNamespaceMapping.Prefix%2A> to refer to the [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] namespace.</span></span> <span data-ttu-id="eb208-108"><xref:System.Windows.Controls.ListBox>在此示例中显示*标题*并*标题*每个*项*。</span><span class="sxs-lookup"><span data-stu-id="eb208-108">The <xref:System.Windows.Controls.ListBox> in this example displays the *title* and *dc:date* of each *item*.</span></span>  
  
 [!code-xaml[XmlnsBindSnippet#XmlNamespaceMapping](~/samples/snippets/csharp/VS_Snippets_Wpf/XmlnsBindSnippet/CS/Window1.xaml#xmlnamespacemapping)]  
  
 <span data-ttu-id="eb208-109">请注意，<xref:System.Windows.Data.XmlNamespaceMapping.Prefix%2A>指定不需要匹配中使用的一个[!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)]源; 如果前缀中的更改[!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)]源映射仍然正常工作。</span><span class="sxs-lookup"><span data-stu-id="eb208-109">Note that the <xref:System.Windows.Data.XmlNamespaceMapping.Prefix%2A> you specify does not have to match the one used in the [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] source; if the prefix changes in the [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] source your mapping still works.</span></span>  
  
 <span data-ttu-id="eb208-110">在此特定示例中，[!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)]数据来自于 web 服务，但<xref:System.Windows.Data.XmlNamespaceMapping>元素还处理内联[!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)]或[!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)]嵌入的文件中的数据。</span><span class="sxs-lookup"><span data-stu-id="eb208-110">In this particular example, the [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] data comes from a web service, but the <xref:System.Windows.Data.XmlNamespaceMapping> element also works with inline [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] or [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] data in an embedded file.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="eb208-111">请参阅</span><span class="sxs-lookup"><span data-stu-id="eb208-111">See also</span></span>

- [<span data-ttu-id="eb208-112">使用 XMLDataProvider 和 XPath 查询绑定到 XML 数据</span><span class="sxs-lookup"><span data-stu-id="eb208-112">Bind to XML Data Using an XMLDataProvider and XPath Queries</span></span>](how-to-bind-to-xml-data-using-an-xmldataprovider-and-xpath-queries.md)
- [<span data-ttu-id="eb208-113">数据绑定概述</span><span class="sxs-lookup"><span data-stu-id="eb208-113">Data Binding Overview</span></span>](data-binding-overview.md)
- [<span data-ttu-id="eb208-114">帮助主题</span><span class="sxs-lookup"><span data-stu-id="eb208-114">How-to Topics</span></span>](data-binding-how-to-topics.md)
