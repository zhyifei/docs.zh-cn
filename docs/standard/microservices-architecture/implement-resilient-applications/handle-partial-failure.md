---
title: "处理部分失败"
description: "为容器化的.NET 应用程序的.NET 微服务体系结构 |处理部分失败"
keywords: "Docker, 微服务, ASP.NET, 容器"
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 05/26/2017
ms.prod: .net-core
ms.technology: dotnet-docker
ms.topic: article
ms.openlocfilehash: b7d16acf3de2d395da70e8f46e59c129dec24f71
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="handling-partial-failure"></a><span data-ttu-id="c36aa-104">处理部分失败</span><span class="sxs-lookup"><span data-stu-id="c36aa-104">Handling partial failure</span></span>

<span data-ttu-id="c36aa-105">在类似于基于微服务的应用程序的分布式系统，没有部分的失败的受始终存在风险。</span><span class="sxs-lookup"><span data-stu-id="c36aa-105">In distributed systems like microservices-based applications, there is an ever-present risk of partial failure.</span></span> <span data-ttu-id="c36aa-106">例如，单个 microservice/容器可能会失败，或可能不可用的短时间内，响应或单个 VM 或服务器可能会崩溃。</span><span class="sxs-lookup"><span data-stu-id="c36aa-106">For instance, a single microservice/container can fail or might not be available to respond for a short time, or a single VM or server can crash.</span></span> <span data-ttu-id="c36aa-107">由于客户端和服务都是单独的进程，服务可能无法及时方式与客户端的请求作出响应。</span><span class="sxs-lookup"><span data-stu-id="c36aa-107">Since clients and services are separate processes, a service might not be able to respond in a timely way to a client’s request.</span></span> <span data-ttu-id="c36aa-108">服务可能重载和速度极慢响应请求，或者可能只是无法访问在短时间由于网络问题。</span><span class="sxs-lookup"><span data-stu-id="c36aa-108">The service might be overloaded and responding extremely slowly to requests, or might simply not be accessible for a short time because of network issues.</span></span>

<span data-ttu-id="c36aa-109">例如，考虑来自 eShopOnContainers 的订单详细信息页示例应用程序。</span><span class="sxs-lookup"><span data-stu-id="c36aa-109">For example, consider the Order details page from the eShopOnContainers sample application.</span></span> <span data-ttu-id="c36aa-110">如果排序微服务停止响应时用户尝试提交订单时，客户端进程 （MVC web 应用程序） 的错误实现 — 例如，如果客户端代码是要同步的 Rpc 用于无超时-将无限期阻止线程等待响应。</span><span class="sxs-lookup"><span data-stu-id="c36aa-110">If the ordering microservice is unresponsive when the user tries to submit an order, a bad implementation of the client process (the MVC web application)—for example, if the client code were to use synchronous RPCs with no timeout—would block threads indefinitely waiting for a response.</span></span> <span data-ttu-id="c36aa-111">除了创建不良用户体验，每个无响应的等待时间使用或阻止线程，并且线程是高度可伸缩的应用程序中极其有价值。</span><span class="sxs-lookup"><span data-stu-id="c36aa-111">In addition to creating a bad user experience, every unresponsive wait consumes or blocks a thread, and threads are extremely valuable in highly scalable applications.</span></span> <span data-ttu-id="c36aa-112">如果有许多阻塞的线程，最终应用程序的运行时可能会用尽线程。</span><span class="sxs-lookup"><span data-stu-id="c36aa-112">If there are many blocked threads, eventually the application’s runtime can run out of threads.</span></span> <span data-ttu-id="c36aa-113">在这种情况下，应用程序会停止而不是全局响应只是部分响应，如图 10-1 中所示。</span><span class="sxs-lookup"><span data-stu-id="c36aa-113">In that case, the application can become globally unresponsive instead of just partially unresponsive, as show in Figure 10-1.</span></span>

![](./media/image1.png)

<span data-ttu-id="c36aa-114">**图 10-1**。</span><span class="sxs-lookup"><span data-stu-id="c36aa-114">**Figure 10-1**.</span></span> <span data-ttu-id="c36aa-115">由于存在影响服务线程可用性的依存关系部分故障</span><span class="sxs-lookup"><span data-stu-id="c36aa-115">Partial failures because of dependencies that impact service thread availability</span></span>

<span data-ttu-id="c36aa-116">在大型基于微服务的应用中，可以放大任何部分的失败，尤其是如果内部微服务交互的大多数基于同步 （这可反模式） 的 HTTP 调用。</span><span class="sxs-lookup"><span data-stu-id="c36aa-116">In a large microservices-based application, any partial failure can be amplified, especially if most of the internal microservices interaction is based on synchronous HTTP calls (which is considered an anti-pattern).</span></span> <span data-ttu-id="c36aa-117">考虑接收的每日的传入呼叫数以百万计的系统。</span><span class="sxs-lookup"><span data-stu-id="c36aa-117">Think about a system that receives millions of incoming calls per day.</span></span> <span data-ttu-id="c36aa-118">如果你的系统具有不好的设计基于同步的 HTTP 调用的长链，这些传入调用对可能会导致许多详细数以百万计的传出调用 （让我们假设 1:4 比率） 多个内部微服务为同步的依赖项。</span><span class="sxs-lookup"><span data-stu-id="c36aa-118">If your system has a bad design that is based on long chains of synchronous HTTP calls, these incoming calls might result in many more millions of outgoing calls (let’s suppose a ratio of 1:4) to dozens of internal microservices as synchronous dependencies.</span></span> <span data-ttu-id="c36aa-119">这种情况下将显示在图 10-2，尤其是依赖项\#3。</span><span class="sxs-lookup"><span data-stu-id="c36aa-119">This situation is shown in Figure 10-2, especially dependency \#3.</span></span>

![](./media/image2.png)

<span data-ttu-id="c36aa-120">**图 10-2**。</span><span class="sxs-lookup"><span data-stu-id="c36aa-120">**Figure 10-2**.</span></span> <span data-ttu-id="c36aa-121">具有不正确的设计，如果突出显示的 HTTP 请求长链的影响</span><span class="sxs-lookup"><span data-stu-id="c36aa-121">The impact of having an incorrect design featuring long chains of HTTP requests</span></span>

<span data-ttu-id="c36aa-122">实质上是间歇性故障中分布式保证和云基于的系统上，即使每个依赖项本身具有极好的可用性。</span><span class="sxs-lookup"><span data-stu-id="c36aa-122">Intermittent failure is virtually guaranteed in a distributed and cloud based system, even if every dependency itself has excellent availability.</span></span> <span data-ttu-id="c36aa-123">这应该是你需要考虑的事实。</span><span class="sxs-lookup"><span data-stu-id="c36aa-123">This should be a fact you need to consider.</span></span>

<span data-ttu-id="c36aa-124">如果你不设计和实现技术，以确保容错功能，可以放大甚至小停机时间。</span><span class="sxs-lookup"><span data-stu-id="c36aa-124">If you do not design and implement techniques to ensure fault tolerance, even small downtimes can be amplified.</span></span> <span data-ttu-id="c36aa-125">例如，50 依赖关系每个具有 99.99%的可用性会导致每个月的停机时间几个小时由于这种连锁反应。</span><span class="sxs-lookup"><span data-stu-id="c36aa-125">As an example, 50 dependencies each with 99.99% of availability would result in several hours of downtime each month because of this ripple effect.</span></span> <span data-ttu-id="c36aa-126">当处理大量的请求时失败时的微服务依赖项时，这种故障能够快速 saturate 中每个服务的所有可用请求线程，并使整个应用程序崩溃。</span><span class="sxs-lookup"><span data-stu-id="c36aa-126">When a microservice dependency fails while handling a high volume of requests, that failure can quickly saturate all available request threads in each service and crash the whole application.</span></span>

![](./media/image3.png)

<span data-ttu-id="c36aa-127">**图 10-3**。</span><span class="sxs-lookup"><span data-stu-id="c36aa-127">**Figure 10-3**.</span></span> <span data-ttu-id="c36aa-128">由微服务使用的同步的 HTTP 调用的长链放大部分的失败</span><span class="sxs-lookup"><span data-stu-id="c36aa-128">Partial failure amplified by microservices with long chains of synchronous HTTP calls</span></span>

<span data-ttu-id="c36aa-129">为了尽量减少此问题，请在部分"*异步 microservice 集成强制实施微服务构成的自治*"（在体系结构章），我们建议你在内部使用异步通信微服务。</span><span class="sxs-lookup"><span data-stu-id="c36aa-129">To minimize this problem, in the section "*Asynchronous microservice integration enforce microservice’s autonomy*” (in the architecture chapter), we encouraged you to use asynchronous communication across the internal microservices.</span></span> <span data-ttu-id="c36aa-130">我们简要介绍多下一节中。</span><span class="sxs-lookup"><span data-stu-id="c36aa-130">We briefly explain more in the next section.</span></span>

<span data-ttu-id="c36aa-131">此外，很重要设计微服务和客户端应用程序可以处理部分故障-即，构建弹性微服务和客户端应用程序。</span><span class="sxs-lookup"><span data-stu-id="c36aa-131">In addition, it is essential that you design your microservices and client applications to handle partial failures—that is, to build resilient microservices and client applications.</span></span>


>[!div class="step-by-step"]
<span data-ttu-id="c36aa-132">[以前](index.md) [下一步] (部分的失败-strategies.md)</span><span class="sxs-lookup"><span data-stu-id="c36aa-132">[Previous] (index.md) [Next] (partial-failure-strategies.md)</span></span>
