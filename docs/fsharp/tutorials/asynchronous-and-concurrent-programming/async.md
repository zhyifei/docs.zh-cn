---
title: "F # 中的异步编程"
description: "了解如何通过是易于使用和自然语言的语言级别编程模型实现 F # 异步编程。"
keywords: .NET, .NET Core
author: cartermp
ms.author: phcart
ms.date: 06/20/2016
ms.topic: article
ms.prod: .net
ms.technology: devlang-fsharp
ms.devlang: fsharp
ms.assetid: f9196bfc-b8a8-4d33-8b53-0dcbd58a69d8
ms.openlocfilehash: 23528d84d0f28283868a1ea316953543d0fd566a
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="async-programming-in-f"></a><span data-ttu-id="2cb7f-104">F # 中的异步编程</span><span class="sxs-lookup"><span data-stu-id="2cb7f-104">Async Programming in F#</span></span> #

> [!NOTE]
> <span data-ttu-id="2cb7f-105">已在本文中发现了一些不精确性。</span><span class="sxs-lookup"><span data-stu-id="2cb7f-105">Some inaccuracies have been discovered in this article.</span></span>  <span data-ttu-id="2cb7f-106">它是正在重写。</span><span class="sxs-lookup"><span data-stu-id="2cb7f-106">It is being rewritten.</span></span>  <span data-ttu-id="2cb7f-107">请参阅[问题 #666](https://github.com/dotnet/docs/issues/666)若要了解有关所做的更改。</span><span class="sxs-lookup"><span data-stu-id="2cb7f-107">See [Issue #666](https://github.com/dotnet/docs/issues/666) to learn about the changes.</span></span>

<span data-ttu-id="2cb7f-108">异步编程 F # 中可以通过设计为易于使用和自然语言的语言级别编程模型来完成。</span><span class="sxs-lookup"><span data-stu-id="2cb7f-108">Async programming in F# can be accomplished through a language-level programming model designed to be easy to use and natural to the language.</span></span>

<span data-ttu-id="2cb7f-109">F # 中的异步编程的核心是`Async<'T>`，可以触发在后台中运行的工作的表示其中`'T`通过这两个特殊返回的任一类型`return`关键字或`unit`如果异步工作流未包含任何若要返回的结果。</span><span class="sxs-lookup"><span data-stu-id="2cb7f-109">The core of async programming in F# is `Async<'T>`, a representation of work that can be triggered to run in the background, where `'T` is either the type returned via the special `return` keyword or `unit` if the async workflow has no result to return.</span></span>

<span data-ttu-id="2cb7f-110">若要了解的关键概念是一个异步表达式的类型是`Async<'T>`，即仅_规范_进行异步上下文中工作。</span><span class="sxs-lookup"><span data-stu-id="2cb7f-110">The key concept to understand is that an async expression’s type is `Async<'T>`, which is merely a _specification_ of work to be done in an asynchronous context.</span></span> <span data-ttu-id="2cb7f-111">它不执行显式启动之前与起始函数之一 (如`Async.RunSynchronously`)。</span><span class="sxs-lookup"><span data-stu-id="2cb7f-111">It is not executed until you explicitly start it with one of the starting functions (such as `Async.RunSynchronously`).</span></span> <span data-ttu-id="2cb7f-112">虽然这是另一种执行工作的考虑，它最终正在实际上非常简单。</span><span class="sxs-lookup"><span data-stu-id="2cb7f-112">Although this is a different way of thinking about doing work, it ends up being quite simple in practice.</span></span>

<span data-ttu-id="2cb7f-113">例如，假设你想要从 dotnetfoundation.org 下载 HTML，而不会阻止主线程。</span><span class="sxs-lookup"><span data-stu-id="2cb7f-113">For example, say you wanted to download the HTML from dotnetfoundation.org without blocking the main thread.</span></span> <span data-ttu-id="2cb7f-114">你可以实现它如下：</span><span class="sxs-lookup"><span data-stu-id="2cb7f-114">You can accomplish it like this:</span></span>

```fsharp
open System
open System.Net

let fetchHtmlAsync url = 
    async {
        let uri = Uri(url)
        use webClient = new WebClient()

        // Execution of fetchHtmlAsync won't continue until the result
        // of AsyncDownloadString is bound.
        let! html = webClient.AsyncDownloadString(uri)
        return html
    }

let html = "http://dotnetfoundation.org" |> fetchHtmlAsync |> Async.RunSynchronously
printfn "%s" html
```

<span data-ttu-id="2cb7f-115">就是这么简单！</span><span class="sxs-lookup"><span data-stu-id="2cb7f-115">And that’s it!</span></span> <span data-ttu-id="2cb7f-116">除了使用外`async`， `let!`，和`return`，这是仅正常 F # 代码。</span><span class="sxs-lookup"><span data-stu-id="2cb7f-116">Aside from the use of `async`, `let!`, and `return`, this is just normal F# code.</span></span>

<span data-ttu-id="2cb7f-117">有几个语法构造该数据类型值得注意：</span><span class="sxs-lookup"><span data-stu-id="2cb7f-117">There are a few syntactical constructs which are worth noting:</span></span>

*   <span data-ttu-id="2cb7f-118">`let!`将绑定 （它运行在另一个上下文） 异步表达式的结果。</span><span class="sxs-lookup"><span data-stu-id="2cb7f-118">`let!` binds the result of an async expression (which runs on another context).</span></span>
*   <span data-ttu-id="2cb7f-119">`use!`工作方式就像`let!`，但在超出范围时释放其绑定的资源。</span><span class="sxs-lookup"><span data-stu-id="2cb7f-119">`use!` works just like `let!`, but disposes its bound resources when it goes out of scope.</span></span>
*   <span data-ttu-id="2cb7f-120">`do!`将等待异步工作流，它不返回任何内容。</span><span class="sxs-lookup"><span data-stu-id="2cb7f-120">`do!` will await an async workflow which doesn’t return anything.</span></span>
*   <span data-ttu-id="2cb7f-121">`return`只需从一个异步表达式将返回结果。</span><span class="sxs-lookup"><span data-stu-id="2cb7f-121">`return` simply returns a result from an async expression.</span></span>
*   <span data-ttu-id="2cb7f-122">`return!`执行另一个异步工作流并返回其返回值作为结果。</span><span class="sxs-lookup"><span data-stu-id="2cb7f-122">`return!` executes another async workflow and returns its return value as a result.</span></span>

<span data-ttu-id="2cb7f-123">此外，普通`let`， `use`，和`do`关键字可以与异步版本一起使用，就像一个常规函数中。</span><span class="sxs-lookup"><span data-stu-id="2cb7f-123">Additionally, normal `let`, `use`, and `do` keywords can be used alongside the async versions just as they would in a normal function.</span></span>

## <a name="how-to-start-async-code-in-f"></a><span data-ttu-id="2cb7f-124">如何启动 F # 中的异步代码</span><span class="sxs-lookup"><span data-stu-id="2cb7f-124">How to start Async Code in F#</span></span> #

<span data-ttu-id="2cb7f-125">如前所述，异步代码是的需要显式启动另一个上下文中进行工作的规范。</span><span class="sxs-lookup"><span data-stu-id="2cb7f-125">As mentioned earlier, async code is a specification of work to be done in another context which needs to be explicitly started.</span></span> <span data-ttu-id="2cb7f-126">以下是两种主要方式来实现此目的：</span><span class="sxs-lookup"><span data-stu-id="2cb7f-126">Here are two primary ways to accomplish this:</span></span>

1.  <span data-ttu-id="2cb7f-127">`Async.RunSynchronously`将在另一个线程上启动的异步工作流，并等待其结果。</span><span class="sxs-lookup"><span data-stu-id="2cb7f-127">`Async.RunSynchronously` will start an async workflow on another thread and await its result.</span></span>

```fsharp
open System
open System.Net

let fetchHtmlAsync url = 
    async {
        let uri = Uri(url)
        use webClient = new WebClient()
        let! html = webClient.AsyncDownloadString(uri)
        return html
    }

 // Execution will pause until fetchHtmlAsync finishes
 let html = "http://dotnetfoundation.org" |> fetchHtmlAsync |> Async.RunSynchronously

 // you actually have the result from fetchHtmlAsync now!
 printfn "%s" html
 ```

2.  <span data-ttu-id="2cb7f-128">`Async.Start`将在另一个线程上启动的异步工作流并将**不**等待其结果。</span><span class="sxs-lookup"><span data-stu-id="2cb7f-128">`Async.Start` will start an async workflow on another thread, and will **not** await its result.</span></span>

```fsharp
open System
open System.Net
  
let uploadDataAsync url data = 
    async {
        let uri = Uri(url)
        use webClient = new WebClient()
        webClient.UploadStringAsync(uri, data)
    }

let workflow = uploadDataAsync "http://url-to-upload-to.com" "hello, world!"

// Execution will continue after calling this!
Async.Start(workflow)

printfn "%s" "uploadDataAsync is running in the background..."
 ```

<span data-ttu-id="2cb7f-129">还有其他方法来启动异步工作流可用于更具体的方案。</span><span class="sxs-lookup"><span data-stu-id="2cb7f-129">There are other ways to start an async workflow available for more specific scenarios.</span></span> <span data-ttu-id="2cb7f-130">对其进行详细[异步引用中](https://msdn.microsoft.com/library/ee370232.aspx)。</span><span class="sxs-lookup"><span data-stu-id="2cb7f-130">They are detailed [in the Async reference](https://msdn.microsoft.com/library/ee370232.aspx).</span></span>

### <a name="a-note-on-threads"></a><span data-ttu-id="2cb7f-131">在线程上注释</span><span class="sxs-lookup"><span data-stu-id="2cb7f-131">A Note on Threads</span></span>

<span data-ttu-id="2cb7f-132">上述"在另一个线程"短语，但务必要知道**这并不意味着异步工作流是的外观的多线程处理**。</span><span class="sxs-lookup"><span data-stu-id="2cb7f-132">The phrase "on another thread" is mentioned above, but it is important to know that **this does not mean that async workflows are a facade for multithreading**.</span></span> <span data-ttu-id="2cb7f-133">工作流实际上"跳转"之间线程，借贷它们对于少量的时间来执行有用的工作。</span><span class="sxs-lookup"><span data-stu-id="2cb7f-133">The workflow actually "jumps" between threads, borrowing them for a small amount of time to do useful work.</span></span> <span data-ttu-id="2cb7f-134">时的异步工作流有效地"等待"（例如，等待为返回的内容的网络调用），它已在时间借贷任何线程将被释放到转有用的工作上其他内容。</span><span class="sxs-lookup"><span data-stu-id="2cb7f-134">When an async workflow is effectively "waiting" (for example, waiting for a network call to return something), any thread it was borrowing at the time is freed up to go do useful work on something else.</span></span> <span data-ttu-id="2cb7f-135">这允许的系统在其运行尽可能情况下，有效地利用异步工作流，并使它们尤其是对于大量 I/O 方案强。</span><span class="sxs-lookup"><span data-stu-id="2cb7f-135">This allows async workflows to utilize the system they run on as effectively as possible, and makes them especially strong for high-volume I/O scenarios.</span></span>

## <a name="how-to-add-parallelism-to-async-code"></a><span data-ttu-id="2cb7f-136">如何将并行添加到异步代码</span><span class="sxs-lookup"><span data-stu-id="2cb7f-136">How to Add Parallelism to Async Code</span></span>

<span data-ttu-id="2cb7f-137">有时你可能需要并行执行多个异步作业收集其结果和解释它们以某种方式。</span><span class="sxs-lookup"><span data-stu-id="2cb7f-137">Sometimes you may need to perform multiple asynchronous jobs in parallel, collect their results, and interpret them in some way.</span></span> <span data-ttu-id="2cb7f-138">`Async.Parallel`允许你执行此操作而无需使用任务并行库，这将涉及到无需强制`Task<'T>`和`Async<'T>`类型。</span><span class="sxs-lookup"><span data-stu-id="2cb7f-138">`Async.Parallel` allows you to do this without needing to use the Task Parallel Library, which would involve needing to coerce `Task<'T>` and `Async<'T>` types.</span></span>

<span data-ttu-id="2cb7f-139">下面的示例将使用`Async.Parallel`若要从并行的四个流行网站下载的 HTML，等待这些任务完成，然后输出下载的 HTML。</span><span class="sxs-lookup"><span data-stu-id="2cb7f-139">The following example will use `Async.Parallel` to download the HTML from four popular sites in parallel, wait for those tasks to complete, and then print the HTML which was downloaded.</span></span>

```fsharp
open System
open System.Net

let urlList = 
    [ "http://www.microsoft.com"
      "http://www.google.com"
      "http://www.amazon.com"
      "http://www.facebook.com" ]

let fetchHtmlAsync url = 
    async {
        let uri = Uri(url)
        use webClient = new WebClient()
        let! html = webClient.AsyncDownloadString(uri)
        return html
    }

let getHtmlList urls =
    urls
    |> Seq.map fetchHtmlAsync   // Build an Async<'T> for each site
    |> Async.Parallel           // Returns an Async<'T []>
    |> Async.RunSynchronously   // Wait for the result of the parallel work

let htmlList = getHtmlList urlList

// We now have the downloaded HTML for each site!
for html in htmlList do
    printfn "%s" html
```

## <a name="important-info-and-advice"></a><span data-ttu-id="2cb7f-140">重要信息和建议</span><span class="sxs-lookup"><span data-stu-id="2cb7f-140">Important Info and Advice</span></span>

*   <span data-ttu-id="2cb7f-141">将"Async"追加到你将使用的任何函数的末尾</span><span class="sxs-lookup"><span data-stu-id="2cb7f-141">Append "Async" to the end of any functions you’ll consume</span></span>

 <span data-ttu-id="2cb7f-142">尽管这是命名约定，但它确实使 API 可发现性等更容易。</span><span class="sxs-lookup"><span data-stu-id="2cb7f-142">Although this is just a naming convention, it does make things like API discoverability easier.</span></span> <span data-ttu-id="2cb7f-143">特别是如果有相同的例程的同步和异步版本，则这是异步通过名称来显式声明一个好办法。</span><span class="sxs-lookup"><span data-stu-id="2cb7f-143">Particularly if there are synchronous and asynchronous versions of the same routine, it’s a good idea to explicitly state which is asynchronous via the name.</span></span>

*   <span data-ttu-id="2cb7f-144">侦听编译器 ！</span><span class="sxs-lookup"><span data-stu-id="2cb7f-144">Listen to the compiler!</span></span>

 <span data-ttu-id="2cb7f-145">F # 编译器是非常严格，使几乎不可能执行其他操作如 troubling 同步运行"async"代码。</span><span class="sxs-lookup"><span data-stu-id="2cb7f-145">F#’s compiler is very strict, making it nearly impossible to do something troubling like run "async" code synchronously.</span></span> <span data-ttu-id="2cb7f-146">如果您遇到一条警告，则代码不会执行你认为它将一个符号。</span><span class="sxs-lookup"><span data-stu-id="2cb7f-146">If you come across a warning, that’s a sign that the code won’t execute how you think it will.</span></span> <span data-ttu-id="2cb7f-147">如果编译器可以为取悦，你的代码将很可能会按预期方式执行。</span><span class="sxs-lookup"><span data-stu-id="2cb7f-147">If you can make the compiler happy, your code will most likely execute as expected.</span></span>

## <a name="for-the-cvb-programmer-looking-into-f"></a><span data-ttu-id="2cb7f-148">为 C# /VB 程序员研究 F #</span><span class="sxs-lookup"><span data-stu-id="2cb7f-148">For the C#/VB Programmer Looking Into F#</span></span> #

<span data-ttu-id="2cb7f-149">本部分假定你熟悉 C# 中的异步模型 / VB.</span><span class="sxs-lookup"><span data-stu-id="2cb7f-149">This section assumes you’re familiar with the async model in C#/VB.</span></span> <span data-ttu-id="2cb7f-150">如果你不可以， [C# 中的异步编程](../../../csharp/async.md)是一个起始点。</span><span class="sxs-lookup"><span data-stu-id="2cb7f-150">If you are not, [Async Programming in C#](../../../csharp/async.md) is a starting point.</span></span>

<span data-ttu-id="2cb7f-151">没有本质上 C# /VB 异步模型和 F # 异步模型之间的区别。</span><span class="sxs-lookup"><span data-stu-id="2cb7f-151">There is a fundamental difference between the C#/VB async model and the F# async model.</span></span>

<span data-ttu-id="2cb7f-152">当调用返回的函数`Task`或`Task<'T>`，该作业是否已经开始执行。</span><span class="sxs-lookup"><span data-stu-id="2cb7f-152">When you call a function which returns a `Task` or `Task<'T>`, that job has already begun execution.</span></span> <span data-ttu-id="2cb7f-153">返回的句柄表示已在运行异步作业。</span><span class="sxs-lookup"><span data-stu-id="2cb7f-153">The handle returned represents an already-running asynchronous job.</span></span> <span data-ttu-id="2cb7f-154">与此相反，当你调用的异步函数在 F # 中，`Async<'a>`返回表示一个作业，它将**生成**在某个时间点。</span><span class="sxs-lookup"><span data-stu-id="2cb7f-154">In contrast, when you call an async function in F#, the `Async<'a>` returned represents a job which will be **generated** at some point.</span></span> <span data-ttu-id="2cb7f-155">了解此模型是功能强大，因为它允许 F # 中的异步作业可以链接在一起变得更容易，有条件地执行和入门的更细粒度的控制。</span><span class="sxs-lookup"><span data-stu-id="2cb7f-155">Understanding this model is powerful, because it allows for asynchronous jobs in F# to be chained together easier, performed conditionally, and be started with a finer grain of control.</span></span>

<span data-ttu-id="2cb7f-156">有几个其他的相似之处和值得注意的区别。</span><span class="sxs-lookup"><span data-stu-id="2cb7f-156">There are a few other similarities and differences worth noting.</span></span>

### <a name="similarities"></a><span data-ttu-id="2cb7f-157">相似之处</span><span class="sxs-lookup"><span data-stu-id="2cb7f-157">Similarities</span></span>

*   <span data-ttu-id="2cb7f-158">`let!``use!`，和`do!`类似于`await`内调用异步作业时`async{ }`块。</span><span class="sxs-lookup"><span data-stu-id="2cb7f-158">`let!`, `use!`, and `do!` are analogous to `await` when calling an async job from within an `async{ }` block.</span></span>

 <span data-ttu-id="2cb7f-159">三个关键字只能在`async { }`块，类似于如何`await`仅会在内部进行调用`async`方法。</span><span class="sxs-lookup"><span data-stu-id="2cb7f-159">The three keywords can only be used within an `async { }` block, similar to how `await` can only be invoked inside an `async` method.</span></span> <span data-ttu-id="2cb7f-160">简单地说，`let!`是为了确保你想要捕获和使用的结果时`use!`内容应会清理其资源，使用它之后, 是同一但和`do!`适用于你想要等待的异步工作流完成不返回值再继续。</span><span class="sxs-lookup"><span data-stu-id="2cb7f-160">In short, `let!` is for when you want to capture and use a result, `use!` is the same but for something whose resources should get cleaned after it’s used, and `do!` is for when you want to wait for an async workflow with no return value to finish before moving on.</span></span>

*   <span data-ttu-id="2cb7f-161">F # 支持类似的方式的数据并行。</span><span class="sxs-lookup"><span data-stu-id="2cb7f-161">F# supports data-parallelism in a similar way.</span></span>

 <span data-ttu-id="2cb7f-162">虽然它的操作方式差别很大，`Async.Parallel`对应于`Task.WhenAll`了所需的一组异步作业的结果，它们都完成时的方案。</span><span class="sxs-lookup"><span data-stu-id="2cb7f-162">Although it operates very differently, `Async.Parallel` corresponds to `Task.WhenAll` for the scenario of wanting the results of a set of async jobs when they all complete.</span></span>

### <a name="differences"></a><span data-ttu-id="2cb7f-163">差异</span><span class="sxs-lookup"><span data-stu-id="2cb7f-163">Differences</span></span>

*   <span data-ttu-id="2cb7f-164">嵌套`let!`不允许，与不同嵌套`await`</span><span class="sxs-lookup"><span data-stu-id="2cb7f-164">Nested `let!` is not allowed, unlike nested `await`</span></span>

 <span data-ttu-id="2cb7f-165">与不同`await`，可以嵌套; 如果无限期，`let!`无法，并且必须绑定使用在另一个内部之前其结果`let!`， `do!`，或`use!`。</span><span class="sxs-lookup"><span data-stu-id="2cb7f-165">Unlike `await`, which can be nested indefinitely, `let!` cannot and must have its result bound before using it inside of another `let!`, `do!`, or `use!`.</span></span>

*   <span data-ttu-id="2cb7f-166">取消支持为在 F # 中比在 C# 中更简单 / VB.</span><span class="sxs-lookup"><span data-stu-id="2cb7f-166">Cancellation support is simpler in F# than in C#/VB.</span></span>

 <span data-ttu-id="2cb7f-167">在 C# /VB 中支持的中途其执行任务的取消需要检查`IsCancellationRequested`属性或调用`ThrowIfCancellationRequested()`上`CancellationToken`传递给异步方法的对象。</span><span class="sxs-lookup"><span data-stu-id="2cb7f-167">Supporting cancellation of a task midway through its execution in C#/VB requires checking the `IsCancellationRequested` property or calling `ThrowIfCancellationRequested()` on a `CancellationToken` object that’s passed into the async method.</span></span>

<span data-ttu-id="2cb7f-168">与此相反，F # 异步工作流是更自然可取消的。</span><span class="sxs-lookup"><span data-stu-id="2cb7f-168">In contrast, F# async workflows are more naturally cancellable.</span></span> <span data-ttu-id="2cb7f-169">取消是一个简单的三个步骤过程。</span><span class="sxs-lookup"><span data-stu-id="2cb7f-169">Cancellation is a simple three-step process.</span></span>

1.  <span data-ttu-id="2cb7f-170">创建一个新的 `CancellationTokenSource`。</span><span class="sxs-lookup"><span data-stu-id="2cb7f-170">Create a new `CancellationTokenSource`.</span></span>
2.  <span data-ttu-id="2cb7f-171">将它传递到起始函数。</span><span class="sxs-lookup"><span data-stu-id="2cb7f-171">Pass it into a starting function.</span></span>
3.  <span data-ttu-id="2cb7f-172">调用`Cancel`令牌上。</span><span class="sxs-lookup"><span data-stu-id="2cb7f-172">Call `Cancel` on the token.</span></span>

<span data-ttu-id="2cb7f-173">示例:</span><span class="sxs-lookup"><span data-stu-id="2cb7f-173">Example:</span></span>

```fsharp
open System
open System.Net

let uploadDataAsync url data = 
    async {
        let uri = Uri(url)
        use webClient = new WebClient()
        webClient.UploadStringAsync(uri, data)
    }

let workflow = uploadDataAsync "http://url-to-upload-to.com" "hello, world!"

let token = new CancellationTokenSource()
Async.Start (workflow, token)

// Immediately cancel uploadDataAsync after it's been started.
token.Cancel()
```

<span data-ttu-id="2cb7f-174">就是这么简单！</span><span class="sxs-lookup"><span data-stu-id="2cb7f-174">And that’s it!</span></span>

## <a name="further-resources"></a><span data-ttu-id="2cb7f-175">其他资源：</span><span class="sxs-lookup"><span data-stu-id="2cb7f-175">Further resources:</span></span>

*   [<span data-ttu-id="2cb7f-176">MSDN 上的异步工作流</span><span class="sxs-lookup"><span data-stu-id="2cb7f-176">Async Workflows on MSDN</span></span>](https://msdn.microsoft.com/library/dd233250.aspx)
*   [<span data-ttu-id="2cb7f-177">F # 的异步序列</span><span class="sxs-lookup"><span data-stu-id="2cb7f-177">Asynchronous Sequences for F#</span></span>](http://fsprojects.github.io/FSharp.Control.AsyncSeq/library/AsyncSeq.html)
*   [<span data-ttu-id="2cb7f-178">F # 数据 HTTP 实用程序</span><span class="sxs-lookup"><span data-stu-id="2cb7f-178">F# Data HTTP Utilities</span></span>](https://fsharp.github.io/FSharp.Data/library/Http.html)
