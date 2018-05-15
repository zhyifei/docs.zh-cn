---
title: 连接到 ADO.NET 中的数据源
ms.date: 03/30/2017
ms.assetid: 9abc3f92-1be3-4e1a-b360-762dc689650e
ms.openlocfilehash: 27653c3e1f14e08fc8b5e1225a441072778a0cc8
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/03/2018
---
# <a name="connecting-to-a-data-source-in-adonet"></a><span data-ttu-id="547a7-102">连接到 ADO.NET 中的数据源</span><span class="sxs-lookup"><span data-stu-id="547a7-102">Connecting to a Data Source in ADO.NET</span></span>
<span data-ttu-id="547a7-103">在 ADO.NET 中使用**连接**要通过提供必要的身份验证信息来连接字符串连接到特定数据源对象。</span><span class="sxs-lookup"><span data-stu-id="547a7-103">In ADO.NET you use a **Connection** object to connect to a specific data source by supplying necessary authentication information in a connection string.</span></span> <span data-ttu-id="547a7-104">**连接**你使用的对象取决于数据源的类型。</span><span class="sxs-lookup"><span data-stu-id="547a7-104">The **Connection** object you use depends on the type of data source.</span></span>  
  
 <span data-ttu-id="547a7-105">随 .NET Framework 提供的每个 .NET Framework 数据提供程序都具有一个 <xref:System.Data.Common.DbConnection> 对象：适用于 OLE DB 的 .NET Framework 数据提供程序包括一个 <xref:System.Data.OleDb.OleDbConnection> 对象，适用于 SQL Server 的 .NET Framework 数据提供程序包括一个 <xref:System.Data.SqlClient.SqlConnection> 对象，适用于 ODBC 的 .NET Framework 数据提供程序包括一个 <xref:System.Data.Odbc.OdbcConnection> 对象，适用于 Oracle 的 .NET Framework 数据提供程序包括一个 <xref:System.Data.OracleClient.OracleConnection> 对象。</span><span class="sxs-lookup"><span data-stu-id="547a7-105">Each .NET Framework data provider included with the .NET Framework has a <xref:System.Data.Common.DbConnection> object: the .NET Framework Data Provider for OLE DB includes an <xref:System.Data.OleDb.OleDbConnection> object, the .NET Framework Data Provider for SQL Server includes a <xref:System.Data.SqlClient.SqlConnection> object, the .NET Framework Data Provider for ODBC includes an <xref:System.Data.Odbc.OdbcConnection> object, and the .NET Framework Data Provider for Oracle includes an <xref:System.Data.OracleClient.OracleConnection> object.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="547a7-106">本节内容</span><span class="sxs-lookup"><span data-stu-id="547a7-106">In This Section</span></span>  
 [<span data-ttu-id="547a7-107">建立连接</span><span class="sxs-lookup"><span data-stu-id="547a7-107">Establishing the Connection</span></span>](../../../../docs/framework/data/adonet/establishing-the-connection.md)  
 <span data-ttu-id="547a7-108">介绍如何使用**连接**对象以建立与数据源的连接。</span><span class="sxs-lookup"><span data-stu-id="547a7-108">Describes how to use a **Connection** object to establish a connection to a data source.</span></span>  
  
 [<span data-ttu-id="547a7-109">连接事件</span><span class="sxs-lookup"><span data-stu-id="547a7-109">Connection Events</span></span>](../../../../docs/framework/data/adonet/connection-events.md)  
 <span data-ttu-id="547a7-110">介绍如何使用**InfoMessage**事件从数据源中检索信息性消息。</span><span class="sxs-lookup"><span data-stu-id="547a7-110">Describes how to use an **InfoMessage** event to retrieve informational messages from a data source.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="547a7-111">请参阅</span><span class="sxs-lookup"><span data-stu-id="547a7-111">See Also</span></span>  
 [<span data-ttu-id="547a7-112">连接字符串</span><span class="sxs-lookup"><span data-stu-id="547a7-112">Connection Strings</span></span>](../../../../docs/framework/data/adonet/connection-strings.md)  
 [<span data-ttu-id="547a7-113">连接池</span><span class="sxs-lookup"><span data-stu-id="547a7-113">Connection Pooling</span></span>](../../../../docs/framework/data/adonet/connection-pooling.md)  
 [<span data-ttu-id="547a7-114">命令和参数</span><span class="sxs-lookup"><span data-stu-id="547a7-114">Commands and Parameters</span></span>](../../../../docs/framework/data/adonet/commands-and-parameters.md)  
 [<span data-ttu-id="547a7-115">DataAdapters 和 DataReaders</span><span class="sxs-lookup"><span data-stu-id="547a7-115">DataAdapters and DataReaders</span></span>](../../../../docs/framework/data/adonet/dataadapters-and-datareaders.md)  
 [<span data-ttu-id="547a7-116">事务和并发性</span><span class="sxs-lookup"><span data-stu-id="547a7-116">Transactions and Concurrency</span></span>](../../../../docs/framework/data/adonet/transactions-and-concurrency.md)  
 [<span data-ttu-id="547a7-117">ADO.NET 托管提供程序和数据集开发人员中心</span><span class="sxs-lookup"><span data-stu-id="547a7-117">ADO.NET Managed Providers and DataSet Developer Center</span></span>](http://go.microsoft.com/fwlink/?LinkId=217917)
