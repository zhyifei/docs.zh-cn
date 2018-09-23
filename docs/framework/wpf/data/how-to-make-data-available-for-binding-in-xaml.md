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
ms.sourcegitcommit: ad99773e5e45068ce03b99518008397e1299e0d1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/23/2018
ms.locfileid: "46703484"
---
# <a name="how-to-make-data-available-for-binding-in-xaml"></a>如何：使数据可用于 XAML 中的绑定
本主题讨论您可以使数据可用于绑定中的各种方法[!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)]，取决于应用程序的需求。  
  
## <a name="example"></a>示例  
 如果有[!INCLUDE[TLA#tla_clr](../../../../includes/tlasharptla-clr-md.md)]对象想要将绑定到从[!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]中，您可以使对象可绑定是定义为资源并为其提供的一种方法`x:Key`。 在以下示例中，必须`Person`具有名为的字符串属性对象`PersonName`。 `Person`对象 (在显示突出显示的行，其中包含`<src>`元素) 在名为命名空间中定义`SDKSample`。  
  
 [!code-xaml[SimpleBinding#Instantiation](../../../../samples/snippets/csharp/VS_Snippets_Wpf/SimpleBinding/CSharp/Page1.xaml?highlight=9,37)]  
  
 然后可以绑定<xref:System.Windows.Controls.TextBlock>控件中的对象[!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]，如突出显示的行包含`<TextBlock>`元素所示。 
  
 或者，可以使用<xref:System.Windows.Data.ObjectDataProvider>类，如以下示例所示：  
  
 [!code-xaml[ObjectDataProvider}](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/SimpleBinding/VisualBasic/Page1.xaml?highlight=10-14,42)]  
  
 定义绑定一样，突出显示的行包含`<TextBlock>`元素所示。  
  
 在此特定示例中，结果是相同： 有<xref:System.Windows.Controls.TextBlock>的文本内容与`Joe`。 但是，<xref:System.Windows.Data.ObjectDataProvider>类提供了功能，例如能够绑定到方法的结果。 您可以选择使用<xref:System.Windows.Data.ObjectDataProvider>类如果您需要它提供的功能。  
  
 但是，如果要绑定到已创建的对象，则需要设置`DataContext`在代码中，如以下示例所示。  
  
 [!code-csharp[ADODataSet#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ADODataSet/CSharp/Window1.xaml.cs#1)]
 [!code-vb[ADODataSet#1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ADODataSet/VisualBasic/Window1.xaml.vb#1)]  
  
 访问[!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)]绑定使用的数据<xref:System.Windows.Data.XmlDataProvider>类，请参阅[XMLDataProvider 和 XPath 查询绑定到 XML 数据使用](../../../../docs/framework/wpf/data/how-to-bind-to-xml-data-using-an-xmldataprovider-and-xpath-queries.md)。 访问[!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)]绑定使用的数据<xref:System.Windows.Data.ObjectDataProvider>类，请参阅[绑定到 XDocument、 XElement 或 LINQ for XML 查询结果](../../../../docs/framework/wpf/data/how-to-bind-to-xdocument-xelement-or-linq-for-xml-query-results.md)。  
  
 可以指定要绑定到的数据很多方式的信息，请参阅[指定绑定源](../../../../docs/framework/wpf/data/how-to-specify-the-binding-source.md)。 有关哪些类型的数据可以绑定到或如何实现您自己[!INCLUDE[TLA#tla_clr](../../../../includes/tlasharptla-clr-md.md)]对象的绑定，请参阅[绑定源概述](../../../../docs/framework/wpf/data/binding-sources-overview.md)。  
  
## <a name="see-also"></a>请参阅  
 [数据绑定概述](../../../../docs/framework/wpf/data/data-binding-overview.md)  
 [帮助主题](../../../../docs/framework/wpf/data/data-binding-how-to-topics.md)
