---
title: "异步概述"
description: "了解异步编程为何是一项能够简单处理多个核心上的阻塞 I/O 和并发操作的关键技术。"
keywords: .NET, .NET Core
author: cartermp
ms.author: wiwagn
ms.date: 06/20/2016
ms.topic: article
ms.prod: .net
ms.technology: dotnet-standard
ms.devlang: dotnet
ms.assetid: 1e38e9d9-8284-46ee-a15f-199adc4f26f4
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: f2dddc21dfb124fe97c397a156743981a67e4037
ms.sourcegitcommit: e7f04439d78909229506b56935a1105a4149ff3d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/23/2017
---
# <a name="async-overview"></a><span data-ttu-id="c0cc0-104">异步概述</span><span class="sxs-lookup"><span data-stu-id="c0cc0-104">Async Overview</span></span>

<span data-ttu-id="c0cc0-105">不久前，人们通过购买更新的电脑和服务器来加快应用的速度，但是这种趋势已经停止了。</span><span class="sxs-lookup"><span data-stu-id="c0cc0-105">Not so long ago, apps got faster simply by buying a newer PC or server and then that trend stopped.</span></span> <span data-ttu-id="c0cc0-106">事实上，趋势逆转了。</span><span class="sxs-lookup"><span data-stu-id="c0cc0-106">In fact, it reversed.</span></span> <span data-ttu-id="c0cc0-107">手机配备 1ghz 单核 ARM 芯片，而服务器工作负荷转向 VM。</span><span class="sxs-lookup"><span data-stu-id="c0cc0-107">Mobile phones appeared with 1ghz single core ARM chips and server workloads transitioned to VMs.</span></span> <span data-ttu-id="c0cc0-108">用户仍青睐响应式 UI，企业所有者则希望拥有能随着其业务缩放的服务器。</span><span class="sxs-lookup"><span data-stu-id="c0cc0-108">Users still want responsive UI and business owners want servers that scale with their business.</span></span> <span data-ttu-id="c0cc0-109">向手机和云的转变以及超过 30 亿使用 Internet 的人口引领着新软件模式的形成。</span><span class="sxs-lookup"><span data-stu-id="c0cc0-109">The transition to mobile and cloud and an internet-connected population of >3B users has resulted in a new set of software patterns.</span></span> 

* <span data-ttu-id="c0cc0-110">有了高应用存储率，客户端应用有望保持始终开启，始终连接的状态，并且可持续响应用户交互（例如，触摸）！</span><span class="sxs-lookup"><span data-stu-id="c0cc0-110">Client applications are expected to be always-on, always-connected and constantly responsive to user interaction (for example, touch) with high app store ratings!</span></span>
* <span data-ttu-id="c0cc0-111">用户期望服务能够通过平稳地扩展和收缩来应对流量高峰。</span><span class="sxs-lookup"><span data-stu-id="c0cc0-111">Services are expected to handle spikes in traffic by gracefully scaling up and down.</span></span> 

<span data-ttu-id="c0cc0-112">异步编程是一项关键技术，使得能够简单处理多个核心上的阻塞 I/O 和并发操作。</span><span class="sxs-lookup"><span data-stu-id="c0cc0-112">Async programming is a key technique that makes it straightforward to handle blocking I/O and concurrent operations on multiple cores.</span></span> <span data-ttu-id="c0cc0-113">通过 C#、VB 和 F## 中易于使用的语言级异步编程模型，.NET 可为应用和服务提供使其变得可响应且富有弹性。</span><span class="sxs-lookup"><span data-stu-id="c0cc0-113">.NET provides the capability for apps and services to be responsive and elastic with easy-to-use, language-level asynchronous programming models in C#, VB, and F#.</span></span>

## <a name="why-write-async-code"></a><span data-ttu-id="c0cc0-114">为什么要编写异步代码？</span><span class="sxs-lookup"><span data-stu-id="c0cc0-114">Why Write Async Code?</span></span>

<span data-ttu-id="c0cc0-115">新型应用广泛使用文件和网络 I/O。</span><span class="sxs-lookup"><span data-stu-id="c0cc0-115">Modern apps make extensive use of file and networking I/O.</span></span> <span data-ttu-id="c0cc0-116">默认情况下 I/O API 一般会阻塞，导致糟糕的用户体验和硬件利用率，除非希望学习和使用富有挑战的模式。</span><span class="sxs-lookup"><span data-stu-id="c0cc0-116">I/O APIs traditionally block by default, resulting in poor user experiences and hardware utilization unless you want to learn and use challenging patterns.</span></span> <span data-ttu-id="c0cc0-117">基于任务的异步 API 和语言级异步编程模型改变了这种模型，只需了解几个新概念就可默认进行异步执行。</span><span class="sxs-lookup"><span data-stu-id="c0cc0-117">Task-based async APIs and the language-level asynchronous programming model invert this model, making async execution the default with few new concepts to learn.</span></span>

<span data-ttu-id="c0cc0-118">异步代码具有以下特点：</span><span class="sxs-lookup"><span data-stu-id="c0cc0-118">Async code has the following characteristics:</span></span>

* <span data-ttu-id="c0cc0-119">等待 I/O 请求返回的同时，可通过生成处理更多请求的线程，处理更多的服务器请求。</span><span class="sxs-lookup"><span data-stu-id="c0cc0-119">Handles more server requests by yielding threads to handle more requests while waiting for I/O requests to return.</span></span>
* <span data-ttu-id="c0cc0-120">等待 I/O 请求的同时生成 UI 交互线程，并通过将长时间运行的工作转换到其他 CPU 核心，让 UI 的响应速度更快。</span><span class="sxs-lookup"><span data-stu-id="c0cc0-120">Enables UIs to be more responsive by yielding threads to UI interaction while waiting for I/O requests and by transitioning long-running work to other CPU cores.</span></span>
* <span data-ttu-id="c0cc0-121">许多较新的 .NET APIs 都是异步的。</span><span class="sxs-lookup"><span data-stu-id="c0cc0-121">Many of the newer .NET APIs are asynchronous.</span></span>
* <span data-ttu-id="c0cc0-122">在 .NET 中编写异步代码很简单！</span><span class="sxs-lookup"><span data-stu-id="c0cc0-122">It's easy to write async code in .NET!</span></span>

## <a name="whats-next"></a><span data-ttu-id="c0cc0-123">后续步骤</span><span class="sxs-lookup"><span data-stu-id="c0cc0-123">What's next?</span></span>

<span data-ttu-id="c0cc0-124">若要深入了解异步概念和编程，请参阅[深入了解异步](async-in-depth.md)和[基于任务的异步编程](~/docs/standard/parallel-programming/task-based-asynchronous-programming.md)。</span><span class="sxs-lookup"><span data-stu-id="c0cc0-124">For a deep dive into async concepts and programming, see [Async in depth](async-in-depth.md) and [Task-based asynchronous programming](~/docs/standard/parallel-programming/task-based-asynchronous-programming.md).</span></span>
