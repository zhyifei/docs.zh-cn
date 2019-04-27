---
title: 生成可复原的准备好使用云服务。 在云中处理暂时性故障
description: 更新现有.NET 应用程序与 Azure 云和 Windows 容器 |生成可复原的准备好使用云服务。 在云中处理暂时性故障
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 04/30/2018
ms.openlocfilehash: 801d017457d1cdc3c8a495c8127b203380cb1d9e
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "61811823"
---
# <a name="build-resilient-services-ready-for-the-cloud-embrace-transient-failures-in-the-cloud"></a><span data-ttu-id="fad73-105">生成适用于云的可复原服务：在云中处理暂时性故障</span><span class="sxs-lookup"><span data-stu-id="fad73-105">Build resilient services ready for the cloud: Embrace transient failures in the cloud</span></span>

<span data-ttu-id="fad73-106">恢复能力是指从故障中恢复并继续工作的能力。</span><span class="sxs-lookup"><span data-stu-id="fad73-106">Resiliency is the ability to recover from failures and continue to function.</span></span> <span data-ttu-id="fad73-107">复原能力不是有关避免故障发生，但接受这一事实，将出现故障，并可避免停机或数据丢失的方式对其然后作出响应。</span><span class="sxs-lookup"><span data-stu-id="fad73-107">Resiliency is not about avoiding failures, but accepting the fact that failures will occur, and then responding to them in a way that avoids downtime or data loss.</span></span> <span data-ttu-id="fad73-108">恢复的目标是使应用程序在发生故障后回到完全正常运行的状态。</span><span class="sxs-lookup"><span data-stu-id="fad73-108">The goal of resiliency is to return the application to a fully functioning state after a failure.</span></span>

<span data-ttu-id="fad73-109">最小值，它实现了基于软件的模型的复原能力，而不是基于硬件的模型时，你的应用程序准备好使用云。</span><span class="sxs-lookup"><span data-stu-id="fad73-109">Your application is ready for the cloud when, at a minimum, it implements a software-based model of resiliency, rather than a hardware-based model.</span></span> <span data-ttu-id="fad73-110">云应用程序必须接受必然会发生部分失败。</span><span class="sxs-lookup"><span data-stu-id="fad73-110">Your cloud application must embrace the partial failures that will certainly occur.</span></span> <span data-ttu-id="fad73-111">设计或部分重构应用程序以实现预期的部分故障的复原能力。</span><span class="sxs-lookup"><span data-stu-id="fad73-111">Design or partially refactor your application to achieve resiliency with expected partial failures.</span></span> <span data-ttu-id="fad73-112">它应设计为处理部分故障，如暂时性网络中断和节点或在云中崩溃的 Vm。</span><span class="sxs-lookup"><span data-stu-id="fad73-112">It should be designed to cope with partial failures, like transient network outages and nodes, or VMs crashing in the cloud.</span></span> <span data-ttu-id="fad73-113">甚至要移动到另一个节点的业务流程协调程序群集中的容器可能会导致应用程序中的间歇性短失败。</span><span class="sxs-lookup"><span data-stu-id="fad73-113">Even containers being moved to a different node within an orchestrator cluster can cause intermittent short failures within the application.</span></span>

## <a name="handling-partial-failure"></a><span data-ttu-id="fad73-114">处理部分失败错误</span><span class="sxs-lookup"><span data-stu-id="fad73-114">Handling partial failure</span></span>

<span data-ttu-id="fad73-115">在基于云的应用程序，没有经常会出现部分失败错误。</span><span class="sxs-lookup"><span data-stu-id="fad73-115">In a cloud-based application, there's an ever-present risk of partial failure.</span></span> <span data-ttu-id="fad73-116">例如，单个网站实例或容器可能会失败，也可能是不可用或在短时间无响应。</span><span class="sxs-lookup"><span data-stu-id="fad73-116">For instance, a single website instance or a container might fail, or it might be unavailable or unresponsive for a short time.</span></span> <span data-ttu-id="fad73-117">或者，单个 VM 或服务器可能会崩溃。</span><span class="sxs-lookup"><span data-stu-id="fad73-117">Or, a single VM or server might crash.</span></span>

<span data-ttu-id="fad73-118">客户端和服务的单独进程，因为服务可能无法及时地响应客户端的请求。</span><span class="sxs-lookup"><span data-stu-id="fad73-118">Because clients and services are separate processes, a service might not be able to respond in a timely manner to a client's request.</span></span> <span data-ttu-id="fad73-119">可重载和响应速度慢的请求，服务也可能不是短时间内访问由于网络问题。</span><span class="sxs-lookup"><span data-stu-id="fad73-119">The service might be overloaded and respond slowly to requests, or it might not be accessible for a short time because of network issues.</span></span>

<span data-ttu-id="fad73-120">例如，考虑访问 Azure SQL 数据库中的数据库的整体化.NET 应用程序。</span><span class="sxs-lookup"><span data-stu-id="fad73-120">For example, consider a monolithic .NET application that accesses a database in Azure SQL Database.</span></span> <span data-ttu-id="fad73-121">如果 Azure SQL 数据库或任何其他第三方服务为响应针对一条简短时间 （Azure SQL 数据库可能移动到另一个节点或服务器，并在几秒内无响应），当用户尝试执行任何操作，该应用程序可能会崩溃和显示w 异常在同一时间点。</span><span class="sxs-lookup"><span data-stu-id="fad73-121">If the Azure SQL database or any other third-party service is unresponsive for a brief time (an Azure SQL database might be moved to a different node or server, and be unresponsive for a few seconds), when the user tries to do any action, the application might crash and show an exception at the same moment.</span></span>

<span data-ttu-id="fad73-122">中的应用程序使用 HTTP 的服务可能出现类似的方案。</span><span class="sxs-lookup"><span data-stu-id="fad73-122">A similar scenario might occur in an app that consumes HTTP services.</span></span> <span data-ttu-id="fad73-123">网络或服务本身可能不能在云中较短的暂时性故障。</span><span class="sxs-lookup"><span data-stu-id="fad73-123">The network or the service itself might not be available in the cloud during a short, transient failure.</span></span>

<span data-ttu-id="fad73-124">图 4-9 所示的可复原应用程序应实现技术，例如"重试使用指数退避算法"以便应用程序有机会处理资源中的暂时性故障。</span><span class="sxs-lookup"><span data-stu-id="fad73-124">A resilient application like the one shown in Figure 4-9 should implement techniques like "retries with exponential backoff" to give the application an opportunity to handle transient failures in resources.</span></span> <span data-ttu-id="fad73-125">此外应在应用程序中使用"断路器"。</span><span class="sxs-lookup"><span data-stu-id="fad73-125">You also should use "circuit breakers" in your applications.</span></span> <span data-ttu-id="fad73-126">断路器会停止应用程序尝试访问资源时实际上长期故障。</span><span class="sxs-lookup"><span data-stu-id="fad73-126">A circuit breaker stops an application from trying to access a resource when it's actually a long-term failure.</span></span> <span data-ttu-id="fad73-127">通过使用断路器，该应用程序可避免人深受启发拒绝到其自身的服务。</span><span class="sxs-lookup"><span data-stu-id="fad73-127">By using a circuit breaker, the application avoids provoking a denial of service to itself.</span></span>

![通过使用指数退避算法的重试处理部分故障](./media/image9.png)

> <span data-ttu-id="fad73-129">**图 4-9。**</span><span class="sxs-lookup"><span data-stu-id="fad73-129">**Figure 4-9.**</span></span> <span data-ttu-id="fad73-130">通过使用指数退避算法的重试处理部分故障</span><span class="sxs-lookup"><span data-stu-id="fad73-130">Partial failures handled by retries with exponential backoff</span></span>

<span data-ttu-id="fad73-131">在 HTTP 资源和数据库资源，可以使用这些技术。</span><span class="sxs-lookup"><span data-stu-id="fad73-131">You can use these techniques both in HTTP resources and in database resources.</span></span> <span data-ttu-id="fad73-132">在图 4-9、 应用程序基于第 3 层体系结构，因此您需要在服务级别 (HTTP) 和数据层级别 (TCP) 这些技术。</span><span class="sxs-lookup"><span data-stu-id="fad73-132">In Figure 4-9, the application is based on a 3-tier architecture, so you need these techniques at the services level (HTTP) and at the data tier level (TCP).</span></span> <span data-ttu-id="fad73-133">在使用仅除了数据库 （任何其他服务或微服务） 的单个应用程序层的单一式应用程序，处理暂时性故障级别的数据库的连接可能已足够。</span><span class="sxs-lookup"><span data-stu-id="fad73-133">In a monolithic application that uses only a single app tier in addition to the database (no additional services or microservices), handling transient failures at the database connection level might be enough.</span></span> <span data-ttu-id="fad73-134">在这种情况下，只是特定的数据库连接的配置都需要。</span><span class="sxs-lookup"><span data-stu-id="fad73-134">In that scenario, just a particular configuration of the database connection is required.</span></span>

<span data-ttu-id="fad73-135">实现访问数据库时，具体取决于使用的，.NET 版本的弹性通信时它可能比较简单 (例如， [Entity Framework 6 或更高版本](/ef/ef6/fundamentals/connection-resiliency/retry-logic)。</span><span class="sxs-lookup"><span data-stu-id="fad73-135">When implementing resilient communications that access the database, depending on the version of .NET you are using, it can be straightforward (for example, [with Entity Framework 6 or later](/ef/ef6/fundamentals/connection-resiliency/retry-logic).</span></span> <span data-ttu-id="fad73-136">它是只需配置数据库连接。）</span><span class="sxs-lookup"><span data-stu-id="fad73-136">It's just a matter of configuring the database connection).</span></span> <span data-ttu-id="fad73-137">或者，可能需要使用其他库等[暂时性故障处理应用程序块](https://docs.microsoft.com/previous-versions/msp-n-p/hh680934(v=pandp.50))（适用于早期版本的.NET），或者甚至实现您自己的库。</span><span class="sxs-lookup"><span data-stu-id="fad73-137">Or, you might need to use additional libraries like the [Transient Fault Handling Application Block](https://docs.microsoft.com/previous-versions/msp-n-p/hh680934(v=pandp.50)) (for earlier versions of .NET), or even implement your own library.</span></span>

<span data-ttu-id="fad73-138">实现 HTTP 重试次数和断路器时，.NET 的推荐方法是使用[Polly](https://github.com/App-vNext/Polly)库，后者面向.NET Framework 4.0、.NET Framework 4.5 和.NET Standard 1.1，包括.NET Core 的支持。</span><span class="sxs-lookup"><span data-stu-id="fad73-138">When implementing HTTP retries and circuit breakers, the recommendation for .NET is to use the [Polly](https://github.com/App-vNext/Polly) library, which targets .NET Framework 4.0, .NET Framework 4.5, and .NET Standard 1.1, which includes .NET Core support.</span></span>

<span data-ttu-id="fad73-139">若要了解如何实现处理云中的部分失败的策略，请参阅以下参考资料。</span><span class="sxs-lookup"><span data-stu-id="fad73-139">To learn how to implement strategies for handling partial failures in the cloud, see the following references.</span></span>

### <a name="additional-resources"></a><span data-ttu-id="fad73-140">其他资源</span><span class="sxs-lookup"><span data-stu-id="fad73-140">Additional resources</span></span>

-   <span data-ttu-id="fad73-141">**实现弹性通信来处理部分失败错误**</span><span class="sxs-lookup"><span data-stu-id="fad73-141">**Implementing resilient communication to handle partial failure**</span></span>

    [https://docs.microsoft.com/dotnet/standard/microservices-architecture/implement-resilient-applications/partial-failure-strategies](../../microservices-architecture/implement-resilient-applications/partial-failure-strategies.md)

-   <span data-ttu-id="fad73-142">**实体框架连接复原和重试逻辑 （6 和更高版本）**</span><span class="sxs-lookup"><span data-stu-id="fad73-142">**Entity Framework connection resiliency and retry logic (version 6 and later)**</span></span>

    [https://docs.microsoft.com/ef/ef6/fundamentals/connection-resiliency/retry-logic](/ef/ef6/fundamentals/connection-resiliency/retry-logic)

-   <span data-ttu-id="fad73-143">**暂时性故障处理应用程序块**</span><span class="sxs-lookup"><span data-stu-id="fad73-143">**The Transient Fault Handling Application Block**</span></span>

-   <https://docs.microsoft.com/previous-versions/msp-n-p/hh680934(v=pandp.50)>

-   <span data-ttu-id="fad73-144">**Polly 适用于弹性 HTTP 通信库**</span><span class="sxs-lookup"><span data-stu-id="fad73-144">**Polly library for resilient HTTP communication**</span></span>

    https://github.com/App-vNext/Polly

>[!div class="step-by-step"]
><span data-ttu-id="fad73-145">[上一页](when-to-deploy-windows-containers-to-azure-container-service-kubernetes.md)
>[下一页](modernize-your-apps-with-monitoring-and-telemetry.md)</span><span class="sxs-lookup"><span data-stu-id="fad73-145">[Previous](when-to-deploy-windows-containers-to-azure-container-service-kubernetes.md)
[Next](modernize-your-apps-with-monitoring-and-telemetry.md)</span></span>
