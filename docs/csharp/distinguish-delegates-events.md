---
title: "区别委托和事件"
description: "了解委托和事件的区别，以及何时使用 .NET Core 的这两种功能。"
keywords: .NET, .NET Core
author: BillWagner
ms.author: wiwagn
ms.date: 06/20/2016
ms.topic: article
ms.prod: .net
ms.technology: devlang-csharp
ms.devlang: csharp
ms.assetid: 0fdc8629-2fdb-4a7c-a433-5b9d04eaf911
ms.openlocfilehash: 3026a0d853cb17dcf05d3b98d814044d743e48dc
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="distinguishing-delegates-and-events"></a><span data-ttu-id="5c6fc-104">区别委托和事件</span><span class="sxs-lookup"><span data-stu-id="5c6fc-104">Distinguishing Delegates and Events</span></span>

[<span data-ttu-id="5c6fc-105">上一页</span><span class="sxs-lookup"><span data-stu-id="5c6fc-105">Previous</span></span>](modern-events.md)

<span data-ttu-id="5c6fc-106">对不熟悉 .NET Core 平台的开发人员而言，在基于 `delegates` 的设计和基于 `events` 的设计之间做出选择是困难的。</span><span class="sxs-lookup"><span data-stu-id="5c6fc-106">Developers that are new to the .NET Core platform often struggle when deciding between a design based on `delegates` and a design based on `events`.</span></span> <span data-ttu-id="5c6fc-107">这是一个困难的选择，因为这两种语言功能非常相似。</span><span class="sxs-lookup"><span data-stu-id="5c6fc-107">This is a difficult concept, because the two language features are very similar.</span></span> <span data-ttu-id="5c6fc-108">事件甚至是使用委托的语言支持构建的。</span><span class="sxs-lookup"><span data-stu-id="5c6fc-108">Events are even built using the language support for delegates.</span></span> 

<span data-ttu-id="5c6fc-109">它们都提供了一个后期绑定方案：在该方案中，组件通过调用仅在运行时识别的方法进行通信。</span><span class="sxs-lookup"><span data-stu-id="5c6fc-109">They both offer a late binding scenario: they enable scenarios where a component communicates by calling a method that is only known at runtime.</span></span> <span data-ttu-id="5c6fc-110">它们都支持单个和多个订阅服务器方法。</span><span class="sxs-lookup"><span data-stu-id="5c6fc-110">They both support single and multiple subscriber methods.</span></span> <span data-ttu-id="5c6fc-111">这称为单播和多播支持。</span><span class="sxs-lookup"><span data-stu-id="5c6fc-111">You may find this referred to as singlecast and multicast support.</span></span> <span data-ttu-id="5c6fc-112">二者均支持用于添加和删除处理程序的类似语法。</span><span class="sxs-lookup"><span data-stu-id="5c6fc-112">They both support similar syntax for adding and removing handlers.</span></span> <span data-ttu-id="5c6fc-113">最后，引发事件和调用委托使用完全相同的方法调用语法。</span><span class="sxs-lookup"><span data-stu-id="5c6fc-113">Finally, raising an event and calling a delegate use exactly the same method call syntax.</span></span> <span data-ttu-id="5c6fc-114">它们甚至都支持与 `?.` 运算符一起使用的相同的 `Invoke()` 方法语法。</span><span class="sxs-lookup"><span data-stu-id="5c6fc-114">They even both support the same `Invoke()` method syntax for use with the `?.` operator.</span></span>

<span data-ttu-id="5c6fc-115">鉴于所有这些相似之处，很难确定何时使用何种语法。</span><span class="sxs-lookup"><span data-stu-id="5c6fc-115">With all those similarities, it is easy to have trouble determining when to use which.</span></span>

## <a name="listening-to-events-is-optional"></a><span data-ttu-id="5c6fc-116">侦听事件是可选的</span><span class="sxs-lookup"><span data-stu-id="5c6fc-116">Listening to Events is Optional</span></span>

<span data-ttu-id="5c6fc-117">在确定要使用的语言功能时，最重要的考虑因素为是否必须具有附加的订阅服务器。</span><span class="sxs-lookup"><span data-stu-id="5c6fc-117">The most important consideration in determining which language feature to use is whether or not there must be an attached subscriber.</span></span> <span data-ttu-id="5c6fc-118">如果你的代码必须调用由订阅服务器提供的代码，则应使用基于委托的设计。</span><span class="sxs-lookup"><span data-stu-id="5c6fc-118">If your code must call the code supplied by the subscriber, you should use a design based on delegates.</span></span> <span data-ttu-id="5c6fc-119">如果你的代码在不调用任何订阅服务器的情况下可完成其所有工作，则应使用基于事件的设计。</span><span class="sxs-lookup"><span data-stu-id="5c6fc-119">If your code can complete all its work without calling any subscribers, you should use a design based on events.</span></span> 

<span data-ttu-id="5c6fc-120">请考虑本部分中生成的示例。</span><span class="sxs-lookup"><span data-stu-id="5c6fc-120">Consider the examples built during this section.</span></span> <span data-ttu-id="5c6fc-121">必须为使用 `List.Sort()` 生成的代码提供 comparer 函数，以便对元素进行正确排序。</span><span class="sxs-lookup"><span data-stu-id="5c6fc-121">The code you built using `List.Sort()` must be given a comparer function in order to properly sort the elements.</span></span> <span data-ttu-id="5c6fc-122">必须与委托一起提供 LINQ 查询，以便确定要返回的元素。</span><span class="sxs-lookup"><span data-stu-id="5c6fc-122">LINQ queries must be supplied with delegates in order to determine what elements to return.</span></span> <span data-ttu-id="5c6fc-123">二者均使用与委托一起生成的设计。</span><span class="sxs-lookup"><span data-stu-id="5c6fc-123">Both used a design built with delegates.</span></span>

<span data-ttu-id="5c6fc-124">请考虑 `Progress` 事件。</span><span class="sxs-lookup"><span data-stu-id="5c6fc-124">Consider the `Progress` event.</span></span> <span data-ttu-id="5c6fc-125">它会报告任务进度。</span><span class="sxs-lookup"><span data-stu-id="5c6fc-125">It reports progress on a task.</span></span>
<span data-ttu-id="5c6fc-126">无论是否具有侦听器，该任务将继续进行。</span><span class="sxs-lookup"><span data-stu-id="5c6fc-126">The task continues to proceed whether or not there are any listeners.</span></span>
<span data-ttu-id="5c6fc-127">`FileSearcher` 是另一个示例。</span><span class="sxs-lookup"><span data-stu-id="5c6fc-127">The `FileSearcher` is another example.</span></span> <span data-ttu-id="5c6fc-128">即使没有附加事件订阅服务器，它仍将搜索和查找已找到的所有文件。</span><span class="sxs-lookup"><span data-stu-id="5c6fc-128">It would still search and find all the files that were sought, even with no event subscribers attached.</span></span>
<span data-ttu-id="5c6fc-129">即使没有任何订阅服务器侦听事件，UX 控件仍正常工作。</span><span class="sxs-lookup"><span data-stu-id="5c6fc-129">UX controls still work correctly, even when there are no subscribers listening to the events.</span></span> <span data-ttu-id="5c6fc-130">它们都使用基于事件的设计。</span><span class="sxs-lookup"><span data-stu-id="5c6fc-130">They both use designs based on events.</span></span>

## <a name="return-values-require-delegates"></a><span data-ttu-id="5c6fc-131">返回值需要委托</span><span class="sxs-lookup"><span data-stu-id="5c6fc-131">Return Values Require Delegates</span></span>

<span data-ttu-id="5c6fc-132">另一个注意事项是委托方法所需的方法原型。</span><span class="sxs-lookup"><span data-stu-id="5c6fc-132">Another consideration is the method prototype you would want for your delegate method.</span></span> <span data-ttu-id="5c6fc-133">如你所见，用于事件的委托均具有无效的返回类型。</span><span class="sxs-lookup"><span data-stu-id="5c6fc-133">As you've seen, the delegates used for events all have a void return type.</span></span> <span data-ttu-id="5c6fc-134">你还看到，存在创建事件处理程序的惯用语，该事件处理程序通过修改事件参数对象的属性将信息传回到事件源。</span><span class="sxs-lookup"><span data-stu-id="5c6fc-134">You've also seen that there are idioms to create event handlers that do pass information back to event sources through modifying properties of the event argument object.</span></span> <span data-ttu-id="5c6fc-135">虽然这些惯用语可发挥作用，但它们不像从方法返回值那样自然。</span><span class="sxs-lookup"><span data-stu-id="5c6fc-135">While these idioms do work, they are not as natural as returning a value from a method.</span></span>

<span data-ttu-id="5c6fc-136">请注意，通常可能会同时存在这两种试探法：如果委托方法返回一个值，则它可能会以某种方式影响算法。</span><span class="sxs-lookup"><span data-stu-id="5c6fc-136">Notice that these two heuristics may often both be present: If your delegate method returns a value, it will likely impact the algorithm in some way.</span></span>

## <a name="event-listeners-often-have-longer-lifetimes"></a><span data-ttu-id="5c6fc-137">事件侦听器通常具有较长的生存期</span><span class="sxs-lookup"><span data-stu-id="5c6fc-137">Event Listeners Often Have Longer Lifetimes</span></span> 

<span data-ttu-id="5c6fc-138">这是一种略弱的对齐方式。</span><span class="sxs-lookup"><span data-stu-id="5c6fc-138">This is a slightly weaker justification.</span></span> <span data-ttu-id="5c6fc-139">但是，你可能会发现，当事件源将在很长一段时间内引发事件时，基于事件的设计会更加自然。</span><span class="sxs-lookup"><span data-stu-id="5c6fc-139">However, you may find that event-based designs are more natural when the event source will be raising events over a long period of time.</span></span> <span data-ttu-id="5c6fc-140">可以在许多系统上看到针对 UX 控件的此操作的示例。</span><span class="sxs-lookup"><span data-stu-id="5c6fc-140">You can see examples of this for UX controls on many systems.</span></span> <span data-ttu-id="5c6fc-141">订阅事件后，事件源可能会在程序的整个生存期内引发事件。</span><span class="sxs-lookup"><span data-stu-id="5c6fc-141">Once you subscribe to an event, the event source may raise events throughout the lifetime of the program.</span></span>
<span data-ttu-id="5c6fc-142">（当不再需要事件时，可以取消订阅事件。）</span><span class="sxs-lookup"><span data-stu-id="5c6fc-142">(You can unsubscribe from events when you no longer need them.)</span></span>

<span data-ttu-id="5c6fc-143">将其与许多基于委托的设计（其中委托用作方法的参数，且在返回该方法后不再使用此委托）进行比较。</span><span class="sxs-lookup"><span data-stu-id="5c6fc-143">Contrast that with many delegate-based designs, where a delegate is used as an argument to a method, and the delegate is not used after that method returns.</span></span>

## <a name="evaluate-carefully"></a><span data-ttu-id="5c6fc-144">仔细评估</span><span class="sxs-lookup"><span data-stu-id="5c6fc-144">Evaluate Carefully</span></span>

<span data-ttu-id="5c6fc-145">以上考虑因素并非固定不变的规则。</span><span class="sxs-lookup"><span data-stu-id="5c6fc-145">The above considerations are not hard and fast rules.</span></span> <span data-ttu-id="5c6fc-146">相反，它们代表可帮助决定针对特定使用情况的最佳选择的指南。</span><span class="sxs-lookup"><span data-stu-id="5c6fc-146">Instead, they represent guidance that can help you decide which choice is best for your particular usage.</span></span> <span data-ttu-id="5c6fc-147">因为两者类似，所以甚至可以将两者作为原型，并考虑使用更加自然的一种。</span><span class="sxs-lookup"><span data-stu-id="5c6fc-147">Because they are similar, you can even prototype both, and consider which would be more natural to work with.</span></span> <span data-ttu-id="5c6fc-148">两者均能很好地处理后期绑定方案。</span><span class="sxs-lookup"><span data-stu-id="5c6fc-148">They both handle late binding scenarios well.</span></span> <span data-ttu-id="5c6fc-149">使用能与设计进行最佳通讯的一种。</span><span class="sxs-lookup"><span data-stu-id="5c6fc-149">Use the one that communicates your design the best.</span></span>
