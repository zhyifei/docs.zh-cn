---
title: 创建未绑定的 DataGridView 控件
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- data [Windows Forms], displaying without binding to data source
- DataGridView control [Windows Forms], unbound data
- DataGridView control [Windows Forms], displaying data without binding to a data source
- data [Windows Forms], unbound
- walkthroughs [Windows Forms], DataGridView control
ms.assetid: 5a8d6afa-1b4b-4b24-8db8-501086ffdebe
ms.openlocfilehash: ceb75d4ee845d1f643d4d88d5a9f1bde73edcc70
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/24/2020
ms.locfileid: "76740172"
---
# <a name="walkthrough-creating-an-unbound-windows-forms-datagridview-control"></a>演练：创建未绑定的 Windows 窗体 DataGridView 控件
您可能经常希望显示不源自数据库的表格数据。 例如，你可能想要显示字符串的二维数组的内容。 <xref:System.Windows.Forms.DataGridView> 类提供一种简单而又高度可自定义的方法来显示数据，而不绑定到数据源。 本演练演示如何在 "未绑定" 模式下填充 <xref:System.Windows.Forms.DataGridView> 控件并管理行的添加和删除。 默认情况下，用户可以添加新行。 若要防止添加行，请将 <xref:System.Windows.Forms.DataGridView.AllowUserToAddRows%2A> 属性设置 `false`。  
  
 若要将本主题中的代码复制为单个列表，请参阅[如何：创建未绑定的 Windows 窗体 DataGridView 控件](how-to-create-an-unbound-windows-forms-datagridview-control.md)。  
  
## <a name="creating-the-form"></a>创建窗体  
  
#### <a name="to-use-an-unbound-datagridview-control"></a>使用未绑定的 DataGridView 控件  
  
1. 创建一个派生自 <xref:System.Windows.Forms.Form> 的类，其中包含以下变量声明和 `Main` 方法。  
  
     [!code-csharp[System.Windows.Forms.DataGridViewSimpleUnbound#01](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewSimpleUnbound/CS/simpleunbound.cs#01)]
     [!code-vb[System.Windows.Forms.DataGridViewSimpleUnbound#01](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewSimpleUnbound/VB/simpleunbound.vb#01)]  
    [!code-csharp[System.Windows.Forms.DataGridViewSimpleUnbound#02](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewSimpleUnbound/CS/simpleunbound.cs#02)]
    [!code-vb[System.Windows.Forms.DataGridViewSimpleUnbound#02](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewSimpleUnbound/VB/simpleunbound.vb#02)]  
  
2. 在窗体的类定义中实现 `SetupLayout` 方法，以设置窗体的布局。  
  
     [!code-csharp[System.Windows.Forms.DataGridViewSimpleUnbound#20](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewSimpleUnbound/CS/simpleunbound.cs#20)]
     [!code-vb[System.Windows.Forms.DataGridViewSimpleUnbound#20](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewSimpleUnbound/VB/simpleunbound.vb#20)]  
  
3. 创建 `SetupDataGridView` 方法以设置 <xref:System.Windows.Forms.DataGridView> 的列和属性。  
  
     此方法首先将 <xref:System.Windows.Forms.DataGridView> 控件添加到窗体的 <xref:System.Windows.Forms.Control.Controls%2A> 集合。 接下来，使用 <xref:System.Windows.Forms.DataGridView.ColumnCount%2A> 属性设置要显示的列数。 列标题的默认样式是通过设置 <xref:System.Windows.Forms.DataGridView.ColumnHeadersDefaultCellStyle%2A> 属性返回的 <xref:System.Windows.Forms.DataGridViewCellStyle> 的 <xref:System.Windows.Forms.DataGridViewCellStyle.BackColor%2A>、<xref:System.Windows.Forms.DataGridViewCellStyle.ForeColor%2A>和 <xref:System.Windows.Forms.DataGridViewCellStyle.Font%2A> 属性设置的。  
  
     设置布局和外观属性，然后分配列名称。 此方法退出时，<xref:System.Windows.Forms.DataGridView> 控件已准备好进行填充。  
  
     [!code-csharp[System.Windows.Forms.DataGridViewSimpleUnbound#30](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewSimpleUnbound/CS/simpleunbound.cs#30)]
     [!code-vb[System.Windows.Forms.DataGridViewSimpleUnbound#30](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewSimpleUnbound/VB/simpleunbound.vb#30)]  
  
4. 创建 `PopulateDataGridView` 方法以便向 <xref:System.Windows.Forms.DataGridView> 控件添加行。  
  
     每一行代表一首歌曲及其关联的信息。  
  
     [!code-csharp[System.Windows.Forms.DataGridViewSimpleUnbound#40](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewSimpleUnbound/CS/simpleunbound.cs#40)]
     [!code-vb[System.Windows.Forms.DataGridViewSimpleUnbound#40](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewSimpleUnbound/VB/simpleunbound.vb#40)]  
  
5. 在实用工具方法就绪后，可以附加事件处理程序。  
  
     您将处理 "**添加**" 和 "**删除**" 按钮的 <xref:System.Windows.Forms.Control.Click> 事件、窗体的 <xref:System.Windows.Forms.Form.Load> 事件和 <xref:System.Windows.Forms.DataGridView> 控件的 <xref:System.Windows.Forms.DataGridView.CellFormatting> 事件。  
  
     引发 "**添加**" 按钮的 <xref:System.Windows.Forms.Control.Click> 事件时，会向 <xref:System.Windows.Forms.DataGridView>中添加一个新的空白行。  
  
     引发 "**删除**" 按钮的 <xref:System.Windows.Forms.Control.Click> 事件时，将删除所选行，除非它是新记录的行，从而使用户能够添加新行。 此行始终是 <xref:System.Windows.Forms.DataGridView> 控件中的最后一行。  
  
     引发窗体的 <xref:System.Windows.Forms.Form.Load> 事件时，将调用 `SetupLayout`、`SetupDataGridView`和 `PopulateDataGridView` 实用工具方法。  
  
     引发 <xref:System.Windows.Forms.DataGridView.CellFormatting> 事件时，`Date` 列中的每个单元格的格式将设置为长日期，除非无法分析该单元的值。  
  
     [!code-csharp[System.Windows.Forms.DataGridViewSimpleUnbound#10](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewSimpleUnbound/CS/simpleunbound.cs#10)]
     [!code-vb[System.Windows.Forms.DataGridViewSimpleUnbound#10](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewSimpleUnbound/VB/simpleunbound.vb#10)]  
  
## <a name="testing-the-application"></a>测试应用程序  
 你现在可以对窗体进行测试，以确保它按预期方式运行。  
  
#### <a name="to-test-the-form"></a>测试窗体  
  
- 按“F5”运行应用程序。  
  
     你将看到一个 <xref:System.Windows.Forms.DataGridView> 控件，该控件显示 `PopulateDataGridView`中列出的歌曲。 您可以通过 "**添加行**" 按钮添加新行，并且可以通过 "**删除行**" 按钮删除所选行。 未绑定的 <xref:System.Windows.Forms.DataGridView> 控件是数据存储区，其数据独立于任何外部源，如 <xref:System.Data.DataSet> 或数组。  
  
## <a name="next-steps"></a>后续步骤  
 此应用程序可让你基本了解 <xref:System.Windows.Forms.DataGridView> 控件的功能。 可以通过多种方式自定义 <xref:System.Windows.Forms.DataGridView> 控件的外观和行为：  
  
- 更改边框和标题样式。 有关详细信息，请参阅[如何：更改 Windows 窗体 DataGridView 控件中的边框和网格线样式](change-the-border-and-gridline-styles-in-the-datagrid.md)。  
  
- 启用或限制 <xref:System.Windows.Forms.DataGridView> 控件的用户输入。 有关详细信息，请参阅[如何：防止在 Windows 窗体 Datagridview 控件中添加和删除行](prevent-row-addition-and-deletion-datagridview.md)以及[如何：在 Windows 窗体 DataGridView 控件中将列设为只读](how-to-make-columns-read-only-in-the-windows-forms-datagridview-control.md)。  
  
- 检查用户输入中的数据库相关错误。 有关详细信息，请参阅[演练：处理 Windows 窗体 DataGridView 控件中的数据输入过程中发生的错误](handling-errors-that-occur-during-data-entry-in-the-datagrid.md)。  
  
- 使用虚拟模式处理非常大的数据集。 有关详细信息，请参阅[演练：在 Windows 窗体 DataGridView 控件中实现虚拟模式](implementing-virtual-mode-wf-datagridview-control.md)。  
  
- 自定义单元格的外观。 有关详细信息，请参阅[如何：自定义 Windows 窗体 Datagridview 控件中单元格的外观](customize-the-appearance-of-cells-in-the-datagrid.md)和[如何：为 Windows 窗体 Datagridview 控件设置默认单元格样式](how-to-set-default-cell-styles-for-the-windows-forms-datagridview-control.md)。  
  
## <a name="see-also"></a>另请参阅

- <xref:System.Windows.Forms.DataGridView>
- [在 Windows 窗体 DataGridView 控件中显示数据](displaying-data-in-the-windows-forms-datagridview-control.md)
- [如何：创建未绑定 Windows 窗体 DataGridView 控件](how-to-create-an-unbound-windows-forms-datagridview-control.md)
- [Windows 窗体 DataGridView 控件中的数据显示模式](data-display-modes-in-the-windows-forms-datagridview-control.md)
