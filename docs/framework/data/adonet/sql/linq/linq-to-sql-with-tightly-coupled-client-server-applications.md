---
title: "具有紧密耦合的客户端-服务器应用程序的 LINQ to SQL"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: e083d805-dcf6-459d-b9af-9ef0563f2dd7
caps.latest.revision: "2"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.workload: dotnet
ms.openlocfilehash: a2fa902cfbea3c6eb15e1832231bb3ed83de5497
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="linq-to-sql-with-tightly-coupled-client-server-applications"></a><span data-ttu-id="32830-102">具有紧密耦合的客户端-服务器应用程序的 LINQ to SQL</span><span class="sxs-lookup"><span data-stu-id="32830-102">LINQ to SQL with Tightly-Coupled Client-Server Applications</span></span>
[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]<span data-ttu-id="32830-103">可在中间层上与表示层上的紧密耦合智能客户端。</span><span class="sxs-lookup"><span data-stu-id="32830-103"> can be used on the middle tier with tightly-coupled Smart Clients on the presentation layer.</span></span> <span data-ttu-id="32830-104">在有些情况下，涉及到只读数据访问，没有进行开放式并发检查，或者具有时间戳的开放式并发，这种情况并不比非远程情况复杂很多。</span><span class="sxs-lookup"><span data-stu-id="32830-104">In scenarios that involve read-only data access, no optimistic concurrency checks, or optimistic concurrency with timestamps, there is not much more complexity than with non-remote scenarios.</span></span> <span data-ttu-id="32830-105">但是，当数据库要求使用原始值进行开放式并发检查时，[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] 不提供对数据集中数据往返的支持级别。</span><span class="sxs-lookup"><span data-stu-id="32830-105">However, when a database requires optimistic concurrency checks with original values, [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] does not provide the level of support for round-tripping of data that you find in DataSets.</span></span> <span data-ttu-id="32830-106">但是，[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] 中间层可以在任何平台上与客户端交换数据。</span><span class="sxs-lookup"><span data-stu-id="32830-106">However, a [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] middle tier can exchange data with clients on any platform.</span></span>  
  
 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]<span data-ttu-id="32830-107">在[!INCLUDE[vs_orcas_long](../../../../../../includes/vs-orcas-long-md.md)]提供无基础结构，以便跟踪实体状态后具有到客户端已序列化。</span><span class="sxs-lookup"><span data-stu-id="32830-107"> in [!INCLUDE[vs_orcas_long](../../../../../../includes/vs-orcas-long-md.md)] provides no infrastructure for tracking entity state after they have been serialized to a client.</span></span> [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]<span data-ttu-id="32830-108">支持面向服务的结构，其中数据和表示层之间的交互很小，相对原子的但不执行任何往返原始值。</span><span class="sxs-lookup"><span data-stu-id="32830-108"> enables service-oriented architectures where interactions between the data and presentation layers are small and relatively atomic, but does not perform any round-tripping of original values.</span></span> <span data-ttu-id="32830-109">因此，如果要将 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] 与紧密耦合的智能客户端结合使用，并且数据库使用具有原始值的开放式并发，那么您必须实现自己的机制，用于在表示层和中间层之间通告更改。</span><span class="sxs-lookup"><span data-stu-id="32830-109">Therefore, if you want to use a tightly-coupled Smart Client with [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)], and a database uses optimistic concurrency with original values, you will have to implement your own mechanism for communicating changes between the presentation tier and middle tier.</span></span> <span data-ttu-id="32830-110">系统设计器负责决定通过以这部分额外工作来换取 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] 在中间层上提供的优点是否有意义。</span><span class="sxs-lookup"><span data-stu-id="32830-110">It is up to the system designer to decide whether it makes sense to do this bit of extra work in exchange for the benefits that [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] provides on the middle tier.</span></span> <span data-ttu-id="32830-111">另一方面，如果数据库具有时间戳，那么就无需自定义的更改跟踪逻辑。</span><span class="sxs-lookup"><span data-stu-id="32830-111">On the other hand, if the database has timestamps, then there is no need for custom change-tracking logic.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="32830-112">请参阅</span><span class="sxs-lookup"><span data-stu-id="32830-112">See Also</span></span>  
 [<span data-ttu-id="32830-113">使用 LINQ to SQL 的 N 层和远程应用程序</span><span class="sxs-lookup"><span data-stu-id="32830-113">N-Tier and Remote Applications with LINQ to SQL</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/n-tier-and-remote-applications-with-linq-to-sql.md)  
 [<span data-ttu-id="32830-114">使用 Web 服务 的 LINQ to SQL N 层</span><span class="sxs-lookup"><span data-stu-id="32830-114">LINQ to SQL N-Tier with Web Services</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/linq-to-sql-n-tier-with-web-services.md)  
 [<span data-ttu-id="32830-115">在 N 层应用程序中使用数据集</span><span class="sxs-lookup"><span data-stu-id="32830-115">Work with datasets in n-tier applications</span></span>](http://msdn.microsoft.com/library/f6ae2ee0-ea5f-4a79-8f4b-e21c115afb20)
