---
title: 自定义 DataGridView 控件中单元格的外观
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- data grids [Windows Forms], customizing cells
- DataGridView control [Windows Forms], customizing cells
- cells [Windows Forms], customizing in DataGridView control
ms.assetid: 478b20c9-625c-4116-9c5c-5a16e6f4ec67
ms.openlocfilehash: 754932427a365a7b032c1ac9627d3237d1f7d0c6
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/24/2020
ms.locfileid: "76744053"
---
# <a name="how-to-customize-the-appearance-of-cells-in-the-windows-forms-datagridview-control"></a>如何：自定义 Windows 窗体 DataGridView 控件中单元格的外观
您可以通过处理 <xref:System.Windows.Forms.DataGridView> 控件的 <xref:System.Windows.Forms.DataGridView.CellPainting> 事件来自定义任意单元格的外观。 可以从 <xref:System.Windows.Forms.DataGridViewCellPaintingEventArgs>的 <xref:System.Windows.Forms.DataGridViewCellPaintingEventArgs.Graphics%2A> 属性中提取 <xref:System.Windows.Forms.DataGridView> 控件的 <xref:System.Drawing.Graphics>。 利用这 <xref:System.Drawing.Graphics>，你可以影响整个 <xref:System.Windows.Forms.DataGridView> 控件的外观，但你通常只想影响当前正在绘制的单元格的外观。 <xref:System.Windows.Forms.DataGridViewCellPaintingEventArgs> 的 <xref:System.Windows.Forms.DataGridViewCellPaintingEventArgs.ClipBounds%2A> 属性使你能够将绘制操作限制为当前正在绘制的单元格。  
  
 在下面的代码示例中，你将使用 <xref:System.Windows.Forms.DataGridView> 控件的配色方案绘制 `ContactName` 列中的所有单元格。 每个单元格的文本内容都在 <xref:System.Drawing.Color.Crimson%2A>中进行绘制，并且嵌入矩形的颜色与 <xref:System.Windows.Forms.DataGridView> 控件的 <xref:System.Windows.Forms.DataGridView.GridColor%2A> 属性相同。  
  
## <a name="example"></a>示例  
 [!code-csharp[System.Windows.Forms.DataGridViewCellPainting#10](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewCellPainting/CS/form1.cs#10)]
 [!code-vb[System.Windows.Forms.DataGridViewCellPainting#10](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewCellPainting/VB/form1.vb#10)]  
  
## <a name="compiling-the-code"></a>编译代码  
 此示例需要：  
  
- 一个名为 `dataGridView1` 的 <xref:System.Windows.Forms.DataGridView> 控件，该控件具有一个 `ContactName` 列，如 Northwind 示例数据库的 Customers 表中的列。  
  
- 对 System、System.Windows.Forms 和 System.Drawing 程序集的引用。  
  
## <a name="see-also"></a>另请参阅

- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.DataGridView.CellPainting>
- [自定义 Windows 窗体 DataGridView 控件](customizing-the-windows-forms-datagridview-control.md)
