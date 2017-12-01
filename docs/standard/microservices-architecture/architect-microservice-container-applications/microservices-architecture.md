---
title: "微服务体系结构"
description: "为容器化的.NET 应用程序的.NET 微服务体系结构 |微服务体系结构"
keywords: "Docker, 微服务, ASP.NET, 容器"
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 05/26/2017
ms.prod: .net-core
ms.technology: dotnet-docker
ms.topic: article
ms.openlocfilehash: 5ede1f0ad19270ca6b7556ff1bb7e4cf8ccf7cbe
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="microservices-architecture"></a>微服务体系结构

顾名思义，微服务体系结构将是一种方法生成服务器应用程序为小型服务的一组。 每个服务在其自己的进程中运行，并与其他进程使用 （如 HTTP/HTTPS)，Websocket 协议通信或[AMQP](https://en.wikipedia.org/wiki/Advanced_Message_Queuing_Protocol)。 每个微服务实现的特定的端到端域或在某些上下文边界内的业务功能和每个必须自主开发和进行可部署独立的。 最后，每个微服务应拥有其相关的域数据模型和基于不同的数据存储技术 （SQL、 NoSQL） 和编程语言不同的域逻辑 （自主性和分散的数据管理）。

Microservice 应该是什么大小？ 在开发时 microservice，大小不应是重要的一点。 相反，重要的一点应创建松散耦合服务以便您具有自主性的开发、 部署和缩放，每个服务。 当然，标识和设计时微服务，你应尝试使它们尽可能小，只要你没有与其他微服务直接依赖项太多。 不是微服务构成的大小是内部的内聚它必须具有和其独立于其他服务更重要。

为什么微服务体系结构？ 简单地说，它提供了长期的灵活性。 微服务启用更好的可维护性复杂、 大，且高度可伸缩的系统中通过让你创建基于许多，每个包含粒度和自治生命周期的独立可部署服务的应用程序。

作为一项额外权益，微服务可以向外扩展独立。 而不是让你必须向外扩展作为一个单元的单个整体应用程序，你可以改为向外扩展特定微服务。 这样一来，你可以扩展只需要更多的处理能力或网络带宽，以支持请求，而不是向外扩展的应用程序不需要进行扩展的其他区域的功能的区域。 这意味着节省成本，因为需要更少的硬件。

![](./media/image6.png)

**图 4-6**。 与微服务方法的整体部署

如图 4-6 所示，微服务方法就会允许敏捷更改和快速迭代的每个微服务，因为您可以更改的复杂、 大，且可缩放的应用程序特定的小区域。

构建细化基于微服务的应用程序启用持续集成和持续交付做法。 它还提高了新的函数传递到应用程序。 细化组成应用程序还允许你运行和测试微服务的隔离，并同时保持它们之间的清除协定自主发展。 只要不更改接口或协定，可以更改任何微服务构成的内部实现，或添加新功能，而不会断开其他微服务。

以下是重要的方面以便在转到生产环境且基于微服务的系统的成功：

-   监视和运行状况检查的服务和基础结构。

-   服务 （即，云和 orchestrators） 的可伸缩基础结构。

-   安全设计和实现多个级别： 身份验证、 授权、 机密管理、 安全通信，等等。

-   通常使用不同的团队将重点放在不同的微服务上的快速应用程序交付。

-   DevOps 和 CI/CD 实践和基础结构。

其中，仅第一个由三个涵盖或在本指南中引入的。 最后两个点，与应用程序生命周期相关，介绍其他[容器 Docker 应用生命周期内使用 Microsoft 平台和工具](https://aka.ms/dockerlifecycleebook)电子书。

## <a name="additional-resources"></a>其他资源

-   **Mark Russinovich。微服务： 由云应用程序 revolution**
    [*https://azure.microsoft.com/blog/microservices-an-application-revolution-powered-by-the-cloud/*](https://azure.microsoft.com/blog/microservices-an-application-revolution-powered-by-the-cloud/)

-   **Martin Fowler。微服务**
    [*http://www.martinfowler.com/articles/microservices.html*](http://www.martinfowler.com/articles/microservices.html)

-   **Martin Fowler。Microservice 先决条件**
    [*http://martinfowler.com/bliki/MicroservicePrerequisites.html*](http://martinfowler.com/bliki/MicroservicePrerequisites.html)

-   **Jimmy Nilsson。块区云计算**
    [*https://www.infoq.com/articles/CCC-Jimmy-Nilsson*](https://www.infoq.com/articles/CCC-Jimmy-Nilsson)

-   **Cesar de la Torre。容器 Docker 应用生命周期内使用 Microsoft 平台和工具**（可下载电子图书） [ *https://aka.ms/dockerlifecycleebook*](https://aka.ms/dockerlifecycleebook)




>[!div class="step-by-step"]
[以前](服务-面向-architecture.md) [下一步] (数据-自主性-每个-microservice.md)
