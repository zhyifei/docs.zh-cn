---
title: 逻辑体系结构与物理体系结构
description: 适用于容器化 .NET 应用程序的 .NET 微服务体系结构 | 逻辑体系结构与物理体系结构
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 05/26/2017
ms.openlocfilehash: bb5f0daf0bcf824d72bb104914de03532bd3f9f7
ms.sourcegitcommit: c7f3e2e9d6ead6cc3acd0d66b10a251d0c66e59d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/09/2018
ms.locfileid: "44213337"
---
# <a name="logical-architecture-versus-physical-architecture"></a>逻辑体系结构与物理体系结构

此时若停止并讨论逻辑体系结构和物理体系结构之间的区别，以及将其用于设计基于微服务的应用程序的方式，会很有用。

首先，创建一个基于微服务的体系结构不需要使用特定的技术。也就是说基于微服务的体系结构不一定需要 Docker 容器。 这些微服务也可以像普通进程那样运行。 微服务是一种逻辑体系结构。

此外，即使微服务能够使用单一服务、进程或容器实现（为简化起见，此方法是 [eShopOnContainers](https://aka.ms/MicroservicesArchitecture) 原始版本采取的做法），生成由数十个甚至数百个服务组成的大型复杂应用程序时，并不是一定要使用到业务微服务和物理服务或容器。

这就是应用程序的逻辑体系结构和物理体系结构之间存在的差异。 系统的逻辑体系结构和逻辑边界不一定要与物理或部署体系结构一对一映射。 这种情况可能会发生，但不会经常发生。

尽管已确定某些业务的微服务或界定上下文，但这并不意味着实现它们的最佳方式总是为每个业务微服务创建单一服务（如 ASP.NET Web API）或者单一 Docker 容器。 必须使用单一服务或容器实现每个业务微服务的这一规则过于严苛。

因此，业务微服务或界定上下文的逻辑体系结构是可能与物理体系结构不一致。 最重要的一点使代码和状态可独立、可进行版本控制、部署和缩放，让业务微服务或界定上下文能够自治。

如图 4-8 所示，Catalog 业务微服务可由几个服务或进程组成。 这些服务可以是多个 ASP.NET Web API 服务，也可以是使用 HTTP 或其他任何协议的其他任何服务。 更重要的是，这些服务只要对于相同业务领域具有内聚性，便能共享相同数据。

![](./media/image8.png)

**图 4-8**。 使用多个物理服务的业务微服务

示例中的服务共享相同的数据模型，因为 Web API 服务面向的是与搜索服务相同的数据。 因此，在业务微服务的物理实现中，拆分该功能便可根据需要纵向扩展或横向扩展这些内部服务中的每一个。 Web API 服务通常比搜索服务需要更多的实例，反之亦然。

简而言之，微服务的逻辑体系结构并不总是与物理部署体系结构一致。 在本指南中，我们所提到的微服务是可以映射到一个或多个服务的业务微服务或逻辑微服务。 大多数情况下，可以映射到单个服务，但也有可能映射到多个服务。


>[!div class="step-by-step"]
[上一页](data-sovereignty-per-microservice.md)
[下一页](distributed-data-management.md)
