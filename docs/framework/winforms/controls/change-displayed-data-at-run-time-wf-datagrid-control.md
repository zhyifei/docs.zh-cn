---
title: 在数据网格控制中更改运行时显示的数据
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- DataGrid control [Windows Forms], dynamically changing at run time
- DataGrid control [Windows Forms], data binding
- cells [Windows Forms], changing DataGrid cell values
ms.assetid: 0c7a6d00-30de-416e-8223-0a81ddb4c1f8
ms.openlocfilehash: 6b788c10784082a0c74ee09f8cd85d540c670b84
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2020
ms.locfileid: "79142376"
---
# <a name="how-to-change-displayed-data-at-run-time-in-the-windows-forms-datagrid-control"></a><span data-ttu-id="6a756-102">如何：在运行时更改 Windows 窗体 DataGrid 控件中显示的数据</span><span class="sxs-lookup"><span data-stu-id="6a756-102">How to: Change Displayed Data at Run Time in the Windows Forms DataGrid Control</span></span>
> [!NOTE]
> <span data-ttu-id="6a756-103"><xref:System.Windows.Forms.DataGridView> 控件取代了 <xref:System.Windows.Forms.DataGrid> 控件并添加了功能；但是，可以选择保留 <xref:System.Windows.Forms.DataGrid> 控件以实现向后兼容并供将来使用。</span><span class="sxs-lookup"><span data-stu-id="6a756-103">The <xref:System.Windows.Forms.DataGridView> control replaces and adds functionality to the <xref:System.Windows.Forms.DataGrid> control; however, the <xref:System.Windows.Forms.DataGrid> control is retained for both backward compatibility and future use, if you choose.</span></span> <span data-ttu-id="6a756-104">有关详细信息，请参阅 [Windows 窗体 DataGridView 控件与 DataGrid 控件之间的区别](differences-between-the-windows-forms-datagridview-and-datagrid-controls.md)。</span><span class="sxs-lookup"><span data-stu-id="6a756-104">For more information, see [Differences Between the Windows Forms DataGridView and DataGrid Controls](differences-between-the-windows-forms-datagridview-and-datagrid-controls.md).</span></span>  
  
 <span data-ttu-id="6a756-105">使用设计时功能创建 Windows<xref:System.Windows.Forms.DataGrid>窗体后，您可能还希望在运行时动态更改网格<xref:System.Data.DataSet>对象的元素。</span><span class="sxs-lookup"><span data-stu-id="6a756-105">After you have created a Windows Forms <xref:System.Windows.Forms.DataGrid> using the design-time features, you may also wish to dynamically change elements of the <xref:System.Data.DataSet> object of the grid at run time.</span></span> <span data-ttu-id="6a756-106">这可能包括对表的单个值的更改或更改绑定到控件的<xref:System.Windows.Forms.DataGrid>数据源。</span><span class="sxs-lookup"><span data-stu-id="6a756-106">This can include changes to either individual values of the table or changing which data source is bound to the <xref:System.Windows.Forms.DataGrid> control.</span></span> <span data-ttu-id="6a756-107">对单个值的更改是通过<xref:System.Data.DataSet>对象而不是控件完成的。 <xref:System.Windows.Forms.DataGrid></span><span class="sxs-lookup"><span data-stu-id="6a756-107">Changes to individual values are done through the <xref:System.Data.DataSet> object, not the <xref:System.Windows.Forms.DataGrid> control.</span></span>  
  
### <a name="to-change-data-programmatically"></a><span data-ttu-id="6a756-108">以编程方式更改数据</span><span class="sxs-lookup"><span data-stu-id="6a756-108">To change data programmatically</span></span>  
  
1. <span data-ttu-id="6a756-109">从<xref:System.Data.DataSet>对象指定所需的表，从表中指定所需的行和字段，并将单元格设置为等于新值。</span><span class="sxs-lookup"><span data-stu-id="6a756-109">Specify the desired table from the <xref:System.Data.DataSet> object and the desired row and field from the table and set the cell equal to the new value.</span></span>  
  
    > [!NOTE]
    > <span data-ttu-id="6a756-110">要指定 表<xref:System.Data.DataSet>的第一个表或表的第一行，请使用 0。</span><span class="sxs-lookup"><span data-stu-id="6a756-110">To specify the first table of the <xref:System.Data.DataSet> or the first row of the table, use 0.</span></span>  
  
     <span data-ttu-id="6a756-111">下面的示例演示如何通过单击`Button1`来更改数据集第一个表的第一行的第二个条目。</span><span class="sxs-lookup"><span data-stu-id="6a756-111">The following example shows how to change the second entry of the first row of the first table of a dataset by clicking `Button1`.</span></span> <span data-ttu-id="6a756-112">以前<xref:System.Data.DataSet>创建的`ds`（ 和`0``1`表 和 ）</span><span class="sxs-lookup"><span data-stu-id="6a756-112">The <xref:System.Data.DataSet> (`ds`) and Tables (`0` and `1`) were previously created.</span></span>  
  
    ```vb  
    Protected Sub Button1_Click(ByVal sender As System.Object, ByVal e As System.EventArgs) Handles Button1.Click  
       ds.tables(0).rows(0)(1) = "NewEntry"  
    End Sub  
    ```  
  
    ```csharp  
    private void button1_Click(object sender, System.EventArgs e)  
    {  
       ds.Tables[0].Rows[0][1]="NewEntry";  
    }  
    ```  
  
    ```cpp  
    private:
       void button1_Click(System::Object^ sender, System::EventArgs^ e)  
       {  
          dataSet1->Tables[0]->Rows[0][1] = "NewEntry";  
       }  
    ```  
  
     <span data-ttu-id="6a756-113">（视觉 C#，视觉C++）将以下代码放在窗体的构造函数中以注册事件处理程序。</span><span class="sxs-lookup"><span data-stu-id="6a756-113">(Visual C#, Visual C++) Place the following code in the form's constructor to register the event handler.</span></span>  
  
    ```csharp  
    this.button1.Click += new System.EventHandler(this.button1_Click);  
    ```  
  
    ```cpp  
    this->button1->Click +=  
       gcnew System::EventHandler(this, &Form1::button1_Click);  
    ```  
  
     <span data-ttu-id="6a756-114">在运行时，可以使用 方法<xref:System.Windows.Forms.DataGrid.SetDataBinding%2A>将<xref:System.Windows.Forms.DataGrid>控件绑定到其他数据源。</span><span class="sxs-lookup"><span data-stu-id="6a756-114">At run time you can use the <xref:System.Windows.Forms.DataGrid.SetDataBinding%2A> method to bind the <xref:System.Windows.Forms.DataGrid> control to a different data source.</span></span> <span data-ttu-id="6a756-115">例如，您可能有多个ADO.NET数据控件，每个控件都连接到不同的数据库。</span><span class="sxs-lookup"><span data-stu-id="6a756-115">For example, you may have several ADO.NET data controls, each connected to a different database.</span></span>  
  
### <a name="to-change-the-datasource-programmatically"></a><span data-ttu-id="6a756-116">以编程方式更改数据源</span><span class="sxs-lookup"><span data-stu-id="6a756-116">To change the DataSource programmatically</span></span>  
  
1. <span data-ttu-id="6a756-117">将<xref:System.Windows.Forms.DataGrid.SetDataBinding%2A>方法设置为要绑定到的数据源和表的名称。</span><span class="sxs-lookup"><span data-stu-id="6a756-117">Set the <xref:System.Windows.Forms.DataGrid.SetDataBinding%2A> method to the name of the data source and table you want to bind to.</span></span>  
  
     <span data-ttu-id="6a756-118">下面的示例演示如何使用<xref:System.Windows.Forms.DataGrid.SetDataBinding%2A>方法将日期源更改为连接到 Pubs 数据库中的作者表ADO.NET数据控件（adoPubsAuthors）。</span><span class="sxs-lookup"><span data-stu-id="6a756-118">The following example shows how to change the date source using the <xref:System.Windows.Forms.DataGrid.SetDataBinding%2A> method to an ADO.NET data control (adoPubsAuthors) that is connected to the Authors table in the Pubs database.</span></span>  
  
    ```vb  
    Private Sub ResetSource()  
       DataGrid1.SetDataBinding(adoPubsAuthors, "Authors")  
    End Sub  
    ```  
  
    ```csharp  
    private void ResetSource()  
    {  
       DataGrid1.SetDataBinding(adoPubsAuthors, "Authors");  
    }  
    ```  
  
    ```cpp  
    private:  
       void ResetSource()  
       {  
          dataGrid1->SetDataBinding(adoPubsAuthors, "Authors");  
       }  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="6a756-119">另请参阅</span><span class="sxs-lookup"><span data-stu-id="6a756-119">See also</span></span>

- [<span data-ttu-id="6a756-120">ADO.NET 数据集</span><span class="sxs-lookup"><span data-stu-id="6a756-120">ADO.NET DataSets</span></span>](../../data/adonet/ado-net-datasets.md)
- [<span data-ttu-id="6a756-121">如何：在 Windows 窗体 DataGrid 控件中删除或隐藏列</span><span class="sxs-lookup"><span data-stu-id="6a756-121">How to: Delete or Hide Columns in the Windows Forms DataGrid Control</span></span>](how-to-delete-or-hide-columns-in-the-windows-forms-datagrid-control.md)
- [<span data-ttu-id="6a756-122">如何：向 Windows 窗体 DataGrid 控件添加表和列</span><span class="sxs-lookup"><span data-stu-id="6a756-122">How to: Add Tables and Columns to the Windows Forms DataGrid Control</span></span>](how-to-add-tables-and-columns-to-the-windows-forms-datagrid-control.md)
- [<span data-ttu-id="6a756-123">如何：将 Windows 窗体 DataGrid 控件绑定到数据源</span><span class="sxs-lookup"><span data-stu-id="6a756-123">How to: Bind the Windows Forms DataGrid Control to a Data Source</span></span>](how-to-bind-the-windows-forms-datagrid-control-to-a-data-source.md)
