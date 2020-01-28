---
title: 演练：处理 DataGridView 控件中的数据输入期间发生的错误
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
ms.openlocfilehash: 77a4dcd9cf069ed8bbee6c49aa41db619c8e12ff
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/24/2020
ms.locfileid: "76738733"
---
# <a name="walkthrough-handling-errors-that-occur-during-data-entry-in-the-windows-forms-datagridview-control"></a>연습: Windows Forms DataGridView 컨트롤에서 데이터 입력 중에 발생하는 오류 처리

处理基础数据存储区中的错误是数据输入应用程序所必需的功能。 Windows 窗体 <xref:System.Windows.Forms.DataGridView> 控件通过公开 <xref:System.Windows.Forms.DataGridView.DataError> 事件实现此功能，该事件是在数据存储区检测到违反约束或违反业务规则时引发的。

在本演练中，您将从 Northwind 示例数据库的 "`Customers`" 表中检索行，并将它们显示在 <xref:System.Windows.Forms.DataGridView> 控件中。 在新行或编辑的现有行中检测到重复的 `CustomerID` 值时，将发生 <xref:System.Windows.Forms.DataGridView.DataError> 事件，该事件将通过显示描述该异常的 <xref:System.Windows.Forms.MessageBox> 进行处理。

若要将本主题中的代码复制为单个列表，请参阅[如何：处理 Windows 窗体 DataGridView 控件中的数据输入期间发生的错误](handle-errors-that-occur-during-data-entry-in-the-datagrid.md)。

## <a name="prerequisites"></a>先决条件

이 연습을 완료하려면 다음 사항이 필요합니다.

- 访问包含 Northwind SQL Server 示例数据库的服务器。

## <a name="creating-the-form"></a>폼 만들기

#### <a name="to-handle-data-entry-errors-in-the-datagridview-control"></a>处理 DataGridView 控件中的数据输入错误

1. 创建一个派生自 <xref:System.Windows.Forms.Form> 的类，其中包含一个 <xref:System.Windows.Forms.DataGridView> 控件和一个 <xref:System.Windows.Forms.BindingSource> 组件。

    下面的代码示例提供了基本的初始化，并包括 `Main` 方法。

    [!code-csharp[System.Windows.Forms.DataGridView.DataError#01](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.DataError/CS/errorhandling.cs#01)]
    [!code-vb[System.Windows.Forms.DataGridView.DataError#01](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.DataError/VB/errorhandling.vb#01)]
    [!code-csharp[System.Windows.Forms.DataGridView.DataError#02](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.DataError/CS/errorhandling.cs#02)]
    [!code-vb[System.Windows.Forms.DataGridView.DataError#02](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.DataError/VB/errorhandling.vb#02)]

2. 在窗体的类定义中实现一个方法，用于处理连接到数据库的详细信息。

    此代码示例使用 `GetData` 方法，该方法返回填充的 <xref:System.Data.DataTable> 对象。 请确保将 `connectionString` 变量设置为适合数据库的值。

    > [!IMPORTANT]
    > 암호와 같은 중요한 정보를 연결 문자열 내에 저장하면 애플리케이션 보안 문제가 발생할 수 있습니다. 데이터베이스 액세스를 제어할 경우에는 통합 보안이라고도 하는 Windows 인증을 사용하는 방법이 더 안전합니다. 자세한 내용은 [연결 정보 보호](../../data/adonet/protecting-connection-information.md)를 참조하세요.

    [!code-csharp[System.Windows.Forms.DataGridView.DataError#30](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.DataError/CS/errorhandling.cs#30)]
    [!code-vb[System.Windows.Forms.DataGridView.DataError#30](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.DataError/VB/errorhandling.vb#30)]

3. 为窗体的 <xref:System.Windows.Forms.Form.Load> 事件实现处理程序，该事件初始化 <xref:System.Windows.Forms.DataGridView> 并 <xref:System.Windows.Forms.BindingSource> 和设置数据绑定。

    [!code-csharp[System.Windows.Forms.DataGridView.DataError#10](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.DataError/CS/errorhandling.cs#10)]
    [!code-vb[System.Windows.Forms.DataGridView.DataError#10](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.DataError/VB/errorhandling.vb#10)]

4. 处理 <xref:System.Windows.Forms.DataGridView>上的 <xref:System.Windows.Forms.DataGridView.DataError> 事件。

    如果错误上下文为 commit 操作，则会在 <xref:System.Windows.Forms.MessageBox>中显示错误。

    [!code-csharp[System.Windows.Forms.DataGridView.DataError#20](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.DataError/CS/errorhandling.cs#20)]
    [!code-vb[System.Windows.Forms.DataGridView.DataError#20](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.DataError/VB/errorhandling.vb#20)]

## <a name="testing-the-application"></a>测试应用程序

你现在可以对窗体进行测试，以确保它按预期方式运行。

#### <a name="to-test-the-form"></a>测试窗体

- F5 키를 눌러 응용 프로그램을 실행합니다.

  你将看到一个使用 Customers 表中的数据填充的 <xref:System.Windows.Forms.DataGridView> 控件。 如果为 `CustomerID` 输入重复的值并提交编辑，则单元值将自动还原，并且你将看到一个显示数据输入错误的 <xref:System.Windows.Forms.MessageBox>。

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
- [Windows Forms DataGridView 컨트롤의 데이터 입력](data-entry-in-the-windows-forms-datagridview-control.md)
- [방법: Windows Forms DataGridView 컨트롤에서 데이터 입력 중에 발생하는 오류 처리](handle-errors-that-occur-during-data-entry-in-the-datagrid.md)
- [연습: Windows Forms DataGridView 컨트롤의 데이터 유효성 검사](walkthrough-validating-data-in-the-windows-forms-datagridview-control.md)
- [연결 정보 보호](../../data/adonet/protecting-connection-information.md)
