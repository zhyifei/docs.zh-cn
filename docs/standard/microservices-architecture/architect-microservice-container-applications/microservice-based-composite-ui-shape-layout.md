---
title: 根据微服务创建复合 UI，包括多个微服务生成的可视 UI 形状和布局
description: 适用于容器化 .NET 应用程序的 .NET 微服务体系结构 | 根据微服务创建复合 UI，包括多个微服务生成的可视 UI 形状和布局
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 05/26/2017
ms.openlocfilehash: 3c5f4c5a1dd1c1065be63ad916af078050c069c1
ms.sourcegitcommit: 5fd80619c760fa8c25d33a6f5661247cb65da465
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/01/2018
ms.locfileid: "50744491"
---
# <a name="creating-composite-ui-based-on-microservices-including-visual-ui-shape-and-layout-generated-by-multiple-microservices"></a>根据微服务创建复合 UI，包括多个微服务生成的可视 UI 形状和布局

微服务体系结构通常从服务器端处理数据和逻辑开始。 但是，根据微服务设计应用程序 UI 是更好的方法。 这意味着拥有的是由微服务生成的复合 UI，而不是服务器上的微服务和使用微服务的整体式客户端应用。 按照这种方法构建的微服务具有逻辑和可视化表示形式，功能十分完整。

图 4-20 显示了在整体式客户端应用程序中使用微服务的更为简单的方式。 当然，在生成 HTML 之后，可以创建一个 ASP.NET MVC 服务，再生成 JavaScript。 该图是一张简图，强调拥有使用微服务的单一（整体式）客户端 UI，该 UI 仅关注逻辑和数据，而不关注 UI 形状（HTML 和 JavaScript）。

![](./media/image20.png)

图 4-20。 使用后端微服务的整体式 UI 应用程序

与之相比，复合 UI 是由微服务本身精确生成和组合成的。 一些微服务可控制 UI 特定区域的视觉形状。 主要区别在于，这具有基于模板的客户端 UI 组件（例如 TS 类），而这些模板的 data-shaping-UI ViewModel 来自于每个微服务。

客户端应用程序启动时，每个客户端 UI 组件（例如 TypeScript 类）自身都会注册一个基础结构微服务，该微服务能够为特定方案提供 ViewModel。 如果微服务形状发生更改，则 UI 也会更改。

图 4-21 显示了一种复合 UI 方法。 这只是一张简图，因为你可能有其他基于不同技术聚合精细部件的微服务，具体取决于是构建传统 Web 方法 (ASP.NET MVC) 还是 SPA（单页应用程序）。

![](./media/image21.png)

图 4-21。 由后端微服务形成的复合 UI 应用程序示例

这些 UI 组合微服务中的每一个都类似于一个小型的 API 网关。 但在此处，每个服务都负责一个小的 UI 领域。

由微服务驱动的复合 UI 方法的挑战性可能更大也可能更小，具体取决于使用的 UI 技术。 例如，对于用于生成 SPA 或本机移动应用的传统 Web 应用程序，则不会使用相同的构建技术（如开发 Xamarin 应用时，此方法可能更具挑战性）。

出于多种原因，[eShopOnContainers](https://aka.ms/MicroservicesArchitecture) 示例应用程序使用整体式 UI 方法。 首先，其作用是引入微服务和容器。 虽然复合 UI 更高级，但该 UI 的设计和开发工作也更复杂。 其次，eShopOnContainers 还提供了基于 Xamarin 的本机移动应用，这增加了客户端 C\# 的复杂性。

不过，建议通过以下参考资料，深入了解基于微服务的复合 UI。

## <a name="additional-resources"></a>其他资源

-   **Composite UI using ASP.NET (Particular’s Workshop)**（使用 ASP.NET（Particular 的 Workshop）的复合 UI）
    [https://go.particular.net/workshop-composite-ui-demo](https://go.particular.net/workshop-composite-ui-demo)

-   **Ruben Oostinga。The Monolithic Frontend in the Microservices Architecture**（微服务体系结构中的整体式前端）
    [https://xebia.com/blog/the-monolithic-frontend-in-the-microservices-architecture/](https://xebia.com/blog/the-monolithic-frontend-in-the-microservices-architecture/)

-   **Mauro Servienti。The secret of better UI composition**（实现更好的 UI 组合的秘诀）
    [https://particular.net/blog/secret-of-better-ui-composition](https://particular.net/blog/secret-of-better-ui-composition)

-   **Viktor Farcic。Including Front-End Web Components Into Microservices**（将前端 Web 组件包含到微服务中）
    [https://technologyconversations.com/2015/08/09/including-front-end-web-components-into-microservices/](https://technologyconversations.com/2015/08/09/including-front-end-web-components-into-microservices/)

-   **Managing Frontend in the Microservices Architecture**\（在微服务体系结构中管理前端）
    [*https://allegro.tech/2016/03/Managing-Frontend-in-the-microservices-architecture.html*](https://allegro.tech/2016/03/Managing-Frontend-in-the-microservices-architecture.html)


>[!div class="step-by-step"]
[上一页](microservices-addressability-service-registry.md)
[下一页](resilient-high-availability-microservices.md)
