---
title: AcceptChange 和 RejectChange
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: e2d1a6fe-31f9-4b83-9728-06c406a3394e
ms.openlocfilehash: 30b2c303b1823430c480f0706500f8f7e7053c4c
ms.sourcegitcommit: 2350a091ef6459f0fcfd894301242400374d8558
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/21/2018
ms.locfileid: "46531822"
---
# <a name="acceptchanges-and-rejectchanges"></a><span data-ttu-id="794d1-102">AcceptChange 和 RejectChange</span><span class="sxs-lookup"><span data-stu-id="794d1-102">AcceptChanges and RejectChanges</span></span>
<span data-ttu-id="794d1-103">在验证中的数据所做的更改的准确性后<xref:System.Data.DataTable>，可以接受使用的更改<xref:System.Data.DataRow.AcceptChanges%2A>方法<xref:System.Data.DataRow>， <xref:System.Data.DataTable>，或<xref:System.Data.DataSet>，它将设置**当前**行值为**原始**值，并将设置**RowState**属性设置为**Unchanged**。</span><span class="sxs-lookup"><span data-stu-id="794d1-103">After verifying the accuracy of changes made to data in a <xref:System.Data.DataTable>, you can accept the changes using the <xref:System.Data.DataRow.AcceptChanges%2A> method of the <xref:System.Data.DataRow>, <xref:System.Data.DataTable>, or <xref:System.Data.DataSet>, which will set the **Current** row values to be the **Original** values and will set the **RowState** property to **Unchanged**.</span></span> <span data-ttu-id="794d1-104">接受或拒绝更改会清除所有**RowError**信息和集**HasErrors**属性设置为**false**。</span><span class="sxs-lookup"><span data-stu-id="794d1-104">Accepting or rejecting changes clears out any **RowError** information and sets the **HasErrors** property to **false**.</span></span> <span data-ttu-id="794d1-105">接受或拒绝更改还可以影响在数据源中更新数据。</span><span class="sxs-lookup"><span data-stu-id="794d1-105">Accepting or rejecting changes can also affect updating data in the data source.</span></span> <span data-ttu-id="794d1-106">有关详细信息，请参阅[使用 Dataadapter 更新数据源](../../../../../docs/framework/data/adonet/updating-data-sources-with-dataadapters.md)。</span><span class="sxs-lookup"><span data-stu-id="794d1-106">For more information, see [Updating Data Sources with DataAdapters](../../../../../docs/framework/data/adonet/updating-data-sources-with-dataadapters.md).</span></span>  
  
 <span data-ttu-id="794d1-107">如果外键约束上存在**DataTable**，接受或拒绝使用更改**AcceptChanges**并**RejectChanges**传播到子行的**DataRow**根据**就**。</span><span class="sxs-lookup"><span data-stu-id="794d1-107">If foreign key constraints exist on the **DataTable**, changes accepted or rejected using **AcceptChanges** and **RejectChanges** are propagated to child rows of the **DataRow** according to the **ForeignKeyConstraint.AcceptRejectRule**.</span></span> <span data-ttu-id="794d1-108">有关详细信息，请参阅[数据表约束](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/datatable-constraints.md)。</span><span class="sxs-lookup"><span data-stu-id="794d1-108">For more information, see [DataTable Constraints](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/datatable-constraints.md).</span></span>  
  
 <span data-ttu-id="794d1-109">以下示例检查有错误的行，如果可以会解决错误，拒绝无法解决错误的行。</span><span class="sxs-lookup"><span data-stu-id="794d1-109">The following example checks for rows with errors, resolves the errors where applicable, and rejects the rows where the error cannot be resolved.</span></span> <span data-ttu-id="794d1-110">请注意，对于已解决的错误， **RowError**值将重置为空字符串，从而导致**HasErrors**属性设置为**false**。</span><span class="sxs-lookup"><span data-stu-id="794d1-110">Note that, for resolved errors, the **RowError** value is reset to an empty string, causing the **HasErrors** property to be set to **false**.</span></span> <span data-ttu-id="794d1-111">当已解决或拒绝，但出现错误的所有行**AcceptChanges**调用以接受所有的更改的整个**DataTable**。</span><span class="sxs-lookup"><span data-stu-id="794d1-111">When all the rows with errors have been resolved or rejected, **AcceptChanges** is called to accept all changes for the entire **DataTable**.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="794d1-112">请参阅</span><span class="sxs-lookup"><span data-stu-id="794d1-112">See Also</span></span>  
 <xref:System.Data.DataRow>  
 <xref:System.Data.DataSet>  
 <xref:System.Data.DataTable>  
 [<span data-ttu-id="794d1-113">操作数据表中的数据</span><span class="sxs-lookup"><span data-stu-id="794d1-113">Manipulating Data in a DataTable</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/manipulating-data-in-a-datatable.md)  
 [<span data-ttu-id="794d1-114">ADO.NET 托管提供程序和数据集开发人员中心</span><span class="sxs-lookup"><span data-stu-id="794d1-114">ADO.NET Managed Providers and DataSet Developer Center</span></span>](https://go.microsoft.com/fwlink/?LinkId=217917)
