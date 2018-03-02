---
title: "使用 Async 和 Await 的异步编程 (C#)"
ms.date: 05/22/2017
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
ms.assetid: 9bcf896a-5826-4189-8c1a-3e35fa08243a
caps.latest.revision: 
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 6822143df2d02c284d7506d180139c18cfbaf370
ms.sourcegitcommit: 655fd4f78741967f80c409cef98347fdcf77857d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/28/2018
---
# <a name="asynchronous-programming-with-async-and-await-c"></a><span data-ttu-id="a3cf7-102">使用 Async 和 Await 的异步编程 (C#)</span><span class="sxs-lookup"><span data-stu-id="a3cf7-102">Asynchronous programming with async and await (C#)</span></span>
<span data-ttu-id="a3cf7-103">通过使用异步编程，你可以避免性能瓶颈并增强应用程序的总体响应能力。</span><span class="sxs-lookup"><span data-stu-id="a3cf7-103">You can avoid performance bottlenecks and enhance the overall responsiveness of your application by using asynchronous programming.</span></span> <span data-ttu-id="a3cf7-104">但是，编写异步应用程序的传统技术可能比较复杂，使它们难以编写、调试和维护。</span><span class="sxs-lookup"><span data-stu-id="a3cf7-104">However, traditional techniques for writing asynchronous applications can be complicated, making them difficult to write, debug, and maintain.</span></span>  
  
<span data-ttu-id="a3cf7-105">[C# 5](../../../whats-new/index.md#previous-versions) 引入了一种简便方法，即异步编程。此方法利用了 .NET Framework 4.5 及更高版本、.NET Core 和 Windows 运行时中的异步支持。</span><span class="sxs-lookup"><span data-stu-id="a3cf7-105">[C# 5](../../../whats-new/index.md#previous-versions) introduced a simplified approach, async programming, that leverages asynchronous support in the .NET Framework 4.5 and higher, .NET Core, and the Windows Runtime.</span></span> <span data-ttu-id="a3cf7-106">编译器可执行开发人员曾进行的高难度工作，且应用程序保留了一个类似于同步代码的逻辑结构。</span><span class="sxs-lookup"><span data-stu-id="a3cf7-106">The compiler does the difficult work that the developer used to do, and your application retains a logical structure that resembles synchronous code.</span></span> <span data-ttu-id="a3cf7-107">因此，你只需做一小部分工作就可以获得异步编程的所有好处。</span><span class="sxs-lookup"><span data-stu-id="a3cf7-107">As a result, you get all the advantages of asynchronous programming with a fraction of the effort.</span></span>  
  
<span data-ttu-id="a3cf7-108">本主题概述了何时以及如何使用异步编程，并包括指向包含详细信息和示例的支持主题的链接。</span><span class="sxs-lookup"><span data-stu-id="a3cf7-108">This topic provides an overview of when and how to use async programming and includes links to support topics that contain details and examples.</span></span>  
  
##  <a name="BKMK_WhentoUseAsynchrony"></a> <span data-ttu-id="a3cf7-109">异步编程提升响应能力</span><span class="sxs-lookup"><span data-stu-id="a3cf7-109">Async improves responsiveness</span></span>  
 <span data-ttu-id="a3cf7-110">异步对可能会被屏蔽的活动（如 Web 访问）至关重要。</span><span class="sxs-lookup"><span data-stu-id="a3cf7-110">Asynchrony is essential for activities that are potentially blocking, such as web access.</span></span> <span data-ttu-id="a3cf7-111">对 Web 资源的访问有时很慢或会延迟。</span><span class="sxs-lookup"><span data-stu-id="a3cf7-111">Access to a web resource sometimes is slow or delayed.</span></span> <span data-ttu-id="a3cf7-112">如果此类活动在同步过程中被屏蔽，整个应用必须等待。</span><span class="sxs-lookup"><span data-stu-id="a3cf7-112">If such an activity is blocked in a synchronous process, the entire application must wait.</span></span> <span data-ttu-id="a3cf7-113">在异步过程中，应用程序可继续执行不依赖 Web 资源的其他工作，直至潜在阻止任务完成。</span><span class="sxs-lookup"><span data-stu-id="a3cf7-113">In an asynchronous process, the application can continue with other work that doesn't depend on the web resource until the potentially blocking task finishes.</span></span>  
  
 <span data-ttu-id="a3cf7-114">下表显示了异步编程提高响应能力的典型区域。</span><span class="sxs-lookup"><span data-stu-id="a3cf7-114">The following table shows typical areas where asynchronous programming improves responsiveness.</span></span> <span data-ttu-id="a3cf7-115">列出的 .NET 和 Windows 运行时 API 包含支持异步编程的方法。</span><span class="sxs-lookup"><span data-stu-id="a3cf7-115">The listed APIs from .NET and the Windows Runtime contain methods that support async programming.</span></span>  
  
| <span data-ttu-id="a3cf7-116">应用程序区域</span><span class="sxs-lookup"><span data-stu-id="a3cf7-116">Application area</span></span>    | <span data-ttu-id="a3cf7-117">包含异步方法的 .NET 类型</span><span class="sxs-lookup"><span data-stu-id="a3cf7-117">.NET types with async methods</span></span>     | <span data-ttu-id="a3cf7-118">包含异步方法的 Windows 运行时类型</span><span class="sxs-lookup"><span data-stu-id="a3cf7-118">Windows Runtime types with async methods</span></span>  |
|---------------------|-----------------------------------|-------------------------------------------|
|<span data-ttu-id="a3cf7-119">Web 访问 </span><span class="sxs-lookup"><span data-stu-id="a3cf7-119">Web access</span></span>|<xref:System.Net.Http.HttpClient>|<xref:Windows.Web.Syndication.SyndicationClient>|
|<span data-ttu-id="a3cf7-120">使用文件</span><span class="sxs-lookup"><span data-stu-id="a3cf7-120">Working with files</span></span>|<span data-ttu-id="a3cf7-121"><xref:System.IO.StreamWriter>, <xref:System.IO.StreamReader>, <xref:System.Xml.XmlReader></span><span class="sxs-lookup"><span data-stu-id="a3cf7-121"><xref:System.IO.StreamWriter>, <xref:System.IO.StreamReader>, <xref:System.Xml.XmlReader></span></span>|<xref:Windows.Storage.StorageFile>|  
|<span data-ttu-id="a3cf7-122">使用图像</span><span class="sxs-lookup"><span data-stu-id="a3cf7-122">Working with images</span></span>||<span data-ttu-id="a3cf7-123"><xref:Windows.Media.Capture.MediaCapture>, <xref:Windows.Graphics.Imaging.BitmapEncoder>, <xref:Windows.Graphics.Imaging.BitmapDecoder></span><span class="sxs-lookup"><span data-stu-id="a3cf7-123"><xref:Windows.Media.Capture.MediaCapture>, <xref:Windows.Graphics.Imaging.BitmapEncoder>, <xref:Windows.Graphics.Imaging.BitmapDecoder></span></span>|  
|<span data-ttu-id="a3cf7-124">WCF 编程</span><span class="sxs-lookup"><span data-stu-id="a3cf7-124">WCF programming</span></span>|[<span data-ttu-id="a3cf7-125">同步和异步操作</span><span class="sxs-lookup"><span data-stu-id="a3cf7-125">Synchronous and Asynchronous Operations</span></span>](../../../../framework/wcf/synchronous-and-asynchronous-operations.md)||  
  
<span data-ttu-id="a3cf7-126">由于所有与用户界面相关的活动通常共享一个线程，因此，异步对访问 UI 线程的应用程序来说尤为重要。</span><span class="sxs-lookup"><span data-stu-id="a3cf7-126">Asynchrony proves especially valuable for applications that access the UI thread because all UI-related activity usually shares one thread.</span></span> <span data-ttu-id="a3cf7-127">如果任何进程在同步应用程序中受阻，则所有进程都将受阻。</span><span class="sxs-lookup"><span data-stu-id="a3cf7-127">If any process is blocked in a synchronous application, all are blocked.</span></span> <span data-ttu-id="a3cf7-128">你的应用程序停止响应，因此，你可能在其等待过程中认为它已经失败。</span><span class="sxs-lookup"><span data-stu-id="a3cf7-128">Your application stops responding, and you might conclude that it has failed when instead it's just waiting.</span></span>  
  
 <span data-ttu-id="a3cf7-129">使用异步方法时，应用程序将继续响应 UI。</span><span class="sxs-lookup"><span data-stu-id="a3cf7-129">When you use asynchronous methods, the application continues to respond to the UI.</span></span> <span data-ttu-id="a3cf7-130">例如，你可以调整窗口的大小或最小化窗口；如果你不希望等待应用程序结束，则可以将其关闭。</span><span class="sxs-lookup"><span data-stu-id="a3cf7-130">You can resize or minimize a window, for example, or you can close the application if you don't want to wait for it to finish.</span></span>  
  
 <span data-ttu-id="a3cf7-131">当设计异步操作时，该基于异步的方法将自动传输的等效对象添加到可从中选择的选项列表中。</span><span class="sxs-lookup"><span data-stu-id="a3cf7-131">The async-based approach adds the equivalent of an automatic transmission to the list of options that you can choose from when designing asynchronous operations.</span></span> <span data-ttu-id="a3cf7-132">开发人员只需要投入较少的工作量即可使你获取传统异步编程的所有优点。</span><span class="sxs-lookup"><span data-stu-id="a3cf7-132">That is, you get all the benefits of traditional asynchronous programming but with much less effort from the developer.</span></span>  
  
##  <a name="BKMK_HowtoWriteanAsyncMethod"></a> <span data-ttu-id="a3cf7-133">异步方法更容易编写</span><span class="sxs-lookup"><span data-stu-id="a3cf7-133">Async methods are easier to write</span></span>  
 <span data-ttu-id="a3cf7-134">C# 中的 [Async](../../../../csharp/language-reference/keywords/async.md) 和 [Await](../../../../csharp/language-reference/keywords/await.md) 关键字是异步编程的核心。</span><span class="sxs-lookup"><span data-stu-id="a3cf7-134">The [async](../../../../csharp/language-reference/keywords/async.md) and [await](../../../../csharp/language-reference/keywords/await.md) keywords in C# are the heart of async programming.</span></span> <span data-ttu-id="a3cf7-135">通过这两个关键字，可以使用 .NET Framework、.NET Core 或 Windows 运行时中的资源，轻松创建异步方法（几乎与创建同步方法一样轻松）。</span><span class="sxs-lookup"><span data-stu-id="a3cf7-135">By using those two keywords, you can use resources in the .NET Framework, .NET Core, or the Windows Runtime to create an asynchronous method almost as easily as you create a synchronous method.</span></span> <span data-ttu-id="a3cf7-136">使用 `async` 关键字定义的异步方法简称为“异步方法”。</span><span class="sxs-lookup"><span data-stu-id="a3cf7-136">Asynchronous methods that you define by using the `async` keyword are referred to as *async methods*.</span></span>  
  
 <span data-ttu-id="a3cf7-137">下面的示例演示了一种异步方法。</span><span class="sxs-lookup"><span data-stu-id="a3cf7-137">The following example shows an async method.</span></span> <span data-ttu-id="a3cf7-138">你应对代码中的几乎所有内容都非常熟悉。</span><span class="sxs-lookup"><span data-stu-id="a3cf7-138">Almost everything in the code should look completely familiar to you.</span></span> <span data-ttu-id="a3cf7-139">注释调出你添加的用来创建异步的功能。</span><span class="sxs-lookup"><span data-stu-id="a3cf7-139">The comments call out the features that you add to create the asynchrony.</span></span>  
  
 <span data-ttu-id="a3cf7-140">此主题的末尾提供完整的 Windows Presentation Foundation (WPF) 示例文件，请从[异步示例：“使用 Async 和 Await 的异步编程”示例](https://code.msdn.microsoft.com/Async-Sample-Example-from-9b9f505c)下载此示例。</span><span class="sxs-lookup"><span data-stu-id="a3cf7-140">You can find a complete Windows Presentation Foundation (WPF) example file at the end of this topic, and you can download the sample from [Async Sample: Example from "Asynchronous Programming with Async and Await"](https://code.msdn.microsoft.com/Async-Sample-Example-from-9b9f505c).</span></span>  
  
```csharp  
// Three things to note in the signature:  
//  - The method has an async modifier.   
//  - The return type is Task or Task<T>. (See "Return Types" section.)  
//    Here, it is Task<int> because the return statement returns an integer.  
//  - The method name ends in "Async."  
async Task<int> AccessTheWebAsync()  
{   
    // You need to add a reference to System.Net.Http to declare client.  
    HttpClient client = new HttpClient();  
  
    // GetStringAsync returns a Task<string>. That means that when you await the  
    // task you'll get a string (urlContents).  
    Task<string> getStringTask = client.GetStringAsync("http://msdn.microsoft.com");  
  
    // You can do work here that doesn't rely on the string from GetStringAsync.  
    DoIndependentWork();  
  
    // The await operator suspends AccessTheWebAsync.  
    //  - AccessTheWebAsync can't continue until getStringTask is complete.  
    //  - Meanwhile, control returns to the caller of AccessTheWebAsync.  
    //  - Control resumes here when getStringTask is complete.   
    //  - The await operator then retrieves the string result from getStringTask.  
    string urlContents = await getStringTask;  
  
    // The return statement specifies an integer result.  
    // Any methods that are awaiting AccessTheWebAsync retrieve the length value.  
    return urlContents.Length;  
}  
```  
  
 <span data-ttu-id="a3cf7-141">如果 `AccessTheWebAsync` 在调用 `GetStringAsync` 和等待其完成期间不能进行任何工作，则你可以通过在下面的单个语句中调用和等待来简化代码。</span><span class="sxs-lookup"><span data-stu-id="a3cf7-141">If `AccessTheWebAsync` doesn't have any work that it can do between calling `GetStringAsync` and awaiting its completion, you can simplify your code by calling and awaiting in the following single statement.</span></span>  
  
```csharp  
string urlContents = await client.GetStringAsync();  
```  
 
<span data-ttu-id="a3cf7-142">以下特征总结了使上一个示例成为异步方法的原因。</span><span class="sxs-lookup"><span data-stu-id="a3cf7-142">The following characteristics summarize what makes the previous example an async method.</span></span>  
  
-   <span data-ttu-id="a3cf7-143">方法签名包含 `async` 修饰符。</span><span class="sxs-lookup"><span data-stu-id="a3cf7-143">The method signature includes an `async` modifier.</span></span>  
  
-   <span data-ttu-id="a3cf7-144">按照约定，异步方法的名称以“Async”后缀结尾。</span><span class="sxs-lookup"><span data-stu-id="a3cf7-144">The name of an async method, by convention, ends with an "Async" suffix.</span></span>  
  
-   <span data-ttu-id="a3cf7-145">返回类型为下列类型之一：</span><span class="sxs-lookup"><span data-stu-id="a3cf7-145">The return type is one of the following types:</span></span>  
  
    -   <span data-ttu-id="a3cf7-146">如果你的方法有操作数为 `TResult` 类型的返回语句，则为 <xref:System.Threading.Tasks.Task%601>。</span><span class="sxs-lookup"><span data-stu-id="a3cf7-146"><xref:System.Threading.Tasks.Task%601> if your method has a return statement in which the operand has type `TResult`.</span></span>  
  
    -   <span data-ttu-id="a3cf7-147">如果你的方法没有返回语句或具有没有操作数的返回语句，则为 <xref:System.Threading.Tasks.Task>。</span><span class="sxs-lookup"><span data-stu-id="a3cf7-147"><xref:System.Threading.Tasks.Task> if your method has no return statement or has a return statement with no operand.</span></span>  
  
    -   <span data-ttu-id="a3cf7-148">`void`：如果要编写异步事件处理程序。</span><span class="sxs-lookup"><span data-stu-id="a3cf7-148">`void` if you're writing an async event handler.</span></span>  

    -   <span data-ttu-id="a3cf7-149">包含 `GetAwaiter` 方法的其他任何类型（自 C# 7 起）。</span><span class="sxs-lookup"><span data-stu-id="a3cf7-149">Any other type that has a `GetAwaiter` method (starting with C# 7).</span></span>
  
     <span data-ttu-id="a3cf7-150">有关详细信息，请参阅[返回类型和参数](#BKMK_ReturnTypesandParameters)部分。</span><span class="sxs-lookup"><span data-stu-id="a3cf7-150">For more information, see the [Return Types and Parameters](#BKMK_ReturnTypesandParameters) section.</span></span>  
  
-   <span data-ttu-id="a3cf7-151">方法通常包含至少一个 await 表达式，该表达式标记一个点，在该点上，直到等待的异步操作完成方法才能继续。</span><span class="sxs-lookup"><span data-stu-id="a3cf7-151">The method usually includes at least one await expression, which marks a point where the method can't continue until the awaited asynchronous operation is complete.</span></span> <span data-ttu-id="a3cf7-152">同时，将方法挂起，并且控件返回到方法的调用方。</span><span class="sxs-lookup"><span data-stu-id="a3cf7-152">In the meantime, the method is suspended, and control returns to the method's caller.</span></span> <span data-ttu-id="a3cf7-153">本主题的下一节将解释悬挂点发生的情况。</span><span class="sxs-lookup"><span data-stu-id="a3cf7-153">The next section of this topic illustrates what happens at the suspension point.</span></span>  
  
 <span data-ttu-id="a3cf7-154">在异步方法中，可使用提供的关键字和类型来指示需要完成的操作，且编译器会完成其余操作，其中包括持续跟踪控件以挂起方法返回等待点时发生的情况。</span><span class="sxs-lookup"><span data-stu-id="a3cf7-154">In async methods, you use the provided keywords and types to indicate what you want to do, and the compiler does the rest, including keeping track of what must happen when control returns to an await point in a suspended method.</span></span> <span data-ttu-id="a3cf7-155">一些常规流程（例如，循环和异常处理）在传统异步代码中处理起来可能很困难。</span><span class="sxs-lookup"><span data-stu-id="a3cf7-155">Some routine processes, such as loops and exception handling, can be difficult to handle in traditional asynchronous code.</span></span> <span data-ttu-id="a3cf7-156">在异步方法中，元素的编写频率与同步解决方案相同且此问题得到解决。</span><span class="sxs-lookup"><span data-stu-id="a3cf7-156">In an async method, you write these elements much as you would in a synchronous solution, and the problem is solved.</span></span>  
  
 <span data-ttu-id="a3cf7-157">若要详细了解旧版 .NET Framework 中的异步性，请参阅 [TPL 和传统 .NET Framework 异步编程](../../../../standard/parallel-programming/tpl-and-traditional-async-programming.md)。</span><span class="sxs-lookup"><span data-stu-id="a3cf7-157">For more information about asynchrony in previous versions of the .NET Framework, see [TPL and Traditional .NET Framework Asynchronous Programming](../../../../standard/parallel-programming/tpl-and-traditional-async-programming.md).</span></span>  
  
##  <a name="BKMK_WhatHappensUnderstandinganAsyncMethod"></a> <span data-ttu-id="a3cf7-158">异步方法的运行机制</span><span class="sxs-lookup"><span data-stu-id="a3cf7-158">What happens in an async method</span></span>  
 <span data-ttu-id="a3cf7-159">异步编程中最需弄清的是控制流是如何从方法移动到方法的。</span><span class="sxs-lookup"><span data-stu-id="a3cf7-159">The most important thing to understand in asynchronous programming is how the control flow moves from method to method.</span></span> <span data-ttu-id="a3cf7-160">下图可引导你完成该过程。</span><span class="sxs-lookup"><span data-stu-id="a3cf7-160">The following diagram leads you through the process.</span></span>  
  
 <span data-ttu-id="a3cf7-161">![跟踪异步程序](../../../../csharp/programming-guide/concepts/async/media/navigationtrace.png "NavigationTrace")</span><span class="sxs-lookup"><span data-stu-id="a3cf7-161">![Trace an async program](../../../../csharp/programming-guide/concepts/async/media/navigationtrace.png "NavigationTrace")</span></span>  
  
 <span data-ttu-id="a3cf7-162">关系图中的数值对应于以下步骤。</span><span class="sxs-lookup"><span data-stu-id="a3cf7-162">The numbers in the diagram correspond to the following steps.</span></span>  
  
1.  <span data-ttu-id="a3cf7-163">事件处理程序调用并等待 `AccessTheWebAsync` 异步方法。</span><span class="sxs-lookup"><span data-stu-id="a3cf7-163">An event handler calls and awaits the  `AccessTheWebAsync` async method.</span></span>  
  
2.  <span data-ttu-id="a3cf7-164">`AccessTheWebAsync` 可创建 <xref:System.Net.Http.HttpClient> 实例并调用 <xref:System.Net.Http.HttpClient.GetStringAsync%2A> 异步方法以下载网站内容作为字符串。</span><span class="sxs-lookup"><span data-stu-id="a3cf7-164">`AccessTheWebAsync` creates an <xref:System.Net.Http.HttpClient> instance and calls the <xref:System.Net.Http.HttpClient.GetStringAsync%2A> asynchronous method to download the contents of a website as a string.</span></span>  
  
3.  <span data-ttu-id="a3cf7-165">`GetStringAsync` 中发生了某种情况，该情况挂起了它的进程。</span><span class="sxs-lookup"><span data-stu-id="a3cf7-165">Something happens in `GetStringAsync` that suspends its progress.</span></span> <span data-ttu-id="a3cf7-166">可能必须等待网站下载或一些其他阻止活动。</span><span class="sxs-lookup"><span data-stu-id="a3cf7-166">Perhaps it must wait for a website to download or some other blocking activity.</span></span> <span data-ttu-id="a3cf7-167">为避免阻止资源，`GetStringAsync` 会将控制权出让给其调用方 `AccessTheWebAsync`。</span><span class="sxs-lookup"><span data-stu-id="a3cf7-167">To avoid blocking resources, `GetStringAsync` yields control to its caller, `AccessTheWebAsync`.</span></span>  
  
     <span data-ttu-id="a3cf7-168">`GetStringAsync` 返回 <xref:System.Threading.Tasks.Task%601>，其中 `TResult` 为字符串，并且 `AccessTheWebAsync` 将任务分配给 `getStringTask` 变量。</span><span class="sxs-lookup"><span data-stu-id="a3cf7-168">`GetStringAsync` returns a <xref:System.Threading.Tasks.Task%601> where `TResult` is a string, and `AccessTheWebAsync` assigns the task to the `getStringTask` variable.</span></span> <span data-ttu-id="a3cf7-169">该任务表示调用 `GetStringAsync` 的正在进行的进程，其中承诺当工作完成时产生实际字符串值。</span><span class="sxs-lookup"><span data-stu-id="a3cf7-169">The task represents the ongoing process for the call to `GetStringAsync`, with a commitment to produce an actual string value when the work is complete.</span></span>  
  
4.  <span data-ttu-id="a3cf7-170">由于尚未等待 `getStringTask`，因此，`AccessTheWebAsync` 可以继续执行不依赖于 `GetStringAsync` 得出的最终结果的其他工作。</span><span class="sxs-lookup"><span data-stu-id="a3cf7-170">Because `getStringTask` hasn't been awaited yet, `AccessTheWebAsync` can continue with other work that doesn't depend on the final result from `GetStringAsync`.</span></span> <span data-ttu-id="a3cf7-171">该任务由对同步方法 `DoIndependentWork` 的调用表示。</span><span class="sxs-lookup"><span data-stu-id="a3cf7-171">That work is represented by a call to the synchronous method `DoIndependentWork`.</span></span>  
  
5.  <span data-ttu-id="a3cf7-172">`DoIndependentWork` 是完成其工作并返回其调用方的同步方法。</span><span class="sxs-lookup"><span data-stu-id="a3cf7-172">`DoIndependentWork` is a synchronous method that does its work and returns to its caller.</span></span>  
  
6.  <span data-ttu-id="a3cf7-173">`AccessTheWebAsync` 已用完工作，可以不受 `getStringTask` 的结果影响。</span><span class="sxs-lookup"><span data-stu-id="a3cf7-173">`AccessTheWebAsync` has run out of work that it can do without a result from `getStringTask`.</span></span> <span data-ttu-id="a3cf7-174">接下来，`AccessTheWebAsync` 需要计算并返回该下载字符串的长度，但该方法仅在具有字符串时才能计算该值。</span><span class="sxs-lookup"><span data-stu-id="a3cf7-174">`AccessTheWebAsync` next wants to calculate and return the length of the downloaded string, but the method can't calculate that value until the method has the string.</span></span>  
  
     <span data-ttu-id="a3cf7-175">因此，`AccessTheWebAsync` 使用一个 await 运算符来挂起其进度，并把控制权交给调用 `AccessTheWebAsync` 的方法。</span><span class="sxs-lookup"><span data-stu-id="a3cf7-175">Therefore, `AccessTheWebAsync` uses an await operator to suspend its progress and to yield control to the method that called `AccessTheWebAsync`.</span></span> <span data-ttu-id="a3cf7-176">`AccessTheWebAsync` 将 `Task<int>` 返回给调用方。</span><span class="sxs-lookup"><span data-stu-id="a3cf7-176">`AccessTheWebAsync` returns a `Task<int>` to the caller.</span></span> <span data-ttu-id="a3cf7-177">该任务表示对产生下载字符串长度的整数结果的一个承诺。</span><span class="sxs-lookup"><span data-stu-id="a3cf7-177">The task represents a promise to produce an integer result that's the length of the downloaded string.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="a3cf7-178">如果 `GetStringAsync`（因此 `getStringTask`）在 `AccessTheWebAsync` 等待前完成，则控件会保留在 `AccessTheWebAsync` 中。</span><span class="sxs-lookup"><span data-stu-id="a3cf7-178">If `GetStringAsync` (and therefore `getStringTask`) is complete before `AccessTheWebAsync` awaits it, control remains in `AccessTheWebAsync`.</span></span> <span data-ttu-id="a3cf7-179">如果异步调用过程 (`getStringTask`) 已完成，并且 `AccessTheWebSync` 不必等待最终结果，则挂起然后返回到 `AccessTheWebAsync` 将造成成本浪费。</span><span class="sxs-lookup"><span data-stu-id="a3cf7-179">The expense of suspending and then returning to `AccessTheWebAsync` would be wasted if the called asynchronous process (`getStringTask`) has already completed and `AccessTheWebSync` doesn't have to wait for the final result.</span></span>  
  
     <span data-ttu-id="a3cf7-180">在调用方内部（此示例中的事件处理程序），处理模式将继续。</span><span class="sxs-lookup"><span data-stu-id="a3cf7-180">Inside the caller (the event handler in this example), the processing pattern continues.</span></span> <span data-ttu-id="a3cf7-181">在等待结果前，调用方可以开展不依赖于 `AccessTheWebAsync` 结果的其他工作，否则就需等待片刻。</span><span class="sxs-lookup"><span data-stu-id="a3cf7-181">The caller might do other work that doesn't depend on the result from `AccessTheWebAsync` before awaiting that result, or the caller might await immediately.</span></span>   <span data-ttu-id="a3cf7-182">事件处理程序等待 `AccessTheWebAsync`，而 `AccessTheWebAsync` 等待 `GetStringAsync`。</span><span class="sxs-lookup"><span data-stu-id="a3cf7-182">The event handler is waiting for `AccessTheWebAsync`, and `AccessTheWebAsync` is waiting for `GetStringAsync`.</span></span>  
  
7.  <span data-ttu-id="a3cf7-183">`GetStringAsync` 完成并生成一个字符串结果。</span><span class="sxs-lookup"><span data-stu-id="a3cf7-183">`GetStringAsync` completes and produces a string result.</span></span> <span data-ttu-id="a3cf7-184">字符串结果不是通过按你预期的方式调用 `GetStringAsync` 所返回的。</span><span class="sxs-lookup"><span data-stu-id="a3cf7-184">The string result isn't returned by the call to `GetStringAsync` in the way that you might expect.</span></span> <span data-ttu-id="a3cf7-185">（记住，该方法已返回步骤 3 中的一个任务）。相反，字符串结果存储在表示 `getStringTask` 方法完成的任务中。</span><span class="sxs-lookup"><span data-stu-id="a3cf7-185">(Remember that the method already returned a task in step 3.) Instead, the string result is stored in the task that represents the completion of the method, `getStringTask`.</span></span> <span data-ttu-id="a3cf7-186">await 运算符从 `getStringTask` 中检索结果。</span><span class="sxs-lookup"><span data-stu-id="a3cf7-186">The await operator retrieves the result from `getStringTask`.</span></span> <span data-ttu-id="a3cf7-187">赋值语句将检索到的结果赋给 `urlContents`。</span><span class="sxs-lookup"><span data-stu-id="a3cf7-187">The assignment statement assigns the retrieved result to `urlContents`.</span></span>  
  
8.  <span data-ttu-id="a3cf7-188">当 `AccessTheWebAsync` 具有字符串结果时，该方法可以计算字符串长度。</span><span class="sxs-lookup"><span data-stu-id="a3cf7-188">When `AccessTheWebAsync` has the string result, the method can calculate the length of the string.</span></span> <span data-ttu-id="a3cf7-189">然后，`AccessTheWebAsync` 工作也将完成，并且等待事件处理程序可继续使用。</span><span class="sxs-lookup"><span data-stu-id="a3cf7-189">Then the work of `AccessTheWebAsync` is also complete, and the waiting event handler can resume.</span></span> <span data-ttu-id="a3cf7-190">在此主题结尾处的完整示例中，可确认事件处理程序检索并打印长度结果的值。</span><span class="sxs-lookup"><span data-stu-id="a3cf7-190">In the full example at the end of the topic, you can confirm that the event handler retrieves and prints the value of the length result.</span></span>    
<span data-ttu-id="a3cf7-191">如果你不熟悉异步编程，请花 1 分钟时间考虑同步行为和异步行为之间的差异。</span><span class="sxs-lookup"><span data-stu-id="a3cf7-191">If you are new to asynchronous programming, take a minute to consider the difference between synchronous and asynchronous behavior.</span></span> <span data-ttu-id="a3cf7-192">当其工作完成时（第 5 步）会返回一个同步方法，但当其工作挂起时（第 3 步和第 6 步），异步方法会返回一个任务值。</span><span class="sxs-lookup"><span data-stu-id="a3cf7-192">A synchronous method returns when its work is complete (step 5), but an async method returns a task value when its work is suspended (steps 3 and 6).</span></span> <span data-ttu-id="a3cf7-193">在异步方法最终完成其工作时，任务会标记为已完成，而结果（如果有）将存储在任务中。</span><span class="sxs-lookup"><span data-stu-id="a3cf7-193">When the async method eventually completes its work, the task is marked as completed and the result, if any, is stored in the task.</span></span>  
  
<span data-ttu-id="a3cf7-194">若要详细了解控制流，请参阅[异步程序中的控制流 (C#)](../../../../csharp/programming-guide/concepts/async/control-flow-in-async-programs.md)。</span><span class="sxs-lookup"><span data-stu-id="a3cf7-194">For more information about control flow, see [Control Flow in Async Programs (C#)](../../../../csharp/programming-guide/concepts/async/control-flow-in-async-programs.md).</span></span>  
  
##  <a name="BKMK_APIAsyncMethods"></a> <span data-ttu-id="a3cf7-195">API 异步方法</span><span class="sxs-lookup"><span data-stu-id="a3cf7-195">API async methods</span></span>  
 <span data-ttu-id="a3cf7-196">你可能想知道从何处可以找到 `GetStringAsync` 等支持异步编程的方法。</span><span class="sxs-lookup"><span data-stu-id="a3cf7-196">You might be wondering where to find methods such as `GetStringAsync` that support async programming.</span></span> <span data-ttu-id="a3cf7-197">.NET Framework 4.5 或更高版本以及 .NET Core 包含许多可与 `async` 和 `await` 结合使用的成员。</span><span class="sxs-lookup"><span data-stu-id="a3cf7-197">The  .NET Framework 4.5 or higher and .NET Core contain many members that work with `async` and `await`.</span></span> <span data-ttu-id="a3cf7-198">可以通过追加到成员名称的“Async”后缀和 <xref:System.Threading.Tasks.Task> 或 <xref:System.Threading.Tasks.Task%601> 的返回类型，识别这些成员。</span><span class="sxs-lookup"><span data-stu-id="a3cf7-198">You can recognize them by the "Async" suffix that’s appended to the member name, and by their return type of <xref:System.Threading.Tasks.Task> or <xref:System.Threading.Tasks.Task%601>.</span></span> <span data-ttu-id="a3cf7-199">例如，`System.IO.Stream` 类包含 <xref:System.IO.Stream.CopyToAsync%2A>、<xref:System.IO.Stream.ReadAsync%2A> 和 <xref:System.IO.Stream.WriteAsync%2A> 等方法，以及同步方法 <xref:System.IO.Stream.CopyTo%2A>、<xref:System.IO.Stream.Read%2A> 和 <xref:System.IO.Stream.Write%2A>。</span><span class="sxs-lookup"><span data-stu-id="a3cf7-199">For example, the `System.IO.Stream` class contains methods such as <xref:System.IO.Stream.CopyToAsync%2A>, <xref:System.IO.Stream.ReadAsync%2A>, and <xref:System.IO.Stream.WriteAsync%2A> alongside the synchronous methods <xref:System.IO.Stream.CopyTo%2A>, <xref:System.IO.Stream.Read%2A>, and <xref:System.IO.Stream.Write%2A>.</span></span>  
  
 <span data-ttu-id="a3cf7-200">Windows 运行时也包含许多可以在 Windows 应用中与 `async` 和 `await` 结合使用的方法。</span><span class="sxs-lookup"><span data-stu-id="a3cf7-200">The Windows Runtime also contains many methods that you can use with `async` and `await` in Windows apps.</span></span> <span data-ttu-id="a3cf7-201">有关详细信息，请参阅有关 UWP 开发的[线程处理和异步编程](/windows/uwp/threading-async/)，以及[异步编程（Windows 应用商店应用）](/previous-versions/windows/apps/hh464924(v=win.10))和[快速入门：将 await 运算符用于异步编程](/previous-versions/windows/apps/hh452713(v=win.10))（前提是你使用早期版本的 Windows 运行时）。</span><span class="sxs-lookup"><span data-stu-id="a3cf7-201">For more information, see [Threading and async programming](/windows/uwp/threading-async/) for UWP development, and [Asynchronous programming (Windows Store apps)](/previous-versions/windows/apps/hh464924(v=win.10)) and [Quickstart: using the await operator for asynchronous programming](/previous-versions/windows/apps/hh452713(v=win.10)) if you use earlier versions of the Windows Runtime.</span></span>  
  
##  <a name="BKMK_Threads"></a><span data-ttu-id="a3cf7-202">线程</span><span class="sxs-lookup"><span data-stu-id="a3cf7-202">Threads</span></span>  
<span data-ttu-id="a3cf7-203">异步方法旨在成为非阻止操作。</span><span class="sxs-lookup"><span data-stu-id="a3cf7-203">Async methods are intended to be non-blocking operations.</span></span> <span data-ttu-id="a3cf7-204">异步方法中的 `await` 表达式在等待的任务正在运行时不会阻止当前线程。</span><span class="sxs-lookup"><span data-stu-id="a3cf7-204">An `await` expression in an async method doesn’t block the current thread while the awaited task is running.</span></span> <span data-ttu-id="a3cf7-205">相反，表达式在继续时注册方法的其余部分并将控件返回到异步方法的调用方。</span><span class="sxs-lookup"><span data-stu-id="a3cf7-205">Instead, the expression signs up the rest of the method as a continuation and returns control to the caller of the async method.</span></span>  
  
<span data-ttu-id="a3cf7-206">`async` 和 `await` 关键字不会创建其他线程。</span><span class="sxs-lookup"><span data-stu-id="a3cf7-206">The `async` and `await` keywords don't cause additional threads to be created.</span></span> <span data-ttu-id="a3cf7-207">因为异步方法不会在其自身线程上运行，因此它不需要多线程。</span><span class="sxs-lookup"><span data-stu-id="a3cf7-207">Async methods don't require multithreading because an async method doesn't run on its own thread.</span></span> <span data-ttu-id="a3cf7-208">只有当方法处于活动状态时，该方法将在当前同步上下文中运行并使用线程上的时间。</span><span class="sxs-lookup"><span data-stu-id="a3cf7-208">The method runs on the current synchronization context and uses time on the thread only when the method is active.</span></span> <span data-ttu-id="a3cf7-209">可以使用 <xref:System.Threading.Tasks.Task.Run%2A?displayProperty=nameWithType> 将占用大量 CPU 的工作移到后台线程，但是后台线程不会帮助正在等待结果的进程变为可用状态。</span><span class="sxs-lookup"><span data-stu-id="a3cf7-209">You can use <xref:System.Threading.Tasks.Task.Run%2A?displayProperty=nameWithType> to move CPU-bound work to a background thread, but a background thread doesn't help with a process that's just waiting for results to become available.</span></span>  
  
<span data-ttu-id="a3cf7-210">对于异步编程而言，该基于异步的方法优于几乎每个用例中的现有方法。</span><span class="sxs-lookup"><span data-stu-id="a3cf7-210">The async-based approach to asynchronous programming is preferable to existing approaches in almost every case.</span></span> <span data-ttu-id="a3cf7-211">具体而言，此方法比 <xref:System.ComponentModel.BackgroundWorker> 类更适用于 IO 绑定操作，因为此代码更简单且无需防止争用条件。</span><span class="sxs-lookup"><span data-stu-id="a3cf7-211">In particular, this approach is better than the <xref:System.ComponentModel.BackgroundWorker> class for IO-bound operations because the code is simpler and you don't have to guard against race conditions.</span></span> <span data-ttu-id="a3cf7-212">结合 <xref:System.Threading.Tasks.Task.Run%2A?displayProperty=nameWithType> 方法使用时，异步编程比 <xref:System.ComponentModel.BackgroundWorker> 更适用于 CPU 绑定操作，因为异步编程将运行代码的协调细节与 `Task.Run` 传输至线程池的工作区分开来。</span><span class="sxs-lookup"><span data-stu-id="a3cf7-212">In combination with the <xref:System.Threading.Tasks.Task.Run%2A?displayProperty=nameWithType> method, async programming is better than <xref:System.ComponentModel.BackgroundWorker> for CPU-bound operations because async programming separates the coordination details of running your code from the work that `Task.Run` transfers to the threadpool.</span></span>  
  
##  <a name="BKMK_AsyncandAwait"></a><span data-ttu-id="a3cf7-213">async 和 await</span><span class="sxs-lookup"><span data-stu-id="a3cf7-213">async and await</span></span>  
 <span data-ttu-id="a3cf7-214">如果使用 [async](../../../../csharp/language-reference/keywords/async.md) 修饰符将某种方法指定为异步方法，即启用以下两种功能。</span><span class="sxs-lookup"><span data-stu-id="a3cf7-214">If you specify that a method is an async method by using the [async](../../../../csharp/language-reference/keywords/async.md) modifier, you enable the following two capabilities.</span></span>  
  
-   <span data-ttu-id="a3cf7-215">标记的异步方法可以使用 [await](../../../../csharp/language-reference/keywords/await.md) 来指定暂停点。</span><span class="sxs-lookup"><span data-stu-id="a3cf7-215">The marked async method can use [await](../../../../csharp/language-reference/keywords/await.md) to designate suspension points.</span></span> <span data-ttu-id="a3cf7-216">`await` 运算符通知编译器异步方法：在等待的异步过程完成后才能继续通过该点。</span><span class="sxs-lookup"><span data-stu-id="a3cf7-216">The `await` operator tells the compiler that the async method can't continue past that point until the awaited asynchronous process is complete.</span></span> <span data-ttu-id="a3cf7-217">同时，控件返回至异步方法的调用方。</span><span class="sxs-lookup"><span data-stu-id="a3cf7-217">In the meantime, control returns to the caller of the async method.</span></span>  
  
     <span data-ttu-id="a3cf7-218">异步方法在 `await` 表达式执行时暂停并不构成方法退出，只会导致 `finally` 代码块不运行。</span><span class="sxs-lookup"><span data-stu-id="a3cf7-218">The suspension of an async method at an `await` expression doesn't constitute an exit from the method, and `finally` blocks don’t run.</span></span>  
  
-   <span data-ttu-id="a3cf7-219">标记的异步方法本身可以通过调用它的方法等待。</span><span class="sxs-lookup"><span data-stu-id="a3cf7-219">The marked async method can itself be awaited by methods that call it.</span></span>  
  
<span data-ttu-id="a3cf7-220">异步方法通常包含 `await` 运算符的一个或多个实例，但缺少 `await` 表达式也不会导致生成编译器错误。</span><span class="sxs-lookup"><span data-stu-id="a3cf7-220">An async method typically contains one or more occurrences of an `await` operator, but the absence of `await` expressions doesn’t cause a compiler error.</span></span> <span data-ttu-id="a3cf7-221">如果异步方法未使用 `await` 运算符标记暂停点，那么异步方法会作为同步方法执行，即使有 `async` 修饰符，也不例外。</span><span class="sxs-lookup"><span data-stu-id="a3cf7-221">If an async method doesn’t use an `await` operator to mark a suspension point, the method executes as a synchronous method does, despite the `async` modifier.</span></span> <span data-ttu-id="a3cf7-222">编译器将为此类方法发布一个警告。</span><span class="sxs-lookup"><span data-stu-id="a3cf7-222">The compiler issues a warning for such methods.</span></span>  
  
 <span data-ttu-id="a3cf7-223">`async` 和 `await` 都是上下文关键字。</span><span class="sxs-lookup"><span data-stu-id="a3cf7-223">`async` and `await` are contextual keywords.</span></span> <span data-ttu-id="a3cf7-224">有关更多信息和示例，请参见以下主题：</span><span class="sxs-lookup"><span data-stu-id="a3cf7-224">For more information and examples, see the following topics:</span></span>  
  
-   [<span data-ttu-id="a3cf7-225">async</span><span class="sxs-lookup"><span data-stu-id="a3cf7-225">async</span></span>](../../../../csharp/language-reference/keywords/async.md)  
  
-   [<span data-ttu-id="a3cf7-226">await</span><span class="sxs-lookup"><span data-stu-id="a3cf7-226">await</span></span>](../../../../csharp/language-reference/keywords/await.md)  
  
##  <a name="BKMK_ReturnTypesandParameters"></a> <span data-ttu-id="a3cf7-227">返回类型和参数</span><span class="sxs-lookup"><span data-stu-id="a3cf7-227">Return types and parameters</span></span>  
<span data-ttu-id="a3cf7-228">异步方法通常返回 <xref:System.Threading.Tasks.Task> 或 <xref:System.Threading.Tasks.Task%601>。</span><span class="sxs-lookup"><span data-stu-id="a3cf7-228">An async method typically returns a <xref:System.Threading.Tasks.Task> or a <xref:System.Threading.Tasks.Task%601>.</span></span> <span data-ttu-id="a3cf7-229">在异步方法中，`await` 运算符应用于通过调用另一个异步方法返回的任务。</span><span class="sxs-lookup"><span data-stu-id="a3cf7-229">Inside an async method, an `await` operator is applied to a task that's returned from a call to another async method.</span></span>  
  
<span data-ttu-id="a3cf7-230">如果方法包含指定 `TResult` 类型操作数的 [return](../../../../csharp/language-reference/keywords/return.md) 语句，将 <xref:System.Threading.Tasks.Task%601> 指定为返回类型。</span><span class="sxs-lookup"><span data-stu-id="a3cf7-230">You specify <xref:System.Threading.Tasks.Task%601> as the return type if the method contains a [return](../../../../csharp/language-reference/keywords/return.md) statement that specifies an operand of type `TResult`.</span></span> 
  
<span data-ttu-id="a3cf7-231">如果方法不含任何 return 语句或包含不返回操作数的 return 语句，将 <xref:System.Threading.Tasks.Task> 用作返回类型。</span><span class="sxs-lookup"><span data-stu-id="a3cf7-231">You use <xref:System.Threading.Tasks.Task>  as the return type if the method has no return statement or has a return statement that doesn't return an operand.</span></span>  

<span data-ttu-id="a3cf7-232">自 C# 7 起，还可以指定其他任何返回类型，前提是返回类型包含 `GetAwaiter` 方法。</span><span class="sxs-lookup"><span data-stu-id="a3cf7-232">Starting with C# 7, you can also specify any other return type, provided that that type includes a `GetAwaiter` method.</span></span> <span data-ttu-id="a3cf7-233">例如，<xref:System.Threading.Tasks.ValueTask%601> 就是这种类型。</span><span class="sxs-lookup"><span data-stu-id="a3cf7-233"><xref:System.Threading.Tasks.ValueTask%601> is an example of such a type.</span></span> <span data-ttu-id="a3cf7-234">可用于 [System.Threading.Tasks.Extension](https://www.nuget.org/packages/System.Threading.Tasks.Extensions/) NuGet 包。</span><span class="sxs-lookup"><span data-stu-id="a3cf7-234">It is available in the [System.Threading.Tasks.Extension](https://www.nuget.org/packages/System.Threading.Tasks.Extensions/) NuGet package.</span></span>
  
 <span data-ttu-id="a3cf7-235">下面的示例演示如何声明并调用可返回 <xref:System.Threading.Tasks.Task%601> 或 <xref:System.Threading.Tasks.Task> 的方法。</span><span class="sxs-lookup"><span data-stu-id="a3cf7-235">The following example shows how you declare and call a method that returns a <xref:System.Threading.Tasks.Task%601> or a <xref:System.Threading.Tasks.Task>.</span></span>  
  
```csharp  
// Signature specifies Task<TResult>  
async Task<int> TaskOfTResult_MethodAsync()  
{  
    int hours;  
    // . . .  
    // Return statement specifies an integer result.  
    return hours;  
}  
  
// Calls to TaskOfTResult_MethodAsync  
Task<int> returnedTaskTResult = TaskOfTResult_MethodAsync();  
int intResult = await returnedTaskTResult;  
// or, in a single statement  
int intResult = await TaskOfTResult_MethodAsync();  
  
// Signature specifies Task  
async Task Task_MethodAsync()  
{  
    // . . .  
    // The method has no return statement.    
}  
  
// Calls to Task_MethodAsync  
Task returnedTask = Task_MethodAsync();  
await returnedTask;  
// or, in a single statement  
await Task_MethodAsync();  
```  
  
<span data-ttu-id="a3cf7-236">每个返回的任务表示正在进行的工作。</span><span class="sxs-lookup"><span data-stu-id="a3cf7-236">Each returned task represents ongoing work.</span></span> <span data-ttu-id="a3cf7-237">任务可封装有关异步进程状态的信息，如果未成功，则最后会封装来自进程的最终结果或进程引发的异常。</span><span class="sxs-lookup"><span data-stu-id="a3cf7-237">A task encapsulates information about the state of the asynchronous process and, eventually, either the final result from the process or the exception that the process raises if it doesn't succeed.</span></span>  
  
<span data-ttu-id="a3cf7-238">异步方法也可以具有 `void` 返回类型。</span><span class="sxs-lookup"><span data-stu-id="a3cf7-238">An async method can also have a `void` return type.</span></span> <span data-ttu-id="a3cf7-239">该返回类型主要用于定义需要 `void` 返回类型的事件处理程序。</span><span class="sxs-lookup"><span data-stu-id="a3cf7-239">This return type is used primarily to define event handlers, where a `void` return type is required.</span></span> <span data-ttu-id="a3cf7-240">异步事件处理程序通常用作异步程序的起始点。</span><span class="sxs-lookup"><span data-stu-id="a3cf7-240">Async event handlers often serve as the starting point for async programs.</span></span>  
  
<span data-ttu-id="a3cf7-241">无法等待具有 `void` 返回类型的异步方法，并且无效返回方法的调用方捕获不到异步方法抛出的任何异常。</span><span class="sxs-lookup"><span data-stu-id="a3cf7-241">An async method that has a `void` return type can’t be awaited, and the caller of a void-returning method can't catch any exceptions that the method throws.</span></span>  
  
<span data-ttu-id="a3cf7-242">异步方法无法声明 [ref](../../../../csharp/language-reference/keywords/ref.md) 或 [out](../../../../csharp/language-reference/keywords/out.md) 参数，但可以调用包含此类参数的方法。</span><span class="sxs-lookup"><span data-stu-id="a3cf7-242">An async method can't declare [ref](../../../../csharp/language-reference/keywords/ref.md) or [out](../../../../csharp/language-reference/keywords/out.md) parameters, but the method can call methods that have such parameters.</span></span> <span data-ttu-id="a3cf7-243">同样，异步方法无法通过引用返回值，但可以调用包含 ref 返回值的方法。</span><span class="sxs-lookup"><span data-stu-id="a3cf7-243">Similarly, an async method can't return a value by reference, although it can call methods with ref return values.</span></span> 
  
<span data-ttu-id="a3cf7-244">有关详细信息和示例，请参阅[异步返回类型 (C#)](../../../../csharp/programming-guide/concepts/async/async-return-types.md)。</span><span class="sxs-lookup"><span data-stu-id="a3cf7-244">For more information and examples, see [Async Return Types (C#)](../../../../csharp/programming-guide/concepts/async/async-return-types.md).</span></span> <span data-ttu-id="a3cf7-245">若要详细了解如何在异步方法中捕获异常，请参阅 [try-catch](../../../../csharp/language-reference/keywords/try-catch.md)。</span><span class="sxs-lookup"><span data-stu-id="a3cf7-245">For more information about how to catch exceptions in async methods, see [try-catch](../../../../csharp/language-reference/keywords/try-catch.md).</span></span> 
  
<span data-ttu-id="a3cf7-246">Windows 运行时编程中的异步 API 具有下列返回类型之一（类似于任务）：</span><span class="sxs-lookup"><span data-stu-id="a3cf7-246">Asynchronous APIs in Windows Runtime programming have one of the following return types, which are similar to tasks:</span></span>  
  
-   <span data-ttu-id="a3cf7-247"><xref:Windows.Foundation.IAsyncOperation%601>（对应于 <xref:System.Threading.Tasks.Task%601>）</span><span class="sxs-lookup"><span data-stu-id="a3cf7-247"><xref:Windows.Foundation.IAsyncOperation%601>, which corresponds to <xref:System.Threading.Tasks.Task%601></span></span>  
  
-   <span data-ttu-id="a3cf7-248"><xref:Windows.Foundation.IAsyncAction>（对应于 <xref:System.Threading.Tasks.Task>）</span><span class="sxs-lookup"><span data-stu-id="a3cf7-248"><xref:Windows.Foundation.IAsyncAction>, which corresponds to <xref:System.Threading.Tasks.Task></span></span>  
  
-   <xref:Windows.Foundation.IAsyncActionWithProgress%601>  
  
-   <xref:Windows.Foundation.IAsyncOperationWithProgress%602>  
   
  
##  <a name="BKMK_NamingConvention"></a> <span data-ttu-id="a3cf7-249">命名约定</span><span class="sxs-lookup"><span data-stu-id="a3cf7-249">Naming convention</span></span>  
 <span data-ttu-id="a3cf7-250">按照约定，将“Async”追加到包含 `async` 修饰符的方法的名称中。</span><span class="sxs-lookup"><span data-stu-id="a3cf7-250">By convention, you append "Async" to the names of methods that have an `async` modifier.</span></span>  
  
 <span data-ttu-id="a3cf7-251">如果某一约定中的事件、基类或接口协定建议其他名称，则可以忽略此约定。</span><span class="sxs-lookup"><span data-stu-id="a3cf7-251">You can ignore the convention where an event, base class, or interface contract suggests a different name.</span></span> <span data-ttu-id="a3cf7-252">例如，你不应重命名常用事件处理程序，例如 `Button1_Click`。</span><span class="sxs-lookup"><span data-stu-id="a3cf7-252">For example, you shouldn’t rename common event handlers, such as `Button1_Click`.</span></span>  
  
##  <a name="BKMK_RelatedTopics"></a> <span data-ttu-id="a3cf7-253">相关主题和示例 (Visual Studio)</span><span class="sxs-lookup"><span data-stu-id="a3cf7-253">Related topics and samples (Visual Studio)</span></span>  
  
|<span data-ttu-id="a3cf7-254">标题</span><span class="sxs-lookup"><span data-stu-id="a3cf7-254">Title</span></span>|<span data-ttu-id="a3cf7-255">描述</span><span class="sxs-lookup"><span data-stu-id="a3cf7-255">Description</span></span>|<span data-ttu-id="a3cf7-256">示例</span><span class="sxs-lookup"><span data-stu-id="a3cf7-256">Sample</span></span>|  
|-----------|-----------------|------------|  
|[<span data-ttu-id="a3cf7-257">演练：使用 Async 和 Await 访问 Web (C#)</span><span class="sxs-lookup"><span data-stu-id="a3cf7-257">Walkthrough: Accessing the Web by Using async and await (C#)</span></span>](../../../../csharp/programming-guide/concepts/async/walkthrough-accessing-the-web-by-using-async-and-await.md)|<span data-ttu-id="a3cf7-258">演示如何将一个同步 WPF 解决方案转换成一个异步 WPF 解决方案。</span><span class="sxs-lookup"><span data-stu-id="a3cf7-258">Shows how to convert a synchronous WPF solution to an asynchronous WPF solution.</span></span> <span data-ttu-id="a3cf7-259">应用程序下载一系列网站。</span><span class="sxs-lookup"><span data-stu-id="a3cf7-259">The application downloads a series of websites.</span></span>|[<span data-ttu-id="a3cf7-260">异步示例：“访问 Web”演练</span><span class="sxs-lookup"><span data-stu-id="a3cf7-260">Async Sample: Accessing the Web Walkthrough</span></span>](https://code.msdn.microsoft.com/Async-Sample-Accessing-the-9c10497f)|  
|[<span data-ttu-id="a3cf7-261">如何：使用 Task.WhenAll 扩展异步演练 (C#)</span><span class="sxs-lookup"><span data-stu-id="a3cf7-261">How to: Extend the async Walkthrough by Using Task.WhenAll (C#)</span></span>](../../../../csharp/programming-guide/concepts/async/how-to-extend-the-async-walkthrough-by-using-task-whenall.md)|<span data-ttu-id="a3cf7-262">将 <xref:System.Threading.Tasks.Task.WhenAll%2A?displayProperty=nameWithType> 添加到上一个演练。</span><span class="sxs-lookup"><span data-stu-id="a3cf7-262">Adds <xref:System.Threading.Tasks.Task.WhenAll%2A?displayProperty=nameWithType> to the previous walkthrough.</span></span> <span data-ttu-id="a3cf7-263">使用 `WhenAll` 同时启动所有下载。</span><span class="sxs-lookup"><span data-stu-id="a3cf7-263">The use of `WhenAll` starts all the downloads at the same time.</span></span>||  
|[<span data-ttu-id="a3cf7-264">如何：使用 Async 和 Await 并行发出多个 Web 请求 (C#)</span><span class="sxs-lookup"><span data-stu-id="a3cf7-264">How to: Make Multiple Web Requests in Parallel by Using async and await (C#)</span></span>](../../../../csharp/programming-guide/concepts/async/how-to-make-multiple-web-requests-in-parallel-by-using-async-and-await.md)|<span data-ttu-id="a3cf7-265">演示如何同时开始几个任务。</span><span class="sxs-lookup"><span data-stu-id="a3cf7-265">Demonstrates how to start several tasks at the same time.</span></span>|[<span data-ttu-id="a3cf7-266">异步示例：并行发出多个 Web 请求</span><span class="sxs-lookup"><span data-stu-id="a3cf7-266">Async Sample: Make Multiple Web Requests in Parallel</span></span>](https://code.msdn.microsoft.com/Async-Make-Multiple-Web-49adb82e)|  
|[<span data-ttu-id="a3cf7-267">异步返回类型 (C#)</span><span class="sxs-lookup"><span data-stu-id="a3cf7-267">Async Return Types (C#)</span></span>](../../../../csharp/programming-guide/concepts/async/async-return-types.md)|<span data-ttu-id="a3cf7-268">描述异步方法可返回的类型，并解释每种类型适用于的情况。</span><span class="sxs-lookup"><span data-stu-id="a3cf7-268">Illustrates the types that async methods can return and explains when each type is appropriate.</span></span>||  
|[<span data-ttu-id="a3cf7-269">异步程序中的控制流 (C#)</span><span class="sxs-lookup"><span data-stu-id="a3cf7-269">Control Flow in Async Programs (C#)</span></span>](../../../../csharp/programming-guide/concepts/async/control-flow-in-async-programs.md)|<span data-ttu-id="a3cf7-270">通过异步程序中的一系列 await 表达式来详细跟踪控制流。</span><span class="sxs-lookup"><span data-stu-id="a3cf7-270">Traces in detail the flow of control through a succession of await expressions in an asynchronous program.</span></span>|[<span data-ttu-id="a3cf7-271">异步示例：异步程序中的控制流</span><span class="sxs-lookup"><span data-stu-id="a3cf7-271">Async Sample: Control Flow in Async Programs</span></span>](https://code.msdn.microsoft.com/Async-Sample-Control-Flow-5c804fc0)|  
|[<span data-ttu-id="a3cf7-272">微调异步应用程序 (C#)</span><span class="sxs-lookup"><span data-stu-id="a3cf7-272">Fine-Tuning Your Async Application (C#)</span></span>](../../../../csharp/programming-guide/concepts/async/fine-tuning-your-async-application.md)|<span data-ttu-id="a3cf7-273">演示如何将以下功能添加到异步解决方案：</span><span class="sxs-lookup"><span data-stu-id="a3cf7-273">Shows how to add the following functionality to your async solution:</span></span><br /><br /> <span data-ttu-id="a3cf7-274">-   [取消一个异步任务或一组任务(C#)](../../../../csharp/programming-guide/concepts/async/cancel-an-async-task-or-a-list-of-tasks.md)</span><span class="sxs-lookup"><span data-stu-id="a3cf7-274">-   [Cancel an Async Task or a List of Tasks (C#)](../../../../csharp/programming-guide/concepts/async/cancel-an-async-task-or-a-list-of-tasks.md)</span></span><br /><span data-ttu-id="a3cf7-275">-   [在一段时间后取消异步任务 (C#)](../../../../csharp/programming-guide/concepts/async/cancel-async-tasks-after-a-period-of-time.md)</span><span class="sxs-lookup"><span data-stu-id="a3cf7-275">-   [Cancel Async Tasks after a Period of Time (C#)](../../../../csharp/programming-guide/concepts/async/cancel-async-tasks-after-a-period-of-time.md)</span></span><br /><span data-ttu-id="a3cf7-276">-   [在完成一个异步任务后取消剩余任务 (C#)](../../../../csharp/programming-guide/concepts/async/cancel-remaining-async-tasks-after-one-is-complete.md)</span><span class="sxs-lookup"><span data-stu-id="a3cf7-276">-   [Cancel Remaining Async Tasks after One Is Complete (C#)](../../../../csharp/programming-guide/concepts/async/cancel-remaining-async-tasks-after-one-is-complete.md)</span></span><br /><span data-ttu-id="a3cf7-277">-   [启动多个异步任务并在其完成时进行处理 (C#)](../../../../csharp/programming-guide/concepts/async/start-multiple-async-tasks-and-process-them-as-they-complete.md)</span><span class="sxs-lookup"><span data-stu-id="a3cf7-277">-   [Start Multiple Async Tasks and Process Them As They Complete (C#)](../../../../csharp/programming-guide/concepts/async/start-multiple-async-tasks-and-process-them-as-they-complete.md)</span></span>|[<span data-ttu-id="a3cf7-278">异步示例：微调应用程序</span><span class="sxs-lookup"><span data-stu-id="a3cf7-278">Async Sample: Fine Tuning Your Application</span></span>](https://code.msdn.microsoft.com/Async-Fine-Tuning-Your-a676abea)|  
|[<span data-ttu-id="a3cf7-279">在异步应用程序中处理重入 (C#)</span><span class="sxs-lookup"><span data-stu-id="a3cf7-279">Handling Reentrancy in Async Apps (C#)</span></span>](../../../../csharp/programming-guide/concepts/async/handling-reentrancy-in-async-apps.md)|<span data-ttu-id="a3cf7-280">演示如何处理有效的异步操作在运行时重启的情况。</span><span class="sxs-lookup"><span data-stu-id="a3cf7-280">Shows how to handle cases in which an active asynchronous operation is restarted while it’s running.</span></span>||  
|<span data-ttu-id="a3cf7-281">[WhenAny：.NET Framework 和 Windows 运行时之间的桥接](https://msdn.microsoft.com/library/jj635140(v=vs.120).aspx)</span><span class="sxs-lookup"><span data-stu-id="a3cf7-281">[WhenAny: Bridging between the .NET Framework and the Windows Runtime](https://msdn.microsoft.com/library/jj635140(v=vs.120).aspx)</span></span>|<span data-ttu-id="a3cf7-282">展示了如何桥接 .NET Framework 与 [!INCLUDE[wrt](~/includes/wrt-md.md)]中 IAsyncOperations 的任务类型，以便可以将 <xref:System.Threading.Tasks.Task.WhenAny%2A> 与 [!INCLUDE[wrt](~/includes/wrt-md.md)] 方法结合使用。</span><span class="sxs-lookup"><span data-stu-id="a3cf7-282">Shows how to bridge between Task types in the .NET Framework and IAsyncOperations in the [!INCLUDE[wrt](~/includes/wrt-md.md)] so that you can use <xref:System.Threading.Tasks.Task.WhenAny%2A> with a [!INCLUDE[wrt](~/includes/wrt-md.md)] method.</span></span>|[<span data-ttu-id="a3cf7-283">异步示例：桥接 .NET 和 Windows 运行时（AsTask 和 WhenAny）</span><span class="sxs-lookup"><span data-stu-id="a3cf7-283">Async Sample: Bridging between .NET and Windows Runtime (AsTask and WhenAny)</span></span>](https://code.msdn.microsoft.com/Async-Sample-Bridging-d6a2f739)|  
|<span data-ttu-id="a3cf7-284">异步取消：.NET Framework 和 Windows 运行时之间的桥接</span><span class="sxs-lookup"><span data-stu-id="a3cf7-284">Async Cancellation: Bridging between the .NET Framework and the Windows Runtime</span></span>|<span data-ttu-id="a3cf7-285">展示了如何桥接 .NET Framework 与 [!INCLUDE[wrt](~/includes/wrt-md.md)]中 IAsyncOperations 的任务类型，以便可以将 <xref:System.Threading.CancellationTokenSource> 与 [!INCLUDE[wrt](~/includes/wrt-md.md)] 方法结合使用。</span><span class="sxs-lookup"><span data-stu-id="a3cf7-285">Shows how to bridge between Task types in the .NET Framework and IAsyncOperations in the [!INCLUDE[wrt](~/includes/wrt-md.md)] so that you can use <xref:System.Threading.CancellationTokenSource> with a [!INCLUDE[wrt](~/includes/wrt-md.md)] method.</span></span>|[<span data-ttu-id="a3cf7-286">异步示例：桥接 .NET 和 Windows 运行时（AsTask 和 Cancellation）</span><span class="sxs-lookup"><span data-stu-id="a3cf7-286">Async Sample: Bridging between .NET and Windows Runtime (AsTask & Cancellation)</span></span>](https://code.msdn.microsoft.com/Async-Sample-Bridging-9479eca3)|  
|[<span data-ttu-id="a3cf7-287">使用 Async 进行文件访问 (C#)</span><span class="sxs-lookup"><span data-stu-id="a3cf7-287">Using Async for File Access (C#)</span></span>](../../../../csharp/programming-guide/concepts/async/using-async-for-file-access.md)|<span data-ttu-id="a3cf7-288">列出并演示使用 async 和 await 访问文件的好处。</span><span class="sxs-lookup"><span data-stu-id="a3cf7-288">Lists and demonstrates the benefits of using async and await to access files.</span></span>||  
|[<span data-ttu-id="a3cf7-289">基于任务的异步模式 (TAP)</span><span class="sxs-lookup"><span data-stu-id="a3cf7-289">Task-based Asynchronous Pattern (TAP)</span></span>](../../../../standard/asynchronous-programming-patterns/task-based-asynchronous-pattern-tap.md)|<span data-ttu-id="a3cf7-290">描述 .NET Framework 中异步的新模式。</span><span class="sxs-lookup"><span data-stu-id="a3cf7-290">Describes a new pattern for asynchrony in the .NET Framework.</span></span> <span data-ttu-id="a3cf7-291">该模式基于 <xref:System.Threading.Tasks.Task> 和 <xref:System.Threading.Tasks.Task%601> 类型。</span><span class="sxs-lookup"><span data-stu-id="a3cf7-291">The pattern is based on the <xref:System.Threading.Tasks.Task> and <xref:System.Threading.Tasks.Task%601> types.</span></span>||  
|[<span data-ttu-id="a3cf7-292">Channel 9 上的异步相关视频</span><span class="sxs-lookup"><span data-stu-id="a3cf7-292">Async Videos on Channel 9</span></span>](https://channel9.msdn.com/search?term=async%20&type=All#pubDate=year&ch9Search&lang-en=en)|<span data-ttu-id="a3cf7-293">提供指向有关异步编程的各种视频的链接。</span><span class="sxs-lookup"><span data-stu-id="a3cf7-293">Provides links to a variety of videos about async programming.</span></span>||  
  
##  <a name="BKMK_CompleteExample"></a> <span data-ttu-id="a3cf7-294">完整示例</span><span class="sxs-lookup"><span data-stu-id="a3cf7-294">Complete example</span></span>  
 <span data-ttu-id="a3cf7-295">下面的代码来自于本主题介绍的 Windows Presentation Foundation (WPF) 应用程序的 MainWindow.xaml.cs 文件。</span><span class="sxs-lookup"><span data-stu-id="a3cf7-295">The following code is the MainWindow.xaml.cs file from the Windows Presentation Foundation (WPF) application that this topic discusses.</span></span> <span data-ttu-id="a3cf7-296">可以从[异步示例：“使用 Async 和 Await 的异步编程”示例](https://code.msdn.microsoft.com/Async-Sample-Example-from-9b9f505c)下载示例。</span><span class="sxs-lookup"><span data-stu-id="a3cf7-296">You can download the sample from [Async Sample: Example from "Asynchronous Programming with Async and Await"](https://code.msdn.microsoft.com/Async-Sample-Example-from-9b9f505c).</span></span>  
  
```csharp  
using System;  
using System.Collections.Generic;  
using System.Linq;  
using System.Text;  
using System.Threading.Tasks;  
using System.Windows;  
using System.Windows.Controls;  
using System.Windows.Data;  
using System.Windows.Documents;  
using System.Windows.Input;  
using System.Windows.Media;  
using System.Windows.Media.Imaging;  
using System.Windows.Navigation;  
using System.Windows.Shapes;  
  
// Add a using directive and a reference for System.Net.Http;  
using System.Net.Http;  
  
namespace AsyncFirstExample  
{  
    public partial class MainWindow : Window  
    {  
        // Mark the event handler with async so you can use await in it.  
        private async void StartButton_Click(object sender, RoutedEventArgs e)  
        {  
            // Call and await separately.  
            //Task<int> getLengthTask = AccessTheWebAsync();  
            //// You can do independent work here.  
            //int contentLength = await getLengthTask;  
  
            int contentLength = await AccessTheWebAsync();  
  
            resultsTextBox.Text +=  
                String.Format("\r\nLength of the downloaded string: {0}.\r\n", contentLength);  
        }  
  
        // Three things to note in the signature:  
        //  - The method has an async modifier.   
        //  - The return type is Task or Task<T>. (See "Return Types" section.)  
        //    Here, it is Task<int> because the return statement returns an integer.  
        //  - The method name ends in "Async."  
        async Task<int> AccessTheWebAsync()  
        {   
            // You need to add a reference to System.Net.Http to declare client.  
            HttpClient client = new HttpClient();  
  
            // GetStringAsync returns a Task<string>. That means that when you await the  
            // task you'll get a string (urlContents).  
            Task<string> getStringTask = client.GetStringAsync("http://msdn.microsoft.com");  
  
            // You can do work here that doesn't rely on the string from GetStringAsync.  
            DoIndependentWork();  
  
            // The await operator suspends AccessTheWebAsync.  
            //  - AccessTheWebAsync can't continue until getStringTask is complete.  
            //  - Meanwhile, control returns to the caller of AccessTheWebAsync.  
            //  - Control resumes here when getStringTask is complete.   
            //  - The await operator then retrieves the string result from getStringTask.  
            string urlContents = await getStringTask;  
  
            // The return statement specifies an integer result.  
            // Any methods that are awaiting AccessTheWebAsync retrieve the length value.  
            return urlContents.Length;  
        }  
  
        void DoIndependentWork()  
        {  
            resultsTextBox.Text += "Working . . . . . . .\r\n";  
        }  
    }  
}  
  
// Sample Output:  
  
// Working . . . . . . .  
  
// Length of the downloaded string: 41564.  
```  
  
## <a name="see-also"></a><span data-ttu-id="a3cf7-297">请参阅</span><span class="sxs-lookup"><span data-stu-id="a3cf7-297">See also</span></span>  
 [<span data-ttu-id="a3cf7-298">async</span><span class="sxs-lookup"><span data-stu-id="a3cf7-298">async</span></span>](../../../../csharp/language-reference/keywords/async.md)  
 [<span data-ttu-id="a3cf7-299">await</span><span class="sxs-lookup"><span data-stu-id="a3cf7-299">await</span></span>](../../../../csharp/language-reference/keywords/await.md)  
 [<span data-ttu-id="a3cf7-300">异步编程</span><span class="sxs-lookup"><span data-stu-id="a3cf7-300">Asynchronous programming</span></span>](../../../../csharp/async.md)  
 [<span data-ttu-id="a3cf7-301">异步概述</span><span class="sxs-lookup"><span data-stu-id="a3cf7-301">Async overview</span></span>](../../../../standard/async.md)  
