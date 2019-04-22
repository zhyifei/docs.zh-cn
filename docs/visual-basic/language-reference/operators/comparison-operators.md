---
title: 比较运算符 (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.<>
- vb.>=
- vb.<=
- vb.>
- vb.<
helpviewer_keywords:
- greater than or equal to operator [Visual Basic]
- '>= operator [Visual Basic]'
- = operator [Visual Basic]
- < operator [Visual Basic]
- less than operator [Visual Basic]
- relational operators [Visual Basic], syntax
- Like operator [Visual Basic]
- <> operator [Visual Basic]
- '> operator [Visual Basic]'
- equal operator [Visual Basic]
- less than or equal to operator [Visual Basic]
- symbols, operators
- greater than operator [Visual Basic]
- comparing values [Visual Basic]
- operators [Visual Basic], relational
- string comparison [Visual Basic]
- not equal to comparison operator [Visual Basic]
- <= operator [Visual Basic]
- operators [Visual Basic], comparison
- Is operator [Visual Basic]
- comparison operators [Visual Basic], Visual Basic
ms.assetid: d6cb12a8-e52e-46a7-8aaf-f804d634a825
ms.openlocfilehash: 9014cac5e2f3933b27411dfe5681fc16f4cdde30
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/18/2019
ms.locfileid: "58821031"
---
# <a name="comparison-operators-visual-basic"></a><span data-ttu-id="d7aad-102">比较运算符 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="d7aad-102">Comparison Operators (Visual Basic)</span></span>
<span data-ttu-id="d7aad-103">以下是定义在 Visual Basic 中的比较运算符。</span><span class="sxs-lookup"><span data-stu-id="d7aad-103">The following are the comparison operators defined in Visual Basic.</span></span>  
  
 <span data-ttu-id="d7aad-104">`<` 运算符</span><span class="sxs-lookup"><span data-stu-id="d7aad-104">`<` operator</span></span>  
  
 <span data-ttu-id="d7aad-105">`<=` 运算符</span><span class="sxs-lookup"><span data-stu-id="d7aad-105">`<=` operator</span></span>  
  
 <span data-ttu-id="d7aad-106">`>` 运算符</span><span class="sxs-lookup"><span data-stu-id="d7aad-106">`>` operator</span></span>  
  
 <span data-ttu-id="d7aad-107">`>=` 运算符</span><span class="sxs-lookup"><span data-stu-id="d7aad-107">`>=` operator</span></span>  
  
 <span data-ttu-id="d7aad-108">`=` 运算符</span><span class="sxs-lookup"><span data-stu-id="d7aad-108">`=` operator</span></span>  
  
 <span data-ttu-id="d7aad-109">`<>` 运算符</span><span class="sxs-lookup"><span data-stu-id="d7aad-109">`<>` operator</span></span>  
  
 [<span data-ttu-id="d7aad-110">Is 运算符</span><span class="sxs-lookup"><span data-stu-id="d7aad-110">Is Operator</span></span>](../../../visual-basic/language-reference/operators/is-operator.md)  
  
 [<span data-ttu-id="d7aad-111">IsNot 运算符</span><span class="sxs-lookup"><span data-stu-id="d7aad-111">IsNot Operator</span></span>](../../../visual-basic/language-reference/operators/isnot-operator.md)  
  
 [<span data-ttu-id="d7aad-112">Like 运算符</span><span class="sxs-lookup"><span data-stu-id="d7aad-112">Like Operator</span></span>](../../../visual-basic/language-reference/operators/like-operator.md)  
  
 <span data-ttu-id="d7aad-113">这些运算符比较两个表达式以确定它们相等，以及如果不是，它们之间的区别。</span><span class="sxs-lookup"><span data-stu-id="d7aad-113">These operators compare two expressions to determine whether or not they are equal, and if not, how they differ.</span></span> <span data-ttu-id="d7aad-114">`Is``IsNot`，和`Like`详细讨论了在单独的帮助页上。</span><span class="sxs-lookup"><span data-stu-id="d7aad-114">`Is`, `IsNot`, and `Like` are discussed in detail on separate Help pages.</span></span> <span data-ttu-id="d7aad-115">关系比较运算符在此页上详细讨论。</span><span class="sxs-lookup"><span data-stu-id="d7aad-115">The relational comparison operators are discussed in detail on this page.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d7aad-116">语法</span><span class="sxs-lookup"><span data-stu-id="d7aad-116">Syntax</span></span>  
  
```  
      result = expression1 comparisonoperator expression2  
result = object1 [Is | IsNot] object2  
result = string Like pattern  
```  
  
## <a name="parts"></a><span data-ttu-id="d7aad-117">部件</span><span class="sxs-lookup"><span data-stu-id="d7aad-117">Parts</span></span>  
 `result`  
 <span data-ttu-id="d7aad-118">必需。</span><span class="sxs-lookup"><span data-stu-id="d7aad-118">Required.</span></span> <span data-ttu-id="d7aad-119">一个`Boolean`值，该值表示比较结果。</span><span class="sxs-lookup"><span data-stu-id="d7aad-119">A `Boolean` value representing the result of the comparison.</span></span>  
  
 `expression`  
 <span data-ttu-id="d7aad-120">必需。</span><span class="sxs-lookup"><span data-stu-id="d7aad-120">Required.</span></span> <span data-ttu-id="d7aad-121">任何表达式。</span><span class="sxs-lookup"><span data-stu-id="d7aad-121">Any expression.</span></span>  
  
 `comparisonoperator`  
 <span data-ttu-id="d7aad-122">必需。</span><span class="sxs-lookup"><span data-stu-id="d7aad-122">Required.</span></span> <span data-ttu-id="d7aad-123">任何关系比较运算符。</span><span class="sxs-lookup"><span data-stu-id="d7aad-123">Any relational comparison operator.</span></span>  
  
 <span data-ttu-id="d7aad-124">`object1`， `object2`</span><span class="sxs-lookup"><span data-stu-id="d7aad-124">`object1`, `object2`</span></span>  
 <span data-ttu-id="d7aad-125">必需。</span><span class="sxs-lookup"><span data-stu-id="d7aad-125">Required.</span></span> <span data-ttu-id="d7aad-126">任何引用对象名称。</span><span class="sxs-lookup"><span data-stu-id="d7aad-126">Any reference object names.</span></span>  
  
 `string`  
 <span data-ttu-id="d7aad-127">必需。</span><span class="sxs-lookup"><span data-stu-id="d7aad-127">Required.</span></span> <span data-ttu-id="d7aad-128">任何 `String` 表达式。</span><span class="sxs-lookup"><span data-stu-id="d7aad-128">Any `String` expression.</span></span>  
  
 `pattern`  
 <span data-ttu-id="d7aad-129">必需。</span><span class="sxs-lookup"><span data-stu-id="d7aad-129">Required.</span></span> <span data-ttu-id="d7aad-130">任何`String`表达式或一系列字符。</span><span class="sxs-lookup"><span data-stu-id="d7aad-130">Any `String` expression or range of characters.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="d7aad-131">备注</span><span class="sxs-lookup"><span data-stu-id="d7aad-131">Remarks</span></span>  
 <span data-ttu-id="d7aad-132">下表包含一系列关系比较运算符和条件，来确定是否`result`是`True`或`False`。</span><span class="sxs-lookup"><span data-stu-id="d7aad-132">The following table contains a list of the relational comparison operators and the conditions that determine whether `result` is `True` or `False`.</span></span>  
  
|<span data-ttu-id="d7aad-133">运算符</span><span class="sxs-lookup"><span data-stu-id="d7aad-133">Operator</span></span>|<span data-ttu-id="d7aad-134">`True` 是否</span><span class="sxs-lookup"><span data-stu-id="d7aad-134">`True` if</span></span>|<span data-ttu-id="d7aad-135">`False` 是否</span><span class="sxs-lookup"><span data-stu-id="d7aad-135">`False` if</span></span>|  
|--------------|---------------|----------------|  
|<span data-ttu-id="d7aad-136">`<` （小于）</span><span class="sxs-lookup"><span data-stu-id="d7aad-136">`<` (Less than)</span></span>|`expression1` < `expression2`|`expression1` >= `expression2`|  
|<span data-ttu-id="d7aad-137">`<=` （小于或等于）</span><span class="sxs-lookup"><span data-stu-id="d7aad-137">`<=` (Less than or equal to)</span></span>|`expression1` <= `expression2`|`expression1` > `expression2`|  
|<span data-ttu-id="d7aad-138">`>` （大于）</span><span class="sxs-lookup"><span data-stu-id="d7aad-138">`>` (Greater than)</span></span>|`expression1` > `expression2`|`expression1` <= `expression2`|  
|<span data-ttu-id="d7aad-139">`>=` （大于或等于）</span><span class="sxs-lookup"><span data-stu-id="d7aad-139">`>=` (Greater than or equal to)</span></span>|`expression1` >= `expression2`|`expression1` < `expression2`|  
|<span data-ttu-id="d7aad-140">`=` （等于）</span><span class="sxs-lookup"><span data-stu-id="d7aad-140">`=` (Equal to)</span></span>|`expression1` = `expression2`|`expression1` <> `expression2`|  
|<span data-ttu-id="d7aad-141">`<>` （不等于）</span><span class="sxs-lookup"><span data-stu-id="d7aad-141">`<>` (Not equal to)</span></span>|`expression1` <> `expression2`|`expression1` = `expression2`|  
  
> [!NOTE]
>  <span data-ttu-id="d7aad-142">[= 运算符](../../../visual-basic/language-reference/operators/assignment-operator.md)还用作赋值运算符。</span><span class="sxs-lookup"><span data-stu-id="d7aad-142">The [= Operator](../../../visual-basic/language-reference/operators/assignment-operator.md) is also used as an assignment operator.</span></span>  
  
 <span data-ttu-id="d7aad-143">`Is`运算符`IsNot`运算符，和`Like`运算符具有特定的比较功能，不同于上表中的运算符。</span><span class="sxs-lookup"><span data-stu-id="d7aad-143">The `Is` operator, the `IsNot` operator, and the `Like` operator have specific comparison functionalities that differ from the operators in the preceding table.</span></span>  
  
## <a name="comparing-numbers"></a><span data-ttu-id="d7aad-144">将数字进行比较</span><span class="sxs-lookup"><span data-stu-id="d7aad-144">Comparing Numbers</span></span>  
 <span data-ttu-id="d7aad-145">当比较类型的表达式`Single`类型之一`Double`，则`Single`表达式转换为`Double`。</span><span class="sxs-lookup"><span data-stu-id="d7aad-145">When you compare an expression of type `Single` to one of type `Double`, the `Single` expression is converted to `Double`.</span></span> <span data-ttu-id="d7aad-146">此行为是与 Visual Basic 6 中所发现的行为相反。</span><span class="sxs-lookup"><span data-stu-id="d7aad-146">This behavior is opposite to the behavior found in Visual Basic 6.</span></span>  
  
 <span data-ttu-id="d7aad-147">同样，当比较类型的表达式`Decimal`类型的表达式`Single`或`Double`，则`Decimal`表达式转换为`Single`或`Double`。</span><span class="sxs-lookup"><span data-stu-id="d7aad-147">Similarly, when you compare an expression of type `Decimal` to an expression of type `Single` or `Double`, the `Decimal` expression is converted to `Single` or `Double`.</span></span> <span data-ttu-id="d7aad-148">有关`Decimal`表达式中，任何小数部分的值小于 1E 28 可能会丢失。</span><span class="sxs-lookup"><span data-stu-id="d7aad-148">For `Decimal` expressions, any fractional value less than 1E-28 might be lost.</span></span> <span data-ttu-id="d7aad-149">此类的小数部分值丢失可能导致两个值时它们不是比较结果为相等。</span><span class="sxs-lookup"><span data-stu-id="d7aad-149">Such fractional value loss may cause two values to compare as equal when they are not.</span></span> <span data-ttu-id="d7aad-150">出于此原因，请注意，当使用等式 (`=`) 比较两个浮点变量。</span><span class="sxs-lookup"><span data-stu-id="d7aad-150">For this reason, you should take care when using equality (`=`) to compare two floating-point variables.</span></span> <span data-ttu-id="d7aad-151">它是差异的更安全，若要测试是否两个数字之间的绝对值是差异的小于较小的可接受容差。</span><span class="sxs-lookup"><span data-stu-id="d7aad-151">It is safer to test whether the absolute value of the difference between the two numbers is less than a small acceptable tolerance.</span></span>  
  
### <a name="floating-point-imprecision"></a><span data-ttu-id="d7aad-152">浮点不精确性</span><span class="sxs-lookup"><span data-stu-id="d7aad-152">Floating-point Imprecision</span></span>  
 <span data-ttu-id="d7aad-153">当使用浮点数时，请注意在内存中不一定有精确的表示形式。</span><span class="sxs-lookup"><span data-stu-id="d7aad-153">When you work with floating-point numbers, keep in mind that they do not always have a precise representation in memory.</span></span> <span data-ttu-id="d7aad-154">这可能导致意外的结果从某些操作，如值比较， [Mod 运算符](../../../visual-basic/language-reference/operators/mod-operator.md)。</span><span class="sxs-lookup"><span data-stu-id="d7aad-154">This could lead to unexpected results from certain operations, such as value comparison and the [Mod Operator](../../../visual-basic/language-reference/operators/mod-operator.md).</span></span> <span data-ttu-id="d7aad-155">有关详细信息，请参阅[故障排除数据类型](../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md)。</span><span class="sxs-lookup"><span data-stu-id="d7aad-155">For more information, see [Troubleshooting Data Types](../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md).</span></span>  
  
## <a name="comparing-strings"></a><span data-ttu-id="d7aad-156">比较字符串</span><span class="sxs-lookup"><span data-stu-id="d7aad-156">Comparing Strings</span></span>  
 <span data-ttu-id="d7aad-157">当比较字符串时，基于它们按字母顺序排序的顺序，具体取决于计算这些字符串表达式`Option Compare`设置。</span><span class="sxs-lookup"><span data-stu-id="d7aad-157">When you compare strings, the string expressions are evaluated based on their alphabetical sort order, which depends on the `Option Compare` setting.</span></span>  
  
 <span data-ttu-id="d7aad-158">`Option Compare Binary` 基本的字符串比较派生自的内部二进制表示形式的字符的排序顺序。</span><span class="sxs-lookup"><span data-stu-id="d7aad-158">`Option Compare Binary` bases string comparisons on a sort order derived from the internal binary representations of the characters.</span></span> <span data-ttu-id="d7aad-159">排序顺序取决于代码页。</span><span class="sxs-lookup"><span data-stu-id="d7aad-159">The sort order is determined by the code page.</span></span> <span data-ttu-id="d7aad-160">下面的示例显示了典型的二进制排序顺序。</span><span class="sxs-lookup"><span data-stu-id="d7aad-160">The following example shows a typical binary sort order.</span></span>  
  
 `A < B < E < Z < a < b < e < z < À < Ê < Ø < à < ê < ø`  
  
 <span data-ttu-id="d7aad-161">`Option Compare Text` 基本的字符串由应用程序的区域设置的不区分大小写的文本排序顺序的比较。</span><span class="sxs-lookup"><span data-stu-id="d7aad-161">`Option Compare Text` bases string comparisons on a case-insensitive, textual sort order determined by your application's locale.</span></span> <span data-ttu-id="d7aad-162">当您将设置`Option Compare Text`和对在前面的示例字符进行排序，以下文本排序顺序应用：</span><span class="sxs-lookup"><span data-stu-id="d7aad-162">When you set `Option Compare Text` and sort the characters in the preceding example, the following text sort order applies:</span></span>  
  
 `(A=a) < (À= à) < (B=b) < (E=e) < (Ê= ê) < (Ø = ø) < (Z=z)`  
  
### <a name="locale-dependence"></a><span data-ttu-id="d7aad-163">区域设置相关性</span><span class="sxs-lookup"><span data-stu-id="d7aad-163">Locale Dependence</span></span>  
 <span data-ttu-id="d7aad-164">当您将设置`Option Compare Text`，字符串比较的结果可能取决于应用程序运行所在的区域设置。</span><span class="sxs-lookup"><span data-stu-id="d7aad-164">When you set `Option Compare Text`, the result of a string comparison can depend on the locale in which the application is running.</span></span> <span data-ttu-id="d7aad-165">两个字符可能会比较结果相等，但不是在另一个区域设置中。</span><span class="sxs-lookup"><span data-stu-id="d7aad-165">Two characters might compare as equal in one locale but not in another.</span></span> <span data-ttu-id="d7aad-166">如果使用的字符串比较来做出重要决策，例如是否接受尝试登录，你应该于区域设置敏感度的警报。</span><span class="sxs-lookup"><span data-stu-id="d7aad-166">If you are using a string comparison to make important decisions, such as whether to accept an attempt to log on, you should be alert to locale sensitivity.</span></span> <span data-ttu-id="d7aad-167">这两个设置，请考虑`Option Compare Binary`或调用<xref:Microsoft.VisualBasic.Strings.StrComp%2A>，这会考虑区域设置。</span><span class="sxs-lookup"><span data-stu-id="d7aad-167">Consider either setting `Option Compare Binary` or calling the <xref:Microsoft.VisualBasic.Strings.StrComp%2A>, which takes the locale into account.</span></span>  
  
## <a name="typeless-programming-with-relational-comparison-operators"></a><span data-ttu-id="d7aad-168">关系比较运算符使用无类型编程</span><span class="sxs-lookup"><span data-stu-id="d7aad-168">Typeless Programming with Relational Comparison Operators</span></span>  
 <span data-ttu-id="d7aad-169">使用具有关系比较运算符`Object`下不允许使用表达式`Option Strict On`。</span><span class="sxs-lookup"><span data-stu-id="d7aad-169">The use of relational comparison operators with `Object` expressions is not allowed under `Option Strict On`.</span></span> <span data-ttu-id="d7aad-170">当`Option Strict`是`Off`，并将`expression1`或`expression2`是`Object`表达式中，运行时类型确定如何比较。</span><span class="sxs-lookup"><span data-stu-id="d7aad-170">When `Option Strict` is `Off`, and either `expression1` or `expression2` is an `Object` expression, the run-time types determine how they are compared.</span></span> <span data-ttu-id="d7aad-171">下表显示了如何比较表达式和比较，具体取决于操作数的运行时类型的结果。</span><span class="sxs-lookup"><span data-stu-id="d7aad-171">The following table shows how the expressions are compared and the result from the comparison, depending on the runtime type of the operands.</span></span>  
  
|<span data-ttu-id="d7aad-172">如果操作数均为</span><span class="sxs-lookup"><span data-stu-id="d7aad-172">If operands are</span></span>|<span data-ttu-id="d7aad-173">比较</span><span class="sxs-lookup"><span data-stu-id="d7aad-173">Comparison is</span></span>|  
|---------------------|-------------------|  
|<span data-ttu-id="d7aad-174">两者 `String`</span><span class="sxs-lookup"><span data-stu-id="d7aad-174">Both `String`</span></span>|<span data-ttu-id="d7aad-175">排序基于字符串排序特征进行比较。</span><span class="sxs-lookup"><span data-stu-id="d7aad-175">Sort comparison based on string sorting characteristics.</span></span>|  
|<span data-ttu-id="d7aad-176">这两个数字</span><span class="sxs-lookup"><span data-stu-id="d7aad-176">Both numeric</span></span>|<span data-ttu-id="d7aad-177">对象转换为`Double`，数值比较。</span><span class="sxs-lookup"><span data-stu-id="d7aad-177">Objects converted to `Double`, numeric comparison.</span></span>|  
|<span data-ttu-id="d7aad-178">一个数值，另一个 `String`</span><span class="sxs-lookup"><span data-stu-id="d7aad-178">One numeric and one `String`</span></span>|<span data-ttu-id="d7aad-179">`String`转换为`Double`并执行数值比较。</span><span class="sxs-lookup"><span data-stu-id="d7aad-179">The `String` is converted to a `Double` and numeric comparison is performed.</span></span> <span data-ttu-id="d7aad-180">如果`String`不能转换为`Double`、<xref:System.InvalidCastException>引发。</span><span class="sxs-lookup"><span data-stu-id="d7aad-180">If the `String` cannot be converted to `Double`, an <xref:System.InvalidCastException> is thrown.</span></span>|  
|<span data-ttu-id="d7aad-181">或者两种方法是以外的其他引用类型 `String`</span><span class="sxs-lookup"><span data-stu-id="d7aad-181">Either or both are reference types other than `String`</span></span>|<span data-ttu-id="d7aad-182">引发 <xref:System.InvalidCastException>。</span><span class="sxs-lookup"><span data-stu-id="d7aad-182">An <xref:System.InvalidCastException> is thrown.</span></span>|  
  
 <span data-ttu-id="d7aad-183">数值比较将`Nothing`为 0。</span><span class="sxs-lookup"><span data-stu-id="d7aad-183">Numeric comparisons treat `Nothing` as 0.</span></span> <span data-ttu-id="d7aad-184">字符串比较将视为`Nothing`作为`""`（空字符串）。</span><span class="sxs-lookup"><span data-stu-id="d7aad-184">String comparisons treat `Nothing` as `""` (an empty string).</span></span>  
  
## <a name="overloading"></a><span data-ttu-id="d7aad-185">重载</span><span class="sxs-lookup"><span data-stu-id="d7aad-185">Overloading</span></span>  
 <span data-ttu-id="d7aad-186">关系比较运算符 (`<`。</span><span class="sxs-lookup"><span data-stu-id="d7aad-186">The relational comparison operators (`<`.</span></span> <span data-ttu-id="d7aad-187">`<=``>`， `>=`， `=`， `<>`) 可以是*重载*，这意味着，某个类或结构可以重新定义其行为时，操作数的类或结构的类型。</span><span class="sxs-lookup"><span data-stu-id="d7aad-187">`<=`, `>`, `>=`, `=`, `<>`) can be *overloaded*, which means that a class or structure can redefine their behavior when an operand has the type of that class or structure.</span></span> <span data-ttu-id="d7aad-188">如果你的代码使用任何这些运算符对这样的类或结构，请确保了解重新定义的行为。</span><span class="sxs-lookup"><span data-stu-id="d7aad-188">If your code uses any of these operators on such a class or structure, be sure you understand the redefined behavior.</span></span> <span data-ttu-id="d7aad-189">有关详细信息，请参阅 [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md)。</span><span class="sxs-lookup"><span data-stu-id="d7aad-189">For more information, see [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span></span>  
  
 <span data-ttu-id="d7aad-190">请注意， [= 运算符](../../../visual-basic/language-reference/operators/assignment-operator.md)仅作为关系比较运算符，而不是赋值运算符可以进行重载。</span><span class="sxs-lookup"><span data-stu-id="d7aad-190">Notice that the [= Operator](../../../visual-basic/language-reference/operators/assignment-operator.md) can be overloaded only as a relational comparison operator, not as an assignment operator.</span></span>  
  
## <a name="example"></a><span data-ttu-id="d7aad-191">示例</span><span class="sxs-lookup"><span data-stu-id="d7aad-191">Example</span></span>  
 <span data-ttu-id="d7aad-192">下面的示例显示了关系比较运算符，用来比较表达式的各种用法。</span><span class="sxs-lookup"><span data-stu-id="d7aad-192">The following example shows various uses of relational comparison operators, which you use to compare expressions.</span></span> <span data-ttu-id="d7aad-193">关系比较运算符将返回`Boolean`表示是否规定的表达式计算结果为结果`True`。</span><span class="sxs-lookup"><span data-stu-id="d7aad-193">Relational comparison operators return a `Boolean` result that represents whether or not the stated expression evaluates to `True`.</span></span> <span data-ttu-id="d7aad-194">当应用`>`和`<`运算符对字符串进行比较使用正常的字符串按字母顺序排序顺序。</span><span class="sxs-lookup"><span data-stu-id="d7aad-194">When you apply the `>` and `<` operators to strings, the comparison is made using the normal alphabetical sorting order of the strings.</span></span> <span data-ttu-id="d7aad-195">此顺序可以是依赖于区域设置。</span><span class="sxs-lookup"><span data-stu-id="d7aad-195">This order can be dependent on your locale setting.</span></span> <span data-ttu-id="d7aad-196">排序是否是区分大小写取决于[Option Compare](../../../visual-basic/language-reference/statements/option-compare-statement.md)设置。</span><span class="sxs-lookup"><span data-stu-id="d7aad-196">Whether the sort is case-sensitive or not depends on the [Option Compare](../../../visual-basic/language-reference/statements/option-compare-statement.md) setting.</span></span>  
  
 [!code-vb[VbVbalrOperators#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#1)]  
  
 <span data-ttu-id="d7aad-197">在上述示例中，第一次比较将返回`False`和其余的比较返回`True`。</span><span class="sxs-lookup"><span data-stu-id="d7aad-197">In the preceding example, the first comparison returns `False` and the remaining comparisons return `True`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d7aad-198">请参阅</span><span class="sxs-lookup"><span data-stu-id="d7aad-198">See also</span></span>

- <xref:System.InvalidCastException>
- [<span data-ttu-id="d7aad-199">= 运算符</span><span class="sxs-lookup"><span data-stu-id="d7aad-199">= Operator</span></span>](../../../visual-basic/language-reference/operators/assignment-operator.md)
- [<span data-ttu-id="d7aad-200">Visual Basic 中的运算符优先级</span><span class="sxs-lookup"><span data-stu-id="d7aad-200">Operator Precedence in Visual Basic</span></span>](../../../visual-basic/language-reference/operators/operator-precedence.md)
- [<span data-ttu-id="d7aad-201">按功能列出的运算符</span><span class="sxs-lookup"><span data-stu-id="d7aad-201">Operators Listed by Functionality</span></span>](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)
- [<span data-ttu-id="d7aad-202">数据类型疑难解答</span><span class="sxs-lookup"><span data-stu-id="d7aad-202">Troubleshooting Data Types</span></span>](../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md)
- [<span data-ttu-id="d7aad-203">在 Visual Basic 中的比较运算符</span><span class="sxs-lookup"><span data-stu-id="d7aad-203">Comparison Operators in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/operators-and-expressions/comparison-operators.md)
