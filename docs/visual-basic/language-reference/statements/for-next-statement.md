---
title: For...Next 语句 (Visual Basic)
ms.date: 07/20/2015
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
ms.openlocfilehash: 5d47d57b75005d5c13dbf8633981dfb2d57d3e90
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/18/2019
ms.locfileid: "58826322"
---
# <a name="fornext-statement-visual-basic"></a><span data-ttu-id="d88fe-102">For...Next 语句 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="d88fe-102">For...Next Statement (Visual Basic)</span></span>
<span data-ttu-id="d88fe-103">将一组语句重复指定的次数。</span><span class="sxs-lookup"><span data-stu-id="d88fe-103">Repeats a group of statements a specified number of times.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d88fe-104">语法</span><span class="sxs-lookup"><span data-stu-id="d88fe-104">Syntax</span></span>  
  
```  
For counter [ As datatype ] = start To end [ Step step ]  
    [ statements ]  
    [ Continue For ]  
    [ statements ]  
    [ Exit For ]  
    [ statements ]  
Next [ counter ]  
```  
  
## <a name="parts"></a><span data-ttu-id="d88fe-105">部件</span><span class="sxs-lookup"><span data-stu-id="d88fe-105">Parts</span></span>  
  
|<span data-ttu-id="d88fe-106">部件</span><span class="sxs-lookup"><span data-stu-id="d88fe-106">Part</span></span>|<span data-ttu-id="d88fe-107">描述</span><span class="sxs-lookup"><span data-stu-id="d88fe-107">Description</span></span>|  
|----------|-----------------|  
|`counter`|<span data-ttu-id="d88fe-108">在所需`For`语句。</span><span class="sxs-lookup"><span data-stu-id="d88fe-108">Required in the `For` statement.</span></span> <span data-ttu-id="d88fe-109">数值变量。</span><span class="sxs-lookup"><span data-stu-id="d88fe-109">Numeric variable.</span></span> <span data-ttu-id="d88fe-110">For 循环控制变量。</span><span class="sxs-lookup"><span data-stu-id="d88fe-110">The control variable for the loop.</span></span> <span data-ttu-id="d88fe-111">有关详细信息，请参阅[计数器参数](#BKMK_Counter)本主题中更高版本。</span><span class="sxs-lookup"><span data-stu-id="d88fe-111">For more information, see [Counter Argument](#BKMK_Counter) later in this topic.</span></span>|  
|`datatype`|<span data-ttu-id="d88fe-112">可选。</span><span class="sxs-lookup"><span data-stu-id="d88fe-112">Optional.</span></span> <span data-ttu-id="d88fe-113">数据类型的`counter`。</span><span class="sxs-lookup"><span data-stu-id="d88fe-113">Data type of `counter`.</span></span> <span data-ttu-id="d88fe-114">有关详细信息，请参阅[计数器参数](#BKMK_Counter)本主题中更高版本。</span><span class="sxs-lookup"><span data-stu-id="d88fe-114">For more information, see [Counter Argument](#BKMK_Counter) later in this topic.</span></span>|  
|`start`|<span data-ttu-id="d88fe-115">必需。</span><span class="sxs-lookup"><span data-stu-id="d88fe-115">Required.</span></span> <span data-ttu-id="d88fe-116">数值表达式。</span><span class="sxs-lookup"><span data-stu-id="d88fe-116">Numeric expression.</span></span> <span data-ttu-id="d88fe-117">`counter` 的初始值。</span><span class="sxs-lookup"><span data-stu-id="d88fe-117">The initial value of `counter`.</span></span>|  
|`end`|<span data-ttu-id="d88fe-118">必需。</span><span class="sxs-lookup"><span data-stu-id="d88fe-118">Required.</span></span> <span data-ttu-id="d88fe-119">数值表达式。</span><span class="sxs-lookup"><span data-stu-id="d88fe-119">Numeric expression.</span></span> <span data-ttu-id="d88fe-120">最终值`counter`。</span><span class="sxs-lookup"><span data-stu-id="d88fe-120">The final value of `counter`.</span></span>|  
|`step`|<span data-ttu-id="d88fe-121">可选。</span><span class="sxs-lookup"><span data-stu-id="d88fe-121">Optional.</span></span> <span data-ttu-id="d88fe-122">数值表达式。</span><span class="sxs-lookup"><span data-stu-id="d88fe-122">Numeric expression.</span></span> <span data-ttu-id="d88fe-123">所根据的数量`counter`循环每次都会递增。</span><span class="sxs-lookup"><span data-stu-id="d88fe-123">The amount by which `counter` is incremented each time through the loop.</span></span>|  
|`statements`|<span data-ttu-id="d88fe-124">可选。</span><span class="sxs-lookup"><span data-stu-id="d88fe-124">Optional.</span></span> <span data-ttu-id="d88fe-125">一个或多个语句之间`For`和`Next`运行指定的次数。</span><span class="sxs-lookup"><span data-stu-id="d88fe-125">One or more statements between `For` and `Next` that run the specified number of times.</span></span>|  
|`Continue For`|<span data-ttu-id="d88fe-126">可选。</span><span class="sxs-lookup"><span data-stu-id="d88fe-126">Optional.</span></span> <span data-ttu-id="d88fe-127">将控制转移到下一步的循环迭代。</span><span class="sxs-lookup"><span data-stu-id="d88fe-127">Transfers control to the next loop iteration.</span></span>|  
|`Exit For`|<span data-ttu-id="d88fe-128">可选。</span><span class="sxs-lookup"><span data-stu-id="d88fe-128">Optional.</span></span> <span data-ttu-id="d88fe-129">将控制的转移`For`循环。</span><span class="sxs-lookup"><span data-stu-id="d88fe-129">Transfers control out of the `For` loop.</span></span>|  
|`Next`|<span data-ttu-id="d88fe-130">必需。</span><span class="sxs-lookup"><span data-stu-id="d88fe-130">Required.</span></span> <span data-ttu-id="d88fe-131">终止的定义`For`循环。</span><span class="sxs-lookup"><span data-stu-id="d88fe-131">Terminates the definition of the `For` loop.</span></span>|  
  
> [!NOTE]
>  <span data-ttu-id="d88fe-132">`To`关键字用于在此语句中指定计数器的范围。</span><span class="sxs-lookup"><span data-stu-id="d88fe-132">The `To` keyword is used in this statement to specify the range for the counter.</span></span> <span data-ttu-id="d88fe-133">您还可以使用此关键字在[选择...Case 语句](../../../visual-basic/language-reference/statements/select-case-statement.md)和数组声明中。</span><span class="sxs-lookup"><span data-stu-id="d88fe-133">You can also use this keyword in the [Select...Case Statement](../../../visual-basic/language-reference/statements/select-case-statement.md) and in array declarations.</span></span> <span data-ttu-id="d88fe-134">有关数组声明的详细信息，请参阅[Dim 语句](../../../visual-basic/language-reference/statements/dim-statement.md)。</span><span class="sxs-lookup"><span data-stu-id="d88fe-134">For more information about array declarations, see [Dim Statement](../../../visual-basic/language-reference/statements/dim-statement.md).</span></span>  
  
## <a name="simple-examples"></a><span data-ttu-id="d88fe-135">简单的示例</span><span class="sxs-lookup"><span data-stu-id="d88fe-135">Simple Examples</span></span>  
 <span data-ttu-id="d88fe-136">您使用`For`...`Next`结构，当你想要重复次数的一组语句。</span><span class="sxs-lookup"><span data-stu-id="d88fe-136">You use a `For`...`Next` structure when you want to repeat a set of statements a set number of times.</span></span>  
  
 <span data-ttu-id="d88fe-137">在以下示例中，`index`变量开头的值为 1，并会在循环结束后的值的每次迭代时递增`index`达到 5。</span><span class="sxs-lookup"><span data-stu-id="d88fe-137">In the following example, the `index` variable starts with a value of 1 and is incremented with each iteration of the loop, ending after the value of `index` reaches 5.</span></span>  
  
 [!code-vb[VbVbalrStatements#111](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class7.vb#111)]  
  
 <span data-ttu-id="d88fe-138">在以下示例中，`number`变量从 2 开始，将降低在循环结束后的值的每次迭代 0.25`number`达到 0。</span><span class="sxs-lookup"><span data-stu-id="d88fe-138">In the following example, the `number` variable starts at 2 and is reduced by 0.25 on each iteration of the loop, ending after the value of `number` reaches 0.</span></span> <span data-ttu-id="d88fe-139">`Step`自变量的`-.25`降低 0.25 循环的每个迭代上的值。</span><span class="sxs-lookup"><span data-stu-id="d88fe-139">The `Step` argument of `-.25` reduces the value by 0.25 on each iteration of the loop.</span></span>  
  
 [!code-vb[VbVbalrStatements#112](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class7.vb#112)]  
  
> [!TIP]
>  <span data-ttu-id="d88fe-140">一个[时...While 语句结束](../../../visual-basic/language-reference/statements/while-end-while-statement.md)或[执行操作...循环语句](../../../visual-basic/language-reference/statements/do-loop-statement.md)正常时你事先不知道在多少次循环中运行这些语句。</span><span class="sxs-lookup"><span data-stu-id="d88fe-140">A [While...End While Statement](../../../visual-basic/language-reference/statements/while-end-while-statement.md) or [Do...Loop Statement](../../../visual-basic/language-reference/statements/do-loop-statement.md) works well when you don't know in advance how many times to run the statements in the loop.</span></span> <span data-ttu-id="d88fe-141">但是，如果您希望运行特定次数的循环`For`...`Next`循环是更好的选择。</span><span class="sxs-lookup"><span data-stu-id="d88fe-141">However, when you expect to run the loop a specific number of times, a `For`...`Next` loop is a better choice.</span></span> <span data-ttu-id="d88fe-142">当您首次进入循环时确定迭代的次数。</span><span class="sxs-lookup"><span data-stu-id="d88fe-142">You determine the number of iterations when you first enter the loop.</span></span>  
  
## <a name="nesting-loops"></a><span data-ttu-id="d88fe-143">嵌套循环</span><span class="sxs-lookup"><span data-stu-id="d88fe-143">Nesting Loops</span></span>  
 <span data-ttu-id="d88fe-144">可以嵌套`For`放置另一个循环内的循环。</span><span class="sxs-lookup"><span data-stu-id="d88fe-144">You can nest `For` loops by putting one loop within another.</span></span> <span data-ttu-id="d88fe-145">下面的示例演示嵌套`For`...`Next`具有不同的步骤值的结构。</span><span class="sxs-lookup"><span data-stu-id="d88fe-145">The following example demonstrates nested `For`...`Next` structures that have different step values.</span></span> <span data-ttu-id="d88fe-146">外部循环创建循环每次迭代的字符串。</span><span class="sxs-lookup"><span data-stu-id="d88fe-146">The outer loop creates a string for every iteration of the loop.</span></span> <span data-ttu-id="d88fe-147">内部循环减小该循环每次迭代的循环计数器变量。</span><span class="sxs-lookup"><span data-stu-id="d88fe-147">The inner loop decrements a loop counter variable for every iteration of the loop.</span></span>  
  
 [!code-vb[VbVbalrStatements#113](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class7.vb#113)]  
  
 <span data-ttu-id="d88fe-148">当嵌套循环，每个循环必须具有一个唯一`counter`变量。</span><span class="sxs-lookup"><span data-stu-id="d88fe-148">When nesting loops, each loop must have a unique `counter` variable.</span></span>  
  
 <span data-ttu-id="d88fe-149">此外可以嵌套不同类型中每个其他控制结构。</span><span class="sxs-lookup"><span data-stu-id="d88fe-149">You can also nest different kinds control structures within each other.</span></span> <span data-ttu-id="d88fe-150">有关详细信息，请参阅[嵌套控制结构](../../../visual-basic/programming-guide/language-features/control-flow/nested-control-structures.md)。</span><span class="sxs-lookup"><span data-stu-id="d88fe-150">For more information, see [Nested Control Structures](../../../visual-basic/programming-guide/language-features/control-flow/nested-control-structures.md).</span></span>  
  
## <a name="exit-for-and-continue-for"></a><span data-ttu-id="d88fe-151">有关退出并继续</span><span class="sxs-lookup"><span data-stu-id="d88fe-151">Exit For and Continue For</span></span>  
 <span data-ttu-id="d88fe-152">`Exit For`语句立即退出`For`...`Next`</span><span class="sxs-lookup"><span data-stu-id="d88fe-152">The `Exit For` statement immediately exits the `For`…`Next`</span></span> <span data-ttu-id="d88fe-153">到后面的语句的循环，并将控制权`Next`语句。</span><span class="sxs-lookup"><span data-stu-id="d88fe-153">loop and transfers control to the statement that follows the `Next` statement.</span></span>  
  
 <span data-ttu-id="d88fe-154">`Continue For`语句控制将立即转移到循环的下一个迭代。</span><span class="sxs-lookup"><span data-stu-id="d88fe-154">The `Continue For` statement transfers control immediately to the next iteration of the loop.</span></span> <span data-ttu-id="d88fe-155">有关详细信息，请参阅[Continue 语句](../../../visual-basic/language-reference/statements/continue-statement.md)。</span><span class="sxs-lookup"><span data-stu-id="d88fe-155">For more information, see [Continue Statement](../../../visual-basic/language-reference/statements/continue-statement.md).</span></span>  
  
 <span data-ttu-id="d88fe-156">下面的示例演示如何使用`Continue For`和`Exit For`语句。</span><span class="sxs-lookup"><span data-stu-id="d88fe-156">The following example illustrates the use of the `Continue For` and `Exit For` statements.</span></span>  
  
 [!code-vb[VbVbalrStatements#115](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class7.vb#115)]  
  
 <span data-ttu-id="d88fe-157">可以将任意数量的`Exit For`中的语句`For`...`Next`</span><span class="sxs-lookup"><span data-stu-id="d88fe-157">You can put any number of `Exit For` statements in a `For`…`Next`</span></span> <span data-ttu-id="d88fe-158">循环。</span><span class="sxs-lookup"><span data-stu-id="d88fe-158">loop.</span></span> <span data-ttu-id="d88fe-159">当使用内嵌套`For`...`Next`</span><span class="sxs-lookup"><span data-stu-id="d88fe-159">When used within nested `For`…`Next`</span></span> <span data-ttu-id="d88fe-160">循环、`Exit For`退出最里面的循环，并将控制转移到下一个较高级别的嵌套。</span><span class="sxs-lookup"><span data-stu-id="d88fe-160">loops, `Exit For` exits the innermost loop and transfers control to the next higher level of nesting.</span></span>  
  
 <span data-ttu-id="d88fe-161">`Exit For` 通常使用后评估某些条件 (例如，在`If`...`Then`...`Else`结构)。</span><span class="sxs-lookup"><span data-stu-id="d88fe-161">`Exit For` is often used after you evaluate some condition (for example, in an `If`...`Then`...`Else` structure).</span></span> <span data-ttu-id="d88fe-162">您可能想要使用`Exit For`满足以下条件：</span><span class="sxs-lookup"><span data-stu-id="d88fe-162">You might want to use `Exit For` for the following conditions:</span></span>  
  
-   <span data-ttu-id="d88fe-163">继续循环访问是不必要或不可能。</span><span class="sxs-lookup"><span data-stu-id="d88fe-163">Continuing to iterate is unnecessary or impossible.</span></span> <span data-ttu-id="d88fe-164">错误的值或终止请求可能会创建这种情况。</span><span class="sxs-lookup"><span data-stu-id="d88fe-164">An erroneous value or a termination request might create this condition.</span></span>  
  
-   <span data-ttu-id="d88fe-165">一个`Try`...`Catch`...`Finally`语句捕获异常。</span><span class="sxs-lookup"><span data-stu-id="d88fe-165">A `Try`...`Catch`...`Finally` statement catches an exception.</span></span> <span data-ttu-id="d88fe-166">可以使用`Exit For`末尾的`Finally`块。</span><span class="sxs-lookup"><span data-stu-id="d88fe-166">You might use `Exit For` at the end of the `Finally` block.</span></span>  
  
-   <span data-ttu-id="d88fe-167">具有无限循环，这是一个循环，无法运行大型或甚至无限数量的次数。</span><span class="sxs-lookup"><span data-stu-id="d88fe-167">You have an endless loop, which is a loop that could run a large or even infinite number of times.</span></span> <span data-ttu-id="d88fe-168">如果检测到此类情况，可以使用`Exit For`来退出循环。</span><span class="sxs-lookup"><span data-stu-id="d88fe-168">If you detect such a condition, you can use `Exit For` to escape the loop.</span></span> <span data-ttu-id="d88fe-169">有关详细信息，请参阅[执行操作...循环语句](../../../visual-basic/language-reference/statements/do-loop-statement.md)。</span><span class="sxs-lookup"><span data-stu-id="d88fe-169">For more information, see [Do...Loop Statement](../../../visual-basic/language-reference/statements/do-loop-statement.md).</span></span>  
  
## <a name="technical-implementation"></a><span data-ttu-id="d88fe-170">技术实现</span><span class="sxs-lookup"><span data-stu-id="d88fe-170">Technical Implementation</span></span>  
 <span data-ttu-id="d88fe-171">当`For`...`Next`循环开始，Visual Basic 的计算结果`start`， `end`，和`step`。</span><span class="sxs-lookup"><span data-stu-id="d88fe-171">When a `For`...`Next` loop starts, Visual Basic evaluates `start`, `end`, and `step`.</span></span> <span data-ttu-id="d88fe-172">Visual Basic 仅在此时间，然后将计算这些值`start`到`counter`。</span><span class="sxs-lookup"><span data-stu-id="d88fe-172">Visual Basic evaluates these values only at this time and then assigns `start` to `counter`.</span></span> <span data-ttu-id="d88fe-173">在之前的语句块将运行，Visual Basic 进行比较`counter`到`end`。</span><span class="sxs-lookup"><span data-stu-id="d88fe-173">Before the statement block runs, Visual Basic compares `counter` to `end`.</span></span> <span data-ttu-id="d88fe-174">如果`counter`已经是大于`end`值 (或较小的 if`step`为负)，则`For`循环结束并将控制权传递到后面的语句`Next`语句。</span><span class="sxs-lookup"><span data-stu-id="d88fe-174">If `counter` is already larger than the `end` value (or smaller if `step` is negative), the `For` loop ends and control passes to the statement that follows the `Next` statement.</span></span> <span data-ttu-id="d88fe-175">否则，在运行语句块。</span><span class="sxs-lookup"><span data-stu-id="d88fe-175">Otherwise, the statement block runs.</span></span>  
  
 <span data-ttu-id="d88fe-176">每次 Visual Basic 遇到`Next`语句，则会递增`counter`通过`step`，并返回到`For`语句。</span><span class="sxs-lookup"><span data-stu-id="d88fe-176">Each time Visual Basic encounters the `Next` statement, it increments `counter` by `step` and returns to the `For` statement.</span></span> <span data-ttu-id="d88fe-177">再次进行比较`counter`到`end`，并再次运行块或者退出循环，具体取决于结果。</span><span class="sxs-lookup"><span data-stu-id="d88fe-177">Again it compares `counter` to `end`, and again it either runs the block or exits the loop, depending on the result.</span></span> <span data-ttu-id="d88fe-178">此过程将继续，直至`counter`传递`end`或`Exit For`遇到语句。</span><span class="sxs-lookup"><span data-stu-id="d88fe-178">This process continues until `counter` passes `end` or an `Exit For` statement is encountered.</span></span>  
  
 <span data-ttu-id="d88fe-179">循环不会阻止直到`counter`已通过`end`。</span><span class="sxs-lookup"><span data-stu-id="d88fe-179">The loop doesn't stop until `counter` has passed `end`.</span></span> <span data-ttu-id="d88fe-180">如果`counter`等同于`end`，循环继续。</span><span class="sxs-lookup"><span data-stu-id="d88fe-180">If `counter` is equal to `end`, the loop continues.</span></span> <span data-ttu-id="d88fe-181">确定是否运行的块的比较`counter`  <=  `end`如果`step`为正并`counter`  >=  `end`如果`step`为负。</span><span class="sxs-lookup"><span data-stu-id="d88fe-181">The comparison that determines whether to run the block is `counter` <= `end` if `step` is positive and `counter` >= `end` if `step` is negative.</span></span>  
  
 <span data-ttu-id="d88fe-182">如果您更改的值`counter`内部循环中，你的代码可能更难以阅读和调试。</span><span class="sxs-lookup"><span data-stu-id="d88fe-182">If you change the value of `counter` while inside a loop, your code might be more difficult to read and debug.</span></span> <span data-ttu-id="d88fe-183">更改的值`start`， `end`，或`step`不会影响已确定时首次进入循环的迭代值。</span><span class="sxs-lookup"><span data-stu-id="d88fe-183">Changing the value of `start`, `end`, or `step` doesn't affect the iteration values that were determined when the loop was first entered.</span></span>  
  
 <span data-ttu-id="d88fe-184">如果嵌套循环，编译器将发出错误信号它是否会遇到`Next`外部的嵌套级别之前, 的语句`Next`内部级别的语句。</span><span class="sxs-lookup"><span data-stu-id="d88fe-184">If you nest loops, the compiler signals an error if it encounters the `Next` statement of an outer nesting level before the `Next` statement of an inner level.</span></span> <span data-ttu-id="d88fe-185">但是，编译器可检测到这只有在指定重叠错误`counter`中每个`Next`语句。</span><span class="sxs-lookup"><span data-stu-id="d88fe-185">However, the compiler can detect this overlapping error only if you specify `counter` in every `Next` statement.</span></span>  
  
### <a name="step-argument"></a><span data-ttu-id="d88fe-186">步骤参数</span><span class="sxs-lookup"><span data-stu-id="d88fe-186">Step Argument</span></span>  
 <span data-ttu-id="d88fe-187">值`step`可以为正数或负数。</span><span class="sxs-lookup"><span data-stu-id="d88fe-187">The value of `step` can be either positive or negative.</span></span> <span data-ttu-id="d88fe-188">此参数确定循环处理根据下表：</span><span class="sxs-lookup"><span data-stu-id="d88fe-188">This parameter determines loop processing according to the following table:</span></span>  
  
|<span data-ttu-id="d88fe-189">**步长值**</span><span class="sxs-lookup"><span data-stu-id="d88fe-189">**Step value**</span></span>|<span data-ttu-id="d88fe-190">**如果，执行循环**</span><span class="sxs-lookup"><span data-stu-id="d88fe-190">**Loop executes if**</span></span>|  
|--------------------|--------------------------|  
|<span data-ttu-id="d88fe-191">正或零</span><span class="sxs-lookup"><span data-stu-id="d88fe-191">Positive or zero</span></span>|`counter` <= `end`|  
|<span data-ttu-id="d88fe-192">负数</span><span class="sxs-lookup"><span data-stu-id="d88fe-192">Negative</span></span>|`counter` >= `end`|  
  
 <span data-ttu-id="d88fe-193">默认值`step`为 1。</span><span class="sxs-lookup"><span data-stu-id="d88fe-193">The default value of `step` is 1.</span></span>  
  
### <a name="BKMK_Counter"></a> <span data-ttu-id="d88fe-194">计数器参数</span><span class="sxs-lookup"><span data-stu-id="d88fe-194">Counter Argument</span></span>  
 <span data-ttu-id="d88fe-195">下表指示是否`counter`定义新的本地变量为作用域为整个`For…Next`循环。</span><span class="sxs-lookup"><span data-stu-id="d88fe-195">The following table indicates whether `counter` defines a new local variable that’s scoped to the entire `For…Next` loop.</span></span> <span data-ttu-id="d88fe-196">此决定取决于是否`datatype`存在以及是否`counter`已定义。</span><span class="sxs-lookup"><span data-stu-id="d88fe-196">This determination depends on whether `datatype` is present and whether `counter` is already defined.</span></span>  
  
|<span data-ttu-id="d88fe-197">是`datatype`存在？</span><span class="sxs-lookup"><span data-stu-id="d88fe-197">Is `datatype` present?</span></span>|<span data-ttu-id="d88fe-198">是`counter`已定义？</span><span class="sxs-lookup"><span data-stu-id="d88fe-198">Is `counter` already defined?</span></span>|<span data-ttu-id="d88fe-199">结果 (是否`counter`定义新的本地变量为作用域为整个`For...Next`循环)</span><span class="sxs-lookup"><span data-stu-id="d88fe-199">Result (whether `counter` defines a new local variable that’s scoped to the entire `For...Next` loop)</span></span>|  
|----------------------------|-----------------------------------|-------------------------------------------------------------------------------------------------------------|  
|<span data-ttu-id="d88fe-200">否</span><span class="sxs-lookup"><span data-stu-id="d88fe-200">No</span></span>|<span data-ttu-id="d88fe-201">是</span><span class="sxs-lookup"><span data-stu-id="d88fe-201">Yes</span></span>|<span data-ttu-id="d88fe-202">不可以，因为`counter`已定义。</span><span class="sxs-lookup"><span data-stu-id="d88fe-202">No, because `counter` is already defined.</span></span> <span data-ttu-id="d88fe-203">如果范围`counter`不是本地的过程中，将出现编译时警告。</span><span class="sxs-lookup"><span data-stu-id="d88fe-203">If the scope of `counter` isn't local to the procedure, a compile-time warning occurs.</span></span>|  
|<span data-ttu-id="d88fe-204">否</span><span class="sxs-lookup"><span data-stu-id="d88fe-204">No</span></span>|<span data-ttu-id="d88fe-205">否</span><span class="sxs-lookup"><span data-stu-id="d88fe-205">No</span></span>|<span data-ttu-id="d88fe-206">可以。</span><span class="sxs-lookup"><span data-stu-id="d88fe-206">Yes.</span></span> <span data-ttu-id="d88fe-207">从推断的数据类型`start`， `end`，和`step`表达式。</span><span class="sxs-lookup"><span data-stu-id="d88fe-207">The data type is inferred from the `start`, `end`, and `step` expressions.</span></span> <span data-ttu-id="d88fe-208">有关类型推理的信息，请参阅[Option Infer 语句](../../../visual-basic/language-reference/statements/option-infer-statement.md)并[本地类型推断](../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md)。</span><span class="sxs-lookup"><span data-stu-id="d88fe-208">For information about type inference, see [Option Infer Statement](../../../visual-basic/language-reference/statements/option-infer-statement.md) and [Local Type Inference](../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md).</span></span>|  
|<span data-ttu-id="d88fe-209">是</span><span class="sxs-lookup"><span data-stu-id="d88fe-209">Yes</span></span>|<span data-ttu-id="d88fe-210">是</span><span class="sxs-lookup"><span data-stu-id="d88fe-210">Yes</span></span>|<span data-ttu-id="d88fe-211">是的但是只有当现有`counter`外部过程定义的变量。</span><span class="sxs-lookup"><span data-stu-id="d88fe-211">Yes, but only if the existing `counter` variable is defined outside the procedure.</span></span> <span data-ttu-id="d88fe-212">该变量保持独立。</span><span class="sxs-lookup"><span data-stu-id="d88fe-212">That variable remains separate.</span></span> <span data-ttu-id="d88fe-213">如果现有范围`counter`变量是本地的过程中，将发生编译时错误。</span><span class="sxs-lookup"><span data-stu-id="d88fe-213">If the scope of the existing `counter` variable is local to the procedure, a compile-time error occurs.</span></span>|  
|<span data-ttu-id="d88fe-214">是</span><span class="sxs-lookup"><span data-stu-id="d88fe-214">Yes</span></span>|<span data-ttu-id="d88fe-215">否</span><span class="sxs-lookup"><span data-stu-id="d88fe-215">No</span></span>|<span data-ttu-id="d88fe-216">可以。</span><span class="sxs-lookup"><span data-stu-id="d88fe-216">Yes.</span></span>|  
  
 <span data-ttu-id="d88fe-217">数据类型的`counter`确定的类型的迭代，它必须是以下类型之一：</span><span class="sxs-lookup"><span data-stu-id="d88fe-217">The data type of `counter` determines the type of the iteration, which must be one of the following types:</span></span>  
  
-   <span data-ttu-id="d88fe-218">一个`Byte`， `SByte`， `UShort`， `Short`， `UInteger`， `Integer`， `ULong`， `Long`， `Decimal`， `Single`，或`Double`。</span><span class="sxs-lookup"><span data-stu-id="d88fe-218">A `Byte`, `SByte`, `UShort`, `Short`, `UInteger`, `Integer`, `ULong`, `Long`, `Decimal`, `Single`, or `Double`.</span></span>  
  
-   <span data-ttu-id="d88fe-219">使用声明的枚举[Enum 语句](../../../visual-basic/language-reference/statements/enum-statement.md)。</span><span class="sxs-lookup"><span data-stu-id="d88fe-219">An enumeration that you declare by using an [Enum Statement](../../../visual-basic/language-reference/statements/enum-statement.md).</span></span>  
  
-   <span data-ttu-id="d88fe-220">一个 `Object`。</span><span class="sxs-lookup"><span data-stu-id="d88fe-220">An `Object`.</span></span>  
  
-   <span data-ttu-id="d88fe-221">一种类型`T`具有以下运算符，其中`B`是一种可在`Boolean`表达式。</span><span class="sxs-lookup"><span data-stu-id="d88fe-221">A type `T` that has the following operators, where `B` is a type that can be used in a `Boolean` expression.</span></span>  
  
     `Public Shared Operator >= (op1 As T, op2 As T) As B`  
  
     `Public Shared Operator <= (op1 As T, op2 As T) As B`  
  
     `Public Shared Operator - (op1 As T, op2 As T) As T`  
  
     `Public Shared Operator + (op1 As T, op2 As T) As T`  
  
 <span data-ttu-id="d88fe-222">您可以选择指定`counter`变量中`Next`语句。</span><span class="sxs-lookup"><span data-stu-id="d88fe-222">You can optionally specify the `counter` variable in the `Next` statement.</span></span> <span data-ttu-id="d88fe-223">此语法可提高应用程序的可读性，尤其是在具有嵌套`For`循环。</span><span class="sxs-lookup"><span data-stu-id="d88fe-223">This syntax improves the readability of your program, especially if you have nested `For` loops.</span></span> <span data-ttu-id="d88fe-224">必须指定的变量，将显示在相应`For`语句。</span><span class="sxs-lookup"><span data-stu-id="d88fe-224">You must specify the variable that appears in the corresponding `For` statement.</span></span>  
  
 <span data-ttu-id="d88fe-225">`start`， `end`，并`step`表达式可以计算为任何数据类型为的类型扩展`counter`。</span><span class="sxs-lookup"><span data-stu-id="d88fe-225">The `start`, `end`, and `step` expressions can evaluate to any data type that widens to the type of `counter`.</span></span> <span data-ttu-id="d88fe-226">如果使用的用户定义类型`counter`，可能需要定义`CType`转换运算符，以将类型的转换`start`， `end`，或`step`为的类型`counter`。</span><span class="sxs-lookup"><span data-stu-id="d88fe-226">If you use a user-defined type for `counter`, you might have to define the `CType` conversion operator to convert the types of `start`, `end`, or `step` to the type of `counter`.</span></span>  
  
## <a name="example"></a><span data-ttu-id="d88fe-227">示例</span><span class="sxs-lookup"><span data-stu-id="d88fe-227">Example</span></span>  
 <span data-ttu-id="d88fe-228">下面的示例从一个泛型列表中移除所有元素。</span><span class="sxs-lookup"><span data-stu-id="d88fe-228">The following example removes all elements from a generic list.</span></span> <span data-ttu-id="d88fe-229">而不是[为每个...下一条语句](../../../visual-basic/language-reference/statements/for-each-next-statement.md)，该示例演示了`For`...`Next`按降序顺序循环访问的语句。</span><span class="sxs-lookup"><span data-stu-id="d88fe-229">Instead of a [For Each...Next Statement](../../../visual-basic/language-reference/statements/for-each-next-statement.md), the example shows a `For`...`Next` statement that iterates in descending order.</span></span> <span data-ttu-id="d88fe-230">该示例使用此方法，因为`removeAt`方法将导致触发 after 已移除的元素具有较低的索引值的元素。</span><span class="sxs-lookup"><span data-stu-id="d88fe-230">The example uses this technique because the `removeAt` method causes elements after the removed element to have a lower index value.</span></span>  
  
 [!code-vb[VbVbalrStatements#114](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class7.vb#114)]  
  
## <a name="example"></a><span data-ttu-id="d88fe-231">示例</span><span class="sxs-lookup"><span data-stu-id="d88fe-231">Example</span></span>  
 <span data-ttu-id="d88fe-232">下面的示例循环访问使用声明的枚举[Enum 语句](../../../visual-basic/language-reference/statements/enum-statement.md)。</span><span class="sxs-lookup"><span data-stu-id="d88fe-232">The following example iterates through an enumeration that's declared by using an [Enum Statement](../../../visual-basic/language-reference/statements/enum-statement.md).</span></span>  
  
 [!code-vb[VbVbalrStatements#116](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class7.vb#116)]  
  
## <a name="example"></a><span data-ttu-id="d88fe-233">示例</span><span class="sxs-lookup"><span data-stu-id="d88fe-233">Example</span></span>  
 <span data-ttu-id="d88fe-234">在以下示例中，语句参数使用具有运算符重载的类`+`， `-`， `>=`，和`<=`运算符。</span><span class="sxs-lookup"><span data-stu-id="d88fe-234">In the following example, the statement parameters use a class that has operator overloads for the `+`, `-`, `>=`, and `<=` operators.</span></span>  
  
 [!code-vb[VbVbalrStatements#117](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class7.vb#117)]  
  
## <a name="see-also"></a><span data-ttu-id="d88fe-235">请参阅</span><span class="sxs-lookup"><span data-stu-id="d88fe-235">See also</span></span>

- <xref:System.Collections.Generic.List%601>
- [<span data-ttu-id="d88fe-236">循环结构</span><span class="sxs-lookup"><span data-stu-id="d88fe-236">Loop Structures</span></span>](../../../visual-basic/programming-guide/language-features/control-flow/loop-structures.md)
- [<span data-ttu-id="d88fe-237">While...End While 语句</span><span class="sxs-lookup"><span data-stu-id="d88fe-237">While...End While Statement</span></span>](../../../visual-basic/language-reference/statements/while-end-while-statement.md)
- [<span data-ttu-id="d88fe-238">Do...Loop 语句</span><span class="sxs-lookup"><span data-stu-id="d88fe-238">Do...Loop Statement</span></span>](../../../visual-basic/language-reference/statements/do-loop-statement.md)
- [<span data-ttu-id="d88fe-239">嵌套的控件结构</span><span class="sxs-lookup"><span data-stu-id="d88fe-239">Nested Control Structures</span></span>](../../../visual-basic/programming-guide/language-features/control-flow/nested-control-structures.md)
- [<span data-ttu-id="d88fe-240">Exit 语句</span><span class="sxs-lookup"><span data-stu-id="d88fe-240">Exit Statement</span></span>](../../../visual-basic/language-reference/statements/exit-statement.md)
- [<span data-ttu-id="d88fe-241">集合</span><span class="sxs-lookup"><span data-stu-id="d88fe-241">Collections</span></span>](../../programming-guide/concepts/collections.md)
