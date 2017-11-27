---
title: "While...End While 语句 (Visual Basic)"
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords:
- vb.While
- vb.While...EndWhile
helpviewer_keywords:
- While statement [Visual Basic], While...End While
- While statement [Visual Basic]
- While...End While statements [Visual Basic]
ms.assetid: b931d1ce-e8ed-44d8-a13d-92a4f5458a1e
caps.latest.revision: "22"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 5f831f233eaa4f1c38d56f3a89bda9b0cf1bccaa
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="whileend-while-statement-visual-basic"></a><span data-ttu-id="31df0-102">While...End While 语句 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="31df0-102">While...End While Statement (Visual Basic)</span></span>
<span data-ttu-id="31df0-103">只要给定的条件运行一系列语句`True`。</span><span class="sxs-lookup"><span data-stu-id="31df0-103">Runs a series of statements as long as a given condition is `True`.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="31df0-104">语法</span><span class="sxs-lookup"><span data-stu-id="31df0-104">Syntax</span></span>  
  
```  
While condition  
    [ statements ]  
    [ Continue While ]  
    [ statements ]  
    [ Exit While ]  
    [ statements ]  
End While  
```  
  
## <a name="parts"></a><span data-ttu-id="31df0-105">部件</span><span class="sxs-lookup"><span data-stu-id="31df0-105">Parts</span></span>  
  
|<span data-ttu-id="31df0-106">术语</span><span class="sxs-lookup"><span data-stu-id="31df0-106">Term</span></span>|<span data-ttu-id="31df0-107">定义</span><span class="sxs-lookup"><span data-stu-id="31df0-107">Definition</span></span>|  
|---|---|  
|`condition`|<span data-ttu-id="31df0-108">必需。</span><span class="sxs-lookup"><span data-stu-id="31df0-108">Required.</span></span> <span data-ttu-id="31df0-109">`Boolean`表达式。</span><span class="sxs-lookup"><span data-stu-id="31df0-109">`Boolean` expression.</span></span> <span data-ttu-id="31df0-110">如果`condition`是`Nothing`，Visual Basic 会将其视为`False`。</span><span class="sxs-lookup"><span data-stu-id="31df0-110">If `condition` is `Nothing`, Visual Basic treats it as `False`.</span></span>|  
|`statements`|<span data-ttu-id="31df0-111">可选。</span><span class="sxs-lookup"><span data-stu-id="31df0-111">Optional.</span></span> <span data-ttu-id="31df0-112">一个或多个语句以下`While`，每次运行该`condition`是`True`。</span><span class="sxs-lookup"><span data-stu-id="31df0-112">One or more statements following `While`, which run every time `condition` is `True`.</span></span>|  
|`Continue While`|<span data-ttu-id="31df0-113">可选。</span><span class="sxs-lookup"><span data-stu-id="31df0-113">Optional.</span></span> <span data-ttu-id="31df0-114">将控制转移到的下一个迭代`While`块。</span><span class="sxs-lookup"><span data-stu-id="31df0-114">Transfers control to the next iteration of the `While` block.</span></span>|  
|`Exit While`|<span data-ttu-id="31df0-115">可选。</span><span class="sxs-lookup"><span data-stu-id="31df0-115">Optional.</span></span> <span data-ttu-id="31df0-116">将扩展的控制转移`While`块。</span><span class="sxs-lookup"><span data-stu-id="31df0-116">Transfers control out of the `While` block.</span></span>|  
|`End While`|<span data-ttu-id="31df0-117">必需。</span><span class="sxs-lookup"><span data-stu-id="31df0-117">Required.</span></span> <span data-ttu-id="31df0-118">终止 `While` 块的定义。</span><span class="sxs-lookup"><span data-stu-id="31df0-118">Terminates the definition of the `While` block.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="31df0-119">备注</span><span class="sxs-lookup"><span data-stu-id="31df0-119">Remarks</span></span>  
 <span data-ttu-id="31df0-120">使用`While...End While`结构时，只要条件仍然要重复语句无限次，一组`True`。</span><span class="sxs-lookup"><span data-stu-id="31df0-120">Use a `While...End While` structure when you want to repeat a set of statements an indefinite number of times, as long as a condition remains `True`.</span></span> <span data-ttu-id="31df0-121">如果想要更灵活地选择你在其中测试条件以及针对什么结果进行测试，你可能希望[执行...循环语句](../../../visual-basic/language-reference/statements/do-loop-statement.md)。</span><span class="sxs-lookup"><span data-stu-id="31df0-121">If you want more flexibility with where you test the condition or what result you test it for, you might prefer the [Do...Loop Statement](../../../visual-basic/language-reference/statements/do-loop-statement.md).</span></span> <span data-ttu-id="31df0-122">如果你想要重复执行语句，一定的时间，[为...下一条语句](../../../visual-basic/language-reference/statements/for-next-statement.md)通常是更好的选择。</span><span class="sxs-lookup"><span data-stu-id="31df0-122">If you want to repeat the statements a set number of times, the [For...Next Statement](../../../visual-basic/language-reference/statements/for-next-statement.md) is usually a better choice.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="31df0-123">`While`关键字还用于[执行...循环语句](../../../visual-basic/language-reference/statements/do-loop-statement.md)、 [Skip While 子句](../../../visual-basic/language-reference/queries/skip-while-clause.md)和[Take While 子句](../../../visual-basic/language-reference/queries/take-while-clause.md)。</span><span class="sxs-lookup"><span data-stu-id="31df0-123">The `While` keyword is also used in the [Do...Loop Statement](../../../visual-basic/language-reference/statements/do-loop-statement.md), the [Skip While Clause](../../../visual-basic/language-reference/queries/skip-while-clause.md) and the [Take While Clause](../../../visual-basic/language-reference/queries/take-while-clause.md).</span></span>  
  
 <span data-ttu-id="31df0-124">如果`condition`是`True`，所有的`statements`运行，直至`End While`遇到语句。</span><span class="sxs-lookup"><span data-stu-id="31df0-124">If `condition` is `True`, all of the `statements` run until the `End While` statement is encountered.</span></span> <span data-ttu-id="31df0-125">随后控制返回到`While`语句，和`condition`再次检查。</span><span class="sxs-lookup"><span data-stu-id="31df0-125">Control then returns to the `While` statement, and `condition` is again checked.</span></span> <span data-ttu-id="31df0-126">如果`condition`仍`True`，请重复该过程。</span><span class="sxs-lookup"><span data-stu-id="31df0-126">If `condition` is still `True`, the process is repeated.</span></span> <span data-ttu-id="31df0-127">如果它具有`False`，控制将传递到后面的语句`End While`语句。</span><span class="sxs-lookup"><span data-stu-id="31df0-127">If it’s `False`, control passes to the statement that follows the `End While` statement.</span></span>  
  
 <span data-ttu-id="31df0-128">`While`语句始终检查条件，然后会启动循环。</span><span class="sxs-lookup"><span data-stu-id="31df0-128">The `While` statement always checks the condition before it starts the loop.</span></span> <span data-ttu-id="31df0-129">循环条件保持时将会继续下去`True`。</span><span class="sxs-lookup"><span data-stu-id="31df0-129">Looping continues while the condition remains `True`.</span></span> <span data-ttu-id="31df0-130">如果`condition`是`False`当您首次进入循环，它不甚至一次运行。</span><span class="sxs-lookup"><span data-stu-id="31df0-130">If `condition` is `False` when you first enter the loop, it doesn’t run even once.</span></span>  
  
 <span data-ttu-id="31df0-131">`condition`通常于比较的两个值，但它的结果可以是任何表达式计算结果为[布尔数据类型](../../../visual-basic/language-reference/data-types/boolean-data-type.md)值 (`True`或`False`)。</span><span class="sxs-lookup"><span data-stu-id="31df0-131">The `condition` usually results from a comparison of two values, but it can be any expression that evaluates to a [Boolean Data Type](../../../visual-basic/language-reference/data-types/boolean-data-type.md) value (`True` or `False`).</span></span> <span data-ttu-id="31df0-132">此表达式可包含的另一个数据类型，如的数值类型，已转换为值`Boolean`。</span><span class="sxs-lookup"><span data-stu-id="31df0-132">This expression can include a value of another data type, such as a numeric type, that has been converted to `Boolean`.</span></span>  
  
 <span data-ttu-id="31df0-133">可以嵌套`While`通过将另一个循环内的循环。</span><span class="sxs-lookup"><span data-stu-id="31df0-133">You can nest `While` loops by placing one loop within another.</span></span> <span data-ttu-id="31df0-134">此外可以嵌套在另一个控制结构的不同类型。</span><span class="sxs-lookup"><span data-stu-id="31df0-134">You can also nest different kinds of control structures within one another.</span></span> <span data-ttu-id="31df0-135">有关详细信息，请参阅[嵌套控制结构](../../../visual-basic/programming-guide/language-features/control-flow/nested-control-structures.md)。</span><span class="sxs-lookup"><span data-stu-id="31df0-135">For more information, see [Nested Control Structures](../../../visual-basic/programming-guide/language-features/control-flow/nested-control-structures.md).</span></span>  
  
## <a name="exit-while"></a><span data-ttu-id="31df0-136">退出时</span><span class="sxs-lookup"><span data-stu-id="31df0-136">Exit While</span></span>  
 <span data-ttu-id="31df0-137">[退出时](../../../visual-basic/language-reference/statements/exit-statement.md)语句可以提供另一种方式退出`While`循环。</span><span class="sxs-lookup"><span data-stu-id="31df0-137">The [Exit While](../../../visual-basic/language-reference/statements/exit-statement.md) statement can provide another way to exit a `While` loop.</span></span> <span data-ttu-id="31df0-138">`Exit While`立即将控制权转交给后面的语句`End While`语句。</span><span class="sxs-lookup"><span data-stu-id="31df0-138">`Exit While` immediately transfers control to the statement that follows the `End While` statement.</span></span>  
  
 <span data-ttu-id="31df0-139">通常使用`Exit While`对某些条件进行评估后 (例如，在`If...Then...Else`结构)。</span><span class="sxs-lookup"><span data-stu-id="31df0-139">You typically use `Exit While` after some condition is evaluated (for example, in an `If...Then...Else` structure).</span></span> <span data-ttu-id="31df0-140">你可能想要退出循环，如果检测到的条件，使它不必要或不可能继续循环，如错误的值或终止请求。</span><span class="sxs-lookup"><span data-stu-id="31df0-140">You might want to exit a loop if you detect a condition that makes it unnecessary or impossible to continue iterating, such as an erroneous value or a termination request.</span></span> <span data-ttu-id="31df0-141">你可以使用`Exit While`当你测试的条件，可能会导致*无限循环*，即无法运行次数极大甚至无限循环。</span><span class="sxs-lookup"><span data-stu-id="31df0-141">You can use `Exit While` when you test for a condition that could cause an *endless loop*, which is a loop that could run an extremely large or even infinite number of times.</span></span> <span data-ttu-id="31df0-142">然后，可以使用`Exit While`来退出循环。</span><span class="sxs-lookup"><span data-stu-id="31df0-142">You can then use `Exit While` to escape the loop.</span></span>  
  
 <span data-ttu-id="31df0-143">你可以放置任意数量的`Exit While`中的任意位置语句`While`循环。</span><span class="sxs-lookup"><span data-stu-id="31df0-143">You can place any number of `Exit While` statements anywhere in the `While` loop.</span></span>  
  
 <span data-ttu-id="31df0-144">当使用内嵌套`While`循环，`Exit While`传输最内层的循环出来放入下一个较高级别的嵌套的控件。</span><span class="sxs-lookup"><span data-stu-id="31df0-144">When used within nested `While` loops, `Exit While` transfers control out of the innermost loop and into the next higher level of nesting.</span></span>  
  
 <span data-ttu-id="31df0-145">`Continue While`语句立即将控制权转交给循环的下一个迭代。</span><span class="sxs-lookup"><span data-stu-id="31df0-145">The `Continue While` statement immediately transfers control to the next iteration of the loop.</span></span> <span data-ttu-id="31df0-146">有关详细信息，请参阅[继续语句](../../../visual-basic/language-reference/statements/continue-statement.md)。</span><span class="sxs-lookup"><span data-stu-id="31df0-146">For more information, see [Continue Statement](../../../visual-basic/language-reference/statements/continue-statement.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="31df0-147">示例</span><span class="sxs-lookup"><span data-stu-id="31df0-147">Example</span></span>  
 <span data-ttu-id="31df0-148">在下面的示例中，在循环中的语句继续运行，直到`index`变量是否大于 10。</span><span class="sxs-lookup"><span data-stu-id="31df0-148">In the following example, the statements in the loop continue to run until the `index` variable is greater than 10.</span></span>  
  
 [!code-vb[VbVbalrStatements#171](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/while-end-while-statement_1.vb)]  
  
## <a name="example"></a><span data-ttu-id="31df0-149">示例</span><span class="sxs-lookup"><span data-stu-id="31df0-149">Example</span></span>  
 <span data-ttu-id="31df0-150">下面的示例演示如何使用`Continue While`和`Exit While`语句。</span><span class="sxs-lookup"><span data-stu-id="31df0-150">The following example illustrates the use of the `Continue While` and `Exit While` statements.</span></span>  
  
 [!code-vb[VbVbalrStatements#172](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/while-end-while-statement_2.vb)]  
  
## <a name="example"></a><span data-ttu-id="31df0-151">示例</span><span class="sxs-lookup"><span data-stu-id="31df0-151">Example</span></span>  
 <span data-ttu-id="31df0-152">下面的示例读取在文本文件中的所有行。</span><span class="sxs-lookup"><span data-stu-id="31df0-152">The following example reads all lines in a text file.</span></span> <span data-ttu-id="31df0-153"><xref:System.IO.File.OpenText%2A>方法打开该文件，并返回<xref:System.IO.StreamReader>读取字符。</span><span class="sxs-lookup"><span data-stu-id="31df0-153">The <xref:System.IO.File.OpenText%2A> method opens the file and returns a <xref:System.IO.StreamReader> that reads the characters.</span></span> <span data-ttu-id="31df0-154">在`While`条件，<xref:System.IO.StreamReader.Peek%2A>方法`StreamReader`确定文件是否包含其他字符。</span><span class="sxs-lookup"><span data-stu-id="31df0-154">In the `While` condition, the <xref:System.IO.StreamReader.Peek%2A> method of the `StreamReader` determines whether the file contains additional characters.</span></span>  
  
 [!code-vb[VbVbalrStatements#173](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/while-end-while-statement_3.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="31df0-155">另请参阅</span><span class="sxs-lookup"><span data-stu-id="31df0-155">See Also</span></span>  
 [<span data-ttu-id="31df0-156">循环结构</span><span class="sxs-lookup"><span data-stu-id="31df0-156">Loop Structures</span></span>](../../../visual-basic/programming-guide/language-features/control-flow/loop-structures.md)  
 [<span data-ttu-id="31df0-157">Do...Loop 语句</span><span class="sxs-lookup"><span data-stu-id="31df0-157">Do...Loop Statement</span></span>](../../../visual-basic/language-reference/statements/do-loop-statement.md)  
 [<span data-ttu-id="31df0-158">For...Next 语句</span><span class="sxs-lookup"><span data-stu-id="31df0-158">For...Next Statement</span></span>](../../../visual-basic/language-reference/statements/for-next-statement.md)  
 [<span data-ttu-id="31df0-159">Boolean 数据类型</span><span class="sxs-lookup"><span data-stu-id="31df0-159">Boolean Data Type</span></span>](../../../visual-basic/language-reference/data-types/boolean-data-type.md)  
 [<span data-ttu-id="31df0-160">嵌套的控件结构</span><span class="sxs-lookup"><span data-stu-id="31df0-160">Nested Control Structures</span></span>](../../../visual-basic/programming-guide/language-features/control-flow/nested-control-structures.md)  
 [<span data-ttu-id="31df0-161">Exit 语句</span><span class="sxs-lookup"><span data-stu-id="31df0-161">Exit Statement</span></span>](../../../visual-basic/language-reference/statements/exit-statement.md)  
 [<span data-ttu-id="31df0-162">Continue 语句</span><span class="sxs-lookup"><span data-stu-id="31df0-162">Continue Statement</span></span>](../../../visual-basic/language-reference/statements/continue-statement.md)
