---
title: Exit 语句 (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.Exit
helpviewer_keywords:
- execution [Visual Basic], ending
- files [Visual Basic], closing
- programs [Visual Basic], quitting
- code, exiting
- Exit statement [Visual Basic]
- program termination
- execution [Visual Basic], stopping
ms.assetid: 760bfb32-5c3f-4bdb-a432-9a6001c92db7
ms.openlocfilehash: 1f386694bd7425ee530b9305ab684b730f9b73c8
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/02/2019
ms.locfileid: "58832627"
---
# <a name="exit-statement-visual-basic"></a><span data-ttu-id="5a44c-102">Exit 语句 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="5a44c-102">Exit Statement (Visual Basic)</span></span>
<span data-ttu-id="5a44c-103">退出过程或块，并立即将控制转移到的过程调用或块定义后面的语句。</span><span class="sxs-lookup"><span data-stu-id="5a44c-103">Exits a procedure or block and transfers control immediately to the statement following the procedure call or the block definition.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5a44c-104">语法</span><span class="sxs-lookup"><span data-stu-id="5a44c-104">Syntax</span></span>  
  
```  
Exit { Do | For | Function | Property | Select | Sub | Try | While }  
```  
  
## <a name="statements"></a><span data-ttu-id="5a44c-105">语句</span><span class="sxs-lookup"><span data-stu-id="5a44c-105">Statements</span></span>  
 `Exit Do`  
 <span data-ttu-id="5a44c-106">立即退出`Do`循环中将显示。</span><span class="sxs-lookup"><span data-stu-id="5a44c-106">Immediately exits the `Do` loop in which it appears.</span></span> <span data-ttu-id="5a44c-107">继续后面的语句执行`Loop`语句。</span><span class="sxs-lookup"><span data-stu-id="5a44c-107">Execution continues with the statement following the `Loop` statement.</span></span> <span data-ttu-id="5a44c-108">`Exit Do` 可仅在`Do`循环。</span><span class="sxs-lookup"><span data-stu-id="5a44c-108">`Exit Do` can be used only inside a `Do` loop.</span></span> <span data-ttu-id="5a44c-109">当使用内嵌套`Do`循环，`Exit Do`退出最里面的循环，并将控制转移到下一个较高级别的嵌套。</span><span class="sxs-lookup"><span data-stu-id="5a44c-109">When used within nested `Do` loops, `Exit Do` exits the innermost loop and transfers control to the next higher level of nesting.</span></span>  
  
 `Exit For`  
 <span data-ttu-id="5a44c-110">立即退出`For`循环中将显示。</span><span class="sxs-lookup"><span data-stu-id="5a44c-110">Immediately exits the `For` loop in which it appears.</span></span> <span data-ttu-id="5a44c-111">继续后面的语句执行`Next`语句。</span><span class="sxs-lookup"><span data-stu-id="5a44c-111">Execution continues with the statement following the `Next` statement.</span></span> <span data-ttu-id="5a44c-112">`Exit For` 可仅在`For`...`Next`或`For Each`...`Next`循环。</span><span class="sxs-lookup"><span data-stu-id="5a44c-112">`Exit For` can be used only inside a `For`...`Next` or `For Each`...`Next` loop.</span></span> <span data-ttu-id="5a44c-113">当使用内嵌套`For`循环，`Exit For`退出最里面的循环，并将控制转移到下一个较高级别的嵌套。</span><span class="sxs-lookup"><span data-stu-id="5a44c-113">When used within nested `For` loops, `Exit For` exits the innermost loop and transfers control to the next higher level of nesting.</span></span>  
  
 `Exit Function`  
 <span data-ttu-id="5a44c-114">立即退出`Function`它所在的过程。</span><span class="sxs-lookup"><span data-stu-id="5a44c-114">Immediately exits the `Function` procedure in which it appears.</span></span> <span data-ttu-id="5a44c-115">继续后面的语句调用的语句的执行`Function`过程。</span><span class="sxs-lookup"><span data-stu-id="5a44c-115">Execution continues with the statement following the statement that called the `Function` procedure.</span></span> <span data-ttu-id="5a44c-116">`Exit Function` 可仅在`Function`过程。</span><span class="sxs-lookup"><span data-stu-id="5a44c-116">`Exit Function` can be used only inside a `Function` procedure.</span></span>  
  
 <span data-ttu-id="5a44c-117">若要指定返回值，可以将值分配给前一行的函数名称`Exit Function`语句。</span><span class="sxs-lookup"><span data-stu-id="5a44c-117">To specify a return value, you can assign the value to the function name on a line before the `Exit Function` statement.</span></span> <span data-ttu-id="5a44c-118">若要将返回值和退出在一个语句中的函数，则可以使用[Return 语句](../../../visual-basic/language-reference/statements/return-statement.md)。</span><span class="sxs-lookup"><span data-stu-id="5a44c-118">To assign the return value and exit the function in one statement, you can instead use the [Return Statement](../../../visual-basic/language-reference/statements/return-statement.md).</span></span>  
  
 `Exit Property`  
 <span data-ttu-id="5a44c-119">立即退出`Property`它所在的过程。</span><span class="sxs-lookup"><span data-stu-id="5a44c-119">Immediately exits the `Property` procedure in which it appears.</span></span> <span data-ttu-id="5a44c-120">继续执行调用语句`Property`过程，也就是说，与请求或设置该属性的值的语句。</span><span class="sxs-lookup"><span data-stu-id="5a44c-120">Execution continues with the statement that called the `Property` procedure, that is, with the statement requesting or setting the property's value.</span></span> <span data-ttu-id="5a44c-121">`Exit Property` 可仅在属性的`Get`或`Set`过程。</span><span class="sxs-lookup"><span data-stu-id="5a44c-121">`Exit Property` can be used only inside a property's `Get` or `Set` procedure.</span></span>  
  
 <span data-ttu-id="5a44c-122">若要指定在返回值`Get`过程中，可以将值分配给前一行的函数名称`Exit Property`语句。</span><span class="sxs-lookup"><span data-stu-id="5a44c-122">To specify a return value in a `Get` procedure, you can assign the value to the function name on a line before the `Exit Property` statement.</span></span> <span data-ttu-id="5a44c-123">若要将分配的返回值和出口`Get`在一个语句中的过程，则可以使用`Return`语句。</span><span class="sxs-lookup"><span data-stu-id="5a44c-123">To assign the return value and exit the `Get` procedure in one statement, you can instead use the `Return` statement.</span></span>  
  
 <span data-ttu-id="5a44c-124">在中`Set`过程中，`Exit Property`语句等效于`Return`语句。</span><span class="sxs-lookup"><span data-stu-id="5a44c-124">In a `Set` procedure, the `Exit Property` statement is equivalent to the `Return` statement.</span></span>  
  
 `Exit Select`  
 <span data-ttu-id="5a44c-125">立即退出`Select Case`阻止所在。</span><span class="sxs-lookup"><span data-stu-id="5a44c-125">Immediately exits the `Select Case` block in which it appears.</span></span> <span data-ttu-id="5a44c-126">继续后面的语句执行`End Select`语句。</span><span class="sxs-lookup"><span data-stu-id="5a44c-126">Execution continues with the statement following the `End Select` statement.</span></span> <span data-ttu-id="5a44c-127">`Exit Select` 可仅在`Select Case`语句。</span><span class="sxs-lookup"><span data-stu-id="5a44c-127">`Exit Select` can be used only inside a `Select Case` statement.</span></span>  
  
 `Exit Sub`  
 <span data-ttu-id="5a44c-128">立即退出`Sub`它所在的过程。</span><span class="sxs-lookup"><span data-stu-id="5a44c-128">Immediately exits the `Sub` procedure in which it appears.</span></span> <span data-ttu-id="5a44c-129">继续后面的语句调用的语句的执行`Sub`过程。</span><span class="sxs-lookup"><span data-stu-id="5a44c-129">Execution continues with the statement following the statement that called the `Sub` procedure.</span></span> <span data-ttu-id="5a44c-130">`Exit Sub` 可仅在`Sub`过程。</span><span class="sxs-lookup"><span data-stu-id="5a44c-130">`Exit Sub` can be used only inside a `Sub` procedure.</span></span>  
  
 <span data-ttu-id="5a44c-131">在中`Sub`过程中，`Exit Sub`语句等效于`Return`语句。</span><span class="sxs-lookup"><span data-stu-id="5a44c-131">In a `Sub` procedure, the `Exit Sub` statement is equivalent to the `Return` statement.</span></span>  
  
 `Exit Try`  
 <span data-ttu-id="5a44c-132">立即退出`Try`或`Catch`阻止所在。</span><span class="sxs-lookup"><span data-stu-id="5a44c-132">Immediately exits the `Try` or `Catch` block in which it appears.</span></span> <span data-ttu-id="5a44c-133">继续执行`Finally`阻止如果有的话，或后面的语句与`End Try`否则为语句。</span><span class="sxs-lookup"><span data-stu-id="5a44c-133">Execution continues with the `Finally` block if there is one, or with the statement following the `End Try` statement otherwise.</span></span> <span data-ttu-id="5a44c-134">`Exit Try` 可仅在`Try`或`Catch`块中，不能在`Finally`块。</span><span class="sxs-lookup"><span data-stu-id="5a44c-134">`Exit Try` can be used only inside a `Try` or `Catch` block, and not inside a `Finally` block.</span></span>  
  
 `Exit While`  
 <span data-ttu-id="5a44c-135">立即退出`While`循环中将显示。</span><span class="sxs-lookup"><span data-stu-id="5a44c-135">Immediately exits the `While` loop in which it appears.</span></span> <span data-ttu-id="5a44c-136">继续后面的语句执行`End While`语句。</span><span class="sxs-lookup"><span data-stu-id="5a44c-136">Execution continues with the statement following the `End While` statement.</span></span> <span data-ttu-id="5a44c-137">`Exit While` 可仅在`While`循环。</span><span class="sxs-lookup"><span data-stu-id="5a44c-137">`Exit While` can be used only inside a `While` loop.</span></span> <span data-ttu-id="5a44c-138">使用时内嵌套`While`循环`Exit While`将控制转移到高循环的一个嵌套级别的循环其中`Exit While`发生。</span><span class="sxs-lookup"><span data-stu-id="5a44c-138">When used within nested `While` loops, `Exit While` transfers control to the loop that is one nested level above the loop where `Exit While` occurs.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="5a44c-139">备注</span><span class="sxs-lookup"><span data-stu-id="5a44c-139">Remarks</span></span>  
 <span data-ttu-id="5a44c-140">不要混淆`Exit`语句替换`End`语句。</span><span class="sxs-lookup"><span data-stu-id="5a44c-140">Do not confuse `Exit` statements with `End` statements.</span></span> <span data-ttu-id="5a44c-141">`Exit` 未定义语句的末尾。</span><span class="sxs-lookup"><span data-stu-id="5a44c-141">`Exit` does not define the end of a statement.</span></span>  
  
## <a name="example"></a><span data-ttu-id="5a44c-142">示例</span><span class="sxs-lookup"><span data-stu-id="5a44c-142">Example</span></span>  
 <span data-ttu-id="5a44c-143">以下示例中，在循环条件停止循环时`index`变量是否大于 100。</span><span class="sxs-lookup"><span data-stu-id="5a44c-143">In the following example, the loop condition stops the loop when the `index` variable is greater than 100.</span></span> <span data-ttu-id="5a44c-144">`If`语句在循环中，但是，导致`Exit Do`语句停止循环索引变量是否大于 10 时。</span><span class="sxs-lookup"><span data-stu-id="5a44c-144">The `If` statement in the loop, however, causes the `Exit Do` statement to stop the loop when the index variable is greater than 10.</span></span>  
  
 [!code-vb[VbVbalrStatements#133](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class10.vb#133)]  
  
## <a name="example"></a><span data-ttu-id="5a44c-145">示例</span><span class="sxs-lookup"><span data-stu-id="5a44c-145">Example</span></span>  
 <span data-ttu-id="5a44c-146">以下示例将返回值分配为函数名称`myFunction`，然后使用`Exit Function`以从函数返回。</span><span class="sxs-lookup"><span data-stu-id="5a44c-146">The following example assigns the return value to the function name `myFunction`, and then uses `Exit Function` to return from the function.</span></span>  
  
 [!code-vb[VbVbalrStatements#23](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#23)]  
  
## <a name="example"></a><span data-ttu-id="5a44c-147">示例</span><span class="sxs-lookup"><span data-stu-id="5a44c-147">Example</span></span>  
 <span data-ttu-id="5a44c-148">下面的示例使用[Return 语句](../../../visual-basic/language-reference/statements/return-statement.md)返回值分配并退出该函数。</span><span class="sxs-lookup"><span data-stu-id="5a44c-148">The following example uses the [Return Statement](../../../visual-basic/language-reference/statements/return-statement.md) to assign the return value and exit the function.</span></span>  
  
 [!code-vb[VbVbalrStatements#24](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#24)]  
  
## <a name="see-also"></a><span data-ttu-id="5a44c-149">请参阅</span><span class="sxs-lookup"><span data-stu-id="5a44c-149">See also</span></span>

- [<span data-ttu-id="5a44c-150">Continue 语句</span><span class="sxs-lookup"><span data-stu-id="5a44c-150">Continue Statement</span></span>](../../../visual-basic/language-reference/statements/continue-statement.md)
- [<span data-ttu-id="5a44c-151">Do...Loop 语句</span><span class="sxs-lookup"><span data-stu-id="5a44c-151">Do...Loop Statement</span></span>](../../../visual-basic/language-reference/statements/do-loop-statement.md)
- [<span data-ttu-id="5a44c-152">End 语句</span><span class="sxs-lookup"><span data-stu-id="5a44c-152">End Statement</span></span>](../../../visual-basic/language-reference/statements/end-statement.md)
- [<span data-ttu-id="5a44c-153">For Each...Next 语句</span><span class="sxs-lookup"><span data-stu-id="5a44c-153">For Each...Next Statement</span></span>](../../../visual-basic/language-reference/statements/for-each-next-statement.md)
- [<span data-ttu-id="5a44c-154">For...Next 语句</span><span class="sxs-lookup"><span data-stu-id="5a44c-154">For...Next Statement</span></span>](../../../visual-basic/language-reference/statements/for-next-statement.md)
- [<span data-ttu-id="5a44c-155">Function 语句</span><span class="sxs-lookup"><span data-stu-id="5a44c-155">Function Statement</span></span>](../../../visual-basic/language-reference/statements/function-statement.md)
- [<span data-ttu-id="5a44c-156">Return 语句</span><span class="sxs-lookup"><span data-stu-id="5a44c-156">Return Statement</span></span>](../../../visual-basic/language-reference/statements/return-statement.md)
- [<span data-ttu-id="5a44c-157">Stop 语句</span><span class="sxs-lookup"><span data-stu-id="5a44c-157">Stop Statement</span></span>](../../../visual-basic/language-reference/statements/stop-statement.md)
- [<span data-ttu-id="5a44c-158">Sub 语句</span><span class="sxs-lookup"><span data-stu-id="5a44c-158">Sub Statement</span></span>](../../../visual-basic/language-reference/statements/sub-statement.md)
- [<span data-ttu-id="5a44c-159">Try...Catch...Finally 语句</span><span class="sxs-lookup"><span data-stu-id="5a44c-159">Try...Catch...Finally Statement</span></span>](../../../visual-basic/language-reference/statements/try-catch-finally-statement.md)
