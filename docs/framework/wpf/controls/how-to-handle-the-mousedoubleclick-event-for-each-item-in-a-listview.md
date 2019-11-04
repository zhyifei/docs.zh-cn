---
title: 如何：处理 ListView 中每一项的 MouseDoubleClick 事件
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- ListView controls [WPF], MouseDoubleClick event
ms.assetid: 81b39369-655a-4585-ac58-4640e5bb8fed
ms.openlocfilehash: 25308ee87fb387787e20c8a8887ae8e4e60742b9
ms.sourcegitcommit: 944ddc52b7f2632f30c668815f92b378efd38eea
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/03/2019
ms.locfileid: "73460228"
---
# <a name="how-to-handle-the-mousedoubleclick-event-for-each-item-in-a-listview"></a>如何：处理 ListView 中每一项的 MouseDoubleClick 事件
若要处理 <xref:System.Windows.Controls.ListView>中某个项的事件，需要向每个 <xref:System.Windows.Controls.ListViewItem>添加一个事件处理程序。 将 <xref:System.Windows.Controls.ListView> 绑定到数据源时，不会显式创建 <xref:System.Windows.Controls.ListViewItem>，但可以通过将 <xref:System.Windows.EventSetter> 添加到 <xref:System.Windows.Controls.ListViewItem>样式来处理每个项的事件。  
  
## <a name="example"></a>示例  
 下面的示例创建一个数据绑定 <xref:System.Windows.Controls.ListView>，并创建 <xref:System.Windows.Style>，以将事件处理程序添加到每个 <xref:System.Windows.Controls.ListViewItem>。  
  
 [!code-xaml[ListViewHowTos#1](~/samples/snippets/csharp/VS_Snippets_Wpf/ListViewHowTos/CSharp/Window1.xaml#1)]  
[!code-xaml[ListViewHowTos#5](~/samples/snippets/csharp/VS_Snippets_Wpf/ListViewHowTos/CSharp/Window1.xaml#5)]  
[!code-xaml[ListViewHowTos#2](~/samples/snippets/csharp/VS_Snippets_Wpf/ListViewHowTos/CSharp/Window1.xaml#2)]  
  
 下面的示例处理 <xref:System.Windows.Controls.Control.MouseDoubleClick> 事件。  
  
 [!code-csharp[ListViewHowTos#6](~/samples/snippets/csharp/VS_Snippets_Wpf/ListViewHowTos/CSharp/Window1.xaml.cs#6)]
 [!code-vb[ListViewHowTos#6](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ListViewHowTos/VisualBasic/Window1.xaml.vb#6)]  
  
> [!NOTE]
> 虽然将 <xref:System.Windows.Controls.ListView> 绑定到数据源最常见，但你可以使用样式将事件处理程序添加到非数据绑定 <xref:System.Windows.Controls.ListView> 中的每个 <xref:System.Windows.Controls.ListViewItem>，无论你是否显式创建 <xref:System.Windows.Controls.ListViewItem>。  有关显式和隐式创建 <xref:System.Windows.Controls.ListViewItem> 控件的详细信息，请参阅 <xref:System.Windows.Controls.ItemsControl>。  
  
## <a name="see-also"></a>请参阅

- <xref:System.Xml.XmlElement>
- [数据绑定概述](../data/data-binding-overview.md)
- [样式设置和模板化](../../../desktop-wpf/fundamentals/styles-templates-overview.md)
- [使用 XMLDataProvider 和 XPath 查询绑定到 XML 数据](../data/how-to-bind-to-xml-data-using-an-xmldataprovider-and-xpath-queries.md)
- [ListView 概述](listview-overview.md)
