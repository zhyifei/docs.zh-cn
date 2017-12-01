---
title: "微服务可寻址性和服务注册表"
description: "为容器化的.NET 应用程序的.NET 微服务体系结构 |微服务可寻址性和服务注册表"
keywords: "Docker, 微服务, ASP.NET, 容器"
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 05/26/2017
ms.prod: .net-core
ms.technology: dotnet-docker
ms.topic: article
ms.openlocfilehash: 19a0200dadfb90a455de690d880f4eeae4772ed7
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="microservices-addressability-and-the-service-registry"></a>微服务可寻址性和服务注册表

每个微服务具有一个唯一名称 (URL)，用于解析其位置。 你微服务必须是可寻址的只要它正在运行。 如果必须考虑有关哪台计算机正在运行特定的微服务，操作可能会快速错误。 在 DNS 解析 URL，到特定计算机的方式相同，你的 microservice 需要具有唯一的名称，以便其当前的位置是可发现。 微服务需要可寻址使它们独立于在运行的基础结构的名称。 这意味着由于需要有没有你的服务的部署方式与它如何发现之间交互[服务注册表](http://microservices.io/patterns/service-registry.html)。 在相同情况下，计算机发生故障，注册表服务必须能够指示该服务现在运行。

[服务注册表模式](http://microservices.io/patterns/service-registry.html)是服务发现的一个关键部分。 注册表是包含服务实例的网络位置的数据库。 服务注册表需要高可用性和最新。 客户端无法缓存从服务注册表中获得的网络位置。 但是，该信息最终将过期并且客户端不再可发现服务实例。 因此，服务注册表包含使用复制协议来保持一致性的服务器的群集。

在某些微服务部署环境中 （称为群集，若要在更高版本的部分讨论），服务发现是内置的。 例如，在一个 Azure 容器服务的环境 Kubernetes DC/操作系统 Marathon 可以处理服务实例注册和取消注册。 它们还充当的角色的服务器端发现路由器每个群集主机上运行代理。 另一个示例是 Azure Service Fabric，还提供了通过其中的框命名服务的服务注册表。

请注意，某些服务注册表和 API 的网关模式，这有助于解决此问题也之间的重叠。 例如，[服务 Fabric 反向代理](https://docs.microsoft.com/azure/service-fabric/service-fabric-reverseproxy)是一种基于服务 Fabrice 命名服务，以帮助解决地址解析到内部服务的 API 网关的实现。

## <a name="additional-resources"></a>其他资源

-   **Chris Richardson。模式： 服务注册表**
    *http://microservices.io/patterns/service-registry.html*

-   **Auth0。服务注册表**
    [*https://auth0.com/blog/an-introduction-to-microservices-part-3-the-service-registry/*](https://auth0.com/blog/an-introduction-to-microservices-part-3-the-service-registry/)

-   **Gabriel Schenker。服务发现**
    [*https://lostechies.com/gabrielschenker/2016/01/27/service-discovery/*](https://lostechies.com/gabrielschenker/2016/01/27/service-discovery/)


>[!div class="step-by-step"]
[以前](维护-microservice-apis.md) [下一步] (microservice-based-composite-ui-shape-layout.md)
