---
title: AcceptChange 和 RejectChange
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: e2d1a6fe-31f9-4b83-9728-06c406a3394e
ms.openlocfilehash: a8589b157bc2579a03d856b73802abc9a4b42855
ms.sourcegitcommit: 2d792961ed48f235cf413d6031576373c3050918
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/31/2019
ms.locfileid: "70204075"
---
# <a name="acceptchanges-and-rejectchanges"></a><span data-ttu-id="e7ba0-102">AcceptChange 和 RejectChange</span><span class="sxs-lookup"><span data-stu-id="e7ba0-102">AcceptChanges and RejectChanges</span></span>
<span data-ttu-id="e7ba0-103">在<xref:System.Data.DataTable>验证对中的数据所做更改的准确性之后, 您可以<xref:System.Data.DataRow> <xref:System.Data.DataRow.AcceptChanges%2A>使用、 <xref:System.Data.DataTable>或<xref:System.Data.DataSet>的方法接受更改, 这会将**当前**行值设置为**原始**值并将**RowState**属性设置为**不变**。</span><span class="sxs-lookup"><span data-stu-id="e7ba0-103">After verifying the accuracy of changes made to data in a <xref:System.Data.DataTable>, you can accept the changes using the <xref:System.Data.DataRow.AcceptChanges%2A> method of the <xref:System.Data.DataRow>, <xref:System.Data.DataTable>, or <xref:System.Data.DataSet>, which will set the **Current** row values to be the **Original** values and will set the **RowState** property to **Unchanged**.</span></span> <span data-ttu-id="e7ba0-104">接受或拒绝更改将清除所有**RowError**信息, 并将**HasErrors**属性设置为**false**。</span><span class="sxs-lookup"><span data-stu-id="e7ba0-104">Accepting or rejecting changes clears out any **RowError** information and sets the **HasErrors** property to **false**.</span></span> <span data-ttu-id="e7ba0-105">接受或拒绝更改还可以影响在数据源中更新数据。</span><span class="sxs-lookup"><span data-stu-id="e7ba0-105">Accepting or rejecting changes can also affect updating data in the data source.</span></span> <span data-ttu-id="e7ba0-106">有关详细信息, 请参阅[用 Dataadapter 更新数据源](../updating-data-sources-with-dataadapters.md)。</span><span class="sxs-lookup"><span data-stu-id="e7ba0-106">For more information, see [Updating Data Sources with DataAdapters](../updating-data-sources-with-dataadapters.md).</span></span>  
  
 <span data-ttu-id="e7ba0-107">如果**DataTable**中存在外键约束, 则使用**AcceptChanges**和**RejectChanges**接受或拒绝的更改会根据 **ForeignKeyConstraint. AcceptRejectRule**。</span><span class="sxs-lookup"><span data-stu-id="e7ba0-107">If foreign key constraints exist on the **DataTable**, changes accepted or rejected using **AcceptChanges** and **RejectChanges** are propagated to child rows of the **DataRow** according to the **ForeignKeyConstraint.AcceptRejectRule**.</span></span> <span data-ttu-id="e7ba0-108">有关详细信息, 请参阅[DataTable 约束](datatable-constraints.md)。</span><span class="sxs-lookup"><span data-stu-id="e7ba0-108">For more information, see [DataTable Constraints](datatable-constraints.md).</span></span>  
  
 <span data-ttu-id="e7ba0-109">以下示例检查有错误的行，如果可以会解决错误，拒绝无法解决错误的行。</span><span class="sxs-lookup"><span data-stu-id="e7ba0-109">The following example checks for rows with errors, resolves the errors where applicable, and rejects the rows where the error cannot be resolved.</span></span> <span data-ttu-id="e7ba0-110">请注意, 对于已解决的错误, **RowError**值会重置为空字符串, 导致**HasErrors**属性设置为**false**。</span><span class="sxs-lookup"><span data-stu-id="e7ba0-110">Note that, for resolved errors, the **RowError** value is reset to an empty string, causing the **HasErrors** property to be set to **false**.</span></span> <span data-ttu-id="e7ba0-111">在已解决或拒绝所有包含错误的行时, 将调用**AcceptChanges**来接受对整个**DataTable**的所有更改。</span><span class="sxs-lookup"><span data-stu-id="e7ba0-111">When all the rows with errors have been resolved or rejected, **AcceptChanges** is called to accept all changes for the entire **DataTable**.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="e7ba0-112">请参阅</span><span class="sxs-lookup"><span data-stu-id="e7ba0-112">See also</span></span>

- <xref:System.Data.DataRow>
- <xref:System.Data.DataSet>
- <xref:System.Data.DataTable>
- [<span data-ttu-id="e7ba0-113">操作数据表中的数据</span><span class="sxs-lookup"><span data-stu-id="e7ba0-113">Manipulating Data in a DataTable</span></span>](manipulating-data-in-a-datatable.md)
- [<span data-ttu-id="e7ba0-114">ADO.NET 托管提供程序和数据集开发人员中心</span><span class="sxs-lookup"><span data-stu-id="e7ba0-114">ADO.NET Managed Providers and DataSet Developer Center</span></span>](https://go.microsoft.com/fwlink/?LinkId=217917)
