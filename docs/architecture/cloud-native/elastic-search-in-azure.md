---
title: 云原生应用程序中的弹性搜索
description: 了解如何将弹性搜索功能添加到云本机应用程序。
author: robvet
ms.date: 03/02/2020
ms.openlocfilehash: da6b9402cf266f5a298b05cf837805b2377bc75a
ms.sourcegitcommit: f87ad41b8e62622da126aa928f7640108c4eff98
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/07/2020
ms.locfileid: "80805560"
---
# <a name="elasticsearch-in-a-cloud-native-app"></a>云原生应用程序中的弹性搜索

[!INCLUDE [book-preview](../../../includes/book-preview.md)]

弹性搜索是一个分布式搜索和分析系统，能够跨不同类型的数据实现复杂的搜索功能。 它是开源的，很受欢迎。 考虑以下公司如何将弹性搜索集成到其应用程序中：

- [维基百科](https://blog.wikimedia.org/2014/01/06/wikimedia-moving-to-elasticsearch/)用于全文和增量（搜索，你键入）搜索。
- [GitHub](https://www.elastic.co/customers/github)用于索引和公开超过 800 万个代码存储库。  
- [用于](https://www.elastic.co/customers/docker)使其容器库可发现。

弹性搜索是建立在[阿帕奇卢塞内](https://lucene.apache.org/core/)全文搜索引擎的顶部。 Lucene 提供高性能的文档索引和查询。 它使用倒置索引方案对数据进行索引 - 它不是将页面映射到关键字，而是将关键字映射到页面，就像书尾的词汇表一样。 Lucene 具有强大的查询语法功能，可以通过以下功能查询数据：

- 术语（完整单词）
- 前缀（以单词开头）
- 通配符（使用\*""或""筛选器）
- 短语（文档中的文本序列）
- 布尔值（合并查询的复杂搜索）

虽然 Lucene 提供用于搜索的低级管道，但 Elasticsearch 提供位于 Lucene 顶部的服务器。 Elasticsearch 增加了更高级别的功能来简化工作 Lucene，包括用于访问 Lucene 索引和搜索功能的 RESTful API。 它还提供了能够大规模可扩展性、容错性和高可用性的分布式基础架构。

对于具有复杂搜索要求的大型云本机应用程序，弹性搜索在 Azure 中作为托管服务提供。 Microsoft Azure 应用商店具有预先配置的模板，开发人员可以使用这些模板在 Azure 上部署弹性搜索群集。

在 Microsoft Azure 应用商店中，开发人员可以使用构建的预配置模板在 Azure 上快速部署弹性搜索群集。 使用 Azure 管理的产品，您最多可以部署 50 个数据节点、20 个协调节点和 3 个专用主节点。

## <a name="summary"></a>总结

本章详细介绍了云本机系统中的数据。 我们首先将单片应用程序中的数据存储与云原生系统中的数据存储模式进行对比。 我们研究了在云本机系统中实现的数据模式，包括跨服务查询、分布式事务和处理大容量系统的模式。 我们将 SQL 与 NoSQL 数据进行了对比。 我们查看了 Azure 中提供的数据存储选项，这些选项包括以 Microsoft 为中心的开源选项。 最后，我们在云本机应用程序中讨论了缓存和弹性搜索。

### <a name="references"></a>参考

- [命令和查询责任分离 (CQRS) 模式](https://docs.microsoft.com/azure/architecture/patterns/cqrs)

- [事件采购模式](https://docs.microsoft.com/azure/architecture/patterns/event-sourcing)

- [为什么在 CAP 定理中 RDBMS 分区容错，为什么它可用？](https://stackoverflow.com/questions/36404765/why-isnt-rdbms-partition-tolerant-in-cap-theorem-and-why-is-it-available)

- [具体化视图](https://docs.microsoft.com/azure/architecture/patterns/materialized-view)

- [您真正需要知道的关于开源数据库的所有信息](https://www.ibm.com/blogs/systems/all-you-really-need-to-know-about-open-source-databases/)

- [补偿事务模式](https://docs.microsoft.com/azure/architecture/patterns/compensating-transaction)

- [佐贺模式](https://microservices.io/patterns/data/saga.html)

- [佐贺模式 |如何使用微服务实现业务事务](https://blog.couchbase.com/saga-pattern-implement-business-transactions-using-microservices-part/)

- [补偿事务模式](https://docs.microsoft.com/azure/architecture/patterns/compensating-transaction)

- [在 9 球后面：解释宇宙 DB 一致性级别](https://blog.jeremylikness.com/blog/2018-03-23_getting-behind-the-9ball-cosmosdb-consistency-levels/)

- [探索不同类型的NoSQL数据库第二部分](https://www.3pillarglobal.com/insights/exploring-the-different-types-of-nosql-databases)

- [在 RDBMS、NoSQL 和 NewSQL 数据库中。采访约翰·瑞安](http://www.odbms.org/blog/2018/03/on-rdbms-nosql-and-newsql-databases-interview-with-john-ryan/)
  
- [SQL vs NoSQL vs NewSQL：完整比较](https://www.xenonstack.com/blog/sql-vs-nosql-vs-newsql/)

- [DASH：库伯内斯-本机数据库的四个属性](https://thenewstack.io/dash-four-properties-of-kubernetes-native-databases/)

- [蟑螂DB](https://www.cockroachlabs.com/)

- [提亚布](https://pingcap.com/en/)

- [尤加字节开发银行](https://www.yugabyte.com/)

- [维特斯](https://vitess.io/)

- [弹性搜索：最终指南](http://shop.oreilly.com/product/0636920028505.do)
  
- [阿帕奇·卢塞内简介](https://www.baeldung.com/lucene)

>[!div class="step-by-step"]
>[上一页](azure-caching.md)
>[下一页](resiliency.md) <!-- Next Chapter -->
