---
title: "演练：实现支持基于事件的异步模式的组件"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Event-based Asynchronous Pattern
- ProgressChangedEventArgs class
- BackgroundWorker component
- events [.NET Framework], asynchronous
- Asynchronous Pattern
- AsyncOperationManager class
- threading [.NET Framework], asynchronous features
- components [.NET Framework], asynchronous
- AsyncOperation class
- threading [Windows Forms], asynchronous features
- AsyncCompletedEventArgs class
ms.assetid: 61f676b5-936f-40f6-83ce-f22805ec9c2f
caps.latest.revision: "21"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 150e4b27cc149774895574ddd196de5f9bc2acd8
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="walkthrough-implementing-a-component-that-supports-the-event-based-asynchronous-pattern"></a><span data-ttu-id="77826-102">演练：实现支持基于事件的异步模式的组件</span><span class="sxs-lookup"><span data-stu-id="77826-102">Walkthrough: Implementing a Component That Supports the Event-based Asynchronous Pattern</span></span>
<span data-ttu-id="77826-103">如果你正在编写具有可能导致显著延迟某些操作的类，请考虑通过实现提供异步功能[基于事件的异步模式概述](../../../docs/standard/asynchronous-programming-patterns/event-based-asynchronous-pattern-overview.md)。</span><span class="sxs-lookup"><span data-stu-id="77826-103">If you are writing a class with some operations that may incur noticeable delays, consider giving it asynchronous functionality by implementing the [Event-based Asynchronous Pattern Overview](../../../docs/standard/asynchronous-programming-patterns/event-based-asynchronous-pattern-overview.md).</span></span>  
  
 <span data-ttu-id="77826-104">本演练阐释了如何创建实现基于事件的异步模式的组件。</span><span class="sxs-lookup"><span data-stu-id="77826-104">This walkthrough illustrates how to create a component that implements the Event-based Asynchronous Pattern.</span></span> <span data-ttu-id="77826-105">使用从帮助程序类实现<xref:System.ComponentModel?displayProperty=nameWithType>命名空间，这样可以确保该组件在任何应用程序模型正确工作，包括[!INCLUDE[vstecasp](../../../includes/vstecasp-md.md)]，控制台应用程序和 Windows 窗体应用程序。</span><span class="sxs-lookup"><span data-stu-id="77826-105">It is implemented using helper classes from the <xref:System.ComponentModel?displayProperty=nameWithType> namespace, which ensures that the component works correctly under any application model, including [!INCLUDE[vstecasp](../../../includes/vstecasp-md.md)], Console applications and Windows Forms applications.</span></span> <span data-ttu-id="77826-106">此组件也是可以用<xref:System.Windows.Forms.PropertyGrid>控制和你自己的自定义设计器。</span><span class="sxs-lookup"><span data-stu-id="77826-106">This component is also designable with a <xref:System.Windows.Forms.PropertyGrid> control and your own custom designers.</span></span>  
  
 <span data-ttu-id="77826-107">完成后，你将具有的应用程序以异步方式计算质数。</span><span class="sxs-lookup"><span data-stu-id="77826-107">When you are through, you will have an application that computes prime numbers asynchronously.</span></span> <span data-ttu-id="77826-108">你的应用程序将具有主用户界面 (UI) 线程和每个质数计算的线程。</span><span class="sxs-lookup"><span data-stu-id="77826-108">Your application will have a main user interface (UI) thread and a thread for each prime number calculation.</span></span> <span data-ttu-id="77826-109">虽然测试是否有大量是质数可能需要花费大量的时间、 通过这种延迟，将不会中断的主 UI 线程和窗体将在计算期间保持响应状态。</span><span class="sxs-lookup"><span data-stu-id="77826-109">Although testing whether a large number is prime can take a noticeable amount of time, the main UI thread will not be interrupted by this delay, and the form will be responsive during the calculations.</span></span> <span data-ttu-id="77826-110">你将能够运行，因为许多计算 like 并发并有选择地取消挂起的计算。</span><span class="sxs-lookup"><span data-stu-id="77826-110">You will be able to run as many calculations as you like concurrently and selectively cancel pending calculations.</span></span>  
  
 <span data-ttu-id="77826-111">本演练涉及以下任务：</span><span class="sxs-lookup"><span data-stu-id="77826-111">Tasks illustrated in this walkthrough include:</span></span>  
  
-   <span data-ttu-id="77826-112">创建组件</span><span class="sxs-lookup"><span data-stu-id="77826-112">Creating the Component</span></span>  
  
-   <span data-ttu-id="77826-113">定义公共异步事件和委托</span><span class="sxs-lookup"><span data-stu-id="77826-113">Defining Public Asynchronous Events and Delegates</span></span>  
  
-   <span data-ttu-id="77826-114">定义私有委托</span><span class="sxs-lookup"><span data-stu-id="77826-114">Defining Private Delegates</span></span>  
  
-   <span data-ttu-id="77826-115">实现公共事件</span><span class="sxs-lookup"><span data-stu-id="77826-115">Implementing Public Events</span></span>  
  
-   <span data-ttu-id="77826-116">实现完成方法</span><span class="sxs-lookup"><span data-stu-id="77826-116">Implementing the Completion Method</span></span>  
  
-   <span data-ttu-id="77826-117">实现的辅助方法</span><span class="sxs-lookup"><span data-stu-id="77826-117">Implementing the Worker Methods</span></span>  
  
-   <span data-ttu-id="77826-118">实现启动和取消方法</span><span class="sxs-lookup"><span data-stu-id="77826-118">Implementing Start and Cancel Methods</span></span>  
  
 <span data-ttu-id="77826-119">若要将代码复制本主题中的一个单独的清单，请参阅[如何： 实现支持基于事件的异步模式的组件](../../../docs/standard/asynchronous-programming-patterns/component-that-supports-the-event-based-asynchronous-pattern.md)。</span><span class="sxs-lookup"><span data-stu-id="77826-119">To copy the code in this topic as a single listing, see [How to: Implement a Component That Supports the Event-based Asynchronous Pattern](../../../docs/standard/asynchronous-programming-patterns/component-that-supports-the-event-based-asynchronous-pattern.md).</span></span>  
  
## <a name="creating-the-component"></a><span data-ttu-id="77826-120">创建组件</span><span class="sxs-lookup"><span data-stu-id="77826-120">Creating the Component</span></span>  
 <span data-ttu-id="77826-121">第一步是创建将实现基于事件的异步模式的组件。</span><span class="sxs-lookup"><span data-stu-id="77826-121">The first step is to create the component that will implement the Event-based Asynchronous Pattern.</span></span>  
  
#### <a name="to-create-the-component"></a><span data-ttu-id="77826-122">要创建的组件</span><span class="sxs-lookup"><span data-stu-id="77826-122">To create the component</span></span>  
  
-   <span data-ttu-id="77826-123">创建一个名为类`PrimeNumberCalculator`继承自<xref:System.ComponentModel.Component>。</span><span class="sxs-lookup"><span data-stu-id="77826-123">Create a class called `PrimeNumberCalculator` that inherits from <xref:System.ComponentModel.Component>.</span></span>  
  
## <a name="defining-public-asynchronous-events-and-delegates"></a><span data-ttu-id="77826-124">定义公共异步事件和委托</span><span class="sxs-lookup"><span data-stu-id="77826-124">Defining Public Asynchronous Events and Delegates</span></span>  
 <span data-ttu-id="77826-125">你的组件进行通信使用事件的客户端。</span><span class="sxs-lookup"><span data-stu-id="77826-125">Your component communicates to clients using events.</span></span> <span data-ttu-id="77826-126">*MethodName* `Completed`事件警报到完成的异步任务，客户端和*MethodName* `ProgressChanged`事件通知的异步任务的进度的客户端。</span><span class="sxs-lookup"><span data-stu-id="77826-126">The *MethodName*`Completed` event alerts clients to the completion of an asynchronous task, and the *MethodName*`ProgressChanged` event informs clients of the progress of an asynchronous task.</span></span>  
  
#### <a name="to-define-asynchronous-events-for-clients-of-your-component"></a><span data-ttu-id="77826-127">若要为你的组件的客户端定义异步事件：</span><span class="sxs-lookup"><span data-stu-id="77826-127">To define asynchronous events for clients of your component:</span></span>  
  
1.  <span data-ttu-id="77826-128">导入<xref:System.Threading?displayProperty=nameWithType>和<xref:System.Collections.Specialized?displayProperty=nameWithType>在你的文件的顶部的命名空间。</span><span class="sxs-lookup"><span data-stu-id="77826-128">Import the <xref:System.Threading?displayProperty=nameWithType> and <xref:System.Collections.Specialized?displayProperty=nameWithType> namespaces at the top of your file.</span></span>  
  
     [!code-csharp[System.ComponentModel.AsyncOperationManager#11](../../../samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.AsyncOperationManager/CS/primenumbercalculatormain.cs#11)]
     [!code-vb[System.ComponentModel.AsyncOperationManager#11](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.AsyncOperationManager/VB/primenumbercalculatormain.vb#11)]  
  
2.  <span data-ttu-id="77826-129">之前`PrimeNumberCalculator`类定义，声明的进度和完成情况的事件的委托。</span><span class="sxs-lookup"><span data-stu-id="77826-129">Before the `PrimeNumberCalculator` class definition, declare delegates for progress and completion events.</span></span>  
  
     [!code-csharp[System.ComponentModel.AsyncOperationManager#7](../../../samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.AsyncOperationManager/CS/primenumbercalculatormain.cs#7)]
     [!code-vb[System.ComponentModel.AsyncOperationManager#7](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.AsyncOperationManager/VB/primenumbercalculatormain.vb#7)]  
  
3.  <span data-ttu-id="77826-130">在`PrimeNumberCalculator`类定义中，声明用于报告进度和完成情况向客户端的事件。</span><span class="sxs-lookup"><span data-stu-id="77826-130">In the `PrimeNumberCalculator` class definition, declare events for reporting progress and completion to clients.</span></span>  
  
     [!code-csharp[System.ComponentModel.AsyncOperationManager#8](../../../samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.AsyncOperationManager/CS/primenumbercalculatormain.cs#8)]
     [!code-vb[System.ComponentModel.AsyncOperationManager#8](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.AsyncOperationManager/VB/primenumbercalculatormain.vb#8)]  
  
4.  <span data-ttu-id="77826-131">后`PrimeNumberCalculator`类定义中，派生`CalculatePrimeCompletedEventArgs`用于报告的每个客户端的事件处理程序的计算结果的类`CalculatePrimeCompleted`.event。</span><span class="sxs-lookup"><span data-stu-id="77826-131">After the `PrimeNumberCalculator` class definition, derive the `CalculatePrimeCompletedEventArgs` class for reporting the outcome of each calculation to the client's event handler for the `CalculatePrimeCompleted`.event.</span></span> <span data-ttu-id="77826-132">除了`AsyncCompletedEventArgs`属性，此类使客户端确定测试什么号、 是否是质数，以及内容的第一个约数是如果它不是质数。</span><span class="sxs-lookup"><span data-stu-id="77826-132">In addition to the `AsyncCompletedEventArgs` properties, this class enables the client to determine what number was tested, whether it is prime, and what the first divisor is if it is not prime.</span></span>  
  
     [!code-csharp[System.ComponentModel.AsyncOperationManager#6](../../../samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.AsyncOperationManager/CS/primenumbercalculatormain.cs#6)]
     [!code-vb[System.ComponentModel.AsyncOperationManager#6](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.AsyncOperationManager/VB/primenumbercalculatormain.vb#6)]  
  
## <a name="checkpoint"></a><span data-ttu-id="77826-133">检查点</span><span class="sxs-lookup"><span data-stu-id="77826-133">Checkpoint</span></span>  
 <span data-ttu-id="77826-134">此时，你可以生成组件。</span><span class="sxs-lookup"><span data-stu-id="77826-134">At this point, you can build the component.</span></span>  
  
#### <a name="to-test-your-component"></a><span data-ttu-id="77826-135">若要测试你的组件</span><span class="sxs-lookup"><span data-stu-id="77826-135">To test your component</span></span>  
  
-   <span data-ttu-id="77826-136">编译该组件。</span><span class="sxs-lookup"><span data-stu-id="77826-136">Compile the component.</span></span>  
  
     <span data-ttu-id="77826-137">你将收到两个编译器警告：</span><span class="sxs-lookup"><span data-stu-id="77826-137">You will receive two compiler warnings:</span></span>  
  
    ```  
    warning CS0067: The event 'AsynchronousPatternExample.PrimeNumberCalculator.ProgressChanged' is never used  
    warning CS0067: The event 'AsynchronousPatternExample.PrimeNumberCalculator.CalculatePrimeCompleted' is never used  
    ```  
  
     <span data-ttu-id="77826-138">在下一部分中，将清除这些警告。</span><span class="sxs-lookup"><span data-stu-id="77826-138">These warnings will be cleared in the next section.</span></span>  
  
## <a name="defining-private-delegates"></a><span data-ttu-id="77826-139">定义私有委托</span><span class="sxs-lookup"><span data-stu-id="77826-139">Defining Private Delegates</span></span>  
 <span data-ttu-id="77826-140">异步方面`PrimeNumberCalculator`组件均与特殊的委托名为在内部实现<xref:System.Threading.SendOrPostCallback>。</span><span class="sxs-lookup"><span data-stu-id="77826-140">The asynchronous aspects of the `PrimeNumberCalculator` component are implemented internally with a special delegate known as a <xref:System.Threading.SendOrPostCallback>.</span></span> <span data-ttu-id="77826-141">A<xref:System.Threading.SendOrPostCallback>表示执行的回调方法<xref:System.Threading.ThreadPool>线程。</span><span class="sxs-lookup"><span data-stu-id="77826-141">A <xref:System.Threading.SendOrPostCallback> represents a callback method that executes on a <xref:System.Threading.ThreadPool> thread.</span></span> <span data-ttu-id="77826-142">回调方法必须具有采用类型的单个参数的签名<xref:System.Object>，这意味着你将需要将传递委托中的包装类之间的状态。</span><span class="sxs-lookup"><span data-stu-id="77826-142">The callback method must have a signature that takes a single parameter of type <xref:System.Object>, which means you will need to pass state among delegates in a wrapper class.</span></span> <span data-ttu-id="77826-143">有关详细信息，请参阅<xref:System.Threading.SendOrPostCallback>。</span><span class="sxs-lookup"><span data-stu-id="77826-143">For more information, see <xref:System.Threading.SendOrPostCallback>.</span></span>  
  
#### <a name="to-implement-your-components-internal-asynchronous-behavior"></a><span data-ttu-id="77826-144">若要实现组件的内部异步行为：</span><span class="sxs-lookup"><span data-stu-id="77826-144">To implement your component's internal asynchronous behavior:</span></span>  
  
1.  <span data-ttu-id="77826-145">声明和创建<xref:System.Threading.SendOrPostCallback>委托中`PrimeNumberCalculator`类。</span><span class="sxs-lookup"><span data-stu-id="77826-145">Declare and create the <xref:System.Threading.SendOrPostCallback> delegates in the `PrimeNumberCalculator` class.</span></span> <span data-ttu-id="77826-146">创建<xref:System.Threading.SendOrPostCallback>实用程序方法中的对象调用`InitializeDelegates`。</span><span class="sxs-lookup"><span data-stu-id="77826-146">Create the <xref:System.Threading.SendOrPostCallback> objects in a utility method called `InitializeDelegates`.</span></span>  
  
     <span data-ttu-id="77826-147">你将需要两个委托： 一个用于向客户端，报告进度，一个用于向客户端报告完成。</span><span class="sxs-lookup"><span data-stu-id="77826-147">You will need two delegates: one for reporting progress to the client, and one for reporting completion to the client.</span></span>  
  
     [!code-csharp[System.ComponentModel.AsyncOperationManager#9](../../../samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.AsyncOperationManager/CS/primenumbercalculatormain.cs#9)]
     [!code-vb[System.ComponentModel.AsyncOperationManager#9](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.AsyncOperationManager/VB/primenumbercalculatormain.vb#9)]  
    [!code-csharp[System.ComponentModel.AsyncOperationManager#20](../../../samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.AsyncOperationManager/CS/primenumbercalculatormain.cs#20)]
    [!code-vb[System.ComponentModel.AsyncOperationManager#20](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.AsyncOperationManager/VB/primenumbercalculatormain.vb#20)]  
  
2.  <span data-ttu-id="77826-148">调用`InitializeDelegates`组件的构造函数中的方法。</span><span class="sxs-lookup"><span data-stu-id="77826-148">Call the `InitializeDelegates` method in your component's constructor.</span></span>  
  
     [!code-csharp[System.ComponentModel.AsyncOperationManager#21](../../../samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.AsyncOperationManager/CS/primenumbercalculatormain.cs#21)]
     [!code-vb[System.ComponentModel.AsyncOperationManager#21](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.AsyncOperationManager/VB/primenumbercalculatormain.vb#21)]  
  
3.  <span data-ttu-id="77826-149">在声明委托`PrimeNumberCalculator`处理以异步方式执行的实际工作的类。</span><span class="sxs-lookup"><span data-stu-id="77826-149">Declare a delegate in the `PrimeNumberCalculator` class that handles the actual work to be done asynchronously.</span></span> <span data-ttu-id="77826-150">此委托包装用于测试是否数字是质数的辅助方法。</span><span class="sxs-lookup"><span data-stu-id="77826-150">This delegate wraps the worker method that tests whether a number is prime.</span></span> <span data-ttu-id="77826-151">委托采用<xref:System.ComponentModel.AsyncOperation>参数，它将用于跟踪异步操作的生存期。</span><span class="sxs-lookup"><span data-stu-id="77826-151">The delegate takes an <xref:System.ComponentModel.AsyncOperation> parameter, which will be used to track the lifetime of the asynchronous operation.</span></span>  
  
     [!code-csharp[System.ComponentModel.AsyncOperationManager#22](../../../samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.AsyncOperationManager/CS/primenumbercalculatormain.cs#22)]
     [!code-vb[System.ComponentModel.AsyncOperationManager#22](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.AsyncOperationManager/VB/primenumbercalculatormain.vb#22)]  
  
4.  <span data-ttu-id="77826-152">创建用于管理挂起的异步操作的生存期的集合。</span><span class="sxs-lookup"><span data-stu-id="77826-152">Create a collection for managing lifetimes of pending asynchronous operations.</span></span> <span data-ttu-id="77826-153">客户端需要跟踪的操作，当它们是执行和完成，但这种跟踪完成通过要求客户端时要传递的唯一令牌或任务 ID、 客户端发出对异步方法的调用的方法。</span><span class="sxs-lookup"><span data-stu-id="77826-153">The client needs a way to track operations as they are executed and completed, and this tracking is done by requiring the client to pass a unique token, or task ID, when the client makes the call to the asynchronous method.</span></span> <span data-ttu-id="77826-154">`PrimeNumberCalculator`组件必须跟踪的每个调用通过使用其相应的调用将任务 ID 相关联。</span><span class="sxs-lookup"><span data-stu-id="77826-154">The `PrimeNumberCalculator` component must keep track of each call by associating the task ID with its corresponding invocation.</span></span> <span data-ttu-id="77826-155">如果客户端传递不唯一，任务 ID`PrimeNumberCalculator`组件必须引发一个异常。</span><span class="sxs-lookup"><span data-stu-id="77826-155">If the client passes a task ID that is not unique, the `PrimeNumberCalculator` component must raise an exception.</span></span>  
  
     <span data-ttu-id="77826-156">`PrimeNumberCalculator`组件将跟踪的任务 ID，通过使用特殊的集合类调用<xref:System.Collections.Specialized.HybridDictionary>。</span><span class="sxs-lookup"><span data-stu-id="77826-156">The `PrimeNumberCalculator` component keeps track of task ID by using a special collection class called a <xref:System.Collections.Specialized.HybridDictionary>.</span></span> <span data-ttu-id="77826-157">在类定义中，创建<xref:System.Collections.Specialized.HybridDictionary>调用`userTokenToLifetime`。</span><span class="sxs-lookup"><span data-stu-id="77826-157">In the class definition, create a <xref:System.Collections.Specialized.HybridDictionary> called `userTokenToLifetime`.</span></span>  
  
     [!code-csharp[System.ComponentModel.AsyncOperationManager#23](../../../samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.AsyncOperationManager/CS/primenumbercalculatormain.cs#23)]
     [!code-vb[System.ComponentModel.AsyncOperationManager#23](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.AsyncOperationManager/VB/primenumbercalculatormain.vb#23)]  
  
## <a name="implementing-public-events"></a><span data-ttu-id="77826-158">实现公共事件</span><span class="sxs-lookup"><span data-stu-id="77826-158">Implementing Public Events</span></span>  
 <span data-ttu-id="77826-159">向客户端使用事件通知实现基于事件的异步模式的组件。</span><span class="sxs-lookup"><span data-stu-id="77826-159">Components that implement the Event-based Asynchronous Pattern communicate to clients using events.</span></span> <span data-ttu-id="77826-160">上的帮助合适的线程调用这些事件<xref:System.ComponentModel.AsyncOperation>类。</span><span class="sxs-lookup"><span data-stu-id="77826-160">These events are invoked on the proper thread with the help of the <xref:System.ComponentModel.AsyncOperation> class.</span></span>  
  
#### <a name="to-raise-events-to-your-components-clients"></a><span data-ttu-id="77826-161">若要引发事件，以便将您的组件的客户端：</span><span class="sxs-lookup"><span data-stu-id="77826-161">To raise events to your component's clients:</span></span>  
  
1.  <span data-ttu-id="77826-162">实现用于向客户端报告的公共事件。</span><span class="sxs-lookup"><span data-stu-id="77826-162">Implement public events for reporting to clients.</span></span> <span data-ttu-id="77826-163">你将需要为报告进度和一个用于报告完成事件。</span><span class="sxs-lookup"><span data-stu-id="77826-163">You will need an event for reporting progress and one for reporting completion.</span></span>  
  
     [!code-csharp[System.ComponentModel.AsyncOperationManager#24](../../../samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.AsyncOperationManager/CS/primenumbercalculatormain.cs#24)]
     [!code-vb[System.ComponentModel.AsyncOperationManager#24](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.AsyncOperationManager/VB/primenumbercalculatormain.vb#24)]  
  
## <a name="implementing-the-completion-method"></a><span data-ttu-id="77826-164">实现完成方法</span><span class="sxs-lookup"><span data-stu-id="77826-164">Implementing the Completion Method</span></span>  
 <span data-ttu-id="77826-165">完成委托是通过成功完成、 错误或取消的异步操作结束时，将调用的基础，自由线程的异步行为的方法。</span><span class="sxs-lookup"><span data-stu-id="77826-165">The completion delegate is the method that the underlying, free-threaded asynchronous behavior will invoke when the asynchronous operation ends by successful completion, error, or cancellation.</span></span> <span data-ttu-id="77826-166">此调用任意线程上发生的情况。</span><span class="sxs-lookup"><span data-stu-id="77826-166">This invocation happens on an arbitrary thread.</span></span>  
  
 <span data-ttu-id="77826-167">此方法是从内部集合的唯一客户端令牌删除客户端的任务 ID 的情况。</span><span class="sxs-lookup"><span data-stu-id="77826-167">This method is where the client's task ID is removed from the internal collection of unique client tokens.</span></span> <span data-ttu-id="77826-168">此方法也会通过调用结束特定的异步操作的生存期<xref:System.ComponentModel.AsyncOperation.PostOperationCompleted%2A>到相应方法<xref:System.ComponentModel.AsyncOperation>。</span><span class="sxs-lookup"><span data-stu-id="77826-168">This method also ends the lifetime of a particular asynchronous operation by calling the <xref:System.ComponentModel.AsyncOperation.PostOperationCompleted%2A> method on the corresponding <xref:System.ComponentModel.AsyncOperation>.</span></span> <span data-ttu-id="77826-169">此调用引发适合于应用程序模型的线程上完成事件。</span><span class="sxs-lookup"><span data-stu-id="77826-169">This call raises the completion event on the thread that is appropriate for the application model.</span></span> <span data-ttu-id="77826-170">后<xref:System.ComponentModel.AsyncOperation.PostOperationCompleted%2A>调用方法时，此实例的<xref:System.ComponentModel.AsyncOperation>不再使用，并将任何后续尝试使用它将引发异常。</span><span class="sxs-lookup"><span data-stu-id="77826-170">After the <xref:System.ComponentModel.AsyncOperation.PostOperationCompleted%2A> method is called, this instance of <xref:System.ComponentModel.AsyncOperation> can no longer be used, and any subsequent attempts to use it will throw an exception.</span></span>  
  
 <span data-ttu-id="77826-171">`CompletionMethod`签名必须包含描述异步操作的结果所需的所有状态。</span><span class="sxs-lookup"><span data-stu-id="77826-171">The `CompletionMethod` signature must hold all state necessary to describe the outcome of the asynchronous operation.</span></span> <span data-ttu-id="77826-172">它包含此特定的异步操作，进行了测试的数量的状态是否为质数和其第一个除数的值如果它不是一个质数数字。</span><span class="sxs-lookup"><span data-stu-id="77826-172">It holds state for the number that was tested by this particular asynchronous operation, whether the number is prime, and the value of its first divisor if it is not a prime number.</span></span> <span data-ttu-id="77826-173">它还包含描述发生的任何异常的状态和<xref:System.ComponentModel.AsyncOperation>对应于此特定任务。</span><span class="sxs-lookup"><span data-stu-id="77826-173">It also holds state describing any exception that occurred, and the <xref:System.ComponentModel.AsyncOperation> corresponding to this particular task.</span></span>  
  
#### <a name="to-complete-an-asynchronous-operation"></a><span data-ttu-id="77826-174">若要完成一个异步操作：</span><span class="sxs-lookup"><span data-stu-id="77826-174">To complete an asynchronous operation:</span></span>  
  
-   <span data-ttu-id="77826-175">实现完成方法。</span><span class="sxs-lookup"><span data-stu-id="77826-175">Implement the completion method.</span></span> <span data-ttu-id="77826-176">它采用六个参数，它用于填充`CalculatePrimeCompletedEventArgs`通过客户端的客户端返回`CalculatePrimeCompletedEventHandler`。</span><span class="sxs-lookup"><span data-stu-id="77826-176">It takes six parameters, which it uses to populate a `CalculatePrimeCompletedEventArgs` that is returned to the client through the client's `CalculatePrimeCompletedEventHandler`.</span></span> <span data-ttu-id="77826-177">它会从内部的集合中，删除客户端的任务 ID 标记和结束异步操作的整个生存期内通过调用<xref:System.ComponentModel.AsyncOperation.PostOperationCompleted%2A>。</span><span class="sxs-lookup"><span data-stu-id="77826-177">It removes the client's task ID token from the internal collection, and it ends the asynchronous operation's lifetime with a call to <xref:System.ComponentModel.AsyncOperation.PostOperationCompleted%2A>.</span></span> <span data-ttu-id="77826-178"><xref:System.ComponentModel.AsyncOperation>封送到的线程或上下文适合于应用程序模型的调用。</span><span class="sxs-lookup"><span data-stu-id="77826-178">The <xref:System.ComponentModel.AsyncOperation> marshals the call to the thread or context that is appropriate for the application model.</span></span>  
  
     [!code-csharp[System.ComponentModel.AsyncOperationManager#26](../../../samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.AsyncOperationManager/CS/primenumbercalculatormain.cs#26)]
     [!code-vb[System.ComponentModel.AsyncOperationManager#26](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.AsyncOperationManager/VB/primenumbercalculatormain.vb#26)]  
  
## <a name="checkpoint"></a><span data-ttu-id="77826-179">检查点</span><span class="sxs-lookup"><span data-stu-id="77826-179">Checkpoint</span></span>  
 <span data-ttu-id="77826-180">此时，你可以生成组件。</span><span class="sxs-lookup"><span data-stu-id="77826-180">At this point, you can build the component.</span></span>  
  
#### <a name="to-test-your-component"></a><span data-ttu-id="77826-181">若要测试你的组件</span><span class="sxs-lookup"><span data-stu-id="77826-181">To test your component</span></span>  
  
-   <span data-ttu-id="77826-182">编译该组件。</span><span class="sxs-lookup"><span data-stu-id="77826-182">Compile the component.</span></span>  
  
     <span data-ttu-id="77826-183">你将收到一个编译器警告：</span><span class="sxs-lookup"><span data-stu-id="77826-183">You will receive one compiler warning:</span></span>  
  
    ```  
    warning CS0169: The private field 'AsynchronousPatternExample.PrimeNumberCalculator.workerDelegate' is never used  
    ```  
  
     <span data-ttu-id="77826-184">此警告将在下一节中解析。</span><span class="sxs-lookup"><span data-stu-id="77826-184">This warning will be resolved in the next section.</span></span>  
  
## <a name="implementing-the-worker-methods"></a><span data-ttu-id="77826-185">实现的辅助方法</span><span class="sxs-lookup"><span data-stu-id="77826-185">Implementing the Worker Methods</span></span>  
 <span data-ttu-id="77826-186">到目前为止，已实现的支持异步代码`PrimeNumberCalculator`组件。</span><span class="sxs-lookup"><span data-stu-id="77826-186">So far, you have implemented the supporting asynchronous code for the `PrimeNumberCalculator` component.</span></span> <span data-ttu-id="77826-187">现在你可以实现执行的实际工作的代码。</span><span class="sxs-lookup"><span data-stu-id="77826-187">Now you can implement the code that does the actual work.</span></span> <span data-ttu-id="77826-188">将实现以下三种方法： `CalculateWorker`， `BuildPrimeNumberList`，和`IsPrime`。</span><span class="sxs-lookup"><span data-stu-id="77826-188">You will implement three methods: `CalculateWorker`, `BuildPrimeNumberList`, and `IsPrime`.</span></span> <span data-ttu-id="77826-189">在一起，`BuildPrimeNumberList`和`IsPrime`构成调用选筛的埃拉托色尼斯，用于确定数字是质数通过查找最多的测试数的平方根的所有质数的已知算法。</span><span class="sxs-lookup"><span data-stu-id="77826-189">Together, `BuildPrimeNumberList` and `IsPrime` comprise a well-known algorithm called the Sieve of Eratosthenes, which determines if a number is prime by finding all the prime numbers up to the square root of the test number.</span></span> <span data-ttu-id="77826-190">如果没有发现任何约数，通过该点，则测试数为质数。</span><span class="sxs-lookup"><span data-stu-id="77826-190">If no divisors are found by that point, the test number is prime.</span></span>  
  
 <span data-ttu-id="77826-191">如果此组件专为最大效率，则它应记住发现的各种调用不同的测试号码的所有质数。</span><span class="sxs-lookup"><span data-stu-id="77826-191">If this component were written for maximum efficiency, it would remember all the prime numbers discovered by various invocations for different test numbers.</span></span> <span data-ttu-id="77826-192">它还会检查最小的约数，例如 2、 3 和 5。</span><span class="sxs-lookup"><span data-stu-id="77826-192">It would also check for trivial divisors like 2, 3, and 5.</span></span> <span data-ttu-id="77826-193">此示例的目的是为了演示如何耗时的操作可以异步执行，但是，以便为你保留为练习这些优化。</span><span class="sxs-lookup"><span data-stu-id="77826-193">The intent of this example is to demonstrate how time-consuming operations can be executed asynchronously, however, so these optimizations are left as an exercise for you.</span></span>  
  
 <span data-ttu-id="77826-194">`CalculateWorker`方法包装在一个委托，并通过调用以异步方式调用`BeginInvoke`。</span><span class="sxs-lookup"><span data-stu-id="77826-194">The `CalculateWorker` method is wrapped in a delegate and is invoked asynchronously with a call to `BeginInvoke`.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="77826-195">进度报告中实现`BuildPrimeNumberList`方法。</span><span class="sxs-lookup"><span data-stu-id="77826-195">Progress reporting is implemented in the `BuildPrimeNumberList` method.</span></span> <span data-ttu-id="77826-196">快速在计算机上，`ProgressChanged`可以快速连续引发事件。</span><span class="sxs-lookup"><span data-stu-id="77826-196">On fast computers, `ProgressChanged` events can be raised in rapid succession.</span></span> <span data-ttu-id="77826-197">客户端线程，在其会引发这些事件，必须能够处理这种情况。</span><span class="sxs-lookup"><span data-stu-id="77826-197">The client thread, on which these events are raised, must be able to handle this situation.</span></span> <span data-ttu-id="77826-198">用户界面代码可能是溢满消息和无法保持同步，结果导致挂起行为。</span><span class="sxs-lookup"><span data-stu-id="77826-198">User interface code may be flooded with messages and unable to keep up, resulting in hanging behavior.</span></span> <span data-ttu-id="77826-199">对于示例用户接口处理这种情况下，请参阅[如何： 实现基于事件的异步模式的客户端](../../../docs/standard/asynchronous-programming-patterns/how-to-implement-a-client-of-the-event-based-asynchronous-pattern.md)。</span><span class="sxs-lookup"><span data-stu-id="77826-199">For an example user interface that handles this situation, see [How to: Implement a Client of the Event-based Asynchronous Pattern](../../../docs/standard/asynchronous-programming-patterns/how-to-implement-a-client-of-the-event-based-asynchronous-pattern.md).</span></span>  
  
#### <a name="to-execute-the-prime-number-calculation-asynchronously"></a><span data-ttu-id="77826-200">以异步方式执行的质数计算：</span><span class="sxs-lookup"><span data-stu-id="77826-200">To execute the prime number calculation asynchronously:</span></span>  
  
1.  <span data-ttu-id="77826-201">实现`TaskCanceled`的实用工具方法。</span><span class="sxs-lookup"><span data-stu-id="77826-201">Implement the `TaskCanceled` utility method.</span></span> <span data-ttu-id="77826-202">此检查任务生存期集合中是否存在给定的任务 ID，并返回`true`如果找不到任务 ID。</span><span class="sxs-lookup"><span data-stu-id="77826-202">This checks the task lifetime collection for the given task ID, and returns `true` if the task ID is not found.</span></span>  
  
     [!code-csharp[System.ComponentModel.AsyncOperationManager#32](../../../samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.AsyncOperationManager/CS/primenumbercalculatormain.cs#32)]
     [!code-vb[System.ComponentModel.AsyncOperationManager#32](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.AsyncOperationManager/VB/primenumbercalculatormain.vb#32)]  
  
2.  <span data-ttu-id="77826-203">实现 `CalculateWorker` 方法。</span><span class="sxs-lookup"><span data-stu-id="77826-203">Implement the `CalculateWorker` method.</span></span> <span data-ttu-id="77826-204">它采用两个参数： 一个数字以测试，请与<xref:System.ComponentModel.AsyncOperation>。</span><span class="sxs-lookup"><span data-stu-id="77826-204">It takes two parameters: a number to test, and an <xref:System.ComponentModel.AsyncOperation>.</span></span>  
  
     [!code-csharp[System.ComponentModel.AsyncOperationManager#27](../../../samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.AsyncOperationManager/CS/primenumbercalculatormain.cs#27)]
     [!code-vb[System.ComponentModel.AsyncOperationManager#27](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.AsyncOperationManager/VB/primenumbercalculatormain.vb#27)]  
  
3.  <span data-ttu-id="77826-205">实现 `BuildPrimeNumberList`。</span><span class="sxs-lookup"><span data-stu-id="77826-205">Implement `BuildPrimeNumberList`.</span></span> <span data-ttu-id="77826-206">它采用两个参数： 的编号，以测试，和<xref:System.ComponentModel.AsyncOperation>。</span><span class="sxs-lookup"><span data-stu-id="77826-206">It takes two parameters: the number to test, and an <xref:System.ComponentModel.AsyncOperation>.</span></span> <span data-ttu-id="77826-207">它使用<xref:System.ComponentModel.AsyncOperation>来报告进度和增量结果。</span><span class="sxs-lookup"><span data-stu-id="77826-207">It uses the <xref:System.ComponentModel.AsyncOperation> to report progress and incremental results.</span></span> <span data-ttu-id="77826-208">这可确保适当线程或应用程序模型的上下文调用客户端的事件处理程序。</span><span class="sxs-lookup"><span data-stu-id="77826-208">This assures that the client's event handlers are called on the proper thread or context for the application model.</span></span> <span data-ttu-id="77826-209">当`BuildPrimeNumberList`质数找到，它报告增量结果给客户端的事件处理程序`ProgressChanged`事件。</span><span class="sxs-lookup"><span data-stu-id="77826-209">When `BuildPrimeNumberList` finds a prime number, it reports this as an incremental result to the client's event handler for the `ProgressChanged` event.</span></span> <span data-ttu-id="77826-210">这需要从派生的类<xref:System.ComponentModel.ProgressChangedEventArgs>、 调用`CalculatePrimeProgressChangedEventArgs`，该类有一个新增属性调用`LatestPrimeNumber`。</span><span class="sxs-lookup"><span data-stu-id="77826-210">This requires a class derived from <xref:System.ComponentModel.ProgressChangedEventArgs>, called `CalculatePrimeProgressChangedEventArgs`, which has one added property called `LatestPrimeNumber`.</span></span>  
  
     <span data-ttu-id="77826-211">`BuildPrimeNumberList`方法还会定期调用`TaskCanceled`方法，如果该方法返回的退出`true`。</span><span class="sxs-lookup"><span data-stu-id="77826-211">The `BuildPrimeNumberList` method also periodically calls the `TaskCanceled` method and exits if the method returns `true`.</span></span>  
  
     [!code-csharp[System.ComponentModel.AsyncOperationManager#5](../../../samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.AsyncOperationManager/CS/primenumbercalculatormain.cs#5)]
     [!code-vb[System.ComponentModel.AsyncOperationManager#5](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.AsyncOperationManager/VB/primenumbercalculatormain.vb#5)]  
  
4.  <span data-ttu-id="77826-212">实现 `IsPrime`。</span><span class="sxs-lookup"><span data-stu-id="77826-212">Implement `IsPrime`.</span></span> <span data-ttu-id="77826-213">它采用三个参数： 已知的质数、 的编号，以测试和找到的第一个约数一个输出参数的列表。</span><span class="sxs-lookup"><span data-stu-id="77826-213">It takes three parameters: a list of known prime numbers, the number to test, and an output parameter for the first divisor found.</span></span> <span data-ttu-id="77826-214">给定的质数列表，它确定测试数是否质数。</span><span class="sxs-lookup"><span data-stu-id="77826-214">Given the list of prime numbers, it determines if the test number is prime.</span></span>  
  
     [!code-csharp[System.ComponentModel.AsyncOperationManager#28](../../../samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.AsyncOperationManager/CS/primenumbercalculatormain.cs#28)]
     [!code-vb[System.ComponentModel.AsyncOperationManager#28](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.AsyncOperationManager/VB/primenumbercalculatormain.vb#28)]  
  
5.  <span data-ttu-id="77826-215">派生`CalculatePrimeProgressChangedEventArgs`从<xref:System.ComponentModel.ProgressChangedEventArgs>。</span><span class="sxs-lookup"><span data-stu-id="77826-215">Derive `CalculatePrimeProgressChangedEventArgs` from <xref:System.ComponentModel.ProgressChangedEventArgs>.</span></span> <span data-ttu-id="77826-216">此类是用于向客户端的事件处理程序报告增量结果必要`ProgressChanged`事件。</span><span class="sxs-lookup"><span data-stu-id="77826-216">This class is necessary for reporting incremental results to the client's event handler for the `ProgressChanged` event.</span></span> <span data-ttu-id="77826-217">它具有一个名为的添加的属性`LatestPrimeNumber`。</span><span class="sxs-lookup"><span data-stu-id="77826-217">It has one added property called `LatestPrimeNumber`.</span></span>  
  
     [!code-csharp[System.ComponentModel.AsyncOperationManager#29](../../../samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.AsyncOperationManager/CS/primenumbercalculatormain.cs#29)]
     [!code-vb[System.ComponentModel.AsyncOperationManager#29](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.AsyncOperationManager/VB/primenumbercalculatormain.vb#29)]  
  
## <a name="checkpoint"></a><span data-ttu-id="77826-218">检查点</span><span class="sxs-lookup"><span data-stu-id="77826-218">Checkpoint</span></span>  
 <span data-ttu-id="77826-219">此时，你可以生成组件。</span><span class="sxs-lookup"><span data-stu-id="77826-219">At this point, you can build the component.</span></span>  
  
#### <a name="to-test-your-component"></a><span data-ttu-id="77826-220">若要测试你的组件</span><span class="sxs-lookup"><span data-stu-id="77826-220">To test your component</span></span>  
  
-   <span data-ttu-id="77826-221">编译该组件。</span><span class="sxs-lookup"><span data-stu-id="77826-221">Compile the component.</span></span>  
  
     <span data-ttu-id="77826-222">所有这些剩下编写是启动和取消异步操作，方法`CalculatePrimeAsync`和`CancelAsync`。</span><span class="sxs-lookup"><span data-stu-id="77826-222">All that remains to be written are the methods to start and cancel asynchronous operations, `CalculatePrimeAsync` and `CancelAsync`.</span></span>  
  
## <a name="implementing-the-start-and-cancel-methods"></a><span data-ttu-id="77826-223">实现启动和取消方法</span><span class="sxs-lookup"><span data-stu-id="77826-223">Implementing the Start and Cancel Methods</span></span>  
 <span data-ttu-id="77826-224">通过调用的辅助方法启动其自身线程上`BeginInvoke`上将其包装的委托。</span><span class="sxs-lookup"><span data-stu-id="77826-224">You start the worker method on its own thread by calling `BeginInvoke` on the delegate that wraps it.</span></span> <span data-ttu-id="77826-225">若要管理特定的异步操作的生存期，请调用<xref:System.ComponentModel.AsyncOperationManager.CreateOperation%2A>方法<xref:System.ComponentModel.AsyncOperationManager>帮助器类。</span><span class="sxs-lookup"><span data-stu-id="77826-225">To manage the lifetime of a particular asynchronous operation, you call the <xref:System.ComponentModel.AsyncOperationManager.CreateOperation%2A> method on the <xref:System.ComponentModel.AsyncOperationManager> helper class.</span></span> <span data-ttu-id="77826-226">这将返回<xref:System.ComponentModel.AsyncOperation>，这将封送到合适的线程或上下文调用客户端的事件处理程序。</span><span class="sxs-lookup"><span data-stu-id="77826-226">This returns an <xref:System.ComponentModel.AsyncOperation>, which marshals calls on the client's event handlers to the proper thread or context.</span></span>  
  
 <span data-ttu-id="77826-227">通过调用取消挂起操作特定<xref:System.ComponentModel.AsyncOperation.PostOperationCompleted%2A>其相应<xref:System.ComponentModel.AsyncOperation>。</span><span class="sxs-lookup"><span data-stu-id="77826-227">You cancel a particular pending operation by calling <xref:System.ComponentModel.AsyncOperation.PostOperationCompleted%2A> on its corresponding <xref:System.ComponentModel.AsyncOperation>.</span></span> <span data-ttu-id="77826-228">这会结束该操作和对任何后续调用其<xref:System.ComponentModel.AsyncOperation>将引发异常。</span><span class="sxs-lookup"><span data-stu-id="77826-228">This ends that operation, and any subsequent calls to its <xref:System.ComponentModel.AsyncOperation> will throw an exception.</span></span>  
  
#### <a name="to-implement-start-and-cancel-functionality"></a><span data-ttu-id="77826-229">若要实现启动和取消功能：</span><span class="sxs-lookup"><span data-stu-id="77826-229">To implement Start and Cancel functionality:</span></span>  
  
1.  <span data-ttu-id="77826-230">实现 `CalculatePrimeAsync` 方法。</span><span class="sxs-lookup"><span data-stu-id="77826-230">Implement the `CalculatePrimeAsync` method.</span></span> <span data-ttu-id="77826-231">请确保客户端提供令牌 (任务 ID) 是唯一的表示当前挂起任务的所有标记。</span><span class="sxs-lookup"><span data-stu-id="77826-231">Make sure the client-supplied token (task ID) is unique with respect to all the tokens representing currently pending tasks.</span></span> <span data-ttu-id="77826-232">如果客户端传递在非唯一令牌中，`CalculatePrimeAsync`引发异常。</span><span class="sxs-lookup"><span data-stu-id="77826-232">If the client passes in a non-unique token, `CalculatePrimeAsync` raises an exception.</span></span> <span data-ttu-id="77826-233">否则，该令牌添加到任务 ID 集合。</span><span class="sxs-lookup"><span data-stu-id="77826-233">Otherwise, the token is added to the task ID collection.</span></span>  
  
     [!code-csharp[System.ComponentModel.AsyncOperationManager#3](../../../samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.AsyncOperationManager/CS/primenumbercalculatormain.cs#3)]
     [!code-vb[System.ComponentModel.AsyncOperationManager#3](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.AsyncOperationManager/VB/primenumbercalculatormain.vb#3)]  
  
2.  <span data-ttu-id="77826-234">实现 `CancelAsync` 方法。</span><span class="sxs-lookup"><span data-stu-id="77826-234">Implement the `CancelAsync` method.</span></span> <span data-ttu-id="77826-235">如果`taskId`参数在令牌的集合中存在，则将删除。</span><span class="sxs-lookup"><span data-stu-id="77826-235">If the `taskId` parameter exists in the token collection, it is removed.</span></span> <span data-ttu-id="77826-236">这可以阻止尚未开始运行的已取消的任务。</span><span class="sxs-lookup"><span data-stu-id="77826-236">This prevents canceled tasks that have not started from running.</span></span> <span data-ttu-id="77826-237">如果该任务正在运行，`BuildPrimeNumberList`方法退出时检测到的任务 ID 已从生存期集合中移除。</span><span class="sxs-lookup"><span data-stu-id="77826-237">If the task is running, the `BuildPrimeNumberList` method exits when it detects that the task ID has been removed from the lifetime collection.</span></span>  
  
     [!code-csharp[System.ComponentModel.AsyncOperationManager#4](../../../samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.AsyncOperationManager/CS/primenumbercalculatormain.cs#4)]
     [!code-vb[System.ComponentModel.AsyncOperationManager#4](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.AsyncOperationManager/VB/primenumbercalculatormain.vb#4)]  
  
## <a name="checkpoint"></a><span data-ttu-id="77826-238">检查点</span><span class="sxs-lookup"><span data-stu-id="77826-238">Checkpoint</span></span>  
 <span data-ttu-id="77826-239">此时，你可以生成组件。</span><span class="sxs-lookup"><span data-stu-id="77826-239">At this point, you can build the component.</span></span>  
  
#### <a name="to-test-your-component"></a><span data-ttu-id="77826-240">若要测试你的组件</span><span class="sxs-lookup"><span data-stu-id="77826-240">To test your component</span></span>  
  
-   <span data-ttu-id="77826-241">编译该组件。</span><span class="sxs-lookup"><span data-stu-id="77826-241">Compile the component.</span></span>  
  
 <span data-ttu-id="77826-242">`PrimeNumberCalculator`组件现在已完成并可供使用。</span><span class="sxs-lookup"><span data-stu-id="77826-242">The `PrimeNumberCalculator` component is now complete and ready to use.</span></span>  
  
 <span data-ttu-id="77826-243">有关使用一个示例客户端`PrimeNumberCalculator`组件，请参阅[如何： 实现基于事件的异步模式的客户端](../../../docs/standard/asynchronous-programming-patterns/how-to-implement-a-client-of-the-event-based-asynchronous-pattern.md)。</span><span class="sxs-lookup"><span data-stu-id="77826-243">For an example client that uses the `PrimeNumberCalculator` component, see [How to: Implement a Client of the Event-based Asynchronous Pattern](../../../docs/standard/asynchronous-programming-patterns/how-to-implement-a-client-of-the-event-based-asynchronous-pattern.md).</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="77826-244">后续步骤</span><span class="sxs-lookup"><span data-stu-id="77826-244">Next Steps</span></span>  
 <span data-ttu-id="77826-245">你可以填写此示例通过编写`CalculatePrime`，同步等效于`CalculatePrimeAsync`方法。</span><span class="sxs-lookup"><span data-stu-id="77826-245">You can fill out this example by writing `CalculatePrime`, the synchronous equivalent of `CalculatePrimeAsync` method.</span></span> <span data-ttu-id="77826-246">这将使`PrimeNumberCalculator`完全符合基于事件的异步模式的组件。</span><span class="sxs-lookup"><span data-stu-id="77826-246">This will make the `PrimeNumberCalculator` component fully compliant with the Event-based Asynchronous Pattern.</span></span>  
  
 <span data-ttu-id="77826-247">您可以通过保留的发现的各种调用不同的测试号码的所有质数列表来改进此示例。</span><span class="sxs-lookup"><span data-stu-id="77826-247">You can improve this example by retaining the list of all the prime numbers discovered by various invocations for different test numbers.</span></span> <span data-ttu-id="77826-248">使用此方法，每个任务将受益于完成前面的任务的工作。</span><span class="sxs-lookup"><span data-stu-id="77826-248">Using this approach, each task will benefit from the work done by previous tasks.</span></span> <span data-ttu-id="77826-249">小心地将其保护与此列表`lock`区域，以便序列化到不同的线程列表的访问。</span><span class="sxs-lookup"><span data-stu-id="77826-249">Be careful to protect this list with `lock` regions, so access to the list by different threads is serialized.</span></span>  
  
 <span data-ttu-id="77826-250">您还可以进行测试，以最小的约数，例如 2、 3 和 5 改善此示例。</span><span class="sxs-lookup"><span data-stu-id="77826-250">You can also improve this example by testing for trivial divisors, like 2, 3, and 5.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="77826-251">另请参阅</span><span class="sxs-lookup"><span data-stu-id="77826-251">See Also</span></span>  
 [<span data-ttu-id="77826-252">如何：在后台运行操作</span><span class="sxs-lookup"><span data-stu-id="77826-252">How to: Run an Operation in the Background</span></span>](../../../docs/framework/winforms/controls/how-to-run-an-operation-in-the-background.md)  
 [<span data-ttu-id="77826-253">基于事件的异步模式概述</span><span class="sxs-lookup"><span data-stu-id="77826-253">Event-based Asynchronous Pattern Overview</span></span>](../../../docs/standard/asynchronous-programming-patterns/event-based-asynchronous-pattern-overview.md)  
 [<span data-ttu-id="77826-254">不在生成中： Visual Basic 中的多线程处理</span><span class="sxs-lookup"><span data-stu-id="77826-254">NOT IN BUILD: Multithreading in Visual Basic</span></span>](http://msdn.microsoft.com/en-us/c731a50c-09c1-4468-9646-54c86b75d269)  
 [<span data-ttu-id="77826-255">如何：实现支持基于事件的异步模式的组件</span><span class="sxs-lookup"><span data-stu-id="77826-255">How to: Implement a Component That Supports the Event-based Asynchronous Pattern</span></span>](../../../docs/standard/asynchronous-programming-patterns/component-that-supports-the-event-based-asynchronous-pattern.md)  
 [<span data-ttu-id="77826-256">使用基于事件的异步模式进行多线程编程</span><span class="sxs-lookup"><span data-stu-id="77826-256">Multithreaded Programming with the Event-based Asynchronous Pattern</span></span>](../../../docs/standard/asynchronous-programming-patterns/multithreaded-programming-with-the-event-based-asynchronous-pattern.md)
