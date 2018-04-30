---
title: SOA 应用程序
description: 使用 Microsoft 平台和工具的容器化 Docker 应用程序的生命周期
ms.prod: .net
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 09/22/2017
ms.topic: article
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: 5f60ff2fb1567d08b9e51e14ce5660a8e42f54aa
ms.sourcegitcommit: 2e8acae16ae802f2d6d04e3ce0a6dbf04e476513
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/18/2018
---
# <a name="soa-applications"></a><span data-ttu-id="28682-103">SOA 应用程序</span><span class="sxs-lookup"><span data-stu-id="28682-103">SOA applications</span></span>

<span data-ttu-id="28682-104">SOA 是的使用过度的术语，意味着要对不同的人是许多不同的事物。</span><span class="sxs-lookup"><span data-stu-id="28682-104">SOA was an overused term and meant so many different things to different people.</span></span> <span data-ttu-id="28682-105">但该你结构的您的应用程序将它分解可以分为不同类型的多个服务 （通常作为 HTTP 服务） 中的体系结构最少和作为公分、 SOA，或面向服务、 平均值如子系统或者，在其他情况下，为层。</span><span class="sxs-lookup"><span data-stu-id="28682-105">But at a minimum and as a common denominator, SOA, or service orientation, mean that you structure the architecture of your application by decomposing it in multiple services (most commonly as HTTP services) that can be classified in different types like subsystems or, in other cases, as tiers.</span></span>

<span data-ttu-id="28682-106">现在，你可以为 Docker 容器，这可解决与部署相关的问题，因为所有依赖项是包含在容器映像部署这些服务。</span><span class="sxs-lookup"><span data-stu-id="28682-106">Today, you can deploy those services as Docker containers, which solves deployment-related issues because all of the dependencies are included within the container image.</span></span> <span data-ttu-id="28682-107">但是，当你需要进行横向扩展 SOAs，则可能遇到挑战，如果你要部署基于单个实例。</span><span class="sxs-lookup"><span data-stu-id="28682-107">However, when you need to scale-out SOAs, you might encounter challenges if you are deploying based on single instances.</span></span> <span data-ttu-id="28682-108">这是群集软件或 orchestrator 的 Docker 将帮助你。</span><span class="sxs-lookup"><span data-stu-id="28682-108">This is where a Docker clustering software or orchestrator will help you.</span></span> <span data-ttu-id="28682-109">当我们检查微服务方法，我们将在此查看更详细地下一节介绍。</span><span class="sxs-lookup"><span data-stu-id="28682-109">We'll look at this in greater detail in the next section when we examine microservices approaches.</span></span>

<span data-ttu-id="28682-110">在一天结束时，容器聚类分析解决方案可为这两种传统 SOA 的体系结构或在其中每个微服务拥有其数据模型的更高级的微服务体系结构。</span><span class="sxs-lookup"><span data-stu-id="28682-110">At the end of the day, the container clustering solutions are useful for both a traditional SOA architecture or for a more advanced microservices architecture in which each microservice owns its data model.</span></span> <span data-ttu-id="28682-111">和，得益于多个数据库，你还可以向外扩展而不是使用由 SOA 服务共享的单一数据库的数据层。</span><span class="sxs-lookup"><span data-stu-id="28682-111">And, thanks to multiple databases, you also can scale-out the data tier instead of working with monolithic databases shared by the SOA services.</span></span> <span data-ttu-id="28682-112">但是，有关将数据拆分讨论是纯粹有关体系结构和设计。</span><span class="sxs-lookup"><span data-stu-id="28682-112">However, the discussion about splitting the data is purely about architecture and design.</span></span>


>[!div class="step-by-step"]
<span data-ttu-id="28682-113">[以前](state-and-data-in-docker-applications.md) [下一步] (安排-高的可伸缩性-availability.md)</span><span class="sxs-lookup"><span data-stu-id="28682-113">[Previous] (state-and-data-in-docker-applications.md) [Next] (orchestrate-high-scalability-availability.md)</span></span>
