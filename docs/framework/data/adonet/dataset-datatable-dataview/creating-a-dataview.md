---
title: 创建数据视图
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: b1cc02d1-23b1-4439-a998-0da1899f3442
ms.openlocfilehash: 9d21b17068ff3ce5b0bd3990144383d7f9ded2f9
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2020
ms.locfileid: "79151333"
---
# <a name="creating-a-dataview"></a><span data-ttu-id="8b834-102">创建数据视图</span><span class="sxs-lookup"><span data-stu-id="8b834-102">Creating a DataView</span></span>
<span data-ttu-id="8b834-103">创建 <xref:System.Data.DataView> 的方法有两种。</span><span class="sxs-lookup"><span data-stu-id="8b834-103">There are two ways to create a <xref:System.Data.DataView>.</span></span> <span data-ttu-id="8b834-104">您可以使用**DataView**构造函数，也可以创建对<xref:System.Data.DataTable.DefaultView%2A>属性<xref:System.Data.DataTable>的引用。</span><span class="sxs-lookup"><span data-stu-id="8b834-104">You can use the **DataView** constructor, or you can create a reference to the <xref:System.Data.DataTable.DefaultView%2A> property of the <xref:System.Data.DataTable>.</span></span> <span data-ttu-id="8b834-105">**DataView**构造函数可以是空的，也可以将**DataTable**作为单个参数，也可以将 DataTable 以及筛选器条件、排序条件和行状态筛选器视为 **"DataTable"。**</span><span class="sxs-lookup"><span data-stu-id="8b834-105">The **DataView** constructor can be empty, or it can take either a **DataTable** as a single argument, or a **DataTable** along with filter criteria, sort criteria, and a row state filter.</span></span> <span data-ttu-id="8b834-106">有关可用于**DataView**的其他参数的详细信息，请参阅[排序和筛选数据](sorting-and-filtering-data.md)。</span><span class="sxs-lookup"><span data-stu-id="8b834-106">For more information about the additional arguments available for use with the **DataView**, see [Sorting and Filtering Data](sorting-and-filtering-data.md).</span></span>  
  
 <span data-ttu-id="8b834-107">由于**DataView**的索引是在创建**DataView**时构建的，并且当修改任何**排序**、**行筛选器**或**RowStateFilter**属性时，在创建**DataView**时，通过提供任何初始排序顺序或筛选条件作为构造函数参数来实现最佳性能。</span><span class="sxs-lookup"><span data-stu-id="8b834-107">Because the index for a **DataView** is built both when the **DataView** is created, and when any of the **Sort**, **RowFilter**, or **RowStateFilter** properties are modified, you achieve best performance by supplying any initial sort order or filtering criteria as constructor arguments when you create the **DataView**.</span></span> <span data-ttu-id="8b834-108">创建**DataView**而不指定排序或筛选条件，然后设置**排序**、**行筛选器**或**RowStateFilter**属性，以后会导致索引至少生成两次：创建**DataView**时生成一次，在修改任何排序或筛选器属性时再次生成索引。</span><span class="sxs-lookup"><span data-stu-id="8b834-108">Creating a **DataView** without specifying sort or filter criteria and then setting the **Sort**, **RowFilter**, or **RowStateFilter** properties later causes the index to be built at least twice: once when the **DataView** is created, and again when any of the sort or filter properties are modified.</span></span>  
  
 <span data-ttu-id="8b834-109">请注意，如果使用不采用任何参数的构造函数创建**DataView，** 则在设置**表**属性之前，您将无法使用**DataView。**</span><span class="sxs-lookup"><span data-stu-id="8b834-109">Note that if you create a **DataView** using the constructor that does not take any arguments, you will not be able to use the **DataView** until you have set the **Table** property.</span></span>  
  
 <span data-ttu-id="8b834-110">以下代码示例演示如何使用**DataView**构造函数创建**DataView。**</span><span class="sxs-lookup"><span data-stu-id="8b834-110">The following code example demonstrates how to create a **DataView** using the **DataView** constructor.</span></span> <span data-ttu-id="8b834-111">随**数据表**一起提供**行筛选器**、**排序**列和**DataViewRowState。**</span><span class="sxs-lookup"><span data-stu-id="8b834-111">A **RowFilter**, **Sort** column, and **DataViewRowState** are supplied along with the **DataTable**.</span></span>  
  
```vb  
Dim custDV As DataView = New DataView(custDS.Tables("Customers"), _  
    "Country = 'USA'", _  
    "ContactName", _  
    DataViewRowState.CurrentRows)  
```  
  
```csharp  
DataView custDV = new DataView(custDS.Tables["Customers"],
    "Country = 'USA'",
    "ContactName",
    DataViewRowState.CurrentRows);  
```  
  
 <span data-ttu-id="8b834-112">以下代码示例演示如何使用表的**DefaultView**属性获取对**DataTable**的默认**DataView**的引用。</span><span class="sxs-lookup"><span data-stu-id="8b834-112">The following code example demonstrates how to obtain a reference to the default **DataView** of a **DataTable** using the **DefaultView** property of the table.</span></span>  
  
```vb  
Dim custDV As DataView = custDS.Tables("Customers").DefaultView  
```  
  
```csharp  
DataView custDV = custDS.Tables["Customers"].DefaultView;  
```  
  
## <a name="see-also"></a><span data-ttu-id="8b834-113">另请参阅</span><span class="sxs-lookup"><span data-stu-id="8b834-113">See also</span></span>

- <xref:System.Data.DataTable>
- <xref:System.Data.DataView>
- [<span data-ttu-id="8b834-114">DataView</span><span class="sxs-lookup"><span data-stu-id="8b834-114">DataViews</span></span>](dataviews.md)
- [<span data-ttu-id="8b834-115">对数据进行排序和筛选</span><span class="sxs-lookup"><span data-stu-id="8b834-115">Sorting and Filtering Data</span></span>](sorting-and-filtering-data.md)
- [<span data-ttu-id="8b834-116">DataTables</span><span class="sxs-lookup"><span data-stu-id="8b834-116">DataTables</span></span>](datatables.md)
- [<span data-ttu-id="8b834-117">ADO.NET 概述</span><span class="sxs-lookup"><span data-stu-id="8b834-117">ADO.NET Overview</span></span>](../ado-net-overview.md)
