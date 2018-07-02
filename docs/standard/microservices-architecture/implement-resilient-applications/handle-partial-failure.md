---
title: 处理部分失败错误
description: 适用于容器化 .NET 应用程序的 .NET 微服务体系结构 | 处理部分失败错误
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 05/26/2017
ms.openlocfilehash: 957a0b1b8b4d217fac591db54e4ee053098bc7da
ms.sourcegitcommit: 979597cd8055534b63d2c6ee8322938a27d0c87b
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/29/2018
ms.locfileid: "37105190"
---
# <a name="handling-partial-failure"></a><span data-ttu-id="5e056-103">处理部分失败错误</span><span class="sxs-lookup"><span data-stu-id="5e056-103">Handling partial failure</span></span>

<span data-ttu-id="5e056-104">在基于微服务的应用程序这类分布式系统中，经常会出现部分失败错误。</span><span class="sxs-lookup"><span data-stu-id="5e056-104">In distributed systems like microservices-based applications, there is an ever-present risk of partial failure.</span></span> <span data-ttu-id="5e056-105">例如，单个微服务/容器可能会失败，也可能无法在短时间响应，或者单个 VM 或服务器会出现故障。</span><span class="sxs-lookup"><span data-stu-id="5e056-105">For instance, a single microservice/container can fail or might not be available to respond for a short time, or a single VM or server can crash.</span></span> <span data-ttu-id="5e056-106">由于客户端和服务是彼此独立的流程，因此服务可能无法及时响应客户端的请求。</span><span class="sxs-lookup"><span data-stu-id="5e056-106">Since clients and services are separate processes, a service might not be able to respond in a timely way to a client’s request.</span></span> <span data-ttu-id="5e056-107">服务可能过载并且对请求的响应速度极慢，或者由于网络问题可能无法在短时间内访问。</span><span class="sxs-lookup"><span data-stu-id="5e056-107">The service might be overloaded and responding extremely slowly to requests, or might simply not be accessible for a short time because of network issues.</span></span>

<span data-ttu-id="5e056-108">例如，请查看 eShopOnContainers 示例应用程序的订单详细信息页。</span><span class="sxs-lookup"><span data-stu-id="5e056-108">For example, consider the Order details page from the eShopOnContainers sample application.</span></span> <span data-ttu-id="5e056-109">如果订购微服务在用户尝试提交订单时没有响应，则客户端进程（MVC Web 应用程序）的错误实现（例如，如果客户端代码使用同步 RPC 而没有出现超时）将会无限期地阻止线程等待回应。</span><span class="sxs-lookup"><span data-stu-id="5e056-109">If the ordering microservice is unresponsive when the user tries to submit an order, a bad implementation of the client process (the MVC web application)—for example, if the client code were to use synchronous RPCs with no timeout—would block threads indefinitely waiting for a response.</span></span> <span data-ttu-id="5e056-110">每个无响应的等待除了会造成不良用户体验之外，还会消耗或阻止线程，然而线程在高度可缩放应用程序中极有价值。</span><span class="sxs-lookup"><span data-stu-id="5e056-110">In addition to creating a bad user experience, every unresponsive wait consumes or blocks a thread, and threads are extremely valuable in highly scalable applications.</span></span> <span data-ttu-id="5e056-111">如果受阻止的线程数量众多，应用程序的运行时最终会耗尽所有线程。</span><span class="sxs-lookup"><span data-stu-id="5e056-111">If there are many blocked threads, eventually the application’s runtime can run out of threads.</span></span> <span data-ttu-id="5e056-112">在这种情况下，应用程序会出现全局无响应，而不只是部分无响应，如图 10-1 中所示。</span><span class="sxs-lookup"><span data-stu-id="5e056-112">In that case, the application can become globally unresponsive instead of just partially unresponsive, as show in Figure 10-1.</span></span>

![](./media/image1.png)

<span data-ttu-id="5e056-113">**图 10-1**。</span><span class="sxs-lookup"><span data-stu-id="5e056-113">**Figure 10-1**.</span></span> <span data-ttu-id="5e056-114">因依赖性影响服务线程可用性而出现的部分失败错误</span><span class="sxs-lookup"><span data-stu-id="5e056-114">Partial failures because of dependencies that impact service thread availability</span></span>

<span data-ttu-id="5e056-115">在基于微服务的大型应用程序中，任何部分失败错误都可能被放大，尤其是在大多数内部微服务交互都基于同步 HTTP 调用的情况下（这种情况被视为反模式）。</span><span class="sxs-lookup"><span data-stu-id="5e056-115">In a large microservices-based application, any partial failure can be amplified, especially if most of the internal microservices interaction is based on synchronous HTTP calls (which is considered an anti-pattern).</span></span> <span data-ttu-id="5e056-116">想想一个每天接收上百万传入调用的系统。</span><span class="sxs-lookup"><span data-stu-id="5e056-116">Think about a system that receives millions of incoming calls per day.</span></span> <span data-ttu-id="5e056-117">如果系统采用基于同步 HTTP 调用长链的不当设计，那么这些传入调用可能会再产生数百万对数十个内部微服务的传出调用（假设比例为 1:4）作为同步依赖项。</span><span class="sxs-lookup"><span data-stu-id="5e056-117">If your system has a bad design that is based on long chains of synchronous HTTP calls, these incoming calls might result in many more millions of outgoing calls (let’s suppose a ratio of 1:4) to dozens of internal microservices as synchronous dependencies.</span></span> <span data-ttu-id="5e056-118">这种情况如图 10-2 所示，依赖项 \# 3 尤其典型。</span><span class="sxs-lookup"><span data-stu-id="5e056-118">This situation is shown in Figure 10-2, especially dependency \#3.</span></span>

![](./media/image2.png)

<span data-ttu-id="5e056-119">**图 10-2**。</span><span class="sxs-lookup"><span data-stu-id="5e056-119">**Figure 10-2**.</span></span> <span data-ttu-id="5e056-120">采用 HTTP 请求长链的不当设计所产生的影响</span><span class="sxs-lookup"><span data-stu-id="5e056-120">The impact of having an incorrect design featuring long chains of HTTP requests</span></span>

<span data-ttu-id="5e056-121">即使每个依赖项本身都具有卓越的可用性，在分布式和基于云的系统中也几乎一定会出现间歇性故障。</span><span class="sxs-lookup"><span data-stu-id="5e056-121">Intermittent failure is virtually guaranteed in a distributed and cloud based system, even if every dependency itself has excellent availability.</span></span> <span data-ttu-id="5e056-122">这应是需要考虑的事实。</span><span class="sxs-lookup"><span data-stu-id="5e056-122">This should be a fact you need to consider.</span></span>

<span data-ttu-id="5e056-123">如果不设计和实现能保证容错的技术，那么即使是很短的故障时间也会被放大。</span><span class="sxs-lookup"><span data-stu-id="5e056-123">If you do not design and implement techniques to ensure fault tolerance, even small downtimes can be amplified.</span></span> <span data-ttu-id="5e056-124">例如，50 个依赖项，每个具有 99.99% 的可用性，因为这种连锁效应，每个月会产生几个小时的故障时间。</span><span class="sxs-lookup"><span data-stu-id="5e056-124">As an example, 50 dependencies each with 99.99% of availability would result in several hours of downtime each month because of this ripple effect.</span></span> <span data-ttu-id="5e056-125">如果微服务依赖项在处理大量请求时出现失败错误，那么该失败错误可能会迅速蔓延到每个服务中的所有可用请求线程，然后导致整个应用程序出现故障。</span><span class="sxs-lookup"><span data-stu-id="5e056-125">When a microservice dependency fails while handling a high volume of requests, that failure can quickly saturate all available request threads in each service and crash the whole application.</span></span>

![](./media/image3.png)

<span data-ttu-id="5e056-126">**图 10-3**。</span><span class="sxs-lookup"><span data-stu-id="5e056-126">**Figure 10-3**.</span></span> <span data-ttu-id="5e056-127">由微服务使用同步 HTTP 调用长链放大的部分失败错误</span><span class="sxs-lookup"><span data-stu-id="5e056-127">Partial failure amplified by microservices with long chains of synchronous HTTP calls</span></span>

<span data-ttu-id="5e056-128">为最大程度地减少此问题，我们在“异步微服务集成强制实现微服务自治性”一节中（体系结构章节）建议在内部微服务间使用异步通信。</span><span class="sxs-lookup"><span data-stu-id="5e056-128">To minimize this problem, in the section "*Asynchronous microservice integration enforce microservice’s autonomy*” (in the architecture chapter), we encouraged you to use asynchronous communication across the internal microservices.</span></span> <span data-ttu-id="5e056-129">我们在下一节会简要介绍更多信息。</span><span class="sxs-lookup"><span data-stu-id="5e056-129">We briefly explain more in the next section.</span></span>

<span data-ttu-id="5e056-130">此外，必须要设计可处理部分失败错误的微服务和客户端应用程序 - 即构建弹性微服务和客户端应用程序。</span><span class="sxs-lookup"><span data-stu-id="5e056-130">In addition, it is essential that you design your microservices and client applications to handle partial failures—that is, to build resilient microservices and client applications.</span></span>


>[!div class="step-by-step"]
<span data-ttu-id="5e056-131">[上一页](index.md)
[下一页](partial-failure-strategies.md)</span><span class="sxs-lookup"><span data-stu-id="5e056-131">[Previous](index.md)
[Next](partial-failure-strategies.md)</span></span>
