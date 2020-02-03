---
title: 使用行模板自定义 DataGridView 控件中的行
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- data grids [Windows Forms], customizing rows
- DataGridView control [Windows Forms], customizing rows
ms.assetid: 6db61607-7e57-4a84-8d63-9d6a7ed7f9ff
ms.openlocfilehash: 35cb95f22c0caa654bf149b5fc4fd0395696a411
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/24/2020
ms.locfileid: "76728382"
---
# <a name="how-to-use-the-row-template-to-customize-rows-in-the-windows-forms-datagridview-control"></a>如何：使用行模板自定义 Windows 窗体 DataGridView 控件中的行
<xref:System.Windows.Forms.DataGridView> 控件将行模板用作通过数据绑定添加到控件的所有行的基础，或在未指定要使用的现有行的情况下调用 <xref:System.Windows.Forms.DataGridViewRowCollection.Add%2A?displayProperty=nameWithType> 方法。  
  
 行模板使您可以更好地控制行的外观和行为，而不是 <xref:System.Windows.Forms.DataGridView.RowsDefaultCellStyle%2A> 属性提供的。 利用行模板，可以设置任何 <xref:System.Windows.Forms.DataGridViewRow> 属性，包括 <xref:System.Windows.Forms.DataGridViewRow.DefaultCellStyle%2A>。  
  
 在某些情况下，您必须使用行模板来实现特定的效果。 例如，行高信息无法存储在 <xref:System.Windows.Forms.DataGridViewCellStyle>中，因此您必须使用行模板来更改所有行使用的默认高度。 当您创建自己的派生自 <xref:System.Windows.Forms.DataGridViewRow> 的类，并且您希望在将新行添加到控件时使用您的自定义类型时，行模板也很有用。  
  
> [!NOTE]
> 行模板仅在添加行时使用。 不能通过更改行模板来更改现有行。  
  
### <a name="to-use-the-row-template"></a>使用行模板  
  
- 设置从 <xref:System.Windows.Forms.DataGridView.RowTemplate%2A?displayProperty=nameWithType> 属性检索的对象的属性。  
  
     [!code-cpp[System.Windows.Forms.DataGridView.RowTemplate#1](~/samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.RowTemplate/CPP/datagridviewrowtemplate.cpp#1)]
     [!code-csharp[System.Windows.Forms.DataGridView.RowTemplate#1](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.RowTemplate/CS/datagridviewrowtemplate.cs#1)]
     [!code-vb[System.Windows.Forms.DataGridView.RowTemplate#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.RowTemplate/VB/datagridviewrowtemplate.vb#1)]  
  
## <a name="compiling-the-code"></a>编译代码  
 此示例需要：  
  
- 名为 <xref:System.Windows.Forms.DataGridView> 的 `dataGridView1` 控件。  
  
- 对 <xref:System?displayProperty=nameWithType><xref:System.Drawing?displayProperty=nameWithType> 和 <xref:System.Windows.Forms?displayProperty=nameWithType> 程序集的引用。  
  
## <a name="see-also"></a>另请参阅

- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.DataGridViewCellStyle>
- <xref:System.Windows.Forms.DataGridViewRow>
- <xref:System.Windows.Forms.DataGridView.RowTemplate%2A?displayProperty=nameWithType>
- [Windows 窗体 DataGridView 控件中的基本格式和样式设置](basic-formatting-and-styling-in-the-windows-forms-datagridview-control.md)
- [Windows 窗体 DataGridView 控件中的单元格样式](cell-styles-in-the-windows-forms-datagridview-control.md)
