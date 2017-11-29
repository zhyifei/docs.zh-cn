---
title: "try-catch（C# 参考）"
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
f1_keywords:
- try
- try_CSharpKeyword
- catch
- catch_CSharpKeyword
helpviewer_keywords:
- catch keyword [C#]
- try-catch statement [C#]
ms.assetid: cb5503c7-bfa1-4610-8fc2-ddcd2e84c438
caps.latest.revision: "45"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 753beb554796ad0aa2c5e15c715240453de9a3e1
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="try-catch-c-reference"></a><span data-ttu-id="24494-102">try-catch（C# 参考）</span><span class="sxs-lookup"><span data-stu-id="24494-102">try-catch (C# Reference)</span></span>
<span data-ttu-id="24494-103">Try-catch 语句包含一个后接一个或多个 `catch` 子句的 `try` 块，这些子句指定不同异常的处理程序。</span><span class="sxs-lookup"><span data-stu-id="24494-103">The try-catch statement consists of a `try` block followed by one or more `catch` clauses, which specify handlers for different exceptions.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="24494-104">备注</span><span class="sxs-lookup"><span data-stu-id="24494-104">Remarks</span></span>  
 <span data-ttu-id="24494-105">引发异常时，公共语言运行时 (CLR) 查找处理此异常的 `catch` 语句。</span><span class="sxs-lookup"><span data-stu-id="24494-105">When an exception is thrown, the common language runtime (CLR) looks for the `catch` statement that handles this exception.</span></span> <span data-ttu-id="24494-106">如果当前正在执行的方法不包含此类 `catch` 块，则 CLR 查看调用了当前方法的方法，并以此类推遍历调用堆栈。</span><span class="sxs-lookup"><span data-stu-id="24494-106">If the currently executing method does not contain such a `catch` block, the CLR looks at the method that called the current method, and so on up the call stack.</span></span> <span data-ttu-id="24494-107">如果未找到任何 `catch` 块，则 CLR 向用户显示一条未处理的异常消息，并停止执行程序。</span><span class="sxs-lookup"><span data-stu-id="24494-107">If no `catch` block is found, then the CLR displays an unhandled exception message to the user and stops execution of the program.</span></span>  
  
 <span data-ttu-id="24494-108">`try` 块包含可能导致异常的受保护的代码。</span><span class="sxs-lookup"><span data-stu-id="24494-108">The `try` block contains the guarded code that may cause the exception.</span></span> <span data-ttu-id="24494-109">将执行此块，直至引发异常或其成功完成。</span><span class="sxs-lookup"><span data-stu-id="24494-109">The block is executed until an exception is thrown or it is completed successfully.</span></span> <span data-ttu-id="24494-110">例如，强制转换 `null` 对象的以下尝试会引发 <xref:System.NullReferenceException> 异常：</span><span class="sxs-lookup"><span data-stu-id="24494-110">For example, the following attempt to cast a `null` object raises the <xref:System.NullReferenceException> exception:</span></span>  
  
```csharp  
object o2 = null;  
try  
{  
    int i2 = (int)o2;   // Error  
}  
```  
  
 <span data-ttu-id="24494-111">尽管可以不带参数使用 `catch` 子句来捕获任何类型的异常，但不推荐这种用法。</span><span class="sxs-lookup"><span data-stu-id="24494-111">Although the `catch` clause can be used without arguments to catch any type of exception, this usage is not recommended.</span></span> <span data-ttu-id="24494-112">一般情况下，只应捕获你知道如何从其恢复的异常。</span><span class="sxs-lookup"><span data-stu-id="24494-112">In general, you should only catch those exceptions that you know how to recover from.</span></span> <span data-ttu-id="24494-113">因此，应始终指定派生自 <xref:System.Exception?displayProperty=nameWithType> 的对象参数，例如：</span><span class="sxs-lookup"><span data-stu-id="24494-113">Therefore, you should always specify an object argument derived from <xref:System.Exception?displayProperty=nameWithType> For example:</span></span>  
  
```csharp  
catch (InvalidCastException e)   
{  
}  
```  
  
 <span data-ttu-id="24494-114">可以使用同一 try-catch 语句中的多个特定 `catch` 子句。</span><span class="sxs-lookup"><span data-stu-id="24494-114">It is possible to use more than one specific `catch` clause in the same try-catch statement.</span></span> <span data-ttu-id="24494-115">在这种情况下，`catch` 子句的顺序很重要，因为 `catch` 子句是按顺序检查的。</span><span class="sxs-lookup"><span data-stu-id="24494-115">In this case, the order of the `catch` clauses is important because the `catch` clauses are examined in order.</span></span> <span data-ttu-id="24494-116">在使用更笼统的子句之前获取特定性更强的异常。</span><span class="sxs-lookup"><span data-stu-id="24494-116">Catch the more specific exceptions before the less specific ones.</span></span> <span data-ttu-id="24494-117">如果捕获块的排序使得永不会达到之后的块，则编译器将产生错误。</span><span class="sxs-lookup"><span data-stu-id="24494-117">The compiler produces an error if you order your catch blocks so that a later block can never be reached.</span></span>  
  
 <span data-ttu-id="24494-118">筛选想要处理的异常的一种方式是使用 `catch` 参数。</span><span class="sxs-lookup"><span data-stu-id="24494-118">Using `catch` arguments is one way to filter for the exceptions you want to handle.</span></span>  <span data-ttu-id="24494-119">也可以使用谓词表达式进一步检查该异常以决定是否要对其进行处理。</span><span class="sxs-lookup"><span data-stu-id="24494-119">You can also use a predicate expression that further examines the exception to decide whether to handle it.</span></span>  <span data-ttu-id="24494-120">如果谓词表达式返回 false，则继续搜索处理程序。</span><span class="sxs-lookup"><span data-stu-id="24494-120">If the predicate expression returns false, then the search for a handler continues.</span></span>  
  
```csharp  
catch (ArgumentException e) when (e.ParamName == "…")  
{  
}  
```  
  
 <span data-ttu-id="24494-121">异常筛选器要优于捕获和重新引发（如下所述），因为筛选器将保留堆栈不受损坏。</span><span class="sxs-lookup"><span data-stu-id="24494-121">Exception filters are preferable to catching and rethrowing (explained below) because filters leave the stack unharmed.</span></span>  <span data-ttu-id="24494-122">如果之后的处理程序转储堆栈，可以查看到异常的原始来源，而不只是重新引发它的最后一个位置。</span><span class="sxs-lookup"><span data-stu-id="24494-122">If a later handler dumps the stack, you can see where the exception originally came from, rather than just the last place it was rethrown.</span></span>  <span data-ttu-id="24494-123">异常筛选器表达式的一个常见用途是日志记录。</span><span class="sxs-lookup"><span data-stu-id="24494-123">A common use of exception filter expressions is logging.</span></span>  <span data-ttu-id="24494-124">可以创建一个始终返回 false 并输出到日志的谓词函数，而且可以在异常通过时进行记录，无需处理并重新引发它们。</span><span class="sxs-lookup"><span data-stu-id="24494-124">You can create a predicate function that always returns false that also outputs to a log, you can log exceptions as they go by without having to handle them and rethrow.</span></span>  
  
 <span data-ttu-id="24494-125">可在 `catch` 块中使用 [throw](../../../csharp/language-reference/keywords/throw.md) 语句以重新引发已由 `catch` 语句捕获的异常。</span><span class="sxs-lookup"><span data-stu-id="24494-125">A [throw](../../../csharp/language-reference/keywords/throw.md) statement can be used in a `catch` block to re-throw the exception that is caught by the `catch` statement.</span></span> <span data-ttu-id="24494-126">下面的示例从 <xref:System.IO.IOException> 异常提取源信息，然后向父方法引发异常。</span><span class="sxs-lookup"><span data-stu-id="24494-126">The following example extracts source information from an <xref:System.IO.IOException> exception, and then throws the exception to the parent method.</span></span>  
  
```csharp  
catch (FileNotFoundException e)  
{  
    // FileNotFoundExceptions are handled here.  
}  
catch (IOException e)  
{  
    // Extract some information from this exception, and then   
    // throw it to the parent method.  
    if (e.Source != null)  
        Console.WriteLine("IOException source: {0}", e.Source);  
    throw;  
}  
```  
  
 <span data-ttu-id="24494-127">你可以捕获一个异常而引发一个不同的异常。</span><span class="sxs-lookup"><span data-stu-id="24494-127">You can catch one exception and throw a different exception.</span></span> <span data-ttu-id="24494-128">执行此操作时，请指定作为内部异常捕获的异常，如以下示例所示。</span><span class="sxs-lookup"><span data-stu-id="24494-128">When you do this, specify the exception that you caught as the inner exception, as shown in the following example.</span></span>  
  
```csharp  
catch (InvalidCastException e)   
{  
    // Perform some action here, and then throw a new exception.  
    throw new YourCustomException("Put your error message here.", e);  
}  
```  
  
 <span data-ttu-id="24494-129">当指定的条件为 true 时，你还可以重新引发异常，如以下示例所示。</span><span class="sxs-lookup"><span data-stu-id="24494-129">You can also re-throw an exception when a specified condition is true, as shown in the following example.</span></span>  
  
```csharp  
catch (InvalidCastException e)  
{  
    if (e.Data == null)  
    {  
        throw;  
    }  
    else  
    {  
        // Take some action.  
    }  
 }  
```  
  
 <span data-ttu-id="24494-130">从 `try` 块内，仅初始化在其中声明的变量。</span><span class="sxs-lookup"><span data-stu-id="24494-130">From inside a `try` block, initialize only variables that are declared therein.</span></span> <span data-ttu-id="24494-131">否则，在完成执行块之前，可能会出现异常。</span><span class="sxs-lookup"><span data-stu-id="24494-131">Otherwise, an exception can occur before the execution of the block is completed.</span></span> <span data-ttu-id="24494-132">例如，在下面的代码示例中，变量 `n` 在 `try` 块内部初始化。</span><span class="sxs-lookup"><span data-stu-id="24494-132">For example, in the following code example, the variable `n` is initialized inside the `try` block.</span></span> <span data-ttu-id="24494-133">尝试在 `Write(n)` 语句的 `try` 块外部使用此变量将生成编译器错误。</span><span class="sxs-lookup"><span data-stu-id="24494-133">An attempt to use this variable outside the `try` block in the `Write(n)` statement will generate a compiler error.</span></span>  
  
```csharp  
static void Main()   
{  
    int n;  
    try   
    {  
        // Do not initialize this variable here.  
        n = 123;  
    }  
    catch  
    {  
    }  
    // Error: Use of unassigned local variable 'n'.  
    Console.Write(n);  
}  
```  
  
 <span data-ttu-id="24494-134">有关 catch 的详细信息，请参阅 [try-catch-finally](../../../csharp/language-reference/keywords/try-catch-finally.md)。</span><span class="sxs-lookup"><span data-stu-id="24494-134">For more information about catch, see [try-catch-finally](../../../csharp/language-reference/keywords/try-catch-finally.md).</span></span>  
  
## <a name="exceptions-in-async-methods"></a><span data-ttu-id="24494-135">异步方法中的异常</span><span class="sxs-lookup"><span data-stu-id="24494-135">Exceptions in Async Methods</span></span>  
 <span data-ttu-id="24494-136">异步方法由 [async](../../../csharp/language-reference/keywords/async.md) 修饰符标记，通常包含一个或多个 await 表达式或语句。</span><span class="sxs-lookup"><span data-stu-id="24494-136">An async method is marked  by an  [async](../../../csharp/language-reference/keywords/async.md) modifier and usually contains one or more await expressions or statements.</span></span> <span data-ttu-id="24494-137">await 表达式将 [await](../../../csharp/language-reference/keywords/await.md) 运算符应用于 <xref:System.Threading.Tasks.Task> 或 <xref:System.Threading.Tasks.Task%601>。</span><span class="sxs-lookup"><span data-stu-id="24494-137">An await expression applies the [await](../../../csharp/language-reference/keywords/await.md) operator to a <xref:System.Threading.Tasks.Task> or <xref:System.Threading.Tasks.Task%601>.</span></span>  
  
 <span data-ttu-id="24494-138">当控件到达异步方法中的 `await` 时，将挂起方法中的进度，直到所等待的任务完成。</span><span class="sxs-lookup"><span data-stu-id="24494-138">When control reaches an `await` in the async method, progress in the method is suspended until the awaited task completes.</span></span> <span data-ttu-id="24494-139">任务完成后，可以在方法中恢复执行。</span><span class="sxs-lookup"><span data-stu-id="24494-139">When the task  is complete, execution can resume in the method.</span></span> <span data-ttu-id="24494-140">有关详细信息，请参阅[使用 async 和 await 的异步编程](../../../csharp/programming-guide/concepts/async/index.md)和[异步程序中的控制流](../../../csharp/programming-guide/concepts/async/control-flow-in-async-programs.md)。</span><span class="sxs-lookup"><span data-stu-id="24494-140">For more information, see [Asynchronous Programming with async and await](../../../csharp/programming-guide/concepts/async/index.md) and [Control Flow in Async Programs](../../../csharp/programming-guide/concepts/async/control-flow-in-async-programs.md).</span></span>  
  
 <span data-ttu-id="24494-141">应用了 `await` 的完成任务可能由于返回此任务的方法中存在未处理的异常而处于错误状态。</span><span class="sxs-lookup"><span data-stu-id="24494-141">The completed task to which `await` is applied might be in a faulted state because of an unhandled exception in the method that returns the task.</span></span> <span data-ttu-id="24494-142">等待该任务引发异常。</span><span class="sxs-lookup"><span data-stu-id="24494-142">Awaiting the task throws an exception.</span></span> <span data-ttu-id="24494-143">如果取消了返回任务的异步进程，此任务最后也可能为已取消状态。</span><span class="sxs-lookup"><span data-stu-id="24494-143">A task can also end up in a canceled state if the asynchronous process that returns it is canceled.</span></span> <span data-ttu-id="24494-144">等待已取消的任务引发 `OperationCanceledException`。</span><span class="sxs-lookup"><span data-stu-id="24494-144">Awaiting a canceled task throws  an `OperationCanceledException`.</span></span> <span data-ttu-id="24494-145">有关如何取消异步进程的详细信息，请参阅[微调异步应用程序](../../programming-guide/concepts/async/fine-tuning-your-async-application.md)。</span><span class="sxs-lookup"><span data-stu-id="24494-145">For more information about how to cancel an asynchronous process, see [Fine-Tuning Your Async Application](../../programming-guide/concepts/async/fine-tuning-your-async-application.md).</span></span>  
  
 <span data-ttu-id="24494-146">若要捕获异常，请在 `try` 块中等待任务并在关联的 `catch` 块中捕获异常。</span><span class="sxs-lookup"><span data-stu-id="24494-146">To catch the exception, await the task in a `try` block, and catch the exception in the associated `catch` block.</span></span> <span data-ttu-id="24494-147">相关示例，请参见“示例”一节。</span><span class="sxs-lookup"><span data-stu-id="24494-147">For an example, see the "Example" section.</span></span>  
  
 <span data-ttu-id="24494-148">任务可能处于错误状态，因为等待的异步方法中发生了多个异常。</span><span class="sxs-lookup"><span data-stu-id="24494-148">A task can be in a faulted state because multiple exceptions occurred in the awaited async method.</span></span> <span data-ttu-id="24494-149">例如，任务可能是对 <xref:System.Threading.Tasks.Task.WhenAll%2A?displayProperty=nameWithType> 调用的结果。</span><span class="sxs-lookup"><span data-stu-id="24494-149">For example, the task might be the result of a call to <xref:System.Threading.Tasks.Task.WhenAll%2A?displayProperty=nameWithType>.</span></span> <span data-ttu-id="24494-150">当等待此类任务时，仅捕捉到其中一个异常，而且你无法预测将会捕获到哪个异常。</span><span class="sxs-lookup"><span data-stu-id="24494-150">When you await such a task, only one of the exceptions is caught, and you can't predict which exception will be caught.</span></span> <span data-ttu-id="24494-151">相关示例，请参见“示例”一节。</span><span class="sxs-lookup"><span data-stu-id="24494-151">For an example, see the "Example" section.</span></span>  
  
## <a name="example"></a><span data-ttu-id="24494-152">示例</span><span class="sxs-lookup"><span data-stu-id="24494-152">Example</span></span>  
 <span data-ttu-id="24494-153">在下面的示例中，`try` 块包含对可能引发异常的 `ProcessString` 方法的调用。</span><span class="sxs-lookup"><span data-stu-id="24494-153">In the following example, the `try` block contains a call to the `ProcessString` method that may cause an exception.</span></span> <span data-ttu-id="24494-154">`catch` 子句包含只在屏幕上显示一条消息的异常处理程序。</span><span class="sxs-lookup"><span data-stu-id="24494-154">The `catch` clause contains the exception handler that just displays a message on the screen.</span></span> <span data-ttu-id="24494-155">当从 `MyMethod` 内部调用 `throw` 语句时，系统将查找 `catch` 语句并显示消息 `Exception caught`。</span><span class="sxs-lookup"><span data-stu-id="24494-155">When the `throw` statement is called from inside `MyMethod`, the system looks for the `catch` statement and displays the message `Exception caught`.</span></span>  
  
 [!code-csharp[csrefKeywordsExceptions#2](../../../csharp/language-reference/keywords/codesnippet/CSharp/try-catch_1.cs)]  
  
## <a name="example"></a><span data-ttu-id="24494-156">示例</span><span class="sxs-lookup"><span data-stu-id="24494-156">Example</span></span>  
 <span data-ttu-id="24494-157">在下面的示例中，使用了两个 catch 块，并捕获到最先出现的最具体的异常。</span><span class="sxs-lookup"><span data-stu-id="24494-157">In the following example, two catch blocks are used, and the most specific exception, which comes first, is caught.</span></span>  
  
 <span data-ttu-id="24494-158">若要捕获最不具体的异常，你可以将 `ProcessString` 中的 throw 语句替换为以下语句：`throw new Exception()`。</span><span class="sxs-lookup"><span data-stu-id="24494-158">To catch the least specific exception, you can replace the throw statement in `ProcessString` with the following statement: `throw new Exception()`.</span></span>  
  
 <span data-ttu-id="24494-159">如果将最不具体的 catch 块置于示例中第一个，将显示以下错误消息：`A previous catch clause already catches all exceptions of this or a super type ('System.Exception')`。</span><span class="sxs-lookup"><span data-stu-id="24494-159">If you place the least-specific catch block first in the example, the following  error message appears: `A previous catch clause already catches all exceptions of this or a super type ('System.Exception')`.</span></span>  
  
 [!code-csharp[csrefKeywordsExceptions#3](../../../csharp/language-reference/keywords/codesnippet/CSharp/try-catch_2.cs)]  
  
## <a name="example"></a><span data-ttu-id="24494-160">示例</span><span class="sxs-lookup"><span data-stu-id="24494-160">Example</span></span>  
 <span data-ttu-id="24494-161">下面的示例阐释异步方法的异常处理。</span><span class="sxs-lookup"><span data-stu-id="24494-161">The following example illustrates exception handling for async methods.</span></span> <span data-ttu-id="24494-162">若要捕获异步任务引发的异常，将 `await` 表达式置于 `try` 块中，并在 `catch` 块中捕获该异常。</span><span class="sxs-lookup"><span data-stu-id="24494-162">To catch an exception that an async task throws, place the `await` expression in a `try` block, and catch the exception in a `catch` block.</span></span>  
  
 <span data-ttu-id="24494-163">在示例中取消注释 `throw new Exception` 行以演示异常处理。</span><span class="sxs-lookup"><span data-stu-id="24494-163">Uncomment the `throw new Exception` line in the example to demonstrate exception handling.</span></span> <span data-ttu-id="24494-164">任务的 `IsFaulted` 属性设置为 `True`，任务的 `Exception.InnerException` 属性设置为异常，并在 `catch` 块中捕获该异常。</span><span class="sxs-lookup"><span data-stu-id="24494-164">The task's `IsFaulted` property is set to `True`, the task's `Exception.InnerException` property is set to the exception, and the exception is caught in the `catch` block.</span></span>  
  
 <span data-ttu-id="24494-165">取消注释 `throw new OperationCancelledException` 行以演示在取消异步进程时发生的情况。</span><span class="sxs-lookup"><span data-stu-id="24494-165">Uncomment the `throw new OperationCancelledException` line to demonstrate what happens when you cancel an asynchronous process.</span></span> <span data-ttu-id="24494-166">任务的 `IsCanceled` 属性设置为 `true`，并在 `catch` 块中捕获异常。</span><span class="sxs-lookup"><span data-stu-id="24494-166">The task's `IsCanceled` property is set to `true`, and the exception is caught in the `catch` block.</span></span> <span data-ttu-id="24494-167">在某些不适用于此示例的情况下，任务的 `IsFaulted` 属性设置为 `true` 且 `IsCanceled` 设置为 `false`。</span><span class="sxs-lookup"><span data-stu-id="24494-167">Under some conditions that don't apply to this example, the task's `IsFaulted` property is set to `true` and `IsCanceled` is set to `false`.</span></span>  
  
 [!code-csharp[csAsyncExceptions#2](../../../csharp/language-reference/keywords/codesnippet/CSharp/try-catch_3.cs)]  
  
## <a name="example"></a><span data-ttu-id="24494-168">示例</span><span class="sxs-lookup"><span data-stu-id="24494-168">Example</span></span>  
 <span data-ttu-id="24494-169">下面的示例阐释了在多个任务可能导致多个异常的情况中的异常处理。</span><span class="sxs-lookup"><span data-stu-id="24494-169">The following example illustrates exception handling where multiple tasks can result in multiple exceptions.</span></span> <span data-ttu-id="24494-170">`try` 块等待由 <xref:System.Threading.Tasks.Task.WhenAll%2A?displayProperty=nameWithType> 的调用返回的任务。</span><span class="sxs-lookup"><span data-stu-id="24494-170">The `try` block awaits the task that's returned by a call to <xref:System.Threading.Tasks.Task.WhenAll%2A?displayProperty=nameWithType>.</span></span> <span data-ttu-id="24494-171">应用了 WhenAll 的三个任务完成后，该任务完成。</span><span class="sxs-lookup"><span data-stu-id="24494-171">The task is complete when the three tasks to which WhenAll is applied are complete.</span></span>  
  
 <span data-ttu-id="24494-172">三个任务中的每一个都会导致异常。</span><span class="sxs-lookup"><span data-stu-id="24494-172">Each of the three tasks causes an exception.</span></span> <span data-ttu-id="24494-173">`catch` 块循环访问异常，这些异常位于由 <xref:System.Threading.Tasks.Task.WhenAll%2A?displayProperty=nameWithType> 返回的任务的 `Exception.InnerExceptions` 属性中。</span><span class="sxs-lookup"><span data-stu-id="24494-173">The `catch` block iterates through the exceptions, which are found in the `Exception.InnerExceptions` property of the task that was returned by <xref:System.Threading.Tasks.Task.WhenAll%2A?displayProperty=nameWithType>.</span></span>  
  
 [!code-csharp[csAsyncExceptions#4](../../../csharp/language-reference/keywords/codesnippet/CSharp/try-catch_4.cs)]  
  
## <a name="c-language-specification"></a><span data-ttu-id="24494-174">C# 语言规范</span><span class="sxs-lookup"><span data-stu-id="24494-174">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="24494-175">另请参阅</span><span class="sxs-lookup"><span data-stu-id="24494-175">See Also</span></span>  
 [<span data-ttu-id="24494-176">C# 参考</span><span class="sxs-lookup"><span data-stu-id="24494-176">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
 [<span data-ttu-id="24494-177">C# 编程指南</span><span class="sxs-lookup"><span data-stu-id="24494-177">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="24494-178">C# 关键字</span><span class="sxs-lookup"><span data-stu-id="24494-178">C# Keywords</span></span>](../../../csharp/language-reference/keywords/index.md)  
 [<span data-ttu-id="24494-179">try、throw 和 catch 语句 (C++)</span><span class="sxs-lookup"><span data-stu-id="24494-179">try, throw, and catch Statements (C++)</span></span>](/cpp/cpp/try-throw-and-catch-statements-cpp)  
 [<span data-ttu-id="24494-180">异常处理语句</span><span class="sxs-lookup"><span data-stu-id="24494-180">Exception Handling Statements</span></span>](../../../csharp/language-reference/keywords/exception-handling-statements.md)  
 [<span data-ttu-id="24494-181">throw</span><span class="sxs-lookup"><span data-stu-id="24494-181">throw</span></span>](../../../csharp/language-reference/keywords/throw.md)  
 [<span data-ttu-id="24494-182">try-finally</span><span class="sxs-lookup"><span data-stu-id="24494-182">try-finally</span></span>](../../../csharp/language-reference/keywords/try-finally.md)  
 [<span data-ttu-id="24494-183">如何显式引发异常</span><span class="sxs-lookup"><span data-stu-id="24494-183">How to: Explicitly Throw Exceptions</span></span>](../../../standard/exceptions/how-to-explicitly-throw-exceptions.md)
