---
title: If...Then...Else 语句
ms.date: 04/16/2018
f1_keywords:
- vb.ElseIf
- vb.Then
- vb.If
- vb.EndIf
helpviewer_keywords:
- ElseIf statement [Visual Basic], If...Then...Else
- Then statement [Visual Basic], If...Then...Else
- control flow [Visual Basic], branching
- execution [Visual Basic], conditional
- TypeOf...Is expression, and If...Then...Else statements
- If...Then...Else statements
- If statement [Visual Basic], If...Then...Else
- If statement [Visual Basic]
- Is operator [Visual Basic], in If...Then...Else statements
- If Operator [Visual Basic]
- branching [Visual Basic], conditional
- If function [Visual Basic], and If...Then...Else statements
- Else statement [Visual Basic]
ms.assetid: 790068a2-1307-4e28-8a72-be5ebda099e9
ms.openlocfilehash: f505755caeb9cc3cfeeb1ba83b6de15f48314103
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/22/2019
ms.locfileid: "74351160"
---
# <a name="ifthenelse-statement-visual-basic"></a><span data-ttu-id="0ef25-102">If...Then...Else 语句 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="0ef25-102">If...Then...Else Statement (Visual Basic)</span></span>

<span data-ttu-id="0ef25-103">根据表达式的值有条件地执行一组语句。</span><span class="sxs-lookup"><span data-stu-id="0ef25-103">Conditionally executes a group of statements, depending on the value of an expression.</span></span>

## <a name="syntax"></a><span data-ttu-id="0ef25-104">语法</span><span class="sxs-lookup"><span data-stu-id="0ef25-104">Syntax</span></span>

```vb
' Multiline syntax:
If condition [ Then ]
    [ statements ]
[ ElseIf elseifcondition [ Then ]
    [ elseifstatements ] ]
[ Else
    [ elsestatements ] ]
End If

' Single-line syntax:
If condition Then [ statements ] [ Else [ elsestatements ] ]
```

## <a name="quick-links-to-example-code"></a><span data-ttu-id="0ef25-105">示例代码的快速链接</span><span class="sxs-lookup"><span data-stu-id="0ef25-105">Quick links to example code</span></span>

<span data-ttu-id="0ef25-106">本文包含一些示例，这些示例演示了 `If`...`Then`...`Else` 语句的用法：</span><span class="sxs-lookup"><span data-stu-id="0ef25-106">This article includes several examples that illustrate uses of the `If`...`Then`...`Else` statement:</span></span>

- [<span data-ttu-id="0ef25-107">多行语法示例</span><span class="sxs-lookup"><span data-stu-id="0ef25-107">Multiline syntax example</span></span>](#multi-line)
- [<span data-ttu-id="0ef25-108">嵌套语法示例</span><span class="sxs-lookup"><span data-stu-id="0ef25-108">Nested syntax example</span></span>](#nested)
- [<span data-ttu-id="0ef25-109">单行语法示例</span><span class="sxs-lookup"><span data-stu-id="0ef25-109">Single-line syntax example</span></span>](#single-line)

## <a name="parts"></a><span data-ttu-id="0ef25-110">部件</span><span class="sxs-lookup"><span data-stu-id="0ef25-110">Parts</span></span>

`condition` \
<span data-ttu-id="0ef25-111">必需。</span><span class="sxs-lookup"><span data-stu-id="0ef25-111">Required.</span></span> <span data-ttu-id="0ef25-112">表达式.</span><span class="sxs-lookup"><span data-stu-id="0ef25-112">Expression.</span></span> <span data-ttu-id="0ef25-113">的计算结果必须为 `True` 或 `False`或可隐式转换为 `Boolean`的数据类型。</span><span class="sxs-lookup"><span data-stu-id="0ef25-113">Must evaluate to `True` or `False`, or to a data type that is implicitly convertible to `Boolean`.</span></span>

<span data-ttu-id="0ef25-114">如果表达式是可[为 null 的可为 null](../../../visual-basic/programming-guide/language-features/data-types/nullable-value-types.md)的 `Boolean`[变量，则](../../../visual-basic/language-reference/nothing.md)将条件视为 `False`的表达式，如果存在 `ElseIf` 块，则将对其进行计算; 如果存在，则执行 `Else` 块。</span><span class="sxs-lookup"><span data-stu-id="0ef25-114">If the expression is a [Nullable](../../../visual-basic/programming-guide/language-features/data-types/nullable-value-types.md) `Boolean` variable that evaluates to [Nothing](../../../visual-basic/language-reference/nothing.md), the condition is treated as if the expression is `False`, and the `ElseIf` blocks are evaluated if they exist, or the `Else` block is executed if it exists.</span></span>

`Then` \
<span data-ttu-id="0ef25-115">在单行语法中为必需;在多行语法中是可选的。</span><span class="sxs-lookup"><span data-stu-id="0ef25-115">Required in the single-line syntax; optional in the multiline syntax.</span></span>

`statements` \
<span data-ttu-id="0ef25-116">可选。</span><span class="sxs-lookup"><span data-stu-id="0ef25-116">Optional.</span></span> <span data-ttu-id="0ef25-117">后面`If`的一个或多个语句 ...如果计算结果为`Then`，则执行。 `condition` `True`</span><span class="sxs-lookup"><span data-stu-id="0ef25-117">One or more statements following `If`...`Then` that are executed if `condition` evaluates to `True`.</span></span>

`elseifcondition` \
<span data-ttu-id="0ef25-118">如果 `ElseIf` 存在，则为必需。</span><span class="sxs-lookup"><span data-stu-id="0ef25-118">Required if `ElseIf` is present.</span></span> <span data-ttu-id="0ef25-119">表达式.</span><span class="sxs-lookup"><span data-stu-id="0ef25-119">Expression.</span></span> <span data-ttu-id="0ef25-120">的计算结果必须为 `True` 或 `False`或可隐式转换为 `Boolean`的数据类型。</span><span class="sxs-lookup"><span data-stu-id="0ef25-120">Must evaluate to `True` or `False`, or to a data type that is implicitly convertible to `Boolean`.</span></span>

`elseifstatements` \
<span data-ttu-id="0ef25-121">可选。</span><span class="sxs-lookup"><span data-stu-id="0ef25-121">Optional.</span></span> <span data-ttu-id="0ef25-122">后面`ElseIf`的一个或多个语句 ...如果计算结果为`Then`，则执行。 `elseifcondition` `True`</span><span class="sxs-lookup"><span data-stu-id="0ef25-122">One or more statements following `ElseIf`...`Then` that are executed if `elseifcondition` evaluates to `True`.</span></span>

`elsestatements` \
<span data-ttu-id="0ef25-123">可选。</span><span class="sxs-lookup"><span data-stu-id="0ef25-123">Optional.</span></span> <span data-ttu-id="0ef25-124">如果以前的 `condition` 或 `elseifcondition` 表达式的计算结果不为 `True`，则执行的一个或多个语句。</span><span class="sxs-lookup"><span data-stu-id="0ef25-124">One or more statements that are executed if no previous `condition` or `elseifcondition` expression evaluates to `True`.</span></span>

`End If` \
<span data-ttu-id="0ef25-125">终止 `If`...`Then`...`Else` 块的多行版本。</span><span class="sxs-lookup"><span data-stu-id="0ef25-125">Terminates the multiline version of `If`...`Then`...`Else` block.</span></span>

## <a name="remarks"></a><span data-ttu-id="0ef25-126">备注</span><span class="sxs-lookup"><span data-stu-id="0ef25-126">Remarks</span></span>

### <a name="multiline-syntax"></a><span data-ttu-id="0ef25-127">多行语法</span><span class="sxs-lookup"><span data-stu-id="0ef25-127">Multiline syntax</span></span>

<span data-ttu-id="0ef25-128">如果遇到 `If``Then`...`Else` 语句，则 `condition` 进行测试。</span><span class="sxs-lookup"><span data-stu-id="0ef25-128">When an `If`...`Then`...`Else` statement is encountered, `condition` is tested.</span></span> <span data-ttu-id="0ef25-129">如果 `True``condition`，则将执行 `Then` 后面的语句。</span><span class="sxs-lookup"><span data-stu-id="0ef25-129">If `condition` is `True`, the statements following `Then` are executed.</span></span> <span data-ttu-id="0ef25-130">如果 `False``condition`，则按顺序计算每个 `ElseIf` 语句（如果有）。</span><span class="sxs-lookup"><span data-stu-id="0ef25-130">If `condition` is `False`, each `ElseIf` statement (if there are any) is evaluated in order.</span></span> <span data-ttu-id="0ef25-131">如果找到 `True` `elseifcondition`，则将执行紧随关联的 `ElseIf` 后面的语句。</span><span class="sxs-lookup"><span data-stu-id="0ef25-131">When a `True` `elseifcondition` is found, the statements immediately following the associated `ElseIf` are executed.</span></span> <span data-ttu-id="0ef25-132">如果 `elseifcondition` 的计算结果不为 `True`，或者没有 `ElseIf` 语句，则将执行 `Else` 后的语句。</span><span class="sxs-lookup"><span data-stu-id="0ef25-132">If no `elseifcondition` evaluates to `True`, or if there are no `ElseIf` statements, the statements following `Else` are executed.</span></span> <span data-ttu-id="0ef25-133">执行以下语句后 `Then`、`ElseIf`或 `Else`，将继续执行 `End If`后的语句。</span><span class="sxs-lookup"><span data-stu-id="0ef25-133">After executing the statements following `Then`, `ElseIf`, or `Else`, execution continues with the statement following `End If`.</span></span>

<span data-ttu-id="0ef25-134">`ElseIf` 和 `Else` 子句都是可选的。</span><span class="sxs-lookup"><span data-stu-id="0ef25-134">The `ElseIf` and `Else` clauses are both optional.</span></span> <span data-ttu-id="0ef25-135">您可以根据需要在 `If`...`Then`...`Else` 语句中包含任意数量的 `ElseIf` 子句，但 `ElseIf` 子句之后不能出现 `Else` 子句。</span><span class="sxs-lookup"><span data-stu-id="0ef25-135">You can have as many `ElseIf` clauses as you want in an `If`...`Then`...`Else` statement, but no `ElseIf` clause can appear after an `Else` clause.</span></span> <span data-ttu-id="0ef25-136">`If`...`Then``Else` 语句可以相互嵌套。</span><span class="sxs-lookup"><span data-stu-id="0ef25-136">`If`...`Then`...`Else` statements can be nested within each other.</span></span>

<span data-ttu-id="0ef25-137">在多行语法中，`If` 语句必须是第一行中的唯一语句。</span><span class="sxs-lookup"><span data-stu-id="0ef25-137">In the multiline syntax, the `If` statement must be the only statement on the first line.</span></span> <span data-ttu-id="0ef25-138">`ElseIf`、`Else`和 `End If` 语句前面只能有一个行标签。</span><span class="sxs-lookup"><span data-stu-id="0ef25-138">The `ElseIf`, `Else`, and `End If` statements can be preceded only by a line label.</span></span> <span data-ttu-id="0ef25-139">`If``Then`...`Else` 块必须以 `End If` 语句结束。</span><span class="sxs-lookup"><span data-stu-id="0ef25-139">The `If`...`Then`...`Else` block must end with an `End If` statement.</span></span>

> [!TIP]
> <span data-ttu-id="0ef25-140">[Select .。。](../../../visual-basic/language-reference/statements/select-case-statement.md)当你评估具有多个可能值的单个表达式时，Case 语句可能更有用。</span><span class="sxs-lookup"><span data-stu-id="0ef25-140">The [Select...Case Statement](../../../visual-basic/language-reference/statements/select-case-statement.md) might be more useful when you evaluate a single expression that has several possible values.</span></span>

### <a name="single-line-syntax"></a><span data-ttu-id="0ef25-141">单行语法</span><span class="sxs-lookup"><span data-stu-id="0ef25-141">Single-Line syntax</span></span>

<span data-ttu-id="0ef25-142">对于一个条件，可以使用单行语法，如果该条件为 true，则执行代码。</span><span class="sxs-lookup"><span data-stu-id="0ef25-142">You can use the single-line syntax for a single condition with code to execute if it's true.</span></span> <span data-ttu-id="0ef25-143">不过，多行语法提供更多的结构和灵活性，更易于读取、维护和调试。</span><span class="sxs-lookup"><span data-stu-id="0ef25-143">However, the multiple-line syntax provides more structure and flexibility and is easier to read, maintain, and debug.</span></span>

<span data-ttu-id="0ef25-144">将检查 `Then` 关键字后面的内容，以确定语句是否为单行 `If`。</span><span class="sxs-lookup"><span data-stu-id="0ef25-144">What follows the `Then` keyword is examined to determine whether a statement is a single-line `If`.</span></span> <span data-ttu-id="0ef25-145">如果在同一行 `Then` 之后出现注释以外的任何内容，则该语句将被视为单行 `If` 语句。</span><span class="sxs-lookup"><span data-stu-id="0ef25-145">If anything other than a comment appears after `Then` on the same line, the statement is treated as a single-line `If` statement.</span></span> <span data-ttu-id="0ef25-146">如果 `Then` 不存在，则它必须是多行 `If`...`Then``Else`的开头。</span><span class="sxs-lookup"><span data-stu-id="0ef25-146">If `Then` is absent, it must be the start of a multiple-line `If`...`Then`...`Else`.</span></span>

<span data-ttu-id="0ef25-147">在单行语法中，可以将多个语句作为 `If``Then` 决策的结果来执行。</span><span class="sxs-lookup"><span data-stu-id="0ef25-147">In the single-line syntax, you can have multiple statements executed as the result of an `If`...`Then` decision.</span></span> <span data-ttu-id="0ef25-148">所有语句必须位于同一行上，并由冒号分隔。</span><span class="sxs-lookup"><span data-stu-id="0ef25-148">All statements must be on the same line and be separated by colons.</span></span>

## <a name="multiline-syntax-example"></a><span data-ttu-id="0ef25-149">多行语法示例</span><span class="sxs-lookup"><span data-stu-id="0ef25-149">Multiline syntax example</span></span>

<a name="multi-line"></a>

<span data-ttu-id="0ef25-150">下面的示例演示如何使用 `If`...`Then`...`Else` 语句的多行语法。</span><span class="sxs-lookup"><span data-stu-id="0ef25-150">The following example illustrates the use of the multiline syntax of the `If`...`Then`...`Else` statement.</span></span>

[!code-vb[VbVbalrStatements#101](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class6.vb#101)]

## <a name="nested-syntax-example"></a><span data-ttu-id="0ef25-151">嵌套语法示例</span><span class="sxs-lookup"><span data-stu-id="0ef25-151">Nested syntax example</span></span>

<a name="nested"></a>

<span data-ttu-id="0ef25-152">下面的示例包含嵌套的 `If`...`Then`...`Else` 语句。</span><span class="sxs-lookup"><span data-stu-id="0ef25-152">The following example contains nested `If`...`Then`...`Else` statements.</span></span>

[!code-vb[VbVbalrStatements#102](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class6.vb#102)]

## <a name="single-line-syntax-example"></a><span data-ttu-id="0ef25-153">单行语法示例</span><span class="sxs-lookup"><span data-stu-id="0ef25-153">Single-Line syntax example</span></span>

<a name="single-line"></a><span data-ttu-id="0ef25-154">下面的示例演示单行语法的用法。</span><span class="sxs-lookup"><span data-stu-id="0ef25-154">The following example illustrates the use of the single-line syntax.</span></span>

[!code-vb[VbVbalrStatements#103](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class6.vb#103)]

## <a name="see-also"></a><span data-ttu-id="0ef25-155">另请参阅</span><span class="sxs-lookup"><span data-stu-id="0ef25-155">See also</span></span>

- <xref:Microsoft.VisualBasic.Interaction.Choose%2A>
- <xref:Microsoft.VisualBasic.Interaction.Switch%2A>
- [<span data-ttu-id="0ef25-156">#If...Then...#Else 指令</span><span class="sxs-lookup"><span data-stu-id="0ef25-156">#If...Then...#Else Directives</span></span>](../../../visual-basic/language-reference/directives/if-then-else-directives.md)
- [<span data-ttu-id="0ef25-157">Select...Case 语句</span><span class="sxs-lookup"><span data-stu-id="0ef25-157">Select...Case Statement</span></span>](../../../visual-basic/language-reference/statements/select-case-statement.md)
- [<span data-ttu-id="0ef25-158">嵌套的控件结构</span><span class="sxs-lookup"><span data-stu-id="0ef25-158">Nested Control Structures</span></span>](../../../visual-basic/programming-guide/language-features/control-flow/nested-control-structures.md)
- [<span data-ttu-id="0ef25-159">决策结构</span><span class="sxs-lookup"><span data-stu-id="0ef25-159">Decision Structures</span></span>](../../../visual-basic/programming-guide/language-features/control-flow/decision-structures.md)
- [<span data-ttu-id="0ef25-160">Visual Basic 中的逻辑运算符和位运算符</span><span class="sxs-lookup"><span data-stu-id="0ef25-160">Logical and Bitwise Operators in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/operators-and-expressions/logical-and-bitwise-operators.md)
- [<span data-ttu-id="0ef25-161">If 运算符</span><span class="sxs-lookup"><span data-stu-id="0ef25-161">If Operator</span></span>](../../../visual-basic/language-reference/operators/if-operator.md)
