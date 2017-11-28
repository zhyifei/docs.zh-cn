---
title: "标准 .NET 事件模式"
description: "介绍 .NET 事件模式，如何创建标准事件源以及订阅并处理代码中的标准事件。"
keywords: .NET, .NET Core
author: BillWagner
ms.author: wiwagn
ms.date: 06/20/2016
ms.topic: article
ms.prod: .net
ms.technology: devlang-csharp
ms.devlang: csharp
ms.assetid: 8a3133d6-4ef2-46f9-9c8d-a8ea8898e4c9
ms.openlocfilehash: 703b7b13a2175fb9c40ff707f333a1bf1530df8c
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="standard-net-event-patterns"></a><span data-ttu-id="add5a-104">标准 .NET 事件模式</span><span class="sxs-lookup"><span data-stu-id="add5a-104">Standard .NET event patterns</span></span>

[<span data-ttu-id="add5a-105">上一页</span><span class="sxs-lookup"><span data-stu-id="add5a-105">Previous</span></span>](events-overview.md)

<span data-ttu-id="add5a-106">.NET 事件通常遵循几种已知模式。</span><span class="sxs-lookup"><span data-stu-id="add5a-106">.NET events generally follow a few known patterns.</span></span> <span data-ttu-id="add5a-107">标准化这些模式意味着开发人员可利用这些标准模式的相关知识，将其应用于任何 .NET 事件程序。</span><span class="sxs-lookup"><span data-stu-id="add5a-107">Standardizing on these patterns means that developers can leverage knowledge of those standard patterns, which can be applied to any .NET event program.</span></span>

<span data-ttu-id="add5a-108">让我们开始通览这些标准模式，以便你掌握创建标准事件源、在代码中订阅和处理标准事件所需的全部知识。</span><span class="sxs-lookup"><span data-stu-id="add5a-108">Let's go through these standard patterns so you will have all the knowledge you need to create standard event sources, and subscribe and process standard events in your code.</span></span>

## <a name="event-delegate-signatures"></a><span data-ttu-id="add5a-109">事件委托签名</span><span class="sxs-lookup"><span data-stu-id="add5a-109">Event Delegate Signatures</span></span>

<span data-ttu-id="add5a-110">.NET 事件委托的标准签名是：</span><span class="sxs-lookup"><span data-stu-id="add5a-110">The standard signature for a .NET event delegate is:</span></span>

```csharp
void OnEventRaised(object sender, EventArgs args);
```

<span data-ttu-id="add5a-111">返回类型为 void。</span><span class="sxs-lookup"><span data-stu-id="add5a-111">The return type is void.</span></span> <span data-ttu-id="add5a-112">事件基于委托，而且是多播委托。</span><span class="sxs-lookup"><span data-stu-id="add5a-112">Events are based on delegates and are multicast delegates.</span></span> <span data-ttu-id="add5a-113">对任何事件源都支持多个订阅服务器。</span><span class="sxs-lookup"><span data-stu-id="add5a-113">That supports multiple subscribers for any event source.</span></span> <span data-ttu-id="add5a-114">来自方法的单个返回值不会扩展到多个事件订阅服务器。</span><span class="sxs-lookup"><span data-stu-id="add5a-114">The single return value from a method doesn't scale to multiple event subscribers.</span></span> <span data-ttu-id="add5a-115">引发事件后事件源的返回值是什么？</span><span class="sxs-lookup"><span data-stu-id="add5a-115">Which return value does the event source see after raising an event?</span></span> <span data-ttu-id="add5a-116">稍后在本文中将介绍如何创建事件协议，以支持事件订阅服务器向事件源报告信息。</span><span class="sxs-lookup"><span data-stu-id="add5a-116">Later in this article you'll see how to create event protocols that support event subscribers that report information to the event source.</span></span>

<span data-ttu-id="add5a-117">参数列表包含两种参数：发件人和事件参数。</span><span class="sxs-lookup"><span data-stu-id="add5a-117">The argument list contains two arguments: the sender, and the event arguments.</span></span> <span data-ttu-id="add5a-118">`sender` 的编译时类型为 `System.Object`，即使有一个始终正确的更底层派生的类型亦是如此。</span><span class="sxs-lookup"><span data-stu-id="add5a-118">The compile time type of `sender` is `System.Object`, even though you likely know a more derived type that would always be correct.</span></span> <span data-ttu-id="add5a-119">按照惯例使用 `object`。</span><span class="sxs-lookup"><span data-stu-id="add5a-119">By convention, use `object`.</span></span>

<span data-ttu-id="add5a-120">第二种参数通常是派生自 `System.EventArgs` 的类型。</span><span class="sxs-lookup"><span data-stu-id="add5a-120">The second argument has typically been a type that is derived from `System.EventArgs`.</span></span> <span data-ttu-id="add5a-121">（在[下一部分](modern-events.md)中此约定不再强制执行。）即使事件类型无需任何其他参数，你仍将提供这两种参数。</span><span class="sxs-lookup"><span data-stu-id="add5a-121">(You'll see in the [next section](modern-events.md) that this convention is no longer enforced.) If your event type does not need any additional arguments, you will still provide both arguments.</span></span>
<span data-ttu-id="add5a-122">应使用特殊值 `EventArgs.Empty` 来表示事件不包含任何附加信息。</span><span class="sxs-lookup"><span data-stu-id="add5a-122">There is a special value, `EventArgs.Empty` that you should use to denote that your event does not contain any additional information.</span></span>

<span data-ttu-id="add5a-123">让我们生成一个类，它在目录或遵循模式的任何子目录中列出文件。</span><span class="sxs-lookup"><span data-stu-id="add5a-123">Let's build a class that lists files in a directory, or any of its subdirectories that follow a pattern.</span></span> <span data-ttu-id="add5a-124">此组件为每个找到的与模式相匹配的文件引发事件。</span><span class="sxs-lookup"><span data-stu-id="add5a-124">This component raises an event for each file found that matches the pattern.</span></span>

<span data-ttu-id="add5a-125">使用事件模型有一些设计优势。</span><span class="sxs-lookup"><span data-stu-id="add5a-125">Using an event model provides some design advantages.</span></span> <span data-ttu-id="add5a-126">可以创建多个事件侦听器，用于在找到查找的文件时执行不同的操作。</span><span class="sxs-lookup"><span data-stu-id="add5a-126">You can create multiple event listeners that perform different actions when a sought file is found.</span></span> <span data-ttu-id="add5a-127">合并不同的侦听器可以创建更可靠的算法。</span><span class="sxs-lookup"><span data-stu-id="add5a-127">Combining the different listeners can create more robust algorithms.</span></span>

<span data-ttu-id="add5a-128">下面是找到查找的文件时的初始事件参数声明：</span><span class="sxs-lookup"><span data-stu-id="add5a-128">Here is the initial event argument declaration for finding a sought file:</span></span> 

```csharp
public class FileFoundArgs : EventArgs
{
    public string FoundFile { get; }

    public FileFoundArgs(string fileName)
    {
        FoundFile = fileName;
    }
}
```

<span data-ttu-id="add5a-129">尽管这种类型看上去是小型的仅限数据的类型，但仍应按约定将其设为引用 (`class`) 类型。</span><span class="sxs-lookup"><span data-stu-id="add5a-129">Even though this type looks like a small, data-only type, you should follow the convention and make it a reference (`class`) type.</span></span> <span data-ttu-id="add5a-130">这意味着参数对象将通过引用来传递，并且所有订阅服务器都将查看到任何数据更新。</span><span class="sxs-lookup"><span data-stu-id="add5a-130">That means the argument object will be passed by reference, and any updates to the data will be viewed by all subscribers.</span></span> <span data-ttu-id="add5a-131">第一版是不可变对象。</span><span class="sxs-lookup"><span data-stu-id="add5a-131">The first version is an immutable object.</span></span> <span data-ttu-id="add5a-132">应优先将事件参数类型中的属性设为不可变。</span><span class="sxs-lookup"><span data-stu-id="add5a-132">You should prefer to make the properties in your event argument type immutable.</span></span> <span data-ttu-id="add5a-133">这样一来，一个订阅服务器在其他订阅服务器看到值之前便无法更改值。</span><span class="sxs-lookup"><span data-stu-id="add5a-133">That way, one subscriber cannot change the values before another subscriber sees them.</span></span> <span data-ttu-id="add5a-134">（但对此也有例外，如下所示。）</span><span class="sxs-lookup"><span data-stu-id="add5a-134">(There are exceptions to this, as you'll see below.)</span></span>  

<span data-ttu-id="add5a-135">接下来，我们要在 FileSearcher 类中创建事件声明。</span><span class="sxs-lookup"><span data-stu-id="add5a-135">Next, we need to create the event declaration in the FileSearcher class.</span></span> <span data-ttu-id="add5a-136">利用 `EventHandler<T>` 类型意味着尚无需创建其他类型定义。</span><span class="sxs-lookup"><span data-stu-id="add5a-136">Leveraging the `EventHandler<T>` type means that you don't need to create yet another type definition.</span></span> <span data-ttu-id="add5a-137">只需使用泛型专业化即可。</span><span class="sxs-lookup"><span data-stu-id="add5a-137">You simply use a generic specialization.</span></span>

<span data-ttu-id="add5a-138">让我们通过填充 FileSearcher 类来搜索与模式匹配的文件，并在发现匹配时引发正确的事件。</span><span class="sxs-lookup"><span data-stu-id="add5a-138">Let's fill out the FileSearcher class to search for files that match a pattern, and raise the correct event when a match is discovered.</span></span>

```csharp
public class FileSearcher
{
    public event EventHandler<FileFoundArgs> FileFound;

    public void Search(string directory, string searchPattern)
    {
        foreach (var file in Directory.EnumerateFiles(directory, searchPattern))
        {
            FileFound?.Invoke(this, new FileFoundArgs(file));
        }
    }
}
```

## <a name="definining-and-raising-field-like-events"></a><span data-ttu-id="add5a-139">定义并引发类似字段的事件</span><span class="sxs-lookup"><span data-stu-id="add5a-139">Definining and Raising Field-Like Events</span></span>

<span data-ttu-id="add5a-140">要将事件添加到类，最简单的方式是将该事件声明为公共字段，如上面的示例中所示：</span><span class="sxs-lookup"><span data-stu-id="add5a-140">The simplest way to add an event to your class is to declare that event as a public field, as in the above example:</span></span>

```csharp
public event EventHandler<FileFoundArgs> FileFound;
```

<span data-ttu-id="add5a-141">看起来它像在声明一个公共字段，这似乎是一个面向对象的不良实践。</span><span class="sxs-lookup"><span data-stu-id="add5a-141">This looks like it's declaring a public field, which would appear to be bad object oriented practice.</span></span> <span data-ttu-id="add5a-142">你希望通过属性或方法来保护数据访问。</span><span class="sxs-lookup"><span data-stu-id="add5a-142">You want to protect data access through properties, or methods.</span></span> <span data-ttu-id="add5a-143">尽管这看起来像一次不良实践，但通过编译器生成的代码却创建了包装器，使事件对象仅能以安全的方式进行访问。</span><span class="sxs-lookup"><span data-stu-id="add5a-143">While this make look like a bad practice, the code generated by the compiler does create wrappers so that the event objects can only be accessed in safe ways.</span></span> <span data-ttu-id="add5a-144">类似字段的事件上唯一可用的操作是添加处理程序：</span><span class="sxs-lookup"><span data-stu-id="add5a-144">The only operations available on a field-like event are add handler:</span></span>

```csharp
EventHandler<FileFoundArgs> onFileFound = (sender, eventArgs) =>
    Console.WriteLine(eventArgs.FoundFile);
lister.FileFound += onFIleFound;
```

<span data-ttu-id="add5a-145">和删除处理程序：</span><span class="sxs-lookup"><span data-stu-id="add5a-145">and remove handler:</span></span>

```csharp
lister.FileFound -= onFileFound;
```

<span data-ttu-id="add5a-146">请注意，处理程序有一个局部变量。</span><span class="sxs-lookup"><span data-stu-id="add5a-146">Note that there's a local variable for the handler.</span></span> <span data-ttu-id="add5a-147">如果使用了 lambda 的正文，则删除操作无法正常进行。</span><span class="sxs-lookup"><span data-stu-id="add5a-147">If you used the body of the lambda, the remove would not work correctly.</span></span> <span data-ttu-id="add5a-148">它将成为不同的委托实例，并静默地不执行任何操作。</span><span class="sxs-lookup"><span data-stu-id="add5a-148">It would be a different instance of the delegate, and silently do nothing.</span></span>

<span data-ttu-id="add5a-149">类之外的代码无法引发事件，也不能执行任何其它操作。</span><span class="sxs-lookup"><span data-stu-id="add5a-149">Code outside the class cannot raise the event, nor can it perform any other operations.</span></span>

## <a name="returning-values-from-event-subscribers"></a><span data-ttu-id="add5a-150">从事件订阅服务器返回值</span><span class="sxs-lookup"><span data-stu-id="add5a-150">Returning Values from Event Subscribers</span></span>

<span data-ttu-id="add5a-151">你的简单版本当前运行正常。</span><span class="sxs-lookup"><span data-stu-id="add5a-151">Your simple version is working fine.</span></span> <span data-ttu-id="add5a-152">让我们添加另一项功能：取消。</span><span class="sxs-lookup"><span data-stu-id="add5a-152">Let's add another feature: Cancellation.</span></span>

<span data-ttu-id="add5a-153">在引发找到的事件时，如果此文件是最后查找到的文件，则侦听器应能够停止进一步的处理。</span><span class="sxs-lookup"><span data-stu-id="add5a-153">When you raise the found event, listeners should be able to stop further processing, if this file is that last one sought.</span></span>

<span data-ttu-id="add5a-154">事件处理程序不返回值，因此需以其它方式进行通信。</span><span class="sxs-lookup"><span data-stu-id="add5a-154">The event handlers do not return a value, so you need to communicate that in another way.</span></span> <span data-ttu-id="add5a-155">标准事件模式使用 EventArgs 对象来包含字段，事件订阅服务器使用这些字段进行通信取消。</span><span class="sxs-lookup"><span data-stu-id="add5a-155">The standard event pattern uses the EventArgs object to include fields that event subscribers can use to communicate cancel.</span></span>

<span data-ttu-id="add5a-156">根据“取消”协定的语义，有两种不同的模式可供使用。</span><span class="sxs-lookup"><span data-stu-id="add5a-156">There are two different patterns that could be used, based on the semantics of the Cancel contract.</span></span> <span data-ttu-id="add5a-157">在两种情况下，你都将为找到的文件事件向 EventArguments 添加布尔字段。</span><span class="sxs-lookup"><span data-stu-id="add5a-157">In both cases, you'll add a boolean field to the EventArguments for the found file event.</span></span> 

<span data-ttu-id="add5a-158">其中一种模式允许任一订阅服务器取消操作。</span><span class="sxs-lookup"><span data-stu-id="add5a-158">One pattern would allow any one subscriber to cancel the operation.</span></span>
<span data-ttu-id="add5a-159">在此模式下，新字段会初始化为 `false`。</span><span class="sxs-lookup"><span data-stu-id="add5a-159">For this pattern, the new field is initialized to `false`.</span></span> <span data-ttu-id="add5a-160">任何订阅服务器都可将其更改为 `true`。</span><span class="sxs-lookup"><span data-stu-id="add5a-160">Any subscriber can change it to `true`.</span></span> <span data-ttu-id="add5a-161">当所有订阅服务器观察到事件已引发后，FileSearcher 组件将检查布尔值，并执行操作。</span><span class="sxs-lookup"><span data-stu-id="add5a-161">After all subscribers have seen the event raised, the FileSearcher component examines the boolean value and takes action.</span></span>

<span data-ttu-id="add5a-162">在第二种模式下，仅当所有订阅服务器都要取消操作时才可取消操作。</span><span class="sxs-lookup"><span data-stu-id="add5a-162">The second pattern would only cancel the operation if all subscribers wanted the operation cancelled.</span></span> <span data-ttu-id="add5a-163">在此模式下，新字段会初始化为指示操作应取消，而任何订阅服务器都可将其更改为指示操作应继续。</span><span class="sxs-lookup"><span data-stu-id="add5a-163">In this pattern, the new field is initialized to indicate the operation should cancel, and any subscriber could change it to indicate the operation should continue.</span></span>
<span data-ttu-id="add5a-164">当所有订阅服务器观察到事件已引发后，FileSearcher 组件将检查布尔，并执行操作。</span><span class="sxs-lookup"><span data-stu-id="add5a-164">After all subscribers have seen the event raised, the FileSearcher component examines the boolean and takes action.</span></span> <span data-ttu-id="add5a-165">此模式还有一个额外步骤：组件需知道是否有任何订阅服务器已经看到过该事件。</span><span class="sxs-lookup"><span data-stu-id="add5a-165">There is one extra step in this pattern: the component needs to know if any subscribers have seen the event.</span></span> <span data-ttu-id="add5a-166">如果没有订阅服务器，字段会错误地指示取消。</span><span class="sxs-lookup"><span data-stu-id="add5a-166">If there are no subscribers, the field would indicate a cancel incorrectly.</span></span>

<span data-ttu-id="add5a-167">让我们来实现此示例的第一版。</span><span class="sxs-lookup"><span data-stu-id="add5a-167">Let's implement the first version for this sample.</span></span> <span data-ttu-id="add5a-168">需将布尔字段添加至 FileFoundEventArgs 类型：</span><span class="sxs-lookup"><span data-stu-id="add5a-168">You need to add a boolean field to the FileFoundEventArgs type:</span></span>

```csharp
public class FileFoundArgs : EventArgs
{
    public string FoundFile { get; }
    public bool CancelRequested { get; set; }

    public FileFoundArgs(string fileName)
    {
        FoundFile = fileName;
    }
}
```

<span data-ttu-id="add5a-169">应将此新字段初始化为 false，以免无故取消。</span><span class="sxs-lookup"><span data-stu-id="add5a-169">This new Field should be initialized to false, so you don't cancel for no reason.</span></span> <span data-ttu-id="add5a-170">这是布尔字段的默认值，因此将自动设置。</span><span class="sxs-lookup"><span data-stu-id="add5a-170">That is the default value for a boolean field, so that happens automatically.</span></span> <span data-ttu-id="add5a-171">对组件进行的唯一其它更改是在引发事件后检查标志，查看是否有任何订阅服务器提出了取消请求：</span><span class="sxs-lookup"><span data-stu-id="add5a-171">The only other change to the component is to check the flag after raising the event to see if any of the subscribers have requested a cancellation:</span></span>

```csharp
public void List(string directory, string searchPattern)
{
    foreach (var file in Directory.EnumerateFiles(directory, searchPattern))
    {
        var args = new FileFoundArgs(file);
        FileFound?.Invoke(this, args);
        if (args.CancelRequested)
            break;
    }
}
```

<span data-ttu-id="add5a-172">此模式的一个优点是不会造成重大更改。</span><span class="sxs-lookup"><span data-stu-id="add5a-172">One advantage of this pattern is that it isn't a breaking change.</span></span>
<span data-ttu-id="add5a-173">在此之前没有订阅服务器请求取消，现在也不会有。</span><span class="sxs-lookup"><span data-stu-id="add5a-173">None of the subscribers requested a cancel before, and they still are not.</span></span> <span data-ttu-id="add5a-174">没有任何订阅服务器代码需要更新，除非它们想支持新的取消协议。</span><span class="sxs-lookup"><span data-stu-id="add5a-174">None of the subscriber code needs updating unless they want to support the new cancel protocol.</span></span> <span data-ttu-id="add5a-175">这是极为松散耦合的。</span><span class="sxs-lookup"><span data-stu-id="add5a-175">It's very loosely coupled.</span></span>

<span data-ttu-id="add5a-176">让我们来更新订阅服务器，使其在找到第一个可执行文件时请求取消：</span><span class="sxs-lookup"><span data-stu-id="add5a-176">Let's update the subscriber so that it requests a cancellation once it finds the first executable:</span></span>

```csharp
EventHandler<FileFoundArgs> onFileFound = (sender, eventArgs) =>
{
    Console.WriteLine(eventArgs.FoundFile);
    eventArgs.CancelRequested = true;
};
```

## <a name="adding-another-event-declaration"></a><span data-ttu-id="add5a-177">添加另一个事件声明</span><span class="sxs-lookup"><span data-stu-id="add5a-177">Adding Another Event Declaration</span></span>

<span data-ttu-id="add5a-178">让我们再添加一项功能，并演示事件的其它语言习惯用语。</span><span class="sxs-lookup"><span data-stu-id="add5a-178">Let's add one more feature, and demonstrate other language idioms for events.</span></span> <span data-ttu-id="add5a-179">让我们添加搜索文件时遍历所有子目录的 `Search()` 方法的重载。</span><span class="sxs-lookup"><span data-stu-id="add5a-179">Let's add an overload of the `Search()` method that traverses all subdirectories in search of files.</span></span>

<span data-ttu-id="add5a-180">在拥有多个子目录的目录中，此操作可能要花较长时间。</span><span class="sxs-lookup"><span data-stu-id="add5a-180">This could get to be a lengthy operation in a directory with many sub-directories.</span></span> <span data-ttu-id="add5a-181">让我们添加一个在每次新目录搜索开始时引发的事件。</span><span class="sxs-lookup"><span data-stu-id="add5a-181">Let's add an event that gets raised when each new directory search begins.</span></span> <span data-ttu-id="add5a-182">这让订阅服务器可以跟踪进度，并根据进度更新用户。</span><span class="sxs-lookup"><span data-stu-id="add5a-182">This enables subscribers to track progress, and update the user as to progress.</span></span> <span data-ttu-id="add5a-183">目前为止，你所创建的所有示例都是公共的。</span><span class="sxs-lookup"><span data-stu-id="add5a-183">All the samples you've created so far are public.</span></span> <span data-ttu-id="add5a-184">让我们把这个示例设为内部事件。</span><span class="sxs-lookup"><span data-stu-id="add5a-184">Let's make this one an internal event.</span></span> <span data-ttu-id="add5a-185">这意味着你也可以将这些类型用于参数内部。</span><span class="sxs-lookup"><span data-stu-id="add5a-185">That means you can also make the types used for the arguments internal as well.</span></span>

<span data-ttu-id="add5a-186">首先，创建新的 EventArgs 派生类，用于报告新目录和进度。</span><span class="sxs-lookup"><span data-stu-id="add5a-186">You'll start by creating the new EventArgs derived class for reporting the new directory and progress.</span></span> 

```csharp
internal class SearchDirectoryArgs : EventArgs
{
    internal string CurrentSearchDirectory { get; }
    internal int TotalDirs { get; }
    internal int CompletedDirs { get; }

    internal SearchDirectoryArgs(string dir, int totalDirs, int completedDirs)
    {
        CurrentSearchDirectory = dir;
        TotalDirs = totalDirs;
        CompletedDirs = completedDirs;
    }
}
``` 

<span data-ttu-id="add5a-187">同样，可以根据建议为事件参数设置不可变的引用类型。</span><span class="sxs-lookup"><span data-stu-id="add5a-187">Again, you can follow the recommendations to make an immutable reference type for the event arguments.</span></span>

<span data-ttu-id="add5a-188">接下来，定义事件。</span><span class="sxs-lookup"><span data-stu-id="add5a-188">Next, define the event.</span></span> <span data-ttu-id="add5a-189">此时，需使用不同的语法。</span><span class="sxs-lookup"><span data-stu-id="add5a-189">This time, you'll use a different syntax.</span></span> <span data-ttu-id="add5a-190">除使用字段语法之外，还可以显式创建包含添加或删除处理程序的属性。</span><span class="sxs-lookup"><span data-stu-id="add5a-190">In addition to using the field syntax, you can explicitly create the property, with add and remove handlers.</span></span> <span data-ttu-id="add5a-191">在本例中，此项目的处理程序中无需包含额外的代码，但这一步演示了你可以如何创建它们。</span><span class="sxs-lookup"><span data-stu-id="add5a-191">In this sample, you won't need extra code in those handlers in this project, but this shows how you would create them.</span></span>

```csharp
internal event EventHandler<SearchDirectoryArgs> DirectoryChanged
{
    add { directoryChanged += value; }
    remove { directoryChanged -= value; }
}
private EventHandler<SearchDirectoryArgs> directoryChanged;
```

<span data-ttu-id="add5a-192">在许多方面，此处编写的代码可反映编译器为你已见过的字段事件定义所生成的代码。</span><span class="sxs-lookup"><span data-stu-id="add5a-192">In may ways, the code you write here mirrors the code the compiler generates for the field event definitions you've seen earlier.</span></span> <span data-ttu-id="add5a-193">创建事件所使用的语法与用于[属性](properties.md)的语法是极为相似的。</span><span class="sxs-lookup"><span data-stu-id="add5a-193">You create the event using syntax very similar to that used for [properties](properties.md).</span></span> <span data-ttu-id="add5a-194">请注意，处理程序的名称各不相同：`add` 和 `remove`。</span><span class="sxs-lookup"><span data-stu-id="add5a-194">Notice that the handlers have different names: `add` and `remove`.</span></span> <span data-ttu-id="add5a-195">通过调用它们来订阅事件，或取消订阅事件。</span><span class="sxs-lookup"><span data-stu-id="add5a-195">These are called to subscribe to the event, or unsubscribe from the event.</span></span> <span data-ttu-id="add5a-196">请注意，还必须声明一个私有支持字段以存储事件变量。</span><span class="sxs-lookup"><span data-stu-id="add5a-196">Notice that you also must declare a private backing field to store the event variable.</span></span> <span data-ttu-id="add5a-197">它初始化为 null。</span><span class="sxs-lookup"><span data-stu-id="add5a-197">It is initialized to null.</span></span>

<span data-ttu-id="add5a-198">接下来，让我们添加 Search() 方法的重载，该重载遍历子目录，并引发这两个事件。</span><span class="sxs-lookup"><span data-stu-id="add5a-198">Next, let's add the overload of the Search() method that traverses subdirectories and raises both events.</span></span> <span data-ttu-id="add5a-199">要实现此目的，最简单的方法是使用默认参数来指定你要搜索所有目录：</span><span class="sxs-lookup"><span data-stu-id="add5a-199">The easiest way to accomplish this is to use a default argument to specify that you want to search all directories:</span></span>

```csharp
public void Search(string directory, string searchPattern, bool searchSubDirs = false)
{
    if (searchSubDirs)
    {
        var allDirectories = Directory.GetDirectories(directory, "*.*", SearchOption.AllDirectories);
        var completedDirs = 0;
        var totalDirs = allDirectories.Length + 1;
        foreach (var dir in allDirectories)
        {
            directoryChanged?.Invoke(this,
                new SearchDirectoryArgs(dir, totalDirs, completedDirs++));
            // Recursively search this child directory:
            SearchDirectory(dir, searchPattern);
        }
        // Include the Current Directory:
        directoryChanged?.Invoke(this,
            new SearchDirectoryArgs(directory, totalDirs, completedDirs++));
        SearchDirectory(directory, searchPattern);
    }
    else
    {
        SearchDirectory(directory, searchPattern);
    }
}

private void SearchDirectory(string directory, string searchPattern)
{
    foreach (var file in Directory.EnumerateFiles(directory, searchPattern))
    {
        var args = new FileFoundArgs(file);
        FileFound?.Invoke(this, args);
        if (args.CancelRequested)
            break;
    }
}
```

<span data-ttu-id="add5a-200">此时可运行调用重载的应用程序来搜索所有子目录。</span><span class="sxs-lookup"><span data-stu-id="add5a-200">At this point, you can run the application calling the overload for searching all sub-directories.</span></span> <span data-ttu-id="add5a-201">虽然新 `ChangeDirectory` 事件中没有订阅服务器，但使用 `?.Invoke()` 习惯用语可确保此操作正常。</span><span class="sxs-lookup"><span data-stu-id="add5a-201">There are no subscribers on the new `ChangeDirectory` event, but using the `?.Invoke()` idiom ensures that this works correctly.</span></span>

 <span data-ttu-id="add5a-202">让我们通过添加处理程序来编写一行，用于在控制台窗口显示进度。</span><span class="sxs-lookup"><span data-stu-id="add5a-202">Let's add a handler to write a line that shows the progress in the console window.</span></span> 

```csharp
lister.DirectoryChanged += (sender, eventArgs) =>
{
    Console.Write($"Entering '{eventArgs.CurrentSearchDirectory}'.");
    Console.WriteLine($" {eventArgs.CompletedDirs} of {eventArgs.TotalDirs} completed...");
};
```

<span data-ttu-id="add5a-203">你已了解了整个 .NET 生态系统所遵循的模式。</span><span class="sxs-lookup"><span data-stu-id="add5a-203">You've seen patterns that are followed throughout the .NET ecosystem.</span></span>
<span data-ttu-id="add5a-204">通过学习这些模式和约定，将能够快速编写惯用的 C# 和 .NET。</span><span class="sxs-lookup"><span data-stu-id="add5a-204">By learning these patterns and conventions, you'll be writing idiomatic C# and .NET quickly.</span></span>

<span data-ttu-id="add5a-205">接下来，将了解在 .NET 的最新版本中关于这些模式的一些更改。</span><span class="sxs-lookup"><span data-stu-id="add5a-205">Next, you'll see some changes in these patterns in the most recent release of .NET.</span></span>

[<span data-ttu-id="add5a-206">下一部分</span><span class="sxs-lookup"><span data-stu-id="add5a-206">Next</span></span>](modern-events.md)
