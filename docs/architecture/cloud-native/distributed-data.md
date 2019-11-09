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
# <a name="distributed-data-for-cloud-native-apps"></a>适用于云原生应用的分布式数据

[!INCLUDE [book-preview](../../../includes/book-preview.md)]

构造包含许多独立微服务的云本机系统时，对数据存储进行更改的方式。

传统的单一应用程序倾向于图5-1 中所示的集中式数据存储。

![单一单一数据库](./media/single-monolithic-database.png)

**图 5-1**。 单一单一数据库

请注意，上图中的所有应用程序组件如何使用单个关系数据库。

此方法有很多好处。 查询跨多个表分布的数据非常简单，并且可以直接实现确保数据一致性的[ACID 事务](https://docs.microsoft.com/windows/desktop/cossdk/acid-properties)。 最终，最终会一直*保持一致*：要么是所有数据更新，要么都不这样做。

云本机系统支持图5-2 中所示的数据体系结构，其中每个微服务拥有并封装其自己的数据。

![跨微服务的多个数据库](./media/data-across-microservices.png)

**图 5-2**。 跨微服务的多个数据库

请注意上图中的每个微服务拥有的方式，并将其封装到数据存储，并且仅从公共 API 向外界公开数据。

利用此模型，每个微服务都可以独立地进行发展，而不必将数据架构更改与其他微服务进行协调。 每个微服务都可以自由实现数据存储（关系数据库、文档数据库、键值存储），这种类型最符合其需求。 在运行时，每个微服务都可以相应地缩放其数据。 如图5-3 所示：

![Polyglot 数据暂留](./media/polyglot-data-persistence.png)

**图 5-3**。 Polyglot 数据暂留

请注意上图中的 "产品目录" 和 "清单" 微服务如何采用关系数据库、排序微服务、NoSql 文档数据库和购物车微服务，这是一个外部键值存储区。 尽管关系数据库仍适用于使用复杂数据的微服务，但 NoSQL 数据库已经获得了相当多的普及，提供了适应性、快速查找和高可用性。 它们的无架构性质使开发人员可以从类型化的数据类和 Orm 的体系结构中消失，这会使更改成本高昂且非常耗时。

>[!div class="step-by-step"]
>[上一页](service-mesh-communication-infrastructure.md)
>[下一页](data-patterns.md)
