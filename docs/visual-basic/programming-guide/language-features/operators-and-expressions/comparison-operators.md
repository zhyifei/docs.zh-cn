---
title: Comparison Operators in Visual Basic
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
ms.openlocfilehash: d08974a929a723d4037300f9d72ae03c072d47fa
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/18/2019
ms.locfileid: "58826153"
---
# <a name="comparison-operators-in-visual-basic"></a><span data-ttu-id="aef2d-102">Comparison Operators in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="aef2d-102">Comparison Operators in Visual Basic</span></span>
<span data-ttu-id="aef2d-103">比较运算符比较两个表达式并返回`Boolean`值，该值表示其值的关系。</span><span class="sxs-lookup"><span data-stu-id="aef2d-103">Comparison operators compare two expressions and return a `Boolean` value that represents the relationship of their values.</span></span> <span data-ttu-id="aef2d-104">有运算符用于比较数字值、 字符串、 比较运算符和运算符用于比较的对象。</span><span class="sxs-lookup"><span data-stu-id="aef2d-104">There are operators for comparing numeric values, operators for comparing strings, and operators for comparing objects.</span></span> <span data-ttu-id="aef2d-105">所有三种类型的运算符是此处所述。</span><span class="sxs-lookup"><span data-stu-id="aef2d-105">All three types of operators are discussed herein.</span></span>  
  
## <a name="comparing-numeric-values"></a><span data-ttu-id="aef2d-106">比较数值</span><span class="sxs-lookup"><span data-stu-id="aef2d-106">Comparing Numeric Values</span></span>  
 <span data-ttu-id="aef2d-107">Visual Basic 将使用六个数字的比较运算符的数字值进行比较。</span><span class="sxs-lookup"><span data-stu-id="aef2d-107">Visual Basic compares numeric values using six numeric comparison operators.</span></span> <span data-ttu-id="aef2d-108">每个运算符采用两个表达式的计算结果为数字值作为操作数。</span><span class="sxs-lookup"><span data-stu-id="aef2d-108">Each operator takes as operands two expressions that evaluate to numeric values.</span></span> <span data-ttu-id="aef2d-109">下表列出的运算符，并显示了每个示例。</span><span class="sxs-lookup"><span data-stu-id="aef2d-109">The following table lists the operators and shows examples of each.</span></span>  
  
|<span data-ttu-id="aef2d-110">运算符</span><span class="sxs-lookup"><span data-stu-id="aef2d-110">Operator</span></span>|<span data-ttu-id="aef2d-111">测试条件</span><span class="sxs-lookup"><span data-stu-id="aef2d-111">Condition tested</span></span>|<span data-ttu-id="aef2d-112">示例</span><span class="sxs-lookup"><span data-stu-id="aef2d-112">Examples</span></span>|  
|--------------|----------------------|--------------|  
|<span data-ttu-id="aef2d-113">`=` （相等）</span><span class="sxs-lookup"><span data-stu-id="aef2d-113">`=` (Equality)</span></span>|<span data-ttu-id="aef2d-114">第一个表达式相等的值是否为第二个值？</span><span class="sxs-lookup"><span data-stu-id="aef2d-114">Is the value of the first expression equal to the value of the second?</span></span>|<span data-ttu-id="aef2d-115">`23`   `=`   `33    ' False`</span><span class="sxs-lookup"><span data-stu-id="aef2d-115">`23`   `=`   `33    ' False`</span></span><br /><br /> <span data-ttu-id="aef2d-116">`23`   `=`   `23    ' True`</span><span class="sxs-lookup"><span data-stu-id="aef2d-116">`23`   `=`   `23    ' True`</span></span><br /><br /> <span data-ttu-id="aef2d-117">`23`   `=`   `12    ' False`</span><span class="sxs-lookup"><span data-stu-id="aef2d-117">`23`   `=`   `12    ' False`</span></span>|  
|<span data-ttu-id="aef2d-118">`<>` （不等于）</span><span class="sxs-lookup"><span data-stu-id="aef2d-118">`<>` (Inequality)</span></span>|<span data-ttu-id="aef2d-119">第一个表达式的值是否为第二个值不相等？</span><span class="sxs-lookup"><span data-stu-id="aef2d-119">Is the value of the first expression unequal to the value of the second?</span></span>|<span data-ttu-id="aef2d-120">`23`   `<>`   `33    ' True`</span><span class="sxs-lookup"><span data-stu-id="aef2d-120">`23`   `<>`   `33    ' True`</span></span><br /><br /> <span data-ttu-id="aef2d-121">`23`   `<>`   `23    ' False`</span><span class="sxs-lookup"><span data-stu-id="aef2d-121">`23`   `<>`   `23    ' False`</span></span><br /><br /> <span data-ttu-id="aef2d-122">`23`   `<>`   `12    ' True`</span><span class="sxs-lookup"><span data-stu-id="aef2d-122">`23`   `<>`   `12    ' True`</span></span>|  
|<span data-ttu-id="aef2d-123">`<` （小于）</span><span class="sxs-lookup"><span data-stu-id="aef2d-123">`<` (Less than)</span></span>|<span data-ttu-id="aef2d-124">第一个表达式的值小于第二个值是否是？</span><span class="sxs-lookup"><span data-stu-id="aef2d-124">Is the value of the first expression less than the value of the second?</span></span>|<span data-ttu-id="aef2d-125">`23`   `<`   `33    ' True`</span><span class="sxs-lookup"><span data-stu-id="aef2d-125">`23`   `<`   `33    ' True`</span></span><br /><br /> <span data-ttu-id="aef2d-126">`23`   `<`   `23    ' False`</span><span class="sxs-lookup"><span data-stu-id="aef2d-126">`23`   `<`   `23    ' False`</span></span><br /><br /> <span data-ttu-id="aef2d-127">`23`   `<`   `12    ' False`</span><span class="sxs-lookup"><span data-stu-id="aef2d-127">`23`   `<`   `12    ' False`</span></span>|  
|<span data-ttu-id="aef2d-128">`>` （大于）</span><span class="sxs-lookup"><span data-stu-id="aef2d-128">`>` (Greater than)</span></span>|<span data-ttu-id="aef2d-129">第一个表达式的值是否大于第二个值？</span><span class="sxs-lookup"><span data-stu-id="aef2d-129">Is the value of the first expression greater than the value of the second?</span></span>|<span data-ttu-id="aef2d-130">`23`   `>`   `33    ' False`</span><span class="sxs-lookup"><span data-stu-id="aef2d-130">`23`   `>`   `33    ' False`</span></span><br /><br /> <span data-ttu-id="aef2d-131">`23`   `>`   `23    ' False`</span><span class="sxs-lookup"><span data-stu-id="aef2d-131">`23`   `>`   `23    ' False`</span></span><br /><br /> <span data-ttu-id="aef2d-132">`23`   `>`   `12    ' True`</span><span class="sxs-lookup"><span data-stu-id="aef2d-132">`23`   `>`   `12    ' True`</span></span>|  
|<span data-ttu-id="aef2d-133">`<=` （小于或等于）</span><span class="sxs-lookup"><span data-stu-id="aef2d-133">`<=` (Less than or equal to)</span></span>|<span data-ttu-id="aef2d-134">第一个表达式的值是否小于或等于第二个值？</span><span class="sxs-lookup"><span data-stu-id="aef2d-134">Is the value of the first expression less than or equal to the value of the second?</span></span>|<span data-ttu-id="aef2d-135">`23`   `<=`   `33    ' True`</span><span class="sxs-lookup"><span data-stu-id="aef2d-135">`23`   `<=`   `33    ' True`</span></span><br /><br /> <span data-ttu-id="aef2d-136">`23`   `<=`   `23    ' True`</span><span class="sxs-lookup"><span data-stu-id="aef2d-136">`23`   `<=`   `23    ' True`</span></span><br /><br /> <span data-ttu-id="aef2d-137">`23`   `<=`   `12    ' False`</span><span class="sxs-lookup"><span data-stu-id="aef2d-137">`23`   `<=`   `12    ' False`</span></span>|  
|<span data-ttu-id="aef2d-138">`>=` （大于或等于）</span><span class="sxs-lookup"><span data-stu-id="aef2d-138">`>=` (Greater than or equal to)</span></span>|<span data-ttu-id="aef2d-139">第一个表达式的值是否大于或等于第二个值？</span><span class="sxs-lookup"><span data-stu-id="aef2d-139">Is the value of the first expression greater than or equal to the value of the second?</span></span>|<span data-ttu-id="aef2d-140">`23`   `>=`   `33    ' False`</span><span class="sxs-lookup"><span data-stu-id="aef2d-140">`23`   `>=`   `33    ' False`</span></span><br /><br /> <span data-ttu-id="aef2d-141">`23`   `>=`   `23    ' True`</span><span class="sxs-lookup"><span data-stu-id="aef2d-141">`23`   `>=`   `23    ' True`</span></span><br /><br /> <span data-ttu-id="aef2d-142">`23`   `>=`   `12    ' True`</span><span class="sxs-lookup"><span data-stu-id="aef2d-142">`23`   `>=`   `12    ' True`</span></span>|  
  
## <a name="comparing-strings"></a><span data-ttu-id="aef2d-143">比较字符串</span><span class="sxs-lookup"><span data-stu-id="aef2d-143">Comparing Strings</span></span>  
 <span data-ttu-id="aef2d-144">Visual Basic 对使用的字符串进行比较[Like 运算符](../../../../visual-basic/language-reference/operators/like-operator.md)以及数值的比较运算符。</span><span class="sxs-lookup"><span data-stu-id="aef2d-144">Visual Basic compares strings using the [Like Operator](../../../../visual-basic/language-reference/operators/like-operator.md) as well as the numeric comparison operators.</span></span> <span data-ttu-id="aef2d-145">`Like`运算符允许您指定的模式。</span><span class="sxs-lookup"><span data-stu-id="aef2d-145">The `Like` operator allows you to specify a pattern.</span></span> <span data-ttu-id="aef2d-146">与指定模式进行比较的字符串，如果匹配，则结果是`True`。</span><span class="sxs-lookup"><span data-stu-id="aef2d-146">The string is then compared against the pattern, and if it matches, the result is `True`.</span></span> <span data-ttu-id="aef2d-147">否则，结果为 `False`。</span><span class="sxs-lookup"><span data-stu-id="aef2d-147">Otherwise, the result is `False`.</span></span> <span data-ttu-id="aef2d-148">数字运算符，你可以比较`String`值基于它们的排序顺序，如以下示例所示。</span><span class="sxs-lookup"><span data-stu-id="aef2d-148">The numeric operators allow you to compare `String` values based on their sort order, as the following example shows.</span></span>  
  
 `"73" < "9"`  
  
 `' The result of the preceding comparison is True.`  
  
 <span data-ttu-id="aef2d-149">在前面的示例结果是`True`因为第一个字符串中的第一个字符的排序之前第二个字符串中的第一个字符。</span><span class="sxs-lookup"><span data-stu-id="aef2d-149">The result in the preceding example is `True` because the first character in the first string sorts before the first character in the second string.</span></span> <span data-ttu-id="aef2d-150">如果第一个字符相等，比较将继续到两个字符串中的下一个字符，依此类推。</span><span class="sxs-lookup"><span data-stu-id="aef2d-150">If the first characters were equal, the comparison would continue to the next character in both strings, and so on.</span></span> <span data-ttu-id="aef2d-151">此外可以测试使用相等运算符，如以下示例所示的字符串相等。</span><span class="sxs-lookup"><span data-stu-id="aef2d-151">You can also test equality of strings using the equality operator, as the following example shows.</span></span>  
  
 `"734" = "734"`  
  
 `' The result of the preceding comparison is True.`  
  
 <span data-ttu-id="aef2d-152">如果一个字符串为前缀，如"aa"和"aaa"，被认为更长的字符串可以大于较短的字符串。</span><span class="sxs-lookup"><span data-stu-id="aef2d-152">If one string is a prefix of another, such as "aa" and "aaa", the longer string is considered to be greater than the shorter string.</span></span> <span data-ttu-id="aef2d-153">下面的示例阐释了这一点。</span><span class="sxs-lookup"><span data-stu-id="aef2d-153">The following example illustrates this.</span></span>  
  
 `"aaa" > "aa"`  
  
 `' The result of the preceding comparison is True.`  
  
 <span data-ttu-id="aef2d-154">排序顺序基于二进制比较或文本比较，具体取决于设置`Option Compare`。</span><span class="sxs-lookup"><span data-stu-id="aef2d-154">The sort order is based on either a binary comparison or a textual comparison depending on the setting of `Option Compare`.</span></span> <span data-ttu-id="aef2d-155">有关详细信息请参阅[Option 比较语句](../../../../visual-basic/language-reference/statements/option-compare-statement.md)。</span><span class="sxs-lookup"><span data-stu-id="aef2d-155">For more information see [Option Compare Statement](../../../../visual-basic/language-reference/statements/option-compare-statement.md).</span></span>  
  
## <a name="comparing-objects"></a><span data-ttu-id="aef2d-156">比较对象</span><span class="sxs-lookup"><span data-stu-id="aef2d-156">Comparing Objects</span></span>  
 <span data-ttu-id="aef2d-157">Visual Basic 使用的两个对象引用变量进行比较[Is 运算符](../../../../visual-basic/language-reference/operators/is-operator.md)并[IsNot 运算符](../../../../visual-basic/language-reference/operators/isnot-operator.md)。</span><span class="sxs-lookup"><span data-stu-id="aef2d-157">Visual Basic compares two object reference variables with the [Is Operator](../../../../visual-basic/language-reference/operators/is-operator.md) and the [IsNot Operator](../../../../visual-basic/language-reference/operators/isnot-operator.md).</span></span> <span data-ttu-id="aef2d-158">可以使用其中任一运算符确定两个引用变量引用同一对象实例。</span><span class="sxs-lookup"><span data-stu-id="aef2d-158">You can use either of these operators to determine if two reference variables refer to the same object instance.</span></span> <span data-ttu-id="aef2d-159">下面的示例阐释了这一点。</span><span class="sxs-lookup"><span data-stu-id="aef2d-159">The following example illustrates this.</span></span>  
  
 [!code-vb[VbVbalrOperators#65](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#65)]  
  
 <span data-ttu-id="aef2d-160">在前面的示例中，`x Is y`计算结果为`True`，因为这两个变量引用同一个实例。</span><span class="sxs-lookup"><span data-stu-id="aef2d-160">In the preceding example, `x Is y` evaluates to `True`, because both variables refer to the same instance.</span></span> <span data-ttu-id="aef2d-161">此结果与下面的示例进行对比。</span><span class="sxs-lookup"><span data-stu-id="aef2d-161">Contrast this result with the following example.</span></span>  
  
 [!code-vb[VbVbalrOperators#66](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#66)]  
  
 <span data-ttu-id="aef2d-162">在前面的示例中，`x Is y`计算结果为`False`，因为虽然变量引用相同类型的对象，但它们是指该类型的不同实例。</span><span class="sxs-lookup"><span data-stu-id="aef2d-162">In the preceding example, `x Is y` evaluates to `False`, because although the variables refer to objects of the same type, they refer to different instances of that type.</span></span>  
  
 <span data-ttu-id="aef2d-163">当你想要测试两个对象不指向同一个实例，`IsNot`运算符可避免通过编程方式笨拙的组合`Not`和`Is`。</span><span class="sxs-lookup"><span data-stu-id="aef2d-163">When you want to test for two objects not pointing to the same instance, the `IsNot` operator lets you avoid a grammatically clumsy combination of `Not` and `Is`.</span></span> <span data-ttu-id="aef2d-164">下面的示例阐释了这一点。</span><span class="sxs-lookup"><span data-stu-id="aef2d-164">The following example illustrates this.</span></span>  
  
 [!code-vb[VbVbalrOperators#67](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#67)]  
  
 <span data-ttu-id="aef2d-165">在前面的示例中，`If a IsNot b`等效于`If Not a Is b`。</span><span class="sxs-lookup"><span data-stu-id="aef2d-165">In the preceding example, `If a IsNot b` is equivalent to `If Not a Is b`.</span></span>  
  
### <a name="comparing-object-type"></a><span data-ttu-id="aef2d-166">比较对象类型</span><span class="sxs-lookup"><span data-stu-id="aef2d-166">Comparing Object Type</span></span>  
 <span data-ttu-id="aef2d-167">你可以测试是否与特定类型的对象是`TypeOf`...`Is`表达式。</span><span class="sxs-lookup"><span data-stu-id="aef2d-167">You can test whether an object is of a particular type with the `TypeOf`...`Is` expression.</span></span> <span data-ttu-id="aef2d-168">语法如下所示：</span><span class="sxs-lookup"><span data-stu-id="aef2d-168">The syntax is as follows:</span></span>  
  
 `TypeOf <objectexpression> Is <typename>`  
  
 <span data-ttu-id="aef2d-169">当`typename`指定接口类型，则`TypeOf`...`Is`表达式返回`True`如果对象实现的接口类型。</span><span class="sxs-lookup"><span data-stu-id="aef2d-169">When `typename` specifies an interface type, then the `TypeOf`...`Is` expression returns `True` if the object implements the interface type.</span></span> <span data-ttu-id="aef2d-170">当`typename`是类类型，则表达式将返回`True`如果对象是指定类或派生自指定类的类的实例。</span><span class="sxs-lookup"><span data-stu-id="aef2d-170">When `typename` is a class type, then the expression returns `True` if the object is an instance of the specified class or of a class that derives from the specified class.</span></span> <span data-ttu-id="aef2d-171">下面的示例阐释了这一点。</span><span class="sxs-lookup"><span data-stu-id="aef2d-171">The following example illustrates this.</span></span>  
  
 [!code-vb[VbVbalrOperators#68](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#68)]  
  
 <span data-ttu-id="aef2d-172">在前面的示例中，`TypeOf x Is Control`表达式的计算结果`True`因为的类型`x`是`Button`，后者又继承`Control`。</span><span class="sxs-lookup"><span data-stu-id="aef2d-172">In the preceding example, the `TypeOf x Is Control` expression evaluates to `True` because the type of `x` is `Button`, which inherits from `Control`.</span></span>  
  
 <span data-ttu-id="aef2d-173">有关详细信息，请参阅[TypeOf 运算符](../../../../visual-basic/language-reference/operators/typeof-operator.md)。</span><span class="sxs-lookup"><span data-stu-id="aef2d-173">For more information, see [TypeOf Operator](../../../../visual-basic/language-reference/operators/typeof-operator.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="aef2d-174">请参阅</span><span class="sxs-lookup"><span data-stu-id="aef2d-174">See also</span></span>

- [<span data-ttu-id="aef2d-175">值的比较</span><span class="sxs-lookup"><span data-stu-id="aef2d-175">Value Comparisons</span></span>](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/value-comparisons.md)
- [<span data-ttu-id="aef2d-176">比较运算符</span><span class="sxs-lookup"><span data-stu-id="aef2d-176">Comparison Operators</span></span>](../../../../visual-basic/language-reference/operators/comparison-operators.md)
- [<span data-ttu-id="aef2d-177">运算符</span><span class="sxs-lookup"><span data-stu-id="aef2d-177">Operators</span></span>](../../../../visual-basic/language-reference/operators/index.md)
- [<span data-ttu-id="aef2d-178">在 Visual Basic 中的算术运算符</span><span class="sxs-lookup"><span data-stu-id="aef2d-178">Arithmetic Operators in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/arithmetic-operators.md)
- [<span data-ttu-id="aef2d-179">在 Visual Basic 中的串联运算符</span><span class="sxs-lookup"><span data-stu-id="aef2d-179">Concatenation Operators in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/concatenation-operators.md)
- [<span data-ttu-id="aef2d-180">在 Visual Basic 中的逻辑和位运算符</span><span class="sxs-lookup"><span data-stu-id="aef2d-180">Logical and Bitwise Operators in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/logical-and-bitwise-operators.md)
