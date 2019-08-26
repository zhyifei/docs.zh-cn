---
title: 如何：用 Windows 窗体 DataGrid 控件创建主/从列表
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
ms.openlocfilehash: f0fd95cf0cd66e9a5105c0b8ff77d8c536a5822d
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2019
ms.locfileid: "69914753"
---
# <a name="how-to-create-masterdetail-lists-with-the-windows-forms-datagrid-control"></a>如何：使用 Windows 窗体 DataGrid 控件创建主/详细信息列表
> [!NOTE]
> <xref:System.Windows.Forms.DataGridView> 控件取代了 <xref:System.Windows.Forms.DataGrid> 控件并添加了功能；但是，可以选择保留 <xref:System.Windows.Forms.DataGrid> 控件以实现向后兼容并供将来使用。 有关详细信息，请参阅 [Windows 窗体 DataGridView 控件与 DataGrid 控件之间的区别](differences-between-the-windows-forms-datagridview-and-datagrid-controls.md)。  
  
 如果您<xref:System.Data.DataSet>包含一系列相关的表, 则可以使用两<xref:System.Windows.Forms.DataGrid>个控件以主/详细信息格式显示数据。 将<xref:System.Windows.Forms.DataGrid>一个网格指定为主网格, 并将第二个指定为详细信息网格。 当你在 "主列表" 中选择条目时, 所有相关的子项都显示在 "详细信息" 列表中。 例如, 如果您<xref:System.Data.DataSet>包含 customers 表和相关订单表, 则您可以将 customers 表指定为主网格, 将 Orders 表指定为详细信息网格。 从主网格中选择客户时, "订单" 表中与该客户关联的所有订单都将显示在 "详细信息" 网格中。  
  
### <a name="to-set-a-masterdetail-relationship-programmatically"></a>以编程方式设置主/从关系  
  
1. 创建两个<xref:System.Windows.Forms.DataGrid>新控件并设置其属性。  
  
2. 向数据集添加表。  
  
3. 声明类型<xref:System.Data.DataRelation>的变量, 以表示要创建的关系。  
  
4. 通过指定关系的名称并指定将绑定两个表的表、列和项来实例化关系。  
  
5. 将关系添加到<xref:System.Data.DataSet>对象的<xref:System.Data.DataSet.Relations%2A>集合中。  
  
6. 使用的<xref:System.Windows.Forms.DataGrid> <xref:System.Data.DataSet>方法将每个网格绑定到。 <xref:System.Windows.Forms.DataGrid.SetDataBinding%2A>  
  
     下面的示例演示如何设置之前生成<xref:System.Data.DataSet>的 (`ds`) 中的 Customers 表和 Orders 表之间的主/从关系。  
  
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

- [DataGrid 控件](datagrid-control-windows-forms.md)
- [DataGrid 控件概述](datagrid-control-overview-windows-forms.md)
- [如何：将 Windows 窗体 DataGrid 控件绑定到数据源](how-to-bind-the-windows-forms-datagrid-control-to-a-data-source.md)
