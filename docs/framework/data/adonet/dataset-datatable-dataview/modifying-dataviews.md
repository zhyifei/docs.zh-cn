---
title: 修改 DataView
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 697a3991-b660-4a5a-8a54-1a2304ff158e
ms.openlocfilehash: 3663b0317176495b13b1092652bd8bf4c79f30d2
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/03/2018
ms.locfileid: "32760097"
---
# <a name="modifying-dataviews"></a>修改 DataView
可以使用 <xref:System.Data.DataView> 在基础表中添加、删除或修改数据行。 能够使用**DataView**修改基础表中的数据通过设置三个布尔值属性之一控制**DataView**。 这三个属性是 <xref:System.Data.DataView.AllowNew%2A>、<xref:System.Data.DataView.AllowEdit%2A> 和 <xref:System.Data.DataView.AllowDelete%2A>。 它们将设置为**true**默认情况下。  
  
 如果**AllowNew**是**true**，你可以使用<xref:System.Data.DataView.AddNew%2A>方法**DataView**创建新<xref:System.Data.DataRowView>。 请注意，新行不会实际添加到基础<xref:System.Data.DataTable>直到<xref:System.Data.DataRowView.EndEdit%2A>方法**DataRowView**调用。 如果<xref:System.Data.DataRowView.CancelEdit%2A>方法**DataRowView**是调用，将丢弃新行。 还要注意，您可以编辑只有一个**DataRowView**一次。 如果调用**AddNew**或**BeginEdit**方法**DataRowView**虽然存在挂起行， **EndEdit**对隐式调用挂起的行。 当**EndEdit**是调用，所做的更改应用于基础**DataTable**和更高版本可以提交或拒绝使用**AcceptChanges**或**RejectChanges**方法**DataTable**，**数据集**，或**DataRow**对象。 如果**AllowNew**是**false**，如果调用引发异常**AddNew**方法**DataRowView**。  
  
 如果**AllowEdit**是**true**，你可以修改的内容**DataRow**通过**DataRowView**。 你可以确认对基础行使用的更改**DataRowView.EndEdit**或拒绝更改使用**DataRowView.CancelEdit**。 注意，一次只能编辑一行。 如果调用**AddNew**或**BeginEdit**方法**DataRowView**虽然存在挂起行， **EndEdit**对隐式调用挂起的行。 当**EndEdit**调用时，建议的更改都将置于**当前**的基础的行版本**DataRow**和更高版本可以提交或拒绝使用**AcceptChanges**或**RejectChanges**方法**DataTable**，**数据集**，或**DataRow**对象。 如果**AllowEdit**是**false**，如果您尝试修改中的值将引发异常**DataView**。  
  
 如果现有**DataRowView**正在编辑的基础事件**DataTable**仍将引发与建议的更改。 请注意，如果你调用**EndEdit**或**CancelEdit**基础**DataRow**、 挂起的更改将应用或取消而不管是否**EndEdit**或**CancelEdit**上调用**DataRowView**。  
  
 如果**AllowDelete**是**true**，你可以删除行从**DataView**使用**删除**方法**DataView**或**DataRowView**从基础删除对象，并且行**DataTable**。 以后可以提交或拒绝删除使用**AcceptChanges**或**RejectChanges**分别。 如果**AllowDelete**是**false**，如果调用引发异常**删除**方法**DataView**或**DataRowView**。  
  
 下面的代码示例禁用通过**DataView**到删除的行，并将新行添加到基础表使用**DataView**。  
  
```vb  
Dim custTable As DataTable = custDS.Tables("Customers")  
Dim custView As DataView = custTable.DefaultView  
custView.Sort = "CompanyName"  
  
custView.AllowDelete = False  
  
Dim newDRV As DataRowView = custView.AddNew()  
newDRV("CustomerID") = "ABCDE"  
newDRV("CompanyName") = "ABC Products"  
newDRV.EndEdit()  
```  
  
```csharp  
DataTable custTable = custDS.Tables["Customers"];  
DataView custView = custTable.DefaultView;  
custView.Sort = "CompanyName";  
  
custView.AllowDelete = false;  
  
DataRowView newDRV = custView.AddNew();  
newDRV["CustomerID"] = "ABCDE";  
newDRV["CompanyName"] = "ABC Products";  
newDRV.EndEdit();  
```  
  
## <a name="see-also"></a>请参阅  
 <xref:System.Data.DataTable>  
 <xref:System.Data.DataView>  
 <xref:System.Data.DataRowView>  
 [数据视图](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/dataviews.md)  
 [ADO.NET 托管提供程序和数据集开发人员中心](http://go.microsoft.com/fwlink/?LinkId=217917)
