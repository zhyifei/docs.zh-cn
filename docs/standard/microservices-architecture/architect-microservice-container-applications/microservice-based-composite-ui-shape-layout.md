---
title: "创建复合 UI 基于微服务，包括 visual UI 形状和布局由多个微服务生成"
description: "为容器化的.NET 应用程序的.NET 微服务体系结构 |创建复合 UI 基于微服务，包括 visual UI 形状和布局由多个微服务生成"
keywords: "Docker, 微服务, ASP.NET, 容器"
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 05/26/2017
ms.prod: .net-core
ms.technology: dotnet-docker
ms.topic: article
ms.openlocfilehash: 4b32fed5eb0de02b01665efa4368eb83e3fda08d
ms.sourcegitcommit: e99dfadbca1992c187179b6a3b42bef44534ebb6
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/01/2017
---
# <a name="creating-composite-ui-based-on-microservices-including-visual-ui-shape-and-layout-generated-by-multiple-microservices"></a>创建复合 UI 基于微服务，包括 visual UI 形状和布局由多个微服务生成

微服务体系结构通常开头服务器端处理数据和逻辑。 但是，更高级的方法是设计用户界面基于微服务以及你的应用程序。 这意味着具有由微服务，而不只是使用微服务的整体的客户端应用和的服务器上的微服务是一个复合 UI。 使用此方法时，生成微服务可以完成，但逻辑和可视表示形式。

图 4-20 演示仅使用从单一的客户端应用程序的微服务的更简单的方法。 当然，你可以生成的 HTML 和 JavaScript 之间的 ASP.NET MVC 服务。 图是简化形式，用于突出显示具有单个 （整体） 客户端 UI 使用微服务，只需专注在逻辑和数据而不在 UI 形状 （HTML 和 JavaScript）。

![](./media/image20.png)

**图 4-20**。 使用后端微服务整体 UI 应用程序

与此相反，复合 UI 精确地生成并由微服务本身。 某些微服务驱动器 UI 的特定区域的可视化形状。 主要区别是，具有客户端 UI 组件 （例如 TS 类） 基于模板，并且这些模板数据调整 UI ViewModel 来自每个微服务。

在客户端应用程序启动时，每个客户端 UI 组件 （例如 TypeScript 类） 将自身注册到能够针对给定方案提供 Viewmodel 基础结构微服务。 如果 microservice 更改形状，UI 会也更改。

图 4-21 显示此复合 UI 方法的版本。 这简化，因为你可能具有其他聚合精细部分基于不同的技术的微服务 — 它依赖于生成的传统 web 方法 (ASP.NET MVC) 或 SPA （单页面应用程序）。

![](./media/image21.png)

**图 4-21**。 复合 UI 应用程序后端微服务受影响的示例

每个这些 UI 组合微服务将类似于小 API 网关。 但在这种情况下每负责较小的 UI 区域。

由微服务驱动的复合 UI 方法可以将更具挑战性或太快，具体取决于哪些 UI 技术正在使用。 例如，你不将用于构建你使用用于生成 SPA 或本机移动应用程序的传统 web 应用程序使用相同的技术 （如开发可以是此方法的更具挑战性的 Xamarin 应用时）。

[EShopOnContainers](http://aka.ms/MicroservicesArchitecture)示例应用程序使用的整体 UI 方法有多个原因。 首先，它是微服务和容器的简介。 复合 UI 更高级，但也需要进一步的设计和开发 UI 时的复杂性。 其次，eShopOnContainers 还提供了基于 Xamarin，可能会使其更复杂的客户端 C 的本机移动应用\#端。

但是，我们鼓励你可以使用以下引用若要了解有关复合 UI 基于微服务的详细信息。

## <a name="additional-resources"></a>其他资源

-   **使用 ASP.NET (特定的 Workshop 中) 的复合 UI**
    [*http://go.particular.net/workshop-composite-ui-demo*](http://go.particular.net/workshop-composite-ui-demo)

-   **Ruben Oostinga。微服务体系结构中的整体前端**
    [*http://blog.xebia.com/the-monolithic-frontend-in-the-microservices-architecture/*](http://blog.xebia.com/the-monolithic-frontend-in-the-microservices-architecture/)

-   **Mauro Servienti。更好用户界面组合的机密**
    [*https://particular.net/blog/secret-of-better-ui-composition*](https://particular.net/blog/secret-of-better-ui-composition)

-   **Viktor Farcic。包括到微服务的前端 Web 组件**
    [*https://technologyconversations.com/2015/08/09/including-front-end-web-components-into-microservices/*](https://technologyconversations.com/2015/08/09/including-front-end-web-components-into-microservices/)

-   **管理微服务体系结构中的前端**\
    [*http://allegro.tech/2016/03/Managing-Frontend-in-the-microservices-architecture.html*](http://allegro.tech/2016/03/Managing-Frontend-in-the-microservices-architecture.html)


>[!div class="step-by-step"]
[以前](微服务-可寻址性-服务-registry.md) [下一步] (弹性-高的可用性-microservices.md)
