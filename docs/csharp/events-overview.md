---
title: "事件介绍"
description: "本概述中介绍 .NET Core 中的事件和事件的语言设计目标。"
keywords: .NET, .NET Core
author: BillWagner
ms.author: wiwagn
ms.date: 06/20/2016
ms.topic: article
ms.prod: .net
ms.technology: devlang-csharp
ms.devlang: csharp
ms.assetid: 9b8d2a00-1584-4a5b-8994-5003d54d8e0c
ms.openlocfilehash: f81c2d9fc2ec69c295485fe06029b5de65335db0
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="introduction-to-events"></a><span data-ttu-id="406a7-104">事件介绍</span><span class="sxs-lookup"><span data-stu-id="406a7-104">Introduction to Events</span></span>

[<span data-ttu-id="406a7-105">上一篇</span><span class="sxs-lookup"><span data-stu-id="406a7-105">Previous</span></span>](delegates-patterns.md)

<span data-ttu-id="406a7-106">和委托类似，事件是*后期绑定*机制。</span><span class="sxs-lookup"><span data-stu-id="406a7-106">Events are, like delegates, a *late binding* mechanism.</span></span> <span data-ttu-id="406a7-107">实际上，事件是建立在对委托的语言支持之上的。</span><span class="sxs-lookup"><span data-stu-id="406a7-107">In fact, events are built on the language support for delegates.</span></span>

<span data-ttu-id="406a7-108">事件是对象用于（向系统中的所有相关组件）广播已发生事情的一种方式。</span><span class="sxs-lookup"><span data-stu-id="406a7-108">Events are a way for an object to broadcast (to all interested components in the system) that something has happened.</span></span> <span data-ttu-id="406a7-109">任何其他组件都可以订阅事件，并在事件引发时得到通知。</span><span class="sxs-lookup"><span data-stu-id="406a7-109">Any other component can subscribe to the event, and be notified when an event is raised.</span></span>

<span data-ttu-id="406a7-110">你可能已在某些编程中使用过事件。</span><span class="sxs-lookup"><span data-stu-id="406a7-110">You've probably used events in some of your programming.</span></span> <span data-ttu-id="406a7-111">许多图形系统都具有用于报告用户交互的事件模型。</span><span class="sxs-lookup"><span data-stu-id="406a7-111">Many graphical systems have an event model to report user interaction.</span></span> <span data-ttu-id="406a7-112">这些事件会报告鼠标移动、按钮点击和类似的交互。</span><span class="sxs-lookup"><span data-stu-id="406a7-112">These events would report mouse movement, button presses and similar interactions.</span></span> <span data-ttu-id="406a7-113">这是使用事件的最常见情景之一，但并非唯一的情景。</span><span class="sxs-lookup"><span data-stu-id="406a7-113">That's one of the most common, but certainly not the only scenario where events are used.</span></span>

<span data-ttu-id="406a7-114">可以定义应针对类引发的事件。</span><span class="sxs-lookup"><span data-stu-id="406a7-114">You can define events that should be raised for your classes.</span></span> <span data-ttu-id="406a7-115">使用事件时，需要注意的一点是特定事件可能没有任何注册的对象。</span><span class="sxs-lookup"><span data-stu-id="406a7-115">One important consideration when working with events is that there may not be any object registered for a particular event.</span></span> <span data-ttu-id="406a7-116">必须编写代码，以确保在未配置侦听器时不会引发事件。</span><span class="sxs-lookup"><span data-stu-id="406a7-116">You must write your code so that it does not raise events when no listeners are configured.</span></span>

<span data-ttu-id="406a7-117">通过订阅事件，还可在两个对象（事件源和事件接收器）之间创建耦合。</span><span class="sxs-lookup"><span data-stu-id="406a7-117">Subscribing to an event also creates a coupling between two objects (the event source, and the event sink).</span></span> <span data-ttu-id="406a7-118">需要确保当不再对事件感兴趣时，事件接收器将从事件源取消订阅。</span><span class="sxs-lookup"><span data-stu-id="406a7-118">You need to ensure that the event sink unsubscribes from the event source when no longer interested in events.</span></span>

## <a name="design-goals-for-event-support"></a><span data-ttu-id="406a7-119">事件支持的设计目标</span><span class="sxs-lookup"><span data-stu-id="406a7-119">Design Goals for Event Support</span></span>

<span data-ttu-id="406a7-120">事件的语言设计针对这些目标。</span><span class="sxs-lookup"><span data-stu-id="406a7-120">The language design for events targets these goals.</span></span>

<span data-ttu-id="406a7-121">首先，在事件源和事件接收器之间启用非常小的耦合。</span><span class="sxs-lookup"><span data-stu-id="406a7-121">First, enable very minimal coupling between an event source and an event sink.</span></span> <span data-ttu-id="406a7-122">这两个组件可能不会由同一个组织编写，甚至可能会通过完全不同的计划进行更新。</span><span class="sxs-lookup"><span data-stu-id="406a7-122">These two components may not be written by the same organization, and may even be updated on totally different schedules.</span></span>

<span data-ttu-id="406a7-123">其次，订阅事件并从同一事件取消订阅应该非常简单。</span><span class="sxs-lookup"><span data-stu-id="406a7-123">Secondly, it should be very simple to subscribe to an event, and to unsubscribe from that same event.</span></span>

<span data-ttu-id="406a7-124">最后，事件源应支持多个事件订阅服务器。</span><span class="sxs-lookup"><span data-stu-id="406a7-124">And finally, event sources should support multiple event subscribers.</span></span> <span data-ttu-id="406a7-125">它还应支持不附加任何事件订阅服务器。</span><span class="sxs-lookup"><span data-stu-id="406a7-125">It should also support having no event subscribers attached.</span></span>

<span data-ttu-id="406a7-126">你会发现事件的目标与委托的目标非常相似。</span><span class="sxs-lookup"><span data-stu-id="406a7-126">You can see that the goals for events are very similar to the goals for delegates.</span></span>
<span data-ttu-id="406a7-127">因此，事件语言支持基于委托语言支持构建。</span><span class="sxs-lookup"><span data-stu-id="406a7-127">That's why the event language support is built on the delegate language support.</span></span>

## <a name="language-support-for-events"></a><span data-ttu-id="406a7-128">事件的语言支持</span><span class="sxs-lookup"><span data-stu-id="406a7-128">Language Support for Events</span></span>

<span data-ttu-id="406a7-129">用于定义事件以及订阅或取消订阅事件的语法是对委托语法的扩展。</span><span class="sxs-lookup"><span data-stu-id="406a7-129">The syntax for defining events, and subscribing or unsubscribing from events is an extension of the syntax for delegates.</span></span>

<span data-ttu-id="406a7-130">定义使用 `event` 关键字的事件：</span><span class="sxs-lookup"><span data-stu-id="406a7-130">To define an event you use the `event` keyword:</span></span>

```csharp
public event EventHandler<FileListArgs> Progress;
```

<span data-ttu-id="406a7-131">该事件（在此示例中，为 `EventHandler<FileListArgs>`）的类型必须为委托类型。</span><span class="sxs-lookup"><span data-stu-id="406a7-131">The type of the event (`EventHandler<FileListArgs>` in this example) must be a delegate type.</span></span> <span data-ttu-id="406a7-132">声明事件时，应遵循许多约定。</span><span class="sxs-lookup"><span data-stu-id="406a7-132">There are a number of conventions that you should follow when declaring an event.</span></span> <span data-ttu-id="406a7-133">通常情况下，事件委托类型具有无效的返回。</span><span class="sxs-lookup"><span data-stu-id="406a7-133">Typically, the event delegate type has a void return.</span></span>
<span data-ttu-id="406a7-134">事件声明应为谓词或谓词短语。</span><span class="sxs-lookup"><span data-stu-id="406a7-134">Event declarations should be a verb, or a verb phrase.</span></span>
<span data-ttu-id="406a7-135">当事件报告已发生的事情时，请使用过去时（如下例所示）。</span><span class="sxs-lookup"><span data-stu-id="406a7-135">Use past tense (as in this example) when the event reports something that has happened.</span></span> <span data-ttu-id="406a7-136">使用现在时谓词（例如 `Closing`）报告将要发生的事情。</span><span class="sxs-lookup"><span data-stu-id="406a7-136">Use a present tense verb (for example, `Closing`) to report something that is about to happen.</span></span> <span data-ttu-id="406a7-137">通常，使用现在时表示类支持某种类型的自定义行为。</span><span class="sxs-lookup"><span data-stu-id="406a7-137">Often, using present tense indicates that your class supports some kind of customization behavior.</span></span> <span data-ttu-id="406a7-138">最常见的方案之一是支持取消。</span><span class="sxs-lookup"><span data-stu-id="406a7-138">One of the most common scenarios is to support cancellation.</span></span> <span data-ttu-id="406a7-139">例如，`Closing` 事件可能包括指示是否应继续执行关闭操作的参数。</span><span class="sxs-lookup"><span data-stu-id="406a7-139">For example, a `Closing` event may include an argument that would indicate if the close operation should continue, or not.</span></span>  <span data-ttu-id="406a7-140">其他方案可能会允许调用方通过更新事件参数的属性来修改行为。</span><span class="sxs-lookup"><span data-stu-id="406a7-140">Other scenarios may enable callers to modify behavior by updating properties of the event arguments.</span></span> <span data-ttu-id="406a7-141">你可以引发一个事件以指示算法将采取的建议的下一步操作。</span><span class="sxs-lookup"><span data-stu-id="406a7-141">You may raise an event to indicate a proposed next action an algorithm will take.</span></span> <span data-ttu-id="406a7-142">事件处理程序可以通过修改事件参数的属性授权不同的操作。</span><span class="sxs-lookup"><span data-stu-id="406a7-142">The event handler may mandate a different action by modifying  properties of the event argument.</span></span>

<span data-ttu-id="406a7-143">想要引发事件时，使用委托调用语法调用事件处理程序：</span><span class="sxs-lookup"><span data-stu-id="406a7-143">When you want to raise the event, you call the event handlers using the delegate invocation syntax:</span></span>

```csharp
Progress?.Invoke(this, new FileListArgs(file));
```

<span data-ttu-id="406a7-144">如[委托](delegates-patterns.md)部分中所介绍的那样，?.</span><span class="sxs-lookup"><span data-stu-id="406a7-144">As discussed in the section on [delegates](delegates-patterns.md), the ?.</span></span>
<span data-ttu-id="406a7-145">运算符可以轻松确保在事件没有订阅服务器时不引发事件。</span><span class="sxs-lookup"><span data-stu-id="406a7-145">operator makes it easy to ensure that you do not attempt to raise the event when there are no subscribers to that event.</span></span>
 
<span data-ttu-id="406a7-146">通过使用 `+=` 运算符订阅事件：</span><span class="sxs-lookup"><span data-stu-id="406a7-146">You subscribe to an event by using the `+=` operator:</span></span>

```csharp
EventHandler<FileListArgs> onProgress = (sender, eventArgs) => 
    Console.WriteLine(eventArgs.FoundFile);
lister.Progress += OnProgress;
```

<span data-ttu-id="406a7-147">处理程序方法通常为前缀“On”，后跟事件名称，如上所示。</span><span class="sxs-lookup"><span data-stu-id="406a7-147">The handler method typically is the prefix 'On' followed by the event name, as shown above.</span></span>

<span data-ttu-id="406a7-148">使用 `-=` 运算符取消订阅：</span><span class="sxs-lookup"><span data-stu-id="406a7-148">You unsubscribe using the `-=` operator:</span></span>

```csharp
lister.Progress -= onProgress;
```

<span data-ttu-id="406a7-149">请务必注意，我为表示事件处理程序的表达式声明了一个局部变量。</span><span class="sxs-lookup"><span data-stu-id="406a7-149">It's important to note that I declared a local variable for the expression that represents the event handler.</span></span> <span data-ttu-id="406a7-150">这将确保取消订阅删除该处理程序。</span><span class="sxs-lookup"><span data-stu-id="406a7-150">That ensures the unsubscribe removes the handler.</span></span>
<span data-ttu-id="406a7-151">如果使用的是 lambda 表达式的主体，则将尝试删除从未附加过的处理程序，此操作为无效操作。</span><span class="sxs-lookup"><span data-stu-id="406a7-151">If, instead, you used the body of the lambda expression, you are attempting to remove a handler that has never been attached, which does nothing.</span></span>

<span data-ttu-id="406a7-152">下一篇文章将介绍有关典型事件模式及此示例的不同变体的详细信息。</span><span class="sxs-lookup"><span data-stu-id="406a7-152">In the next article, you'll learn more about typical event patterns, and different variations on this example.</span></span>

[<span data-ttu-id="406a7-153">下一篇</span><span class="sxs-lookup"><span data-stu-id="406a7-153">Next</span></span>](event-pattern.md)
