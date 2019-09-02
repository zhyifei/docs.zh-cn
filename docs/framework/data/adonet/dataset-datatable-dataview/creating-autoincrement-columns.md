---
title: 创建 AutoIncrement 列
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: cf09732a-ab54-4d98-89e2-4d0a1f28fbce
ms.openlocfilehash: 2548ad9382b406978dac0a3d366207626278f501
ms.sourcegitcommit: 2d792961ed48f235cf413d6031576373c3050918
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/31/2019
ms.locfileid: "70205132"
---
# <a name="creating-autoincrement-columns"></a><span data-ttu-id="fd62f-102">创建 AutoIncrement 列</span><span class="sxs-lookup"><span data-stu-id="fd62f-102">Creating AutoIncrement Columns</span></span>
<span data-ttu-id="fd62f-103">要确保列值的唯一，可将列值设置为在表中添加新行时自动递增。</span><span class="sxs-lookup"><span data-stu-id="fd62f-103">To ensure unique column values, you can set the column values to increment automatically when new rows are added to the table.</span></span> <span data-ttu-id="fd62f-104">若要创建自动增量<xref:System.Data.DataColumn>, 请<xref:System.Data.DataColumn.AutoIncrement%2A>将列的属性设置为**true**。</span><span class="sxs-lookup"><span data-stu-id="fd62f-104">To create an auto-incrementing <xref:System.Data.DataColumn>, set the <xref:System.Data.DataColumn.AutoIncrement%2A> property of the column to **true**.</span></span> <span data-ttu-id="fd62f-105">然后, 在<xref:System.Data.DataColumn.AutoIncrementSeed%2A>属性中定义的值开始, 每添加一行,**自动增量**列的值将按列的<xref:System.Data.DataColumn.AutoIncrementStep%2A>属性中定义的值增加。 <xref:System.Data.DataColumn></span><span class="sxs-lookup"><span data-stu-id="fd62f-105">The <xref:System.Data.DataColumn> then starts with the value defined in the <xref:System.Data.DataColumn.AutoIncrementSeed%2A> property, and with each row added the value of the **AutoIncrement** column increases by the value defined in the <xref:System.Data.DataColumn.AutoIncrementStep%2A> property of the column.</span></span>  
  
 <span data-ttu-id="fd62f-106">对于**自动增量**列, 建议将<xref:System.Data.DataColumn.ReadOnly%2A> **DataColumn**的属性设置为**true**。</span><span class="sxs-lookup"><span data-stu-id="fd62f-106">For **AutoIncrement** columns, we recommend that the <xref:System.Data.DataColumn.ReadOnly%2A> property of the **DataColumn** be set to **true**.</span></span>  
  
 <span data-ttu-id="fd62f-107">以下示例演示了如何创建从值 200 开始并以 3 为增量递增的列。</span><span class="sxs-lookup"><span data-stu-id="fd62f-107">The following example demonstrates how to create a column that starts with a value of 200 and adds incrementally in steps of 3.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="fd62f-108">请参阅</span><span class="sxs-lookup"><span data-stu-id="fd62f-108">See also</span></span>

- <xref:System.Data.DataColumn>
- [<span data-ttu-id="fd62f-109">数据表架构定义</span><span class="sxs-lookup"><span data-stu-id="fd62f-109">DataTable Schema Definition</span></span>](datatable-schema-definition.md)
- [<span data-ttu-id="fd62f-110">数据表</span><span class="sxs-lookup"><span data-stu-id="fd62f-110">DataTables</span></span>](datatables.md)
- [<span data-ttu-id="fd62f-111">ADO.NET 托管提供程序和数据集开发人员中心</span><span class="sxs-lookup"><span data-stu-id="fd62f-111">ADO.NET Managed Providers and DataSet Developer Center</span></span>](https://go.microsoft.com/fwlink/?LinkId=217917)
