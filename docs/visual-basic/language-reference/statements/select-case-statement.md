---
title: Select...Case 语句
ms.date: 07/20/2015
f1_keywords:
- vb.Select
- vb.Case
helpviewer_keywords:
- Select statement [Visual Basic]
- Case statement [Visual Basic]
- Select...Case statements
- conditional statements [Visual Basic], Select Case
- control flow [Visual Basic], branching
- Else keyword [Visual Basic], in Select...Case statements
- execution [Visual Basic], conditional
- To keyword [Visual Basic], in Select...Case statements
- Select Case statement [Visual Basic], Select...Case
- Select statement [Visual Basic], Select...Case
- Is operator [Visual Basic], in Select...Case statements
- branching [Visual Basic], conditional
- Case Else statement [Visual Basic], Select...Case
- End keyword [Visual Basic], Select Case statements
- Case statement [Visual Basic], Select...Case
ms.assetid: 68877b65-5419-4bf0-a465-20cd0e4c7d44
ms.openlocfilehash: 4dddfe5fbf7092c911291ffc6841e76f8c2748e9
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/22/2019
ms.locfileid: "74352831"
---
# <a name="selectcase-statement-visual-basic"></a><span data-ttu-id="4f7e3-102">Select...Case 语句 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="4f7e3-102">Select...Case Statement (Visual Basic)</span></span>
<span data-ttu-id="4f7e3-103">根据表达式的值运行若干组语句中的一个。</span><span class="sxs-lookup"><span data-stu-id="4f7e3-103">Runs one of several groups of statements, depending on the value of an expression.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4f7e3-104">语法</span><span class="sxs-lookup"><span data-stu-id="4f7e3-104">Syntax</span></span>  
  
```vb  
Select [ Case ] testexpression  
    [ Case expressionlist  
        [ statements ] ]  
    [ Case Else  
        [ elsestatements ] ]  
End Select  
```  
  
## <a name="parts"></a><span data-ttu-id="4f7e3-105">部件</span><span class="sxs-lookup"><span data-stu-id="4f7e3-105">Parts</span></span>  
  
|<span data-ttu-id="4f7e3-106">术语</span><span class="sxs-lookup"><span data-stu-id="4f7e3-106">Term</span></span>|<span data-ttu-id="4f7e3-107">Definition</span><span class="sxs-lookup"><span data-stu-id="4f7e3-107">Definition</span></span>|  
|---|---|  
|`testexpression`|<span data-ttu-id="4f7e3-108">必需。</span><span class="sxs-lookup"><span data-stu-id="4f7e3-108">Required.</span></span> <span data-ttu-id="4f7e3-109">表达式.</span><span class="sxs-lookup"><span data-stu-id="4f7e3-109">Expression.</span></span> <span data-ttu-id="4f7e3-110">的计算结果必须为基本数据类型之一（`Boolean`、`Byte`、`Char`、`Date`、`Double`、`Decimal`、`Integer`、`Long`、`Object`、`SByte`、`Short`、`Single`、`String`、`UInteger`、`ULong`和 `UShort`）。</span><span class="sxs-lookup"><span data-stu-id="4f7e3-110">Must evaluate to one of the elementary data types (`Boolean`, `Byte`, `Char`, `Date`, `Double`, `Decimal`, `Integer`, `Long`, `Object`, `SByte`, `Short`, `Single`, `String`, `UInteger`, `ULong`, and `UShort`).</span></span>|  
|`expressionlist`|<span data-ttu-id="4f7e3-111">在 `Case` 语句中是必需的。</span><span class="sxs-lookup"><span data-stu-id="4f7e3-111">Required in a `Case` statement.</span></span> <span data-ttu-id="4f7e3-112">表示 `testexpression`的匹配值的表达式子句的列表。</span><span class="sxs-lookup"><span data-stu-id="4f7e3-112">List of expression clauses representing match values for `testexpression`.</span></span> <span data-ttu-id="4f7e3-113">多个表达式子句之间用逗号分隔。</span><span class="sxs-lookup"><span data-stu-id="4f7e3-113">Multiple expression clauses are separated by commas.</span></span> <span data-ttu-id="4f7e3-114">每个子句可以采用以下形式之一：</span><span class="sxs-lookup"><span data-stu-id="4f7e3-114">Each clause can take one of the following forms:</span></span><br /><br /> <span data-ttu-id="4f7e3-115">-   *表达式*2 *`To` 2*</span><span class="sxs-lookup"><span data-stu-id="4f7e3-115">-   *expression1* `To` *expression2*</span></span><br /><span data-ttu-id="4f7e3-116">-[`Is`] *.comparisonoperator* *表达式*</span><span class="sxs-lookup"><span data-stu-id="4f7e3-116">-   [ `Is` ] *comparisonoperator* *expression*</span></span><br /><span data-ttu-id="4f7e3-117">-   *表达式*</span><span class="sxs-lookup"><span data-stu-id="4f7e3-117">-   *expression*</span></span><br /><br /> <span data-ttu-id="4f7e3-118">使用 `To` 关键字指定 `testexpression`的匹配值范围的边界。</span><span class="sxs-lookup"><span data-stu-id="4f7e3-118">Use the `To` keyword to specify the boundaries of a range of match values for `testexpression`.</span></span> <span data-ttu-id="4f7e3-119">`expression1` 的值必须小于或等于 `expression2`的值。</span><span class="sxs-lookup"><span data-stu-id="4f7e3-119">The value of `expression1` must be less than or equal to the value of `expression2`.</span></span><br /><br /> <span data-ttu-id="4f7e3-120">将 `Is` 关键字与比较运算符（`=`、`<>`、`<`、`<=`、`>`或 `>=`）结合使用，以指定 `testexpression`匹配值的限制。</span><span class="sxs-lookup"><span data-stu-id="4f7e3-120">Use the `Is` keyword with a comparison operator (`=`, `<>`, `<`, `<=`, `>`, or `>=`) to specify a restriction on the match values for `testexpression`.</span></span> <span data-ttu-id="4f7e3-121">如果未提供 `Is` 关键字，则自动将其插入 *.comparisonoperator*之前。</span><span class="sxs-lookup"><span data-stu-id="4f7e3-121">If the `Is` keyword is not supplied, it is automatically inserted before *comparisonoperator*.</span></span><br /><br /> <span data-ttu-id="4f7e3-122">仅指定 `expression` 的窗体被视为 `Is` 窗体的特殊情况，其中 *.comparisonoperator*是等号（`=`）。</span><span class="sxs-lookup"><span data-stu-id="4f7e3-122">The form specifying only `expression` is treated as a special case of the `Is` form where *comparisonoperator* is the equal sign (`=`).</span></span> <span data-ttu-id="4f7e3-123">此形式的计算结果为 `testexpression` = `expression`。</span><span class="sxs-lookup"><span data-stu-id="4f7e3-123">This form is evaluated as `testexpression` = `expression`.</span></span><br /><br /> <span data-ttu-id="4f7e3-124">`expressionlist` 中的表达式可以是任何数据类型，前提是它们可隐式转换为 `testexpression` 的类型，并且相应的 `comparisonoperator` 对于它与之一起使用的两个类型都有效。</span><span class="sxs-lookup"><span data-stu-id="4f7e3-124">The expressions in `expressionlist` can be of any data type, provided they are implicitly convertible to the type of `testexpression` and the appropriate `comparisonoperator` is valid for the two types it is being used with.</span></span>|  
|`statements`|<span data-ttu-id="4f7e3-125">可选。</span><span class="sxs-lookup"><span data-stu-id="4f7e3-125">Optional.</span></span> <span data-ttu-id="4f7e3-126">如果 `testexpression` 与 `expressionlist`中的任何子句匹配，则 `Case` 运行的一个或多个语句。</span><span class="sxs-lookup"><span data-stu-id="4f7e3-126">One or more statements following `Case` that run if `testexpression` matches any clause in `expressionlist`.</span></span>|  
|`elsestatements`|<span data-ttu-id="4f7e3-127">可选。</span><span class="sxs-lookup"><span data-stu-id="4f7e3-127">Optional.</span></span> <span data-ttu-id="4f7e3-128">如果 `testexpression` 与任何 `Case` 语句的 `expressionlist` 中的任何子句都不匹配，则在运行 `Case Else` 后面的一个或多个语句。</span><span class="sxs-lookup"><span data-stu-id="4f7e3-128">One or more statements following `Case Else` that run if `testexpression` does not match any clause in the `expressionlist` of any of the `Case` statements.</span></span>|  
|`End Select`|<span data-ttu-id="4f7e3-129">终止`Case` 构造 `Select`的定义。</span><span class="sxs-lookup"><span data-stu-id="4f7e3-129">Terminates the definition of the `Select`...`Case` construction.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="4f7e3-130">备注</span><span class="sxs-lookup"><span data-stu-id="4f7e3-130">Remarks</span></span>  
 <span data-ttu-id="4f7e3-131">如果 `testexpression` 与任何 `Case` `expressionlist` 子句匹配，则遵循该 `Case` 语句的语句将运行到下一个 `Case`、`Case Else`或 `End Select` 语句之后。</span><span class="sxs-lookup"><span data-stu-id="4f7e3-131">If `testexpression` matches any `Case` `expressionlist` clause, the statements following that `Case` statement run up to the next `Case`, `Case Else`, or `End Select` statement.</span></span> <span data-ttu-id="4f7e3-132">然后，控件传递到 `End Select`后面的语句。</span><span class="sxs-lookup"><span data-stu-id="4f7e3-132">Control then passes to the statement following `End Select`.</span></span> <span data-ttu-id="4f7e3-133">如果 `testexpression` 在多个 `Case` 子句中匹配 `expressionlist` 子句，则仅运行第一个匹配后的语句。</span><span class="sxs-lookup"><span data-stu-id="4f7e3-133">If `testexpression` matches an `expressionlist` clause in more than one `Case` clause, only the statements following the first match run.</span></span>  
  
 <span data-ttu-id="4f7e3-134">如果在任何其他 `Case` 语句的 `testexpression` 和 `expressionlist` 子句之间找不到匹配项，则使用 `Case Else` 语句引入要运行的 `elsestatements`。</span><span class="sxs-lookup"><span data-stu-id="4f7e3-134">The `Case Else` statement is used to introduce the `elsestatements` to run if no match is found between the `testexpression` and an `expressionlist` clause in any of the other `Case` statements.</span></span> <span data-ttu-id="4f7e3-135">虽然不是必需的，但最好在 `Select Case` 构造中使用 `Case Else` 语句来处理不可预见的 `testexpression` 值。</span><span class="sxs-lookup"><span data-stu-id="4f7e3-135">Although not required, it is a good idea to have a `Case Else` statement in your `Select Case` construction to handle unforeseen `testexpression` values.</span></span> <span data-ttu-id="4f7e3-136">如果没有 `Case` `expressionlist` 子句匹配 `testexpression`，并且没有 `Case Else` 语句，控制将传递到 `End Select`后面的语句。</span><span class="sxs-lookup"><span data-stu-id="4f7e3-136">If no `Case` `expressionlist` clause matches `testexpression` and there is no `Case Else` statement, control passes to the statement following `End Select`.</span></span>  
  
 <span data-ttu-id="4f7e3-137">可以在每个 `Case` 子句中使用多个表达式或范围。</span><span class="sxs-lookup"><span data-stu-id="4f7e3-137">You can use multiple expressions or ranges in each `Case` clause.</span></span> <span data-ttu-id="4f7e3-138">例如，下面的行是有效的。</span><span class="sxs-lookup"><span data-stu-id="4f7e3-138">For example, the following line is valid.</span></span>  
  
 `Case 1 To 4, 7 To 9, 11, 13, Is > maxNumber`  
  
> [!NOTE]
> <span data-ttu-id="4f7e3-139">`Case` 和 `Case Else` 语句中使用的 `Is` 关键字与[Is 运算符](../../../visual-basic/language-reference/operators/is-operator.md)不同，后者用于对象引用比较。</span><span class="sxs-lookup"><span data-stu-id="4f7e3-139">The `Is` keyword used in the `Case` and `Case Else` statements is not the same as the [Is Operator](../../../visual-basic/language-reference/operators/is-operator.md), which is used for object reference comparison.</span></span>  
  
 <span data-ttu-id="4f7e3-140">您可以为字符串指定范围和多个表达式。</span><span class="sxs-lookup"><span data-stu-id="4f7e3-140">You can specify ranges and multiple expressions for character strings.</span></span> <span data-ttu-id="4f7e3-141">在下面的示例中，`Case` 匹配任何完全等于 "苹果" 的字符串，其值介于 "螺母" 和 "soup" 之间按字母顺序排序，或者包含与 `testItem`的当前值完全相同的值。</span><span class="sxs-lookup"><span data-stu-id="4f7e3-141">In the following example, `Case` matches any string that is exactly equal to "apples", has a value between "nuts" and "soup" in alphabetical order, or contains the exact same value as the current value of `testItem`.</span></span>  
  
 `Case "apples", "nuts" To "soup", testItem`  
  
 <span data-ttu-id="4f7e3-142">`Option Compare` 的设置可能会影响字符串比较。</span><span class="sxs-lookup"><span data-stu-id="4f7e3-142">The setting of `Option Compare` can affect string comparisons.</span></span> <span data-ttu-id="4f7e3-143">在 `Option Compare Text`下，字符串 "苹果" 和 "苹果" 的比较结果相等，但在 `Option Compare Binary`下，它们不会。</span><span class="sxs-lookup"><span data-stu-id="4f7e3-143">Under `Option Compare Text`, the strings "Apples" and "apples" compare as equal, but under `Option Compare Binary`, they do not.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="4f7e3-144">具有多个子句的 `Case` 语句可以表现称为 "*短路*" 的行为。</span><span class="sxs-lookup"><span data-stu-id="4f7e3-144">A `Case` statement with multiple clauses can exhibit behavior known as *short-circuiting*.</span></span> <span data-ttu-id="4f7e3-145">Visual Basic 从左到右计算子句，并且如果一个生成与 `testexpression`的匹配项，则不会计算剩余的子句。</span><span class="sxs-lookup"><span data-stu-id="4f7e3-145">Visual Basic evaluates the clauses from left to right, and if one produces a match with `testexpression`, the remaining clauses are not evaluated.</span></span> <span data-ttu-id="4f7e3-146">短路可以提高性能，但如果希望计算 `expressionlist` 中的每个表达式，则可能产生意外的结果。</span><span class="sxs-lookup"><span data-stu-id="4f7e3-146">Short-circuiting can improve performance, but it can produce unexpected results if you are expecting every expression in `expressionlist` to be evaluated.</span></span> <span data-ttu-id="4f7e3-147">有关短路的详细信息，请参阅[布尔表达式](../../../visual-basic/programming-guide/language-features/operators-and-expressions/boolean-expressions.md)。</span><span class="sxs-lookup"><span data-stu-id="4f7e3-147">For more information on short-circuiting, see [Boolean Expressions](../../../visual-basic/programming-guide/language-features/operators-and-expressions/boolean-expressions.md).</span></span>  
  
 <span data-ttu-id="4f7e3-148">如果 `Case` 或 `Case Else` 语句块内的代码不需要在块中运行任何更多语句，则它可以使用 `Exit Select` 语句退出块。</span><span class="sxs-lookup"><span data-stu-id="4f7e3-148">If the code within a `Case` or `Case Else` statement block does not need to run any more of the statements in the block, it can exit the block by using the `Exit Select` statement.</span></span> <span data-ttu-id="4f7e3-149">这会将控制立即传输到 `End Select`后面的语句中。</span><span class="sxs-lookup"><span data-stu-id="4f7e3-149">This transfers control immediately to the statement following `End Select`.</span></span>  
  
 <span data-ttu-id="4f7e3-150">`Select Case` 构造可以嵌套。</span><span class="sxs-lookup"><span data-stu-id="4f7e3-150">`Select Case` constructions can be nested.</span></span> <span data-ttu-id="4f7e3-151">每个嵌套 `Select Case` 构造必须具有匹配的 `End Select` 语句，并且必须完全包含在其嵌套的外部 `Select Case` 构造的单个 `Case` 或 `Case Else` 语句块内。</span><span class="sxs-lookup"><span data-stu-id="4f7e3-151">Each nested `Select Case` construction must have a matching `End Select` statement and must be completely contained within a single `Case` or `Case Else` statement block of the outer `Select Case` construction within which it is nested.</span></span>  
  
## <a name="example"></a><span data-ttu-id="4f7e3-152">示例</span><span class="sxs-lookup"><span data-stu-id="4f7e3-152">Example</span></span>  
 <span data-ttu-id="4f7e3-153">下面的示例使用 `Select Case` 构造来编写与 `number`变量的值相对应的行。</span><span class="sxs-lookup"><span data-stu-id="4f7e3-153">The following example uses a `Select Case` construction to write a line corresponding to the value of the variable `number`.</span></span> <span data-ttu-id="4f7e3-154">第二个 `Case` 语句包含与 `number`的当前值相匹配的值，因此，将运行写入 "6 到8个（含）" 的语句。</span><span class="sxs-lookup"><span data-stu-id="4f7e3-154">The second `Case` statement contains the value that matches the current value of `number`, so the statement that writes "Between 6 and 8, inclusive" runs.</span></span>  
  
 [!code-vb[VbVbalrStatements#54](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#54)]  
  
## <a name="see-also"></a><span data-ttu-id="4f7e3-155">另请参阅</span><span class="sxs-lookup"><span data-stu-id="4f7e3-155">See also</span></span>

- <xref:Microsoft.VisualBasic.Interaction.Choose%2A>
- [<span data-ttu-id="4f7e3-156">End 语句</span><span class="sxs-lookup"><span data-stu-id="4f7e3-156">End Statement</span></span>](../../../visual-basic/language-reference/statements/end-statement.md)
- [<span data-ttu-id="4f7e3-157">If...Then...Else 语句</span><span class="sxs-lookup"><span data-stu-id="4f7e3-157">If...Then...Else Statement</span></span>](../../../visual-basic/language-reference/statements/if-then-else-statement.md)
- [<span data-ttu-id="4f7e3-158">Option Compare 语句</span><span class="sxs-lookup"><span data-stu-id="4f7e3-158">Option Compare Statement</span></span>](../../../visual-basic/language-reference/statements/option-compare-statement.md)
- [<span data-ttu-id="4f7e3-159">Exit 语句</span><span class="sxs-lookup"><span data-stu-id="4f7e3-159">Exit Statement</span></span>](../../../visual-basic/language-reference/statements/exit-statement.md)
