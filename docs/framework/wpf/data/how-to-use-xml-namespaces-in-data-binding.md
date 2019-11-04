---
title: 如何：在数据绑定中使用 XML 命名空间
ms.date: 03/30/2017
helpviewer_keywords:
- XML [WPF], namespaces
- data binding [WPF], XML namespaces
- namespaces [WPF], XML
ms.assetid: a47c832f-dc84-48f2-96d5-cde18fc4284b
ms.openlocfilehash: 47ce0d951df39c7b60aa2a543baf845f5471de6c
ms.sourcegitcommit: 944ddc52b7f2632f30c668815f92b378efd38eea
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/03/2019
ms.locfileid: "73460300"
---
# <a name="how-to-use-xml-namespaces-in-data-binding"></a>如何：在数据绑定中使用 XML 命名空间
## <a name="example"></a>示例
 本示例演示如何处理在 [!INCLUDE[TLA#tla_xml](../../../../includes/tlasharptla-xml-md.md)] 绑定源中指定的命名空间。

 如果 [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] 数据具有以下 [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] 命名空间定义：

 `<rss version="2.0" xmlns:dc="http://purl.org/dc/elements/1.1/">`

 您可以使用 <xref:System.Windows.Data.XmlNamespaceMapping> 元素将命名空间映射到 <xref:System.Windows.Data.XmlNamespaceMapping.Prefix%2A>，如下面的示例中所示。 然后，可以使用 <xref:System.Windows.Data.XmlNamespaceMapping.Prefix%2A> 引用 [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] 命名空间。 本示例中的 <xref:System.Windows.Controls.ListBox> 显示每个*项目*的*标题*和*dc：日期*。

 [!code-xaml[XmlnsBindSnippet#XmlNamespaceMapping](~/samples/snippets/csharp/VS_Snippets_Wpf/XmlnsBindSnippet/CS/Window1.xaml#xmlnamespacemapping)]

 请注意，您指定的 <xref:System.Windows.Data.XmlNamespaceMapping.Prefix%2A> 不必与 [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] 源中使用的相同;如果 [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] 源中的前缀发生更改，则映射仍可正常工作。

 在此特定示例中，[!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] 的数据来自 web 服务，但 <xref:System.Windows.Data.XmlNamespaceMapping> 元素也适用于内嵌 [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] 或嵌入文件中 [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] 数据。

## <a name="see-also"></a>请参阅

- [使用 XMLDataProvider 和 XPath 查询绑定到 XML 数据](how-to-bind-to-xml-data-using-an-xmldataprovider-and-xpath-queries.md)
- [数据绑定概述](../../../desktop-wpf/data/data-binding-overview.md)
- [帮助主题](data-binding-how-to-topics.md)
