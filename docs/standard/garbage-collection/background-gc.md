---
title: 后台垃圾回收
description: 了解 .NET 中的后台垃圾回收，以及工作站和服务器垃圾回收有哪些区别。
ms.date: 04/21/2020
helpviewer_keywords:
- garbage collection, background
- background garbage collection
ms.openlocfilehash: dcb1d348e679e07646273b8fbc4ea29b44ee4974
ms.sourcegitcommit: 73aa9653547a1cd70ee6586221f79cc29b588ebd
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2020
ms.locfileid: "82103495"
---
# <a name="background-garbage-collection"></a><span data-ttu-id="4692e-103">后台垃圾回收</span><span class="sxs-lookup"><span data-stu-id="4692e-103">Background garbage collection</span></span>

<span data-ttu-id="4692e-104">在后台垃圾回收 (GC) 中，在进行第 2 代回收的过程中，将会根据需要收集暂时代（第 0 代和第 1 代）。</span><span class="sxs-lookup"><span data-stu-id="4692e-104">In background garbage collection (GC), ephemeral generations (0 and 1) are collected as needed while the collection of generation 2 is in progress.</span></span> <span data-ttu-id="4692e-105">后台垃圾回收是在一个或多个专用线程上执行的，具体取决于它是后台还是服务器 GC，它只适用于第 2 代回收。</span><span class="sxs-lookup"><span data-stu-id="4692e-105">Background garbage collection is performed on one or more dedicated threads, depending on whether it's background or server GC, and applies only to generation 2 collections.</span></span>

<span data-ttu-id="4692e-106">默认启用后台垃圾回收。</span><span class="sxs-lookup"><span data-stu-id="4692e-106">Background garbage collection is enabled by default.</span></span> <span data-ttu-id="4692e-107">可以在 .NET Framework 应用程序中使用 [gcConcurrent](../../../docs/framework/configure-apps/file-schema/runtime/gcconcurrent-element.md) 配置设置或 .NET Core 应用中的 [System.GC.Concurrent](../../core/run-time-config/garbage-collector.md#systemgcconcurrentcomplus_gcconcurrent) 来启用或禁用后台垃圾回收。</span><span class="sxs-lookup"><span data-stu-id="4692e-107">It can be enabled or disabled with the [gcConcurrent](../../../docs/framework/configure-apps/file-schema/runtime/gcconcurrent-element.md) configuration setting in .NET Framework apps or the [System.GC.Concurrent](../../core/run-time-config/garbage-collector.md#systemgcconcurrentcomplus_gcconcurrent) setting in .NET Core apps.</span></span>

> [!NOTE]
> <span data-ttu-id="4692e-108">后台垃圾回收替换在 .NET Framework 4 及更高版本中可用的[并行垃圾回收](#concurrent-garbage-collection)。</span><span class="sxs-lookup"><span data-stu-id="4692e-108">Background garbage collection replaces [concurrent garbage collection](#concurrent-garbage-collection) and is available in .NET Framework 4 and later versions.</span></span> <span data-ttu-id="4692e-109">在 .NET Framework 4 中，仅支持工作站垃圾回收  。</span><span class="sxs-lookup"><span data-stu-id="4692e-109">In .NET Framework 4, it's supported only for *workstation* garbage collection.</span></span> <span data-ttu-id="4692e-110">从 .NET Framework 4.5 开始，后台垃圾回收可用于工作站和服务器垃圾回收   。</span><span class="sxs-lookup"><span data-stu-id="4692e-110">Starting with .NET Framework 4.5, background garbage collection is available for both *workstation* and *server* garbage collection.</span></span>

<span data-ttu-id="4692e-111">后台垃圾回收期间对暂时代的回收称为“前台”垃圾回收  。</span><span class="sxs-lookup"><span data-stu-id="4692e-111">A collection on ephemeral generations during background garbage collection is known as *foreground* garbage collection.</span></span> <span data-ttu-id="4692e-112">发生前台垃圾回收时，所有托管线程都将被挂起。</span><span class="sxs-lookup"><span data-stu-id="4692e-112">When foreground garbage collections occur, all managed threads are suspended.</span></span>

<span data-ttu-id="4692e-113">当后台垃圾回收正在进行并且你已在第 0 代中分配了足够的对象时，CLR 将执行第 0 代或第 1 代前台垃圾回收。</span><span class="sxs-lookup"><span data-stu-id="4692e-113">When background garbage collection is in progress and you've allocated enough objects in generation 0, the CLR performs a generation 0 or generation 1 foreground garbage collection.</span></span> <span data-ttu-id="4692e-114">专用的后台垃圾回收线程将在常见的安全点上进行检查以确定是否存在对前台垃圾回收的请求。</span><span class="sxs-lookup"><span data-stu-id="4692e-114">The dedicated background garbage collection thread checks at frequent safe points to determine whether there is a request for foreground garbage collection.</span></span> <span data-ttu-id="4692e-115">如果存在，则后台回收将挂起自身以便前台垃圾回收可以发生。</span><span class="sxs-lookup"><span data-stu-id="4692e-115">If there is, the background collection suspends itself so that foreground garbage collection can occur.</span></span> <span data-ttu-id="4692e-116">在前台垃圾回收完成之后，专用的后台垃圾回收线程和用户线程将继续。</span><span class="sxs-lookup"><span data-stu-id="4692e-116">After the foreground garbage collection is completed, the dedicated background garbage collection threads and user threads resume.</span></span>

<span data-ttu-id="4692e-117">后台垃圾回收可以消除并发垃圾回收所带来的分配限制，因为在后台垃圾回收期间，可发生暂时垃圾回收。</span><span class="sxs-lookup"><span data-stu-id="4692e-117">Background garbage collection removes allocation restrictions imposed by concurrent garbage collection, because ephemeral garbage collections can occur during background garbage collection.</span></span> <span data-ttu-id="4692e-118">后台垃圾回收可以删除暂存世代中的死对象。</span><span class="sxs-lookup"><span data-stu-id="4692e-118">Background garbage collection can remove dead objects in ephemeral generations.</span></span> <span data-ttu-id="4692e-119">如果需要，它还可以在第 1 代垃圾回收期间扩展堆。</span><span class="sxs-lookup"><span data-stu-id="4692e-119">It can also expand the heap if needed during a generation 1 garbage collection.</span></span>

## <a name="background-workstation-vs-server-gc"></a><span data-ttu-id="4692e-120">后台工作站与服务器 GC</span><span class="sxs-lookup"><span data-stu-id="4692e-120">Background workstation vs. server GC</span></span>

<span data-ttu-id="4692e-121">从 .NET Framework 4.5 开始，后台垃圾回收可用于服务器 GC。</span><span class="sxs-lookup"><span data-stu-id="4692e-121">Starting with .NET Framework 4.5, background garbage collection is available for server GC.</span></span> <span data-ttu-id="4692e-122">服务器 GC 是服务器垃圾回收的默认模式。</span><span class="sxs-lookup"><span data-stu-id="4692e-122">Background GC is the default mode for server garbage collection.</span></span>

<span data-ttu-id="4692e-123">后台服务器垃圾回收与后台工作站垃圾回收具有类似功能，但有一些不同之处：</span><span class="sxs-lookup"><span data-stu-id="4692e-123">Background server garbage collection functions similarly to background workstation garbage collection, but there are a few differences:</span></span>

- <span data-ttu-id="4692e-124">后台工作区域垃圾回收使用一个专用的后台垃圾回收线程，而后台服务器垃圾回收使用多个线程。</span><span class="sxs-lookup"><span data-stu-id="4692e-124">Background workstation garbage collection uses one dedicated background garbage collection thread, whereas background server garbage collection uses multiple threads.</span></span> <span data-ttu-id="4692e-125">通常一个逻辑处理器有一个专用线程。</span><span class="sxs-lookup"><span data-stu-id="4692e-125">Typically, there's a dedicated thread for each logical processor.</span></span>

- <span data-ttu-id="4692e-126">不同于工作站后台垃圾回收线程，这些后台服务器 GC 线程不会超时。</span><span class="sxs-lookup"><span data-stu-id="4692e-126">Unlike the workstation background garbage collection thread, the background server GC threads do not time out.</span></span>

<span data-ttu-id="4692e-127">下图显示对独立专用线程执行的后台工作站垃圾回收  ：</span><span class="sxs-lookup"><span data-stu-id="4692e-127">The following illustration shows background *workstation* garbage collection performed on a separate, dedicated thread:</span></span>

![后台工作站垃圾回收](./media/fundamentals/background-workstation-garbage-collection.png)

<span data-ttu-id="4692e-129">下图显示对独立专用线程执行的后台服务器垃圾回收  ：</span><span class="sxs-lookup"><span data-stu-id="4692e-129">The following illustration shows background *server* garbage collection performed on separate, dedicated threads:</span></span>

![后台服务器垃圾回收](./media/fundamentals/background-server-garbage-collection.png)

## <a name="concurrent-garbage-collection"></a><span data-ttu-id="4692e-131">并行垃圾回收</span><span class="sxs-lookup"><span data-stu-id="4692e-131">Concurrent garbage collection</span></span>

> [!TIP]
> <span data-ttu-id="4692e-132">本部分仅适用于：</span><span class="sxs-lookup"><span data-stu-id="4692e-132">This section applies to:</span></span>
>
> - <span data-ttu-id="4692e-133">用于工作站垃圾回收的 .NET Framework 3.5 及更早版本</span><span class="sxs-lookup"><span data-stu-id="4692e-133">.NET Framework 3.5 and earlier for workstation garbage collection</span></span>
> - <span data-ttu-id="4692e-134">用于服务器垃圾回收的 .NET Framework 4 及更早版本</span><span class="sxs-lookup"><span data-stu-id="4692e-134">.NET Framework 4 and earlier for server garbage collection</span></span>
>
> <span data-ttu-id="4692e-135">在更高的版本中，后台垃圾回收取代了并行垃圾回收。</span><span class="sxs-lookup"><span data-stu-id="4692e-135">Concurrent garbage is replaced by background garbage collection in later versions.</span></span>

<span data-ttu-id="4692e-136">在工作站或服务器垃圾回收中，你可以[启用并发垃圾回收](../../../docs/framework/configure-apps/file-schema/runtime/gcconcurrent-element.md)，以便在大多数回收期间，让各线程与执行垃圾回收的专用线程并发运行。</span><span class="sxs-lookup"><span data-stu-id="4692e-136">In workstation or server garbage collection, you can [enable concurrent garbage collection](../../../docs/framework/configure-apps/file-schema/runtime/gcconcurrent-element.md), which enables threads to run concurrently with a dedicated thread that performs the garbage collection for most of the duration of the collection.</span></span> <span data-ttu-id="4692e-137">此选项只影响第 2 代中的垃圾回收；第 0 代和第 1 代中的垃圾回收始终是非并发的，因为它们完成的速度很快。</span><span class="sxs-lookup"><span data-stu-id="4692e-137">This option affects only garbage collections in generation 2; generations 0 and 1 are always non-concurrent because they finish fast.</span></span>

<span data-ttu-id="4692e-138">并发垃圾回收通过最大程度地减少因回收引起的暂停，使交互应用程序能够更快地响应。</span><span class="sxs-lookup"><span data-stu-id="4692e-138">Concurrent garbage collection enables interactive applications to be more responsive by minimizing pauses for a collection.</span></span> <span data-ttu-id="4692e-139">在运行并发垃圾回收线程的大多数时间，托管线程可以继续运行。</span><span class="sxs-lookup"><span data-stu-id="4692e-139">Managed threads can continue to run most of the time while the concurrent garbage collection thread is running.</span></span> <span data-ttu-id="4692e-140">这可以使得在发生垃圾回收时的暂停时间更短。</span><span class="sxs-lookup"><span data-stu-id="4692e-140">This results in shorter pauses while a garbage collection is occurring.</span></span>

<span data-ttu-id="4692e-141">并发垃圾回收在一个专用线程上执行。</span><span class="sxs-lookup"><span data-stu-id="4692e-141">Concurrent garbage collection is performed on a dedicated thread.</span></span> <span data-ttu-id="4692e-142">默认情况下，CLR 将运行工作站垃圾回收，并在单处理器和多处理器计算机上同时启用并发垃圾回收。</span><span class="sxs-lookup"><span data-stu-id="4692e-142">By default, the CLR runs workstation garbage collection with concurrent garbage collection enabled on both single-processor and multi-processor computers.</span></span>

<span data-ttu-id="4692e-143">下图演示了在单独的专用线程上执行的并发垃圾回收。</span><span class="sxs-lookup"><span data-stu-id="4692e-143">The following illustration shows concurrent garbage collection performed on a separate dedicated thread.</span></span>

![并发垃圾回收线程](./media/gc-concurrent.png)

## <a name="see-also"></a><span data-ttu-id="4692e-145">请参阅</span><span class="sxs-lookup"><span data-stu-id="4692e-145">See also</span></span>

- [<span data-ttu-id="4692e-146">工作站和服务器垃圾回收</span><span class="sxs-lookup"><span data-stu-id="4692e-146">Workstation and server garbage collection</span></span>](workstation-server-gc.md)
- [<span data-ttu-id="4692e-147">用于垃圾回收的运行时配置选项</span><span class="sxs-lookup"><span data-stu-id="4692e-147">Run-time configuration options for garbage collection</span></span>](../../core/run-time-config/garbage-collector.md)
