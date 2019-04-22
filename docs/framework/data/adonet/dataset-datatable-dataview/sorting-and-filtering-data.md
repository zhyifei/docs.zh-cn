---
title: 对数据进行排序和筛选
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: fdd9c753-39df-48cd-9822-2781afe76200
ms.openlocfilehash: 8d8bd85f65adfde5f239e1e2dd79d65517b745a8
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/18/2019
ms.locfileid: "59166239"
---
# <a name="sorting-and-filtering-data"></a><span data-ttu-id="bf839-102">对数据进行排序和筛选</span><span class="sxs-lookup"><span data-stu-id="bf839-102">Sorting and Filtering Data</span></span>
<span data-ttu-id="bf839-103"><xref:System.Data.DataView> 为在 <xref:System.Data.DataTable> 中对数据排序和筛选提供了多种方法：</span><span class="sxs-lookup"><span data-stu-id="bf839-103">The <xref:System.Data.DataView> provides several ways of sorting and filtering data in a <xref:System.Data.DataTable>:</span></span>  
  
-   <span data-ttu-id="bf839-104">可以使用 <xref:System.Data.DataView.Sort%2A> 属性指定单个或多个列排序顺序并包含 ASC（升序）和 DESC（降序）参数。</span><span class="sxs-lookup"><span data-stu-id="bf839-104">You can use the <xref:System.Data.DataView.Sort%2A> property to specify single or multiple column sort orders and include ASC (ascending) and DESC (descending) parameters.</span></span>  
  
-   <span data-ttu-id="bf839-105">可以使用 <xref:System.Data.DataView.ApplyDefaultSort%2A> 属性自动以升序创建基于表的一个或多个主键列的排序顺序。</span><span class="sxs-lookup"><span data-stu-id="bf839-105">You can use the <xref:System.Data.DataView.ApplyDefaultSort%2A> property to automatically create a sort order, in ascending order, based on the primary key column or columns of the table.</span></span> <span data-ttu-id="bf839-106"><xref:System.Data.DataView.ApplyDefaultSort%2A> 时，才适用**排序**属性为 null 引用或空字符串，并且表已定义主键时。</span><span class="sxs-lookup"><span data-stu-id="bf839-106"><xref:System.Data.DataView.ApplyDefaultSort%2A> only applies when the **Sort** property is a null reference or an empty string, and when the table has a primary key defined.</span></span>  
  
-   <span data-ttu-id="bf839-107">可以使用 <xref:System.Data.DataView.RowFilter%2A> 属性根据行的列值来指定行的子集。</span><span class="sxs-lookup"><span data-stu-id="bf839-107">You can use the <xref:System.Data.DataView.RowFilter%2A> property to specify subsets of rows based on their column values.</span></span> <span data-ttu-id="bf839-108">有关有效表达式的详细信息**RowFilter**属性，请参阅的参考信息<xref:System.Data.DataColumn.Expression%2A>属性的<xref:System.Data.DataColumn>类。</span><span class="sxs-lookup"><span data-stu-id="bf839-108">For details about valid expressions for the **RowFilter** property, see the reference information for the <xref:System.Data.DataColumn.Expression%2A> property of the <xref:System.Data.DataColumn> class.</span></span>  
  
     <span data-ttu-id="bf839-109">如果你想要返回的数据，而不是提供数据的子集的动态视图的特定查询的结果，请使用<xref:System.Data.DataView.Find%2A>或<xref:System.Data.DataView.FindRows%2A>方法的**DataView**以获得最佳性能而不是设置**RowFilter**属性。</span><span class="sxs-lookup"><span data-stu-id="bf839-109">If you want to return the results of a particular query on the data, as opposed to providing a dynamic view of a subset of the data, use the <xref:System.Data.DataView.Find%2A> or <xref:System.Data.DataView.FindRows%2A> methods of the **DataView** to achieve best performance rather than setting the **RowFilter** property.</span></span> <span data-ttu-id="bf839-110">设置**RowFilter**属性会重新生成索引的数据，将添加到你的应用程序的开销并降低性能。</span><span class="sxs-lookup"><span data-stu-id="bf839-110">Setting the **RowFilter** property rebuilds the index for the data, adding overhead to your application and decreasing performance.</span></span> <span data-ttu-id="bf839-111">**RowFilter**属性最适合用于数据绑定应用程序中其中绑定的控件显示筛选的结果。</span><span class="sxs-lookup"><span data-stu-id="bf839-111">The **RowFilter** property is best used in a data-bound application where a bound control displays filtered results.</span></span> <span data-ttu-id="bf839-112">**查找**并**FindRows**方法利用当前的索引而无需重新生成索引。</span><span class="sxs-lookup"><span data-stu-id="bf839-112">The **Find** and **FindRows** methods leverage the current index without requiring the index to be rebuilt.</span></span> <span data-ttu-id="bf839-113">有关详细信息**查找**并**FindRows**方法，请参阅[查找行](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/finding-rows.md)。</span><span class="sxs-lookup"><span data-stu-id="bf839-113">For more information about the **Find** and **FindRows** methods, see [Finding Rows](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/finding-rows.md).</span></span>  
  
-   <span data-ttu-id="bf839-114">可以使用 <xref:System.Data.DataView.RowStateFilter%2A> 属性指定要查看的行版本。</span><span class="sxs-lookup"><span data-stu-id="bf839-114">You can use the <xref:System.Data.DataView.RowStateFilter%2A> property to specify which row versions to view.</span></span> <span data-ttu-id="bf839-115">**DataView**隐式地管理要公开具体取决于哪个行版本**RowState**基础行。</span><span class="sxs-lookup"><span data-stu-id="bf839-115">The **DataView** implicitly manages which row version to expose depending upon the **RowState** of the underlying row.</span></span> <span data-ttu-id="bf839-116">例如，如果**RowStateFilter**设置为**DataViewRowState.Deleted**，则**DataView**公开**原始**行版本所有**Deleted**行，因为没有任何**当前**行版本。</span><span class="sxs-lookup"><span data-stu-id="bf839-116">For example, if the **RowStateFilter** is set to **DataViewRowState.Deleted**, the **DataView** exposes the **Original** row version of all **Deleted** rows because there is no **Current** row version.</span></span> <span data-ttu-id="bf839-117">您可以确定某行的行版本通过使用公开**RowVersion**的属性**DataRowView**。</span><span class="sxs-lookup"><span data-stu-id="bf839-117">You can determine which row version of a row is being exposed by using the **RowVersion** property of the **DataRowView**.</span></span>  
  
     <span data-ttu-id="bf839-118">下表显示的选项**DataViewRowState**。</span><span class="sxs-lookup"><span data-stu-id="bf839-118">The following table shows the options for **DataViewRowState**.</span></span>  
  
    |<span data-ttu-id="bf839-119">DataViewRowState 选项</span><span class="sxs-lookup"><span data-stu-id="bf839-119">DataViewRowState options</span></span>|<span data-ttu-id="bf839-120">描述</span><span class="sxs-lookup"><span data-stu-id="bf839-120">Description</span></span>|  
    |------------------------------|-----------------|  
    |<span data-ttu-id="bf839-121">**CurrentRows**</span><span class="sxs-lookup"><span data-stu-id="bf839-121">**CurrentRows**</span></span>|<span data-ttu-id="bf839-122">**当前**行版本的所有**Unchanged**， **Added**，并**Modified**行。</span><span class="sxs-lookup"><span data-stu-id="bf839-122">The **Current** row version of all **Unchanged**, **Added**, and **Modified** rows.</span></span> <span data-ttu-id="bf839-123">这是默认设置。</span><span class="sxs-lookup"><span data-stu-id="bf839-123">This is the default.</span></span>|  
    |<span data-ttu-id="bf839-124">**添加**</span><span class="sxs-lookup"><span data-stu-id="bf839-124">**Added**</span></span>|<span data-ttu-id="bf839-125">**当前**行版本的所有**Added**行。</span><span class="sxs-lookup"><span data-stu-id="bf839-125">The **Current** row version of all **Added** rows.</span></span>|  
    |<span data-ttu-id="bf839-126">**已删除**</span><span class="sxs-lookup"><span data-stu-id="bf839-126">**Deleted**</span></span>|<span data-ttu-id="bf839-127">**原始**行版本的所有**Deleted**行。</span><span class="sxs-lookup"><span data-stu-id="bf839-127">The **Original** row version of all **Deleted** rows.</span></span>|  
    |<span data-ttu-id="bf839-128">**ModifiedCurrent**</span><span class="sxs-lookup"><span data-stu-id="bf839-128">**ModifiedCurrent**</span></span>|<span data-ttu-id="bf839-129">**当前**行版本的所有**Modified**行。</span><span class="sxs-lookup"><span data-stu-id="bf839-129">The **Current** row version of all **Modified** rows.</span></span>|  
    |<span data-ttu-id="bf839-130">**ModifiedOriginal**</span><span class="sxs-lookup"><span data-stu-id="bf839-130">**ModifiedOriginal**</span></span>|<span data-ttu-id="bf839-131">**原始**行版本的所有**Modified**行。</span><span class="sxs-lookup"><span data-stu-id="bf839-131">The **Original** row version of all **Modified** rows.</span></span>|  
    |<span data-ttu-id="bf839-132">**无**</span><span class="sxs-lookup"><span data-stu-id="bf839-132">**None**</span></span>|<span data-ttu-id="bf839-133">没有行。</span><span class="sxs-lookup"><span data-stu-id="bf839-133">No rows.</span></span>|  
    |<span data-ttu-id="bf839-134">**OriginalRows**</span><span class="sxs-lookup"><span data-stu-id="bf839-134">**OriginalRows**</span></span>|<span data-ttu-id="bf839-135">**原始**行版本的所有**Unchanged**， **Modified**，以及**已删除**行。</span><span class="sxs-lookup"><span data-stu-id="bf839-135">The **Original** row version of all **Unchanged**, **Modified**, and **Deleted** rows.</span></span>|  
    |<span data-ttu-id="bf839-136">**保持不变**</span><span class="sxs-lookup"><span data-stu-id="bf839-136">**Unchanged**</span></span>|<span data-ttu-id="bf839-137">**当前**行版本的所有**Unchanged**行。</span><span class="sxs-lookup"><span data-stu-id="bf839-137">The **Current** row version of all **Unchanged** rows.</span></span>|  
  
 <span data-ttu-id="bf839-138">有关行状态和行版本的详细信息，请参阅[行状态和行版本](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/row-states-and-row-versions.md)。</span><span class="sxs-lookup"><span data-stu-id="bf839-138">For more information about row states and row versions, see [Row States and Row Versions](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/row-states-and-row-versions.md).</span></span>  
  
 <span data-ttu-id="bf839-139">以下代码示例创建一个视图，该视图显示所有库存量小于或等于再订购量的产品，这些产品首先按供应商 ID 排序，然后按产品名称排序。</span><span class="sxs-lookup"><span data-stu-id="bf839-139">The following code example creates a view that shows all the products where the number of units in stock is less than or equal to the reorder level, sorted first by supplier ID and then by product name.</span></span>  
  
```vb  
Dim prodView As DataView = New DataView(prodDS.Tables("Products"), _  
   "UnitsInStock <= ReorderLevel", _  
   "SupplierID, ProductName", _  
   DataViewRowState.CurrentRows)  
```  
  
```csharp  
DataView prodView = new DataView(prodDS.Tables["Products"],  
   "UnitsInStock <= ReorderLevel",  
   "SupplierID, ProductName",  
   DataViewRowState.CurrentRows);  
```  
  
## <a name="see-also"></a><span data-ttu-id="bf839-140">请参阅</span><span class="sxs-lookup"><span data-stu-id="bf839-140">See also</span></span>

- <xref:System.Data.DataViewRowState>
- <xref:System.Data.DataColumn.Expression%2A?displayProperty=nameWithType>
- <xref:System.Data.DataTable>
- <xref:System.Data.DataView>
- [<span data-ttu-id="bf839-141">数据视图</span><span class="sxs-lookup"><span data-stu-id="bf839-141">DataViews</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/dataviews.md)
- [<span data-ttu-id="bf839-142">ADO.NET 托管提供程序和数据集开发人员中心</span><span class="sxs-lookup"><span data-stu-id="bf839-142">ADO.NET Managed Providers and DataSet Developer Center</span></span>](https://go.microsoft.com/fwlink/?LinkId=217917)
