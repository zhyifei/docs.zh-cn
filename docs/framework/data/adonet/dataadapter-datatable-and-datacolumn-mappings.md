---
title: "DataAdapter 数据表和 DataColumn 映射"
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
ms.assetid: d023260a-a66a-4c39-b8f4-090cd130e730
caps.latest.revision: "3"
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload: dotnet
ms.openlocfilehash: e104ba75026c2ff387eb7c74b11c505e34085f41
ms.sourcegitcommit: ed26cfef4e18f6d93ab822d8c29f902cff3519d1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/17/2018
---
# <a name="dataadapter-datatable-and-datacolumn-mappings"></a>DataAdapter 数据表和 DataColumn 映射
A **DataAdapter**包含零个或多集合<xref:System.Data.Common.DataTableMapping>对象在其**TableMappings**属性。 A **DataTableMapping**提供从针对数据源，查询返回的数据之间的主映射和<xref:System.Data.DataTable>。 **DataTableMapping**名称可以代替了传递**DataTable**名称到**填充**方法**DataAdapter**。 下面的示例创建**DataTableMapping**名为**AuthorsMapping**为**作者**表。  
  
```vb  
workAdapter.TableMappings.Add("AuthorsMapping", "Authors")  
```  
  
```csharp  
workAdapter.TableMappings.Add("AuthorsMapping", "Authors");  
```  
  
 A **DataTableMapping**使你能够使用中的列名称**DataTable**不同的数据库中。 **DataAdapter**使用此映射来更新表时的列匹配。  
  
 如果不指定**TableName**或**DataTableMapping**时调用的名称**填充**或**更新**方法**DataAdapter**、 **DataAdapter**查找**DataTableMapping**名为"Table"。 如果该**DataTableMapping**不存在， **TableName**的**DataTable**为"Table"。 你可以指定默认值**DataTableMapping**通过创建**DataTableMapping**替换为"Table"的名称。  
  
 下面的代码示例创建**DataTableMapping** (从<xref:System.Data.Common>命名空间) 并使其成为指定的默认映射**DataAdapter**通过其命名为"Table"。 然后该示例从查询结果中的第一个表的列的映射 (**客户**表**Northwind**数据库) 到一组中的更加友好的用户名称**Northwind 客户**表中<xref:System.Data.DataSet>。 对于未映射的列，将使用数据源中的列名称。  
  
```vb  
Dim mapping As DataTableMapping = _  
  adapter.TableMappings.Add("Table", "NorthwindCustomers")  
mapping.ColumnMappings.Add("CompanyName", "Company")  
mapping.ColumnMappings.Add("ContactName", "Contact")  
mapping.ColumnMappings.Add("PostalCode", "ZIPCode")  
  
adapter.Fill(custDS)  
```  
  
```csharp  
DataTableMapping mapping =   
  adapter.TableMappings.Add("Table", "NorthwindCustomers");  
mapping.ColumnMappings.Add("CompanyName", "Company");  
mapping.ColumnMappings.Add("ContactName", "Contact");  
mapping.ColumnMappings.Add("PostalCode", "ZIPCode");  
  
adapter.Fill(custDS);  
```  
  
 在更高级的情况下，你可能决定你想相同**DataAdapter**以支持不同的映射不同的表加载。 若要执行此操作，只需添加附加**DataTableMapping**对象。  
  
 当**填充**方法传递的实例**数据集**和**DataTableMapping**名称，如果存在具有该名称的映射; 否则为将使用， **DataTable**的名称，将使用。  
  
 下面的示例创建**DataTableMapping**名称为**客户**和**DataTable**名称**BizTalkSchema**。 示例然后映射到的 SELECT 语句返回的行**BizTalkSchema** **DataTable**。  
  
```vb  
Dim mapping As ITableMapping = _  
  adapter.TableMappings.Add("Customers", "BizTalkSchema")  
mapping.ColumnMappings.Add("CustomerID", "ClientID")  
mapping.ColumnMappings.Add("CompanyName", "ClientName")  
mapping.ColumnMappings.Add("ContactName", "Contact")  
mapping.ColumnMappings.Add("PostalCode", "ZIP")  
  
adapter.Fill(custDS, "Customers")  
```  
  
```csharp  
ITableMapping mapping =   
  adapter.TableMappings.Add("Customers", "BizTalkSchema");  
mapping.ColumnMappings.Add("CustomerID", "ClientID");  
mapping.ColumnMappings.Add("CompanyName", "ClientName");  
mapping.ColumnMappings.Add("ContactName", "Contact");  
mapping.ColumnMappings.Add("PostalCode", "ZIP");  
  
adapter.Fill(custDS, "Customers");  
```  
  
> [!NOTE]
>  如果没有为列映射提供源列名称或者没有为表映射提供源表名称，则将自动生成默认名称。 如果为列映射提供没有源列，则列映射提供递增的默认名称的**SourceColumn** *N，*开头**SourceColumn1**。 如果为表映射提供没有源表名称，则表映射提供递增的默认名称的**SourceTable** *N*，第一页为**SourceTable1**。  
  
> [!NOTE]
>  我们建议你避免的命名约定**SourceColumn** *N*为列映射，或**SourceTable** *N*表映射，因为所提供的名称可能与中的现有默认列映射名称冲突**ColumnMappingCollection**或中的表映射名称**DataTableMappingCollection**. 如果提供的名称已经存在，将引发异常。  
  
## <a name="handling-multiple-result-sets"></a>处理多个结果集  
 如果你**SelectCommand**返回多个表，**填充**自动生成具有递增的值中的表的表名称**数据集**，第一页为在窗体上指定表名称和继续**TableName** *N*，第一页为**TableName1**。 你可以使用表映射将自动生成的表名称映射到要为表中指定的名称**数据集**。 例如，对于**SelectCommand**返回两个表，**客户**和**订单**，发出以下调用**填充**。  
  
```  
adapter.Fill(customersDataSet, "Customers")  
```  
  
 在创建两个表**数据集**:**客户**和**Customers1**。 你可以使用表映射以确保第二个表名为**订单**而不是**Customers1**。 若要执行此操作，将映射的源表**Customers1**到**数据集**表**订单**，下面的示例中所示。  
  
```  
adapter.TableMappings.Add("Customers1", "Orders")  
adapter.Fill(customersDataSet, "Customers")  
```  
  
## <a name="see-also"></a>请参阅  
 [DataAdapters 和 DataReaders](../../../../docs/framework/data/adonet/dataadapters-and-datareaders.md)  
 [在 ADO.NET 中检索和修改数据](../../../../docs/framework/data/adonet/retrieving-and-modifying-data.md)  
 [ADO.NET 托管提供程序和数据集开发人员中心](http://go.microsoft.com/fwlink/?LinkId=217917)
