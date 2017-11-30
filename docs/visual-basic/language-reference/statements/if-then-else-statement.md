---
title: "If...Then...Else 语句 (Visual Basic)"
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
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
caps.latest.revision: "29"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 898b72055345e88ca35f805de211c0c57cd74200
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="ifthenelse-statement-visual-basic"></a><span data-ttu-id="7919f-102">If...Then...Else 语句 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="7919f-102">If...Then...Else Statement (Visual Basic)</span></span>
<span data-ttu-id="7919f-103">根据表达式的值有条件地执行一组语句。</span><span class="sxs-lookup"><span data-stu-id="7919f-103">Conditionally executes a group of statements, depending on the value of an expression.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7919f-104">语法</span><span class="sxs-lookup"><span data-stu-id="7919f-104">Syntax</span></span>  
  
```  
' Multiple-line syntax:  
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
  
## <a name="parts"></a><span data-ttu-id="7919f-105">部件</span><span class="sxs-lookup"><span data-stu-id="7919f-105">Parts</span></span>  
 `condition`  
 <span data-ttu-id="7919f-106">必需。</span><span class="sxs-lookup"><span data-stu-id="7919f-106">Required.</span></span> <span data-ttu-id="7919f-107">表达式。</span><span class="sxs-lookup"><span data-stu-id="7919f-107">Expression.</span></span> <span data-ttu-id="7919f-108">计算结果必须为`True`或`False`，或隐式转换为的数据类型`Boolean`。</span><span class="sxs-lookup"><span data-stu-id="7919f-108">Must evaluate to `True` or `False`, or to a data type that is implicitly convertible to `Boolean`.</span></span>  
  
 <span data-ttu-id="7919f-109">如果表达式为[可以为 Null](../../../visual-basic/programming-guide/language-features/data-types/nullable-value-types.md) `Boolean`变量计算结果为[执行任何操作](../../../visual-basic/language-reference/nothing.md)，条件将被视为的表达式不是`True`，和`Else`块是执行。</span><span class="sxs-lookup"><span data-stu-id="7919f-109">If the expression is a [Nullable](../../../visual-basic/programming-guide/language-features/data-types/nullable-value-types.md)`Boolean` variable that evaluates to [Nothing](../../../visual-basic/language-reference/nothing.md), the condition is treated as if the expression is not `True`, and the `Else` block is executed.</span></span>  
  
 `Then`  
 <span data-ttu-id="7919f-110">中的单行语法; 所需在多个行的语法中可选。</span><span class="sxs-lookup"><span data-stu-id="7919f-110">Required in the single-line syntax; optional in the multiple-line syntax.</span></span>  
  
 `statements`  
 <span data-ttu-id="7919f-111">可选。</span><span class="sxs-lookup"><span data-stu-id="7919f-111">Optional.</span></span> <span data-ttu-id="7919f-112">一个或多个语句以下`If`...`Then`如果将执行该`condition`计算结果为`True`。</span><span class="sxs-lookup"><span data-stu-id="7919f-112">One or more statements following `If`...`Then` that are executed if `condition` evaluates to `True`.</span></span>  
  
 `elseifcondition`  
 <span data-ttu-id="7919f-113">如果存在`ElseIf`存在。</span><span class="sxs-lookup"><span data-stu-id="7919f-113">Required if `ElseIf` is present.</span></span> <span data-ttu-id="7919f-114">表达式。</span><span class="sxs-lookup"><span data-stu-id="7919f-114">Expression.</span></span> <span data-ttu-id="7919f-115">计算结果必须为`True`或`False`，或隐式转换为的数据类型`Boolean`。</span><span class="sxs-lookup"><span data-stu-id="7919f-115">Must evaluate to `True` or `False`, or to a data type that is implicitly convertible to `Boolean`.</span></span>  
  
 `elseifstatements`  
 <span data-ttu-id="7919f-116">可选。</span><span class="sxs-lookup"><span data-stu-id="7919f-116">Optional.</span></span> <span data-ttu-id="7919f-117">一个或多个语句以下`ElseIf`...`Then`如果将执行该`elseifcondition`计算结果为`True`。</span><span class="sxs-lookup"><span data-stu-id="7919f-117">One or more statements following `ElseIf`...`Then` that are executed if `elseifcondition` evaluates to `True`.</span></span>  
  
 `elsestatements`  
 <span data-ttu-id="7919f-118">可选。</span><span class="sxs-lookup"><span data-stu-id="7919f-118">Optional.</span></span> <span data-ttu-id="7919f-119">如果不再具有以前执行的一个或多个语句`condition`或`elseifcondition`表达式计算结果为`True`。</span><span class="sxs-lookup"><span data-stu-id="7919f-119">One or more statements that are executed if no previous `condition` or `elseifcondition` expression evaluates to `True`.</span></span>  
  
 `End If`  
 <span data-ttu-id="7919f-120">终止`If`...`Then`...`Else`块。</span><span class="sxs-lookup"><span data-stu-id="7919f-120">Terminates the `If`...`Then`...`Else` block.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="7919f-121">备注</span><span class="sxs-lookup"><span data-stu-id="7919f-121">Remarks</span></span>  
  
## <a name="multiple-line-syntax"></a><span data-ttu-id="7919f-122">多个行语法</span><span class="sxs-lookup"><span data-stu-id="7919f-122">Multiple-Line Syntax</span></span>  
 <span data-ttu-id="7919f-123">当`If`...`Then`...`Else`遇到语句时，`condition`测试。</span><span class="sxs-lookup"><span data-stu-id="7919f-123">When an `If`...`Then`...`Else` statement is encountered, `condition` is tested.</span></span> <span data-ttu-id="7919f-124">如果`condition`是`True`，后面的语句`Then`执行。</span><span class="sxs-lookup"><span data-stu-id="7919f-124">If `condition` is `True`, the statements following `Then` are executed.</span></span> <span data-ttu-id="7919f-125">如果`condition`是`False`，每个`ElseIf`语句 （如果有的话） 顺序计算。</span><span class="sxs-lookup"><span data-stu-id="7919f-125">If `condition` is `False`, each `ElseIf` statement (if there are any) is evaluated in order.</span></span> <span data-ttu-id="7919f-126">当`True``elseifcondition`找到，紧跟在关联的语句`ElseIf`执行。</span><span class="sxs-lookup"><span data-stu-id="7919f-126">When a `True``elseifcondition` is found, the statements immediately following the associated `ElseIf` are executed.</span></span> <span data-ttu-id="7919f-127">如果没有`elseifcondition`计算结果为`True`，或者是否有任何`ElseIf`，以下语句`Else`执行。</span><span class="sxs-lookup"><span data-stu-id="7919f-127">If no `elseifcondition` evaluates to `True`, or if there are no `ElseIf` statements, the statements following `Else` are executed.</span></span> <span data-ttu-id="7919f-128">执行后面的语句后`Then`， `ElseIf`，或`Else`，继续后面的语句执行`End If`。</span><span class="sxs-lookup"><span data-stu-id="7919f-128">After executing the statements following `Then`, `ElseIf`, or `Else`, execution continues with the statement following `End If`.</span></span>  
  
 <span data-ttu-id="7919f-129">`ElseIf`和`Else`子句都是可选。</span><span class="sxs-lookup"><span data-stu-id="7919f-129">The `ElseIf` and `Else` clauses are both optional.</span></span> <span data-ttu-id="7919f-130">你可以作为许多`ElseIf`根据需要`If`...`Then`...`Else`语句，但不是`ElseIf`子句可以出现后`Else`子句。</span><span class="sxs-lookup"><span data-stu-id="7919f-130">You can have as many `ElseIf` clauses as you want in an `If`...`Then`...`Else` statement, but no `ElseIf` clause can appear after an `Else` clause.</span></span> <span data-ttu-id="7919f-131">`If`...`Then`...`Else`语句可以相互嵌套。</span><span class="sxs-lookup"><span data-stu-id="7919f-131">`If`...`Then`...`Else` statements can be nested within each other.</span></span>  
  
 <span data-ttu-id="7919f-132">在多个行语法中，`If`语句必须是第一个行的唯一语句。</span><span class="sxs-lookup"><span data-stu-id="7919f-132">In the multiple-line syntax, the `If` statement must be the only statement on the first line.</span></span> <span data-ttu-id="7919f-133">`ElseIf`， `Else`，和`End If`语句仅可以前面的行标签。</span><span class="sxs-lookup"><span data-stu-id="7919f-133">The `ElseIf`, `Else`, and `End If` statements can be preceded only by a line label.</span></span> <span data-ttu-id="7919f-134">`If`...`Then`...`Else`块必须以结束`End If`语句。</span><span class="sxs-lookup"><span data-stu-id="7919f-134">The `If`...`Then`...`Else` block must end with an `End If` statement.</span></span>  
  
> [!TIP]
>  <span data-ttu-id="7919f-135">[选择...Case 语句](../../../visual-basic/language-reference/statements/select-case-statement.md)计算有几个可能值的单个表达式时可能会更有用。</span><span class="sxs-lookup"><span data-stu-id="7919f-135">The [Select...Case Statement](../../../visual-basic/language-reference/statements/select-case-statement.md) might be more useful when you evaluate a single expression that has several possible values.</span></span>  
  
## <a name="single-line-syntax"></a><span data-ttu-id="7919f-136">单行语法</span><span class="sxs-lookup"><span data-stu-id="7919f-136">Single-Line Syntax</span></span>  
 <span data-ttu-id="7919f-137">对于较短的简单测试，可以使用的单行语法。</span><span class="sxs-lookup"><span data-stu-id="7919f-137">You can use the single-line syntax for short, simple tests.</span></span> <span data-ttu-id="7919f-138">但是，多个行语法提供了多个结构和灵活性，并通常可以更轻松地读取、 维护和调试。</span><span class="sxs-lookup"><span data-stu-id="7919f-138">However, the multiple-line syntax provides more structure and flexibility and is usually easier to read, maintain, and debug.</span></span>  
  
 <span data-ttu-id="7919f-139">哪些如下所示`Then`关键字将检查以确定语句是否是单线条`If`。</span><span class="sxs-lookup"><span data-stu-id="7919f-139">What follows the `Then` keyword is examined to determine whether a statement is a single-line `If`.</span></span> <span data-ttu-id="7919f-140">如果注释之外的任何内容出现在`Then`上同一行中，该语句将被视为单线条`If`语句。</span><span class="sxs-lookup"><span data-stu-id="7919f-140">If anything other than a comment appears after `Then` on the same line, the statement is treated as a single-line `If` statement.</span></span> <span data-ttu-id="7919f-141">如果`Then`不存在，它必须是多个行的开头`If`...`Then`...`Else`.</span><span class="sxs-lookup"><span data-stu-id="7919f-141">If `Then` is absent, it must be the start of a multiple-line `If`...`Then`...`Else`.</span></span>  
  
 <span data-ttu-id="7919f-142">在单行语法中，你可以有多个语句的结果作为执行`If`...`Then`决策。</span><span class="sxs-lookup"><span data-stu-id="7919f-142">In the single-line syntax, you can have multiple statements executed as the result of an `If`...`Then` decision.</span></span> <span data-ttu-id="7919f-143">所有语句必须是同一行上，并且由冒号分隔。</span><span class="sxs-lookup"><span data-stu-id="7919f-143">All statements must be on the same line and be separated by colons.</span></span>  
  
## <a name="example"></a><span data-ttu-id="7919f-144">示例</span><span class="sxs-lookup"><span data-stu-id="7919f-144">Example</span></span>  
 <span data-ttu-id="7919f-145">下面的示例演示如何使用的多个行语法`If`...`Then`...`Else`语句。</span><span class="sxs-lookup"><span data-stu-id="7919f-145">The following example illustrates the use of the multiple-line syntax of the `If`...`Then`...`Else` statement.</span></span>  
  
 [!code-vb[VbVbalrStatements#101](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/if-then-else-statement_1.vb)]  
  
## <a name="example"></a><span data-ttu-id="7919f-146">示例</span><span class="sxs-lookup"><span data-stu-id="7919f-146">Example</span></span>  
 <span data-ttu-id="7919f-147">下面的示例包含嵌套`If`...`Then`...`Else`语句。</span><span class="sxs-lookup"><span data-stu-id="7919f-147">The following example contains nested `If`...`Then`...`Else` statements.</span></span>  
  
 [!code-vb[VbVbalrStatements#102](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/if-then-else-statement_2.vb)]  
  
## <a name="example"></a><span data-ttu-id="7919f-148">示例</span><span class="sxs-lookup"><span data-stu-id="7919f-148">Example</span></span>  
 <span data-ttu-id="7919f-149">下面的示例演示如何使用单线条语法。</span><span class="sxs-lookup"><span data-stu-id="7919f-149">The following example illustrates the use of the single-line syntax.</span></span>  
  
 [!code-vb[VbVbalrStatements#103](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/if-then-else-statement_3.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="7919f-150">另请参阅</span><span class="sxs-lookup"><span data-stu-id="7919f-150">See Also</span></span>  
 <xref:Microsoft.VisualBasic.Interaction.Choose%2A>  
 <xref:Microsoft.VisualBasic.Interaction.Switch%2A>  
 [<span data-ttu-id="7919f-151">#If...Then...#Else 指令</span><span class="sxs-lookup"><span data-stu-id="7919f-151">#If...Then...#Else Directives</span></span>](../../../visual-basic/language-reference/directives/if-then-else-directives.md)  
 [<span data-ttu-id="7919f-152">Select...Case 语句</span><span class="sxs-lookup"><span data-stu-id="7919f-152">Select...Case Statement</span></span>](../../../visual-basic/language-reference/statements/select-case-statement.md)  
 [<span data-ttu-id="7919f-153">嵌套的控件结构</span><span class="sxs-lookup"><span data-stu-id="7919f-153">Nested Control Structures</span></span>](../../../visual-basic/programming-guide/language-features/control-flow/nested-control-structures.md)  
 [<span data-ttu-id="7919f-154">决策结构</span><span class="sxs-lookup"><span data-stu-id="7919f-154">Decision Structures</span></span>](../../../visual-basic/programming-guide/language-features/control-flow/decision-structures.md)  
 [<span data-ttu-id="7919f-155">在 Visual Basic 中的逻辑和按位运算符</span><span class="sxs-lookup"><span data-stu-id="7919f-155">Logical and Bitwise Operators in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/operators-and-expressions/logical-and-bitwise-operators.md)  
 [<span data-ttu-id="7919f-156">If 运算符</span><span class="sxs-lookup"><span data-stu-id="7919f-156">If Operator</span></span>](../../../visual-basic/language-reference/operators/if-operator.md)
