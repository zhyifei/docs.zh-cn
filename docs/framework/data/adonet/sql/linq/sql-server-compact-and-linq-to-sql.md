---
title: "SQL Server Compact 与 LINQ to SQL"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 59022359-a5a2-4c42-9a6a-5c0259c3ad17
caps.latest.revision: "5"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.workload: dotnet
ms.openlocfilehash: 2717a94228dc1be8da0d84179201747d60c896a5
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="sql-server-compact-and-linq-to-sql"></a><span data-ttu-id="b00af-102">SQL Server Compact 与 LINQ to SQL</span><span class="sxs-lookup"><span data-stu-id="b00af-102">SQL Server Compact and LINQ to SQL</span></span>
<span data-ttu-id="b00af-103">SQL Server Compact 是随 Visual Studio 一起安装的默认数据库。</span><span class="sxs-lookup"><span data-stu-id="b00af-103">SQL Server Compact is the default database installed with Visual Studio.</span></span> <span data-ttu-id="b00af-104">有关详细信息，请参阅[PAVE 通过使用 SQL Server Compact (Visual Studio)](http://msdn.microsoft.com/en-us/13320dd1-94e5-4077-bf76-8df253695ccc)。</span><span class="sxs-lookup"><span data-stu-id="b00af-104">For more information, see [PAVE OVER Using SQL Server Compact (Visual Studio)](http://msdn.microsoft.com/en-us/13320dd1-94e5-4077-bf76-8df253695ccc).</span></span>  
  
 <span data-ttu-id="b00af-105">本主题概述了在用法、 配置、 功能集和作用域的关键差异[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]支持。</span><span class="sxs-lookup"><span data-stu-id="b00af-105">This topic outlines the key differences in usage, configuration, feature sets, and scope of [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] support.</span></span>  
  
## <a name="characteristics-of-sql-server-compact-in-relation-to-linq-to-sql"></a><span data-ttu-id="b00af-106">SQL Server Compact 相对于 LINQ to SQL 的特性</span><span class="sxs-lookup"><span data-stu-id="b00af-106">Characteristics of SQL Server Compact in Relation to LINQ to SQL</span></span>  
 <span data-ttu-id="b00af-107">默认情况下，SQL Server Compact 安装所有[!INCLUDE[vs_current_short](../../../../../../includes/vs-current-short-md.md)]版本，因此是用于在开发计算机上可用[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="b00af-107">By default, SQL Server Compact is installed for all [!INCLUDE[vs_current_short](../../../../../../includes/vs-current-short-md.md)] editions, and is therefore available on the development computer for use with [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)].</span></span> <span data-ttu-id="b00af-108">但是部署的应用程序使用 SQL Server Compact 和[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]程序的方式不同[!INCLUDE[ssNoVersion](../../../../../../includes/ssnoversion-md.md)]应用程序。</span><span class="sxs-lookup"><span data-stu-id="b00af-108">But deployment of an application that uses SQL Server Compact and [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] differs from that for a [!INCLUDE[ssNoVersion](../../../../../../includes/ssnoversion-md.md)] application.</span></span> <span data-ttu-id="b00af-109">SQL Server Compact 不是 .NET Framework 的一部分，因此必须与应用程序一起打包或单独从 Microsoft 网站下载。</span><span class="sxs-lookup"><span data-stu-id="b00af-109">SQL Server Compact is not a part of the .NET Framework, and therefore must be packaged with the application or downloaded separately from the Microsoft site.</span></span>  
  
 <span data-ttu-id="b00af-110">请注意下列特性：</span><span class="sxs-lookup"><span data-stu-id="b00af-110">Note the following characteristics:</span></span>  
  
-   <span data-ttu-id="b00af-111">SQL Server Compact 打包为可直接对数据库文件（扩展名为 .sdf）使用的 DLL。</span><span class="sxs-lookup"><span data-stu-id="b00af-111">SQL Server Compact is packaged as a DLL that can be used against database files (.sdf extension) directly.</span></span>  
  
-   <span data-ttu-id="b00af-112">在与客户端应用程序相同的进程中运行的是 SQL Server Compact。</span><span class="sxs-lookup"><span data-stu-id="b00af-112">SQL Server Compact runs in the same process as the client application.</span></span> <span data-ttu-id="b00af-113">与 SQL Server Compact 通信的效率因此可能会大大高于与通信[!INCLUDE[ssNoVersion](../../../../../../includes/ssnoversion-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="b00af-113">The efficiency of communication with SQL Server Compact can therefore be significantly higher than communicating with [!INCLUDE[ssNoVersion](../../../../../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="b00af-114">另一方面，SQL Server Compact 确实需要带来开销的托管和非托管代码之间的互操作性。</span><span class="sxs-lookup"><span data-stu-id="b00af-114">On the other hand, SQL Server Compact does require interoperability between managed and unmanaged code with its attendant costs.</span></span>  
  
-   <span data-ttu-id="b00af-115">SQL Server Compact DLL 的大小很小。</span><span class="sxs-lookup"><span data-stu-id="b00af-115">The size of the SQL Server Compact DLL is small.</span></span> <span data-ttu-id="b00af-116">这一特征减小了应用程序的总大小。</span><span class="sxs-lookup"><span data-stu-id="b00af-116">This feature reduces the overall application size.</span></span>  
  
-   <span data-ttu-id="b00af-117">[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] 运行时和 SQLMetal 命令行工具支持 SQL Server Compact。</span><span class="sxs-lookup"><span data-stu-id="b00af-117">The [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] runtime and the SQLMetal command-line tool support SQL Server Compact.</span></span>  
  
-   <span data-ttu-id="b00af-118">[!INCLUDE[vs_ordesigner_long](../../../../../../includes/vs-ordesigner-long-md.md)] 不支持 SQL Server Compact。</span><span class="sxs-lookup"><span data-stu-id="b00af-118">The [!INCLUDE[vs_ordesigner_long](../../../../../../includes/vs-ordesigner-long-md.md)] does not support SQL Server Compact.</span></span>  
  
## <a name="feature-set"></a><span data-ttu-id="b00af-119">功能集</span><span class="sxs-lookup"><span data-stu-id="b00af-119">Feature Set</span></span>  
 <span data-ttu-id="b00af-120">SQL Server Compact 功能集是要简单得多的功能集相比[!INCLUDE[ssNoVersion](../../../../../../includes/ssnoversion-md.md)]中可能会影响程序的以下方面[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]应用程序：</span><span class="sxs-lookup"><span data-stu-id="b00af-120">The SQL Server Compact feature set is much simpler than the feature set of [!INCLUDE[ssNoVersion](../../../../../../includes/ssnoversion-md.md)] in the following ways that can affect [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] applications :</span></span>  
  
-   <span data-ttu-id="b00af-121">SQL Server Compact 不支持存储过程或视图。</span><span class="sxs-lookup"><span data-stu-id="b00af-121">SQL Server Compact does not support stored procedures or views.</span></span>  
  
-   <span data-ttu-id="b00af-122">SQL Server Compact 仅支持部分数据类型和 SQL 函数。</span><span class="sxs-lookup"><span data-stu-id="b00af-122">SQL Server Compact supports only a subset of data types and SQL functions.</span></span>  
  
-   <span data-ttu-id="b00af-123">SQL Server Compact 仅支持部分 SQL 构造。</span><span class="sxs-lookup"><span data-stu-id="b00af-123">SQL Server Compact supports only a subset of SQL constructs.</span></span>  
  
-   <span data-ttu-id="b00af-124">SQL Server Compact 仅提供具有最基本功能的优化器。</span><span class="sxs-lookup"><span data-stu-id="b00af-124">SQL Server Compact provides only a minimal optimizer.</span></span> <span data-ttu-id="b00af-125">有些查询可能会超时。</span><span class="sxs-lookup"><span data-stu-id="b00af-125">It is possible that some queries might time out.</span></span>  
  
-   <span data-ttu-id="b00af-126">SQL Server Compact 不支持部分信任。</span><span class="sxs-lookup"><span data-stu-id="b00af-126">SQL Server Compact does not support partial trust.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b00af-127">请参阅</span><span class="sxs-lookup"><span data-stu-id="b00af-127">See Also</span></span>  
 [<span data-ttu-id="b00af-128">参考</span><span class="sxs-lookup"><span data-stu-id="b00af-128">Reference</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/reference.md)
