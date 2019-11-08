---
title: 如何：使用 XMLDataProvider 和 XPath 查询绑定到 XML 数据
ms.date: 03/30/2017
helpviewer_keywords:
- XmlDataProvider [WPF], binding to XML data
- data binding [WPF], binding to XML data using XmlDataProvider queries
- binding [WPF], to XML data using XmlDataProvider queries
ms.assetid: 7dcd018f-16aa-4870-8e47-c1b4ea31e574
ms.openlocfilehash: f075d646539de5d68e1c9c75d9664451125e9919
ms.sourcegitcommit: 22be09204266253d45ece46f51cc6f080f2b3fd6
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/07/2019
ms.locfileid: "73733561"
---
# <a name="how-to-bind-to-xml-data-using-an-xmldataprovider-and-xpath-queries"></a>如何：使用 XMLDataProvider 和 XPath 查询绑定到 XML 数据
此示例演示如何使用 <xref:System.Windows.Data.XmlDataProvider>绑定到 XML 数据。  
  
 使用 <xref:System.Windows.Data.XmlDataProvider>，可以通过应用程序中的数据绑定访问的基础数据可以是 XML 节点的任意树。 换句话说，<xref:System.Windows.Data.XmlDataProvider> 提供了一种简便的方法来使用 XML 节点的任意树作为绑定源。  
  
## <a name="example"></a>示例  
 在下面的示例中，数据直接作为 XML*数据岛*嵌入到 <xref:System.Windows.FrameworkElement.Resources%2A> 部分中。 XML 数据岛必须包装在 `<x:XData>` 标记中，并且始终有一个根节点，这是此示例中的*清单*。  
  
> [!NOTE]
> XML 数据的根节点具有将 XML 命名空间设置为空字符串的**xmlns**属性。 将 XPath 查询应用到 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 页中内联的数据岛时，需要此属性。 在此内联情况下，[!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]，因此数据岛继承了 <xref:System.Windows> 命名空间。 因此，需要将命名空间设置为空白，以使 XPath 查询不受 <xref:System.Windows> 命名空间的限定，这会 misdirect 查询。  
  
 [!code-xaml[XMLDataSource#1](~/samples/snippets/csharp/VS_Snippets_Wpf/XmlDataSource/CS/Window1.xaml#1)]  
  
 如此示例中所示，若要使用属性语法创建相同的绑定声明，必须对特殊字符进行正确转义。 有关详细信息，请参阅 [XML 字符实体和 XAML](../../xaml-services/xml-character-entities-and-xaml.md)。  
  
 运行此示例时，<xref:System.Windows.Controls.ListBox> 将显示以下各项。 这些项为 *Books* 下所有元素的 *Title*，其中 *Stock* 值为“*out*”，*Number* 值为 3 或者大于或等于 8。 请注意，不会返回任何*CD*项目，因为在 <xref:System.Windows.Data.XmlDataProvider> 上设置的 <xref:System.Windows.Data.XmlDataProvider.XPath%2A> 值指示只应公开*图书*元素（实质上是设置筛选器）。  
  
 ![显示四本书标题的 XPath 示例的屏幕截图。](./media/how-to-bind-to-xml-data-using-an-xmldataprovider-and-xpath-queries/xpath-example-listbox-details.png)  
  
 在此示例中，将显示书籍标题，因为 <xref:System.Windows.DataTemplate> 中 <xref:System.Windows.Controls.TextBlock> 绑定的 <xref:System.Windows.Data.Binding.XPath%2A> 设置为 "*Title*"。 如果要显示特性的值（如*ISBN*），请将此 <xref:System.Windows.Data.Binding.XPath%2A> 值设置为 "`@ISBN`"。  
  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 中的 **XPath** 属性使用 XmlNode.SelectNodes 方法处理。 可以修改 **XPath** 查询以获取不同的结果。 下面是前面示例中绑定 <xref:System.Windows.Controls.ListBox> 上的 <xref:System.Windows.Data.Binding.XPath%2A> 查询的一些示例：  
  
- `XPath="Book[1]"` 将返回第一个 Book 元素（“XML in Action”）。 请注意，**XPath** 索引从 1 而不是从 0 开始。  
  
- `XPath="Book[@*]"` 将返回带有任意属性的所有 Book 元素。  
  
- `XPath="Book[last()-1]"` 将返回第二个至最后一个 Book 元素（“Introducing Microsoft .NET”）。  
  
- `XPath="*[position()>3]"` 将返回除前 3 个元素之外的所有 Book 元素。  
  
 运行**XPath**查询时，它将返回 <xref:System.Xml.XmlNode> 或 XmlNodes 列表。 <xref:System.Xml.XmlNode> 是公共语言运行时（CLR）对象，这意味着你可以使用 <xref:System.Windows.Data.Binding.Path%2A> 属性绑定到公共语言运行时（CLR）属性。 再以上述示例为例。 如果该示例的其余部分保持不变，并且将 <xref:System.Windows.Controls.TextBlock> 绑定更改为以下内容，则会在 <xref:System.Windows.Controls.ListBox>中看到返回的 XmlNodes 的名称。 在此情况下，所有返回节点的名称为“*Book*”。  
  
 [!code-xaml[XmlDataSourceVariation#XmlNodePath](~/samples/snippets/csharp/VS_Snippets_Wpf/XmlDataSourceVariation/CS/Page1.xaml#xmlnodepath)]  
  
 在某些应用程序中，将 XML 作为数据岛嵌入到 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 页的源中可能不太方便，因为在编译时必须知道数据的确切内容。 因此，还支持从外部 XML 文件获取数据，如以下示例中所示：  
  
 [!code-xaml[XMLDataSource2#XmlFileExample](~/samples/snippets/csharp/VS_Snippets_Wpf/XmlDataSource2/CS/Window1.xaml#xmlfileexample)]  
  
 如果 XML 数据位于远程 XML 文件中，则可以通过将相应的 URL 分配到 <xref:System.Windows.Data.XmlDataProvider.Source%2A> 特性来定义对数据的访问权限，如下所示：  
  
```xml  
<XmlDataProvider x:Key="BookData" Source="http://MyUrl" XPath="Books"/>  
```  
  
## <a name="see-also"></a>请参阅

- <xref:System.Windows.Data.ObjectDataProvider>
- [绑定到 XDocument、XElement 或 LINQ to XML 查询结果](how-to-bind-to-xdocument-xelement-or-linq-for-xml-query-results.md)
- [将主-详细模式与分层 XML 数据结合使用](how-to-use-the-master-detail-pattern-with-hierarchical-xml-data.md)
- [绑定源概述](binding-sources-overview.md)
- [数据绑定概述](../../../desktop-wpf/data/data-binding-overview.md)
- [帮助主题](data-binding-how-to-topics.md)
