---
title: "如何：使用 XMLDataProvider 和 XPath 查询绑定到 XML 数据"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- XmlDataProvider [WPF], binding to XML data
- data binding [WPF], binding to XML data using XmlDataProvider queries
- binding [WPF], to XML data using XmlDataProvider queries
ms.assetid: 7dcd018f-16aa-4870-8e47-c1b4ea31e574
caps.latest.revision: "22"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 92037be2280eaa248951ff9bad82b7a1581a4fd9
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-bind-to-xml-data-using-an-xmldataprovider-and-xpath-queries"></a>如何：使用 XMLDataProvider 和 XPath 查询绑定到 XML 数据
此示例演示如何将绑定到[!INCLUDE[TLA#tla_xml](../../../../includes/tlasharptla-xml-md.md)]数据使用<xref:System.Windows.Data.XmlDataProvider>。  
  
 与<xref:System.Windows.Data.XmlDataProvider>，则基础可以通过你的应用程序中的数据绑定的数据可以是任何树[!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)]节点。 换而言之，<xref:System.Windows.Data.XmlDataProvider>提供一种简便方式使用的任何树[!INCLUDE[TLA#tla_xml](../../../../includes/tlasharptla-xml-md.md)]作为绑定源的节点。  
  
## <a name="example"></a>示例  
 在下面的示例中，则数据嵌入直接作为[!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)]*数据岛*内<xref:System.Windows.FrameworkElement.Resources%2A>部分。 [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] 数据岛必须包装在 `<x:XData>` 标记中，并始终具有一个单一根节点，在本示例中根节点为 *Inventory*。  
  
> [!NOTE]
>  [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] 数据的根节点具有一个将 [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] 命名空间设置为空字符串的 **xmlns** 属性。 将 XPath 查询应用到 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 页中内联的数据岛时，需要此属性。 在本例内联[!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]，并因此数据岛，继承<xref:System.Windows>命名空间。 因此，你需要将命名空间设置为空，以防止 XPath 查询正在由限定<xref:System.Windows>误导查询的命名空间。  
  
 [!code-xaml[XMLDataSource#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/XmlDataSource/CS/Window1.xaml#1)]  
  
 如此示例中所示，若要使用属性语法创建相同的绑定声明，必须对特殊字符进行正确转义。 有关详细信息，请参阅 [XML 字符实体和 XAML](../../../../docs/framework/xaml-services/xml-character-entities-and-xaml.md)。  
  
 <xref:System.Windows.Controls.ListBox>运行此示例时，将显示以下各项。 这些项为 *Books* 下所有元素的 *Title*，其中 *Stock* 值为“*out*”，*Number* 值为 3 或者大于或等于 8。 请注意，没有*CD*返回项，因为<xref:System.Windows.Data.XmlDataProvider.XPath%2A>值上设置<xref:System.Windows.Data.XmlDataProvider>仅指示*丛书*元素应公开 （实质上设置筛选器）。  
  
 ![XPath 示例](../../../../docs/framework/wpf/data/media/xpathexample.PNG "XPathExample")  
  
 在此示例中，因为显示书名<xref:System.Windows.Data.Binding.XPath%2A>的<xref:System.Windows.Controls.TextBlock>中绑定<xref:System.Windows.DataTemplate>设置为"*标题*"。 如果你想要显示的值的属性，如*ISBN*，则会将设置的<xref:System.Windows.Data.Binding.XPath%2A>值赋给"`@ISBN`"。  
  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 中的 **XPath** 属性使用 XmlNode.SelectNodes 方法处理。 可以修改 **XPath** 查询以获取不同的结果。 下面是一些示例为<xref:System.Windows.Data.Binding.XPath%2A>查询在绑定上<xref:System.Windows.Controls.ListBox>从前面的示例：  
  
-   `XPath="Book[1]"` 将返回第一个 Book 元素（“XML in Action”）。 请注意，**XPath** 索引从 1 而不是从 0 开始。  
  
-   `XPath="Book[@*]"` 将返回带有任意属性的所有 Book 元素。  
  
-   `XPath="Book[last()-1]"` 将返回第二个至最后一个 Book 元素（“Introducing Microsoft .NET”）。  
  
-   `XPath="*[position()>3]"` 将返回除前 3 个元素之外的所有 Book 元素。  
  
 当你运行**XPath**查询，它将返回<xref:System.Xml.XmlNode>或 XmlNodes 的列表。 <xref:System.Xml.XmlNode>是[!INCLUDE[TLA#tla_clr](../../../../includes/tlasharptla-clr-md.md)]对象，这意味着你可以使用<xref:System.Windows.Data.Binding.Path%2A>属性将绑定到[!INCLUDE[TLA#tla_clr](../../../../includes/tlasharptla-clr-md.md)]属性。 再以上述示例为例。 如果该示例的其余部分保持不变，并且更改<xref:System.Windows.Controls.TextBlock>绑定到以下，你将看到的名称中返回 XmlNodes <xref:System.Windows.Controls.ListBox>。 在此情况下，所有返回节点的名称为“*Book*”。  
  
 [!code-xaml[XmlDataSourceVariation#XmlNodePath](../../../../samples/snippets/csharp/VS_Snippets_Wpf/XmlDataSourceVariation/CS/Page1.xaml#xmlnodepath)]  
  
 在某些应用程序中，将 [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] 作为 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 页的源内的数据岛嵌入可能很不方便，因为在编译时必须知道该数据的确切内容。 因此，还支持从外部 [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] 文件获取该数据，如下面的示例所示：  
  
 [!code-xaml[XMLDataSource2#XmlFileExample](../../../../samples/snippets/csharp/VS_Snippets_Wpf/XmlDataSource2/CS/Window1.xaml#xmlfileexample)]  
  
 如果[!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)]数据驻留在远程[!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)]文件，你将定义的访问权限的数据通过分配适当[!INCLUDE[TLA2#tla_url](../../../../includes/tla2sharptla-url-md.md)]到<xref:System.Windows.Data.XmlDataProvider.Source%2A>属性，如下所示：  
  
```xml  
<XmlDataProvider x:Key="BookData" Source="http://MyUrl" XPath="Books"/>  
```  
  
## <a name="see-also"></a>请参阅  
 <xref:System.Windows.Data.ObjectDataProvider>  
 [绑定到 XDocument、XElement 或 LINQ to XML 查询结果](../../../../docs/framework/wpf/data/how-to-bind-to-xdocument-xelement-or-linq-for-xml-query-results.md)  
 [将主-详细模式与分层 XML 数据结合使用](../../../../docs/framework/wpf/data/how-to-use-the-master-detail-pattern-with-hierarchical-xml-data.md)  
 [绑定源概述](../../../../docs/framework/wpf/data/binding-sources-overview.md)  
 [数据绑定概述](../../../../docs/framework/wpf/data/data-binding-overview.md)  
 [帮助主题](../../../../docs/framework/wpf/data/data-binding-how-to-topics.md)
