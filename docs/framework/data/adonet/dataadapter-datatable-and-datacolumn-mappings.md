---
title: DataAdapter 数据表和 DataColumn 映射
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: d023260a-a66a-4c39-b8f4-090cd130e730
ms.openlocfilehash: 6380dd0512bd7834f50b87f90f445cb01b7a8b95
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2020
ms.locfileid: "79151554"
---
# <a name="dataadapter-datatable-and-datacolumn-mappings"></a>DataAdapter 数据表和 DataColumn 映射
**DataAdapter**在其**表映射**属性中包含零个或多个<xref:System.Data.Common.DataTableMapping>对象的集合。 **DataTableMapping**在从针对数据源的查询返回的数据和 之间提供主映射<xref:System.Data.DataTable>。 **数据表映射**名称可以代替**数据表**名称传递给**数据适配器**的**填充**方法。 下面的示例为 **"作者"** 表创建名为 **"作者映射"****的数据表映射**。  
  
```vb  
workAdapter.TableMappings.Add("AuthorsMapping", "Authors")  
```  
  
```csharp  
workAdapter.TableMappings.Add("AuthorsMapping", "Authors");  
```  
  
 **DataTable 映射**使您能够在**DataTable**中使用与数据库中不同的列名称。 **数据适配器**在更新表时使用映射与列匹配。  
  
 如果在调用**DataAdapter**的**填充**或**更新**方法时未指定**表名**或**DataTable 映射**名称，**则数据适配器**将查找名为"表"**的数据表映射**。 如果**数据表映射**不存在，**则数据表**的**表名称**为"表"。 您可以通过创建名称为"表"**的数据表映射**来指定默认**数据表映射**。  
  
 以下代码示例创建**DataTable 映射**（从<xref:System.Data.Common>命名空间），并通过将其命名为"表"使其成为指定**DataAdapter**的默认映射。 然后，该示例将查询结果中的第一个表（**北风**数据库**的客户**表）中的列映射到<xref:System.Data.DataSet>中的**北风客户**表中的一组更用户友好的名称。 对于未映射的列，将使用数据源中的列名称。  
  
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
  
 在更高级的情况下，您可以决定希望相同的**DataAdapter**支持使用不同的映射加载不同的表。 为此，只需添加其他**DataTable 映射**对象即可。  
  
 当**填充**方法传递**DataSet**实例和**DataTable 映射**名称时，如果存在具有该名称的映射，则使用该映射;如果使用填充方法。否则，将使用具有该名称**的数据表**。  
  
 以下示例创建一个**数据表映射**，其名称为**客户**，数据**表**名称为**BizTalkSchema**。 然后，该示例将 SELECT 语句返回的行映射到**BizTalkSchema** **数据表**。  
  
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
> 如果没有为列映射提供源列名称或者没有为表映射提供源表名称，则将自动生成默认名称。 如果未为列映射提供源列，则为列映射指定一个增量默认名称**SourceColumn** *N，* 从**SourceColumn1**开始。 如果表映射未提供源表名称，则表映射将给出**源表** *N*的增量默认名称，从**SourceTable1**开始。  
  
> [!NOTE]
> 我们建议您避免为列映射而避免**SourceColumn** *N*的命名约定，或者为表映射保留**SourceTable** *N，* 因为提供的名称可能与**DataTableMapping 集合**中的**列映射集合**或表映射名称中的现有默认列映射名称冲突。 如果提供的名称已经存在，将引发异常。  
  
## <a name="handling-multiple-result-sets"></a>处理多个结果集  
 如果**SelectCommand**返回多个表，**则填充**将自动生成具有**DataSet**中表的增量值的表名称，从指定的表名称开始，并在表**Name** *N*窗体中继续，从**表Name1**开始。 可以使用表映射将自动生成的表名称映射到您希望在**DataSet**中为表指定的名称。 例如，对于返回两个表"**客户**和**订单**"的**SelectCommand，** 发出以下调用**Fill**。  
  
```vb  
adapter.Fill(customersDataSet, "Customers")  
```  

```csharp  
adapter.Fill(customersDataSet, "Customers");  
```  

 在**DataSet**中创建了两个表：**客户**和**客户1**。 可以使用表映射来确保第二个表名为 **"订单"** 而不是 **"客户1"。** 为此，将**客户 1**的源表映射到**DataSet**表**订单**，如以下示例所示。  
  
```vb  
adapter.TableMappings.Add("Customers1", "Orders")  
adapter.Fill(customersDataSet, "Customers")  
```  

```csharp  
adapter.TableMappings.Add("Customers1", "Orders");  
adapter.Fill(customersDataSet, "Customers");  
```
  
## <a name="see-also"></a>另请参阅

- [DataAdapters 和 DataReaders](dataadapters-and-datareaders.md)
- [在 ADO.NET 中检索和修改数据](retrieving-and-modifying-data.md)
- [ADO.NET 概述](ado-net-overview.md)
