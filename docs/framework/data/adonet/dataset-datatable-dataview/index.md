---
title: 数据集、数据表和数据视图
ms.date: 03/30/2017
ms.assetid: 6d4c4b69-8919-4224-8a65-6cca1c61b48f
ms.openlocfilehash: 2303b0ce9bc8b389a3a7af9e8fcfbcb13d0007ae
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/03/2018
ms.locfileid: "32759483"
---
# <a name="datasets-datatables-and-dataviews"></a><span data-ttu-id="20fff-102">数据集、数据表和数据视图</span><span class="sxs-lookup"><span data-stu-id="20fff-102">DataSets, DataTables, and DataViews</span></span>
<span data-ttu-id="20fff-103">ADO.NET <xref:System.Data.DataSet> 是数据的一种内存驻留表示形式，无论它包含的数据来自什么数据源，都会提供一致的关系编程模型。</span><span class="sxs-lookup"><span data-stu-id="20fff-103">The ADO.NET <xref:System.Data.DataSet> is a memory-resident representation of data that provides a consistent relational programming model regardless of the source of the data it contains.</span></span> <span data-ttu-id="20fff-104"><xref:System.Data.DataSet> 表示整个数据集，其中包含对数据进行包含、排序和约束的表以及表间的关系。</span><span class="sxs-lookup"><span data-stu-id="20fff-104">A <xref:System.Data.DataSet> represents a complete set of data including the tables that contain, order, and constrain the data, as well as the relationships between the tables.</span></span>  
  
 <span data-ttu-id="20fff-105">使用 <xref:System.Data.DataSet> 的方法有若干种，这些方法可以单独应用，也可以结合应用。</span><span class="sxs-lookup"><span data-stu-id="20fff-105">There are several ways of working with a <xref:System.Data.DataSet>, which can be applied independently or in combination.</span></span> <span data-ttu-id="20fff-106">你可以：</span><span class="sxs-lookup"><span data-stu-id="20fff-106">You can:</span></span>  
  
-   <span data-ttu-id="20fff-107">以编程方式在 <xref:System.Data.DataTable> 中创建 <xref:System.Data.DataRelation>、<xref:System.Data.Constraint> 和 <xref:System.Data.DataSet>，并使用数据填充表。</span><span class="sxs-lookup"><span data-stu-id="20fff-107">Programmatically create a <xref:System.Data.DataTable>, <xref:System.Data.DataRelation>, and <xref:System.Data.Constraint> within a <xref:System.Data.DataSet> and populate the tables with data.</span></span>  
  
-   <span data-ttu-id="20fff-108">通过 <xref:System.Data.DataSet> 用现有关系数据源中的数据表填充 `DataAdapter`。</span><span class="sxs-lookup"><span data-stu-id="20fff-108">Populate the <xref:System.Data.DataSet> with tables of data from an existing relational data source using a `DataAdapter`.</span></span>  
  
-   <span data-ttu-id="20fff-109">使用 XML 加载和保持 <xref:System.Data.DataSet> 内容。</span><span class="sxs-lookup"><span data-stu-id="20fff-109">Load and persist the <xref:System.Data.DataSet> contents using XML.</span></span> <span data-ttu-id="20fff-110">有关详细信息，请参阅[在数据集中使用 XML](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/using-xml-in-a-dataset.md)。</span><span class="sxs-lookup"><span data-stu-id="20fff-110">For more information, see [Using XML in a DataSet](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/using-xml-in-a-dataset.md).</span></span>  
  
 <span data-ttu-id="20fff-111">强类型化的 <xref:System.Data.DataSet> 也可以使用 XML Web services 来进行传输。</span><span class="sxs-lookup"><span data-stu-id="20fff-111">A strongly typed <xref:System.Data.DataSet> can also be transported using an XML Web service.</span></span> <span data-ttu-id="20fff-112"><xref:System.Data.DataSet> 的设计使其成为使用 XML Web services 传输数据的理想选择。</span><span class="sxs-lookup"><span data-stu-id="20fff-112">The design of the <xref:System.Data.DataSet> makes it ideal for transporting data using XML Web services.</span></span> <span data-ttu-id="20fff-113">有关 XML Web service 的概述，请参阅 [XML Web service 概述](http://msdn.microsoft.com/library/9db0c7b8-bca6-462b-9be5-f5f9a7f05a4d)。</span><span class="sxs-lookup"><span data-stu-id="20fff-113">For an overview of XML Web services, see [XML Web Services Overview](http://msdn.microsoft.com/library/9db0c7b8-bca6-462b-9be5-f5f9a7f05a4d).</span></span> <span data-ttu-id="20fff-114">有关通过 XML Web service 使用 <xref:System.Data.DataSet> 的示例，请参阅[通过 XML Web service 使用数据集](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/consuming-a-dataset-from-an-xml-web-service.md)。</span><span class="sxs-lookup"><span data-stu-id="20fff-114">For an example of consuming a <xref:System.Data.DataSet> from an XML Web service, see [Consuming a DataSet from an XML Web Service](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/consuming-a-dataset-from-an-xml-web-service.md).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="20fff-115">本节内容</span><span class="sxs-lookup"><span data-stu-id="20fff-115">In This Section</span></span>  
 [<span data-ttu-id="20fff-116">创建数据集</span><span class="sxs-lookup"><span data-stu-id="20fff-116">Creating a DataSet</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/creating-a-dataset.md)  
 <span data-ttu-id="20fff-117">描述创建 <xref:System.Data.DataSet> 实例的语法。</span><span class="sxs-lookup"><span data-stu-id="20fff-117">Describes the syntax for creating an instance of a <xref:System.Data.DataSet>.</span></span>  
  
 [<span data-ttu-id="20fff-118">将数据表添加到数据集中</span><span class="sxs-lookup"><span data-stu-id="20fff-118">Adding a DataTable to a DataSet</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/adding-a-datatable-to-a-dataset.md)  
 <span data-ttu-id="20fff-119">描述如何创建表和列并将其添加到 <xref:System.Data.DataSet> 中。</span><span class="sxs-lookup"><span data-stu-id="20fff-119">Describes how to create and add tables and columns to a <xref:System.Data.DataSet>.</span></span>  
  
 [<span data-ttu-id="20fff-120">添加数据关系</span><span class="sxs-lookup"><span data-stu-id="20fff-120">Adding DataRelations</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/adding-datarelations.md)  
 <span data-ttu-id="20fff-121">描述如何创建 <xref:System.Data.DataSet> 中表之间的关系。</span><span class="sxs-lookup"><span data-stu-id="20fff-121">Describes how to create relations between tables in a <xref:System.Data.DataSet>.</span></span>  
  
 [<span data-ttu-id="20fff-122">导航数据关系</span><span class="sxs-lookup"><span data-stu-id="20fff-122">Navigating DataRelations</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/navigating-datarelations.md)  
 <span data-ttu-id="20fff-123">描述如何使用 <xref:System.Data.DataSet> 中表之间的关系来返回具有父子关系的子行或父行。</span><span class="sxs-lookup"><span data-stu-id="20fff-123">Describes how to use the relations between tables in a <xref:System.Data.DataSet> to return the child or parent rows of a parent-child relationship.</span></span>  
  
 [<span data-ttu-id="20fff-124">合并数据集内容</span><span class="sxs-lookup"><span data-stu-id="20fff-124">Merging DataSet Contents</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/merging-dataset-contents.md)  
 <span data-ttu-id="20fff-125">描述如何将一个 <xref:System.Data.DataSet>、<xref:System.Data.DataTable> 或 <xref:System.Data.DataRow> 数组的内容合并到另一个 <xref:System.Data.DataSet> 中。</span><span class="sxs-lookup"><span data-stu-id="20fff-125">Describes how to merge the contents of one <xref:System.Data.DataSet>, <xref:System.Data.DataTable>, or <xref:System.Data.DataRow> array into another <xref:System.Data.DataSet>.</span></span>  
  
 [<span data-ttu-id="20fff-126">复制数据集内容</span><span class="sxs-lookup"><span data-stu-id="20fff-126">Copying DataSet Contents</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/copying-dataset-contents.md)  
 <span data-ttu-id="20fff-127">描述如何创建可包含架构和指定数据的 <xref:System.Data.DataSet> 副本。</span><span class="sxs-lookup"><span data-stu-id="20fff-127">Describes how to create a copy of a <xref:System.Data.DataSet> that can contain schema as well as specified data.</span></span>  
  
 [<span data-ttu-id="20fff-128">处理数据集事件</span><span class="sxs-lookup"><span data-stu-id="20fff-128">Handling DataSet Events</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/handling-dataset-events.md)  
 <span data-ttu-id="20fff-129">描述 <xref:System.Data.DataSet> 的事件并说明如何使用这些事件。</span><span class="sxs-lookup"><span data-stu-id="20fff-129">Describes the events of a <xref:System.Data.DataSet> and how to use them.</span></span>  
  
 [<span data-ttu-id="20fff-130">类型化数据集</span><span class="sxs-lookup"><span data-stu-id="20fff-130">Typed DataSets</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/typed-datasets.md)  
 <span data-ttu-id="20fff-131">描述类型化 <xref:System.Data.DataSet> 的定义并说明如何创建和使用。</span><span class="sxs-lookup"><span data-stu-id="20fff-131">Discusses what a typed <xref:System.Data.DataSet> is and how to create and use it.</span></span>  
  
 [<span data-ttu-id="20fff-132">数据表</span><span class="sxs-lookup"><span data-stu-id="20fff-132">DataTables</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/datatables.md)  
 <span data-ttu-id="20fff-133">描述如何创建 <xref:System.Data.DataTable>、定义架构和处理数据。</span><span class="sxs-lookup"><span data-stu-id="20fff-133">Describes how to create a <xref:System.Data.DataTable>, define the schema, and manipulate data.</span></span>  
  
 [<span data-ttu-id="20fff-134">DataTableReader</span><span class="sxs-lookup"><span data-stu-id="20fff-134">DataTableReaders</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/datatablereaders.md)  
 <span data-ttu-id="20fff-135">描述如何创建和使用 <xref:System.Data.DataTableReader>。</span><span class="sxs-lookup"><span data-stu-id="20fff-135">Describes how to create and use a <xref:System.Data.DataTableReader>.</span></span>  
  
 [<span data-ttu-id="20fff-136">数据视图</span><span class="sxs-lookup"><span data-stu-id="20fff-136">DataViews</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/dataviews.md)  
 <span data-ttu-id="20fff-137">描述如何创建和使用 `DataViews` 以及如何使用 <xref:System.Data.DataView> 事件。</span><span class="sxs-lookup"><span data-stu-id="20fff-137">Describes how to create and work with `DataViews` and work with <xref:System.Data.DataView> events.</span></span>  
  
 [<span data-ttu-id="20fff-138">在数据集中使用 XML</span><span class="sxs-lookup"><span data-stu-id="20fff-138">Using XML in a DataSet</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/using-xml-in-a-dataset.md)  
 <span data-ttu-id="20fff-139">描述 <xref:System.Data.DataSet> 如何作为数据源与 XML 进行交互（包括以 XML 数据的形式加载和保持 <xref:System.Data.DataSet> 的内容）。</span><span class="sxs-lookup"><span data-stu-id="20fff-139">Describes how the <xref:System.Data.DataSet> interacts with XML as a data source, including loading and persisting the contents of a <xref:System.Data.DataSet> as XML data.</span></span>  
  
 [<span data-ttu-id="20fff-140">通过 XML Web service 使用数据集</span><span class="sxs-lookup"><span data-stu-id="20fff-140">Consuming a DataSet from an XML Web Service</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/consuming-a-dataset-from-an-xml-web-service.md)  
 <span data-ttu-id="20fff-141">描述如何创建使用 <xref:System.Data.DataSet> 来传输数据的 XML Web services。</span><span class="sxs-lookup"><span data-stu-id="20fff-141">Describes how to create an XML Web service that uses a <xref:System.Data.DataSet> to transport data.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="20fff-142">相关章节</span><span class="sxs-lookup"><span data-stu-id="20fff-142">Related Sections</span></span>  
 [<span data-ttu-id="20fff-143">ADO.NET 新增功能</span><span class="sxs-lookup"><span data-stu-id="20fff-143">What's New in ADO.NET</span></span>](../../../../../docs/framework/data/adonet/whats-new.md)  
 <span data-ttu-id="20fff-144">介绍 ADO.NET 中的新增功能。</span><span class="sxs-lookup"><span data-stu-id="20fff-144">Introduces features that are new in ADO.NET.</span></span>  
  
 [<span data-ttu-id="20fff-145">ADO.NET 概述</span><span class="sxs-lookup"><span data-stu-id="20fff-145">ADO.NET Overview</span></span>](../../../../../docs/framework/data/adonet/ado-net-overview.md)  
 <span data-ttu-id="20fff-146">提供对 ADO.NET 设计和组件的介绍。</span><span class="sxs-lookup"><span data-stu-id="20fff-146">Provides an introduction to the design and components of ADO.NET.</span></span>  
  
 [<span data-ttu-id="20fff-147">从 DataAdapter 填充数据集</span><span class="sxs-lookup"><span data-stu-id="20fff-147">Populating a DataSet from a DataAdapter</span></span>](../../../../../docs/framework/data/adonet/populating-a-dataset-from-a-dataadapter.md)  
 <span data-ttu-id="20fff-148">描述如何从数据源加载包含数据的**数据集**。</span><span class="sxs-lookup"><span data-stu-id="20fff-148">Describes how to load a **DataSet** with data from a data source.</span></span>  
  
 [<span data-ttu-id="20fff-149">使用 DataAdapter 更新数据源</span><span class="sxs-lookup"><span data-stu-id="20fff-149">Updating Data Sources with DataAdapters</span></span>](../../../../../docs/framework/data/adonet/updating-data-sources-with-dataadapters.md)  
 <span data-ttu-id="20fff-150">描述如何将对**数据集**中的数据的更改解析回数据源。</span><span class="sxs-lookup"><span data-stu-id="20fff-150">Describes how to resolve changes to the data in a **DataSet** back to the data source.</span></span>  
  
 [<span data-ttu-id="20fff-151">将现有约束添加到数据集</span><span class="sxs-lookup"><span data-stu-id="20fff-151">Adding Existing Constraints to a DataSet</span></span>](../../../../../docs/framework/data/adonet/adding-existing-constraints-to-a-dataset.md)  
 <span data-ttu-id="20fff-152">描述如何使用数据源中的主键信息填充**数据集**。</span><span class="sxs-lookup"><span data-stu-id="20fff-152">Describes how to populate a **DataSet** with primary key information from a data source.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="20fff-153">请参阅</span><span class="sxs-lookup"><span data-stu-id="20fff-153">See Also</span></span>  
 [<span data-ttu-id="20fff-154">ADO.NET</span><span class="sxs-lookup"><span data-stu-id="20fff-154">ADO.NET</span></span>](../../../../../docs/framework/data/adonet/index.md)  
 [<span data-ttu-id="20fff-155">ADO.NET 托管提供程序和数据集开发人员中心</span><span class="sxs-lookup"><span data-stu-id="20fff-155">ADO.NET Managed Providers and DataSet Developer Center</span></span>](http://go.microsoft.com/fwlink/?LinkId=217917)
