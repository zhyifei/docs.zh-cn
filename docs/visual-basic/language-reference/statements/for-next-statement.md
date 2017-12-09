---
title: "For...Next 语句 (Visual Basic)"
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords:
- vb.Step
- vb.Next
- vb.To
- vb.for
helpviewer_keywords:
- infinite loops
- Next keyword [Visual Basic], For...Next statements
- For keyword [Visual Basic], For...Next statements
- Step keyword [Visual Basic], For...Next statements
- operator overloading, For...Next statement
- To keyword [Visual Basic], For...Next statements
- endless loops
- loops, endless
- instructions, repeating
- Next statement [Visual Basic], For...Next
- For...Next statements
- loop structures [Visual Basic], For...Next
- loops, infinite
- Exit statement [Visual Basic], For...Next statements
- For statement [Visual Basic]
ms.assetid: f5fc0d51-67ce-4c36-9f09-31c9a91c94e9
caps.latest.revision: "64"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 009c5a383cc3296f7f92888a344fa265547f1077
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="fornext-statement-visual-basic"></a><span data-ttu-id="c7079-102">For...Next 语句 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="c7079-102">For...Next Statement (Visual Basic)</span></span>
<span data-ttu-id="c7079-103">将一组语句重复指定的次数。</span><span class="sxs-lookup"><span data-stu-id="c7079-103">Repeats a group of statements a specified number of times.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c7079-104">语法</span><span class="sxs-lookup"><span data-stu-id="c7079-104">Syntax</span></span>  
  
```  
For counter [ As datatype ] = start To end [ Step step ]  
    [ statements ]  
    [ Continue For ]  
    [ statements ]  
    [ Exit For ]  
    [ statements ]  
Next [ counter ]  
```  
  
## <a name="parts"></a><span data-ttu-id="c7079-105">部件</span><span class="sxs-lookup"><span data-stu-id="c7079-105">Parts</span></span>  
  
|<span data-ttu-id="c7079-106">部件</span><span class="sxs-lookup"><span data-stu-id="c7079-106">Part</span></span>|<span data-ttu-id="c7079-107">描述</span><span class="sxs-lookup"><span data-stu-id="c7079-107">Description</span></span>|  
|----------|-----------------|  
|`counter`|<span data-ttu-id="c7079-108">中所需`For`语句。</span><span class="sxs-lookup"><span data-stu-id="c7079-108">Required in the `For` statement.</span></span> <span data-ttu-id="c7079-109">数值变量。</span><span class="sxs-lookup"><span data-stu-id="c7079-109">Numeric variable.</span></span> <span data-ttu-id="c7079-110">For 循环控制变量。</span><span class="sxs-lookup"><span data-stu-id="c7079-110">The control variable for the loop.</span></span> <span data-ttu-id="c7079-111">有关详细信息，请参阅[计数器参数](#BKMK_Counter)本主题中更高版本。</span><span class="sxs-lookup"><span data-stu-id="c7079-111">For more information, see [Counter Argument](#BKMK_Counter) later in this topic.</span></span>|  
|`datatype`|<span data-ttu-id="c7079-112">可选。</span><span class="sxs-lookup"><span data-stu-id="c7079-112">Optional.</span></span> <span data-ttu-id="c7079-113">数据类型的`counter`。</span><span class="sxs-lookup"><span data-stu-id="c7079-113">Data type of `counter`.</span></span> <span data-ttu-id="c7079-114">有关详细信息，请参阅[计数器参数](#BKMK_Counter)本主题中更高版本。</span><span class="sxs-lookup"><span data-stu-id="c7079-114">For more information, see [Counter Argument](#BKMK_Counter) later in this topic.</span></span>|  
|`start`|<span data-ttu-id="c7079-115">必需。</span><span class="sxs-lookup"><span data-stu-id="c7079-115">Required.</span></span> <span data-ttu-id="c7079-116">数值表达式。</span><span class="sxs-lookup"><span data-stu-id="c7079-116">Numeric expression.</span></span> <span data-ttu-id="c7079-117">`counter` 的初始值。</span><span class="sxs-lookup"><span data-stu-id="c7079-117">The initial value of `counter`.</span></span>|  
|`end`|<span data-ttu-id="c7079-118">必需。</span><span class="sxs-lookup"><span data-stu-id="c7079-118">Required.</span></span> <span data-ttu-id="c7079-119">数值表达式。</span><span class="sxs-lookup"><span data-stu-id="c7079-119">Numeric expression.</span></span> <span data-ttu-id="c7079-120">最终值`counter`。</span><span class="sxs-lookup"><span data-stu-id="c7079-120">The final value of `counter`.</span></span>|  
|`step`|<span data-ttu-id="c7079-121">可选。</span><span class="sxs-lookup"><span data-stu-id="c7079-121">Optional.</span></span> <span data-ttu-id="c7079-122">数值表达式。</span><span class="sxs-lookup"><span data-stu-id="c7079-122">Numeric expression.</span></span> <span data-ttu-id="c7079-123">依据的数量`counter`执行循环时，每次都会递增。</span><span class="sxs-lookup"><span data-stu-id="c7079-123">The amount by which `counter` is incremented each time through the loop.</span></span>|  
|`statements`|<span data-ttu-id="c7079-124">可选。</span><span class="sxs-lookup"><span data-stu-id="c7079-124">Optional.</span></span> <span data-ttu-id="c7079-125">一个或多个语句之间`For`和`Next`运行指定的次数。</span><span class="sxs-lookup"><span data-stu-id="c7079-125">One or more statements between `For` and `Next` that run the specified number of times.</span></span>|  
|`Continue For`|<span data-ttu-id="c7079-126">可选。</span><span class="sxs-lookup"><span data-stu-id="c7079-126">Optional.</span></span> <span data-ttu-id="c7079-127">将控制转移到下一步的循环迭代。</span><span class="sxs-lookup"><span data-stu-id="c7079-127">Transfers control to the next loop iteration.</span></span>|  
|`Exit For`|<span data-ttu-id="c7079-128">可选。</span><span class="sxs-lookup"><span data-stu-id="c7079-128">Optional.</span></span> <span data-ttu-id="c7079-129">将扩展的控制转移`For`循环。</span><span class="sxs-lookup"><span data-stu-id="c7079-129">Transfers control out of the `For` loop.</span></span>|  
|`Next`|<span data-ttu-id="c7079-130">必需。</span><span class="sxs-lookup"><span data-stu-id="c7079-130">Required.</span></span> <span data-ttu-id="c7079-131">终止的定义`For`循环。</span><span class="sxs-lookup"><span data-stu-id="c7079-131">Terminates the definition of the `For` loop.</span></span>|  
  
> [!NOTE]
>  <span data-ttu-id="c7079-132">`To`关键字用于在此语句中指定计数器的范围。</span><span class="sxs-lookup"><span data-stu-id="c7079-132">The `To` keyword is used in this statement to specify the range for the counter.</span></span> <span data-ttu-id="c7079-133">你还可以使用此关键字在[选择...Case 语句](../../../visual-basic/language-reference/statements/select-case-statement.md)和数组声明中。</span><span class="sxs-lookup"><span data-stu-id="c7079-133">You can also use this keyword in the [Select...Case Statement](../../../visual-basic/language-reference/statements/select-case-statement.md) and in array declarations.</span></span> <span data-ttu-id="c7079-134">有关数组声明的详细信息，请参阅[Dim 语句](../../../visual-basic/language-reference/statements/dim-statement.md)。</span><span class="sxs-lookup"><span data-stu-id="c7079-134">For more information about array declarations, see [Dim Statement](../../../visual-basic/language-reference/statements/dim-statement.md).</span></span>  
  
## <a name="simple-examples"></a><span data-ttu-id="c7079-135">简单的示例</span><span class="sxs-lookup"><span data-stu-id="c7079-135">Simple Examples</span></span>  
 <span data-ttu-id="c7079-136">你使用`For`...`Next`结构时要重复次数的一组语句。</span><span class="sxs-lookup"><span data-stu-id="c7079-136">You use a `For`...`Next` structure when you want to repeat a set of statements a set number of times.</span></span>  
  
 <span data-ttu-id="c7079-137">在下面的示例中，`index`变量开头的值为 1，并与每个迭代循环，结束后的值递增`index`达到 5。</span><span class="sxs-lookup"><span data-stu-id="c7079-137">In the following example, the `index` variable starts with a value of 1 and is incremented with each iteration of the loop, ending after the value of `index` reaches 5.</span></span>  
  
 [!code-vb[VbVbalrStatements#111](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/for-next-statement_1.vb)]  
  
 <span data-ttu-id="c7079-138">在下面的示例中，`number`变量从 2 开始，并通过循环，结束后的值的每个迭代上的 0.25 减少`number`达到 0。</span><span class="sxs-lookup"><span data-stu-id="c7079-138">In the following example, the `number` variable starts at 2 and is reduced by 0.25 on each iteration of the loop, ending after the value of `number` reaches 0.</span></span> <span data-ttu-id="c7079-139">`Step`参数`-.25`降低 0.25 循环的每个迭代上的值。</span><span class="sxs-lookup"><span data-stu-id="c7079-139">The `Step` argument of `-.25` reduces the value by 0.25 on each iteration of the loop.</span></span>  
  
 [!code-vb[VbVbalrStatements#112](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/for-next-statement_2.vb)]  
  
> [!TIP]
>  <span data-ttu-id="c7079-140">A[时...While 语句结束](../../../visual-basic/language-reference/statements/while-end-while-statement.md)或[执行...循环语句](../../../visual-basic/language-reference/statements/do-loop-statement.md)可以有效地工作时你不知道提前多少次，以在循环中运行语句。</span><span class="sxs-lookup"><span data-stu-id="c7079-140">A [While...End While Statement](../../../visual-basic/language-reference/statements/while-end-while-statement.md) or [Do...Loop Statement](../../../visual-basic/language-reference/statements/do-loop-statement.md) works well when you don't know in advance how many times to run the statements in the loop.</span></span> <span data-ttu-id="c7079-141">但是，如果你希望运行特定次数的循环`For`...`Next`循环是更好的选择。</span><span class="sxs-lookup"><span data-stu-id="c7079-141">However, when you expect to run the loop a specific number of times, a `For`...`Next` loop is a better choice.</span></span> <span data-ttu-id="c7079-142">当您首次进入循环时确定迭代的数。</span><span class="sxs-lookup"><span data-stu-id="c7079-142">You determine the number of iterations when you first enter the loop.</span></span>  
  
## <a name="nesting-loops"></a><span data-ttu-id="c7079-143">嵌套循环</span><span class="sxs-lookup"><span data-stu-id="c7079-143">Nesting Loops</span></span>  
 <span data-ttu-id="c7079-144">可以嵌套`For`置于另一个循环内的循环。</span><span class="sxs-lookup"><span data-stu-id="c7079-144">You can nest `For` loops by putting one loop within another.</span></span> <span data-ttu-id="c7079-145">下面的示例演示嵌套`For`...`Next`具有不同的单步值的结构。</span><span class="sxs-lookup"><span data-stu-id="c7079-145">The following example demonstrates nested `For`...`Next` structures that have different step values.</span></span> <span data-ttu-id="c7079-146">外部循环创建循环的每次迭代的字符串。</span><span class="sxs-lookup"><span data-stu-id="c7079-146">The outer loop creates a string for every iteration of the loop.</span></span> <span data-ttu-id="c7079-147">内部循环递减循环的每次迭代循环计数器变量。</span><span class="sxs-lookup"><span data-stu-id="c7079-147">The inner loop decrements a loop counter variable for every iteration of the loop.</span></span>  
  
 [!code-vb[VbVbalrStatements#113](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/for-next-statement_3.vb)]  
  
 <span data-ttu-id="c7079-148">每个循环时嵌套循环，必须具有唯一`counter`变量。</span><span class="sxs-lookup"><span data-stu-id="c7079-148">When nesting loops, each loop must have a unique `counter` variable.</span></span>  
  
 <span data-ttu-id="c7079-149">你可嵌套不同类型控制结构彼此内部。</span><span class="sxs-lookup"><span data-stu-id="c7079-149">You can also nest different kinds control structures within each other.</span></span> <span data-ttu-id="c7079-150">有关详细信息，请参阅[嵌套控制结构](../../../visual-basic/programming-guide/language-features/control-flow/nested-control-structures.md)。</span><span class="sxs-lookup"><span data-stu-id="c7079-150">For more information, see [Nested Control Structures](../../../visual-basic/programming-guide/language-features/control-flow/nested-control-structures.md).</span></span>  
  
## <a name="exit-for-and-continue-for"></a><span data-ttu-id="c7079-151">退出的针对并继续</span><span class="sxs-lookup"><span data-stu-id="c7079-151">Exit For and Continue For</span></span>  
 <span data-ttu-id="c7079-152">`Exit For`语句将立即退出`For`...`Next`</span><span class="sxs-lookup"><span data-stu-id="c7079-152">The `Exit For` statement immediately exits the `For`…`Next`</span></span> <span data-ttu-id="c7079-153">到后面的语句的循环，并将控制权`Next`语句。</span><span class="sxs-lookup"><span data-stu-id="c7079-153">loop and transfers control to the statement that follows the `Next` statement.</span></span>  
  
 <span data-ttu-id="c7079-154">`Continue For`语句将控制权立即到循环的下一个迭代。</span><span class="sxs-lookup"><span data-stu-id="c7079-154">The `Continue For` statement transfers control immediately to the next iteration of the loop.</span></span> <span data-ttu-id="c7079-155">有关详细信息，请参阅[继续语句](../../../visual-basic/language-reference/statements/continue-statement.md)。</span><span class="sxs-lookup"><span data-stu-id="c7079-155">For more information, see [Continue Statement](../../../visual-basic/language-reference/statements/continue-statement.md).</span></span>  
  
 <span data-ttu-id="c7079-156">下面的示例演示如何使用`Continue For`和`Exit For`语句。</span><span class="sxs-lookup"><span data-stu-id="c7079-156">The following example illustrates the use of the `Continue For` and `Exit For` statements.</span></span>  
  
 [!code-vb[VbVbalrStatements#115](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/for-next-statement_4.vb)]  
  
 <span data-ttu-id="c7079-157">你可以放置任意数量的`Exit For`中的语句`For`...`Next`</span><span class="sxs-lookup"><span data-stu-id="c7079-157">You can put any number of `Exit For` statements in a `For`…`Next`</span></span> <span data-ttu-id="c7079-158">循环。</span><span class="sxs-lookup"><span data-stu-id="c7079-158">loop.</span></span> <span data-ttu-id="c7079-159">当使用内嵌套`For`...`Next`</span><span class="sxs-lookup"><span data-stu-id="c7079-159">When used within nested `For`…`Next`</span></span> <span data-ttu-id="c7079-160">循环，`Exit For`退出最内层的循环，并将控制转移到下一步较高级别的嵌套。</span><span class="sxs-lookup"><span data-stu-id="c7079-160">loops, `Exit For` exits the innermost loop and transfers control to the next higher level of nesting.</span></span>  
  
 <span data-ttu-id="c7079-161">`Exit For`后你评估一些条件通常使用 (例如，在`If`...`Then`...`Else`结构)。</span><span class="sxs-lookup"><span data-stu-id="c7079-161">`Exit For` is often used after you evaluate some condition (for example, in an `If`...`Then`...`Else` structure).</span></span> <span data-ttu-id="c7079-162">你可能想要使用`Exit For`在以下情况：</span><span class="sxs-lookup"><span data-stu-id="c7079-162">You might want to use `Exit For` for the following conditions:</span></span>  
  
-   <span data-ttu-id="c7079-163">继续循环是不必要或无法完成。</span><span class="sxs-lookup"><span data-stu-id="c7079-163">Continuing to iterate is unnecessary or impossible.</span></span> <span data-ttu-id="c7079-164">错误的值或终止请求可能要创建此条件。</span><span class="sxs-lookup"><span data-stu-id="c7079-164">An erroneous value or a termination request might create this condition.</span></span>  
  
-   <span data-ttu-id="c7079-165">A `Try`...`Catch`...`Finally`语句会捕捉异常。</span><span class="sxs-lookup"><span data-stu-id="c7079-165">A `Try`...`Catch`...`Finally` statement catches an exception.</span></span> <span data-ttu-id="c7079-166">你可以使用`Exit For`末尾`Finally`块。</span><span class="sxs-lookup"><span data-stu-id="c7079-166">You might use `Exit For` at the end of the `Finally` block.</span></span>  
  
-   <span data-ttu-id="c7079-167">具有无限循环，即无法运行大型或甚至无限数量的次数的循环。</span><span class="sxs-lookup"><span data-stu-id="c7079-167">You have an endless loop, which is a loop that could run a large or even infinite number of times.</span></span> <span data-ttu-id="c7079-168">如果检测到此类条件，则可以使用`Exit For`来退出循环。</span><span class="sxs-lookup"><span data-stu-id="c7079-168">If you detect such a condition, you can use `Exit For` to escape the loop.</span></span> <span data-ttu-id="c7079-169">有关详细信息，请参阅[执行...循环语句](../../../visual-basic/language-reference/statements/do-loop-statement.md)。</span><span class="sxs-lookup"><span data-stu-id="c7079-169">For more information, see [Do...Loop Statement](../../../visual-basic/language-reference/statements/do-loop-statement.md).</span></span>  
  
## <a name="technical-implementation"></a><span data-ttu-id="c7079-170">技术实现</span><span class="sxs-lookup"><span data-stu-id="c7079-170">Technical Implementation</span></span>  
 <span data-ttu-id="c7079-171">当`For`...`Next`循环开始，Visual Basic 的计算结果`start`， `end`，和`step`。</span><span class="sxs-lookup"><span data-stu-id="c7079-171">When a `For`...`Next` loop starts, Visual Basic evaluates `start`, `end`, and `step`.</span></span> <span data-ttu-id="c7079-172">Visual Basic 计算这些值仅在此时间，然后将分配`start`到`counter`。</span><span class="sxs-lookup"><span data-stu-id="c7079-172">Visual Basic evaluates these values only at this time and then assigns `start` to `counter`.</span></span> <span data-ttu-id="c7079-173">在之前的语句块将运行，Visual Basic 比较`counter`到`end`。</span><span class="sxs-lookup"><span data-stu-id="c7079-173">Before the statement block runs, Visual Basic compares `counter` to `end`.</span></span> <span data-ttu-id="c7079-174">如果`counter`已大于`end`值 (或较小如果`step`为负)，则`For`循环结束并将控制权传递到后面的语句`Next`语句。</span><span class="sxs-lookup"><span data-stu-id="c7079-174">If `counter` is already larger than the `end` value (or smaller if `step` is negative), the `For` loop ends and control passes to the statement that follows the `Next` statement.</span></span> <span data-ttu-id="c7079-175">否则，在运行此语句块。</span><span class="sxs-lookup"><span data-stu-id="c7079-175">Otherwise, the statement block runs.</span></span>  
  
 <span data-ttu-id="c7079-176">每次 Visual Basic 遇到`Next`语句，都将增大`counter`通过`step`并返回到`For`语句。</span><span class="sxs-lookup"><span data-stu-id="c7079-176">Each time Visual Basic encounters the `Next` statement, it increments `counter` by `step` and returns to the `For` statement.</span></span> <span data-ttu-id="c7079-177">它将再次比较`counter`到`end`，并再次运行块或者退出循环，具体取决于结果。</span><span class="sxs-lookup"><span data-stu-id="c7079-177">Again it compares `counter` to `end`, and again it either runs the block or exits the loop, depending on the result.</span></span> <span data-ttu-id="c7079-178">此过程将继续，直至`counter`传递`end`或`Exit For`遇到语句。</span><span class="sxs-lookup"><span data-stu-id="c7079-178">This process continues until `counter` passes `end` or an `Exit For` statement is encountered.</span></span>  
  
 <span data-ttu-id="c7079-179">循环不会阻止直到`counter`经过`end`。</span><span class="sxs-lookup"><span data-stu-id="c7079-179">The loop doesn't stop until `counter` has passed `end`.</span></span> <span data-ttu-id="c7079-180">如果`counter`等同于`end`，循环继续。</span><span class="sxs-lookup"><span data-stu-id="c7079-180">If `counter` is equal to `end`, the loop continues.</span></span> <span data-ttu-id="c7079-181">确定是否运行块的比较是`counter`  <=  `end`如果`step`为正和`counter`  >=  `end`如果`step`为负。</span><span class="sxs-lookup"><span data-stu-id="c7079-181">The comparison that determines whether to run the block is `counter` <= `end` if `step` is positive and `counter` >= `end` if `step` is negative.</span></span>  
  
 <span data-ttu-id="c7079-182">如果你更改的值`counter`循环内, 你的代码可能会更难读取和调试。</span><span class="sxs-lookup"><span data-stu-id="c7079-182">If you change the value of `counter` while inside a loop, your code might be more difficult to read and debug.</span></span> <span data-ttu-id="c7079-183">更改的值`start`， `end`，或`step`不会影响已确定第一次键入循环的迭代值。</span><span class="sxs-lookup"><span data-stu-id="c7079-183">Changing the value of `start`, `end`, or `step` doesn't affect the iteration values that were determined when the loop was first entered.</span></span>  
  
 <span data-ttu-id="c7079-184">如果嵌套循环，编译器将发出错误信号它是否会遇到`Next`语句之前外部嵌套级别`Next`内部级别的语句。</span><span class="sxs-lookup"><span data-stu-id="c7079-184">If you nest loops, the compiler signals an error if it encounters the `Next` statement of an outer nesting level before the `Next` statement of an inner level.</span></span> <span data-ttu-id="c7079-185">但是，编译器可以检测到这只有在指定重叠错误`counter`中每个`Next`语句。</span><span class="sxs-lookup"><span data-stu-id="c7079-185">However, the compiler can detect this overlapping error only if you specify `counter` in every `Next` statement.</span></span>  
  
### <a name="step-argument"></a><span data-ttu-id="c7079-186">步骤参数</span><span class="sxs-lookup"><span data-stu-id="c7079-186">Step Argument</span></span>  
 <span data-ttu-id="c7079-187">值`step`可以是正数或负数。</span><span class="sxs-lookup"><span data-stu-id="c7079-187">The value of `step` can be either positive or negative.</span></span> <span data-ttu-id="c7079-188">此参数确定循环处理根据下表：</span><span class="sxs-lookup"><span data-stu-id="c7079-188">This parameter determines loop processing according to the following table:</span></span>  
  
|<span data-ttu-id="c7079-189">**步长值**</span><span class="sxs-lookup"><span data-stu-id="c7079-189">**Step value**</span></span>|<span data-ttu-id="c7079-190">**循环执行的条件**</span><span class="sxs-lookup"><span data-stu-id="c7079-190">**Loop executes if**</span></span>|  
|--------------------|--------------------------|  
|<span data-ttu-id="c7079-191">正或零</span><span class="sxs-lookup"><span data-stu-id="c7079-191">Positive or zero</span></span>|`counter` <= `end`|  
|<span data-ttu-id="c7079-192">负数</span><span class="sxs-lookup"><span data-stu-id="c7079-192">Negative</span></span>|`counter` >= `end`|  
  
 <span data-ttu-id="c7079-193">默认值`step`为 1。</span><span class="sxs-lookup"><span data-stu-id="c7079-193">The default value of `step` is 1.</span></span>  
  
###  <a name="BKMK_Counter"></a><span data-ttu-id="c7079-194">计数器自变量</span><span class="sxs-lookup"><span data-stu-id="c7079-194">Counter Argument</span></span>  
 <span data-ttu-id="c7079-195">下表指示是否`counter`定义新的本地变量为作用域为整个`For…Next`循环。</span><span class="sxs-lookup"><span data-stu-id="c7079-195">The following table indicates whether `counter` defines a new local variable that’s scoped to the entire `For…Next` loop.</span></span> <span data-ttu-id="c7079-196">此决定取决于是否`datatype`存在以及是否`counter`已定义。</span><span class="sxs-lookup"><span data-stu-id="c7079-196">This determination depends on whether `datatype` is present and whether `counter` is already defined.</span></span>  
  
|<span data-ttu-id="c7079-197">是`datatype`存在？</span><span class="sxs-lookup"><span data-stu-id="c7079-197">Is `datatype` present?</span></span>|<span data-ttu-id="c7079-198">是`counter`已定义？</span><span class="sxs-lookup"><span data-stu-id="c7079-198">Is `counter` already defined?</span></span>|<span data-ttu-id="c7079-199">结果 (是否`counter`定义新的本地变量为作用域为整个`For...Next`循环)</span><span class="sxs-lookup"><span data-stu-id="c7079-199">Result (whether `counter` defines a new local variable that’s scoped to the entire `For...Next` loop)</span></span>|  
|----------------------------|-----------------------------------|-------------------------------------------------------------------------------------------------------------|  
|<span data-ttu-id="c7079-200">No</span><span class="sxs-lookup"><span data-stu-id="c7079-200">No</span></span>|<span data-ttu-id="c7079-201">是</span><span class="sxs-lookup"><span data-stu-id="c7079-201">Yes</span></span>|<span data-ttu-id="c7079-202">否，因为`counter`已定义。</span><span class="sxs-lookup"><span data-stu-id="c7079-202">No, because `counter` is already defined.</span></span> <span data-ttu-id="c7079-203">如果的作用域`counter`不在本地进行过程： 出现编译时警告。</span><span class="sxs-lookup"><span data-stu-id="c7079-203">If the scope of `counter` isn't local to the procedure, a compile-time warning occurs.</span></span>|  
|<span data-ttu-id="c7079-204">No</span><span class="sxs-lookup"><span data-stu-id="c7079-204">No</span></span>|<span data-ttu-id="c7079-205">No</span><span class="sxs-lookup"><span data-stu-id="c7079-205">No</span></span>|<span data-ttu-id="c7079-206">可以。</span><span class="sxs-lookup"><span data-stu-id="c7079-206">Yes.</span></span> <span data-ttu-id="c7079-207">数据类型，则从推断`start`， `end`，和`step`表达式。</span><span class="sxs-lookup"><span data-stu-id="c7079-207">The data type is inferred from the `start`, `end`, and `step` expressions.</span></span> <span data-ttu-id="c7079-208">类型推理有关的信息，请参阅[Option Infer 语句](../../../visual-basic/language-reference/statements/option-infer-statement.md)和[本地类型推理](../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md)。</span><span class="sxs-lookup"><span data-stu-id="c7079-208">For information about type inference, see [Option Infer Statement](../../../visual-basic/language-reference/statements/option-infer-statement.md) and [Local Type Inference](../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md).</span></span>|  
|<span data-ttu-id="c7079-209">是</span><span class="sxs-lookup"><span data-stu-id="c7079-209">Yes</span></span>|<span data-ttu-id="c7079-210">是</span><span class="sxs-lookup"><span data-stu-id="c7079-210">Yes</span></span>|<span data-ttu-id="c7079-211">是，但仅当现有`counter`外部过程定义变量。</span><span class="sxs-lookup"><span data-stu-id="c7079-211">Yes, but only if the existing `counter` variable is defined outside the procedure.</span></span> <span data-ttu-id="c7079-212">该变量保持独立。</span><span class="sxs-lookup"><span data-stu-id="c7079-212">That variable remains separate.</span></span> <span data-ttu-id="c7079-213">如果现有的作用域`counter`变量是本地的过程，则发生编译时错误。</span><span class="sxs-lookup"><span data-stu-id="c7079-213">If the scope of the existing `counter` variable is local to the procedure, a compile-time error occurs.</span></span>|  
|<span data-ttu-id="c7079-214">是</span><span class="sxs-lookup"><span data-stu-id="c7079-214">Yes</span></span>|<span data-ttu-id="c7079-215">No</span><span class="sxs-lookup"><span data-stu-id="c7079-215">No</span></span>|<span data-ttu-id="c7079-216">可以。</span><span class="sxs-lookup"><span data-stu-id="c7079-216">Yes.</span></span>|  
  
 <span data-ttu-id="c7079-217">数据类型`counter`确定的一种迭代中，它必须是以下类型之一：</span><span class="sxs-lookup"><span data-stu-id="c7079-217">The data type of `counter` determines the type of the iteration, which must be one of the following types:</span></span>  
  
-   <span data-ttu-id="c7079-218">A `Byte`， `SByte`， `UShort`， `Short`， `UInteger`， `Integer`， `ULong`， `Long`， `Decimal`， `Single`，或`Double`。</span><span class="sxs-lookup"><span data-stu-id="c7079-218">A `Byte`, `SByte`, `UShort`, `Short`, `UInteger`, `Integer`, `ULong`, `Long`, `Decimal`, `Single`, or `Double`.</span></span>  
  
-   <span data-ttu-id="c7079-219">可使用声明的枚举[Enum 语句](../../../visual-basic/language-reference/statements/enum-statement.md)。</span><span class="sxs-lookup"><span data-stu-id="c7079-219">An enumeration that you declare by using an [Enum Statement](../../../visual-basic/language-reference/statements/enum-statement.md).</span></span>  
  
-   <span data-ttu-id="c7079-220">一个 `Object`。</span><span class="sxs-lookup"><span data-stu-id="c7079-220">An `Object`.</span></span>  
  
-   <span data-ttu-id="c7079-221">一种类型`T`具有以下运算符，其中`B`是一种可在`Boolean`表达式。</span><span class="sxs-lookup"><span data-stu-id="c7079-221">A type `T` that has the following operators, where `B` is a type that can be used in a `Boolean` expression.</span></span>  
  
     `Public Shared Operator >= (op1 As T, op2 As T) As B`  
  
     `Public Shared Operator <= (op1 As T, op2 As T) As B`  
  
     `Public Shared Operator - (op1 As T, op2 As T) As T`  
  
     `Public Shared Operator + (op1 As T, op2 As T) As T`  
  
 <span data-ttu-id="c7079-222">你可以选择指定`counter`变量中`Next`语句。</span><span class="sxs-lookup"><span data-stu-id="c7079-222">You can optionally specify the `counter` variable in the `Next` statement.</span></span> <span data-ttu-id="c7079-223">此语法提高您的程序的可读性，尤其是在具有嵌套`For`循环。</span><span class="sxs-lookup"><span data-stu-id="c7079-223">This syntax improves the readability of your program, especially if you have nested `For` loops.</span></span> <span data-ttu-id="c7079-224">必须在相应指定出现的变量`For`语句。</span><span class="sxs-lookup"><span data-stu-id="c7079-224">You must specify the variable that appears in the corresponding `For` statement.</span></span>  
  
 <span data-ttu-id="c7079-225">`start`， `end`，和`step`表达式可以计算为任何数据类型扩大到的一种`counter`。</span><span class="sxs-lookup"><span data-stu-id="c7079-225">The `start`, `end`, and `step` expressions can evaluate to any data type that widens to the type of `counter`.</span></span> <span data-ttu-id="c7079-226">如果你使用的用户定义类型`counter`，可能需要定义`CType`转换运算符以转换的类型`start`， `end`，或`step`为的类型`counter`。</span><span class="sxs-lookup"><span data-stu-id="c7079-226">If you use a user-defined type for `counter`, you might have to define the `CType` conversion operator to convert the types of `start`, `end`, or `step` to the type of `counter`.</span></span>  
  
## <a name="example"></a><span data-ttu-id="c7079-227">示例</span><span class="sxs-lookup"><span data-stu-id="c7079-227">Example</span></span>  
 <span data-ttu-id="c7079-228">下面的示例从泛型列表中移除所有元素。</span><span class="sxs-lookup"><span data-stu-id="c7079-228">The following example removes all elements from a generic list.</span></span> <span data-ttu-id="c7079-229">而不是[每个...下一条语句](../../../visual-basic/language-reference/statements/for-each-next-statement.md)的示例所示`For`...`Next`循环以降序顺序的语句。</span><span class="sxs-lookup"><span data-stu-id="c7079-229">Instead of a [For Each...Next Statement](../../../visual-basic/language-reference/statements/for-each-next-statement.md), the example shows a `For`...`Next` statement that iterates in descending order.</span></span> <span data-ttu-id="c7079-230">该示例使用此技术，因为`removeAt`方法将导致触发 after 已删除的元素具有较低的索引值的元素。</span><span class="sxs-lookup"><span data-stu-id="c7079-230">The example uses this technique because the `removeAt` method causes elements after the removed element to have a lower index value.</span></span>  
  
 [!code-vb[VbVbalrStatements#114](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/for-next-statement_5.vb)]  
  
## <a name="example"></a><span data-ttu-id="c7079-231">示例</span><span class="sxs-lookup"><span data-stu-id="c7079-231">Example</span></span>  
 <span data-ttu-id="c7079-232">下面的示例循环访问一个枚举，通过使用声明[Enum 语句](../../../visual-basic/language-reference/statements/enum-statement.md)。</span><span class="sxs-lookup"><span data-stu-id="c7079-232">The following example iterates through an enumeration that's declared by using an [Enum Statement](../../../visual-basic/language-reference/statements/enum-statement.md).</span></span>  
  
 [!code-vb[VbVbalrStatements#116](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/for-next-statement_6.vb)]  
  
## <a name="example"></a><span data-ttu-id="c7079-233">示例</span><span class="sxs-lookup"><span data-stu-id="c7079-233">Example</span></span>  
 <span data-ttu-id="c7079-234">在下面的示例中，语句参数使用具有运算符重载的类`+`， `-`， `>=`，和`<=`运算符。</span><span class="sxs-lookup"><span data-stu-id="c7079-234">In the following example, the statement parameters use a class that has operator overloads for the `+`, `-`, `>=`, and `<=` operators.</span></span>  
  
 [!code-vb[VbVbalrStatements#117](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/for-next-statement_7.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="c7079-235">另请参阅</span><span class="sxs-lookup"><span data-stu-id="c7079-235">See Also</span></span>  
 <xref:System.Collections.Generic.List%601>  
 [<span data-ttu-id="c7079-236">循环结构</span><span class="sxs-lookup"><span data-stu-id="c7079-236">Loop Structures</span></span>](../../../visual-basic/programming-guide/language-features/control-flow/loop-structures.md)  
 [<span data-ttu-id="c7079-237">While...End While 语句</span><span class="sxs-lookup"><span data-stu-id="c7079-237">While...End While Statement</span></span>](../../../visual-basic/language-reference/statements/while-end-while-statement.md)  
 [<span data-ttu-id="c7079-238">Do...Loop 语句</span><span class="sxs-lookup"><span data-stu-id="c7079-238">Do...Loop Statement</span></span>](../../../visual-basic/language-reference/statements/do-loop-statement.md)  
 [<span data-ttu-id="c7079-239">嵌套的控件结构</span><span class="sxs-lookup"><span data-stu-id="c7079-239">Nested Control Structures</span></span>](../../../visual-basic/programming-guide/language-features/control-flow/nested-control-structures.md)  
 [<span data-ttu-id="c7079-240">Exit 语句</span><span class="sxs-lookup"><span data-stu-id="c7079-240">Exit Statement</span></span>](../../../visual-basic/language-reference/statements/exit-statement.md)  
 [<span data-ttu-id="c7079-241">集合</span><span class="sxs-lookup"><span data-stu-id="c7079-241">Collections</span></span>](http://msdn.microsoft.com/library/e76533a9-5033-4a0b-b003-9c2be60d185b)
