---
title: 如何：为 Windows 窗体 DataGridView 控件中的单个单元格添加工具提示
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- tooltips [Windows Forms], adding to data grids
- DataGridView control [Windows Forms], adding tooltips
- data grids [Windows Forms], adding tooltips
ms.assetid: 2a81f9de-d58b-4ea8-bc0b-8d93c2f4cf78
ms.openlocfilehash: 50eb02a8f6e9a987fad074c173ab6711fa91143f
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-add-tooltips-to-individual-cells-in-a-windows-forms-datagridview-control"></a>如何：为 Windows 窗体 DataGridView 控件中的单个单元格添加工具提示
默认情况下，工具提示用于显示的值<xref:System.Windows.Forms.DataGridView>太小而无法显示其完整内容的单元格。 你可以重写此行为，但是，若要设置的各个单元格的工具提示文本值。 这很有用，可以显示用户有关的其他信息单元格或者向用户提供的单元格内容的备用说明。 例如，如果你有行显示状态图标，你可能想要提供使用工具提示的文本说明。  
  
 你可以通过设置来禁用单元格级别工具提示的显示<xref:System.Windows.Forms.DataGridView.ShowCellToolTips%2A?displayProperty=nameWithType>属性`false`。  
  
### <a name="to-add-a-tooltip-to-a-cell"></a>若要向单元格添加工具提示  
  
-   设置 <xref:System.Windows.Forms.DataGridViewCell.ToolTipText%2A?displayProperty=nameWithType> 属性。  
  
     [!code-cpp[System.Windows.Forms.DataGridViewCell.ToolTipText#1](../../../../samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewCell.ToolTipText/cpp/datagridviewcell.tooltiptext.cpp#1)]
     [!code-csharp[System.Windows.Forms.DataGridViewCell.ToolTipText#1](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewCell.ToolTipText/CS/datagridviewcell.tooltiptext.cs#1)]
     [!code-vb[System.Windows.Forms.DataGridViewCell.ToolTipText#1](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewCell.ToolTipText/VB/datagridviewcell.tooltiptext.vb#1)]  
  
## <a name="compiling-the-code"></a>编译代码  
  
-   此示例需要：  
  
-   A<xref:System.Windows.Forms.DataGridView>控件名为`dataGridView1`，其中包含一个名为列`Rating`用于显示字符串值的一到四个星号 ("*") 符号。 <xref:System.Windows.Forms.DataGridView.CellFormatting>的控件的事件必须与示例中所示的事件处理程序方法关联。  
  
-   对 <xref:System?displayProperty=nameWithType> 和 <xref:System.Windows.Forms?displayProperty=nameWithType> 程序集的引用。  
  
## <a name="robust-programming"></a>可靠编程  
 当绑定<xref:System.Windows.Forms.DataGridView>控件拖到外部数据源或通过实现虚拟模式提供您自己的数据源，你可能会遇到性能问题。 若要避免对性能产生负面影响，在处理大量数据时，处理<xref:System.Windows.Forms.DataGridView.CellToolTipTextNeeded>事件而不是设置<xref:System.Windows.Forms.DataGridViewCell.ToolTipText%2A>多个单元格的属性。 当你处理此事件，获取单元格的值<xref:System.Windows.Forms.DataGridViewCell.ToolTipText%2A>属性引发事件，并返回的值<xref:System.Windows.Forms.DataGridViewCellToolTipTextNeededEventArgs.ToolTipText%2A?displayProperty=nameWithType>属性作为指定在事件处理程序。  
  
## <a name="see-also"></a>请参阅  
 <xref:System.Windows.Forms.DataGridView>  
 <xref:System.Windows.Forms.DataGridView.ShowCellToolTips%2A?displayProperty=nameWithType>  
 <xref:System.Windows.Forms.DataGridView.CellToolTipTextNeeded?displayProperty=nameWithType>  
 <xref:System.Windows.Forms.DataGridViewCell>  
 <xref:System.Windows.Forms.DataGridViewCell.ToolTipText%2A?displayProperty=nameWithType>  
 [使用 Windows 窗体 DataGridView 控件中的单元格、行和列编程](../../../../docs/framework/winforms/controls/programming-with-cells-rows-and-columns-in-the-datagrid.md)
