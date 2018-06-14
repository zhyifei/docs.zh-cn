---
title: 向数据表添加列
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: e85c4a0e-4f3f-458c-b58b-0ddbc06bf974
ms.openlocfilehash: 8ee47ddce273e564673d96d2b2e276b68879373f
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/03/2018
ms.locfileid: "32760461"
---
# <a name="adding-columns-to-a-datatable"></a>向数据表添加列
A<xref:System.Data.DataTable>包含一套<xref:System.Data.DataColumn>所引用的对象**列**的表的属性。 这个列的集合与任何约束一起定义表的架构（即结构）。  
  
 你创建**DataColumn**通过使用表中的对象**DataColumn**构造函数，或通过调用**添加**方法**列**属性表，这是<xref:System.Data.DataColumnCollection>。 **添加**方法将接受可选**ColumnName**， **DataType**，和**表达式**自变量，并创建新**DataColumn**作为集合的成员。 它还会接受现有**DataColumn**对象并将其添加到集合，并返回对所添加的引用**DataColumn**如果请求。 因为**DataTable**对象不是特定于任何数据源、 指定的数据类型时使用.NET Framework 类型**DataColumn**。  
  
 下面的示例将添加到四个列**DataTable**。  
  
```vb  
Dim workTable As DataTable = New DataTable("Customers")  
  
Dim workCol As DataColumn = workTable.Columns.Add( _  
    "CustID", Type.GetType("System.Int32"))  
workCol.AllowDBNull = false  
workCol.Unique = true  
  
workTable.Columns.Add("CustLName", Type.GetType("System.String"))  
workTable.Columns.Add("CustFName", Type.GetType("System.String"))  
workTable.Columns.Add("Purchases", Type.GetType("System.Double"))  
```  
  
```csharp  
DataTable workTable = new DataTable("Customers");  
  
DataColumn workCol = workTable.Columns.Add("CustID", typeof(Int32));  
workCol.AllowDBNull = false;  
workCol.Unique = true;  
  
workTable.Columns.Add("CustLName", typeof(String));  
workTable.Columns.Add("CustFName", typeof(String));  
workTable.Columns.Add("Purchases", typeof(Double));  
```  
  
 在示例中，请注意，属性**CustID**列设置为不允许**DBNull**值并将值是唯一约束。 但是，如果你定义**CustID**为主密钥列的表、 列**AllowDBNull**属性将自动设置为**false**和**Unique**属性将自动设置为**true**。 有关详细信息，请参阅[定义主键](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/defining-primary-keys.md)。  
  
> [!CAUTION]
>  如果列名称未提供的列，该列会得到递增的默认名称的列*N，* 从"Column1"开始，当它添加到**DataColumnCollection**。 我们建议你避免的命名约定"列*N*"时提供的列名，因为提供的名称可能与中的现有默认列名称相冲突**DataColumnCollection**。 如果提供的名称已经存在，将引发异常。  
  
 如果将 <xref:System.Xml.Linq.XElement> 用作 <xref:System.Data.DataColumn.DataType%2A> 中的 <xref:System.Data.DataColumn> 的 <xref:System.Data.DataTable>，则在读入数据时，XML 序列化将不起作用。 例如，如果通过使用 <xref:System.Xml.XmlDocument> 方法来写出 `DataTable.WriteXml`，则在序列化为 XML 时，<xref:System.Xml.Linq.XElement> 中会出现一个额外的父节点。 若要解决此问题，请使用 <xref:System.Data.SqlTypes.SqlXml> 类型来代替 <xref:System.Xml.Linq.XElement>。 `ReadXml` 和 `WriteXml` 对 <xref:System.Data.SqlTypes.SqlXml> 均能正确使用。  
  
## <a name="see-also"></a>请参阅  
 <xref:System.Data.DataColumn>  
 <xref:System.Data.DataColumnCollection>  
 <xref:System.Data.DataTable>  
 [数据表架构定义](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/datatable-schema-definition.md)  
 [数据表](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/datatables.md)  
 [ADO.NET 托管提供程序和数据集开发人员中心](http://go.microsoft.com/fwlink/?LinkId=217917)
