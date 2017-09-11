---
title: "异步返回类型 (Visual Basic 中) |Microsoft 文档"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
ms.assetid: 07890291-ee72-42d3-932a-fa4d312f2c60
caps.latest.revision: 3
author: stevehoag
ms.author: shoag
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: 703d3fc3f503017edf38521d77f9b15a92d0ebf3
ms.contentlocale: zh-cn
ms.lasthandoff: 03/13/2017

---
# <a name="async-return-types-visual-basic"></a><span data-ttu-id="12635-102">异步返回类型 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="12635-102">Async Return Types (Visual Basic)</span></span>
<span data-ttu-id="12635-103">Async 方法具有三个可能的返回类型︰ <xref:System.Threading.Tasks.Task%601>， <xref:System.Threading.Tasks.Task>，和 void。</xref:System.Threading.Tasks.Task> </xref:System.Threading.Tasks.Task%601></span><span class="sxs-lookup"><span data-stu-id="12635-103">Async methods have three possible return types: <xref:System.Threading.Tasks.Task%601>, <xref:System.Threading.Tasks.Task>, and void.</span></span> <span data-ttu-id="12635-104">在 Visual Basic 中形式写入 void 返回类型[Sub](../../../../visual-basic/programming-guide/language-features/procedures/sub-procedures.md)过程。</span><span class="sxs-lookup"><span data-stu-id="12635-104">In Visual Basic, the void return type is written as a [Sub](../../../../visual-basic/programming-guide/language-features/procedures/sub-procedures.md) procedure.</span></span> <span data-ttu-id="12635-105">有关异步方法的详细信息，请参阅[使用 Async 和 Await (Visual Basic 中) 的异步编程](../../../../visual-basic/programming-guide/concepts/async/index.md)。</span><span class="sxs-lookup"><span data-stu-id="12635-105">For more information about async methods, see [Asynchronous Programming with Async and Await (Visual Basic)](../../../../visual-basic/programming-guide/concepts/async/index.md).</span></span>  
  
 <span data-ttu-id="12635-106">在以下其中一节检查每个返回类型，且在本主题末尾可以找到使用全部三种类型的完整示例。</span><span class="sxs-lookup"><span data-stu-id="12635-106">Each return type is examined in one of the following sections, and you can find a full example that uses all three types at the end of the topic.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="12635-107">若要运行该示例，必须具有 Visual Studio 2012 或更高版本和.NET Framework 4.5 或更高版本安装在您的计算机上。</span><span class="sxs-lookup"><span data-stu-id="12635-107">To run the example, you must have Visual Studio 2012 or newer and the .NET Framework 4.5 or newer installed on your computer.</span></span>  
  
##  <span data-ttu-id="12635-108"><a name="BKMK_TaskTReturnType"></a>Task （t） 返回类型</span><span class="sxs-lookup"><span data-stu-id="12635-108"><a name="BKMK_TaskTReturnType"></a> Task(T) Return Type</span></span>  
 <span data-ttu-id="12635-109"><xref:System.Threading.Tasks.Task%601>返回类型可用于异步方法，其中包含[返回](../../../../visual-basic/language-reference/statements/return-statement.md)语句，则该操作数类型`TResult`。</xref:System.Threading.Tasks.Task%601></span><span class="sxs-lookup"><span data-stu-id="12635-109">The <xref:System.Threading.Tasks.Task%601> return type is used for an async method that contains a [Return](../../../../visual-basic/language-reference/statements/return-statement.md) statement in which the operand has type `TResult`.</span></span>  
  
 <span data-ttu-id="12635-110">在下面的示例中，`TaskOfT_MethodAsync`异步方法包含的 return 语句，返回一个整数。</span><span class="sxs-lookup"><span data-stu-id="12635-110">In the following example, the `TaskOfT_MethodAsync` async method contains a return statement that returns an integer.</span></span> <span data-ttu-id="12635-111">因此，该方法声明必须指定返回类型为`Task(Of Integer)`。</span><span class="sxs-lookup"><span data-stu-id="12635-111">Therefore, the method declaration must specify a return type of `Task(Of Integer)`.</span></span>  
  
```vb  
' TASK(OF T) EXAMPLE  
Async Function TaskOfT_MethodAsync() As Task(Of Integer)  
  
    ' The body of an async method is expected to contain an awaited   
    ' asynchronous call.  
    ' Task.FromResult is a placeholder for actual work that returns a string.  
    Dim today As String = Await Task.FromResult(Of String)(DateTime.Now.DayOfWeek.ToString())  
  
    ' The method then can process the result in some way.  
    Dim leisureHours As Integer  
    If today.First() = "S" Then  
        leisureHours = 16  
    Else  
        leisureHours = 5  
    End If  
  
    ' Because the return statement specifies an operand of type Integer, the   
    ' method must have a return type of Task(Of Integer).   
    Return leisureHours  
End Function  
```  
  
 <span data-ttu-id="12635-112">当`TaskOfT_MethodAsync`称为从在 await 表达式中，await 表达式中检索的整数值 (值`leisureHours`) 存储在由返回的任务`TaskOfT_MethodAsync`。</span><span class="sxs-lookup"><span data-stu-id="12635-112">When `TaskOfT_MethodAsync` is called from within an await expression, the await expression retrieves the integer value (the value of `leisureHours`) that's stored in the task that's returned by `TaskOfT_MethodAsync`.</span></span> <span data-ttu-id="12635-113">有关详细信息 await 表达式，请参阅[Await 运算符](../../../../visual-basic/language-reference/operators/await-operator.md)。</span><span class="sxs-lookup"><span data-stu-id="12635-113">For more information about await expressions, see [Await Operator](../../../../visual-basic/language-reference/operators/await-operator.md).</span></span>  
  
 <span data-ttu-id="12635-114">下面的代码调用和等待方法`TaskOfT_MethodAsync`。</span><span class="sxs-lookup"><span data-stu-id="12635-114">The following code calls and awaits method `TaskOfT_MethodAsync`.</span></span> <span data-ttu-id="12635-115">结果赋给`result1`变量。</span><span class="sxs-lookup"><span data-stu-id="12635-115">The result is assigned to the `result1` variable.</span></span>  
  
```vb  
' Call and await the Task(Of T)-returning async method in the same statement.  
Dim result1 As Integer = Await TaskOfT_MethodAsync()  
```  
  
 <span data-ttu-id="12635-116">您可以更好地理解了这种分隔对调用`TaskOfT_MethodAsync`的应用程序从`Await`，如下面的代码所示。</span><span class="sxs-lookup"><span data-stu-id="12635-116">You can better understand how this happens by separating the call to `TaskOfT_MethodAsync` from the application of `Await`, as the following code shows.</span></span> <span data-ttu-id="12635-117">对方法的调用`TaskOfT_MethodAsync`这并不是立即处于等待状态的返回`Task(Of Integer)`，正如您期望的声明中的方法。</span><span class="sxs-lookup"><span data-stu-id="12635-117">A call to method `TaskOfT_MethodAsync` that isn't immediately awaited returns a `Task(Of Integer)`, as you would expect from the declaration of the method.</span></span> <span data-ttu-id="12635-118">该任务指派给`integerTask`变量在示例中。</span><span class="sxs-lookup"><span data-stu-id="12635-118">The task is assigned to the `integerTask` variable in the example.</span></span> <span data-ttu-id="12635-119">因为`integerTask`是<xref:System.Threading.Tasks.Task%601>，它包含<xref:System.Threading.Tasks.Task%601.Result>类型的属性`TResult`。</xref:System.Threading.Tasks.Task%601.Result> </xref:System.Threading.Tasks.Task%601></span><span class="sxs-lookup"><span data-stu-id="12635-119">Because `integerTask` is a <xref:System.Threading.Tasks.Task%601>, it contains a <xref:System.Threading.Tasks.Task%601.Result> property of type `TResult`.</span></span> <span data-ttu-id="12635-120">在这种情况下，TResult 表示整数类型。</span><span class="sxs-lookup"><span data-stu-id="12635-120">In this case, TResult represents an integer type.</span></span> <span data-ttu-id="12635-121">当`Await`应用于`integerTask`，await 表达式的计算结果的内容为<xref:System.Threading.Tasks.Task%601.Result%2A>属性`integerTask`。</xref:System.Threading.Tasks.Task%601.Result%2A></span><span class="sxs-lookup"><span data-stu-id="12635-121">When `Await` is applied to `integerTask`, the await expression evaluates to the contents of the <xref:System.Threading.Tasks.Task%601.Result%2A> property of `integerTask`.</span></span> <span data-ttu-id="12635-122">将值赋给`result2`变量。</span><span class="sxs-lookup"><span data-stu-id="12635-122">The value is assigned to the `result2` variable.</span></span>  
  
> [!WARNING]
>  <span data-ttu-id="12635-123"><xref:System.Threading.Tasks.Task%601.Result%2A>属性是阻塞属性。</xref:System.Threading.Tasks.Task%601.Result%2A></span><span class="sxs-lookup"><span data-stu-id="12635-123">The <xref:System.Threading.Tasks.Task%601.Result%2A> property is a blocking property.</span></span> <span data-ttu-id="12635-124">如果你在其任务完成之前尝试访问它，当前处于活动状态的线程将被阻止，直到任务完成且值为可用。</span><span class="sxs-lookup"><span data-stu-id="12635-124">If you try to access it before its task is finished, the thread that's currently active is blocked until the task completes and the value is available.</span></span> <span data-ttu-id="12635-125">在大多数情况下，应通过使用访问值`Await`而不是直接访问的属性。</span><span class="sxs-lookup"><span data-stu-id="12635-125">In most cases, you should access the value by using `Await` instead of accessing the property directly.</span></span>  
  
```vb  
' Call and await in separate statements.  
Dim integerTask As Task(Of Integer) = TaskOfT_MethodAsync()  
  
' You can do other work that does not rely on resultTask before awaiting.  
textBox1.Text &= String.Format("Application can continue working while the Task(Of T) runs. . . . " & vbCrLf)  
  
Dim result2 As Integer = Await integerTask  
```  
  
 <span data-ttu-id="12635-126">下面的代码中的显示语句验证的值`result1`变量，`result2`变量，与`Result`是相同的属性。</span><span class="sxs-lookup"><span data-stu-id="12635-126">The display statements in the following code verify that the values of the `result1` variable, the `result2` variable, and the `Result` property are the same.</span></span> <span data-ttu-id="12635-127">请记住，`Result`属性是阻塞属性，并且之前等待的 task 不应访问。</span><span class="sxs-lookup"><span data-stu-id="12635-127">Remember that the `Result` property is a blocking property and shouldn't be accessed before its task has been awaited.</span></span>  
  
```vb  
' Display the values of the result1 variable, the result2 variable, and  
' the resultTask.Result property.  
textBox1.Text &= String.Format(vbCrLf & "Value of result1 variable:   {0}" & vbCrLf, result1)  
textBox1.Text &= String.Format("Value of result2 variable:   {0}" & vbCrLf, result2)  
textBox1.Text &= String.Format("Value of resultTask.Result:  {0}" & vbCrLf, integerTask.Result)  
```  
  
##  <span data-ttu-id="12635-128"><a name="BKMK_TaskReturnType"></a>任务返回类型</span><span class="sxs-lookup"><span data-stu-id="12635-128"><a name="BKMK_TaskReturnType"></a> Task Return Type</span></span>  
 <span data-ttu-id="12635-129">不包含 return 语句或包含通常不返回操作数的 return 语句的 Async 方法具有返回类型为<xref:System.Threading.Tasks.Task>。</xref:System.Threading.Tasks.Task></span><span class="sxs-lookup"><span data-stu-id="12635-129">Async methods that don't contain a return statement or that contain a return statement that doesn't return an operand usually have a return type of <xref:System.Threading.Tasks.Task>.</span></span> <span data-ttu-id="12635-130">这种方法应为[Sub](../../../../visual-basic/programming-guide/language-features/procedures/sub-procedures.md)过程，如果它们编写的同步运行。</span><span class="sxs-lookup"><span data-stu-id="12635-130">Such methods would be [Sub](../../../../visual-basic/programming-guide/language-features/procedures/sub-procedures.md) procedures if they were written to run synchronously.</span></span> <span data-ttu-id="12635-131">如果您使用`Task`返回类型对于异步方法中，调用的方法可以使用`Await`运算符可暂停调用方的完成直到完成调用的异步方法。</span><span class="sxs-lookup"><span data-stu-id="12635-131">If you use a `Task` return type for an async method, a calling method can use an `Await` operator to suspend the caller's completion until the called async method has finished.</span></span>  
  
 <span data-ttu-id="12635-132">在下面的示例中，异步方法`Task_MethodAsync`不包含 return 语句。</span><span class="sxs-lookup"><span data-stu-id="12635-132">In the following example, async method `Task_MethodAsync` doesn't contain a return statement.</span></span> <span data-ttu-id="12635-133">因此，您指定的返回类型为`Task`对于方法，这样`Task_MethodAsync`以等待。</span><span class="sxs-lookup"><span data-stu-id="12635-133">Therefore, you specify a return type of `Task` for the method, which enables `Task_MethodAsync` to be awaited.</span></span> <span data-ttu-id="12635-134">定义`Task`类型不包括`Result`属性存储返回值。</span><span class="sxs-lookup"><span data-stu-id="12635-134">The definition of the `Task` type doesn't include a `Result` property to store a return value.</span></span>  
  
```vb  
' TASK EXAMPLE  
Async Function Task_MethodAsync() As Task  
  
    ' The body of an async method is expected to contain an awaited   
    ' asynchronous call.  
    ' Task.Delay is a placeholder for actual work.  
    Await Task.Delay(2000)  
    textBox1.Text &= String.Format(vbCrLf & "Sorry for the delay. . . ." & vbCrLf)  
  
    ' This method has no return statement, so its return type is Task.   
End Function  
```  
  
 <span data-ttu-id="12635-135">`Task_MethodAsync`调用该方法并使用 await 语句而不是 await 表达式，类似于同步的调用语句等待`Sub`或返回 void 的方法。</span><span class="sxs-lookup"><span data-stu-id="12635-135">`Task_MethodAsync` is called and awaited by using an await statement instead of an await expression, similar to the calling statement for a synchronous `Sub` or void-returning method.</span></span> <span data-ttu-id="12635-136">应用程序的`Await`运算符在这种情况下不生成值。</span><span class="sxs-lookup"><span data-stu-id="12635-136">The application of an `Await` operator in this case doesn't produce a value.</span></span>  
  
 <span data-ttu-id="12635-137">下面的代码调用和等待方法`Task_MethodAsync`。</span><span class="sxs-lookup"><span data-stu-id="12635-137">The following code calls and awaits method `Task_MethodAsync`.</span></span>  
  
```vb  
' Call and await the Task-returning async method in the same statement.  
Await Task_MethodAsync()  
```  
  
 <span data-ttu-id="12635-138">如下所示的上一个<xref:System.Threading.Tasks.Task%601>示例中，可以单独对调用`Task_MethodAsync`的应用程序从`Await`运算符，如以下代码所示。</xref:System.Threading.Tasks.Task%601></span><span class="sxs-lookup"><span data-stu-id="12635-138">As in the previous <xref:System.Threading.Tasks.Task%601> example, you can separate the call to `Task_MethodAsync` from the application of an `Await` operator, as the following code shows.</span></span> <span data-ttu-id="12635-139">但是，请记住，`Task`没有`Result`属性，并当 await 运算符应用于生成没有值`Task`。</span><span class="sxs-lookup"><span data-stu-id="12635-139">However, remember that a `Task` doesn't have a `Result` property, and that no value is produced when an await operator is applied to a `Task`.</span></span>  
  
 <span data-ttu-id="12635-140">下面的代码分隔调用`Task_MethodAsync`从等待该任务，`Task_MethodAsync`返回。</span><span class="sxs-lookup"><span data-stu-id="12635-140">The following code separates calling `Task_MethodAsync` from awaiting the task that `Task_MethodAsync` returns.</span></span>  
  
<span data-ttu-id="12635-141"><CodeContentPlaceHolder>6</CodeContentPlaceHolder></span><span class="sxs-lookup"><span data-stu-id="12635-141"><CodeContentPlaceHolder>6</CodeContentPlaceHolder></span></span>  
##  <span data-ttu-id="12635-142"><a name="BKMK_VoidReturnType"></a>Void 返回类型</span><span class="sxs-lookup"><span data-stu-id="12635-142"><a name="BKMK_VoidReturnType"></a> Void Return Type</span></span>  
 <span data-ttu-id="12635-143">主要用途`Sub`过程是在事件处理程序，其中没有返回类型 （也称为 void 返回类型用其他语言）。</span><span class="sxs-lookup"><span data-stu-id="12635-143">The primary use of `Sub` procedures is in event handlers, where there is no return type (referred to as a void return type in other languages).</span></span> <span data-ttu-id="12635-144">Void 返回还可用于替代返回 void 的方法，或者用于执行可分类为"发后不理"活动的方法。</span><span class="sxs-lookup"><span data-stu-id="12635-144">A void return also can be used to override void-returning methods or for methods that perform activities that can be categorized as "fire and forget."</span></span> <span data-ttu-id="12635-145">但是，您应返回`Task`只要有可能，因为不能等待返回 void 的异步方法。</span><span class="sxs-lookup"><span data-stu-id="12635-145">However, you should return a `Task` wherever possible, because a void-returning async method can't be awaited.</span></span> <span data-ttu-id="12635-146">这种方法的任何调用方必须能够继续完成，而无需等待调用的异步方法完成，并且调用方必须独立于异步方法生成的任何值或异常。</span><span class="sxs-lookup"><span data-stu-id="12635-146">Any caller of such a method must be able to continue to completion without waiting for the called async method to finish, and the caller must be independent of any values or exceptions that the async method generates.</span></span>  
  
 <span data-ttu-id="12635-147">返回 void 的异步方法的调用方无法捕获从该方法引发的异常，且此类未经处理的异常可能会导致应用程序故障。</span><span class="sxs-lookup"><span data-stu-id="12635-147">The caller of a void-returning async method can't catch exceptions that are thrown from the method, and such unhandled exceptions are likely to cause your application to fail.</span></span> <span data-ttu-id="12635-148">如果返回的异步方法中发生异常<xref:System.Threading.Tasks.Task>或<xref:System.Threading.Tasks.Task%601>，存储在返回的任务，并等待该任务时再次引发异常。</xref:System.Threading.Tasks.Task%601> </xref:System.Threading.Tasks.Task></span><span class="sxs-lookup"><span data-stu-id="12635-148">If an exception occurs in an async method that returns a <xref:System.Threading.Tasks.Task> or <xref:System.Threading.Tasks.Task%601>, the exception is stored in the returned task, and rethrown when the task is awaited.</span></span> <span data-ttu-id="12635-149">因此，请确保可以产生异常任何 async 方法都具有返回类型为<xref:System.Threading.Tasks.Task>或<xref:System.Threading.Tasks.Task%601>和对方法的调用会等待。</xref:System.Threading.Tasks.Task%601> </xref:System.Threading.Tasks.Task></span><span class="sxs-lookup"><span data-stu-id="12635-149">Therefore, make sure that any async method that can produce an exception has a return type of <xref:System.Threading.Tasks.Task> or <xref:System.Threading.Tasks.Task%601> and that calls to the method are awaited.</span></span>  
  
 <span data-ttu-id="12635-150">有关如何在异步方法中捕捉异常的详细信息，请参阅[重试...Catch...Finally 语句](../../../../visual-basic/language-reference/statements/try-catch-finally-statement.md)。</span><span class="sxs-lookup"><span data-stu-id="12635-150">For more information about how to catch exceptions in async methods, see [Try...Catch...Finally Statement](../../../../visual-basic/language-reference/statements/try-catch-finally-statement.md).</span></span>  
  
 <span data-ttu-id="12635-151">下面的代码定义了异步事件处理程序。</span><span class="sxs-lookup"><span data-stu-id="12635-151">The following code defines an async event handler.</span></span>  
  
<span data-ttu-id="12635-152"><CodeContentPlaceHolder>7</CodeContentPlaceHolder></span><span class="sxs-lookup"><span data-stu-id="12635-152"><CodeContentPlaceHolder>7</CodeContentPlaceHolder></span></span>  
##  <span data-ttu-id="12635-153"><a name="BKMK_Example"></a>完整的示例</span><span class="sxs-lookup"><span data-stu-id="12635-153"><a name="BKMK_Example"></a> Complete Example</span></span>  
 <span data-ttu-id="12635-154">以下 Windows Presentation Foundation (WPF) 项目包含本主题中的代码示例。</span><span class="sxs-lookup"><span data-stu-id="12635-154">The following Windows Presentation Foundation (WPF) project contains the code examples from this topic.</span></span>  
  
 <span data-ttu-id="12635-155">若要运行项目，请执行下列步骤：</span><span class="sxs-lookup"><span data-stu-id="12635-155">To run the project, perform the following steps:</span></span>  
  
1.  <span data-ttu-id="12635-156">启动 Visual Studio。</span><span class="sxs-lookup"><span data-stu-id="12635-156">Start Visual Studio.</span></span>  
  
2.  <span data-ttu-id="12635-157">在菜单栏上，依次选择“文件” ****、“新建” ****、“项目” ****。</span><span class="sxs-lookup"><span data-stu-id="12635-157">On the menu bar, choose **File**, **New**, **Project**.</span></span>  
  
     <span data-ttu-id="12635-158">**“新建项目”** 对话框随即打开。</span><span class="sxs-lookup"><span data-stu-id="12635-158">The **New Project** dialog box opens.</span></span>  
  
3.  <span data-ttu-id="12635-159">在**已安装**，**模板**类别中，选择**Visual Basic**，然后选择**Windows**。</span><span class="sxs-lookup"><span data-stu-id="12635-159">In the **Installed**, **Templates** category, choose **Visual Basic**, and then choose **Windows**.</span></span> <span data-ttu-id="12635-160">选择**WPF 应用程序**从项目类型列表。</span><span class="sxs-lookup"><span data-stu-id="12635-160">Choose **WPF Application** from the list of project types.</span></span>  
  
4.  <span data-ttu-id="12635-161">输入`AsyncReturnTypes`作为项目的名称，然后选择**确定**按钮。</span><span class="sxs-lookup"><span data-stu-id="12635-161">Enter `AsyncReturnTypes` as the name of the project, and then choose the **OK** button.</span></span>  
  
     <span data-ttu-id="12635-162">新项目将出现在**解决方案资源管理器**。</span><span class="sxs-lookup"><span data-stu-id="12635-162">The new project appears in **Solution Explorer**.</span></span>  
  
5.  <span data-ttu-id="12635-163">在 Visual Studio 代码编辑器中，选择 **“MainWindow.xaml”** 选项卡。</span><span class="sxs-lookup"><span data-stu-id="12635-163">In the Visual Studio Code Editor, choose the **MainWindow.xaml** tab.</span></span>  
  
     <span data-ttu-id="12635-164">如果选项卡不可见，打开快捷菜单中的 MainWindow.xaml**解决方案资源管理器**，然后选择**打开**。</span><span class="sxs-lookup"><span data-stu-id="12635-164">If the tab is not visible, open the shortcut menu for MainWindow.xaml in **Solution Explorer**, and then choose **Open**.</span></span>  
  
6.  <span data-ttu-id="12635-165">在**XAML** MainWindow.xaml，窗口将替换为下面的代码的代码。</span><span class="sxs-lookup"><span data-stu-id="12635-165">In the **XAML** window of MainWindow.xaml, replace the code with the following code.</span></span>  
  
    ```vb  
    <Window x:Class="MainWindow"  
            xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"  
            xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"  
            Title="MainWindow" Height="350" Width="525">  
        <Grid>  
            <Button x:Name="button1" Content="Start" HorizontalAlignment="Left" Margin="214,28,0,0" VerticalAlignment="Top" Width="75" HorizontalContentAlignment="Center" FontWeight="Bold" FontFamily="Aharoni" Click="button1_Click"/>  
            <TextBox x:Name="textBox1" Margin="0,80,0,0" TextWrapping="Wrap" FontFamily="Lucida Console"/>  
  
        </Grid>  
    </Window>  
  
    ```  
  
     <span data-ttu-id="12635-166">一个简单的窗口，其中包含一个文本框和一个按钮将出现在**设计**MainWindow.xaml 的窗口。</span><span class="sxs-lookup"><span data-stu-id="12635-166">A simple window that contains a text box and a button appears in the **Design** window of MainWindow.xaml.</span></span>  
  
7.  <span data-ttu-id="12635-167">在**解决方案资源管理器**，MainWindow.xaml.vb，打开快捷菜单，然后选择**查看代码**。</span><span class="sxs-lookup"><span data-stu-id="12635-167">In **Solution Explorer**, open the shortcut menu for MainWindow.xaml.vb, and then choose **View Code**.</span></span>  
  
8.  <span data-ttu-id="12635-168">将 MainWindow.xaml.vb 中的代码替换为以下代码。</span><span class="sxs-lookup"><span data-stu-id="12635-168">Replace the code in MainWindow.xaml.vb with the following code.</span></span>  
  
    ```vb  
    Class MainWindow  
  
        ' SUB EXAMPLE  
        Async Sub button1_Click(sender As Object, e As RoutedEventArgs) Handles button1.Click  
  
            textBox1.Clear()  
  
            ' Start the process and await its completion. DriverAsync is a   
            ' Task-returning async method.  
            Await DriverAsync()  
  
            ' Say goodbye.  
            textBox1.Text &= vbCrLf & "All done, exiting button-click event handler."  
        End Sub  
  
        Async Function DriverAsync() As Task  
  
            ' Task(Of T)   
            ' Call and await the Task(Of T)-returning async method in the same statement.  
            Dim result1 As Integer = Await TaskOfT_MethodAsync()  
  
            ' Call and await in separate statements.  
            Dim integerTask As Task(Of Integer) = TaskOfT_MethodAsync()  
  
            ' You can do other work that does not rely on resultTask before awaiting.  
            textBox1.Text &= String.Format("Application can continue working while the Task(Of T) runs. . . . " & vbCrLf)  
  
            Dim result2 As Integer = Await integerTask  
  
            ' Display the values of the result1 variable, the result2 variable, and  
            ' the resultTask.Result property.  
            textBox1.Text &= String.Format(vbCrLf & "Value of result1 variable:   {0}" & vbCrLf, result1)  
            textBox1.Text &= String.Format("Value of result2 variable:   {0}" & vbCrLf, result2)  
            textBox1.Text &= String.Format("Value of resultTask.Result:  {0}" & vbCrLf, integerTask.Result)  
  
            ' Task   
            ' Call and await the Task-returning async method in the same statement.  
            Await Task_MethodAsync()  
  
            ' Call and await in separate statements.  
            Dim simpleTask As Task = Task_MethodAsync()  
  
            ' You can do other work that does not rely on simpleTask before awaiting.  
            textBox1.Text &= String.Format(vbCrLf & "Application can continue working while the Task runs. . . ." & vbCrLf)  
  
            Await simpleTask  
        End Function  
  
        ' TASK(OF T) EXAMPLE  
        Async Function TaskOfT_MethodAsync() As Task(Of Integer)  
  
            ' The body of an async method is expected to contain an awaited   
            ' asynchronous call.  
            ' Task.FromResult is a placeholder for actual work that returns a string.  
            Dim today As String = Await Task.FromResult(Of String)(DateTime.Now.DayOfWeek.ToString())  
  
            ' The method then can process the result in some way.  
            Dim leisureHours As Integer  
            If today.First() = "S" Then  
                leisureHours = 16  
            Else  
                leisureHours = 5  
            End If  
  
            ' Because the return statement specifies an operand of type Integer, the   
            ' method must have a return type of Task(Of Integer).   
            Return leisureHours  
        End Function  
  
        ' TASK EXAMPLE  
        Async Function Task_MethodAsync() As Task  
  
            ' The body of an async method is expected to contain an awaited   
            ' asynchronous call.  
            ' Task.Delay is a placeholder for actual work.  
            Await Task.Delay(2000)  
            textBox1.Text &= String.Format(vbCrLf & "Sorry for the delay. . . ." & vbCrLf)  
  
            ' This method has no return statement, so its return type is Task.   
        End Function  
  
    End Class  
    ```  
  
9. <span data-ttu-id="12635-169">按 F5 键以运行程序，然后选择 **“启动”** 按钮。</span><span class="sxs-lookup"><span data-stu-id="12635-169">Choose the F5 key to run the program, and then choose the **Start** button.</span></span>  
  
     <span data-ttu-id="12635-170">应出现以下输出。</span><span class="sxs-lookup"><span data-stu-id="12635-170">The following output should appear.</span></span>  
  
    ```  
    Application can continue working while the Task<T> runs. . . .   
  
    Value of result1 variable:   5  
    Value of result2 variable:   5  
    Value of integerTask.Result: 5  
  
    Sorry for the delay. . . .  
  
    Application can continue working while the Task runs. . . .  
  
    Sorry for the delay. . . .  
  
    All done, exiting button-click event handler.  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="12635-171">另请参阅</span><span class="sxs-lookup"><span data-stu-id="12635-171">See Also</span></span>  
 <span data-ttu-id="12635-172"><xref:System.Threading.Tasks.Task.FromResult%2A></xref:System.Threading.Tasks.Task.FromResult%2A></span><span class="sxs-lookup"><span data-stu-id="12635-172"><xref:System.Threading.Tasks.Task.FromResult%2A></span></span>   
<span data-ttu-id="12635-173"> [演练︰ 访问 Web 使用 Async 和 Await (Visual Basic)](../../../../visual-basic/programming-guide/concepts/async/walkthrough-accessing-the-web-by-using-async-and-await.md) </span><span class="sxs-lookup"><span data-stu-id="12635-173"> [Walkthrough: Accessing the Web by Using Async and Await (Visual Basic)](../../../../visual-basic/programming-guide/concepts/async/walkthrough-accessing-the-web-by-using-async-and-await.md) </span></span>  
<span data-ttu-id="12635-174"> [异步程序 (Visual Basic 中) 中的控制流](../../../../visual-basic/programming-guide/concepts/async/control-flow-in-async-programs.md) </span><span class="sxs-lookup"><span data-stu-id="12635-174"> [Control Flow in Async Programs (Visual Basic)](../../../../visual-basic/programming-guide/concepts/async/control-flow-in-async-programs.md) </span></span>  
<span data-ttu-id="12635-175"> [异步](../../../../visual-basic/language-reference/modifiers/async.md) </span><span class="sxs-lookup"><span data-stu-id="12635-175"> [Async](../../../../visual-basic/language-reference/modifiers/async.md) </span></span>  
<span data-ttu-id="12635-176"> [Await 运算符](../../../../visual-basic/language-reference/operators/await-operator.md)</span><span class="sxs-lookup"><span data-stu-id="12635-176"> [Await Operator](../../../../visual-basic/language-reference/operators/await-operator.md)</span></span>
