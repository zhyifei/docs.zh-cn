---
title: "在 Visual Basic 中的比较运算符 |Microsoft 文档"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- comparison operators, comparing strings
- comparison operators, comparing objects
- strings [Visual Basic], comparing
- comparison operators
- string comparison [Visual Basic], operators
- objects [Visual Basic], comparing
- numbers, comparing
- Visual Basic code, operators
- string comparison [Visual Basic]
- numeric values, comparing
- comparison operators, comparing numeric values
- operators [Visual Basic], comparison
ms.assetid: 0b570339-5407-474f-8421-e183a8b303ee
caps.latest.revision: 13
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: a958481fa04cb1a9abde69c5215dccd6dbbe4a14
ms.contentlocale: zh-cn
ms.lasthandoff: 04/12/2017

---
# <a name="comparison-operators-in-visual-basic"></a><span data-ttu-id="dbca6-102">Comparison Operators in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="dbca6-102">Comparison Operators in Visual Basic</span></span>
<span data-ttu-id="dbca6-103">比较运算符比较两个表达式并返回`Boolean`值，该值表示其值的关系。</span><span class="sxs-lookup"><span data-stu-id="dbca6-103">Comparison operators compare two expressions and return a `Boolean` value that represents the relationship of their values.</span></span> <span data-ttu-id="dbca6-104">有运算符用于比较数字值，用于比较字符串的运算符和运算符用于比较对象。</span><span class="sxs-lookup"><span data-stu-id="dbca6-104">There are operators for comparing numeric values, operators for comparing strings, and operators for comparing objects.</span></span> <span data-ttu-id="dbca6-105">本文讨论了所有三种类型的运算符。</span><span class="sxs-lookup"><span data-stu-id="dbca6-105">All three types of operators are discussed herein.</span></span>  
  
## <a name="comparing-numeric-values"></a><span data-ttu-id="dbca6-106">比较数值</span><span class="sxs-lookup"><span data-stu-id="dbca6-106">Comparing Numeric Values</span></span>  
 [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]<span data-ttu-id="dbca6-107">将使用六个数值的比较运算符的数字值进行比较。</span><span class="sxs-lookup"><span data-stu-id="dbca6-107"> compares numeric values using six numeric comparison operators.</span></span> <span data-ttu-id="dbca6-108">每个运算符采用两个表达式计算结果为数字值作为操作数。</span><span class="sxs-lookup"><span data-stu-id="dbca6-108">Each operator takes as operands two expressions that evaluate to numeric values.</span></span> <span data-ttu-id="dbca6-109">下表列出的运算符，并显示每个示例。</span><span class="sxs-lookup"><span data-stu-id="dbca6-109">The following table lists the operators and shows examples of each.</span></span>  
  
|<span data-ttu-id="dbca6-110">运算符</span><span class="sxs-lookup"><span data-stu-id="dbca6-110">Operator</span></span>|<span data-ttu-id="dbca6-111">测试的条件</span><span class="sxs-lookup"><span data-stu-id="dbca6-111">Condition tested</span></span>|<span data-ttu-id="dbca6-112">示例</span><span class="sxs-lookup"><span data-stu-id="dbca6-112">Examples</span></span>|  
|--------------|----------------------|--------------|  
|<span data-ttu-id="dbca6-113">`=`（相等）</span><span class="sxs-lookup"><span data-stu-id="dbca6-113">`=` (Equality)</span></span>|<span data-ttu-id="dbca6-114">第一个表达式相等的值是否为第二个值？</span><span class="sxs-lookup"><span data-stu-id="dbca6-114">Is the value of the first expression equal to the value of the second?</span></span>|<span data-ttu-id="dbca6-115">`23`   `=`   `33    ' False`</span><span class="sxs-lookup"><span data-stu-id="dbca6-115">`23`   `=`   `33    ' False`</span></span><br /><br /> <span data-ttu-id="dbca6-116">`23`   `=`   `23    ' True`</span><span class="sxs-lookup"><span data-stu-id="dbca6-116">`23`   `=`   `23    ' True`</span></span><br /><br /> <span data-ttu-id="dbca6-117">`23`   `=`   `12    ' False`</span><span class="sxs-lookup"><span data-stu-id="dbca6-117">`23`   `=`   `12    ' False`</span></span>|  
|<span data-ttu-id="dbca6-118">`<>`（不等于）</span><span class="sxs-lookup"><span data-stu-id="dbca6-118">`<>` (Inequality)</span></span>|<span data-ttu-id="dbca6-119">第一个表达式的值是否不等于第二个值？</span><span class="sxs-lookup"><span data-stu-id="dbca6-119">Is the value of the first expression unequal to the value of the second?</span></span>|<span data-ttu-id="dbca6-120">`23`   `<>`   `33    ' True`</span><span class="sxs-lookup"><span data-stu-id="dbca6-120">`23`   `<>`   `33    ' True`</span></span><br /><br /> <span data-ttu-id="dbca6-121">`23`   `<>`   `23    ' False`</span><span class="sxs-lookup"><span data-stu-id="dbca6-121">`23`   `<>`   `23    ' False`</span></span><br /><br /> <span data-ttu-id="dbca6-122">`23`   `<>`   `12    ' True`</span><span class="sxs-lookup"><span data-stu-id="dbca6-122">`23`   `<>`   `12    ' True`</span></span>|  
|<span data-ttu-id="dbca6-123">`<`（小于）</span><span class="sxs-lookup"><span data-stu-id="dbca6-123">`<` (Less than)</span></span>|<span data-ttu-id="dbca6-124">第一个表达式的值小于第二个值是多少？</span><span class="sxs-lookup"><span data-stu-id="dbca6-124">Is the value of the first expression less than the value of the second?</span></span>|<span data-ttu-id="dbca6-125">`23`   `<`   `33    ' True`</span><span class="sxs-lookup"><span data-stu-id="dbca6-125">`23`   `<`   `33    ' True`</span></span><br /><br /> <span data-ttu-id="dbca6-126">`23`   `<`   `23    ' False`</span><span class="sxs-lookup"><span data-stu-id="dbca6-126">`23`   `<`   `23    ' False`</span></span><br /><br /> <span data-ttu-id="dbca6-127">`23`   `<`   `12    ' False`</span><span class="sxs-lookup"><span data-stu-id="dbca6-127">`23`   `<`   `12    ' False`</span></span>|  
|<span data-ttu-id="dbca6-128">`>`（大于）</span><span class="sxs-lookup"><span data-stu-id="dbca6-128">`>` (Greater than)</span></span>|<span data-ttu-id="dbca6-129">第一个表达式的值是否大于第二个值？</span><span class="sxs-lookup"><span data-stu-id="dbca6-129">Is the value of the first expression greater than the value of the second?</span></span>|<span data-ttu-id="dbca6-130">`23`   `>`   `33    ' False`</span><span class="sxs-lookup"><span data-stu-id="dbca6-130">`23`   `>`   `33    ' False`</span></span><br /><br /> <span data-ttu-id="dbca6-131">`23`   `>`   `23    ' False`</span><span class="sxs-lookup"><span data-stu-id="dbca6-131">`23`   `>`   `23    ' False`</span></span><br /><br /> <span data-ttu-id="dbca6-132">`23`   `>`   `12    ' True`</span><span class="sxs-lookup"><span data-stu-id="dbca6-132">`23`   `>`   `12    ' True`</span></span>|  
|<span data-ttu-id="dbca6-133">`<=`（小于或等于）</span><span class="sxs-lookup"><span data-stu-id="dbca6-133">`<=` (Less than or equal to)</span></span>|<span data-ttu-id="dbca6-134">第一个表达式的值是否小于或等于第二个值？</span><span class="sxs-lookup"><span data-stu-id="dbca6-134">Is the value of the first expression less than or equal to the value of the second?</span></span>|<span data-ttu-id="dbca6-135">`23`   `<=`   `33    ' True`</span><span class="sxs-lookup"><span data-stu-id="dbca6-135">`23`   `<=`   `33    ' True`</span></span><br /><br /> <span data-ttu-id="dbca6-136">`23`   `<=`   `23    ' True`</span><span class="sxs-lookup"><span data-stu-id="dbca6-136">`23`   `<=`   `23    ' True`</span></span><br /><br /> <span data-ttu-id="dbca6-137">`23`   `<=`   `12    ' False`</span><span class="sxs-lookup"><span data-stu-id="dbca6-137">`23`   `<=`   `12    ' False`</span></span>|  
|<span data-ttu-id="dbca6-138">`>=`（大于或等于）</span><span class="sxs-lookup"><span data-stu-id="dbca6-138">`>=` (Greater than or equal to)</span></span>|<span data-ttu-id="dbca6-139">第一个表达式的值是否大于或等于第二个值？</span><span class="sxs-lookup"><span data-stu-id="dbca6-139">Is the value of the first expression greater than or equal to the value of the second?</span></span>|<span data-ttu-id="dbca6-140">`23`   `>=`   `33    ' False`</span><span class="sxs-lookup"><span data-stu-id="dbca6-140">`23`   `>=`   `33    ' False`</span></span><br /><br /> <span data-ttu-id="dbca6-141">`23`   `>=`   `23    ' True`</span><span class="sxs-lookup"><span data-stu-id="dbca6-141">`23`   `>=`   `23    ' True`</span></span><br /><br /> <span data-ttu-id="dbca6-142">`23`   `>=`   `12    ' True`</span><span class="sxs-lookup"><span data-stu-id="dbca6-142">`23`   `>=`   `12    ' True`</span></span>|  
  
## <a name="comparing-strings"></a><span data-ttu-id="dbca6-143">比较字符串</span><span class="sxs-lookup"><span data-stu-id="dbca6-143">Comparing Strings</span></span>  
 [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]<span data-ttu-id="dbca6-144">使用比较字符串[Like 运算符](../../../../visual-basic/language-reference/operators/like-operator.md)以及数值比较运算符。</span><span class="sxs-lookup"><span data-stu-id="dbca6-144"> compares strings using the [Like Operator](../../../../visual-basic/language-reference/operators/like-operator.md) as well as the numeric comparison operators.</span></span> <span data-ttu-id="dbca6-145">`Like`运算符，你可以指定一种模式。</span><span class="sxs-lookup"><span data-stu-id="dbca6-145">The `Like` operator allows you to specify a pattern.</span></span> <span data-ttu-id="dbca6-146">与指定的模式，然后比较字符串和如果匹配，则结果是`True`。</span><span class="sxs-lookup"><span data-stu-id="dbca6-146">The string is then compared against the pattern, and if it matches, the result is `True`.</span></span> <span data-ttu-id="dbca6-147">否则，结果是`False`。</span><span class="sxs-lookup"><span data-stu-id="dbca6-147">Otherwise, the result is `False`.</span></span> <span data-ttu-id="dbca6-148">数字运算符，你可以比较`String`值基于其排序顺序，如以下示例所示。</span><span class="sxs-lookup"><span data-stu-id="dbca6-148">The numeric operators allow you to compare `String` values based on their sort order, as the following example shows.</span></span>  
  
 `"73" < "9"`  
  
 `' The result of the preceding comparison is True.`  
  
 <span data-ttu-id="dbca6-149">在前面的示例的结果是`True`因为第一个字符串中的第一个字符的排序之前第二个字符串中的第一个字符。</span><span class="sxs-lookup"><span data-stu-id="dbca6-149">The result in the preceding example is `True` because the first character in the first string sorts before the first character in the second string.</span></span> <span data-ttu-id="dbca6-150">如果第一个字符等于，比较将继续使用两个字符串中的下一个字符，依此类推。</span><span class="sxs-lookup"><span data-stu-id="dbca6-150">If the first characters were equal, the comparison would continue to the next character in both strings, and so on.</span></span> <span data-ttu-id="dbca6-151">此外可以测试使用相等运算符，如以下示例所示的字符串相等。</span><span class="sxs-lookup"><span data-stu-id="dbca6-151">You can also test equality of strings using the equality operator, as the following example shows.</span></span>  
  
 `"734" = "734"`  
  
 `' The result of the preceding comparison is True.`  
  
 <span data-ttu-id="dbca6-152">一个字符串是否与另一一个前缀，例如"aa"和"aaa"，认为是较长的字符串必须晚于较短的字符串。</span><span class="sxs-lookup"><span data-stu-id="dbca6-152">If one string is a prefix of another, such as "aa" and "aaa", the longer string is considered to be greater than the shorter string.</span></span> <span data-ttu-id="dbca6-153">下面的示例阐释了这一点。</span><span class="sxs-lookup"><span data-stu-id="dbca6-153">The following example illustrates this.</span></span>  
  
 `"aaa" > "aa"`  
  
 `' The result of the preceding comparison is True.`  
  
 <span data-ttu-id="dbca6-154">排序顺序取决于二进制比较或文本比较，这取决于设置`Option Compare`。</span><span class="sxs-lookup"><span data-stu-id="dbca6-154">The sort order is based on either a binary comparison or a textual comparison depending on the setting of `Option Compare`.</span></span> <span data-ttu-id="dbca6-155">有关详细信息请参阅[选项比较语句](../../../../visual-basic/language-reference/statements/option-compare-statement.md)。</span><span class="sxs-lookup"><span data-stu-id="dbca6-155">For more information see [Option Compare Statement](../../../../visual-basic/language-reference/statements/option-compare-statement.md).</span></span>  
  
## <a name="comparing-objects"></a><span data-ttu-id="dbca6-156">比较对象</span><span class="sxs-lookup"><span data-stu-id="dbca6-156">Comparing Objects</span></span>  
 [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]<span data-ttu-id="dbca6-157">比较两个对象引用变量与[Is 运算符](../../../../visual-basic/language-reference/operators/is-operator.md)和[IsNot 运算符](../../../../visual-basic/language-reference/operators/isnot-operator.md)。</span><span class="sxs-lookup"><span data-stu-id="dbca6-157"> compares two object reference variables with the [Is Operator](../../../../visual-basic/language-reference/operators/is-operator.md) and the [IsNot Operator](../../../../visual-basic/language-reference/operators/isnot-operator.md).</span></span> <span data-ttu-id="dbca6-158">可以使用其中任一运算符以确定两个引用变量引用同一对象实例。</span><span class="sxs-lookup"><span data-stu-id="dbca6-158">You can use either of these operators to determine if two reference variables refer to the same object instance.</span></span> <span data-ttu-id="dbca6-159">下面的示例阐释了这一点。</span><span class="sxs-lookup"><span data-stu-id="dbca6-159">The following example illustrates this.</span></span>  
  
 <span data-ttu-id="dbca6-160">[!code-vb[VbVbalrOperators #&65;](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/comparison-operators_1.vb)]</span><span class="sxs-lookup"><span data-stu-id="dbca6-160">[!code-vb[VbVbalrOperators#65](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/comparison-operators_1.vb)]</span></span>  
  
 <span data-ttu-id="dbca6-161">在前面的示例中，`x Is y`的计算结果为`True`，这是因为这两个变量引用的同一个实例。</span><span class="sxs-lookup"><span data-stu-id="dbca6-161">In the preceding example, `x Is y` evaluates to `True`, because both variables refer to the same instance.</span></span> <span data-ttu-id="dbca6-162">此结果与下面的示例作一个对比。</span><span class="sxs-lookup"><span data-stu-id="dbca6-162">Contrast this result with the following example.</span></span>  
  
 <span data-ttu-id="dbca6-163">[!code-vb[VbVbalrOperators #&66;](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/comparison-operators_2.vb)]</span><span class="sxs-lookup"><span data-stu-id="dbca6-163">[!code-vb[VbVbalrOperators#66](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/comparison-operators_2.vb)]</span></span>  
  
 <span data-ttu-id="dbca6-164">在前面的示例中，`x Is y`的计算结果为`False`，这是因为尽管两个变量引用指向同一类型的对象，它们是指该类型的不同实例。</span><span class="sxs-lookup"><span data-stu-id="dbca6-164">In the preceding example, `x Is y` evaluates to `False`, because although the variables refer to objects of the same type, they refer to different instances of that type.</span></span>  
  
 <span data-ttu-id="dbca6-165">当你想要测试的两个对象不指向同一个实例，`IsNot`运算符可避免从语法角度而言不太妥当的组合`Not`和`Is`。</span><span class="sxs-lookup"><span data-stu-id="dbca6-165">When you want to test for two objects not pointing to the same instance, the `IsNot` operator lets you avoid a grammatically clumsy combination of `Not` and `Is`.</span></span> <span data-ttu-id="dbca6-166">下面的示例阐释了这一点。</span><span class="sxs-lookup"><span data-stu-id="dbca6-166">The following example illustrates this.</span></span>  
  
 <span data-ttu-id="dbca6-167">[!code-vb[VbVbalrOperators #&67;](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/comparison-operators_3.vb)]</span><span class="sxs-lookup"><span data-stu-id="dbca6-167">[!code-vb[VbVbalrOperators#67](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/comparison-operators_3.vb)]</span></span>  
  
 <span data-ttu-id="dbca6-168">在前面的示例中，`If a IsNot b`等同于`If Not a Is b`。</span><span class="sxs-lookup"><span data-stu-id="dbca6-168">In the preceding example, `If a IsNot b` is equivalent to `If Not a Is b`.</span></span>  
  
### <a name="comparing-object-type"></a><span data-ttu-id="dbca6-169">比较对象类型</span><span class="sxs-lookup"><span data-stu-id="dbca6-169">Comparing Object Type</span></span>  
 <span data-ttu-id="dbca6-170">您可以测试对象是否为具有特定类型的`TypeOf`...`Is`表达式。</span><span class="sxs-lookup"><span data-stu-id="dbca6-170">You can test whether an object is of a particular type with the `TypeOf`...`Is` expression.</span></span> <span data-ttu-id="dbca6-171">语法如下所示：</span><span class="sxs-lookup"><span data-stu-id="dbca6-171">The syntax is as follows:</span></span>  
  
 `TypeOf <objectexpression> Is <typename>`  
  
 <span data-ttu-id="dbca6-172">当`typename`指定接口类型，则`TypeOf`...`Is`表达式返回`True`如果对象实现的接口类型。</span><span class="sxs-lookup"><span data-stu-id="dbca6-172">When `typename` specifies an interface type, then the `TypeOf`...`Is` expression returns `True` if the object implements the interface type.</span></span> <span data-ttu-id="dbca6-173">当`typename`是类类型，则表达式将返回`True`的对象是否为指定类或派生自指定类的类的实例。</span><span class="sxs-lookup"><span data-stu-id="dbca6-173">When `typename` is a class type, then the expression returns `True` if the object is an instance of the specified class or of a class that derives from the specified class.</span></span> <span data-ttu-id="dbca6-174">下面的示例阐释了这一点。</span><span class="sxs-lookup"><span data-stu-id="dbca6-174">The following example illustrates this.</span></span>  
  
 <span data-ttu-id="dbca6-175">[!code-vb[VbVbalrOperators #&68;](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/comparison-operators_4.vb)]</span><span class="sxs-lookup"><span data-stu-id="dbca6-175">[!code-vb[VbVbalrOperators#68](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/comparison-operators_4.vb)]</span></span>  
  
 <span data-ttu-id="dbca6-176">在前面的示例中，`TypeOf x Is Control`表达式计算结果为`True`因为的一种`x`是`Button`，它是从`Control`。</span><span class="sxs-lookup"><span data-stu-id="dbca6-176">In the preceding example, the `TypeOf x Is Control` expression evaluates to `True` because the type of `x` is `Button`, which inherits from `Control`.</span></span>  
  
 <span data-ttu-id="dbca6-177">有关详细信息，请参阅[TypeOf 运算符](../../../../visual-basic/language-reference/operators/typeof-operator.md)。</span><span class="sxs-lookup"><span data-stu-id="dbca6-177">For more information, see [TypeOf Operator](../../../../visual-basic/language-reference/operators/typeof-operator.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dbca6-178">另请参阅</span><span class="sxs-lookup"><span data-stu-id="dbca6-178">See Also</span></span>  
 <span data-ttu-id="dbca6-179">[值的比较](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/value-comparisons.md) </span><span class="sxs-lookup"><span data-stu-id="dbca6-179">[Value Comparisons](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/value-comparisons.md) </span></span>  
<span data-ttu-id="dbca6-180"> [比较运算符](../../../../visual-basic/language-reference/operators/comparison-operators.md) </span><span class="sxs-lookup"><span data-stu-id="dbca6-180"> [Comparison Operators](../../../../visual-basic/language-reference/operators/comparison-operators.md) </span></span>  
<span data-ttu-id="dbca6-181"> [运算符](../../../../visual-basic/language-reference/operators/index.md) </span><span class="sxs-lookup"><span data-stu-id="dbca6-181"> [Operators](../../../../visual-basic/language-reference/operators/index.md) </span></span>  
<span data-ttu-id="dbca6-182"> [在 Visual Basic 中的算术运算符](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/arithmetic-operators.md) </span><span class="sxs-lookup"><span data-stu-id="dbca6-182"> [Arithmetic Operators in Visual Basic](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/arithmetic-operators.md) </span></span>  
<span data-ttu-id="dbca6-183"> [在 Visual Basic 中的串联运算符](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/concatenation-operators.md) </span><span class="sxs-lookup"><span data-stu-id="dbca6-183"> [Concatenation Operators in Visual Basic](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/concatenation-operators.md) </span></span>  
<span data-ttu-id="dbca6-184"> [在 Visual Basic 中的逻辑和按位运算符](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/logical-and-bitwise-operators.md)</span><span class="sxs-lookup"><span data-stu-id="dbca6-184"> [Logical and Bitwise Operators in Visual Basic](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/logical-and-bitwise-operators.md)</span></span>
