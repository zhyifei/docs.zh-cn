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
ms.openlocfilehash: 91e89dbf36024c31f4afcd9b6d956944baf13576
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2020
ms.locfileid: "79174181"
---
# <a name="how-to-make-data-available-for-binding-in-xaml"></a>如何：使数据可用于 XAML 中的绑定
本主题讨论各种方法，您可以根据应用程序的需求将数据可用于绑定[!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)]。  
  
## <a name="example"></a>示例  
 如果您有一个公用语言运行时 （CLR） 对象，您希望绑定[!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]到 ，使对象可用于绑定的一种方法是将其定义为资源并给它一个`x:Key`。 在下面的示例中，您有一个`Person`具有字符串属性的对象， `PersonName` 对象`Person`（在显示的突出显示包含`<src>`元素的行中）在称为`SDKSample`的命名空间中定义。  
  
 [!code-xaml[SimpleBinding#Instantiation](~/samples/snippets/csharp/VS_Snippets_Wpf/SimpleBinding/CSharp/Page1.xaml?highlight=9,37)]  
  
 然后，<xref:System.Windows.Controls.TextBlock>可以将控件绑定到 中[!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]的对象，如包含`<TextBlock>`元素的突出显示行所示。
  
 或者，您可以使用类<xref:System.Windows.Data.ObjectDataProvider>，如以下示例所示：  
  
 [!code-xaml[ObjectDataProvider}](~/samples/snippets/visualbasic/VS_Snippets_Wpf/SimpleBinding/VisualBasic/Page1.xaml?highlight=10-14,42)]  
  
 定义绑定的方式与包含`<TextBlock>`元素的突出显示行相同。  
  
 在此特定示例中，结果相同：您<xref:System.Windows.Controls.TextBlock>具有 与 文本内容`Joe`一起 。 但是，类<xref:System.Windows.Data.ObjectDataProvider>提供的功能，例如绑定到方法结果的功能。 如果需要提供的功能，<xref:System.Windows.Data.ObjectDataProvider>可以选择使用该类。  
  
 但是，如果要绑定到已创建的对象，则需要设置`DataContext`in 代码，如以下示例所示。  
  
 [!code-csharp[ADODataSet#1](~/samples/snippets/csharp/VS_Snippets_Wpf/ADODataSet/CSharp/Window1.xaml.cs#1)]
 [!code-vb[ADODataSet#1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ADODataSet/VisualBasic/Window1.xaml.vb#1)]  
  
 要使用<xref:System.Windows.Data.XmlDataProvider>类访问 XML 数据以进行绑定，请参阅[使用 XMLData 提供程序和 XPath 查询绑定到 XML 数据](how-to-bind-to-xml-data-using-an-xmldataprovider-and-xpath-queries.md)。 要使用 类访问用于绑定的<xref:System.Windows.Data.ObjectDataProvider>XML 数据，请参阅[绑定到 XDocument、XElement 或 LINQ 获取 XML 查询结果](how-to-bind-to-xdocument-xelement-or-linq-for-xml-query-results.md)。  
  
 有关指定绑定数据的许多方法的信息，请参阅[指定绑定源](how-to-specify-the-binding-source.md)。 有关可以绑定到哪些类型的数据以及如何实现自己的通用语言运行时 （CLR） 对象进行绑定的信息，请参阅[绑定源概述](binding-sources-overview.md)。  
  
## <a name="see-also"></a>另请参阅

- [数据绑定概述](../../../desktop-wpf/data/data-binding-overview.md)
- [如何使用主题](data-binding-how-to-topics.md)
