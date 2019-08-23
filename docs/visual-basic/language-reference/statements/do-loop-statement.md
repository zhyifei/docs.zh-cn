---
title: Do...Loop 语句 (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.Do
- vb.Loop
- vb.Until
helpviewer_keywords:
- conditional statements [Visual Basic], Do�Loop
- while statement [Visual Basic], Do...Loop
- execution [Visual Basic], conditional
- Do loops
- Until keyword [Visual Basic], Do...Loop statement
- Do...Loop statement
- instructions, repeating
- Do statement [Visual Basic]
- Exit statement [Visual Basic], in Do...Loop statements
- loop structures [Visual Basic], Do�Loop statements
- do-while statements [Visual Basic]
- loops, exiting
- Loop keyword [Visual Basic], Do...Loop statement
ms.assetid: 892f9096-b3e2-4aee-834d-83bc4e2c379d
ms.openlocfilehash: 75a2129a9f332024831d97021e381f1b3d4fa048
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2019
ms.locfileid: "69943001"
---
# <a name="doloop-statement-visual-basic"></a><span data-ttu-id="16451-102">Do...Loop 语句 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="16451-102">Do...Loop Statement (Visual Basic)</span></span>
<span data-ttu-id="16451-103">当`Boolean`条件为`True`或在条件变为`True`之前, 重复语句块。</span><span class="sxs-lookup"><span data-stu-id="16451-103">Repeats a block of statements while a `Boolean` condition is `True` or until the condition becomes `True`.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="16451-104">语法</span><span class="sxs-lookup"><span data-stu-id="16451-104">Syntax</span></span>  
  
```  
Do { While | Until } condition  
    [ statements ]  
    [ Continue Do ]  
    [ statements ]  
    [ Exit Do ]  
    [ statements ]  
Loop  
-or-  
Do  
    [ statements ]  
    [ Continue Do ]  
    [ statements ]  
    [ Exit Do ]  
    [ statements ]  
Loop { While | Until } condition  
```  
  
## <a name="parts"></a><span data-ttu-id="16451-105">部件</span><span class="sxs-lookup"><span data-stu-id="16451-105">Parts</span></span>  
  
|<span data-ttu-id="16451-106">术语</span><span class="sxs-lookup"><span data-stu-id="16451-106">Term</span></span>|<span data-ttu-id="16451-107">定义</span><span class="sxs-lookup"><span data-stu-id="16451-107">Definition</span></span>|  
|---|---|  
|`Do`|<span data-ttu-id="16451-108">必需。</span><span class="sxs-lookup"><span data-stu-id="16451-108">Required.</span></span> <span data-ttu-id="16451-109">开始`Do`循环的定义。</span><span class="sxs-lookup"><span data-stu-id="16451-109">Starts the definition of the `Do` loop.</span></span>|  
|`While`|<span data-ttu-id="16451-110">必选项（除非使用了 `Until`）。</span><span class="sxs-lookup"><span data-stu-id="16451-110">Required unless `Until` is used.</span></span> <span data-ttu-id="16451-111">重复循环, 直到`condition`为`False`为止。</span><span class="sxs-lookup"><span data-stu-id="16451-111">Repeat the loop until `condition` is `False`.</span></span>|  
|`Until`|<span data-ttu-id="16451-112">必选项（除非使用了 `While`）。</span><span class="sxs-lookup"><span data-stu-id="16451-112">Required unless `While` is used.</span></span> <span data-ttu-id="16451-113">重复循环, 直到`condition`为`True`为止。</span><span class="sxs-lookup"><span data-stu-id="16451-113">Repeat the loop until `condition` is `True`.</span></span>|  
|`condition`|<span data-ttu-id="16451-114">可选。</span><span class="sxs-lookup"><span data-stu-id="16451-114">Optional.</span></span> <span data-ttu-id="16451-115">`Boolean`表达式.</span><span class="sxs-lookup"><span data-stu-id="16451-115">`Boolean` expression.</span></span> <span data-ttu-id="16451-116">如果`condition`为`Nothing` ,则VisualBasic`False`将其视为。</span><span class="sxs-lookup"><span data-stu-id="16451-116">If `condition` is `Nothing`, Visual Basic treats it as `False`.</span></span>|  
|`statements`|<span data-ttu-id="16451-117">可选。</span><span class="sxs-lookup"><span data-stu-id="16451-117">Optional.</span></span> <span data-ttu-id="16451-118">一个或多个重复的语句, 或在之前`condition` `True`重复。</span><span class="sxs-lookup"><span data-stu-id="16451-118">One or more statements that are repeated while, or until, `condition` is `True`.</span></span>|  
|`Continue Do`|<span data-ttu-id="16451-119">可选。</span><span class="sxs-lookup"><span data-stu-id="16451-119">Optional.</span></span> <span data-ttu-id="16451-120">将控制转移到`Do`循环的下一次迭代。</span><span class="sxs-lookup"><span data-stu-id="16451-120">Transfers control to the next iteration of the `Do` loop.</span></span>|  
|`Exit Do`|<span data-ttu-id="16451-121">可选。</span><span class="sxs-lookup"><span data-stu-id="16451-121">Optional.</span></span> <span data-ttu-id="16451-122">将控制转移到`Do`循环外。</span><span class="sxs-lookup"><span data-stu-id="16451-122">Transfers control out of the `Do` loop.</span></span>|  
|`Loop`|<span data-ttu-id="16451-123">必需。</span><span class="sxs-lookup"><span data-stu-id="16451-123">Required.</span></span> <span data-ttu-id="16451-124">终止`Do`循环的定义。</span><span class="sxs-lookup"><span data-stu-id="16451-124">Terminates the definition of the `Do` loop.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="16451-125">备注</span><span class="sxs-lookup"><span data-stu-id="16451-125">Remarks</span></span>  
 <span data-ttu-id="16451-126">如果希望在满足条件之前重复一组语句, 请使用结构。`Do...Loop`</span><span class="sxs-lookup"><span data-stu-id="16451-126">Use a `Do...Loop` structure when you want to repeat a set of statements an indefinite number of times, until a condition is satisfied.</span></span> <span data-ttu-id="16451-127">如果要将语句重复一组次数, 则[下一条语句](../../../visual-basic/language-reference/statements/for-next-statement.md)通常是更好的选择。</span><span class="sxs-lookup"><span data-stu-id="16451-127">If you want to repeat the statements a set number of times, the [For...Next Statement](../../../visual-basic/language-reference/statements/for-next-statement.md) is usually a better choice.</span></span>  
  
 <span data-ttu-id="16451-128">您可以使用`While`或`Until`来指定`condition`, 但不能同时使用两者。</span><span class="sxs-lookup"><span data-stu-id="16451-128">You can use either `While` or `Until` to specify `condition`, but not both.</span></span>  
  
 <span data-ttu-id="16451-129">只能在循环`condition`的开头或结尾测试一次。</span><span class="sxs-lookup"><span data-stu-id="16451-129">You can test `condition` only one time, at either the start or the end of the loop.</span></span> <span data-ttu-id="16451-130">如果在循环`condition`开始时测试 ( `Do`在语句中), 则循环可能不会运行一次。</span><span class="sxs-lookup"><span data-stu-id="16451-130">If you test `condition` at the start of the loop (in the `Do` statement), the loop might not run even one time.</span></span> <span data-ttu-id="16451-131">如果在循环的末尾测试 (在`Loop`语句中), 该循环始终至少运行一次。</span><span class="sxs-lookup"><span data-stu-id="16451-131">If you test at the end of the loop (in the `Loop` statement), the loop always runs at least one time.</span></span>  
  
 <span data-ttu-id="16451-132">这种情况通常是由两个值比较导致的, 但它可以是计算结果为[布尔数据类型](../../../visual-basic/language-reference/data-types/boolean-data-type.md)值 (`True`或`False`) 的任何表达式。</span><span class="sxs-lookup"><span data-stu-id="16451-132">The condition usually results from a comparison of two values, but it can be any expression that evaluates to a [Boolean Data Type](../../../visual-basic/language-reference/data-types/boolean-data-type.md) value (`True` or `False`).</span></span> <span data-ttu-id="16451-133">这包括已转换为`Boolean`的其他数据类型 (如数值类型) 的值。</span><span class="sxs-lookup"><span data-stu-id="16451-133">This includes values of other data types, such as numeric types, that have been converted to `Boolean`.</span></span>  
  
 <span data-ttu-id="16451-134">可以通过在`Do`另一个循环中放置循环来嵌套循环。</span><span class="sxs-lookup"><span data-stu-id="16451-134">You can nest `Do` loops by putting one loop within another.</span></span> <span data-ttu-id="16451-135">您还可以在彼此之间嵌套不同种类的控制结构。</span><span class="sxs-lookup"><span data-stu-id="16451-135">You can also nest different kinds of control structures within each other.</span></span> <span data-ttu-id="16451-136">有关详细信息, 请参阅[嵌套控制结构](../../../visual-basic/programming-guide/language-features/control-flow/nested-control-structures.md)。</span><span class="sxs-lookup"><span data-stu-id="16451-136">For more information, see [Nested Control Structures](../../../visual-basic/programming-guide/language-features/control-flow/nested-control-structures.md).</span></span>  
  
> [!NOTE]
> <span data-ttu-id="16451-137">此`Do...Loop`结构提供的灵活性比[.。。End While 语句](../../../visual-basic/language-reference/statements/while-end-while-statement.md), 因为它可用于决定是在停止`condition` `True`时还是在第一次变为`True`时结束循环。</span><span class="sxs-lookup"><span data-stu-id="16451-137">The `Do...Loop` structure gives you more flexibility than the [While...End While Statement](../../../visual-basic/language-reference/statements/while-end-while-statement.md) because it enables you to decide whether to end the loop when `condition` stops being `True` or when it first becomes `True`.</span></span> <span data-ttu-id="16451-138">它还使你能够在`condition`循环的开头或结尾进行测试。</span><span class="sxs-lookup"><span data-stu-id="16451-138">It also enables you to test `condition` at either the start or the end of the loop.</span></span>  
  
## <a name="exit-do"></a><span data-ttu-id="16451-139">退出 Do</span><span class="sxs-lookup"><span data-stu-id="16451-139">Exit Do</span></span>  
 <span data-ttu-id="16451-140">[Exit Do](../../../visual-basic/language-reference/statements/exit-statement.md)语句可以提供退出的`Do…Loop`替代方法。</span><span class="sxs-lookup"><span data-stu-id="16451-140">The [Exit Do](../../../visual-basic/language-reference/statements/exit-statement.md) statement can provide an alternative way to exit a `Do…Loop`.</span></span> <span data-ttu-id="16451-141">`Exit Do`将控制立即传输到`Loop`语句后面的语句。</span><span class="sxs-lookup"><span data-stu-id="16451-141">`Exit Do` transfers control immediately to the statement that follows the `Loop` statement.</span></span>  
  
 <span data-ttu-id="16451-142">`Exit Do`通常在计算某些条件后 (例如在`If...Then...Else`结构中) 使用。</span><span class="sxs-lookup"><span data-stu-id="16451-142">`Exit Do` is often used after some condition is evaluated, for example in an `If...Then...Else` structure.</span></span> <span data-ttu-id="16451-143">如果检测到可能导致不必要或无法继续迭代的条件 (如错误值或终止请求), 则可能需要退出循环。</span><span class="sxs-lookup"><span data-stu-id="16451-143">You might want to exit a loop if you detect a condition that makes it unnecessary or impossible to continue iterating, such as an erroneous value or a termination request.</span></span> <span data-ttu-id="16451-144">的`Exit Do`一种用途是测试可能导致*无限循环*的情况, 这是一个可运行很大甚至无限次数的循环。</span><span class="sxs-lookup"><span data-stu-id="16451-144">One use of `Exit Do` is to test for a condition that could cause an *endless loop*, which is a loop that could run a large or even infinite number of times.</span></span> <span data-ttu-id="16451-145">您可以使用`Exit Do`来转义循环。</span><span class="sxs-lookup"><span data-stu-id="16451-145">You can use `Exit Do` to escape the loop.</span></span>  
  
 <span data-ttu-id="16451-146">`Exit Do` 可以`Do…Loop`在中的任意位置包含任意数量的语句。</span><span class="sxs-lookup"><span data-stu-id="16451-146">You can include any number of `Exit Do` statements anywhere in a `Do…Loop`.</span></span>  
  
 <span data-ttu-id="16451-147">在嵌套`Do`循环内使用时`Exit Do` , 将控制转移出最内层循环, 并将其转移到下一个更高的嵌套级别。</span><span class="sxs-lookup"><span data-stu-id="16451-147">When used within nested `Do` loops, `Exit Do` transfers control out of the innermost loop and into the next higher level of nesting.</span></span>  
  
## <a name="example"></a><span data-ttu-id="16451-148">示例</span><span class="sxs-lookup"><span data-stu-id="16451-148">Example</span></span>  
 <span data-ttu-id="16451-149">在下面的示例中, 循环中的语句将继续运行, 直到`index`变量大于10。</span><span class="sxs-lookup"><span data-stu-id="16451-149">In the following example, the statements in the loop continue to run until the `index` variable is greater than 10.</span></span> <span data-ttu-id="16451-150">`Until`子句位于循环的结尾。</span><span class="sxs-lookup"><span data-stu-id="16451-150">The `Until` clause is at the end of the loop.</span></span>  
  
 [!code-vb[VbVbalrStatements#131](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class10.vb#131)]  
  
## <a name="example"></a><span data-ttu-id="16451-151">示例</span><span class="sxs-lookup"><span data-stu-id="16451-151">Example</span></span>  
 <span data-ttu-id="16451-152">下面的示例使用`While`子句而不`Until`是子句, 并`condition`在循环的开头而不是在结束时进行测试。</span><span class="sxs-lookup"><span data-stu-id="16451-152">The following example uses a `While` clause instead of an `Until` clause, and `condition` is tested at the start of the loop instead of at the end.</span></span>  
  
 [!code-vb[VbVbalrStatements#132](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class10.vb#132)]  
  
## <a name="example"></a><span data-ttu-id="16451-153">示例</span><span class="sxs-lookup"><span data-stu-id="16451-153">Example</span></span>  
 <span data-ttu-id="16451-154">在下面的示例中`condition` , `index`当变量大于100时停止循环。</span><span class="sxs-lookup"><span data-stu-id="16451-154">In the following example, `condition` stops the loop when the `index` variable is greater than 100.</span></span> <span data-ttu-id="16451-155">但是`If` , 循环中的语句`Exit Do`会导致语句在索引变量大于10时停止循环。</span><span class="sxs-lookup"><span data-stu-id="16451-155">The `If` statement in the loop, however, causes the `Exit Do` statement to stop the loop when the index variable is greater than 10.</span></span>  
  
 [!code-vb[VbVbalrStatements#133](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class10.vb#133)]  
  
## <a name="example"></a><span data-ttu-id="16451-156">示例</span><span class="sxs-lookup"><span data-stu-id="16451-156">Example</span></span>  
 <span data-ttu-id="16451-157">下面的示例读取文本文件中的所有行。</span><span class="sxs-lookup"><span data-stu-id="16451-157">The following example reads all lines in a text file.</span></span> <span data-ttu-id="16451-158">方法打开文件并<xref:System.IO.StreamReader>返回读取字符的。 <xref:System.IO.File.OpenText%2A></span><span class="sxs-lookup"><span data-stu-id="16451-158">The <xref:System.IO.File.OpenText%2A> method opens the file and returns a <xref:System.IO.StreamReader> that reads the characters.</span></span> <span data-ttu-id="16451-159">在条件中<xref:System.IO.StreamReader.Peek%2A> , 的方法`StreamReader`确定是否有任何其他字符。 `Do...Loop`</span><span class="sxs-lookup"><span data-stu-id="16451-159">In the `Do...Loop` condition, the <xref:System.IO.StreamReader.Peek%2A> method of the `StreamReader` determines whether there are any additional characters.</span></span>  
  
 [!code-vb[VbVbalrStatements#134](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class10.vb#134)]  
  
## <a name="see-also"></a><span data-ttu-id="16451-160">请参阅</span><span class="sxs-lookup"><span data-stu-id="16451-160">See also</span></span>

- [<span data-ttu-id="16451-161">循环结构</span><span class="sxs-lookup"><span data-stu-id="16451-161">Loop Structures</span></span>](../../../visual-basic/programming-guide/language-features/control-flow/loop-structures.md)
- [<span data-ttu-id="16451-162">For...Next 语句</span><span class="sxs-lookup"><span data-stu-id="16451-162">For...Next Statement</span></span>](../../../visual-basic/language-reference/statements/for-next-statement.md)
- [<span data-ttu-id="16451-163">Boolean 数据类型</span><span class="sxs-lookup"><span data-stu-id="16451-163">Boolean Data Type</span></span>](../../../visual-basic/language-reference/data-types/boolean-data-type.md)
- [<span data-ttu-id="16451-164">嵌套的控件结构</span><span class="sxs-lookup"><span data-stu-id="16451-164">Nested Control Structures</span></span>](../../../visual-basic/programming-guide/language-features/control-flow/nested-control-structures.md)
- [<span data-ttu-id="16451-165">Exit 语句</span><span class="sxs-lookup"><span data-stu-id="16451-165">Exit Statement</span></span>](../../../visual-basic/language-reference/statements/exit-statement.md)
- [<span data-ttu-id="16451-166">While...End While 语句</span><span class="sxs-lookup"><span data-stu-id="16451-166">While...End While Statement</span></span>](../../../visual-basic/language-reference/statements/while-end-while-statement.md)
