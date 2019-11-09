---
title: 分布式数据
description: 构建适用于 Azure 的云本机 .NET 应用 |云本机应用的分布式数据
ms.date: 06/30/2019
ms.openlocfilehash: b715ae5203264a023bc9f911aa74ee222afe3d68
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/30/2019
ms.locfileid: "73841809"
---
# <a name="distributed-data-for-cloud-native-apps"></a><span data-ttu-id="0abc7-103">适用于云原生应用的分布式数据</span><span class="sxs-lookup"><span data-stu-id="0abc7-103">Distributed data for cloud-native apps</span></span>

[!INCLUDE [book-preview](../../../includes/book-preview.md)]

<span data-ttu-id="0abc7-104">构造包含许多独立微服务的云本机系统时，对数据存储进行更改的方式。</span><span class="sxs-lookup"><span data-stu-id="0abc7-104">When constructing a cloud-native system that consists of many independent microservices, the way you think about data storage changes.</span></span>

<span data-ttu-id="0abc7-105">传统的单一应用程序倾向于图5-1 中所示的集中式数据存储。</span><span class="sxs-lookup"><span data-stu-id="0abc7-105">Traditional monolithic applications favor a centralized data store shown in Figure 5-1.</span></span>

![单一单一数据库](./media/single-monolithic-database.png)

<span data-ttu-id="0abc7-107">**图 5-1**。</span><span class="sxs-lookup"><span data-stu-id="0abc7-107">**Figure 5-1**.</span></span> <span data-ttu-id="0abc7-108">单一单一数据库</span><span class="sxs-lookup"><span data-stu-id="0abc7-108">Single monolithic database</span></span>

<span data-ttu-id="0abc7-109">请注意，上图中的所有应用程序组件如何使用单个关系数据库。</span><span class="sxs-lookup"><span data-stu-id="0abc7-109">Note in the previous figure how all of the application components consume a single relational database.</span></span>

<span data-ttu-id="0abc7-110">此方法有很多好处。</span><span class="sxs-lookup"><span data-stu-id="0abc7-110">There are many benefits to this approach.</span></span> <span data-ttu-id="0abc7-111">查询跨多个表分布的数据非常简单，并且可以直接实现确保数据一致性的[ACID 事务](https://docs.microsoft.com/windows/desktop/cossdk/acid-properties)。</span><span class="sxs-lookup"><span data-stu-id="0abc7-111">It's straightforward to query data spread across  multiple tables, and it's straightforward to implement [ACID transactions](https://docs.microsoft.com/windows/desktop/cossdk/acid-properties) that ensure data consistency.</span></span> <span data-ttu-id="0abc7-112">最终，最终会一直*保持一致*：要么是所有数据更新，要么都不这样做。</span><span class="sxs-lookup"><span data-stu-id="0abc7-112">You always end up with *immediate consistency*: either all your data updates or none of it does.</span></span>

<span data-ttu-id="0abc7-113">云本机系统支持图5-2 中所示的数据体系结构，其中每个微服务拥有并封装其自己的数据。</span><span class="sxs-lookup"><span data-stu-id="0abc7-113">Cloud-native systems favor a data architecture shown in Figure 5-2 in which each microservice owns and encapsulates its own data.</span></span>

![跨微服务的多个数据库](./media/data-across-microservices.png)

<span data-ttu-id="0abc7-115">**图 5-2**。</span><span class="sxs-lookup"><span data-stu-id="0abc7-115">**Figure 5-2**.</span></span> <span data-ttu-id="0abc7-116">跨微服务的多个数据库</span><span class="sxs-lookup"><span data-stu-id="0abc7-116">Multiple databases across microservices</span></span>

<span data-ttu-id="0abc7-117">请注意上图中的每个微服务拥有的方式，并将其封装到数据存储，并且仅从公共 API 向外界公开数据。</span><span class="sxs-lookup"><span data-stu-id="0abc7-117">Note how in the previous figure each microservice owns and encapsulates it data store and only exposes data to the outside world from its public API.</span></span>

<span data-ttu-id="0abc7-118">利用此模型，每个微服务都可以独立地进行发展，而不必将数据架构更改与其他微服务进行协调。</span><span class="sxs-lookup"><span data-stu-id="0abc7-118">This model enables each microservice to evolve independently without having to coordinate data schema changes with other microservices.</span></span> <span data-ttu-id="0abc7-119">每个微服务都可以自由实现数据存储（关系数据库、文档数据库、键值存储），这种类型最符合其需求。</span><span class="sxs-lookup"><span data-stu-id="0abc7-119">Each microservice is free to implement the data store (relational database, document database, key-value store) type that best matches its needs.</span></span> <span data-ttu-id="0abc7-120">在运行时，每个微服务都可以相应地缩放其数据。</span><span class="sxs-lookup"><span data-stu-id="0abc7-120">At runtime, each microservice can scale its data accordingly.</span></span> <span data-ttu-id="0abc7-121">如图5-3 所示：</span><span class="sxs-lookup"><span data-stu-id="0abc7-121">This is shown in Figure 5-3:</span></span>

![Polyglot 数据暂留](./media/polyglot-data-persistence.png)

<span data-ttu-id="0abc7-123">**图 5-3**。</span><span class="sxs-lookup"><span data-stu-id="0abc7-123">**Figure 5-3**.</span></span> <span data-ttu-id="0abc7-124">Polyglot 数据暂留</span><span class="sxs-lookup"><span data-stu-id="0abc7-124">Polyglot data persistence</span></span>

<span data-ttu-id="0abc7-125">请注意上图中的 "产品目录" 和 "清单" 微服务如何采用关系数据库、排序微服务、NoSql 文档数据库和购物车微服务，这是一个外部键值存储区。</span><span class="sxs-lookup"><span data-stu-id="0abc7-125">Note how in the previous figure the product catalog and inventory microservices adopt relational databases, the ordering microservice, a NoSql document database, and the shopping cart microservice, which is an external key-value store.</span></span> <span data-ttu-id="0abc7-126">尽管关系数据库仍适用于使用复杂数据的微服务，但 NoSQL 数据库已经获得了相当多的普及，提供了适应性、快速查找和高可用性。</span><span class="sxs-lookup"><span data-stu-id="0abc7-126">While relational databases remain relevant for microservices with complex data, NoSQL databases have gained considerable popularity, providing adaptability, fast lookup, and high availability.</span></span> <span data-ttu-id="0abc7-127">它们的无架构性质使开发人员可以从类型化的数据类和 Orm 的体系结构中消失，这会使更改成本高昂且非常耗时。</span><span class="sxs-lookup"><span data-stu-id="0abc7-127">Their schemaless nature allows developers to move away from an architecture of typed data classes and ORMs that make change expensive and time-consuming.</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="0abc7-128">[上一页](service-mesh-communication-infrastructure.md)
>[下一页](data-patterns.md)</span><span class="sxs-lookup"><span data-stu-id="0abc7-128">[Previous](service-mesh-communication-infrastructure.md)
[Next](data-patterns.md)</span></span>
