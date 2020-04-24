---
title: 如何：处理 ListView 中每一项的 MouseDoubleClick 事件
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- ListView controls [WPF], MouseDoubleClick event
ms.assetid: 81b39369-655a-4585-ac58-4640e5bb8fed
ms.openlocfilehash: 7bbc7bad36b3b1f2c92065e5f5699e5a86ac6189
ms.sourcegitcommit: 62285ec11fa8e8424bab00511a90760c60e63c95
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/20/2020
ms.locfileid: "81646111"
---
# <a name="how-to-handle-the-mousedoubleclick-event-for-each-item-in-a-listview"></a>如何：处理 ListView 中每一项的 MouseDoubleClick 事件
要处理 中的项的事件<xref:System.Windows.Controls.ListView>，需要向每个<xref:System.Windows.Controls.ListViewItem>添加事件处理程序。 <xref:System.Windows.Controls.ListView>当 绑定到数据源时，不会显式创建 ，<xref:System.Windows.Controls.ListViewItem>但可以通过将 项<xref:System.Windows.EventSetter>添加到<xref:System.Windows.Controls.ListViewItem>的样式来处理每个项的事件。  
  
## <a name="example"></a>示例  
 下面的示例创建一个数据绑定<xref:System.Windows.Controls.ListView>，并创建<xref:System.Windows.Style>一个来向每个<xref:System.Windows.Controls.ListViewItem>添加事件处理程序。  
  
 [!code-xaml[ListViewHowTos#1](~/samples/snippets/csharp/VS_Snippets_Wpf/ListViewHowTos/CSharp/Window1.xaml#1)]  
[!code-xaml[ListViewHowTos#5](~/samples/snippets/csharp/VS_Snippets_Wpf/ListViewHowTos/CSharp/Window1.xaml#5)]  
[!code-xaml[ListViewHowTos#2](~/samples/snippets/csharp/VS_Snippets_Wpf/ListViewHowTos/CSharp/Window1.xaml#2)]  
  
 下面的示例处理该<xref:System.Windows.Controls.Control.MouseDoubleClick>事件。  
  
 [!code-csharp[ListViewHowTos#6](~/samples/snippets/csharp/VS_Snippets_Wpf/ListViewHowTos/CSharp/Window1.xaml.cs#6)]
 [!code-vb[ListViewHowTos#6](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ListViewHowTos/VisualBasic/Window1.xaml.vb#6)]  
  
> [!NOTE]
> 尽管<xref:System.Windows.Controls.ListView>将 绑定到数据源是最常见的，但可以使用样式将事件处理程序添加到非数据绑定<xref:System.Windows.Controls.ListViewItem><xref:System.Windows.Controls.ListView>中的每个对象，而不管是否显式创建 。 <xref:System.Windows.Controls.ListViewItem>  有关显式和隐式创建的<xref:System.Windows.Controls.ListViewItem>控件的详细信息，请参阅。 <xref:System.Windows.Controls.ItemsControl>  
  
## <a name="see-also"></a>另请参阅

- <xref:System.Xml.XmlElement>
- [数据绑定概述](../../../desktop-wpf/data/data-binding-overview.md)
- [样式设置和模板化](../../../desktop-wpf/fundamentals/styles-templates-overview.md)
- [使用 XML 数据提供程序和 XPath 查询绑定到 XML 数据](../data/how-to-bind-to-xml-data-using-an-xmldataprovider-and-xpath-queries.md)
- [ListView 概述](listview-overview.md)
