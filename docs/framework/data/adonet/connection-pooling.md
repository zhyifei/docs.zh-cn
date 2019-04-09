---
title: 连接池
ms.date: 03/30/2017
ms.assetid: 955c057f-aea8-4ba8-aa6d-e3dfa18ba8d5
ms.openlocfilehash: 4cba53993489f51ed39ac52bff4fa252beb9aafd
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/08/2019
ms.locfileid: "59180448"
---
# <a name="connection-pooling"></a><span data-ttu-id="f66c0-102">连接池</span><span class="sxs-lookup"><span data-stu-id="f66c0-102">Connection Pooling</span></span>
<span data-ttu-id="f66c0-103">连接到数据源可能需要很长时间。</span><span class="sxs-lookup"><span data-stu-id="f66c0-103">Connecting to a data source can be time consuming.</span></span> <span data-ttu-id="f66c0-104">若要打开连接的成本降至最低，ADO.NET 使用名为优化技术*连接池*，其中反复打开和关闭连接的成本降至最低。</span><span class="sxs-lookup"><span data-stu-id="f66c0-104">To minimize the cost of opening connections, ADO.NET uses an optimization technique called *connection pooling*, which minimizes the cost of repeatedly opening and closing connections.</span></span> <span data-ttu-id="f66c0-105">.NET Framework 数据提供程序处理连接池的方式有所不同。</span><span class="sxs-lookup"><span data-stu-id="f66c0-105">Connection pooling is handled differently for the .NET Framework data providers.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="f66c0-106">本节内容</span><span class="sxs-lookup"><span data-stu-id="f66c0-106">In This Section</span></span>  
 [<span data-ttu-id="f66c0-107">SQL Server 连接池 (ADO.NET)</span><span class="sxs-lookup"><span data-stu-id="f66c0-107">SQL Server Connection Pooling (ADO.NET)</span></span>](../../../../docs/framework/data/adonet/sql-server-connection-pooling.md)  
 <span data-ttu-id="f66c0-108">提供的连接池的概述和介绍连接池在 SQL Server 中的工作方式。</span><span class="sxs-lookup"><span data-stu-id="f66c0-108">Provides an overview of connection pooling and describes how connection pooling works in SQL Server.</span></span>  
  
 [<span data-ttu-id="f66c0-109">OLE DB、ODBC 和 Oracle 连接池</span><span class="sxs-lookup"><span data-stu-id="f66c0-109">OLE DB, ODBC, and Oracle Connection Pooling</span></span>](../../../../docs/framework/data/adonet/ole-db-odbc-and-oracle-connection-pooling.md)  
 <span data-ttu-id="f66c0-110">说明适用于 OLE DB 的 .NET Framework 数据提供程序、适用于 ODBC 的 .NET Framework 数据提供程序和适用于 Oracle 的 .NET Framework 数据提供程序的连接池。</span><span class="sxs-lookup"><span data-stu-id="f66c0-110">Describes connection pooling for the .NET Framework Data Provider for OLE DB, the .NET Framework Data Provider for ODBC, and the .NET Framework Data Provider for Oracle.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f66c0-111">请参阅</span><span class="sxs-lookup"><span data-stu-id="f66c0-111">See also</span></span>

- [<span data-ttu-id="f66c0-112">在 ADO.NET 中检索和修改数据</span><span class="sxs-lookup"><span data-stu-id="f66c0-112">Retrieving and Modifying Data in ADO.NET</span></span>](../../../../docs/framework/data/adonet/retrieving-and-modifying-data.md)
- [<span data-ttu-id="f66c0-113">ADO.NET 托管提供程序和 DataSet 开发人员中心</span><span class="sxs-lookup"><span data-stu-id="f66c0-113">ADO.NET Managed Providers and DataSet Developer Center</span></span>](https://go.microsoft.com/fwlink/?LinkId=217917)
