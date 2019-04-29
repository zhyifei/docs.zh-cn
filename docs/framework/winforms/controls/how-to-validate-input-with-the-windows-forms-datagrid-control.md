---
title: 如何：用 Windows 窗体 DataGrid 控件验证输入
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
ms.openlocfilehash: dc8c8f157e6673c1bddc68bfb511683e6d2b99be
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "61796469"
---
# <a name="how-to-validate-input-with-the-windows-forms-datagrid-control"></a><span data-ttu-id="205f2-102">如何：用 Windows 窗体 DataGrid 控件验证输入</span><span class="sxs-lookup"><span data-stu-id="205f2-102">How to: Validate Input with the Windows Forms DataGrid Control</span></span>

> [!NOTE]
> <span data-ttu-id="205f2-103"><xref:System.Windows.Forms.DataGridView> 控件取代了 <xref:System.Windows.Forms.DataGrid> 控件并添加了功能；但是，可以选择保留 <xref:System.Windows.Forms.DataGrid> 控件以实现向后兼容并供将来使用。</span><span class="sxs-lookup"><span data-stu-id="205f2-103">The <xref:System.Windows.Forms.DataGridView> control replaces and adds functionality to the <xref:System.Windows.Forms.DataGrid> control; however, the <xref:System.Windows.Forms.DataGrid> control is retained for both backward compatibility and future use, if you choose.</span></span> <span data-ttu-id="205f2-104">有关详细信息，请参阅 [Windows 窗体 DataGridView 控件与 DataGrid 控件之间的区别](differences-between-the-windows-forms-datagridview-and-datagrid-controls.md)。</span><span class="sxs-lookup"><span data-stu-id="205f2-104">For more information, see [Differences Between the Windows Forms DataGridView and DataGrid Controls](differences-between-the-windows-forms-datagridview-and-datagrid-controls.md).</span></span>

<span data-ttu-id="205f2-105">有两种类型的输入验证可用于 Windows 窗体<xref:System.Windows.Forms.DataGrid>控件。</span><span class="sxs-lookup"><span data-stu-id="205f2-105">There are two types of input validation available for the Windows Forms <xref:System.Windows.Forms.DataGrid> control.</span></span> <span data-ttu-id="205f2-106">如果用户尝试输入的单元格，例如整数、 字符串不可接受的数据类型的值的新的无效值将被替换的旧值。</span><span class="sxs-lookup"><span data-stu-id="205f2-106">If the user attempts to enter a value that is of an unacceptable data type for the cell, for example a string into an integer, the new invalid value is replaced with the old value.</span></span> <span data-ttu-id="205f2-107">这种输入验证自动完成的不能自定义。</span><span class="sxs-lookup"><span data-stu-id="205f2-107">This kind of input validation is done automatically and cannot be customized.</span></span>

<span data-ttu-id="205f2-108">可以使用其他类型的输入验证拒绝任何不可接受的数据，例如中必须是大于或等于 1 或不适当的字符串的字段值为 0。</span><span class="sxs-lookup"><span data-stu-id="205f2-108">The other type of input validation can be used to reject any unacceptable data, for example a 0 value in a field that must be greater than or equal to 1, or an inappropriate string.</span></span> <span data-ttu-id="205f2-109">这通过编写事件处理程序完成在数据集中<xref:System.Data.DataTable.ColumnChanging>或<xref:System.Data.DataTable.RowChanging>事件。</span><span class="sxs-lookup"><span data-stu-id="205f2-109">This is done in the dataset by writing an event handler for the <xref:System.Data.DataTable.ColumnChanging> or <xref:System.Data.DataTable.RowChanging> event.</span></span> <span data-ttu-id="205f2-110">下面的示例使用<xref:System.Data.DataTable.ColumnChanging>事件因为不可接受的值特别是"Product"列不允许。</span><span class="sxs-lookup"><span data-stu-id="205f2-110">The example below uses the <xref:System.Data.DataTable.ColumnChanging> event because the unacceptable value is disallowed for the "Product" column in particular.</span></span> <span data-ttu-id="205f2-111">可以使用<xref:System.Data.DataTable.RowChanging>对于检查"结束日期"列的值是否晚于同一行中的"起始日期"列的事件。</span><span class="sxs-lookup"><span data-stu-id="205f2-111">You might use the <xref:System.Data.DataTable.RowChanging> event for checking that the value of an "End Date" column is later than the "Start Date" column in the same row.</span></span>

## <a name="to-validate-user-input"></a><span data-ttu-id="205f2-112">若要验证用户输入</span><span class="sxs-lookup"><span data-stu-id="205f2-112">To validate user input</span></span>

1. <span data-ttu-id="205f2-113">编写代码来处理<xref:System.Data.DataTable.ColumnChanging>适当的表的事件。</span><span class="sxs-lookup"><span data-stu-id="205f2-113">Write code to handle the <xref:System.Data.DataTable.ColumnChanging> event for the appropriate table.</span></span> <span data-ttu-id="205f2-114">检测到不适当的输入时，调用<xref:System.Data.DataRow.SetColumnError%2A>方法的<xref:System.Data.DataRow>对象。</span><span class="sxs-lookup"><span data-stu-id="205f2-114">When inappropriate input is detected, call the <xref:System.Data.DataRow.SetColumnError%2A> method of the <xref:System.Data.DataRow> object.</span></span>

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

2. <span data-ttu-id="205f2-115">连接到该事件的事件处理程序。</span><span class="sxs-lookup"><span data-stu-id="205f2-115">Connect the event handler to the event.</span></span>

    <span data-ttu-id="205f2-116">将下面的代码中窗体的<xref:System.Windows.Forms.Form.Load>事件或其构造函数。</span><span class="sxs-lookup"><span data-stu-id="205f2-116">Place the following code within either the form's <xref:System.Windows.Forms.Form.Load> event or its constructor.</span></span>

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

## <a name="see-also"></a><span data-ttu-id="205f2-117">请参阅</span><span class="sxs-lookup"><span data-stu-id="205f2-117">See also</span></span>

- <xref:System.Windows.Forms.DataGrid>
- <xref:System.Data.DataTable.ColumnChanging>
- <xref:System.Data.DataRow.SetColumnError%2A>
- [<span data-ttu-id="205f2-118">DataGrid 控件</span><span class="sxs-lookup"><span data-stu-id="205f2-118">DataGrid Control</span></span>](datagrid-control-windows-forms.md)
