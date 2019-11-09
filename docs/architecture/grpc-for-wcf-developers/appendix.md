---
title: 附录-适用于 WCF 开发人员的 gRPC
description: 在新式微服务体系结构中讨论分布式事务及其实现。
author: markrendle
ms.date: 09/02/2019
ms.openlocfilehash: d181eb07dd50ed338d02edb1908626e6ca3fb56c
ms.sourcegitcommit: 337bdc5a463875daf2cc6883e5a2da97d56f5000
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/24/2019
ms.locfileid: "73841677"
---
# <a name="appendix-a---transactions"></a>附录 A-事务

Windows Communication Foundation （WCF）支持的分布式事务，允许跨多个服务执行原子操作。 此功能基于[Microsoft 分布式事务处理协调器](https://docs.microsoft.com/previous-versions/windows/desktop/ms684146(v=vs.85))。

在新式微服务的环境中，这种类型的自动分布式事务处理是不可能的。 在播放时，有太多不同的技术，其中包括关系数据库、NoSQL 数据存储区和消息系统，而不是提到可在单个环境中使用的操作系统、编程语言和框架的组合。

WCF 分布式事务是称为[两阶段提交（2pc）](https://en.wikipedia.org/wiki/Two-phase_commit_protocol)的实现。 可以通过协调跨服务的消息、在每个服务中创建打开的事务，并根据成功或失败发送 "提交" 或 "回滚" 消息，手动实现2PC 事务。 但是，随着系统的发展，管理2PC 所涉及的复杂性可能会呈指数级增长，而开放事务会持有可能对性能产生负面影响的数据库锁，更糟的是导致跨服务死锁。

如果可能，最好避免分布式事务。 如果数据的两个项都需要进行原子更新，请考虑使用同一服务对它们进行处理，并使用单个请求或消息将这些原子更改应用到该服务。

如果无法做到这一点，一种替代方法是使用[Saga 模式](https://microservices.io/patterns/data/saga.html)。 在 saga 中，更新按顺序进行处理;每个更新成功后，将触发下一个更新。 这些触发器可以从服务传播到服务，或由 saga 协调器或 "orchestrator" 管理。 如果在此过程中的任何时间点更新失败，则已完成其更新的服务会应用特定的逻辑来反转它们。

另一种方法是使用域驱动设计（DDD）和命令/查询责任分离（CQRS），如[.Net 微服务电子书](https://docs.microsoft.com/dotnet/architecture/microservices/microservice-ddd-cqrs-patterns/)中所述。 特别是，使用域事件或[事件来源](https://martinfowler.com/eaaDev/EventSourcing.html)有助于确保在&mdash;不会立即&mdash;应用时更新更新。

>[!div class="step-by-step"]
>[上一部分](application-performance-management.md)
