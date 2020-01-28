---
title: 向 DataGridView 控件中的各个单元格添加工具提示
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
ms.openlocfilehash: ac86db5fa27a95adb20888cd59b5e236941d9177
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/24/2020
ms.locfileid: "76732176"
---
# <a name="how-to-add-tooltips-to-individual-cells-in-a-windows-forms-datagridview-control"></a>如何：为 Windows 窗体 DataGridView 控件中的单个单元格添加工具提示
默认情况下，工具提示用于显示 <xref:System.Windows.Forms.DataGridView> 的单元格的值，这些值太小而无法显示其全部内容。 不过，您可以重写此行为，以便为个别单元格设置工具提示文本值。 这对于向用户显示有关单元的其他信息或向用户提供单元内容的替代说明非常有用。 例如，如果有一个显示状态图标的行，则可能需要使用工具提示提供文本说明。  
  
 还可以通过将 <xref:System.Windows.Forms.DataGridView.ShowCellToolTips%2A?displayProperty=nameWithType> 属性设置为 `false`来禁用单元格级工具提示的显示。  
  
### <a name="to-add-a-tooltip-to-a-cell"></a>向单元格添加工具提示  
  
- 设置 <xref:System.Windows.Forms.DataGridViewCell.ToolTipText%2A?displayProperty=nameWithType> 属性。  
  
     [!code-cpp[System.Windows.Forms.DataGridViewCell.ToolTipText#1](~/samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewCell.ToolTipText/cpp/datagridviewcell.tooltiptext.cpp#1)]
     [!code-csharp[System.Windows.Forms.DataGridViewCell.ToolTipText#1](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewCell.ToolTipText/CS/datagridviewcell.tooltiptext.cs#1)]
     [!code-vb[System.Windows.Forms.DataGridViewCell.ToolTipText#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewCell.ToolTipText/VB/datagridviewcell.tooltiptext.vb#1)]  
  
## <a name="compiling-the-code"></a>编译代码  
  
- 此示例需要：  
  
- 名为 `dataGridView1` 的 <xref:System.Windows.Forms.DataGridView> 控件，其中包含一个名为 `Rating` 的列，用于显示一到四个星号（"*"）符号的字符串值。 控件的 <xref:System.Windows.Forms.DataGridView.CellFormatting> 事件必须与此示例中所示的事件处理程序方法相关联。  
  
- 对 <xref:System?displayProperty=nameWithType> 和 <xref:System.Windows.Forms?displayProperty=nameWithType> 程序集的引用。  
  
## <a name="robust-programming"></a>可靠的编程  
 将 <xref:System.Windows.Forms.DataGridView> 控件绑定到外部数据源或通过实现虚拟模式提供自己的数据源时，可能会遇到性能问题。 若要避免在处理大量数据时出现性能损失，请处理 <xref:System.Windows.Forms.DataGridView.CellToolTipTextNeeded> 事件，而不是设置多个单元格的 <xref:System.Windows.Forms.DataGridViewCell.ToolTipText%2A> 属性。 处理此事件时，获取单元 <xref:System.Windows.Forms.DataGridViewCell.ToolTipText%2A> 属性的值将引发事件，并返回事件处理程序中指定的 <xref:System.Windows.Forms.DataGridViewCellToolTipTextNeededEventArgs.ToolTipText%2A?displayProperty=nameWithType> 属性的值。  
  
## <a name="see-also"></a>另请参阅

- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.DataGridView.ShowCellToolTips%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridView.CellToolTipTextNeeded?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridViewCell>
- <xref:System.Windows.Forms.DataGridViewCell.ToolTipText%2A?displayProperty=nameWithType>
- [使用 Windows 窗体 DataGridView 控件中的单元格、行和列编程](programming-with-cells-rows-and-columns-in-the-datagrid.md)
