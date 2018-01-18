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
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload: dotnet
ms.openlocfilehash: 1df18730d3a4428f245fe4222dafec0eaf6c08a5
ms.sourcegitcommit: ed26cfef4e18f6d93ab822d8c29f902cff3519d1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/17/2018
---
# <a name="connecting-to-a-data-source-in-adonet"></a><span data-ttu-id="5d9fb-102">连接到 ADO.NET 中的数据源</span><span class="sxs-lookup"><span data-stu-id="5d9fb-102">Connecting to a Data Source in ADO.NET</span></span>
<span data-ttu-id="5d9fb-103">在 ADO.NET 中使用**连接**要通过提供必要的身份验证信息来连接字符串连接到特定数据源对象。</span><span class="sxs-lookup"><span data-stu-id="5d9fb-103">In ADO.NET you use a **Connection** object to connect to a specific data source by supplying necessary authentication information in a connection string.</span></span> <span data-ttu-id="5d9fb-104">**连接**你使用的对象取决于数据源的类型。</span><span class="sxs-lookup"><span data-stu-id="5d9fb-104">The **Connection** object you use depends on the type of data source.</span></span>  
  
 <span data-ttu-id="5d9fb-105">随 .NET Framework 提供的每个 .NET Framework 数据提供程序都具有一个 <xref:System.Data.Common.DbConnection> 对象：适用于 OLE DB 的 .NET Framework 数据提供程序包括一个 <xref:System.Data.OleDb.OleDbConnection> 对象，适用于 SQL Server 的 .NET Framework 数据提供程序包括一个 <xref:System.Data.SqlClient.SqlConnection> 对象，适用于 ODBC 的 .NET Framework 数据提供程序包括一个 <xref:System.Data.Odbc.OdbcConnection> 对象，适用于 Oracle 的 .NET Framework 数据提供程序包括一个 <xref:System.Data.OracleClient.OracleConnection> 对象。</span><span class="sxs-lookup"><span data-stu-id="5d9fb-105">Each .NET Framework data provider included with the .NET Framework has a <xref:System.Data.Common.DbConnection> object: the .NET Framework Data Provider for OLE DB includes an <xref:System.Data.OleDb.OleDbConnection> object, the .NET Framework Data Provider for SQL Server includes a <xref:System.Data.SqlClient.SqlConnection> object, the .NET Framework Data Provider for ODBC includes an <xref:System.Data.Odbc.OdbcConnection> object, and the .NET Framework Data Provider for Oracle includes an <xref:System.Data.OracleClient.OracleConnection> object.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="5d9fb-106">本节内容</span><span class="sxs-lookup"><span data-stu-id="5d9fb-106">In This Section</span></span>  
 [<span data-ttu-id="5d9fb-107">建立连接</span><span class="sxs-lookup"><span data-stu-id="5d9fb-107">Establishing the Connection</span></span>](../../../../docs/framework/data/adonet/establishing-the-connection.md)  
 <span data-ttu-id="5d9fb-108">介绍如何使用**连接**对象以建立与数据源的连接。</span><span class="sxs-lookup"><span data-stu-id="5d9fb-108">Describes how to use a **Connection** object to establish a connection to a data source.</span></span>  
  
 [<span data-ttu-id="5d9fb-109">连接事件</span><span class="sxs-lookup"><span data-stu-id="5d9fb-109">Connection Events</span></span>](../../../../docs/framework/data/adonet/connection-events.md)  
 <span data-ttu-id="5d9fb-110">介绍如何使用**InfoMessage**事件从数据源中检索信息性消息。</span><span class="sxs-lookup"><span data-stu-id="5d9fb-110">Describes how to use an **InfoMessage** event to retrieve informational messages from a data source.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5d9fb-111">请参阅</span><span class="sxs-lookup"><span data-stu-id="5d9fb-111">See Also</span></span>  
 [<span data-ttu-id="5d9fb-112">连接字符串</span><span class="sxs-lookup"><span data-stu-id="5d9fb-112">Connection Strings</span></span>](../../../../docs/framework/data/adonet/connection-strings.md)  
 [<span data-ttu-id="5d9fb-113">连接池</span><span class="sxs-lookup"><span data-stu-id="5d9fb-113">Connection Pooling</span></span>](../../../../docs/framework/data/adonet/connection-pooling.md)  
 [<span data-ttu-id="5d9fb-114">命令和参数</span><span class="sxs-lookup"><span data-stu-id="5d9fb-114">Commands and Parameters</span></span>](../../../../docs/framework/data/adonet/commands-and-parameters.md)  
 [<span data-ttu-id="5d9fb-115">DataAdapters 和 DataReaders</span><span class="sxs-lookup"><span data-stu-id="5d9fb-115">DataAdapters and DataReaders</span></span>](../../../../docs/framework/data/adonet/dataadapters-and-datareaders.md)  
 [<span data-ttu-id="5d9fb-116">事务和并发性</span><span class="sxs-lookup"><span data-stu-id="5d9fb-116">Transactions and Concurrency</span></span>](../../../../docs/framework/data/adonet/transactions-and-concurrency.md)  
 [<span data-ttu-id="5d9fb-117">ADO.NET 托管提供程序和数据集开发人员中心</span><span class="sxs-lookup"><span data-stu-id="5d9fb-117">ADO.NET Managed Providers and DataSet Developer Center</span></span>](http://go.microsoft.com/fwlink/?LinkId=217917)
