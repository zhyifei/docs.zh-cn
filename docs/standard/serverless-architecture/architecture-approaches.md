---
title: 体系结构方法的无服务器应用
description: 用于构建基于云的企业应用程序，从到无服务器的 N 层体系结构方法体系结构的简介。
author: JEREMYLIKNESS
ms.author: jeliknes
ms.date: 06/26/2018
ms.openlocfilehash: 04ad383586f974bb2dccc4623a9a254f5668dab4
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "61640175"
---
# <a name="architecture-approaches"></a><span data-ttu-id="692be-103">体系结构方法</span><span class="sxs-lookup"><span data-stu-id="692be-103">Architecture approaches</span></span>

<span data-ttu-id="692be-104">了解构建企业应用的现有方法可帮助阐明通过无服务器扮演的角色。</span><span class="sxs-lookup"><span data-stu-id="692be-104">Understanding existing approaches to architecting enterprise apps helps clarify the role played by serverless.</span></span> <span data-ttu-id="692be-105">有许多方法和数十年的软件开发中不断演变的模式，都具有其自己的优点和缺点。</span><span class="sxs-lookup"><span data-stu-id="692be-105">There are many approaches and patterns that evolved over decades of software development, and all have their own pros and cons.</span></span> <span data-ttu-id="692be-106">在许多情况下，最终的解决方案可能涉及确定一种方法，但可能集成多种不同的方法。</span><span class="sxs-lookup"><span data-stu-id="692be-106">In many cases, the ultimate solution may not involve deciding on a single approach but may integrate several approaches.</span></span> <span data-ttu-id="692be-107">迁移方案通常涉及到从一个体系结构方法切换到另一个通过一种混合方法。</span><span class="sxs-lookup"><span data-stu-id="692be-107">Migration scenarios often involve shifting from one architecture approach to another through a hybrid approach.</span></span>

<span data-ttu-id="692be-108">本章概述了为企业应用程序的这两个逻辑和物理体系结构模式。</span><span class="sxs-lookup"><span data-stu-id="692be-108">This chapter provides an overview of both logical and physical architecture patterns for enterprise applications.</span></span>

## <a name="architecture-patterns"></a><span data-ttu-id="692be-109">体系结构模式</span><span class="sxs-lookup"><span data-stu-id="692be-109">Architecture patterns</span></span>

<span data-ttu-id="692be-110">现代业务应用程序遵循多种体系结构模式。</span><span class="sxs-lookup"><span data-stu-id="692be-110">Modern business applications follow a variety of architecture patterns.</span></span> <span data-ttu-id="692be-111">本部分表示的常见模式的调查。</span><span class="sxs-lookup"><span data-stu-id="692be-111">This section represents a survey of common patterns.</span></span> <span data-ttu-id="692be-112">此处列出的模式并不一定所有最佳实践，但说明了不同的方法。</span><span class="sxs-lookup"><span data-stu-id="692be-112">The patterns listed here aren't necessarily all best practices, but illustrate different approaches.</span></span>

<span data-ttu-id="692be-113">有关详细信息，请参阅[Azure 应用程序体系结构指南](https://docs.microsoft.com/azure/architecture/guide/)。</span><span class="sxs-lookup"><span data-stu-id="692be-113">For more information, see [Azure application architecture guide](https://docs.microsoft.com/azure/architecture/guide/).</span></span>

## <a name="monoliths"></a><span data-ttu-id="692be-114">庞大的单体结构</span><span class="sxs-lookup"><span data-stu-id="692be-114">Monoliths</span></span>

<span data-ttu-id="692be-115">许多业务应用程序遵循单体架构模式。</span><span class="sxs-lookup"><span data-stu-id="692be-115">Many business applications follow a monolith pattern.</span></span> <span data-ttu-id="692be-116">旧版应用程序通常实现为庞大的单体结构。</span><span class="sxs-lookup"><span data-stu-id="692be-116">Legacy applications are often implemented as monoliths.</span></span> <span data-ttu-id="692be-117">在整体应用程序模式中，单个部署中包含所有应用程序问题。</span><span class="sxs-lookup"><span data-stu-id="692be-117">In the monolith pattern, all application concerns are contained in a single deployment.</span></span> <span data-ttu-id="692be-118">从用户界面到数据库调用的一切尽在相同的基本代码。</span><span class="sxs-lookup"><span data-stu-id="692be-118">Everything from user interface to database calls is included in the same codebase.</span></span>

![整体应用程序体系结构](./media/monolith-architecture.png)

<span data-ttu-id="692be-120">有几个优势的单体架构方法。</span><span class="sxs-lookup"><span data-stu-id="692be-120">There are several advantages to the monolith approach.</span></span> <span data-ttu-id="692be-121">通常很容易提取单个代码库，并开始处理。</span><span class="sxs-lookup"><span data-stu-id="692be-121">It's often easy to pull down a single code base and start working.</span></span> <span data-ttu-id="692be-122">加速时间可能会更少，并创建测试环境非常简单，提供的新副本。</span><span class="sxs-lookup"><span data-stu-id="692be-122">Ramp up time may be less, and creating test environments is as simple as providing a new copy.</span></span> <span data-ttu-id="692be-123">单体结构可能会设计为包括多个组件和应用程序。</span><span class="sxs-lookup"><span data-stu-id="692be-123">The monolith may be designed to include multiple components and applications.</span></span>

<span data-ttu-id="692be-124">遗憾的是，整体应用程序模式通常会分解在规模较大。</span><span class="sxs-lookup"><span data-stu-id="692be-124">Unfortunately, the monolith pattern tends to break down at scale.</span></span> <span data-ttu-id="692be-125">单体架构方法的主要缺点包括：</span><span class="sxs-lookup"><span data-stu-id="692be-125">Major disadvantages of the monolith approach include:</span></span>

* <span data-ttu-id="692be-126">很难在相同的基本代码中的并行工作。</span><span class="sxs-lookup"><span data-stu-id="692be-126">Difficult to work in parallel in the same code base.</span></span>
* <span data-ttu-id="692be-127">任何更改，哪怕微不足道，都要求部署整个应用程序的新版本。</span><span class="sxs-lookup"><span data-stu-id="692be-127">Any change, no matter how trivial, requires deploying a new version of the entire application.</span></span>
* <span data-ttu-id="692be-128">重构可能会影响整个应用程序。</span><span class="sxs-lookup"><span data-stu-id="692be-128">Refactoring potentially impacts the entire application.</span></span>
* <span data-ttu-id="692be-129">唯一的解决方案，缩放通常是创建多个占用大量资源的副本的单体结构。</span><span class="sxs-lookup"><span data-stu-id="692be-129">Often the only solution to scale is to create multiple, resource-intensive copies of the monolith.</span></span>
* <span data-ttu-id="692be-130">当系统展开或获取其他系统时，集成可能很困难。</span><span class="sxs-lookup"><span data-stu-id="692be-130">As systems expand or other systems are acquired, integration can be difficult.</span></span>
* <span data-ttu-id="692be-131">它可能很难测试由于需要在要配置整个单体架构。</span><span class="sxs-lookup"><span data-stu-id="692be-131">It may be difficult to test due to the need to configure the entire monolith.</span></span>
* <span data-ttu-id="692be-132">代码重用具有挑战性，其他应用程序最终通常具有其自己的代码的副本。</span><span class="sxs-lookup"><span data-stu-id="692be-132">Code reuse is challenging and often other apps end up having their own copies of code.</span></span>

<span data-ttu-id="692be-133">许多企业到云环境查找的机会来将整体应用程序应用程序迁移和在同一时间对其进行重构为更多可用的模式。</span><span class="sxs-lookup"><span data-stu-id="692be-133">Many businesses look to the cloud as an opportunity to migrate monolith applications and at the same time refactor them to more usable patterns.</span></span> <span data-ttu-id="692be-134">很常见，用于显示单个应用程序和组件，让他们可以维护、 部署，以及单独缩放。</span><span class="sxs-lookup"><span data-stu-id="692be-134">It's common to break out the individual applications and components to allow them to be maintained, deployed, and scaled separately.</span></span>

## <a name="n-layer-applications"></a><span data-ttu-id="692be-135">N 层应用程序</span><span class="sxs-lookup"><span data-stu-id="692be-135">N-Layer applications</span></span>

<span data-ttu-id="692be-136">N 层应用程序分区到特定层的应用程序逻辑。</span><span class="sxs-lookup"><span data-stu-id="692be-136">N-layer application partition application logic into specific layers.</span></span> <span data-ttu-id="692be-137">最常见的层包括：</span><span class="sxs-lookup"><span data-stu-id="692be-137">The most common layers include:</span></span>

* <span data-ttu-id="692be-138">用户界面</span><span class="sxs-lookup"><span data-stu-id="692be-138">User interface</span></span>
* <span data-ttu-id="692be-139">业务逻辑</span><span class="sxs-lookup"><span data-stu-id="692be-139">Business logic</span></span>
* <span data-ttu-id="692be-140">数据访问</span><span class="sxs-lookup"><span data-stu-id="692be-140">Data access</span></span>

<span data-ttu-id="692be-141">其他层可能包括中间件、 批处理和 API。</span><span class="sxs-lookup"><span data-stu-id="692be-141">Other layers may include middleware, batch processing, and API.</span></span> <span data-ttu-id="692be-142">请务必注意这些层分为逻辑。</span><span class="sxs-lookup"><span data-stu-id="692be-142">It's important to note the layers are logical.</span></span> <span data-ttu-id="692be-143">尽管他们正在开发中隔离，但它们可能全部部署到相同的目标平台。</span><span class="sxs-lookup"><span data-stu-id="692be-143">Although they're developed in isolation, they may all be deployed to the same target platform.</span></span>

![N 层体系结构](./media/n-layer-architecture.png)

<span data-ttu-id="692be-145">有几个优势的 N 层方法，包括：</span><span class="sxs-lookup"><span data-stu-id="692be-145">There are several advantages to the N-Layer approach, including:</span></span>

* <span data-ttu-id="692be-146">重构是隔离到一个层。</span><span class="sxs-lookup"><span data-stu-id="692be-146">Refactoring is isolated to a layer.</span></span>
* <span data-ttu-id="692be-147">团队可以独立地构建、 测试、 部署和维护不同的层。</span><span class="sxs-lookup"><span data-stu-id="692be-147">Teams can independently build, test, deploy, and maintain separate layers.</span></span>
* <span data-ttu-id="692be-148">层可以换出，例如数据层可能会访问多个数据库，而无需更改 UI 层。</span><span class="sxs-lookup"><span data-stu-id="692be-148">Layers can be swapped out, for example the data layer may access multiple databases without requiring changes to the UI layer.</span></span>

<span data-ttu-id="692be-149">无服务器可能用于实现一个或多个层。</span><span class="sxs-lookup"><span data-stu-id="692be-149">Serverless may be used to implement one or more layers.</span></span>

## <a name="microservices"></a><span data-ttu-id="692be-150">微服务</span><span class="sxs-lookup"><span data-stu-id="692be-150">Microservices</span></span>

<span data-ttu-id="692be-151">**[微服务](https://docs.microsoft.com/azure/architecture/guide/architecture-styles/microservices)** 体系结构包含包括的共同特征：</span><span class="sxs-lookup"><span data-stu-id="692be-151">**[Microservices](https://docs.microsoft.com/azure/architecture/guide/architecture-styles/microservices)** architectures contain common characteristics that include:</span></span>

* <span data-ttu-id="692be-152">应用程序由多个小型服务组成。</span><span class="sxs-lookup"><span data-stu-id="692be-152">Applications are composed of several small services.</span></span>
* <span data-ttu-id="692be-153">每个服务在其自己的进程中运行。</span><span class="sxs-lookup"><span data-stu-id="692be-153">Each service runs in its own process.</span></span>
* <span data-ttu-id="692be-154">服务对齐围绕业务域。</span><span class="sxs-lookup"><span data-stu-id="692be-154">Services are aligned around business domains.</span></span>
* <span data-ttu-id="692be-155">服务通过轻量 Api，通常使用 HTTP 作为传输协议进行通信。</span><span class="sxs-lookup"><span data-stu-id="692be-155">Services communicate over lightweight APIs, typically using HTTP as the transport.</span></span>
* <span data-ttu-id="692be-156">服务可以部署和独立升级。</span><span class="sxs-lookup"><span data-stu-id="692be-156">Services can be deployed and upgraded independently.</span></span>
* <span data-ttu-id="692be-157">服务并不是依赖于单个数据存储区。</span><span class="sxs-lookup"><span data-stu-id="692be-157">Services aren't dependent on a single data store.</span></span>
* <span data-ttu-id="692be-158">系统设计与失败的需求，并甚至某些服务失败时，可能仍会运行该应用程序。</span><span class="sxs-lookup"><span data-stu-id="692be-158">The system is designed with failure in mind, and the app may still run even when certain services fail.</span></span>

<span data-ttu-id="692be-159">微服务不一定要与其他体系结构方式互相排斥。</span><span class="sxs-lookup"><span data-stu-id="692be-159">Microservices don't have to be mutually exclusive to other architecture approaches.</span></span> <span data-ttu-id="692be-160">例如，N 层体系结构可能会为中间层使用微服务。</span><span class="sxs-lookup"><span data-stu-id="692be-160">For example, an N-Tier architecture may use microservices for the middle tier.</span></span> <span data-ttu-id="692be-161">还有可能要在有许多种情况下，从 IIS 到容器主机上的虚拟目录中实现微服务。</span><span class="sxs-lookup"><span data-stu-id="692be-161">It's also possible to implement microservices in a variety of ways, from virtual directories on IIS hosts to containers.</span></span> <span data-ttu-id="692be-162">微服务的特征，使它们尤其适合无服务器实现。</span><span class="sxs-lookup"><span data-stu-id="692be-162">The characteristics of microservices make them especially ideal for serverless implementations.</span></span>

![微服务体系结构](./media/microservices-architecture.png)

<span data-ttu-id="692be-164">微服务体系结构的优点包括：</span><span class="sxs-lookup"><span data-stu-id="692be-164">The pros of microservices architectures include:</span></span>

* <span data-ttu-id="692be-165">重构是通常独立于单个服务。</span><span class="sxs-lookup"><span data-stu-id="692be-165">Refactoring is often isolated to a single service.</span></span>
* <span data-ttu-id="692be-166">服务可以互相独立地进行升级。</span><span class="sxs-lookup"><span data-stu-id="692be-166">Services can be upgraded independently of each other.</span></span>
* <span data-ttu-id="692be-167">可以为单独的服务的需求优化复原能力和灵活性。</span><span class="sxs-lookup"><span data-stu-id="692be-167">Resiliency and elasticity can be tuned to the demands of individual services.</span></span>
* <span data-ttu-id="692be-168">开发可以并行发生跨不同的团队和平台。</span><span class="sxs-lookup"><span data-stu-id="692be-168">Development can happen in parallel across disparate teams and platforms.</span></span>
* <span data-ttu-id="692be-169">它是更轻松地编写的独立服务的全面测试。</span><span class="sxs-lookup"><span data-stu-id="692be-169">It's easier to write comprehensive tests for isolated services.</span></span>

<span data-ttu-id="692be-170">微服务有其特有的挑战，包括：</span><span class="sxs-lookup"><span data-stu-id="692be-170">Microservices come with their own challenges, including:</span></span>

* <span data-ttu-id="692be-171">确定哪些服务以及如何对其进行调用。</span><span class="sxs-lookup"><span data-stu-id="692be-171">Determining what services are available and how to call them.</span></span>
* <span data-ttu-id="692be-172">管理服务的生命周期。</span><span class="sxs-lookup"><span data-stu-id="692be-172">Managing the lifecycle of services.</span></span>
* <span data-ttu-id="692be-173">了解如何服务组合在一起在整个应用程序中。</span><span class="sxs-lookup"><span data-stu-id="692be-173">Understanding how services fit together in the overall application.</span></span>
* <span data-ttu-id="692be-174">完整的系统调用跨不同服务所做的测试。</span><span class="sxs-lookup"><span data-stu-id="692be-174">Full system testing of calls made across disparate services.</span></span>

<span data-ttu-id="692be-175">最终有的解决方案来满足所有这些挑战，包括利用讨论了更高版本的无服务器的优势。</span><span class="sxs-lookup"><span data-stu-id="692be-175">Ultimately there are solutions to address all of these challenges, including tapping into the benefits of serverless that are discussed later.</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="692be-176">[上一页](index.md)
>[下一页](architecture-deployment-approaches.md)</span><span class="sxs-lookup"><span data-stu-id="692be-176">[Previous](index.md)
[Next](architecture-deployment-approaches.md)</span></span>