---
title: 连接到数据源
ms.date: 03/30/2017
ms.assetid: 9abc3f92-1be3-4e1a-b360-762dc689650e
ms.openlocfilehash: 84dc15c0965b7ac8209bd9115d611162e57d6dda
ms.sourcegitcommit: 19014f9c081ca2ff19652ca12503828db8239d48
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "76980244"
---
# <a name="connecting-to-a-data-source-in-adonet"></a><span data-ttu-id="74b3c-102">连接到 ADO.NET 中的数据源</span><span class="sxs-lookup"><span data-stu-id="74b3c-102">Connecting to a Data Source in ADO.NET</span></span>
<span data-ttu-id="74b3c-103">在 ADO.NET 中，可以通过在连接字符串中提供必要的身份验证信息来使用**连接**对象连接到特定数据源。</span><span class="sxs-lookup"><span data-stu-id="74b3c-103">In ADO.NET you use a **Connection** object to connect to a specific data source by supplying necessary authentication information in a connection string.</span></span> <span data-ttu-id="74b3c-104">使用的**连接**对象取决于数据源的类型。</span><span class="sxs-lookup"><span data-stu-id="74b3c-104">The **Connection** object you use depends on the type of data source.</span></span>  
  
 <span data-ttu-id="74b3c-105">随 .NET Framework 提供的每个 .NET Framework 数据提供程序都具有一个 <xref:System.Data.Common.DbConnection> 对象：适用于 OLE DB 的 .NET Framework 数据提供程序包括一个 <xref:System.Data.OleDb.OleDbConnection> 对象，适用于 SQL Server 的 .NET Framework 数据提供程序包括一个 <xref:System.Data.SqlClient.SqlConnection> 对象，适用于 ODBC 的 .NET Framework 数据提供程序包括一个 <xref:System.Data.Odbc.OdbcConnection> 对象，适用于 Oracle 的 .NET Framework 数据提供程序包括一个 <xref:System.Data.OracleClient.OracleConnection> 对象。</span><span class="sxs-lookup"><span data-stu-id="74b3c-105">Each .NET Framework data provider included with the .NET Framework has a <xref:System.Data.Common.DbConnection> object: the .NET Framework Data Provider for OLE DB includes an <xref:System.Data.OleDb.OleDbConnection> object, the .NET Framework Data Provider for SQL Server includes a <xref:System.Data.SqlClient.SqlConnection> object, the .NET Framework Data Provider for ODBC includes an <xref:System.Data.Odbc.OdbcConnection> object, and the .NET Framework Data Provider for Oracle includes an <xref:System.Data.OracleClient.OracleConnection> object.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="74b3c-106">本节内容</span><span class="sxs-lookup"><span data-stu-id="74b3c-106">In This Section</span></span>  
 [<span data-ttu-id="74b3c-107">建立连接</span><span class="sxs-lookup"><span data-stu-id="74b3c-107">Establishing the Connection</span></span>](establishing-the-connection.md)  
 <span data-ttu-id="74b3c-108">介绍如何使用**连接**对象建立与数据源的连接。</span><span class="sxs-lookup"><span data-stu-id="74b3c-108">Describes how to use a **Connection** object to establish a connection to a data source.</span></span>  
  
 [<span data-ttu-id="74b3c-109">连接事件</span><span class="sxs-lookup"><span data-stu-id="74b3c-109">Connection Events</span></span>](connection-events.md)  
 <span data-ttu-id="74b3c-110">介绍如何使用**InfoMessage**事件从数据源中检索信息性消息。</span><span class="sxs-lookup"><span data-stu-id="74b3c-110">Describes how to use an **InfoMessage** event to retrieve informational messages from a data source.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="74b3c-111">另请参阅</span><span class="sxs-lookup"><span data-stu-id="74b3c-111">See also</span></span>

- [<span data-ttu-id="74b3c-112">连接字符串</span><span class="sxs-lookup"><span data-stu-id="74b3c-112">Connection Strings</span></span>](connection-strings.md)
- [<span data-ttu-id="74b3c-113">连接池</span><span class="sxs-lookup"><span data-stu-id="74b3c-113">Connection Pooling</span></span>](connection-pooling.md)
- [<span data-ttu-id="74b3c-114">命令和参数</span><span class="sxs-lookup"><span data-stu-id="74b3c-114">Commands and Parameters</span></span>](commands-and-parameters.md)
- [<span data-ttu-id="74b3c-115">DataAdapters 和 DataReaders</span><span class="sxs-lookup"><span data-stu-id="74b3c-115">DataAdapters and DataReaders</span></span>](dataadapters-and-datareaders.md)
- [<span data-ttu-id="74b3c-116">事务和并发性</span><span class="sxs-lookup"><span data-stu-id="74b3c-116">Transactions and Concurrency</span></span>](transactions-and-concurrency.md)
- [<span data-ttu-id="74b3c-117">ADO.NET 概述</span><span class="sxs-lookup"><span data-stu-id="74b3c-117">ADO.NET Overview</span></span>](ado-net-overview.md)
