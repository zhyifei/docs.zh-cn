---
title: On Error 语句 (Visual Basic)
ms.date: 07/20/2015
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
ms.openlocfilehash: 16a2ee7f16df92db8deb44ff979ec077eefc20aa
ms.sourcegitcommit: 40364ded04fa6cdcb2b6beca7f68412e2e12f633
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/28/2019
ms.locfileid: "56976481"
---
# <a name="on-error-statement-visual-basic"></a><span data-ttu-id="d61dd-102">On Error 语句 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="d61dd-102">On Error Statement (Visual Basic)</span></span>
<span data-ttu-id="d61dd-103">启用错误处理例程，并指定该例程在过程; 中的位置此外可以用于禁用错误处理例程。</span><span class="sxs-lookup"><span data-stu-id="d61dd-103">Enables an error-handling routine and specifies the location of the routine within a procedure; can also be used to disable an error-handling routine.</span></span>  
  
 <span data-ttu-id="d61dd-104">如果错误处理，不会发生任何运行时错误是致命： 显示一条错误消息，并且停止执行。</span><span class="sxs-lookup"><span data-stu-id="d61dd-104">Without error handling, any run-time error that occurs is fatal: an error message is displayed, and execution stops.</span></span>  
  
 <span data-ttu-id="d61dd-105">只要有可能，我们建议您同时使用结构化的异常处理在代码中，而不使用非结构化的异常处理和`On Error`语句。</span><span class="sxs-lookup"><span data-stu-id="d61dd-105">Whenever possible, we suggest you use structured exception handling in your code, rather than using unstructured exception handling and the `On Error` statement.</span></span> <span data-ttu-id="d61dd-106">有关详细信息，请参阅 [Try...Catch...Finally 语句](../../../visual-basic/language-reference/statements/try-catch-finally-statement.md)。</span><span class="sxs-lookup"><span data-stu-id="d61dd-106">For more information, see [Try...Catch...Finally Statement](../../../visual-basic/language-reference/statements/try-catch-finally-statement.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="d61dd-107">`Error`关键字还用于[Error 语句](../../../visual-basic/language-reference/statements/error-statement.md)，这为了向后兼容受支持。</span><span class="sxs-lookup"><span data-stu-id="d61dd-107">The `Error` keyword is also used in the [Error Statement](../../../visual-basic/language-reference/statements/error-statement.md), which is supported for backward compatibility.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d61dd-108">语法</span><span class="sxs-lookup"><span data-stu-id="d61dd-108">Syntax</span></span>  
  
```  
On Error { GoTo [ line | 0 | -1 ] | Resume Next }  
```  
  
## <a name="parts"></a><span data-ttu-id="d61dd-109">部件</span><span class="sxs-lookup"><span data-stu-id="d61dd-109">Parts</span></span>  
  
|<span data-ttu-id="d61dd-110">术语</span><span class="sxs-lookup"><span data-stu-id="d61dd-110">Term</span></span>|<span data-ttu-id="d61dd-111">定义</span><span class="sxs-lookup"><span data-stu-id="d61dd-111">Definition</span></span>|  
|---|---|  
|<span data-ttu-id="d61dd-112">`GoTo` `line`</span><span class="sxs-lookup"><span data-stu-id="d61dd-112">`GoTo` `line`</span></span>|<span data-ttu-id="d61dd-113">启用指定在所需的行开始的错误处理例程`line`参数。</span><span class="sxs-lookup"><span data-stu-id="d61dd-113">Enables the error-handling routine that starts at the line specified in the required `line` argument.</span></span> <span data-ttu-id="d61dd-114">`line`参数是任意行标签或行号。</span><span class="sxs-lookup"><span data-stu-id="d61dd-114">The `line` argument is any line label or line number.</span></span> <span data-ttu-id="d61dd-115">如果出现运行时错误，则控制分支到指定的行，使错误处理程序处于活动状态。</span><span class="sxs-lookup"><span data-stu-id="d61dd-115">If a run-time error occurs, control branches to the specified line, making the error handler active.</span></span> <span data-ttu-id="d61dd-116">指定的行必须采用与相同的步骤`On Error`语句或编译时错误会发生。</span><span class="sxs-lookup"><span data-stu-id="d61dd-116">The specified line must be in the same procedure as the `On Error` statement, or a compile-time error will occur.</span></span>|  
|<span data-ttu-id="d61dd-117">`GoTo` 0</span><span class="sxs-lookup"><span data-stu-id="d61dd-117">`GoTo` 0</span></span>|<span data-ttu-id="d61dd-118">禁用当前过程中启用的错误处理和重置为`Nothing`。</span><span class="sxs-lookup"><span data-stu-id="d61dd-118">Disables enabled error handler in the current procedure and resets it to `Nothing`.</span></span>|  
|<span data-ttu-id="d61dd-119">`GoTo` -1</span><span class="sxs-lookup"><span data-stu-id="d61dd-119">`GoTo` -1</span></span>|<span data-ttu-id="d61dd-120">禁用当前过程中已启用的异常和重置为`Nothing`。</span><span class="sxs-lookup"><span data-stu-id="d61dd-120">Disables enabled exception in the current procedure and resets it to `Nothing`.</span></span>|  
|`Resume Next`|<span data-ttu-id="d61dd-121">指定语句出现运行时错误时，控件跳转到紧跟其中发生错误，并从该点继续执行该语句的语句。</span><span class="sxs-lookup"><span data-stu-id="d61dd-121">Specifies that when a run-time error occurs, control goes to the statement immediately following the statement where the error occurred, and execution continues from that point.</span></span> <span data-ttu-id="d61dd-122">使用此窗体而非`On Error GoTo`访问对象时。</span><span class="sxs-lookup"><span data-stu-id="d61dd-122">Use this form rather than `On Error GoTo` when accessing objects.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="d61dd-123">备注</span><span class="sxs-lookup"><span data-stu-id="d61dd-123">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="d61dd-124">我们建议使用只要有可能，在代码中的结构化的异常处理，而不是使用非结构化的异常处理和`On Error`语句。</span><span class="sxs-lookup"><span data-stu-id="d61dd-124">We recommend that you use structured exception handling in your code whenever possible, rather than using unstructured exception handling and the `On Error` statement.</span></span> <span data-ttu-id="d61dd-125">有关详细信息，请参阅 [Try...Catch...Finally 语句](../../../visual-basic/language-reference/statements/try-catch-finally-statement.md)。</span><span class="sxs-lookup"><span data-stu-id="d61dd-125">For more information, see [Try...Catch...Finally Statement](../../../visual-basic/language-reference/statements/try-catch-finally-statement.md).</span></span>  
  
 <span data-ttu-id="d61dd-126">"已启用"的错误处理程序是指已开启，`On Error`语句。</span><span class="sxs-lookup"><span data-stu-id="d61dd-126">An "enabled" error handler is one that is turned on by an `On Error` statement.</span></span> <span data-ttu-id="d61dd-127">"活动"的错误处理程序是一个已启用的处理程序的过程中处理错误。</span><span class="sxs-lookup"><span data-stu-id="d61dd-127">An "active" error handler is an enabled handler that is in the process of handling an error.</span></span>  
  
 <span data-ttu-id="d61dd-128">错误处理程序处于活动状态时如果发生错误 (错误的匹配项之间和一个`Resume`， `Exit Sub`， `Exit Function`，或`Exit Property`语句)，当前过程的错误处理程序无法处理该错误。</span><span class="sxs-lookup"><span data-stu-id="d61dd-128">If an error occurs while an error handler is active (between the occurrence of the error and a `Resume`, `Exit Sub`, `Exit Function`, or `Exit Property` statement), the current procedure's error handler cannot handle the error.</span></span> <span data-ttu-id="d61dd-129">控制权返回给调用的过程。</span><span class="sxs-lookup"><span data-stu-id="d61dd-129">Control returns to the calling procedure.</span></span>  
  
 <span data-ttu-id="d61dd-130">如果调用过程具有一个已启用的错误处理程序，它被激活以处理错误。</span><span class="sxs-lookup"><span data-stu-id="d61dd-130">If the calling procedure has an enabled error handler, it is activated to handle the error.</span></span> <span data-ttu-id="d61dd-131">如果调用过程的错误处理程序还处于活动状态，控制将传递回通过前一个调用过程中，直到找到已启用，但非活动状态，错误处理程序。</span><span class="sxs-lookup"><span data-stu-id="d61dd-131">If the calling procedure's error handler is also active, control passes back through previous calling procedures until an enabled, but inactive, error handler is found.</span></span> <span data-ttu-id="d61dd-132">如果不找到任何此类错误处理程序，则这个错误是致命它实际发生的时候。</span><span class="sxs-lookup"><span data-stu-id="d61dd-132">If no such error handler is found, the error is fatal at the point at which it actually occurred.</span></span>  
  
 <span data-ttu-id="d61dd-133">错误处理程序将控制传递回调用过程时，每次该过程将成为当前的过程。</span><span class="sxs-lookup"><span data-stu-id="d61dd-133">Each time the error handler passes control back to a calling procedure, that procedure becomes the current procedure.</span></span> <span data-ttu-id="d61dd-134">一旦通过任何过程中的错误处理程序处理错误，则执行将在由指定的位置的当前过程`Resume`语句。</span><span class="sxs-lookup"><span data-stu-id="d61dd-134">Once an error is handled by an error handler in any procedure, execution resumes in the current procedure at the point designated by the `Resume` statement.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="d61dd-135">不是错误处理例程`Sub`过程或`Function`过程。</span><span class="sxs-lookup"><span data-stu-id="d61dd-135">An error-handling routine is not a `Sub` procedure or a `Function` procedure.</span></span> <span data-ttu-id="d61dd-136">它是一段代码标记行标签或行号。</span><span class="sxs-lookup"><span data-stu-id="d61dd-136">It is a section of code marked by a line label or a line number.</span></span>  
  
## <a name="number-property"></a><span data-ttu-id="d61dd-137">Number 属性</span><span class="sxs-lookup"><span data-stu-id="d61dd-137">Number Property</span></span>  
 <span data-ttu-id="d61dd-138">错误处理例程依赖于中的值`Number`属性的`Err`对象，以确定错误的原因。</span><span class="sxs-lookup"><span data-stu-id="d61dd-138">Error-handling routines rely on the value in the `Number` property of the `Err` object to determine the cause of the error.</span></span> <span data-ttu-id="d61dd-139">例程应测试或保存相关的属性值中`Err`对象之前可能出现其他错误或错误调用之前可能会导致的过程。</span><span class="sxs-lookup"><span data-stu-id="d61dd-139">The routine should test or save relevant property values in the `Err` object before any other error can occur or before a procedure that might cause an error is called.</span></span> <span data-ttu-id="d61dd-140">中的属性值`Err`对象只反映最新的错误。</span><span class="sxs-lookup"><span data-stu-id="d61dd-140">The property values in the `Err` object reflect only the most recent error.</span></span> <span data-ttu-id="d61dd-141">与相关联的错误消息`Err.Number`中包含`Err.Description`。</span><span class="sxs-lookup"><span data-stu-id="d61dd-141">The error message associated with `Err.Number` is contained in `Err.Description`.</span></span>  
  
## <a name="throw-statement"></a><span data-ttu-id="d61dd-142">Throw 语句</span><span class="sxs-lookup"><span data-stu-id="d61dd-142">Throw Statement</span></span>  
 <span data-ttu-id="d61dd-143">与引发的错误`Err.Raise`方法设置`Exception`属性设置为新创建的实例<xref:System.Exception>类。</span><span class="sxs-lookup"><span data-stu-id="d61dd-143">An error that is raised with the `Err.Raise` method sets the `Exception` property to a newly created instance of the <xref:System.Exception> class.</span></span> <span data-ttu-id="d61dd-144">为了支持派生的异常类型的异常引发`Throw`语句支持的语言。</span><span class="sxs-lookup"><span data-stu-id="d61dd-144">In order to support the raising of exceptions of derived exception types, a `Throw` statement is supported in the language.</span></span> <span data-ttu-id="d61dd-145">这将是要引发的异常实例的单个参数。</span><span class="sxs-lookup"><span data-stu-id="d61dd-145">This takes a single parameter that is the exception instance to be thrown.</span></span> <span data-ttu-id="d61dd-146">下面的示例演示如何使用现有的异常处理支持使用这些功能：</span><span class="sxs-lookup"><span data-stu-id="d61dd-146">The following example shows how these features can be used with the existing exception handling support:</span></span>  
  
 [!code-vb[VbVbalrErrorHandling#17](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrErrorHandling/VB/Class1.vb#17)]  
  
 <span data-ttu-id="d61dd-147">请注意，`On Error GoTo`语句捕获所有错误，而不考虑异常类。</span><span class="sxs-lookup"><span data-stu-id="d61dd-147">Notice that the `On Error GoTo` statement traps all errors, regardless of the exception class.</span></span>  
  
## <a name="on-error-resume-next"></a><span data-ttu-id="d61dd-148">On Error Resume Next</span><span class="sxs-lookup"><span data-stu-id="d61dd-148">On Error Resume Next</span></span>  
 <span data-ttu-id="d61dd-149">`On Error Resume Next` 会导致执行继续后立即导致运行时错误，该语句的语句或使用紧跟最新的语句调用带过程包含`On Error Resume Next`语句。</span><span class="sxs-lookup"><span data-stu-id="d61dd-149">`On Error Resume Next` causes execution to continue with the statement immediately following the statement that caused the run-time error, or with the statement immediately following the most recent call out of the procedure containing the `On Error Resume Next` statement.</span></span> <span data-ttu-id="d61dd-150">此语句允许执行继续运行时错误。</span><span class="sxs-lookup"><span data-stu-id="d61dd-150">This statement allows execution to continue despite a run-time error.</span></span> <span data-ttu-id="d61dd-151">您可以将会出现错误的错误处理例程，而不是将控制转移到过程内的另一个位置。</span><span class="sxs-lookup"><span data-stu-id="d61dd-151">You can place the error-handling routine where the error would occur rather than transferring control to another location within the procedure.</span></span> <span data-ttu-id="d61dd-152">`On Error Resume Next`语句变为非活动状态时调用另一个过程，因此应执行`On Error Resume Next`中每个语句调用例程，如果你想在该例程处理内联错误。</span><span class="sxs-lookup"><span data-stu-id="d61dd-152">An `On Error Resume Next` statement becomes inactive when another procedure is called, so you should execute an `On Error Resume Next` statement in each called routine if you want inline error handling within that routine.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="d61dd-153">`On Error Resume Next`构造可能优于`On Error GoTo`处理期间对其他对象的访问生成的错误时。</span><span class="sxs-lookup"><span data-stu-id="d61dd-153">The `On Error Resume Next` construct may be preferable to `On Error GoTo` when handling errors generated during access to other objects.</span></span> <span data-ttu-id="d61dd-154">检查`Err`与对象的每个交互清楚地了解对象所访问的代码之后。</span><span class="sxs-lookup"><span data-stu-id="d61dd-154">Checking `Err` after each interaction with an object removes ambiguity about which object was accessed by the code.</span></span> <span data-ttu-id="d61dd-155">可以确定哪个对象放置中的错误代码`Err.Number`，以及哪个对象最初生成错误 (中指定的对象`Err.Source`)。</span><span class="sxs-lookup"><span data-stu-id="d61dd-155">You can be sure which object placed the error code in `Err.Number`, as well as which object originally generated the error (the object specified in `Err.Source`).</span></span>  
  
## <a name="on-error-goto-0"></a><span data-ttu-id="d61dd-156">Error GoTo 0 上</span><span class="sxs-lookup"><span data-stu-id="d61dd-156">On Error GoTo 0</span></span>  
 <span data-ttu-id="d61dd-157">`On Error GoTo 0` 禁用当前过程中的错误处理。</span><span class="sxs-lookup"><span data-stu-id="d61dd-157">`On Error GoTo 0` disables error handling in the current procedure.</span></span> <span data-ttu-id="d61dd-158">它不会作为错误处理代码的开头指定 0 行，即使过程包含编号为 0 的行。</span><span class="sxs-lookup"><span data-stu-id="d61dd-158">It doesn't specify line 0 as the start of the error-handling code, even if the procedure contains a line numbered 0.</span></span> <span data-ttu-id="d61dd-159">无需`On Error GoTo 0`退出一个过程时，会自动禁用语句中，错误处理程序。</span><span class="sxs-lookup"><span data-stu-id="d61dd-159">Without an `On Error GoTo 0` statement, an error handler is automatically disabled when a procedure is exited.</span></span>  
  
## <a name="on-error-goto--1"></a><span data-ttu-id="d61dd-160">在错误 GoTo-1</span><span class="sxs-lookup"><span data-stu-id="d61dd-160">On Error GoTo -1</span></span>  
 <span data-ttu-id="d61dd-161">`On Error GoTo -1` 禁用当前过程中的异常。</span><span class="sxs-lookup"><span data-stu-id="d61dd-161">`On Error GoTo -1` disables the exception in the current procedure.</span></span> <span data-ttu-id="d61dd-162">它不指定行-1 作为开头的错误处理代码，即使过程包含的行号为-1。</span><span class="sxs-lookup"><span data-stu-id="d61dd-162">It does not specify line -1 as the start of the error-handling code, even if the procedure contains a line numbered -1.</span></span> <span data-ttu-id="d61dd-163">无需`On Error GoTo -1`退出一个过程时，会自动禁用语句中，异常。</span><span class="sxs-lookup"><span data-stu-id="d61dd-163">Without an `On Error GoTo -1` statement, an exception is automatically disabled when a procedure is exited.</span></span>  
  
 <span data-ttu-id="d61dd-164">若要阻止运行时未发生错误的错误处理代码，请将置于`Exit Sub`， `Exit Function`，或`Exit Property`语句之前的错误处理例程，如以下片段中所示：</span><span class="sxs-lookup"><span data-stu-id="d61dd-164">To prevent error-handling code from running when no error has occurred, place an `Exit Sub`, `Exit Function`, or `Exit Property` statement immediately before the error-handling routine, as in the following fragment:</span></span>  
  
 [!code-vb[VbVbalrErrorHandling#18](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrErrorHandling/VB/Class1.vb#18)]  
  
 <span data-ttu-id="d61dd-165">在这里，错误处理代码如下所示`Exit Sub`语句位于`End Sub`语句以将其与过程流。</span><span class="sxs-lookup"><span data-stu-id="d61dd-165">Here, the error-handling code follows the `Exit Sub` statement and precedes the `End Sub` statement to separate it from the procedure flow.</span></span> <span data-ttu-id="d61dd-166">可以将错误处理代码放在过程中的任意位置。</span><span class="sxs-lookup"><span data-stu-id="d61dd-166">You can place error-handling code anywhere in a procedure.</span></span>  
  
## <a name="untrapped-errors"></a><span data-ttu-id="d61dd-167">无法捕获的错误</span><span class="sxs-lookup"><span data-stu-id="d61dd-167">Untrapped Errors</span></span>  
 <span data-ttu-id="d61dd-168">无法捕获的对象中的错误返回到控制应用程序作为可执行文件运行时对象。</span><span class="sxs-lookup"><span data-stu-id="d61dd-168">Untrapped errors in objects are returned to the controlling application when the object is running as an executable file.</span></span> <span data-ttu-id="d61dd-169">在开发环境中，无法捕获的错误返回到控制应用程序仅当设置了适当的选项。</span><span class="sxs-lookup"><span data-stu-id="d61dd-169">Within the development environment, untrapped errors are returned to the controlling application only if the proper options are set.</span></span> <span data-ttu-id="d61dd-170">请参阅的说明这些选项应该设置在调试过程中的、 如何进行设置，以及主机是否可以创建类的主机应用程序的文档。</span><span class="sxs-lookup"><span data-stu-id="d61dd-170">See your host application's documentation for a description of which options should be set during debugging, how to set them, and whether the host can create classes.</span></span>  
  
 <span data-ttu-id="d61dd-171">如果创建了访问其他对象的对象，应尝试处理它们可能传回任何未处理的错误。</span><span class="sxs-lookup"><span data-stu-id="d61dd-171">If you create an object that accesses other objects, you should try to handle any unhandled errors they pass back.</span></span> <span data-ttu-id="d61dd-172">如果您不能映射中的错误代码`Err.Number`到某个你自己的错误，然后传递它们重新添加到您的对象的调用方。</span><span class="sxs-lookup"><span data-stu-id="d61dd-172">If you cannot, map the error codes in `Err.Number` to one of your own errors and then pass them back to the caller of your object.</span></span> <span data-ttu-id="d61dd-173">应通过添加到您的错误代码来指定错误`VbObjectError`常量。</span><span class="sxs-lookup"><span data-stu-id="d61dd-173">You should specify your error by adding your error code to the `VbObjectError` constant.</span></span> <span data-ttu-id="d61dd-174">例如，如果您的错误代码为 1052年，将其分配，如下所示：</span><span class="sxs-lookup"><span data-stu-id="d61dd-174">For example, if your error code is 1052, assign it as follows:</span></span>  
  
 [!code-vb[VbVbalrErrorHandling#19](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrErrorHandling/VB/Class1.vb#19)]  
  
> [!CAUTION]
>  <span data-ttu-id="d61dd-175">系统对 Windows 动态链接库 (Dll) 的调用过程中出现错误不会引发异常并不能与 Visual Basic 错误捕获捕获。</span><span class="sxs-lookup"><span data-stu-id="d61dd-175">System errors during calls to Windows dynamic-link libraries (DLLs) do not raise exceptions and cannot be trapped with Visual Basic error trapping.</span></span> <span data-ttu-id="d61dd-176">当调用 DLL 函数，应检查成功或失败 （根据 API 规范），每个返回值和出现故障时，检查值`Err`对象的`LastDLLError`属性。</span><span class="sxs-lookup"><span data-stu-id="d61dd-176">When calling DLL functions, you should check each return value for success or failure (according to the API specifications), and in the event of a failure, check the value in the `Err` object's `LastDLLError` property.</span></span>  
  
## <a name="example"></a><span data-ttu-id="d61dd-177">示例</span><span class="sxs-lookup"><span data-stu-id="d61dd-177">Example</span></span>  
 <span data-ttu-id="d61dd-178">此示例首先使用`On Error GoTo`语句指定的位置的过程中的错误处理例程。</span><span class="sxs-lookup"><span data-stu-id="d61dd-178">This example first uses the `On Error GoTo` statement to specify the location of an error-handling routine within a procedure.</span></span> <span data-ttu-id="d61dd-179">在示例中，尝试除以零将产生错误编号为 6。</span><span class="sxs-lookup"><span data-stu-id="d61dd-179">In the example, an attempt to divide by zero generates error number 6.</span></span> <span data-ttu-id="d61dd-180">在错误处理例程中，处理该错误，然后将控件返回到导致该错误的语句。</span><span class="sxs-lookup"><span data-stu-id="d61dd-180">The error is handled in the error-handling routine, and control is then returned to the statement that caused the error.</span></span> <span data-ttu-id="d61dd-181">`On Error GoTo 0`语句关闭错误捕获。</span><span class="sxs-lookup"><span data-stu-id="d61dd-181">The `On Error GoTo 0` statement turns off error trapping.</span></span> <span data-ttu-id="d61dd-182">然后`On Error Resume Next`语句用于延迟错误捕获，以确保可以为某些已知的下一个语句所生成错误的上下文。</span><span class="sxs-lookup"><span data-stu-id="d61dd-182">Then the `On Error Resume Next` statement is used to defer error trapping so that the context for the error generated by the next statement can be known for certain.</span></span> <span data-ttu-id="d61dd-183">请注意，`Err.Clear`用于清除`Err`之后处理该错误的对象的属性。</span><span class="sxs-lookup"><span data-stu-id="d61dd-183">Note that `Err.Clear` is used to clear the `Err` object's properties after the error is handled.</span></span>  
  
 [!code-vb[VbVbalrErrorHandling#20](../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/on-error-statement_4.vb)]  
  
## <a name="requirements"></a><span data-ttu-id="d61dd-184">要求</span><span class="sxs-lookup"><span data-stu-id="d61dd-184">Requirements</span></span>  
 <span data-ttu-id="d61dd-185">**命名空间：**[Microsoft.VisualBasic](../../../visual-basic/language-reference/runtime-library-members.md)</span><span class="sxs-lookup"><span data-stu-id="d61dd-185">**Namespace:** [Microsoft.VisualBasic](../../../visual-basic/language-reference/runtime-library-members.md)</span></span>  
  
 <span data-ttu-id="d61dd-186">**程序集：** Visual Basic 运行库（在 Microsoft.VisualBasic.dll 中）</span><span class="sxs-lookup"><span data-stu-id="d61dd-186">**Assembly:** Visual Basic Runtime Library (in Microsoft.VisualBasic.dll)</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d61dd-187">请参阅</span><span class="sxs-lookup"><span data-stu-id="d61dd-187">See also</span></span>
- <xref:Microsoft.VisualBasic.Information.Err%2A>
- <xref:Microsoft.VisualBasic.ErrObject.Number%2A>
- <xref:Microsoft.VisualBasic.ErrObject.Description%2A>
- <xref:Microsoft.VisualBasic.ErrObject.LastDllError%2A>
- [<span data-ttu-id="d61dd-188">End 语句</span><span class="sxs-lookup"><span data-stu-id="d61dd-188">End Statement</span></span>](../../../visual-basic/language-reference/statements/end-statement.md)
- [<span data-ttu-id="d61dd-189">Exit 语句</span><span class="sxs-lookup"><span data-stu-id="d61dd-189">Exit Statement</span></span>](../../../visual-basic/language-reference/statements/exit-statement.md)
- [<span data-ttu-id="d61dd-190">Resume 语句</span><span class="sxs-lookup"><span data-stu-id="d61dd-190">Resume Statement</span></span>](../../../visual-basic/language-reference/statements/resume-statement.md)
- [<span data-ttu-id="d61dd-191">错误消息</span><span class="sxs-lookup"><span data-stu-id="d61dd-191">Error Messages</span></span>](../../../visual-basic/language-reference/error-messages/index.md)
- [<span data-ttu-id="d61dd-192">Try...Catch...Finally 语句</span><span class="sxs-lookup"><span data-stu-id="d61dd-192">Try...Catch...Finally Statement</span></span>](../../../visual-basic/language-reference/statements/try-catch-finally-statement.md)
