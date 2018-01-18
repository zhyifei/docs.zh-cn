---
title: "创建数据表"
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
ms.assetid: eecf9d78-60e3-4fdc-8de0-e56c13a89414
caps.latest.revision: "4"
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload: dotnet
ms.openlocfilehash: 94fa5507d71fef557baadc6ee8979efeee4acf40
ms.sourcegitcommit: ed26cfef4e18f6d93ab822d8c29f902cff3519d1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/17/2018
---
# <a name="creating-a-datatable"></a>创建数据表
<xref:System.Data.DataTable> 表示一个内存内关系数据的表，可以独立创建和使用，也可以由其他 .NET Framework 对象使用，最常见的情况是作为 <xref:System.Data.DataSet> 的成员使用。  
  
 你可以创建**DataTable**对象使用合适的**DataTable**构造函数。 你可以将其添加到**数据集**使用**添加**方法以将其添加到**DataTable**对象的**表**集合。  
  
 你还可以创建**DataTable**对象内**数据集**使用**填充**或**FillSchema**方法**DataAdapter**对象，或从预定义或推断 XML 架构使用**ReadXml**， **ReadXmlSchema**，或**InferXmlSchema**方法的**数据集**。 请注意，添加之后**DataTable**作为的成员**表**的一个集合**数据集**，不能将其添加到的任何其他表集合**数据集**。  
  
 当你首次创建**DataTable**，它不具有架构 （即结构）。 若要定义表的架构，必须创建并添加<xref:System.Data.DataColumn>对象添加到**列**表的集合。 此外可以定义主键列对于表，并创建并添加**约束**对象添加到**约束**表的集合。 在定义的架构后**DataTable**，您可以通过添加行数据添加到表**DataRow**对象添加到**行**表的集合。  
  
 不要求你提供的值<xref:System.Data.DataTable.TableName%2A>属性在创建时**DataTable**; 你可以在另一个时，指定该属性，或者可以将它保留为空。 但是，当你添加不包含的表时，才**TableName**值赋给**数据集**，表将给定表的递增的默认名称*N*，第一页为 Table0"表"。  
  
> [!NOTE]
>  我们建议你避免"表*N*"命名约定，如果你提供**TableName**值，因为所提供的名称可能与中的现有默认表名称发生冲突**数据集**. 如果提供的名称已经存在，将引发异常。  
  
 下面的示例创建的实例**DataTable**对象并将其分配的名称"Customers。  
  
```vb  
Dim workTable as DataTable = New DataTable("Customers")  
```  
  
```csharp  
DataTable workTable = new DataTable("Customers");  
```  
  
 下面的示例创建的实例**DataTable**通过将其添加到**表**集合**数据集**。  
  
```vb  
Dim customers As DataSet = New DataSet  
Dim customersTable As DataTable = _  
   customers.Tables.Add("CustomersTable")  
```  
  
```csharp  
DataSet customers = new DataSet();  
DataTable customersTable = customers.Tables.Add("CustomersTable");  
```  
  
## <a name="see-also"></a>请参阅  
 <xref:System.Data.DataTable>  
 <xref:System.Data.DataTableCollection>  
 [数据表](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/datatables.md)  
 [从 DataAdapter 填充数据集](../../../../../docs/framework/data/adonet/populating-a-dataset-from-a-dataadapter.md)  
 [从 XML 加载数据集](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/loading-a-dataset-from-xml.md)  
 [从 XML 加载数据集构架信息](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/loading-dataset-schema-information-from-xml.md)  
 [ADO.NET 托管提供程序和数据集开发人员中心](http://go.microsoft.com/fwlink/?LinkId=217917)
