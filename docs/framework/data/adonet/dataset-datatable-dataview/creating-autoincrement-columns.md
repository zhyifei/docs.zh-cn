---
title: 创建 AutoIncrement 列
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: cf09732a-ab54-4d98-89e2-4d0a1f28fbce
ms.openlocfilehash: 5e4a36829107480a44980c7210b39c21231c67f4
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/07/2019
ms.locfileid: "70786458"
---
# <a name="creating-autoincrement-columns"></a><span data-ttu-id="f48cc-102">创建 AutoIncrement 列</span><span class="sxs-lookup"><span data-stu-id="f48cc-102">Creating AutoIncrement Columns</span></span>
<span data-ttu-id="f48cc-103">要确保列值的唯一，可将列值设置为在表中添加新行时自动递增。</span><span class="sxs-lookup"><span data-stu-id="f48cc-103">To ensure unique column values, you can set the column values to increment automatically when new rows are added to the table.</span></span> <span data-ttu-id="f48cc-104">若要创建自动增量<xref:System.Data.DataColumn>，请<xref:System.Data.DataColumn.AutoIncrement%2A>将列的属性设置为**true**。</span><span class="sxs-lookup"><span data-stu-id="f48cc-104">To create an auto-incrementing <xref:System.Data.DataColumn>, set the <xref:System.Data.DataColumn.AutoIncrement%2A> property of the column to **true**.</span></span> <span data-ttu-id="f48cc-105">然后，在<xref:System.Data.DataColumn.AutoIncrementSeed%2A>属性中定义的值开始，每添加一行，**自动增量**列的值将按列的<xref:System.Data.DataColumn.AutoIncrementStep%2A>属性中定义的值增加。 <xref:System.Data.DataColumn></span><span class="sxs-lookup"><span data-stu-id="f48cc-105">The <xref:System.Data.DataColumn> then starts with the value defined in the <xref:System.Data.DataColumn.AutoIncrementSeed%2A> property, and with each row added the value of the **AutoIncrement** column increases by the value defined in the <xref:System.Data.DataColumn.AutoIncrementStep%2A> property of the column.</span></span>  
  
 <span data-ttu-id="f48cc-106">对于**自动增量**列，建议将<xref:System.Data.DataColumn.ReadOnly%2A> **DataColumn**的属性设置为**true**。</span><span class="sxs-lookup"><span data-stu-id="f48cc-106">For **AutoIncrement** columns, we recommend that the <xref:System.Data.DataColumn.ReadOnly%2A> property of the **DataColumn** be set to **true**.</span></span>  
  
 <span data-ttu-id="f48cc-107">以下示例演示了如何创建从值 200 开始并以 3 为增量递增的列。</span><span class="sxs-lookup"><span data-stu-id="f48cc-107">The following example demonstrates how to create a column that starts with a value of 200 and adds incrementally in steps of 3.</span></span>  
  
```vb  
Dim workColumn As DataColumn = workTable.Columns.Add( _  
    "CustomerID", typeof(Int32))  
workColumn.AutoIncrement = true  
workColumn.AutoIncrementSeed = 200  
workColumn.AutoIncrementStep = 3  
```  
  
```csharp  
DataColumn workColumn = workTable.Columns.Add(  
    "CustomerID", typeof(Int32));  
workColumn.AutoIncrement = true;  
workColumn.AutoIncrementSeed = 200;  
workColumn.AutoIncrementStep = 3;  
```  
  
## <a name="see-also"></a><span data-ttu-id="f48cc-108">请参阅</span><span class="sxs-lookup"><span data-stu-id="f48cc-108">See also</span></span>

- <xref:System.Data.DataColumn>
- [<span data-ttu-id="f48cc-109">数据表架构定义</span><span class="sxs-lookup"><span data-stu-id="f48cc-109">DataTable Schema Definition</span></span>](datatable-schema-definition.md)
- [<span data-ttu-id="f48cc-110">数据表</span><span class="sxs-lookup"><span data-stu-id="f48cc-110">DataTables</span></span>](datatables.md)
- [<span data-ttu-id="f48cc-111">ADO.NET 概述</span><span class="sxs-lookup"><span data-stu-id="f48cc-111">ADO.NET Overview</span></span>](../ado-net-overview.md)
