---
title: DataTables
ms.date: 03/30/2017
ms.assetid: 52ff0e32-3e5a-41de-9a3b-7b04ea52b83e
ms.openlocfilehash: 2849d159fbfdb0c0739b76fd288a987d4ce3d02f
ms.sourcegitcommit: 3c1c3ba79895335ff3737934e39372555ca7d6d0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/05/2018
ms.locfileid: "43786054"
---
# <a name="datatables"></a><span data-ttu-id="bc0bb-102">DataTables</span><span class="sxs-lookup"><span data-stu-id="bc0bb-102">DataTables</span></span>
<span data-ttu-id="bc0bb-103"><xref:System.Data.DataSet> 由表、关系和约束的集合组成。</span><span class="sxs-lookup"><span data-stu-id="bc0bb-103">A <xref:System.Data.DataSet> is made up of a collection of tables, relationships, and constraints.</span></span> <span data-ttu-id="bc0bb-104">在 ADO.NET 中，<xref:System.Data.DataTable>对象用于表示中的表**数据集**。</span><span class="sxs-lookup"><span data-stu-id="bc0bb-104">In ADO.NET, <xref:System.Data.DataTable> objects are used to represent the tables in a **DataSet**.</span></span> <span data-ttu-id="bc0bb-105">一个**DataTable**表示的内存中关系数据; 一个表的数据是本地的。它驻留，但可以从数据源，例如 Microsoft SQL Server 使用填充的基于网络的应用程序**DataAdapter**有关详细信息，请参阅[填充数据集从 DataAdapter](../../../../../docs/framework/data/adonet/populating-a-dataset-from-a-dataadapter.md).</span><span class="sxs-lookup"><span data-stu-id="bc0bb-105">A **DataTable** represents one table of in-memory relational data; the data is local to the .NET-based application in which it resides, but can be populated from a data source such as Microsoft SQL Server using a **DataAdapter** For more information, see [Populating a DataSet from a DataAdapter](../../../../../docs/framework/data/adonet/populating-a-dataset-from-a-dataadapter.md).</span></span>  
  
 <span data-ttu-id="bc0bb-106">**DataTable**类是的成员**System.Data**中的.NET Framework 类库命名空间。</span><span class="sxs-lookup"><span data-stu-id="bc0bb-106">The **DataTable** class is a member of the **System.Data** namespace within the .NET Framework class library.</span></span> <span data-ttu-id="bc0bb-107">可以创建和使用**DataTable**单独或作为的成员**数据集**，并**DataTable**对象还可在与其他.NET Framework 对象，一起使用包括<xref:System.Data.DataView>。</span><span class="sxs-lookup"><span data-stu-id="bc0bb-107">You can create and use a **DataTable** independently or as a member of a **DataSet**, and **DataTable** objects can also be used in conjunction with other .NET Framework objects, including the <xref:System.Data.DataView>.</span></span> <span data-ttu-id="bc0bb-108">访问的表中的集合**数据集**通过**表**属性**数据集**对象。</span><span class="sxs-lookup"><span data-stu-id="bc0bb-108">You access the collection of tables in a **DataSet** through the **Tables** property of the **DataSet** object.</span></span>  
  
 <span data-ttu-id="bc0bb-109">表的架构或结构由列和约束表示。</span><span class="sxs-lookup"><span data-stu-id="bc0bb-109">The schema, or structure of a table is represented by columns and constraints.</span></span> <span data-ttu-id="bc0bb-110">定义的架构**DataTable**使用<xref:System.Data.DataColumn>对象，以及<xref:System.Data.ForeignKeyConstraint>和<xref:System.Data.UniqueConstraint>对象。</span><span class="sxs-lookup"><span data-stu-id="bc0bb-110">You define the schema of a **DataTable** using <xref:System.Data.DataColumn> objects as well as <xref:System.Data.ForeignKeyConstraint> and <xref:System.Data.UniqueConstraint> objects.</span></span> <span data-ttu-id="bc0bb-111">表中的列可以映射到数据源中的列、包含从表达式计算所得的值、自动递增它们的值，或包含主键值。</span><span class="sxs-lookup"><span data-stu-id="bc0bb-111">The columns in a table can map to columns in a data source, contain calculated values from expressions, automatically increment their values, or contain primary key values.</span></span>  
  
 <span data-ttu-id="bc0bb-112">架构，除了**DataTable**还必须具有要包含并对数据排序的行。</span><span class="sxs-lookup"><span data-stu-id="bc0bb-112">In addition to a schema, a **DataTable** must also have rows to contain and order data.</span></span> <span data-ttu-id="bc0bb-113"><xref:System.Data.DataRow> 类表示表中包含的实际数据。</span><span class="sxs-lookup"><span data-stu-id="bc0bb-113">The <xref:System.Data.DataRow> class represents the actual data contained in a table.</span></span> <span data-ttu-id="bc0bb-114">您使用**DataRow**和其属性和方法用于检索、 计算和处理表中的数据。</span><span class="sxs-lookup"><span data-stu-id="bc0bb-114">You use the **DataRow** and its properties and methods to retrieve, evaluate, and manipulate the data in a table.</span></span> <span data-ttu-id="bc0bb-115">在访问和更改的行的数据**DataRow**对象维护其当前和原始状态。</span><span class="sxs-lookup"><span data-stu-id="bc0bb-115">As you access and change the data within a row, the **DataRow** object maintains both its current and original state.</span></span>  
  
 <span data-ttu-id="bc0bb-116">您可以使用表中的一个或多个相关的列来创建表与表之间的父子关系。</span><span class="sxs-lookup"><span data-stu-id="bc0bb-116">You can create parent-child relationships between tables using one or more related columns in the tables.</span></span> <span data-ttu-id="bc0bb-117">创建之间的关系**DataTable**对象使用<xref:System.Data.DataRelation>。</span><span class="sxs-lookup"><span data-stu-id="bc0bb-117">You create a relationship between **DataTable** objects using a <xref:System.Data.DataRelation>.</span></span> <span data-ttu-id="bc0bb-118">**DataRelation**对象然后可用于返回特定行的相关的子或父行。</span><span class="sxs-lookup"><span data-stu-id="bc0bb-118">**DataRelation** objects can then be used to return the related child or parent rows of a particular row.</span></span> <span data-ttu-id="bc0bb-119">有关详细信息，请参阅[添加 Datarelation](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/adding-datarelations.md)。</span><span class="sxs-lookup"><span data-stu-id="bc0bb-119">For more information, see [Adding DataRelations](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/adding-datarelations.md).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="bc0bb-120">本节内容</span><span class="sxs-lookup"><span data-stu-id="bc0bb-120">In This Section</span></span>  
 [<span data-ttu-id="bc0bb-121">创建数据表</span><span class="sxs-lookup"><span data-stu-id="bc0bb-121">Creating a DataTable</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/creating-a-datatable.md)  
 <span data-ttu-id="bc0bb-122">说明如何创建**DataTable**并将其添加到**数据集**。</span><span class="sxs-lookup"><span data-stu-id="bc0bb-122">Explains how to create a **DataTable** and add it to a **DataSet**.</span></span>  
  
 [<span data-ttu-id="bc0bb-123">数据表架构定义</span><span class="sxs-lookup"><span data-stu-id="bc0bb-123">DataTable Schema Definition</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/datatable-schema-definition.md)  
 <span data-ttu-id="bc0bb-124">提供有关创建和使用信息**DataColumn**对象和约束。</span><span class="sxs-lookup"><span data-stu-id="bc0bb-124">Provides information about creating and using **DataColumn** objects and constraints.</span></span>  
  
 [<span data-ttu-id="bc0bb-125">操作数据表中的数据</span><span class="sxs-lookup"><span data-stu-id="bc0bb-125">Manipulating Data in a DataTable</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/manipulating-data-in-a-datatable.md)  
 <span data-ttu-id="bc0bb-126">说明如何添加、修改和删除表中的数据。</span><span class="sxs-lookup"><span data-stu-id="bc0bb-126">Explains how to add, modify, and delete data in a table.</span></span> <span data-ttu-id="bc0bb-127">说明如何使用**DataTable**事件来检查对表中的数据的更改。</span><span class="sxs-lookup"><span data-stu-id="bc0bb-127">Explains how to use **DataTable** events to examine changes to data in the table.</span></span>  
  
 [<span data-ttu-id="bc0bb-128">处理数据表事件</span><span class="sxs-lookup"><span data-stu-id="bc0bb-128">Handling DataTable Events</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/handling-datatable-events.md)  
 <span data-ttu-id="bc0bb-129">用于提供有关可用的事件信息**DataTable**，包括修改列值和添加或删除行时的事件。</span><span class="sxs-lookup"><span data-stu-id="bc0bb-129">Provides information about the events available for use with a **DataTable**, including events when column values are modified and rows are added or deleted.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="bc0bb-130">相关章节</span><span class="sxs-lookup"><span data-stu-id="bc0bb-130">Related Sections</span></span>  
 [<span data-ttu-id="bc0bb-131">ADO.NET</span><span class="sxs-lookup"><span data-stu-id="bc0bb-131">ADO.NET</span></span>](../../../../../docs/framework/data/adonet/index.md)  
 <span data-ttu-id="bc0bb-132">描述 ADO.NET 结构和组件，并说明如何用来访问现有的数据源和管理应用程序数据。</span><span class="sxs-lookup"><span data-stu-id="bc0bb-132">Describes the ADO.NET architecture and components, and how to use them to access existing data sources and manage application data.</span></span>  
  
 [<span data-ttu-id="bc0bb-133">数据集、数据表和数据视图</span><span class="sxs-lookup"><span data-stu-id="bc0bb-133">DataSets, DataTables, and DataViews</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/index.md)  
 <span data-ttu-id="bc0bb-134">提供有关 ADO.NET 的信息**数据集**包括如何创建表之间的关系。</span><span class="sxs-lookup"><span data-stu-id="bc0bb-134">Provides information about the ADO.NET **DataSet** including how to create relationships between tables.</span></span>  
  
 <xref:System.Data.Constraint>  
 <span data-ttu-id="bc0bb-135">有关提供的参考信息**约束**对象。</span><span class="sxs-lookup"><span data-stu-id="bc0bb-135">Provides reference information about the **Constraint** object.</span></span>  
  
 <xref:System.Data.DataColumn>  
 <span data-ttu-id="bc0bb-136">有关提供的参考信息**DataColumn**对象。</span><span class="sxs-lookup"><span data-stu-id="bc0bb-136">Provides reference information about the **DataColumn** object.</span></span>  
  
 <xref:System.Data.DataSet>  
 <span data-ttu-id="bc0bb-137">有关提供的参考信息**数据集**对象。</span><span class="sxs-lookup"><span data-stu-id="bc0bb-137">Provides reference information about the **DataSet** object.</span></span>  
  
 <xref:System.Data.DataTable>  
 <span data-ttu-id="bc0bb-138">有关提供的参考信息**DataTable**对象。</span><span class="sxs-lookup"><span data-stu-id="bc0bb-138">Provides reference information about the **DataTable** object.</span></span>  
  
 [<span data-ttu-id="bc0bb-139">类库概述</span><span class="sxs-lookup"><span data-stu-id="bc0bb-139">Class Library Overview</span></span>](../../../../../docs/standard/class-library-overview.md)  
 <span data-ttu-id="bc0bb-140">概述了.NET Framework 类库，包括**系统**命名空间以及第二个级别的命名空间**System.Data**。</span><span class="sxs-lookup"><span data-stu-id="bc0bb-140">Provides an overview of the .NET Framework class library, including the **System** namespace as well as its second-level namespace, **System.Data**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bc0bb-141">请参阅</span><span class="sxs-lookup"><span data-stu-id="bc0bb-141">See Also</span></span>  
 [<span data-ttu-id="bc0bb-142">ADO.NET 托管提供程序和数据集开发人员中心</span><span class="sxs-lookup"><span data-stu-id="bc0bb-142">ADO.NET Managed Providers and DataSet Developer Center</span></span>](https://go.microsoft.com/fwlink/?LinkId=217917)
