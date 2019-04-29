---
title: Select...Case 语句 (Visual Basic)
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
ms.openlocfilehash: f99db4f1dc224e5f75ee67ba94c3745f28438724
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "61783885"
---
# <a name="selectcase-statement-visual-basic"></a><span data-ttu-id="c0a32-102">Select...Case 语句 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="c0a32-102">Select...Case Statement (Visual Basic)</span></span>
<span data-ttu-id="c0a32-103">在运行的语句，具体取决于表达式的值的多个组之一。</span><span class="sxs-lookup"><span data-stu-id="c0a32-103">Runs one of several groups of statements, depending on the value of an expression.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c0a32-104">语法</span><span class="sxs-lookup"><span data-stu-id="c0a32-104">Syntax</span></span>  
  
```  
Select [ Case ] testexpression  
    [ Case expressionlist  
        [ statements ] ]  
    [ Case Else  
        [ elsestatements ] ]  
End Select  
```  
  
## <a name="parts"></a><span data-ttu-id="c0a32-105">部件</span><span class="sxs-lookup"><span data-stu-id="c0a32-105">Parts</span></span>  
  
|<span data-ttu-id="c0a32-106">术语</span><span class="sxs-lookup"><span data-stu-id="c0a32-106">Term</span></span>|<span data-ttu-id="c0a32-107">定义</span><span class="sxs-lookup"><span data-stu-id="c0a32-107">Definition</span></span>|  
|---|---|  
|`testexpression`|<span data-ttu-id="c0a32-108">必需。</span><span class="sxs-lookup"><span data-stu-id="c0a32-108">Required.</span></span> <span data-ttu-id="c0a32-109">表达式。</span><span class="sxs-lookup"><span data-stu-id="c0a32-109">Expression.</span></span> <span data-ttu-id="c0a32-110">计算结果必须为基本数据类型之一 (`Boolean`， `Byte`， `Char`， `Date`， `Double`， `Decimal`， `Integer`， `Long`， `Object`， `SByte`， `Short`，`Single`， `String`， `UInteger`， `ULong`，和`UShort`)。</span><span class="sxs-lookup"><span data-stu-id="c0a32-110">Must evaluate to one of the elementary data types (`Boolean`, `Byte`, `Char`, `Date`, `Double`, `Decimal`, `Integer`, `Long`, `Object`, `SByte`, `Short`, `Single`, `String`, `UInteger`, `ULong`, and `UShort`).</span></span>|  
|`expressionlist`|<span data-ttu-id="c0a32-111">在所需`Case`语句。</span><span class="sxs-lookup"><span data-stu-id="c0a32-111">Required in a `Case` statement.</span></span> <span data-ttu-id="c0a32-112">表示匹配值的表达式子句的列表`testexpression`。</span><span class="sxs-lookup"><span data-stu-id="c0a32-112">List of expression clauses representing match values for `testexpression`.</span></span> <span data-ttu-id="c0a32-113">由逗号分隔多个表达式子句。</span><span class="sxs-lookup"><span data-stu-id="c0a32-113">Multiple expression clauses are separated by commas.</span></span> <span data-ttu-id="c0a32-114">每个子句可以采用以下形式之一：</span><span class="sxs-lookup"><span data-stu-id="c0a32-114">Each clause can take one of the following forms:</span></span><br /><br /> <span data-ttu-id="c0a32-115">-   *expression1* `To` *expression2*</span><span class="sxs-lookup"><span data-stu-id="c0a32-115">-   *expression1* `To` *expression2*</span></span><br /><span data-ttu-id="c0a32-116">-   [ `Is` ] *comparisonoperator* *expression*</span><span class="sxs-lookup"><span data-stu-id="c0a32-116">-   [ `Is` ] *comparisonoperator* *expression*</span></span><br /><span data-ttu-id="c0a32-117">-   *expression*</span><span class="sxs-lookup"><span data-stu-id="c0a32-117">-   *expression*</span></span><br /><br /> <span data-ttu-id="c0a32-118">使用`To`关键字来指定匹配的范围边界值`testexpression`。</span><span class="sxs-lookup"><span data-stu-id="c0a32-118">Use the `To` keyword to specify the boundaries of a range of match values for `testexpression`.</span></span> <span data-ttu-id="c0a32-119">值`expression1`必须小于或等于的值`expression2`。</span><span class="sxs-lookup"><span data-stu-id="c0a32-119">The value of `expression1` must be less than or equal to the value of `expression2`.</span></span><br /><br /> <span data-ttu-id="c0a32-120">使用`Is`关键字的比较运算符 (`=`， `<>`， `<`， `<=`， `>`，或者`>=`) 来指定匹配值的限制`testexpression`。</span><span class="sxs-lookup"><span data-stu-id="c0a32-120">Use the `Is` keyword with a comparison operator (`=`, `<>`, `<`, `<=`, `>`, or `>=`) to specify a restriction on the match values for `testexpression`.</span></span> <span data-ttu-id="c0a32-121">如果`Is`未提供关键字，它将自动插入之前*比较运算符*。</span><span class="sxs-lookup"><span data-stu-id="c0a32-121">If the `Is` keyword is not supplied, it is automatically inserted before *comparisonoperator*.</span></span><br /><br /> <span data-ttu-id="c0a32-122">仅指定窗体`expression`被视为一种特殊的情况`Is`形成 where*比较运算符*是等号 (`=`)。</span><span class="sxs-lookup"><span data-stu-id="c0a32-122">The form specifying only `expression` is treated as a special case of the `Is` form where *comparisonoperator* is the equal sign (`=`).</span></span> <span data-ttu-id="c0a32-123">此窗体评为`testexpression`  =  `expression`。</span><span class="sxs-lookup"><span data-stu-id="c0a32-123">This form is evaluated as `testexpression` = `expression`.</span></span><br /><br /> <span data-ttu-id="c0a32-124">中的表达式`expressionlist`可以为任何数据类型，则它们隐式转换为的类型`testexpression`适当`comparisonoperator`对与正在使用它的两种类型有效。</span><span class="sxs-lookup"><span data-stu-id="c0a32-124">The expressions in `expressionlist` can be of any data type, provided they are implicitly convertible to the type of `testexpression` and the appropriate `comparisonoperator` is valid for the two types it is being used with.</span></span>|  
|`statements`|<span data-ttu-id="c0a32-125">可选。</span><span class="sxs-lookup"><span data-stu-id="c0a32-125">Optional.</span></span> <span data-ttu-id="c0a32-126">一个或多个语句之后`Case`，运行的如果`testexpression`匹配中的任何子句`expressionlist`。</span><span class="sxs-lookup"><span data-stu-id="c0a32-126">One or more statements following `Case` that run if `testexpression` matches any clause in `expressionlist`.</span></span>|  
|`elsestatements`|<span data-ttu-id="c0a32-127">可选。</span><span class="sxs-lookup"><span data-stu-id="c0a32-127">Optional.</span></span> <span data-ttu-id="c0a32-128">一个或多个语句之后`Case Else`，运行的如果`testexpression`不匹配中的任何子句`expressionlist`任何`Case`语句。</span><span class="sxs-lookup"><span data-stu-id="c0a32-128">One or more statements following `Case Else` that run if `testexpression` does not match any clause in the `expressionlist` of any of the `Case` statements.</span></span>|  
|`End Select`|<span data-ttu-id="c0a32-129">终止的定义`Select`...`Case`构造。</span><span class="sxs-lookup"><span data-stu-id="c0a32-129">Terminates the definition of the `Select`...`Case` construction.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="c0a32-130">备注</span><span class="sxs-lookup"><span data-stu-id="c0a32-130">Remarks</span></span>  
 <span data-ttu-id="c0a32-131">如果`testexpression`匹配任何`Case``expressionlist`子句中，之后的语句`Case`语句最多运行下一步`Case`， `Case Else`，或`End Select`语句。</span><span class="sxs-lookup"><span data-stu-id="c0a32-131">If `testexpression` matches any `Case` `expressionlist` clause, the statements following that `Case` statement run up to the next `Case`, `Case Else`, or `End Select` statement.</span></span> <span data-ttu-id="c0a32-132">控制权然后传递给后面的语句`End Select`。</span><span class="sxs-lookup"><span data-stu-id="c0a32-132">Control then passes to the statement following `End Select`.</span></span> <span data-ttu-id="c0a32-133">如果`testexpression`匹配`expressionlist`中多个子句`Case`子句，仅第一个匹配之后的语句运行。</span><span class="sxs-lookup"><span data-stu-id="c0a32-133">If `testexpression` matches an `expressionlist` clause in more than one `Case` clause, only the statements following the first match run.</span></span>  
  
 <span data-ttu-id="c0a32-134">`Case Else`语句用于引入`elsestatements`之间不存在任何匹配时要运行`testexpression`和一个`expressionlist`中任何其他子句`Case`语句。</span><span class="sxs-lookup"><span data-stu-id="c0a32-134">The `Case Else` statement is used to introduce the `elsestatements` to run if no match is found between the `testexpression` and an `expressionlist` clause in any of the other `Case` statements.</span></span> <span data-ttu-id="c0a32-135">尽管没有要求，它是个好办法`Case Else`语句中的您`Select Case`构造来处理无法预料`testexpression`值。</span><span class="sxs-lookup"><span data-stu-id="c0a32-135">Although not required, it is a good idea to have a `Case Else` statement in your `Select Case` construction to handle unforeseen `testexpression` values.</span></span> <span data-ttu-id="c0a32-136">如果没有`Case``expressionlist`子句匹配`testexpression`，并且没有任何`Case Else`语句，控制将传递到后面的语句`End Select`。</span><span class="sxs-lookup"><span data-stu-id="c0a32-136">If no `Case` `expressionlist` clause matches `testexpression` and there is no `Case Else` statement, control passes to the statement following `End Select`.</span></span>  
  
 <span data-ttu-id="c0a32-137">您可以使用多个表达式或范围中每个`Case`子句。</span><span class="sxs-lookup"><span data-stu-id="c0a32-137">You can use multiple expressions or ranges in each `Case` clause.</span></span> <span data-ttu-id="c0a32-138">例如，下面的行是有效的。</span><span class="sxs-lookup"><span data-stu-id="c0a32-138">For example, the following line is valid.</span></span>  
  
 `Case 1 To 4, 7 To 9, 11, 13, Is > maxNumber`  
  
> [!NOTE]
>  <span data-ttu-id="c0a32-139">`Is`中使用的关键字`Case`并`Case Else`语句不是与相同[Is 运算符](../../../visual-basic/language-reference/operators/is-operator.md)，用于对象的引用比较。</span><span class="sxs-lookup"><span data-stu-id="c0a32-139">The `Is` keyword used in the `Case` and `Case Else` statements is not the same as the [Is Operator](../../../visual-basic/language-reference/operators/is-operator.md), which is used for object reference comparison.</span></span>  
  
 <span data-ttu-id="c0a32-140">您可以指定范围和字符串使用多个表达式。</span><span class="sxs-lookup"><span data-stu-id="c0a32-140">You can specify ranges and multiple expressions for character strings.</span></span> <span data-ttu-id="c0a32-141">在以下示例中，`Case`匹配任何字符串，是完全相等"apples"、"螺母"和"soup"之间的值按字母顺序，或包含完全相同的值的当前值`testItem`。</span><span class="sxs-lookup"><span data-stu-id="c0a32-141">In the following example, `Case` matches any string that is exactly equal to "apples", has a value between "nuts" and "soup" in alphabetical order, or contains the exact same value as the current value of `testItem`.</span></span>  
  
 `Case "apples", "nuts" To "soup", testItem`  
  
 <span data-ttu-id="c0a32-142">设置`Option Compare`可能会影响字符串比较。</span><span class="sxs-lookup"><span data-stu-id="c0a32-142">The setting of `Option Compare` can affect string comparisons.</span></span> <span data-ttu-id="c0a32-143">下`Option Compare Text`，"苹果"和"apples"的字符串的比较结果相等，但在`Option Compare Binary`，它们不匹配。</span><span class="sxs-lookup"><span data-stu-id="c0a32-143">Under `Option Compare Text`, the strings "Apples" and "apples" compare as equal, but under `Option Compare Binary`, they do not.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="c0a32-144">一个`Case`包含多个子句的语句可能会表现出行为称为*短路*。</span><span class="sxs-lookup"><span data-stu-id="c0a32-144">A `Case` statement with multiple clauses can exhibit behavior known as *short-circuiting*.</span></span> <span data-ttu-id="c0a32-145">Visual Basic 从左到右，这些子句的计算结果和如果一个将生成与匹配`testexpression`，不计算剩余的子句。</span><span class="sxs-lookup"><span data-stu-id="c0a32-145">Visual Basic evaluates the clauses from left to right, and if one produces a match with `testexpression`, the remaining clauses are not evaluated.</span></span> <span data-ttu-id="c0a32-146">短路可以提高性能，但它可以产生意外的结果，如果希望在每个表达式`expressionlist`要计算。</span><span class="sxs-lookup"><span data-stu-id="c0a32-146">Short-circuiting can improve performance, but it can produce unexpected results if you are expecting every expression in `expressionlist` to be evaluated.</span></span> <span data-ttu-id="c0a32-147">有关短路的详细信息，请参阅[布尔表达式](../../../visual-basic/programming-guide/language-features/operators-and-expressions/boolean-expressions.md)。</span><span class="sxs-lookup"><span data-stu-id="c0a32-147">For more information on short-circuiting, see [Boolean Expressions](../../../visual-basic/programming-guide/language-features/operators-and-expressions/boolean-expressions.md).</span></span>  
  
 <span data-ttu-id="c0a32-148">如果中的代码`Case`或`Case Else`语句块不需要在块中运行任何其他语句，它可以使用退出块`Exit Select`语句。</span><span class="sxs-lookup"><span data-stu-id="c0a32-148">If the code within a `Case` or `Case Else` statement block does not need to run any more of the statements in the block, it can exit the block by using the `Exit Select` statement.</span></span> <span data-ttu-id="c0a32-149">此控件将立即转移到后面的语句`End Select`。</span><span class="sxs-lookup"><span data-stu-id="c0a32-149">This transfers control immediately to the statement following `End Select`.</span></span>  
  
 <span data-ttu-id="c0a32-150">`Select Case` 构造可相互嵌套。</span><span class="sxs-lookup"><span data-stu-id="c0a32-150">`Select Case` constructions can be nested.</span></span> <span data-ttu-id="c0a32-151">每个嵌套`Select Case`构造必须有一个匹配`End Select`语句，并且必须完全包含在单个`Case`或`Case Else`语句块的外部`Select Case`构造它嵌套在其中。</span><span class="sxs-lookup"><span data-stu-id="c0a32-151">Each nested `Select Case` construction must have a matching `End Select` statement and must be completely contained within a single `Case` or `Case Else` statement block of the outer `Select Case` construction within which it is nested.</span></span>  
  
## <a name="example"></a><span data-ttu-id="c0a32-152">示例</span><span class="sxs-lookup"><span data-stu-id="c0a32-152">Example</span></span>  
 <span data-ttu-id="c0a32-153">下面的示例使用`Select Case`构造来写入变量的值相对应的行`number`。</span><span class="sxs-lookup"><span data-stu-id="c0a32-153">The following example uses a `Select Case` construction to write a line corresponding to the value of the variable `number`.</span></span> <span data-ttu-id="c0a32-154">第二个`Case`语句包含的值相匹配的当前值`number`，因此该语句，它将写入"为 6 到 8，非独占"运行。</span><span class="sxs-lookup"><span data-stu-id="c0a32-154">The second `Case` statement contains the value that matches the current value of `number`, so the statement that writes "Between 6 and 8, inclusive" runs.</span></span>  
  
 [!code-vb[VbVbalrStatements#54](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#54)]  
  
## <a name="see-also"></a><span data-ttu-id="c0a32-155">请参阅</span><span class="sxs-lookup"><span data-stu-id="c0a32-155">See also</span></span>

- <xref:Microsoft.VisualBasic.Interaction.Choose%2A>
- [<span data-ttu-id="c0a32-156">End 语句</span><span class="sxs-lookup"><span data-stu-id="c0a32-156">End Statement</span></span>](../../../visual-basic/language-reference/statements/end-statement.md)
- [<span data-ttu-id="c0a32-157">If...Then...Else 语句</span><span class="sxs-lookup"><span data-stu-id="c0a32-157">If...Then...Else Statement</span></span>](../../../visual-basic/language-reference/statements/if-then-else-statement.md)
- [<span data-ttu-id="c0a32-158">Option Compare 语句</span><span class="sxs-lookup"><span data-stu-id="c0a32-158">Option Compare Statement</span></span>](../../../visual-basic/language-reference/statements/option-compare-statement.md)
- [<span data-ttu-id="c0a32-159">Exit 语句</span><span class="sxs-lookup"><span data-stu-id="c0a32-159">Exit Statement</span></span>](../../../visual-basic/language-reference/statements/exit-statement.md)
