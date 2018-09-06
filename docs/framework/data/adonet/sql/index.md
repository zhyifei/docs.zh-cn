---
title: SQL Server 和 ADO.NET
ms.date: 03/30/2017
ms.assetid: c18b1fb1-2af1-4de7-80a4-95e56fd976cb
ms.openlocfilehash: 32fc946f46ddac63d87b7e5a3d8f7120799f7223
ms.sourcegitcommit: a885cc8c3e444ca6471348893d5373c6e9e49a47
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/06/2018
ms.locfileid: "43885926"
---
# <a name="sql-server-and-adonet"></a><span data-ttu-id="20664-102">SQL Server 和 ADO.NET</span><span class="sxs-lookup"><span data-stu-id="20664-102">SQL Server and ADO.NET</span></span>
<span data-ttu-id="20664-103">本节描述适用于 SQL Server 的 .NET Framework 数据提供程序 (<xref:System.Data.SqlClient>) 特定的功能和行为。</span><span class="sxs-lookup"><span data-stu-id="20664-103">This section describes features and behaviors that are specific to the .NET Framework Data Provider for SQL Server (<xref:System.Data.SqlClient>).</span></span>  
  
 <span data-ttu-id="20664-104"><xref:System.Data.SqlClient> 提供了对 SQL Server 各版本的访问，而 SQL Server 封装了数据库特定协议。</span><span class="sxs-lookup"><span data-stu-id="20664-104"><xref:System.Data.SqlClient> provides access to versions of SQL Server, which encapsulates database-specific protocols.</span></span> <span data-ttu-id="20664-105">该数据提供程序设计的功能与 OLE DB、ODBC 和 Oracle 的 .NET Framework 数据提供程序的功能类似。</span><span class="sxs-lookup"><span data-stu-id="20664-105">The functionality of the data provider is designed to be similar to that of the .NET Framework data providers for OLE DB, ODBC, and Oracle.</span></span> <span data-ttu-id="20664-106"><xref:System.Data.SqlClient> 包括一个表格格式数据流 (TDS) 分析器以直接与 SQL Server 进行通信。</span><span class="sxs-lookup"><span data-stu-id="20664-106"><xref:System.Data.SqlClient> includes a tabular data stream (TDS) parser to communicate directly with SQL Server.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="20664-107">要使用 SQL Server .NET Framework 数据提供程序，应用程序必须引用 <xref:System.Data.SqlClient> 命名空间。</span><span class="sxs-lookup"><span data-stu-id="20664-107">To use the .NET Framework Data Provider for SQL Server, an application must reference the <xref:System.Data.SqlClient> namespace.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="20664-108">本节内容</span><span class="sxs-lookup"><span data-stu-id="20664-108">In This Section</span></span>  
 [<span data-ttu-id="20664-109">SQL Server 安全性</span><span class="sxs-lookup"><span data-stu-id="20664-109">SQL Server Security</span></span>](../../../../../docs/framework/data/adonet/sql/sql-server-security.md)  
 <span data-ttu-id="20664-110">概述 SQL Server 安全功能以及用于创建面向 SQL Server 的安全 ADO.NET 应用程序的应用方案。</span><span class="sxs-lookup"><span data-stu-id="20664-110">Provides an overview of SQL Server security features, and application scenarios for creating secure ADO.NET applications that target SQL Server.</span></span>  
  
 [<span data-ttu-id="20664-111">SQL Server 数据类型和 ADO.NET</span><span class="sxs-lookup"><span data-stu-id="20664-111">SQL Server Data Types and ADO.NET</span></span>](../../../../../docs/framework/data/adonet/sql/sql-server-data-types.md)  
 <span data-ttu-id="20664-112">描述如何使用 SQL Server 数据类型以及这些数据类型如何与 .NET Framework 数据类型进行交互。</span><span class="sxs-lookup"><span data-stu-id="20664-112">Describes how to work with SQL Server data types and how they interact with .NET Framework data types.</span></span>  
  
 [<span data-ttu-id="20664-113">SQL Server 二进制和大值数据</span><span class="sxs-lookup"><span data-stu-id="20664-113">SQL Server Binary and Large-Value Data</span></span>](../../../../../docs/framework/data/adonet/sql/sql-server-binary-and-large-value-data.md)  
 <span data-ttu-id="20664-114">描述如何在 SQL Server 中使用大值数据。</span><span class="sxs-lookup"><span data-stu-id="20664-114">Describes how to work with large value data in SQL Server.</span></span>  
  
 [<span data-ttu-id="20664-115">ADO.NET 中的 SQL Server 数据操作</span><span class="sxs-lookup"><span data-stu-id="20664-115">SQL Server Data Operations in ADO.NET</span></span>](../../../../../docs/framework/data/adonet/sql/sql-server-data-operations.md)  
 <span data-ttu-id="20664-116">说明如何使用 SQL Server 中的数据。</span><span class="sxs-lookup"><span data-stu-id="20664-116">Describes how to work with data in SQL Server.</span></span> <span data-ttu-id="20664-117">包含有关批量复制操作、MARS、异步操作和表值参数的各节。</span><span class="sxs-lookup"><span data-stu-id="20664-117">Contains sections about bulk copy operations, MARS, asynchronous operations, and table-valued parameters.</span></span>  
  
 [<span data-ttu-id="20664-118">SQL Server 功能和 ADO.NET</span><span class="sxs-lookup"><span data-stu-id="20664-118">SQL Server Features and ADO.NET</span></span>](../../../../../docs/framework/data/adonet/sql/sql-server-features-and-adonet.md)  
 <span data-ttu-id="20664-119">描述对 ADO.NET 应用程序开发人员十分有用的 SQL Server 功能。</span><span class="sxs-lookup"><span data-stu-id="20664-119">Describes SQL Server features that are useful for ADO.NET application developers.</span></span>  
  
 [<span data-ttu-id="20664-120">LINQ to SQL</span><span class="sxs-lookup"><span data-stu-id="20664-120">LINQ to SQL</span></span>](../../../../../docs/framework/data/adonet/sql/linq/index.md)  
 <span data-ttu-id="20664-121">描述创建 LINQ to SQL 应用程序所需的基本构造块、进程和技术。</span><span class="sxs-lookup"><span data-stu-id="20664-121">Describes the basic building blocks, processes, and techniques required for creating LINQ to SQL applications.</span></span>  
  
 <span data-ttu-id="20664-122">有关 SQL Server 数据库引擎的完整文档，请参见与您所使用的 SQL Server 版本对应的 SQL Server 联机丛书。</span><span class="sxs-lookup"><span data-stu-id="20664-122">For complete documentation of the SQL Server Database Engine, see SQL Server Books Online for the version of SQL Server you are using.</span></span>  
  
 [<span data-ttu-id="20664-123">SQL Server 联机丛书</span><span class="sxs-lookup"><span data-stu-id="20664-123">SQL Server Books Online</span></span>](/sql/sql-server/sql-server-technical-documentation)  
  
## <a name="see-also"></a><span data-ttu-id="20664-124">请参阅</span><span class="sxs-lookup"><span data-stu-id="20664-124">See Also</span></span>  
 [<span data-ttu-id="20664-125">保证 ADO.NET 应用程序的安全</span><span class="sxs-lookup"><span data-stu-id="20664-125">Securing ADO.NET Applications</span></span>](../../../../../docs/framework/data/adonet/securing-ado-net-applications.md)  
 [<span data-ttu-id="20664-126">ADO.NET 中的数据类型映射</span><span class="sxs-lookup"><span data-stu-id="20664-126">Data Type Mappings in ADO.NET</span></span>](../../../../../docs/framework/data/adonet/data-type-mappings-in-ado-net.md)  
 [<span data-ttu-id="20664-127">数据集、数据表和数据视图</span><span class="sxs-lookup"><span data-stu-id="20664-127">DataSets, DataTables, and DataViews</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/index.md)  
 [<span data-ttu-id="20664-128">在 ADO.NET 中检索和修改数据</span><span class="sxs-lookup"><span data-stu-id="20664-128">Retrieving and Modifying Data in ADO.NET</span></span>](../../../../../docs/framework/data/adonet/retrieving-and-modifying-data.md)  
 [<span data-ttu-id="20664-129">ADO.NET 托管提供程序和数据集开发人员中心</span><span class="sxs-lookup"><span data-stu-id="20664-129">ADO.NET Managed Providers and DataSet Developer Center</span></span>](https://go.microsoft.com/fwlink/?LinkId=217917)
