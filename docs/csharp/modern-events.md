---
title: 更新的 .NET Core 事件模式
description: 了解 .NET Core 事件模式如何通过向后兼容性实现灵活性，以及如何通过异步订阅服务器实现安全事件处理。
ms.date: 06/20/2016
ms.assetid: 9aa627c3-3222-4094-9ca8-7e88e1071e06
ms.openlocfilehash: 158295215932f54c75afdf1e96d48453434129fe
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "64751784"
---
# <a name="the-updated-net-core-event-pattern"></a><span data-ttu-id="1b289-103">更新的 .NET Core 事件模式</span><span class="sxs-lookup"><span data-stu-id="1b289-103">The Updated .NET Core Event Pattern</span></span>

[<span data-ttu-id="1b289-104">上一篇文章</span><span class="sxs-lookup"><span data-stu-id="1b289-104">Previous</span></span>](event-pattern.md)

<span data-ttu-id="1b289-105">上一篇文章讨论了最常见的事件模式。</span><span class="sxs-lookup"><span data-stu-id="1b289-105">The previous article discussed the most common event patterns.</span></span> <span data-ttu-id="1b289-106">.NET Core 的模式较为宽松。</span><span class="sxs-lookup"><span data-stu-id="1b289-106">.NET Core has a more relaxed pattern.</span></span> <span data-ttu-id="1b289-107">在此版本中，`EventHandler<TEventArgs>` 定义不再要求 `TEventArgs` 必须是派生自 `System.EventArgs` 的类。</span><span class="sxs-lookup"><span data-stu-id="1b289-107">In this version, the `EventHandler<TEventArgs>` definition no longer has the constraint that `TEventArgs` must be a class derived from `System.EventArgs`.</span></span>

<span data-ttu-id="1b289-108">这就提高了灵活性，并且还具有后向兼容性。</span><span class="sxs-lookup"><span data-stu-id="1b289-108">This increases flexibility for you, and is backwards compatible.</span></span> <span data-ttu-id="1b289-109">首先讨论灵活性。</span><span class="sxs-lookup"><span data-stu-id="1b289-109">Let's start with the flexibility.</span></span> <span data-ttu-id="1b289-110">类 System.EventArgs 引入了一个方法 `MemberwiseClone()`，该方法可创建对象的浅表副本。</span><span class="sxs-lookup"><span data-stu-id="1b289-110">The class System.EventArgs introduces one method: `MemberwiseClone()`, which creates a shallow copy of the object.</span></span>
<span data-ttu-id="1b289-111">对于任何派生自 `EventArgs` 的类，该方法必须使用反射才能实现其功能。</span><span class="sxs-lookup"><span data-stu-id="1b289-111">That method must use reflection in order to implement its functionality for any class derived from `EventArgs`.</span></span> <span data-ttu-id="1b289-112">该功能在特定的派生类中更容易创建。</span><span class="sxs-lookup"><span data-stu-id="1b289-112">That functionality is easier to create in a specific derived class.</span></span> <span data-ttu-id="1b289-113">实际上，这意味着派生自 System.EventArgs 的类会限制你的设计，且不会为你提供任何附加好处。</span><span class="sxs-lookup"><span data-stu-id="1b289-113">That effectively means that deriving from System.EventArgs is a constraint that limits your designs, but does not provide any additional benefit.</span></span>
<span data-ttu-id="1b289-114">其实，可以更改 `FileFoundArgs` 和 `SearchDirectoryArgs` 的定义，使它们不从 `EventArgs` 派生。</span><span class="sxs-lookup"><span data-stu-id="1b289-114">In fact, you can change the definitions of `FileFoundArgs` and `SearchDirectoryArgs` so that they do not derive from `EventArgs`.</span></span>
<span data-ttu-id="1b289-115">该程序的工作原理相同。</span><span class="sxs-lookup"><span data-stu-id="1b289-115">The program will work exactly the same.</span></span>

<span data-ttu-id="1b289-116">如果还要进行一处更改，还可将 `SearchDirectoryArgs` 更改为结构：</span><span class="sxs-lookup"><span data-stu-id="1b289-116">You could also change the `SearchDirectoryArgs` to a struct, if you make one more change:</span></span>

```csharp
internal struct SearchDirectoryArgs
{
    internal string CurrentSearchDirectory { get; }
    internal int TotalDirs { get; }
    internal int CompletedDirs { get; }

    internal SearchDirectoryArgs(string dir, int totalDirs, int completedDirs) : this()
    {
        CurrentSearchDirectory = dir;
        TotalDirs = totalDirs;
        CompletedDirs = completedDirs;
    }
}
```

<span data-ttu-id="1b289-117">其他更改为：在输入初始化所有字段的构造函数之前调用无参数构造函数。</span><span class="sxs-lookup"><span data-stu-id="1b289-117">The additional change is to call the parameterless constructor before entering the constructor that initializes all the fields.</span></span> <span data-ttu-id="1b289-118">若没有此添加，C# 规则将报告先访问属性再分配属性。</span><span class="sxs-lookup"><span data-stu-id="1b289-118">Without that addition, the rules of C# would report that the properties are being accessed before they have been assigned.</span></span>

<span data-ttu-id="1b289-119">不应将 `FileFoundArgs` 从类（引用类型）更改为结构（值类型）。</span><span class="sxs-lookup"><span data-stu-id="1b289-119">You should not change the `FileFoundArgs` from a class (reference type) to a struct (value type).</span></span> <span data-ttu-id="1b289-120">这是因为处理取消的协议要求通过引用传递事件参数。</span><span class="sxs-lookup"><span data-stu-id="1b289-120">That's because the protocol for handling cancel requires that the event arguments are passed by reference.</span></span> <span data-ttu-id="1b289-121">如果进行了相同的更改，文件搜索类将永远不会观察到任何事件订阅者所做的任何更改。</span><span class="sxs-lookup"><span data-stu-id="1b289-121">If you made the same change, the file search class could never observe any changes made by any of the event subscribers.</span></span> <span data-ttu-id="1b289-122">结构的新副本将用于每个订阅者，并且该副本将与文件搜索对象所看到的不同。</span><span class="sxs-lookup"><span data-stu-id="1b289-122">A new copy of the structure would be used for each subscriber, and that copy would be a different copy than the one seen by the file search object.</span></span>

<span data-ttu-id="1b289-123">接下来，让我们考虑这种更改如何具有后向兼容性。</span><span class="sxs-lookup"><span data-stu-id="1b289-123">Next, let's consider how this change can be backwards compatible.</span></span>
<span data-ttu-id="1b289-124">删除约束不会影响任何现有代码。</span><span class="sxs-lookup"><span data-stu-id="1b289-124">The removal of the constraint does not affect any existing code.</span></span> <span data-ttu-id="1b289-125">任何现有的事件参数类型仍然派生自 `System.EventArgs`。</span><span class="sxs-lookup"><span data-stu-id="1b289-125">Any existing event argument types do still derive from `System.EventArgs`.</span></span>
<span data-ttu-id="1b289-126">它们将继续从 `System.EventArgs` 派生，其中一个主要原因就是后向兼容性。</span><span class="sxs-lookup"><span data-stu-id="1b289-126">Backwards compatibility is one major reason why they will continue to derive from `System.EventArgs`.</span></span> <span data-ttu-id="1b289-127">任何现有的事件订阅者都是遵循经典模式的事件的订阅者。</span><span class="sxs-lookup"><span data-stu-id="1b289-127">Any existing event subscribers will be subscribers to an event that followed the classic pattern.</span></span>

<span data-ttu-id="1b289-128">遵循类似的逻辑，现在创建的任何事件参数类型在任何现有代码库中都不会有任何订阅者。</span><span class="sxs-lookup"><span data-stu-id="1b289-128">Following similar logic, any event argument type created now would not have any subscribers in any existing codebases.</span></span> <span data-ttu-id="1b289-129">只有从 `System.EventArgs` 派生的新事件类型才会破坏这些代码库。</span><span class="sxs-lookup"><span data-stu-id="1b289-129">New event types that do not derive from `System.EventArgs` will not break those codebases.</span></span>

## <a name="events-with-async-subscribers"></a><span data-ttu-id="1b289-130">异步事件订阅者</span><span class="sxs-lookup"><span data-stu-id="1b289-130">Events with Async subscribers</span></span>

<span data-ttu-id="1b289-131">还有最后一个模式需要了解：如何正确编写调用异步代码的事件订阅服务器。</span><span class="sxs-lookup"><span data-stu-id="1b289-131">You have one final pattern to learn: How to correctly write event subscribers that call async code.</span></span> <span data-ttu-id="1b289-132">该问题详见 [async 和 await](async.md) 一文。</span><span class="sxs-lookup"><span data-stu-id="1b289-132">The challenge is described in the article on [async and await](async.md).</span></span> <span data-ttu-id="1b289-133">异步方法可具有一个 void 返回类型，但强烈建议不要使用它。</span><span class="sxs-lookup"><span data-stu-id="1b289-133">Async methods can have a void return type, but that is strongly discouraged.</span></span> <span data-ttu-id="1b289-134">事件订阅者代码调用异步方法时，只能创建 `async void` 方法。</span><span class="sxs-lookup"><span data-stu-id="1b289-134">When your event subscriber code calls an async method, you have no choice but to create an `async void` method.</span></span> <span data-ttu-id="1b289-135">事件处理程序签名需要该方法。</span><span class="sxs-lookup"><span data-stu-id="1b289-135">The event handler signature requires it.</span></span>

<span data-ttu-id="1b289-136">你需要协调此对立指南。</span><span class="sxs-lookup"><span data-stu-id="1b289-136">You need to reconcile this opposing guidance.</span></span> <span data-ttu-id="1b289-137">不管怎样，必须创建安全的 `async void` 方法。</span><span class="sxs-lookup"><span data-stu-id="1b289-137">Somehow, you must create a safe `async void` method.</span></span> <span data-ttu-id="1b289-138">需要实现的模式的基础知识如下：</span><span class="sxs-lookup"><span data-stu-id="1b289-138">The basics of the pattern you need to implement are below:</span></span>

```csharp
worker.StartWorking += async (sender, eventArgs) =>
{
    try 
    {
        await DoWorkAsync();
    }
    catch (Exception e)
    {
        //Some form of logging.
        Console.WriteLine($"Async task failure: {e.ToString()}");
        // Consider gracefully, and quickly exiting.
    }
};
```

<span data-ttu-id="1b289-139">首先请注意，处理程序已被标记为异步处理程序。</span><span class="sxs-lookup"><span data-stu-id="1b289-139">First, notice that the handler is marked as an async handler.</span></span> <span data-ttu-id="1b289-140">因为它将被分配给一个事件处理程序委托类型，所以它将有一个 void 返回类型。</span><span class="sxs-lookup"><span data-stu-id="1b289-140">Because it is being assigned to an event handler delegate type, it will have a void return type.</span></span> <span data-ttu-id="1b289-141">这意味着必须遵循处理程序中显示的模式，并且不允许在异步处理程序上下文之外引发异常。</span><span class="sxs-lookup"><span data-stu-id="1b289-141">That means you must follow the pattern shown in the handler, and not allow any exceptions to be thrown out of the context of the async handler.</span></span> <span data-ttu-id="1b289-142">因为它不返回任务，所以没有任何可通过进入故障状态报告错误的任务。</span><span class="sxs-lookup"><span data-stu-id="1b289-142">Because it does not return a task, there is no task that can report the error by entering the faulted state.</span></span> <span data-ttu-id="1b289-143">因为方法是异步的，所以不能简单地引发异常。</span><span class="sxs-lookup"><span data-stu-id="1b289-143">Because the method is async, the method can't simply throw the exception.</span></span> <span data-ttu-id="1b289-144">（调用方法已继续执行，因为它是 `async`。）对于不同的环境，实际的运行时行为将有不同的定义。</span><span class="sxs-lookup"><span data-stu-id="1b289-144">(The calling method has continued execution because it is `async`.) The actual runtime behavior will be defined differently for different environments.</span></span> <span data-ttu-id="1b289-145">它可能会终止线程或程序，或可能使程序处于未确定状态。</span><span class="sxs-lookup"><span data-stu-id="1b289-145">It may terminate the thread, it may terminate the program, or it may leave the program in an undetermined state.</span></span> <span data-ttu-id="1b289-146">这些都不是好的结果。</span><span class="sxs-lookup"><span data-stu-id="1b289-146">None of those are good outcomes.</span></span>

<span data-ttu-id="1b289-147">这就是为什么你应该在自己的 try 块中包装异步任务的 await 语句。</span><span class="sxs-lookup"><span data-stu-id="1b289-147">That's why you should wrap the await statement for the async Task in your own try block.</span></span> <span data-ttu-id="1b289-148">如果它的确导致任务出错，则可以记录该错误。</span><span class="sxs-lookup"><span data-stu-id="1b289-148">If it does cause a faulted task, you can log the error.</span></span> <span data-ttu-id="1b289-149">如果它是应用程序无法从中恢复的错误，则可以迅速优雅地退出此程序。</span><span class="sxs-lookup"><span data-stu-id="1b289-149">If it is an error from which your application cannot recover, you can exit the program quickly and gracefully</span></span>

<span data-ttu-id="1b289-150">这些就是 .NET 事件模式的主要更新。</span><span class="sxs-lookup"><span data-stu-id="1b289-150">Those are the major updates to the .NET event pattern.</span></span> <span data-ttu-id="1b289-151">你将在所使用的库中看到许多早期版本的示例。</span><span class="sxs-lookup"><span data-stu-id="1b289-151">You will see many examples of the earlier versions in the libraries you work with.</span></span> <span data-ttu-id="1b289-152">但是，你也应了解最新的模式是什么。</span><span class="sxs-lookup"><span data-stu-id="1b289-152">However, you should understand what the latest patterns are as well.</span></span>

<span data-ttu-id="1b289-153">本系列的下一篇文章将有助于你区分在设计中使用 `delegates` 和 `events`。</span><span class="sxs-lookup"><span data-stu-id="1b289-153">The next article in this series helps you distinguish between using `delegates` and `events` in your designs.</span></span> <span data-ttu-id="1b289-154">它们是类似的概念，该文章将帮助你为程序做出最好的决定。</span><span class="sxs-lookup"><span data-stu-id="1b289-154">They are similar concepts, and that article will help you make the best decision for your programs.</span></span>

[<span data-ttu-id="1b289-155">下一页</span><span class="sxs-lookup"><span data-stu-id="1b289-155">Next</span></span>](distinguish-delegates-events.md)
