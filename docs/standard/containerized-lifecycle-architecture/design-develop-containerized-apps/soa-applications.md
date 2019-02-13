---
title: SOA 应用程序
description: 请记住容器也可以是 SOA 应用程序的有用的部署选项。
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 11/23/2018
ms.openlocfilehash: 4fd39e075c5730cf7fddb0138cdb5267a914c91f
ms.sourcegitcommit: 30e2fe5cc4165aa6dde7218ec80a13def3255e98
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/13/2019
ms.locfileid: "56221259"
---
# <a name="soa-applications"></a><span data-ttu-id="613cf-103">SOA 应用程序</span><span class="sxs-lookup"><span data-stu-id="613cf-103">SOA applications</span></span>

<span data-ttu-id="613cf-104">SOA 是一个使用过度的术语，意味着不同的人这么多不同的理解。</span><span class="sxs-lookup"><span data-stu-id="613cf-104">SOA was an overused term and meant so many different things to different people.</span></span> <span data-ttu-id="613cf-105">但至少和通用标准，SOA，或服务导向，平均值作为该您结构通过将它分解 （通常为 HTTP 服务） 可以分为不同类型的多个服务中的应用程序的体系结构，如子系统或者，在其他情况下，作为层。</span><span class="sxs-lookup"><span data-stu-id="613cf-105">But at a minimum and as a common denominator, SOA, or service orientation, mean that you structure the architecture of your application by decomposing it in multiple services (most commonly as HTTP services) that can be classified in different types like subsystems or, in other cases, as tiers.</span></span>

<span data-ttu-id="613cf-106">现在，你可以为 Docker 容器，这可解决与部署相关的问题，因为所有依赖项都将包含在容器映像部署这些服务。</span><span class="sxs-lookup"><span data-stu-id="613cf-106">Today, you can deploy those services as Docker containers, which solves deployment-related issues because all of the dependencies are included within the container image.</span></span> <span data-ttu-id="613cf-107">但是，当您需要进行横向扩展 Soa，如果要部署基于单个实例可能会遇到难题。</span><span class="sxs-lookup"><span data-stu-id="613cf-107">However, when you need to scale-out SOAs, you might encounter challenges if you are deploying based on single instances.</span></span> <span data-ttu-id="613cf-108">这是 Docker 群集软件或业务流程协调程序将帮助你。</span><span class="sxs-lookup"><span data-stu-id="613cf-108">This is where a Docker clustering software or orchestrator will help you.</span></span> <span data-ttu-id="613cf-109">我们将介绍这在下一节中更详细地探讨如何使用微服务方法时。</span><span class="sxs-lookup"><span data-stu-id="613cf-109">We'll look at this in greater detail in the next section when we examine microservices approaches.</span></span>

<span data-ttu-id="613cf-110">在一天结束时，容器聚类分析解决方案可用于这两种传统 SOA 体系结构或在其中每个微服务拥有它的数据模型的更高级的微服务体系结构。</span><span class="sxs-lookup"><span data-stu-id="613cf-110">At the end of the day, the container clustering solutions are useful for both a traditional SOA architecture or for a more advanced microservices architecture in which each microservice owns its data model.</span></span> <span data-ttu-id="613cf-111">并且，由于多个数据库，您还可以向外缩放而不是使用共享的 SOA 服务的整体式数据库的数据层。</span><span class="sxs-lookup"><span data-stu-id="613cf-111">And, thanks to multiple databases, you also can scale-out the data tier instead of working with monolithic databases shared by the SOA services.</span></span> <span data-ttu-id="613cf-112">但是，有关将数据拆分的讨论是纯粹有关体系结构和设计。</span><span class="sxs-lookup"><span data-stu-id="613cf-112">However, the discussion about splitting the data is purely about architecture and design.</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="613cf-113">[上一页](state-and-data-in-docker-applications.md)
>[下一页](orchestrate-high-scalability-availability.md)</span><span class="sxs-lookup"><span data-stu-id="613cf-113">[Previous](state-and-data-in-docker-applications.md)
[Next](orchestrate-high-scalability-availability.md)</span></span>