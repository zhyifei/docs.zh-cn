---
title: 演练：验证 Windows 窗体 DataGridView 控件中的数据
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- validating data [Windows Forms], Windows Forms
- data [Windows Forms], validation
- DataGridView control [Windows Forms], data validation
- data grids [Windows Forms], validating data
- data validation [Windows Forms], Windows Forms
- walkthroughs [Windows Forms], DataGridView control
ms.assetid: a4f1d015-2969-430c-8ea2-b612d179c290
ms.openlocfilehash: 8ad8caef5db13b1f917a6c27da523d3ded915d84
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
---
# <a name="walkthrough-validating-data-in-the-windows-forms-datagridview-control"></a>演练：验证 Windows 窗体 DataGridView 控件中的数据
时向用户显示数据条目功能，你经常需要验证你的窗体中输入的数据。 <xref:System.Windows.Forms.DataGridView>类提供了一种简便方式提交到数据存储区数据之前执行验证。 你可以通过处理在验证数据<xref:System.Windows.Forms.DataGridView.CellValidating>事件，由引发<xref:System.Windows.Forms.DataGridView>当前单元格的更改时。  
  
 在本演练中，你将检索行从`Customers`Northwind 示例数据库中表，然后将其显示在<xref:System.Windows.Forms.DataGridView>控件。 当用户编辑中的单元格`CompanyName`列，尝试将单元格，保留<xref:System.Windows.Forms.DataGridView.CellValidating>事件处理程序将检查新的公司名称字符串，以确保如果新值是空字符串，则不为空;<xref:System.Windows.Forms.DataGridView>将阻止用户的光标离开单元格，直到输入非空字符串。  
  
 若要将代码复制本主题中的一个单独的清单，请参阅[如何： 在 Windows 窗体 DataGridView 控件中验证数据](../../../../docs/framework/winforms/controls/how-to-validate-data-in-the-windows-forms-datagridview-control.md)。  
  
## <a name="prerequisites"></a>系统必备  
 若要完成本演练，你将需要：  
  
-   到 Northwind SQL Server 示例数据库的服务器的访问。  
  
## <a name="creating-the-form"></a>创建窗体  
  
#### <a name="to-validate-data-entered-in-a-datagridview"></a>在 DataGridView 中输入的数据进行验证  
  
1.  创建一个类，派生自<xref:System.Windows.Forms.Form>和包含<xref:System.Windows.Forms.DataGridView>控件和<xref:System.Windows.Forms.BindingSource>组件。  
  
     下面的代码示例提供了基本的初始化，并且包含`Main`方法。  
  
     [!code-csharp[System.Windows.Forms.DataGridViewDataValidation#01](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewDataValidation/CS/datavalidation.cs#01)]
     [!code-vb[System.Windows.Forms.DataGridViewDataValidation#01](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewDataValidation/VB/datavalidation.vb#01)]  
    [!code-csharp[System.Windows.Forms.DataGridViewDataValidation#02](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewDataValidation/CS/datavalidation.cs#02)]
    [!code-vb[System.Windows.Forms.DataGridViewDataValidation#02](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewDataValidation/VB/datavalidation.vb#02)]  
  
2.  实现用于处理连接到数据库的详细信息窗体的类定义中的方法。  
  
     此代码示例使用`GetData`返回填充的方法<xref:System.Data.DataTable>对象。 请确保你设置`connectionString`变量为适合于你的数据库的值。  
  
    > [!IMPORTANT]
    >  将敏感信息（如密码）存储在连接字符串中可能会影响应用程序的安全性。 使用 Windows 身份验证，也称为集成安全性，是一种更安全的方法来控制对数据库的访问。 有关详细信息，请参阅[保护连接信息](../../../../docs/framework/data/adonet/protecting-connection-information.md)。  
  
     [!code-csharp[System.Windows.Forms.DataGridViewDataValidation#30](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewDataValidation/CS/datavalidation.cs#30)]
     [!code-vb[System.Windows.Forms.DataGridViewDataValidation#30](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewDataValidation/VB/datavalidation.vb#30)]  
  
3.  实现你的窗体的处理<xref:System.Windows.Forms.Form.Load>初始化的事件<xref:System.Windows.Forms.DataGridView>和<xref:System.Windows.Forms.BindingSource>和数据绑定设置。  
  
     [!code-csharp[System.Windows.Forms.DataGridViewDataValidation#10](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewDataValidation/CS/datavalidation.cs#10)]
     [!code-vb[System.Windows.Forms.DataGridViewDataValidation#10](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewDataValidation/VB/datavalidation.vb#10)]  
  
4.  实现处理程序<xref:System.Windows.Forms.DataGridView>控件的<xref:System.Windows.Forms.DataGridView.CellValidating>和<xref:System.Windows.Forms.DataGridView.CellEndEdit>事件。  
  
     <xref:System.Windows.Forms.DataGridView.CellValidating>事件处理程序是其中确定是否在单元格的值`CompanyName`列为空。 如果单元格的值未通过验证，则设置<xref:System.ComponentModel.CancelEventArgs.Cancel%2A>属性<xref:System.Windows.Forms.DataGridViewCellValidatingEventArgs?displayProperty=nameWithType>类到`true`。 这将导致<xref:System.Windows.Forms.DataGridView>以防光标离开该单元格的控件。 设置<xref:System.Windows.Forms.DataGridViewRow.ErrorText%2A>为说明性字符串的行上的属性。 此时将显示错误图标，包含错误文本的工具提示。 在<xref:System.Windows.Forms.DataGridView.CellEndEdit>事件处理程序中，设置<xref:System.Windows.Forms.DataGridViewRow.ErrorText%2A>属性为空字符串的行。 <xref:System.Windows.Forms.DataGridView.CellEndEdit>仅当单元格退出编辑模式，则不能如果它未通过验证时，才发生的事件。  
  
     [!code-csharp[System.Windows.Forms.DataGridViewDataValidation#20](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewDataValidation/CS/datavalidation.cs#20)]
     [!code-vb[System.Windows.Forms.DataGridViewDataValidation#20](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewDataValidation/VB/datavalidation.vb#20)]  
  
## <a name="testing-the-application"></a>测试应用程序  
 你现在可以测试窗体，以确保其行为与预期相同。  
  
#### <a name="to-test-the-form"></a>若要测试窗体  
  
-   编译并运行该应用程序。  
  
     你将看到<xref:System.Windows.Forms.DataGridView>数据填充`Customers`表。 当你双击中的单元格`CompanyName`列中，你可以编辑的值。 如果您删除的所有字符并按 TAB 键退出该单元格，<xref:System.Windows.Forms.DataGridView>会阻止您退出。 当你的单元格中键入非空字符串<xref:System.Windows.Forms.DataGridView>控制可用于退出单元格。  
  
## <a name="next-steps"></a>后续步骤  
 此应用程序提供一个基本的了解<xref:System.Windows.Forms.DataGridView>控件的功能。 你可以自定义的外观和行为<xref:System.Windows.Forms.DataGridView>控制以下几种方式：  
  
-   更改边框和标头的样式。 有关详细信息，请参阅[如何： 更改边框和网格线在 Windows 窗体 DataGridView 控件中的样式](../../../../docs/framework/winforms/controls/change-the-border-and-gridline-styles-in-the-datagrid.md)。  
  
-   允许或限制用户输入到<xref:System.Windows.Forms.DataGridView>控件。 有关详细信息，请参阅[如何： 防止添加和删除行在 Windows 窗体 DataGridView 控件中](../../../../docs/framework/winforms/controls/prevent-row-addition-and-deletion-datagridview.md)，和[如何： 在 Windows 窗体 DataGridView 控件中使列成为只读](../../../../docs/framework/winforms/controls/how-to-make-columns-read-only-in-the-windows-forms-datagridview-control.md)。  
  
-   检查与数据库相关的错误的用户输入。 有关详细信息，请参阅[演练： 处理在 Windows 窗体 DataGridView 控件中输入数据时发生的错误](../../../../docs/framework/winforms/controls/handling-errors-that-occur-during-data-entry-in-the-datagrid.md)。  
  
-   处理非常大的数据集使用的虚拟模式。 有关详细信息，请参阅[演练： 在 Windows 窗体 DataGridView 控件中实现虚拟模式](../../../../docs/framework/winforms/controls/implementing-virtual-mode-wf-datagridview-control.md)。  
  
-   自定义单元格的外观。 有关详细信息，请参阅[如何： 自定义 Windows 窗体 DataGridView 控件中的单元外观](../../../../docs/framework/winforms/controls/customize-the-appearance-of-cells-in-the-datagrid.md)和[如何： 设置字体和颜色样式在 Windows 窗体 DataGridView 控件中](../../../../docs/framework/winforms/controls/how-to-set-font-and-color-styles-in-the-windows-forms-datagridview-control.md)。  
  
## <a name="see-also"></a>请参阅  
 <xref:System.Windows.Forms.DataGridView>  
 <xref:System.Windows.Forms.BindingSource>  
 [Windows 窗体 DataGridView 控件中的数据输入](../../../../docs/framework/winforms/controls/data-entry-in-the-windows-forms-datagridview-control.md)  
 [如何：在 Windows 窗体 DataGridView 控件中验证数据](../../../../docs/framework/winforms/controls/how-to-validate-data-in-the-windows-forms-datagridview-control.md)  
 [演练：处理在 Windows 窗体 DataGridView 控件有数据输入时发生的错误](../../../../docs/framework/winforms/controls/handling-errors-that-occur-during-data-entry-in-the-datagrid.md)  
 [保护连接信息](../../../../docs/framework/data/adonet/protecting-connection-information.md)
