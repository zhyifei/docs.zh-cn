---
title: 重试...Catch...Finally 语句-Visual Basic
description: 了解如何使用异常处理用于 Visual Basic Try/Catch/Finally 语句。
ms.date: 12/07/2018
f1_keywords:
- vb.Try...Catch...Finally
- vb.when
- vb.Finally
- vb.Catch
- vb.Try
helpviewer_keywords:
- Try...Catch...Finally statements
- Try statement [Visual Basic]
- try-catch exception handling, Try...Catch...Finally statements
- error handling, while running code
- Try statement [Visual Basic], Try...Catch...Finally
- Finally keyword [Visual Basic], Try...Catch...Finally
- Catch statement [Visual Basic]
- When keyword [Visual Basic]
- Visual Basic code, handling errors while running
- structured exception handling, Try...Catch...Finally statements
ms.assetid: d6488026-ccb3-42b8-a810-0d97b9d6472b
ms.custom: seodec18
ms.openlocfilehash: 126f20c86bb47e8002382e069ce6236600394aba
ms.sourcegitcommit: 8699383914c24a0df033393f55db3369db728a7b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/15/2019
ms.locfileid: "65638775"
---
# <a name="trycatchfinally-statement-visual-basic"></a><span data-ttu-id="a85a6-103">Try...Catch...Finally 语句 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="a85a6-103">Try...Catch...Finally Statement (Visual Basic)</span></span>

<span data-ttu-id="a85a6-104">提供了一种方法来处理可能会出现在给定的块的代码，同时仍在运行代码的部分或全部可能错误。</span><span class="sxs-lookup"><span data-stu-id="a85a6-104">Provides a way to handle some or all possible errors that may occur in a given block of code, while still running code.</span></span>

## <a name="syntax"></a><span data-ttu-id="a85a6-105">语法</span><span class="sxs-lookup"><span data-stu-id="a85a6-105">Syntax</span></span>

```vb
Try
    [ tryStatements ]
    [ Exit Try ]
[ Catch [ exception [ As type ] ] [ When expression ]
    [ catchStatements ]
    [ Exit Try ] ]
[ Catch ... ]
[ Finally
    [ finallyStatements ] ]
End Try
```

## <a name="parts"></a><span data-ttu-id="a85a6-106">部件</span><span class="sxs-lookup"><span data-stu-id="a85a6-106">Parts</span></span>

|<span data-ttu-id="a85a6-107">术语</span><span class="sxs-lookup"><span data-stu-id="a85a6-107">Term</span></span>|<span data-ttu-id="a85a6-108">定义</span><span class="sxs-lookup"><span data-stu-id="a85a6-108">Definition</span></span>|
|---|---|
|`tryStatements`|<span data-ttu-id="a85a6-109">可选。</span><span class="sxs-lookup"><span data-stu-id="a85a6-109">Optional.</span></span> <span data-ttu-id="a85a6-110">语句可能会出错。</span><span class="sxs-lookup"><span data-stu-id="a85a6-110">Statement(s) where an error can occur.</span></span> <span data-ttu-id="a85a6-111">可以是复合语句。</span><span class="sxs-lookup"><span data-stu-id="a85a6-111">Can be a compound statement.</span></span>|
|`Catch`|<span data-ttu-id="a85a6-112">可选。</span><span class="sxs-lookup"><span data-stu-id="a85a6-112">Optional.</span></span> <span data-ttu-id="a85a6-113">多个`Catch`允许的块。</span><span class="sxs-lookup"><span data-stu-id="a85a6-113">Multiple `Catch` blocks permitted.</span></span> <span data-ttu-id="a85a6-114">如果处理时，会发生异常`Try`块，每个`Catch`语句检查按文本顺序，以确定是否将它与处理异常，`exception`表示已引发的异常。</span><span class="sxs-lookup"><span data-stu-id="a85a6-114">If an exception occurs when processing the `Try` block, each `Catch` statement is examined in textual order to determine whether it handles the exception, with `exception` representing the exception that has been thrown.</span></span>|
|`exception`|<span data-ttu-id="a85a6-115">可选。</span><span class="sxs-lookup"><span data-stu-id="a85a6-115">Optional.</span></span> <span data-ttu-id="a85a6-116">任何变量名称。</span><span class="sxs-lookup"><span data-stu-id="a85a6-116">Any variable name.</span></span> <span data-ttu-id="a85a6-117">`exception` 的初始值是引发的错误的值。</span><span class="sxs-lookup"><span data-stu-id="a85a6-117">The initial value of `exception` is the value of the thrown error.</span></span> <span data-ttu-id="a85a6-118">用于`Catch`指定错误捕获。</span><span class="sxs-lookup"><span data-stu-id="a85a6-118">Used with `Catch` to specify the error caught.</span></span> <span data-ttu-id="a85a6-119">如果省略，`Catch`语句将捕获所有异常。</span><span class="sxs-lookup"><span data-stu-id="a85a6-119">If omitted, the `Catch` statement catches any exception.</span></span>|
|`type`|<span data-ttu-id="a85a6-120">可选。</span><span class="sxs-lookup"><span data-stu-id="a85a6-120">Optional.</span></span> <span data-ttu-id="a85a6-121">指定类筛选器的类型。</span><span class="sxs-lookup"><span data-stu-id="a85a6-121">Specifies the type of class filter.</span></span> <span data-ttu-id="a85a6-122">如果的值`exception`是由指定类型的`type`或派生类型的标识符将成为绑定到的异常对象。</span><span class="sxs-lookup"><span data-stu-id="a85a6-122">If the value of `exception` is of the type specified by `type` or of a derived type, the identifier becomes bound to the exception object.</span></span>|
|`When`|<span data-ttu-id="a85a6-123">可选。</span><span class="sxs-lookup"><span data-stu-id="a85a6-123">Optional.</span></span> <span data-ttu-id="a85a6-124">一个`Catch`语句`When`子句捕获了异常时，才`expression`的计算结果为`True`。</span><span class="sxs-lookup"><span data-stu-id="a85a6-124">A `Catch` statement with a `When` clause catches exceptions only when `expression` evaluates to `True`.</span></span> <span data-ttu-id="a85a6-125">一个`When`只在检查异常的类型之后应用子句和`expression`可能指表示异常的标识符。</span><span class="sxs-lookup"><span data-stu-id="a85a6-125">A `When` clause is applied only after checking the type of the exception, and `expression` may refer to the identifier representing the exception.</span></span>|
|`expression`|<span data-ttu-id="a85a6-126">可选。</span><span class="sxs-lookup"><span data-stu-id="a85a6-126">Optional.</span></span> <span data-ttu-id="a85a6-127">必须可隐式转换为`Boolean`。</span><span class="sxs-lookup"><span data-stu-id="a85a6-127">Must be implicitly convertible to `Boolean`.</span></span> <span data-ttu-id="a85a6-128">描述泛型的筛选器的任何表达式。</span><span class="sxs-lookup"><span data-stu-id="a85a6-128">Any expression that describes a generic filter.</span></span> <span data-ttu-id="a85a6-129">通常用于筛选的错误号。</span><span class="sxs-lookup"><span data-stu-id="a85a6-129">Typically used to filter by error number.</span></span> <span data-ttu-id="a85a6-130">用于`When`关键字来指定在其下捕获该错误的情况。</span><span class="sxs-lookup"><span data-stu-id="a85a6-130">Used with `When` keyword to specify circumstances under which the error is caught.</span></span>|
|`catchStatements`|<span data-ttu-id="a85a6-131">可选。</span><span class="sxs-lookup"><span data-stu-id="a85a6-131">Optional.</span></span> <span data-ttu-id="a85a6-132">若要处理发生在关联的错误的语句`Try`块。</span><span class="sxs-lookup"><span data-stu-id="a85a6-132">Statement(s) to handle errors that occur in the associated `Try` block.</span></span> <span data-ttu-id="a85a6-133">可以是复合语句。</span><span class="sxs-lookup"><span data-stu-id="a85a6-133">Can be a compound statement.</span></span>|
|`Exit Try`|<span data-ttu-id="a85a6-134">可选。</span><span class="sxs-lookup"><span data-stu-id="a85a6-134">Optional.</span></span> <span data-ttu-id="a85a6-135">关键字跳出`Try...Catch...Finally`结构。</span><span class="sxs-lookup"><span data-stu-id="a85a6-135">Keyword that breaks out of the `Try...Catch...Finally` structure.</span></span> <span data-ttu-id="a85a6-136">紧跟代码处继续执行`End Try`语句。</span><span class="sxs-lookup"><span data-stu-id="a85a6-136">Execution resumes with the code immediately following the `End Try` statement.</span></span> <span data-ttu-id="a85a6-137">`Finally`仍然要执行的语句。</span><span class="sxs-lookup"><span data-stu-id="a85a6-137">The `Finally` statement will still be executed.</span></span> <span data-ttu-id="a85a6-138">中不允许使用`Finally`块。</span><span class="sxs-lookup"><span data-stu-id="a85a6-138">Not allowed in `Finally` blocks.</span></span>|
|`Finally`|<span data-ttu-id="a85a6-139">可选。</span><span class="sxs-lookup"><span data-stu-id="a85a6-139">Optional.</span></span> <span data-ttu-id="a85a6-140">一个`Finally`当执行离开的任何部分时始终执行块`Try...Catch`语句。</span><span class="sxs-lookup"><span data-stu-id="a85a6-140">A `Finally` block is always executed when execution leaves any part of the `Try...Catch` statement.</span></span>|
|`finallyStatements`|<span data-ttu-id="a85a6-141">可选。</span><span class="sxs-lookup"><span data-stu-id="a85a6-141">Optional.</span></span> <span data-ttu-id="a85a6-142">所有其他错误处理发生后执行的语句。</span><span class="sxs-lookup"><span data-stu-id="a85a6-142">Statement(s) that are executed after all other error processing has occurred.</span></span>|
|`End Try`|<span data-ttu-id="a85a6-143">终止`Try...Catch...Finally`结构。</span><span class="sxs-lookup"><span data-stu-id="a85a6-143">Terminates the `Try...Catch...Finally` structure.</span></span>|

## <a name="remarks"></a><span data-ttu-id="a85a6-144">备注</span><span class="sxs-lookup"><span data-stu-id="a85a6-144">Remarks</span></span>

<span data-ttu-id="a85a6-145">如果希望在特定代码部分的过程中可能会发生特定异常，将代码放入`Try`阻止并使用`Catch`块保留控件和处理异常，如果发生这种情况。</span><span class="sxs-lookup"><span data-stu-id="a85a6-145">If you expect that a particular exception might occur during a particular section of code, put the code in a `Try` block and use a `Catch` block to retain control and handle the exception if it occurs.</span></span>

<span data-ttu-id="a85a6-146">一个`Try…Catch`语句组成`Try`块后跟一个或多个`Catch`子句指定不同异常的处理程序。</span><span class="sxs-lookup"><span data-stu-id="a85a6-146">A `Try…Catch` statement consists of a `Try` block followed by one or more `Catch` clauses, which specify handlers for various exceptions.</span></span> <span data-ttu-id="a85a6-147">引发异常`Try`阻止，Visual Basic 查找`Catch`处理异常的语句。</span><span class="sxs-lookup"><span data-stu-id="a85a6-147">When an exception is thrown in a `Try` block, Visual Basic looks for the `Catch` statement that handles the exception.</span></span> <span data-ttu-id="a85a6-148">如果匹配`Catch`找不到语句、 Visual Basic 会检查调用当前方法，并以此类推遍历调用堆栈的方法。</span><span class="sxs-lookup"><span data-stu-id="a85a6-148">If a matching `Catch` statement is not found, Visual Basic examines the method that called the current method, and so on up the call stack.</span></span> <span data-ttu-id="a85a6-149">如果没有`Catch`找到块、 Visual Basic，向用户显示未处理的异常消息和停止程序执行。</span><span class="sxs-lookup"><span data-stu-id="a85a6-149">If no `Catch` block is found, Visual Basic displays an unhandled exception message to the user and stops execution of the program.</span></span>

<span data-ttu-id="a85a6-150">可以使用多个`Catch`中的语句`Try…Catch`语句。</span><span class="sxs-lookup"><span data-stu-id="a85a6-150">You can use more than one `Catch` statement in a `Try…Catch` statement.</span></span> <span data-ttu-id="a85a6-151">如果这样的顺序做`Catch`子句很重要，因为它们会按顺序检查。</span><span class="sxs-lookup"><span data-stu-id="a85a6-151">If you do this, the order of the `Catch` clauses is significant because they are examined in order.</span></span> <span data-ttu-id="a85a6-152">在使用更笼统的子句之前获取特定性更强的异常。</span><span class="sxs-lookup"><span data-stu-id="a85a6-152">Catch the more specific exceptions before the less specific ones.</span></span>

<span data-ttu-id="a85a6-153">以下`Catch`语句条件是最不具体，并将捕获所有派生的异常<xref:System.Exception>类。</span><span class="sxs-lookup"><span data-stu-id="a85a6-153">The following `Catch` statement conditions are the least specific, and will catch all exceptions that derive from the <xref:System.Exception> class.</span></span> <span data-ttu-id="a85a6-154">应与上一通常使用这些变体之一`Catch`阻止入`Try...Catch...Finally`后捕获您期望的所有特定异常的结构。</span><span class="sxs-lookup"><span data-stu-id="a85a6-154">You should ordinarily use one of these variations as the last `Catch` block in the `Try...Catch...Finally` structure, after catching all the specific exceptions you expect.</span></span> <span data-ttu-id="a85a6-155">控制流可以永远不会达到`Catch`遵循以下任一这些变体的块。</span><span class="sxs-lookup"><span data-stu-id="a85a6-155">Control flow can never reach a `Catch` block that follows either of these variations.</span></span>

- <span data-ttu-id="a85a6-156">`type`是`Exception`，例如： `Catch ex As Exception`</span><span class="sxs-lookup"><span data-stu-id="a85a6-156">The `type` is `Exception`, for example: `Catch ex As Exception`</span></span>

- <span data-ttu-id="a85a6-157">语句没有`exception`变量，例如： `Catch`</span><span class="sxs-lookup"><span data-stu-id="a85a6-157">The statement has no `exception` variable, for example: `Catch`</span></span>

<span data-ttu-id="a85a6-158">当`Try…Catch…Finally`语句嵌套在另一个`Try`块中，Visual Basic 首先检查每个`Catch`语句中使用最内层`Try`块。</span><span class="sxs-lookup"><span data-stu-id="a85a6-158">When a `Try…Catch…Finally` statement is nested in another `Try` block, Visual Basic first examines each `Catch` statement in the innermost `Try` block.</span></span> <span data-ttu-id="a85a6-159">如果没有匹配`Catch`找到语句，则继续搜索`Catch`语句的外部`Try…Catch…Finally`块。</span><span class="sxs-lookup"><span data-stu-id="a85a6-159">If no matching `Catch` statement is found, the search proceeds to the `Catch` statements of the outer `Try…Catch…Finally` block.</span></span>

<span data-ttu-id="a85a6-160">从本地变量`Try`块中均不提供`Catch`阻止，因为它们是单独的块。</span><span class="sxs-lookup"><span data-stu-id="a85a6-160">Local variables from a `Try` block are not available in a `Catch` block because they are separate blocks.</span></span> <span data-ttu-id="a85a6-161">如果你想要在多个块中使用变量，声明外部变量`Try...Catch...Finally`结构。</span><span class="sxs-lookup"><span data-stu-id="a85a6-161">If you want to use a variable in more than one block, declare the variable outside the `Try...Catch...Finally` structure.</span></span>

> [!TIP]
> <span data-ttu-id="a85a6-162">`Try…Catch…Finally`语句是可作为 IntelliSense 代码片段。</span><span class="sxs-lookup"><span data-stu-id="a85a6-162">The `Try…Catch…Finally` statement is available as an IntelliSense code snippet.</span></span> <span data-ttu-id="a85a6-163">在代码片段管理器中，展开**代码模式-If、 为每个，Try Catch、 属性等**，然后**错误处理 （异常）**。</span><span class="sxs-lookup"><span data-stu-id="a85a6-163">In the Code Snippets Manager, expand **Code Patterns - If, For Each, Try Catch, Property, etc**, and then **Error Handling (Exceptions)**.</span></span> <span data-ttu-id="a85a6-164">有关详细信息，请参阅[代码片段](/visualstudio/ide/code-snippets)。</span><span class="sxs-lookup"><span data-stu-id="a85a6-164">For more information, see [Code Snippets](/visualstudio/ide/code-snippets).</span></span>

## <a name="finally-block"></a><span data-ttu-id="a85a6-165">Finally 块</span><span class="sxs-lookup"><span data-stu-id="a85a6-165">Finally block</span></span>

<span data-ttu-id="a85a6-166">如果必须在退出之前必须运行的一个或多个语句`Try`结构，请使用`Finally`块。</span><span class="sxs-lookup"><span data-stu-id="a85a6-166">If you have one or more statements that must run before you exit the `Try` structure, use a `Finally` block.</span></span> <span data-ttu-id="a85a6-167">控制权将传递给`Finally`阻止它传递出之前`Try…Catch`结构。</span><span class="sxs-lookup"><span data-stu-id="a85a6-167">Control passes to the `Finally` block just before it passes out of the `Try…Catch` structure.</span></span> <span data-ttu-id="a85a6-168">即使内任何位置发生异常，这是如此`Try`结构。</span><span class="sxs-lookup"><span data-stu-id="a85a6-168">This is true even if an exception occurs anywhere inside the `Try` structure.</span></span>

<span data-ttu-id="a85a6-169">一个`Finally`块可用于运行任何代码必须执行，即使出现异常。</span><span class="sxs-lookup"><span data-stu-id="a85a6-169">A `Finally` block is useful for running any code that must execute even if there is an exception.</span></span> <span data-ttu-id="a85a6-170">控制权将传递给`Finally`块而不考虑如何`Try...Catch`阻止退出。</span><span class="sxs-lookup"><span data-stu-id="a85a6-170">Control is passed to the `Finally` block regardless of how the `Try...Catch` block exits.</span></span>

<span data-ttu-id="a85a6-171">中的代码`Finally`阻止运行，即使你的代码遇到`Return`中的语句`Try`或`Catch`块。</span><span class="sxs-lookup"><span data-stu-id="a85a6-171">The code in a `Finally` block runs even if your code encounters a `Return` statement in a `Try` or `Catch` block.</span></span> <span data-ttu-id="a85a6-172">控件不会传递从`Try`或`Catch`阻止对相应`Finally`阻止在以下情况下：</span><span class="sxs-lookup"><span data-stu-id="a85a6-172">Control does not pass from a `Try` or `Catch` block to the corresponding `Finally` block in the following cases:</span></span>

- <span data-ttu-id="a85a6-173">[End 语句](end-statement.md)中遇到`Try`或`Catch`块。</span><span class="sxs-lookup"><span data-stu-id="a85a6-173">An [End Statement](end-statement.md) is encountered in the `Try` or `Catch` block.</span></span>

- <span data-ttu-id="a85a6-174">一个<xref:System.StackOverflowException>中引发`Try`或`Catch`块。</span><span class="sxs-lookup"><span data-stu-id="a85a6-174">A <xref:System.StackOverflowException> is thrown in the `Try` or `Catch` block.</span></span>

<span data-ttu-id="a85a6-175">它不是有效显式传输到执行`Finally`块。</span><span class="sxs-lookup"><span data-stu-id="a85a6-175">It is not valid to explicitly transfer execution into a `Finally` block.</span></span> <span data-ttu-id="a85a6-176">将执行共转`Finally`块不是有效的除非通过异常。</span><span class="sxs-lookup"><span data-stu-id="a85a6-176">Transferring execution out of a `Finally` block is not valid, except through an exception.</span></span>

<span data-ttu-id="a85a6-177">如果`Try`语句不包含至少一个`Catch`块中，它必须包含`Finally`块。</span><span class="sxs-lookup"><span data-stu-id="a85a6-177">If a `Try` statement does not contain at least one `Catch` block, it must contain a `Finally` block.</span></span>

> [!TIP]
> <span data-ttu-id="a85a6-178">如果不需要捕获特定异常`Using`语句的行为类似于`Try…Finally`块，并保证可供使用的资源，而不考虑如何退出块。</span><span class="sxs-lookup"><span data-stu-id="a85a6-178">If you do not have to catch specific exceptions, the `Using` statement behaves like a `Try…Finally` block, and guarantees disposal of the resources, regardless of how you exit the block.</span></span> <span data-ttu-id="a85a6-179">这是即使使用未经处理的异常，则返回 true。</span><span class="sxs-lookup"><span data-stu-id="a85a6-179">This is true even with an unhandled exception.</span></span> <span data-ttu-id="a85a6-180">有关详细信息，请参阅 [Using 语句](using-statement.md)。</span><span class="sxs-lookup"><span data-stu-id="a85a6-180">For more information, see [Using Statement](using-statement.md).</span></span>

## <a name="exception-argument"></a><span data-ttu-id="a85a6-181">异常自变量</span><span class="sxs-lookup"><span data-stu-id="a85a6-181">Exception argument</span></span>

<span data-ttu-id="a85a6-182">`Catch`块`exception`自变量是实例<xref:System.Exception>类或派生自类`Exception`类。</span><span class="sxs-lookup"><span data-stu-id="a85a6-182">The `Catch` block `exception` argument is an instance of the <xref:System.Exception> class or a class that derives from the `Exception` class.</span></span> <span data-ttu-id="a85a6-183">`Exception`类实例对应于中发生的错误`Try`块。</span><span class="sxs-lookup"><span data-stu-id="a85a6-183">The `Exception` class instance corresponds to the error that occurred in the `Try` block.</span></span>

<span data-ttu-id="a85a6-184">属性`Exception`对象帮助以确定原因和处理的异常的位置。</span><span class="sxs-lookup"><span data-stu-id="a85a6-184">The properties of the `Exception` object help to identify the cause and location of an exception.</span></span> <span data-ttu-id="a85a6-185">例如，<xref:System.Exception.StackTrace%2A>属性列出了导致异常，从而帮助你查找代码中发生错误的被调用的方法。</span><span class="sxs-lookup"><span data-stu-id="a85a6-185">For example, the <xref:System.Exception.StackTrace%2A> property lists the called methods that led to the exception, helping you find where the error occurred in the code.</span></span> <span data-ttu-id="a85a6-186"><xref:System.Exception.Message%2A> 返回描述异常的消息。</span><span class="sxs-lookup"><span data-stu-id="a85a6-186"><xref:System.Exception.Message%2A> returns a message that describes the exception.</span></span> <span data-ttu-id="a85a6-187"><xref:System.Exception.HelpLink%2A> 返回一个链接到关联的帮助文件。</span><span class="sxs-lookup"><span data-stu-id="a85a6-187"><xref:System.Exception.HelpLink%2A> returns a link to an associated Help file.</span></span> <span data-ttu-id="a85a6-188"><xref:System.Exception.InnerException%2A> 返回`Exception`导致当前异常，或其对象返回`Nothing`如果没有原始`Exception`。</span><span class="sxs-lookup"><span data-stu-id="a85a6-188"><xref:System.Exception.InnerException%2A> returns the `Exception` object that caused the current exception, or it returns `Nothing` if there is no original `Exception`.</span></span>

## <a name="considerations-when-using-a-trycatch-statement"></a><span data-ttu-id="a85a6-189">使用一试时的注意事项...Catch 语句</span><span class="sxs-lookup"><span data-stu-id="a85a6-189">Considerations when using a Try…Catch statement</span></span>

<span data-ttu-id="a85a6-190">使用`Try…Catch`语句只是为了发出的信号的异常或意外程序事件。</span><span class="sxs-lookup"><span data-stu-id="a85a6-190">Use a `Try…Catch` statement only to signal the occurrence of unusual or unanticipated program events.</span></span> <span data-ttu-id="a85a6-191">此问题的原因包括：</span><span class="sxs-lookup"><span data-stu-id="a85a6-191">Reasons for this include the following:</span></span>

- <span data-ttu-id="a85a6-192">在运行时捕获的异常创建额外的开销，并可能速度要慢于预检查，以避免异常。</span><span class="sxs-lookup"><span data-stu-id="a85a6-192">Catching exceptions at runtime creates additional overhead, and is likely to be slower than pre-checking to avoid exceptions.</span></span>

- <span data-ttu-id="a85a6-193">如果`Catch`无法正确处理块、 异常可能不会正确报告给用户。</span><span class="sxs-lookup"><span data-stu-id="a85a6-193">If a `Catch` block is not handled correctly, the exception might not be reported correctly to users.</span></span>

- <span data-ttu-id="a85a6-194">异常处理会使程序更复杂。</span><span class="sxs-lookup"><span data-stu-id="a85a6-194">Exception handling makes a program more complex.</span></span>

<span data-ttu-id="a85a6-195">不始终需要`Try…Catch`语句来检查可能发生的条件。</span><span class="sxs-lookup"><span data-stu-id="a85a6-195">You do not always need a `Try…Catch` statement to check for a condition that is likely to occur.</span></span> <span data-ttu-id="a85a6-196">以下示例检查文件是否存在之前尝试将其打开。</span><span class="sxs-lookup"><span data-stu-id="a85a6-196">The following example checks whether a file exists before trying to open it.</span></span> <span data-ttu-id="a85a6-197">这减少了用于捕获引发的异常需要<xref:System.IO.File.OpenText%2A>方法。</span><span class="sxs-lookup"><span data-stu-id="a85a6-197">This reduces the need for catching an exception thrown by the <xref:System.IO.File.OpenText%2A> method.</span></span>

[!code-vb[VbVbalrStatements#94](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#94)]

<span data-ttu-id="a85a6-198">确保在该代码`Catch`块可以正确地报告给用户，异常，通过线程安全日志记录或相应的消息。</span><span class="sxs-lookup"><span data-stu-id="a85a6-198">Ensure that code in `Catch` blocks can properly report exceptions to users, whether through thread-safe logging or appropriate messages.</span></span> <span data-ttu-id="a85a6-199">否则，异常可能仍是未知的。</span><span class="sxs-lookup"><span data-stu-id="a85a6-199">Otherwise, exceptions might remain unknown.</span></span>

## <a name="async-methods"></a><span data-ttu-id="a85a6-200">异步方法</span><span class="sxs-lookup"><span data-stu-id="a85a6-200">Async methods</span></span>

<span data-ttu-id="a85a6-201">如果标记与方法[异步](../modifiers/async.md)修饰符，可以使用[Await](../operators/await-operator.md)方法中的运算符。</span><span class="sxs-lookup"><span data-stu-id="a85a6-201">If you mark a method with the [Async](../modifiers/async.md) modifier, you can use the [Await](../operators/await-operator.md) operator in the method.</span></span> <span data-ttu-id="a85a6-202">使用语句`Await`运算符挂起执行方法，直到等待的任务完成。</span><span class="sxs-lookup"><span data-stu-id="a85a6-202">A statement with the `Await` operator suspends execution of the method until the awaited task completes.</span></span> <span data-ttu-id="a85a6-203">任务表示正在进行的工作。</span><span class="sxs-lookup"><span data-stu-id="a85a6-203">The task represents ongoing work.</span></span> <span data-ttu-id="a85a6-204">当与之关联的任务`Await`运算符完成后，执行将继续在同一方法中。</span><span class="sxs-lookup"><span data-stu-id="a85a6-204">When the task that's associated with the `Await` operator finishes, execution resumes in the same method.</span></span> <span data-ttu-id="a85a6-205">有关详细信息，请参阅[异步程序中的控制流](../../../visual-basic/programming-guide/concepts/async/control-flow-in-async-programs.md)。</span><span class="sxs-lookup"><span data-stu-id="a85a6-205">For more information, see [Control Flow in Async Programs](../../../visual-basic/programming-guide/concepts/async/control-flow-in-async-programs.md).</span></span>

<span data-ttu-id="a85a6-206">异步方法返回的任务可能最终处于错误状态，指示它完成由于未经处理的异常。</span><span class="sxs-lookup"><span data-stu-id="a85a6-206">A task returned by an Async method may end in a faulted state, indicating that it completed due to an unhandled exception.</span></span> <span data-ttu-id="a85a6-207">任务最终还会在已取消状态，这会导致`OperationCanceledException`引发从 await 表达式。</span><span class="sxs-lookup"><span data-stu-id="a85a6-207">A task may also end in a canceled state, which results in an `OperationCanceledException` being thrown out of the await expression.</span></span> <span data-ttu-id="a85a6-208">若要捕获异常的任何一种，将置于`Await`与中的任务相关联的表达式`Try`阻止，并捕捉的异常中`Catch`块。</span><span class="sxs-lookup"><span data-stu-id="a85a6-208">To catch either type of exception, place the `Await` expression that's associated with the task in a `Try` block, and catch the exception in the `Catch` block.</span></span> <span data-ttu-id="a85a6-209">本主题后面提供示例。</span><span class="sxs-lookup"><span data-stu-id="a85a6-209">An example is provided later in this topic.</span></span>

<span data-ttu-id="a85a6-210">任务可能处于错误状态，因为多个异常的负责其出错。</span><span class="sxs-lookup"><span data-stu-id="a85a6-210">A task can be in a faulted state because multiple exceptions were responsible for its faulting.</span></span> <span data-ttu-id="a85a6-211">例如，任务可能是对 <xref:System.Threading.Tasks.Task.WhenAll%2A?displayProperty=nameWithType> 调用的结果。</span><span class="sxs-lookup"><span data-stu-id="a85a6-211">For example, the task might be the result of a call to <xref:System.Threading.Tasks.Task.WhenAll%2A?displayProperty=nameWithType>.</span></span> <span data-ttu-id="a85a6-212">当等待此类任务时，捕获的异常都只有一个异常，异常，并且不能预测将捕获的异常。</span><span class="sxs-lookup"><span data-stu-id="a85a6-212">When you await such a task, the caught exception is only one of the exceptions, and you can't predict which exception will be caught.</span></span> <span data-ttu-id="a85a6-213">本主题后面提供示例。</span><span class="sxs-lookup"><span data-stu-id="a85a6-213">An example is provided later in this topic.</span></span>

<span data-ttu-id="a85a6-214">`Await`表达式不能包含在内`Catch`块或`Finally`块。</span><span class="sxs-lookup"><span data-stu-id="a85a6-214">An `Await` expression can't be inside a `Catch` block or `Finally` block.</span></span>

## <a name="iterators"></a><span data-ttu-id="a85a6-215">Iterators</span><span class="sxs-lookup"><span data-stu-id="a85a6-215">Iterators</span></span>

<span data-ttu-id="a85a6-216">迭代器函数或`Get`访问器对集合执行自定义迭代。</span><span class="sxs-lookup"><span data-stu-id="a85a6-216">An iterator function or `Get` accessor performs a custom iteration over a collection.</span></span> <span data-ttu-id="a85a6-217">迭代器使用[产生](yield-statement.md)语句返回一次的集合的每个元素。</span><span class="sxs-lookup"><span data-stu-id="a85a6-217">An iterator uses a [Yield](yield-statement.md) statement to return each element of the collection one at a time.</span></span> <span data-ttu-id="a85a6-218">使用调用迭代器函数[为每个...下一条语句](for-each-next-statement.md)。</span><span class="sxs-lookup"><span data-stu-id="a85a6-218">You call an iterator function by using a [For Each...Next Statement](for-each-next-statement.md).</span></span>

<span data-ttu-id="a85a6-219">一个`Yield`语句可以是内部`Try`块。</span><span class="sxs-lookup"><span data-stu-id="a85a6-219">A `Yield` statement can be inside a `Try` block.</span></span> <span data-ttu-id="a85a6-220">一个`Try`包含块`Yield`语句可以有`Catch`阻止，并且可以具有`Finally`块。</span><span class="sxs-lookup"><span data-stu-id="a85a6-220">A `Try` block that contains a `Yield` statement can have `Catch` blocks, and can have a `Finally` block.</span></span> <span data-ttu-id="a85a6-221">请参阅的"重试块中 Visual Basic"部分[迭代器](../../programming-guide/concepts/iterators.md)有关的示例。</span><span class="sxs-lookup"><span data-stu-id="a85a6-221">See the "Try Blocks in Visual Basic" section of [Iterators](../../programming-guide/concepts/iterators.md) for an example.</span></span>

<span data-ttu-id="a85a6-222">一个`Yield`语句不能包含在内`Catch`块或`Finally`块。</span><span class="sxs-lookup"><span data-stu-id="a85a6-222">A `Yield` statement cannot be inside a `Catch` block or a `Finally` block.</span></span>

<span data-ttu-id="a85a6-223">如果`For Each`正文 （之外的迭代器函数） 会引发异常，`Catch`未执行迭代器函数中的块，但`Finally`执行迭代器函数中的块。</span><span class="sxs-lookup"><span data-stu-id="a85a6-223">If the `For Each` body (outside of the iterator function) throws an exception, a `Catch` block in the iterator function is not executed, but a `Finally` block in the iterator function is executed.</span></span> <span data-ttu-id="a85a6-224">一个`Catch`迭代器函数内的块将捕获在迭代器函数内部发生的异常。</span><span class="sxs-lookup"><span data-stu-id="a85a6-224">A `Catch` block inside an iterator function catches only exceptions that occur inside the iterator function.</span></span>

## <a name="partial-trust-situations"></a><span data-ttu-id="a85a6-225">部分信任情况下</span><span class="sxs-lookup"><span data-stu-id="a85a6-225">Partial-trust situations</span></span>

<span data-ttu-id="a85a6-226">在部分信任情况下，例如网络共享上托管的应用程序`Try...Catch...Finally`不会捕获包含在调用的方法调用之前发生的安全异常。</span><span class="sxs-lookup"><span data-stu-id="a85a6-226">In partial-trust situations, such as an application hosted on a network share, `Try...Catch...Finally` does not catch security exceptions that occur before the method that contains the call is invoked.</span></span> <span data-ttu-id="a85a6-227">以下示例中，将其放在服务器共享上并从这里，运行时生成错误"System.Security.SecurityException:请求失败。"</span><span class="sxs-lookup"><span data-stu-id="a85a6-227">The following example, when you put it on a server share and run from there, produces the error "System.Security.SecurityException: Request Failed."</span></span> <span data-ttu-id="a85a6-228">有关安全异常的详细信息，请参阅<xref:System.Security.SecurityException>类。</span><span class="sxs-lookup"><span data-stu-id="a85a6-228">For more information about security exceptions, see the <xref:System.Security.SecurityException> class.</span></span>

[!code-vb[VbVbalrStatements#85](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#85)]

<span data-ttu-id="a85a6-229">在这种部分信任情况下，您必须将放`Process.Start`在单独的语句`Sub`。</span><span class="sxs-lookup"><span data-stu-id="a85a6-229">In such a partial-trust situation, you have to put the `Process.Start` statement in a separate `Sub`.</span></span> <span data-ttu-id="a85a6-230">首次调用`Sub`将失败。</span><span class="sxs-lookup"><span data-stu-id="a85a6-230">The initial call to the `Sub` will fail.</span></span> <span data-ttu-id="a85a6-231">这使得`Try...Catch`捕获它之前`Sub`，其中包含`Process.Start`启动和产生安全异常。</span><span class="sxs-lookup"><span data-stu-id="a85a6-231">This enables `Try...Catch` to catch it before the `Sub` that contains `Process.Start` is started and the security exception produced.</span></span>

## <a name="examples"></a><span data-ttu-id="a85a6-232">示例</span><span class="sxs-lookup"><span data-stu-id="a85a6-232">Examples</span></span>

### <a name="the-structure-of-trycatchfinally"></a><span data-ttu-id="a85a6-233">Try 结构...Catch...最后</span><span class="sxs-lookup"><span data-stu-id="a85a6-233">The structure of Try...Catch...Finally</span></span>

<span data-ttu-id="a85a6-234">下面的示例演示了结构`Try...Catch...Finally`语句。</span><span class="sxs-lookup"><span data-stu-id="a85a6-234">The following example illustrates the structure of the `Try...Catch...Finally` statement.</span></span>

[!code-vb[VbVbalrStatements#86](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#86)]  

### <a name="exception-in-a-method-called-from-a-try-block"></a><span data-ttu-id="a85a6-235">在 Try 块中调用的方法中的异常</span><span class="sxs-lookup"><span data-stu-id="a85a6-235">Exception in a method called from a Try block</span></span>

<span data-ttu-id="a85a6-236">在以下示例中，`CreateException`方法会抛出`NullReferenceException`。</span><span class="sxs-lookup"><span data-stu-id="a85a6-236">In the following example, the `CreateException` method throws a `NullReferenceException`.</span></span> <span data-ttu-id="a85a6-237">生成异常的代码不在`Try`块。</span><span class="sxs-lookup"><span data-stu-id="a85a6-237">The code that generates the exception is not in a `Try` block.</span></span> <span data-ttu-id="a85a6-238">因此，`CreateException`方法不会处理异常。</span><span class="sxs-lookup"><span data-stu-id="a85a6-238">Therefore, the `CreateException` method does not handle the exception.</span></span> <span data-ttu-id="a85a6-239">`RunSample`方法未处理该异常，因为在调用`CreateException`方法处于`Try`块。</span><span class="sxs-lookup"><span data-stu-id="a85a6-239">The `RunSample` method does handle the exception because the call to the `CreateException` method is in a `Try` block.</span></span>

<span data-ttu-id="a85a6-240">该示例包含`Catch`几种类型的异常的语句按从最具体到最抽象。</span><span class="sxs-lookup"><span data-stu-id="a85a6-240">The example includes `Catch` statements for several types of exceptions, ordered from the most specific to the most general.</span></span>

[!code-vb[VbVbalrStatements#91](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#91)]

### <a name="the-catch-when-statement"></a><span data-ttu-id="a85a6-241">当 Catch 语句</span><span class="sxs-lookup"><span data-stu-id="a85a6-241">The Catch When statement</span></span>

<span data-ttu-id="a85a6-242">下面的示例演示如何使用`Catch When`要作为筛选依据的条件表达式的语句。</span><span class="sxs-lookup"><span data-stu-id="a85a6-242">The following example shows how to use a `Catch When` statement to filter on a conditional expression.</span></span> <span data-ttu-id="a85a6-243">如果条件表达式的计算结果为`True`中的代码`Catch`块将运行。</span><span class="sxs-lookup"><span data-stu-id="a85a6-243">If the conditional expression evaluates to `True`, the code in the `Catch` block runs.</span></span>

[!code-vb[VbVbalrStatements#92](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#92)]

### <a name="nested-try-statements"></a><span data-ttu-id="a85a6-244">嵌套的 Try 语句</span><span class="sxs-lookup"><span data-stu-id="a85a6-244">Nested Try statements</span></span>

<span data-ttu-id="a85a6-245">下面的示例有`Try…Catch`中包含的语句`Try`块。</span><span class="sxs-lookup"><span data-stu-id="a85a6-245">The following example has a `Try…Catch` statement that is contained in a `Try` block.</span></span> <span data-ttu-id="a85a6-246">内部`Catch`块将引发异常有其`InnerException`属性设置为原始异常。</span><span class="sxs-lookup"><span data-stu-id="a85a6-246">The inner `Catch` block throws an exception that has its `InnerException` property set to the original exception.</span></span> <span data-ttu-id="a85a6-247">外部`Catch`块都会报告自己的异常和内部异常。</span><span class="sxs-lookup"><span data-stu-id="a85a6-247">The outer `Catch` block reports its own exception and the inner exception.</span></span>

[!code-vb[VbVbalrStatements#93](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#93)]

### <a name="exception-handling-for-async-methods"></a><span data-ttu-id="a85a6-248">异步方法处理异常</span><span class="sxs-lookup"><span data-stu-id="a85a6-248">Exception handling for async methods</span></span>

<span data-ttu-id="a85a6-249">下面的示例阐释异步方法的异常处理。</span><span class="sxs-lookup"><span data-stu-id="a85a6-249">The following example illustrates exception handling for async methods.</span></span> <span data-ttu-id="a85a6-250">若要捕获应用于异步任务，异常`Await`表达式是在`Try`的调用方和异常块中捕获`Catch`块。</span><span class="sxs-lookup"><span data-stu-id="a85a6-250">To catch an exception that applies to an async task, the `Await` expression is in a `Try` block of the caller, and the exception is caught in the `Catch` block.</span></span>

<span data-ttu-id="a85a6-251">在示例中取消注释 `Throw New Exception` 行以演示异常处理。</span><span class="sxs-lookup"><span data-stu-id="a85a6-251">Uncomment the `Throw New Exception` line in the example to demonstrate exception handling.</span></span> <span data-ttu-id="a85a6-252">在捕获的异常`Catch`阻止的任务`IsFaulted`属性设置为`True`，和任务的`Exception.InnerException`属性设置为异常。</span><span class="sxs-lookup"><span data-stu-id="a85a6-252">The exception is caught in the `Catch` block, the task's `IsFaulted` property is set to `True`, and the task's `Exception.InnerException` property is set to the exception.</span></span>

<span data-ttu-id="a85a6-253">取消注释 `Throw New OperationCancelledException` 行以演示在取消异步进程时发生的情况。</span><span class="sxs-lookup"><span data-stu-id="a85a6-253">Uncomment the `Throw New OperationCancelledException` line to demonstrate what happens when you cancel an asynchronous process.</span></span> <span data-ttu-id="a85a6-254">在捕获的异常`Catch`块中，并且该任务`IsCanceled`属性设置为`True`。</span><span class="sxs-lookup"><span data-stu-id="a85a6-254">The exception is caught in the `Catch` block, and the task's `IsCanceled` property is set to `True`.</span></span> <span data-ttu-id="a85a6-255">但是，在不会应用于此示例中，某些情况下`IsFaulted`设置为`True`并`IsCanceled`设置为`False`。</span><span class="sxs-lookup"><span data-stu-id="a85a6-255">However, under some conditions that don't apply to this example, `IsFaulted` is set to `True` and `IsCanceled` is set to `False`.</span></span>

[!code-vb[csAsyncExceptions#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/csasyncexceptions/vb/class1.vb#1)]

### <a name="handling-multiple-exceptions-in-async-methods"></a><span data-ttu-id="a85a6-256">异步方法中的多个异常处理</span><span class="sxs-lookup"><span data-stu-id="a85a6-256">Handling multiple exceptions in async methods</span></span>

<span data-ttu-id="a85a6-257">下面的示例阐释了在多个任务可能导致多个异常的情况中的异常处理。</span><span class="sxs-lookup"><span data-stu-id="a85a6-257">The following example illustrates exception handling where multiple tasks can result in multiple exceptions.</span></span> <span data-ttu-id="a85a6-258">`Try`块都有`Await`任务的表达式的<xref:System.Threading.Tasks.Task.WhenAll%2A?displayProperty=nameWithType>返回。</span><span class="sxs-lookup"><span data-stu-id="a85a6-258">The `Try` block has the `Await` expression for the task that <xref:System.Threading.Tasks.Task.WhenAll%2A?displayProperty=nameWithType> returned.</span></span> <span data-ttu-id="a85a6-259">任务已完成时向其三个任务<xref:System.Threading.Tasks.Task.WhenAll%2A?displayProperty=nameWithType>应用完成。</span><span class="sxs-lookup"><span data-stu-id="a85a6-259">The task is complete when the three tasks to which <xref:System.Threading.Tasks.Task.WhenAll%2A?displayProperty=nameWithType> is applied are complete.</span></span>

<span data-ttu-id="a85a6-260">三个任务中的每一个都会导致异常。</span><span class="sxs-lookup"><span data-stu-id="a85a6-260">Each of the three tasks causes an exception.</span></span> <span data-ttu-id="a85a6-261">`Catch`块循环访问异常，异常中找到`Exception.InnerExceptions`任务属性的`Task.WhenAll`返回。</span><span class="sxs-lookup"><span data-stu-id="a85a6-261">The `Catch` block iterates through the exceptions, which are found in the `Exception.InnerExceptions` property of the task that `Task.WhenAll` returned.</span></span>

[!code-vb[csAsyncExceptions#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/csasyncexceptions/vb/class1.vb#3)]

## <a name="see-also"></a><span data-ttu-id="a85a6-262">请参阅</span><span class="sxs-lookup"><span data-stu-id="a85a6-262">See also</span></span>

- <xref:Microsoft.VisualBasic.Information.Err%2A>
- <xref:System.Exception>
- [<span data-ttu-id="a85a6-263">Exit 语句</span><span class="sxs-lookup"><span data-stu-id="a85a6-263">Exit Statement</span></span>](exit-statement.md)
- [<span data-ttu-id="a85a6-264">On Error 语句</span><span class="sxs-lookup"><span data-stu-id="a85a6-264">On Error Statement</span></span>](on-error-statement.md)
- [<span data-ttu-id="a85a6-265">有关使用代码片段的最佳做法</span><span class="sxs-lookup"><span data-stu-id="a85a6-265">Best Practices for Using Code Snippets</span></span>](/visualstudio/ide/best-practices-for-using-code-snippets)
- [<span data-ttu-id="a85a6-266">异常处理</span><span class="sxs-lookup"><span data-stu-id="a85a6-266">Exception Handling</span></span>](../../../standard/parallel-programming/exception-handling-task-parallel-library.md)
- [<span data-ttu-id="a85a6-267">Throw 语句</span><span class="sxs-lookup"><span data-stu-id="a85a6-267">Throw Statement</span></span>](throw-statement.md)
