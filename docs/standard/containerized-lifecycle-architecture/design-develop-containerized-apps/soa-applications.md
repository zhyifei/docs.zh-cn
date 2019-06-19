---
title: SOA 应用程序
description: 请记住，容器也可以是 SOA 应用程序的有用部署选项。
ms.date: 02/15/2019
ms.openlocfilehash: aa56ada7b14a465fb3dafd02b03b815782ac765b
ms.sourcegitcommit: 5bc85ad81d96b8dc2a90ce53bada475ee5662c44
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/13/2019
ms.locfileid: "65644765"
---
# <a name="service-oriented-applications"></a><span data-ttu-id="9fad5-103">面向服务的应用程序</span><span class="sxs-lookup"><span data-stu-id="9fad5-103">Service-oriented applications</span></span>

<span data-ttu-id="9fad5-104">面向服务的体系结构 (SOA) 是一个使用过度的术语，不同的人对它的理解不尽相同。</span><span class="sxs-lookup"><span data-stu-id="9fad5-104">Service-Oriented Architecture (SOA) was an overused term that meant many different things to different people.</span></span> <span data-ttu-id="9fad5-105">但相同的理解是，SOA 意味着通过将应用程序的体系结构分解为多个服务（通常为 HTTP 服务），将其分为不同类型（例如子系统，或者在其他情况下分类为层），从而来划分应用程序的结构。</span><span class="sxs-lookup"><span data-stu-id="9fad5-105">But as a common denominator, SOA means that you structure the architecture of your application by decomposing it into several services (most commonly as HTTP services) that can be classified in different types like subsystems or, in other cases, as tiers.</span></span>

<span data-ttu-id="9fad5-106">现在，你可以将这些服务部署为 Docker 容器，从而解决与部署相关的问题，因为所有依赖项都包含在容器映像中。</span><span class="sxs-lookup"><span data-stu-id="9fad5-106">Today, you can deploy those services as Docker containers, which solve deployment-related issues because all of the dependencies are included in the container image.</span></span> <span data-ttu-id="9fad5-107">但是，当你需要扩展 SOA 时，如果基于单个实例进行部署，则可能会遇到难题。</span><span class="sxs-lookup"><span data-stu-id="9fad5-107">However, when you need to scale out SOAs, you might encounter challenges if you're deploying based on single instances.</span></span> <span data-ttu-id="9fad5-108">可以使用 Docker 群集软件或业务流程协调程序来处理此难题。</span><span class="sxs-lookup"><span data-stu-id="9fad5-108">This challenge can be handled using Docker clustering software or an orchestrator.</span></span> <span data-ttu-id="9fad5-109">当我们探索微服务方法时，我们将在下一部分中更详细地讨论业务流程协调程序。</span><span class="sxs-lookup"><span data-stu-id="9fad5-109">We'll look at orchestrators in greater detail in the next section, when we explore microservices approaches.</span></span>

<span data-ttu-id="9fad5-110">对于传统的面向服务的体系结构和更高级的微服务体系结构，Docker 容器都是有用的（但不是必需的）。</span><span class="sxs-lookup"><span data-stu-id="9fad5-110">Docker containers are useful (but not required) for both traditional service-oriented architectures and the more advanced microservices architectures.</span></span>

<span data-ttu-id="9fad5-111">归根结底，容器群集解决方案对于传统的 SOA 体系结构和更高级的微服务体系结构都很有用，其中每个微服务都拥有其数据模型。</span><span class="sxs-lookup"><span data-stu-id="9fad5-111">At the end of the day, the container clustering solutions are useful for both a traditional SOA architecture and for a more advanced microservices architecture in which each microservice owns its data model.</span></span> <span data-ttu-id="9fad5-112">由于有多个数据库，还可以扩展数据层，而不必使用 SOA 服务共享的单一数据库。</span><span class="sxs-lookup"><span data-stu-id="9fad5-112">And thanks to multiple databases, you also can scale out the data tier instead of working with monolithic databases shared by the SOA services.</span></span> <span data-ttu-id="9fad5-113">但是，关于拆分数据的讨论纯粹是关于架构和设计。</span><span class="sxs-lookup"><span data-stu-id="9fad5-113">However, the discussion about splitting the data is purely about architecture and design.</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="9fad5-114">[上一页](state-and-data-in-docker-applications.md)
>[下一页](orchestrate-high-scalability-availability.md)</span><span class="sxs-lookup"><span data-stu-id="9fad5-114">[Previous](state-and-data-in-docker-applications.md)
[Next](orchestrate-high-scalability-availability.md)</span></span>
