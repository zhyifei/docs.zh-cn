---
title: SQL Server Compact 与 LINQ to SQL
ms.date: 03/30/2017
ms.assetid: 59022359-a5a2-4c42-9a6a-5c0259c3ad17
ms.openlocfilehash: db3f7aef082d965dc27b69f5a966ff038c0ffac0
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/18/2019
ms.locfileid: "59145712"
---
# <a name="sql-server-compact-and-linq-to-sql"></a><span data-ttu-id="5c70d-102">SQL Server Compact 与 LINQ to SQL</span><span class="sxs-lookup"><span data-stu-id="5c70d-102">SQL Server Compact and LINQ to SQL</span></span>
<span data-ttu-id="5c70d-103">SQL Server Compact 是与 Visual Studio 一起安装的默认数据库。</span><span class="sxs-lookup"><span data-stu-id="5c70d-103">SQL Server Compact is the default database installed with Visual Studio.</span></span> <span data-ttu-id="5c70d-104">有关详细信息，请参阅[使用 SQL Server Compact (Visual Studio)](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2012/aa983321(v=vs.110))。</span><span class="sxs-lookup"><span data-stu-id="5c70d-104">For more information, see [Using SQL Server Compact (Visual Studio)](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2012/aa983321(v=vs.110)).</span></span>  
  
 <span data-ttu-id="5c70d-105">本主题概述了使用情况、 配置、 功能集和作用域中的主要差异[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]支持。</span><span class="sxs-lookup"><span data-stu-id="5c70d-105">This topic outlines the key differences in usage, configuration, feature sets, and scope of [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] support.</span></span>  
  
## <a name="characteristics-of-sql-server-compact-in-relation-to-linq-to-sql"></a><span data-ttu-id="5c70d-106">SQL Server Compact 相对于 LINQ to SQL 的特性</span><span class="sxs-lookup"><span data-stu-id="5c70d-106">Characteristics of SQL Server Compact in Relation to LINQ to SQL</span></span>  
 <span data-ttu-id="5c70d-107">默认情况下，SQL Server Compact 针对所有 Visual Studio 版本，安装，因此可用于在开发计算机上[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="5c70d-107">By default, SQL Server Compact is installed for all Visual Studio editions, and is therefore available on the development computer for use with [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)].</span></span> <span data-ttu-id="5c70d-108">但使用 SQL Server Compact 的应用程序的部署和[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]不同于 SQL Server 应用程序。</span><span class="sxs-lookup"><span data-stu-id="5c70d-108">But deployment of an application that uses SQL Server Compact and [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] differs from that for a SQL Server application.</span></span> <span data-ttu-id="5c70d-109">SQL Server Compact 不是 .NET Framework 的一部分，因此必须与应用程序一起打包或单独从 Microsoft 网站下载。</span><span class="sxs-lookup"><span data-stu-id="5c70d-109">SQL Server Compact is not a part of the .NET Framework, and therefore must be packaged with the application or downloaded separately from the Microsoft site.</span></span>  
  
 <span data-ttu-id="5c70d-110">请注意下列特性：</span><span class="sxs-lookup"><span data-stu-id="5c70d-110">Note the following characteristics:</span></span>  
  
-   <span data-ttu-id="5c70d-111">SQL Server Compact 打包为可直接对数据库文件（扩展名为 .sdf）使用的 DLL。</span><span class="sxs-lookup"><span data-stu-id="5c70d-111">SQL Server Compact is packaged as a DLL that can be used against database files (.sdf extension) directly.</span></span>  
  
-   <span data-ttu-id="5c70d-112">在与客户端应用程序相同的进程中运行的是 SQL Server Compact。</span><span class="sxs-lookup"><span data-stu-id="5c70d-112">SQL Server Compact runs in the same process as the client application.</span></span> <span data-ttu-id="5c70d-113">因此，与 SQL Server Compact 进行通信的效率可能大大高于与 SQL Server 通信。</span><span class="sxs-lookup"><span data-stu-id="5c70d-113">The efficiency of communication with SQL Server Compact can therefore be significantly higher than communicating with SQL Server.</span></span> <span data-ttu-id="5c70d-114">但是，SQL Server Compact 确实需要耗费一定的开销与托管和非托管代码之间的互操作性。</span><span class="sxs-lookup"><span data-stu-id="5c70d-114">On the other hand, SQL Server Compact does require interoperability between managed and unmanaged code with its attendant costs.</span></span>  
  
-   <span data-ttu-id="5c70d-115">SQL Server Compact DLL 的大小很小。</span><span class="sxs-lookup"><span data-stu-id="5c70d-115">The size of the SQL Server Compact DLL is small.</span></span> <span data-ttu-id="5c70d-116">这一特征减小了应用程序的总大小。</span><span class="sxs-lookup"><span data-stu-id="5c70d-116">This feature reduces the overall application size.</span></span>  
  
-   <span data-ttu-id="5c70d-117">[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] 运行时和 SQLMetal 命令行工具支持 SQL Server Compact。</span><span class="sxs-lookup"><span data-stu-id="5c70d-117">The [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] runtime and the SQLMetal command-line tool support SQL Server Compact.</span></span>  
  
-   <span data-ttu-id="5c70d-118">[!INCLUDE[vs_ordesigner_long](../../../../../../includes/vs-ordesigner-long-md.md)] 不支持 SQL Server Compact。</span><span class="sxs-lookup"><span data-stu-id="5c70d-118">The [!INCLUDE[vs_ordesigner_long](../../../../../../includes/vs-ordesigner-long-md.md)] does not support SQL Server Compact.</span></span>  
  
## <a name="feature-set"></a><span data-ttu-id="5c70d-119">功能集</span><span class="sxs-lookup"><span data-stu-id="5c70d-119">Feature Set</span></span>  
 <span data-ttu-id="5c70d-120">SQL Server Compact 功能集可能会影响以下方面是 SQL Server 功能集相比要简单得[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]应用程序：</span><span class="sxs-lookup"><span data-stu-id="5c70d-120">The SQL Server Compact feature set is much simpler than the feature set of SQL Server in the following ways that can affect [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] applications :</span></span>  
  
-   <span data-ttu-id="5c70d-121">SQL Server Compact 不支持存储过程或视图。</span><span class="sxs-lookup"><span data-stu-id="5c70d-121">SQL Server Compact does not support stored procedures or views.</span></span>  
  
-   <span data-ttu-id="5c70d-122">SQL Server Compact 仅支持部分数据类型和 SQL 函数。</span><span class="sxs-lookup"><span data-stu-id="5c70d-122">SQL Server Compact supports only a subset of data types and SQL functions.</span></span>  
  
-   <span data-ttu-id="5c70d-123">SQL Server Compact 仅支持部分 SQL 构造。</span><span class="sxs-lookup"><span data-stu-id="5c70d-123">SQL Server Compact supports only a subset of SQL constructs.</span></span>  
  
-   <span data-ttu-id="5c70d-124">SQL Server Compact 仅提供具有最基本功能的优化器。</span><span class="sxs-lookup"><span data-stu-id="5c70d-124">SQL Server Compact provides only a minimal optimizer.</span></span> <span data-ttu-id="5c70d-125">有些查询可能会超时。</span><span class="sxs-lookup"><span data-stu-id="5c70d-125">It is possible that some queries might time out.</span></span>  
  
-   <span data-ttu-id="5c70d-126">SQL Server Compact 不支持部分信任。</span><span class="sxs-lookup"><span data-stu-id="5c70d-126">SQL Server Compact does not support partial trust.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5c70d-127">请参阅</span><span class="sxs-lookup"><span data-stu-id="5c70d-127">See also</span></span>

- [<span data-ttu-id="5c70d-128">引用</span><span class="sxs-lookup"><span data-stu-id="5c70d-128">Reference</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/reference.md)
