---
title: 比较运算符
ms.date: 07/20/2015
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
ms.openlocfilehash: e1feb08539e47ec6fda64aa1a1f8ec2cc19f7b62
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/22/2019
ms.locfileid: "74346069"
---
# <a name="comparison-operators-in-visual-basic"></a><span data-ttu-id="889a7-102">Comparison Operators in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="889a7-102">Comparison Operators in Visual Basic</span></span>
<span data-ttu-id="889a7-103">比较运算符比较两个表达式，并返回一个表示其值的关系的 `Boolean` 值。</span><span class="sxs-lookup"><span data-stu-id="889a7-103">Comparison operators compare two expressions and return a `Boolean` value that represents the relationship of their values.</span></span> <span data-ttu-id="889a7-104">有一些运算符用于比较数值、用于比较字符串的运算符以及用于比较对象的运算符。</span><span class="sxs-lookup"><span data-stu-id="889a7-104">There are operators for comparing numeric values, operators for comparing strings, and operators for comparing objects.</span></span> <span data-ttu-id="889a7-105">这里讨论了所有这三种类型的运算符。</span><span class="sxs-lookup"><span data-stu-id="889a7-105">All three types of operators are discussed herein.</span></span>  
  
## <a name="comparing-numeric-values"></a><span data-ttu-id="889a7-106">比较数值</span><span class="sxs-lookup"><span data-stu-id="889a7-106">Comparing Numeric Values</span></span>  
 <span data-ttu-id="889a7-107">Visual Basic 使用六个数值比较运算符比较数值。</span><span class="sxs-lookup"><span data-stu-id="889a7-107">Visual Basic compares numeric values using six numeric comparison operators.</span></span> <span data-ttu-id="889a7-108">每个运算符都采用两个计算为数值的表达式作为操作数。</span><span class="sxs-lookup"><span data-stu-id="889a7-108">Each operator takes as operands two expressions that evaluate to numeric values.</span></span> <span data-ttu-id="889a7-109">下表列出了运算符，并显示了每个运算符的示例。</span><span class="sxs-lookup"><span data-stu-id="889a7-109">The following table lists the operators and shows examples of each.</span></span>  
  
|<span data-ttu-id="889a7-110">运算符</span><span class="sxs-lookup"><span data-stu-id="889a7-110">Operator</span></span>|<span data-ttu-id="889a7-111">测试的条件</span><span class="sxs-lookup"><span data-stu-id="889a7-111">Condition tested</span></span>|<span data-ttu-id="889a7-112">示例</span><span class="sxs-lookup"><span data-stu-id="889a7-112">Examples</span></span>|  
|--------------|----------------------|--------------|  
|<span data-ttu-id="889a7-113">`=` （等于）</span><span class="sxs-lookup"><span data-stu-id="889a7-113">`=` (Equality)</span></span>|<span data-ttu-id="889a7-114">第一个表达式的值是否等于第二个表达式的值？</span><span class="sxs-lookup"><span data-stu-id="889a7-114">Is the value of the first expression equal to the value of the second?</span></span>|<span data-ttu-id="889a7-115">`23`   `=`   `33    ' False`</span><span class="sxs-lookup"><span data-stu-id="889a7-115">`23`   `=`   `33    ' False`</span></span><br /><br /> <span data-ttu-id="889a7-116">`23`   `=`   `23    ' True`</span><span class="sxs-lookup"><span data-stu-id="889a7-116">`23`   `=`   `23    ' True`</span></span><br /><br /> <span data-ttu-id="889a7-117">`23`   `=`   `12    ' False`</span><span class="sxs-lookup"><span data-stu-id="889a7-117">`23`   `=`   `12    ' False`</span></span>|  
|<span data-ttu-id="889a7-118">`<>` （不等于）</span><span class="sxs-lookup"><span data-stu-id="889a7-118">`<>` (Inequality)</span></span>|<span data-ttu-id="889a7-119">第一个表达式的值是否与第二个表达式的值不相等？</span><span class="sxs-lookup"><span data-stu-id="889a7-119">Is the value of the first expression unequal to the value of the second?</span></span>|<span data-ttu-id="889a7-120">`23`   `<>`   `33    ' True`</span><span class="sxs-lookup"><span data-stu-id="889a7-120">`23`   `<>`   `33    ' True`</span></span><br /><br /> <span data-ttu-id="889a7-121">`23`   `<>`   `23    ' False`</span><span class="sxs-lookup"><span data-stu-id="889a7-121">`23`   `<>`   `23    ' False`</span></span><br /><br /> <span data-ttu-id="889a7-122">`23`   `<>`   `12    ' True`</span><span class="sxs-lookup"><span data-stu-id="889a7-122">`23`   `<>`   `12    ' True`</span></span>|  
|<span data-ttu-id="889a7-123">`<` （小于）</span><span class="sxs-lookup"><span data-stu-id="889a7-123">`<` (Less than)</span></span>|<span data-ttu-id="889a7-124">第一个表达式的值是否小于第二个表达式的值？</span><span class="sxs-lookup"><span data-stu-id="889a7-124">Is the value of the first expression less than the value of the second?</span></span>|<span data-ttu-id="889a7-125">`23`   `<`   `33    ' True`</span><span class="sxs-lookup"><span data-stu-id="889a7-125">`23`   `<`   `33    ' True`</span></span><br /><br /> <span data-ttu-id="889a7-126">`23`   `<`   `23    ' False`</span><span class="sxs-lookup"><span data-stu-id="889a7-126">`23`   `<`   `23    ' False`</span></span><br /><br /> <span data-ttu-id="889a7-127">`23`   `<`   `12    ' False`</span><span class="sxs-lookup"><span data-stu-id="889a7-127">`23`   `<`   `12    ' False`</span></span>|  
|<span data-ttu-id="889a7-128">`>` （大于）</span><span class="sxs-lookup"><span data-stu-id="889a7-128">`>` (Greater than)</span></span>|<span data-ttu-id="889a7-129">第一个表达式的值是否大于第二个表达式的值？</span><span class="sxs-lookup"><span data-stu-id="889a7-129">Is the value of the first expression greater than the value of the second?</span></span>|<span data-ttu-id="889a7-130">`23`   `>`   `33    ' False`</span><span class="sxs-lookup"><span data-stu-id="889a7-130">`23`   `>`   `33    ' False`</span></span><br /><br /> <span data-ttu-id="889a7-131">`23`   `>`   `23    ' False`</span><span class="sxs-lookup"><span data-stu-id="889a7-131">`23`   `>`   `23    ' False`</span></span><br /><br /> <span data-ttu-id="889a7-132">`23`   `>`   `12    ' True`</span><span class="sxs-lookup"><span data-stu-id="889a7-132">`23`   `>`   `12    ' True`</span></span>|  
|<span data-ttu-id="889a7-133">`<=` （小于或等于）</span><span class="sxs-lookup"><span data-stu-id="889a7-133">`<=` (Less than or equal to)</span></span>|<span data-ttu-id="889a7-134">第一个表达式的值是否小于或等于第二个表达式的值？</span><span class="sxs-lookup"><span data-stu-id="889a7-134">Is the value of the first expression less than or equal to the value of the second?</span></span>|<span data-ttu-id="889a7-135">`23`   `<=`   `33    ' True`</span><span class="sxs-lookup"><span data-stu-id="889a7-135">`23`   `<=`   `33    ' True`</span></span><br /><br /> <span data-ttu-id="889a7-136">`23`   `<=`   `23    ' True`</span><span class="sxs-lookup"><span data-stu-id="889a7-136">`23`   `<=`   `23    ' True`</span></span><br /><br /> <span data-ttu-id="889a7-137">`23`   `<=`   `12    ' False`</span><span class="sxs-lookup"><span data-stu-id="889a7-137">`23`   `<=`   `12    ' False`</span></span>|  
|<span data-ttu-id="889a7-138">`>=` （大于或等于）</span><span class="sxs-lookup"><span data-stu-id="889a7-138">`>=` (Greater than or equal to)</span></span>|<span data-ttu-id="889a7-139">第一个表达式的值是否大于或等于第二个表达式的值？</span><span class="sxs-lookup"><span data-stu-id="889a7-139">Is the value of the first expression greater than or equal to the value of the second?</span></span>|<span data-ttu-id="889a7-140">`23`   `>=`   `33    ' False`</span><span class="sxs-lookup"><span data-stu-id="889a7-140">`23`   `>=`   `33    ' False`</span></span><br /><br /> <span data-ttu-id="889a7-141">`23`   `>=`   `23    ' True`</span><span class="sxs-lookup"><span data-stu-id="889a7-141">`23`   `>=`   `23    ' True`</span></span><br /><br /> <span data-ttu-id="889a7-142">`23`   `>=`   `12    ' True`</span><span class="sxs-lookup"><span data-stu-id="889a7-142">`23`   `>=`   `12    ' True`</span></span>|  
  
## <a name="comparing-strings"></a><span data-ttu-id="889a7-143">比较字符串</span><span class="sxs-lookup"><span data-stu-id="889a7-143">Comparing Strings</span></span>  
 <span data-ttu-id="889a7-144">Visual Basic 使用[Like 运算符](../../../../visual-basic/language-reference/operators/like-operator.md)以及数字比较运算符来比较字符串。</span><span class="sxs-lookup"><span data-stu-id="889a7-144">Visual Basic compares strings using the [Like Operator](../../../../visual-basic/language-reference/operators/like-operator.md) as well as the numeric comparison operators.</span></span> <span data-ttu-id="889a7-145">使用 `Like` 运算符可以指定模式。</span><span class="sxs-lookup"><span data-stu-id="889a7-145">The `Like` operator allows you to specify a pattern.</span></span> <span data-ttu-id="889a7-146">然后，将该字符串与模式进行比较，如果匹配，则 `True`结果。</span><span class="sxs-lookup"><span data-stu-id="889a7-146">The string is then compared against the pattern, and if it matches, the result is `True`.</span></span> <span data-ttu-id="889a7-147">否则，结果为 `False`。</span><span class="sxs-lookup"><span data-stu-id="889a7-147">Otherwise, the result is `False`.</span></span> <span data-ttu-id="889a7-148">数字运算符使你可以基于它们的排序顺序比较 `String` 值，如下面的示例所示。</span><span class="sxs-lookup"><span data-stu-id="889a7-148">The numeric operators allow you to compare `String` values based on their sort order, as the following example shows.</span></span>  
  
 `"73" < "9"`  
  
 `' The result of the preceding comparison is True.`  
  
 <span data-ttu-id="889a7-149">由于第一个字符串中的第一个字符排在第二个字符串中的第一个字符之前，因此 `True` 前面的示例中的结果。</span><span class="sxs-lookup"><span data-stu-id="889a7-149">The result in the preceding example is `True` because the first character in the first string sorts before the first character in the second string.</span></span> <span data-ttu-id="889a7-150">如果第一个字符相等，则比较将继续执行两个字符串中的下一个字符，依此类推。</span><span class="sxs-lookup"><span data-stu-id="889a7-150">If the first characters were equal, the comparison would continue to the next character in both strings, and so on.</span></span> <span data-ttu-id="889a7-151">你还可以使用相等运算符测试字符串的相等性，如下面的示例所示。</span><span class="sxs-lookup"><span data-stu-id="889a7-151">You can also test equality of strings using the equality operator, as the following example shows.</span></span>  
  
 `"734" = "734"`  
  
 `' The result of the preceding comparison is True.`  
  
 <span data-ttu-id="889a7-152">如果一个字符串是另一个字符串的前缀（如 "aa" 和 "aaa"），则较长的字符串将被视为大于较短的字符串。</span><span class="sxs-lookup"><span data-stu-id="889a7-152">If one string is a prefix of another, such as "aa" and "aaa", the longer string is considered to be greater than the shorter string.</span></span> <span data-ttu-id="889a7-153">下面的示例对此进行了演示。</span><span class="sxs-lookup"><span data-stu-id="889a7-153">The following example illustrates this.</span></span>  
  
 `"aaa" > "aa"`  
  
 `' The result of the preceding comparison is True.`  
  
 <span data-ttu-id="889a7-154">根据 `Option Compare`的设置，排序顺序基于二进制比较或文本比较。</span><span class="sxs-lookup"><span data-stu-id="889a7-154">The sort order is based on either a binary comparison or a textual comparison depending on the setting of `Option Compare`.</span></span> <span data-ttu-id="889a7-155">有关详细信息，请参阅[Option Compare 语句](../../../../visual-basic/language-reference/statements/option-compare-statement.md)。</span><span class="sxs-lookup"><span data-stu-id="889a7-155">For more information see [Option Compare Statement](../../../../visual-basic/language-reference/statements/option-compare-statement.md).</span></span>  
  
## <a name="comparing-objects"></a><span data-ttu-id="889a7-156">比较对象</span><span class="sxs-lookup"><span data-stu-id="889a7-156">Comparing Objects</span></span>  
 <span data-ttu-id="889a7-157">Visual Basic 将两个对象引用变量与[Is 运算符](../../../../visual-basic/language-reference/operators/is-operator.md)和[IsNot 运算符](../../../../visual-basic/language-reference/operators/isnot-operator.md)进行比较。</span><span class="sxs-lookup"><span data-stu-id="889a7-157">Visual Basic compares two object reference variables with the [Is Operator](../../../../visual-basic/language-reference/operators/is-operator.md) and the [IsNot Operator](../../../../visual-basic/language-reference/operators/isnot-operator.md).</span></span> <span data-ttu-id="889a7-158">您可以使用其中任一运算符来确定两个引用变量是否引用同一对象实例。</span><span class="sxs-lookup"><span data-stu-id="889a7-158">You can use either of these operators to determine if two reference variables refer to the same object instance.</span></span> <span data-ttu-id="889a7-159">下面的示例对此进行了演示。</span><span class="sxs-lookup"><span data-stu-id="889a7-159">The following example illustrates this.</span></span>  
  
 [!code-vb[VbVbalrOperators#65](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#65)]  
  
 <span data-ttu-id="889a7-160">在前面的示例中，`x Is y` 的计算结果为 `True`，因为这两个变量引用相同的实例。</span><span class="sxs-lookup"><span data-stu-id="889a7-160">In the preceding example, `x Is y` evaluates to `True`, because both variables refer to the same instance.</span></span> <span data-ttu-id="889a7-161">将此结果与下面的示例进行比较。</span><span class="sxs-lookup"><span data-stu-id="889a7-161">Contrast this result with the following example.</span></span>  
  
 [!code-vb[VbVbalrOperators#66](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#66)]  
  
 <span data-ttu-id="889a7-162">在前面的示例中，`x Is y` 的计算结果为 `False`，因为尽管变量引用相同类型的对象，但它们引用该类型的不同实例。</span><span class="sxs-lookup"><span data-stu-id="889a7-162">In the preceding example, `x Is y` evaluates to `False`, because although the variables refer to objects of the same type, they refer to different instances of that type.</span></span>  
  
 <span data-ttu-id="889a7-163">如果要测试两个不指向同一实例的对象，则 `IsNot` 运算符使你可以避免使用 `Not` 和 `Is`的语法笨拙组合。</span><span class="sxs-lookup"><span data-stu-id="889a7-163">When you want to test for two objects not pointing to the same instance, the `IsNot` operator lets you avoid a grammatically clumsy combination of `Not` and `Is`.</span></span> <span data-ttu-id="889a7-164">下面的示例对此进行了演示。</span><span class="sxs-lookup"><span data-stu-id="889a7-164">The following example illustrates this.</span></span>  
  
 [!code-vb[VbVbalrOperators#67](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#67)]  
  
 <span data-ttu-id="889a7-165">在前面的示例中，`If a IsNot b` 等效于 `If Not a Is b`。</span><span class="sxs-lookup"><span data-stu-id="889a7-165">In the preceding example, `If a IsNot b` is equivalent to `If Not a Is b`.</span></span>  
  
### <a name="comparing-object-type"></a><span data-ttu-id="889a7-166">比较对象类型</span><span class="sxs-lookup"><span data-stu-id="889a7-166">Comparing Object Type</span></span>  
 <span data-ttu-id="889a7-167">您可以使用 `TypeOf`...`Is` 表达式测试对象是否为特定类型。</span><span class="sxs-lookup"><span data-stu-id="889a7-167">You can test whether an object is of a particular type with the `TypeOf`...`Is` expression.</span></span> <span data-ttu-id="889a7-168">语法如下所示：</span><span class="sxs-lookup"><span data-stu-id="889a7-168">The syntax is as follows:</span></span>  
  
 `TypeOf <objectexpression> Is <typename>`  
  
 <span data-ttu-id="889a7-169">当 `typename` 指定接口类型时，如果对象实现接口类型，则 `TypeOf``Is` 表达式将返回 `True`。</span><span class="sxs-lookup"><span data-stu-id="889a7-169">When `typename` specifies an interface type, then the `TypeOf`...`Is` expression returns `True` if the object implements the interface type.</span></span> <span data-ttu-id="889a7-170">当 `typename` 为类类型时，如果该对象是指定类的实例或从指定类派生的类的实例，则表达式返回 `True`。</span><span class="sxs-lookup"><span data-stu-id="889a7-170">When `typename` is a class type, then the expression returns `True` if the object is an instance of the specified class or of a class that derives from the specified class.</span></span> <span data-ttu-id="889a7-171">下面的示例对此进行了演示。</span><span class="sxs-lookup"><span data-stu-id="889a7-171">The following example illustrates this.</span></span>  
  
 [!code-vb[VbVbalrOperators#68](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#68)]  
  
 <span data-ttu-id="889a7-172">在前面的示例中，`TypeOf x Is Control` 表达式的计算结果为 `True`，因为 `x` 的类型是 `Button`，后者从 `Control`继承。</span><span class="sxs-lookup"><span data-stu-id="889a7-172">In the preceding example, the `TypeOf x Is Control` expression evaluates to `True` because the type of `x` is `Button`, which inherits from `Control`.</span></span>  
  
 <span data-ttu-id="889a7-173">有关详细信息，请参阅[TypeOf 运算符](../../../../visual-basic/language-reference/operators/typeof-operator.md)。</span><span class="sxs-lookup"><span data-stu-id="889a7-173">For more information, see [TypeOf Operator](../../../../visual-basic/language-reference/operators/typeof-operator.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="889a7-174">另请参阅</span><span class="sxs-lookup"><span data-stu-id="889a7-174">See also</span></span>

- [<span data-ttu-id="889a7-175">值的比较</span><span class="sxs-lookup"><span data-stu-id="889a7-175">Value Comparisons</span></span>](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/value-comparisons.md)
- [<span data-ttu-id="889a7-176">比较运算符</span><span class="sxs-lookup"><span data-stu-id="889a7-176">Comparison Operators</span></span>](../../../../visual-basic/language-reference/operators/comparison-operators.md)
- [<span data-ttu-id="889a7-177">运算符</span><span class="sxs-lookup"><span data-stu-id="889a7-177">Operators</span></span>](../../../../visual-basic/language-reference/operators/index.md)
- [<span data-ttu-id="889a7-178">Visual Basic 中的算术运算符</span><span class="sxs-lookup"><span data-stu-id="889a7-178">Arithmetic Operators in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/arithmetic-operators.md)
- [<span data-ttu-id="889a7-179">Visual Basic 中的串联运算符</span><span class="sxs-lookup"><span data-stu-id="889a7-179">Concatenation Operators in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/concatenation-operators.md)
- [<span data-ttu-id="889a7-180">Visual Basic 中的逻辑运算符和位运算符</span><span class="sxs-lookup"><span data-stu-id="889a7-180">Logical and Bitwise Operators in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/logical-and-bitwise-operators.md)
