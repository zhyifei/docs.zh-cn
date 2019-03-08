---
title: SOA 应用程序
description: 请记住容器也可以是 SOA 应用程序的有用的部署选项。
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 02/15/2019
ms.openlocfilehash: ee71873ac15246f979fd2b08d92280ba797ff6ee
ms.sourcegitcommit: 58fc0e6564a37fa1b9b1b140a637e864c4cf696e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/08/2019
ms.locfileid: "57675792"
---
# <a name="service-oriented-applications"></a><span data-ttu-id="12e11-103">面向服务的应用程序</span><span class="sxs-lookup"><span data-stu-id="12e11-103">Service-oriented applications</span></span>

<span data-ttu-id="12e11-104">面向服务的体系结构 (SOA) 是一个使用过度的术语，意味着不同的人很多不同的理解。</span><span class="sxs-lookup"><span data-stu-id="12e11-104">Service-Oriented Architecture (SOA) was an overused term that meant many different things to different people.</span></span> <span data-ttu-id="12e11-105">但相同的理解，SOA 意味着通过分解为可进行分类等子系统的不同类型中，或在其他情况下，作为层的多个服务 （通常为 HTTP 服务） 构建的应用程序体系结构。</span><span class="sxs-lookup"><span data-stu-id="12e11-105">But as a common denominator, SOA means that you structure the architecture of your application by decomposing it into several services (most commonly as HTTP services) that can be classified in different types like subsystems or, in other cases, as tiers.</span></span>

<span data-ttu-id="12e11-106">现在，可以将这些服务部署为 Docker 容器，解决与部署相关的问题，因为容器映像中包含了所有依赖项。</span><span class="sxs-lookup"><span data-stu-id="12e11-106">Today, you can deploy those services as Docker containers, which solve deployment-related issues because all of the dependencies are included in the container image.</span></span> <span data-ttu-id="12e11-107">但是，当您需要向外扩展 Soa，如果要部署基于单个实例可能遇到难题。</span><span class="sxs-lookup"><span data-stu-id="12e11-107">However, when you need to scale out SOAs, you might encounter challenges if you're deploying based on single instances.</span></span> <span data-ttu-id="12e11-108">可以使用 Docker 群集软件或业务流程协调程序处理这一挑战。</span><span class="sxs-lookup"><span data-stu-id="12e11-108">This challenge can be handled using Docker clustering software or an orchestrator.</span></span> <span data-ttu-id="12e11-109">我们将探讨微服务方法时，我们来看看下一节中更详细地业务流程协调程序。</span><span class="sxs-lookup"><span data-stu-id="12e11-109">We'll look at orchestrators in greater detail in the next section, when we explore microservices approaches.</span></span>

<span data-ttu-id="12e11-110">对于传统的面向服务的体系结构和更高级的微服务体系结构，Docker 容器都是有用的（但不是必需的）。</span><span class="sxs-lookup"><span data-stu-id="12e11-110">Docker containers are useful (but not required) for both traditional service-oriented architectures and the more advanced microservices architectures.</span></span>

<span data-ttu-id="12e11-111">在一天结束时，容器聚类分析解决方案是适用于这两种传统 SOA 的体系结构以及在其中每个微服务拥有它的数据模型的更高级的微服务体系结构。</span><span class="sxs-lookup"><span data-stu-id="12e11-111">At the end of the day, the container clustering solutions are useful for both a traditional SOA architecture and for a more advanced microservices architecture in which each microservice owns its data model.</span></span> <span data-ttu-id="12e11-112">和得益于多个数据库，您还可以向外扩展而不是使用共享的 SOA 服务的整体式数据库的数据层。</span><span class="sxs-lookup"><span data-stu-id="12e11-112">And thanks to multiple databases, you also can scale out the data tier instead of working with monolithic databases shared by the SOA services.</span></span> <span data-ttu-id="12e11-113">但是，有关将数据拆分的讨论是纯粹有关体系结构和设计。</span><span class="sxs-lookup"><span data-stu-id="12e11-113">However, the discussion about splitting the data is purely about architecture and design.</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="12e11-114">[上一页](state-and-data-in-docker-applications.md)
>[下一页](orchestrate-high-scalability-availability.md)</span><span class="sxs-lookup"><span data-stu-id="12e11-114">[Previous](state-and-data-in-docker-applications.md)
[Next](orchestrate-high-scalability-availability.md)</span></span>
