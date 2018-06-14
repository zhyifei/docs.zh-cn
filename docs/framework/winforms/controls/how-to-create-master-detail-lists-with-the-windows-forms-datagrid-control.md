---
title: 如何： 使用 Windows 窗体 DataGrid 控件创建主 / 详细信息列表
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- master-details lists
- DataGrid control [Windows Forms], master-details lists
- related tables [Windows Forms], displaying in DataGrid control
ms.assetid: 20388c6a-94f9-4d96-be18-8c200491247f
ms.openlocfilehash: 528d07b766987bdeca22ce480c601a2bdd324c89
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33531113"
---
# <a name="how-to-create-masterdetail-lists-with-the-windows-forms-datagrid-control"></a>如何：使用 Windows 窗体 DataGrid 控件创建主/从列表
> [!NOTE]
>  <xref:System.Windows.Forms.DataGridView> 控件取代了 <xref:System.Windows.Forms.DataGrid> 控件并添加了功能；但是，可以选择保留 <xref:System.Windows.Forms.DataGrid> 控件以实现向后兼容并供将来使用。 有关详细信息，请参阅 [Windows 窗体 DataGridView 控件与 DataGrid 控件之间的区别](../../../../docs/framework/winforms/controls/differences-between-the-windows-forms-datagridview-and-datagrid-controls.md)。  
  
 如果你<xref:System.Data.DataSet>包含一系列相关表，则可以使用两个<xref:System.Windows.Forms.DataGrid>控件以主/从格式显示数据。 一个<xref:System.Windows.Forms.DataGrid>指定为将主网格，和第二个指定为详细信息网格。 后在主列表中选择一个条目，所有相关的子项将显示在详细信息列表。 例如，如果你<xref:System.Data.DataSet>包含 Customers 表和相关的 Orders 表，则会指定要将主网格的 Customers 表和 Orders 表的详细信息网格。 时从主网格中选择某个客户时，将在详细信息网格中显示所有与 Orders 表中的客户的订单。  
  
### <a name="to-set-a-masterdetail-relationship-programmatically"></a>以编程方式设置的主/从关系  
  
1.  创建两个新<xref:System.Windows.Forms.DataGrid>控件并设置其属性。  
  
2.  将表添加到数据集。  
  
3.  声明类型的变量的<xref:System.Data.DataRelation>来表示你想要创建的关系。  
  
4.  通过指定关系的名称，并指定表、 列和两个表将起到关联的项，实例化关系。  
  
5.  添加到关系<xref:System.Data.DataSet>对象的<xref:System.Data.DataSet.Relations%2A>集合。  
  
6.  使用<xref:System.Windows.Forms.DataGrid.SetDataBinding%2A>方法<xref:System.Windows.Forms.DataGrid>要绑定到网格的每个<xref:System.Data.DataSet>。  
  
     下面的示例演示如何设置中以前生成的客户和订单表之间的主/从关系<xref:System.Data.DataSet>(`ds`)。  
  
    ```vb  
    Dim myDataRelation As DataRelation  
    myDataRelation = New DataRelation _  
       ("CustOrd", ds.Tables("Customers").Columns("CustomerID"), _  
       ds.Tables("Orders").Columns("CustomerID"))  
    ' Add the relation to the DataSet.  
    ds.Relations.Add(myDataRelation)  
    GridOrders.SetDataBinding(ds, "Customers")  
    GridDetails.SetDataBinding(ds, "Customers.CustOrd")  
    ```  
  
    ```csharp  
    DataRelation myDataRelation;  
    myDataRelation = new DataRelation("CustOrd", ds.Tables["Customers"].Columns["CustomerID"], ds.Tables["Orders"].Columns["CustomerID"]);  
    // Add the relation to the DataSet.  
    ds.Relations.Add(myDataRelation);  
    GridOrders.SetDataBinding(ds,"Customers");  
    GridDetails.SetDataBinding(ds,"Customers.CustOrd");  
    ```  
  
    ```cpp  
    DataRelation^ myDataRelation;  
    myDataRelation = gcnew DataRelation("CustOrd",  
       ds->Tables["Customers"]->Columns["CustomerID"],  
       ds->Tables["Orders"]->Columns["CustomerID"]);  
    // Add the relation to the DataSet.  
    ds->Relations->Add(myDataRelation);  
    GridOrders->SetDataBinding(ds, "Customers");  
    GridDetails->SetDataBinding(ds, "Customers.CustOrd");  
    ```  
  
## <a name="see-also"></a>请参阅  
 [DataGrid 控件](../../../../docs/framework/winforms/controls/datagrid-control-windows-forms.md)  
 [DataGrid 控件概述](../../../../docs/framework/winforms/controls/datagrid-control-overview-windows-forms.md)  
 [如何：将 Windows 窗体 DataGrid 控件绑定到数据源](../../../../docs/framework/winforms/controls/how-to-bind-the-windows-forms-datagrid-control-to-a-data-source.md)
