---
title: 如何：自定义 Windows 窗体 DataGridView 控件中单元格的外观
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- data grids [Windows Forms], customizing cells
- DataGridView control [Windows Forms], customizing cells
- cells [Windows Forms], customizing in DataGridView control
ms.assetid: 478b20c9-625c-4116-9c5c-5a16e6f4ec67
ms.openlocfilehash: 9b07c139689a9776f6f901c0f9fbe9d2d0303d56
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "64648150"
---
# <a name="how-to-customize-the-appearance-of-cells-in-the-windows-forms-datagridview-control"></a>如何：自定义 Windows 窗体 DataGridView 控件中单元格的外观
您可以通过处理自定义的任意单元格的外观<xref:System.Windows.Forms.DataGridView>控件的<xref:System.Windows.Forms.DataGridView.CellPainting>事件。 你可以提取<xref:System.Windows.Forms.DataGridView>控件的<xref:System.Drawing.Graphics>从<xref:System.Windows.Forms.DataGridViewCellPaintingEventArgs.Graphics%2A>属性的<xref:System.Windows.Forms.DataGridViewCellPaintingEventArgs>。 与此<xref:System.Drawing.Graphics>，可能会影响整个外观<xref:System.Windows.Forms.DataGridView>控件，但你通常会想要产生效果仅为当前正在绘制的单元格的外观。 <xref:System.Windows.Forms.DataGridViewCellPaintingEventArgs.ClipBounds%2A>属性的<xref:System.Windows.Forms.DataGridViewCellPaintingEventArgs>使您能够限制您对当前正在绘制的单元格的绘制操作。  
  
 在下面的代码示例中，将绘制中的所有单元格`ContactName`列使用<xref:System.Windows.Forms.DataGridView>控件的配色方案。 在绘制每个单元格的文本内容<xref:System.Drawing.Color.Crimson%2A>，并与相同的颜色绘制一个内嵌的矩形<xref:System.Windows.Forms.DataGridView>控件的<xref:System.Windows.Forms.DataGridView.GridColor%2A>属性。  
  
## <a name="example"></a>示例  
 [!code-csharp[System.Windows.Forms.DataGridViewCellPainting#10](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewCellPainting/CS/form1.cs#10)]
 [!code-vb[System.Windows.Forms.DataGridViewCellPainting#10](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewCellPainting/VB/form1.vb#10)]  
  
## <a name="compiling-the-code"></a>编译代码  
 此示例需要：  
  
- 一个<xref:System.Windows.Forms.DataGridView>名为控件`dataGridView1`与`ContactName`如 Northwind 示例数据库中的 Customers 表中的列。  
  
- 对 System、System.Windows.Forms 和 System.Drawing 程序集的引用。  
  
## <a name="see-also"></a>请参阅

- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.DataGridView.CellPainting>
- [自定义 Windows 窗体 DataGridView 控件](customizing-the-windows-forms-datagridview-control.md)
