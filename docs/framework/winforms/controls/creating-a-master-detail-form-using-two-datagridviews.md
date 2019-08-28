---
title: 演练：使用两个 Windows 窗体 DataGridView 控件创建主-详细信息窗体
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
ms.openlocfilehash: 4212c7223aca6a5e7de3189d5f6b2757453cc438
ms.sourcegitcommit: 581ab03291e91983459e56e40ea8d97b5189227e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/27/2019
ms.locfileid: "70046094"
---
# <a name="walkthrough-creating-a-masterdetail-form-using-two-windows-forms-datagridview-controls"></a>演练：使用两个 Windows 窗体 DataGridView 控件创建一个主/详细信息窗体

使用<xref:System.Windows.Forms.DataGridView>控件的最常见方案之一是*主/详细信息*窗体, 其中显示两个数据库表之间的父/子关系。 如果选择主表中的行, 则会将详细信息表更新为相应的子数据。

使用<xref:System.Windows.Forms.DataGridView> 控件<xref:System.Windows.Forms.BindingSource>和组件之间的交互可以轻松实现主/详细信息窗体。 在本演练中, 您将使用两个<xref:System.Windows.Forms.DataGridView>控件和两个<xref:System.Windows.Forms.BindingSource>组件生成窗体。 此窗体将在 Northwind SQL Server 示例数据库中显示两个相关`Customers`的`Orders`表: 和。 完成后, 您将获得一个窗体, 其中显示了主<xref:System.Windows.Forms.DataGridView>数据库中的所有客户以及所选客户在详细信息<xref:System.Windows.Forms.DataGridView>中的所有订单。

要将本主题中的代码作为单个列表进行复制，请参阅[如何：使用两个 Windows 窗体 DataGridView 控件](create-a-master-detail-form-using-two-datagridviews.md)创建主窗体/详细信息窗体。

## <a name="prerequisites"></a>系统必备

若要完成本演练，你将需要：

- 访问包含 Northwind SQL Server 示例数据库的服务器。

## <a name="creating-the-form"></a>创建窗体

#### <a name="to-create-a-masterdetail-form"></a>创建主窗体/详细信息窗体

1. 创建一个从派生的<xref:System.Windows.Forms.Form>类, 其中包含两个<xref:System.Windows.Forms.DataGridView>控件<xref:System.Windows.Forms.BindingSource>和两个组件。 下面的代码提供基本的窗体初始化并`Main`包含方法。 如果你使用 Visual Studio 设计器来创建窗体, 则可以使用设计器生成的代码而不是此代码, 但请务必使用此处的变量声明中显示的名称。

    [!code-csharp[System.Windows.Forms.DataGridViewMasterDetails#01](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMasterDetails/CS/masterdetails.cs#01)]
    [!code-vb[System.Windows.Forms.DataGridViewMasterDetails#01](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMasterDetails/VB/masterdetails.vb#01)]
    [!code-csharp[System.Windows.Forms.DataGridViewMasterDetails#02](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMasterDetails/CS/masterdetails.cs#02)]
    [!code-vb[System.Windows.Forms.DataGridViewMasterDetails#02](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMasterDetails/VB/masterdetails.vb#02)]

2. 在窗体的类定义中实现一个方法, 用于处理连接到数据库的详细信息。 此示例使用一个`GetData`方法, 该方法<xref:System.Data.DataSet>填充对象, 将<xref:System.Data.DataRelation>对象添加到数据集, 并绑定这些<xref:System.Windows.Forms.BindingSource>组件。 请确保将 `connectionString` 变量设置为适合数据库的值。

    > [!IMPORTANT]
    > 将敏感信息（如密码）存储在连接字符串中可能会影响应用程序的安全性。 若要控制对数据库的访问，一种较为安全的方法是使用 Windows 身份验证（也称为集成安全性）。 有关详细信息，请参阅[保护连接信息](../../data/adonet/protecting-connection-information.md)。

    [!code-csharp[System.Windows.Forms.DataGridViewMasterDetails#20](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMasterDetails/CS/masterdetails.cs#20)]
    [!code-vb[System.Windows.Forms.DataGridViewMasterDetails#20](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMasterDetails/VB/masterdetails.vb#20)]

3. 实现<xref:System.Windows.Forms.Form.Load>窗体事件的处理程序, 该处理程序<xref:System.Windows.Forms.DataGridView>将控件绑定<xref:System.Windows.Forms.BindingSource>到组件并调用`GetData`方法。 下面的示例包含可调整列<xref:System.Windows.Forms.DataGridView>大小以适应显示的数据的代码。

    [!code-csharp[System.Windows.Forms.DataGridViewMasterDetails#10](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMasterDetails/CS/masterdetails.cs#10)]
    [!code-vb[System.Windows.Forms.DataGridViewMasterDetails#10](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMasterDetails/VB/masterdetails.vb#10)]

## <a name="testing-the-application"></a>测试应用程序

你现在可以对窗体进行测试, 以确保它按预期方式运行。

#### <a name="to-test-the-form"></a>测试窗体

- 编译并运行该应用程序。

  您将看到两<xref:System.Windows.Forms.DataGridView>个控件, 一个在对方。 在顶部是 Northwind `Customers`表中的客户, 底部是对应于所选客户的。 `Orders` 选择上部<xref:System.Windows.Forms.DataGridView>的不同行时, 会相应地<xref:System.Windows.Forms.DataGridView>更改的内容。

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
- [在 Windows 窗体 DataGridView 控件中显示数据](displaying-data-in-the-windows-forms-datagridview-control.md)
- [如何：使用两个 Windows 窗体 DataGridView 控件创建主窗体/详细信息窗体](create-a-master-detail-form-using-two-datagridviews.md)
- [保护连接信息](../../data/adonet/protecting-connection-information.md)
