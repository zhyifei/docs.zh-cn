---
title: 异步编程 - C#
description: 了解 .NET Core 提供的 C# 语言级别异步编程模式。
author: cartermp
ms.date: 06/20/2016
ms.assetid: b878c34c-a78f-419e-a594-a2b44fa521a4
ms.custom: seodec18
ms.openlocfilehash: 90fd7332242ed58d7716e248248e2c06a6ba023f
ms.sourcegitcommit: 462dc41a13942e467984e48f4018d1f79ae67346
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/19/2019
ms.locfileid: "58185735"
---
# <a name="asynchronous-programming"></a><span data-ttu-id="b6174-103">异步编程</span><span class="sxs-lookup"><span data-stu-id="b6174-103">Asynchronous programming</span></span>

<span data-ttu-id="b6174-104">如果需要 I/O 绑定（例如从网络请求数据或访问数据库），则需要利用异步编程。</span><span class="sxs-lookup"><span data-stu-id="b6174-104">If you have any I/O-bound needs (such as requesting data from a network or accessing a database), you'll want to utilize asynchronous programming.</span></span>  <span data-ttu-id="b6174-105">还可以使用 CPU 绑定代码（例如执行成本高昂的计算），对编写异步代码而言，这是一个不错的方案。</span><span class="sxs-lookup"><span data-stu-id="b6174-105">You could also have CPU-bound code, such as performing an expensive calculation, which is also a good scenario for writing async code.</span></span>

<span data-ttu-id="b6174-106">C# 拥有语言级别的异步编程模型，它使你能轻松编写异步代码，而无需应付回叫或符合支持异步的库。</span><span class="sxs-lookup"><span data-stu-id="b6174-106">C# has a language-level asynchronous programming model which allows for easily writing asynchronous code without having to juggle callbacks or conform to a library which supports asynchrony.</span></span> <span data-ttu-id="b6174-107">它遵循[基于任务的异步模式 (TAP)](../standard/asynchronous-programming-patterns/task-based-asynchronous-pattern-tap.md)。</span><span class="sxs-lookup"><span data-stu-id="b6174-107">It follows what is known as the [Task-based Asynchronous Pattern (TAP)](../standard/asynchronous-programming-patterns/task-based-asynchronous-pattern-tap.md).</span></span>

## <a name="basic-overview-of-the-asynchronous-model"></a><span data-ttu-id="b6174-108">异步模型的基本概述</span><span class="sxs-lookup"><span data-stu-id="b6174-108">Basic Overview of the Asynchronous Model</span></span>

<span data-ttu-id="b6174-109">异步编程的核心是 `Task` 和 `Task<T>` 对象，这两个对象对异步操作建模。</span><span class="sxs-lookup"><span data-stu-id="b6174-109">The core of async programming is the `Task` and `Task<T>` objects, which model asynchronous operations.</span></span>  <span data-ttu-id="b6174-110">它们受关键字 `async` 和 `await` 的支持。</span><span class="sxs-lookup"><span data-stu-id="b6174-110">They are supported by the `async` and `await` keywords.</span></span>  <span data-ttu-id="b6174-111">在大多数情况下模型十分简单：</span><span class="sxs-lookup"><span data-stu-id="b6174-111">The model is fairly simple in most cases:</span></span>

<span data-ttu-id="b6174-112">对于 I/O 绑定代码，当你 `await` 一个操作，它将返回 `async` 方法中的一个 `Task` 或 `Task<T>`。</span><span class="sxs-lookup"><span data-stu-id="b6174-112">For I/O-bound code, you `await` an operation which returns a `Task` or `Task<T>` inside of an `async` method.</span></span>

<span data-ttu-id="b6174-113">对于 CPU 绑定代码，当你 `await` 一个操作，它将在后台线程通过 `Task.Run` 方法启动。</span><span class="sxs-lookup"><span data-stu-id="b6174-113">For CPU-bound code, you `await` an operation which is started on a background thread with the `Task.Run` method.</span></span>

<span data-ttu-id="b6174-114">`await` 关键字有这奇妙的作用。</span><span class="sxs-lookup"><span data-stu-id="b6174-114">The `await` keyword is where the magic happens.</span></span> <span data-ttu-id="b6174-115">它控制执行 `await` 的方法的调用方，且它最终允许 UI 具有响应性或服务具有灵活性。</span><span class="sxs-lookup"><span data-stu-id="b6174-115">It yields control to the caller of the method that performed `await`, and it ultimately allows a UI to be responsive or a service to be elastic.</span></span>

<span data-ttu-id="b6174-116">除上方链接的 TAP 文章中介绍的 `async` 和 `await` 之外，还有其他处理异步代码的方法，但本文档将在下文中重点介绍语言级别的构造。</span><span class="sxs-lookup"><span data-stu-id="b6174-116">There are other ways to approach async code than `async` and `await` outlined in the TAP article linked above, but this document will focus on the language-level constructs from this point forward.</span></span>

### <a name="io-bound-example-downloading-data-from-a-web-service"></a><span data-ttu-id="b6174-117">I/O 绑定示例：从 Web 服务下载数据</span><span class="sxs-lookup"><span data-stu-id="b6174-117">I/O-Bound Example: Downloading data from a web service</span></span>

<span data-ttu-id="b6174-118">你可能需要在按下按钮时从 Web 服务下载某些数据，但不希望阻止 UI 线程。</span><span class="sxs-lookup"><span data-stu-id="b6174-118">You may need to download some data from a web service when a button is pressed, but don’t want to block the UI thread.</span></span> <span data-ttu-id="b6174-119">只需执行如下操作即可轻松实现：</span><span class="sxs-lookup"><span data-stu-id="b6174-119">It can be accomplished simply like this:</span></span>

```csharp
private readonly HttpClient _httpClient = new HttpClient();

downloadButton.Clicked += async (o, e) =>
{
    // This line will yield control to the UI as the request
    // from the web service is happening.
    //
    // The UI thread is now free to perform other work.
    var stringData = await _httpClient.GetStringAsync(URL);
    DoSomethingWithData(stringData);
};
```

<span data-ttu-id="b6174-120">就是这么简单！</span><span class="sxs-lookup"><span data-stu-id="b6174-120">And that’s it!</span></span> <span data-ttu-id="b6174-121">代码表示目的（异步下载某些数据），而不会在与任务对象的交互中停滞。</span><span class="sxs-lookup"><span data-stu-id="b6174-121">The code expresses the intent (downloading some data asynchronously) without getting bogged down in interacting with Task objects.</span></span>

### <a name="cpu-bound-example-performing-a-calculation-for-a-game"></a><span data-ttu-id="b6174-122">CPU 绑定示例：为游戏执行计算</span><span class="sxs-lookup"><span data-stu-id="b6174-122">CPU-bound Example: Performing a Calculation for a Game</span></span>

<span data-ttu-id="b6174-123">假设你正在编写一个移动游戏，在该游戏中，按下某个按钮将会对屏幕中的许多敌人造成伤害。</span><span class="sxs-lookup"><span data-stu-id="b6174-123">Say you're writing a mobile game where pressing a button can inflict damage on many enemies on the screen.</span></span>  <span data-ttu-id="b6174-124">执行伤害计算的开销可能极大，而且在 UI 线程中执行计算有可能使游戏在计算执行过程中暂停！</span><span class="sxs-lookup"><span data-stu-id="b6174-124">Performing the damage calculation can be expensive, and doing it on the UI thread would make the game appear to pause as the calculation is performed!</span></span>

<span data-ttu-id="b6174-125">此问题的最佳解决方法是启动一个后台线程，它使用 `Task.Run` 执行工作，并 `await` 其结果。</span><span class="sxs-lookup"><span data-stu-id="b6174-125">The best way to handle this is to start a background thread which does the work using `Task.Run`, and `await` its result.</span></span>  <span data-ttu-id="b6174-126">这可确保在执行工作时 UI 能流畅运行。</span><span class="sxs-lookup"><span data-stu-id="b6174-126">This will allow the UI to feel smooth as the work is being done.</span></span>

```csharp
private DamageResult CalculateDamageDone()
{
    // Code omitted:
    //
    // Does an expensive calculation and returns
    // the result of that calculation.
}


calculateButton.Clicked += async (o, e) =>
{
    // This line will yield control to the UI while CalculateDamageDone()
    // performs its work.  The UI thread is free to perform other work.
    var damageResult = await Task.Run(() => CalculateDamageDone());
    DisplayDamage(damageResult);
};
```

<span data-ttu-id="b6174-127">就是这么简单！</span><span class="sxs-lookup"><span data-stu-id="b6174-127">And that's it!</span></span>  <span data-ttu-id="b6174-128">此代码清楚地表达了按钮的单击事件的目的，它无需手动管理后台线程，而是通过非阻止性的方式来实现。</span><span class="sxs-lookup"><span data-stu-id="b6174-128">This code cleanly expresses the intent of the button's click event, it doesn't require managing a background thread manually, and it does so in a non-blocking way.</span></span>

### <a name="what-happens-under-the-covers"></a><span data-ttu-id="b6174-129">内部原理</span><span class="sxs-lookup"><span data-stu-id="b6174-129">What happens under the covers</span></span>

<span data-ttu-id="b6174-130">异步操作涉及许多移动部分。</span><span class="sxs-lookup"><span data-stu-id="b6174-130">There's a lot of moving pieces where asynchronous operations are concerned.</span></span>  <span data-ttu-id="b6174-131">若要了解 `Task` 和 `Task<T>` 的内部原理，请参阅[深入了解异步](../standard/async-in-depth.md)，以获取详细信息。</span><span class="sxs-lookup"><span data-stu-id="b6174-131">If you're curious about what's happening underneath the covers of `Task` and `Task<T>`, checkout the [Async in-depth](../standard/async-in-depth.md) article for more information.</span></span>

<span data-ttu-id="b6174-132">在 C# 方面，编译器将代码转换为状态机，它将跟踪类似以下内容：到达 `await` 时暂停执行以及后台作业完成时继续执行。</span><span class="sxs-lookup"><span data-stu-id="b6174-132">On the C# side of things, the compiler transforms your code into a state machine which keeps track of things like yielding execution when an `await` is reached and resuming execution when a background job has finished.</span></span>

<span data-ttu-id="b6174-133">从理论上讲，这是[异步的承诺模型](https://en.wikipedia.org/wiki/Futures_and_promises)的实现。</span><span class="sxs-lookup"><span data-stu-id="b6174-133">For the theoretically-inclined, this is an implementation of the [Promise Model of asynchrony](https://en.wikipedia.org/wiki/Futures_and_promises).</span></span>

## <a name="key-pieces-to-understand"></a><span data-ttu-id="b6174-134">需了解的要点</span><span class="sxs-lookup"><span data-stu-id="b6174-134">Key Pieces to Understand</span></span>

* <span data-ttu-id="b6174-135">异步代码可用于 I/O 绑定和 CPU 绑定代码，但在每个方案中有所不同。</span><span class="sxs-lookup"><span data-stu-id="b6174-135">Async code can be used for both I/O-bound and CPU-bound code, but differently for each scenario.</span></span>
* <span data-ttu-id="b6174-136">异步代码使用 `Task<T>` 和 `Task`，它们是对后台所完成的工作进行建模的构造。</span><span class="sxs-lookup"><span data-stu-id="b6174-136">Async code uses `Task<T>` and `Task`, which are constructs used to model work being done in the background.</span></span>
* <span data-ttu-id="b6174-137">`async` 关键字将方法转换为异步方法，这使你能在其正文中使用 `await` 关键字。</span><span class="sxs-lookup"><span data-stu-id="b6174-137">The `async` keyword turns a method into an async method, which allows you to use the `await` keyword in its body.</span></span>
* <span data-ttu-id="b6174-138">应用 `await` 关键字后，它将挂起调用方法，并将控制权返还给调用方，直到等待的任务完成。</span><span class="sxs-lookup"><span data-stu-id="b6174-138">When the `await` keyword is applied, it suspends the calling method and yields control back to its caller until the awaited task is complete.</span></span>
* <span data-ttu-id="b6174-139">仅允许在异步方法中使用 `await`。</span><span class="sxs-lookup"><span data-stu-id="b6174-139">`await` can only be used inside an async method.</span></span>

## <a name="recognize-cpu-bound-and-io-bound-work"></a><span data-ttu-id="b6174-140">识别 CPU 绑定和 I/O 绑定工作</span><span class="sxs-lookup"><span data-stu-id="b6174-140">Recognize CPU-Bound and I/O-Bound Work</span></span>

<span data-ttu-id="b6174-141">本指南的前两个示例演示如何将 `async` 和 `await` 用于 I/O 绑定和 CPU 绑定工作。</span><span class="sxs-lookup"><span data-stu-id="b6174-141">The first two examples of this guide showed how you can use `async` and `await` for I/O-bound and CPU-bound work.</span></span>  <span data-ttu-id="b6174-142">确定所需执行的操作是 I/O 绑定或 CPU 绑定是关键，因为这会极大影响代码性能，并可能导致某些构造的误用。</span><span class="sxs-lookup"><span data-stu-id="b6174-142">It's key that you can identify when a job you need to do is I/O-bound or CPU-bound, because it can greatly affect the performance of your code and could potentially lead to misusing certain constructs.</span></span>

<span data-ttu-id="b6174-143">以下是编写代码前应考虑的两个问题：</span><span class="sxs-lookup"><span data-stu-id="b6174-143">Here are two questions you should ask before you write any code:</span></span>

1. <span data-ttu-id="b6174-144">你的代码是否会“等待”某些内容，例如数据库中的数据？</span><span class="sxs-lookup"><span data-stu-id="b6174-144">Will your code be "waiting" for something, such as data from a database?</span></span>

    <span data-ttu-id="b6174-145">如果答案为“是”，则你的工作是 **I/O 绑定**。</span><span class="sxs-lookup"><span data-stu-id="b6174-145">If your answer is "yes", then your work is **I/O-bound**.</span></span>

2. <span data-ttu-id="b6174-146">你的代码是否要执行开销巨大的计算？</span><span class="sxs-lookup"><span data-stu-id="b6174-146">Will your code be performing a very expensive computation?</span></span>

    <span data-ttu-id="b6174-147">如果答案为“是”，则你的工作是 **CPU 绑定**。</span><span class="sxs-lookup"><span data-stu-id="b6174-147">If you answered "yes", then your work is **CPU-bound**.</span></span>

<span data-ttu-id="b6174-148">如果你的工作为 **I/O 绑定**，请使用 `async` 和 `await`（而不使用 `Task.Run`）。</span><span class="sxs-lookup"><span data-stu-id="b6174-148">If the work you have is **I/O-bound**, use `async` and `await` *without* `Task.Run`.</span></span>  <span data-ttu-id="b6174-149">不应使用任务并行库。</span><span class="sxs-lookup"><span data-stu-id="b6174-149">You *should not* use the Task Parallel Library.</span></span>  <span data-ttu-id="b6174-150">相关原因在[深入了解异步的文章](../standard/async-in-depth.md)中说明。</span><span class="sxs-lookup"><span data-stu-id="b6174-150">The reason for this is outlined in the [Async in Depth article](../standard/async-in-depth.md).</span></span>

<span data-ttu-id="b6174-151">如果你的工作为 **CPU 绑定**，并且你重视响应能力，请使用 `async` 和 `await`，并在另一个线程上使用 `Task.Run` 生成工作。</span><span class="sxs-lookup"><span data-stu-id="b6174-151">If the work you have is **CPU-bound** and you care about responsiveness, use `async` and `await` but spawn the work off on another thread *with* `Task.Run`.</span></span>  <span data-ttu-id="b6174-152">如果该工作同时适用于并发和并行，则应考虑使用[任务并行库](../standard/parallel-programming/task-parallel-library-tpl.md)。</span><span class="sxs-lookup"><span data-stu-id="b6174-152">If the work is appropriate for concurrency and parallelism, you should also consider using the [Task Parallel Library](../standard/parallel-programming/task-parallel-library-tpl.md).</span></span>

<span data-ttu-id="b6174-153">此外，应始终对代码的执行进行测量。</span><span class="sxs-lookup"><span data-stu-id="b6174-153">Additionally, you should always measure the execution of your code.</span></span>  <span data-ttu-id="b6174-154">例如，你可能会遇到这样的情况：多线程处理时，上下文切换的开销高于 CPU 绑定工作的开销。</span><span class="sxs-lookup"><span data-stu-id="b6174-154">For example, you may find yourself in a situation where your CPU-bound work is not costly enough compared with the overhead of context switches when multithreading.</span></span>  <span data-ttu-id="b6174-155">每种选择都有折衷，应根据自身情况选择正确的折衷方案。</span><span class="sxs-lookup"><span data-stu-id="b6174-155">Every choice has its tradeoff, and you should pick the correct tradeoff for your situation.</span></span>

## <a name="more-examples"></a><span data-ttu-id="b6174-156">更多示例</span><span class="sxs-lookup"><span data-stu-id="b6174-156">More Examples</span></span>

<span data-ttu-id="b6174-157">下列示例演示了多种使用 C# 编写异步代码的方法。</span><span class="sxs-lookup"><span data-stu-id="b6174-157">The following examples demonstrate various ways you can write async code in C#.</span></span>  <span data-ttu-id="b6174-158">它们涉及你可能会遇到的一些不同方案。</span><span class="sxs-lookup"><span data-stu-id="b6174-158">They cover a few different scenarios you may come across.</span></span>

### <a name="extracting-data-from-a-network"></a><span data-ttu-id="b6174-159">从网络提取数据</span><span class="sxs-lookup"><span data-stu-id="b6174-159">Extracting Data from a Network</span></span>

<span data-ttu-id="b6174-160">此代码片段从 [www.dotnetfoundation.org](https://www.dotnetfoundation.org) 主页下载 HTML，并对 HTML 中出现字符串“.NET”的次数计数。</span><span class="sxs-lookup"><span data-stu-id="b6174-160">This snippet downloads the HTML from the homepage at [www.dotnetfoundation.org](https://www.dotnetfoundation.org) and counts the number of times the string ".NET" occurs in the HTML.</span></span>  <span data-ttu-id="b6174-161">它使用 ASP.NET MVC 定义执行此任务的 Web 控制器方法，以便返回数字。</span><span class="sxs-lookup"><span data-stu-id="b6174-161">It uses ASP.NET MVC to define a web controller method which performs this task, returning the number.</span></span>

> [!NOTE]
> <span data-ttu-id="b6174-162">如果打算在生产代码中进行 HTML 分析，则不要使用正则表达式。</span><span class="sxs-lookup"><span data-stu-id="b6174-162">If you plan on doing HTML parsing in production code, don't use regular expressions.</span></span> <span data-ttu-id="b6174-163">改为使用分析库。</span><span class="sxs-lookup"><span data-stu-id="b6174-163">Use a parsing library instead.</span></span>

```csharp
private readonly HttpClient _httpClient = new HttpClient();

[HttpGet]
[Route("DotNetCount")]
public async Task<int> GetDotNetCountAsync()
{
    // Suspends GetDotNetCountAsync() to allow the caller (the web server)
    // to accept another request, rather than blocking on this one.
    var html = await _httpClient.GetStringAsync("https://dotnetfoundation.org");

    return Regex.Matches(html, @"\.NET").Count;
}
```

<span data-ttu-id="b6174-164">以下是为通用 Windows 应用编写的相同方案，当按下按钮时，它将执行相同的任务：</span><span class="sxs-lookup"><span data-stu-id="b6174-164">Here's the same scenario written for a Universal Windows App, which performs the same task when a Button is pressed:</span></span>

```csharp
private readonly HttpClient _httpClient = new HttpClient();

private async void SeeTheDotNets_Click(object sender, RoutedEventArgs e)
{
    // Capture the task handle here so we can await the background task later.
    var getDotNetFoundationHtmlTask = _httpClient.GetStringAsync("https://www.dotnetfoundation.org");

    // Any other work on the UI thread can be done here, such as enabling a Progress Bar.
    // This is important to do here, before the "await" call, so that the user
    // sees the progress bar before execution of this method is yielded.
    NetworkProgressBar.IsEnabled = true;
    NetworkProgressBar.Visibility = Visibility.Visible;

    // The await operator suspends SeeTheDotNets_Click, returning control to its caller.
    // This is what allows the app to be responsive and not hang on the UI thread.
    var html = await getDotNetFoundationHtmlTask;
    int count = Regex.Matches(html, @"\.NET").Count;

    DotNetCountLabel.Text = $"Number of .NETs on dotnetfoundation.org: {count}";

    NetworkProgressBar.IsEnabled = false;
    NetworkProgressBar.Visibility = Visibility.Collapsed;
}
```

### <a name="waiting-for-multiple-tasks-to-complete"></a><span data-ttu-id="b6174-165">等待多个任务完成</span><span class="sxs-lookup"><span data-stu-id="b6174-165">Waiting for Multiple Tasks to Complete</span></span>

<span data-ttu-id="b6174-166">你可能发现自己处于需要并行检索多个数据部分的情况。</span><span class="sxs-lookup"><span data-stu-id="b6174-166">You may find yourself in a situation where you need to retrieve multiple pieces of data concurrently.</span></span>  <span data-ttu-id="b6174-167">`Task` API 包含两种方法（即 `Task.WhenAll` 和 `Task.WhenAny`），这些方法允许你编写在多个后台作业中执行非阻止等待的异步代码。</span><span class="sxs-lookup"><span data-stu-id="b6174-167">The `Task` API contains two methods, `Task.WhenAll` and `Task.WhenAny` which allow you to write asynchronous code which performs a non-blocking wait on multiple background jobs.</span></span>

<span data-ttu-id="b6174-168">此示例演示如何为一组 `User` 捕捉 `userId` 数据。</span><span class="sxs-lookup"><span data-stu-id="b6174-168">This example shows how you might grab `User` data for a set of `userId`s.</span></span>

```csharp
public async Task<User> GetUserAsync(int userId)
{
    // Code omitted:
    //
    // Given a user Id {userId}, retrieves a User object corresponding
    // to the entry in the database with {userId} as its Id.
}

public static async Task<IEnumerable<User>> GetUsersAsync(IEnumerable<int> userIds)
{
    var getUserTasks = new List<Task<User>>();

    foreach (int userId in userIds)
    {
        getUserTasks.Add(GetUserAsync(userId));
    }

    return await Task.WhenAll(getUserTasks);
}
```

<span data-ttu-id="b6174-169">以下是使用 LINQ 进行更简洁编写的另一种方法：</span><span class="sxs-lookup"><span data-stu-id="b6174-169">Here's another way to write this a bit more succinctly, using LINQ:</span></span>

```csharp
public async Task<User> GetUserAsync(int userId)
{
    // Code omitted:
    //
    // Given a user Id {userId}, retrieves a User object corresponding
    // to the entry in the database with {userId} as its Id.
}

public static async Task<User[]> GetUsersAsync(IEnumerable<int> userIds)
{
    var getUserTasks = userIds.Select(id => GetUserAsync(id));
    return await Task.WhenAll(getUserTasks);
}
```

<span data-ttu-id="b6174-170">尽管它的代码较少，但在混合 LINQ 和异步代码时需要谨慎操作。</span><span class="sxs-lookup"><span data-stu-id="b6174-170">Although it's less code, take care when mixing LINQ with asynchronous code.</span></span>  <span data-ttu-id="b6174-171">因为 LINQ 使用延迟的执行，因此异步调用将不会像在 `foreach()` 循环中那样立刻发生，除非强制所生成的序列通过对 `.ToList()` 或 `.ToArray()` 的调用循环访问。</span><span class="sxs-lookup"><span data-stu-id="b6174-171">Because LINQ uses deferred (lazy) execution, async calls won't happen immediately as they do in a `foreach()` loop unless you force the generated sequence to iterate with a call to `.ToList()` or `.ToArray()`.</span></span>

## <a name="important-info-and-advice"></a><span data-ttu-id="b6174-172">重要信息和建议</span><span class="sxs-lookup"><span data-stu-id="b6174-172">Important Info and Advice</span></span>

<span data-ttu-id="b6174-173">尽管异步编程相对简单，但应记住一些可避免意外行为的要点。</span><span class="sxs-lookup"><span data-stu-id="b6174-173">Although async programming is relatively straightforward, there are some details to keep in mind which can prevent unexpected behavior.</span></span>

* <span data-ttu-id="b6174-174">`async`**方法需在其主体中具有**`await` **关键字，否则它们将永不暂停！**</span><span class="sxs-lookup"><span data-stu-id="b6174-174">`async` **methods need to have an** `await` **keyword in their body or they will never yield!**</span></span>

<span data-ttu-id="b6174-175">这一点需牢记在心。</span><span class="sxs-lookup"><span data-stu-id="b6174-175">This is important to keep in mind.</span></span>  <span data-ttu-id="b6174-176">如果 `await` 未用在 `async` 方法的主体中，C# 编译器将生成一个警告，但此代码将会以类似普通方法的方式进行编译和运行。</span><span class="sxs-lookup"><span data-stu-id="b6174-176">If `await` is not used in the body of an `async` method, the C# compiler will generate a warning, but the code will compile and run as if it were a normal method.</span></span>  <span data-ttu-id="b6174-177">请注意这会导致效率低下，因为由 C# 编译器为异步方法生成的状态机将不会完成任何任务。</span><span class="sxs-lookup"><span data-stu-id="b6174-177">Note that this would also be incredibly inefficient, as the state machine generated by the C# compiler for the async method would not be accomplishing anything.</span></span>

* <span data-ttu-id="b6174-178">应将“Async”作为后缀添加到所编写的每个异步方法名称中。</span><span class="sxs-lookup"><span data-stu-id="b6174-178">**You should add "Async" as the suffix of every async method name you write.**</span></span>

<span data-ttu-id="b6174-179">这是 .NET 中的惯例，以便更轻松区分同步和异步方法。</span><span class="sxs-lookup"><span data-stu-id="b6174-179">This is the convention used in .NET to more-easily differentiate synchronous and asynchronous methods.</span></span> <span data-ttu-id="b6174-180">请注意，未由代码显式调用的某些方法（如事件处理程序或 Web 控制器方法）并不一定适用。</span><span class="sxs-lookup"><span data-stu-id="b6174-180">Note that certain methods which aren’t explicitly called by your code (such as event handlers or web controller methods) don’t necessarily apply.</span></span> <span data-ttu-id="b6174-181">由于它们未由代码显式调用，因此对其显式命名并不重要。</span><span class="sxs-lookup"><span data-stu-id="b6174-181">Because these are not explicitly called by your code, being explicit about their naming isn’t as important.</span></span>

* <span data-ttu-id="b6174-182">`async void` **应仅用于事件处理程序。**</span><span class="sxs-lookup"><span data-stu-id="b6174-182">`async void` **should only be used for event handlers.**</span></span>

<span data-ttu-id="b6174-183">`async void` 是允许异步事件处理程序工作的唯一方法，因为事件不具有返回类型（因此无法利用 `Task` 和 `Task<T>`）。</span><span class="sxs-lookup"><span data-stu-id="b6174-183">`async void` is the only way to allow asynchronous event handlers to work because events do not have return types (thus cannot make use of `Task` and `Task<T>`).</span></span> <span data-ttu-id="b6174-184">其他任何对 `async void` 的使用都不遵循 TAP 模型，且可能存在一定使用难度，例如：</span><span class="sxs-lookup"><span data-stu-id="b6174-184">Any other use of `async void` does not follow the TAP model and can be challenging to use, such as:</span></span>

* <span data-ttu-id="b6174-185">`async void` 方法中引发的异常无法在该方法外部被捕获。</span><span class="sxs-lookup"><span data-stu-id="b6174-185">Exceptions thrown in an `async void` method can’t be caught outside of that method.</span></span>
* <span data-ttu-id="b6174-186">十分难以测试 `async void` 方法。</span><span class="sxs-lookup"><span data-stu-id="b6174-186">`async void` methods are very difficult to test.</span></span>
* <span data-ttu-id="b6174-187">如果调用方不希望 `async void` 方法是异步方法，则这些方法可能会产生不好的副作用。</span><span class="sxs-lookup"><span data-stu-id="b6174-187">`async void` methods can cause bad side effects if the caller isn’t expecting them to be async.</span></span>

* <span data-ttu-id="b6174-188">**在 LINQ 表达式中使用异步 lambda 时请谨慎**</span><span class="sxs-lookup"><span data-stu-id="b6174-188">**Tread carefully when using async lambdas in LINQ expressions**</span></span>

<span data-ttu-id="b6174-189">LINQ 中的 Lambda 表达式使用延迟执行，这意味着代码可能在你并不希望结束的时候停止执行。</span><span class="sxs-lookup"><span data-stu-id="b6174-189">Lambda expressions in LINQ use deferred execution, meaning code could end up executing at a time when you’re not expecting it to.</span></span> <span data-ttu-id="b6174-190">如果编写不正确，将阻塞任务引入其中时可能很容易导致死锁。</span><span class="sxs-lookup"><span data-stu-id="b6174-190">The introduction of blocking tasks into this can easily result in a deadlock if not written correctly.</span></span> <span data-ttu-id="b6174-191">此外，此类异步代码嵌套可能会对推断代码的执行带来更多困难。</span><span class="sxs-lookup"><span data-stu-id="b6174-191">Additionally, the nesting of asynchronous code like this can also make it more difficult to reason about the execution of the code.</span></span> <span data-ttu-id="b6174-192">Async 和 LINQ 的功能都十分强大，但在结合使用两者时应尽可能小心。</span><span class="sxs-lookup"><span data-stu-id="b6174-192">Async and LINQ are powerful, but should be used together as carefully and clearly as possible.</span></span>

* <span data-ttu-id="b6174-193">**采用非阻止方式编写等待任务的代码**</span><span class="sxs-lookup"><span data-stu-id="b6174-193">**Write code that awaits Tasks in a non-blocking manner**</span></span>

<span data-ttu-id="b6174-194">将阻止当前线程作为等待任务完成的方法可能导致死锁和已阻止的上下文线程，且可能需要更复杂的错误处理。</span><span class="sxs-lookup"><span data-stu-id="b6174-194">Blocking the current thread as a means to wait for a Task to complete can result in deadlocks and blocked context threads, and can require significantly more complex error-handling.</span></span> <span data-ttu-id="b6174-195">下表提供了关于如何以非阻止方式处理等待任务的指南：</span><span class="sxs-lookup"><span data-stu-id="b6174-195">The following table provides guidance on how to deal with waiting for Tasks in a non-blocking way:</span></span>

| <span data-ttu-id="b6174-196">使用以下方式...</span><span class="sxs-lookup"><span data-stu-id="b6174-196">Use this...</span></span> | <span data-ttu-id="b6174-197">而不是…</span><span class="sxs-lookup"><span data-stu-id="b6174-197">Instead of this...</span></span> | <span data-ttu-id="b6174-198">若要执行此操作</span><span class="sxs-lookup"><span data-stu-id="b6174-198">When wishing to do this</span></span> |
| --- | --- | --- |
| `await` | <span data-ttu-id="b6174-199">`Task.Wait` 或 `Task.Result`</span><span class="sxs-lookup"><span data-stu-id="b6174-199">`Task.Wait` or `Task.Result`</span></span> | <span data-ttu-id="b6174-200">检索后台任务的结果</span><span class="sxs-lookup"><span data-stu-id="b6174-200">Retrieving the result of a background task</span></span> |
| `await Task.WhenAny` | `Task.WaitAny` | <span data-ttu-id="b6174-201">等待任何任务完成</span><span class="sxs-lookup"><span data-stu-id="b6174-201">Waiting for any task to complete</span></span> |
| `await Task.WhenAll` | `Task.WaitAll` | <span data-ttu-id="b6174-202">等待所有任务完成</span><span class="sxs-lookup"><span data-stu-id="b6174-202">Waiting for all tasks to complete</span></span> |
| `await Task.Delay` | `Thread.Sleep` | <span data-ttu-id="b6174-203">等待一段时间</span><span class="sxs-lookup"><span data-stu-id="b6174-203">Waiting for a period of time</span></span> |

* <span data-ttu-id="b6174-204">**编写状态欠缺的代码**</span><span class="sxs-lookup"><span data-stu-id="b6174-204">**Write less stateful code**</span></span>

<span data-ttu-id="b6174-205">请勿依赖全局对象的状态或某些方法的执行。</span><span class="sxs-lookup"><span data-stu-id="b6174-205">Don’t depend on the state of global objects or the execution of certain methods.</span></span> <span data-ttu-id="b6174-206">请仅依赖方法的返回值。</span><span class="sxs-lookup"><span data-stu-id="b6174-206">Instead, depend only on the return values of methods.</span></span> <span data-ttu-id="b6174-207">为什么？</span><span class="sxs-lookup"><span data-stu-id="b6174-207">Why?</span></span>

* <span data-ttu-id="b6174-208">这样更容易推断代码。</span><span class="sxs-lookup"><span data-stu-id="b6174-208">Code will be easier to reason about.</span></span>
* <span data-ttu-id="b6174-209">这样更容易测试代码。</span><span class="sxs-lookup"><span data-stu-id="b6174-209">Code will be easier to test.</span></span>
* <span data-ttu-id="b6174-210">混合异步和同步代码更简单。</span><span class="sxs-lookup"><span data-stu-id="b6174-210">Mixing async and synchronous code is far simpler.</span></span>
* <span data-ttu-id="b6174-211">通常可完全避免争用条件。</span><span class="sxs-lookup"><span data-stu-id="b6174-211">Race conditions can typically be avoided altogether.</span></span>
* <span data-ttu-id="b6174-212">通过依赖返回值，协调异步代码可变得简单。</span><span class="sxs-lookup"><span data-stu-id="b6174-212">Depending on return values makes coordinating async code simple.</span></span>
* <span data-ttu-id="b6174-213">（好处）它非常适用于依赖关系注入。</span><span class="sxs-lookup"><span data-stu-id="b6174-213">(Bonus) it works really well with dependency injection.</span></span>

<span data-ttu-id="b6174-214">建议的目标是实现代码中完整或接近完整的[引用透明度](https://en.wikipedia.org/wiki/Referential_transparency_%28computer_science%29)。</span><span class="sxs-lookup"><span data-stu-id="b6174-214">A recommended goal is to achieve complete or near-complete [Referential Transparency](https://en.wikipedia.org/wiki/Referential_transparency_%28computer_science%29) in your code.</span></span> <span data-ttu-id="b6174-215">这么做能获得高度可预测、可测试和可维护的基本代码。</span><span class="sxs-lookup"><span data-stu-id="b6174-215">Doing so will result in an extremely predictable, testable, and maintainable codebase.</span></span>

## <a name="other-resources"></a><span data-ttu-id="b6174-216">其他资源</span><span class="sxs-lookup"><span data-stu-id="b6174-216">Other Resources</span></span>

* <span data-ttu-id="b6174-217">[深入了解异步](../standard/async-in-depth.md)提供了关于任务如何工作的详细信息。</span><span class="sxs-lookup"><span data-stu-id="b6174-217">[Async in-depth](../standard/async-in-depth.md) provides more information about how Tasks work.</span></span>
* [<span data-ttu-id="b6174-218">使用 Async 和 Await 的异步编程 (C#)</span><span class="sxs-lookup"><span data-stu-id="b6174-218">Asynchronous programming with async and await (C#)</span></span>](./programming-guide/concepts/async/index.md)
* <span data-ttu-id="b6174-219">由 Lucian Wischik 所著的 [Six Essential Tips for Async](https://channel9.msdn.com/Series/Three-Essential-Tips-for-Async)（关于异步的六个要点）是有关异步编程的绝佳资源</span><span class="sxs-lookup"><span data-stu-id="b6174-219">Lucian Wischik's [Six Essential Tips for Async](https://channel9.msdn.com/Series/Three-Essential-Tips-for-Async) are a wonderful resource for async programming</span></span>