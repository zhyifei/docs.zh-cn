---
title: 如何：使数据可用于 XAML 中的绑定
ms.date: 01/29/2018
dev_langs:
- csharp
- vb
helpviewer_keywords:
- data binding [WPF], making data available for binding
- binding data [WPF], making data available for
ms.assetid: 7103c2e8-0e31-4a13-bf12-ca382221a8d5
ms.openlocfilehash: 09a6fca48c06efca6f06b9e0617de9095197bd17
ms.sourcegitcommit: 700b9003ea6bdd83a53458bbc436c9b5778344f1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/03/2018
ms.locfileid: "48261467"
---
# <a name="how-to-make-data-available-for-binding-in-xaml"></a>如何：使数据可用于 XAML 中的绑定
本主题讨论使数据可用于[!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)]绑定的各种方法，取决于应用程序的需求。  
  
## <a name="example"></a>示例  
 如果想绑定到[!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]中[!INCLUDE[TLA#tla_clr](../../../../includes/tlasharptla-clr-md.md)]对象，使该对象可用于绑定的一种方法是将其定义为资源并为其提供`x:Key`。 在以下示例中，一个`Person`对象具有字符串属性`PersonName`。 `Person`对象 (在突出显示的包含`<src>`元素的行中) 定义在命名空间`SDKSample`中。  
  
 [!code-xaml[SimpleBinding#Instantiation](../../../../samples/snippets/csharp/VS_Snippets_Wpf/SimpleBinding/CSharp/Page1.xaml?highlight=9,37)]  
  
 然后就可以将<xref:System.Windows.Controls.TextBlock>控件绑定到[!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]中的对象，如突出显示的包含`<TextBlock>`元素的行所示。 
  
 或者使用<xref:System.Windows.Data.ObjectDataProvider>类，如以下示例所示：  
  
 [!code-xaml[ObjectDataProvider}](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/SimpleBinding/VisualBasic/Page1.xaml?highlight=10-14,42)]  
  
 以相同的方式定义绑定，如突出显示的包含`<TextBlock>`元素的行所示。  
  
 在此特定示例中，结果是相同的： <xref:System.Windows.Controls.TextBlock>的文本内容为`Joe`。 但是，<xref:System.Windows.Data.ObjectDataProvider>类还提供了其他功能，例如能够绑定到方法的结果。 如果您需要<xref:System.Windows.Data.ObjectDataProvider>类提供的功能就可以选用它。  
  
 但是，如果要绑定到已创建的对象，则需要在代码中设置`DataContext`，如以下示例所示。  
  
 [!code-csharp[ADODataSet#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ADODataSet/CSharp/Window1.xaml.cs#1)]
 [!code-vb[ADODataSet#1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ADODataSet/VisualBasic/Window1.xaml.vb#1)]  
  
 使用<xref:System.Windows.Data.XmlDataProvider>类访问[!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)]数据用于绑定，请参阅[XMLDataProvider 和 XPath 查询绑定到 XML 数据使用](../../../../docs/framework/wpf/data/how-to-bind-to-xml-data-using-an-xmldataprovider-and-xpath-queries.md)。 使用<xref:System.Windows.Data.ObjectDataProvider>类访问[!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)]数据用于绑定，请参阅[绑定到 XDocument、 XElement 或 LINQ for XML 查询结果](../../../../docs/framework/wpf/data/how-to-bind-to-xdocument-xelement-or-linq-for-xml-query-results.md)。  
  
 有关各种指定绑定数据的方式，请参阅[指定绑定源](../../../../docs/framework/wpf/data/how-to-specify-the-binding-source.md)。 有关哪些类型的数据可以用于绑定，或如何实现您自己的[!INCLUDE[TLA#tla_clr](../../../../includes/tlasharptla-clr-md.md)]对象的绑定，请参阅[绑定源概述](../../../../docs/framework/wpf/data/binding-sources-overview.md)。  
  
## <a name="see-also"></a>请参阅  
 [数据绑定概述](../../../../docs/framework/wpf/data/data-binding-overview.md)  
 [帮助主题](../../../../docs/framework/wpf/data/data-binding-how-to-topics.md)
