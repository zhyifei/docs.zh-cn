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
ms.openlocfilehash: 3ff3d67f38f510b798da3e470de066cff1e98f29
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/18/2019
ms.locfileid: "58826036"
---
# <a name="doloop-statement-visual-basic"></a><span data-ttu-id="2c466-102">Do...Loop 语句 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="2c466-102">Do...Loop Statement (Visual Basic)</span></span>
<span data-ttu-id="2c466-103">重复块语句时`Boolean`是条件`True`或直到条件变为`True`。</span><span class="sxs-lookup"><span data-stu-id="2c466-103">Repeats a block of statements while a `Boolean` condition is `True` or until the condition becomes `True`.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2c466-104">语法</span><span class="sxs-lookup"><span data-stu-id="2c466-104">Syntax</span></span>  
  
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
  
## <a name="parts"></a><span data-ttu-id="2c466-105">部件</span><span class="sxs-lookup"><span data-stu-id="2c466-105">Parts</span></span>  
  
|<span data-ttu-id="2c466-106">术语</span><span class="sxs-lookup"><span data-stu-id="2c466-106">Term</span></span>|<span data-ttu-id="2c466-107">定义</span><span class="sxs-lookup"><span data-stu-id="2c466-107">Definition</span></span>|  
|---|---|  
|`Do`|<span data-ttu-id="2c466-108">必需。</span><span class="sxs-lookup"><span data-stu-id="2c466-108">Required.</span></span> <span data-ttu-id="2c466-109">启动的定义`Do`循环。</span><span class="sxs-lookup"><span data-stu-id="2c466-109">Starts the definition of the `Do` loop.</span></span>|  
|`While`|<span data-ttu-id="2c466-110">必选项（除非使用了 `Until`）。</span><span class="sxs-lookup"><span data-stu-id="2c466-110">Required unless `Until` is used.</span></span> <span data-ttu-id="2c466-111">重复循环，直到`condition`是`False`。</span><span class="sxs-lookup"><span data-stu-id="2c466-111">Repeat the loop until `condition` is `False`.</span></span>|  
|`Until`|<span data-ttu-id="2c466-112">必选项（除非使用了 `While`）。</span><span class="sxs-lookup"><span data-stu-id="2c466-112">Required unless `While` is used.</span></span> <span data-ttu-id="2c466-113">重复循环，直到`condition`是`True`。</span><span class="sxs-lookup"><span data-stu-id="2c466-113">Repeat the loop until `condition` is `True`.</span></span>|  
|`condition`|<span data-ttu-id="2c466-114">可选。</span><span class="sxs-lookup"><span data-stu-id="2c466-114">Optional.</span></span> <span data-ttu-id="2c466-115">`Boolean` 表达式。</span><span class="sxs-lookup"><span data-stu-id="2c466-115">`Boolean` expression.</span></span> <span data-ttu-id="2c466-116">如果`condition`是`Nothing`，Visual Basic 会将其视为`False`。</span><span class="sxs-lookup"><span data-stu-id="2c466-116">If `condition` is `Nothing`, Visual Basic treats it as `False`.</span></span>|  
|`statements`|<span data-ttu-id="2c466-117">可选。</span><span class="sxs-lookup"><span data-stu-id="2c466-117">Optional.</span></span> <span data-ttu-id="2c466-118">一个或多个语句时，或直到，重复`condition`是`True`。</span><span class="sxs-lookup"><span data-stu-id="2c466-118">One or more statements that are repeated while, or until, `condition` is `True`.</span></span>|  
|`Continue Do`|<span data-ttu-id="2c466-119">可选。</span><span class="sxs-lookup"><span data-stu-id="2c466-119">Optional.</span></span> <span data-ttu-id="2c466-120">将控制转移到的下一个迭代`Do`循环。</span><span class="sxs-lookup"><span data-stu-id="2c466-120">Transfers control to the next iteration of the `Do` loop.</span></span>|  
|`Exit Do`|<span data-ttu-id="2c466-121">可选。</span><span class="sxs-lookup"><span data-stu-id="2c466-121">Optional.</span></span> <span data-ttu-id="2c466-122">将控制的转移`Do`循环。</span><span class="sxs-lookup"><span data-stu-id="2c466-122">Transfers control out of the `Do` loop.</span></span>|  
|`Loop`|<span data-ttu-id="2c466-123">必需。</span><span class="sxs-lookup"><span data-stu-id="2c466-123">Required.</span></span> <span data-ttu-id="2c466-124">终止的定义`Do`循环。</span><span class="sxs-lookup"><span data-stu-id="2c466-124">Terminates the definition of the `Do` loop.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="2c466-125">备注</span><span class="sxs-lookup"><span data-stu-id="2c466-125">Remarks</span></span>  
 <span data-ttu-id="2c466-126">使用`Do...Loop`结构，当你想要重复执行一系列语句无限的次数，直到满足某个条件。</span><span class="sxs-lookup"><span data-stu-id="2c466-126">Use a `Do...Loop` structure when you want to repeat a set of statements an indefinite number of times, until a condition is satisfied.</span></span> <span data-ttu-id="2c466-127">如果你想要重复执行语句，一定的时间，[为...下一条语句](../../../visual-basic/language-reference/statements/for-next-statement.md)通常是更好的选择。</span><span class="sxs-lookup"><span data-stu-id="2c466-127">If you want to repeat the statements a set number of times, the [For...Next Statement](../../../visual-basic/language-reference/statements/for-next-statement.md) is usually a better choice.</span></span>  
  
 <span data-ttu-id="2c466-128">你可以使用`While`或`Until`来指定`condition`，但不可同时使用两者。</span><span class="sxs-lookup"><span data-stu-id="2c466-128">You can use either `While` or `Until` to specify `condition`, but not both.</span></span>  
  
 <span data-ttu-id="2c466-129">你可以测试`condition`仅一次的开头或循环的末尾。</span><span class="sxs-lookup"><span data-stu-id="2c466-129">You can test `condition` only one time, at either the start or the end of the loop.</span></span> <span data-ttu-id="2c466-130">如果测试`condition`循环的开头 (在`Do`语句)，该循环可能无法运行它甚至一次。</span><span class="sxs-lookup"><span data-stu-id="2c466-130">If you test `condition` at the start of the loop (in the `Do` statement), the loop might not run even one time.</span></span> <span data-ttu-id="2c466-131">如果测试在循环末尾 (在`Loop`语句)，循环始终运行至少一次。</span><span class="sxs-lookup"><span data-stu-id="2c466-131">If you test at the end of the loop (in the `Loop` statement), the loop always runs at least one time.</span></span>  
  
 <span data-ttu-id="2c466-132">条件通常从两个值的比较结果，但它可以是任何表达式的计算结果为[布尔数据类型](../../../visual-basic/language-reference/data-types/boolean-data-type.md)值 (`True`或`False`)。</span><span class="sxs-lookup"><span data-stu-id="2c466-132">The condition usually results from a comparison of two values, but it can be any expression that evaluates to a [Boolean Data Type](../../../visual-basic/language-reference/data-types/boolean-data-type.md) value (`True` or `False`).</span></span> <span data-ttu-id="2c466-133">这包括其他数据类型，例如，已转换为数值类型的值`Boolean`。</span><span class="sxs-lookup"><span data-stu-id="2c466-133">This includes values of other data types, such as numeric types, that have been converted to `Boolean`.</span></span>  
  
 <span data-ttu-id="2c466-134">可以嵌套`Do`放置另一个循环内的循环。</span><span class="sxs-lookup"><span data-stu-id="2c466-134">You can nest `Do` loops by putting one loop within another.</span></span> <span data-ttu-id="2c466-135">此外可以嵌套不同类型的控制结构彼此内。</span><span class="sxs-lookup"><span data-stu-id="2c466-135">You can also nest different kinds of control structures within each other.</span></span> <span data-ttu-id="2c466-136">有关详细信息，请参阅[嵌套控制结构](../../../visual-basic/programming-guide/language-features/control-flow/nested-control-structures.md)。</span><span class="sxs-lookup"><span data-stu-id="2c466-136">For more information, see [Nested Control Structures](../../../visual-basic/programming-guide/language-features/control-flow/nested-control-structures.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="2c466-137">`Do...Loop`结构为您提供了更大的灵活性比[时...结束 While 语句](../../../visual-basic/language-reference/statements/while-end-while-statement.md)因为它使您可以决定是否要结束循环时`condition`停止正在`True`或第一次为`True`。</span><span class="sxs-lookup"><span data-stu-id="2c466-137">The `Do...Loop` structure gives you more flexibility than the [While...End While Statement](../../../visual-basic/language-reference/statements/while-end-while-statement.md) because it enables you to decide whether to end the loop when `condition` stops being `True` or when it first becomes `True`.</span></span> <span data-ttu-id="2c466-138">它还使您可以测试`condition`的开头或循环的末尾。</span><span class="sxs-lookup"><span data-stu-id="2c466-138">It also enables you to test `condition` at either the start or the end of the loop.</span></span>  
  
## <a name="exit-do"></a><span data-ttu-id="2c466-139">退出 Do</span><span class="sxs-lookup"><span data-stu-id="2c466-139">Exit Do</span></span>  
 <span data-ttu-id="2c466-140">[Exit Do](../../../visual-basic/language-reference/statements/exit-statement.md)语句可以提供了一种退出`Do…Loop`。</span><span class="sxs-lookup"><span data-stu-id="2c466-140">The [Exit Do](../../../visual-basic/language-reference/statements/exit-statement.md) statement can provide an alternative way to exit a `Do…Loop`.</span></span> <span data-ttu-id="2c466-141">`Exit Do` 立即将控制转移到后面的语句`Loop`语句。</span><span class="sxs-lookup"><span data-stu-id="2c466-141">`Exit Do` transfers control immediately to the statement that follows the `Loop` statement.</span></span>  
  
 <span data-ttu-id="2c466-142">`Exit Do` 通常用于计算某些条件，例如，在之后`If...Then...Else`结构。</span><span class="sxs-lookup"><span data-stu-id="2c466-142">`Exit Do` is often used after some condition is evaluated, for example in an `If...Then...Else` structure.</span></span> <span data-ttu-id="2c466-143">您可能需要退出循环，如果检测到导致其不必要或无法继续循环访问，例如错误的值或终止请求的条件。</span><span class="sxs-lookup"><span data-stu-id="2c466-143">You might want to exit a loop if you detect a condition that makes it unnecessary or impossible to continue iterating, such as an erroneous value or a termination request.</span></span> <span data-ttu-id="2c466-144">一种用途`Exit Do`是要测试一个条件，可能会导致*无限循环*，这是一个循环，无法运行大型或甚至无限数量的次数。</span><span class="sxs-lookup"><span data-stu-id="2c466-144">One use of `Exit Do` is to test for a condition that could cause an *endless loop*, which is a loop that could run a large or even infinite number of times.</span></span> <span data-ttu-id="2c466-145">可以使用`Exit Do`来退出循环。</span><span class="sxs-lookup"><span data-stu-id="2c466-145">You can use `Exit Do` to escape the loop.</span></span>  
  
 <span data-ttu-id="2c466-146">可以包含任意数量的`Exit Do`中的任意位置语句`Do…Loop`。</span><span class="sxs-lookup"><span data-stu-id="2c466-146">You can include any number of `Exit Do` statements anywhere in a `Do…Loop`.</span></span>  
  
 <span data-ttu-id="2c466-147">当使用内嵌套`Do`循环，`Exit Do`控制权从最里面的循环和到下一个较高级别的嵌套。</span><span class="sxs-lookup"><span data-stu-id="2c466-147">When used within nested `Do` loops, `Exit Do` transfers control out of the innermost loop and into the next higher level of nesting.</span></span>  
  
## <a name="example"></a><span data-ttu-id="2c466-148">示例</span><span class="sxs-lookup"><span data-stu-id="2c466-148">Example</span></span>  
 <span data-ttu-id="2c466-149">在以下示例中，在循环中的语句继续运行，直到`index`变量是否大于 10。</span><span class="sxs-lookup"><span data-stu-id="2c466-149">In the following example, the statements in the loop continue to run until the `index` variable is greater than 10.</span></span> <span data-ttu-id="2c466-150">`Until`子句在循环的末尾处。</span><span class="sxs-lookup"><span data-stu-id="2c466-150">The `Until` clause is at the end of the loop.</span></span>  
  
 [!code-vb[VbVbalrStatements#131](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class10.vb#131)]  
  
## <a name="example"></a><span data-ttu-id="2c466-151">示例</span><span class="sxs-lookup"><span data-stu-id="2c466-151">Example</span></span>  
 <span data-ttu-id="2c466-152">下面的示例使用`While`子句而不是`Until`子句，和`condition`的循环，而不是结束时开始时测试。</span><span class="sxs-lookup"><span data-stu-id="2c466-152">The following example uses a `While` clause instead of an `Until` clause, and `condition` is tested at the start of the loop instead of at the end.</span></span>  
  
 [!code-vb[VbVbalrStatements#132](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class10.vb#132)]  
  
## <a name="example"></a><span data-ttu-id="2c466-153">示例</span><span class="sxs-lookup"><span data-stu-id="2c466-153">Example</span></span>  
 <span data-ttu-id="2c466-154">在以下示例中，`condition`停止该循环时`index`变量是否大于 100。</span><span class="sxs-lookup"><span data-stu-id="2c466-154">In the following example, `condition` stops the loop when the `index` variable is greater than 100.</span></span> <span data-ttu-id="2c466-155">`If`语句在循环中，但是，导致`Exit Do`语句停止循环索引变量是否大于 10 时。</span><span class="sxs-lookup"><span data-stu-id="2c466-155">The `If` statement in the loop, however, causes the `Exit Do` statement to stop the loop when the index variable is greater than 10.</span></span>  
  
 [!code-vb[VbVbalrStatements#133](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class10.vb#133)]  
  
## <a name="example"></a><span data-ttu-id="2c466-156">示例</span><span class="sxs-lookup"><span data-stu-id="2c466-156">Example</span></span>  
 <span data-ttu-id="2c466-157">下面的示例读取在文本文件中的所有行。</span><span class="sxs-lookup"><span data-stu-id="2c466-157">The following example reads all lines in a text file.</span></span> <span data-ttu-id="2c466-158"><xref:System.IO.File.OpenText%2A>方法打开文件并返回<xref:System.IO.StreamReader>读取字符。</span><span class="sxs-lookup"><span data-stu-id="2c466-158">The <xref:System.IO.File.OpenText%2A> method opens the file and returns a <xref:System.IO.StreamReader> that reads the characters.</span></span> <span data-ttu-id="2c466-159">在中`Do...Loop`条件，请<xref:System.IO.StreamReader.Peek%2A>方法的`StreamReader`确定是否存在任何其他字符。</span><span class="sxs-lookup"><span data-stu-id="2c466-159">In the `Do...Loop` condition, the <xref:System.IO.StreamReader.Peek%2A> method of the `StreamReader` determines whether there are any additional characters.</span></span>  
  
 [!code-vb[VbVbalrStatements#134](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class10.vb#134)]  
  
## <a name="see-also"></a><span data-ttu-id="2c466-160">请参阅</span><span class="sxs-lookup"><span data-stu-id="2c466-160">See also</span></span>

- [<span data-ttu-id="2c466-161">循环结构</span><span class="sxs-lookup"><span data-stu-id="2c466-161">Loop Structures</span></span>](../../../visual-basic/programming-guide/language-features/control-flow/loop-structures.md)
- [<span data-ttu-id="2c466-162">For...Next 语句</span><span class="sxs-lookup"><span data-stu-id="2c466-162">For...Next Statement</span></span>](../../../visual-basic/language-reference/statements/for-next-statement.md)
- [<span data-ttu-id="2c466-163">Boolean 数据类型</span><span class="sxs-lookup"><span data-stu-id="2c466-163">Boolean Data Type</span></span>](../../../visual-basic/language-reference/data-types/boolean-data-type.md)
- [<span data-ttu-id="2c466-164">嵌套的控件结构</span><span class="sxs-lookup"><span data-stu-id="2c466-164">Nested Control Structures</span></span>](../../../visual-basic/programming-guide/language-features/control-flow/nested-control-structures.md)
- [<span data-ttu-id="2c466-165">Exit 语句</span><span class="sxs-lookup"><span data-stu-id="2c466-165">Exit Statement</span></span>](../../../visual-basic/language-reference/statements/exit-statement.md)
- [<span data-ttu-id="2c466-166">While...End While 语句</span><span class="sxs-lookup"><span data-stu-id="2c466-166">While...End While Statement</span></span>](../../../visual-basic/language-reference/statements/while-end-while-statement.md)
