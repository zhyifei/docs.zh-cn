---
title: 由于不等待此调用，因此在调用完成之前，当前方法将继续运行
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- bc42358
- vbc42358
helpviewer_keywords:
- BC42358
ms.assetid: 43342515-c3c8-4155-9263-c302afabcbc2
caps.latest.revision: 8
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: a0d0a5e7c50bacc657a3f54a7f08036ede59cbfa
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="because-this-call-is-not-awaited-the-current-method-continues-to-run-before-the-call-is-completed"></a><span data-ttu-id="3f035-102">由于不等待此调用，因此在调用完成之前，当前方法将继续运行</span><span class="sxs-lookup"><span data-stu-id="3f035-102">Because this call is not awaited, the current method continues to run before the call is completed</span></span>
<span data-ttu-id="3f035-103">在调用完成之前，会继续执行当前方法，原因是此调用不处于等待状态。</span><span class="sxs-lookup"><span data-stu-id="3f035-103">Because this call is not awaited, execution of the current method continues before the call is completed.</span></span> <span data-ttu-id="3f035-104">请考虑向调用结果应用“Await”运算符。</span><span class="sxs-lookup"><span data-stu-id="3f035-104">Consider applying the 'Await' operator to the result of the call.</span></span>  
  
 <span data-ttu-id="3f035-105">当前方法调用返回 <xref:System.Threading.Tasks.Task> 或 <xref:System.Threading.Tasks.Task%601> 的异步方法，而不对结果应用 [Await](../../../visual-basic/language-reference/operators/await-operator.md) 运算符。</span><span class="sxs-lookup"><span data-stu-id="3f035-105">The current method calls an async method that returns a <xref:System.Threading.Tasks.Task> or a <xref:System.Threading.Tasks.Task%601> and doesn’t apply the [Await](../../../visual-basic/language-reference/operators/await-operator.md) operator to the result.</span></span> <span data-ttu-id="3f035-106">对异步方法的调用会启动异步任务。</span><span class="sxs-lookup"><span data-stu-id="3f035-106">The call to the async method starts an asynchronous task.</span></span> <span data-ttu-id="3f035-107">但是，由于没有应用 `Await` 运算符，程序将继续运行，而不必等待任务完成。</span><span class="sxs-lookup"><span data-stu-id="3f035-107">However, because no `Await` operator is applied, the program continues without waiting for the task to complete.</span></span> <span data-ttu-id="3f035-108">在大多数情况下，此行为并不是你所期望的。</span><span class="sxs-lookup"><span data-stu-id="3f035-108">In most cases, that behavior isn't expected.</span></span> <span data-ttu-id="3f035-109">方法调用的其他方面通常取决于调用的结果，而调用的方法至少应在从包含调用的方法返回之前完成。</span><span class="sxs-lookup"><span data-stu-id="3f035-109">Usually other aspects of the calling method depend on the results of the call or, minimally, the called method is expected to complete before you return from the method that contains the call.</span></span>  
  
 <span data-ttu-id="3f035-110">对于被调用的异步方法中引发的异常，如何进行处理同样是一个重要的问题。</span><span class="sxs-lookup"><span data-stu-id="3f035-110">An equally important issue is what happens with exceptions that are raised in the called async method.</span></span> <span data-ttu-id="3f035-111">在返回 <xref:System.Threading.Tasks.Task> 或  <xref:System.Threading.Tasks.Task%601> 的方法中引发的异常将存储在返回的任务中。</span><span class="sxs-lookup"><span data-stu-id="3f035-111">An exception that’s raised in a method that returns a <xref:System.Threading.Tasks.Task> or  <xref:System.Threading.Tasks.Task%601> is stored in the returned task.</span></span> <span data-ttu-id="3f035-112">如果不等待任务或不显式检查异常，该异常会丢失。</span><span class="sxs-lookup"><span data-stu-id="3f035-112">If you don't await the task or explicitly check for exceptions, the exception is lost.</span></span> <span data-ttu-id="3f035-113">如果等待任务，将重新引发异常。</span><span class="sxs-lookup"><span data-stu-id="3f035-113">If you await the task, its exception is rethrown.</span></span>  
  
 <span data-ttu-id="3f035-114">作为最佳做法，应始终等待调用。</span><span class="sxs-lookup"><span data-stu-id="3f035-114">As a best practice, you should always await the call.</span></span>  
  
 <span data-ttu-id="3f035-115">默认情况下，此消息是一个警告。</span><span class="sxs-lookup"><span data-stu-id="3f035-115">By default, this message is a warning.</span></span> <span data-ttu-id="3f035-116">有关隐藏警告或将警告视为错误的详细信息，请参阅[在 Visual Basic 中的配置警告](/visualstudio/ide/configuring-warnings-in-visual-basic)。</span><span class="sxs-lookup"><span data-stu-id="3f035-116">For more information about hiding warnings or treating warnings as errors, see [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).</span></span>  
  
 <span data-ttu-id="3f035-117">**错误 ID：** BC42358</span><span class="sxs-lookup"><span data-stu-id="3f035-117">**Error ID:** BC42358</span></span>  
  
### <a name="to-address-this-warning"></a><span data-ttu-id="3f035-118">解决此警告</span><span class="sxs-lookup"><span data-stu-id="3f035-118">To address this warning</span></span>  
  
-   <span data-ttu-id="3f035-119">只有当您确定不需要等待异步调用完成并且调用的方法不会引发任何异常时，才应考虑禁止显示警告。</span><span class="sxs-lookup"><span data-stu-id="3f035-119">You should consider suppressing the warning only if you're sure that you don't want to wait for the asynchronous call to complete and that the called method won't raise any exceptions.</span></span> <span data-ttu-id="3f035-120">在此情况下，可以通过将调用的任务结果分配给变量来禁止显示警告。</span><span class="sxs-lookup"><span data-stu-id="3f035-120">In that case, you can suppress the warning by assigning the task result of the call to a variable.</span></span>  
  
     <span data-ttu-id="3f035-121">下面的示例演示如何生成警告，如何禁止显示警告以及如何等待调用。</span><span class="sxs-lookup"><span data-stu-id="3f035-121">The following example shows how to cause the warning, how to suppress it, and how to await the call.</span></span>  
  
    ```vb  
    Async Function CallingMethodAsync() As Task  
  
        ResultsTextBox.Text &= vbCrLf & "  Entering calling method."  
  
        ' Variable delay is used to slow down the called method so that you  
        ' can distinguish between awaiting and not awaiting in the program's output.   
        ' You can adjust the value to produce the output that this topic shows   
        ' after the code.  
        Dim delay = 5000  
  
        ' Call #1.  
        ' Call an async method. Because you don't await it, its completion isn't   
        ' coordinated with the current method, CallingMethodAsync.  
        ' The following line causes the warning.  
        CalledMethodAsync(delay)  
  
        ' Call #2.  
        ' To suppress the warning without awaiting, you can assign the   
        ' returned task to a variable. The assignment doesn't change how  
        ' the program runs. However, the recommended practice is always to  
        ' await a call to an async method.  
        ' Replace Call #1 with the following line.  
        'Task delayTask = CalledMethodAsync(delay)  
  
        ' Call #3  
        ' To contrast with an awaited call, replace the unawaited call   
        ' (Call #1 or Call #2) with the following awaited call. The best   
        ' practice is to await the call.  
  
        'Await CalledMethodAsync(delay)  
  
        ' If the call to CalledMethodAsync isn't awaited, CallingMethodAsync  
        ' continues to run and, in this example, finishes its work and returns  
        ' to its caller.  
        ResultsTextBox.Text &= vbCrLf & "  Returning from calling method."  
    End Function  
  
    Async Function CalledMethodAsync(howLong As Integer) As Task  
  
        ResultsTextBox.Text &= vbCrLf & "    Entering called method, starting and awaiting Task.Delay."  
        ' Slow the process down a little so you can distinguish between awaiting  
        ' and not awaiting. Adjust the value for howLong if necessary.  
        Await Task.Delay(howLong)  
        ResultsTextBox.Text &= vbCrLf & "    Task.Delay is finished--returning from called method."  
    End Function  
    ```  
  
     <span data-ttu-id="3f035-122">在此示例中，如果选择调用 1 或调用 2，未等待的异步方法 (`CalledMethodAsync`) 将在调用方 (`CallingMethodAsync`) 和调用方的调用方 (`StartButton_Click`) 完成后完成。</span><span class="sxs-lookup"><span data-stu-id="3f035-122">In the example, if you choose Call #1 or Call #2, the unawaited async method (`CalledMethodAsync`) finishes after both its caller (`CallingMethodAsync`) and the caller's caller (`StartButton_Click`) are complete.</span></span> <span data-ttu-id="3f035-123">以下输出的最后一行演示了调用的方法何时完成。</span><span class="sxs-lookup"><span data-stu-id="3f035-123">The last line in the following output shows you when the called method finishes.</span></span> <span data-ttu-id="3f035-124">输出内容标示了整个示例中何时进入和退出调用 `CallingMethodAsync` 的事件处理程序。</span><span class="sxs-lookup"><span data-stu-id="3f035-124">Entry to and exit from the event handler that calls `CallingMethodAsync` in the full example are marked in the output.</span></span>  
  
    ```  
    Entering the Click event handler.  
      Entering calling method.  
        Entering called method, starting and awaiting Task.Delay.  
      Returning from calling method.  
    Exiting the Click event handler.  
        Task.Delay is finished--returning from called method.  
    ```  
  
## <a name="example"></a><span data-ttu-id="3f035-125">示例</span><span class="sxs-lookup"><span data-stu-id="3f035-125">Example</span></span>  
 <span data-ttu-id="3f035-126">以下 Windows Presentation Foundation (WPF) 应用程序包含上一示例中的方法。</span><span class="sxs-lookup"><span data-stu-id="3f035-126">The following Windows Presentation Foundation (WPF) application contains the methods from the previous example.</span></span> <span data-ttu-id="3f035-127">下列步骤用于设置该应用程序。</span><span class="sxs-lookup"><span data-stu-id="3f035-127">The following steps set up the application.</span></span>  
  
1.  <span data-ttu-id="3f035-128">创建一个 WPF 应用程序，将其命名为 `AsyncWarning`。</span><span class="sxs-lookup"><span data-stu-id="3f035-128">Create a WPF application, and name it `AsyncWarning`.</span></span>  
  
2.  <span data-ttu-id="3f035-129">在 Visual Studio 代码编辑器中，选择 **“MainWindow.xaml”** 选项卡。</span><span class="sxs-lookup"><span data-stu-id="3f035-129">In the Visual Studio Code Editor, choose the **MainWindow.xaml** tab.</span></span>  
  
     <span data-ttu-id="3f035-130">如果此选项卡不可见，则在解决方案资源管理器 中，打开 MainWindow.xaml 的快捷菜单，然后选择“查看代码” 。</span><span class="sxs-lookup"><span data-stu-id="3f035-130">If the tab isn't visible, open the shortcut menu for MainWindow.xaml in **Solution Explorer**, and then choose **View Code**.</span></span>  
  
3.  <span data-ttu-id="3f035-131">在“XAML”  视图中，将 MainWindow.xaml 的代码替换为下面的代码。</span><span class="sxs-lookup"><span data-stu-id="3f035-131">Replace the code in the **XAML** view of MainWindow.xaml with the following code.</span></span>  
  
    ```vb  
    <Window x:Class="MainWindow"  
            xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"  
            xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"  
            Title="MainWindow" Height="350" Width="525">  
        <Grid>  
            <Button x:Name="StartButton" Content="Start" HorizontalAlignment="Left" Margin="214,28,0,0" VerticalAlignment="Top" Width="75" HorizontalContentAlignment="Center" FontWeight="Bold" FontFamily="Aharoni" Click="StartButton_Click" />  
            <TextBox x:Name="ResultsTextBox" Margin="0,80,0,0" TextWrapping="Wrap" FontFamily="Lucida Console"/>  
        </Grid>  
    </Window>  
    ```  
  
     <span data-ttu-id="3f035-132">MainWindow.xaml 的“设计”  视图中将显示一个简单的窗口，其中包含一个按钮和一个文本框。</span><span class="sxs-lookup"><span data-stu-id="3f035-132">A simple window that contains a button and a text box appears in the **Design** view of MainWindow.xaml.</span></span>  
  
     <span data-ttu-id="3f035-133">有关 XAML 设计器的详细信息，请参阅[使用 XAML 设计器创建 UI](/visualstudio/designers/creating-a-ui-by-using-xaml-designer-in-visual-studio)。</span><span class="sxs-lookup"><span data-stu-id="3f035-133">For more information about the XAML Designer, see [Creating a UI by using XAML Designer](/visualstudio/designers/creating-a-ui-by-using-xaml-designer-in-visual-studio).</span></span> <span data-ttu-id="3f035-134">有关如何自行生成简单 UI 的信息，请参阅[演练：使用 Async 和 Await 访问 Web](http://msdn.microsoft.com/library/25879a6d-fdee-4a38-bc98-bb8c24d16042)的“创建 WPF 应用程序的步骤”和“设计简单的 WPF MainWindow 的步骤”两个章节。</span><span class="sxs-lookup"><span data-stu-id="3f035-134">For information about how to build your own simple UI, see the "To create a WPF application" and "To design a simple WPF MainWindow" sections of [Walkthrough: Accessing the Web by Using Async and Await](http://msdn.microsoft.com/library/25879a6d-fdee-4a38-bc98-bb8c24d16042).</span></span>  
  
4.  <span data-ttu-id="3f035-135">将 MainWindow.xaml.vb 中的代码替换为以下代码。</span><span class="sxs-lookup"><span data-stu-id="3f035-135">Replace the code in MainWindow.xaml.vb with the following code.</span></span>  
  
    ```vb  
    Class MainWindow   
  
        Private Async Sub StartButton_Click(sender As Object, e As RoutedEventArgs)  
  
            ResultsTextBox.Text &= vbCrLf & "Entering the Click event handler."  
            Await CallingMethodAsync()  
            ResultsTextBox.Text &= vbCrLf & "Exiting the Click event handler."  
        End Sub  
  
        Async Function CallingMethodAsync() As Task  
  
            ResultsTextBox.Text &= vbCrLf & "  Entering calling method."  
  
            ' Variable delay is used to slow down the called method so that you  
            ' can distinguish between awaiting and not awaiting in the program's output.   
            ' You can adjust the value to produce the output that this topic shows   
            ' after the code.  
            Dim delay = 5000  
  
            ' Call #1.  
            ' Call an async method. Because you don't await it, its completion isn't   
            ' coordinated with the current method, CallingMethodAsync.  
            ' The following line causes the warning.  
            CalledMethodAsync(delay)  
  
            ' Call #2.  
            ' To suppress the warning without awaiting, you can assign the   
            ' returned task to a variable. The assignment doesn't change how  
            ' the program runs. However, the recommended practice is always to  
            ' await a call to an async method.  
  
            ' Replace Call #1 with the following line.  
            'Task delayTask = CalledMethodAsync(delay)  
  
            ' Call #3  
            ' To contrast with an awaited call, replace the unawaited call   
            ' (Call #1 or Call #2) with the following awaited call. The best   
            ' practice is to await the call.  
  
            'Await CalledMethodAsync(delay)  
  
            ' If the call to CalledMethodAsync isn't awaited, CallingMethodAsync  
            ' continues to run and, in this example, finishes its work and returns  
            ' to its caller.  
            ResultsTextBox.Text &= vbCrLf & "  Returning from calling method."  
        End Function  
  
        Async Function CalledMethodAsync(howLong As Integer) As Task  
  
            ResultsTextBox.Text &= vbCrLf & "    Entering called method, starting and awaiting Task.Delay."  
            ' Slow the process down a little so you can distinguish between awaiting  
            ' and not awaiting. Adjust the value for howLong if necessary.  
            Await Task.Delay(howLong)  
            ResultsTextBox.Text &= vbCrLf & "    Task.Delay is finished--returning from called method."  
        End Function  
  
    End Class  
  
    ' Output  
  
    ' Entering the Click event handler.  
    '   Entering calling method.  
    '     Entering called method, starting and awaiting Task.Delay.  
    '   Returning from calling method.  
    ' Exiting the Click event handler.  
    '     Task.Delay is finished--returning from called method.  
  
    ' Output  
  
    ' Entering the Click event handler.  
    '   Entering calling method.  
    '     Entering called method, starting and awaiting Task.Delay.  
    '     Task.Delay is finished--returning from called method.  
    '   Returning from calling method.  
    ' Exiting the Click event handler.  
    ```  
  
5.  <span data-ttu-id="3f035-136">按 F5 键以运行程序，然后选择 **“启动”** 按钮。</span><span class="sxs-lookup"><span data-stu-id="3f035-136">Choose the F5 key to run the program, and then choose the **Start** button.</span></span>  
  
     <span data-ttu-id="3f035-137">预期的输出显示在代码末尾。</span><span class="sxs-lookup"><span data-stu-id="3f035-137">The expected output appears at the end of the code.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3f035-138">另请参阅</span><span class="sxs-lookup"><span data-stu-id="3f035-138">See Also</span></span>  
 [<span data-ttu-id="3f035-139">Await 运算符</span><span class="sxs-lookup"><span data-stu-id="3f035-139">Await Operator</span></span>](../../../visual-basic/language-reference/operators/await-operator.md)  
 [<span data-ttu-id="3f035-140">使用 Async 和 Await 的异步编程</span><span class="sxs-lookup"><span data-stu-id="3f035-140">Asynchronous Programming with Async and Await</span></span>](../../../visual-basic/programming-guide/concepts/async/index.md)
