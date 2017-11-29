---
title: "连接到 ADO.NET 中的数据源"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 9abc3f92-1be3-4e1a-b360-762dc689650e
caps.latest.revision: "3"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: 0d21c571b659e9d7aef65893db18b034d614e2af
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="connecting-to-a-data-source-in-adonet"></a><span data-ttu-id="e8a4c-102">连接到 ADO.NET 中的数据源</span><span class="sxs-lookup"><span data-stu-id="e8a4c-102">Connecting to a Data Source in ADO.NET</span></span>
<span data-ttu-id="e8a4c-103">在 ADO.NET 中使用**连接**要通过提供必要的身份验证信息来连接字符串连接到特定数据源对象。</span><span class="sxs-lookup"><span data-stu-id="e8a4c-103">In ADO.NET you use a **Connection** object to connect to a specific data source by supplying necessary authentication information in a connection string.</span></span> <span data-ttu-id="e8a4c-104">**连接**你使用的对象取决于数据源的类型。</span><span class="sxs-lookup"><span data-stu-id="e8a4c-104">The **Connection** object you use depends on the type of data source.</span></span>  
  
 <span data-ttu-id="e8a4c-105">随 .NET Framework 提供的每个 .NET Framework 数据提供程序都具有一个 <xref:System.Data.Common.DbConnection> 对象：适用于 OLE DB 的 .NET Framework 数据提供程序包括一个 <xref:System.Data.OleDb.OleDbConnection> 对象，适用于 SQL Server 的 .NET Framework 数据提供程序包括一个 <xref:System.Data.SqlClient.SqlConnection> 对象，适用于 ODBC 的 .NET Framework 数据提供程序包括一个 <xref:System.Data.Odbc.OdbcConnection> 对象，适用于 Oracle 的 .NET Framework 数据提供程序包括一个 <xref:System.Data.OracleClient.OracleConnection> 对象。</span><span class="sxs-lookup"><span data-stu-id="e8a4c-105">Each .NET Framework data provider included with the .NET Framework has a <xref:System.Data.Common.DbConnection> object: the .NET Framework Data Provider for OLE DB includes an <xref:System.Data.OleDb.OleDbConnection> object, the .NET Framework Data Provider for SQL Server includes a <xref:System.Data.SqlClient.SqlConnection> object, the .NET Framework Data Provider for ODBC includes an <xref:System.Data.Odbc.OdbcConnection> object, and the .NET Framework Data Provider for Oracle includes an <xref:System.Data.OracleClient.OracleConnection> object.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="e8a4c-106">本节内容</span><span class="sxs-lookup"><span data-stu-id="e8a4c-106">In This Section</span></span>  
 [<span data-ttu-id="e8a4c-107">建立连接</span><span class="sxs-lookup"><span data-stu-id="e8a4c-107">Establishing the Connection</span></span>](../../../../docs/framework/data/adonet/establishing-the-connection.md)  
 <span data-ttu-id="e8a4c-108">介绍如何使用**连接**对象以建立与数据源的连接。</span><span class="sxs-lookup"><span data-stu-id="e8a4c-108">Describes how to use a **Connection** object to establish a connection to a data source.</span></span>  
  
 [<span data-ttu-id="e8a4c-109">连接事件</span><span class="sxs-lookup"><span data-stu-id="e8a4c-109">Connection Events</span></span>](../../../../docs/framework/data/adonet/connection-events.md)  
 <span data-ttu-id="e8a4c-110">介绍如何使用**InfoMessage**事件从数据源中检索信息性消息。</span><span class="sxs-lookup"><span data-stu-id="e8a4c-110">Describes how to use an **InfoMessage** event to retrieve informational messages from a data source.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e8a4c-111">另请参阅</span><span class="sxs-lookup"><span data-stu-id="e8a4c-111">See Also</span></span>  
 [<span data-ttu-id="e8a4c-112">连接字符串</span><span class="sxs-lookup"><span data-stu-id="e8a4c-112">Connection Strings</span></span>](../../../../docs/framework/data/adonet/connection-strings.md)  
 [<span data-ttu-id="e8a4c-113">连接池</span><span class="sxs-lookup"><span data-stu-id="e8a4c-113">Connection Pooling</span></span>](../../../../docs/framework/data/adonet/connection-pooling.md)  
 [<span data-ttu-id="e8a4c-114">命令和参数</span><span class="sxs-lookup"><span data-stu-id="e8a4c-114">Commands and Parameters</span></span>](../../../../docs/framework/data/adonet/commands-and-parameters.md)  
 [<span data-ttu-id="e8a4c-115">Dataadapter 和 Datareader</span><span class="sxs-lookup"><span data-stu-id="e8a4c-115">DataAdapters and DataReaders</span></span>](../../../../docs/framework/data/adonet/dataadapters-and-datareaders.md)  
 [<span data-ttu-id="e8a4c-116">事务和并发性</span><span class="sxs-lookup"><span data-stu-id="e8a4c-116">Transactions and Concurrency</span></span>](../../../../docs/framework/data/adonet/transactions-and-concurrency.md)  
 [<span data-ttu-id="e8a4c-117">ADO.NET 托管提供程序和数据集开发人员中心</span><span class="sxs-lookup"><span data-stu-id="e8a4c-117">ADO.NET Managed Providers and DataSet Developer Center</span></span>](http://go.microsoft.com/fwlink/?LinkId=217917)
