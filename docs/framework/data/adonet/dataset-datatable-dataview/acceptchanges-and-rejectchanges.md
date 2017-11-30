---
title: "AcceptChange 和 RejectChange"
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
ms.assetid: e2d1a6fe-31f9-4b83-9728-06c406a3394e
caps.latest.revision: "4"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: 6ac64fee869ce58413e799f4217f009ef6ae91a9
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="acceptchanges-and-rejectchanges"></a>AcceptChange 和 RejectChange
在验证中的数据所做的更改的准确性后<xref:System.Data.DataTable>，你可以接受所做的更改使用<xref:System.Data.DataRow.AcceptChanges%2A>方法<xref:System.Data.DataRow>， <xref:System.Data.DataTable>，或<xref:System.Data.DataSet>，它将设置**当前**行值应为**原始**值并将设置**RowState**属性**Unchanged**。 接受或拒绝更改会清除所有**RowError**信息和集**HasErrors**属性**false**。 接受或拒绝更改还可以影响在数据源中更新数据。 有关详细信息，请参阅[使用 Dataadapter 更新数据源](../../../../../docs/framework/data/adonet/updating-data-sources-with-dataadapters.md)。  
  
 如果外键约束上存在**DataTable**，接受或拒绝使用更改**AcceptChanges**和**RejectChanges**传播到子行的**DataRow**根据**ForeignKeyConstraint.AcceptRejectRule**。 有关详细信息，请参阅[数据表约束](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/datatable-constraints.md)。  
  
 以下示例检查有错误的行，如果可以会解决错误，拒绝无法解决错误的行。 请注意，对于解析错误， **RowError**值重置为空字符串，从而导致**HasErrors**属性设置为**false**。 已解决或拒绝，出现错误的所有行时**AcceptChanges**调用以接受所有的更改的整个**DataTable**。  
  
```vb  
If workTable.HasErrors Then  
  Dim errRow As DataRow  
  
  For Each errRow in workTable.GetErrors()  
  
    If errRow.RowError = "Total cannot exceed 1000." Then  
      errRow("Total") = 1000  
      errRow.RowError = ""    ' Clear the error.  
    Else  
      errRow.RejectChanges()  
    End If  
  Next  
End If  
  
workTable.AcceptChanges()  
```  
  
```csharp  
if (workTable.HasErrors)  
{  
  
  foreach (DataRow errRow in workTable.GetErrors())  
  {  
    if (errRow.RowError == "Total cannot exceed 1000.")  
    {  
      errRow["Total"] = 1000;  
      errRow.RowError = "";    // Clear the error.  
    }  
    else  
      errRow.RejectChanges();  
  }  
}  
  
workTable.AcceptChanges();  
```  
  
## <a name="see-also"></a>另请参阅  
 <xref:System.Data.DataRow>  
 <xref:System.Data.DataSet>  
 <xref:System.Data.DataTable>  
 [操作数据表中的数据](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/manipulating-data-in-a-datatable.md)  
 [ADO.NET 托管提供程序和数据集开发人员中心](http://go.microsoft.com/fwlink/?LinkId=217917)
