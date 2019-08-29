---
title: 如何：处理 ListView 中每一项的 MouseDoubleClick 事件
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- ListView controls [WPF], MouseDoubleClick event
ms.assetid: 81b39369-655a-4585-ac58-4640e5bb8fed
ms.openlocfilehash: 7e51c810a2e1e4bf4157aa1311255c5547021b60
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2019
ms.locfileid: "69962066"
---
# <a name="how-to-handle-the-mousedoubleclick-event-for-each-item-in-a-listview"></a>如何：处理 ListView 中每一项的 MouseDoubleClick 事件
若要在中处理项的事件<xref:System.Windows.Controls.ListView>, 需要向每个<xref:System.Windows.Controls.ListViewItem>中添加一个事件处理程序。 当绑定到数据源时, 您不会显式<xref:System.Windows.Controls.ListViewItem>创建, 但您可以通过将添加<xref:System.Windows.EventSetter>到的样式<xref:System.Windows.Controls.ListViewItem>来处理每个项的事件。 <xref:System.Windows.Controls.ListView>  
  
## <a name="example"></a>示例  
 下面的示例创建一个数据绑定<xref:System.Windows.Controls.ListView> , 并创建一个<xref:System.Windows.Style>来向每个<xref:System.Windows.Controls.ListViewItem>中添加一个事件处理程序。  
  
 [!code-xaml[ListViewHowTos#1](~/samples/snippets/csharp/VS_Snippets_Wpf/ListViewHowTos/CSharp/Window1.xaml#1)]  
[!code-xaml[ListViewHowTos#5](~/samples/snippets/csharp/VS_Snippets_Wpf/ListViewHowTos/CSharp/Window1.xaml#5)]  
[!code-xaml[ListViewHowTos#2](~/samples/snippets/csharp/VS_Snippets_Wpf/ListViewHowTos/CSharp/Window1.xaml#2)]  
  
 下面的示例处理<xref:System.Windows.Controls.Control.MouseDoubleClick>事件。  
  
 [!code-csharp[ListViewHowTos#6](~/samples/snippets/csharp/VS_Snippets_Wpf/ListViewHowTos/CSharp/Window1.xaml.cs#6)]
 [!code-vb[ListViewHowTos#6](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ListViewHowTos/VisualBasic/Window1.xaml.vb#6)]  
  
> [!NOTE]
> 虽然将绑定<xref:System.Windows.Controls.ListView>到数据源最常见, 但你可以使用样式将事件处理程序添加到非数据<xref:System.Windows.Controls.ListView>绑定中的<xref:System.Windows.Controls.ListViewItem>每个, 无论你是否显式创建。 <xref:System.Windows.Controls.ListViewItem>  有关显式和隐式创建<xref:System.Windows.Controls.ListViewItem>的控件的详细信息, 请参阅。 <xref:System.Windows.Controls.ItemsControl>  
  
## <a name="see-also"></a>请参阅

- <xref:System.Xml.XmlElement>
- [数据绑定概述](../data/data-binding-overview.md)
- [样式设置和模板化](styling-and-templating.md)
- [使用 XMLDataProvider 和 XPath 查询绑定到 XML 数据](../data/how-to-bind-to-xml-data-using-an-xmldataprovider-and-xpath-queries.md)
- [ListView 概述](listview-overview.md)
