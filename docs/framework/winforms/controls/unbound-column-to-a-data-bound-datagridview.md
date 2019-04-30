---
title: 如何：将未绑定的列添加到已绑定数据的 Windows 窗体 DataGridView 控件
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- columns [Windows Forms], unbound data
- data grids [Windows Forms], adding unbound columns
- DataGridView control [Windows Forms], unbound data
ms.assetid: f7bdc4d8-ba8e-421b-ad62-82d936f01372
ms.openlocfilehash: 40308f7e8cc12dcff5b7d4393645f6a9007cc2b7
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "62009196"
---
# <a name="how-to-add-an-unbound-column-to-a-data-bound-windows-forms-datagridview-control"></a>如何：将未绑定的列添加到已绑定数据的 Windows 窗体 DataGridView 控件
在 <xref:System.Windows.Forms.DataGridView> 控件中显示的数据通常来自某种类型的数据源，但你可能需要显示并非来自该数据源的一列数据。 这种列称为未绑定列。 未绑定列可有多种形式。 它们常用于提供对数据行详细信息的访问。  
  
 下面的代码示例演示如何创建未绑定的列**详细信息**实现母版/详细信息方案时，与父表中的特定行相关按钮以显示子表。 若要响应按钮点击，请实现显示包含子表的窗体的 <xref:System.Windows.Forms.DataGridView.CellClick?displayProperty=nameWithType> 事件处理程序。  
  
 Visual Studio 中对此任务提供支持。  另请参阅[如何：添加和删除列在 Windows 窗体 DataGridView 控件使用设计器](add-and-remove-columns-in-the-datagrid-using-the-designer.md)。  
  
## <a name="example"></a>示例  
 [!code-csharp[System.Windows.Forms.DataGridViewMisc#010](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/CS/datagridviewmisc.cs#010)]
 [!code-vb[System.Windows.Forms.DataGridViewMisc#010](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/VB/datagridviewmisc.vb#010)]  
  
## <a name="compiling-the-code"></a>编译代码  
 此示例需要：  
  
- 名为 `dataGridView1` 的 <xref:System.Windows.Forms.DataGridView> 控件。  
  
- 对 <xref:System?displayProperty=nameWithType> 和 <xref:System.Windows.Forms?displayProperty=nameWithType> 程序集的引用。  
  
## <a name="see-also"></a>请参阅

- <xref:System.Windows.Forms.DataGridView>
- [在 Windows 窗体 DataGridView 控件中显示数据](displaying-data-in-the-windows-forms-datagridview-control.md)
- [Windows 窗体 DataGridView 控件中的数据显示模式](data-display-modes-in-the-windows-forms-datagridview-control.md)
