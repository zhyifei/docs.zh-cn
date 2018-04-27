---
title: 构建可复原的服务供云。 采用在云中的暂时性故障
description: 为容器化的.NET 应用程序的.NET 微服务体系结构 |构建可复原的服务供云。 采用在云中的暂时性故障
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 10/26/2017
ms.prod: .net
ms.topic: article
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: 0ac1d67a5b5b9a19f47c1d20eeb446977466510f
ms.sourcegitcommit: 2e8acae16ae802f2d6d04e3ce0a6dbf04e476513
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/18/2018
---
# <a name="build-resilient-services-ready-for-the-cloud-embrace-transient-failures-in-the-cloud"></a><span data-ttu-id="59678-105">构建可复原的服务供云： 采用在云中的暂时性故障</span><span class="sxs-lookup"><span data-stu-id="59678-105">Build resilient services ready for the cloud: Embrace transient failures in the cloud</span></span>

<span data-ttu-id="59678-106">恢复能力是指从故障中恢复并继续工作的能力。</span><span class="sxs-lookup"><span data-stu-id="59678-106">Resiliency is the ability to recover from failures and continue to function.</span></span> <span data-ttu-id="59678-107">复原能力不是有关避免失败，但接受这一事实，将出现故障，并可避免停机时间或数据丢失的方式然后对它们的响应。</span><span class="sxs-lookup"><span data-stu-id="59678-107">Resiliency is not about avoiding failures, but accepting the fact that failures will occur, and then responding to them in a way that avoids downtime or data loss.</span></span> <span data-ttu-id="59678-108">恢复的目标是使应用程序在发生故障后回到完全正常运行的状态。</span><span class="sxs-lookup"><span data-stu-id="59678-108">The goal of resiliency is to return the application to a fully functioning state after a failure.</span></span>

<span data-ttu-id="59678-109">至少，实施基于软件的模型的复原能力，而不是基于硬件的模型时，你的应用程序可供云。</span><span class="sxs-lookup"><span data-stu-id="59678-109">Your application is ready for the cloud when, at a minimum, it implements a software-based model of resiliency, rather than a hardware-based model.</span></span> <span data-ttu-id="59678-110">云应用程序必须采用肯定会发生部分故障。</span><span class="sxs-lookup"><span data-stu-id="59678-110">Your cloud application must embrace the partial failures that will certainly occur.</span></span> <span data-ttu-id="59678-111">你需要设计或部分重构你的应用程序，如果您想要获得预期的部分故障中恢复。</span><span class="sxs-lookup"><span data-stu-id="59678-111">You need to design or partially refactor your application if you want to achieve resiliency to expected partial failures.</span></span> <span data-ttu-id="59678-112">它应设计为处理部分故障，如暂时性网络中断和节点或在云中发生故障的 Vm。</span><span class="sxs-lookup"><span data-stu-id="59678-112">It should be designed to cope with partial failures, like transient network outages and nodes, or VMs crashing in the cloud.</span></span> <span data-ttu-id="59678-113">正在移到不同 orchestrator 群集内节点的甚至容器可能会导致应用程序中的间歇性短失败。</span><span class="sxs-lookup"><span data-stu-id="59678-113">Even containers being moved to a different node within an orchestrator cluster can cause intermittent short failures within the application.</span></span>

## <a name="handling-partial-failure"></a><span data-ttu-id="59678-114">处理部分失败错误</span><span class="sxs-lookup"><span data-stu-id="59678-114">Handling partial failure</span></span>

<span data-ttu-id="59678-115">在基于云的应用程序，没有部分的失败的受始终存在风险。</span><span class="sxs-lookup"><span data-stu-id="59678-115">In a cloud-based application, there's an ever-present risk of partial failure.</span></span> <span data-ttu-id="59678-116">例如，单个网站实例或容器可能会失败，或者它可能不可用或没有响应。 在短时间。</span><span class="sxs-lookup"><span data-stu-id="59678-116">For instance, a single website instance or a container might fail, or it might be unavailable or unresponsive for a short time.</span></span> <span data-ttu-id="59678-117">或者，单个 VM 或服务器可能会崩溃。</span><span class="sxs-lookup"><span data-stu-id="59678-117">Or, a single VM or server might crash.</span></span>

<span data-ttu-id="59678-118">因为客户端和服务都是单独的进程，服务可能无法及时响应客户端的请求。</span><span class="sxs-lookup"><span data-stu-id="59678-118">Because clients and services are separate processes, a service might not be able to respond in a timely manner to a client's request.</span></span> <span data-ttu-id="59678-119">服务可能被重载并响应速度极慢的请求，或它可能只是无法访问在短时间由于网络问题。</span><span class="sxs-lookup"><span data-stu-id="59678-119">The service might be overloaded and respond extremely slowly to requests, or it might simply not be accessible for a short time because of network issues.</span></span>

<span data-ttu-id="59678-120">例如，考虑的整体的.NET 应用程序访问 Azure SQL 数据库中的数据库。</span><span class="sxs-lookup"><span data-stu-id="59678-120">For example, consider a monolithic .NET application that accesses a database in Azure SQL Database.</span></span> <span data-ttu-id="59678-121">如果 Azure SQL 数据库或任何其他第三方服务的一条简短停止响应时间 （Azure SQL 数据库可能被移动到另一个节点或服务器，并可能在几秒内没有响应），当用户尝试执行任何操作，该应用程序可能崩溃和显示w 异常完全相同的时间。</span><span class="sxs-lookup"><span data-stu-id="59678-121">If the Azure SQL database or any other third-party service is unresponsive for a brief time (an Azure SQL database might be moved to a different node or server, and be unresponsive for a few seconds), when the user tries to do any action, the application might crash and show an exception at the very same moment.</span></span>

<span data-ttu-id="59678-122">类似的方案可能会出现在应用程序使用 HTTP 服务。</span><span class="sxs-lookup"><span data-stu-id="59678-122">A similar scenario might occur in an app that consumes HTTP services.</span></span> <span data-ttu-id="59678-123">网络或服务本身可能不能在云中出现较短的暂时性故障。</span><span class="sxs-lookup"><span data-stu-id="59678-123">The network or the service itself might not be available in the cloud during a short, transient failure.</span></span>

<span data-ttu-id="59678-124">显示在图 4-9 中所示弹性应用程序应实现"重试使用指数退让"技术以便应用程序有机会处理在资源中的暂时性故障。</span><span class="sxs-lookup"><span data-stu-id="59678-124">A resilient application like the one shown in Figure 4-9 should implement techniques like "retries with exponential backoff" to give the application an opportunity to handle transient failures in resources.</span></span> <span data-ttu-id="59678-125">此外应在应用程序中使用"断路器"。</span><span class="sxs-lookup"><span data-stu-id="59678-125">You also should use "circuit breakers" in your applications.</span></span> <span data-ttu-id="59678-126">断路器将停止应用程序尝试访问资源时实际长期故障。</span><span class="sxs-lookup"><span data-stu-id="59678-126">A circuit breaker stops an application from trying to access a resource when it's actually a long-term failure.</span></span> <span data-ttu-id="59678-127">通过使用断路器，该应用程序可避免引发拒绝到其自身的服务。</span><span class="sxs-lookup"><span data-stu-id="59678-127">By using a circuit breaker, the application avoids provoking a denial of service to itself.</span></span>

![由具有指数回退重试处理部分故障](./media/image9.png)

> <span data-ttu-id="59678-129">**图 4-9。**</span><span class="sxs-lookup"><span data-stu-id="59678-129">**Figure 4-9.**</span></span> <span data-ttu-id="59678-130">由具有指数回退重试处理部分故障</span><span class="sxs-lookup"><span data-stu-id="59678-130">Partial failures handled by retries with exponential backoff</span></span>

<span data-ttu-id="59678-131">在 HTTP 资源和数据库资源，你可以使用这些技术。</span><span class="sxs-lookup"><span data-stu-id="59678-131">You can use these techniques both in HTTP resources and in database resources.</span></span> <span data-ttu-id="59678-132">在图 4-9、 应用程序基于 3 层体系结构，因此需要在服务级别 (HTTP) 和数据层级别 (TCP) 这些技术。</span><span class="sxs-lookup"><span data-stu-id="59678-132">In Figure 4-9, the application is based on a 3-tier architecture, so you need these techniques at the services level (HTTP) and at the data tier level (TCP).</span></span> <span data-ttu-id="59678-133">在使用单个应用程序层将数据库 （没有其他服务或微服务） 以及一个整体应用程序，处理数据库连接级别的暂时性故障可能是足够。</span><span class="sxs-lookup"><span data-stu-id="59678-133">In a monolithic application that uses only a single app tier in addition to the database (no additional services or microservices), handling transient failures at the database connection level might be enough.</span></span> <span data-ttu-id="59678-134">在该方案中，通常只是数据库连接的特定配置是必需的。</span><span class="sxs-lookup"><span data-stu-id="59678-134">In that scenario, usually just a particular configuration of the database connection is required.</span></span>

<span data-ttu-id="59678-135">实现访问数据库时，具体取决于你使用的，.NET 版本的弹性通信时它可以是非常简单 (例如， [Entity Framework 6 或更高版本](https://msdn.microsoft.com/library/dn456835(v=vs.113).aspx)，它是只需配置数据库连接）。</span><span class="sxs-lookup"><span data-stu-id="59678-135">When implementing resilient communications that access the database, depending on the version of .NET you are using, it can be very straightforward (for example, [with Entity Framework 6 or later](https://msdn.microsoft.com/library/dn456835(v=vs.113).aspx), it's just a matter of configuring the database connection).</span></span> <span data-ttu-id="59678-136">或者，你可能需要使用类似的其他库[暂时性故障处理应用程序块](https://msdn.microsoft.com/library/hh680934(v=pandp.50).aspx)（对于早期版本的.NET），或甚至实现你自己的库。</span><span class="sxs-lookup"><span data-stu-id="59678-136">Or, you might need to use additional libraries like the [Transient Fault Handling Application Block](https://msdn.microsoft.com/library/hh680934(v=pandp.50).aspx) (for earlier versions of .NET), or even implement your own library.</span></span>

<span data-ttu-id="59678-137">实现 HTTP 重试次数和断路器时，.NET 的推荐方法是使用[Polly](https://github.com/App-vNext/Polly)库，后者面向.NET 4.0、.NET 4.5 和.NET 标准 1.1，包括.NET 核心的支持。</span><span class="sxs-lookup"><span data-stu-id="59678-137">When implementing HTTP retries and circuit breakers, the recommendation for .NET is to use the [Polly](https://github.com/App-vNext/Polly) library, which targets .NET 4.0, .NET 4.5, and .NET Standard 1.1, which includes .NET Core support.</span></span>

<span data-ttu-id="59678-138">若要了解如何实现用于处理部分故障在云中的策略，请参阅以下引用。</span><span class="sxs-lookup"><span data-stu-id="59678-138">To learn how to implement strategies for handling partial failures in the cloud, see the following references.</span></span>

### <a name="additional-resources"></a><span data-ttu-id="59678-139">其他资源</span><span class="sxs-lookup"><span data-stu-id="59678-139">Additional resources</span></span>

-   <span data-ttu-id="59678-140">**实现弹性通信来处理部分失败**</span><span class="sxs-lookup"><span data-stu-id="59678-140">**Implementing resilient communication to handle partial failure**</span></span>

    [https://docs.microsoft.com/dotnet/standard/microservices-architecture/implement-resilient-applications/partial-failure-strategies](../../microservices-architecture/implement-resilient-applications/partial-failure-strategies.md)

-   <span data-ttu-id="59678-141">**实体框架连接复原和重试逻辑 （6 和更高版本）**</span><span class="sxs-lookup"><span data-stu-id="59678-141">**Entity Framework connection resiliency and retry logic (version 6 and later)**</span></span>

    [https://msdn.microsoft.com/library/dn456835(v=vs.113).aspx](https://msdn.microsoft.com/library/dn456835(v=vs.113).aspx)

-   <span data-ttu-id="59678-142">**暂时性故障处理应用程序块**</span><span class="sxs-lookup"><span data-stu-id="59678-142">**The Transient Fault Handling Application Block**</span></span>

-   [https://msdn.microsoft.com/library/hh680934(v=pandp.50).aspx](https://msdn.microsoft.com/library/hh680934(v=pandp.50).aspx)

-   <span data-ttu-id="59678-143">**弹性 HTTP 通信的 Polly 库**</span><span class="sxs-lookup"><span data-stu-id="59678-143">**Polly library for resilient HTTP communication**</span></span>

    https://github.com/App-vNext/Polly

>[!div class="step-by-step"]
<span data-ttu-id="59678-144">[上一页](when-to-deploy-windows-containers-to-azure-container-service-kubernetes.md)
[下一页](modernize-your-apps-with-monitoring-and-telemetry.md)</span><span class="sxs-lookup"><span data-stu-id="59678-144">[Previous](when-to-deploy-windows-containers-to-azure-container-service-kubernetes.md)
[Next](modernize-your-apps-with-monitoring-and-telemetry.md)</span></span>
