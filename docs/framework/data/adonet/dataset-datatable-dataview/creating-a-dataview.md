---
title: 创建数据视图
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: b1cc02d1-23b1-4439-a998-0da1899f3442
ms.openlocfilehash: d118f97e425782dbdf89c7e5d1eccd4d371b419c
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/03/2018
---
# <a name="creating-a-dataview"></a><span data-ttu-id="b6cdd-102">创建数据视图</span><span class="sxs-lookup"><span data-stu-id="b6cdd-102">Creating a DataView</span></span>
<span data-ttu-id="b6cdd-103">创建 <xref:System.Data.DataView> 的方法有两种。</span><span class="sxs-lookup"><span data-stu-id="b6cdd-103">There are two ways to create a <xref:System.Data.DataView>.</span></span> <span data-ttu-id="b6cdd-104">你可以使用**DataView**构造函数，也可以创建对引用<xref:System.Data.DataTable.DefaultView%2A>属性<xref:System.Data.DataTable>。</span><span class="sxs-lookup"><span data-stu-id="b6cdd-104">You can use the **DataView** constructor, or you can create a reference to the <xref:System.Data.DataTable.DefaultView%2A> property of the <xref:System.Data.DataTable>.</span></span> <span data-ttu-id="b6cdd-105">**DataView**构造函数可以为空，或它可以采用**DataTable**作为单个参数，或**DataTable**与筛选条件、 排序条件和行状态筛选器。</span><span class="sxs-lookup"><span data-stu-id="b6cdd-105">The **DataView** constructor can be empty, or it can take either a **DataTable** as a single argument, or a **DataTable** along with filter criteria, sort criteria, and a row state filter.</span></span> <span data-ttu-id="b6cdd-106">有关用于与一起使用的其他参数的详细信息**DataView**，请参阅[排序和筛选数据](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/sorting-and-filtering-data.md)。</span><span class="sxs-lookup"><span data-stu-id="b6cdd-106">For more information about the additional arguments available for use with the **DataView**, see [Sorting and Filtering Data](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/sorting-and-filtering-data.md).</span></span>  
  
 <span data-ttu-id="b6cdd-107">因为索引**DataView**这两个时，会生成**DataView**创建后，和任何**排序**， **RowFilter**，或**RowStateFilter**属性将被修改，通过提供任何初始排序顺序或筛选条件作为构造函数自变量，在创建时获得最佳性能**DataView**。</span><span class="sxs-lookup"><span data-stu-id="b6cdd-107">Because the index for a **DataView** is built both when the **DataView** is created, and when any of the **Sort**, **RowFilter**, or **RowStateFilter** properties are modified, you achieve best performance by supplying any initial sort order or filtering criteria as constructor arguments when you create the **DataView**.</span></span> <span data-ttu-id="b6cdd-108">创建**DataView**而无需指定排序或筛选条件，然后设置**排序**， **RowFilter**，或**RowStateFilter**属性更高版本使索引生成至少两次： 一次时**DataView**创建后，并且任何排序或筛选器属性再次进行修改时。</span><span class="sxs-lookup"><span data-stu-id="b6cdd-108">Creating a **DataView** without specifying sort or filter criteria and then setting the **Sort**, **RowFilter**, or **RowStateFilter** properties later causes the index to be built at least twice: once when the **DataView** is created, and again when any of the sort or filter properties are modified.</span></span>  
  
 <span data-ttu-id="b6cdd-109">请注意，如果你创建**DataView**使用不采用任何参数的构造函数，你将不能使用**DataView**设置之前**表**属性.</span><span class="sxs-lookup"><span data-stu-id="b6cdd-109">Note that if you create a **DataView** using the constructor that does not take any arguments, you will not be able to use the **DataView** until you have set the **Table** property.</span></span>  
  
 <span data-ttu-id="b6cdd-110">下面的代码示例演示如何创建**DataView**使用**DataView**构造函数。</span><span class="sxs-lookup"><span data-stu-id="b6cdd-110">The following code example demonstrates how to create a **DataView** using the **DataView** constructor.</span></span> <span data-ttu-id="b6cdd-111">A **RowFilter**，**排序**列中，和**DataViewRowState**连同提供**DataTable**。</span><span class="sxs-lookup"><span data-stu-id="b6cdd-111">A **RowFilter**, **Sort** column, and **DataViewRowState** are supplied along with the **DataTable**.</span></span>  
  
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
  
 <span data-ttu-id="b6cdd-112">下面的代码示例演示如何获取对默认值的引用**DataView**的**DataTable**使用**默认视图**的表的属性。</span><span class="sxs-lookup"><span data-stu-id="b6cdd-112">The following code example demonstrates how to obtain a reference to the default **DataView** of a **DataTable** using the **DefaultView** property of the table.</span></span>  
  
```vb  
Dim custDV As DataView = custDS.Tables("Customers").DefaultView  
```  
  
```csharp  
DataView custDV = custDS.Tables["Customers"].DefaultView;  
```  
  
## <a name="see-also"></a><span data-ttu-id="b6cdd-113">请参阅</span><span class="sxs-lookup"><span data-stu-id="b6cdd-113">See Also</span></span>  
 <xref:System.Data.DataTable>  
 <xref:System.Data.DataView>  
 [<span data-ttu-id="b6cdd-114">数据视图</span><span class="sxs-lookup"><span data-stu-id="b6cdd-114">DataViews</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/dataviews.md)  
 [<span data-ttu-id="b6cdd-115">对数据进行排序和筛选</span><span class="sxs-lookup"><span data-stu-id="b6cdd-115">Sorting and Filtering Data</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/sorting-and-filtering-data.md)  
 [<span data-ttu-id="b6cdd-116">数据表</span><span class="sxs-lookup"><span data-stu-id="b6cdd-116">DataTables</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/datatables.md)  
 [<span data-ttu-id="b6cdd-117">ADO.NET 托管提供程序和数据集开发人员中心</span><span class="sxs-lookup"><span data-stu-id="b6cdd-117">ADO.NET Managed Providers and DataSet Developer Center</span></span>](http://go.microsoft.com/fwlink/?LinkId=217917)
