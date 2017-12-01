---
title: "创建、 不断发展，和版本控制 microservice Api 和协定"
description: "为容器化的.NET 应用程序的.NET 微服务体系结构 |创建、 不断发展，和版本控制 microservice Api 和协定"
keywords: "Docker, 微服务, ASP.NET, 容器"
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 05/26/2017
ms.prod: .net-core
ms.technology: dotnet-docker
ms.topic: article
ms.openlocfilehash: 433711c3479eafd52bf9f5d53faf8e5707c6c624
ms.sourcegitcommit: c2e216692ef7576a213ae16af2377cd98d1a67fa
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/22/2017
---
# <a name="creating-evolving-and-versioning-microservice-apis-and-contracts"></a>创建、 不断发展，和版本控制 microservice Api 和协定

微服务 API 是服务及其客户端之间的协定。 你将能够独立地变化 microservice，仅当你不会中断其 API 协定，这正是协定是很重要。 如果更改协定时，它会影响客户端应用程序或 API 网关。

API 定义的性质取决于所使用的哪个协议。 例如，如果你使用消息传送 (如[AMQP](https://www.amqp.org/))，API 包含的消息类型。 如果你使用 HTTP 和 rest 样式服务，该 API 组成的 Url，并请求和响应的 JSON 格式。

但是，即使你是仔细初始协定，服务 API 将需要随时间而变化。 该事件发生时-尤其是如果你的 API 是一个由多个客户端应用程序使用的公共 API，你通常不能强制所有客户端升级到新的 API 约定。 通常需要以增量方式部署中同时运行的服务协定的旧和新版本的方式的服务的新版本。 因此，务必对它的服务版本控制的策略。

小型，如如果你将添加属性或参数到你的 API 的 API 更改时，使用较旧的 API 的客户端应切换，并适用于服务的新版本。 你可能能够提供默认值是必需的任何缺少的特性，并且客户端可能能够忽略任何额外的响应的属性。

但是，有时你需要对服务 API 进行主版本号和不兼容的更改。 因为你可能不能强制客户端应用程序或服务，若要立即升级到最新版本，服务必须段支持的 api 的较旧版本。 如果使用不基于 HTTP 的机制例如 REST，一种方法是在 URL 中或向 HTTP 标头中嵌入的 API 版本号。 然后你可以决定实现服务同时在同一服务实例，这两个版本，或部署每个处理 API 的版本的不同实例之间。 此一个好方法是[中介模式](https://en.wikipedia.org/wiki/Mediator_pattern)(例如， [MediatR 库](https://github.com/jbogard/MediatR)) 若要分离的不同实现版本到独立的处理程序。

最后，如果你使用 REST 体系结构，[超媒体](https://www.infoq.com/articles/mark-baker-hypermedia)是你的服务的版本控制的最佳解决方案，并允许 evolvable Api。

## <a name="additional-resources"></a>其他资源

-   **Scott Hanselman。ASP.NET 核心 RESTful Web API 版本控制变得更容易**
    <http://www.hanselman.com/blog/ASPNETCoreRESTfulWebAPIVersioningMadeEasy.aspx>

-   **版本控制 RESTful web API**
    [*https://docs.microsoft.com/azure/architecture/best-practices/api-design#versioning-a-restful-web-api*](https://docs.microsoft.com/azure/architecture/best-practices/api-design#versioning-a-restful-web-api)

-   **Roy Fielding。版本控制、 超媒体和 REST**
    <https://www.infoq.com/articles/roy-fielding-on-versioning>


>[!div class="step-by-step"]
[以前](异步-消息-基于-communication.md) [下一步] (微服务-可寻址性-服务-registry.md)
