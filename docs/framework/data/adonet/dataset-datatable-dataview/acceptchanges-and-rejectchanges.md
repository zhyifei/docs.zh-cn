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
# <a name="acceptchanges-and-rejectchanges"></a><span data-ttu-id="204da-102">AcceptChange 和 RejectChange</span><span class="sxs-lookup"><span data-stu-id="204da-102">AcceptChanges and RejectChanges</span></span>
<span data-ttu-id="204da-103">在验证中的数据所做的更改的准确性后<xref:System.Data.DataTable>，你可以接受所做的更改使用<xref:System.Data.DataRow.AcceptChanges%2A>方法<xref:System.Data.DataRow>， <xref:System.Data.DataTable>，或<xref:System.Data.DataSet>，它将设置**当前**行值应为**原始**值并将设置**RowState**属性**Unchanged**。</span><span class="sxs-lookup"><span data-stu-id="204da-103">After verifying the accuracy of changes made to data in a <xref:System.Data.DataTable>, you can accept the changes using the <xref:System.Data.DataRow.AcceptChanges%2A> method of the <xref:System.Data.DataRow>, <xref:System.Data.DataTable>, or <xref:System.Data.DataSet>, which will set the **Current** row values to be the **Original** values and will set the **RowState** property to **Unchanged**.</span></span> <span data-ttu-id="204da-104">接受或拒绝更改会清除所有**RowError**信息和集**HasErrors**属性**false**。</span><span class="sxs-lookup"><span data-stu-id="204da-104">Accepting or rejecting changes clears out any **RowError** information and sets the **HasErrors** property to **false**.</span></span> <span data-ttu-id="204da-105">接受或拒绝更改还可以影响在数据源中更新数据。</span><span class="sxs-lookup"><span data-stu-id="204da-105">Accepting or rejecting changes can also affect updating data in the data source.</span></span> <span data-ttu-id="204da-106">有关详细信息，请参阅[使用 Dataadapter 更新数据源](../../../../../docs/framework/data/adonet/updating-data-sources-with-dataadapters.md)。</span><span class="sxs-lookup"><span data-stu-id="204da-106">For more information, see [Updating Data Sources with DataAdapters](../../../../../docs/framework/data/adonet/updating-data-sources-with-dataadapters.md).</span></span>  
  
 <span data-ttu-id="204da-107">如果外键约束上存在**DataTable**，接受或拒绝使用更改**AcceptChanges**和**RejectChanges**传播到子行的**DataRow**根据**ForeignKeyConstraint.AcceptRejectRule**。</span><span class="sxs-lookup"><span data-stu-id="204da-107">If foreign key constraints exist on the **DataTable**, changes accepted or rejected using **AcceptChanges** and **RejectChanges** are propagated to child rows of the **DataRow** according to the **ForeignKeyConstraint.AcceptRejectRule**.</span></span> <span data-ttu-id="204da-108">有关详细信息，请参阅[数据表约束](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/datatable-constraints.md)。</span><span class="sxs-lookup"><span data-stu-id="204da-108">For more information, see [DataTable Constraints](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/datatable-constraints.md).</span></span>  
  
 <span data-ttu-id="204da-109">以下示例检查有错误的行，如果可以会解决错误，拒绝无法解决错误的行。</span><span class="sxs-lookup"><span data-stu-id="204da-109">The following example checks for rows with errors, resolves the errors where applicable, and rejects the rows where the error cannot be resolved.</span></span> <span data-ttu-id="204da-110">请注意，对于解析错误， **RowError**值重置为空字符串，从而导致**HasErrors**属性设置为**false**。</span><span class="sxs-lookup"><span data-stu-id="204da-110">Note that, for resolved errors, the **RowError** value is reset to an empty string, causing the **HasErrors** property to be set to **false**.</span></span> <span data-ttu-id="204da-111">已解决或拒绝，出现错误的所有行时**AcceptChanges**调用以接受所有的更改的整个**DataTable**。</span><span class="sxs-lookup"><span data-stu-id="204da-111">When all the rows with errors have been resolved or rejected, **AcceptChanges** is called to accept all changes for the entire **DataTable**.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="204da-112">另请参阅</span><span class="sxs-lookup"><span data-stu-id="204da-112">See Also</span></span>  
 <xref:System.Data.DataRow>  
 <xref:System.Data.DataSet>  
 <xref:System.Data.DataTable>  
 [<span data-ttu-id="204da-113">操作数据表中的数据</span><span class="sxs-lookup"><span data-stu-id="204da-113">Manipulating Data in a DataTable</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/manipulating-data-in-a-datatable.md)  
 [<span data-ttu-id="204da-114">ADO.NET 托管提供程序和数据集开发人员中心</span><span class="sxs-lookup"><span data-stu-id="204da-114">ADO.NET Managed Providers and DataSet Developer Center</span></span>](http://go.microsoft.com/fwlink/?LinkId=217917)
