---
title: 实现可复原的应用程序
description: 了解恢复能力，这是微服务体系结构中的核心概念。 必须了解如何在发生瞬间失败时进行适当的处理。
ms.date: 01/30/2020
ms.openlocfilehash: 46276a6b9b36a494bfae657275692ca9d5554d86
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/15/2020
ms.locfileid: "78847227"
---
# <a name="implement-resilient-applications"></a><span data-ttu-id="fbe78-104">实现可复原的应用程序</span><span class="sxs-lookup"><span data-stu-id="fbe78-104">Implement resilient applications</span></span>

<span data-ttu-id="fbe78-105">微服务和基于云的应用程序必须允许最终必然会发生的部分故障。*必须设计应用程序，使其可从这些部分失败中恢复。*</span><span class="sxs-lookup"><span data-stu-id="fbe78-105">*Your microservice and cloud-based applications must embrace the partial failures that will certainly occur eventually. You must design your application to be resilient to those partial failures.*</span></span>

<span data-ttu-id="fbe78-106">恢复能力是指从故障中恢复并继续工作的能力。</span><span class="sxs-lookup"><span data-stu-id="fbe78-106">Resiliency is the ability to recover from failures and continue to function.</span></span> <span data-ttu-id="fbe78-107">这并不是指避免失败，而是接受会发生失败这一事实，并以能够避免停机或数据丢失的方式对失败做出响应。</span><span class="sxs-lookup"><span data-stu-id="fbe78-107">It isn't about avoiding failures but accepting the fact that failures will happen and responding to them in a way that avoids downtime or data loss.</span></span> <span data-ttu-id="fbe78-108">恢复的目标是使应用程序在发生故障后回到完全正常运行的状态。</span><span class="sxs-lookup"><span data-stu-id="fbe78-108">The goal of resiliency is to return the application to a fully functioning state after a failure.</span></span>

<span data-ttu-id="fbe78-109">设计和部署基于微服务的应用程序已经非常具有挑战性。</span><span class="sxs-lookup"><span data-stu-id="fbe78-109">It's challenging enough to design and deploy a microservices-based application.</span></span> <span data-ttu-id="fbe78-110">然而还需要让应用程序在必然发生某种故障的环境中保持正常运行。</span><span class="sxs-lookup"><span data-stu-id="fbe78-110">But you also need to keep your application running in an environment where some sort of failure is certain.</span></span> <span data-ttu-id="fbe78-111">因此，应用程序应具有恢复能力。</span><span class="sxs-lookup"><span data-stu-id="fbe78-111">Therefore, your application should be resilient.</span></span> <span data-ttu-id="fbe78-112">应将其设计为能够处理部分故障，如网络中断或者云中节点或 VM 故障。</span><span class="sxs-lookup"><span data-stu-id="fbe78-112">It should be designed to cope with partial failures, like network outages or nodes or VMs crashing in the cloud.</span></span> <span data-ttu-id="fbe78-113">甚至将微服务（容器）移动到群集内的另一个节点，也可能导致应用程序出现间歇性的功能短缺故障。</span><span class="sxs-lookup"><span data-stu-id="fbe78-113">Even microservices (containers) being moved to a different node within a cluster can cause intermittent short failures within the application.</span></span>

<span data-ttu-id="fbe78-114">应用程序的各个组件还应涵盖运行状况监视功能。</span><span class="sxs-lookup"><span data-stu-id="fbe78-114">The many individual components of your application should also incorporate health monitoring features.</span></span> <span data-ttu-id="fbe78-115">遵循本章节中的准则，可创建这样的应用程序：即使在基于云的复杂部署中出现短暂停机或暂时中断，它也能平稳运行。</span><span class="sxs-lookup"><span data-stu-id="fbe78-115">By following the guidelines in this chapter, you can create an application that can work smoothly in spite of transient downtime or the normal hiccups that occur in complex and cloud-based deployments.</span></span>

>[!IMPORTANT]
> <span data-ttu-id="fbe78-116">在版本 3.0.0 之前，eShopOnContainer 一直在使用 [Polly 库](http://www.thepollyproject.org/)通过[类型化客户端](./use-httpclientfactory-to-implement-resilient-http-requests.md)实现复原。</span><span class="sxs-lookup"><span data-stu-id="fbe78-116">eShopOnContainer had been using the [Polly library](http://www.thepollyproject.org/) to implement resiliency using [Typed Clients](./use-httpclientfactory-to-implement-resilient-http-requests.md) up until the release 3.0.0.</span></span>
>
> <span data-ttu-id="fbe78-117">从版本 3.0.0 开始，HTTP 调用复原通过使用 [Linkerd 网格](https://linkerd.io/)来实现，该网格在 Kubernetes 群集内以透明且可配置的方式处理重试，而不必在代码中处理这些问题。</span><span class="sxs-lookup"><span data-stu-id="fbe78-117">Starting with release 3.0.0, the HTTP calls resiliency is implemented using a [Linkerd mesh](https://linkerd.io/), that handles retries in a transparent and configurable fashion, within a Kubernetes cluster, without having to handle those concerns in the code.</span></span>
>
> <span data-ttu-id="fbe78-118">Polly 库仍用于向数据库连接添加复原能力，尤其是在启动服务时。</span><span class="sxs-lookup"><span data-stu-id="fbe78-118">The Polly library is still used to add resilience to database connections, specially while starting up the services.</span></span>

>[!WARNING]
> <span data-ttu-id="fbe78-119">本部分中的所有代码示例在使用 Linkerd 之前都是有效的，不会进行更新以反映当前实际代码。</span><span class="sxs-lookup"><span data-stu-id="fbe78-119">All code samples in this section were valid before using Linkerd and are not updated to reflect the current actual code.</span></span> <span data-ttu-id="fbe78-120">因此，它们在本部分的上下文中是有意义的。</span><span class="sxs-lookup"><span data-stu-id="fbe78-120">So they make sense in the context of this section.</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="fbe78-121">[上一页](../microservice-ddd-cqrs-patterns/microservice-application-layer-implementation-web-api.md)
>[下一页](handle-partial-failure.md)</span><span class="sxs-lookup"><span data-stu-id="fbe78-121">[Previous](../microservice-ddd-cqrs-patterns/microservice-application-layer-implementation-web-api.md)
[Next](handle-partial-failure.md)</span></span>
