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
ms.openlocfilehash: ddb07bdf5f67e281847082ba4487568e9ba3c9f5
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2019
ms.locfileid: "69962233"
---
# <a name="comparison-operators-visual-basic"></a><span data-ttu-id="a4473-102">比较运算符 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="a4473-102">Comparison Operators (Visual Basic)</span></span>
<span data-ttu-id="a4473-103">下面是 Visual Basic 中定义的比较运算符。</span><span class="sxs-lookup"><span data-stu-id="a4473-103">The following are the comparison operators defined in Visual Basic.</span></span>

 <span data-ttu-id="a4473-104">`<`操作员</span><span class="sxs-lookup"><span data-stu-id="a4473-104">`<` operator</span></span>

 <span data-ttu-id="a4473-105">`<=`操作员</span><span class="sxs-lookup"><span data-stu-id="a4473-105">`<=` operator</span></span>

 <span data-ttu-id="a4473-106">`>`操作员</span><span class="sxs-lookup"><span data-stu-id="a4473-106">`>` operator</span></span>

 <span data-ttu-id="a4473-107">`>=`操作员</span><span class="sxs-lookup"><span data-stu-id="a4473-107">`>=` operator</span></span>

 <span data-ttu-id="a4473-108">`=`操作员</span><span class="sxs-lookup"><span data-stu-id="a4473-108">`=` operator</span></span>

 <span data-ttu-id="a4473-109">`<>`操作员</span><span class="sxs-lookup"><span data-stu-id="a4473-109">`<>` operator</span></span>

 [<span data-ttu-id="a4473-110">Is 运算符</span><span class="sxs-lookup"><span data-stu-id="a4473-110">Is Operator</span></span>](../../../visual-basic/language-reference/operators/is-operator.md)

 [<span data-ttu-id="a4473-111">IsNot 运算符</span><span class="sxs-lookup"><span data-stu-id="a4473-111">IsNot Operator</span></span>](../../../visual-basic/language-reference/operators/isnot-operator.md)

 [<span data-ttu-id="a4473-112">Like 运算符</span><span class="sxs-lookup"><span data-stu-id="a4473-112">Like Operator</span></span>](../../../visual-basic/language-reference/operators/like-operator.md)

 <span data-ttu-id="a4473-113">这些运算符比较两个表达式以确定它们是否相等, 如果不相等, 则确定它们之间的差异。</span><span class="sxs-lookup"><span data-stu-id="a4473-113">These operators compare two expressions to determine whether or not they are equal, and if not, how they differ.</span></span> <span data-ttu-id="a4473-114">`Is`在`IsNot`单独的`Like`帮助页上详细讨论了、和。</span><span class="sxs-lookup"><span data-stu-id="a4473-114">`Is`, `IsNot`, and `Like` are discussed in detail on separate Help pages.</span></span> <span data-ttu-id="a4473-115">此页上详细讨论了关系比较运算符。</span><span class="sxs-lookup"><span data-stu-id="a4473-115">The relational comparison operators are discussed in detail on this page.</span></span>

## <a name="syntax"></a><span data-ttu-id="a4473-116">语法</span><span class="sxs-lookup"><span data-stu-id="a4473-116">Syntax</span></span>
  
```vb
result = expression1 comparisonoperator expression2  
result = object1 [Is | IsNot] object2  
result = string Like pattern  
```  
  
## <a name="parts"></a><span data-ttu-id="a4473-117">部件</span><span class="sxs-lookup"><span data-stu-id="a4473-117">Parts</span></span>
 `result`  
 <span data-ttu-id="a4473-118">必需。</span><span class="sxs-lookup"><span data-stu-id="a4473-118">Required.</span></span> <span data-ttu-id="a4473-119">一个`Boolean`值, 该值表示比较的结果。</span><span class="sxs-lookup"><span data-stu-id="a4473-119">A `Boolean` value representing the result of the comparison.</span></span>

 <span data-ttu-id="a4473-120">`expression1`， `expression2`</span><span class="sxs-lookup"><span data-stu-id="a4473-120">`expression1`, `expression2`</span></span>  
 <span data-ttu-id="a4473-121">必需。</span><span class="sxs-lookup"><span data-stu-id="a4473-121">Required.</span></span> <span data-ttu-id="a4473-122">任何表达式。</span><span class="sxs-lookup"><span data-stu-id="a4473-122">Any expression.</span></span>

 `comparisonoperator`  
 <span data-ttu-id="a4473-123">必需。</span><span class="sxs-lookup"><span data-stu-id="a4473-123">Required.</span></span> <span data-ttu-id="a4473-124">任何关系比较运算符。</span><span class="sxs-lookup"><span data-stu-id="a4473-124">Any relational comparison operator.</span></span>

 <span data-ttu-id="a4473-125">`object1`， `object2`</span><span class="sxs-lookup"><span data-stu-id="a4473-125">`object1`, `object2`</span></span>  
 <span data-ttu-id="a4473-126">必需。</span><span class="sxs-lookup"><span data-stu-id="a4473-126">Required.</span></span> <span data-ttu-id="a4473-127">任何引用对象的名称。</span><span class="sxs-lookup"><span data-stu-id="a4473-127">Any reference object names.</span></span>

 `string`  
 <span data-ttu-id="a4473-128">必需。</span><span class="sxs-lookup"><span data-stu-id="a4473-128">Required.</span></span> <span data-ttu-id="a4473-129">任何 `String` 表达式。</span><span class="sxs-lookup"><span data-stu-id="a4473-129">Any `String` expression.</span></span>

 `pattern`  
 <span data-ttu-id="a4473-130">必需。</span><span class="sxs-lookup"><span data-stu-id="a4473-130">Required.</span></span> <span data-ttu-id="a4473-131">任何`String`表达式或字符范围。</span><span class="sxs-lookup"><span data-stu-id="a4473-131">Any `String` expression or range of characters.</span></span>

## <a name="remarks"></a><span data-ttu-id="a4473-132">备注</span><span class="sxs-lookup"><span data-stu-id="a4473-132">Remarks</span></span>
 <span data-ttu-id="a4473-133">下表包含关系比较运算符和确定`result`是`True`还是`False`的条件的列表。</span><span class="sxs-lookup"><span data-stu-id="a4473-133">The following table contains a list of the relational comparison operators and the conditions that determine whether `result` is `True` or `False`.</span></span>

|<span data-ttu-id="a4473-134">运算符</span><span class="sxs-lookup"><span data-stu-id="a4473-134">Operator</span></span>|<span data-ttu-id="a4473-135">`True` 是否</span><span class="sxs-lookup"><span data-stu-id="a4473-135">`True` if</span></span>|<span data-ttu-id="a4473-136">`False` 是否</span><span class="sxs-lookup"><span data-stu-id="a4473-136">`False` if</span></span>|
|--------------|---------------|----------------|
|<span data-ttu-id="a4473-137">`<`(小于)</span><span class="sxs-lookup"><span data-stu-id="a4473-137">`<` (Less than)</span></span>|`expression1` < `expression2`|`expression1` >= `expression2`|
|<span data-ttu-id="a4473-138">`<=`(小于或等于)</span><span class="sxs-lookup"><span data-stu-id="a4473-138">`<=` (Less than or equal to)</span></span>|`expression1` <= `expression2`|`expression1` > `expression2`|
|<span data-ttu-id="a4473-139">`>`(大于)</span><span class="sxs-lookup"><span data-stu-id="a4473-139">`>` (Greater than)</span></span>|`expression1` > `expression2`|`expression1` <= `expression2`|
|<span data-ttu-id="a4473-140">`>=`(大于或等于)</span><span class="sxs-lookup"><span data-stu-id="a4473-140">`>=` (Greater than or equal to)</span></span>|`expression1` >= `expression2`|`expression1` < `expression2`|
|<span data-ttu-id="a4473-141">`=`(等于)</span><span class="sxs-lookup"><span data-stu-id="a4473-141">`=` (Equal to)</span></span>|`expression1` = `expression2`|`expression1` <> `expression2`|
|<span data-ttu-id="a4473-142">`<>`(不等于)</span><span class="sxs-lookup"><span data-stu-id="a4473-142">`<>` (Not equal to)</span></span>|`expression1` <> `expression2`|`expression1` = `expression2`|

> [!NOTE]
> <span data-ttu-id="a4473-143">[= 运算符](../../../visual-basic/language-reference/operators/assignment-operator.md)也用作赋值运算符。</span><span class="sxs-lookup"><span data-stu-id="a4473-143">The [= Operator](../../../visual-basic/language-reference/operators/assignment-operator.md) is also used as an assignment operator.</span></span>

 <span data-ttu-id="a4473-144">运算符、运算符和`Like`运算符具有特定的比较功能, 这些功能不同于上表中的运算符。 `IsNot` `Is`</span><span class="sxs-lookup"><span data-stu-id="a4473-144">The `Is` operator, the `IsNot` operator, and the `Like` operator have specific comparison functionalities that differ from the operators in the preceding table.</span></span>

## <a name="comparing-numbers"></a><span data-ttu-id="a4473-145">比较数字</span><span class="sxs-lookup"><span data-stu-id="a4473-145">Comparing Numbers</span></span>
 <span data-ttu-id="a4473-146">将类型`Single`的表达式与类型`Double`的表达式进行比较时, `Single`表达式将转换为`Double`。</span><span class="sxs-lookup"><span data-stu-id="a4473-146">When you compare an expression of type `Single` to one of type `Double`, the `Single` expression is converted to `Double`.</span></span> <span data-ttu-id="a4473-147">此行为与 Visual Basic 6 中的行为相反。</span><span class="sxs-lookup"><span data-stu-id="a4473-147">This behavior is opposite to the behavior found in Visual Basic 6.</span></span>

 <span data-ttu-id="a4473-148">`Decimal`同样, 将类型的表达式与或`Double`类型`Single`的表达式进行比较时, `Decimal`表达式将转换为`Single`或`Double`。</span><span class="sxs-lookup"><span data-stu-id="a4473-148">Similarly, when you compare an expression of type `Decimal` to an expression of type `Single` or `Double`, the `Decimal` expression is converted to `Single` or `Double`.</span></span> <span data-ttu-id="a4473-149">对于`Decimal`表达式, 小于 1e-28 的任何小数值都可能会丢失。</span><span class="sxs-lookup"><span data-stu-id="a4473-149">For `Decimal` expressions, any fractional value less than 1E-28 might be lost.</span></span> <span data-ttu-id="a4473-150">此类小数值损失可能导致两个值在不时比较为相等。</span><span class="sxs-lookup"><span data-stu-id="a4473-150">Such fractional value loss may cause two values to compare as equal when they are not.</span></span> <span data-ttu-id="a4473-151">出于此原因, 应小心使用相等 (`=`) 来比较两个浮点变量。</span><span class="sxs-lookup"><span data-stu-id="a4473-151">For this reason, you should take care when using equality (`=`) to compare two floating-point variables.</span></span> <span data-ttu-id="a4473-152">更安全的做法是测试两个数字之差的绝对值是否小于可接受的小容差。</span><span class="sxs-lookup"><span data-stu-id="a4473-152">It is safer to test whether the absolute value of the difference between the two numbers is less than a small acceptable tolerance.</span></span>

### <a name="floating-point-imprecision"></a><span data-ttu-id="a4473-153">浮点不精确性</span><span class="sxs-lookup"><span data-stu-id="a4473-153">Floating-point Imprecision</span></span>
 <span data-ttu-id="a4473-154">使用浮点数时, 请记住, 它们在内存中不一定有精确的表示形式。</span><span class="sxs-lookup"><span data-stu-id="a4473-154">When you work with floating-point numbers, keep in mind that they do not always have a precise representation in memory.</span></span> <span data-ttu-id="a4473-155">这可能会导致某些操作产生意外结果, 如值比较和[Mod 运算符](../../../visual-basic/language-reference/operators/mod-operator.md)。</span><span class="sxs-lookup"><span data-stu-id="a4473-155">This could lead to unexpected results from certain operations, such as value comparison and the [Mod Operator](../../../visual-basic/language-reference/operators/mod-operator.md).</span></span> <span data-ttu-id="a4473-156">有关详细信息, 请参阅[数据类型疑难解答](../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md)。</span><span class="sxs-lookup"><span data-stu-id="a4473-156">For more information, see [Troubleshooting Data Types](../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md).</span></span>

## <a name="comparing-strings"></a><span data-ttu-id="a4473-157">比较字符串</span><span class="sxs-lookup"><span data-stu-id="a4473-157">Comparing Strings</span></span>
 <span data-ttu-id="a4473-158">在比较字符串时, 将根据`Option Compare`设置的字母顺序对字符串表达式进行计算。</span><span class="sxs-lookup"><span data-stu-id="a4473-158">When you compare strings, the string expressions are evaluated based on their alphabetical sort order, which depends on the `Option Compare` setting.</span></span>

 <span data-ttu-id="a4473-159">`Option Compare Binary`对从字符的内部二进制表示形式派生的排序顺序进行字符串比较。</span><span class="sxs-lookup"><span data-stu-id="a4473-159">`Option Compare Binary` bases string comparisons on a sort order derived from the internal binary representations of the characters.</span></span> <span data-ttu-id="a4473-160">排序顺序由代码页确定。</span><span class="sxs-lookup"><span data-stu-id="a4473-160">The sort order is determined by the code page.</span></span> <span data-ttu-id="a4473-161">下面的示例显示了一个典型的二进制排序顺序。</span><span class="sxs-lookup"><span data-stu-id="a4473-161">The following example shows a typical binary sort order.</span></span>

 `A < B < E < Z < a < b < e < z < À < Ê < Ø < à < ê < ø`

 <span data-ttu-id="a4473-162">`Option Compare Text`基于不区分大小写的文本排序顺序对应用程序的区域设置进行字符串比较。</span><span class="sxs-lookup"><span data-stu-id="a4473-162">`Option Compare Text` bases string comparisons on a case-insensitive, textual sort order determined by your application's locale.</span></span> <span data-ttu-id="a4473-163">设置`Option Compare Text`和排序前面的示例中的字符时, 将应用以下文本排序顺序:</span><span class="sxs-lookup"><span data-stu-id="a4473-163">When you set `Option Compare Text` and sort the characters in the preceding example, the following text sort order applies:</span></span>

 `(A=a) < (À= à) < (B=b) < (E=e) < (Ê= ê) < (Ø = ø) < (Z=z)`

### <a name="locale-dependence"></a><span data-ttu-id="a4473-164">区域设置依赖关系</span><span class="sxs-lookup"><span data-stu-id="a4473-164">Locale Dependence</span></span>
 <span data-ttu-id="a4473-165">设置`Option Compare Text`时, 字符串比较的结果可能取决于应用程序运行所在的区域设置。</span><span class="sxs-lookup"><span data-stu-id="a4473-165">When you set `Option Compare Text`, the result of a string comparison can depend on the locale in which the application is running.</span></span> <span data-ttu-id="a4473-166">在一个区域设置中, 两个字符的比较结果可能不相同, 而在另一个区域中</span><span class="sxs-lookup"><span data-stu-id="a4473-166">Two characters might compare as equal in one locale but not in another.</span></span> <span data-ttu-id="a4473-167">如果使用字符串比较来做出重要决策 (例如是否接受登录尝试), 则应注意区域设置的敏感性。</span><span class="sxs-lookup"><span data-stu-id="a4473-167">If you are using a string comparison to make important decisions, such as whether to accept an attempt to log on, you should be alert to locale sensitivity.</span></span> <span data-ttu-id="a4473-168">请考虑设置`Option Compare Binary`或<xref:Microsoft.VisualBasic.Strings.StrComp%2A>调用, 这会使区域设置生效。</span><span class="sxs-lookup"><span data-stu-id="a4473-168">Consider either setting `Option Compare Binary` or calling the <xref:Microsoft.VisualBasic.Strings.StrComp%2A>, which takes the locale into account.</span></span>

## <a name="typeless-programming-with-relational-comparison-operators"></a><span data-ttu-id="a4473-169">用关系比较运算符进行无方式编程</span><span class="sxs-lookup"><span data-stu-id="a4473-169">Typeless Programming with Relational Comparison Operators</span></span>
 <span data-ttu-id="a4473-170">不允许在下`Object` `Option Strict On`使用带有表达式的关系比较运算符。</span><span class="sxs-lookup"><span data-stu-id="a4473-170">The use of relational comparison operators with `Object` expressions is not allowed under `Option Strict On`.</span></span> <span data-ttu-id="a4473-171">如果`Option Strict`为`Off`,并且`expression1` 或`expression2`是表达式,则运行时类型确定如何比较它们。`Object`</span><span class="sxs-lookup"><span data-stu-id="a4473-171">When `Option Strict` is `Off`, and either `expression1` or `expression2` is an `Object` expression, the run-time types determine how they are compared.</span></span> <span data-ttu-id="a4473-172">下表显示了如何比较表达式和比较的结果, 具体取决于操作数的运行时类型。</span><span class="sxs-lookup"><span data-stu-id="a4473-172">The following table shows how the expressions are compared and the result from the comparison, depending on the runtime type of the operands.</span></span>

|<span data-ttu-id="a4473-173">如果操作数为</span><span class="sxs-lookup"><span data-stu-id="a4473-173">If operands are</span></span>|<span data-ttu-id="a4473-174">比较是</span><span class="sxs-lookup"><span data-stu-id="a4473-174">Comparison is</span></span>|
|---------------------|-------------------|
|<span data-ttu-id="a4473-175">全部`String`</span><span class="sxs-lookup"><span data-stu-id="a4473-175">Both `String`</span></span>|<span data-ttu-id="a4473-176">基于字符串排序特性的排序比较。</span><span class="sxs-lookup"><span data-stu-id="a4473-176">Sort comparison based on string sorting characteristics.</span></span>|
|<span data-ttu-id="a4473-177">均为数值</span><span class="sxs-lookup"><span data-stu-id="a4473-177">Both numeric</span></span>|<span data-ttu-id="a4473-178">转换为`Double`数值比较的对象。</span><span class="sxs-lookup"><span data-stu-id="a4473-178">Objects converted to `Double`, numeric comparison.</span></span>|
|<span data-ttu-id="a4473-179">一个数字和一个`String`</span><span class="sxs-lookup"><span data-stu-id="a4473-179">One numeric and one `String`</span></span>|<span data-ttu-id="a4473-180">`String` 转换`Double`为并执行数值比较。</span><span class="sxs-lookup"><span data-stu-id="a4473-180">The `String` is converted to a `Double` and numeric comparison is performed.</span></span> <span data-ttu-id="a4473-181">如果无法转换为`Double`, <xref:System.InvalidCastException>则会引发。 `String`</span><span class="sxs-lookup"><span data-stu-id="a4473-181">If the `String` cannot be converted to `Double`, an <xref:System.InvalidCastException> is thrown.</span></span>|
|<span data-ttu-id="a4473-182">其中一个或两个都是引用类型, 而不是`String`</span><span class="sxs-lookup"><span data-stu-id="a4473-182">Either or both are reference types other than `String`</span></span>|<span data-ttu-id="a4473-183">引发 <xref:System.InvalidCastException>。</span><span class="sxs-lookup"><span data-stu-id="a4473-183">An <xref:System.InvalidCastException> is thrown.</span></span>|

 <span data-ttu-id="a4473-184">数值比较视为`Nothing` 0。</span><span class="sxs-lookup"><span data-stu-id="a4473-184">Numeric comparisons treat `Nothing` as 0.</span></span> <span data-ttu-id="a4473-185">字符串比较视为`Nothing` `""` (空字符串)。</span><span class="sxs-lookup"><span data-stu-id="a4473-185">String comparisons treat `Nothing` as `""` (an empty string).</span></span>

## <a name="overloading"></a><span data-ttu-id="a4473-186">重载</span><span class="sxs-lookup"><span data-stu-id="a4473-186">Overloading</span></span>
 <span data-ttu-id="a4473-187">关系比较运算符 (`<`。</span><span class="sxs-lookup"><span data-stu-id="a4473-187">The relational comparison operators (`<`.</span></span> <span data-ttu-id="a4473-188">`<=`可以重载`>=`、 `=`、、 、`<>`), 这意味着当操作数具有该类或结构的类型时, 该类或结构可以重新定义它们的行为。 `>`</span><span class="sxs-lookup"><span data-stu-id="a4473-188">`<=`, `>`, `>=`, `=`, `<>`) can be *overloaded*, which means that a class or structure can redefine their behavior when an operand has the type of that class or structure.</span></span> <span data-ttu-id="a4473-189">如果你的代码在此类或结构上使用这些运算符中的任何一种, 请确保了解重定义的行为。</span><span class="sxs-lookup"><span data-stu-id="a4473-189">If your code uses any of these operators on such a class or structure, be sure you understand the redefined behavior.</span></span> <span data-ttu-id="a4473-190">有关详细信息，请参阅 [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md)。</span><span class="sxs-lookup"><span data-stu-id="a4473-190">For more information, see [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span></span>

 <span data-ttu-id="a4473-191">请注意, [= 运算符](../../../visual-basic/language-reference/operators/assignment-operator.md)只能作为关系比较运算符重载, 而不能作为赋值运算符重载。</span><span class="sxs-lookup"><span data-stu-id="a4473-191">Notice that the [= Operator](../../../visual-basic/language-reference/operators/assignment-operator.md) can be overloaded only as a relational comparison operator, not as an assignment operator.</span></span>

## <a name="example"></a><span data-ttu-id="a4473-192">示例</span><span class="sxs-lookup"><span data-stu-id="a4473-192">Example</span></span>
 <span data-ttu-id="a4473-193">下面的示例演示了用于比较表达式的关系比较运算符的各种用法。</span><span class="sxs-lookup"><span data-stu-id="a4473-193">The following example shows various uses of relational comparison operators, which you use to compare expressions.</span></span> <span data-ttu-id="a4473-194">关系比较运算符返回一个`Boolean`结果, 该结果表示指定表达式的计算结果是否`True`为。</span><span class="sxs-lookup"><span data-stu-id="a4473-194">Relational comparison operators return a `Boolean` result that represents whether or not the stated expression evaluates to `True`.</span></span> <span data-ttu-id="a4473-195">将`>` and`<`运算符应用到字符串时, 将使用标准的按字母顺序排序的字符串进行比较。</span><span class="sxs-lookup"><span data-stu-id="a4473-195">When you apply the `>` and `<` operators to strings, the comparison is made using the normal alphabetical sorting order of the strings.</span></span> <span data-ttu-id="a4473-196">此顺序可能取决于区域设置。</span><span class="sxs-lookup"><span data-stu-id="a4473-196">This order can be dependent on your locale setting.</span></span> <span data-ttu-id="a4473-197">排序是否区分大小写取决于 "[选项比较](../../../visual-basic/language-reference/statements/option-compare-statement.md)" 设置。</span><span class="sxs-lookup"><span data-stu-id="a4473-197">Whether the sort is case-sensitive or not depends on the [Option Compare](../../../visual-basic/language-reference/statements/option-compare-statement.md) setting.</span></span>

 [!code-vb[VbVbalrOperators#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#1)]

 <span data-ttu-id="a4473-198">在前面的示例中, 第一个比较`False`返回, 其余比较返回`True`。</span><span class="sxs-lookup"><span data-stu-id="a4473-198">In the preceding example, the first comparison returns `False` and the remaining comparisons return `True`.</span></span>

## <a name="see-also"></a><span data-ttu-id="a4473-199">请参阅</span><span class="sxs-lookup"><span data-stu-id="a4473-199">See also</span></span>

- <xref:System.InvalidCastException>
- [<span data-ttu-id="a4473-200">= 运算符</span><span class="sxs-lookup"><span data-stu-id="a4473-200">= Operator</span></span>](../../../visual-basic/language-reference/operators/assignment-operator.md)
- [<span data-ttu-id="a4473-201">Visual Basic 中的运算符优先级</span><span class="sxs-lookup"><span data-stu-id="a4473-201">Operator Precedence in Visual Basic</span></span>](../../../visual-basic/language-reference/operators/operator-precedence.md)
- [<span data-ttu-id="a4473-202">按功能列出的运算符</span><span class="sxs-lookup"><span data-stu-id="a4473-202">Operators Listed by Functionality</span></span>](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)
- [<span data-ttu-id="a4473-203">数据类型疑难解答</span><span class="sxs-lookup"><span data-stu-id="a4473-203">Troubleshooting Data Types</span></span>](../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md)
- [<span data-ttu-id="a4473-204">Visual Basic 中的比较运算符</span><span class="sxs-lookup"><span data-stu-id="a4473-204">Comparison Operators in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/operators-and-expressions/comparison-operators.md)
