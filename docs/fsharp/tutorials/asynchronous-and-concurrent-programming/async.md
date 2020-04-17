---
title: 异步编程
description: 了解 F# 如何基于从核心函数编程概念派生的语言级编程模型为异步提供干净的支持。
ms.date: 12/17/2018
ms.openlocfilehash: 9b2e3057c126d84474c21fde653da5bbee32938a
ms.sourcegitcommit: d9470d8b2278b33108332c05224d86049cb9484b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/17/2020
ms.locfileid: "81608031"
---
# <a name="async-programming-in-f"></a><span data-ttu-id="58453-103">F 中的异步编程\#</span><span class="sxs-lookup"><span data-stu-id="58453-103">Async programming in F\#</span></span>

<span data-ttu-id="58453-104">异步编程是一种机制，对于现代应用程序来说，由于各种原因至关重要。</span><span class="sxs-lookup"><span data-stu-id="58453-104">Asynchronous programming is a mechanism that is essential to modern applications for diverse reasons.</span></span> <span data-ttu-id="58453-105">大多数开发人员会遇到两个主要用例：</span><span class="sxs-lookup"><span data-stu-id="58453-105">There are two primary use cases that most developers will encounter:</span></span>

- <span data-ttu-id="58453-106">显示一个服务器进程，该服务器进程可以服务大量并发传入请求，同时最小化请求处理时占用的系统资源，等待来自该进程外部的系统或服务的输入</span><span class="sxs-lookup"><span data-stu-id="58453-106">Presenting a server process that can service a significant number of concurrent incoming requests, while minimizing the system resources occupied while request processing awaits inputs from systems or services external to that process</span></span>
- <span data-ttu-id="58453-107">维护响应灵敏的 UI 或主线程，同时推进后台工作</span><span class="sxs-lookup"><span data-stu-id="58453-107">Maintaining a responsive UI or main thread while concurrently progressing background work</span></span>

<span data-ttu-id="58453-108">尽管后台工作通常涉及多个线程的利用，但单独考虑异步和多线程的概念非常重要。</span><span class="sxs-lookup"><span data-stu-id="58453-108">Although background work often does involve the utilization of multiple threads, it's important to consider the concepts of asynchrony and multi-threading separately.</span></span> <span data-ttu-id="58453-109">事实上，它们是单独的问题，一个并不意味着另一个。</span><span class="sxs-lookup"><span data-stu-id="58453-109">In fact, they are separate concerns, and one does not imply the other.</span></span> <span data-ttu-id="58453-110">本文中介绍的内容将更详细地介绍这一点。</span><span class="sxs-lookup"><span data-stu-id="58453-110">What follows in this article describes this in more detail.</span></span>

## <a name="asynchrony-defined"></a><span data-ttu-id="58453-111">已定义异步</span><span class="sxs-lookup"><span data-stu-id="58453-111">Asynchrony defined</span></span>

<span data-ttu-id="58453-112">前一点 -异步与多个线程的利用率无关 - 值得进一步解释一下。</span><span class="sxs-lookup"><span data-stu-id="58453-112">The previous point - that asynchrony is independent of the utilization of multiple threads - is worth explaining a bit further.</span></span> <span data-ttu-id="58453-113">有三个概念有时相关，但严格地相互独立：</span><span class="sxs-lookup"><span data-stu-id="58453-113">There are three concepts that are sometimes related, but strictly independent of one another:</span></span>

- <span data-ttu-id="58453-114">并发性;在重叠的时间段中执行多个计算时。</span><span class="sxs-lookup"><span data-stu-id="58453-114">Concurrency; when multiple computations execute in overlapping time periods.</span></span>
- <span data-ttu-id="58453-115">并行性;当多个计算或单个计算的几个部分完全同时运行时。</span><span class="sxs-lookup"><span data-stu-id="58453-115">Parallelism; when multiple computations or several parts of a single computation run at exactly the same time.</span></span>
- <span data-ttu-id="58453-116">异步;当一个或多个计算可以独立于主程序流执行时。</span><span class="sxs-lookup"><span data-stu-id="58453-116">Asynchrony; when one or more computations can execute separately from the main program flow.</span></span>

<span data-ttu-id="58453-117">这三个概念都是正交概念，但很容易组合，尤其是当它们一起使用时。</span><span class="sxs-lookup"><span data-stu-id="58453-117">All three are orthogonal concepts, but can be easily conflated, especially when they are used together.</span></span> <span data-ttu-id="58453-118">例如，您可能需要并行执行多个异步计算。</span><span class="sxs-lookup"><span data-stu-id="58453-118">For example, you may need to execute multiple asynchronous computations in parallel.</span></span> <span data-ttu-id="58453-119">这并不意味着并行性或异步性相互暗示。</span><span class="sxs-lookup"><span data-stu-id="58453-119">This does not mean that parallelism or asynchrony imply one another.</span></span>

<span data-ttu-id="58453-120">如果考虑"异步"一词的词源，则涉及两个部分：</span><span class="sxs-lookup"><span data-stu-id="58453-120">If you consider the etymology of the word "asynchronous", there are two pieces involved:</span></span>

- <span data-ttu-id="58453-121">"a"，意思是"不"。</span><span class="sxs-lookup"><span data-stu-id="58453-121">"a", meaning "not".</span></span>
- <span data-ttu-id="58453-122">"同步"，意思是"同时"。</span><span class="sxs-lookup"><span data-stu-id="58453-122">"synchronous", meaning "at the same time".</span></span>

<span data-ttu-id="58453-123">将这两个术语放在一起时，您将看到"异步"表示"不是同时"。</span><span class="sxs-lookup"><span data-stu-id="58453-123">When you put these two terms together, you'll see that "asynchronous" means "not at the same time".</span></span> <span data-ttu-id="58453-124">就这么简单！</span><span class="sxs-lookup"><span data-stu-id="58453-124">That's it!</span></span> <span data-ttu-id="58453-125">这个定义中没有并发性或并行性的含义。</span><span class="sxs-lookup"><span data-stu-id="58453-125">There is no implication of concurrency or parallelism in this definition.</span></span> <span data-ttu-id="58453-126">在实践中也是如此。</span><span class="sxs-lookup"><span data-stu-id="58453-126">This is also true in practice.</span></span>

<span data-ttu-id="58453-127">实际上，F# 中的异步计算计划独立于主程序流执行。</span><span class="sxs-lookup"><span data-stu-id="58453-127">In practical terms, asynchronous computations in F# are scheduled to execute independently of the main program flow.</span></span> <span data-ttu-id="58453-128">这并不意味着并发性或并行性，也不意味着计算总是在后台发生。</span><span class="sxs-lookup"><span data-stu-id="58453-128">This doesn't imply concurrency or parallelism, nor does it imply that a computation always happens in the background.</span></span> <span data-ttu-id="58453-129">事实上，异步计算甚至可以同步执行，具体取决于计算的性质和计算执行的环境。</span><span class="sxs-lookup"><span data-stu-id="58453-129">In fact, asynchronous computations can even execute synchronously, depending on the nature of the computation and the environment the computation is executing in.</span></span>

<span data-ttu-id="58453-130">您应该有的主要要点是异步计算独立于主程序流。</span><span class="sxs-lookup"><span data-stu-id="58453-130">The main takeaway you should have is that asynchronous computations are independent of the main program flow.</span></span> <span data-ttu-id="58453-131">尽管对异步计算执行的时间或方式几乎没有保证，但有一些方法来编排和调度它们。</span><span class="sxs-lookup"><span data-stu-id="58453-131">Although there are few guarantees about when or how an asynchronous computation executes, there are some approaches to orchestrating and scheduling them.</span></span> <span data-ttu-id="58453-132">本文的其余部分将探讨 F# 异步的核心概念以及如何使用 F# 中内置的类型、函数和表达式。</span><span class="sxs-lookup"><span data-stu-id="58453-132">The rest of this article explores core concepts for F# asynchrony and how to use the types, functions, and expressions built into F#.</span></span>

## <a name="core-concepts"></a><span data-ttu-id="58453-133">核心概念</span><span class="sxs-lookup"><span data-stu-id="58453-133">Core concepts</span></span>

<span data-ttu-id="58453-134">在 F# 中，异步编程围绕三个核心概念：</span><span class="sxs-lookup"><span data-stu-id="58453-134">In F#, asynchronous programming is centered around three core concepts:</span></span>

- <span data-ttu-id="58453-135">表示`Async<'T>`可组合异步计算的类型。</span><span class="sxs-lookup"><span data-stu-id="58453-135">The `Async<'T>` type, which represents a composable asynchronous computation.</span></span>
- <span data-ttu-id="58453-136">模块`Async`函数允许您安排异步工作、撰写异步计算并转换异步结果。</span><span class="sxs-lookup"><span data-stu-id="58453-136">The `Async` module functions, which let you schedule asynchronous work, compose asynchronous computations, and transform asynchronous results.</span></span>
- <span data-ttu-id="58453-137">`async { }`[计算表达式](../../language-reference/computation-expressions.md)，为构建和控制异步计算提供了方便的语法。</span><span class="sxs-lookup"><span data-stu-id="58453-137">The `async { }` [computation expression](../../language-reference/computation-expressions.md), which provides a convenient syntax for building and controlling asynchronous computations.</span></span>

<span data-ttu-id="58453-138">您可以在以下示例中看到以下三个概念：</span><span class="sxs-lookup"><span data-stu-id="58453-138">You can see these three concepts in the following example:</span></span>

```fsharp
open System
open System.IO

let printTotalFileBytes path =
    async {
        let! bytes = File.ReadAllBytesAsync(path) |> Async.AwaitTask
        let fileName = Path.GetFileName(path)
        printfn "File %s has %d bytes" fileName bytes.Length
    }

[<EntryPoint>]
let main argv =
    printTotalFileBytes "path-to-file.txt"
    |> Async.RunSynchronously

    Console.Read() |> ignore
    0
```

<span data-ttu-id="58453-139">在此示例中，`printTotalFileBytes`函数的类型`string -> Async<unit>`为 。</span><span class="sxs-lookup"><span data-stu-id="58453-139">In the example, the `printTotalFileBytes` function is of type `string -> Async<unit>`.</span></span> <span data-ttu-id="58453-140">调用函数实际上不会执行异步计算。</span><span class="sxs-lookup"><span data-stu-id="58453-140">Calling the function does not actually execute the asynchronous computation.</span></span> <span data-ttu-id="58453-141">相反，它返回`Async<unit>`充当以异步方式执行*的工作规范的*。</span><span class="sxs-lookup"><span data-stu-id="58453-141">Instead, it returns an `Async<unit>` that acts as a *specification* of the work that is to execute asynchronously.</span></span> <span data-ttu-id="58453-142">它在其`Async.AwaitTask`正文中调用，它将 的结果<xref:System.IO.File.ReadAllBytesAsync%2A>转换为适当的类型。</span><span class="sxs-lookup"><span data-stu-id="58453-142">It calls `Async.AwaitTask` in its body, which converts the result of <xref:System.IO.File.ReadAllBytesAsync%2A> to an appropriate type.</span></span>

<span data-ttu-id="58453-143">另一个重要的行是调用`Async.RunSynchronously`。</span><span class="sxs-lookup"><span data-stu-id="58453-143">Another important line is the call to `Async.RunSynchronously`.</span></span> <span data-ttu-id="58453-144">这是 Async 模块启动函数之一，如果要实际执行 F# 异步计算，则需要调用这些函数。</span><span class="sxs-lookup"><span data-stu-id="58453-144">This is one of the Async module starting functions that you'll need to call if you want to actually execute an F# asynchronous computation.</span></span>

<span data-ttu-id="58453-145">这与 C#/可视化基本`async`编程风格有根本区别。</span><span class="sxs-lookup"><span data-stu-id="58453-145">This is a fundamental difference with the C#/Visual Basic style of `async` programming.</span></span> <span data-ttu-id="58453-146">在 F# 中，异步计算可以视为**冷任务**。</span><span class="sxs-lookup"><span data-stu-id="58453-146">In F#, asynchronous computations can be thought of as **Cold tasks**.</span></span> <span data-ttu-id="58453-147">它们必须显式开始实际执行。</span><span class="sxs-lookup"><span data-stu-id="58453-147">They must be explicitly started to actually execute.</span></span> <span data-ttu-id="58453-148">这具有一些优点，因为它允许您比 C# 或 Visual Basic 更容易组合和序列异步工作。</span><span class="sxs-lookup"><span data-stu-id="58453-148">This has some advantages, as it allows you to combine and sequence asynchronous work much more easily than in C# or Visual Basic.</span></span>

## <a name="combine-asynchronous-computations"></a><span data-ttu-id="58453-149">合并异步计算</span><span class="sxs-lookup"><span data-stu-id="58453-149">Combine asynchronous computations</span></span>

<span data-ttu-id="58453-150">下面是一个通过组合计算构建在前一个示例的基础上的示例：</span><span class="sxs-lookup"><span data-stu-id="58453-150">Here is an example that builds upon the previous one by combining computations:</span></span>

```fsharp
open System
open System.IO

let printTotalFileBytes path =
    async {
        let! bytes = File.ReadAllBytesAsync(path) |> Async.AwaitTask
        let fileName = Path.GetFileName(path)
        printfn "File %s has %d bytes" fileName bytes.Length
    }

[<EntryPoint>]
let main argv =
    argv
    |> Array.map printTotalFileBytes
    |> Async.Parallel
    |> Async.Ignore
    |> Async.RunSynchronously

    0
```

<span data-ttu-id="58453-151">正如您所看到的，该`main`函数还有更多的调用。</span><span class="sxs-lookup"><span data-stu-id="58453-151">As you can see, the `main` function has quite a few more calls made.</span></span> <span data-ttu-id="58453-152">从概念上讲，它执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="58453-152">Conceptually, it does the following:</span></span>

1. <span data-ttu-id="58453-153">将命令行参数转换为`Async<unit>`具有`Array.map`的计算。</span><span class="sxs-lookup"><span data-stu-id="58453-153">Transform the command-line arguments into `Async<unit>` computations with `Array.map`.</span></span>
2. <span data-ttu-id="58453-154">创建一`Async<'T[]>`个计划并在运行时并行`printTotalFileBytes`运行计算。</span><span class="sxs-lookup"><span data-stu-id="58453-154">Create an `Async<'T[]>` that schedules and runs the `printTotalFileBytes` computations in parallel when it runs.</span></span>
3. <span data-ttu-id="58453-155">创建将`Async<unit>`运行并行计算并忽略其结果的</span><span class="sxs-lookup"><span data-stu-id="58453-155">Create an `Async<unit>` that will run the parallel computation and ignore its result.</span></span>
4. <span data-ttu-id="58453-156">显式运行最后一个计算`Async.RunSynchronously`与 和 块，直到它完成。</span><span class="sxs-lookup"><span data-stu-id="58453-156">Explicitly run the last computation with `Async.RunSynchronously` and block until it is completes.</span></span>

<span data-ttu-id="58453-157">运行此程序时，`printTotalFileBytes`每个命令行参数并行运行。</span><span class="sxs-lookup"><span data-stu-id="58453-157">When this program runs, `printTotalFileBytes` runs in parallel for each command-line argument.</span></span> <span data-ttu-id="58453-158">由于异步计算独立于程序流执行，因此它们无法按顺序打印其信息并完成执行。</span><span class="sxs-lookup"><span data-stu-id="58453-158">Because asynchronous computations execute independently of program flow, there is no order in which they print their information and finish executing.</span></span> <span data-ttu-id="58453-159">计算将并行计划，但不能保证其执行顺序。</span><span class="sxs-lookup"><span data-stu-id="58453-159">The computations will be scheduled in parallel, but their order of execution is not guaranteed.</span></span>

## <a name="sequence-asynchronous-computations"></a><span data-ttu-id="58453-160">序列异步计算</span><span class="sxs-lookup"><span data-stu-id="58453-160">Sequence asynchronous computations</span></span>

<span data-ttu-id="58453-161">因为`Async<'T>`是工作规范，而不是已经运行的任务，因此可以轻松地执行更复杂的转换。</span><span class="sxs-lookup"><span data-stu-id="58453-161">Because `Async<'T>` is a specification of work rather than an already-running task, you can perform more intricate transformations easily.</span></span> <span data-ttu-id="58453-162">下面是一个示例，它对一组 Async 计算进行排序，以便它们逐一执行。</span><span class="sxs-lookup"><span data-stu-id="58453-162">Here is an example that sequences a set of Async computations so they execute one after another.</span></span>

```fsharp
let printTotalFileBytes path =
    async {
        let! bytes = File.ReadAllBytesAsync(path) |> Async.AwaitTask
        let fileName = Path.GetFileName(path)
        printfn "File %s has %d bytes" fileName bytes.Length
    }

[<EntryPoint>]
let main argv =
    argv
    |> Array.map printTotalFileBytes
    |> Async.Sequential
    |> Async.Ignore
    |> Async.RunSynchronously
    |> ignore
```

<span data-ttu-id="58453-163">这将按计划`printTotalFileBytes`按 的元素的顺序执行，`argv`而不是并行调度它们。</span><span class="sxs-lookup"><span data-stu-id="58453-163">This will schedule `printTotalFileBytes` to execute in the order of the elements of `argv` rather than scheduling them in parallel.</span></span> <span data-ttu-id="58453-164">由于下一项不会计划，直到最后一次计算完成执行后，计算将进行排序，以便其执行中没有重叠。</span><span class="sxs-lookup"><span data-stu-id="58453-164">Because the next item will not be scheduled until after the last computation has finished executing, the computations are sequenced such that there is no overlap in their execution.</span></span>

## <a name="important-async-module-functions"></a><span data-ttu-id="58453-165">重要的异步模块功能</span><span class="sxs-lookup"><span data-stu-id="58453-165">Important Async module functions</span></span>

<span data-ttu-id="58453-166">在 F# 中编写异步代码时，通常会与处理计算计划的框架进行交互。</span><span class="sxs-lookup"><span data-stu-id="58453-166">When you write async code in F# you'll usually interact with a framework that handles scheduling of computations for you.</span></span> <span data-ttu-id="58453-167">但是，情况并非总是如此，因此最好了解各种启动函数来安排异步工作。</span><span class="sxs-lookup"><span data-stu-id="58453-167">However, this is not always the case, so it is good to learn the various starting functions to schedule asynchronous work.</span></span>

<span data-ttu-id="58453-168">由于 F# 异步计算是工作_规范_，而不是已执行的工作的表示形式，因此必须显式从启动函数开始。</span><span class="sxs-lookup"><span data-stu-id="58453-168">Because F# asynchronous computations are a _specification_ of work rather than a representation of work that is already executing, they must be explicitly started with a starting function.</span></span> <span data-ttu-id="58453-169">有许多[Async 启动函数](https://msdn.microsoft.com/library/ee370232.aspx)在不同的上下文中非常有用。</span><span class="sxs-lookup"><span data-stu-id="58453-169">There are many [Async starting functions](https://msdn.microsoft.com/library/ee370232.aspx) that are helpful in different contexts.</span></span> <span data-ttu-id="58453-170">以下部分介绍一些更常见的起始函数。</span><span class="sxs-lookup"><span data-stu-id="58453-170">The following section describes some of the more common starting functions.</span></span>

### <a name="asyncstartchild"></a><span data-ttu-id="58453-171">异步.开始儿童</span><span class="sxs-lookup"><span data-stu-id="58453-171">Async.StartChild</span></span>

<span data-ttu-id="58453-172">在异步计算中启动子计算。</span><span class="sxs-lookup"><span data-stu-id="58453-172">Starts a child computation within an asynchronous computation.</span></span> <span data-ttu-id="58453-173">这允许同时执行多个异步计算。</span><span class="sxs-lookup"><span data-stu-id="58453-173">This allows multiple asynchronous computations to be executed concurrently.</span></span> <span data-ttu-id="58453-174">子计算与父计算共享取消令牌。</span><span class="sxs-lookup"><span data-stu-id="58453-174">The child computation shares a cancellation token with the parent computation.</span></span> <span data-ttu-id="58453-175">如果取消父计算，则子计算也会取消。</span><span class="sxs-lookup"><span data-stu-id="58453-175">If the parent computation is canceled, the child computation is also canceled.</span></span>

<span data-ttu-id="58453-176">签名：</span><span class="sxs-lookup"><span data-stu-id="58453-176">Signature:</span></span>

```fsharp
computation: Async<'T> * timeout: ?int -> Async<Async<'T>>
```

<span data-ttu-id="58453-177">使用场合：</span><span class="sxs-lookup"><span data-stu-id="58453-177">When to use:</span></span>

- <span data-ttu-id="58453-178">当您要同时执行多个异步计算，而不是一次执行一个异步计算时，却不希望将它们同时计划。</span><span class="sxs-lookup"><span data-stu-id="58453-178">When you want to execute multiple asynchronous computations concurrently rather than one at a time, but not have them scheduled in parallel.</span></span>
- <span data-ttu-id="58453-179">当您希望将子计算的生存期与父计算的生存期绑定时。</span><span class="sxs-lookup"><span data-stu-id="58453-179">When you wish to tie the lifetime of a child computation to that of a parent computation.</span></span>

<span data-ttu-id="58453-180">需要注意的：</span><span class="sxs-lookup"><span data-stu-id="58453-180">What to watch out for:</span></span>

- <span data-ttu-id="58453-181">使用`Async.StartChild`启动多个计算与并行调度计算计算策略不同。</span><span class="sxs-lookup"><span data-stu-id="58453-181">Starting multiple computations with `Async.StartChild` isn't the same as scheduling them in parallel.</span></span> <span data-ttu-id="58453-182">如果要并行计划计算，请使用`Async.Parallel`。</span><span class="sxs-lookup"><span data-stu-id="58453-182">If you wish to schedule computations in parallel, use `Async.Parallel`.</span></span>
- <span data-ttu-id="58453-183">取消父计算将触发取消它启动的所有子计算。</span><span class="sxs-lookup"><span data-stu-id="58453-183">Canceling a parent computation will trigger cancellation of all child computations it started.</span></span>

### <a name="asyncstartimmediate"></a><span data-ttu-id="58453-184">异步.立即启动</span><span class="sxs-lookup"><span data-stu-id="58453-184">Async.StartImmediate</span></span>

<span data-ttu-id="58453-185">运行异步计算，立即开始在当前操作系统线程上。</span><span class="sxs-lookup"><span data-stu-id="58453-185">Runs an asynchronous computation, starting immediately on the current operating system thread.</span></span> <span data-ttu-id="58453-186">如果您在计算期间需要更新调用线程上的内容，这非常有用。</span><span class="sxs-lookup"><span data-stu-id="58453-186">This is helpful if you need to update something on the calling thread during the computation.</span></span> <span data-ttu-id="58453-187">例如，如果异步计算必须更新 UI（如更新进度栏），则应`Async.StartImmediate`使用。</span><span class="sxs-lookup"><span data-stu-id="58453-187">For example, if an asynchronous computation must update a UI (such as updating a progress bar), then `Async.StartImmediate` should be used.</span></span>

<span data-ttu-id="58453-188">签名：</span><span class="sxs-lookup"><span data-stu-id="58453-188">Signature:</span></span>

```fsharp
computation: Async<unit> - cancellationToken: ?CancellationToken -> unit
```

<span data-ttu-id="58453-189">使用场合：</span><span class="sxs-lookup"><span data-stu-id="58453-189">When to use:</span></span>

- <span data-ttu-id="58453-190">当您需要在异步计算中更新调用线程上的内容时。</span><span class="sxs-lookup"><span data-stu-id="58453-190">When you need to update something on the calling thread in the middle of an asynchronous computation.</span></span>

<span data-ttu-id="58453-191">需要注意的：</span><span class="sxs-lookup"><span data-stu-id="58453-191">What to watch out for:</span></span>

- <span data-ttu-id="58453-192">异步计算中的代码将在预定的任何线程上运行。</span><span class="sxs-lookup"><span data-stu-id="58453-192">Code in the asynchronous computation will run on whatever thread one happens to be scheduled on.</span></span> <span data-ttu-id="58453-193">如果该线程在某种程度上是敏感的（如 UI 线程），则可能会有问题。</span><span class="sxs-lookup"><span data-stu-id="58453-193">This can be problematic if that thread is in some way sensitive, such as a UI thread.</span></span> <span data-ttu-id="58453-194">在这种情况下，`Async.StartImmediate`很可能不适合使用。</span><span class="sxs-lookup"><span data-stu-id="58453-194">In such cases, `Async.StartImmediate` is likely inappropriate to use.</span></span>

### <a name="asyncstartastask"></a><span data-ttu-id="58453-195">异步.StartAsTask</span><span class="sxs-lookup"><span data-stu-id="58453-195">Async.StartAsTask</span></span>

<span data-ttu-id="58453-196">在线程池中执行计算。</span><span class="sxs-lookup"><span data-stu-id="58453-196">Executes a computation in the thread pool.</span></span> <span data-ttu-id="58453-197">返回将在<xref:System.Threading.Tasks.Task%601>计算终止后在相应状态上完成的 的 返回 （生成结果、引发异常或被取消）。</span><span class="sxs-lookup"><span data-stu-id="58453-197">Returns a <xref:System.Threading.Tasks.Task%601> that will be completed on the corresponding state once the computation terminates (produces the result, throws exception, or gets canceled).</span></span> <span data-ttu-id="58453-198">如果未提供取消令牌，则使用默认取消令牌。</span><span class="sxs-lookup"><span data-stu-id="58453-198">If no cancellation token is provided, then the default cancellation token is used.</span></span>

<span data-ttu-id="58453-199">签名：</span><span class="sxs-lookup"><span data-stu-id="58453-199">Signature:</span></span>

```fsharp
computation: Async<'T> - taskCreationOptions: ?TaskCreationOptions - cancellationToken: ?CancellationToken -> Task<'T>
```

<span data-ttu-id="58453-200">使用场合：</span><span class="sxs-lookup"><span data-stu-id="58453-200">When to use:</span></span>

- <span data-ttu-id="58453-201">当您需要调用 .NET API 时，该<xref:System.Threading.Tasks.Task%601>API 希望 表示异步计算的结果。</span><span class="sxs-lookup"><span data-stu-id="58453-201">When you need to call into a .NET API that expects a <xref:System.Threading.Tasks.Task%601> to represent the result of an asynchronous computation.</span></span>

<span data-ttu-id="58453-202">需要注意的：</span><span class="sxs-lookup"><span data-stu-id="58453-202">What to watch out for:</span></span>

- <span data-ttu-id="58453-203">此调用将分配一个`Task`附加对象，如果经常使用，可能会增加开销。</span><span class="sxs-lookup"><span data-stu-id="58453-203">This call will allocate an additional `Task` object, which can increase overhead if it is used often.</span></span>

### <a name="asyncparallel"></a><span data-ttu-id="58453-204">异步.并行</span><span class="sxs-lookup"><span data-stu-id="58453-204">Async.Parallel</span></span>

<span data-ttu-id="58453-205">计划要并行执行的异步计算序列。</span><span class="sxs-lookup"><span data-stu-id="58453-205">Schedules a sequence of asynchronous computations to be executed in parallel.</span></span> <span data-ttu-id="58453-206">通过指定`maxDegreesOfParallelism`参数，可以选择调整/限制并行性的程度。</span><span class="sxs-lookup"><span data-stu-id="58453-206">The degree of parallelism can be optionally tuned/throttled by specifying the `maxDegreesOfParallelism` parameter.</span></span>

<span data-ttu-id="58453-207">签名：</span><span class="sxs-lookup"><span data-stu-id="58453-207">Signature:</span></span>

```fsharp
computations: seq<Async<'T>> - ?maxDegreesOfParallelism: int -> Async<'T[]>
```

<span data-ttu-id="58453-208">何时使用:</span><span class="sxs-lookup"><span data-stu-id="58453-208">When to use it:</span></span>

- <span data-ttu-id="58453-209">如果需要同时运行一组计算，并且不依赖于它们的执行顺序。</span><span class="sxs-lookup"><span data-stu-id="58453-209">If you need to run a set of computations at the same time and have no reliance on their order of execution.</span></span>
- <span data-ttu-id="58453-210">如果不需要并行计划计算的结果，直到它们全部完成。</span><span class="sxs-lookup"><span data-stu-id="58453-210">If you don't require results from computations scheduled in parallel until they have all completed.</span></span>

<span data-ttu-id="58453-211">需要注意的：</span><span class="sxs-lookup"><span data-stu-id="58453-211">What to watch out for:</span></span>

- <span data-ttu-id="58453-212">只有在所有计算完成后，才能访问生成的值数组。</span><span class="sxs-lookup"><span data-stu-id="58453-212">You can only access the resulting array of values once all computations have finished.</span></span>
- <span data-ttu-id="58453-213">计算将运行，但它们最终都会得到计划。</span><span class="sxs-lookup"><span data-stu-id="58453-213">Computations will be run however they end up getting scheduled.</span></span> <span data-ttu-id="58453-214">这意味着您不能依赖他们的执行顺序。</span><span class="sxs-lookup"><span data-stu-id="58453-214">This means you cannot rely on their order of their execution.</span></span>

### <a name="asyncsequential"></a><span data-ttu-id="58453-215">异步。顺序</span><span class="sxs-lookup"><span data-stu-id="58453-215">Async.Sequential</span></span>

<span data-ttu-id="58453-216">计划一系列异步计算，以便按传递顺序执行。</span><span class="sxs-lookup"><span data-stu-id="58453-216">Schedules a sequence of asynchronous computations to be executed in the order that they are passed.</span></span> <span data-ttu-id="58453-217">将执行第一个计算，然后执行下一个计算，等等。</span><span class="sxs-lookup"><span data-stu-id="58453-217">The first computation will be executed, then the next, and so on.</span></span> <span data-ttu-id="58453-218">不会并行执行任何计算。</span><span class="sxs-lookup"><span data-stu-id="58453-218">No computations will be executed in parallel.</span></span>

<span data-ttu-id="58453-219">签名：</span><span class="sxs-lookup"><span data-stu-id="58453-219">Signature:</span></span>

```fsharp
computations: seq<Async<'T>> -> Async<'T[]>
```

<span data-ttu-id="58453-220">何时使用:</span><span class="sxs-lookup"><span data-stu-id="58453-220">When to use it:</span></span>

- <span data-ttu-id="58453-221">如果需要按顺序执行多个计算。</span><span class="sxs-lookup"><span data-stu-id="58453-221">If you need to execute multiple computations in order.</span></span>

<span data-ttu-id="58453-222">需要注意的：</span><span class="sxs-lookup"><span data-stu-id="58453-222">What to watch out for:</span></span>

- <span data-ttu-id="58453-223">只有在所有计算完成后，才能访问生成的值数组。</span><span class="sxs-lookup"><span data-stu-id="58453-223">You can only access the resulting array of values once all computations have finished.</span></span>
- <span data-ttu-id="58453-224">计算将以传递给此函数的顺序运行，这可能意味着在返回结果之前将经过更多的时间。</span><span class="sxs-lookup"><span data-stu-id="58453-224">Computations will be run in the order that they are passed to this function, which can mean that more time will elapse before the results are returned.</span></span>

### <a name="asyncawaittask"></a><span data-ttu-id="58453-225">异步.Await任务</span><span class="sxs-lookup"><span data-stu-id="58453-225">Async.AwaitTask</span></span>

<span data-ttu-id="58453-226">返回一个异步计算，该计算等待给定<xref:System.Threading.Tasks.Task%601>的计算完成，并将其结果作为`Async<'T>`</span><span class="sxs-lookup"><span data-stu-id="58453-226">Returns an asynchronous computation that waits for the given <xref:System.Threading.Tasks.Task%601> to complete and returns its result as an `Async<'T>`</span></span>

<span data-ttu-id="58453-227">签名：</span><span class="sxs-lookup"><span data-stu-id="58453-227">Signature:</span></span>

```fsharp
task: Task<'T>  -> Async<'T>
```

<span data-ttu-id="58453-228">使用场合：</span><span class="sxs-lookup"><span data-stu-id="58453-228">When to use:</span></span>

- <span data-ttu-id="58453-229">使用 .NET API 时，该<xref:System.Threading.Tasks.Task%601>API 在 F# 异步计算中返回 。</span><span class="sxs-lookup"><span data-stu-id="58453-229">When you are consuming a .NET API that returns a <xref:System.Threading.Tasks.Task%601> within an F# asynchronous computation.</span></span>

<span data-ttu-id="58453-230">需要注意的：</span><span class="sxs-lookup"><span data-stu-id="58453-230">What to watch out for:</span></span>

- <span data-ttu-id="58453-231">异常按照任务并行库<xref:System.AggregateException>的约定进行包装，这与 F# 异步通常显示异常的方式不同。</span><span class="sxs-lookup"><span data-stu-id="58453-231">Exceptions are wrapped in <xref:System.AggregateException> following the convention of the Task Parallel Library, and this is different from how F# async generally surfaces exceptions.</span></span>

### <a name="asynccatch"></a><span data-ttu-id="58453-232">异步.捕获</span><span class="sxs-lookup"><span data-stu-id="58453-232">Async.Catch</span></span>

<span data-ttu-id="58453-233">创建一个异步计算，该计算执行`Async<'T>`给定的`Async<Choice<'T, exn>>`，返回 。</span><span class="sxs-lookup"><span data-stu-id="58453-233">Creates an asynchronous computation that executes a given `Async<'T>`, returning an `Async<Choice<'T, exn>>`.</span></span> <span data-ttu-id="58453-234">如果给定`Async<'T>`完成成功，则返回具有结果`Choice1Of2`值的 返回 。</span><span class="sxs-lookup"><span data-stu-id="58453-234">If the given `Async<'T>` completes successfully, then a `Choice1Of2` is returned with the resultant value.</span></span> <span data-ttu-id="58453-235">如果在异常完成之前引发异常，`Choice2of2`则返回，并引发异常。</span><span class="sxs-lookup"><span data-stu-id="58453-235">If an exception is thrown before it completes, then a `Choice2of2` is returned with the raised exception.</span></span> <span data-ttu-id="58453-236">如果它用于由许多计算组成的异步计算，并且其中一个计算引发异常，则包罗万象的计算将完全停止。</span><span class="sxs-lookup"><span data-stu-id="58453-236">If it is used on an asynchronous computation that is itself composed of many computations, and one of those computations throws an exception, the encompassing computation will be stopped entirely.</span></span>

<span data-ttu-id="58453-237">签名：</span><span class="sxs-lookup"><span data-stu-id="58453-237">Signature:</span></span>

```fsharp
computation: Async<'T> -> Async<Choice<'T, exn>>
```

<span data-ttu-id="58453-238">使用场合：</span><span class="sxs-lookup"><span data-stu-id="58453-238">When to use:</span></span>

- <span data-ttu-id="58453-239">执行异步工作时，可能会因异常而失败，并且希望在调用方中处理该异常。</span><span class="sxs-lookup"><span data-stu-id="58453-239">When you are performing asynchronous work that may fail with an exception and you want to handle that exception in the caller.</span></span>

<span data-ttu-id="58453-240">需要注意的：</span><span class="sxs-lookup"><span data-stu-id="58453-240">What to watch out for:</span></span>

- <span data-ttu-id="58453-241">使用组合或序列异步计算时，如果包包含计算的"内部"计算之一引发异常，则包包含计算将完全停止。</span><span class="sxs-lookup"><span data-stu-id="58453-241">When using combined or sequenced asynchronous computations, the encompassing computation will fully stop if one of its "internal" computations throws an exception.</span></span>

### <a name="asyncignore"></a><span data-ttu-id="58453-242">异步.忽略</span><span class="sxs-lookup"><span data-stu-id="58453-242">Async.Ignore</span></span>

<span data-ttu-id="58453-243">创建运行给定计算并忽略其结果的异步计算。</span><span class="sxs-lookup"><span data-stu-id="58453-243">Creates an asynchronous computation that runs the given computation and ignores its result.</span></span>

<span data-ttu-id="58453-244">签名：</span><span class="sxs-lookup"><span data-stu-id="58453-244">Signature:</span></span>

```fsharp
computation: Async<'T> -> Async<unit>
```

<span data-ttu-id="58453-245">使用场合：</span><span class="sxs-lookup"><span data-stu-id="58453-245">When to use:</span></span>

- <span data-ttu-id="58453-246">当您有不需要结果的异步计算时。</span><span class="sxs-lookup"><span data-stu-id="58453-246">When you have an asynchronous computation whose result is not needed.</span></span> <span data-ttu-id="58453-247">这类似于非异步`ignore`代码的代码。</span><span class="sxs-lookup"><span data-stu-id="58453-247">This is analogous to the `ignore` code for non-asynchronous code.</span></span>

<span data-ttu-id="58453-248">需要注意的：</span><span class="sxs-lookup"><span data-stu-id="58453-248">What to watch out for:</span></span>

- <span data-ttu-id="58453-249">如果必须使用此，因为您希望使用`Async.Start`或其他需要`Async<unit>`的功能，请考虑丢弃结果是否可以执行。</span><span class="sxs-lookup"><span data-stu-id="58453-249">If you must use this because you wish to use `Async.Start` or another function that requires `Async<unit>`, consider if discarding the result is okay to do.</span></span> <span data-ttu-id="58453-250">放弃结果只是为了适合类型签名通常不应该做。</span><span class="sxs-lookup"><span data-stu-id="58453-250">Discarding results just to fit a type signature should not generally be done.</span></span>

### <a name="asyncrunsynchronously"></a><span data-ttu-id="58453-251">异步.同步运行</span><span class="sxs-lookup"><span data-stu-id="58453-251">Async.RunSynchronously</span></span>

<span data-ttu-id="58453-252">运行异步计算，并在调用线程上等待其结果。</span><span class="sxs-lookup"><span data-stu-id="58453-252">Runs an asynchronous computation and awaits its result on the calling thread.</span></span> <span data-ttu-id="58453-253">此呼叫已阻塞。</span><span class="sxs-lookup"><span data-stu-id="58453-253">This call is blocking.</span></span>

<span data-ttu-id="58453-254">签名：</span><span class="sxs-lookup"><span data-stu-id="58453-254">Signature:</span></span>

```fsharp
computation: Async<'T> - timeout: ?int - cancellationToken: ?CancellationToken -> 'T
```

<span data-ttu-id="58453-255">何时使用:</span><span class="sxs-lookup"><span data-stu-id="58453-255">When to use it:</span></span>

- <span data-ttu-id="58453-256">如果需要，请仅在应用程序中使用它一次 - 在可执行文件的入口点。</span><span class="sxs-lookup"><span data-stu-id="58453-256">If you need it, use it only once in an application - at the entry point for an executable.</span></span>
- <span data-ttu-id="58453-257">当您不关心性能并希望同时执行一组其他异步操作时。</span><span class="sxs-lookup"><span data-stu-id="58453-257">When you don't care about performance and want to execute a set of other asynchronous operations at once.</span></span>

<span data-ttu-id="58453-258">需要注意的：</span><span class="sxs-lookup"><span data-stu-id="58453-258">What to watch out for:</span></span>

- <span data-ttu-id="58453-259">调用`Async.RunSynchronously`阻止调用线程，直到执行完成。</span><span class="sxs-lookup"><span data-stu-id="58453-259">Calling `Async.RunSynchronously` blocks the calling thread until the execution completes.</span></span>

### <a name="asyncstart"></a><span data-ttu-id="58453-260">异步.开始</span><span class="sxs-lookup"><span data-stu-id="58453-260">Async.Start</span></span>

<span data-ttu-id="58453-261">在线程池中启动可异步计算，该`unit`计算返回 。</span><span class="sxs-lookup"><span data-stu-id="58453-261">Starts an asynchronous computation in the thread pool that returns `unit`.</span></span> <span data-ttu-id="58453-262">不等待结果。</span><span class="sxs-lookup"><span data-stu-id="58453-262">Doesn't wait for its result.</span></span> <span data-ttu-id="58453-263">从`Async.Start`开始嵌套计算完全独立于调用它们的父计算开始。</span><span class="sxs-lookup"><span data-stu-id="58453-263">Nested computations started with `Async.Start` are started completely independently of the parent computation that called them.</span></span> <span data-ttu-id="58453-264">其生存期不与任何父计算相关联。</span><span class="sxs-lookup"><span data-stu-id="58453-264">Their lifetime is not tied to any parent computation.</span></span> <span data-ttu-id="58453-265">如果取消父计算，则不会取消子计算。</span><span class="sxs-lookup"><span data-stu-id="58453-265">If the parent computation is canceled, no child computations are cancelled.</span></span>

<span data-ttu-id="58453-266">签名：</span><span class="sxs-lookup"><span data-stu-id="58453-266">Signature:</span></span>

```fsharp
computation: Async<unit> - cancellationToken: ?CancellationToken -> unit
```

<span data-ttu-id="58453-267">仅在：</span><span class="sxs-lookup"><span data-stu-id="58453-267">Use only when:</span></span>

- <span data-ttu-id="58453-268">异步计算不会产生结果和/或需要处理一个结果。</span><span class="sxs-lookup"><span data-stu-id="58453-268">You have an asynchronous computation that doesn't yield a result and/or require processing of one.</span></span>
- <span data-ttu-id="58453-269">您无需知道异步计算何时完成。</span><span class="sxs-lookup"><span data-stu-id="58453-269">You don't need to know when an asynchronous computation completes.</span></span>
- <span data-ttu-id="58453-270">您不关心异步计算运行哪个线程。</span><span class="sxs-lookup"><span data-stu-id="58453-270">You don't care which thread an asynchronous computation runs on.</span></span>
- <span data-ttu-id="58453-271">您无需了解或报告任务产生的异常。</span><span class="sxs-lookup"><span data-stu-id="58453-271">You don't have any need to be aware of or report exceptions resulting from the task.</span></span>

<span data-ttu-id="58453-272">需要注意的：</span><span class="sxs-lookup"><span data-stu-id="58453-272">What to watch out for:</span></span>

- <span data-ttu-id="58453-273">由开始`Async.Start`计算引发的异常不会传播到调用方。</span><span class="sxs-lookup"><span data-stu-id="58453-273">Exceptions raised by computations started with `Async.Start` aren't propagated to the caller.</span></span> <span data-ttu-id="58453-274">调用堆栈将完全解功能。</span><span class="sxs-lookup"><span data-stu-id="58453-274">The call stack will be completely unwound.</span></span>
- <span data-ttu-id="58453-275">任何有效的工作（如调用`printfn`）开始`Async.Start`不会导致在程序执行的主线程上发生效果。</span><span class="sxs-lookup"><span data-stu-id="58453-275">Any effectful work (such as calling `printfn`) started with `Async.Start` won't cause the effect to happen on the main thread of a program's execution.</span></span>

## <a name="interoperate-with-net"></a><span data-ttu-id="58453-276">与 .NET 互操作</span><span class="sxs-lookup"><span data-stu-id="58453-276">Interoperate with .NET</span></span>

<span data-ttu-id="58453-277">您可能正在使用使用[异步/await-](../../../standard/async.md)样式异步编程的 .NET 库或 C# 代码库。</span><span class="sxs-lookup"><span data-stu-id="58453-277">You may be working with a .NET library or C# codebase that uses [async/await](../../../standard/async.md)-style asynchronous programming.</span></span> <span data-ttu-id="58453-278">由于 C# 和大多数 .NET 库使用<xref:System.Threading.Tasks.Task%601><xref:System.Threading.Tasks.Task>和 类型作为其核心抽象，而不是`Async<'T>`，您必须跨越这两种异步方法之间的边界。</span><span class="sxs-lookup"><span data-stu-id="58453-278">Because C# and the majority of .NET libraries use the <xref:System.Threading.Tasks.Task%601> and <xref:System.Threading.Tasks.Task> types as their core abstractions rather than `Async<'T>`, you must cross a boundary between these two approaches to asynchrony.</span></span>

### <a name="how-to-work-with-net-async-and-taskt"></a><span data-ttu-id="58453-279">如何使用 .NET 异步和`Task<T>`</span><span class="sxs-lookup"><span data-stu-id="58453-279">How to work with .NET async and `Task<T>`</span></span>

<span data-ttu-id="58453-280">使用 .NET 异步库和代码库（<xref:System.Threading.Tasks.Task%601>即具有返回值的异步计算）非常简单，并且具有 F# 的内置支持。</span><span class="sxs-lookup"><span data-stu-id="58453-280">Working with .NET async libraries and codebases that use <xref:System.Threading.Tasks.Task%601> (that is, async computations that have return values) is straightforward and has built-in support with F#.</span></span>

<span data-ttu-id="58453-281">可以使用 函数`Async.AwaitTask`等待 .NET 异步计算：</span><span class="sxs-lookup"><span data-stu-id="58453-281">You can use the `Async.AwaitTask` function to await a .NET asynchronous computation:</span></span>

```fsharp
let getValueFromLibrary param =
    async {
        let! value = DotNetLibrary.GetValueAsync param |> Async.AwaitTask
        return value
    }
```

<span data-ttu-id="58453-282">可以使用 函数`Async.StartAsTask`将异步计算传递给 .NET 调用方：</span><span class="sxs-lookup"><span data-stu-id="58453-282">You can use the `Async.StartAsTask` function to pass an asynchronous computation to a .NET caller:</span></span>

```fsharp
let computationForCaller param =
    async {
        let! result = getAsyncResult param
        return result
    } |> Async.StartAsTask
```

### <a name="how-to-work-with-net-async-and-task"></a><span data-ttu-id="58453-283">如何使用 .NET 异步和`Task`</span><span class="sxs-lookup"><span data-stu-id="58453-283">How to work with .NET async and `Task`</span></span>

<span data-ttu-id="58453-284">要使用使用的<xref:System.Threading.Tasks.Task>API（即 .NET 异步计算不返回值），您可能需要添加一个将 转换为`Async<'T>`的其他函数： <xref:System.Threading.Tasks.Task></span><span class="sxs-lookup"><span data-stu-id="58453-284">To work with APIs that use <xref:System.Threading.Tasks.Task> (that is, .NET async computations that do not return a value), you may need to add an additional function that will convert an `Async<'T>` to a <xref:System.Threading.Tasks.Task>:</span></span>

```fsharp
module Async =
    // Async<unit> -> Task
    let startTaskFromAsyncUnit (comp: Async<unit>) =
        Async.StartAsTask comp :> Task
```

<span data-ttu-id="58453-285">已经有一个`Async.AwaitTask`接受作为<xref:System.Threading.Tasks.Task>输入的。</span><span class="sxs-lookup"><span data-stu-id="58453-285">There is already an `Async.AwaitTask` that accepts a <xref:System.Threading.Tasks.Task> as input.</span></span> <span data-ttu-id="58453-286">使用此函数和以前定义的`startTaskFromAsyncUnit`函数，可以从 F# 异<xref:System.Threading.Tasks.Task>步计算开始和等待类型。</span><span class="sxs-lookup"><span data-stu-id="58453-286">With this and the previously defined `startTaskFromAsyncUnit` function, you can start and await <xref:System.Threading.Tasks.Task> types from an F# async computation.</span></span>

## <a name="relationship-to-multi-threading"></a><span data-ttu-id="58453-287">与多线程的关系</span><span class="sxs-lookup"><span data-stu-id="58453-287">Relationship to multi-threading</span></span>

<span data-ttu-id="58453-288">尽管本文中提到了线程，但有两件重要的事情需要记住：</span><span class="sxs-lookup"><span data-stu-id="58453-288">Although threading is mentioned throughout this article, there are two important things to remember:</span></span>

1. <span data-ttu-id="58453-289">除非在当前线程上显式启动，否则异步计算和线程之间没有关联。</span><span class="sxs-lookup"><span data-stu-id="58453-289">There is no affinity between an asynchronous computation and a thread, unless explicitly started on the current thread.</span></span>
1. <span data-ttu-id="58453-290">F# 中的异步编程不是多线程的抽象。</span><span class="sxs-lookup"><span data-stu-id="58453-290">Asynchronous programming in F# is not an abstraction for multi-threading.</span></span>

<span data-ttu-id="58453-291">例如，计算实际上可能在其调用方的线程上运行，具体取决于工作的性质。</span><span class="sxs-lookup"><span data-stu-id="58453-291">For example, a computation may actually run on its caller's thread, depending on the nature of the work.</span></span> <span data-ttu-id="58453-292">计算还可以"跳转"线程之间，借用它们少量时间在"等待"期间（例如网络呼叫传输时）之间执行有用的工作。</span><span class="sxs-lookup"><span data-stu-id="58453-292">A computation could also "jump" between threads, borrowing them for a small amount of time to do useful work in between periods of "waiting" (such as when a network call is in transit).</span></span>

<span data-ttu-id="58453-293">尽管 F# 提供了在当前线程（或显式不在当前线程上）启动异步计算的一些功能，但异步通常不与特定的线程策略相关联。</span><span class="sxs-lookup"><span data-stu-id="58453-293">Although F# provides some abilities to start an asynchronous computation on the current thread (or explicitly not on the current thread), asynchrony generally is not associated with a particular threading strategy.</span></span>

## <a name="see-also"></a><span data-ttu-id="58453-294">请参阅</span><span class="sxs-lookup"><span data-stu-id="58453-294">See also</span></span>

- [<span data-ttu-id="58453-295">F# 异步编程模型</span><span class="sxs-lookup"><span data-stu-id="58453-295">The F# Asynchronous Programming Model</span></span>](https://www.microsoft.com/research/publication/the-f-asynchronous-programming-model)
- [<span data-ttu-id="58453-296">Jet.com 的 F# 异步指南</span><span class="sxs-lookup"><span data-stu-id="58453-296">Jet.com's F# Async Guide</span></span>](https://medium.com/jettech/f-async-guide-eb3c8a2d180a)
- [<span data-ttu-id="58453-297">F# 用于娱乐和盈利的异步编程指南</span><span class="sxs-lookup"><span data-stu-id="58453-297">F# for fun and profit's Asynchronous Programming guide</span></span>](https://fsharpforfunandprofit.com/posts/concurrency-async-and-parallel/)
- [<span data-ttu-id="58453-298">C# 和 F# 中的异步：C 中的异步哥查#</span><span class="sxs-lookup"><span data-stu-id="58453-298">Async in C# and F#: Asynchronous gotchas in C#</span></span>](http://tomasp.net/blog/csharp-async-gotchas.aspx/)
