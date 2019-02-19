---
title: 生成和使用异步流
description: 本高级教程演示了生成和使用异步流提供一种更自然的方式来处理可能以异步方式生成的数据序列的场景。
ms.date: 02/10/2019
ms.custom: mvc
ms.openlocfilehash: c8be9cf4b83e3dd72232279e7c15dcba639c2058
ms.sourcegitcommit: bef803e2025642df39f2f1e046767d89031e0304
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/15/2019
ms.locfileid: "56305996"
---
# <a name="tutorial-generate-and-consume-async-streams-using-c-80-and-net-core-30"></a><span data-ttu-id="27b47-103">教程：使用 C# 8.0 和 .NET Core 3.0 生成和使用异步流</span><span class="sxs-lookup"><span data-stu-id="27b47-103">Tutorial: Generate and consume async streams using C# 8.0 and .NET Core 3.0</span></span>

<span data-ttu-id="27b47-104">C# 8.0 引入了**异步流**，在能够以异步方式检索或生成数据流中的元素时，它将对数据的流式处理源进行建模。</span><span class="sxs-lookup"><span data-stu-id="27b47-104">C# 8.0 introduces **async streams**, which model a streaming source of data when the elements in the data stream may be retrieved or generated asynchronously.</span></span> <span data-ttu-id="27b47-105">异步流依赖于在 .NET Standard 2.1 中引入且在 .NET Core 3.0 中实现的新接口，以便为异步流式处理数据源提供一个自然的编程模型。</span><span class="sxs-lookup"><span data-stu-id="27b47-105">Async streams rely on new interfaces introduced in .NET Standard 2.1 and implemented in .NET Core 3.0 to provide a natural programming model for asynchronous streaming data sources.</span></span>

<span data-ttu-id="27b47-106">在本教程中，你将了解：</span><span class="sxs-lookup"><span data-stu-id="27b47-106">In this tutorial, you'll learn how to:</span></span>

> [!div class="checklist"]
> * <span data-ttu-id="27b47-107">创建以异步方式生成数据元素序列的数据源。</span><span class="sxs-lookup"><span data-stu-id="27b47-107">Create a data source that generates a sequence of data elements asynchronously.</span></span>
> * <span data-ttu-id="27b47-108">以异步方式使用该数据源。</span><span class="sxs-lookup"><span data-stu-id="27b47-108">Consume that data source asynchronously.</span></span>
> * <span data-ttu-id="27b47-109">识别新接口和数据源何时优先于先前的同步数据序列。</span><span class="sxs-lookup"><span data-stu-id="27b47-109">Recognize when the new interface and data source are preferred to earlier synchronous data sequences.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="27b47-110">系统必备</span><span class="sxs-lookup"><span data-stu-id="27b47-110">Prerequisites</span></span>

<span data-ttu-id="27b47-111">你需要将计算机设置为运行 .NET Core，包括 C# 8.0 beta 编译器。</span><span class="sxs-lookup"><span data-stu-id="27b47-111">You’ll need to set up your machine to run .NET Core, including the C# 8.0 beta compiler.</span></span> <span data-ttu-id="27b47-112">从 [Visual Studio 2019 预览版 1](https://visualstudio.microsoft.com/vs/preview/) 或 [.NET Core 3.0 预览版 1 SDK](https://dotnet.microsoft.com/download/dotnet-core/3.0) 开始，可以使用 C# 8 beta 编译器。</span><span class="sxs-lookup"><span data-stu-id="27b47-112">The C# 8 beta compiler is available starting with [Visual Studio 2019 preview 1](https://visualstudio.microsoft.com/vs/preview/), or [.NET Core 3.0 preview 1 SDK](https://dotnet.microsoft.com/download/dotnet-core/3.0).</span></span> <span data-ttu-id="27b47-113">异步流首先可在 .NET Core 3.0 预览版 1 中使用。</span><span class="sxs-lookup"><span data-stu-id="27b47-113">Async streams are first available in .NET Core 3.0 preview 1.</span></span>

<span data-ttu-id="27b47-114">将需要创建 [GitHub 访问令牌](https://help.github.com/articles/creating-a-personal-access-token-for-the-command-line/#creating-a-token)，以便可以访问 GitHub GraphQL 终结点。</span><span class="sxs-lookup"><span data-stu-id="27b47-114">You'll need to create a [GitHub access token](https://help.github.com/articles/creating-a-personal-access-token-for-the-command-line/#creating-a-token) so that you can access the GitHub GraphQL endpoint.</span></span> <span data-ttu-id="27b47-115">为 GitHub 访问令牌选择以下权限：</span><span class="sxs-lookup"><span data-stu-id="27b47-115">Select the following permissions for your GitHub Access Token:</span></span>

- <span data-ttu-id="27b47-116">repo:status</span><span class="sxs-lookup"><span data-stu-id="27b47-116">repo:status</span></span>
- <span data-ttu-id="27b47-117">public_repo</span><span class="sxs-lookup"><span data-stu-id="27b47-117">public_repo</span></span>

<span data-ttu-id="27b47-118">将访问令牌保存在安全位置，以便可以使用它来访问 GitHub API 终结点。</span><span class="sxs-lookup"><span data-stu-id="27b47-118">Save the access token in a safe place so you can use it to gain access to the GitHub API endpoint.</span></span>

> [!WARNING]
> <span data-ttu-id="27b47-119">保护个人访问令牌。</span><span class="sxs-lookup"><span data-stu-id="27b47-119">Keep your personal access token secure.</span></span> <span data-ttu-id="27b47-120">任何带有你的个人访问令牌的软件都可以使用你的访问权限进行 GitHub API 调用。</span><span class="sxs-lookup"><span data-stu-id="27b47-120">Any software with your personal access token could make GitHub API calls using your access rights.</span></span>

<span data-ttu-id="27b47-121">本教程假设你熟悉 C# 和 .NET，包括 Visual Studio 或 .NET Core CLI。</span><span class="sxs-lookup"><span data-stu-id="27b47-121">This tutorial assumes you're familiar with C# and .NET, including either Visual Studio or the .NET Core CLI.</span></span>

## <a name="run-the-starter-application"></a><span data-ttu-id="27b47-122">运行初学者应用程序</span><span class="sxs-lookup"><span data-stu-id="27b47-122">Run the starter application</span></span>

<span data-ttu-id="27b47-123">可以从 [csharp/tutorials/AsyncStreams](https://github.com/dotnet/samples/tree/master/csharp/tutorials/AsyncStreams/start) 文件夹中的 [dotnet/samples](https://github.com/dotnet/samples) 存储库获得本教程中使用的初学者应用程序代码。</span><span class="sxs-lookup"><span data-stu-id="27b47-123">You can get the code for the starter application used in this tutorial from our [dotnet/samples](https://github.com/dotnet/samples) repository in the [csharp/tutorials/AsyncStreams](https://github.com/dotnet/samples/tree/master/csharp/tutorials/AsyncStreams/start) folder.</span></span>

<span data-ttu-id="27b47-124">初学者应用程序是一个控制台应用程序，它使用 [GitHub GraphQL](https://developer.github.com/v4/) 接口检索最近在 [dotnet/docs](https://github.com/dotnet/docs) 存储库中编写的问题。</span><span class="sxs-lookup"><span data-stu-id="27b47-124">The starter application is a console application that uses the [GitHub GraphQL](https://developer.github.com/v4/) interface to retrieve recent issues written in the [dotnet/docs](https://github.com/dotnet/docs) repository.</span></span> <span data-ttu-id="27b47-125">首先来看一下以下初学者应用 `Main` 方法的代码：</span><span class="sxs-lookup"><span data-stu-id="27b47-125">Start by looking at the following code for the starter app `Main` method:</span></span>

[!code-csharp[StarterAppMain](~/samples/csharp/tutorials/AsyncStreams/start/IssuePRreport/IssuePRreport/Program.cs#StarterAppMain)]

<span data-ttu-id="27b47-126">可以将 `GitHubKey` 环境变量设置为个人访问令牌，也可以将对 `GenEnvVariable` 的调用中的最后一个参数替换为个人访问令牌。</span><span class="sxs-lookup"><span data-stu-id="27b47-126">You can either set a `GitHubKey` environment variable to your personal access token, or you can replace the last argument in the call to `GenEnvVariable` with your personal access token.</span></span> <span data-ttu-id="27b47-127">如果要与他人一起保存源代码，或将其放入共享源代码存储库，请勿将访问代码放入源代码中。</span><span class="sxs-lookup"><span data-stu-id="27b47-127">Don't put your access code in source code if you'll be saving the source with others, or putting it in a shared source repository.</span></span>

<span data-ttu-id="27b47-128">在创建 GitHub 客户端后，`Main` 中的代码将创建一个进度报告对象和一个取消令牌。</span><span class="sxs-lookup"><span data-stu-id="27b47-128">After creating the GitHub client, the code in `Main` creates a progress reporting object and a cancellation token.</span></span> <span data-ttu-id="27b47-129">创建这些对象之后，`Main` 调用 `runPagedQueryAsync` 来检索最近创建的 250 个问题。</span><span class="sxs-lookup"><span data-stu-id="27b47-129">Once those objects are created, `Main` calls `runPagedQueryAsync` to retrieve the most recent 250 created issues.</span></span> <span data-ttu-id="27b47-130">任务完成后，将显示结果。</span><span class="sxs-lookup"><span data-stu-id="27b47-130">After that task has finished, the results are displayed.</span></span>

<span data-ttu-id="27b47-131">在运行初学者应用程序时，可以对该应用程序的运行方式进行一些重要观察。</span><span class="sxs-lookup"><span data-stu-id="27b47-131">When you run the starter application, you can make some important observations about how this application runs.</span></span>  <span data-ttu-id="27b47-132">将看到从 GitHub 返回的每个页面的进度报告。</span><span class="sxs-lookup"><span data-stu-id="27b47-132">You'll see progress reported for each page returned from GitHub.</span></span> <span data-ttu-id="27b47-133">在 GitHub 返回问题的每个新页面之前，可以观察到明显的停顿。</span><span class="sxs-lookup"><span data-stu-id="27b47-133">You can observe a noticeable pause before GitHub returns each new page of issues.</span></span> <span data-ttu-id="27b47-134">最后，只有在从 GitHub 检索到所有 10 个页面之后，问题才会显示出来。</span><span class="sxs-lookup"><span data-stu-id="27b47-134">Finally, the issues are displayed only after all 10 pages have been retrieved from GitHub.</span></span>

## <a name="examine-the-implementation"></a><span data-ttu-id="27b47-135">检查实现情况</span><span class="sxs-lookup"><span data-stu-id="27b47-135">Examine the implementation</span></span>

<span data-ttu-id="27b47-136">该实现揭示了你观察到上一部分中讨论的行为的原因。</span><span class="sxs-lookup"><span data-stu-id="27b47-136">The implementation reveals why you observed the behavior discussed in the previous section.</span></span> <span data-ttu-id="27b47-137">检查 `runPagedQueryAsync` 的代码：</span><span class="sxs-lookup"><span data-stu-id="27b47-137">Examine the code for `runPagedQueryAsync`:</span></span>

[!code-csharp[RunPagedQueryStarter](~/samples/csharp/tutorials/AsyncStreams/start/IssuePRreport/IssuePRreport/Program.cs#RunPagedQuery)]

<span data-ttu-id="27b47-138">让我们集中讨论前面代码的分页算法和异步结构。</span><span class="sxs-lookup"><span data-stu-id="27b47-138">Let's concentrate on the paging algorithm and async structure of the preceding code.</span></span> <span data-ttu-id="27b47-139">（有关 GitHub GraphQL API 的详细信息，可以参考 [GitHub GraphQL 文档](https://developer.github.com/v4/guides/)。）`runPagedQueryAsync` 方法按从最新到最旧的顺序枚举问题。</span><span class="sxs-lookup"><span data-stu-id="27b47-139">(You can consult the [GitHub GraphQL documentation](https://developer.github.com/v4/guides/) for details on the GitHub GraphQL API.) The `runPagedQueryAsync` method enumerates the issues from most recent to oldest.</span></span> <span data-ttu-id="27b47-140">它每页请求 25 个问题，并检查响应的 `pageInfo` 结构以继续上一页的操作。</span><span class="sxs-lookup"><span data-stu-id="27b47-140">It requests 25 issues per page and examines the `pageInfo` structure of the response to continue with the previous page.</span></span> <span data-ttu-id="27b47-141">这遵循了 GraphQL 对多页响应的标准分页支持。</span><span class="sxs-lookup"><span data-stu-id="27b47-141">That follows GraphQL's standard paging support for multi-page responses.</span></span> <span data-ttu-id="27b47-142">响应包括 `pageInfo` 对象，该对象包含用于请求上一页的 `hasPreviousPages` 值和 `startCursor` 值。</span><span class="sxs-lookup"><span data-stu-id="27b47-142">The response includes a `pageInfo` object that includes a `hasPreviousPages` value and a `startCursor` value used to request the previous page.</span></span> <span data-ttu-id="27b47-143">问题在 `nodes` 数组中。</span><span class="sxs-lookup"><span data-stu-id="27b47-143">The issues are in the `nodes` array.</span></span> <span data-ttu-id="27b47-144">`runPagedQueryAsync` 方法将这些节点追加到一个数组中，其中包含所有页面的所有结果。</span><span class="sxs-lookup"><span data-stu-id="27b47-144">The `runPagedQueryAsync` method appends these nodes to an array that contains all the results from all pages.</span></span>

<span data-ttu-id="27b47-145">在检索和还原结果页之后，`runPagedQueryAsync` 将报告进度并检查是否取消。</span><span class="sxs-lookup"><span data-stu-id="27b47-145">After retrieving and restoring a page of results, `runPagedQueryAsync` reports progress and checks for cancellation.</span></span> <span data-ttu-id="27b47-146">如果已请求取消，`runPagedQueryAsync` 将引发 <xref:System.OperationCanceledException>。</span><span class="sxs-lookup"><span data-stu-id="27b47-146">If cancellation has been requested, `runPagedQueryAsync` throws an <xref:System.OperationCanceledException>.</span></span>

<span data-ttu-id="27b47-147">此代码中有几个可以改进的元素。</span><span class="sxs-lookup"><span data-stu-id="27b47-147">There are several elements in this code that can be improved.</span></span> <span data-ttu-id="27b47-148">最重要的是，`runPagedQueryAsync` 必须为返回的所有问题分配存储空间。</span><span class="sxs-lookup"><span data-stu-id="27b47-148">Most importantly, `runPagedQueryAsync` must allocate storage for all the issues returned.</span></span> <span data-ttu-id="27b47-149">该示例在 250 个问题处停止，因为检索所有未决问题需要更多的内存来存储所有检索到的问题。</span><span class="sxs-lookup"><span data-stu-id="27b47-149">This sample stops at 250 issues because retrieving all open issues would require much more memory to store all the retrieved issues.</span></span> <span data-ttu-id="27b47-150">此外，支持进度和支持取消的协议使得算法在第一次读取时更加难以理解。</span><span class="sxs-lookup"><span data-stu-id="27b47-150">In addition, the protocols for supporting progress and supporting cancellation make the algorithm harder to understand on its first reading.</span></span> <span data-ttu-id="27b47-151">必须查找进度类，以找到报告进度的位置。</span><span class="sxs-lookup"><span data-stu-id="27b47-151">You must look for the progress class to find where progress is reported.</span></span> <span data-ttu-id="27b47-152">还必须通过 <xref:System.Threading.CancellationTokenSource> 及其关联的 <xref:System.Threading.CancellationToken> 跟踪通信，以了解在何处请求取消，以及在何处授予取消。</span><span class="sxs-lookup"><span data-stu-id="27b47-152">You also have to trace the communications through the <xref:System.Threading.CancellationTokenSource> and its associated <xref:System.Threading.CancellationToken> to understand where cancellation is requested and where it's granted.</span></span>

## <a name="async-streams-provide-a-better-way"></a><span data-ttu-id="27b47-153">异步流可提供更好的方法</span><span class="sxs-lookup"><span data-stu-id="27b47-153">Async streams provide a better way</span></span>

<span data-ttu-id="27b47-154">异步流和关联语言支持解决了所有这些问题。</span><span class="sxs-lookup"><span data-stu-id="27b47-154">Async streams and the associated language support address all those concerns.</span></span> <span data-ttu-id="27b47-155">生成序列的代码现在可以使用 `yield return` 返回用 `async` 修饰符声明的方法中的元素。</span><span class="sxs-lookup"><span data-stu-id="27b47-155">The code that generates the sequence can now use `yield return` to return elements in a method that was declared with the `async` modifier.</span></span> <span data-ttu-id="27b47-156">可以通过 `await foreach` 循环来使用异步流，就像通过 `foreach` 循环使用任何序列一样。</span><span class="sxs-lookup"><span data-stu-id="27b47-156">You can consume an async stream using an `await foreach` loop just as you consume any sequence using a `foreach` loop.</span></span>

<span data-ttu-id="27b47-157">这些新语言功能依赖于添加到 .NET Standard 2.1 并在 .NET Core 3.0 中实现的三个新接口：</span><span class="sxs-lookup"><span data-stu-id="27b47-157">These new language features depend on three new interfaces added to .NET Standard 2.1 and implemented in .NET Core 3.0:</span></span>

```csharp
namespace System.Collections.Generic
{
    public interface IAsyncEnumerable<out T>
    {
        IAsyncEnumerator<T> GetAsyncEnumerator(CancellationToken cancellationToken = default);
    }

    public interface IAsyncEnumerator<out T> : IAsyncDisposable
    {
        T Current { get; }

        ValueTask<bool> MoveNextAsync();
    }
}

namespace System
{
    public interface IAsyncDisposable
    {
        ValueTask DisposeAsync();
    }
}
```

<span data-ttu-id="27b47-158">大多数 C# 开发人员都应该熟悉这三个接口。</span><span class="sxs-lookup"><span data-stu-id="27b47-158">These three interfaces should be familiar to most C# developers.</span></span> <span data-ttu-id="27b47-159">它们的行为方式类似于其对应的同步对象：</span><span class="sxs-lookup"><span data-stu-id="27b47-159">They behave in a manner similar to their synchronous counterparts:</span></span>

- <xref:System.Collections.Generic.IEnumerable%601?displayProperty=nameWithType>
- <xref:System.Collections.Generic.IEnumerator%601?displayProperty=nameWithType>
- <xref:System.IDisposable?displayProperty=nameWithType>

<span data-ttu-id="27b47-160">可能不熟悉的一种类型是 <xref:System.Threading.Tasks.ValueTask?displayProperty=nameWithType>。</span><span class="sxs-lookup"><span data-stu-id="27b47-160">One type that may be unfamiliar is <xref:System.Threading.Tasks.ValueTask?displayProperty=nameWithType>.</span></span> <span data-ttu-id="27b47-161">`ValueTask` 结构提供了与 <xref:System.Threading.Tasks.Task?displayProperty=nameWithType> 类类似的 API。</span><span class="sxs-lookup"><span data-stu-id="27b47-161">The `ValueTask` struct provides a similar API to the <xref:System.Threading.Tasks.Task?displayProperty=nameWithType> class.</span></span> <span data-ttu-id="27b47-162">出于性能方面的原因，这些接口中使用了 `ValueTask`。</span><span class="sxs-lookup"><span data-stu-id="27b47-162">`ValueTask` is used in these interfaces for performance reasons.</span></span>

## <a name="convert-to-async-streams"></a><span data-ttu-id="27b47-163">转换为异步流</span><span class="sxs-lookup"><span data-stu-id="27b47-163">Convert to async streams</span></span>

<span data-ttu-id="27b47-164">接下来，转换 `runPagedQueryAsync` 方法以生成异步流。</span><span class="sxs-lookup"><span data-stu-id="27b47-164">Next, convert the `runPagedQueryAsync` method to generate an async stream.</span></span> <span data-ttu-id="27b47-165">首先，更改 `runPagedQueryAsync` 的签名以返回 `IAsyncEnumerable<JToken>`，并从参数列表删除取消令牌和进度对象，如以下代码所示：</span><span class="sxs-lookup"><span data-stu-id="27b47-165">First, change the signature of `runPagedQueryAsync` to return an `IAsyncEnumerable<JToken>`, and remove the cancellation token and progress objects from the parameter list as shown in the following code:</span></span>

[!code-csharp[FinishedSignature](~/samples/csharp/tutorials/AsyncStreams/finished/IssuePRreport/IssuePRreport/Program.cs#UpdateSignature)]

<span data-ttu-id="27b47-166">起始代码在检索页面时处理每个页面，如以下代码所示：</span><span class="sxs-lookup"><span data-stu-id="27b47-166">The starter code processes each page as the page is retrieved, as shown in the following code:</span></span>

[!code-csharp[StarterPaging](~/samples/csharp/tutorials/AsyncStreams/start/IssuePRreport/IssuePRreport/Program.cs#ProcessPage)]

<span data-ttu-id="27b47-167">将这三行替换为以下代码：</span><span class="sxs-lookup"><span data-stu-id="27b47-167">Replace those three lines with the following code:</span></span>

[!code-csharp[FinishedPaging](~/samples/csharp/tutorials/AsyncStreams/finished/IssuePRreport/IssuePRreport/Program.cs#YieldReturnPage)]

<span data-ttu-id="27b47-168">还可以在此方法中删除前面的 `finalResults` 声明以及你修改的循环之后的 `return` 语句。</span><span class="sxs-lookup"><span data-stu-id="27b47-168">You can also remove the declaration of `finalResults` earlier in this method and the `return` statement that follows the loop you modified.</span></span>

<span data-ttu-id="27b47-169">已完成更改以生成异步流。</span><span class="sxs-lookup"><span data-stu-id="27b47-169">You've finished the changes to generate an async stream.</span></span> <span data-ttu-id="27b47-170">完成的方法应类似于下面的代码：</span><span class="sxs-lookup"><span data-stu-id="27b47-170">The finished method should resemble the code below:</span></span>

[!code-csharp[FinishedGenerate](~/samples/csharp/tutorials/AsyncStreams/finished/IssuePRreport/IssuePRreport/Program.cs#GenerateAsyncStream)]

<span data-ttu-id="27b47-171">接下来，将使用集合的代码更改为使用异步流。</span><span class="sxs-lookup"><span data-stu-id="27b47-171">Next, you change the code that consumes the collection to consume the async stream.</span></span> <span data-ttu-id="27b47-172">在 `Main` 中找到以下处理问题集合的代码：</span><span class="sxs-lookup"><span data-stu-id="27b47-172">Find the following code in `Main` that processes the collection of issues:</span></span>

[!code-csharp[EnumerateOldStyle](~/samples/csharp/tutorials/AsyncStreams/start/IssuePRreport/IssuePRreport/Program.cs#EnumerateOldStyle)]

<span data-ttu-id="27b47-173">将该代码替换为以下 `await foreach` 循环：</span><span class="sxs-lookup"><span data-stu-id="27b47-173">Replace that code with the following `await foreach` loop:</span></span>

[!code-csharp[FinishedEnumerateAsyncStream](~/samples/csharp/tutorials/AsyncStreams/finished/IssuePRreport/IssuePRreport/Program.cs#EnumerateAsyncStream)]

<span data-ttu-id="27b47-174">可以从 [csharp/tutorials/AsyncStreams](https://github.com/dotnet/samples/tree/master/csharp/tutorials/AsyncStreams/finished) 文件夹中的 [dotnet/samples](https://github.com/dotnet/samples) 存储库获得完成教程的代码。</span><span class="sxs-lookup"><span data-stu-id="27b47-174">You can get the code for the finished tutorial from the [dotnet/samples](https://github.com/dotnet/samples) repository in the [csharp/tutorials/AsyncStreams](https://github.com/dotnet/samples/tree/master/csharp/tutorials/AsyncStreams/finished) folder.</span></span>

## <a name="run-the-finished-application"></a><span data-ttu-id="27b47-175">运行完成的应用程序</span><span class="sxs-lookup"><span data-stu-id="27b47-175">Run the finished application</span></span>

<span data-ttu-id="27b47-176">再次运行该应用程序。</span><span class="sxs-lookup"><span data-stu-id="27b47-176">Run the application again.</span></span> <span data-ttu-id="27b47-177">将其行为与初学者应用程序的行为进行对比。</span><span class="sxs-lookup"><span data-stu-id="27b47-177">Contrast its behavior with the behavior of the starter application.</span></span> <span data-ttu-id="27b47-178">会在结果的第一页可用立即对其进行枚举。</span><span class="sxs-lookup"><span data-stu-id="27b47-178">The first page of results is enumerated as soon as it's available.</span></span> <span data-ttu-id="27b47-179">在请求和检索每个新页面时都会有一个可观察到的暂停，然后快速枚举下一页结果。</span><span class="sxs-lookup"><span data-stu-id="27b47-179">There's an observable pause as each new page is requested and retrieved, then the next page's results are quickly enumerated.</span></span> <span data-ttu-id="27b47-180">不需要 `try` / `catch` 块来处理取消：调用者可以停止枚举集合。</span><span class="sxs-lookup"><span data-stu-id="27b47-180">The `try` / `catch` block isn't needed to handle cancellation: the caller can stop enumerating the collection.</span></span> <span data-ttu-id="27b47-181">由于异步流在下载每个页面时生成结果，因此可以清楚地报告进度。</span><span class="sxs-lookup"><span data-stu-id="27b47-181">Progress is clearly reported because the async stream generates results as each page is downloaded.</span></span>

<span data-ttu-id="27b47-182">通过检查代码，可以看到内存使用方面的改进。</span><span class="sxs-lookup"><span data-stu-id="27b47-182">You can see improvements in memory use by examining the code.</span></span> <span data-ttu-id="27b47-183">不再需要在枚举所有结果之前分配一个集合来存储它们。</span><span class="sxs-lookup"><span data-stu-id="27b47-183">You no longer need to allocate a collection to store all the results before they're enumerated.</span></span> <span data-ttu-id="27b47-184">调用者可以决定如何使用结果，以及是否需要存储集合。</span><span class="sxs-lookup"><span data-stu-id="27b47-184">The caller can determine how to consume the results and if a storage collection is needed.</span></span>

<span data-ttu-id="27b47-185">运行初学者应用程序和已完成的应用程序，可以自行观察实现之间的差异。</span><span class="sxs-lookup"><span data-stu-id="27b47-185">Run both the starter and finished applications and you can observe the differences between the implementations for yourself.</span></span> <span data-ttu-id="27b47-186">可以在完成本教程后删除在开始学习本教程时创建的 GitHub 访问令牌。</span><span class="sxs-lookup"><span data-stu-id="27b47-186">You can delete the GitHub access token you created when you started this tutorial after you've finished.</span></span> <span data-ttu-id="27b47-187">如果攻击者获得了对该令牌的访问权限，他们可以使用你的凭据来访问 GitHub API。</span><span class="sxs-lookup"><span data-stu-id="27b47-187">If an attacker gained access to that token, they could access GitHub APIs using your credentials.</span></span>
