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
ms.openlocfilehash: 9c25653809c51662ea5b606ab97be6a9b50d5986
ms.sourcegitcommit: 7bfe1682d9368cf88d43e895d1e80ba2d88c3a99
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/04/2019
ms.locfileid: "71956933"
---
# <a name="exit-statement-visual-basic"></a><span data-ttu-id="9aa7e-102">Exit 语句 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="9aa7e-102">Exit Statement (Visual Basic)</span></span>

<span data-ttu-id="9aa7e-103">退出过程或块并将控制立即传输到过程调用或块定义后面的语句。</span><span class="sxs-lookup"><span data-stu-id="9aa7e-103">Exits a procedure or block and transfers control immediately to the statement following the procedure call or the block definition.</span></span>

## <a name="syntax"></a><span data-ttu-id="9aa7e-104">语法</span><span class="sxs-lookup"><span data-stu-id="9aa7e-104">Syntax</span></span>

```vb
Exit { Do | For | Function | Property | Select | Sub | Try | While }
```

## <a name="statements"></a><span data-ttu-id="9aa7e-105">语句</span><span class="sxs-lookup"><span data-stu-id="9aa7e-105">Statements</span></span>

 `Exit Do`  
 <span data-ttu-id="9aa7e-106">立即退出出现 @no__t 的0循环。</span><span class="sxs-lookup"><span data-stu-id="9aa7e-106">Immediately exits the `Do` loop in which it appears.</span></span> <span data-ttu-id="9aa7e-107">继续执行 `Loop` 语句后面的语句。</span><span class="sxs-lookup"><span data-stu-id="9aa7e-107">Execution continues with the statement following the `Loop` statement.</span></span> <span data-ttu-id="9aa7e-108">`Exit Do` 只能在 @no__t 循环内使用。</span><span class="sxs-lookup"><span data-stu-id="9aa7e-108">`Exit Do` can be used only inside a `Do` loop.</span></span> <span data-ttu-id="9aa7e-109">在嵌套 `Do` 循环内使用时，`Exit Do` 退出最内层的循环，并将控制转移到下一个更高的嵌套级别。</span><span class="sxs-lookup"><span data-stu-id="9aa7e-109">When used within nested `Do` loops, `Exit Do` exits the innermost loop and transfers control to the next higher level of nesting.</span></span>

 `Exit For`  
 <span data-ttu-id="9aa7e-110">立即退出出现 @no__t 的0循环。</span><span class="sxs-lookup"><span data-stu-id="9aa7e-110">Immediately exits the `For` loop in which it appears.</span></span> <span data-ttu-id="9aa7e-111">继续执行 `Next` 语句后面的语句。</span><span class="sxs-lookup"><span data-stu-id="9aa7e-111">Execution continues with the statement following the `Next` statement.</span></span> <span data-ttu-id="9aa7e-112">`Exit For` 只能在 @no__t `Next` 或 `For Each` ... `Next` 循环内使用。</span><span class="sxs-lookup"><span data-stu-id="9aa7e-112">`Exit For` can be used only inside a `For`...`Next` or `For Each`...`Next` loop.</span></span> <span data-ttu-id="9aa7e-113">在嵌套 `For` 循环内使用时，`Exit For` 退出最内层的循环，并将控制转移到下一个更高的嵌套级别。</span><span class="sxs-lookup"><span data-stu-id="9aa7e-113">When used within nested `For` loops, `Exit For` exits the innermost loop and transfers control to the next higher level of nesting.</span></span>

 `Exit Function`  
 <span data-ttu-id="9aa7e-114">会立即退出显示它的 @no__t 0 过程。</span><span class="sxs-lookup"><span data-stu-id="9aa7e-114">Immediately exits the `Function` procedure in which it appears.</span></span> <span data-ttu-id="9aa7e-115">执行将继续，语句后跟调用 `Function` 过程的语句后面的语句。</span><span class="sxs-lookup"><span data-stu-id="9aa7e-115">Execution continues with the statement following the statement that called the `Function` procedure.</span></span> <span data-ttu-id="9aa7e-116">`Exit Function` 只能在 @no__t 一过程中使用。</span><span class="sxs-lookup"><span data-stu-id="9aa7e-116">`Exit Function` can be used only inside a `Function` procedure.</span></span>

 <span data-ttu-id="9aa7e-117">若要指定返回值，可以在 `Exit Function` 语句之前，将值分配给函数名称。</span><span class="sxs-lookup"><span data-stu-id="9aa7e-117">To specify a return value, you can assign the value to the function name on a line before the `Exit Function` statement.</span></span> <span data-ttu-id="9aa7e-118">若要分配返回值并在一个语句中退出函数，可以改为使用[Return 语句](return-statement.md)。</span><span class="sxs-lookup"><span data-stu-id="9aa7e-118">To assign the return value and exit the function in one statement, you can instead use the [Return Statement](return-statement.md).</span></span>

 `Exit Property`  
 <span data-ttu-id="9aa7e-119">会立即退出显示它的 @no__t 0 过程。</span><span class="sxs-lookup"><span data-stu-id="9aa7e-119">Immediately exits the `Property` procedure in which it appears.</span></span> <span data-ttu-id="9aa7e-120">执行将继续，语句称为 @no__t 的过程，即，语句请求或设置属性的值。</span><span class="sxs-lookup"><span data-stu-id="9aa7e-120">Execution continues with the statement that called the `Property` procedure, that is, with the statement requesting or setting the property's value.</span></span> <span data-ttu-id="9aa7e-121">`Exit Property` 只能在属性的 @no__t 或 @no__t 步骤中使用。</span><span class="sxs-lookup"><span data-stu-id="9aa7e-121">`Exit Property` can be used only inside a property's `Get` or `Set` procedure.</span></span>

 <span data-ttu-id="9aa7e-122">若要在 @no__t 的过程中指定返回值，可以在 @no__t 1 语句之前，将值分配给函数名称。</span><span class="sxs-lookup"><span data-stu-id="9aa7e-122">To specify a return value in a `Get` procedure, you can assign the value to the function name on a line before the `Exit Property` statement.</span></span> <span data-ttu-id="9aa7e-123">若要在一个语句中分配返回值并退出 `Get` 过程，可以改为使用 @no__t 语句。</span><span class="sxs-lookup"><span data-stu-id="9aa7e-123">To assign the return value and exit the `Get` procedure in one statement, you can instead use the `Return` statement.</span></span>

 <span data-ttu-id="9aa7e-124">在 @no__t 的过程中，@no__t 语句等效于第 2 @no__t 语句。</span><span class="sxs-lookup"><span data-stu-id="9aa7e-124">In a `Set` procedure, the `Exit Property` statement is equivalent to the `Return` statement.</span></span>

 `Exit Select`  
 <span data-ttu-id="9aa7e-125">立即退出出现 @no__t 的块。</span><span class="sxs-lookup"><span data-stu-id="9aa7e-125">Immediately exits the `Select Case` block in which it appears.</span></span> <span data-ttu-id="9aa7e-126">继续执行 `End Select` 语句后面的语句。</span><span class="sxs-lookup"><span data-stu-id="9aa7e-126">Execution continues with the statement following the `End Select` statement.</span></span> <span data-ttu-id="9aa7e-127">`Exit Select` 只能在 @no__t 语句中使用。</span><span class="sxs-lookup"><span data-stu-id="9aa7e-127">`Exit Select` can be used only inside a `Select Case` statement.</span></span>

 `Exit Sub`  
 <span data-ttu-id="9aa7e-128">会立即退出显示它的 @no__t 0 过程。</span><span class="sxs-lookup"><span data-stu-id="9aa7e-128">Immediately exits the `Sub` procedure in which it appears.</span></span> <span data-ttu-id="9aa7e-129">执行将继续，语句后跟调用 `Sub` 过程的语句后面的语句。</span><span class="sxs-lookup"><span data-stu-id="9aa7e-129">Execution continues with the statement following the statement that called the `Sub` procedure.</span></span> <span data-ttu-id="9aa7e-130">`Exit Sub` 只能在 @no__t 一过程中使用。</span><span class="sxs-lookup"><span data-stu-id="9aa7e-130">`Exit Sub` can be used only inside a `Sub` procedure.</span></span>

 <span data-ttu-id="9aa7e-131">在 @no__t 的过程中，@no__t 语句等效于第 2 @no__t 语句。</span><span class="sxs-lookup"><span data-stu-id="9aa7e-131">In a `Sub` procedure, the `Exit Sub` statement is equivalent to the `Return` statement.</span></span>

 `Exit Try`  
 <span data-ttu-id="9aa7e-132">立即退出出现 @no__t 0 或 `Catch` 块。</span><span class="sxs-lookup"><span data-stu-id="9aa7e-132">Immediately exits the `Try` or `Catch` block in which it appears.</span></span> <span data-ttu-id="9aa7e-133">如果有 `Finally` 块，则继续执行; 否则，将继续执行 `End Try` 语句后面的语句。</span><span class="sxs-lookup"><span data-stu-id="9aa7e-133">Execution continues with the `Finally` block if there is one, or with the statement following the `End Try` statement otherwise.</span></span> <span data-ttu-id="9aa7e-134">`Exit Try` 只能在 @no__t 或 `Catch` 块内使用，而不能在 @no__t 块内使用。</span><span class="sxs-lookup"><span data-stu-id="9aa7e-134">`Exit Try` can be used only inside a `Try` or `Catch` block, and not inside a `Finally` block.</span></span>

 `Exit While`  
 <span data-ttu-id="9aa7e-135">立即退出出现 @no__t 的0循环。</span><span class="sxs-lookup"><span data-stu-id="9aa7e-135">Immediately exits the `While` loop in which it appears.</span></span> <span data-ttu-id="9aa7e-136">继续执行 `End While` 语句后面的语句。</span><span class="sxs-lookup"><span data-stu-id="9aa7e-136">Execution continues with the statement following the `End While` statement.</span></span> <span data-ttu-id="9aa7e-137">`Exit While` 只能在 @no__t 循环内使用。</span><span class="sxs-lookup"><span data-stu-id="9aa7e-137">`Exit While` can be used only inside a `While` loop.</span></span> <span data-ttu-id="9aa7e-138">在嵌套 `While` 循环内使用时，`Exit While` 会将控制转移到循环，该循环是在发生 `Exit While` 的循环之上的一个嵌套级别。</span><span class="sxs-lookup"><span data-stu-id="9aa7e-138">When used within nested `While` loops, `Exit While` transfers control to the loop that is one nested level above the loop where `Exit While` occurs.</span></span>

## <a name="remarks"></a><span data-ttu-id="9aa7e-139">备注</span><span class="sxs-lookup"><span data-stu-id="9aa7e-139">Remarks</span></span>

<span data-ttu-id="9aa7e-140">不要将 `Exit` 语句与 @no__t 语句混淆。</span><span class="sxs-lookup"><span data-stu-id="9aa7e-140">Do not confuse `Exit` statements with `End` statements.</span></span> <span data-ttu-id="9aa7e-141">`Exit` 不定义语句的末尾。</span><span class="sxs-lookup"><span data-stu-id="9aa7e-141">`Exit` does not define the end of a statement.</span></span>

## <a name="example"></a><span data-ttu-id="9aa7e-142">示例</span><span class="sxs-lookup"><span data-stu-id="9aa7e-142">Example</span></span>

<span data-ttu-id="9aa7e-143">在下面的示例中，当 `index` 变量大于100时，loop 条件将停止循环。</span><span class="sxs-lookup"><span data-stu-id="9aa7e-143">In the following example, the loop condition stops the loop when the `index` variable is greater than 100.</span></span> <span data-ttu-id="9aa7e-144">但是，循环中的 `If` 语句导致当索引变量大于10时，`Exit Do` 语句停止循环。</span><span class="sxs-lookup"><span data-stu-id="9aa7e-144">The `If` statement in the loop, however, causes the `Exit Do` statement to stop the loop when the index variable is greater than 10.</span></span>

[!code-vb[VbVbalrStatements#133](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class10.vb#133)]

## <a name="example"></a><span data-ttu-id="9aa7e-145">示例</span><span class="sxs-lookup"><span data-stu-id="9aa7e-145">Example</span></span>

<span data-ttu-id="9aa7e-146">下面的示例将返回值分配给函数名称 `myFunction`，然后使用 `Exit Function` 从函数返回：</span><span class="sxs-lookup"><span data-stu-id="9aa7e-146">The following example assigns the return value to the function name `myFunction`, and then uses `Exit Function` to return from the function:</span></span>

[!code-vb[VbVbalrStatements#23](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#23)]

## <a name="example"></a><span data-ttu-id="9aa7e-147">示例</span><span class="sxs-lookup"><span data-stu-id="9aa7e-147">Example</span></span>

<span data-ttu-id="9aa7e-148">下面的示例使用[Return 语句](return-statement.md)来分配返回值并退出函数：</span><span class="sxs-lookup"><span data-stu-id="9aa7e-148">The following example uses the [Return Statement](return-statement.md) to assign the return value and exit the function:</span></span>

[!code-vb[VbVbalrStatements#24](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#24)]

## <a name="see-also"></a><span data-ttu-id="9aa7e-149">请参阅</span><span class="sxs-lookup"><span data-stu-id="9aa7e-149">See also</span></span>

- [<span data-ttu-id="9aa7e-150">Continue 语句</span><span class="sxs-lookup"><span data-stu-id="9aa7e-150">Continue Statement</span></span>](continue-statement.md)
- [<span data-ttu-id="9aa7e-151">Do...Loop 语句</span><span class="sxs-lookup"><span data-stu-id="9aa7e-151">Do...Loop Statement</span></span>](do-loop-statement.md)
- [<span data-ttu-id="9aa7e-152">End 语句</span><span class="sxs-lookup"><span data-stu-id="9aa7e-152">End Statement</span></span>](end-statement.md)
- [<span data-ttu-id="9aa7e-153">For Each...Next 语句</span><span class="sxs-lookup"><span data-stu-id="9aa7e-153">For Each...Next Statement</span></span>](for-each-next-statement.md)
- [<span data-ttu-id="9aa7e-154">For...Next 语句</span><span class="sxs-lookup"><span data-stu-id="9aa7e-154">For...Next Statement</span></span>](for-next-statement.md)
- [<span data-ttu-id="9aa7e-155">Function 语句</span><span class="sxs-lookup"><span data-stu-id="9aa7e-155">Function Statement</span></span>](function-statement.md)
- [<span data-ttu-id="9aa7e-156">Return 语句</span><span class="sxs-lookup"><span data-stu-id="9aa7e-156">Return Statement</span></span>](return-statement.md)
- [<span data-ttu-id="9aa7e-157">Stop 语句</span><span class="sxs-lookup"><span data-stu-id="9aa7e-157">Stop Statement</span></span>](stop-statement.md)
- [<span data-ttu-id="9aa7e-158">Sub 语句</span><span class="sxs-lookup"><span data-stu-id="9aa7e-158">Sub Statement</span></span>](sub-statement.md)
- [<span data-ttu-id="9aa7e-159">Try...Catch...Finally 语句</span><span class="sxs-lookup"><span data-stu-id="9aa7e-159">Try...Catch...Finally Statement</span></span>](try-catch-finally-statement.md)
