---
title: Exit 语句
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
ms.openlocfilehash: 1bfe81428fd3c50663fd8978e05c6a945cd47df8
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/22/2019
ms.locfileid: "74345941"
---
# <a name="exit-statement-visual-basic"></a><span data-ttu-id="63532-102">Exit 语句 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="63532-102">Exit Statement (Visual Basic)</span></span>

<span data-ttu-id="63532-103">退出过程或块并将控制立即传输到过程调用或块定义后面的语句。</span><span class="sxs-lookup"><span data-stu-id="63532-103">Exits a procedure or block and transfers control immediately to the statement following the procedure call or the block definition.</span></span>

## <a name="syntax"></a><span data-ttu-id="63532-104">语法</span><span class="sxs-lookup"><span data-stu-id="63532-104">Syntax</span></span>

```vb
Exit { Do | For | Function | Property | Select | Sub | Try | While }
```

## <a name="statements"></a><span data-ttu-id="63532-105">语句</span><span class="sxs-lookup"><span data-stu-id="63532-105">Statements</span></span>

 `Exit Do`  
 <span data-ttu-id="63532-106">立即退出出现 `Do` 循环。</span><span class="sxs-lookup"><span data-stu-id="63532-106">Immediately exits the `Do` loop in which it appears.</span></span> <span data-ttu-id="63532-107">继续执行 `Loop` 语句后面的语句。</span><span class="sxs-lookup"><span data-stu-id="63532-107">Execution continues with the statement following the `Loop` statement.</span></span> <span data-ttu-id="63532-108">`Exit Do` 只能在 `Do` 循环内使用。</span><span class="sxs-lookup"><span data-stu-id="63532-108">`Exit Do` can be used only inside a `Do` loop.</span></span> <span data-ttu-id="63532-109">在嵌套的 `Do` 循环中使用时，`Exit Do` 退出最内层的循环，并将控制转移到下一个更高的嵌套级别。</span><span class="sxs-lookup"><span data-stu-id="63532-109">When used within nested `Do` loops, `Exit Do` exits the innermost loop and transfers control to the next higher level of nesting.</span></span>

 `Exit For`  
 <span data-ttu-id="63532-110">立即退出出现 `For` 循环。</span><span class="sxs-lookup"><span data-stu-id="63532-110">Immediately exits the `For` loop in which it appears.</span></span> <span data-ttu-id="63532-111">继续执行 `Next` 语句后面的语句。</span><span class="sxs-lookup"><span data-stu-id="63532-111">Execution continues with the statement following the `Next` statement.</span></span> <span data-ttu-id="63532-112">`Exit For` 只能在 `For`...`Next` 或 `For Each`...`Next` 循环内使用。</span><span class="sxs-lookup"><span data-stu-id="63532-112">`Exit For` can be used only inside a `For`...`Next` or `For Each`...`Next` loop.</span></span> <span data-ttu-id="63532-113">在嵌套的 `For` 循环中使用时，`Exit For` 退出最内层的循环，并将控制转移到下一个更高的嵌套级别。</span><span class="sxs-lookup"><span data-stu-id="63532-113">When used within nested `For` loops, `Exit For` exits the innermost loop and transfers control to the next higher level of nesting.</span></span>

 `Exit Function`  
 <span data-ttu-id="63532-114">立即退出显示的 `Function` 过程。</span><span class="sxs-lookup"><span data-stu-id="63532-114">Immediately exits the `Function` procedure in which it appears.</span></span> <span data-ttu-id="63532-115">继续执行调用 `Function` 过程的语句后面的语句。</span><span class="sxs-lookup"><span data-stu-id="63532-115">Execution continues with the statement following the statement that called the `Function` procedure.</span></span> <span data-ttu-id="63532-116">`Exit Function` 只能在 `Function` 过程中使用。</span><span class="sxs-lookup"><span data-stu-id="63532-116">`Exit Function` can be used only inside a `Function` procedure.</span></span>

 <span data-ttu-id="63532-117">若要指定一个返回值，可以在 `Exit Function` 语句前面的行上将值分配给函数名称。</span><span class="sxs-lookup"><span data-stu-id="63532-117">To specify a return value, you can assign the value to the function name on a line before the `Exit Function` statement.</span></span> <span data-ttu-id="63532-118">若要分配返回值并在一个语句中退出函数，可以改为使用[Return 语句](return-statement.md)。</span><span class="sxs-lookup"><span data-stu-id="63532-118">To assign the return value and exit the function in one statement, you can instead use the [Return Statement](return-statement.md).</span></span>

 `Exit Property`  
 <span data-ttu-id="63532-119">立即退出显示的 `Property` 过程。</span><span class="sxs-lookup"><span data-stu-id="63532-119">Immediately exits the `Property` procedure in which it appears.</span></span> <span data-ttu-id="63532-120">执行将继续执行调用 `Property` 过程的语句，即，语句请求或设置属性的值。</span><span class="sxs-lookup"><span data-stu-id="63532-120">Execution continues with the statement that called the `Property` procedure, that is, with the statement requesting or setting the property's value.</span></span> <span data-ttu-id="63532-121">`Exit Property` 只能在属性的 `Get` 或 `Set` 过程中使用。</span><span class="sxs-lookup"><span data-stu-id="63532-121">`Exit Property` can be used only inside a property's `Get` or `Set` procedure.</span></span>

 <span data-ttu-id="63532-122">若要在 `Get` 过程中指定返回值，可以在 `Exit Property` 语句前面的行上将值分配给函数名称。</span><span class="sxs-lookup"><span data-stu-id="63532-122">To specify a return value in a `Get` procedure, you can assign the value to the function name on a line before the `Exit Property` statement.</span></span> <span data-ttu-id="63532-123">若要分配返回值并在一个语句中退出 `Get` 过程，则可以改用 `Return` 语句。</span><span class="sxs-lookup"><span data-stu-id="63532-123">To assign the return value and exit the `Get` procedure in one statement, you can instead use the `Return` statement.</span></span>

 <span data-ttu-id="63532-124">在 `Set` 过程中，`Exit Property` 语句与 `Return` 语句等效。</span><span class="sxs-lookup"><span data-stu-id="63532-124">In a `Set` procedure, the `Exit Property` statement is equivalent to the `Return` statement.</span></span>

 `Exit Select`  
 <span data-ttu-id="63532-125">立即退出显示该 `Select Case` 的块。</span><span class="sxs-lookup"><span data-stu-id="63532-125">Immediately exits the `Select Case` block in which it appears.</span></span> <span data-ttu-id="63532-126">继续执行 `End Select` 语句后面的语句。</span><span class="sxs-lookup"><span data-stu-id="63532-126">Execution continues with the statement following the `End Select` statement.</span></span> <span data-ttu-id="63532-127">`Exit Select` 只能在 `Select Case` 语句内使用。</span><span class="sxs-lookup"><span data-stu-id="63532-127">`Exit Select` can be used only inside a `Select Case` statement.</span></span>

 `Exit Sub`  
 <span data-ttu-id="63532-128">立即退出显示的 `Sub` 过程。</span><span class="sxs-lookup"><span data-stu-id="63532-128">Immediately exits the `Sub` procedure in which it appears.</span></span> <span data-ttu-id="63532-129">继续执行调用 `Sub` 过程的语句后面的语句。</span><span class="sxs-lookup"><span data-stu-id="63532-129">Execution continues with the statement following the statement that called the `Sub` procedure.</span></span> <span data-ttu-id="63532-130">`Exit Sub` 只能在 `Sub` 过程中使用。</span><span class="sxs-lookup"><span data-stu-id="63532-130">`Exit Sub` can be used only inside a `Sub` procedure.</span></span>

 <span data-ttu-id="63532-131">在 `Sub` 过程中，`Exit Sub` 语句与 `Return` 语句等效。</span><span class="sxs-lookup"><span data-stu-id="63532-131">In a `Sub` procedure, the `Exit Sub` statement is equivalent to the `Return` statement.</span></span>

 `Exit Try`  
 <span data-ttu-id="63532-132">会立即退出显示的 `Try` 或 `Catch` 块。</span><span class="sxs-lookup"><span data-stu-id="63532-132">Immediately exits the `Try` or `Catch` block in which it appears.</span></span> <span data-ttu-id="63532-133">如果有一个，则继续执行 `Finally` 块，否则将继续执行 `End Try` 语句后面的语句。</span><span class="sxs-lookup"><span data-stu-id="63532-133">Execution continues with the `Finally` block if there is one, or with the statement following the `End Try` statement otherwise.</span></span> <span data-ttu-id="63532-134">`Exit Try` 只能在 `Try` 或 `Catch` 块内使用，而不能在 `Finally` 块内使用。</span><span class="sxs-lookup"><span data-stu-id="63532-134">`Exit Try` can be used only inside a `Try` or `Catch` block, and not inside a `Finally` block.</span></span>

 `Exit While`  
 <span data-ttu-id="63532-135">立即退出出现 `While` 循环。</span><span class="sxs-lookup"><span data-stu-id="63532-135">Immediately exits the `While` loop in which it appears.</span></span> <span data-ttu-id="63532-136">继续执行 `End While` 语句后面的语句。</span><span class="sxs-lookup"><span data-stu-id="63532-136">Execution continues with the statement following the `End While` statement.</span></span> <span data-ttu-id="63532-137">`Exit While` 只能在 `While` 循环内使用。</span><span class="sxs-lookup"><span data-stu-id="63532-137">`Exit While` can be used only inside a `While` loop.</span></span> <span data-ttu-id="63532-138">在嵌套的 `While` 循环中使用时，`Exit While` 将控制转移到循环，该循环在 `Exit While` 发生的循环之上的一个嵌套级别。</span><span class="sxs-lookup"><span data-stu-id="63532-138">When used within nested `While` loops, `Exit While` transfers control to the loop that is one nested level above the loop where `Exit While` occurs.</span></span>

## <a name="remarks"></a><span data-ttu-id="63532-139">备注</span><span class="sxs-lookup"><span data-stu-id="63532-139">Remarks</span></span>

<span data-ttu-id="63532-140">不要将 `Exit` 语句与 `End` 语句混淆。</span><span class="sxs-lookup"><span data-stu-id="63532-140">Do not confuse `Exit` statements with `End` statements.</span></span> <span data-ttu-id="63532-141">`Exit` 不定义语句的末尾。</span><span class="sxs-lookup"><span data-stu-id="63532-141">`Exit` does not define the end of a statement.</span></span>

## <a name="example"></a><span data-ttu-id="63532-142">示例</span><span class="sxs-lookup"><span data-stu-id="63532-142">Example</span></span>

<span data-ttu-id="63532-143">在下面的示例中，循环条件在 `index` 变量大于100时停止循环。</span><span class="sxs-lookup"><span data-stu-id="63532-143">In the following example, the loop condition stops the loop when the `index` variable is greater than 100.</span></span> <span data-ttu-id="63532-144">但是，循环中的 `If` 语句导致 `Exit Do` 语句在索引变量大于10时停止循环。</span><span class="sxs-lookup"><span data-stu-id="63532-144">The `If` statement in the loop, however, causes the `Exit Do` statement to stop the loop when the index variable is greater than 10.</span></span>

[!code-vb[VbVbalrStatements#133](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class10.vb#133)]

## <a name="example"></a><span data-ttu-id="63532-145">示例</span><span class="sxs-lookup"><span data-stu-id="63532-145">Example</span></span>

<span data-ttu-id="63532-146">下面的示例将返回值分配给函数名称 `myFunction`，然后使用 `Exit Function` 从函数返回：</span><span class="sxs-lookup"><span data-stu-id="63532-146">The following example assigns the return value to the function name `myFunction`, and then uses `Exit Function` to return from the function:</span></span>

[!code-vb[VbVbalrStatements#23](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#23)]

## <a name="example"></a><span data-ttu-id="63532-147">示例</span><span class="sxs-lookup"><span data-stu-id="63532-147">Example</span></span>

<span data-ttu-id="63532-148">下面的示例使用[Return 语句](return-statement.md)来分配返回值并退出函数：</span><span class="sxs-lookup"><span data-stu-id="63532-148">The following example uses the [Return Statement](return-statement.md) to assign the return value and exit the function:</span></span>

[!code-vb[VbVbalrStatements#24](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#24)]

## <a name="see-also"></a><span data-ttu-id="63532-149">另请参阅</span><span class="sxs-lookup"><span data-stu-id="63532-149">See also</span></span>

- [<span data-ttu-id="63532-150">Continue 语句</span><span class="sxs-lookup"><span data-stu-id="63532-150">Continue Statement</span></span>](continue-statement.md)
- [<span data-ttu-id="63532-151">Do...Loop 语句</span><span class="sxs-lookup"><span data-stu-id="63532-151">Do...Loop Statement</span></span>](do-loop-statement.md)
- [<span data-ttu-id="63532-152">End 语句</span><span class="sxs-lookup"><span data-stu-id="63532-152">End Statement</span></span>](end-statement.md)
- [<span data-ttu-id="63532-153">For Each...Next 语句</span><span class="sxs-lookup"><span data-stu-id="63532-153">For Each...Next Statement</span></span>](for-each-next-statement.md)
- [<span data-ttu-id="63532-154">For...Next 语句</span><span class="sxs-lookup"><span data-stu-id="63532-154">For...Next Statement</span></span>](for-next-statement.md)
- [<span data-ttu-id="63532-155">Function 语句</span><span class="sxs-lookup"><span data-stu-id="63532-155">Function Statement</span></span>](function-statement.md)
- [<span data-ttu-id="63532-156">Return 语句</span><span class="sxs-lookup"><span data-stu-id="63532-156">Return Statement</span></span>](return-statement.md)
- [<span data-ttu-id="63532-157">Stop 语句</span><span class="sxs-lookup"><span data-stu-id="63532-157">Stop Statement</span></span>](stop-statement.md)
- [<span data-ttu-id="63532-158">Sub 语句</span><span class="sxs-lookup"><span data-stu-id="63532-158">Sub Statement</span></span>](sub-statement.md)
- [<span data-ttu-id="63532-159">Try...Catch...Finally 语句</span><span class="sxs-lookup"><span data-stu-id="63532-159">Try...Catch...Finally Statement</span></span>](try-catch-finally-statement.md)
