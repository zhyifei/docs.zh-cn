---
title: 创建数据视图
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: b1cc02d1-23b1-4439-a998-0da1899f3442
ms.openlocfilehash: 3e1c31dac458594eee70ddd99469aca7cf63b848
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/07/2019
ms.locfileid: "70785486"
---
# <a name="creating-a-dataview"></a><span data-ttu-id="0bb56-102">创建数据视图</span><span class="sxs-lookup"><span data-stu-id="0bb56-102">Creating a DataView</span></span>
<span data-ttu-id="0bb56-103">创建 <xref:System.Data.DataView> 的方法有两种。</span><span class="sxs-lookup"><span data-stu-id="0bb56-103">There are two ways to create a <xref:System.Data.DataView>.</span></span> <span data-ttu-id="0bb56-104">您可以使用**DataView**构造函数，也可以创建对<xref:System.Data.DataTable.DefaultView%2A>的属性<xref:System.Data.DataTable>的引用。</span><span class="sxs-lookup"><span data-stu-id="0bb56-104">You can use the **DataView** constructor, or you can create a reference to the <xref:System.Data.DataTable.DefaultView%2A> property of the <xref:System.Data.DataTable>.</span></span> <span data-ttu-id="0bb56-105">**DataView**构造函数可以为空，也可以采用**datatable**作为单个参数，或将**datatable**与筛选条件、排序条件和行状态筛选器一起使用。</span><span class="sxs-lookup"><span data-stu-id="0bb56-105">The **DataView** constructor can be empty, or it can take either a **DataTable** as a single argument, or a **DataTable** along with filter criteria, sort criteria, and a row state filter.</span></span> <span data-ttu-id="0bb56-106">有关可用于**DataView**的其他参数的详细信息，请参阅对[数据进行排序和筛选](sorting-and-filtering-data.md)。</span><span class="sxs-lookup"><span data-stu-id="0bb56-106">For more information about the additional arguments available for use with the **DataView**, see [Sorting and Filtering Data](sorting-and-filtering-data.md).</span></span>  
  
 <span data-ttu-id="0bb56-107">由于在创建**dataview**时以及在修改任何**Sort**、 **RowFilter**或**RowStateFilter**属性时都会生成**dataview**的索引，因此，通过提供任何初始创建**DataView**时，排序顺序或筛选条件为构造函数参数。</span><span class="sxs-lookup"><span data-stu-id="0bb56-107">Because the index for a **DataView** is built both when the **DataView** is created, and when any of the **Sort**, **RowFilter**, or **RowStateFilter** properties are modified, you achieve best performance by supplying any initial sort order or filtering criteria as constructor arguments when you create the **DataView**.</span></span> <span data-ttu-id="0bb56-108">在不指定排序或筛选条件的情况下创建**DataView** ，然后设置**sort**、 **RowFilter**或**RowStateFilter**属性，稍后会导致索引至少生成两次：将**DataView**已创建，并在修改任何排序或筛选属性时重新创建。</span><span class="sxs-lookup"><span data-stu-id="0bb56-108">Creating a **DataView** without specifying sort or filter criteria and then setting the **Sort**, **RowFilter**, or **RowStateFilter** properties later causes the index to be built at least twice: once when the **DataView** is created, and again when any of the sort or filter properties are modified.</span></span>  
  
 <span data-ttu-id="0bb56-109">请注意，如果使用不采用任何参数的构造函数来创建**dataview** ，则在设置**表**属性之前，将无法使用**dataview** 。</span><span class="sxs-lookup"><span data-stu-id="0bb56-109">Note that if you create a **DataView** using the constructor that does not take any arguments, you will not be able to use the **DataView** until you have set the **Table** property.</span></span>  
  
 <span data-ttu-id="0bb56-110">下面的代码示例演示如何使用**dataview**构造函数创建**dataview** 。</span><span class="sxs-lookup"><span data-stu-id="0bb56-110">The following code example demonstrates how to create a **DataView** using the **DataView** constructor.</span></span> <span data-ttu-id="0bb56-111">**RowFilter**、 **Sort**列和**DataViewRowState**随**DataTable**一起提供。</span><span class="sxs-lookup"><span data-stu-id="0bb56-111">A **RowFilter**, **Sort** column, and **DataViewRowState** are supplied along with the **DataTable**.</span></span>  
  
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
  
 <span data-ttu-id="0bb56-112">下面的代码示例演示如何使用表的**DefaultView**属性获取对**DataTable**的默认**DataView**的引用。</span><span class="sxs-lookup"><span data-stu-id="0bb56-112">The following code example demonstrates how to obtain a reference to the default **DataView** of a **DataTable** using the **DefaultView** property of the table.</span></span>  
  
```vb  
Dim custDV As DataView = custDS.Tables("Customers").DefaultView  
```  
  
```csharp  
DataView custDV = custDS.Tables["Customers"].DefaultView;  
```  
  
## <a name="see-also"></a><span data-ttu-id="0bb56-113">请参阅</span><span class="sxs-lookup"><span data-stu-id="0bb56-113">See also</span></span>

- <xref:System.Data.DataTable>
- <xref:System.Data.DataView>
- [<span data-ttu-id="0bb56-114">数据视图</span><span class="sxs-lookup"><span data-stu-id="0bb56-114">DataViews</span></span>](dataviews.md)
- [<span data-ttu-id="0bb56-115">对数据进行排序和筛选</span><span class="sxs-lookup"><span data-stu-id="0bb56-115">Sorting and Filtering Data</span></span>](sorting-and-filtering-data.md)
- [<span data-ttu-id="0bb56-116">数据表</span><span class="sxs-lookup"><span data-stu-id="0bb56-116">DataTables</span></span>](datatables.md)
- [<span data-ttu-id="0bb56-117">ADO.NET 概述</span><span class="sxs-lookup"><span data-stu-id="0bb56-117">ADO.NET Overview</span></span>](../ado-net-overview.md)
