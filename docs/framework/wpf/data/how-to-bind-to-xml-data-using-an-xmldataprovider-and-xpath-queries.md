---
title: 如何：使用 XMLDataProvider 和 XPath 查询绑定到 XML 数据
ms.date: 03/30/2017
helpviewer_keywords:
- XmlDataProvider [WPF], binding to XML data
- data binding [WPF], binding to XML data using XmlDataProvider queries
- binding [WPF], to XML data using XmlDataProvider queries
ms.assetid: 7dcd018f-16aa-4870-8e47-c1b4ea31e574
ms.openlocfilehash: 2d2b9e4dd817562a6b4de15edc51b428c397f29b
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54509297"
---
# <a name="how-to-bind-to-xml-data-using-an-xmldataprovider-and-xpath-queries"></a>如何：使用 XMLDataProvider 和 XPath 查询绑定到 XML 数据
此示例演示如何将绑定到[!INCLUDE[TLA#tla_xml](../../../../includes/tlasharptla-xml-md.md)]数据使用<xref:System.Windows.Data.XmlDataProvider>。  
  
 与<xref:System.Windows.Data.XmlDataProvider>，则基础可以通过在应用程序中的数据绑定访问的数据可以是任何树[!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)]节点。 换而言之，<xref:System.Windows.Data.XmlDataProvider>提供了方便地使用的任意树[!INCLUDE[TLA#tla_xml](../../../../includes/tlasharptla-xml-md.md)]用作绑定源的节点。  
  
## <a name="example"></a>示例  
 在以下示例中，嵌入数据作为直接[!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)]*数据岛*内<xref:System.Windows.FrameworkElement.Resources%2A>部分。 [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] 数据岛必须包装在 `<x:XData>` 标记中，并始终具有一个单一根节点，在本示例中根节点为 *Inventory*。  
  
> [!NOTE]
>  [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] 数据的根节点具有一个将 [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] 命名空间设置为空字符串的 **xmlns** 属性。 将 XPath 查询应用到 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 页中内联的数据岛时，需要此属性。 在本例内联[!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]，因此数据岛，它继承<xref:System.Windows>命名空间。 因此，您需要设置命名空间为空，以防止 XPath 查询正在由限定<xref:System.Windows>命名空间，而误导查询。  
  
 [!code-xaml[XMLDataSource#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/XmlDataSource/CS/Window1.xaml#1)]  
  
 如此示例中所示，若要使用属性语法创建相同的绑定声明，必须对特殊字符进行正确转义。 有关详细信息，请参阅 [XML 字符实体和 XAML](../../../../docs/framework/xaml-services/xml-character-entities-and-xaml.md)。  
  
 <xref:System.Windows.Controls.ListBox>时运行此示例中，将显示以下各项。 这些项为 *Books* 下所有元素的 *Title*，其中 *Stock* 值为“*out*”，*Number* 值为 3 或者大于或等于 8。 请注意，没有*CD*返回的项，因为<xref:System.Windows.Data.XmlDataProvider.XPath%2A>值上设置<xref:System.Windows.Data.XmlDataProvider>仅指示*丛书*元素应公开 （这设置筛选器）。  
  
 ![XPath 示例](../../../../docs/framework/wpf/data/media/xpathexample.PNG "XPathExample")  
  
 在此示例中，因为显示书名<xref:System.Windows.Data.Binding.XPath%2A>的<xref:System.Windows.Controls.TextBlock>中的绑定<xref:System.Windows.DataTemplate>设置为"*标题*"。 如果你想要显示的值的属性，如*ISBN*，则会将该设置<xref:System.Windows.Data.Binding.XPath%2A>值设置为"`@ISBN`"。  
  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 中的 **XPath** 属性使用 XmlNode.SelectNodes 方法处理。 可以修改 **XPath** 查询以获取不同的结果。 下面是有关一些示例<xref:System.Windows.Data.Binding.XPath%2A>查询上绑定了<xref:System.Windows.Controls.ListBox>来自前面的示例：  
  
-   `XPath="Book[1]"` 将返回第一个 Book 元素（“XML in Action”）。 请注意，**XPath** 索引从 1 而不是从 0 开始。  
  
-   `XPath="Book[@*]"` 将返回带有任意属性的所有 Book 元素。  
  
-   `XPath="Book[last()-1]"` 将返回第二个至最后一个 Book 元素（“Introducing Microsoft .NET”）。  
  
-   `XPath="*[position()>3]"` 将返回除前 3 个元素之外的所有 Book 元素。  
  
 在运行时**XPath**查询，它将返回<xref:System.Xml.XmlNode>或 Xmlnode 列表。 <xref:System.Xml.XmlNode> 是[!INCLUDE[TLA#tla_clr](../../../../includes/tlasharptla-clr-md.md)]对象，这意味着可以使用<xref:System.Windows.Data.Binding.Path%2A>要绑定到属性[!INCLUDE[TLA#tla_clr](../../../../includes/tlasharptla-clr-md.md)]属性。 再以上述示例为例。 如果该示例的其余部分保持不变，并且你更改<xref:System.Windows.Controls.TextBlock>绑定到以下，将看到在返回的 Xmlnode 的名称<xref:System.Windows.Controls.ListBox>。 在此情况下，所有返回节点的名称为“*Book*”。  
  
 [!code-xaml[XmlDataSourceVariation#XmlNodePath](../../../../samples/snippets/csharp/VS_Snippets_Wpf/XmlDataSourceVariation/CS/Page1.xaml#xmlnodepath)]  
  
 在某些应用程序中，将 [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] 作为 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 页的源内的数据岛嵌入可能很不方便，因为在编译时必须知道该数据的确切内容。 因此，还支持从外部 [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] 文件获取该数据，如下面的示例所示：  
  
 [!code-xaml[XMLDataSource2#XmlFileExample](../../../../samples/snippets/csharp/VS_Snippets_Wpf/XmlDataSource2/CS/Window1.xaml#xmlfileexample)]  
  
 如果[!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)]数据驻留在远程[!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)]文件中，您将通过定义访问权限的数据分配一个适当[!INCLUDE[TLA2#tla_url](../../../../includes/tla2sharptla-url-md.md)]到<xref:System.Windows.Data.XmlDataProvider.Source%2A>属性，如下所示：  
  
```xml  
<XmlDataProvider x:Key="BookData" Source="http://MyUrl" XPath="Books"/>  
```  
  
## <a name="see-also"></a>请参阅
- <xref:System.Windows.Data.ObjectDataProvider>
- [绑定到 XDocument、XElement 或 LINQ to XML 查询结果](../../../../docs/framework/wpf/data/how-to-bind-to-xdocument-xelement-or-linq-for-xml-query-results.md)
- [将主-详细模式与分层 XML 数据结合使用](../../../../docs/framework/wpf/data/how-to-use-the-master-detail-pattern-with-hierarchical-xml-data.md)
- [绑定源概述](../../../../docs/framework/wpf/data/binding-sources-overview.md)
- [数据绑定概述](../../../../docs/framework/wpf/data/data-binding-overview.md)
- [帮助主题](../../../../docs/framework/wpf/data/data-binding-how-to-topics.md)
