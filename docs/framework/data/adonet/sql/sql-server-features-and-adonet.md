---
title: "SQL Server 功能和 ADO.NET"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 2839529b-a79b-4450-be5d-07a98dbc7a0f
caps.latest.revision: "9"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: 27a46a4dbb98d5c2bdcd30c485ae1b3b047a1a13
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="sql-server-features-and-adonet"></a><span data-ttu-id="f3100-102">SQL Server 功能和 ADO.NET</span><span class="sxs-lookup"><span data-stu-id="f3100-102">SQL Server Features and ADO.NET</span></span>
<span data-ttu-id="f3100-103">本节中的主题讨论 SQL Server 中针对使用 ADO.NET 开发数据库应用程序的功能。</span><span class="sxs-lookup"><span data-stu-id="f3100-103">The topics in this section discuss features in SQL Server that are targeted at developing database applications using ADO.NET.</span></span>  
  
 <span data-ttu-id="f3100-104">有关更多信息，请参见与您所使用的 SQL Server 版本对应的 SQL Server 联机丛书，如下表中所示。</span><span class="sxs-lookup"><span data-stu-id="f3100-104">For more information, see SQL Server Books Online for the version of SQL Server you are using, as listed in the following table.</span></span>  
  
 <span data-ttu-id="f3100-105">**SQL Server 联机丛书**</span><span class="sxs-lookup"><span data-stu-id="f3100-105">**SQL Server Books Online**</span></span>  
  
1.  [<span data-ttu-id="f3100-106">开发 （数据库引擎）</span><span class="sxs-lookup"><span data-stu-id="f3100-106">Development (Database Engine)</span></span>](http://go.microsoft.com/fwlink/?LinkId=115245)  
  
## <a name="in-this-section"></a><span data-ttu-id="f3100-107">本节内容</span><span class="sxs-lookup"><span data-stu-id="f3100-107">In This Section</span></span>  
 [<span data-ttu-id="f3100-108">枚举实例的 SQL Server (ADO.NET)</span><span class="sxs-lookup"><span data-stu-id="f3100-108">Enumerating Instances of SQL Server (ADO.NET)</span></span>](../../../../../docs/framework/data/adonet/sql/enumerating-instances-of-sql-server.md)  
 <span data-ttu-id="f3100-109">描述如何枚举 SQL Server 的活动实例。</span><span class="sxs-lookup"><span data-stu-id="f3100-109">Describes how to enumerate active instances of SQL Server.</span></span>  
  
 [<span data-ttu-id="f3100-110">SQL Server 的提供程序统计信息</span><span class="sxs-lookup"><span data-stu-id="f3100-110">Provider Statistics for SQL Server</span></span>](../../../../../docs/framework/data/adonet/sql/provider-statistics-for-sql-server.md)  
 <span data-ttu-id="f3100-111">描述对获取 SQL Server 运行时统计信息的支持。</span><span class="sxs-lookup"><span data-stu-id="f3100-111">Describes support for obtaining SQL Server run-time statistics.</span></span>  
  
 [<span data-ttu-id="f3100-112">SQL Server Express 用户实例</span><span class="sxs-lookup"><span data-stu-id="f3100-112">SQL Server Express User Instances</span></span>](../../../../../docs/framework/data/adonet/sql/sql-server-express-user-instances.md)  
 <span data-ttu-id="f3100-113">描述对 SQL Server Express 用户实例的支持。</span><span class="sxs-lookup"><span data-stu-id="f3100-113">Describes support for SQL Server Express user instances.</span></span>  
  
 [<span data-ttu-id="f3100-114">SQL Server 中的数据库镜像</span><span class="sxs-lookup"><span data-stu-id="f3100-114">Database Mirroring in SQL Server</span></span>](../../../../../docs/framework/data/adonet/sql/database-mirroring-in-sql-server.md)  
 <span data-ttu-id="f3100-115">描述数据库镜像功能。</span><span class="sxs-lookup"><span data-stu-id="f3100-115">Describes database mirroring functionality.</span></span>  
  
 [<span data-ttu-id="f3100-116">SQL Server 公共语言运行时集成</span><span class="sxs-lookup"><span data-stu-id="f3100-116">SQL Server Common Language Runtime Integration</span></span>](../../../../../docs/framework/data/adonet/sql/sql-server-common-language-runtime-integration.md)  
 <span data-ttu-id="f3100-117">说明如何从 SQL Server 的公共语言运行库 (CLR) 数据库对象中访问数据。</span><span class="sxs-lookup"><span data-stu-id="f3100-117">Describes how data can be accessed from within a common language runtime (CLR) database object in SQL Server.</span></span>  
  
 [<span data-ttu-id="f3100-118">SQL Server 中的查询通知</span><span class="sxs-lookup"><span data-stu-id="f3100-118">Query Notifications in SQL Server</span></span>](../../../../../docs/framework/data/adonet/sql/query-notifications-in-sql-server.md)  
 <span data-ttu-id="f3100-119">说明数据发生更改时，.NET Framework 应用程序如何从 SQL Server 请求通知。</span><span class="sxs-lookup"><span data-stu-id="f3100-119">Describes how .NET Framework applications can request notification from SQL Server when data has changed.</span></span>  
  
 [<span data-ttu-id="f3100-120">SQL Server 中的快照隔离</span><span class="sxs-lookup"><span data-stu-id="f3100-120">Snapshot Isolation in SQL Server</span></span>](../../../../../docs/framework/data/adonet/sql/snapshot-isolation-in-sql-server.md)  
 <span data-ttu-id="f3100-121">描述对快照隔离的支持，该行版本机制旨在减少事务应用程序中的阻碍。</span><span class="sxs-lookup"><span data-stu-id="f3100-121">Describes support for snapshot isolation, a row versioning mechanism designed to reduce blocking in transactional applications.</span></span>  
  
 [<span data-ttu-id="f3100-122">SqlClient 对高可用性、 灾难恢复的支持</span><span class="sxs-lookup"><span data-stu-id="f3100-122">SqlClient Support for High Availability, Disaster Recovery</span></span>](../../../../../docs/framework/data/adonet/sql/sqlclient-support-for-high-availability-disaster-recovery.md)  
 <span data-ttu-id="f3100-123">描述高可用性、灾难恢复 (AlwaysOn) 可用性组的 SqlClient 支持。</span><span class="sxs-lookup"><span data-stu-id="f3100-123">Describes SqlClient support for high-availability, disaster recovery (AlwaysOn) availability groups.</span></span>  
  
 [<span data-ttu-id="f3100-124">SqlClient 对 LocalDB 的支持</span><span class="sxs-lookup"><span data-stu-id="f3100-124">SqlClient Support for LocalDB</span></span>](../../../../../docs/framework/data/adonet/sql/sqlclient-support-for-localdb.md)  
 <span data-ttu-id="f3100-125">描述 LocalDB 数据库的 SqlClient 支持。</span><span class="sxs-lookup"><span data-stu-id="f3100-125">Describes SqlClient support for LocalDB databases.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f3100-126">另请参阅</span><span class="sxs-lookup"><span data-stu-id="f3100-126">See Also</span></span>  
 [<span data-ttu-id="f3100-127">ADO.NET 中的 SQL Server 数据操作</span><span class="sxs-lookup"><span data-stu-id="f3100-127">SQL Server Data Operations in ADO.NET</span></span>](../../../../../docs/framework/data/adonet/sql/sql-server-data-operations.md)  
 [<span data-ttu-id="f3100-128">在 ADO.NET 中检索和修改数据</span><span class="sxs-lookup"><span data-stu-id="f3100-128">Retrieving and Modifying Data in ADO.NET</span></span>](../../../../../docs/framework/data/adonet/retrieving-and-modifying-data.md)  
 [<span data-ttu-id="f3100-129">LINQ to SQL</span><span class="sxs-lookup"><span data-stu-id="f3100-129">LINQ to SQL</span></span>](../../../../../docs/framework/data/adonet/sql/linq/index.md)  
 [<span data-ttu-id="f3100-130">SQL Server 和 ADO.NET</span><span class="sxs-lookup"><span data-stu-id="f3100-130">SQL Server and ADO.NET</span></span>](../../../../../docs/framework/data/adonet/sql/index.md)  
 [<span data-ttu-id="f3100-131">ADO.NET 托管提供程序和数据集开发人员中心</span><span class="sxs-lookup"><span data-stu-id="f3100-131">ADO.NET Managed Providers and DataSet Developer Center</span></span>](http://go.microsoft.com/fwlink/?LinkId=217917)
