---
title: 为云构建复原服务就绪。 在云中处理暂时性故障
description: 通过 Azure 云和 Windows 容器实现现有 .NET 应用程序的现代化 |为云构建复原服务就绪。 在云中处理暂时性故障
ms.date: 04/30/2018
ms.openlocfilehash: 5d25fb0d15ff7b9f04b9491454d1368e4aa7f593
ms.sourcegitcommit: f20dd18dbcf2275513281f5d9ad7ece6a62644b4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/30/2019
ms.locfileid: "69578350"
---
# <a name="build-resilient-services-ready-for-the-cloud-embrace-transient-failures-in-the-cloud"></a><span data-ttu-id="09a62-105">生成适用于云的可复原服务：在云中处理暂时性故障</span><span class="sxs-lookup"><span data-stu-id="09a62-105">Build resilient services ready for the cloud: Embrace transient failures in the cloud</span></span>

<span data-ttu-id="09a62-106">恢复能力是指从故障中恢复并继续工作的能力。</span><span class="sxs-lookup"><span data-stu-id="09a62-106">Resiliency is the ability to recover from failures and continue to function.</span></span> <span data-ttu-id="09a62-107">复原并不是要避免故障, 而是接受会发生故障的事实, 然后以避免停机或数据丢失的方式对其进行响应。</span><span class="sxs-lookup"><span data-stu-id="09a62-107">Resiliency is not about avoiding failures, but accepting the fact that failures will occur, and then responding to them in a way that avoids downtime or data loss.</span></span> <span data-ttu-id="09a62-108">恢复的目标是使应用程序在发生故障后回到完全正常运行的状态。</span><span class="sxs-lookup"><span data-stu-id="09a62-108">The goal of resiliency is to return the application to a fully functioning state after a failure.</span></span>

<span data-ttu-id="09a62-109">当你的应用程序至少实现了基于软件的复原模式 (而不是基于硬件的模型) 时, 你的应用程序即可为云做好准备。</span><span class="sxs-lookup"><span data-stu-id="09a62-109">Your application is ready for the cloud when, at a minimum, it implements a software-based model of resiliency, rather than a hardware-based model.</span></span> <span data-ttu-id="09a62-110">你的云应用程序必须采用将会出现的部分故障。</span><span class="sxs-lookup"><span data-stu-id="09a62-110">Your cloud application must embrace the partial failures that will certainly occur.</span></span> <span data-ttu-id="09a62-111">设计或部分重构您的应用程序, 以通过预期的部分故障实现复原。</span><span class="sxs-lookup"><span data-stu-id="09a62-111">Design or partially refactor your application to achieve resiliency with expected partial failures.</span></span> <span data-ttu-id="09a62-112">它应该用于应对部分故障, 例如暂时性的网络中断和节点, 或者 Vm 在云中崩溃。</span><span class="sxs-lookup"><span data-stu-id="09a62-112">It should be designed to cope with partial failures, like transient network outages and nodes, or VMs crashing in the cloud.</span></span> <span data-ttu-id="09a62-113">即使将容器移至 orchestrator 群集内的其他节点, 也可能导致应用程序中出现间歇性的短故障。</span><span class="sxs-lookup"><span data-stu-id="09a62-113">Even containers being moved to a different node within an orchestrator cluster can cause intermittent short failures within the application.</span></span>

## <a name="handling-partial-failure"></a><span data-ttu-id="09a62-114">处理部分失败错误</span><span class="sxs-lookup"><span data-stu-id="09a62-114">Handling partial failure</span></span>

<span data-ttu-id="09a62-115">在基于云的应用程序中, 存在部分故障的现有风险。</span><span class="sxs-lookup"><span data-stu-id="09a62-115">In a cloud-based application, there's an ever-present risk of partial failure.</span></span> <span data-ttu-id="09a62-116">例如, 单个网站实例或容器可能会失败, 或者可能是短时间不可用或没有响应。</span><span class="sxs-lookup"><span data-stu-id="09a62-116">For instance, a single website instance or a container might fail, or it might be unavailable or unresponsive for a short time.</span></span> <span data-ttu-id="09a62-117">或者, 单个 VM 或服务器可能会崩溃。</span><span class="sxs-lookup"><span data-stu-id="09a62-117">Or, a single VM or server might crash.</span></span>

<span data-ttu-id="09a62-118">由于客户端和服务是独立的进程, 因此服务可能无法及时响应客户端的请求。</span><span class="sxs-lookup"><span data-stu-id="09a62-118">Because clients and services are separate processes, a service might not be able to respond in a timely manner to a client's request.</span></span> <span data-ttu-id="09a62-119">此服务可能已过载, 响应速度慢, 或者由于网络问题而无法在短时间访问该服务。</span><span class="sxs-lookup"><span data-stu-id="09a62-119">The service might be overloaded and respond slowly to requests, or it might not be accessible for a short time because of network issues.</span></span>

<span data-ttu-id="09a62-120">例如, 假设有一个在 Azure SQL 数据库中访问数据库的单一 .NET 应用程序。</span><span class="sxs-lookup"><span data-stu-id="09a62-120">For example, consider a monolithic .NET application that accesses a database in Azure SQL Database.</span></span> <span data-ttu-id="09a62-121">如果 Azure SQL 数据库或任何其他第三方服务没有短暂的响应时间 (Azure SQL 数据库可能会移动到不同的节点或服务器, 并且在几秒钟内无响应), 则当用户尝试执行任何操作时, 应用程序可能会崩溃并完成 show 此时引发异常。</span><span class="sxs-lookup"><span data-stu-id="09a62-121">If the Azure SQL database or any other third-party service is unresponsive for a brief time (an Azure SQL database might be moved to a different node or server, and be unresponsive for a few seconds), when the user tries to do any action, the application might crash and show an exception at the same moment.</span></span>

<span data-ttu-id="09a62-122">使用 HTTP 服务的应用可能会出现类似的情况。</span><span class="sxs-lookup"><span data-stu-id="09a62-122">A similar scenario might occur in an app that consumes HTTP services.</span></span> <span data-ttu-id="09a62-123">在出现短暂的暂时性故障时, 网络或服务本身可能无法在云中使用。</span><span class="sxs-lookup"><span data-stu-id="09a62-123">The network or the service itself might not be available in the cloud during a short, transient failure.</span></span>

<span data-ttu-id="09a62-124">如图4-9 中所示的弹性应用程序应该实现 "使用指数回退重试" 之类的技术, 使应用程序有机会处理资源的暂时性故障。</span><span class="sxs-lookup"><span data-stu-id="09a62-124">A resilient application like the one shown in Figure 4-9 should implement techniques like "retries with exponential backoff" to give the application an opportunity to handle transient failures in resources.</span></span> <span data-ttu-id="09a62-125">你还应在应用程序中使用 "断路程序"。</span><span class="sxs-lookup"><span data-stu-id="09a62-125">You also should use "circuit breakers" in your applications.</span></span> <span data-ttu-id="09a62-126">当某个应用程序实际上是长期故障时, 断路器会阻止该应用程序尝试访问该资源。</span><span class="sxs-lookup"><span data-stu-id="09a62-126">A circuit breaker stops an application from trying to access a resource when it's actually a long-term failure.</span></span> <span data-ttu-id="09a62-127">通过使用断路器, 应用程序可避免造成自身的拒绝服务。</span><span class="sxs-lookup"><span data-stu-id="09a62-127">By using a circuit breaker, the application avoids provoking a denial of service to itself.</span></span>

![使用指数回退处理重试的部分失败](./media/image9.png)

> <span data-ttu-id="09a62-129">**图4-9。**</span><span class="sxs-lookup"><span data-stu-id="09a62-129">**Figure 4-9.**</span></span> <span data-ttu-id="09a62-130">使用指数回退处理重试的部分失败</span><span class="sxs-lookup"><span data-stu-id="09a62-130">Partial failures handled by retries with exponential backoff</span></span>

<span data-ttu-id="09a62-131">可以在 HTTP 资源和数据库资源中使用这些技术。</span><span class="sxs-lookup"><span data-stu-id="09a62-131">You can use these techniques both in HTTP resources and in database resources.</span></span> <span data-ttu-id="09a62-132">在图4-9 中, 应用程序基于3层体系结构, 因此, 你需要在服务级别 (HTTP) 和数据层级 (TCP) 上使用这些方法。</span><span class="sxs-lookup"><span data-stu-id="09a62-132">In Figure 4-9, the application is based on a 3-tier architecture, so you need these techniques at the services level (HTTP) and at the data tier level (TCP).</span></span> <span data-ttu-id="09a62-133">在仅使用单个应用层和数据库 (无其他服务或微服务) 的单一应用程序层中, 处理数据库连接级别的暂时性故障可能就足够了。</span><span class="sxs-lookup"><span data-stu-id="09a62-133">In a monolithic application that uses only a single app tier in addition to the database (no additional services or microservices), handling transient failures at the database connection level might be enough.</span></span> <span data-ttu-id="09a62-134">在这种情况下, 只需要数据库连接的特定配置。</span><span class="sxs-lookup"><span data-stu-id="09a62-134">In that scenario, just a particular configuration of the database connection is required.</span></span>

<span data-ttu-id="09a62-135">实现访问数据库的可恢复性通信时, 根据所使用的 .NET 版本, 它可能很简单 (例如,[使用实体框架6或更高](/ef/ef6/fundamentals/connection-resiliency/retry-logic)版本)。</span><span class="sxs-lookup"><span data-stu-id="09a62-135">When implementing resilient communications that access the database, depending on the version of .NET you are using, it can be straightforward (for example, [with Entity Framework 6 or later](/ef/ef6/fundamentals/connection-resiliency/retry-logic).</span></span> <span data-ttu-id="09a62-136">只需配置数据库连接即可)。</span><span class="sxs-lookup"><span data-stu-id="09a62-136">It's just a matter of configuring the database connection).</span></span> <span data-ttu-id="09a62-137">或者, 你可能需要使用其他库, 如[暂时性故障处理应用程序块](https://docs.microsoft.com/previous-versions/msp-n-p/hh680934(v=pandp.50))(适用于早期版本的 .net), 甚至实现你自己的库。</span><span class="sxs-lookup"><span data-stu-id="09a62-137">Or, you might need to use additional libraries like the [Transient Fault Handling Application Block](https://docs.microsoft.com/previous-versions/msp-n-p/hh680934(v=pandp.50)) (for earlier versions of .NET), or even implement your own library.</span></span>

<span data-ttu-id="09a62-138">实现 HTTP 重试次数和断路器时，.NET 的推荐方法是使用[Polly](https://github.com/App-vNext/Polly)库，后者面向.NET Framework 4.0、.NET Framework 4.5 和.NET Standard 1.1，包括.NET Core 的支持。</span><span class="sxs-lookup"><span data-stu-id="09a62-138">When implementing HTTP retries and circuit breakers, the recommendation for .NET is to use the [Polly](https://github.com/App-vNext/Polly) library, which targets .NET Framework 4.0, .NET Framework 4.5, and .NET Standard 1.1, which includes .NET Core support.</span></span>

<span data-ttu-id="09a62-139">若要了解如何实现用于处理云中部分故障的策略, 请参阅以下参考。</span><span class="sxs-lookup"><span data-stu-id="09a62-139">To learn how to implement strategies for handling partial failures in the cloud, see the following references.</span></span>

### <a name="additional-resources"></a><span data-ttu-id="09a62-140">其他资源</span><span class="sxs-lookup"><span data-stu-id="09a62-140">Additional resources</span></span>

- <span data-ttu-id="09a62-141">**实现可恢复性通信以处理部分故障**</span><span class="sxs-lookup"><span data-stu-id="09a62-141">**Implementing resilient communication to handle partial failure**</span></span>

    [https://docs.microsoft.com/dotnet/architecture/microservices/implement-resilient-applications/partial-failure-strategies](../../microservices/implement-resilient-applications/partial-failure-strategies.md)

- <span data-ttu-id="09a62-142">**实体框架连接复原和重试逻辑 (版本6及更高版本)**</span><span class="sxs-lookup"><span data-stu-id="09a62-142">**Entity Framework connection resiliency and retry logic (version 6 and later)**</span></span>

    [https://docs.microsoft.com/ef/ef6/fundamentals/connection-resiliency/retry-logic](/ef/ef6/fundamentals/connection-resiliency/retry-logic)

- <span data-ttu-id="09a62-143">**暂时性故障处理应用程序块**</span><span class="sxs-lookup"><span data-stu-id="09a62-143">**The Transient Fault Handling Application Block**</span></span>

- <https://docs.microsoft.com/previous-versions/msp-n-p/hh680934(v=pandp.50)>

- <span data-ttu-id="09a62-144">**用于复原 HTTP 通信的 Polly 库**</span><span class="sxs-lookup"><span data-stu-id="09a62-144">**Polly library for resilient HTTP communication**</span></span>

    https://github.com/App-vNext/Polly

>[!div class="step-by-step"]
><span data-ttu-id="09a62-145">[上一页](when-to-deploy-windows-containers-to-azure-container-service-kubernetes.md)
>[下一页](modernize-your-apps-with-monitoring-and-telemetry.md)</span><span class="sxs-lookup"><span data-stu-id="09a62-145">[Previous](when-to-deploy-windows-containers-to-azure-container-service-kubernetes.md)
[Next](modernize-your-apps-with-monitoring-and-telemetry.md)</span></span>
