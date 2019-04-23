---
title: 检索数据库架构信息
ms.date: 03/30/2017
ms.assetid: 79038d52-f122-4fd4-9bfb-aaa22d6a114b
ms.openlocfilehash: 885d3c9ad61c9099c960ddb0c0f77fa8a98dbefa
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/18/2019
ms.locfileid: "59133700"
---
# <a name="retrieving-database-schema-information"></a><span data-ttu-id="ef7b2-102">检索数据库架构信息</span><span class="sxs-lookup"><span data-stu-id="ef7b2-102">Retrieving Database Schema Information</span></span>
<span data-ttu-id="ef7b2-103">从数据库获取架构信息通过架构发现过程来完成。</span><span class="sxs-lookup"><span data-stu-id="ef7b2-103">Obtaining schema information from a database is accomplished with the process of schema discovery.</span></span> <span data-ttu-id="ef7b2-104">架构发现，应用程序可以请求托管提供程序查找并返回有关数据库架构的信息也称为*元数据*，给定数据库。</span><span class="sxs-lookup"><span data-stu-id="ef7b2-104">Schema discovery allows applications to request that managed providers find and return information about the database schema, also known as *metadata*, of a given database.</span></span> <span data-ttu-id="ef7b2-105">不同的数据库架构元素（例如表、列和存储过程）通过架构集合进行公开。</span><span class="sxs-lookup"><span data-stu-id="ef7b2-105">Different database schema elements such as tables, columns, and stored-procedures are exposed through schema collections.</span></span> <span data-ttu-id="ef7b2-106">每个架构集合包含所使用的提供程序特定的各种架构信息。</span><span class="sxs-lookup"><span data-stu-id="ef7b2-106">Each schema collection contains a variety of schema information specific to the provider being used.</span></span>  
  
 <span data-ttu-id="ef7b2-107">每个.NET Framework 托管提供程序实现**GetSchema**中的方法**连接**类，并从返回的架构信息**GetSchema**方法采用的形式<xref:System.Data.DataTable>。</span><span class="sxs-lookup"><span data-stu-id="ef7b2-107">Each of the .NET Framework managed providers implement the **GetSchema** method in the **Connection** class, and the schema information that is returned from the **GetSchema** method comes in the form of a <xref:System.Data.DataTable>.</span></span> <span data-ttu-id="ef7b2-108">**GetSchema**方法是重载的方法，提供可选参数来指定架构集合返回，并限制返回的信息量。</span><span class="sxs-lookup"><span data-stu-id="ef7b2-108">The **GetSchema** method is an overloaded method that provides optional parameters for specifying the schema collection to return, and restricting the amount of information returned.</span></span>  
  
 <span data-ttu-id="ef7b2-109">提供.NET Framework 数据提供程序的 OLE DB、 ODBC、 Oracle 和 SqlClient **GetSchemaTable**方法，它返回描述列元数据的 DataTable **DataReader**。</span><span class="sxs-lookup"><span data-stu-id="ef7b2-109">The .NET Framework Data Providers for OLE DB, ODBC, Oracle, and SqlClient provide a **GetSchemaTable** method that returns a DataTable describing the column metadata of the **DataReader**.</span></span>  
  
 <span data-ttu-id="ef7b2-110">适用于 OLE DB 的 .NET Framework 数据提供程序还使用 <xref:System.Data.OleDb.OleDbConnection.GetOleDbSchemaTable%2A> 对象的 <xref:System.Data.OleDb.OleDbConnection> 方法来公开架构信息。</span><span class="sxs-lookup"><span data-stu-id="ef7b2-110">The .NET Framework Data Provider for OLE DB also exposes schema information by using the <xref:System.Data.OleDb.OleDbConnection.GetOleDbSchemaTable%2A> method of the <xref:System.Data.OleDb.OleDbConnection> object.</span></span> <span data-ttu-id="ef7b2-111">作为参数， **GetOleDbSchemaTable**采用<xref:System.Data.OleDb.OleDbSchemaGuid>，它标识要返回架构信息并对这些限制的数组返回的列。</span><span class="sxs-lookup"><span data-stu-id="ef7b2-111">As arguments, **GetOleDbSchemaTable** takes an <xref:System.Data.OleDb.OleDbSchemaGuid> that identifies the schema information to return, and an array of restrictions on those returned columns.</span></span> <span data-ttu-id="ef7b2-112">**GetOleDbSchemaTable**返回<xref:System.Data.DataTable>填充的请求的架构信息。</span><span class="sxs-lookup"><span data-stu-id="ef7b2-112">**GetOleDbSchemaTable** returns a <xref:System.Data.DataTable> populated with the requested schema information.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="ef7b2-113">本节内容</span><span class="sxs-lookup"><span data-stu-id="ef7b2-113">In This Section</span></span>  
 [<span data-ttu-id="ef7b2-114">GetSchema 和架构集合</span><span class="sxs-lookup"><span data-stu-id="ef7b2-114">GetSchema and Schema Collections</span></span>](../../../../docs/framework/data/adonet/getschema-and-schema-collections.md)  
 <span data-ttu-id="ef7b2-115">介绍**GetSchema**方法以及如何使用它来检索和限制数据库中的架构信息。</span><span class="sxs-lookup"><span data-stu-id="ef7b2-115">Describes the **GetSchema** method and how it can be used to retrieve and restrict schema information from a database.</span></span>  
  
 <span data-ttu-id="ef7b2-116">架构限制</span><span class="sxs-lookup"><span data-stu-id="ef7b2-116">Schema Restrictions</span></span>  
 <span data-ttu-id="ef7b2-117">描述可以用于架构限制**GetSchema**。</span><span class="sxs-lookup"><span data-stu-id="ef7b2-117">Describes schema restrictions that can be used with **GetSchema**.</span></span>  
  
 [<span data-ttu-id="ef7b2-118">公共架构集合</span><span class="sxs-lookup"><span data-stu-id="ef7b2-118">Common Schema Collections</span></span>](../../../../docs/framework/data/adonet/common-schema-collections.md)  
 <span data-ttu-id="ef7b2-119">描述所有 .NET Framework 托管提供程序均支持的所有通用架构集合。</span><span class="sxs-lookup"><span data-stu-id="ef7b2-119">Describes all of the common schema collections supported by all of the .NET Framework managed providers.</span></span>  
  
 [<span data-ttu-id="ef7b2-120">SQL Server 架构集合</span><span class="sxs-lookup"><span data-stu-id="ef7b2-120">SQL Server Schema Collections</span></span>](../../../../docs/framework/data/adonet/sql-server-schema-collections.md)  
 <span data-ttu-id="ef7b2-121">描述适用于 SQL Server 的 .NET Framework 提供程序支持的架构集合。</span><span class="sxs-lookup"><span data-stu-id="ef7b2-121">Describes the schema collection supported by the .NET Framework provider for SQL Server.</span></span>  
  
 [<span data-ttu-id="ef7b2-122">Oracle 架构集合</span><span class="sxs-lookup"><span data-stu-id="ef7b2-122">Oracle Schema Collections</span></span>](../../../../docs/framework/data/adonet/oracle-schema-collections.md)  
 <span data-ttu-id="ef7b2-123">描述适用于 Oracle 的 SQL Server .NET Framework 提供程序支持的架构集合。</span><span class="sxs-lookup"><span data-stu-id="ef7b2-123">Describes the schema collection supported by the .NET Framework provider for Oracle.</span></span>  
  
 [<span data-ttu-id="ef7b2-124">ODBC 架构集合</span><span class="sxs-lookup"><span data-stu-id="ef7b2-124">ODBC Schema Collections</span></span>](../../../../docs/framework/data/adonet/odbc-schema-collections.md)  
 <span data-ttu-id="ef7b2-125">描述 ODBC 驱动程序的架构集合。</span><span class="sxs-lookup"><span data-stu-id="ef7b2-125">Describes the schema collections for ODBC drivers.</span></span>  
  
 [<span data-ttu-id="ef7b2-126">OLE DB 架构集合</span><span class="sxs-lookup"><span data-stu-id="ef7b2-126">OLE DB Schema Collections</span></span>](../../../../docs/framework/data/adonet/ole-db-schema-collections.md)  
 <span data-ttu-id="ef7b2-127">描述 OLE DB 提供程序的架构集合。</span><span class="sxs-lookup"><span data-stu-id="ef7b2-127">Describes the schema collections for OLE DB providers.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="ef7b2-128">参考</span><span class="sxs-lookup"><span data-stu-id="ef7b2-128">Reference</span></span>  
 <xref:System.Data.Common.DbConnection.GetSchema%2A>  
 <span data-ttu-id="ef7b2-129">介绍**GetSchema**方法的<xref:System.Data.Common.DbConnection>类。</span><span class="sxs-lookup"><span data-stu-id="ef7b2-129">Describes the **GetSchema** method of the <xref:System.Data.Common.DbConnection> class.</span></span>  
  
 <xref:System.Data.Odbc.OdbcConnection.GetSchema%2A>  
 <span data-ttu-id="ef7b2-130">介绍**GetSchema**方法的<xref:System.Data.Odbc.OdbcConnection>类。</span><span class="sxs-lookup"><span data-stu-id="ef7b2-130">Describes the **GetSchema** method of the <xref:System.Data.Odbc.OdbcConnection> class.</span></span>  
  
 <xref:System.Data.OleDb.OleDbConnection.GetSchema%2A>  
 <span data-ttu-id="ef7b2-131">介绍**GetSchema**方法的<xref:System.Data.OleDb.OleDbConnection>类。</span><span class="sxs-lookup"><span data-stu-id="ef7b2-131">Describes the **GetSchema** method of the <xref:System.Data.OleDb.OleDbConnection> class.</span></span>  
  
 <xref:System.Data.OracleClient.OracleConnection.GetSchema%2A>  
 <span data-ttu-id="ef7b2-132">介绍**GetSchema**方法的<xref:System.Data.OracleClient.OracleConnection>类。</span><span class="sxs-lookup"><span data-stu-id="ef7b2-132">Describes the **GetSchema** method of the <xref:System.Data.OracleClient.OracleConnection> class.</span></span>  
  
 <xref:System.Data.SqlClient.SqlConnection.GetSchema%2A>  
 <span data-ttu-id="ef7b2-133">介绍**GetSchema**方法的<xref:System.Data.SqlClient.SqlConnection>类。</span><span class="sxs-lookup"><span data-stu-id="ef7b2-133">Describes the **GetSchema** method of the <xref:System.Data.SqlClient.SqlConnection> class.</span></span>  
  
 <xref:System.Data.Common.DbDataReader.GetSchemaTable%2A>  
 <span data-ttu-id="ef7b2-134">介绍**GetSchemaTable**方法的<xref:System.Data.Common.DbDataReader>类。</span><span class="sxs-lookup"><span data-stu-id="ef7b2-134">Describes the **GetSchemaTable** method of the <xref:System.Data.Common.DbDataReader> class.</span></span>  
  
 <xref:System.Data.Odbc.OdbcDataReader.GetSchemaTable%2A>  
 <span data-ttu-id="ef7b2-135">介绍**GetSchemaTable**方法的<xref:System.Data.Odbc.OdbcDataReader>类。</span><span class="sxs-lookup"><span data-stu-id="ef7b2-135">Describes the **GetSchemaTable** method of the <xref:System.Data.Odbc.OdbcDataReader> class.</span></span>  
  
 <xref:System.Data.OleDb.OleDbDataReader.GetSchemaTable%2A>  
 <span data-ttu-id="ef7b2-136">介绍**GetSchemaTable**方法的<xref:System.Data.OleDb.OleDbDataReader>类。</span><span class="sxs-lookup"><span data-stu-id="ef7b2-136">Describes the **GetSchemaTable** method of the <xref:System.Data.OleDb.OleDbDataReader> class.</span></span>  
  
 <xref:System.Data.OracleClient.OracleDataReader.GetSchemaTable%2A>  
 <span data-ttu-id="ef7b2-137">介绍**GetSchemaTable**方法的<xref:System.Data.OracleClient.OracleDataReader>类。</span><span class="sxs-lookup"><span data-stu-id="ef7b2-137">Describes the **GetSchemaTable** method of the <xref:System.Data.OracleClient.OracleDataReader> class.</span></span>  
  
 <xref:System.Data.SqlClient.SqlDataReader.GetSchemaTable%2A>  
 <span data-ttu-id="ef7b2-138">介绍**GetSchemaTable**方法的<xref:System.Data.SqlClient.SqlDataReader>类。</span><span class="sxs-lookup"><span data-stu-id="ef7b2-138">Describes the **GetSchemaTable** method of the <xref:System.Data.SqlClient.SqlDataReader> class.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ef7b2-139">请参阅</span><span class="sxs-lookup"><span data-stu-id="ef7b2-139">See also</span></span>

- [<span data-ttu-id="ef7b2-140">在 ADO.NET 中检索和修改数据</span><span class="sxs-lookup"><span data-stu-id="ef7b2-140">Retrieving and Modifying Data in ADO.NET</span></span>](../../../../docs/framework/data/adonet/retrieving-and-modifying-data.md)
- [<span data-ttu-id="ef7b2-141">ADO.NET 托管提供程序和数据集开发人员中心</span><span class="sxs-lookup"><span data-stu-id="ef7b2-141">ADO.NET Managed Providers and DataSet Developer Center</span></span>](https://go.microsoft.com/fwlink/?LinkId=217917)
