---
title: "DataAdapter 和 DataReader"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: cc952ca2-ec19-46ab-9189-15174b52cb74
caps.latest.revision: "4"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.workload: dotnet
ms.openlocfilehash: 6d071622862a645d11ea8228574f81d5f8c3e6e2
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="dataadapters-and-datareaders"></a><span data-ttu-id="e262a-102">DataAdapter 和 DataReader</span><span class="sxs-lookup"><span data-stu-id="e262a-102">DataAdapters and DataReaders</span></span>
<span data-ttu-id="e262a-103">你可以使用 ADO.NET **DataReader**以从数据库中检索数据的只读、 只进流。</span><span class="sxs-lookup"><span data-stu-id="e262a-103">You can use the ADO.NET **DataReader** to retrieve a read-only, forward-only stream of data from a database.</span></span> <span data-ttu-id="e262a-104">查询执行，以及存储在客户端上的网络缓冲区，直到你请求时，这些结果将返回使用**读取**方法**DataReader**。</span><span class="sxs-lookup"><span data-stu-id="e262a-104">Results are returned as the query executes, and are stored in the network buffer on the client until you request them using the **Read** method of the **DataReader**.</span></span> <span data-ttu-id="e262a-105">使用**DataReader**可以提高应用程序性能，检索数据，只要它不可用，并且 （默认） 存储在内存，从而减少系统开销中一次只有一个行。</span><span class="sxs-lookup"><span data-stu-id="e262a-105">Using the **DataReader** can increase application performance both by retrieving data as soon as it is available, and (by default) storing only one row at a time in memory, reducing system overhead.</span></span>  
  
 <span data-ttu-id="e262a-106"><xref:System.Data.Common.DataAdapter> 用于从数据源检索数据并填充 <xref:System.Data.DataSet> 中的表。</span><span class="sxs-lookup"><span data-stu-id="e262a-106">A <xref:System.Data.Common.DataAdapter> is used to retrieve data from a data source and populate tables within a <xref:System.Data.DataSet>.</span></span> <span data-ttu-id="e262a-107">`DataAdapter` 还可将对 `DataSet` 所做的更改解析回数据源。</span><span class="sxs-lookup"><span data-stu-id="e262a-107">The `DataAdapter` also resolves changes made to the `DataSet` back to the data source.</span></span> <span data-ttu-id="e262a-108">`DataAdapter` 使用 .NET Framework 数据提供程序的 `Connection` 对象连接到数据源，并使用 `Command` 对象从数据源检索数据以及将更改解析回数据源。</span><span class="sxs-lookup"><span data-stu-id="e262a-108">The `DataAdapter` uses the `Connection` object of the .NET Framework data provider to connect to a data source, and it uses `Command` objects to retrieve data from and resolve changes to the data source.</span></span>  
  
 <span data-ttu-id="e262a-109">随 .NET Framework 提供的每个 .NET Framework 数据提供程序都具有一个 <xref:System.Data.Common.DbDataReader> 和一个 <xref:System.Data.Common.DbDataAdapter> 对象：用于 OLE DB 的 .NET Framework 数据提供程序包括一个 <xref:System.Data.OleDb.OleDbDataReader> 和一个 <xref:System.Data.OleDb.OleDbDataAdapter> 对象，用于 SQL Server 的 .NET Framework 数据提供程序包括一个 <xref:System.Data.SqlClient.SqlDataReader> 和一个 <xref:System.Data.SqlClient.SqlDataAdapter> 对象，用于 ODBC 的 .NET Framework 数据提供程序包括一个 <xref:System.Data.Odbc.OdbcDataReader> 和一个 <xref:System.Data.Odbc.OdbcDataAdapter> 对象，用于 Oracle 的 .NET Framework 数据提供程序包括一个 <xref:System.Data.OracleClient.OracleDataReader> 和一个 <xref:System.Data.OracleClient.OracleDataAdapter> 对象。</span><span class="sxs-lookup"><span data-stu-id="e262a-109">Each .NET Framework data provider included with the .NET Framework has a <xref:System.Data.Common.DbDataReader> and a <xref:System.Data.Common.DbDataAdapter> object: the .NET Framework Data Provider for OLE DB includes an <xref:System.Data.OleDb.OleDbDataReader> and an <xref:System.Data.OleDb.OleDbDataAdapter> object, the .NET Framework Data Provider for SQL Server includes a <xref:System.Data.SqlClient.SqlDataReader> and a <xref:System.Data.SqlClient.SqlDataAdapter> object, the .NET Framework Data Provider for ODBC includes an <xref:System.Data.Odbc.OdbcDataReader> and an <xref:System.Data.Odbc.OdbcDataAdapter> object, and the .NET Framework Data Provider for Oracle includes an <xref:System.Data.OracleClient.OracleDataReader> and an <xref:System.Data.OracleClient.OracleDataAdapter> object.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="e262a-110">本节内容</span><span class="sxs-lookup"><span data-stu-id="e262a-110">In This Section</span></span>  
 [<span data-ttu-id="e262a-111">使用 DataReader 检索 ADO 数据</span><span class="sxs-lookup"><span data-stu-id="e262a-111">Retrieving Data Using a DataReader</span></span>](../../../../docs/framework/data/adonet/retrieving-data-using-a-datareader.md)  
 <span data-ttu-id="e262a-112">描述 ADO.NET **DataReader**对象以及如何使用它从数据源返回结果流。</span><span class="sxs-lookup"><span data-stu-id="e262a-112">Describes the ADO.NET **DataReader** object and how to use it to return a stream of results from a data source.</span></span>  
  
 [<span data-ttu-id="e262a-113">从 DataAdapter 填充数据集</span><span class="sxs-lookup"><span data-stu-id="e262a-113">Populating a DataSet from a DataAdapter</span></span>](../../../../docs/framework/data/adonet/populating-a-dataset-from-a-dataadapter.md)  
 <span data-ttu-id="e262a-114">说明如何通过 `DataSet` 使用表、列和行填充 `DataAdapter`。</span><span class="sxs-lookup"><span data-stu-id="e262a-114">Describes how to fill a `DataSet` with tables, columns, and rows by using a `DataAdapter`.</span></span>  
  
 [<span data-ttu-id="e262a-115">DataAdapter 参数</span><span class="sxs-lookup"><span data-stu-id="e262a-115">DataAdapter Parameters</span></span>](../../../../docs/framework/data/adonet/dataadapter-parameters.md)  
 <span data-ttu-id="e262a-116">说明如何与 `DataAdapter` 的命令属性一起使用参数，包括如何将 `DataSet` 的列内容映射到命令参数。</span><span class="sxs-lookup"><span data-stu-id="e262a-116">Describes how to use parameters with the command properties of a `DataAdapter` including how to map the contents of a column in a `DataSet` to a command parameter.</span></span>  
  
 [<span data-ttu-id="e262a-117">将现有约束添加到数据集</span><span class="sxs-lookup"><span data-stu-id="e262a-117">Adding Existing Constraints to a DataSet</span></span>](../../../../docs/framework/data/adonet/adding-existing-constraints-to-a-dataset.md)  
 <span data-ttu-id="e262a-118">说明如何将现有约束添加到 `DataSet`。</span><span class="sxs-lookup"><span data-stu-id="e262a-118">Describes how to add existing constraints to a `DataSet`.</span></span>  
  
 [<span data-ttu-id="e262a-119">DataAdapter 数据表和 DataColumn 映射</span><span class="sxs-lookup"><span data-stu-id="e262a-119">DataAdapter DataTable and DataColumn Mappings</span></span>](../../../../docs/framework/data/adonet/dataadapter-datatable-and-datacolumn-mappings.md)  
 <span data-ttu-id="e262a-120">说明如何为 `DataTableMappings` 设置 `ColumnMappings` 和 `DataAdapter`。</span><span class="sxs-lookup"><span data-stu-id="e262a-120">Describes how to set up `DataTableMappings` and `ColumnMappings` for a `DataAdapter`.</span></span>  
  
 [<span data-ttu-id="e262a-121">通过查询结果分页</span><span class="sxs-lookup"><span data-stu-id="e262a-121">Paging Through a Query Result</span></span>](../../../../docs/framework/data/adonet/paging-through-a-query-result.md)  
 <span data-ttu-id="e262a-122">提供一个以数据页形式查看查询结果的示例。</span><span class="sxs-lookup"><span data-stu-id="e262a-122">Provides an example of viewing the results of a query as pages of data.</span></span>  
  
 [<span data-ttu-id="e262a-123">使用 DataAdapter 更新数据源</span><span class="sxs-lookup"><span data-stu-id="e262a-123">Updating Data Sources with DataAdapters</span></span>](../../../../docs/framework/data/adonet/updating-data-sources-with-dataadapters.md)  
 <span data-ttu-id="e262a-124">说明如何使用 `DataAdapter` 将 `DataSet` 中的更改解析回数据库。</span><span class="sxs-lookup"><span data-stu-id="e262a-124">Describes how to use a `DataAdapter` to resolve changes in a `DataSet` back to the database.</span></span>  
  
 [<span data-ttu-id="e262a-125">处理 DataAdapter 事件</span><span class="sxs-lookup"><span data-stu-id="e262a-125">Handling DataAdapter Events</span></span>](../../../../docs/framework/data/adonet/handling-dataadapter-events.md)  
 <span data-ttu-id="e262a-126">说明 `DataAdapter` 事件以及如何使用这些事件。</span><span class="sxs-lookup"><span data-stu-id="e262a-126">Describes `DataAdapter` events and how to use them.</span></span>  
  
 [<span data-ttu-id="e262a-127">使用 DataAdapter 执行批处理操作</span><span class="sxs-lookup"><span data-stu-id="e262a-127">Performing Batch Operations Using DataAdapters</span></span>](../../../../docs/framework/data/adonet/performing-batch-operations-using-dataadapters.md)  
 <span data-ttu-id="e262a-128">说明在从 `DataSet` 应用更新时，如何通过减少与 SQL Server 之间的往返次数来提高应用程序的性能。</span><span class="sxs-lookup"><span data-stu-id="e262a-128">Describes enhancing application performance by reducing the number of round trips to SQL Server when applying updates from the `DataSet`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e262a-129">请参阅</span><span class="sxs-lookup"><span data-stu-id="e262a-129">See Also</span></span>  
 [<span data-ttu-id="e262a-130">连接到数据源</span><span class="sxs-lookup"><span data-stu-id="e262a-130">Connecting to a Data Source</span></span>](../../../../docs/framework/data/adonet/connecting-to-a-data-source.md)  
 [<span data-ttu-id="e262a-131">命令和参数</span><span class="sxs-lookup"><span data-stu-id="e262a-131">Commands and Parameters</span></span>](../../../../docs/framework/data/adonet/commands-and-parameters.md)  
 [<span data-ttu-id="e262a-132">事务和并发性</span><span class="sxs-lookup"><span data-stu-id="e262a-132">Transactions and Concurrency</span></span>](../../../../docs/framework/data/adonet/transactions-and-concurrency.md)  
 [<span data-ttu-id="e262a-133">数据集、数据表和数据视图</span><span class="sxs-lookup"><span data-stu-id="e262a-133">DataSets, DataTables, and DataViews</span></span>](../../../../docs/framework/data/adonet/dataset-datatable-dataview/index.md)  
 [<span data-ttu-id="e262a-134">ADO.NET 托管提供程序和数据集开发人员中心</span><span class="sxs-lookup"><span data-stu-id="e262a-134">ADO.NET Managed Providers and DataSet Developer Center</span></span>](http://go.microsoft.com/fwlink/?LinkId=217917)
