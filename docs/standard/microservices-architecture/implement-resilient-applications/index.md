---
title: 实现具有恢复能力的应用程序
description: 适用于容器化 .NET 应用程序的 .NET 微服务体系结构 | 实现具有恢复能力的应用程序
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 05/26/2017
ms.openlocfilehash: ddb0f54b15735b9192d2088495947588f59829a0
ms.sourcegitcommit: 979597cd8055534b63d2c6ee8322938a27d0c87b
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/29/2018
ms.locfileid: "37106046"
---
# <a name="implementing-resilient-applications"></a><span data-ttu-id="3df02-103">实现具有恢复能力的应用程序</span><span class="sxs-lookup"><span data-stu-id="3df02-103">Implementing Resilient Applications</span></span>

<span data-ttu-id="3df02-104">基于微服务和云的应用程序必须包容最终必然会发生的部分故障。需要设计应用程序，使其可从这些部分故障中恢复。</span><span class="sxs-lookup"><span data-stu-id="3df02-104">*Your microservice and cloud based applications must embrace the partial failures that will certainly occur eventually. You need to design your application so it will be resilient to those partial failures.*</span></span>

<span data-ttu-id="3df02-105">恢复能力是指从故障中恢复并继续工作的能力。</span><span class="sxs-lookup"><span data-stu-id="3df02-105">Resiliency is the ability to recover from failures and continue to function.</span></span> <span data-ttu-id="3df02-106">这并不是指避免故障，而是接受会发生故障这一事实，并以能够避免停机或数据丢失的方式对故障做出响应。</span><span class="sxs-lookup"><span data-stu-id="3df02-106">It is not about avoiding failures, but accepting the fact that failures will happen and responding to them in a way that avoids downtime or data loss.</span></span> <span data-ttu-id="3df02-107">恢复的目标是使应用程序在发生故障后回到完全正常运行的状态。</span><span class="sxs-lookup"><span data-stu-id="3df02-107">The goal of resiliency is to return the application to a fully functioning state after a failure.</span></span>

<span data-ttu-id="3df02-108">设计和部署基于微服务的应用程序已经非常具有挑战性。</span><span class="sxs-lookup"><span data-stu-id="3df02-108">It is challenging enough to design and deploy a microservices-based application.</span></span> <span data-ttu-id="3df02-109">然而还需要让应用程序在必然发生某种故障的环境中保持正常运行。</span><span class="sxs-lookup"><span data-stu-id="3df02-109">But you also need to keep your application running in an environment where some sort of failure is certain.</span></span> <span data-ttu-id="3df02-110">因此，应用程序应具有恢复能力。</span><span class="sxs-lookup"><span data-stu-id="3df02-110">Therefore, your application should be resilient.</span></span> <span data-ttu-id="3df02-111">应将其设计为能够处理部分故障，如网络中断或者云中节点或 VM 故障。</span><span class="sxs-lookup"><span data-stu-id="3df02-111">It should be designed to cope with partial failures, like network outages or nodes or VMs crashing in the cloud.</span></span> <span data-ttu-id="3df02-112">甚至将微服务（容器）移动到群集内的另一个节点，也可能导致应用程序出现间歇性的功能短缺故障。</span><span class="sxs-lookup"><span data-stu-id="3df02-112">Even microservices (containers) being moved to a different node within a cluster can cause intermittent short failures within the application.</span></span>

<span data-ttu-id="3df02-113">应用程序的各个组件还应涵盖运行状况监视功能。</span><span class="sxs-lookup"><span data-stu-id="3df02-113">The many individual components of your application should also incorporate health monitoring features.</span></span> <span data-ttu-id="3df02-114">遵循本章节中的准则，可创建这样的应用程序：即使在基于云的复杂部署中出现短暂停机或暂时中断，它也能平稳运行。</span><span class="sxs-lookup"><span data-stu-id="3df02-114">By following the guidelines in this chapter, you can create an application that can work smoothly in spite of transient downtime or the normal hiccups that occur in complex and cloud-based deployments.</span></span>


>[!div class="step-by-step"]
<span data-ttu-id="3df02-115">[上一页](../microservice-ddd-cqrs-patterns/microservice-application-layer-implementation-web-api.md)
[下一页](handle-partial-failure.md)</span><span class="sxs-lookup"><span data-stu-id="3df02-115">[Previous](../microservice-ddd-cqrs-patterns/microservice-application-layer-implementation-web-api.md)
[Next](handle-partial-failure.md)</span></span>
