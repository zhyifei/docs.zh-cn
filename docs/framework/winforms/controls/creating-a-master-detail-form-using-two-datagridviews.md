---
title: 演练：使用两个 DataGridView 控件创建主/详细信息窗体
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- DataGridView control [Windows Forms], master/detail form
- parent-child tables [Windows Forms], displaying on Windows Forms
- master-details lists [Windows Forms], displaying on Windows Forms
- walkthroughs [Windows Forms], DataGridView control
ms.assetid: c5fa29e8-47f7-4691-829b-0e697a691f36
ms.openlocfilehash: bb3da36430c7493b941f3711cb584b4517d5bd54
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/24/2020
ms.locfileid: "76740579"
---
# <a name="walkthrough-creating-a-masterdetail-form-using-two-windows-forms-datagridview-controls"></a>演练：使用两个 Windows 窗体 DataGridView 控件创建一个主/从窗体

使用 <xref:System.Windows.Forms.DataGridView> 控件最常见的方案之一是*主/详细信息*窗体，在该窗体中显示两个数据库表之间的父/子关系。 如果选择主表中的行，则会将详细信息表更新为相应的子数据。

通过使用 <xref:System.Windows.Forms.DataGridView> 控件与 <xref:System.Windows.Forms.BindingSource> 组件之间的交互，实现主/详细信息窗体非常简单。 在本演练中，您将使用两个 <xref:System.Windows.Forms.DataGridView> 控件和两个 <xref:System.Windows.Forms.BindingSource> 组件生成窗体。 窗体将在 Northwind SQL Server 示例数据库中显示两个相关的表： `Customers` 和 `Orders`。 完成后，您将获得一个窗体，其中显示了 master <xref:System.Windows.Forms.DataGridView> 中数据库中的所有客户以及详细信息 <xref:System.Windows.Forms.DataGridView>中所选客户的所有订单。

若要将本主题中的代码复制为单个列表，请参阅[如何：使用两个 Windows 窗体 DataGridView 控件创建主窗体/详细信息窗体](create-a-master-detail-form-using-two-datagridviews.md)。

## <a name="prerequisites"></a>先决条件

为了完成本演练，您需要：

- 访问包含 Northwind SQL Server 示例数据库的服务器。

## <a name="creating-the-form"></a>创建窗体

#### <a name="to-create-a-masterdetail-form"></a>创建主窗体/详细信息窗体

1. 创建一个派生自 <xref:System.Windows.Forms.Form> 的类，其中包含两个 <xref:System.Windows.Forms.DataGridView> 控件和两个 <xref:System.Windows.Forms.BindingSource> 组件。 下面的代码提供基本的窗体初始化并包括 `Main` 方法。 如果你使用 Visual Studio 设计器来创建窗体，则可以使用设计器生成的代码而不是此代码，但请务必使用此处的变量声明中显示的名称。

    [!code-csharp[System.Windows.Forms.DataGridViewMasterDetails#01](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMasterDetails/CS/masterdetails.cs#01)]
    [!code-vb[System.Windows.Forms.DataGridViewMasterDetails#01](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMasterDetails/VB/masterdetails.vb#01)]
    [!code-csharp[System.Windows.Forms.DataGridViewMasterDetails#02](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMasterDetails/CS/masterdetails.cs#02)]
    [!code-vb[System.Windows.Forms.DataGridViewMasterDetails#02](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMasterDetails/VB/masterdetails.vb#02)]

2. 在窗体的类定义中实现一个方法，用于处理连接到数据库的详细信息。 此示例使用 `GetData` 方法，该方法填充 <xref:System.Data.DataSet> 对象，将 <xref:System.Data.DataRelation> 对象添加到数据集，并绑定 <xref:System.Windows.Forms.BindingSource> 组件。 请确保将 `connectionString` 变量设置为适合数据库的值。

    > [!IMPORTANT]
    > 将敏感信息（如密码）存储在连接字符串中可能会影响应用程序的安全性。 若要控制对数据库的访问，一种较为安全的方法是使用 Windows 身份验证（也称为集成安全性）。 有关详细信息，请参阅[保护连接信息](../../data/adonet/protecting-connection-information.md)。

    [!code-csharp[System.Windows.Forms.DataGridViewMasterDetails#20](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMasterDetails/CS/masterdetails.cs#20)]
    [!code-vb[System.Windows.Forms.DataGridViewMasterDetails#20](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMasterDetails/VB/masterdetails.vb#20)]

3. 为窗体的 <xref:System.Windows.Forms.Form.Load> 事件实现一个处理程序，该事件将 <xref:System.Windows.Forms.DataGridView> 控件绑定到 <xref:System.Windows.Forms.BindingSource> 组件并调用 `GetData` 方法。 下面的示例包含用于调整 <xref:System.Windows.Forms.DataGridView> 列的大小以适合显示的数据的代码。

    [!code-csharp[System.Windows.Forms.DataGridViewMasterDetails#10](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMasterDetails/CS/masterdetails.cs#10)]
    [!code-vb[System.Windows.Forms.DataGridViewMasterDetails#10](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMasterDetails/VB/masterdetails.vb#10)]

## <a name="testing-the-application"></a>测试应用程序

你现在可以对窗体进行测试，以确保它按预期方式运行。

#### <a name="to-test-the-form"></a>测试窗体

- 编译并运行该应用程序。

  你将看到两个 <xref:System.Windows.Forms.DataGridView> 控件，一个在另一个。 在顶部是 Northwind `Customers` 表中的客户，底部是对应于所选客户的 `Orders`。 当您在上面 <xref:System.Windows.Forms.DataGridView>中选择不同行时，<xref:System.Windows.Forms.DataGridView> 的内容会相应地发生更改。

## <a name="next-steps"></a>后续步骤

此应用程序可让你基本了解 <xref:System.Windows.Forms.DataGridView> 控件的功能。 可以通过多种方式自定义 <xref:System.Windows.Forms.DataGridView> 控件的外观和行为：

- 更改边框和标题样式。 有关详细信息，请参阅[如何：更改 Windows 窗体 DataGridView 控件中的边框和网格线样式](change-the-border-and-gridline-styles-in-the-datagrid.md)。

- 启用或限制 <xref:System.Windows.Forms.DataGridView> 控件的用户输入。 有关详细信息，请参阅[如何：防止在 Windows 窗体 Datagridview 控件中添加和删除行](prevent-row-addition-and-deletion-datagridview.md)以及[如何：在 Windows 窗体 DataGridView 控件中将列设为只读](how-to-make-columns-read-only-in-the-windows-forms-datagridview-control.md)。

- 验证 <xref:System.Windows.Forms.DataGridView> 控件的用户输入。 有关详细信息，请参阅[演练：验证 Windows 窗体 DataGridView 控件中的数据](walkthrough-validating-data-in-the-windows-forms-datagridview-control.md)。

- 使用虚拟模式处理非常大的数据集。 有关详细信息，请参阅[演练：在 Windows 窗体 DataGridView 控件中实现虚拟模式](implementing-virtual-mode-wf-datagridview-control.md)。

- 自定义单元格的外观。 有关详细信息，请参阅[如何：自定义 Windows 窗体 Datagridview 控件中单元格的外观](customize-the-appearance-of-cells-in-the-datagrid.md)和[如何：为 Windows 窗体 Datagridview 控件设置默认单元格样式](how-to-set-default-cell-styles-for-the-windows-forms-datagridview-control.md)。

## <a name="see-also"></a>另请参阅

- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.BindingSource>
- [在 Windows 窗体 DataGridView 控件中显示数据](displaying-data-in-the-windows-forms-datagridview-control.md)
- [如何：使用两个 Windows 窗体 DataGridView 控件创建主窗体/详细信息窗体](create-a-master-detail-form-using-two-datagridviews.md)
- [保护连接信息](../../data/adonet/protecting-connection-information.md)
