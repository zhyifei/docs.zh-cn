---
title: "管理 DataView"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
ms.assetid: 0b67fab5-1722-4d2b-bfc1-247a75f0f1ee
caps.latest.revision: "4"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: 3cf89cd378d19b5de64a733e80ec757c7e3bdb89
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="managing-dataviews"></a>管理 DataView
可以使用 <xref:System.Data.DataViewManager> 来管理 <xref:System.Data.DataView> 中所有表的视图设置。 如果你有想要绑定到多个表的控件，如网格进行关系导航**DataViewManager**是理想之选。  
  
 **DataViewManager**包含一套<xref:System.Data.DataViewSetting>用于设置中的表的视图设置的对象<xref:System.Data.DataSet>。 <xref:System.Data.DataViewSettingCollection>包含一个<xref:System.Data.DataViewSetting>每个表中的对象**数据集**。 你可以设置默认值**ApplyDefaultSort**，**排序**， **RowFilter**，和**RowStateFilter**所引用表的属性使用其**DataViewSetting**。 你可以引用**DataViewSetting**为特定表按名称或序号引用，或者通过将传递给该特定表对象的引用。 你可以访问的集合**DataViewSetting**中的对象**DataViewManager**使用**Dataviewsetting**属性。  
  
 以下代码示例填充**数据集**与 SQL Server **Northwind**数据库表**客户**，**订单**，和**订单明细**、 创建表之间的关系，然后使用**DataViewManager** ，来设置默认**DataView**设置和绑定**DataGrid**到**DataViewManager**。 该示例设置的默认**DataView**中的所有表设置**数据集**要作为排序依据表的主键 (**ApplyDefaultSort**  =  **true**)，然后修改的排序顺序**客户**表要作为排序依据**CompanyName**。  
  
```vb  
' Assumes connection is a valid SqlConnection to Northwind.  
' Create a Connection, DataAdapters, and a DataSet.  
Dim custDA As SqlDataAdapter = New SqlDataAdapter( _  
  "SELECT CustomerID, CompanyName FROM Customers", connection)  
Dim orderDA As SqlDataAdapter = New SqlDataAdapter( _  
  "SELECT OrderID, CustomerID FROM Orders", connection)  
Dim ordDetDA As SqlDataAdapter = New SqlDataAdapter( _  
  "SELECT OrderID, ProductID, Quantity FROM [Order Details]", connection)  
  
Dim custDS As DataSet = New DataSet()  
  
' Open the Connection.  
connection.Open()  
  
    ' Fill the DataSet with schema information and data.  
    custDA.MissingSchemaAction = MissingSchemaAction.AddWithKey  
    orderDA.MissingSchemaAction = MissingSchemaAction.AddWithKey  
    ordDetDA.MissingSchemaAction = MissingSchemaAction.AddWithKey  
  
    custDA.Fill(custDS, "Customers")  
    orderDA.Fill(custDS, "Orders")  
    ordDetDA.Fill(custDS, "OrderDetails")  
  
    ' Close the Connection.  
    connection.Close()  
  
    ' Create relationships.  
    custDS.Relations.Add("CustomerOrders", _  
          custDS.Tables("Customers").Columns("CustomerID"), _  
          custDS.Tables("Orders").Columns("CustomerID"))  
  
    custDS.Relations.Add("OrderDetails", _  
          custDS.Tables("Orders").Columns("OrderID"), _  
          custDS.Tables("OrderDetails").Columns("OrderID"))  
  
' Create default DataView settings.  
Dim viewManager As DataViewManager = New DataViewManager(custDS)  
  
Dim viewSetting As DataViewSetting  
For Each viewSetting In viewManager.DataViewSettings  
  viewSetting.ApplyDefaultSort = True  
Next  
  
viewManager.DataViewSettings("Customers").Sort = "CompanyName"  
  
' Bind to a DataGrid.  
Dim grid As System.Windows.Forms.DataGrid = New System.Windows.Forms.DataGrid()  
grid.SetDataBinding(viewManager, "Customers")  
```  
  
```csharp  
// Assumes connection is a valid SqlConnection to Northwind.  
// Create a Connection, DataAdapters, and a DataSet.  
SqlDataAdapter custDA = new SqlDataAdapter(  
  "SELECT CustomerID, CompanyName FROM Customers", connection);  
SqlDataAdapter orderDA = new SqlDataAdapter(  
  "SELECT OrderID, CustomerID FROM Orders", connection);  
SqlDataAdapter ordDetDA = new SqlDataAdapter(  
  "SELECT OrderID, ProductID, Quantity FROM [Order Details]", connection);  
  
DataSet custDS = new DataSet();  
  
// Open the Connection.  
connection.Open();  
  
    // Fill the DataSet with schema information and data.  
    custDA.MissingSchemaAction = MissingSchemaAction.AddWithKey;  
    orderDA.MissingSchemaAction = MissingSchemaAction.AddWithKey;  
    ordDetDA.MissingSchemaAction = MissingSchemaAction.AddWithKey;  
  
    custDA.Fill(custDS, "Customers");  
    orderDA.Fill(custDS, "Orders");  
    ordDetDA.Fill(custDS, "OrderDetails");  
  
    // Close the Connection.  
    connection.Close();  
  
    // Create relationships.  
    custDS.Relations.Add("CustomerOrders",  
          custDS.Tables["Customers"].Columns["CustomerID"],  
          custDS.Tables["Orders"].Columns["CustomerID"]);  
  
    custDS.Relations.Add("OrderDetails",  
          custDS.Tables["Orders"].Columns["OrderID"],  
          custDS.Tables["OrderDetails"].Columns["OrderID"]);  
  
// Create default DataView settings.  
DataViewManager viewManager = new DataViewManager(custDS);  
  
foreach (DataViewSetting viewSetting in viewManager.DataViewSettings)  
  viewSetting.ApplyDefaultSort = true;  
  
viewManager.DataViewSettings["Customers"].Sort = "CompanyName";  
  
// Bind to a DataGrid.  
System.Windows.Forms.DataGrid grid = new System.Windows.Forms.DataGrid();  
grid.SetDataBinding(viewManager, "Customers");  
```  
  
## <a name="see-also"></a>另请参阅  
 <xref:System.Data.DataSet>  
 <xref:System.Data.DataViewManager>  
 <xref:System.Data.DataViewSetting>  
 <xref:System.Data.DataViewSettingCollection>  
 [数据视图](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/dataviews.md)  
 [ADO.NET 托管提供程序和数据集开发人员中心](http://go.microsoft.com/fwlink/?LinkId=217917)
