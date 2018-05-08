---
title: 如何：在运行时更改 Windows 窗体 DataGrid 控件中显示的数据
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
ms.openlocfilehash: 1059f774ae8d2c203d7a4f5c02c597b4686304f7
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-change-displayed-data-at-run-time-in-the-windows-forms-datagrid-control"></a>如何：在运行时更改 Windows 窗体 DataGrid 控件中显示的数据
> [!NOTE]
>  <xref:System.Windows.Forms.DataGridView> 控件取代了 <xref:System.Windows.Forms.DataGrid> 控件并添加了功能；但是，可以选择保留 <xref:System.Windows.Forms.DataGrid> 控件以实现向后兼容并供将来使用。 有关详细信息，请参阅 [Windows 窗体 DataGridView 控件与 DataGrid 控件之间的区别](../../../../docs/framework/winforms/controls/differences-between-the-windows-forms-datagridview-and-datagrid-controls.md)。  
  
 创建 Windows 窗体后<xref:System.Windows.Forms.DataGrid>使用的设计时功能，你可能还想要动态更改元素的<xref:System.Data.DataSet>在网格中运行时的对象。 这可以包括对表的任一单个值的更改，或更改的数据源绑定到<xref:System.Windows.Forms.DataGrid>控件。 对单个值的更改都是通过<xref:System.Data.DataSet>对象，而不<xref:System.Windows.Forms.DataGrid>控件。  
  
### <a name="to-change-data-programmatically"></a>若要以编程方式更改数据  
  
1.  指定所需的表，从<xref:System.Data.DataSet>对象和所需的行和字段从表并将该单元格设置为新值。  
  
    > [!NOTE]
    >  若要指定的第一个表<xref:System.Data.DataSet>或表，则第一行使用 0。  
  
     下面的示例演示如何通过单击来更改数据集的第一个表的第一行的第二项`Button1`。 <xref:System.Data.DataSet> (`ds`) 和表 (`0`和`1`) 以前创建。  
  
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
  
     (Visual C#， [!INCLUDE[vcprvc](../../../../includes/vcprvc-md.md)]) 将以下代码放在窗体的构造函数以注册事件处理程序。  
  
    ```csharp  
    this.button1.Click += new System.EventHandler(this.button1_Click);  
    ```  
  
    ```cpp  
    this->button1->Click +=  
       gcnew System::EventHandler(this, &Form1::button1_Click);  
    ```  
  
     在运行的时，你可以使用<xref:System.Windows.Forms.DataGrid.SetDataBinding%2A>方法将绑定<xref:System.Windows.Forms.DataGrid>到不同的数据源的控件。 例如，你可以有几个[!INCLUDE[vstecado](../../../../includes/vstecado-md.md)]数据控件，每个连接到不同的数据库。  
  
### <a name="to-change-the-datasource-programmatically"></a>若要以编程方式更改数据源  
  
1.  设置<xref:System.Windows.Forms.DataGrid.SetDataBinding%2A>方法为数据源和你想要将绑定到的表的名称。  
  
     下面的示例演示如何更改日期源使用<xref:System.Windows.Forms.DataGrid.SetDataBinding%2A>方法[!INCLUDE[vstecado](../../../../includes/vstecado-md.md)]数据控件 (adoPubsAuthors)，连接到 Pubs 数据库中的作者表。  
  
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
  
## <a name="see-also"></a>请参阅  
 [ADO.NET 数据集](../../../../docs/framework/data/adonet/ado-net-datasets.md)  
 [如何：在 Windows 窗体 DataGrid 控件中删除或隐藏列](../../../../docs/framework/winforms/controls/how-to-delete-or-hide-columns-in-the-windows-forms-datagrid-control.md)  
 [如何：向 Windows 窗体 DataGrid 控件添加表和列](../../../../docs/framework/winforms/controls/how-to-add-tables-and-columns-to-the-windows-forms-datagrid-control.md)  
 [如何：将 Windows 窗体 DataGrid 控件绑定到数据源](../../../../docs/framework/winforms/controls/how-to-bind-the-windows-forms-datagrid-control-to-a-data-source.md)
