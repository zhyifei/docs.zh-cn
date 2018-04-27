---
title: If...Then...Else 语句 (Visual Basic)
ms.date: 04/16/2018
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: conceptual
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
caps.latest.revision: 29
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 1080a17cfcc493175c1e2f3527837030b4254bc2
ms.sourcegitcommit: 2e8acae16ae802f2d6d04e3ce0a6dbf04e476513
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/18/2018
---
# <a name="ifthenelse-statement-visual-basic"></a><span data-ttu-id="40984-102">If...Then...Else 语句 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="40984-102">If...Then...Else Statement (Visual Basic)</span></span>
<span data-ttu-id="40984-103">根据表达式的值有条件地执行一组语句。</span><span class="sxs-lookup"><span data-stu-id="40984-103">Conditionally executes a group of statements, depending on the value of an expression.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="40984-104">语法</span><span class="sxs-lookup"><span data-stu-id="40984-104">Syntax</span></span>  
  
```  
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

## <a name="quick-links-to-example-code"></a><span data-ttu-id="40984-105">指向代码示例的快速链接</span><span class="sxs-lookup"><span data-stu-id="40984-105">Quick links to example code</span></span>

<span data-ttu-id="40984-106">本文包括几个示例演示使用`If`...`Then`...`Else`语句：</span><span class="sxs-lookup"><span data-stu-id="40984-106">This article includes several examples that illustrate uses of the `If`...`Then`...`Else` statement:</span></span>

* [<span data-ttu-id="40984-107">多行的语法示例</span><span class="sxs-lookup"><span data-stu-id="40984-107">Multiline syntax example</span></span>](#multi-line)
* [<span data-ttu-id="40984-108">嵌套的语法示例</span><span class="sxs-lookup"><span data-stu-id="40984-108">Nested syntax example</span></span>](#nested)
* [<span data-ttu-id="40984-109">单行语法示例</span><span class="sxs-lookup"><span data-stu-id="40984-109">Single-line syntax example</span></span>](#single-line)

## <a name="parts"></a><span data-ttu-id="40984-110">部件</span><span class="sxs-lookup"><span data-stu-id="40984-110">Parts</span></span>  
 `condition`  
 <span data-ttu-id="40984-111">必须的。</span><span class="sxs-lookup"><span data-stu-id="40984-111">Required.</span></span> <span data-ttu-id="40984-112">表达式。</span><span class="sxs-lookup"><span data-stu-id="40984-112">Expression.</span></span> <span data-ttu-id="40984-113">计算结果必须为`True`或`False`，或隐式转换为的数据类型`Boolean`。</span><span class="sxs-lookup"><span data-stu-id="40984-113">Must evaluate to `True` or `False`, or to a data type that is implicitly convertible to `Boolean`.</span></span>  
  
 <span data-ttu-id="40984-114">如果表达式为[可以为 Null](../../../visual-basic/programming-guide/language-features/data-types/nullable-value-types.md) `Boolean`变量计算结果为[执行任何操作](../../../visual-basic/language-reference/nothing.md)，条件将被视为表达式是`False`和`Else`执行块。</span><span class="sxs-lookup"><span data-stu-id="40984-114">If the expression is a [Nullable](../../../visual-basic/programming-guide/language-features/data-types/nullable-value-types.md) `Boolean` variable that evaluates to [Nothing](../../../visual-basic/language-reference/nothing.md), the condition is treated as if the expression is `False` and the `Else` block is executed.</span></span>  
  
 `Then`  
 <span data-ttu-id="40984-115">中的单行语法; 所需在多行的语法中可选。</span><span class="sxs-lookup"><span data-stu-id="40984-115">Required in the single-line syntax; optional in the multiline syntax.</span></span>  
  
 `statements`  
 <span data-ttu-id="40984-116">可选。</span><span class="sxs-lookup"><span data-stu-id="40984-116">Optional.</span></span> <span data-ttu-id="40984-117">一个或多个语句以下`If`...`Then`如果将执行该`condition`计算结果为`True`。</span><span class="sxs-lookup"><span data-stu-id="40984-117">One or more statements following `If`...`Then` that are executed if `condition` evaluates to `True`.</span></span>  
  
 `elseifcondition`  
 <span data-ttu-id="40984-118">如果存在`ElseIf`存在。</span><span class="sxs-lookup"><span data-stu-id="40984-118">Required if `ElseIf` is present.</span></span> <span data-ttu-id="40984-119">表达式。</span><span class="sxs-lookup"><span data-stu-id="40984-119">Expression.</span></span> <span data-ttu-id="40984-120">计算结果必须为`True`或`False`，或隐式转换为的数据类型`Boolean`。</span><span class="sxs-lookup"><span data-stu-id="40984-120">Must evaluate to `True` or `False`, or to a data type that is implicitly convertible to `Boolean`.</span></span>  
  
 `elseifstatements`  
 <span data-ttu-id="40984-121">可选。</span><span class="sxs-lookup"><span data-stu-id="40984-121">Optional.</span></span> <span data-ttu-id="40984-122">一个或多个语句以下`ElseIf`...`Then`如果将执行该`elseifcondition`计算结果为`True`。</span><span class="sxs-lookup"><span data-stu-id="40984-122">One or more statements following `ElseIf`...`Then` that are executed if `elseifcondition` evaluates to `True`.</span></span>  
  
 `elsestatements`  
 <span data-ttu-id="40984-123">可选。</span><span class="sxs-lookup"><span data-stu-id="40984-123">Optional.</span></span> <span data-ttu-id="40984-124">如果不再具有以前执行的一个或多个语句`condition`或`elseifcondition`表达式计算结果为`True`。</span><span class="sxs-lookup"><span data-stu-id="40984-124">One or more statements that are executed if no previous `condition` or `elseifcondition` expression evaluates to `True`.</span></span>  
  
 `End If`  
 <span data-ttu-id="40984-125">终止的多行版本`If`...`Then`...`Else`块。</span><span class="sxs-lookup"><span data-stu-id="40984-125">Terminates the multiline version of `If`...`Then`...`Else` block.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="40984-126">备注</span><span class="sxs-lookup"><span data-stu-id="40984-126">Remarks</span></span>  
  
### <a name="multiline-syntax"></a><span data-ttu-id="40984-127">多行的语法</span><span class="sxs-lookup"><span data-stu-id="40984-127">Multiline syntax</span></span>  
 <span data-ttu-id="40984-128">当`If`...`Then`...`Else`遇到语句时，`condition`测试。</span><span class="sxs-lookup"><span data-stu-id="40984-128">When an `If`...`Then`...`Else` statement is encountered, `condition` is tested.</span></span> <span data-ttu-id="40984-129">如果`condition`是`True`，后面的语句`Then`执行。</span><span class="sxs-lookup"><span data-stu-id="40984-129">If `condition` is `True`, the statements following `Then` are executed.</span></span> <span data-ttu-id="40984-130">如果`condition`是`False`，每个`ElseIf`语句 （如果有的话） 顺序计算。</span><span class="sxs-lookup"><span data-stu-id="40984-130">If `condition` is `False`, each `ElseIf` statement (if there are any) is evaluated in order.</span></span> <span data-ttu-id="40984-131">当`True``elseifcondition`找到，紧跟在关联的语句`ElseIf`执行。</span><span class="sxs-lookup"><span data-stu-id="40984-131">When a `True` `elseifcondition` is found, the statements immediately following the associated `ElseIf` are executed.</span></span> <span data-ttu-id="40984-132">如果没有`elseifcondition`计算结果为`True`，或者是否有任何`ElseIf`，以下语句`Else`执行。</span><span class="sxs-lookup"><span data-stu-id="40984-132">If no `elseifcondition` evaluates to `True`, or if there are no `ElseIf` statements, the statements following `Else` are executed.</span></span> <span data-ttu-id="40984-133">执行后面的语句后`Then`， `ElseIf`，或`Else`，继续后面的语句执行`End If`。</span><span class="sxs-lookup"><span data-stu-id="40984-133">After executing the statements following `Then`, `ElseIf`, or `Else`, execution continues with the statement following `End If`.</span></span>  
  
 <span data-ttu-id="40984-134">`ElseIf`和`Else`子句都是可选。</span><span class="sxs-lookup"><span data-stu-id="40984-134">The `ElseIf` and `Else` clauses are both optional.</span></span> <span data-ttu-id="40984-135">你可以作为许多`ElseIf`根据需要`If`...`Then`...`Else`语句，但不是`ElseIf`子句可以出现后`Else`子句。</span><span class="sxs-lookup"><span data-stu-id="40984-135">You can have as many `ElseIf` clauses as you want in an `If`...`Then`...`Else` statement, but no `ElseIf` clause can appear after an `Else` clause.</span></span> <span data-ttu-id="40984-136">`If`...`Then`...`Else`语句可以相互嵌套。</span><span class="sxs-lookup"><span data-stu-id="40984-136">`If`...`Then`...`Else` statements can be nested within each other.</span></span>  
  
 <span data-ttu-id="40984-137">在多行的语法中，`If`语句必须是第一个行的唯一语句。</span><span class="sxs-lookup"><span data-stu-id="40984-137">In the multiline syntax, the `If` statement must be the only statement on the first line.</span></span> <span data-ttu-id="40984-138">`ElseIf`， `Else`，和`End If`语句仅可以前面的行标签。</span><span class="sxs-lookup"><span data-stu-id="40984-138">The `ElseIf`, `Else`, and `End If` statements can be preceded only by a line label.</span></span> <span data-ttu-id="40984-139">`If`...`Then`...`Else`块必须以结束`End If`语句。</span><span class="sxs-lookup"><span data-stu-id="40984-139">The `If`...`Then`...`Else` block must end with an `End If` statement.</span></span>  
  
> [!TIP]
>  <span data-ttu-id="40984-140">[选择...Case 语句](../../../visual-basic/language-reference/statements/select-case-statement.md)计算有几个可能值的单个表达式时可能会更有用。</span><span class="sxs-lookup"><span data-stu-id="40984-140">The [Select...Case Statement](../../../visual-basic/language-reference/statements/select-case-statement.md) might be more useful when you evaluate a single expression that has several possible values.</span></span>  
  
### <a name="single-line-syntax"></a><span data-ttu-id="40984-141">单行语法</span><span class="sxs-lookup"><span data-stu-id="40984-141">Single-Line syntax</span></span>  
 <span data-ttu-id="40984-142">可以针对单个条件，代码使用的单行语法执行如果为 true。</span><span class="sxs-lookup"><span data-stu-id="40984-142">You can use the single-line syntax for a single condition with code to execute if it's true.</span></span> <span data-ttu-id="40984-143">但是，多个行语法提供了多个结构和灵活性，并且可以更轻松地读取、 维护和调试。</span><span class="sxs-lookup"><span data-stu-id="40984-143">However, the multiple-line syntax provides more structure and flexibility and is easier to read, maintain, and debug.</span></span>  
  
 <span data-ttu-id="40984-144">哪些如下所示`Then`关键字将检查以确定语句是否是单线条`If`。</span><span class="sxs-lookup"><span data-stu-id="40984-144">What follows the `Then` keyword is examined to determine whether a statement is a single-line `If`.</span></span> <span data-ttu-id="40984-145">如果注释之外的任何内容出现在`Then`上同一行中，该语句将被视为单线条`If`语句。</span><span class="sxs-lookup"><span data-stu-id="40984-145">If anything other than a comment appears after `Then` on the same line, the statement is treated as a single-line `If` statement.</span></span> <span data-ttu-id="40984-146">如果`Then`不存在，它必须是多个行的开头`If`...`Then`...`Else`.</span><span class="sxs-lookup"><span data-stu-id="40984-146">If `Then` is absent, it must be the start of a multiple-line `If`...`Then`...`Else`.</span></span>  
  
 <span data-ttu-id="40984-147">在单行语法中，你可以有多个语句的结果作为执行`If`...`Then`决策。</span><span class="sxs-lookup"><span data-stu-id="40984-147">In the single-line syntax, you can have multiple statements executed as the result of an `If`...`Then` decision.</span></span> <span data-ttu-id="40984-148">所有语句必须是同一行上，并且由冒号分隔。</span><span class="sxs-lookup"><span data-stu-id="40984-148">All statements must be on the same line and be separated by colons.</span></span>  

## <a name="multiline-syntax-example"></a><span data-ttu-id="40984-149">多行的语法示例</span><span class="sxs-lookup"><span data-stu-id="40984-149">Multiline syntax example</span></span>

<a name="multi-line"></a>
 
 <span data-ttu-id="40984-150">下面的示例演示如何使用的多行的语法`If`...`Then`...`Else`语句。</span><span class="sxs-lookup"><span data-stu-id="40984-150">The following example illustrates the use of the multiline syntax of the `If`...`Then`...`Else` statement.</span></span>  
  
 [!code-vb[VbVbalrStatements#101](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/if-then-else-statement_1.vb?highlight=11,14,17,19)]

## <a name="nested-syntax-example"></a><span data-ttu-id="40984-151">嵌套的语法示例</span><span class="sxs-lookup"><span data-stu-id="40984-151">Nested syntax example</span></span>

<a name="nested"></a>

 <span data-ttu-id="40984-152">下面的示例包含嵌套`If`...`Then`...`Else`语句。</span><span class="sxs-lookup"><span data-stu-id="40984-152">The following example contains nested `If`...`Then`...`Else` statements.</span></span>  
  
 [!code-vb[VbVbalrStatements#102](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/if-then-else-statement_2.vb?highlight=14,15,17,19,20,21,23,25,26,28)]

## <a name="single-line-syntax-example"></a><span data-ttu-id="40984-153">单行语法示例</span><span class="sxs-lookup"><span data-stu-id="40984-153">Single-Line syntax example</span></span>
  
<a name="single-line"></a> <span data-ttu-id="40984-154">下面的示例演示如何使用单线条语法。</span><span class="sxs-lookup"><span data-stu-id="40984-154">The following example illustrates the use of the single-line syntax.</span></span>  
  
 [!code-vb[VbVbalrStatements#103](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/if-then-else-statement_3.vb?highlight=18)]
  
## <a name="see-also"></a><span data-ttu-id="40984-155">请参阅</span><span class="sxs-lookup"><span data-stu-id="40984-155">See also</span></span>  
 <xref:Microsoft.VisualBasic.Interaction.Choose%2A>  
 <xref:Microsoft.VisualBasic.Interaction.Switch%2A>  
 [<span data-ttu-id="40984-156">#If...Then...#Else 指令</span><span class="sxs-lookup"><span data-stu-id="40984-156">#If...Then...#Else Directives</span></span>](../../../visual-basic/language-reference/directives/if-then-else-directives.md)  
 [<span data-ttu-id="40984-157">Select...Case 语句</span><span class="sxs-lookup"><span data-stu-id="40984-157">Select...Case Statement</span></span>](../../../visual-basic/language-reference/statements/select-case-statement.md)  
 [<span data-ttu-id="40984-158">嵌套的控件结构</span><span class="sxs-lookup"><span data-stu-id="40984-158">Nested Control Structures</span></span>](../../../visual-basic/programming-guide/language-features/control-flow/nested-control-structures.md)  
 [<span data-ttu-id="40984-159">决策结构</span><span class="sxs-lookup"><span data-stu-id="40984-159">Decision Structures</span></span>](../../../visual-basic/programming-guide/language-features/control-flow/decision-structures.md)  
 [<span data-ttu-id="40984-160">在 Visual Basic 中的逻辑和按位运算符</span><span class="sxs-lookup"><span data-stu-id="40984-160">Logical and Bitwise Operators in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/operators-and-expressions/logical-and-bitwise-operators.md)  
 [<span data-ttu-id="40984-161">If 运算符</span><span class="sxs-lookup"><span data-stu-id="40984-161">If Operator</span></span>](../../../visual-basic/language-reference/operators/if-operator.md)
