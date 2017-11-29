---
title: "如何：使用 GridSplitter 调整列的大小"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- grid columns [WPF], resizing
- GridSplitter control [WPF], resizing grid columns
- resizing grid columns [WPF]
ms.assetid: 47b20fe6-7adc-4aa6-9693-b4e184eef74b
caps.latest.revision: "13"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 5c8299a3f4885618601c8087a61c21dc5d989813
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-resize-columns-with-a-gridsplitter"></a>如何：使用 GridSplitter 调整列的大小
此示例演示如何创建垂直<xref:System.Windows.Controls.GridSplitter>以便重新分发中的两列之间的空间<xref:System.Windows.Controls.Grid>而无需更改的维度<xref:System.Windows.Controls.Grid>。  
  
## <a name="example"></a>示例  
 **如何创建覆盖列边缘的 GridSplitter**  
  
 若要指定<xref:System.Windows.Controls.GridSplitter>中的相邻列的大小进行调整<xref:System.Windows.Controls.Grid>，将其设置<xref:System.Windows.Controls.Grid.Column%2A>附加到一个要调整大小的列的属性。 如果你<xref:System.Windows.Controls.Grid>有多个对应的一行，设置<xref:System.Windows.Controls.Grid.RowSpan%2A>附加属性写入的行数。 然后设置<xref:System.Windows.FrameworkElement.HorizontalAlignment%2A>属性<xref:System.Windows.HorizontalAlignment.Left>或<xref:System.Windows.HorizontalAlignment.Right>（你设置的对齐方式取决于你想要调整大小的两个列）。 最后，设置<xref:System.Windows.FrameworkElement.VerticalAlignment%2A>属性<xref:System.Windows.VerticalAlignment.Stretch>。  
  
 [!code-xaml[GridSplitterRowColumn#GridSplitterColumnOverlay](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GridSplitterRowColumn/CS/Window1.xaml#gridsplittercolumnoverlay)]  
  
 A<xref:System.Windows.Controls.GridSplitter>不具有其各自的列中的其他控件可能被遮盖<xref:System.Windows.Controls.Grid>。 有关如何避免此问题的详细信息，请参阅[确保 GridSplitter 可见](../../../../docs/framework/wpf/controls/how-to-make-sure-that-a-gridsplitter-is-visible.md)。  
  
 **如何创建占据一列的 GridSplitter**  
  
 若要指定<xref:System.Windows.Controls.GridSplitter>占用中的列<xref:System.Windows.Controls.Grid>，将其设置<xref:System.Windows.Controls.Grid.Column%2A>附加到一个要调整大小的列的属性。 如果你网格包含多个行，请设置<xref:System.Windows.Controls.Grid.RowSpan%2A>附加属性写入的行数。 然后设置<xref:System.Windows.FrameworkElement.HorizontalAlignment%2A>到<xref:System.Windows.HorizontalAlignment.Center>，将其设置<xref:System.Windows.FrameworkElement.VerticalAlignment%2A>属性<xref:System.Windows.VerticalAlignment.Stretch>，并设置<xref:System.Windows.Controls.ColumnDefinition.Width%2A>包含的列的<xref:System.Windows.Controls.GridSplitter>到<xref:System.Windows.GridLength.Auto%2A>。  
  
 下面的示例演示如何定义垂直<xref:System.Windows.Controls.GridSplitter>，中占据一列和调整它的任何一侧列的大小。  
  
 [!code-xaml[GridSplitterRowColumn#GridSplitterEntireColumnPart1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GridSplitterRowColumn/CS/Window1.xaml#gridsplitterentirecolumnpart1)]  
[!code-xaml[GridSplitterRowColumn#GridSplitterEntireColumnPart2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GridSplitterRowColumn/CS/Window1.xaml#gridsplitterentirecolumnpart2)]  
  
## <a name="see-also"></a>另请参阅  
 <xref:System.Windows.Controls.GridSplitter>  
 [操作说明主题](../../../../docs/framework/wpf/controls/gridsplitter-how-to-topics.md)
