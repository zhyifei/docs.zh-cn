---
title: 基于 DataGridView 控件中的更改执行自定义操作
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- cells [Windows Forms], detecting changes
- DataGridView control [Windows Forms], detecting changes in cells
- data grids [Windows Forms], detecting changes in cells
ms.assetid: 7fa44d01-97f4-4ccb-a149-bc72628d2c36
ms.openlocfilehash: a809134b0a79bc9685c5b84acce58b4c61b5c526
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/24/2020
ms.locfileid: "76744279"
---
# <a name="how-to-perform-a-custom-action-based-on-changes-in-a-cell-of-a-windows-forms-datagridview-control"></a>如何：根据 Windows 窗体 DataGridView 控件的单元格中的更改执行自定义操作
<xref:System.Windows.Forms.DataGridView> 控件有多个事件可用于检测 <xref:System.Windows.Forms.DataGridView> 单元格状态的更改。 最常使用的两种情况是 <xref:System.Windows.Forms.DataGridView.CellValueChanged> 和 <xref:System.Windows.Forms.DataGridView.CellStateChanged> 事件。  
  
### <a name="to-detect-changes-in-the-values-of-datagridview-cells"></a>检测 DataGridView 单元值的更改  
  
- 为 <xref:System.Windows.Forms.DataGridView.CellValueChanged> 事件编写处理程序。  
  
     [!code-csharp[System.Windows.Forms.DataGridViewMisc#130](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/CS/datagridviewmisc.cs#130)]
     [!code-vb[System.Windows.Forms.DataGridViewMisc#130](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/VB/datagridviewmisc.vb#130)]  
  
### <a name="to-detect-changes-in-the-states-of-datagridview-cells"></a>检测 DataGridView 单元格状态的更改  
  
- 为 <xref:System.Windows.Forms.DataGridView.CellStateChanged> 事件编写处理程序。  
  
     [!code-csharp[System.Windows.Forms.DataGridViewMisc#135](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/CS/datagridviewmisc.cs#135)]
     [!code-vb[System.Windows.Forms.DataGridViewMisc#135](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/VB/datagridviewmisc.vb#135)]  
  
## <a name="compiling-the-code"></a>编译代码  
 此示例需要：  
  
- 名为 <xref:System.Windows.Forms.DataGridView> 的 `dataGridView1` 控件。 对于C#，事件处理程序必须连接到相应的事件。  
  
- 对 <xref:System?displayProperty=nameWithType> 和 <xref:System.Windows.Forms?displayProperty=nameWithType> 程序集的引用。  
  
## <a name="see-also"></a>另请参阅

- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.DataGridView.CellValueChanged?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridView.CellStateChanged?displayProperty=nameWithType>
- [使用 Windows 窗体 DataGridView 控件中的单元格、行和列编程](programming-with-cells-rows-and-columns-in-the-datagrid.md)
- [演练：在 Windows 窗体 DataGridView 控件中验证数据](walkthrough-validating-data-in-the-windows-forms-datagridview-control.md)
