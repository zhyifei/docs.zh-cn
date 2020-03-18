---
title: 云原生应用程序中的弹性搜索
description: 了解如何将弹性搜索功能添加到云本机应用程序。
author: robvet
ms.date: 01/22/2020
ms.openlocfilehash: 1bce255b6315006b11e0b6ac77040300f67ed984
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2020
ms.locfileid: "79141284"
---
# <a name="elasticsearch-in-a-cloud-native-app"></a><span data-ttu-id="ca314-103">云原生应用程序中的弹性搜索</span><span class="sxs-lookup"><span data-stu-id="ca314-103">Elasticsearch in a cloud-native app</span></span>

[!INCLUDE [book-preview](../../../includes/book-preview.md)]

<span data-ttu-id="ca314-104">弹性搜索是一个分布式搜索和分析系统，能够跨不同类型的数据实现复杂的搜索功能。</span><span class="sxs-lookup"><span data-stu-id="ca314-104">Elasticsearch is a distributed search and analytics system that enables complex search capabilities across diverse types of data.</span></span> <span data-ttu-id="ca314-105">它是开源的，很受欢迎。</span><span class="sxs-lookup"><span data-stu-id="ca314-105">It's open source and widely popular.</span></span> <span data-ttu-id="ca314-106">考虑以下公司如何将弹性搜索集成到其应用程序中：</span><span class="sxs-lookup"><span data-stu-id="ca314-106">Consider how the following companies integrate Elasticsearch into their application:</span></span>

- <span data-ttu-id="ca314-107">[维基百科](https://blog.wikimedia.org/2014/01/06/wikimedia-moving-to-elasticsearch/)用于全文和增量（搜索，你键入）搜索。</span><span class="sxs-lookup"><span data-stu-id="ca314-107">[Wikipedia](https://blog.wikimedia.org/2014/01/06/wikimedia-moving-to-elasticsearch/) for full-text and incremental (search as you type) searching.</span></span>
- <span data-ttu-id="ca314-108">[GitHub](https://www.elastic.co/customers/github)用于索引和公开超过 800 万个代码存储库。</span><span class="sxs-lookup"><span data-stu-id="ca314-108">[GitHub](https://www.elastic.co/customers/github) to index and expose over 8 million code repositories.</span></span>  
- <span data-ttu-id="ca314-109">[用于](https://www.elastic.co/customers/docker)使其容器库可发现。</span><span class="sxs-lookup"><span data-stu-id="ca314-109">[Docker](https://www.elastic.co/customers/docker) for making its container library discoverable.</span></span>

<span data-ttu-id="ca314-110">弹性搜索是建立在[阿帕奇卢塞内](https://lucene.apache.org/core/)全文搜索引擎的顶部。</span><span class="sxs-lookup"><span data-stu-id="ca314-110">Elasticsearch is built on top of the [Apache Lucene](https://lucene.apache.org/core/) full-text search engine.</span></span> <span data-ttu-id="ca314-111">Lucene 提供高性能的文档索引和查询。</span><span class="sxs-lookup"><span data-stu-id="ca314-111">Lucene provides high-performance document indexing and querying.</span></span> <span data-ttu-id="ca314-112">它使用倒置索引方案对数据进行索引 - 它不是将页面映射到关键字，而是将关键字映射到页面，就像书尾的词汇表一样。</span><span class="sxs-lookup"><span data-stu-id="ca314-112">It indexes data with an inverted indexing scheme – instead of mapping pages to keywords, it maps keywords to pages just like a glossary at the end of a book.</span></span> <span data-ttu-id="ca314-113">Lucene 具有强大的查询语法功能，可以通过以下功能查询数据：</span><span class="sxs-lookup"><span data-stu-id="ca314-113">Lucene has powerful query syntax capabilities and can query data by:</span></span>

- <span data-ttu-id="ca314-114">术语（完整单词）</span><span class="sxs-lookup"><span data-stu-id="ca314-114">Term (a full word)</span></span>
- <span data-ttu-id="ca314-115">前缀（以单词开头）</span><span class="sxs-lookup"><span data-stu-id="ca314-115">Prefix (starts-with word)</span></span>
- <span data-ttu-id="ca314-116">通配符（使用\*""或""筛选器）</span><span class="sxs-lookup"><span data-stu-id="ca314-116">Wildcard (using "\*" or "?" filters)</span></span>
- <span data-ttu-id="ca314-117">短语（文档中的文本序列）</span><span class="sxs-lookup"><span data-stu-id="ca314-117">Phrase (a sequence of text in a document)</span></span>
- <span data-ttu-id="ca314-118">布尔值（合并查询的复杂搜索）</span><span class="sxs-lookup"><span data-stu-id="ca314-118">Boolean value (complex searches combining queries)</span></span>

<span data-ttu-id="ca314-119">虽然 Lucene 提供用于搜索的低级管道，但 Elasticsearch 提供位于 Lucene 顶部的服务器。</span><span class="sxs-lookup"><span data-stu-id="ca314-119">While Lucene provides low-level plumbing for searching, Elasticsearch provides the server that sits on top of Lucene.</span></span> <span data-ttu-id="ca314-120">Elasticsearch 增加了更高级别的功能来简化工作 Lucene，包括用于访问 Lucene 索引和搜索功能的 RESTful API。</span><span class="sxs-lookup"><span data-stu-id="ca314-120">Elasticsearch adds higher-level functionality to simplify working Lucene, including a RESTful API to access Lucene’s indexing and searching functionality.</span></span> <span data-ttu-id="ca314-121">它还提供了能够大规模可扩展性、容错性和高可用性的分布式基础架构。</span><span class="sxs-lookup"><span data-stu-id="ca314-121">It also provides a distributed infrastructure capable of massive scalability, fault tolerance, and high availability.</span></span>

<span data-ttu-id="ca314-122">对于具有复杂搜索要求的大型云本机应用程序，弹性搜索在 Azure 中作为托管服务提供。</span><span class="sxs-lookup"><span data-stu-id="ca314-122">For larger cloud-native applications with complex search requirements, Elasticsearch is available as managed service in Azure.</span></span> <span data-ttu-id="ca314-123">Microsoft Azure 应用商店具有预先配置的模板，开发人员可以使用这些模板在 Azure 上部署弹性搜索群集。</span><span class="sxs-lookup"><span data-stu-id="ca314-123">The Microsoft Azure Marketplace features preconfigured templates which developers can use to deploy an Elasticsearch cluster on Azure.</span></span>

<span data-ttu-id="ca314-124">在 Microsoft Azure 应用商店中，开发人员可以使用构建的预配置模板在 Azure 上快速部署弹性搜索群集。</span><span class="sxs-lookup"><span data-stu-id="ca314-124">From the Microsoft Azure Marketplace, developers can use preconfigured templates built to quickly deploy an Elasticsearch cluster on Azure.</span></span> <span data-ttu-id="ca314-125">使用 Azure 管理的产品，您最多可以部署 50 个数据节点、20 个协调节点和 3 个专用主节点。</span><span class="sxs-lookup"><span data-stu-id="ca314-125">Using the Azure-managed offering, you can deploy up to 50 data nodes, 20 coordinating nodes, and three dedicated master nodes.</span></span>

## <a name="summary"></a><span data-ttu-id="ca314-126">总结</span><span class="sxs-lookup"><span data-stu-id="ca314-126">Summary</span></span>

<span data-ttu-id="ca314-127">本章详细介绍了云本机系统中的数据。</span><span class="sxs-lookup"><span data-stu-id="ca314-127">This chapter presented a detailed look at data in cloud-native systems.</span></span> <span data-ttu-id="ca314-128">我们首先将单片应用程序中的数据存储与云原生系统中的数据存储模式进行对比。</span><span class="sxs-lookup"><span data-stu-id="ca314-128">We started by contrasting data storage in monolithic applications with data storage patterns in cloud-native systems.</span></span> <span data-ttu-id="ca314-129">我们研究了在云本机系统中实现的数据模式，包括跨服务查询、分布式事务和处理大容量系统的模式。</span><span class="sxs-lookup"><span data-stu-id="ca314-129">We looked at data patterns implemented in cloud-native systems, including cross-service queries, distributed transactions, and patterns to deal with high-volume systems.</span></span> <span data-ttu-id="ca314-130">我们将 SQL 与 NoSQL 数据进行了对比。</span><span class="sxs-lookup"><span data-stu-id="ca314-130">We contrasted SQL with NoSQL data.</span></span> <span data-ttu-id="ca314-131">我们查看了 Azure 中提供的数据存储选项，这些选项包括以 Microsoft 为中心的开源选项。</span><span class="sxs-lookup"><span data-stu-id="ca314-131">We looked at data storage options available in Azure that include both Microsoft-centric and open-source options.</span></span> <span data-ttu-id="ca314-132">最后，我们在云本机应用程序中讨论了缓存和弹性搜索。</span><span class="sxs-lookup"><span data-stu-id="ca314-132">Finally, we discussed caching and Elasticsearch in a cloud-native application.</span></span>

### <a name="references"></a><span data-ttu-id="ca314-133">参考</span><span class="sxs-lookup"><span data-stu-id="ca314-133">References</span></span>

- [<span data-ttu-id="ca314-134">命令和查询责任分离 (CQRS) 模式</span><span class="sxs-lookup"><span data-stu-id="ca314-134">Command and Query Responsibility Segregation (CQRS) pattern</span></span>](https://docs.microsoft.com/azure/architecture/patterns/cqrs)

- [<span data-ttu-id="ca314-135">事件采购模式</span><span class="sxs-lookup"><span data-stu-id="ca314-135">Event Sourcing pattern</span></span>](https://docs.microsoft.com/azure/architecture/patterns/event-sourcing)

- [<span data-ttu-id="ca314-136">RDBMS vs. NoSQL 数据库：概述</span><span class="sxs-lookup"><span data-stu-id="ca314-136">RDBMSs vs. NoSQL Databases: Overview</span></span>](https://maxivak.com/rdbms-vs-nosql-databases/)

- [<span data-ttu-id="ca314-137">为什么在 CAP 定理中 RDBMS 分区容错，为什么它可用？</span><span class="sxs-lookup"><span data-stu-id="ca314-137">Why isn't RDBMS Partition Tolerant in CAP Theorem and why is it Available?</span></span>](https://stackoverflow.com/questions/36404765/why-isnt-rdbms-partition-tolerant-in-cap-theorem-and-why-is-it-available)

- [<span data-ttu-id="ca314-138">具体化视图</span><span class="sxs-lookup"><span data-stu-id="ca314-138">Materialized View</span></span>](https://docs.microsoft.com/azure/architecture/patterns/materialized-view)

- [<span data-ttu-id="ca314-139">您真正需要知道的关于开源数据库的所有信息</span><span class="sxs-lookup"><span data-stu-id="ca314-139">All you really need to know about open source databases</span></span>](https://www.ibm.com/blogs/systems/all-you-really-need-to-know-about-open-source-databases/)

- [<span data-ttu-id="ca314-140">补偿事务模式</span><span class="sxs-lookup"><span data-stu-id="ca314-140">Compensating Transaction pattern</span></span>](https://docs.microsoft.com/azure/architecture/patterns/compensating-transaction)

- [<span data-ttu-id="ca314-141">佐贺模式</span><span class="sxs-lookup"><span data-stu-id="ca314-141">Saga Pattern</span></span>](https://microservices.io/patterns/data/saga.html)

- [<span data-ttu-id="ca314-142">佐贺模式 |如何使用微服务实现业务事务</span><span class="sxs-lookup"><span data-stu-id="ca314-142">Saga Patterns | How to implement business transactions using microservices</span></span>](https://blog.couchbase.com/saga-pattern-implement-business-transactions-using-microservices-part/)

- [<span data-ttu-id="ca314-143">补偿事务模式</span><span class="sxs-lookup"><span data-stu-id="ca314-143">Compensating Transaction pattern</span></span>](https://docs.microsoft.com/azure/architecture/patterns/compensating-transaction)

- [<span data-ttu-id="ca314-144">在 9 球后面：解释宇宙 DB 一致性级别</span><span class="sxs-lookup"><span data-stu-id="ca314-144">Getting Behind the 9-Ball: Cosmos DB Consistency Levels Explained</span></span>](https://blog.jeremylikness.com/blog/2018-03-23_getting-behind-the-9ball-cosmosdb-consistency-levels/)

- [<span data-ttu-id="ca314-145">探索不同类型的NoSQL数据库第二部分</span><span class="sxs-lookup"><span data-stu-id="ca314-145">Exploring the different types of NoSQL Databases Part II</span></span>](https://www.3pillarglobal.com/insights/exploring-the-different-types-of-nosql-databases)

- [<span data-ttu-id="ca314-146">在 RDBMS、NoSQL 和 NewSQL 数据库中。采访约翰·瑞安</span><span class="sxs-lookup"><span data-stu-id="ca314-146">On RDBMS, NoSQL and NewSQL databases. Interview with John Ryan</span></span>](http://www.odbms.org/blog/2018/03/on-rdbms-nosql-and-newsql-databases-interview-with-john-ryan/)
  
- [<span data-ttu-id="ca314-147">SQL vs NoSQL vs NewSQL：完整比较</span><span class="sxs-lookup"><span data-stu-id="ca314-147">SQL vs NoSQL vs NewSQL: The Full Comparison</span></span>](https://www.xenonstack.com/blog/sql-vs-nosql-vs-newsql/)

- [<span data-ttu-id="ca314-148">DASH：库伯内斯-本机数据库的四个属性</span><span class="sxs-lookup"><span data-stu-id="ca314-148">DASH: Four Properties of Kubernetes-Native Databases</span></span>](https://thenewstack.io/dash-four-properties-of-kubernetes-native-databases/)

- [<span data-ttu-id="ca314-149">蟑螂DB</span><span class="sxs-lookup"><span data-stu-id="ca314-149">CockroachDB</span></span>](https://www.cockroachlabs.com/)

- [<span data-ttu-id="ca314-150">提亚布</span><span class="sxs-lookup"><span data-stu-id="ca314-150">TiDB</span></span>](https://pingcap.com/en/)

- [<span data-ttu-id="ca314-151">尤加字节开发银行</span><span class="sxs-lookup"><span data-stu-id="ca314-151">YugabyteDB</span></span>](https://www.yugabyte.com/)

- [<span data-ttu-id="ca314-152">维特斯</span><span class="sxs-lookup"><span data-stu-id="ca314-152">Vitess</span></span>](https://vitess.io/)

- [<span data-ttu-id="ca314-153">弹性搜索：最终指南</span><span class="sxs-lookup"><span data-stu-id="ca314-153">Elasticsearch: The Definitive Guide</span></span>](http://shop.oreilly.com/product/0636920028505.do)
  
- [<span data-ttu-id="ca314-154">阿帕奇·卢塞内简介</span><span class="sxs-lookup"><span data-stu-id="ca314-154">Introduction to Apache Lucene</span></span>](https://www.baeldung.com/lucene)

>[!div class="step-by-step"]
><span data-ttu-id="ca314-155">[上一个](azure-caching.md)
>[下一个](resiliency.md)</span><span class="sxs-lookup"><span data-stu-id="ca314-155">[Previous](azure-caching.md)
[Next](resiliency.md)</span></span> <!-- Next Chapter -->
