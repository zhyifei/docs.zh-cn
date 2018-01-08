---
title: "如何：接收第一机会异常通知"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-bcl
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- first-chance exception notifications
- exceptions, first chance notifications
ms.assetid: 66f002b8-a97d-4a6e-a503-2cec01689113
caps.latest.revision: "10"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: d8c98f8a1f09488bb2d93c4fda531f695354059a
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-receive-first-chance-exception-notifications"></a><span data-ttu-id="0d9c3-102">如何：接收第一机会异常通知</span><span class="sxs-lookup"><span data-stu-id="0d9c3-102">How to: Receive First-Chance Exception Notifications</span></span>
<span data-ttu-id="0d9c3-103">通过 <xref:System.AppDomain> 类的 <xref:System.AppDomain.FirstChanceException> 事件，可在公共语言运行时开始搜索异常处理程序之前，收到已引发异常的通知。</span><span class="sxs-lookup"><span data-stu-id="0d9c3-103">The <xref:System.AppDomain.FirstChanceException> event of the <xref:System.AppDomain> class lets you receive a notification that an exception has been thrown, before the common language runtime has begun searching for exception handlers.</span></span>  
  
 <span data-ttu-id="0d9c3-104">该事件在应用程序域级别引发。</span><span class="sxs-lookup"><span data-stu-id="0d9c3-104">The event is raised at the application domain level.</span></span> <span data-ttu-id="0d9c3-105">由于执行线程可能经过多个应用程序域，因此可在一个应用程序域中处理另一个应用程序域中未处理的异常。</span><span class="sxs-lookup"><span data-stu-id="0d9c3-105">A thread of execution can pass through multiple application domains, so an exception that is unhandled in one application domain could be handled in another application domain.</span></span> <span data-ttu-id="0d9c3-106">已添加该事件的处理程序的每个应用程序域中均会出现通知，直到某个应用程序域处理该异常。</span><span class="sxs-lookup"><span data-stu-id="0d9c3-106">The notification occurs in each application domain that has added a handler for the event, until an application domain handles the exception.</span></span>  
  
 <span data-ttu-id="0d9c3-107">本文中的过程和示例说明如何在具有一个应用程序域的简单程序中和创建的应用程序域中接收最可能发生的异常通知。</span><span class="sxs-lookup"><span data-stu-id="0d9c3-107">The procedures and examples in this article show how to receive first-chance exception notifications in a simple program that has one application domain, and in an application domain that you create.</span></span>  
  
 <span data-ttu-id="0d9c3-108">有关跨多个应用程序域的更复杂示例，请参阅 <xref:System.AppDomain.FirstChanceException> 事件的示例。</span><span class="sxs-lookup"><span data-stu-id="0d9c3-108">For a more complex example that spans several application domains, see the example for the <xref:System.AppDomain.FirstChanceException> event.</span></span>  
  
## <a name="receiving-first-chance-exception-notifications-in-the-default-application-domain"></a><span data-ttu-id="0d9c3-109">在默认应用程序域中接收最可能发生的异常通知</span><span class="sxs-lookup"><span data-stu-id="0d9c3-109">Receiving First-Chance Exception Notifications in the Default Application Domain</span></span>  
 <span data-ttu-id="0d9c3-110">在以下过程中，应用程序的入口点（`Main()` 方法）在默认应用程序域中运行。</span><span class="sxs-lookup"><span data-stu-id="0d9c3-110">In the following procedure, the entry point for the application, the `Main()` method, runs in the default application domain.</span></span>  
  
#### <a name="to-demonstrate-first-chance-exception-notifications-in-the-default-application-domain"></a><span data-ttu-id="0d9c3-111">在默认应用程序域中演示最可能发生的异常通知</span><span class="sxs-lookup"><span data-stu-id="0d9c3-111">To demonstrate first-chance exception notifications in the default application domain</span></span>  
  
1.  <span data-ttu-id="0d9c3-112">使用 lambda 函数为 <xref:System.AppDomain.FirstChanceException> 事件定义事件处理程序，并将其附加到此事件。</span><span class="sxs-lookup"><span data-stu-id="0d9c3-112">Define an event handler for the <xref:System.AppDomain.FirstChanceException> event, using a lambda function, and attach it to the event.</span></span> <span data-ttu-id="0d9c3-113">在此示例中，事件处理程序输出了在其中处理事件的应用程序域的名称和异常的 <xref:System.Exception.Message%2A> 属性。</span><span class="sxs-lookup"><span data-stu-id="0d9c3-113">In this example, the event handler prints the name of the application domain where the event was handled and the exception's <xref:System.Exception.Message%2A> property.</span></span>  
  
     [!code-csharp[System.AppDomain.FirstChanceException_howto_simple#2](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.appdomain.firstchanceexception_howto_simple/cs/example.cs#2)]
     [!code-vb[System.AppDomain.FirstChanceException_howto_simple#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.appdomain.firstchanceexception_howto_simple/vb/example.vb#2)]  
  
2.  <span data-ttu-id="0d9c3-114">引发异常并将其捕获。</span><span class="sxs-lookup"><span data-stu-id="0d9c3-114">Throw an exception and catch it.</span></span> <span data-ttu-id="0d9c3-115">在运行时找到异常处理程序之前，引发 <xref:System.AppDomain.FirstChanceException> 事件并显示一条消息。</span><span class="sxs-lookup"><span data-stu-id="0d9c3-115">Before the runtime locates the exception handler, the <xref:System.AppDomain.FirstChanceException> event is raised and displays a message.</span></span> <span data-ttu-id="0d9c3-116">此消息后跟由异常处理程序显示的消息。</span><span class="sxs-lookup"><span data-stu-id="0d9c3-116">This message is followed by the message that is displayed by the exception handler.</span></span>  
  
     [!code-csharp[System.AppDomain.FirstChanceException_howto_simple#3](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.appdomain.firstchanceexception_howto_simple/cs/example.cs#3)]
     [!code-vb[System.AppDomain.FirstChanceException_howto_simple#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.appdomain.firstchanceexception_howto_simple/vb/example.vb#3)]  
  
3.  <span data-ttu-id="0d9c3-117">引发异常，但不将其捕获。</span><span class="sxs-lookup"><span data-stu-id="0d9c3-117">Throw an exception, but do not catch it.</span></span> <span data-ttu-id="0d9c3-118">在运行时查找异常处理程序之前，引发 <xref:System.AppDomain.FirstChanceException> 事件并显示一条消息。</span><span class="sxs-lookup"><span data-stu-id="0d9c3-118">Before the runtime looks for an exception handler, the <xref:System.AppDomain.FirstChanceException> event is raised and displays a message.</span></span> <span data-ttu-id="0d9c3-119">由于没有任何异常处理程序，因此应用程序将终止。</span><span class="sxs-lookup"><span data-stu-id="0d9c3-119">There is no exception handler, so the application terminates.</span></span>  
  
     [!code-csharp[System.AppDomain.FirstChanceException_howto_simple#4](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.appdomain.firstchanceexception_howto_simple/cs/example.cs#4)]
     [!code-vb[System.AppDomain.FirstChanceException_howto_simple#4](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.appdomain.firstchanceexception_howto_simple/vb/example.vb#4)]  
  
     <span data-ttu-id="0d9c3-120">此过程前 3 个步骤中显示的代码构成了一个完整的控制台应用程序。</span><span class="sxs-lookup"><span data-stu-id="0d9c3-120">The code that is shown in the first three steps of this procedure forms a complete console application.</span></span> <span data-ttu-id="0d9c3-121">应用程序的输出因 .exe 文件的名称而异，因为默认应用程序域的名称是由 .exe 文件的名称和扩展名组成的。</span><span class="sxs-lookup"><span data-stu-id="0d9c3-121">The output from the application varies, depending on the name of the .exe file, because the name of the default application domain consists of the name and extension of the .exe file.</span></span> <span data-ttu-id="0d9c3-122">有关示例输出，请参阅以下内容。</span><span class="sxs-lookup"><span data-stu-id="0d9c3-122">See the following for sample output.</span></span>  
  
     [!code-csharp[System.AppDomain.FirstChanceException_howto_simple#5](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.appdomain.firstchanceexception_howto_simple/cs/example.cs#5)]
     [!code-vb[System.AppDomain.FirstChanceException_howto_simple#5](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.appdomain.firstchanceexception_howto_simple/vb/example.vb#5)]  
  
## <a name="receiving-first-chance-exception-notifications-in-another-application-domain"></a><span data-ttu-id="0d9c3-123">在另一个应用程序域中接收最可能发生的异常通知</span><span class="sxs-lookup"><span data-stu-id="0d9c3-123">Receiving First-Chance Exception Notifications in Another Application Domain</span></span>  
 <span data-ttu-id="0d9c3-124">如果程序包含多个应用程序域，则可选择用于接收通知的应用程序域。</span><span class="sxs-lookup"><span data-stu-id="0d9c3-124">If your program contains more than one application domain, you can choose which application domains receive notifications.</span></span>  
  
#### <a name="to-receive-first-chance-exception-notifications-in-an-application-domain-that-you-create"></a><span data-ttu-id="0d9c3-125">在创建的应用程序域中接收最可能发生的异常通知</span><span class="sxs-lookup"><span data-stu-id="0d9c3-125">To receive first-chance exception notifications in an application domain that you create</span></span>  
  
1.  <span data-ttu-id="0d9c3-126">为 <xref:System.AppDomain.FirstChanceException> 事件定义事件处理程序。</span><span class="sxs-lookup"><span data-stu-id="0d9c3-126">Define an event handler for the <xref:System.AppDomain.FirstChanceException> event.</span></span> <span data-ttu-id="0d9c3-127">此示例使用 `static` 方法（在 Visual Basic 中为 `Shared` 方法），该方法可输出在其中处理事件的应用程序域的名称和异常的 <xref:System.Exception.Message%2A> 属性。</span><span class="sxs-lookup"><span data-stu-id="0d9c3-127">This example uses a `static` method (`Shared` method in Visual Basic) that prints the name of the application domain where the event was handled and the exception's <xref:System.Exception.Message%2A> property.</span></span>  
  
     [!code-csharp[System.AppDomain.FirstChanceException_howto#3](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.appdomain.firstchanceexception_howto/cs/example.cs#3)]
     [!code-vb[System.AppDomain.FirstChanceException_howto#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.appdomain.firstchanceexception_howto/vb/example.vb#3)]  
  
2.  <span data-ttu-id="0d9c3-128">创建一个应用程序域，并为该应用程序域的 <xref:System.AppDomain.FirstChanceException> 事件添加事件处理程序。</span><span class="sxs-lookup"><span data-stu-id="0d9c3-128">Create an application domain and add the event handler to the <xref:System.AppDomain.FirstChanceException> event for that application domain.</span></span> <span data-ttu-id="0d9c3-129">在此示例中，该应用程序域的名称为 `AD1`。</span><span class="sxs-lookup"><span data-stu-id="0d9c3-129">In this example, the application domain is named `AD1`.</span></span>  
  
     [!code-csharp[System.AppDomain.FirstChanceException_howto#2](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.appdomain.firstchanceexception_howto/cs/example.cs#2)]
     [!code-vb[System.AppDomain.FirstChanceException_howto#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.appdomain.firstchanceexception_howto/vb/example.vb#2)]  
  
     <span data-ttu-id="0d9c3-130">可按照相同的方式在默认应用程序域中处理此事件。</span><span class="sxs-lookup"><span data-stu-id="0d9c3-130">You can handle this event in the default application domain in the same way.</span></span> <span data-ttu-id="0d9c3-131">使用 `Main()` 中的 `static`（在 Visual Basic 中为 `Shared`）<xref:System.AppDomain.CurrentDomain%2A?displayProperty=nameWithType> 属性可获取对默认应用程序域的引用。</span><span class="sxs-lookup"><span data-stu-id="0d9c3-131">Use the `static` (`Shared` in Visual Basic) <xref:System.AppDomain.CurrentDomain%2A?displayProperty=nameWithType> property in `Main()` to get a reference to the default application domain.</span></span>  
  
#### <a name="to-demonstrate-first-chance-exception-notifications-in-the-application-domain"></a><span data-ttu-id="0d9c3-132">在应用程序域中演示最可能发生的异常通知</span><span class="sxs-lookup"><span data-stu-id="0d9c3-132">To demonstrate first-chance exception notifications in the application domain</span></span>  
  
1.  <span data-ttu-id="0d9c3-133">在上一过程创建的应用程序域中创建一个 `Worker` 对象。</span><span class="sxs-lookup"><span data-stu-id="0d9c3-133">Create a `Worker` object in the application domain that you created in the previous procedure.</span></span> <span data-ttu-id="0d9c3-134">`Worker` 类必须是公共的，且派生自 <xref:System.MarshalByRefObject>，如本文末尾的完整示例中所示。</span><span class="sxs-lookup"><span data-stu-id="0d9c3-134">The `Worker` class must be public, and must derive from <xref:System.MarshalByRefObject>, as shown in the complete example at the end of this article.</span></span>  
  
     [!code-csharp[System.AppDomain.FirstChanceException_howto#4](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.appdomain.firstchanceexception_howto/cs/example.cs#4)]
     [!code-vb[System.AppDomain.FirstChanceException_howto#4](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.appdomain.firstchanceexception_howto/vb/example.vb#4)]  
  
2.  <span data-ttu-id="0d9c3-135">调用 `Worker` 对象的一个可引发异常的方法。</span><span class="sxs-lookup"><span data-stu-id="0d9c3-135">Call a method of the `Worker` object that throws an exception.</span></span> <span data-ttu-id="0d9c3-136">在此示例中，调用了两次 `Thrower` 方法。</span><span class="sxs-lookup"><span data-stu-id="0d9c3-136">In this example, the `Thrower` method is called twice.</span></span> <span data-ttu-id="0d9c3-137">第一次调用时，该方法的参数为 `true`，这使该方法捕获自己的异常。</span><span class="sxs-lookup"><span data-stu-id="0d9c3-137">The first time, the method argument is `true`, which causes the method to catch its own exception.</span></span> <span data-ttu-id="0d9c3-138">第二次调用时，该方法的参数为 `false`，并且 `Main()` 方法捕获默认应用程序域中的异常。</span><span class="sxs-lookup"><span data-stu-id="0d9c3-138">The second time, the argument is `false`, and the `Main()` method catches the exception in the default application domain.</span></span>  
  
     [!code-csharp[System.AppDomain.FirstChanceException_howto#6](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.appdomain.firstchanceexception_howto/cs/example.cs#6)]
     [!code-vb[System.AppDomain.FirstChanceException_howto#6](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.appdomain.firstchanceexception_howto/vb/example.vb#6)]  
  
3.  <span data-ttu-id="0d9c3-139">在 `Thrower` 方法中放置代码以控制该方法是否处理自己的异常。</span><span class="sxs-lookup"><span data-stu-id="0d9c3-139">Place code in the `Thrower` method to control whether the method handles its own exception.</span></span>  
  
     [!code-csharp[System.AppDomain.FirstChanceException_howto#5](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.appdomain.firstchanceexception_howto/cs/example.cs#5)]
     [!code-vb[System.AppDomain.FirstChanceException_howto#5](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.appdomain.firstchanceexception_howto/vb/example.vb#5)]  
  
## <a name="example"></a><span data-ttu-id="0d9c3-140">示例</span><span class="sxs-lookup"><span data-stu-id="0d9c3-140">Example</span></span>  
 <span data-ttu-id="0d9c3-141">下例创建一个名为 `AD1` 的应用程序域，并向该应用程序域的 <xref:System.AppDomain.FirstChanceException> 事件添加一个事件处理程序。</span><span class="sxs-lookup"><span data-stu-id="0d9c3-141">The following example creates an application domain named `AD1` and adds an event handler to the application domain's <xref:System.AppDomain.FirstChanceException> event.</span></span> <span data-ttu-id="0d9c3-142">此示例还会在应用程序域中创建 `Worker` 类的一个实例，并调用名为 `Thrower` 的方法，该方法将引发 <xref:System.ArgumentException>。</span><span class="sxs-lookup"><span data-stu-id="0d9c3-142">The example creates an instance of the `Worker` class in the application domain, and calls a method named `Thrower` that throws an <xref:System.ArgumentException>.</span></span> <span data-ttu-id="0d9c3-143">该方法可能会捕获异常，也可能无法处理异常，具体取决于其参数的值。</span><span class="sxs-lookup"><span data-stu-id="0d9c3-143">Depending on the value of its argument, the method either catches the exception or fails to handle it.</span></span>  
  
 <span data-ttu-id="0d9c3-144">每当 `Thrower` 方法在 `AD1` 中引发异常时，`AD1` 中就会引发 <xref:System.AppDomain.FirstChanceException> 事件，并且事件处理程序会显示一条消息。</span><span class="sxs-lookup"><span data-stu-id="0d9c3-144">Each time the `Thrower` method throws an exception in `AD1`, the <xref:System.AppDomain.FirstChanceException> event is raised in `AD1`, and the event handler displays a message.</span></span> <span data-ttu-id="0d9c3-145">然后，运行时将查找异常处理程序。</span><span class="sxs-lookup"><span data-stu-id="0d9c3-145">The runtime then looks for an exception handler.</span></span> <span data-ttu-id="0d9c3-146">在第一种情况下，可在 `AD1` 中找到异常处理程序。</span><span class="sxs-lookup"><span data-stu-id="0d9c3-146">In the first case, the exception handler is found in `AD1`.</span></span> <span data-ttu-id="0d9c3-147">在第二种情况下，不会在 `AD1` 中处理异常，而是在默认应用程序域中捕获异常。</span><span class="sxs-lookup"><span data-stu-id="0d9c3-147">In the second case, the exception is unhandled in `AD1`, and instead is caught in the default application domain.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="0d9c3-148">默认应用程序域的名称与可执行文件的名称相同。</span><span class="sxs-lookup"><span data-stu-id="0d9c3-148">The name of the default application domain is the same as the name of the executable.</span></span>  
  
 <span data-ttu-id="0d9c3-149">如果将 <xref:System.AppDomain.FirstChanceException> 事件的处理程序添加到默认应用程序域，则在默认应用程序域处理异常之前，系统将引发并处理该事件。</span><span class="sxs-lookup"><span data-stu-id="0d9c3-149">If you add a handler for the <xref:System.AppDomain.FirstChanceException> event to the default application domain, the event is raised and handled before the default application domain handles the exception.</span></span> <span data-ttu-id="0d9c3-150">为此，请将 C# 代码 `AppDomain.CurrentDomain.FirstChanceException += FirstChanceException;`（在 Visual Basic 中为 `AddHandler AppDomain.CurrentDomain.FirstChanceException, FirstChanceException`）添加到 `Main()` 的开头。</span><span class="sxs-lookup"><span data-stu-id="0d9c3-150">To see this, add the C# code `AppDomain.CurrentDomain.FirstChanceException += FirstChanceException;` (in Visual Basic, `AddHandler AppDomain.CurrentDomain.FirstChanceException, FirstChanceException`) at the beginning of `Main()`.</span></span>  
  
 [!code-csharp[System.AppDomain.FirstChanceException_howto#1](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.appdomain.firstchanceexception_howto/cs/example.cs#1)]
 [!code-vb[System.AppDomain.FirstChanceException_howto#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.appdomain.firstchanceexception_howto/vb/example.vb#1)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="0d9c3-151">编译代码</span><span class="sxs-lookup"><span data-stu-id="0d9c3-151">Compiling the Code</span></span>  
  
-   <span data-ttu-id="0d9c3-152">此示例是一个命令行应用程序。</span><span class="sxs-lookup"><span data-stu-id="0d9c3-152">This example is a command-line application.</span></span> <span data-ttu-id="0d9c3-153">若要在 [!INCLUDE[vs_dev10_long](../../../includes/vs-dev10-long-md.md)] 中编译并运行此代码，请将 C# 代码 `Console.ReadLine();`（在 Visual Basic 中为 `Console.ReadLine()`）添加到 `Main()` 的末尾，阻止命令窗口在你查看输出之前关闭。</span><span class="sxs-lookup"><span data-stu-id="0d9c3-153">To compile and run this code in [!INCLUDE[vs_dev10_long](../../../includes/vs-dev10-long-md.md)], add the C# code `Console.ReadLine();` (in Visual Basic, `Console.ReadLine()`) at the end of `Main()`, to prevent the command window from closing before you can read the output.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0d9c3-154">请参阅</span><span class="sxs-lookup"><span data-stu-id="0d9c3-154">See Also</span></span>  
 <xref:System.AppDomain.FirstChanceException>
