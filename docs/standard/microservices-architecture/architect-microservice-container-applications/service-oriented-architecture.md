---
title: 面向服务的体系结构
description: 了解微服务与面向服务的体系结构 (SOA) 之间的根本区别。
ms.date: 09/20/2018
ms.openlocfilehash: 84786539fbac0e8b38a81a2580232474774cd355
ms.sourcegitcommit: 8699383914c24a0df033393f55db3369db728a7b
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/15/2019
ms.locfileid: "65640056"
---
# <a name="service-oriented-architecture"></a><span data-ttu-id="b2485-103">面向服务的体系结构</span><span class="sxs-lookup"><span data-stu-id="b2485-103">Service-oriented architecture</span></span>

<span data-ttu-id="b2485-104">面向服务的体系结构 (SOA) 是一个使用过度的术语，不同的人对它的理解不尽相同。</span><span class="sxs-lookup"><span data-stu-id="b2485-104">Service-oriented architecture (SOA) was an overused term and has meant different things to different people.</span></span> <span data-ttu-id="b2485-105">但相同的理解是，SOA 意味着通过将应用程序分解为多个服务（通常为 HTTP 服务），将其分为不同类型（例如子系统或层），从而来划分应用程序的结构。</span><span class="sxs-lookup"><span data-stu-id="b2485-105">But as a common denominator, SOA means that you structure your application by decomposing it into multiple services (most commonly as HTTP services) that can be classified as different types like subsystems or tiers.</span></span>

<span data-ttu-id="b2485-106">这些服务现可部署为 Docker 容器，这可解决部署问题，因为容器映像中包含所有依赖关系。</span><span class="sxs-lookup"><span data-stu-id="b2485-106">Those services can now be deployed as Docker containers, which solves deployment issues, because all the dependencies are included in the container image.</span></span> <span data-ttu-id="b2485-107">但是，当需要纵向扩展 SOA 应用程序时，如果基于单个 Docker 主机进行部署，可能面临可伸缩性和可用性挑战。</span><span class="sxs-lookup"><span data-stu-id="b2485-107">However, when you need to scale up SOA applications, you might have scalability and availability challenges if you're deploying based on single Docker hosts.</span></span> <span data-ttu-id="b2485-108">在这种情况下，Docker 群集软件或业务流程协调程序可能会对你有所帮助，我们稍后将在介绍微服务部署方法的部分中进行说明。</span><span class="sxs-lookup"><span data-stu-id="b2485-108">This is where Docker clustering software or an orchestrator can help you, as explained in later sections where deployment approaches for microservices are described.</span></span>

<span data-ttu-id="b2485-109">对于传统的面向服务的体系结构和更高级的微服务体系结构，Docker 容器都是有用的（但不是必需的）。</span><span class="sxs-lookup"><span data-stu-id="b2485-109">Docker containers are useful (but not required) for both traditional service-oriented architectures and the more advanced microservices architectures.</span></span>

<span data-ttu-id="b2485-110">微服务源自 SOA，但 SOA 不同于微服务体系结构。</span><span class="sxs-lookup"><span data-stu-id="b2485-110">Microservices derive from SOA, but SOA is different from microservices architecture.</span></span> <span data-ttu-id="b2485-111">诸如大型中央代理、组织级别的中央业务流程协调程序和[企业服务总线 (ESB)](https://en.wikipedia.org/wiki/Enterprise_service_bus) 等功能在 SOA 中很典型。</span><span class="sxs-lookup"><span data-stu-id="b2485-111">Features like large central brokers, central orchestrators at the organization level, and the [Enterprise Service Bus (ESB)](https://en.wikipedia.org/wiki/Enterprise_service_bus) are typical in SOA.</span></span> <span data-ttu-id="b2485-112">但在大多数情况下，这些是微服务社区中的反模式。</span><span class="sxs-lookup"><span data-stu-id="b2485-112">But in most cases, these are anti-patterns in the microservice community.</span></span> <span data-ttu-id="b2485-113">事实上，有些人认为“微服务体系结构是处理得当的 SOA”。</span><span class="sxs-lookup"><span data-stu-id="b2485-113">In fact, some people argue that "The microservice architecture is SOA done right."</span></span>

<span data-ttu-id="b2485-114">本指南关注微服务，因为相较于微服务体系结构中的要求和技术，SOA 方法不那么受普遍认可。</span><span class="sxs-lookup"><span data-stu-id="b2485-114">This guide focuses on microservices, because a SOA approach is less prescriptive than the requirements and techniques used in a microservice architecture.</span></span> <span data-ttu-id="b2485-115">如果知道如何生成基于微服务的应用程序，还会了解如何构建更简单的面向服务的应用程序。</span><span class="sxs-lookup"><span data-stu-id="b2485-115">If you know how to build a microservice-based application, you also know how to build a simpler service-oriented application.</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="b2485-116">[上一页](docker-application-state-data.md)
>[下一页](microservices-architecture.md)</span><span class="sxs-lookup"><span data-stu-id="b2485-116">[Previous](docker-application-state-data.md)
[Next](microservices-architecture.md)</span></span>
