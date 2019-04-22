---
title: While...End While 语句 (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.While
- vb.While...EndWhile
helpviewer_keywords:
- While statement [Visual Basic], While...End While
- While statement [Visual Basic]
- While...End While statements [Visual Basic]
ms.assetid: b931d1ce-e8ed-44d8-a13d-92a4f5458a1e
ms.openlocfilehash: 00ca0ad24231128b25a988921386d6bd3265e9a0
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/18/2019
ms.locfileid: "58843703"
---
# <a name="whileend-while-statement-visual-basic"></a><span data-ttu-id="95b01-102">While...End While 语句 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="95b01-102">While...End While Statement (Visual Basic)</span></span>
<span data-ttu-id="95b01-103">只要给定的条件是运行一系列语句`True`。</span><span class="sxs-lookup"><span data-stu-id="95b01-103">Runs a series of statements as long as a given condition is `True`.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="95b01-104">语法</span><span class="sxs-lookup"><span data-stu-id="95b01-104">Syntax</span></span>  
  
```  
While condition  
    [ statements ]  
    [ Continue While ]  
    [ statements ]  
    [ Exit While ]  
    [ statements ]  
End While  
```  
  
## <a name="parts"></a><span data-ttu-id="95b01-105">部件</span><span class="sxs-lookup"><span data-stu-id="95b01-105">Parts</span></span>  
  
|<span data-ttu-id="95b01-106">术语</span><span class="sxs-lookup"><span data-stu-id="95b01-106">Term</span></span>|<span data-ttu-id="95b01-107">定义</span><span class="sxs-lookup"><span data-stu-id="95b01-107">Definition</span></span>|  
|---|---|  
|`condition`|<span data-ttu-id="95b01-108">必需。</span><span class="sxs-lookup"><span data-stu-id="95b01-108">Required.</span></span> <span data-ttu-id="95b01-109">`Boolean` 表达式。</span><span class="sxs-lookup"><span data-stu-id="95b01-109">`Boolean` expression.</span></span> <span data-ttu-id="95b01-110">如果`condition`是`Nothing`，Visual Basic 会将其视为`False`。</span><span class="sxs-lookup"><span data-stu-id="95b01-110">If `condition` is `Nothing`, Visual Basic treats it as `False`.</span></span>|  
|`statements`|<span data-ttu-id="95b01-111">可选。</span><span class="sxs-lookup"><span data-stu-id="95b01-111">Optional.</span></span> <span data-ttu-id="95b01-112">一个或多个语句之后`While`，其中每次运行`condition`是`True`。</span><span class="sxs-lookup"><span data-stu-id="95b01-112">One or more statements following `While`, which run every time `condition` is `True`.</span></span>|  
|`Continue While`|<span data-ttu-id="95b01-113">可选。</span><span class="sxs-lookup"><span data-stu-id="95b01-113">Optional.</span></span> <span data-ttu-id="95b01-114">将控制转移到的下一个迭代`While`块。</span><span class="sxs-lookup"><span data-stu-id="95b01-114">Transfers control to the next iteration of the `While` block.</span></span>|  
|`Exit While`|<span data-ttu-id="95b01-115">可选。</span><span class="sxs-lookup"><span data-stu-id="95b01-115">Optional.</span></span> <span data-ttu-id="95b01-116">将控制的转移`While`块。</span><span class="sxs-lookup"><span data-stu-id="95b01-116">Transfers control out of the `While` block.</span></span>|  
|`End While`|<span data-ttu-id="95b01-117">必需。</span><span class="sxs-lookup"><span data-stu-id="95b01-117">Required.</span></span> <span data-ttu-id="95b01-118">终止 `While` 块的定义。</span><span class="sxs-lookup"><span data-stu-id="95b01-118">Terminates the definition of the `While` block.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="95b01-119">备注</span><span class="sxs-lookup"><span data-stu-id="95b01-119">Remarks</span></span>  
 <span data-ttu-id="95b01-120">使用`While...End While`结构，当你想要重复执行一系列语句无限的次数，前提是在条件保持`True`。</span><span class="sxs-lookup"><span data-stu-id="95b01-120">Use a `While...End While` structure when you want to repeat a set of statements an indefinite number of times, as long as a condition remains `True`.</span></span> <span data-ttu-id="95b01-121">如果想要更灵活地使用测试条件以及针对什么结果进行测试，您可能倾向于[执行操作...循环语句](../../../visual-basic/language-reference/statements/do-loop-statement.md)。</span><span class="sxs-lookup"><span data-stu-id="95b01-121">If you want more flexibility with where you test the condition or what result you test it for, you might prefer the [Do...Loop Statement](../../../visual-basic/language-reference/statements/do-loop-statement.md).</span></span> <span data-ttu-id="95b01-122">如果你想要重复执行语句，一定的时间，[为...下一条语句](../../../visual-basic/language-reference/statements/for-next-statement.md)通常是更好的选择。</span><span class="sxs-lookup"><span data-stu-id="95b01-122">If you want to repeat the statements a set number of times, the [For...Next Statement](../../../visual-basic/language-reference/statements/for-next-statement.md) is usually a better choice.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="95b01-123">`While`关键字还用于[执行操作...循环语句](../../../visual-basic/language-reference/statements/do-loop-statement.md)，则[Skip While 子句](../../../visual-basic/language-reference/queries/skip-while-clause.md)并且[Take While 子句](../../../visual-basic/language-reference/queries/take-while-clause.md)。</span><span class="sxs-lookup"><span data-stu-id="95b01-123">The `While` keyword is also used in the [Do...Loop Statement](../../../visual-basic/language-reference/statements/do-loop-statement.md), the [Skip While Clause](../../../visual-basic/language-reference/queries/skip-while-clause.md) and the [Take While Clause](../../../visual-basic/language-reference/queries/take-while-clause.md).</span></span>  
  
 <span data-ttu-id="95b01-124">如果`condition`是`True`，则所有的`statements`运行，直至`End While`遇到语句。</span><span class="sxs-lookup"><span data-stu-id="95b01-124">If `condition` is `True`, all of the `statements` run until the `End While` statement is encountered.</span></span> <span data-ttu-id="95b01-125">随后控制返回到`While`语句，和`condition`再次检查。</span><span class="sxs-lookup"><span data-stu-id="95b01-125">Control then returns to the `While` statement, and `condition` is again checked.</span></span> <span data-ttu-id="95b01-126">如果`condition`仍是`True`，重复该过程。</span><span class="sxs-lookup"><span data-stu-id="95b01-126">If `condition` is still `True`, the process is repeated.</span></span> <span data-ttu-id="95b01-127">如果它具有`False`，控制将传递到后面的语句`End While`语句。</span><span class="sxs-lookup"><span data-stu-id="95b01-127">If it’s `False`, control passes to the statement that follows the `End While` statement.</span></span>  
  
 <span data-ttu-id="95b01-128">`While`语句始终检查条件，然后会启动循环。</span><span class="sxs-lookup"><span data-stu-id="95b01-128">The `While` statement always checks the condition before it starts the loop.</span></span> <span data-ttu-id="95b01-129">循环的条件的同时继续`True`。</span><span class="sxs-lookup"><span data-stu-id="95b01-129">Looping continues while the condition remains `True`.</span></span> <span data-ttu-id="95b01-130">如果`condition`是`False`时您首次进入循环，它不能甚至一次运行。</span><span class="sxs-lookup"><span data-stu-id="95b01-130">If `condition` is `False` when you first enter the loop, it doesn’t run even once.</span></span>  
  
 <span data-ttu-id="95b01-131">`condition`通常的比较结果的两个值，但它可以是任何表达式的计算结果为[布尔数据类型](../../../visual-basic/language-reference/data-types/boolean-data-type.md)值 (`True`或`False`)。</span><span class="sxs-lookup"><span data-stu-id="95b01-131">The `condition` usually results from a comparison of two values, but it can be any expression that evaluates to a [Boolean Data Type](../../../visual-basic/language-reference/data-types/boolean-data-type.md) value (`True` or `False`).</span></span> <span data-ttu-id="95b01-132">此表达式可包含其他数据类型，例如数值类型，已转换为的值`Boolean`。</span><span class="sxs-lookup"><span data-stu-id="95b01-132">This expression can include a value of another data type, such as a numeric type, that has been converted to `Boolean`.</span></span>  
  
 <span data-ttu-id="95b01-133">可以嵌套`While`上来将另一个循环内的循环。</span><span class="sxs-lookup"><span data-stu-id="95b01-133">You can nest `While` loops by placing one loop within another.</span></span> <span data-ttu-id="95b01-134">此外可以嵌套在另一个控制结构的不同种类。</span><span class="sxs-lookup"><span data-stu-id="95b01-134">You can also nest different kinds of control structures within one another.</span></span> <span data-ttu-id="95b01-135">有关详细信息，请参阅[嵌套控制结构](../../../visual-basic/programming-guide/language-features/control-flow/nested-control-structures.md)。</span><span class="sxs-lookup"><span data-stu-id="95b01-135">For more information, see [Nested Control Structures](../../../visual-basic/programming-guide/language-features/control-flow/nested-control-structures.md).</span></span>  
  
## <a name="exit-while"></a><span data-ttu-id="95b01-136">退出时</span><span class="sxs-lookup"><span data-stu-id="95b01-136">Exit While</span></span>  
 <span data-ttu-id="95b01-137">[退出时](../../../visual-basic/language-reference/statements/exit-statement.md)语句可以提供另一种方法退出`While`循环。</span><span class="sxs-lookup"><span data-stu-id="95b01-137">The [Exit While](../../../visual-basic/language-reference/statements/exit-statement.md) statement can provide another way to exit a `While` loop.</span></span> <span data-ttu-id="95b01-138">`Exit While` 立即将控制权移交给后面的语句`End While`语句。</span><span class="sxs-lookup"><span data-stu-id="95b01-138">`Exit While` immediately transfers control to the statement that follows the `End While` statement.</span></span>  
  
 <span data-ttu-id="95b01-139">通常使用`Exit While`对某些条件的求值后 (例如，在`If...Then...Else`结构)。</span><span class="sxs-lookup"><span data-stu-id="95b01-139">You typically use `Exit While` after some condition is evaluated (for example, in an `If...Then...Else` structure).</span></span> <span data-ttu-id="95b01-140">您可能需要退出循环，如果检测到导致其不必要或无法继续循环访问，例如错误的值或终止请求的条件。</span><span class="sxs-lookup"><span data-stu-id="95b01-140">You might want to exit a loop if you detect a condition that makes it unnecessary or impossible to continue iterating, such as an erroneous value or a termination request.</span></span> <span data-ttu-id="95b01-141">可以使用`Exit While`在您测试条件可能会导致*无限循环*，这是可以运行次数极大甚至无限循环。</span><span class="sxs-lookup"><span data-stu-id="95b01-141">You can use `Exit While` when you test for a condition that could cause an *endless loop*, which is a loop that could run an extremely large or even infinite number of times.</span></span> <span data-ttu-id="95b01-142">然后，可以使用`Exit While`来退出循环。</span><span class="sxs-lookup"><span data-stu-id="95b01-142">You can then use `Exit While` to escape the loop.</span></span>  
  
 <span data-ttu-id="95b01-143">可以将任意数量的放置`Exit While`中的任意位置语句`While`循环。</span><span class="sxs-lookup"><span data-stu-id="95b01-143">You can place any number of `Exit While` statements anywhere in the `While` loop.</span></span>  
  
 <span data-ttu-id="95b01-144">当使用内嵌套`While`循环，`Exit While`控制权从最里面的循环和到下一个较高级别的嵌套。</span><span class="sxs-lookup"><span data-stu-id="95b01-144">When used within nested `While` loops, `Exit While` transfers control out of the innermost loop and into the next higher level of nesting.</span></span>  
  
 <span data-ttu-id="95b01-145">`Continue While`语句立即将控制转移到循环的下一个迭代。</span><span class="sxs-lookup"><span data-stu-id="95b01-145">The `Continue While` statement immediately transfers control to the next iteration of the loop.</span></span> <span data-ttu-id="95b01-146">有关详细信息，请参阅[Continue 语句](../../../visual-basic/language-reference/statements/continue-statement.md)。</span><span class="sxs-lookup"><span data-stu-id="95b01-146">For more information, see [Continue Statement](../../../visual-basic/language-reference/statements/continue-statement.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="95b01-147">示例</span><span class="sxs-lookup"><span data-stu-id="95b01-147">Example</span></span>  
 <span data-ttu-id="95b01-148">在以下示例中，在循环中的语句继续运行，直到`index`变量是否大于 10。</span><span class="sxs-lookup"><span data-stu-id="95b01-148">In the following example, the statements in the loop continue to run until the `index` variable is greater than 10.</span></span>  
  
 [!code-vb[VbVbalrStatements#171](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class14.vb#171)]  
  
## <a name="example"></a><span data-ttu-id="95b01-149">示例</span><span class="sxs-lookup"><span data-stu-id="95b01-149">Example</span></span>  
 <span data-ttu-id="95b01-150">下面的示例演示如何使用`Continue While`和`Exit While`语句。</span><span class="sxs-lookup"><span data-stu-id="95b01-150">The following example illustrates the use of the `Continue While` and `Exit While` statements.</span></span>  
  
 [!code-vb[VbVbalrStatements#172](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class14.vb#172)]  
  
## <a name="example"></a><span data-ttu-id="95b01-151">示例</span><span class="sxs-lookup"><span data-stu-id="95b01-151">Example</span></span>  
 <span data-ttu-id="95b01-152">下面的示例读取在文本文件中的所有行。</span><span class="sxs-lookup"><span data-stu-id="95b01-152">The following example reads all lines in a text file.</span></span> <span data-ttu-id="95b01-153"><xref:System.IO.File.OpenText%2A>方法打开文件并返回<xref:System.IO.StreamReader>读取字符。</span><span class="sxs-lookup"><span data-stu-id="95b01-153">The <xref:System.IO.File.OpenText%2A> method opens the file and returns a <xref:System.IO.StreamReader> that reads the characters.</span></span> <span data-ttu-id="95b01-154">在中`While`条件，请<xref:System.IO.StreamReader.Peek%2A>方法的`StreamReader`确定文件是否包含其他字符。</span><span class="sxs-lookup"><span data-stu-id="95b01-154">In the `While` condition, the <xref:System.IO.StreamReader.Peek%2A> method of the `StreamReader` determines whether the file contains additional characters.</span></span>  
  
 [!code-vb[VbVbalrStatements#173](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class14.vb#173)]  
  
## <a name="see-also"></a><span data-ttu-id="95b01-155">请参阅</span><span class="sxs-lookup"><span data-stu-id="95b01-155">See also</span></span>

- [<span data-ttu-id="95b01-156">循环结构</span><span class="sxs-lookup"><span data-stu-id="95b01-156">Loop Structures</span></span>](../../../visual-basic/programming-guide/language-features/control-flow/loop-structures.md)
- [<span data-ttu-id="95b01-157">Do...Loop 语句</span><span class="sxs-lookup"><span data-stu-id="95b01-157">Do...Loop Statement</span></span>](../../../visual-basic/language-reference/statements/do-loop-statement.md)
- [<span data-ttu-id="95b01-158">For...Next 语句</span><span class="sxs-lookup"><span data-stu-id="95b01-158">For...Next Statement</span></span>](../../../visual-basic/language-reference/statements/for-next-statement.md)
- [<span data-ttu-id="95b01-159">Boolean 数据类型</span><span class="sxs-lookup"><span data-stu-id="95b01-159">Boolean Data Type</span></span>](../../../visual-basic/language-reference/data-types/boolean-data-type.md)
- [<span data-ttu-id="95b01-160">嵌套的控件结构</span><span class="sxs-lookup"><span data-stu-id="95b01-160">Nested Control Structures</span></span>](../../../visual-basic/programming-guide/language-features/control-flow/nested-control-structures.md)
- [<span data-ttu-id="95b01-161">Exit 语句</span><span class="sxs-lookup"><span data-stu-id="95b01-161">Exit Statement</span></span>](../../../visual-basic/language-reference/statements/exit-statement.md)
- [<span data-ttu-id="95b01-162">Continue 语句</span><span class="sxs-lookup"><span data-stu-id="95b01-162">Continue Statement</span></span>](../../../visual-basic/language-reference/statements/continue-statement.md)
