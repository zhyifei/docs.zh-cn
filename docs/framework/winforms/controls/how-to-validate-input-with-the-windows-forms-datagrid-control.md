---
title: 通过 DataGrid 控件验证输入
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- DataGrid control [Windows Forms], examples
- user input [Windows Forms], validating
- examples [Windows Forms], DataGrid control
- DataGrid control [Windows Forms], validating input
- validation [Windows Forms], user input
ms.assetid: f1e9c3a0-d0a1-4893-a615-b4b0db046c63
ms.openlocfilehash: 3958089007401d2e977c9c96f07c9196e6216596
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/24/2020
ms.locfileid: "76728296"
---
# <a name="how-to-validate-input-with-the-windows-forms-datagrid-control"></a>如何：用 Windows 窗体 DataGrid 控件验证输入

> [!NOTE]
> <xref:System.Windows.Forms.DataGridView> 控件取代了 <xref:System.Windows.Forms.DataGrid> 控件并添加了功能；但是，可以选择保留 <xref:System.Windows.Forms.DataGrid> 控件以实现向后兼容并供将来使用。 有关详细信息，请参阅 [Windows 窗体 DataGridView 控件与 DataGrid 控件之间的区别](differences-between-the-windows-forms-datagridview-and-datagrid-controls.md)。

Windows 窗体 <xref:System.Windows.Forms.DataGrid> 控件提供两种类型的输入验证。 如果用户尝试输入的值不是单元格的不可接受的数据类型（例如，将字符串转换为整数），则新的无效值将替换为旧值。 这种输入验证是自动完成的，不能进行自定义。

其他类型的输入验证可用于拒绝任何不可接受的数据，例如，字段中的值必须大于或等于1，或者字符串不正确。 这是通过为 <xref:System.Data.DataTable.ColumnChanging> 或 <xref:System.Data.DataTable.RowChanging> 事件编写事件处理程序在数据集中完成的。 下面的示例使用 <xref:System.Data.DataTable.ColumnChanging> 事件，因为特定的 "Product" 列不允许使用不可接受的值。 您可以使用 <xref:System.Data.DataTable.RowChanging> 事件来检查 "结束日期" 列的值是否晚于同一行中的 "开始日期" 列。

## <a name="to-validate-user-input"></a>验证用户输入

1. 编写代码来处理相应表的 <xref:System.Data.DataTable.ColumnChanging> 事件。 如果检测到不正确的输入，请调用 <xref:System.Data.DataRow> 对象的 <xref:System.Data.DataRow.SetColumnError%2A> 方法。

    ```vb
    Private Sub Customers_ColumnChanging(ByVal sender As Object, _
    ByVal e As System.Data.DataColumnChangeEventArgs)
       ' Only check for errors in the Product column
       If (e.Column.ColumnName.Equals("Product")) Then
          ' Do not allow "Automobile" as a product.
          If CType(e.ProposedValue, String) = "Automobile" Then
             Dim badValue As Object = e.ProposedValue
             e.ProposedValue = "Bad Data"
             e.Row.RowError = "The Product column contains an error"
             e.Row.SetColumnError(e.Column, "Product cannot be " & _
             CType(badValue, String))
          End If
       End If
    End Sub
    ```

    ```csharp
    //Handle column changing events on the Customers table
    private void Customers_ColumnChanging(object sender, System.Data.DataColumnChangeEventArgs e) {

       //Only check for errors in the Product column
       if (e.Column.ColumnName.Equals("Product")) {

          //Do not allow "Automobile" as a product
          if (e.ProposedValue.Equals("Automobile")) {
             object badValue = e.ProposedValue;
             e.ProposedValue = "Bad Data";
             e.Row.RowError = "The Product column contains an error";
             e.Row.SetColumnError(e.Column, "Product cannot be " + badValue);
          }
       }
    }
    ```

2. 将事件处理程序连接到事件。

    将以下代码放在窗体的 <xref:System.Windows.Forms.Form.Load> 事件或其构造函数中。

    ```vb
    ' Assumes the grid is bound to a dataset called customersDataSet1
    ' with a table called Customers.
    ' Put this code in the form's Load event or its constructor.
    AddHandler customersDataSet1.Tables("Customers").ColumnChanging, AddressOf Customers_ColumnChanging
    ```

    ```csharp
    // Assumes the grid is bound to a dataset called customersDataSet1
    // with a table called Customers.
    // Put this code in the form's Load event or its constructor.
    customersDataSet1.Tables["Customers"].ColumnChanging += new DataColumnChangeEventHandler(this.Customers_ColumnChanging);
    ```

## <a name="see-also"></a>另请参阅

- <xref:System.Windows.Forms.DataGrid>
- <xref:System.Data.DataTable.ColumnChanging>
- <xref:System.Data.DataRow.SetColumnError%2A>
- [DataGrid 控件](datagrid-control-windows-forms.md)
