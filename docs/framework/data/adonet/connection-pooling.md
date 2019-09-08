---
title: 连接池
ms.date: 03/30/2017
ms.assetid: 955c057f-aea8-4ba8-aa6d-e3dfa18ba8d5
ms.openlocfilehash: c431011cf57fd9ef79c2f0a099ab1080116c571f
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/07/2019
ms.locfileid: "70786707"
---
# <a name="connection-pooling"></a><span data-ttu-id="2a88b-102">连接池</span><span class="sxs-lookup"><span data-stu-id="2a88b-102">Connection Pooling</span></span>
<span data-ttu-id="2a88b-103">连接到数据源可能需要很长时间。</span><span class="sxs-lookup"><span data-stu-id="2a88b-103">Connecting to a data source can be time consuming.</span></span> <span data-ttu-id="2a88b-104">为了最大程度地降低打开连接的成本，ADO.NET 使用一种称为*连接池*的优化技术，这会最大程度地降低重复打开和关闭连接的成本。</span><span class="sxs-lookup"><span data-stu-id="2a88b-104">To minimize the cost of opening connections, ADO.NET uses an optimization technique called *connection pooling*, which minimizes the cost of repeatedly opening and closing connections.</span></span> <span data-ttu-id="2a88b-105">.NET Framework 数据提供程序处理连接池的方式有所不同。</span><span class="sxs-lookup"><span data-stu-id="2a88b-105">Connection pooling is handled differently for the .NET Framework data providers.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="2a88b-106">本节内容</span><span class="sxs-lookup"><span data-stu-id="2a88b-106">In This Section</span></span>  
 [<span data-ttu-id="2a88b-107">SQL Server 连接池 (ADO.NET)</span><span class="sxs-lookup"><span data-stu-id="2a88b-107">SQL Server Connection Pooling (ADO.NET)</span></span>](sql-server-connection-pooling.md)  
 <span data-ttu-id="2a88b-108">提供连接池的概述，并介绍连接池在 SQL Server 中的工作原理。</span><span class="sxs-lookup"><span data-stu-id="2a88b-108">Provides an overview of connection pooling and describes how connection pooling works in SQL Server.</span></span>  
  
 [<span data-ttu-id="2a88b-109">OLE DB、ODBC 和 Oracle 连接池</span><span class="sxs-lookup"><span data-stu-id="2a88b-109">OLE DB, ODBC, and Oracle Connection Pooling</span></span>](ole-db-odbc-and-oracle-connection-pooling.md)  
 <span data-ttu-id="2a88b-110">说明适用于 OLE DB 的 .NET Framework 数据提供程序、适用于 ODBC 的 .NET Framework 数据提供程序和适用于 Oracle 的 .NET Framework 数据提供程序的连接池。</span><span class="sxs-lookup"><span data-stu-id="2a88b-110">Describes connection pooling for the .NET Framework Data Provider for OLE DB, the .NET Framework Data Provider for ODBC, and the .NET Framework Data Provider for Oracle.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2a88b-111">请参阅</span><span class="sxs-lookup"><span data-stu-id="2a88b-111">See also</span></span>

- [<span data-ttu-id="2a88b-112">在 ADO.NET 中检索和修改数据</span><span class="sxs-lookup"><span data-stu-id="2a88b-112">Retrieving and Modifying Data in ADO.NET</span></span>](retrieving-and-modifying-data.md)
- [<span data-ttu-id="2a88b-113">ADO.NET 概述</span><span class="sxs-lookup"><span data-stu-id="2a88b-113">ADO.NET Overview</span></span>](ado-net-overview.md)
