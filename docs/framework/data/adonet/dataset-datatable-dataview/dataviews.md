---
title: DataView
ms.date: 03/30/2017
ms.assetid: 0fe5dfa2-c1cd-435f-90b6-b4dd2e3ef34b
ms.openlocfilehash: f3e5d047496785c34c1fe242853829ae0110dc2a
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/03/2018
---
# <a name="dataviews"></a><span data-ttu-id="78872-102">DataView</span><span class="sxs-lookup"><span data-stu-id="78872-102">DataViews</span></span>
<span data-ttu-id="78872-103">您可以利用 <xref:System.Data.DataView> 创建存储在 <xref:System.Data.DataTable>（一种通常在数据绑定应用程序中使用的功能）中的数据的不同视图。</span><span class="sxs-lookup"><span data-stu-id="78872-103">A <xref:System.Data.DataView> enables you to create different views of the data stored in a <xref:System.Data.DataTable>, a capability that is often used in data-binding applications.</span></span> <span data-ttu-id="78872-104">使用**DataView**，您可以公开具有不同的排序顺序的表中的数据，并且你可以按行状态或基于筛选器表达式来筛选数据。</span><span class="sxs-lookup"><span data-stu-id="78872-104">Using a **DataView**, you can expose the data in a table with different sort orders, and you can filter the data by row state or based on a filter expression.</span></span>  
  
 <span data-ttu-id="78872-105">A **DataView**提供在基础数据的动态视图**DataTable**： 内容、 排序和成员身份反映的更改，在发生。</span><span class="sxs-lookup"><span data-stu-id="78872-105">A **DataView** provides a dynamic view of data in the underlying **DataTable**: the content, ordering, and membership reflect changes as they occur.</span></span> <span data-ttu-id="78872-106">此行为不同于**选择**方法**DataTable**，它将返回<xref:System.Data.DataRow>表中的数组基于特定筛选器和/或排序顺序： thiscontent 反映对更改基础表，但其成员资格和顺序却保持不变。</span><span class="sxs-lookup"><span data-stu-id="78872-106">This behavior differs from the **Select** method of the **DataTable**, which returns a <xref:System.Data.DataRow> array from a table based on a particular filter and/or sort order: thiscontent reflects changes to the underlying table, but its membership and ordering remain static.</span></span> <span data-ttu-id="78872-107">动态功能**DataView**使其适合用于数据绑定应用程序。</span><span class="sxs-lookup"><span data-stu-id="78872-107">The dynamic capabilities of the **DataView** make it ideal for data-binding applications.</span></span>  
  
 <span data-ttu-id="78872-108">A **DataView**你提供一组数据，类似于数据库视图，可向其应用不同排序和筛选条件的动态视图。</span><span class="sxs-lookup"><span data-stu-id="78872-108">A **DataView** provides you with a dynamic view of a single set of data, much like a database view, to which you can apply different sorting and filtering criteria.</span></span> <span data-ttu-id="78872-109">与数据库视图，但是，不同**DataView**不能作为表处理，并且无法提供联接的表的视图。</span><span class="sxs-lookup"><span data-stu-id="78872-109">Unlike a database view, however, a **DataView** cannot be treated as a table and cannot provide a view of joined tables.</span></span> <span data-ttu-id="78872-110">另外，还不能排除存在于源表中的列，也不能追加不存在于源表中的列（如计算列）。</span><span class="sxs-lookup"><span data-stu-id="78872-110">You also cannot exclude columns that exist in the source table, nor can you append columns, such as computational columns, that do not exist in the source table.</span></span>  
  
 <span data-ttu-id="78872-111">你可以使用<xref:System.Data.DataView.DataViewManager%2A>来管理中的所有表的视图设置**数据集**。</span><span class="sxs-lookup"><span data-stu-id="78872-111">You can use a <xref:System.Data.DataView.DataViewManager%2A> to manage view settings for all the tables in a **DataSet**.</span></span> <span data-ttu-id="78872-112">**DataViewManager**提供了方便的方式来管理每个表的默认视图设置。</span><span class="sxs-lookup"><span data-stu-id="78872-112">The **DataViewManager** provides you with a convenient way to manage default view settings for each table.</span></span> <span data-ttu-id="78872-113">当一个控件绑定到多个表的**数据集**，绑定到**DataViewManager**是理想的选择。</span><span class="sxs-lookup"><span data-stu-id="78872-113">When binding a control to more than one table of a **DataSet**, binding to a **DataViewManager** is the ideal choice.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="78872-114">本节内容</span><span class="sxs-lookup"><span data-stu-id="78872-114">In This Section</span></span>  
 [<span data-ttu-id="78872-115">创建数据视图</span><span class="sxs-lookup"><span data-stu-id="78872-115">Creating a DataView</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/creating-a-dataview.md)  
 <span data-ttu-id="78872-116">描述如何创建**DataView**为**DataTable**。</span><span class="sxs-lookup"><span data-stu-id="78872-116">Describes how to create a **DataView** for a **DataTable**.</span></span>  
  
 [<span data-ttu-id="78872-117">对数据进行排序和筛选</span><span class="sxs-lookup"><span data-stu-id="78872-117">Sorting and Filtering Data</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/sorting-and-filtering-data.md)  
 <span data-ttu-id="78872-118">描述如何设置的属性**DataView**以返回满足指定筛选条件的数据行的子集，或以特定排序顺序返回数据。</span><span class="sxs-lookup"><span data-stu-id="78872-118">Describes how to set the properties of a **DataView** to return subsets of data rows meeting specific filter criteria, or to return data in a particular sort order.</span></span>  
  
 [<span data-ttu-id="78872-119">DataRow 和 DataRowView</span><span class="sxs-lookup"><span data-stu-id="78872-119">DataRows and DataRowViews</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/datarows-and-datarowviews.md)  
 <span data-ttu-id="78872-120">介绍如何访问由公开的数据**DataView**。</span><span class="sxs-lookup"><span data-stu-id="78872-120">Describes how to access the data exposed by the **DataView**.</span></span>  
  
 [<span data-ttu-id="78872-121">查找行</span><span class="sxs-lookup"><span data-stu-id="78872-121">Finding Rows</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/finding-rows.md)  
 <span data-ttu-id="78872-122">介绍如何以查找中的特定行**DataView**。</span><span class="sxs-lookup"><span data-stu-id="78872-122">Describes how to find a particular row in a **DataView**.</span></span>  
  
 [<span data-ttu-id="78872-123">ChildView 和关系</span><span class="sxs-lookup"><span data-stu-id="78872-123">ChildViews and Relations</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/childviews-and-relations.md)  
 <span data-ttu-id="78872-124">描述如何创建父-子关系中使用的数据的视图**DataView**。</span><span class="sxs-lookup"><span data-stu-id="78872-124">Describes how to create views of data from a parent-child relationship using a **DataView**.</span></span>  
  
 [<span data-ttu-id="78872-125">修改 DataView</span><span class="sxs-lookup"><span data-stu-id="78872-125">Modifying DataViews</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/modifying-dataviews.md)  
 <span data-ttu-id="78872-126">描述如何修改在基础数据**DataTable**通过**DataView**，包括启用或禁用更新。</span><span class="sxs-lookup"><span data-stu-id="78872-126">Describes how to modify the data in the underlying **DataTable** via the **DataView**, including enabling or disabling updates.</span></span>  
  
 [<span data-ttu-id="78872-127">处理 DataView 事件</span><span class="sxs-lookup"><span data-stu-id="78872-127">Handling DataView Events</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/handling-dataview-events.md)  
 <span data-ttu-id="78872-128">介绍如何使用**ListChanged**可以接收通知的事件时的内容或顺序**DataView**正在更新。</span><span class="sxs-lookup"><span data-stu-id="78872-128">Describes how to use the **ListChanged** event to receive notification when the contents or order of a **DataView** is being updated.</span></span>  
  
 [<span data-ttu-id="78872-129">管理 DataView</span><span class="sxs-lookup"><span data-stu-id="78872-129">Managing DataViews</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/managing-dataviews.md)  
 <span data-ttu-id="78872-130">介绍如何使用**DataViewManager**管理**DataView**每个表中的设置**数据集**。</span><span class="sxs-lookup"><span data-stu-id="78872-130">Describes how to use a **DataViewManager** to manage **DataView** settings for each table in a **DataSet**.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="78872-131">相关章节</span><span class="sxs-lookup"><span data-stu-id="78872-131">Related Sections</span></span>  
 [<span data-ttu-id="78872-132">ASP.NET Web 应用程序</span><span class="sxs-lookup"><span data-stu-id="78872-132">ASP.NET Web Applications</span></span>](http://msdn.microsoft.com/library/a812d7b7-049e-4234-a4c2-6acf690301f6)  
 <span data-ttu-id="78872-133">提供创建 ASP.NET 应用程序、Web 窗体和 Web 服务的概述和详细步骤信息。</span><span class="sxs-lookup"><span data-stu-id="78872-133">Provides overviews and detailed, step-by-step procedures for creating ASP.NET applications, Web Forms, and Web Services.</span></span>  
  
 [<span data-ttu-id="78872-134">Windows 应用程序</span><span class="sxs-lookup"><span data-stu-id="78872-134">Windows Applications</span></span>](http://msdn.microsoft.com/library/a6bb2180-09b1-4738-b9fd-7fb05fc92f23)  
 <span data-ttu-id="78872-135">提供有关使用 Windows 窗体和控制台应用程序的详细信息。</span><span class="sxs-lookup"><span data-stu-id="78872-135">Provides detailed information about working with Windows Forms and console applications.</span></span>  
  
 [<span data-ttu-id="78872-136">数据集、数据表和数据视图</span><span class="sxs-lookup"><span data-stu-id="78872-136">DataSets, DataTables, and DataViews</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/index.md)  
 <span data-ttu-id="78872-137">描述**数据集**对象以及如何使用它来管理应用程序数据。</span><span class="sxs-lookup"><span data-stu-id="78872-137">Describes the **DataSet** object and how you can use it to manage application data.</span></span>  
  
 [<span data-ttu-id="78872-138">数据表</span><span class="sxs-lookup"><span data-stu-id="78872-138">DataTables</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/datatables.md)  
 <span data-ttu-id="78872-139">描述**DataTable**对象以及如何使用它来管理应用程序数据本身或作为的一部分**数据集**。</span><span class="sxs-lookup"><span data-stu-id="78872-139">Describes the **DataTable** object and how you can use it to manage application data by itself or as part of a **DataSet**.</span></span>  
  
 [<span data-ttu-id="78872-140">ADO.NET</span><span class="sxs-lookup"><span data-stu-id="78872-140">ADO.NET</span></span>](../../../../../docs/framework/data/adonet/index.md)  
 <span data-ttu-id="78872-141">描述 ADO.NET 结构和组件，并说明如何使用 ADO.NET 来访问现有的数据源和管理应用程序数据。</span><span class="sxs-lookup"><span data-stu-id="78872-141">Describes the ADO.NET architecture and components, and how to use ADO.NET to access existing data sources and manage application data.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="78872-142">请参阅</span><span class="sxs-lookup"><span data-stu-id="78872-142">See Also</span></span>  
 [<span data-ttu-id="78872-143">ADO.NET 托管提供程序和数据集开发人员中心</span><span class="sxs-lookup"><span data-stu-id="78872-143">ADO.NET Managed Providers and DataSet Developer Center</span></span>](http://go.microsoft.com/fwlink/?LinkId=217917)
