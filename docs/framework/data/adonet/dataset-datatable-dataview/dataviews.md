---
title: DataView
ms.date: 03/30/2017
ms.assetid: 0fe5dfa2-c1cd-435f-90b6-b4dd2e3ef34b
ms.openlocfilehash: 8a06accb11631f2dce6b0d39587d7274223c0e68
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/07/2019
ms.locfileid: "70786343"
---
# <a name="dataviews"></a><span data-ttu-id="ae983-102">DataView</span><span class="sxs-lookup"><span data-stu-id="ae983-102">DataViews</span></span>
<span data-ttu-id="ae983-103">您可以利用 <xref:System.Data.DataView> 创建存储在 <xref:System.Data.DataTable>（一种通常在数据绑定应用程序中使用的功能）中的数据的不同视图。</span><span class="sxs-lookup"><span data-stu-id="ae983-103">A <xref:System.Data.DataView> enables you to create different views of the data stored in a <xref:System.Data.DataTable>, a capability that is often used in data-binding applications.</span></span> <span data-ttu-id="ae983-104">使用**DataView**，你可以使用不同的排序顺序公开表中的数据，并且可以按行状态或基于筛选器表达式来筛选数据。</span><span class="sxs-lookup"><span data-stu-id="ae983-104">Using a **DataView**, you can expose the data in a table with different sort orders, and you can filter the data by row state or based on a filter expression.</span></span>  
  
 <span data-ttu-id="ae983-105">**DataView**提供基础**DataTable**中的数据的动态视图：内容、排序和成员身份在更改发生时反映更改。</span><span class="sxs-lookup"><span data-stu-id="ae983-105">A **DataView** provides a dynamic view of data in the underlying **DataTable**: the content, ordering, and membership reflect changes as they occur.</span></span> <span data-ttu-id="ae983-106">此行为不同于**DataTable**的**Select**方法，该方法根据特定筛选<xref:System.Data.DataRow>器和/或排序顺序从表返回数组：此内容反映了对基础表的更改，但其成员资格和排序始终为静态。</span><span class="sxs-lookup"><span data-stu-id="ae983-106">This behavior differs from the **Select** method of the **DataTable**, which returns a <xref:System.Data.DataRow> array from a table based on a particular filter and/or sort order: this content reflects changes to the underlying table, but its membership and ordering remain static.</span></span> <span data-ttu-id="ae983-107">**DataView**的动态功能使其成为数据绑定应用程序的理想之选。</span><span class="sxs-lookup"><span data-stu-id="ae983-107">The dynamic capabilities of the **DataView** make it ideal for data-binding applications.</span></span>  
  
 <span data-ttu-id="ae983-108">数据**视图为您提供了**一组数据的动态视图，这与数据库视图非常类似，您可以将不同的排序和筛选条件应用于该视图。</span><span class="sxs-lookup"><span data-stu-id="ae983-108">A **DataView** provides you with a dynamic view of a single set of data, much like a database view, to which you can apply different sorting and filtering criteria.</span></span> <span data-ttu-id="ae983-109">但是，与数据库视图不同， **DataView**不能被视为表，也不能提供联接的表的视图。</span><span class="sxs-lookup"><span data-stu-id="ae983-109">Unlike a database view, however, a **DataView** cannot be treated as a table and cannot provide a view of joined tables.</span></span> <span data-ttu-id="ae983-110">另外，还不能排除存在于源表中的列，也不能追加不存在于源表中的列（如计算列）。</span><span class="sxs-lookup"><span data-stu-id="ae983-110">You also cannot exclude columns that exist in the source table, nor can you append columns, such as computational columns, that do not exist in the source table.</span></span>  
  
 <span data-ttu-id="ae983-111">您可以使用<xref:System.Data.DataView.DataViewManager%2A>来管理**数据集中**所有表的视图设置。</span><span class="sxs-lookup"><span data-stu-id="ae983-111">You can use a <xref:System.Data.DataView.DataViewManager%2A> to manage view settings for all the tables in a **DataSet**.</span></span> <span data-ttu-id="ae983-112">**DataViewManager**为你提供了一种方便的方法来管理每个表的默认视图设置。</span><span class="sxs-lookup"><span data-stu-id="ae983-112">The **DataViewManager** provides you with a convenient way to manage default view settings for each table.</span></span> <span data-ttu-id="ae983-113">将控件绑定到**数据集**的多个表时，绑定到**DataViewManager**是理想的选择。</span><span class="sxs-lookup"><span data-stu-id="ae983-113">When binding a control to more than one table of a **DataSet**, binding to a **DataViewManager** is the ideal choice.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="ae983-114">本节内容</span><span class="sxs-lookup"><span data-stu-id="ae983-114">In This Section</span></span>  
 [<span data-ttu-id="ae983-115">创建数据视图</span><span class="sxs-lookup"><span data-stu-id="ae983-115">Creating a DataView</span></span>](creating-a-dataview.md)  
 <span data-ttu-id="ae983-116">介绍如何为**DataTable**创建**DataView** 。</span><span class="sxs-lookup"><span data-stu-id="ae983-116">Describes how to create a **DataView** for a **DataTable**.</span></span>  
  
 [<span data-ttu-id="ae983-117">对数据进行排序和筛选</span><span class="sxs-lookup"><span data-stu-id="ae983-117">Sorting and Filtering Data</span></span>](sorting-and-filtering-data.md)  
 <span data-ttu-id="ae983-118">描述如何设置**DataView**的属性以返回满足特定筛选条件的数据行子集，或返回按特定排序顺序返回的数据。</span><span class="sxs-lookup"><span data-stu-id="ae983-118">Describes how to set the properties of a **DataView** to return subsets of data rows meeting specific filter criteria, or to return data in a particular sort order.</span></span>  
  
 [<span data-ttu-id="ae983-119">DataRow 和 DataRowView</span><span class="sxs-lookup"><span data-stu-id="ae983-119">DataRows and DataRowViews</span></span>](datarows-and-datarowviews.md)  
 <span data-ttu-id="ae983-120">描述如何访问由**DataView**公开的数据。</span><span class="sxs-lookup"><span data-stu-id="ae983-120">Describes how to access the data exposed by the **DataView**.</span></span>  
  
 [<span data-ttu-id="ae983-121">查找行</span><span class="sxs-lookup"><span data-stu-id="ae983-121">Finding Rows</span></span>](finding-rows.md)  
 <span data-ttu-id="ae983-122">介绍如何在**DataView**中查找特定的行。</span><span class="sxs-lookup"><span data-stu-id="ae983-122">Describes how to find a particular row in a **DataView**.</span></span>  
  
 [<span data-ttu-id="ae983-123">ChildView 和关系</span><span class="sxs-lookup"><span data-stu-id="ae983-123">ChildViews and Relations</span></span>](childviews-and-relations.md)  
 <span data-ttu-id="ae983-124">介绍如何使用**DataView**创建父子关系中的数据视图。</span><span class="sxs-lookup"><span data-stu-id="ae983-124">Describes how to create views of data from a parent-child relationship using a **DataView**.</span></span>  
  
 [<span data-ttu-id="ae983-125">修改 DataView</span><span class="sxs-lookup"><span data-stu-id="ae983-125">Modifying DataViews</span></span>](modifying-dataviews.md)  
 <span data-ttu-id="ae983-126">介绍如何通过**DataView**修改基础**DataTable**中的数据，包括启用或禁用更新。</span><span class="sxs-lookup"><span data-stu-id="ae983-126">Describes how to modify the data in the underlying **DataTable** via the **DataView**, including enabling or disabling updates.</span></span>  
  
 [<span data-ttu-id="ae983-127">处理 DataView 事件</span><span class="sxs-lookup"><span data-stu-id="ae983-127">Handling DataView Events</span></span>](handling-dataview-events.md)  
 <span data-ttu-id="ae983-128">介绍如何使用**ListChanged**事件在更新**DataView**的内容或顺序时接收通知。</span><span class="sxs-lookup"><span data-stu-id="ae983-128">Describes how to use the **ListChanged** event to receive notification when the contents or order of a **DataView** is being updated.</span></span>  
  
 [<span data-ttu-id="ae983-129">管理 DataView</span><span class="sxs-lookup"><span data-stu-id="ae983-129">Managing DataViews</span></span>](managing-dataviews.md)  
 <span data-ttu-id="ae983-130">介绍如何使用**DataViewManager**来管理**数据集中**每个表的**DataView**设置。</span><span class="sxs-lookup"><span data-stu-id="ae983-130">Describes how to use a **DataViewManager** to manage **DataView** settings for each table in a **DataSet**.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="ae983-131">相关章节</span><span class="sxs-lookup"><span data-stu-id="ae983-131">Related Sections</span></span>  
 <span data-ttu-id="ae983-132">[ASP.NET Web 应用程序](https://docs.microsoft.com/previous-versions/655cec97(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="ae983-132">[ASP.NET Web Applications](https://docs.microsoft.com/previous-versions/655cec97(v=vs.100))</span></span>  
 <span data-ttu-id="ae983-133">提供创建 ASP.NET 应用程序、Web 窗体和 Web 服务的概述和详细步骤信息。</span><span class="sxs-lookup"><span data-stu-id="ae983-133">Provides overviews and detailed, step-by-step procedures for creating ASP.NET applications, Web Forms, and Web Services.</span></span>  
  
 <span data-ttu-id="ae983-134">[Windows 应用程序](https://docs.microsoft.com/previous-versions/ms184421(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="ae983-134">[Windows Applications](https://docs.microsoft.com/previous-versions/ms184421(v=vs.100))</span></span>  
 <span data-ttu-id="ae983-135">提供有关使用 Windows 窗体和控制台应用程序的详细信息。</span><span class="sxs-lookup"><span data-stu-id="ae983-135">Provides detailed information about working with Windows Forms and console applications.</span></span>  
  
 [<span data-ttu-id="ae983-136">数据集、数据表和数据视图</span><span class="sxs-lookup"><span data-stu-id="ae983-136">DataSets, DataTables, and DataViews</span></span>](index.md)  
 <span data-ttu-id="ae983-137">介绍**DataSet**对象以及如何使用它来管理应用程序数据。</span><span class="sxs-lookup"><span data-stu-id="ae983-137">Describes the **DataSet** object and how you can use it to manage application data.</span></span>  
  
 [<span data-ttu-id="ae983-138">数据表</span><span class="sxs-lookup"><span data-stu-id="ae983-138">DataTables</span></span>](datatables.md)  
 <span data-ttu-id="ae983-139">介绍**DataTable**对象，以及如何使用它来管理应用程序数据或将其作为**数据集**的一部分。</span><span class="sxs-lookup"><span data-stu-id="ae983-139">Describes the **DataTable** object and how you can use it to manage application data by itself or as part of a **DataSet**.</span></span>  
  
 [<span data-ttu-id="ae983-140">ADO.NET</span><span class="sxs-lookup"><span data-stu-id="ae983-140">ADO.NET</span></span>](../index.md)  
 <span data-ttu-id="ae983-141">描述 ADO.NET 结构和组件，并说明如何使用 ADO.NET 来访问现有的数据源和管理应用程序数据。</span><span class="sxs-lookup"><span data-stu-id="ae983-141">Describes the ADO.NET architecture and components, and how to use ADO.NET to access existing data sources and manage application data.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ae983-142">请参阅</span><span class="sxs-lookup"><span data-stu-id="ae983-142">See also</span></span>

- [<span data-ttu-id="ae983-143">ADO.NET 概述</span><span class="sxs-lookup"><span data-stu-id="ae983-143">ADO.NET Overview</span></span>](../ado-net-overview.md)
