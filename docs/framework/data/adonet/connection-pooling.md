---
title: "连接池"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 955c057f-aea8-4ba8-aa6d-e3dfa18ba8d5
caps.latest.revision: "3"
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload: dotnet
ms.openlocfilehash: 7205bc307af6a4a9f307b84a7b3875b77dadb765
ms.sourcegitcommit: ed26cfef4e18f6d93ab822d8c29f902cff3519d1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/17/2018
---
# <a name="connection-pooling"></a><span data-ttu-id="17faf-102">连接池</span><span class="sxs-lookup"><span data-stu-id="17faf-102">Connection Pooling</span></span>
<span data-ttu-id="17faf-103">连接到数据源可能需要很长时间。</span><span class="sxs-lookup"><span data-stu-id="17faf-103">Connecting to a data source can be time consuming.</span></span> <span data-ttu-id="17faf-104">打开连接的成本降到最低，ADO.NET 使用称为的优化方法*连接池*，其中重复打开和关闭连接的成本降至最低。</span><span class="sxs-lookup"><span data-stu-id="17faf-104">To minimize the cost of opening connections, ADO.NET uses an optimization technique called *connection pooling*, which minimizes the cost of repeatedly opening and closing connections.</span></span> <span data-ttu-id="17faf-105">.NET Framework 数据提供程序处理连接池的方式有所不同。</span><span class="sxs-lookup"><span data-stu-id="17faf-105">Connection pooling is handled differently for the .NET Framework data providers.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="17faf-106">本节内容</span><span class="sxs-lookup"><span data-stu-id="17faf-106">In This Section</span></span>  
 [<span data-ttu-id="17faf-107">SQL Server 连接池 (ADO.NET)</span><span class="sxs-lookup"><span data-stu-id="17faf-107">SQL Server Connection Pooling (ADO.NET)</span></span>](../../../../docs/framework/data/adonet/sql-server-connection-pooling.md)  
 <span data-ttu-id="17faf-108">概述连接池的并说明 [!INCLUDE[ssNoVersion](../../../../includes/ssnoversion-md.md)] 中连接池的工作原理。</span><span class="sxs-lookup"><span data-stu-id="17faf-108">Provides an overview of connection pooling and describes how connection pooling works in [!INCLUDE[ssNoVersion](../../../../includes/ssnoversion-md.md)].</span></span>  
  
 [<span data-ttu-id="17faf-109">OLE DB、ODBC 和 Oracle 连接池</span><span class="sxs-lookup"><span data-stu-id="17faf-109">OLE DB, ODBC, and Oracle Connection Pooling</span></span>](../../../../docs/framework/data/adonet/ole-db-odbc-and-oracle-connection-pooling.md)  
 <span data-ttu-id="17faf-110">说明适用于 OLE DB 的 .NET Framework 数据提供程序、适用于 ODBC 的 .NET Framework 数据提供程序和适用于 Oracle 的 .NET Framework 数据提供程序的连接池。</span><span class="sxs-lookup"><span data-stu-id="17faf-110">Describes connection pooling for the .NET Framework Data Provider for OLE DB, the .NET Framework Data Provider for ODBC, and the .NET Framework Data Provider for Oracle.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="17faf-111">请参阅</span><span class="sxs-lookup"><span data-stu-id="17faf-111">See Also</span></span>  
 [<span data-ttu-id="17faf-112">在 ADO.NET 中检索和修改数据</span><span class="sxs-lookup"><span data-stu-id="17faf-112">Retrieving and Modifying Data in ADO.NET</span></span>](../../../../docs/framework/data/adonet/retrieving-and-modifying-data.md)  
 [<span data-ttu-id="17faf-113">ADO.NET 托管提供程序和数据集开发人员中心</span><span class="sxs-lookup"><span data-stu-id="17faf-113">ADO.NET Managed Providers and DataSet Developer Center</span></span>](http://go.microsoft.com/fwlink/?LinkId=217917)
