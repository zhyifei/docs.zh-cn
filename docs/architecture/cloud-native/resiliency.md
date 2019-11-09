---
title: 云本机复原能力
description: 构建适用于 Azure 的云本机 .NET 应用 |云本机复原
ms.date: 06/30/2019
ms.openlocfilehash: 680542abc5d8c43c577321d5ae834f0a13290da3
ms.sourcegitcommit: 55f438d4d00a34b9aca9eedaac3f85590bb11565
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/23/2019
ms.locfileid: "73841041"
---
# <a name="cloud-native-resiliency"></a><span data-ttu-id="688d5-103">云本机复原能力</span><span class="sxs-lookup"><span data-stu-id="688d5-103">Cloud-native resiliency</span></span>

[!INCLUDE [book-preview](../../../includes/book-preview.md)]

<span data-ttu-id="688d5-104">复原能力是指系统能够应对故障，并仍能正常工作。</span><span class="sxs-lookup"><span data-stu-id="688d5-104">Resiliency is the ability of your system to react to failure and still remain functional.</span></span> <span data-ttu-id="688d5-105">这并不是为了避免失败。</span><span class="sxs-lookup"><span data-stu-id="688d5-105">It isn't about avoiding failure.</span></span> <span data-ttu-id="688d5-106">但这就是在基于云的系统中接受该故障是不可避免的，并生成应用程序来响应它。</span><span class="sxs-lookup"><span data-stu-id="688d5-106">But it's about accepting that failure is inevitable in cloud-based systems and building your application to respond to it.</span></span> <span data-ttu-id="688d5-107">复原的最终目标是在故障后将应用程序恢复到完全正常运行的状态。</span><span class="sxs-lookup"><span data-stu-id="688d5-107">The end-goal of resiliency is to return the application to a fully functioning state after a failure.</span></span>

<span data-ttu-id="688d5-108">与传统的单一应用程序不同，在一个进程中，一切都一起运行，云本机系统采用分布式体系结构，如图6-1 所示：</span><span class="sxs-lookup"><span data-stu-id="688d5-108">Unlike traditional monolithic applications, where everything runs together in a single process, cloud-native systems embrace distributed architecture as shown in Figure 6-1:</span></span>

![分布式云-本机环境](./media/distributed-cloud-native-environment.png)

<span data-ttu-id="688d5-110">**图 6-1**。</span><span class="sxs-lookup"><span data-stu-id="688d5-110">**Figure 6-1.**</span></span> <span data-ttu-id="688d5-111">分布式云-本机环境</span><span class="sxs-lookup"><span data-stu-id="688d5-111">Distributed cloud-native environment</span></span>

<span data-ttu-id="688d5-112">在上图中，请注意每个客户端、微服务和基于云的[后备服务](https://12factor.net/backing-services)如何作为单独的进程运行，跨不同的服务器运行，并通过基于网络的调用进行通信。</span><span class="sxs-lookup"><span data-stu-id="688d5-112">In the previous figure, note how each client, microservice, and cloud-based [backing service](https://12factor.net/backing-services) executes as a separate process, running across different servers, all communicating via network-based calls.</span></span>

<span data-ttu-id="688d5-113">那么，会出现什么问题呢？</span><span class="sxs-lookup"><span data-stu-id="688d5-113">So, what could go wrong?</span></span>

- <span data-ttu-id="688d5-114">意外的[网络延迟](https://www.techopedia.com/definition/8553/network-latency)。</span><span class="sxs-lookup"><span data-stu-id="688d5-114">Unexpected [network latency](https://www.techopedia.com/definition/8553/network-latency).</span></span>
- <span data-ttu-id="688d5-115">[暂时性故障](https://docs.microsoft.com/azure/architecture/best-practices/transient-faults)（暂时性网络连接错误）。</span><span class="sxs-lookup"><span data-stu-id="688d5-115">[Transient faults](https://docs.microsoft.com/azure/architecture/best-practices/transient-faults) (temporary network connectivity errors).</span></span>
- <span data-ttu-id="688d5-116">由长时间运行的同步操作阻止。</span><span class="sxs-lookup"><span data-stu-id="688d5-116">Blocking by a long-running synchronous operation.</span></span>
- <span data-ttu-id="688d5-117">已崩溃并且正在重新启动或移动的主机进程。</span><span class="sxs-lookup"><span data-stu-id="688d5-117">A host process that has crashed and is being restarted or moved.</span></span>
- <span data-ttu-id="688d5-118">一段时间后无法响应的重载微服务。</span><span class="sxs-lookup"><span data-stu-id="688d5-118">An overloaded microservice that can't respond for a short time.</span></span>
- <span data-ttu-id="688d5-119">正在进行的 DevOps 操作，例如更新或缩放操作。</span><span class="sxs-lookup"><span data-stu-id="688d5-119">An in-flight DevOps operation such as an update or scaling operation.</span></span>
- <span data-ttu-id="688d5-120">Orchestrator 操作，如将服务从一个节点移到另一个节点。</span><span class="sxs-lookup"><span data-stu-id="688d5-120">An Orchestrator operation such as moving a service from one node to another.</span></span>
- <span data-ttu-id="688d5-121">商用硬件发生硬件故障。</span><span class="sxs-lookup"><span data-stu-id="688d5-121">Hardware failures from commodity hardware.</span></span>

<span data-ttu-id="688d5-122">在将分布式服务部署到基于云的基础结构中时，先前列表中的因素非常真实，你必须构建保守来处理它们。</span><span class="sxs-lookup"><span data-stu-id="688d5-122">When deploying distributed services into cloud-based infrastructure, the factors from the previous list become very real and you must architect and develop defensively to deal with them.</span></span>

<span data-ttu-id="688d5-123">在小规模的分布式系统中，故障不会频繁，但随着系统的扩大和缩小，你可能会在部分故障变为正常操作时遇到更多的问题。</span><span class="sxs-lookup"><span data-stu-id="688d5-123">In a small-scale distributed system, failure will be less frequent, but as a system scales up and out, you can expect to experience more of these issues to a point where partial failure becomes normal operation.</span></span>

<span data-ttu-id="688d5-124">因此，您的应用程序和基础结构必须具有复原能力。</span><span class="sxs-lookup"><span data-stu-id="688d5-124">Therefore, your application and infrastructure must be resilient.</span></span> <span data-ttu-id="688d5-125">在以下部分中，我们将探讨可添加到应用程序中的防御性技术，以及可以利用的内置云功能，以帮助你对用户体验进行验证。</span><span class="sxs-lookup"><span data-stu-id="688d5-125">In the following sections, we'll explore defensive techniques that you can add to your application and built-in cloud features that you can leverage to help bullet-proof your user's experience.</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="688d5-126">[上一页](azure-data-storage.md)
>[下一页](application-resiliency-patterns.md)</span><span class="sxs-lookup"><span data-stu-id="688d5-126">[Previous](azure-data-storage.md)
[Next](application-resiliency-patterns.md)</span></span>
