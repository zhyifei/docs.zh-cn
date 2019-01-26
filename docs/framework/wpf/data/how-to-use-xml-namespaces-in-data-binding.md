---
title: 如何：在数据绑定中使用 XML 命名空间
ms.date: 03/30/2017
helpviewer_keywords:
- XML [WPF], namespaces
- data binding [WPF], XML namespaces
- namespaces [WPF], XML
ms.assetid: a47c832f-dc84-48f2-96d5-cde18fc4284b
ms.openlocfilehash: bd2a156920057dc197fabbaa46e3a2d886a1b322
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54600344"
---
# <a name="how-to-use-xml-namespaces-in-data-binding"></a>如何：在数据绑定中使用 XML 命名空间
## <a name="example"></a>示例  
 本示例演示如何处理在 [!INCLUDE[TLA#tla_xml](../../../../includes/tlasharptla-xml-md.md)] 绑定源中指定的命名空间。  
  
 如果 [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] 数据具有以下 [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] 命名空间定义：  
  
 `<rss version="2.0" xmlns:dc="http://purl.org/dc/elements/1.1/">`  
  
 可以使用 <xref:System.Windows.Data.XmlNamespaceMapping> 元素将命名空间映射到 <xref:System.Windows.Data.XmlNamespaceMapping.Prefix%2A>，如下面的示例所示。 然后就可以用 <xref:System.Windows.Data.XmlNamespaceMapping.Prefix%2A> 来指代 [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] 命名空间。 此示例中的 <xref:System.Windows.Controls.ListBox> 显示每个 *item* 的 *title* 和 *dc:date*。  
  
 [!code-xaml[XmlnsBindSnippet#XmlNamespaceMapping](../../../../samples/snippets/csharp/VS_Snippets_Wpf/XmlnsBindSnippet/CS/Window1.xaml#xmlnamespacemapping)]  
  
 请注意，指定的 <xref:System.Windows.Data.XmlNamespaceMapping.Prefix%2A> 不需要匹配于 [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] 源中使用的; 如果 [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] 源中的前缀发生变化，映射仍然能正常工作。  
  
 在此特定示例中，[!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] 数据来自于 web 服务，但 <xref:System.Windows.Data.XmlNamespaceMapping> 元素也能处理内联 [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] 或嵌入文件中的 [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] 的数据。  
  
## <a name="see-also"></a>请参阅
- [使用 XMLDataProvider 和 XPath 查询绑定到 XML 数据](../../../../docs/framework/wpf/data/how-to-bind-to-xml-data-using-an-xmldataprovider-and-xpath-queries.md)
- [数据绑定概述](../../../../docs/framework/wpf/data/data-binding-overview.md)
- [帮助主题](../../../../docs/framework/wpf/data/data-binding-how-to-topics.md)
