---
title: Async (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.Async
helpviewer_keywords:
- Async [Visual Basic]
- Async keyword [Visual Basic]
ms.assetid: 1be8b4b5-9689-41b5-bd33-b906bfd53bc5
ms.openlocfilehash: aaf5a95edb9cba9726163be3925b006a7641597c
ms.sourcegitcommit: ad800f019ac976cb669e635fb0ea49db740e6890
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/29/2019
ms.locfileid: "73040860"
---
# <a name="async-visual-basic"></a><span data-ttu-id="4fb5a-102">Async (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="4fb5a-102">Async (Visual Basic)</span></span>

<span data-ttu-id="4fb5a-103">`Async` 修饰符指示它修改的方法或[lambda 表达式](../../../visual-basic/programming-guide/language-features/procedures/lambda-expressions.md)是异步的。</span><span class="sxs-lookup"><span data-stu-id="4fb5a-103">The `Async` modifier indicates that the method or [lambda expression](../../../visual-basic/programming-guide/language-features/procedures/lambda-expressions.md) that it modifies is asynchronous.</span></span> <span data-ttu-id="4fb5a-104">此类方法称为*异步方法*。</span><span class="sxs-lookup"><span data-stu-id="4fb5a-104">Such methods are referred to as *async methods*.</span></span>

<span data-ttu-id="4fb5a-105">异步方法提供了一种简便方式来完成可能需要长时间运行的工作，而不必阻止调用方的线程。</span><span class="sxs-lookup"><span data-stu-id="4fb5a-105">An async method provides a convenient way to do potentially long-running work without blocking the caller's thread.</span></span> <span data-ttu-id="4fb5a-106">异步方法的调用方可以恢复其工作，而无需等待异步方法完成。</span><span class="sxs-lookup"><span data-stu-id="4fb5a-106">The caller of an async method can resume its work without waiting for the async method to finish.</span></span>

> [!NOTE]
> <span data-ttu-id="4fb5a-107">`Async` 和 `Await` 关键字是在 Visual Studio 2012 中引入的。</span><span class="sxs-lookup"><span data-stu-id="4fb5a-107">The `Async` and `Await` keywords were introduced in Visual Studio 2012.</span></span> <span data-ttu-id="4fb5a-108">有关异步编程的介绍，请参阅[使用 async 和 Await 进行异步编程](../../../visual-basic/programming-guide/concepts/async/index.md)。</span><span class="sxs-lookup"><span data-stu-id="4fb5a-108">For an introduction to async programming, see [Asynchronous Programming with Async and Await](../../../visual-basic/programming-guide/concepts/async/index.md).</span></span>

<span data-ttu-id="4fb5a-109">下面的示例显示一个异步方法的结构。</span><span class="sxs-lookup"><span data-stu-id="4fb5a-109">The following example shows the structure of an async method.</span></span> <span data-ttu-id="4fb5a-110">按照约定，异步方法名的结尾为“Async”。</span><span class="sxs-lookup"><span data-stu-id="4fb5a-110">By convention, async method names end in "Async."</span></span>

```vb
Public Async Function ExampleMethodAsync() As Task(Of Integer)
    ' . . .

    ' At the Await expression, execution in this method is suspended and,
    ' if AwaitedProcessAsync has not already finished, control returns
    ' to the caller of ExampleMethodAsync. When the awaited task is
    ' completed, this method resumes execution.
    Dim exampleInt As Integer = Await AwaitedProcessAsync()

    ' . . .

    ' The return statement completes the task. Any method that is
    ' awaiting ExampleMethodAsync can now get the integer result.
    Return exampleInt
End Function
```

<span data-ttu-id="4fb5a-111">通常，由 `Async` 关键字修改的方法包含至少一个[Await](../../../visual-basic/language-reference/modifiers/async.md)表达式或语句。</span><span class="sxs-lookup"><span data-stu-id="4fb5a-111">Typically, a method modified by the `Async` keyword contains at least one [Await](../../../visual-basic/language-reference/modifiers/async.md) expression or statement.</span></span> <span data-ttu-id="4fb5a-112">方法同步运行，直至到达第一个 `Await`，此时暂停，直到等待的任务完成。</span><span class="sxs-lookup"><span data-stu-id="4fb5a-112">The method runs synchronously until it reaches the first `Await`, at which point it suspends until the awaited task completes.</span></span> <span data-ttu-id="4fb5a-113">同时，控制权返回给方法的调用方。</span><span class="sxs-lookup"><span data-stu-id="4fb5a-113">In the meantime, control is returned to the caller of the method.</span></span> <span data-ttu-id="4fb5a-114">如果该方法不包含 `Await` 表达式或语句，则该方法将不会被挂起并作为同步方法执行。</span><span class="sxs-lookup"><span data-stu-id="4fb5a-114">If the method doesn't contain an `Await` expression or statement, the method isn't suspended and executes as a synchronous method does.</span></span> <span data-ttu-id="4fb5a-115">编译器警告将通知你不包含 `Await` 的任何异步方法，因为该情况可能表示存在错误。</span><span class="sxs-lookup"><span data-stu-id="4fb5a-115">A compiler warning alerts you to any async methods that don't contain `Await` because that situation might indicate an error.</span></span> <span data-ttu-id="4fb5a-116">有关详细信息，请参阅[编译器错误](../error-messages/bc42358.md)。</span><span class="sxs-lookup"><span data-stu-id="4fb5a-116">For more information, see the [compiler error](../error-messages/bc42358.md).</span></span>

<span data-ttu-id="4fb5a-117">`Async` 关键字是一个非保留的关键字。</span><span class="sxs-lookup"><span data-stu-id="4fb5a-117">The `Async` keyword is an unreserved keyword.</span></span> <span data-ttu-id="4fb5a-118">在修饰方法或 lambda 表达式时，它是关键字。</span><span class="sxs-lookup"><span data-stu-id="4fb5a-118">It is a keyword when it modifies a method or a lambda expression.</span></span> <span data-ttu-id="4fb5a-119">在所有其他上下文中，都会将其解释为标识符。</span><span class="sxs-lookup"><span data-stu-id="4fb5a-119">In all other contexts, it is interpreted as an identifier.</span></span>

## <a name="return-types"></a><span data-ttu-id="4fb5a-120">返回类型</span><span class="sxs-lookup"><span data-stu-id="4fb5a-120">Return Types</span></span>

<span data-ttu-id="4fb5a-121">异步方法可以是[Sub](../../../visual-basic/programming-guide/language-features/procedures/sub-procedures.md)过程，也可以是返回类型为 <xref:System.Threading.Tasks.Task> 或 <xref:System.Threading.Tasks.Task%601>的[函数](../../../visual-basic/programming-guide/language-features/procedures/function-procedures.md)过程。</span><span class="sxs-lookup"><span data-stu-id="4fb5a-121">An async method is either a [Sub](../../../visual-basic/programming-guide/language-features/procedures/sub-procedures.md) procedure, or a [Function](../../../visual-basic/programming-guide/language-features/procedures/function-procedures.md) procedure that has a return type of <xref:System.Threading.Tasks.Task> or <xref:System.Threading.Tasks.Task%601>.</span></span> <span data-ttu-id="4fb5a-122">方法不能声明任何[ByRef](../../../visual-basic/language-reference/modifiers/byref.md)参数。</span><span class="sxs-lookup"><span data-stu-id="4fb5a-122">The method cannot declare any [ByRef](../../../visual-basic/language-reference/modifiers/byref.md) parameters.</span></span>

<span data-ttu-id="4fb5a-123">如果方法的[返回](../../../visual-basic/language-reference/statements/return-statement.md)语句具有类型为 TResult 的操作数，则为异步方法的返回类型指定 `Task(Of TResult)`。</span><span class="sxs-lookup"><span data-stu-id="4fb5a-123">You specify `Task(Of TResult)` for the return type of an async method if the [Return](../../../visual-basic/language-reference/statements/return-statement.md) statement of the method has an operand of type TResult.</span></span> <span data-ttu-id="4fb5a-124">如果当方法完成时未返回有意义的值，则应使用 `Task`。</span><span class="sxs-lookup"><span data-stu-id="4fb5a-124">You use `Task` if no meaningful value is returned when the method is completed.</span></span> <span data-ttu-id="4fb5a-125">即对方法的调用返回 `Task`，但 `Task` 完成时，等待 `Await` 的任何 `Task` 语句不会产生结果值。</span><span class="sxs-lookup"><span data-stu-id="4fb5a-125">That is, a call to the method returns a `Task`, but when the `Task` is completed, any `Await` statement that's awaiting the `Task` doesn’t produce a result value.</span></span>

<span data-ttu-id="4fb5a-126">异步子例程主要用于定义需要 `Sub` 程序的事件处理程序。</span><span class="sxs-lookup"><span data-stu-id="4fb5a-126">Async subroutines are used primarily to define event handlers where a `Sub` procedure is required.</span></span> <span data-ttu-id="4fb5a-127">异步子程序的调用方不能等待它，并且无法捕获该方法引发的异常。</span><span class="sxs-lookup"><span data-stu-id="4fb5a-127">The caller of an async subroutine can't await it and can't catch exceptions that the method throws.</span></span>

<span data-ttu-id="4fb5a-128">有关详细信息和示例，请参阅[异步返回类型](../../../visual-basic/programming-guide/concepts/async/async-return-types.md)。</span><span class="sxs-lookup"><span data-stu-id="4fb5a-128">For more information and examples, see [Async Return Types](../../../visual-basic/programming-guide/concepts/async/async-return-types.md).</span></span>

## <a name="example"></a><span data-ttu-id="4fb5a-129">示例</span><span class="sxs-lookup"><span data-stu-id="4fb5a-129">Example</span></span>

<span data-ttu-id="4fb5a-130">下面的示例显示一个异步事件处理程序、一个异步 lambda 表达式和一个异步方法。</span><span class="sxs-lookup"><span data-stu-id="4fb5a-130">The following examples show an async event handler, an async lambda expression, and an async method.</span></span> <span data-ttu-id="4fb5a-131">有关使用这些元素的完整示例，请参阅[演练：使用 Async 和 Await 访问 Web](../../../visual-basic/programming-guide/concepts/async/walkthrough-accessing-the-web-by-using-async-and-await.md)。</span><span class="sxs-lookup"><span data-stu-id="4fb5a-131">For a full example that uses these elements, see [Walkthrough: Accessing the Web by Using Async and Await](../../../visual-basic/programming-guide/concepts/async/walkthrough-accessing-the-web-by-using-async-and-await.md).</span></span> <span data-ttu-id="4fb5a-132">可从[开发人员代码示例](https://code.msdn.microsoft.com/Async-Sample-Accessing-the-9c10497f)下载演练代码。</span><span class="sxs-lookup"><span data-stu-id="4fb5a-132">You can download the walkthrough code from [Developer Code Samples](https://code.msdn.microsoft.com/Async-Sample-Accessing-the-9c10497f).</span></span>

```vb
' An event handler must be a Sub procedure.
Async Sub button1_Click(sender As Object, e As RoutedEventArgs) Handles button1.Click
    textBox1.Clear()
    ' SumPageSizesAsync is a method that returns a Task.
    Await SumPageSizesAsync()
    textBox1.Text = vbCrLf & "Control returned to button1_Click."
End Sub

' The following async lambda expression creates an equivalent anonymous
' event handler.
AddHandler button1.Click, Async Sub(sender, e)
                              textBox1.Clear()
                              ' SumPageSizesAsync is a method that returns a Task.
                              Await SumPageSizesAsync()
                              textBox1.Text = vbCrLf & "Control returned to button1_Click."
                          End Sub

' The following async method returns a Task(Of T).
' A typical call awaits the Byte array result:
'      Dim result As Byte() = Await GetURLContents("https://msdn.com")
Private Async Function GetURLContentsAsync(url As String) As Task(Of Byte())

    ' The downloaded resource ends up in the variable named content.
    Dim content = New MemoryStream()

    ' Initialize an HttpWebRequest for the current URL.
    Dim webReq = CType(WebRequest.Create(url), HttpWebRequest)

    ' Send the request to the Internet resource and wait for
    ' the response.
    Using response As WebResponse = Await webReq.GetResponseAsync()
        ' Get the data stream that is associated with the specified URL.
        Using responseStream As Stream = response.GetResponseStream()
            ' Read the bytes in responseStream and copy them to content.
            ' CopyToAsync returns a Task, not a Task<T>.
            Await responseStream.CopyToAsync(content)
        End Using
    End Using

    ' Return the result as a byte array.
    Return content.ToArray()
End Function
```

## <a name="see-also"></a><span data-ttu-id="4fb5a-133">请参阅</span><span class="sxs-lookup"><span data-stu-id="4fb5a-133">See also</span></span>

- <xref:System.Runtime.CompilerServices.AsyncStateMachineAttribute>
- [<span data-ttu-id="4fb5a-134">Await 运算符</span><span class="sxs-lookup"><span data-stu-id="4fb5a-134">Await Operator</span></span>](../../../visual-basic/language-reference/operators/await-operator.md)
- [<span data-ttu-id="4fb5a-135">使用 Async 和 Await 的异步编程</span><span class="sxs-lookup"><span data-stu-id="4fb5a-135">Asynchronous Programming with Async and Await</span></span>](../../../visual-basic/programming-guide/concepts/async/index.md)
- [<span data-ttu-id="4fb5a-136">演练：使用 Async 和 Await 访问 Web</span><span class="sxs-lookup"><span data-stu-id="4fb5a-136">Walkthrough: Accessing the Web by Using Async and Await</span></span>](../../../visual-basic/programming-guide/concepts/async/walkthrough-accessing-the-web-by-using-async-and-await.md)
