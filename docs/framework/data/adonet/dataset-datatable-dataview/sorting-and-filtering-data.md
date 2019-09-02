---
title: 对数据进行排序和筛选
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: fdd9c753-39df-48cd-9822-2781afe76200
ms.openlocfilehash: 0907aa2a66e1bf51fefc7bed8ea2612cc0c830fa
ms.sourcegitcommit: 2d792961ed48f235cf413d6031576373c3050918
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/31/2019
ms.locfileid: "70203229"
---
# <a name="sorting-and-filtering-data"></a><span data-ttu-id="80512-102">对数据进行排序和筛选</span><span class="sxs-lookup"><span data-stu-id="80512-102">Sorting and Filtering Data</span></span>
<span data-ttu-id="80512-103"><xref:System.Data.DataView> 为在 <xref:System.Data.DataTable> 中对数据排序和筛选提供了多种方法：</span><span class="sxs-lookup"><span data-stu-id="80512-103">The <xref:System.Data.DataView> provides several ways of sorting and filtering data in a <xref:System.Data.DataTable>:</span></span>  
  
- <span data-ttu-id="80512-104">可以使用 <xref:System.Data.DataView.Sort%2A> 属性指定单个或多个列排序顺序并包含 ASC（升序）和 DESC（降序）参数。</span><span class="sxs-lookup"><span data-stu-id="80512-104">You can use the <xref:System.Data.DataView.Sort%2A> property to specify single or multiple column sort orders and include ASC (ascending) and DESC (descending) parameters.</span></span>  
  
- <span data-ttu-id="80512-105">可以使用 <xref:System.Data.DataView.ApplyDefaultSort%2A> 属性自动以升序创建基于表的一个或多个主键列的排序顺序。</span><span class="sxs-lookup"><span data-stu-id="80512-105">You can use the <xref:System.Data.DataView.ApplyDefaultSort%2A> property to automatically create a sort order, in ascending order, based on the primary key column or columns of the table.</span></span> <span data-ttu-id="80512-106"><xref:System.Data.DataView.ApplyDefaultSort%2A>仅当**Sort**属性为空引用或空字符串时以及表已定义主键时, 才适用。</span><span class="sxs-lookup"><span data-stu-id="80512-106"><xref:System.Data.DataView.ApplyDefaultSort%2A> only applies when the **Sort** property is a null reference or an empty string, and when the table has a primary key defined.</span></span>  
  
- <span data-ttu-id="80512-107">可以使用 <xref:System.Data.DataView.RowFilter%2A> 属性根据行的列值来指定行的子集。</span><span class="sxs-lookup"><span data-stu-id="80512-107">You can use the <xref:System.Data.DataView.RowFilter%2A> property to specify subsets of rows based on their column values.</span></span> <span data-ttu-id="80512-108">有关**RowFilter**属性的有效表达式的详细信息, 请参阅<xref:System.Data.DataColumn.Expression%2A> <xref:System.Data.DataColumn>类的属性的参考信息。</span><span class="sxs-lookup"><span data-stu-id="80512-108">For details about valid expressions for the **RowFilter** property, see the reference information for the <xref:System.Data.DataColumn.Expression%2A> property of the <xref:System.Data.DataColumn> class.</span></span>  
  
     <span data-ttu-id="80512-109">如果要返回数据的特定查询的结果, 而不是提供数据子集的动态视图, 请使用<xref:System.Data.DataView.Find%2A> **DataView**的或<xref:System.Data.DataView.FindRows%2A>方法来实现最佳性能, 而不是将**RowFilter**属性。</span><span class="sxs-lookup"><span data-stu-id="80512-109">If you want to return the results of a particular query on the data, as opposed to providing a dynamic view of a subset of the data, use the <xref:System.Data.DataView.Find%2A> or <xref:System.Data.DataView.FindRows%2A> methods of the **DataView** to achieve best performance rather than setting the **RowFilter** property.</span></span> <span data-ttu-id="80512-110">设置**RowFilter**属性会重新生成数据的索引, 从而增加应用程序的系统开销并降低性能。</span><span class="sxs-lookup"><span data-stu-id="80512-110">Setting the **RowFilter** property rebuilds the index for the data, adding overhead to your application and decreasing performance.</span></span> <span data-ttu-id="80512-111">在绑定控件显示筛选结果的数据绑定应用程序中, 最好使用**RowFilter**属性。</span><span class="sxs-lookup"><span data-stu-id="80512-111">The **RowFilter** property is best used in a data-bound application where a bound control displays filtered results.</span></span> <span data-ttu-id="80512-112">**Find**和**FindRows**方法利用当前索引, 而无需重新生成索引。</span><span class="sxs-lookup"><span data-stu-id="80512-112">The **Find** and **FindRows** methods leverage the current index without requiring the index to be rebuilt.</span></span> <span data-ttu-id="80512-113">有关**Find**和**FindRows**方法的详细信息, 请参阅[查找行](finding-rows.md)。</span><span class="sxs-lookup"><span data-stu-id="80512-113">For more information about the **Find** and **FindRows** methods, see [Finding Rows](finding-rows.md).</span></span>  
  
- <span data-ttu-id="80512-114">可以使用 <xref:System.Data.DataView.RowStateFilter%2A> 属性指定要查看的行版本。</span><span class="sxs-lookup"><span data-stu-id="80512-114">You can use the <xref:System.Data.DataView.RowStateFilter%2A> property to specify which row versions to view.</span></span> <span data-ttu-id="80512-115">**DataView**根据基础行的**RowState**隐式地管理要公开的行版本。</span><span class="sxs-lookup"><span data-stu-id="80512-115">The **DataView** implicitly manages which row version to expose depending upon the **RowState** of the underlying row.</span></span> <span data-ttu-id="80512-116">例如, 如果**RowStateFilter**设置为**DataViewRowState**, 则**DataView**将公开所有**已删除**行的**原始**行版本, 因为没有**当前**行版本。</span><span class="sxs-lookup"><span data-stu-id="80512-116">For example, if the **RowStateFilter** is set to **DataViewRowState.Deleted**, the **DataView** exposes the **Original** row version of all **Deleted** rows because there is no **Current** row version.</span></span> <span data-ttu-id="80512-117">您可以使用**DataRowView**的**RowVersion**属性来确定要公开行的哪个行版本。</span><span class="sxs-lookup"><span data-stu-id="80512-117">You can determine which row version of a row is being exposed by using the **RowVersion** property of the **DataRowView**.</span></span>  
  
     <span data-ttu-id="80512-118">下表显示了**DataViewRowState**的选项。</span><span class="sxs-lookup"><span data-stu-id="80512-118">The following table shows the options for **DataViewRowState**.</span></span>  
  
    |<span data-ttu-id="80512-119">DataViewRowState 选项</span><span class="sxs-lookup"><span data-stu-id="80512-119">DataViewRowState options</span></span>|<span data-ttu-id="80512-120">描述</span><span class="sxs-lookup"><span data-stu-id="80512-120">Description</span></span>|  
    |------------------------------|-----------------|  
    |<span data-ttu-id="80512-121">**CurrentRows**</span><span class="sxs-lookup"><span data-stu-id="80512-121">**CurrentRows**</span></span>|<span data-ttu-id="80512-122">所有**未更改**的、**已添加**的行和**已修改**的行的**当前**行版本。</span><span class="sxs-lookup"><span data-stu-id="80512-122">The **Current** row version of all **Unchanged**, **Added**, and **Modified** rows.</span></span> <span data-ttu-id="80512-123">这是默认设置。</span><span class="sxs-lookup"><span data-stu-id="80512-123">This is the default.</span></span>|  
    |<span data-ttu-id="80512-124">**已**</span><span class="sxs-lookup"><span data-stu-id="80512-124">**Added**</span></span>|<span data-ttu-id="80512-125">所有**已添加**行的**当前**行版本。</span><span class="sxs-lookup"><span data-stu-id="80512-125">The **Current** row version of all **Added** rows.</span></span>|  
    |<span data-ttu-id="80512-126">**删除**</span><span class="sxs-lookup"><span data-stu-id="80512-126">**Deleted**</span></span>|<span data-ttu-id="80512-127">所有**已删除**行的**原始**行版本。</span><span class="sxs-lookup"><span data-stu-id="80512-127">The **Original** row version of all **Deleted** rows.</span></span>|  
    |<span data-ttu-id="80512-128">**ModifiedCurrent**</span><span class="sxs-lookup"><span data-stu-id="80512-128">**ModifiedCurrent**</span></span>|<span data-ttu-id="80512-129">所有**已修改**行的**当前**行版本。</span><span class="sxs-lookup"><span data-stu-id="80512-129">The **Current** row version of all **Modified** rows.</span></span>|  
    |<span data-ttu-id="80512-130">**ModifiedOriginal**</span><span class="sxs-lookup"><span data-stu-id="80512-130">**ModifiedOriginal**</span></span>|<span data-ttu-id="80512-131">所有**已修改**行的**原始**行版本。</span><span class="sxs-lookup"><span data-stu-id="80512-131">The **Original** row version of all **Modified** rows.</span></span>|  
    |<span data-ttu-id="80512-132">**无**</span><span class="sxs-lookup"><span data-stu-id="80512-132">**None**</span></span>|<span data-ttu-id="80512-133">没有行。</span><span class="sxs-lookup"><span data-stu-id="80512-133">No rows.</span></span>|  
    |<span data-ttu-id="80512-134">**OriginalRows**</span><span class="sxs-lookup"><span data-stu-id="80512-134">**OriginalRows**</span></span>|<span data-ttu-id="80512-135">所有**未更改**、**已修改**和**已删除**行的**原始**行版本。</span><span class="sxs-lookup"><span data-stu-id="80512-135">The **Original** row version of all **Unchanged**, **Modified**, and **Deleted** rows.</span></span>|  
    |<span data-ttu-id="80512-136">**变化**</span><span class="sxs-lookup"><span data-stu-id="80512-136">**Unchanged**</span></span>|<span data-ttu-id="80512-137">所有**未更改**的行的**当前**行版本。</span><span class="sxs-lookup"><span data-stu-id="80512-137">The **Current** row version of all **Unchanged** rows.</span></span>|  
  
 <span data-ttu-id="80512-138">有关行状态和行版本的详细信息, 请参阅[行状态和行版本](row-states-and-row-versions.md)。</span><span class="sxs-lookup"><span data-stu-id="80512-138">For more information about row states and row versions, see [Row States and Row Versions](row-states-and-row-versions.md).</span></span>  
  
 <span data-ttu-id="80512-139">以下代码示例创建一个视图，该视图显示所有库存量小于或等于再订购量的产品，这些产品首先按供应商 ID 排序，然后按产品名称排序。</span><span class="sxs-lookup"><span data-stu-id="80512-139">The following code example creates a view that shows all the products where the number of units in stock is less than or equal to the reorder level, sorted first by supplier ID and then by product name.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="80512-140">请参阅</span><span class="sxs-lookup"><span data-stu-id="80512-140">See also</span></span>

- <xref:System.Data.DataViewRowState>
- <xref:System.Data.DataColumn.Expression%2A?displayProperty=nameWithType>
- <xref:System.Data.DataTable>
- <xref:System.Data.DataView>
- [<span data-ttu-id="80512-141">数据视图</span><span class="sxs-lookup"><span data-stu-id="80512-141">DataViews</span></span>](dataviews.md)
- [<span data-ttu-id="80512-142">ADO.NET 托管提供程序和数据集开发人员中心</span><span class="sxs-lookup"><span data-stu-id="80512-142">ADO.NET Managed Providers and DataSet Developer Center</span></span>](https://go.microsoft.com/fwlink/?LinkId=217917)
