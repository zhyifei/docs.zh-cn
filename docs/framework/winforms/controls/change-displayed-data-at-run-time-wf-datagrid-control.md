---
title: 如何：更改 Windows 窗体 DataGrid 控件中在运行时显示的数据
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
ms.openlocfilehash: c7bf70a67729744f4cf96318f6b270a5ea81b812
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2019
ms.locfileid: "69917723"
---
# <a name="how-to-change-displayed-data-at-run-time-in-the-windows-forms-datagrid-control"></a>如何：更改 Windows 窗体 DataGrid 控件中在运行时显示的数据
> [!NOTE]
> <xref:System.Windows.Forms.DataGridView> 控件取代了 <xref:System.Windows.Forms.DataGrid> 控件并添加了功能；但是，可以选择保留 <xref:System.Windows.Forms.DataGrid> 控件以实现向后兼容并供将来使用。 有关详细信息，请参阅 [Windows 窗体 DataGridView 控件与 DataGrid 控件之间的区别](differences-between-the-windows-forms-datagridview-and-datagrid-controls.md)。  
  
 使用设计时功能创建 Windows 窗体<xref:System.Windows.Forms.DataGrid>后, 你可能还希望在运行时动态更改网格<xref:System.Data.DataSet>对象的元素。 这可以包括更改表的单个值或更改绑定到<xref:System.Windows.Forms.DataGrid>控件的数据源。 对单个值的<xref:System.Data.DataSet>更改是通过对象 ( <xref:System.Windows.Forms.DataGrid>而不是控件) 完成的。  
  
### <a name="to-change-data-programmatically"></a>以编程方式更改数据  
  
1. 从该<xref:System.Data.DataSet>对象指定所需的表以及表中所需的行和字段, 并将该单元格设置为等于新的值。  
  
    > [!NOTE]
    > 若要指定表的第一个<xref:System.Data.DataSet>表或表的第一行, 请使用0。  
  
     下面的示例演示如何通过单击`Button1`更改数据集中第一个表的第一行的第二个条目。 之前<xref:System.Data.DataSet>创建`ds`了 () 和`0`表`1`(和)。  
  
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
  
     (视觉C#对象、 C++视觉对象)将以下代码放在窗体的构造函数中以注册事件处理程序。  
  
    ```csharp  
    this.button1.Click += new System.EventHandler(this.button1_Click);  
    ```  
  
    ```cpp  
    this->button1->Click +=  
       gcnew System::EventHandler(this, &Form1::button1_Click);  
    ```  
  
     在运行时, 可以使用<xref:System.Windows.Forms.DataGrid.SetDataBinding%2A>方法将<xref:System.Windows.Forms.DataGrid>控件绑定到不同的数据源。 例如, 您可能有多个 ADO.NET 数据控件, 每个控件都连接到不同的数据库。  
  
### <a name="to-change-the-datasource-programmatically"></a>以编程方式更改数据源  
  
1. <xref:System.Windows.Forms.DataGrid.SetDataBinding%2A>将方法设置为要绑定到的数据源和表的名称。  
  
     下面的示例演示如何使用<xref:System.Windows.Forms.DataGrid.SetDataBinding%2A>方法将数据源更改为连接到 Pubs 数据库中的 Authors 表的 ADO.NET 数据控件 (adoPubsAuthors)。  
  
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

- [ADO.NET 数据集](../../data/adonet/ado-net-datasets.md)
- [如何：删除或隐藏 Windows 窗体 DataGrid 控件中的列](how-to-delete-or-hide-columns-in-the-windows-forms-datagrid-control.md)
- [如何：向 Windows 窗体 DataGrid 控件添加表和列](how-to-add-tables-and-columns-to-the-windows-forms-datagrid-control.md)
- [如何：将 Windows 窗体 DataGrid 控件绑定到数据源](how-to-bind-the-windows-forms-datagrid-control-to-a-data-source.md)
