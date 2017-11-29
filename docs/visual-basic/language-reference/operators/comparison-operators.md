---
title: "比较运算符 (Visual Basic)"
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
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
- comparison operators [Visual Basic], Visual Basicl
ms.assetid: d6cb12a8-e52e-46a7-8aaf-f804d634a825
caps.latest.revision: "20"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: aa450f7978f46196663c7534b31597b04d80482a
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="comparison-operators-visual-basic"></a><span data-ttu-id="d5586-102">比较运算符 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="d5586-102">Comparison Operators (Visual Basic)</span></span>
<span data-ttu-id="d5586-103">以下是定义在 Visual Basic 中的比较运算符。</span><span class="sxs-lookup"><span data-stu-id="d5586-103">The following are the comparison operators defined in Visual Basic.</span></span>  
  
 <span data-ttu-id="d5586-104">`<`运算符</span><span class="sxs-lookup"><span data-stu-id="d5586-104">`<` operator</span></span>  
  
 <span data-ttu-id="d5586-105">`<=`运算符</span><span class="sxs-lookup"><span data-stu-id="d5586-105">`<=` operator</span></span>  
  
 <span data-ttu-id="d5586-106">`>`运算符</span><span class="sxs-lookup"><span data-stu-id="d5586-106">`>` operator</span></span>  
  
 <span data-ttu-id="d5586-107">`>=`运算符</span><span class="sxs-lookup"><span data-stu-id="d5586-107">`>=` operator</span></span>  
  
 <span data-ttu-id="d5586-108">`=`运算符</span><span class="sxs-lookup"><span data-stu-id="d5586-108">`=` operator</span></span>  
  
 <span data-ttu-id="d5586-109">`<>`运算符</span><span class="sxs-lookup"><span data-stu-id="d5586-109">`<>` operator</span></span>  
  
 [<span data-ttu-id="d5586-110">Is 运算符</span><span class="sxs-lookup"><span data-stu-id="d5586-110">Is Operator</span></span>](../../../visual-basic/language-reference/operators/is-operator.md)  
  
 [<span data-ttu-id="d5586-111">IsNot 运算符</span><span class="sxs-lookup"><span data-stu-id="d5586-111">IsNot Operator</span></span>](../../../visual-basic/language-reference/operators/isnot-operator.md)  
  
 [<span data-ttu-id="d5586-112">Like 运算符</span><span class="sxs-lookup"><span data-stu-id="d5586-112">Like Operator</span></span>](../../../visual-basic/language-reference/operators/like-operator.md)  
  
 <span data-ttu-id="d5586-113">这些运算符比较两个表达式以确定它们相等，以及如果不是，有何不同。</span><span class="sxs-lookup"><span data-stu-id="d5586-113">These operators compare two expressions to determine whether or not they are equal, and if not, how they differ.</span></span> <span data-ttu-id="d5586-114">`Is``IsNot`，和`Like`详细地讨论了在单独的帮助页上。</span><span class="sxs-lookup"><span data-stu-id="d5586-114">`Is`, `IsNot`, and `Like` are discussed in detail on separate Help pages.</span></span> <span data-ttu-id="d5586-115">关系的比较运算符在此页上详细讨论。</span><span class="sxs-lookup"><span data-stu-id="d5586-115">The relational comparison operators are discussed in detail on this page.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d5586-116">语法</span><span class="sxs-lookup"><span data-stu-id="d5586-116">Syntax</span></span>  
  
```  
      result = expression1 comparisonoperator expression2  
result = object1 [Is | IsNot] object2  
result = string Like pattern  
```  
  
## <a name="parts"></a><span data-ttu-id="d5586-117">部件</span><span class="sxs-lookup"><span data-stu-id="d5586-117">Parts</span></span>  
 `result`  
 <span data-ttu-id="d5586-118">必需。</span><span class="sxs-lookup"><span data-stu-id="d5586-118">Required.</span></span> <span data-ttu-id="d5586-119">A`Boolean`表示结果的比较的值。</span><span class="sxs-lookup"><span data-stu-id="d5586-119">A `Boolean` value representing the result of the comparison.</span></span>  
  
 `expression`  
 <span data-ttu-id="d5586-120">必需。</span><span class="sxs-lookup"><span data-stu-id="d5586-120">Required.</span></span> <span data-ttu-id="d5586-121">任何表达式。</span><span class="sxs-lookup"><span data-stu-id="d5586-121">Any expression.</span></span>  
  
 `comparisonoperator`  
 <span data-ttu-id="d5586-122">必需。</span><span class="sxs-lookup"><span data-stu-id="d5586-122">Required.</span></span> <span data-ttu-id="d5586-123">任何关系的比较运算符。</span><span class="sxs-lookup"><span data-stu-id="d5586-123">Any relational comparison operator.</span></span>  
  
 <span data-ttu-id="d5586-124">`object1`, `object2`</span><span class="sxs-lookup"><span data-stu-id="d5586-124">`object1`, `object2`</span></span>  
 <span data-ttu-id="d5586-125">必需。</span><span class="sxs-lookup"><span data-stu-id="d5586-125">Required.</span></span> <span data-ttu-id="d5586-126">对象名称的任何引用。</span><span class="sxs-lookup"><span data-stu-id="d5586-126">Any reference object names.</span></span>  
  
 `string`  
 <span data-ttu-id="d5586-127">必需。</span><span class="sxs-lookup"><span data-stu-id="d5586-127">Required.</span></span> <span data-ttu-id="d5586-128">任何 `String` 表达式。</span><span class="sxs-lookup"><span data-stu-id="d5586-128">Any `String` expression.</span></span>  
  
 `pattern`  
 <span data-ttu-id="d5586-129">必需。</span><span class="sxs-lookup"><span data-stu-id="d5586-129">Required.</span></span> <span data-ttu-id="d5586-130">任何`String`表达式或范围的字符。</span><span class="sxs-lookup"><span data-stu-id="d5586-130">Any `String` expression or range of characters.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="d5586-131">备注</span><span class="sxs-lookup"><span data-stu-id="d5586-131">Remarks</span></span>  
 <span data-ttu-id="d5586-132">下表包含关系的比较运算符和确定的条件的列表是否`result`是`True`或`False`。</span><span class="sxs-lookup"><span data-stu-id="d5586-132">The following table contains a list of the relational comparison operators and the conditions that determine whether `result` is `True` or `False`.</span></span>  
  
|<span data-ttu-id="d5586-133">运算符</span><span class="sxs-lookup"><span data-stu-id="d5586-133">Operator</span></span>|<span data-ttu-id="d5586-134">`True`如果</span><span class="sxs-lookup"><span data-stu-id="d5586-134">`True` if</span></span>|<span data-ttu-id="d5586-135">`False`如果</span><span class="sxs-lookup"><span data-stu-id="d5586-135">`False` if</span></span>|  
|--------------|---------------|----------------|  
|<span data-ttu-id="d5586-136">`<`（小于）</span><span class="sxs-lookup"><span data-stu-id="d5586-136">`<` (Less than)</span></span>|`expression1` < `expression2`|`expression1` >= `expression2`|  
|<span data-ttu-id="d5586-137">`<=`（小于或等于）</span><span class="sxs-lookup"><span data-stu-id="d5586-137">`<=` (Less than or equal to)</span></span>|`expression1` <= `expression2`|`expression1` > `expression2`|  
|<span data-ttu-id="d5586-138">`>`（大于）</span><span class="sxs-lookup"><span data-stu-id="d5586-138">`>` (Greater than)</span></span>|`expression1` > `expression2`|`expression1` <= `expression2`|  
|<span data-ttu-id="d5586-139">`>=`（大于或等于）</span><span class="sxs-lookup"><span data-stu-id="d5586-139">`>=` (Greater than or equal to)</span></span>|`expression1` >= `expression2`|`expression1` < `expression2`|  
|<span data-ttu-id="d5586-140">`=`（等于）</span><span class="sxs-lookup"><span data-stu-id="d5586-140">`=` (Equal to)</span></span>|`expression1` = `expression2`|`expression1` <> `expression2`|  
|<span data-ttu-id="d5586-141">`<>`（不等于）</span><span class="sxs-lookup"><span data-stu-id="d5586-141">`<>` (Not equal to)</span></span>|`expression1` <> `expression2`|`expression1` = `expression2`|  
  
> [!NOTE]
>  <span data-ttu-id="d5586-142">[= 运算符](../../../visual-basic/language-reference/operators/assignment-operator.md)还用作赋值运算符。</span><span class="sxs-lookup"><span data-stu-id="d5586-142">The [= Operator](../../../visual-basic/language-reference/operators/assignment-operator.md) is also used as an assignment operator.</span></span>  
  
 <span data-ttu-id="d5586-143">`Is`运算符，`IsNot`运算符，与`Like`运算符具有特定的比较功能不同于前面的表中的运算符。</span><span class="sxs-lookup"><span data-stu-id="d5586-143">The `Is` operator, the `IsNot` operator, and the `Like` operator have specific comparison functionalities that differ from the operators in the preceding table.</span></span>  
  
## <a name="comparing-numbers"></a><span data-ttu-id="d5586-144">将数字进行比较</span><span class="sxs-lookup"><span data-stu-id="d5586-144">Comparing Numbers</span></span>  
 <span data-ttu-id="d5586-145">类型的类型的表达式的比较时`Single`类型之一`Double`、`Single`表达式转换为`Double`。</span><span class="sxs-lookup"><span data-stu-id="d5586-145">When you compare an expression of type `Single` to one of type `Double`, the `Single` expression is converted to `Double`.</span></span> <span data-ttu-id="d5586-146">此行为是相反的行为在 Visual Basic 6 中找到。</span><span class="sxs-lookup"><span data-stu-id="d5586-146">This behavior is opposite to the behavior found in Visual Basic 6.</span></span>  
  
 <span data-ttu-id="d5586-147">同样，当比较类型的表达式`Decimal`到类型的表达式`Single`或`Double`、`Decimal`表达式转换为`Single`或`Double`。</span><span class="sxs-lookup"><span data-stu-id="d5586-147">Similarly, when you compare an expression of type `Decimal` to an expression of type `Single` or `Double`, the `Decimal` expression is converted to `Single` or `Double`.</span></span> <span data-ttu-id="d5586-148">有关`Decimal`表达式，任何小数部分的值小于 1E-28 可能会丢失。</span><span class="sxs-lookup"><span data-stu-id="d5586-148">For `Decimal` expressions, any fractional value less than 1E-28 might be lost.</span></span> <span data-ttu-id="d5586-149">此类小数部分值丢失可能导致两个值的比较结果相等时它们就不是。</span><span class="sxs-lookup"><span data-stu-id="d5586-149">Such fractional value loss may cause two values to compare as equal when they are not.</span></span> <span data-ttu-id="d5586-150">为此，您需要采取措施时使用相等 (`=`) 要比较两个浮点变量。</span><span class="sxs-lookup"><span data-stu-id="d5586-150">For this reason, you should take care when using equality (`=`) to compare two floating-point variables.</span></span> <span data-ttu-id="d5586-151">它会更加安全，来测试两个数字之间的差异的绝对值的数值是否早于一个小的可接受容差。</span><span class="sxs-lookup"><span data-stu-id="d5586-151">It is safer to test whether the absolute value of the difference between the two numbers is less than a small acceptable tolerance.</span></span>  
  
### <a name="floating-point-imprecision"></a><span data-ttu-id="d5586-152">浮点不精确性</span><span class="sxs-lookup"><span data-stu-id="d5586-152">Floating-point Imprecision</span></span>  
 <span data-ttu-id="d5586-153">当使用浮点数时，请注意在内存中不始终具有精确的表示形式。</span><span class="sxs-lookup"><span data-stu-id="d5586-153">When you work with floating-point numbers, keep in mind that they do not always have a precise representation in memory.</span></span> <span data-ttu-id="d5586-154">这可能导致意外的结果从某些操作，如值比较和[Mod 运算符](../../../visual-basic/language-reference/operators/mod-operator.md)。</span><span class="sxs-lookup"><span data-stu-id="d5586-154">This could lead to unexpected results from certain operations, such as value comparison and the [Mod Operator](../../../visual-basic/language-reference/operators/mod-operator.md).</span></span> <span data-ttu-id="d5586-155">有关详细信息，请参阅[故障排除数据类型](../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md)。</span><span class="sxs-lookup"><span data-stu-id="d5586-155">For more information, see [Troubleshooting Data Types](../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md).</span></span>  
  
## <a name="comparing-strings"></a><span data-ttu-id="d5586-156">比较字符串</span><span class="sxs-lookup"><span data-stu-id="d5586-156">Comparing Strings</span></span>  
 <span data-ttu-id="d5586-157">当比较字符串时，根据其按字母顺序排序顺序，具体取决于对的字符串表达式进行计算`Option Compare`设置。</span><span class="sxs-lookup"><span data-stu-id="d5586-157">When you compare strings, the string expressions are evaluated based on their alphabetical sort order, which depends on the `Option Compare` setting.</span></span>  
  
 <span data-ttu-id="d5586-158">`Option Compare Binary`基的字符串比较派生自字符的内部二进制表示的排序顺序。</span><span class="sxs-lookup"><span data-stu-id="d5586-158">`Option Compare Binary` bases string comparisons on a sort order derived from the internal binary representations of the characters.</span></span> <span data-ttu-id="d5586-159">排序顺序取决于代码页。</span><span class="sxs-lookup"><span data-stu-id="d5586-159">The sort order is determined by the code page.</span></span> <span data-ttu-id="d5586-160">下面的示例演示典型的二进制排序顺序。</span><span class="sxs-lookup"><span data-stu-id="d5586-160">The following example shows a typical binary sort order.</span></span>  
  
 `A < B < E < Z < a < b < e < z < À < Ê < Ø < à < ê < ø`  
  
 <span data-ttu-id="d5586-161">`Option Compare Text`基的字符串由应用程序的区域设置的不区分大小写、 文本排序顺序的比较。</span><span class="sxs-lookup"><span data-stu-id="d5586-161">`Option Compare Text` bases string comparisons on a case-insensitive, textual sort order determined by your application's locale.</span></span> <span data-ttu-id="d5586-162">当你将设置`Option Compare Text`和排序的字符在前面的示例，请应用以下文本排序顺序：</span><span class="sxs-lookup"><span data-stu-id="d5586-162">When you set `Option Compare Text` and sort the characters in the preceding example, the following text sort order applies:</span></span>  
  
 `(A=a) < (À= à) < (B=b) < (E=e) < (Ê= ê) < (Ø = ø) < (Z=z)`  
  
### <a name="locale-dependence"></a><span data-ttu-id="d5586-163">区域设置依赖项</span><span class="sxs-lookup"><span data-stu-id="d5586-163">Locale Dependence</span></span>  
 <span data-ttu-id="d5586-164">当你将设置`Option Compare Text`，字符串比较的结果的可能取决于运行该应用程序的区域设置。</span><span class="sxs-lookup"><span data-stu-id="d5586-164">When you set `Option Compare Text`, the result of a string comparison can depend on the locale in which the application is running.</span></span> <span data-ttu-id="d5586-165">两个字符可能比较结果相等，但不是在另一个区域设置中。</span><span class="sxs-lookup"><span data-stu-id="d5586-165">Two characters might compare as equal in one locale but not in another.</span></span> <span data-ttu-id="d5586-166">如果你使用的字符串比较来做出重要决定，例如是否接受尝试登录，你应与区域设置敏感度警报。</span><span class="sxs-lookup"><span data-stu-id="d5586-166">If you are using a string comparison to make important decisions, such as whether to accept an attempt to log on, you should be alert to locale sensitivity.</span></span> <span data-ttu-id="d5586-167">请考虑这两个设置`Option Compare Binary`或调用<xref:Microsoft.VisualBasic.Strings.StrComp%2A>，这将考虑在内的区域设置。</span><span class="sxs-lookup"><span data-stu-id="d5586-167">Consider either setting `Option Compare Binary` or calling the <xref:Microsoft.VisualBasic.Strings.StrComp%2A>, which takes the locale into account.</span></span>  
  
## <a name="typeless-programming-with-relational-comparison-operators"></a><span data-ttu-id="d5586-168">使用关系比较运算符的无类型编程</span><span class="sxs-lookup"><span data-stu-id="d5586-168">Typeless Programming with Relational Comparison Operators</span></span>  
 <span data-ttu-id="d5586-169">使用关系比较运算符和`Object`表达式不允许在`Option Strict On`。</span><span class="sxs-lookup"><span data-stu-id="d5586-169">The use of relational comparison operators with `Object` expressions is not allowed under `Option Strict On`.</span></span> <span data-ttu-id="d5586-170">当`Option Strict`是`Off`，并且`expression1`或`expression2`是`Object`表达式中，运行时类型确定如何对它们进行比较。</span><span class="sxs-lookup"><span data-stu-id="d5586-170">When `Option Strict` is `Off`, and either `expression1` or `expression2` is an `Object` expression, the run-time types determine how they are compared.</span></span> <span data-ttu-id="d5586-171">下表显示如何比较表达式和比较，具体取决于操作数的运行时类型的结果。</span><span class="sxs-lookup"><span data-stu-id="d5586-171">The following table shows how the expressions are compared and the result from the comparison, depending on the runtime type of the operands.</span></span>  
  
|<span data-ttu-id="d5586-172">如果操作数都是</span><span class="sxs-lookup"><span data-stu-id="d5586-172">If operands are</span></span>|<span data-ttu-id="d5586-173">比较是</span><span class="sxs-lookup"><span data-stu-id="d5586-173">Comparison is</span></span>|  
|---------------------|-------------------|  
|<span data-ttu-id="d5586-174">同时`String`</span><span class="sxs-lookup"><span data-stu-id="d5586-174">Both `String`</span></span>|<span data-ttu-id="d5586-175">排序基于字符串排序特征进行比较。</span><span class="sxs-lookup"><span data-stu-id="d5586-175">Sort comparison based on string sorting characteristics.</span></span>|  
|<span data-ttu-id="d5586-176">这两个数字</span><span class="sxs-lookup"><span data-stu-id="d5586-176">Both numeric</span></span>|<span data-ttu-id="d5586-177">对象转换为`Double`，数值比较。</span><span class="sxs-lookup"><span data-stu-id="d5586-177">Objects converted to `Double`, numeric comparison.</span></span>|  
|<span data-ttu-id="d5586-178">一个数值而另一个`String`</span><span class="sxs-lookup"><span data-stu-id="d5586-178">One numeric and one `String`</span></span>|<span data-ttu-id="d5586-179">`String`转换为`Double`和执行数值比较。</span><span class="sxs-lookup"><span data-stu-id="d5586-179">The `String` is converted to a `Double` and numeric comparison is performed.</span></span> <span data-ttu-id="d5586-180">如果`String`不能转换为`Double`、<xref:System.InvalidCastException>引发。</span><span class="sxs-lookup"><span data-stu-id="d5586-180">If the `String` cannot be converted to `Double`, an <xref:System.InvalidCastException> is thrown.</span></span>|  
|<span data-ttu-id="d5586-181">一种或两是以外的其他引用类型`String`</span><span class="sxs-lookup"><span data-stu-id="d5586-181">Either or both are reference types other than `String`</span></span>|<span data-ttu-id="d5586-182">引发 <xref:System.InvalidCastException>。</span><span class="sxs-lookup"><span data-stu-id="d5586-182">An <xref:System.InvalidCastException> is thrown.</span></span>|  
  
 <span data-ttu-id="d5586-183">数值比较将`Nothing`为 0。</span><span class="sxs-lookup"><span data-stu-id="d5586-183">Numeric comparisons treat `Nothing` as 0.</span></span> <span data-ttu-id="d5586-184">字符串比较将`Nothing`作为`""`（空字符串）。</span><span class="sxs-lookup"><span data-stu-id="d5586-184">String comparisons treat `Nothing` as `""` (an empty string).</span></span>  
  
## <a name="overloading"></a><span data-ttu-id="d5586-185">重载</span><span class="sxs-lookup"><span data-stu-id="d5586-185">Overloading</span></span>  
 <span data-ttu-id="d5586-186">关系的比较运算符 (`<`。</span><span class="sxs-lookup"><span data-stu-id="d5586-186">The relational comparison operators (`<`.</span></span> <span data-ttu-id="d5586-187">`<=``>`， `>=`， `=`， `<>`) 可以是*重载*，这意味着，一个类或结构可以重新定义它们的行为时，操作数的类或结构的类型。</span><span class="sxs-lookup"><span data-stu-id="d5586-187">`<=`, `>`, `>=`, `=`, `<>`) can be *overloaded*, which means that a class or structure can redefine their behavior when an operand has the type of that class or structure.</span></span> <span data-ttu-id="d5586-188">如果你的代码使用以上任意运算符对这样的类或结构，请确保你了解重新定义的行为。</span><span class="sxs-lookup"><span data-stu-id="d5586-188">If your code uses any of these operators on such a class or structure, be sure you understand the redefined behavior.</span></span> <span data-ttu-id="d5586-189">有关详细信息，请参阅[运算符过程](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md)。</span><span class="sxs-lookup"><span data-stu-id="d5586-189">For more information, see [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span></span>  
  
 <span data-ttu-id="d5586-190">请注意， [= 运算符](../../../visual-basic/language-reference/operators/assignment-operator.md)仅为关系的比较运算符，而不是赋值运算符可以重载。</span><span class="sxs-lookup"><span data-stu-id="d5586-190">Notice that the [= Operator](../../../visual-basic/language-reference/operators/assignment-operator.md) can be overloaded only as a relational comparison operator, not as an assignment operator.</span></span>  
  
## <a name="example"></a><span data-ttu-id="d5586-191">示例</span><span class="sxs-lookup"><span data-stu-id="d5586-191">Example</span></span>  
 <span data-ttu-id="d5586-192">下面的示例演示关系的比较运算符，用于比较表达式的各种的用法。</span><span class="sxs-lookup"><span data-stu-id="d5586-192">The following example shows various uses of relational comparison operators, which you use to compare expressions.</span></span> <span data-ttu-id="d5586-193">关系的比较运算符返回`Boolean`表示无论是否规定的表达式计算结果为结果`True`。</span><span class="sxs-lookup"><span data-stu-id="d5586-193">Relational comparison operators return a `Boolean` result that represents whether or not the stated expression evaluates to `True`.</span></span> <span data-ttu-id="d5586-194">当你将`>`和`<`为字符串的运算符，比较使用进行的字符串的正常按字母顺序排序顺序。</span><span class="sxs-lookup"><span data-stu-id="d5586-194">When you apply the `>` and `<` operators to strings, the comparison is made using the normal alphabetical sorting order of the strings.</span></span> <span data-ttu-id="d5586-195">可以按此顺序依赖于区域设置。</span><span class="sxs-lookup"><span data-stu-id="d5586-195">This order can be dependent on your locale setting.</span></span> <span data-ttu-id="d5586-196">是否排序是区分大小写或不依赖于[Option Compare](../../../visual-basic/language-reference/statements/option-compare-statement.md)设置。</span><span class="sxs-lookup"><span data-stu-id="d5586-196">Whether the sort is case-sensitive or not depends on the [Option Compare](../../../visual-basic/language-reference/statements/option-compare-statement.md) setting.</span></span>  
  
 [!code-vb[VbVbalrOperators#1](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/comparison-operators_1.vb)]  
  
 <span data-ttu-id="d5586-197">在前面的示例中，返回的第一个比较`False`和其余的比较返回`True`。</span><span class="sxs-lookup"><span data-stu-id="d5586-197">In the preceding example, the first comparison returns `False` and the remaining comparisons return `True`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d5586-198">另请参阅</span><span class="sxs-lookup"><span data-stu-id="d5586-198">See Also</span></span>  
 <xref:System.InvalidCastException>  
 [<span data-ttu-id="d5586-199">= 运算符</span><span class="sxs-lookup"><span data-stu-id="d5586-199">= Operator</span></span>](../../../visual-basic/language-reference/operators/assignment-operator.md)  
 [<span data-ttu-id="d5586-200">Visual Basic 中的运算符优先级</span><span class="sxs-lookup"><span data-stu-id="d5586-200">Operator Precedence in Visual Basic</span></span>](../../../visual-basic/language-reference/operators/operator-precedence.md)  
 [<span data-ttu-id="d5586-201">按功能列出的运算符</span><span class="sxs-lookup"><span data-stu-id="d5586-201">Operators Listed by Functionality</span></span>](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)  
 [<span data-ttu-id="d5586-202">数据类型疑难解答</span><span class="sxs-lookup"><span data-stu-id="d5586-202">Troubleshooting Data Types</span></span>](../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md)  
 [<span data-ttu-id="d5586-203">在 Visual Basic 中的比较运算符</span><span class="sxs-lookup"><span data-stu-id="d5586-203">Comparison Operators in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/operators-and-expressions/comparison-operators.md)
