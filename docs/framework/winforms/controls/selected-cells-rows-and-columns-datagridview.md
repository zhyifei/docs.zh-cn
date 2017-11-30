---
title: "如何：获取 Windows 窗体 DataGridView 控件中选定的单元格、行和列"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- selection [Windows Forms], DataGridView control [Windows Forms]
- DataGridView control [Windows Forms], getting selection
- getting selection [Windows Forms], DataGridView control [Windows Forms]
ms.assetid: d93c4b5b-498e-49bc-982a-2229d61778e4
caps.latest.revision: "17"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: aada475af0ccac03dfa6ef9248b0fb07fd86b3ce
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-get-the-selected-cells-rows-and-columns-in-the-windows-forms-datagridview-control"></a>如何：获取 Windows 窗体 DataGridView 控件中选定的单元格、行和列
你可以获取选定的单元格、 行或列从<xref:System.Windows.Forms.DataGridView>通过使用相应的属性的控件： <xref:System.Windows.Forms.DataGridView.SelectedCells%2A>， <xref:System.Windows.Forms.DataGridView.SelectedRows%2A>，和<xref:System.Windows.Forms.DataGridView.SelectedColumns%2A>。 在下面的过程中，你将获取选定的单元格，并显示在其行和列索引<xref:System.Windows.Forms.MessageBox>。  
  
### <a name="to-get-the-selected-cells-in-a-datagridview-control"></a>若要获取 DataGridView 控件中选定的单元格  
  
-   使用 <xref:System.Windows.Forms.DataGridView.SelectedCells%2A> 属性。  
  
    > [!NOTE]
    >  使用<xref:System.Windows.Forms.DataGridView.AreAllCellsSelected%2A>方法，以避免只显示可能会极大量的单元格。  
  
     [!code-csharp[System.Windows.Forms.DataGridViewSelectedCollections#10](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewSelectedCollections/CS/DataGridViewSelectedCollections.cs#10)]
     [!code-vb[System.Windows.Forms.DataGridViewSelectedCollections#10](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewSelectedCollections/VB/DataGridViewSelectedCollections.vb#10)]  
  
### <a name="to-get-the-selected-rows-in-a-datagridview-control"></a>在 DataGridView 控件中获取所选的行  
  
-   使用 <xref:System.Windows.Forms.DataGridView.SelectedRows%2A> 属性。 若要使用户能够选择行，必须设置<xref:System.Windows.Forms.DataGridView.SelectionMode%2A>属性<xref:System.Windows.Forms.DataGridViewSelectionMode.FullRowSelect>或<xref:System.Windows.Forms.DataGridViewSelectionMode.RowHeaderSelect>。  
  
     [!code-csharp[System.Windows.Forms.DataGridViewSelectedCollections#20](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewSelectedCollections/CS/DataGridViewSelectedCollections.cs#20)]
     [!code-vb[System.Windows.Forms.DataGridViewSelectedCollections#20](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewSelectedCollections/VB/DataGridViewSelectedCollections.vb#20)]  
  
### <a name="to-get-the-selected-columns-in-a-datagridview-control"></a>在 DataGridView 控件中获取所选的列  
  
-   使用 <xref:System.Windows.Forms.DataGridView.SelectedColumns%2A> 属性。 若要使用户能够选择列，必须设置<xref:System.Windows.Forms.DataGridView.SelectionMode%2A>属性<xref:System.Windows.Forms.DataGridViewSelectionMode.FullColumnSelect>或<xref:System.Windows.Forms.DataGridViewSelectionMode.ColumnHeaderSelect>。  
  
     [!code-csharp[System.Windows.Forms.DataGridViewSelectedCollections#30](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewSelectedCollections/CS/DataGridViewSelectedCollections.cs#30)]
     [!code-vb[System.Windows.Forms.DataGridViewSelectedCollections#30](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewSelectedCollections/VB/DataGridViewSelectedCollections.vb#30)]  
  
## <a name="compiling-the-code"></a>编译代码  
 此示例需要：  
  
-   <xref:System.Windows.Forms.Button>控件名为`selectedCellsButton`， `selectedRowsButton`，和`selectedColumnsButton`，每个处理程序<xref:System.Windows.Forms.Control.Click>附加事件。  
  
-   名为 `dataGridView1` 的 <xref:System.Windows.Forms.DataGridView> 控件。  
  
-   对 <xref:System?displayProperty=nameWithType><xref:System.Windows.Forms?displayProperty=nameWithType> 和 <xref:System.Text?displayProperty=nameWithType> 程序集的引用。  
  
## <a name="robust-programming"></a>可靠编程  
 本主题中所述的集合时选择的单元格、 行或列的较大数字不高效地执行。 有关使用这些集合的大量数据的详细信息，请参阅[缩放 Windows 窗体 DataGridView 控件的最佳做法](../../../../docs/framework/winforms/controls/best-practices-for-scaling-the-windows-forms-datagridview-control.md)。  
  
## <a name="see-also"></a>另请参阅  
 <xref:System.Windows.Forms.DataGridView>  
 <xref:System.Windows.Forms.DataGridView.SelectionMode%2A>  
 <xref:System.Windows.Forms.DataGridView.AreAllCellsSelected%2A>  
 <xref:System.Windows.Forms.DataGridView.SelectedCells%2A>  
 <xref:System.Windows.Forms.DataGridView.SelectedRows%2A>  
 <xref:System.Windows.Forms.DataGridView.SelectedColumns%2A>  
 [将选择模式和剪贴板与 Windows 窗体 DataGridView 控件结合使用](../../../../docs/framework/winforms/controls/selection-and-clipboard-use-with-the-windows-forms-datagridview-control.md)
