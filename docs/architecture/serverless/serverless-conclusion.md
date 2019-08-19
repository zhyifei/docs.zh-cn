---
title: 要点-无服务器应用
description: 无服务器可提供许多好处, 并有其自身的挑战。 本指南概述了重要的要点。
author: JEREMYLIKNESS
ms.author: jeliknes
ms.date: 06/26/2018
ms.openlocfilehash: ae9fc47bf07a7e28688942b856b4743ae7aadc36
ms.sourcegitcommit: f20dd18dbcf2275513281f5d9ad7ece6a62644b4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/30/2019
ms.locfileid: "69577240"
---
# <a name="conclusion"></a><span data-ttu-id="b3573-104">结束语</span><span class="sxs-lookup"><span data-stu-id="b3573-104">Conclusion</span></span>

<span data-ttu-id="b3573-105">以下关键的结论是本指南最重要的结论。</span><span class="sxs-lookup"><span data-stu-id="b3573-105">The following key takeaways are the most important conclusions from this guide.</span></span>

<span data-ttu-id="b3573-106">**使用无服务器的好处。**</span><span class="sxs-lookup"><span data-stu-id="b3573-106">**Benefits of using serverless.**</span></span> <span data-ttu-id="b3573-107">无服务器解决方案提供了节约成本的重要优势, 因为无服务器是按使用付费模式实现的。</span><span class="sxs-lookup"><span data-stu-id="b3573-107">Serverless solutions provide the important benefit of cost savings because serverless is implemented in a pay-per-use model.</span></span> <span data-ttu-id="b3573-108">无服务器可独立缩放、测试和部署应用程序的各个组件。</span><span class="sxs-lookup"><span data-stu-id="b3573-108">Serverless makes it possible to independently scale, test, and deploy individual components of your application.</span></span> <span data-ttu-id="b3573-109">无服务器唯一适合于实现微服务体系结构并完全集成到 DevOps 管道。</span><span class="sxs-lookup"><span data-stu-id="b3573-109">Serverless is uniquely suited to implement microservices architectures and integrates fully into a DevOps pipeline.</span></span>

<span data-ttu-id="b3573-110">**作为部署单元的代码。**</span><span class="sxs-lookup"><span data-stu-id="b3573-110">**Code as a unit of deployment.**</span></span> <span data-ttu-id="b3573-111">无服务器将硬件、操作系统和运行时从应用程序中提取出来。</span><span class="sxs-lookup"><span data-stu-id="b3573-111">Serverless abstracts the hardware, OS, and runtime away from the application.</span></span> <span data-ttu-id="b3573-112">无服务器支持在代码中将业务逻辑专注于部署单元。</span><span class="sxs-lookup"><span data-stu-id="b3573-112">Serverless enables focusing on business logic in code as the unit of deployment.</span></span>

<span data-ttu-id="b3573-113">**触发器和绑定。**</span><span class="sxs-lookup"><span data-stu-id="b3573-113">**Triggers and bindings.**</span></span> <span data-ttu-id="b3573-114">无服务器简化与存储、Api 和其他云资源的集成。</span><span class="sxs-lookup"><span data-stu-id="b3573-114">Serverless eases integration with storage, APIs, and other cloud resources.</span></span> <span data-ttu-id="b3573-115">Azure Functions 提供触发器来执行代码和绑定以与资源进行交互。</span><span class="sxs-lookup"><span data-stu-id="b3573-115">Azure Functions provides triggers to execute code and bindings to interact with resources.</span></span>

<span data-ttu-id="b3573-116">**微服务。**</span><span class="sxs-lookup"><span data-stu-id="b3573-116">**Microservices.**</span></span> <span data-ttu-id="b3573-117">微服务体系结构正在成为分布式和大型或复杂的任务关键型应用程序的首选方法, 这些应用程序基于多个独立子系统的自治服务形式。</span><span class="sxs-lookup"><span data-stu-id="b3573-117">The microservices architecture is becoming the preferred approach for distributed and large or complex mission-critical applications that are based on multiple independent subsystems in the form of autonomous services.</span></span> <span data-ttu-id="b3573-118">在基于微服务的体系结构中, 应用程序构建为可单独开发、测试、版本控制、部署和缩放的服务集合。</span><span class="sxs-lookup"><span data-stu-id="b3573-118">In a microservice-based architecture, the application is built as a collection of services that can be developed, tested, versioned, deployed, and scaled independently.</span></span> <span data-ttu-id="b3573-119">无服务器是一种非常适合用于构建这些服务的体系结构。</span><span class="sxs-lookup"><span data-stu-id="b3573-119">Serverless is an architecture well-suited for building these services.</span></span>

<span data-ttu-id="b3573-120">**无服务器平台。**</span><span class="sxs-lookup"><span data-stu-id="b3573-120">**Serverless platforms.**</span></span> <span data-ttu-id="b3573-121">无服务器不只是关于代码。</span><span class="sxs-lookup"><span data-stu-id="b3573-121">Serverless isn't just about the code.</span></span> <span data-ttu-id="b3573-122">支持无服务器体系结构的平台包括无服务器工作流和业务流程、无服务器消息传递和事件服务以及无服务器数据库。</span><span class="sxs-lookup"><span data-stu-id="b3573-122">Platforms that support serverless architectures include serverless workflows and orchestration, serverless messaging and event services, and serverless databases.</span></span>

<span data-ttu-id="b3573-123">**无服务器挑战。**</span><span class="sxs-lookup"><span data-stu-id="b3573-123">**Serverless challenges.**</span></span> <span data-ttu-id="b3573-124">无服务器服务带来了与分布式应用程序开发相关的难题, 例如, 分段和独立的数据模型、复原、版本控制和服务发现。</span><span class="sxs-lookup"><span data-stu-id="b3573-124">Serverless introduces challenges related to distributed application development, such as fragmented and independent data models, resiliency, versioning, and service discovery.</span></span> <span data-ttu-id="b3573-125">无服务器的理想情况可能不适合长时间运行的进程或可受益于更紧密耦合的组件。</span><span class="sxs-lookup"><span data-stu-id="b3573-125">Serverless may not be ideally suited to long running processes or components that benefit from tighter coupling.</span></span>

<span data-ttu-id="b3573-126">**无服务器作为工具, 而不是工具箱。**</span><span class="sxs-lookup"><span data-stu-id="b3573-126">**Serverless as a tool, not the toolbox.**</span></span> <span data-ttu-id="b3573-127">无服务器不是应用程序体系结构的独有解决方案。</span><span class="sxs-lookup"><span data-stu-id="b3573-127">Serverless is not the exclusive solution to application architecture.</span></span> <span data-ttu-id="b3573-128">它是一种可作为混合应用程序的一部分使用的工具, 其中可能包含传统层、单体架构后端和容器。</span><span class="sxs-lookup"><span data-stu-id="b3573-128">It is a tool that can be leveraged as part of a hybrid application that may contain traditional tiers, monolith back ends, and containers.</span></span> <span data-ttu-id="b3573-129">无服务器可用于增强现有解决方案, 而不是应用程序开发的全部或无方法。</span><span class="sxs-lookup"><span data-stu-id="b3573-129">Serverless can be used to enhance existing solutions and is not an all-or-nothing approach to application development.</span></span>

>[!div class="step-by-step"]
>[<span data-ttu-id="b3573-130">上一篇</span><span class="sxs-lookup"><span data-stu-id="b3573-130">Previous</span></span>](serverless-business-scenarios.md)
