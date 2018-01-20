---
title: "使用 LINQ to SQL 的 N 层和远程应用程序"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 854a1cdd-53cb-45f5-83ca-63962a9b3598
caps.latest.revision: "5"
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload: dotnet
ms.openlocfilehash: 272c125096e08819a7f70b830e1f359a760f687f
ms.sourcegitcommit: c0dd436f6f8f44dc80dc43b07f6841a00b74b23f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/19/2018
---
# <a name="n-tier-and-remote-applications-with-linq-to-sql"></a><span data-ttu-id="42e4d-102">使用 LINQ to SQL 的 N 层和远程应用程序</span><span class="sxs-lookup"><span data-stu-id="42e4d-102">N-Tier and Remote Applications with LINQ to SQL</span></span>
<span data-ttu-id="42e4d-103">可以创建使用 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] 的 n 层或多层应用程序。</span><span class="sxs-lookup"><span data-stu-id="42e4d-103">You can create n-tier or multitier applications that use [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)].</span></span> <span data-ttu-id="42e4d-104">通常情况下，[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]数据上下文、 实体类和查询构造逻辑都位于中间层作为数据访问层 (DAL)。</span><span class="sxs-lookup"><span data-stu-id="42e4d-104">Typically, the [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] data context, entity classes, and query construction logic are located on the middle tier as the data access layer (DAL).</span></span> <span data-ttu-id="42e4d-105">业务逻辑和任何非持久性数据都可以在实体的分部类和分部方法中以及数据上下文中完整实现，也可以在单独的类中实现。</span><span class="sxs-lookup"><span data-stu-id="42e4d-105">Business logic and any non-persistent data can be implemented completely in partial classes and methods of entities and the data context, or it can be implemented in separate classes.</span></span>  
  
 <span data-ttu-id="42e4d-106">客户端或表示层调用中间层的远程接口上的方法，而该层上的 DAL 会执行映射到 <xref:System.Data.Linq.DataContext> 方法的查询或存储过程。</span><span class="sxs-lookup"><span data-stu-id="42e4d-106">The client or presentation layer calls methods on the middle-tier's remote interface, and the DAL on that tier will execute queries or stored procedures that are mapped to <xref:System.Data.Linq.DataContext> methods.</span></span> <span data-ttu-id="42e4d-107">中间层通常以实体或代理对象的 XML 表示形式向客户端返回数据。</span><span class="sxs-lookup"><span data-stu-id="42e4d-107">The middle tier returns the data to clients typically as XML representations of entities or proxy objects.</span></span>  
  
 <span data-ttu-id="42e4d-108">在中间层上，实体由数据上下文创建，数据上下文会跟踪实体的状态，并管理从数据库延迟加载实体以及将更改提交给数据库的过程。</span><span class="sxs-lookup"><span data-stu-id="42e4d-108">On the middle tier, entities are created by the data context, which tracks their state, and manages deferred loading from and submission of changes to the database.</span></span> <span data-ttu-id="42e4d-109">这些实体被“附加”到 `DataContext`。</span><span class="sxs-lookup"><span data-stu-id="42e4d-109">These entities are "attached" to the `DataContext`.</span></span> <span data-ttu-id="42e4d-110">但是，在实体通过序列化发送到其他层后，这些实体会分离出来，这意味着 `DataContext` 不再跟踪它们的状态。</span><span class="sxs-lookup"><span data-stu-id="42e4d-110">However, after the entities are sent to another tier through serialization, they become detached, which means the `DataContext` is no longer tracking their state.</span></span> <span data-ttu-id="42e4d-111">必须在将客户端发送回来进行更新的实体重新附加到数据上下文之后，[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] 才能将更改提交给数据库。</span><span class="sxs-lookup"><span data-stu-id="42e4d-111">Entities that the client sends back for updates must be reattached to the data context before [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] can submit the changes to the database.</span></span> <span data-ttu-id="42e4d-112">如果原始值和/或时间戳是开放式并发检查所必需的，则客户端负责将它们返回给中间层。</span><span class="sxs-lookup"><span data-stu-id="42e4d-112">The client is responsible for providing original values and/or timestamps back to the middle tier if those are required for optimistic concurrency checks.</span></span>  
  
 <span data-ttu-id="42e4d-113">在 ASP.NET 应用程序中，<xref:System.Web.UI.WebControls.LinqDataSource> 管理这一复杂过程的大部分工作。</span><span class="sxs-lookup"><span data-stu-id="42e4d-113">In ASP.NET applications, the <xref:System.Web.UI.WebControls.LinqDataSource> manages most of this complexity.</span></span> <span data-ttu-id="42e4d-114">有关详细信息，请参阅[NIB: LinqDataSource Web 服务器控件概述](http://msdn.microsoft.com/library/104cfc3f-7385-47d3-8a51-830dfa791136)。</span><span class="sxs-lookup"><span data-stu-id="42e4d-114">For more information, see [NIB: LinqDataSource Web Server Control Overview](http://msdn.microsoft.com/library/104cfc3f-7385-47d3-8a51-830dfa791136).</span></span>  
  
## <a name="additional-resources"></a><span data-ttu-id="42e4d-115">其他资源</span><span class="sxs-lookup"><span data-stu-id="42e4d-115">Additional Resources</span></span>  
 <span data-ttu-id="42e4d-116">有关如何实现使用 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] 的 n 层应用程序的更多信息，请参见以下主题：</span><span class="sxs-lookup"><span data-stu-id="42e4d-116">For more information about how to implement n-tier applications that use [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)], see the following topics:</span></span>  
  
-   [<span data-ttu-id="42e4d-117">使用 ASP.NET 的 LINQ to SQL N 层</span><span class="sxs-lookup"><span data-stu-id="42e4d-117">LINQ to SQL N-Tier with ASP.NET</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/linq-to-sql-n-tier-with-aspnet.md)  
  
-   [<span data-ttu-id="42e4d-118">使用 Web 服务 的 LINQ to SQL N 层</span><span class="sxs-lookup"><span data-stu-id="42e4d-118">LINQ to SQL N-Tier with Web Services</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/linq-to-sql-n-tier-with-web-services.md)  
  
-   [<span data-ttu-id="42e4d-119">具有紧密耦合的客户端-服务器应用程序的 LINQ to SQL</span><span class="sxs-lookup"><span data-stu-id="42e4d-119">LINQ to SQL with Tightly-Coupled Client-Server Applications</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/linq-to-sql-with-tightly-coupled-client-server-applications.md)  
  
-   [<span data-ttu-id="42e4d-120">实现 N 层业务逻辑</span><span class="sxs-lookup"><span data-stu-id="42e4d-120">Implementing N-Tier Business Logic</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/implementing-business-logic-linq-to-sql.md)  
  
-   [<span data-ttu-id="42e4d-121">N 层应用程序中的数据检索和 CUD 操作 (LINQ to SQL)</span><span class="sxs-lookup"><span data-stu-id="42e4d-121">Data Retrieval and CUD Operations in N-Tier Applications (LINQ to SQL)</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/data-retrieval-and-cud-operations-in-n-tier-applications.md)  
  
 <span data-ttu-id="42e4d-122">有关使用 ADO.NET 数据集的 n 层应用程序的详细信息，请参阅[处理 n 层应用程序中的数据集](http://msdn.microsoft.com/library/f6ae2ee0-ea5f-4a79-8f4b-e21c115afb20)。</span><span class="sxs-lookup"><span data-stu-id="42e4d-122">For more information about n-tier applications that use ADO.NET DataSets, see [Work with datasets in n-tier applications](http://msdn.microsoft.com/library/f6ae2ee0-ea5f-4a79-8f4b-e21c115afb20).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="42e4d-123">请参阅</span><span class="sxs-lookup"><span data-stu-id="42e4d-123">See Also</span></span>  
 [<span data-ttu-id="42e4d-124">背景信息</span><span class="sxs-lookup"><span data-stu-id="42e4d-124">Background Information</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/background-information.md)
