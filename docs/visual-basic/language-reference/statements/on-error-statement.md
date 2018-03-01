---
title: "On Error 语句 (Visual Basic)"
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vb.OnError
helpviewer_keywords:
- Visual Basic code, control flow
- Resume Next statement [Visual Basic]
- errors [Visual Basic], trapping
- error handling, On Error statement
- Next statement [Visual Basic], On Error
- control flow [Visual Basic], branching
- Error keyword [Visual Basic]
- execution [Visual Basic], conditional
- Resume statement [Visual Basic], and On Error statement
- Error statement [Visual Basic], and On Error statement
- GoTo statement [Visual Basic], and On Error statement
- branching [Visual Basic], on error
- conditional statements [Visual Basic], On Error
- On Error statement [Visual Basic], syntax
- On keyword [Visual Basic]
- run-time errors [Visual Basic], handling
- On Error statement [Visual Basic]
ms.assetid: ff947930-fb84-40cf-bd66-1ea219561d5c
caps.latest.revision: 
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 96baa5d91d0a600b84ed832fb1e3b1ed71a9d89d
ms.sourcegitcommit: 2142a4732bb4ff519b9817db4c24a237b9810d4b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/05/2018
---
# <a name="on-error-statement-visual-basic"></a><span data-ttu-id="110a6-102">On Error 语句 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="110a6-102">On Error Statement (Visual Basic)</span></span>
<span data-ttu-id="110a6-103">启用错误处理例程，并指定过程; 中的例程的位置此外可以用于禁用错误处理例程。</span><span class="sxs-lookup"><span data-stu-id="110a6-103">Enables an error-handling routine and specifies the location of the routine within a procedure; can also be used to disable an error-handling routine.</span></span>  
  
 <span data-ttu-id="110a6-104">如果错误处理，不会发生任何运行时错误是致命： 显示错误消息，并且停止执行。</span><span class="sxs-lookup"><span data-stu-id="110a6-104">Without error handling, any run-time error that occurs is fatal: an error message is displayed, and execution stops.</span></span>  
  
 <span data-ttu-id="110a6-105">只要有可能，我们建议你使用结构化的异常处理在代码中，而不是使用非结构化的异常处理和`On Error`语句。</span><span class="sxs-lookup"><span data-stu-id="110a6-105">Whenever possible, we suggest you use structured exception handling in your code, rather than using unstructured exception handling and the `On Error` statement.</span></span> <span data-ttu-id="110a6-106">有关详细信息，请参阅 [Try...Catch...Finally 语句](../../../visual-basic/language-reference/statements/try-catch-finally-statement.md)。</span><span class="sxs-lookup"><span data-stu-id="110a6-106">For more information, see [Try...Catch...Finally Statement](../../../visual-basic/language-reference/statements/try-catch-finally-statement.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="110a6-107">`Error`关键字还用于[Error 语句](../../../visual-basic/language-reference/statements/error-statement.md)，这为了向后兼容受支持。</span><span class="sxs-lookup"><span data-stu-id="110a6-107">The `Error` keyword is also used in the [Error Statement](../../../visual-basic/language-reference/statements/error-statement.md), which is supported for backward compatibility.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="110a6-108">语法</span><span class="sxs-lookup"><span data-stu-id="110a6-108">Syntax</span></span>  
  
```  
On Error { GoTo [ line | 0 | -1 ] | Resume Next }  
```  
  
## <a name="parts"></a><span data-ttu-id="110a6-109">部件</span><span class="sxs-lookup"><span data-stu-id="110a6-109">Parts</span></span>  
  
|<span data-ttu-id="110a6-110">术语</span><span class="sxs-lookup"><span data-stu-id="110a6-110">Term</span></span>|<span data-ttu-id="110a6-111">定义</span><span class="sxs-lookup"><span data-stu-id="110a6-111">Definition</span></span>|  
|---|---|  
|<span data-ttu-id="110a6-112">`GoTo` `line`</span><span class="sxs-lookup"><span data-stu-id="110a6-112">`GoTo` `line`</span></span>|<span data-ttu-id="110a6-113">启用开始指定所需的代码行的错误处理例程`line`自变量。</span><span class="sxs-lookup"><span data-stu-id="110a6-113">Enables the error-handling routine that starts at the line specified in the required `line` argument.</span></span> <span data-ttu-id="110a6-114">`line`自变量可以是任何行标签或行号。</span><span class="sxs-lookup"><span data-stu-id="110a6-114">The `line` argument is any line label or line number.</span></span> <span data-ttu-id="110a6-115">如果发生运行时错误，则控制分支到指定的行，以激活错误处理程序。</span><span class="sxs-lookup"><span data-stu-id="110a6-115">If a run-time error occurs, control branches to the specified line, making the error handler active.</span></span> <span data-ttu-id="110a6-116">指定的行必须是相同的过程中`On Error`语句或编译时错误会发生。</span><span class="sxs-lookup"><span data-stu-id="110a6-116">The specified line must be in the same procedure as the `On Error` statement, or a compile-time error will occur.</span></span>|  
|<span data-ttu-id="110a6-117">`GoTo` 0</span><span class="sxs-lookup"><span data-stu-id="110a6-117">`GoTo` 0</span></span>|<span data-ttu-id="110a6-118">禁用当前的过程中启用的错误处理和重置为`Nothing`。</span><span class="sxs-lookup"><span data-stu-id="110a6-118">Disables enabled error handler in the current procedure and resets it to `Nothing`.</span></span>|  
|<span data-ttu-id="110a6-119">`GoTo` -1</span><span class="sxs-lookup"><span data-stu-id="110a6-119">`GoTo` -1</span></span>|<span data-ttu-id="110a6-120">禁用当前的过程中已启用的异常和重置为`Nothing`。</span><span class="sxs-lookup"><span data-stu-id="110a6-120">Disables enabled exception in the current procedure and resets it to `Nothing`.</span></span>|  
|`Resume Next`|<span data-ttu-id="110a6-121">指定的运行时错误时，控件跳转到紧跟其中发生错误，并从该点继续执行该语句的语句。</span><span class="sxs-lookup"><span data-stu-id="110a6-121">Specifies that when a run-time error occurs, control goes to the statement immediately following the statement where the error occurred, and execution continues from that point.</span></span> <span data-ttu-id="110a6-122">使用此窗体而非`On Error GoTo`时访问的对象。</span><span class="sxs-lookup"><span data-stu-id="110a6-122">Use this form rather than `On Error GoTo` when accessing objects.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="110a6-123">备注</span><span class="sxs-lookup"><span data-stu-id="110a6-123">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="110a6-124">我们建议你使用结构化的异常处理，只要有可能，在代码中，而不是无需使用非结构化的异常处理和`On Error`语句。</span><span class="sxs-lookup"><span data-stu-id="110a6-124">We recommend that you use structured exception handling in your code whenever possible, rather than using unstructured exception handling and the `On Error` statement.</span></span> <span data-ttu-id="110a6-125">有关详细信息，请参阅 [Try...Catch...Finally 语句](../../../visual-basic/language-reference/statements/try-catch-finally-statement.md)。</span><span class="sxs-lookup"><span data-stu-id="110a6-125">For more information, see [Try...Catch...Finally Statement](../../../visual-basic/language-reference/statements/try-catch-finally-statement.md).</span></span>  
  
 <span data-ttu-id="110a6-126">"Enabled"错误处理程序是指通过开启`On Error`语句。</span><span class="sxs-lookup"><span data-stu-id="110a6-126">An "enabled" error handler is one that is turned on by an `On Error` statement.</span></span> <span data-ttu-id="110a6-127">"活动"的错误处理程序是已启用的处理程序正在处理错误。</span><span class="sxs-lookup"><span data-stu-id="110a6-127">An "active" error handler is an enabled handler that is in the process of handling an error.</span></span>  
  
 <span data-ttu-id="110a6-128">错误处理程序处于活动状态时如果发生错误 (之间发生错误的和`Resume`， `Exit Sub`， `Exit Function`，或`Exit Property`语句)，则当前过程的错误处理程序无法处理该错误。</span><span class="sxs-lookup"><span data-stu-id="110a6-128">If an error occurs while an error handler is active (between the occurrence of the error and a `Resume`, `Exit Sub`, `Exit Function`, or `Exit Property` statement), the current procedure's error handler cannot handle the error.</span></span> <span data-ttu-id="110a6-129">控制权返回给调用的过程。</span><span class="sxs-lookup"><span data-stu-id="110a6-129">Control returns to the calling procedure.</span></span>  
  
 <span data-ttu-id="110a6-130">如果调用过程有一个已启用的错误处理程序，它将激活地处理错误。</span><span class="sxs-lookup"><span data-stu-id="110a6-130">If the calling procedure has an enabled error handler, it is activated to handle the error.</span></span> <span data-ttu-id="110a6-131">如果调用过程的错误处理程序还处于活动状态的控制权将传递回通过前一个调用过程中，直到找到已启用，但非活动状态、 错误处理程序。</span><span class="sxs-lookup"><span data-stu-id="110a6-131">If the calling procedure's error handler is also active, control passes back through previous calling procedures until an enabled, but inactive, error handler is found.</span></span> <span data-ttu-id="110a6-132">如果不找到任何此类错误处理程序，这个错误是致命它实际发生的时候。</span><span class="sxs-lookup"><span data-stu-id="110a6-132">If no such error handler is found, the error is fatal at the point at which it actually occurred.</span></span>  
  
 <span data-ttu-id="110a6-133">错误处理程序将控制权返回给调用过程时，每次该过程将成为当前过程。</span><span class="sxs-lookup"><span data-stu-id="110a6-133">Each time the error handler passes control back to a calling procedure, that procedure becomes the current procedure.</span></span> <span data-ttu-id="110a6-134">在当前过程中由指定的位置后通过错误处理程序的任何程序中处理错误，继续执行`Resume`语句。</span><span class="sxs-lookup"><span data-stu-id="110a6-134">Once an error is handled by an error handler in any procedure, execution resumes in the current procedure at the point designated by the `Resume` statement.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="110a6-135">错误处理例程不`Sub`过程或`Function`过程。</span><span class="sxs-lookup"><span data-stu-id="110a6-135">An error-handling routine is not a `Sub` procedure or a `Function` procedure.</span></span> <span data-ttu-id="110a6-136">它是一段代码标记的行标签或行号。</span><span class="sxs-lookup"><span data-stu-id="110a6-136">It is a section of code marked by a line label or a line number.</span></span>  
  
## <a name="number-property"></a><span data-ttu-id="110a6-137">Number 属性</span><span class="sxs-lookup"><span data-stu-id="110a6-137">Number Property</span></span>  
 <span data-ttu-id="110a6-138">错误处理例程依赖于中的值`Number`属性`Err`对象以确定错误的原因。</span><span class="sxs-lookup"><span data-stu-id="110a6-138">Error-handling routines rely on the value in the `Number` property of the `Err` object to determine the cause of the error.</span></span> <span data-ttu-id="110a6-139">例程应测试或保存中相关的属性值`Err`对象之前可能出现其他错误或错误调用之前可能会导致的过程。</span><span class="sxs-lookup"><span data-stu-id="110a6-139">The routine should test or save relevant property values in the `Err` object before any other error can occur or before a procedure that might cause an error is called.</span></span> <span data-ttu-id="110a6-140">属性值将在`Err`对象只反映最新的错误。</span><span class="sxs-lookup"><span data-stu-id="110a6-140">The property values in the `Err` object reflect only the most recent error.</span></span> <span data-ttu-id="110a6-141">与关联的错误消息`Err.Number`中包含`Err.Description`。</span><span class="sxs-lookup"><span data-stu-id="110a6-141">The error message associated with `Err.Number` is contained in `Err.Description`.</span></span>  
  
## <a name="throw-statement"></a><span data-ttu-id="110a6-142">Throw 语句</span><span class="sxs-lookup"><span data-stu-id="110a6-142">Throw Statement</span></span>  
 <span data-ttu-id="110a6-143">引发错误`Err.Raise`方法设置`Exception`属性的新创建的实例<xref:System.Exception>类。</span><span class="sxs-lookup"><span data-stu-id="110a6-143">An error that is raised with the `Err.Raise` method sets the `Exception` property to a newly created instance of the <xref:System.Exception> class.</span></span> <span data-ttu-id="110a6-144">为了支持派生的异常类型的异常引发`Throw`语句支持的语言。</span><span class="sxs-lookup"><span data-stu-id="110a6-144">In order to support the raising of exceptions of derived exception types, a `Throw` statement is supported in the language.</span></span> <span data-ttu-id="110a6-145">这将是要引发的异常实例的单个参数。</span><span class="sxs-lookup"><span data-stu-id="110a6-145">This takes a single parameter that is the exception instance to be thrown.</span></span> <span data-ttu-id="110a6-146">下面的示例演示如何与现有异常处理支持使用这些功能：</span><span class="sxs-lookup"><span data-stu-id="110a6-146">The following example shows how these features can be used with the existing exception handling support:</span></span>  
  
 [!code-vb[VbVbalrErrorHandling#17](../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/on-error-statement_1.vb)]  
  
 <span data-ttu-id="110a6-147">请注意，`On Error GoTo`语句捕获所有错误，而不考虑异常类。</span><span class="sxs-lookup"><span data-stu-id="110a6-147">Notice that the `On Error GoTo` statement traps all errors, regardless of the exception class.</span></span>  
  
## <a name="on-error-resume-next"></a><span data-ttu-id="110a6-148">On Error Resume Next</span><span class="sxs-lookup"><span data-stu-id="110a6-148">On Error Resume Next</span></span>  
 <span data-ttu-id="110a6-149">`On Error Resume Next`会导致执行继续紧跟导致运行时错误的语句的语句或使用紧随最新的语句调用外过程包含`On Error Resume Next`语句。</span><span class="sxs-lookup"><span data-stu-id="110a6-149">`On Error Resume Next` causes execution to continue with the statement immediately following the statement that caused the run-time error, or with the statement immediately following the most recent call out of the procedure containing the `On Error Resume Next` statement.</span></span> <span data-ttu-id="110a6-150">此语句允许执行运行时错误时仍继续。</span><span class="sxs-lookup"><span data-stu-id="110a6-150">This statement allows execution to continue despite a run-time error.</span></span> <span data-ttu-id="110a6-151">你可以将会出现错误的错误处理例程，而不是将控制转移到过程内的另一个位置。</span><span class="sxs-lookup"><span data-stu-id="110a6-151">You can place the error-handling routine where the error would occur rather than transferring control to another location within the procedure.</span></span> <span data-ttu-id="110a6-152">`On Error Resume Next`语句变为非活动状态时调用另一个过程，因此应执行`On Error Resume Next`中每个语句调用例程，如果你想内联错误处理中该例程。</span><span class="sxs-lookup"><span data-stu-id="110a6-152">An `On Error Resume Next` statement becomes inactive when another procedure is called, so you should execute an `On Error Resume Next` statement in each called routine if you want inline error handling within that routine.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="110a6-153">`On Error Resume Next`构造可能优于`On Error GoTo`时处理期间对其他对象的访问生成的错误。</span><span class="sxs-lookup"><span data-stu-id="110a6-153">The `On Error Resume Next` construct may be preferable to `On Error GoTo` when handling errors generated during access to other objects.</span></span> <span data-ttu-id="110a6-154">检查`Err`与对象的每个交互清楚地了解对象所访问的代码后。</span><span class="sxs-lookup"><span data-stu-id="110a6-154">Checking `Err` after each interaction with an object removes ambiguity about which object was accessed by the code.</span></span> <span data-ttu-id="110a6-155">你可以将确定哪些对象放置中的错误代码`Err.Number`，以及哪些对象最初生成错误 (中指定的对象`Err.Source`)。</span><span class="sxs-lookup"><span data-stu-id="110a6-155">You can be sure which object placed the error code in `Err.Number`, as well as which object originally generated the error (the object specified in `Err.Source`).</span></span>  
  
## <a name="on-error-goto-0"></a><span data-ttu-id="110a6-156">On Error GoTo 0</span><span class="sxs-lookup"><span data-stu-id="110a6-156">On Error GoTo 0</span></span>  
 <span data-ttu-id="110a6-157">`On Error GoTo 0`禁用当前的过程中的错误处理。</span><span class="sxs-lookup"><span data-stu-id="110a6-157">`On Error GoTo 0` disables error handling in the current procedure.</span></span> <span data-ttu-id="110a6-158">它不会作为错误处理代码中，开始指定 0 行，即使过程包含编号为 0 的行。</span><span class="sxs-lookup"><span data-stu-id="110a6-158">It doesn't specify line 0 as the start of the error-handling code, even if the procedure contains a line numbered 0.</span></span> <span data-ttu-id="110a6-159">而无需`On Error GoTo 0`过程退出时，会自动禁用语句，错误处理程序。</span><span class="sxs-lookup"><span data-stu-id="110a6-159">Without an `On Error GoTo 0` statement, an error handler is automatically disabled when a procedure is exited.</span></span>  
  
## <a name="on-error-goto--1"></a><span data-ttu-id="110a6-160">On Error GoTo-1</span><span class="sxs-lookup"><span data-stu-id="110a6-160">On Error GoTo -1</span></span>  
 <span data-ttu-id="110a6-161">`On Error GoTo -1`禁用当前的过程中的异常。</span><span class="sxs-lookup"><span data-stu-id="110a6-161">`On Error GoTo -1` disables the exception in the current procedure.</span></span> <span data-ttu-id="110a6-162">即使过程包含编号为-1 的行，它不作为错误处理代码中，开始指定行-1。</span><span class="sxs-lookup"><span data-stu-id="110a6-162">It does not specify line -1 as the start of the error-handling code, even if the procedure contains a line numbered -1.</span></span> <span data-ttu-id="110a6-163">而无需`On Error GoTo -1`过程退出时，会自动禁用语句，异常。</span><span class="sxs-lookup"><span data-stu-id="110a6-163">Without an `On Error GoTo -1` statement, an exception is automatically disabled when a procedure is exited.</span></span>  
  
 <span data-ttu-id="110a6-164">若要防止错误处理代码运行时未发生错误，将放置`Exit Sub`， `Exit Function`，或`Exit Property`语句之前的错误处理例程，如以下片段中所示：</span><span class="sxs-lookup"><span data-stu-id="110a6-164">To prevent error-handling code from running when no error has occurred, place an `Exit Sub`, `Exit Function`, or `Exit Property` statement immediately before the error-handling routine, as in the following fragment:</span></span>  
  
 [!code-vb[VbVbalrErrorHandling#18](../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/on-error-statement_2.vb)]  
  
 <span data-ttu-id="110a6-165">在这里，错误处理代码遵循`Exit Sub`语句位于`End Sub`语句以将其与过程流。</span><span class="sxs-lookup"><span data-stu-id="110a6-165">Here, the error-handling code follows the `Exit Sub` statement and precedes the `End Sub` statement to separate it from the procedure flow.</span></span> <span data-ttu-id="110a6-166">可以将错误处理代码放置在过程中的任意位置。</span><span class="sxs-lookup"><span data-stu-id="110a6-166">You can place error-handling code anywhere in a procedure.</span></span>  
  
## <a name="untrapped-errors"></a><span data-ttu-id="110a6-167">无法捕获的错误</span><span class="sxs-lookup"><span data-stu-id="110a6-167">Untrapped Errors</span></span>  
 <span data-ttu-id="110a6-168">当对象的可执行文件以运行时无法捕获的错误，在对象中返回给控制应用程序。</span><span class="sxs-lookup"><span data-stu-id="110a6-168">Untrapped errors in objects are returned to the controlling application when the object is running as an executable file.</span></span> <span data-ttu-id="110a6-169">在开发环境中，无法捕获的错误返回到控制应用程序仅当设置了正确的选项。</span><span class="sxs-lookup"><span data-stu-id="110a6-169">Within the development environment, untrapped errors are returned to the controlling application only if the proper options are set.</span></span> <span data-ttu-id="110a6-170">请参阅有关种选项应为在调试过程中的集、 如何进行设置，和主机是否可以创建类的说明的主机应用程序的文档。</span><span class="sxs-lookup"><span data-stu-id="110a6-170">See your host application's documentation for a description of which options should be set during debugging, how to set them, and whether the host can create classes.</span></span>  
  
 <span data-ttu-id="110a6-171">如果创建了访问其他对象的对象，你应尝试处理它们可能传回任何未处理的错误。</span><span class="sxs-lookup"><span data-stu-id="110a6-171">If you create an object that accesses other objects, you should try to handle any unhandled errors they pass back.</span></span> <span data-ttu-id="110a6-172">如果你不能映射中的错误代码`Err.Number`到其中一个你自己的错误，然后将传递它们重新添加到你的对象的调用方。</span><span class="sxs-lookup"><span data-stu-id="110a6-172">If you cannot, map the error codes in `Err.Number` to one of your own errors and then pass them back to the caller of your object.</span></span> <span data-ttu-id="110a6-173">你应通过添加你的错误代码来指定错误`VbObjectError`常量。</span><span class="sxs-lookup"><span data-stu-id="110a6-173">You should specify your error by adding your error code to the `VbObjectError` constant.</span></span> <span data-ttu-id="110a6-174">例如，如果你的错误代码是 1052年，将其分配，如下所示：</span><span class="sxs-lookup"><span data-stu-id="110a6-174">For example, if your error code is 1052, assign it as follows:</span></span>  
  
 [!code-vb[VbVbalrErrorHandling#19](../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/on-error-statement_3.vb)]  
  
> [!CAUTION]
>  <span data-ttu-id="110a6-175">对 Windows 动态链接库 (Dll) 的调用期间的系统错误不会引发异常和无法困在 Visual Basic 错误捕获。</span><span class="sxs-lookup"><span data-stu-id="110a6-175">System errors during calls to Windows dynamic-link libraries (DLLs) do not raise exceptions and cannot be trapped with Visual Basic error trapping.</span></span> <span data-ttu-id="110a6-176">当调用 DLL 函数，应检查成功或失败 （根据 API 规范），每个返回值和出现故障，请检查此值`Err`对象的`LastDLLError`属性。</span><span class="sxs-lookup"><span data-stu-id="110a6-176">When calling DLL functions, you should check each return value for success or failure (according to the API specifications), and in the event of a failure, check the value in the `Err` object's `LastDLLError` property.</span></span>  
  
## <a name="example"></a><span data-ttu-id="110a6-177">示例</span><span class="sxs-lookup"><span data-stu-id="110a6-177">Example</span></span>  
 <span data-ttu-id="110a6-178">此示例首先使用`On Error GoTo`语句指定的过程中的错误处理例程的位置。</span><span class="sxs-lookup"><span data-stu-id="110a6-178">This example first uses the `On Error GoTo` statement to specify the location of an error-handling routine within a procedure.</span></span> <span data-ttu-id="110a6-179">在示例中，尝试除以零会生成错误编号为 6。</span><span class="sxs-lookup"><span data-stu-id="110a6-179">In the example, an attempt to divide by zero generates error number 6.</span></span> <span data-ttu-id="110a6-180">错误处理中的错误处理例程，并且控件然后返回到导致错误的语句。</span><span class="sxs-lookup"><span data-stu-id="110a6-180">The error is handled in the error-handling routine, and control is then returned to the statement that caused the error.</span></span> <span data-ttu-id="110a6-181">`On Error GoTo 0`语句关闭错误捕获。</span><span class="sxs-lookup"><span data-stu-id="110a6-181">The `On Error GoTo 0` statement turns off error trapping.</span></span> <span data-ttu-id="110a6-182">则`On Error Resume Next`语句用于推迟错误捕获，以便可以为某些已知所生成错误的下一个语句的上下文。</span><span class="sxs-lookup"><span data-stu-id="110a6-182">Then the `On Error Resume Next` statement is used to defer error trapping so that the context for the error generated by the next statement can be known for certain.</span></span> <span data-ttu-id="110a6-183">请注意，`Err.Clear`用于清除`Err`处理该错误后的对象的属性。</span><span class="sxs-lookup"><span data-stu-id="110a6-183">Note that `Err.Clear` is used to clear the `Err` object's properties after the error is handled.</span></span>  
  
 [!code-vb[VbVbalrErrorHandling#20](../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/on-error-statement_4.vb)]  
  
## <a name="requirements"></a><span data-ttu-id="110a6-184">惠?</span><span class="sxs-lookup"><span data-stu-id="110a6-184">Requirements</span></span>  
 <span data-ttu-id="110a6-185">**Namespace:** [Microsoft.VisualBasic](../../../visual-basic/language-reference/runtime-library-members.md)</span><span class="sxs-lookup"><span data-stu-id="110a6-185">**Namespace:** [Microsoft.VisualBasic](../../../visual-basic/language-reference/runtime-library-members.md)</span></span>  
  
 <span data-ttu-id="110a6-186">**程序集：** Visual Basic 运行库 （在 Microsoft.VisualBasic.dll 中)</span><span class="sxs-lookup"><span data-stu-id="110a6-186">**Assembly:** Visual Basic Runtime Library (in Microsoft.VisualBasic.dll)</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="110a6-187">请参阅</span><span class="sxs-lookup"><span data-stu-id="110a6-187">See Also</span></span>  
 <xref:Microsoft.VisualBasic.Information.Err%2A>  
 <xref:Microsoft.VisualBasic.ErrObject.Number%2A>  
 <xref:Microsoft.VisualBasic.ErrObject.Description%2A>  
 <xref:Microsoft.VisualBasic.ErrObject.LastDllError%2A>  
 [<span data-ttu-id="110a6-188">End 语句</span><span class="sxs-lookup"><span data-stu-id="110a6-188">End Statement</span></span>](../../../visual-basic/language-reference/statements/end-statement.md)  
 [<span data-ttu-id="110a6-189">Exit 语句</span><span class="sxs-lookup"><span data-stu-id="110a6-189">Exit Statement</span></span>](../../../visual-basic/language-reference/statements/exit-statement.md)  
 [<span data-ttu-id="110a6-190">Resume 语句</span><span class="sxs-lookup"><span data-stu-id="110a6-190">Resume Statement</span></span>](../../../visual-basic/language-reference/statements/resume-statement.md)  
 [<span data-ttu-id="110a6-191">错误消息</span><span class="sxs-lookup"><span data-stu-id="110a6-191">Error Messages</span></span>](../../../visual-basic/language-reference/error-messages/index.md)  
 [<span data-ttu-id="110a6-192">Try...Catch...Finally 语句</span><span class="sxs-lookup"><span data-stu-id="110a6-192">Try...Catch...Finally Statement</span></span>](../../../visual-basic/language-reference/statements/try-catch-finally-statement.md)
