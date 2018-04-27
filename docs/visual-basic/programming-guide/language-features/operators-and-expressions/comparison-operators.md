---
title: Comparison Operators in Visual Basic
ms.custom: ''
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- comparison operators [Visual Basic], comparing strings
- comparison operators [Visual Basic], comparing objects
- strings [Visual Basic], comparing
- comparison operators [Visual Basic]
- string comparison [Visual Basic], operators
- objects [Visual Basic], comparing
- numbers [Visual Basic], comparing
- Visual Basic code, operators
- string comparison [Visual Basic]
- numeric values [Visual Basic], comparing
- comparison operators [Visual Basic], comparing numeric values
- operators [Visual Basic], comparison
ms.assetid: 0b570339-5407-474f-8421-e183a8b303ee
caps.latest.revision: 13
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 77c5520be63d6d05cc4b895b99b466cd8e486f6a
ms.sourcegitcommit: 86adcc06e35390f13c1e372c36d2e044f1fc31ef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/26/2018
---
# <a name="comparison-operators-in-visual-basic"></a><span data-ttu-id="cefa7-102">Comparison Operators in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="cefa7-102">Comparison Operators in Visual Basic</span></span>
<span data-ttu-id="cefa7-103">比较运算符比较两个表达式，并返回`Boolean`值，该值表示其值的关系。</span><span class="sxs-lookup"><span data-stu-id="cefa7-103">Comparison operators compare two expressions and return a `Boolean` value that represents the relationship of their values.</span></span> <span data-ttu-id="cefa7-104">有关比较数值，用于比较字符串，运算符和运算符对于比较对象有运算符。</span><span class="sxs-lookup"><span data-stu-id="cefa7-104">There are operators for comparing numeric values, operators for comparing strings, and operators for comparing objects.</span></span> <span data-ttu-id="cefa7-105">此处讨论了所有三种类型的运算符。</span><span class="sxs-lookup"><span data-stu-id="cefa7-105">All three types of operators are discussed herein.</span></span>  
  
## <a name="comparing-numeric-values"></a><span data-ttu-id="cefa7-106">比较数值</span><span class="sxs-lookup"><span data-stu-id="cefa7-106">Comparing Numeric Values</span></span>  
 <span data-ttu-id="cefa7-107">Visual Basic 使用六个数值比较运算符的数字值进行比较。</span><span class="sxs-lookup"><span data-stu-id="cefa7-107">Visual Basic compares numeric values using six numeric comparison operators.</span></span> <span data-ttu-id="cefa7-108">每个运算符将两个表达式计算结果为数字值作为操作数。</span><span class="sxs-lookup"><span data-stu-id="cefa7-108">Each operator takes as operands two expressions that evaluate to numeric values.</span></span> <span data-ttu-id="cefa7-109">下表列出了运算符，并显示每个示例。</span><span class="sxs-lookup"><span data-stu-id="cefa7-109">The following table lists the operators and shows examples of each.</span></span>  
  
|<span data-ttu-id="cefa7-110">运算符</span><span class="sxs-lookup"><span data-stu-id="cefa7-110">Operator</span></span>|<span data-ttu-id="cefa7-111">测试的条件</span><span class="sxs-lookup"><span data-stu-id="cefa7-111">Condition tested</span></span>|<span data-ttu-id="cefa7-112">示例</span><span class="sxs-lookup"><span data-stu-id="cefa7-112">Examples</span></span>|  
|--------------|----------------------|--------------|  
|<span data-ttu-id="cefa7-113">`=` （相等）</span><span class="sxs-lookup"><span data-stu-id="cefa7-113">`=` (Equality)</span></span>|<span data-ttu-id="cefa7-114">第一个表达式相等的值是否为第二个值？</span><span class="sxs-lookup"><span data-stu-id="cefa7-114">Is the value of the first expression equal to the value of the second?</span></span>|<span data-ttu-id="cefa7-115">`23`   `=`   `33    ' False`</span><span class="sxs-lookup"><span data-stu-id="cefa7-115">`23`   `=`   `33    ' False`</span></span><br /><br /> <span data-ttu-id="cefa7-116">`23`   `=`   `23    ' True`</span><span class="sxs-lookup"><span data-stu-id="cefa7-116">`23`   `=`   `23    ' True`</span></span><br /><br /> <span data-ttu-id="cefa7-117">`23`   `=`   `12    ' False`</span><span class="sxs-lookup"><span data-stu-id="cefa7-117">`23`   `=`   `12    ' False`</span></span>|  
|<span data-ttu-id="cefa7-118">`<>` （不等）</span><span class="sxs-lookup"><span data-stu-id="cefa7-118">`<>` (Inequality)</span></span>|<span data-ttu-id="cefa7-119">是第一个表达式的值不等于第二个值？</span><span class="sxs-lookup"><span data-stu-id="cefa7-119">Is the value of the first expression unequal to the value of the second?</span></span>|<span data-ttu-id="cefa7-120">`23`   `<>`   `33    ' True`</span><span class="sxs-lookup"><span data-stu-id="cefa7-120">`23`   `<>`   `33    ' True`</span></span><br /><br /> <span data-ttu-id="cefa7-121">`23`   `<>`   `23    ' False`</span><span class="sxs-lookup"><span data-stu-id="cefa7-121">`23`   `<>`   `23    ' False`</span></span><br /><br /> <span data-ttu-id="cefa7-122">`23`   `<>`   `12    ' True`</span><span class="sxs-lookup"><span data-stu-id="cefa7-122">`23`   `<>`   `12    ' True`</span></span>|  
|<span data-ttu-id="cefa7-123">`<` （小于）</span><span class="sxs-lookup"><span data-stu-id="cefa7-123">`<` (Less than)</span></span>|<span data-ttu-id="cefa7-124">第一个表达式的值小于第二个值是多少？</span><span class="sxs-lookup"><span data-stu-id="cefa7-124">Is the value of the first expression less than the value of the second?</span></span>|<span data-ttu-id="cefa7-125">`23`   `<`   `33    ' True`</span><span class="sxs-lookup"><span data-stu-id="cefa7-125">`23`   `<`   `33    ' True`</span></span><br /><br /> <span data-ttu-id="cefa7-126">`23`   `<`   `23    ' False`</span><span class="sxs-lookup"><span data-stu-id="cefa7-126">`23`   `<`   `23    ' False`</span></span><br /><br /> <span data-ttu-id="cefa7-127">`23`   `<`   `12    ' False`</span><span class="sxs-lookup"><span data-stu-id="cefa7-127">`23`   `<`   `12    ' False`</span></span>|  
|<span data-ttu-id="cefa7-128">`>` （大于）</span><span class="sxs-lookup"><span data-stu-id="cefa7-128">`>` (Greater than)</span></span>|<span data-ttu-id="cefa7-129">是第一个表达式的值大于第二个值？</span><span class="sxs-lookup"><span data-stu-id="cefa7-129">Is the value of the first expression greater than the value of the second?</span></span>|<span data-ttu-id="cefa7-130">`23`   `>`   `33    ' False`</span><span class="sxs-lookup"><span data-stu-id="cefa7-130">`23`   `>`   `33    ' False`</span></span><br /><br /> <span data-ttu-id="cefa7-131">`23`   `>`   `23    ' False`</span><span class="sxs-lookup"><span data-stu-id="cefa7-131">`23`   `>`   `23    ' False`</span></span><br /><br /> <span data-ttu-id="cefa7-132">`23`   `>`   `12    ' True`</span><span class="sxs-lookup"><span data-stu-id="cefa7-132">`23`   `>`   `12    ' True`</span></span>|  
|<span data-ttu-id="cefa7-133">`<=` （小于或等于）</span><span class="sxs-lookup"><span data-stu-id="cefa7-133">`<=` (Less than or equal to)</span></span>|<span data-ttu-id="cefa7-134">是第一个表达式的值小于或等于第二个值？</span><span class="sxs-lookup"><span data-stu-id="cefa7-134">Is the value of the first expression less than or equal to the value of the second?</span></span>|<span data-ttu-id="cefa7-135">`23`   `<=`   `33    ' True`</span><span class="sxs-lookup"><span data-stu-id="cefa7-135">`23`   `<=`   `33    ' True`</span></span><br /><br /> <span data-ttu-id="cefa7-136">`23`   `<=`   `23    ' True`</span><span class="sxs-lookup"><span data-stu-id="cefa7-136">`23`   `<=`   `23    ' True`</span></span><br /><br /> <span data-ttu-id="cefa7-137">`23`   `<=`   `12    ' False`</span><span class="sxs-lookup"><span data-stu-id="cefa7-137">`23`   `<=`   `12    ' False`</span></span>|  
|<span data-ttu-id="cefa7-138">`>=` （大于或等于）</span><span class="sxs-lookup"><span data-stu-id="cefa7-138">`>=` (Greater than or equal to)</span></span>|<span data-ttu-id="cefa7-139">是第一个表达式的值大于或等于第二个值？</span><span class="sxs-lookup"><span data-stu-id="cefa7-139">Is the value of the first expression greater than or equal to the value of the second?</span></span>|<span data-ttu-id="cefa7-140">`23`   `>=`   `33    ' False`</span><span class="sxs-lookup"><span data-stu-id="cefa7-140">`23`   `>=`   `33    ' False`</span></span><br /><br /> <span data-ttu-id="cefa7-141">`23`   `>=`   `23    ' True`</span><span class="sxs-lookup"><span data-stu-id="cefa7-141">`23`   `>=`   `23    ' True`</span></span><br /><br /> <span data-ttu-id="cefa7-142">`23`   `>=`   `12    ' True`</span><span class="sxs-lookup"><span data-stu-id="cefa7-142">`23`   `>=`   `12    ' True`</span></span>|  
  
## <a name="comparing-strings"></a><span data-ttu-id="cefa7-143">比较字符串</span><span class="sxs-lookup"><span data-stu-id="cefa7-143">Comparing Strings</span></span>  
 <span data-ttu-id="cefa7-144">Visual Basic 比较字符串使用[Like 运算符](../../../../visual-basic/language-reference/operators/like-operator.md)以及数值比较运算符。</span><span class="sxs-lookup"><span data-stu-id="cefa7-144">Visual Basic compares strings using the [Like Operator](../../../../visual-basic/language-reference/operators/like-operator.md) as well as the numeric comparison operators.</span></span> <span data-ttu-id="cefa7-145">`Like`运算符，你可以指定的模式。</span><span class="sxs-lookup"><span data-stu-id="cefa7-145">The `Like` operator allows you to specify a pattern.</span></span> <span data-ttu-id="cefa7-146">针对的模式，然后比较字符串和如果匹配，则结果是`True`。</span><span class="sxs-lookup"><span data-stu-id="cefa7-146">The string is then compared against the pattern, and if it matches, the result is `True`.</span></span> <span data-ttu-id="cefa7-147">否则，结果是`False`。</span><span class="sxs-lookup"><span data-stu-id="cefa7-147">Otherwise, the result is `False`.</span></span> <span data-ttu-id="cefa7-148">数值运算符，你可以比较`String`值基于其排序顺序，如以下示例所示。</span><span class="sxs-lookup"><span data-stu-id="cefa7-148">The numeric operators allow you to compare `String` values based on their sort order, as the following example shows.</span></span>  
  
 `"73" < "9"`  
  
 `' The result of the preceding comparison is True.`  
  
 <span data-ttu-id="cefa7-149">前面的示例中的结果将`True`因为第一个字符串中的第一个字符的排序之前第二个字符串中的第一个字符。</span><span class="sxs-lookup"><span data-stu-id="cefa7-149">The result in the preceding example is `True` because the first character in the first string sorts before the first character in the second string.</span></span> <span data-ttu-id="cefa7-150">如果第一个字符相等，比较将继续到两个字符串中的下一个字符，依次类推。</span><span class="sxs-lookup"><span data-stu-id="cefa7-150">If the first characters were equal, the comparison would continue to the next character in both strings, and so on.</span></span> <span data-ttu-id="cefa7-151">你还可以测试使用相等运算符，如以下示例所示的字符串相等。</span><span class="sxs-lookup"><span data-stu-id="cefa7-151">You can also test equality of strings using the equality operator, as the following example shows.</span></span>  
  
 `"734" = "734"`  
  
 `' The result of the preceding comparison is True.`  
  
 <span data-ttu-id="cefa7-152">如果一个字符串是否与另一一个前缀，例如"aa"和"aaa"，则被视为较长的字符串可大于较短的字符串。</span><span class="sxs-lookup"><span data-stu-id="cefa7-152">If one string is a prefix of another, such as "aa" and "aaa", the longer string is considered to be greater than the shorter string.</span></span> <span data-ttu-id="cefa7-153">下面的示例阐释了这一点。</span><span class="sxs-lookup"><span data-stu-id="cefa7-153">The following example illustrates this.</span></span>  
  
 `"aaa" > "aa"`  
  
 `' The result of the preceding comparison is True.`  
  
 <span data-ttu-id="cefa7-154">排序顺序基于二进制比较或具体取决于的设置的文本比较`Option Compare`。</span><span class="sxs-lookup"><span data-stu-id="cefa7-154">The sort order is based on either a binary comparison or a textual comparison depending on the setting of `Option Compare`.</span></span> <span data-ttu-id="cefa7-155">有关详细信息请参阅[选项比较语句](../../../../visual-basic/language-reference/statements/option-compare-statement.md)。</span><span class="sxs-lookup"><span data-stu-id="cefa7-155">For more information see [Option Compare Statement](../../../../visual-basic/language-reference/statements/option-compare-statement.md).</span></span>  
  
## <a name="comparing-objects"></a><span data-ttu-id="cefa7-156">比较对象</span><span class="sxs-lookup"><span data-stu-id="cefa7-156">Comparing Objects</span></span>  
 <span data-ttu-id="cefa7-157">Visual Basic 比较两个对象引用变量与[Is 运算符](../../../../visual-basic/language-reference/operators/is-operator.md)和[IsNot 运算符](../../../../visual-basic/language-reference/operators/isnot-operator.md)。</span><span class="sxs-lookup"><span data-stu-id="cefa7-157">Visual Basic compares two object reference variables with the [Is Operator](../../../../visual-basic/language-reference/operators/is-operator.md) and the [IsNot Operator](../../../../visual-basic/language-reference/operators/isnot-operator.md).</span></span> <span data-ttu-id="cefa7-158">你可以使用其中任一运算符以确定是否两个引用变量引用同一对象实例。</span><span class="sxs-lookup"><span data-stu-id="cefa7-158">You can use either of these operators to determine if two reference variables refer to the same object instance.</span></span> <span data-ttu-id="cefa7-159">下面的示例阐释了这一点。</span><span class="sxs-lookup"><span data-stu-id="cefa7-159">The following example illustrates this.</span></span>  
  
 [!code-vb[VbVbalrOperators#65](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/comparison-operators_1.vb)]  
  
 <span data-ttu-id="cefa7-160">在前面的示例中，`x Is y`计算结果为`True`，因为这两个变量引用相同实例。</span><span class="sxs-lookup"><span data-stu-id="cefa7-160">In the preceding example, `x Is y` evaluates to `True`, because both variables refer to the same instance.</span></span> <span data-ttu-id="cefa7-161">将此结果与下面的示例作一个对比。</span><span class="sxs-lookup"><span data-stu-id="cefa7-161">Contrast this result with the following example.</span></span>  
  
 [!code-vb[VbVbalrOperators#66](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/comparison-operators_2.vb)]  
  
 <span data-ttu-id="cefa7-162">在前面的示例中，`x Is y`计算结果为`False`，因为尽管两个变量引用指向同一类型的对象，它们是指该类型的不同实例。</span><span class="sxs-lookup"><span data-stu-id="cefa7-162">In the preceding example, `x Is y` evaluates to `False`, because although the variables refer to objects of the same type, they refer to different instances of that type.</span></span>  
  
 <span data-ttu-id="cefa7-163">当你想要测试的两个对象不指向同一个实例，`IsNot`运算符可以帮助您避免的语法非常笨拙组合`Not`和`Is`。</span><span class="sxs-lookup"><span data-stu-id="cefa7-163">When you want to test for two objects not pointing to the same instance, the `IsNot` operator lets you avoid a grammatically clumsy combination of `Not` and `Is`.</span></span> <span data-ttu-id="cefa7-164">下面的示例阐释了这一点。</span><span class="sxs-lookup"><span data-stu-id="cefa7-164">The following example illustrates this.</span></span>  
  
 [!code-vb[VbVbalrOperators#67](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/comparison-operators_3.vb)]  
  
 <span data-ttu-id="cefa7-165">在前面的示例中，`If a IsNot b`等效于`If Not a Is b`。</span><span class="sxs-lookup"><span data-stu-id="cefa7-165">In the preceding example, `If a IsNot b` is equivalent to `If Not a Is b`.</span></span>  
  
### <a name="comparing-object-type"></a><span data-ttu-id="cefa7-166">比较对象类型</span><span class="sxs-lookup"><span data-stu-id="cefa7-166">Comparing Object Type</span></span>  
 <span data-ttu-id="cefa7-167">你可以测试是否具有特定类型的对象是`TypeOf`...`Is`表达式。</span><span class="sxs-lookup"><span data-stu-id="cefa7-167">You can test whether an object is of a particular type with the `TypeOf`...`Is` expression.</span></span> <span data-ttu-id="cefa7-168">语法如下所示：</span><span class="sxs-lookup"><span data-stu-id="cefa7-168">The syntax is as follows:</span></span>  
  
 `TypeOf <objectexpression> Is <typename>`  
  
 <span data-ttu-id="cefa7-169">当`typename`指定接口类型，则`TypeOf`...`Is`表达式返回`True`如果对象实现的接口类型。</span><span class="sxs-lookup"><span data-stu-id="cefa7-169">When `typename` specifies an interface type, then the `TypeOf`...`Is` expression returns `True` if the object implements the interface type.</span></span> <span data-ttu-id="cefa7-170">当`typename`是类类型，则该表达式返回`True`如果对象是指定类或派生自指定类的类的实例。</span><span class="sxs-lookup"><span data-stu-id="cefa7-170">When `typename` is a class type, then the expression returns `True` if the object is an instance of the specified class or of a class that derives from the specified class.</span></span> <span data-ttu-id="cefa7-171">下面的示例阐释了这一点。</span><span class="sxs-lookup"><span data-stu-id="cefa7-171">The following example illustrates this.</span></span>  
  
 [!code-vb[VbVbalrOperators#68](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/comparison-operators_4.vb)]  
  
 <span data-ttu-id="cefa7-172">在前面的示例中，`TypeOf x Is Control`表达式计算结果为`True`因为的一种`x`是`Button`，它继承自`Control`。</span><span class="sxs-lookup"><span data-stu-id="cefa7-172">In the preceding example, the `TypeOf x Is Control` expression evaluates to `True` because the type of `x` is `Button`, which inherits from `Control`.</span></span>  
  
 <span data-ttu-id="cefa7-173">有关详细信息，请参阅[TypeOf 运算符](../../../../visual-basic/language-reference/operators/typeof-operator.md)。</span><span class="sxs-lookup"><span data-stu-id="cefa7-173">For more information, see [TypeOf Operator](../../../../visual-basic/language-reference/operators/typeof-operator.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cefa7-174">请参阅</span><span class="sxs-lookup"><span data-stu-id="cefa7-174">See Also</span></span>  
 [<span data-ttu-id="cefa7-175">值的比较</span><span class="sxs-lookup"><span data-stu-id="cefa7-175">Value Comparisons</span></span>](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/value-comparisons.md)  
 [<span data-ttu-id="cefa7-176">比较运算符</span><span class="sxs-lookup"><span data-stu-id="cefa7-176">Comparison Operators</span></span>](../../../../visual-basic/language-reference/operators/comparison-operators.md)  
 [<span data-ttu-id="cefa7-177">运算符</span><span class="sxs-lookup"><span data-stu-id="cefa7-177">Operators</span></span>](../../../../visual-basic/language-reference/operators/index.md)  
 [<span data-ttu-id="cefa7-178">在 Visual Basic 中的算术运算符</span><span class="sxs-lookup"><span data-stu-id="cefa7-178">Arithmetic Operators in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/arithmetic-operators.md)  
 [<span data-ttu-id="cefa7-179">在 Visual Basic 中的串联运算符</span><span class="sxs-lookup"><span data-stu-id="cefa7-179">Concatenation Operators in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/concatenation-operators.md)  
 [<span data-ttu-id="cefa7-180">在 Visual Basic 中的逻辑和按位运算符</span><span class="sxs-lookup"><span data-stu-id="cefa7-180">Logical and Bitwise Operators in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/logical-and-bitwise-operators.md)
