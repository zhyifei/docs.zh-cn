---
title: 演练：处理在 Windows 窗体 DataGridView 控件中输入数据时发生的错误
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- error handling [Windows Forms], dataGridView control
- data grids [Windows Forms], error handling
- DataGridView control [Windows Forms], error handling
- data entry [Windows Forms], error handling
- error handling [Windows Forms], data entry
- walkthroughs [Windows Forms], DataGridView control
ms.assetid: 30a68b85-d3af-4946-83c1-1e2d010d0511
ms.openlocfilehash: cee6fe3b049378fa7bbe2585a3607049eaf231bc
ms.sourcegitcommit: 581ab03291e91983459e56e40ea8d97b5189227e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/27/2019
ms.locfileid: "70046080"
---
# <a name="walkthrough-handling-errors-that-occur-during-data-entry-in-the-windows-forms-datagridview-control"></a>演练：处理在 Windows 窗体 DataGridView 控件中输入数据时发生的错误

处理基础数据存储区中的错误是数据输入应用程序所必需的功能。 <xref:System.Windows.Forms.DataGridView> 通过<xref:System.Windows.Forms.DataGridView.DataError>公开事件, Windows 窗体控件可以轻松地实现这一点, 在数据存储区检测到违反约束或违反业务规则时, 将引发此事件。

在本演练中, 您将从 Northwind 示例`Customers`数据库的表中检索行, 并将它们显示<xref:System.Windows.Forms.DataGridView>在控件中。 当在新`CustomerID`行或已编辑的现有行中检测到重复值时, <xref:System.Windows.Forms.DataGridView.DataError>将发生该事件, 将通过显示<xref:System.Windows.Forms.MessageBox>描述该异常的来处理该事件。

要将本主题中的代码作为单个列表进行复制，请参阅[如何：处理 Windows 窗体 DataGridView 控件](handle-errors-that-occur-during-data-entry-in-the-datagrid.md)中的数据输入过程中发生的错误。

## <a name="prerequisites"></a>系统必备

若要完成本演练，你将需要：

- 访问包含 Northwind SQL Server 示例数据库的服务器。

## <a name="creating-the-form"></a>创建窗体

#### <a name="to-handle-data-entry-errors-in-the-datagridview-control"></a>处理 DataGridView 控件中的数据输入错误

1. 创建一个派生自<xref:System.Windows.Forms.Form>的类, 并包含一个<xref:System.Windows.Forms.DataGridView>控件和<xref:System.Windows.Forms.BindingSource>一个组件。

    下面的代码示例提供了基本的`Main`初始化并包含方法。

    [!code-csharp[System.Windows.Forms.DataGridView.DataError#01](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.DataError/CS/errorhandling.cs#01)]
    [!code-vb[System.Windows.Forms.DataGridView.DataError#01](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.DataError/VB/errorhandling.vb#01)]
    [!code-csharp[System.Windows.Forms.DataGridView.DataError#02](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.DataError/CS/errorhandling.cs#02)]
    [!code-vb[System.Windows.Forms.DataGridView.DataError#02](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.DataError/VB/errorhandling.vb#02)]

2. 在窗体的类定义中实现一个方法, 用于处理连接到数据库的详细信息。

    此代码示例使用一个`GetData`方法, 该方法返回<xref:System.Data.DataTable>填充的对象。 请确保将`connectionString`变量设置为适合数据库的值。

    > [!IMPORTANT]
    > 将敏感信息（如密码）存储在连接字符串中可能会影响应用程序的安全性。 若要控制对数据库的访问，一种较为安全的方法是使用 Windows 身份验证（也称为集成安全性）。 有关详细信息，请参阅[保护连接信息](../../data/adonet/protecting-connection-information.md)。

    [!code-csharp[System.Windows.Forms.DataGridView.DataError#30](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.DataError/CS/errorhandling.cs#30)]
    [!code-vb[System.Windows.Forms.DataGridView.DataError#30](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.DataError/VB/errorhandling.vb#30)]

3. 实现窗体<xref:System.Windows.Forms.Form.Load>事件的处理程序, 该处理程序<xref:System.Windows.Forms.DataGridView>初始化<xref:System.Windows.Forms.BindingSource>和并设置数据绑定。

    [!code-csharp[System.Windows.Forms.DataGridView.DataError#10](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.DataError/CS/errorhandling.cs#10)]
    [!code-vb[System.Windows.Forms.DataGridView.DataError#10](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.DataError/VB/errorhandling.vb#10)]

4. 在上处理<xref:System.Windows.Forms.DataGridView.DataError>事件。 <xref:System.Windows.Forms.DataGridView>

    如果错误的上下文是提交操作, 请在中<xref:System.Windows.Forms.MessageBox>显示错误。

    [!code-csharp[System.Windows.Forms.DataGridView.DataError#20](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.DataError/CS/errorhandling.cs#20)]
    [!code-vb[System.Windows.Forms.DataGridView.DataError#20](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.DataError/VB/errorhandling.vb#20)]

## <a name="testing-the-application"></a>测试应用程序

你现在可以对窗体进行测试, 以确保它按预期方式运行。

#### <a name="to-test-the-form"></a>测试窗体

- 按 F5 运行该应用程序。

  您将看到一个<xref:System.Windows.Forms.DataGridView>用 Customers 表中的数据填充的控件。 如果为`CustomerID`输入重复值并提交编辑, 则单元值将自动还原, 并且你将看到一个<xref:System.Windows.Forms.MessageBox>显示数据输入错误的。

## <a name="next-steps"></a>后续步骤

此应用程序可让你对<xref:System.Windows.Forms.DataGridView>控件的功能有一个基本的了解。 可以通过多种方式自定义<xref:System.Windows.Forms.DataGridView>控件的外观和行为:

- 更改边框和标题样式。 有关详细信息，请参阅[如何：更改 Windows 窗体 DataGridView 控件](change-the-border-and-gridline-styles-in-the-datagrid.md)中的边框和网格线样式。

- 启用或限制控件的<xref:System.Windows.Forms.DataGridView>用户输入。 有关详细信息，请参阅[如何：禁止 Windows 窗体 DataGridView 控件](prevent-row-addition-and-deletion-datagridview.md)中添加和删除行, 以及[如何:在 Windows 窗体 DataGridView 控件](how-to-make-columns-read-only-in-the-windows-forms-datagridview-control.md)中将列设为只读。

- 验证控件的<xref:System.Windows.Forms.DataGridView>用户输入。 有关详细信息，请参见[演练：正在验证 Windows 窗体 DataGridView 控件](walkthrough-validating-data-in-the-windows-forms-datagridview-control.md)中的数据。

- 使用虚拟模式处理非常大的数据集。 有关详细信息，请参见[演练：在 Windows 窗体 DataGridView 控件](implementing-virtual-mode-wf-datagridview-control.md)中实现虚拟模式。

- 自定义单元格的外观。 有关详细信息，请参阅[如何：自定义 Windows 窗体 DataGridView 控件](customize-the-appearance-of-cells-in-the-datagrid.md)中单元格的外观, 以及[如何执行以下操作:设置 Windows 窗体 DataGridView 控件](how-to-set-default-cell-styles-for-the-windows-forms-datagridview-control.md)的默认单元格样式。

## <a name="see-also"></a>请参阅

- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.BindingSource>
- [Windows 窗体 DataGridView 控件中的数据输入](data-entry-in-the-windows-forms-datagridview-control.md)
- [如何：处理 Windows 窗体 DataGridView 控件中的数据输入过程中发生的错误](handle-errors-that-occur-during-data-entry-in-the-datagrid.md)
- [演练：验证 Windows 窗体 DataGridView 控件中的数据](walkthrough-validating-data-in-the-windows-forms-datagridview-control.md)
- [保护连接信息](../../data/adonet/protecting-connection-information.md)
