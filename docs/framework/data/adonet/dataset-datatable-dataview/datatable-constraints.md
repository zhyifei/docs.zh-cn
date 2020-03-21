---
title: 数据表约束
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 27c9f2fd-f64d-4b4e-bbf6-1d24f47067cb
ms.openlocfilehash: 4b7972c281786a4e36d0e9c1e455776a293423ee
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2020
ms.locfileid: "79151281"
---
# <a name="datatable-constraints"></a>数据表约束
为了维护数据的完整性，可以使用约束来对 <xref:System.Data.DataTable> 中的数据施加限制。 约束是应用于某列或相关各列的自动规则，它决定了某行的值以某种方式更改时的操作过程。 当 的属性`System.Data.DataSet.EnforceConstraints`<xref:System.Data.DataSet>**为 true**时，将强制执行约束。 有关显示如何设置 `EnforceConstraints` 属性的代码示例，请参见 <xref:System.Data.DataSet.EnforceConstraints%2A> 参考主题。  
  
 ADO.NET 中有两种约束：<xref:System.Data.ForeignKeyConstraint> 和 <xref:System.Data.UniqueConstraint>。 默认情况下，当您通过向<xref:System.Data.DataRelation>**DataSet**添加 创建 两个或多个表之间的关系时，将自动创建这两个约束。 但是，您可以通过在创建关系时指定**创建约束** = **为 false**来禁用此行为。  
  
## <a name="foreignkeyconstraint"></a>ForeignKeyConstraint  
 **外键约束**强制实施有关如何传播相关表的更新和删除的规则。 例如，如果更新或删除一个表行中的值，并且同一值也用于一个或多个相关表，**则外键约束**将确定相关表中发生的情况。  
  
 **外键约束**的<xref:System.Data.ForeignKeyConstraint.DeleteRule%2A>和<xref:System.Data.ForeignKeyConstraint.UpdateRule%2A>属性定义用户尝试删除或更新相关表中的行时要执行的操作。 下表描述了**外键约束**的**DeleteRule**和**UpdateRule**属性可用的不同设置。  
  
|规则设置|说明|  
|------------------|-----------------|  
|**级 联**|删除或更新相关的行。|  
|**SetNull**|将相关行中的值设置为**DBNull**。|  
|**SetDefault**|将相关行中的值设置为默认值。|  
|**无**|对相关行不执行任何操作。 这是默认值。|  
  
 **外键约束**可以限制并传播对相关列的更改。 根据为列的**外键约束**设置的属性，如果**DataSet**的**强制约束**属性**为 true，** 则对父行执行某些操作将导致异常。 例如，如果**外键约束**的**DeleteRule**属性为 **"无**"，则如果父行具有任何子行，则无法删除该行。  
  
 可以使用**外键约束**构造函数在单个列之间或列数组之间创建外键约束。 将生成的**外键约束**对象传递给**表的约束属性**的**Add**方法，该方法是**约束集合**。 还可以将构造函数参数传递给**约束集合**的**Add**方法的几个重载，以创建**外键约束**。  
  
 创建**外键约束**时，可以将**DeleteRule**和**UpdateRule**值作为参数传递给构造函数，也可以将它们设置为属性，如以下示例（其中**DeleteRule**值设置为 **"无**" ）。  
  
```vb  
Dim custOrderFK As ForeignKeyConstraint = New ForeignKeyConstraint("CustOrderFK", _  
  custDS.Tables("CustTable").Columns("CustomerID"), _  
  custDS.Tables("OrdersTable").Columns("CustomerID"))  
custOrderFK.DeleteRule = Rule.None
' Cannot delete a customer value that has associated existing orders.  
custDS.Tables("OrdersTable").Constraints.Add(custOrderFK)  
```  
  
```csharp  
ForeignKeyConstraint custOrderFK = new ForeignKeyConstraint("CustOrderFK",  
  custDS.Tables["CustTable"].Columns["CustomerID"],
  custDS.Tables["OrdersTable"].Columns["CustomerID"]);  
custOrderFK.DeleteRule = Rule.None;
// Cannot delete a customer value that has associated existing orders.  
custDS.Tables["OrdersTable"].Constraints.Add(custOrderFK);  
```  
  
### <a name="acceptrejectrule"></a>AcceptRejectRule  
 可以使用 **"接受更改**"方法接受对行的更改，或使用**数据集**、**数据表**或 DataRow 的**拒绝更改**方法取消对行**的更改**。 当**数据集**包含**外键约束**时，调用 **"接受更改**"或 **"拒绝更改"** 方法将强制执行 **"接受拒绝规则**"。 **外键约束**的 **"接受拒绝规则"** 属性确定在父行上调用 **"接受更改**"或 **"拒绝更改**"时将对子行执行哪些操作。  
  
 下表列出了 **"接受拒绝规则**"的可用设置。  
  
|规则设置|说明|  
|------------------|-----------------|  
|**级 联**|接受或拒绝对子行的更改。|  
|**无**|对子行不执行任何操作。 这是默认值。|  
  
### <a name="example"></a>示例  
 下面的示例创建一个 <xref:System.Data.ForeignKeyConstraint>，设置它的一些属性（包括 <xref:System.Data.ForeignKeyConstraint.AcceptRejectRule%2A>），并将它添加到 <xref:System.Data.ConstraintCollection> 对象的 <xref:System.Data.DataTable>。  
  
 [!code-csharp[DataWorks Data.AcceptRejectRule#1](../../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks Data.AcceptRejectRule/CS/source.cs#1)]
 [!code-vb[DataWorks Data.AcceptRejectRule#1](../../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks Data.AcceptRejectRule/VB/source.vb#1)]  
  
## <a name="uniqueconstraint"></a>UniqueConstraint  
 **唯一约束**对象可以分配给单个列或**DataTable**中的列数组，可确保指定列或列中的所有数据每行都是唯一的。 可以使用**唯一约束**构造函数为列或列数组创建唯一约束。 将生成的**唯一约束**对象传递给**表的约束属性**的**Add**方法，该方法是**约束集合**。 还可以将构造函数参数传递给**约束集合**的**Add**方法的几个重载，以创建**唯一约束**。 为列或列创建**唯一约束**时，可以选择指定列或列是主键。  
  
 还可以通过将列**的唯一**属性设置为**true，** 为列创建唯一约束。 或者，将单个列**的唯一**属性设置为**false**将删除可能存在的任何唯一约束。 如果将一列或多列定义为表的主键，会自动为一个或多个指定的列创建唯一的约束。 如果从**DataTable****的主键**属性中删除列，则将删除**唯一约束**。  
  
 下面的示例为**DataTable**的两列创建**唯一约束**。  
  
```vb  
Dim custTable As DataTable = custDS.Tables("Customers")  
Dim custUnique As UniqueConstraint = _  
    New UniqueConstraint(New DataColumn()   {custTable.Columns("CustomerID"), _  
    custTable.Columns("CompanyName")})  
custDS.Tables("Customers").Constraints.Add(custUnique)  
```  
  
```csharp  
DataTable custTable = custDS.Tables["Customers"];  
UniqueConstraint custUnique = new UniqueConstraint(new DataColumn[]
    {custTable.Columns["CustomerID"],
    custTable.Columns["CompanyName"]});  
custDS.Tables["Customers"].Constraints.Add(custUnique);  
```  
  
## <a name="see-also"></a>另请参阅

- <xref:System.Data.DataRelation>
- <xref:System.Data.DataTable>
- <xref:System.Data.ForeignKeyConstraint>
- <xref:System.Data.UniqueConstraint>
- [数据表架构定义](datatable-schema-definition.md)
- [数据集、数据表和数据视图](index.md)
- [ADO.NET 概述](../ado-net-overview.md)
