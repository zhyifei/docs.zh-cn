---
title: 异步概述
description: 了解异步编程为何是一项能够简单处理多个核心上的阻塞 I/O 和并发操作的关键技术。
author: cartermp
ms.author: wiwagn
ms.date: 06/20/2016
ms.technology: dotnet-standard
ms.assetid: 1e38e9d9-8284-46ee-a15f-199adc4f26f4
ms.openlocfilehash: aa08389d896fa81dbed8a63bb22a97e151016392
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "64628796"
---
# <a name="async-overview"></a><span data-ttu-id="d4e75-103">异步概述</span><span class="sxs-lookup"><span data-stu-id="d4e75-103">Async Overview</span></span>

<span data-ttu-id="d4e75-104">不久前，人们通过购买更新的电脑和服务器来加快应用的速度，但是这种趋势已经停止了。</span><span class="sxs-lookup"><span data-stu-id="d4e75-104">Not so long ago, apps got faster simply by buying a newer PC or server and then that trend stopped.</span></span> <span data-ttu-id="d4e75-105">事实上，趋势逆转了。</span><span class="sxs-lookup"><span data-stu-id="d4e75-105">In fact, it reversed.</span></span> <span data-ttu-id="d4e75-106">手机配备 1ghz 单核 ARM 芯片，而服务器工作负荷转向 VM。</span><span class="sxs-lookup"><span data-stu-id="d4e75-106">Mobile phones appeared with 1ghz single core ARM chips and server workloads transitioned to VMs.</span></span> <span data-ttu-id="d4e75-107">用户仍青睐响应式 UI，企业所有者则希望拥有能随着其业务缩放的服务器。</span><span class="sxs-lookup"><span data-stu-id="d4e75-107">Users still want responsive UI and business owners want servers that scale with their business.</span></span> <span data-ttu-id="d4e75-108">向手机和云的转变以及超过 30 亿使用 Internet 的人口引领着新软件模式的形成。</span><span class="sxs-lookup"><span data-stu-id="d4e75-108">The transition to mobile and cloud and an internet-connected population of >3B users has resulted in a new set of software patterns.</span></span> 

* <span data-ttu-id="d4e75-109">有了高应用存储率，客户端应用有望保持始终开启，始终连接的状态，并且可持续响应用户交互（例如，触摸）！</span><span class="sxs-lookup"><span data-stu-id="d4e75-109">Client applications are expected to be always-on, always-connected and constantly responsive to user interaction (for example, touch) with high app store ratings!</span></span>
* <span data-ttu-id="d4e75-110">用户期望服务能够通过平稳地扩展和收缩来应对流量高峰。</span><span class="sxs-lookup"><span data-stu-id="d4e75-110">Services are expected to handle spikes in traffic by gracefully scaling up and down.</span></span> 

<span data-ttu-id="d4e75-111">异步编程是一项关键技术，可以直接处理多个核心上的阻塞 I/O 和并发操作。</span><span class="sxs-lookup"><span data-stu-id="d4e75-111">Async programming is a key technique that makes it straightforward to handle blocking I/O and concurrent operations on multiple cores.</span></span> <span data-ttu-id="d4e75-112">.NET 可以通过 C#、VB 和 F# 中的易用语言级异步编程模型提高应用和服务的响应速度和灵活性。</span><span class="sxs-lookup"><span data-stu-id="d4e75-112">.NET provides the capability for apps and services to be responsive and elastic with easy-to-use, language-level asynchronous programming models in C#, VB, and F#.</span></span>

## <a name="why-write-async-code"></a><span data-ttu-id="d4e75-113">为什么要编写异步代码？</span><span class="sxs-lookup"><span data-stu-id="d4e75-113">Why Write Async Code?</span></span>

<span data-ttu-id="d4e75-114">新型应用广泛使用文件和网络 I/O。</span><span class="sxs-lookup"><span data-stu-id="d4e75-114">Modern apps make extensive use of file and networking I/O.</span></span> <span data-ttu-id="d4e75-115">默认情况下 I/O API 一般会阻塞，导致糟糕的用户体验和硬件利用率，除非希望学习和使用富有挑战的模式。</span><span class="sxs-lookup"><span data-stu-id="d4e75-115">I/O APIs traditionally block by default, resulting in poor user experiences and hardware utilization unless you want to learn and use challenging patterns.</span></span> <span data-ttu-id="d4e75-116">基于任务的异步 API 和语言级异步编程模型改变了这种模型，只需了解几个新概念就可默认进行异步执行。</span><span class="sxs-lookup"><span data-stu-id="d4e75-116">Task-based async APIs and the language-level asynchronous programming model invert this model, making async execution the default with few new concepts to learn.</span></span>

<span data-ttu-id="d4e75-117">异步代码具有以下特点：</span><span class="sxs-lookup"><span data-stu-id="d4e75-117">Async code has the following characteristics:</span></span>

* <span data-ttu-id="d4e75-118">等待 I/O 请求返回的同时，可通过生成处理更多请求的线程，处理更多的服务器请求。</span><span class="sxs-lookup"><span data-stu-id="d4e75-118">Handles more server requests by yielding threads to handle more requests while waiting for I/O requests to return.</span></span>
* <span data-ttu-id="d4e75-119">等待 I/O 请求的同时生成 UI 交互线程，并通过将长时间运行的工作转换到其他 CPU 核心，让 UI 的响应速度更快。</span><span class="sxs-lookup"><span data-stu-id="d4e75-119">Enables UIs to be more responsive by yielding threads to UI interaction while waiting for I/O requests and by transitioning long-running work to other CPU cores.</span></span>
* <span data-ttu-id="d4e75-120">许多较新的 .NET APIs 都是异步的。</span><span class="sxs-lookup"><span data-stu-id="d4e75-120">Many of the newer .NET APIs are asynchronous.</span></span>
* <span data-ttu-id="d4e75-121">在 .NET 中编写异步代码很简单！</span><span class="sxs-lookup"><span data-stu-id="d4e75-121">It's easy to write async code in .NET!</span></span>

## <a name="whats-next"></a><span data-ttu-id="d4e75-122">后续步骤</span><span class="sxs-lookup"><span data-stu-id="d4e75-122">What's next?</span></span>

<span data-ttu-id="d4e75-123">有关详细信息，请参阅[异步深度剖析](async-in-depth.md)主题。</span><span class="sxs-lookup"><span data-stu-id="d4e75-123">For more information, see the [Async in depth](async-in-depth.md) topic.</span></span>

<span data-ttu-id="d4e75-124">[异步编程模式](asynchronous-programming-patterns/index.md)主题概述了 .NET 支持的三个异步编程模式：</span><span class="sxs-lookup"><span data-stu-id="d4e75-124">The [Asynchronous Programming Patterns](asynchronous-programming-patterns/index.md) topic provides an overview of the three asynchronous programming patterns supported in .NET:</span></span>  
  
- <span data-ttu-id="d4e75-125">[异步编程模型 (APM)](asynchronous-programming-patterns/asynchronous-programming-model-apm.md)（旧版）</span><span class="sxs-lookup"><span data-stu-id="d4e75-125">[Asynchronous Programming Model (APM)](asynchronous-programming-patterns/asynchronous-programming-model-apm.md) (legacy)</span></span>  
  
- <span data-ttu-id="d4e75-126">[基于事件的异步模式 (EAP)](asynchronous-programming-patterns/event-based-asynchronous-pattern-eap.md)（旧版）</span><span class="sxs-lookup"><span data-stu-id="d4e75-126">[Event-based Asynchronous Pattern (EAP)](asynchronous-programming-patterns/event-based-asynchronous-pattern-eap.md) (legacy)</span></span>  
  
- <span data-ttu-id="d4e75-127">[基于任务的异步模式 (TAP)](asynchronous-programming-patterns/task-based-asynchronous-pattern-tap.md)（建议用于新开发）</span><span class="sxs-lookup"><span data-stu-id="d4e75-127">[Task-based Asynchronous Pattern (TAP)](asynchronous-programming-patterns/task-based-asynchronous-pattern-tap.md) (recommended for new development)</span></span>  

<span data-ttu-id="d4e75-128">若要详细了解推荐的基于任务的编程模型，请参阅[基于任务的异步编程](parallel-programming/task-based-asynchronous-programming.md)主题。</span><span class="sxs-lookup"><span data-stu-id="d4e75-128">For more information about recommended task-based programming model, see the [Task-based asynchronous programming](parallel-programming/task-based-asynchronous-programming.md) topic.</span></span>
