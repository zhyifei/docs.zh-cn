---
title: 异步编程
description: 了解如何F#通过是易于使用和自然语言的语言级别编程模型实现异步编程。
ms.date: 06/20/2016
ms.openlocfilehash: 6925a0132f9beed6be5f9dded3630b551072bea2
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/09/2019
ms.locfileid: "59343449"
---
# <a name="async-programming-in-f"></a><span data-ttu-id="392fb-103">F 中的异步编程\#</span><span class="sxs-lookup"><span data-stu-id="392fb-103">Async Programming in F\#</span></span>

> [!NOTE]
> <span data-ttu-id="392fb-104">在本文中发现了一些错误。</span><span class="sxs-lookup"><span data-stu-id="392fb-104">Some inaccuracies have been discovered in this article.</span></span>  <span data-ttu-id="392fb-105">它是被重写。</span><span class="sxs-lookup"><span data-stu-id="392fb-105">It is being rewritten.</span></span>  <span data-ttu-id="392fb-106">请参阅[问题 #666](https://github.com/dotnet/docs/issues/666)若要了解有关所做的更改。</span><span class="sxs-lookup"><span data-stu-id="392fb-106">See [Issue #666](https://github.com/dotnet/docs/issues/666) to learn about the changes.</span></span>

<span data-ttu-id="392fb-107">异步编程中F#可以通过设计为易于使用和自然语言的语言级别编程模型来完成。</span><span class="sxs-lookup"><span data-stu-id="392fb-107">Async programming in F# can be accomplished through a language-level programming model designed to be easy to use and natural to the language.</span></span>

<span data-ttu-id="392fb-108">异步编程中的核心F#是`Async<'T>`，表示形式可以触发以便在后台运行的工作位置`'T`通过特殊的返回类型`return`关键字或`unit`如果异步工作流具有要返回的结果。</span><span class="sxs-lookup"><span data-stu-id="392fb-108">The core of async programming in F# is `Async<'T>`, a representation of work that can be triggered to run in the background, where `'T` is either the type returned via the special `return` keyword or `unit` if the async workflow has no result to return.</span></span>

<span data-ttu-id="392fb-109">若要了解的关键概念在于异步表达式的类型是`Async<'T>`，即只_规范_的异步上下文中完成的工作。</span><span class="sxs-lookup"><span data-stu-id="392fb-109">The key concept to understand is that an async expression’s type is `Async<'T>`, which is merely a _specification_ of work to be done in an asynchronous context.</span></span> <span data-ttu-id="392fb-110">不执行直到它显式启动其中一个起始函数 (如`Async.RunSynchronously`)。</span><span class="sxs-lookup"><span data-stu-id="392fb-110">It is not executed until you explicitly start it with one of the starting functions (such as `Async.RunSynchronously`).</span></span> <span data-ttu-id="392fb-111">虽然这是以不同的方式考虑执行工作的但它最终实际上非常简单。</span><span class="sxs-lookup"><span data-stu-id="392fb-111">Although this is a different way of thinking about doing work, it ends up being quite simple in practice.</span></span>

<span data-ttu-id="392fb-112">例如，假设你想要从 dotnetfoundation.org 下载 HTML，而不会阻止主线程。</span><span class="sxs-lookup"><span data-stu-id="392fb-112">For example, say you wanted to download the HTML from dotnetfoundation.org without blocking the main thread.</span></span> <span data-ttu-id="392fb-113">您可以实现它像这样：</span><span class="sxs-lookup"><span data-stu-id="392fb-113">You can accomplish it like this:</span></span>

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

let html = "https://dotnetfoundation.org" |> fetchHtmlAsync |> Async.RunSynchronously
printfn "%s" html
```

<span data-ttu-id="392fb-114">就是这么简单！</span><span class="sxs-lookup"><span data-stu-id="392fb-114">And that’s it!</span></span> <span data-ttu-id="392fb-115">除了使用`async`， `let!`，并`return`，这是正常的只是F#代码。</span><span class="sxs-lookup"><span data-stu-id="392fb-115">Aside from the use of `async`, `let!`, and `return`, this is just normal F# code.</span></span>

<span data-ttu-id="392fb-116">有几个语法构造是值得一提：</span><span class="sxs-lookup"><span data-stu-id="392fb-116">There are a few syntactical constructs which are worth noting:</span></span>

*   `let!` <span data-ttu-id="392fb-117">将一个异步表达式 （其在另一个上下文中运行） 的结果绑定。</span><span class="sxs-lookup"><span data-stu-id="392fb-117">binds the result of an async expression (which runs on another context).</span></span>
*   `use!` <span data-ttu-id="392fb-118">工作方式就类似于`let!`，但它超出范围时释放其绑定的资源。</span><span class="sxs-lookup"><span data-stu-id="392fb-118">works just like `let!`, but disposes its bound resources when it goes out of scope.</span></span>
*   `do!` <span data-ttu-id="392fb-119">将 await 的异步工作流，这不会返回任何内容。</span><span class="sxs-lookup"><span data-stu-id="392fb-119">will await an async workflow which doesn’t return anything.</span></span>
*   `return` <span data-ttu-id="392fb-120">只需从异步表达式将返回结果。</span><span class="sxs-lookup"><span data-stu-id="392fb-120">simply returns a result from an async expression.</span></span>
*   `return!` <span data-ttu-id="392fb-121">执行另一个异步工作流并返回其返回值作为结果。</span><span class="sxs-lookup"><span data-stu-id="392fb-121">executes another async workflow and returns its return value as a result.</span></span>

<span data-ttu-id="392fb-122">此外，正常`let`， `use`，和`do`关键字可以用异步版本，就像在普通函数中。</span><span class="sxs-lookup"><span data-stu-id="392fb-122">Additionally, normal `let`, `use`, and `do` keywords can be used alongside the async versions just as they would in a normal function.</span></span>

## <a name="how-to-start-async-code-in-f"></a><span data-ttu-id="392fb-123">如何在 F 中启动异步代码\#</span><span class="sxs-lookup"><span data-stu-id="392fb-123">How to start Async Code in F\#</span></span>

<span data-ttu-id="392fb-124">前面曾提到，异步代码将是一种规范，需要对其显式启动另一个上下文中完成工作。</span><span class="sxs-lookup"><span data-stu-id="392fb-124">As mentioned earlier, async code is a specification of work to be done in another context which needs to be explicitly started.</span></span> <span data-ttu-id="392fb-125">下面是两种主要方法来实现此目的：</span><span class="sxs-lookup"><span data-stu-id="392fb-125">Here are two primary ways to accomplish this:</span></span>

1. `Async.RunSynchronously` <span data-ttu-id="392fb-126">将另一个线程上启动异步工作流，并等待其结果。</span><span class="sxs-lookup"><span data-stu-id="392fb-126">will start an async workflow on another thread and await its result.</span></span>

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
 let html = "https://dotnetfoundation.org" |> fetchHtmlAsync |> Async.RunSynchronously

 // you actually have the result from fetchHtmlAsync now!
 printfn "%s" html
 ```

2. `Async.Start` <span data-ttu-id="392fb-127">将另一个线程上启动的异步工作流，并将**不**等待其结果。</span><span class="sxs-lookup"><span data-stu-id="392fb-127">will start an async workflow on another thread, and will **not** await its result.</span></span>

```fsharp
open System
open System.Net
  
let uploadDataAsync url data = 
    async {
        let uri = Uri(url)
        use webClient = new WebClient()
        webClient.UploadStringAsync(uri, data)
    }

let workflow = uploadDataAsync "https://url-to-upload-to.com" "hello, world!"

// Execution will continue after calling this!
Async.Start(workflow)

printfn "%s" "uploadDataAsync is running in the background..."
 ```

<span data-ttu-id="392fb-128">还有其他方法来启动异步工作流可用于更多特定方案。</span><span class="sxs-lookup"><span data-stu-id="392fb-128">There are other ways to start an async workflow available for more specific scenarios.</span></span> <span data-ttu-id="392fb-129">对其进行详细[异步参考中](https://msdn.microsoft.com/library/ee370232.aspx)。</span><span class="sxs-lookup"><span data-stu-id="392fb-129">They are detailed [in the Async reference](https://msdn.microsoft.com/library/ee370232.aspx).</span></span>

### <a name="a-note-on-threads"></a><span data-ttu-id="392fb-130">有关线程的说明</span><span class="sxs-lookup"><span data-stu-id="392fb-130">A Note on Threads</span></span>

<span data-ttu-id="392fb-131">上述"在另一个线程"短语，但务必要知道**这并不意味着异步工作流是用于的外观的多线程处理**。</span><span class="sxs-lookup"><span data-stu-id="392fb-131">The phrase "on another thread" is mentioned above, but it is important to know that **this does not mean that async workflows are a facade for multithreading**.</span></span> <span data-ttu-id="392fb-132">工作流实际"跳转"借用的少量时间来执行有用的工作线程之间。</span><span class="sxs-lookup"><span data-stu-id="392fb-132">The workflow actually "jumps" between threads, borrowing them for a small amount of time to do useful work.</span></span> <span data-ttu-id="392fb-133">时异步工作流有效地"等待"（例如，等待网络调用，以返回某些内容），在时，它借用了任何线程被释放到转执行有用的工作在别的事情上。</span><span class="sxs-lookup"><span data-stu-id="392fb-133">When an async workflow is effectively "waiting" (for example, waiting for a network call to return something), any thread it was borrowing at the time is freed up to go do useful work on something else.</span></span> <span data-ttu-id="392fb-134">这允许异步工作流，以利用它们尽可能有效地运行的系统并使这些极强的大量 I/O 方案。</span><span class="sxs-lookup"><span data-stu-id="392fb-134">This allows async workflows to utilize the system they run on as effectively as possible, and makes them especially strong for high-volume I/O scenarios.</span></span>

## <a name="how-to-add-parallelism-to-async-code"></a><span data-ttu-id="392fb-135">如何将并行处理添加到异步代码</span><span class="sxs-lookup"><span data-stu-id="392fb-135">How to Add Parallelism to Async Code</span></span>

<span data-ttu-id="392fb-136">有时您可能需要并行执行多个异步作业收集其结果，并以某种方式进行解释。</span><span class="sxs-lookup"><span data-stu-id="392fb-136">Sometimes you may need to perform multiple asynchronous jobs in parallel, collect their results, and interpret them in some way.</span></span> `Async.Parallel` <span data-ttu-id="392fb-137">允许您执行此操作而无需使用任务并行库，这会涉及无需强制转换`Task<'T>`和`Async<'T>`类型。</span><span class="sxs-lookup"><span data-stu-id="392fb-137">allows you to do this without needing to use the Task Parallel Library, which would involve needing to coerce `Task<'T>` and `Async<'T>` types.</span></span>

<span data-ttu-id="392fb-138">下面的示例将使用`Async.Parallel`从并行的四个常用网站下载 HTML，等待这些任务完成，然后输出已下载的 HTML。</span><span class="sxs-lookup"><span data-stu-id="392fb-138">The following example will use `Async.Parallel` to download the HTML from four popular sites in parallel, wait for those tasks to complete, and then print the HTML which was downloaded.</span></span>

```fsharp
open System
open System.Net

let urlList = 
    [ "https://www.microsoft.com"
      "https://www.google.com"
      "https://www.amazon.com"
      "https://www.facebook.com" ]

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

## <a name="important-info-and-advice"></a><span data-ttu-id="392fb-139">重要信息和建议</span><span class="sxs-lookup"><span data-stu-id="392fb-139">Important Info and Advice</span></span>

*   <span data-ttu-id="392fb-140">将"Async"追加到末尾将使用的任何函数</span><span class="sxs-lookup"><span data-stu-id="392fb-140">Append "Async" to the end of any functions you’ll consume</span></span>

 <span data-ttu-id="392fb-141">虽然这是命名约定，但它确实使 API 可发现性等内容更容易。</span><span class="sxs-lookup"><span data-stu-id="392fb-141">Although this is just a naming convention, it does make things like API discoverability easier.</span></span> <span data-ttu-id="392fb-142">尤其是例程的当有相同的同步和异步版本，它是例程的显式声明为异步通过名称的一个好办法。</span><span class="sxs-lookup"><span data-stu-id="392fb-142">Particularly if there are synchronous and asynchronous versions of the same routine, it’s a good idea to explicitly state which is asynchronous via the name.</span></span>

*   <span data-ttu-id="392fb-143">侦听编译器 ！</span><span class="sxs-lookup"><span data-stu-id="392fb-143">Listen to the compiler!</span></span>

 <span data-ttu-id="392fb-144">F#编译器是非常严格，因此几乎不可能执行一些麻烦的问题等操作以同步方式运行"async"代码。</span><span class="sxs-lookup"><span data-stu-id="392fb-144">F#’s compiler is very strict, making it nearly impossible to do something troubling like run "async" code synchronously.</span></span> <span data-ttu-id="392fb-145">如果您遇到一条警告，则代码不会执行认为它将如何登录。</span><span class="sxs-lookup"><span data-stu-id="392fb-145">If you come across a warning, that’s a sign that the code won’t execute how you think it will.</span></span> <span data-ttu-id="392fb-146">如果编译器可以为取悦，按预期方式将很可能执行代码。</span><span class="sxs-lookup"><span data-stu-id="392fb-146">If you can make the compiler happy, your code will most likely execute as expected.</span></span>

## <a name="for-the-cvb-programmer-looking-into-f"></a><span data-ttu-id="392fb-147">有关C#/VB 程序员研究 F\#</span><span class="sxs-lookup"><span data-stu-id="392fb-147">For the C#/VB Programmer Looking Into F\#</span></span>

<span data-ttu-id="392fb-148">本部分假定您熟悉使用中的异步模型C#/VB.</span><span class="sxs-lookup"><span data-stu-id="392fb-148">This section assumes you’re familiar with the async model in C#/VB.</span></span> <span data-ttu-id="392fb-149">如果你不可以，[中的异步编程C#](../../../csharp/async.md)是一个起始点。</span><span class="sxs-lookup"><span data-stu-id="392fb-149">If you are not, [Async Programming in C#](../../../csharp/async.md) is a starting point.</span></span>

<span data-ttu-id="392fb-150">没有本质上之间的区别C#/VB 异步模型和F#异步模型。</span><span class="sxs-lookup"><span data-stu-id="392fb-150">There is a fundamental difference between the C#/VB async model and the F# async model.</span></span>

<span data-ttu-id="392fb-151">当调用一个函数，它返回`Task`或`Task<'T>`，该作业已开始执行。</span><span class="sxs-lookup"><span data-stu-id="392fb-151">When you call a function which returns a `Task` or `Task<'T>`, that job has already begun execution.</span></span> <span data-ttu-id="392fb-152">返回的句柄表示已在运行异步作业。</span><span class="sxs-lookup"><span data-stu-id="392fb-152">The handle returned represents an already-running asynchronous job.</span></span> <span data-ttu-id="392fb-153">与此相反，当您调用异步函数F#，则`Async<'a>`返回表示一个作业，它将是**生成**在某个时间点。</span><span class="sxs-lookup"><span data-stu-id="392fb-153">In contrast, when you call an async function in F#, the `Async<'a>` returned represents a job which will be **generated** at some point.</span></span> <span data-ttu-id="392fb-154">了解此模型非常强大，因为它允许在异步作业F#链接起来变得更容易，有条件地执行和入门的更细粒度的控制。</span><span class="sxs-lookup"><span data-stu-id="392fb-154">Understanding this model is powerful, because it allows for asynchronous jobs in F# to be chained together easier, performed conditionally, and be started with a finer grain of control.</span></span>

<span data-ttu-id="392fb-155">有几个其他的相似之处和值得注意的区别。</span><span class="sxs-lookup"><span data-stu-id="392fb-155">There are a few other similarities and differences worth noting.</span></span>

### <a name="similarities"></a><span data-ttu-id="392fb-156">相似之处</span><span class="sxs-lookup"><span data-stu-id="392fb-156">Similarities</span></span>

*   `let!`<span data-ttu-id="392fb-157">`use!`，并`do!`类似于`await`内调用的异步作业时`async{ }`块。</span><span class="sxs-lookup"><span data-stu-id="392fb-157">, `use!`, and `do!` are analogous to `await` when calling an async job from within an `async{ }` block.</span></span>

 <span data-ttu-id="392fb-158">只能在使用三个关键字`async { }`块中，类似于如何`await`只能在调用`async`方法。</span><span class="sxs-lookup"><span data-stu-id="392fb-158">The three keywords can only be used within an `async { }` block, similar to how `await` can only be invoked inside an `async` method.</span></span> <span data-ttu-id="392fb-159">简单地说，`let!`适用于你想要捕获和使用结果`use!`是相同，但某些内容在使用后，应会清理其资源和`do!`适用于你想要等待的异步工作流完成不返回值再继续。</span><span class="sxs-lookup"><span data-stu-id="392fb-159">In short, `let!` is for when you want to capture and use a result, `use!` is the same but for something whose resources should get cleaned after it’s used, and `do!` is for when you want to wait for an async workflow with no return value to finish before moving on.</span></span>

*   <span data-ttu-id="392fb-160">F#类似的方式支持数据并行。</span><span class="sxs-lookup"><span data-stu-id="392fb-160">F# supports data-parallelism in a similar way.</span></span>

 <span data-ttu-id="392fb-161">尽管它以非常不同的方式，运行`Async.Parallel`对应于`Task.WhenAll`想的一组异步作业结果，它们全部完成时的方案。</span><span class="sxs-lookup"><span data-stu-id="392fb-161">Although it operates very differently, `Async.Parallel` corresponds to `Task.WhenAll` for the scenario of wanting the results of a set of async jobs when they all complete.</span></span>

### <a name="differences"></a><span data-ttu-id="392fb-162">差异</span><span class="sxs-lookup"><span data-stu-id="392fb-162">Differences</span></span>

*   <span data-ttu-id="392fb-163">嵌套`let!`不允许，与不同嵌套</span><span class="sxs-lookup"><span data-stu-id="392fb-163">Nested `let!` is not allowed, unlike nested</span></span> `await`

 <span data-ttu-id="392fb-164">与不同`await`，可以嵌套无限期`let!`能并且必须包含另一个内部使用它之前绑定其结果`let!`， `do!`，或`use!`。</span><span class="sxs-lookup"><span data-stu-id="392fb-164">Unlike `await`, which can be nested indefinitely, `let!` cannot and must have its result bound before using it inside of another `let!`, `do!`, or `use!`.</span></span>

*   <span data-ttu-id="392fb-165">取消支持是在F#比C#/VB.</span><span class="sxs-lookup"><span data-stu-id="392fb-165">Cancellation support is simpler in F# than in C#/VB.</span></span>

 <span data-ttu-id="392fb-166">支持的任务在执行中途取消C#/VB 需要检查`IsCancellationRequested`属性或调用`ThrowIfCancellationRequested()`上`CancellationToken`传递到异步方法的对象。</span><span class="sxs-lookup"><span data-stu-id="392fb-166">Supporting cancellation of a task midway through its execution in C#/VB requires checking the `IsCancellationRequested` property or calling `ThrowIfCancellationRequested()` on a `CancellationToken` object that’s passed into the async method.</span></span>

<span data-ttu-id="392fb-167">与此相反，F#异步工作流是更自然可取消。</span><span class="sxs-lookup"><span data-stu-id="392fb-167">In contrast, F# async workflows are more naturally cancellable.</span></span> <span data-ttu-id="392fb-168">取消是一个简单的三步骤过程。</span><span class="sxs-lookup"><span data-stu-id="392fb-168">Cancellation is a simple three-step process.</span></span>

1. <span data-ttu-id="392fb-169">创建一个新的 `CancellationTokenSource`。</span><span class="sxs-lookup"><span data-stu-id="392fb-169">Create a new `CancellationTokenSource`.</span></span>
2. <span data-ttu-id="392fb-170">将它传递到起始函数。</span><span class="sxs-lookup"><span data-stu-id="392fb-170">Pass it into a starting function.</span></span>
3. <span data-ttu-id="392fb-171">调用`Cancel`的令牌。</span><span class="sxs-lookup"><span data-stu-id="392fb-171">Call `Cancel` on the token.</span></span>

<span data-ttu-id="392fb-172">示例:</span><span class="sxs-lookup"><span data-stu-id="392fb-172">Example:</span></span>

```fsharp
open System.Threading

// Create a workflow which will loop forever.
let workflow =
    async {
        while true do
            printfn "Working..."
            do! Async.Sleep 1000
    }
    
let tokenSource = new CancellationTokenSource()

// Start the workflow in the background
Async.Start (workflow, tokenSource.Token)

// Executing the next line will stop the workflow
tokenSource.Cancel()
```

<span data-ttu-id="392fb-173">就是这么简单！</span><span class="sxs-lookup"><span data-stu-id="392fb-173">And that’s it!</span></span>

## <a name="further-resources"></a><span data-ttu-id="392fb-174">其他资源：</span><span class="sxs-lookup"><span data-stu-id="392fb-174">Further resources:</span></span>

*   [<span data-ttu-id="392fb-175">MSDN 上的异步工作流</span><span class="sxs-lookup"><span data-stu-id="392fb-175">Async Workflows on MSDN</span></span>](https://msdn.microsoft.com/library/dd233250.aspx)
*   [<span data-ttu-id="392fb-176">异步序列F#</span><span class="sxs-lookup"><span data-stu-id="392fb-176">Asynchronous Sequences for F#</span></span>](https://fsprojects.github.io/FSharp.Control.AsyncSeq/library/AsyncSeq.html)
*   [<span data-ttu-id="392fb-177">F#HTTP 数据实用程序</span><span class="sxs-lookup"><span data-stu-id="392fb-177">F# Data HTTP Utilities</span></span>](https://fsharp.github.io/FSharp.Data/library/Http.html)