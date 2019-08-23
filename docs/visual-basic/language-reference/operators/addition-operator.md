---
title: + 运算符 (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.+
helpviewer_keywords:
- arithmetic operators [Visual Basic], addition
- + operator
- concatenation operators [Visual Basic], syntax
- strings [Visual Basic], concatenating
- sum operator [Visual Basic]
ms.assetid: 5694778f-0a2c-4539-8009-f66f318fb46d
ms.openlocfilehash: ab18a7137a31ed8e616f465e7d617305c96d7b10
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2019
ms.locfileid: "69943022"
---
# <a name="-operator-visual-basic"></a><span data-ttu-id="38613-102">+ 运算符 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="38613-102">+ Operator (Visual Basic)</span></span>
<span data-ttu-id="38613-103">将两个数相加或返回数值表达式的正值。</span><span class="sxs-lookup"><span data-stu-id="38613-103">Adds two numbers or returns the positive value of a numeric expression.</span></span> <span data-ttu-id="38613-104">还可用于连接两个字符串表达式。</span><span class="sxs-lookup"><span data-stu-id="38613-104">Can also be used to concatenate two string expressions.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="38613-105">语法</span><span class="sxs-lookup"><span data-stu-id="38613-105">Syntax</span></span>  
  
```vb
expression1 + expression2  
- or -  
+ expression1  
```  
  
## <a name="parts"></a><span data-ttu-id="38613-106">部件</span><span class="sxs-lookup"><span data-stu-id="38613-106">Parts</span></span>  
  
|<span data-ttu-id="38613-107">术语</span><span class="sxs-lookup"><span data-stu-id="38613-107">Term</span></span>|<span data-ttu-id="38613-108">定义</span><span class="sxs-lookup"><span data-stu-id="38613-108">Definition</span></span>|  
|---|---|  
|`expression1`|<span data-ttu-id="38613-109">必需。</span><span class="sxs-lookup"><span data-stu-id="38613-109">Required.</span></span> <span data-ttu-id="38613-110">任何数值或字符串表达式。</span><span class="sxs-lookup"><span data-stu-id="38613-110">Any numeric or string expression.</span></span>|  
|`expression2`|<span data-ttu-id="38613-111">必需, `+`除非操作员计算负值。</span><span class="sxs-lookup"><span data-stu-id="38613-111">Required unless the `+` operator is calculating a negative value.</span></span> <span data-ttu-id="38613-112">任何数值或字符串表达式。</span><span class="sxs-lookup"><span data-stu-id="38613-112">Any numeric or string expression.</span></span>|  
  
## <a name="result"></a><span data-ttu-id="38613-113">结果</span><span class="sxs-lookup"><span data-stu-id="38613-113">Result</span></span>  
 <span data-ttu-id="38613-114">如果`expression1` 和`expression2`均为数值, 则结果为其算术和。</span><span class="sxs-lookup"><span data-stu-id="38613-114">If `expression1` and `expression2` are both numeric, the result is their arithmetic sum.</span></span>  
  
 <span data-ttu-id="38613-115">如果`expression2`不存在, 则`+`运算符为表达式的未更改值的*一元*标识运算符。</span><span class="sxs-lookup"><span data-stu-id="38613-115">If `expression2` is absent, the `+` operator is the *unary* identity operator for the unchanged value of an expression.</span></span> <span data-ttu-id="38613-116">从这种意义上讲, 操作包括保留的符号`expression1`, 因此如果`expression1`为负, 则结果为负。</span><span class="sxs-lookup"><span data-stu-id="38613-116">In this sense, the operation consists of retaining the sign of `expression1`, so the result is negative if `expression1` is negative.</span></span>  
  
 <span data-ttu-id="38613-117">如果`expression1` 和`expression2`都是字符串, 则结果是其值的串联。</span><span class="sxs-lookup"><span data-stu-id="38613-117">If `expression1` and `expression2` are both strings, the result is the concatenation of their values.</span></span>  
  
 <span data-ttu-id="38613-118">如果`expression1` 和`expression2`属于混合类型, 则执行的操作取决于它们的类型、内容和[Option Strict 语句](../../../visual-basic/language-reference/statements/option-strict-statement.md)的设置。</span><span class="sxs-lookup"><span data-stu-id="38613-118">If `expression1` and `expression2` are of mixed types, the action taken depends on their types, their contents, and the setting of the [Option Strict Statement](../../../visual-basic/language-reference/statements/option-strict-statement.md).</span></span> <span data-ttu-id="38613-119">有关详细信息, 请参阅 "备注" 中的表。</span><span class="sxs-lookup"><span data-stu-id="38613-119">For more information, see the tables in "Remarks."</span></span>  
  
## <a name="supported-types"></a><span data-ttu-id="38613-120">支持的类型</span><span class="sxs-lookup"><span data-stu-id="38613-120">Supported Types</span></span>  
 <span data-ttu-id="38613-121">所有数值类型, 包括无符号和浮点类型以及`Decimal` `String`和。</span><span class="sxs-lookup"><span data-stu-id="38613-121">All numeric types, including the unsigned and floating-point types and `Decimal`, and `String`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="38613-122">备注</span><span class="sxs-lookup"><span data-stu-id="38613-122">Remarks</span></span>  
 <span data-ttu-id="38613-123">通常, `+`如果可能, 将执行算术加法运算, 并且仅当两个表达式都是字符串时才会进行连接。</span><span class="sxs-lookup"><span data-stu-id="38613-123">In general, `+` performs arithmetic addition when possible, and concatenates only when both expressions are strings.</span></span>  
  
 <span data-ttu-id="38613-124">如果两个表达式均`Object`为, 则 Visual Basic 执行以下操作。</span><span class="sxs-lookup"><span data-stu-id="38613-124">If neither expression is an `Object`, Visual Basic takes the following actions.</span></span>  
  
|<span data-ttu-id="38613-125">表达式的数据类型</span><span class="sxs-lookup"><span data-stu-id="38613-125">Data types of expressions</span></span>|<span data-ttu-id="38613-126">编译器操作</span><span class="sxs-lookup"><span data-stu-id="38613-126">Action by compiler</span></span>|  
|---|---|  
|<span data-ttu-id="38613-127">这两个表达式均为数值`SByte`数据`Byte`类型 ( `UShort`、 `Integer` `Short` `UInteger` 、、`Decimal`、 `ULong` 、、`Double`、、、或) `Long` `Single`</span><span class="sxs-lookup"><span data-stu-id="38613-127">Both expressions are numeric data types (`SByte`, `Byte`, `Short`, `UShort`, `Integer`, `UInteger`, `Long`, `ULong`, `Decimal`, `Single`, or `Double`)</span></span>|<span data-ttu-id="38613-128">把.</span><span class="sxs-lookup"><span data-stu-id="38613-128">Add.</span></span> <span data-ttu-id="38613-129">Result 数据类型是适用于`expression1`和`expression2`的数据类型的数值类型。</span><span class="sxs-lookup"><span data-stu-id="38613-129">The result data type is a numeric type appropriate for the data types of `expression1` and `expression2`.</span></span> <span data-ttu-id="38613-130">请参阅[运算符结果的数据类型](../../../visual-basic/language-reference/operators/data-types-of-operator-results.md)中的 "整数算法" 表。</span><span class="sxs-lookup"><span data-stu-id="38613-130">See the "Integer Arithmetic" tables in [Data Types of Operator Results](../../../visual-basic/language-reference/operators/data-types-of-operator-results.md).</span></span>|  
|<span data-ttu-id="38613-131">这两个表达式的类型为`String`</span><span class="sxs-lookup"><span data-stu-id="38613-131">Both expressions are of type `String`</span></span>|<span data-ttu-id="38613-132">起来.</span><span class="sxs-lookup"><span data-stu-id="38613-132">Concatenate.</span></span>|  
|<span data-ttu-id="38613-133">一个表达式为数值数据类型, 另一个表达式为字符串</span><span class="sxs-lookup"><span data-stu-id="38613-133">One expression is a numeric data type and the other is a string</span></span>|<span data-ttu-id="38613-134">如果`Option Strict` 为`On`, 则生成编译器错误。</span><span class="sxs-lookup"><span data-stu-id="38613-134">If `Option Strict` is `On`, then generate a compiler error.</span></span><br /><br /> <span data-ttu-id="38613-135">如果`Option Strict`为`Off` ,则`Double`将隐式转换为并添加。`String`</span><span class="sxs-lookup"><span data-stu-id="38613-135">If `Option Strict` is `Off`, then implicitly convert the `String` to `Double` and add.</span></span><br /><br /> <span data-ttu-id="38613-136">如果无法转换为`Double`, 则引发<xref:System.InvalidCastException>异常。 `String`</span><span class="sxs-lookup"><span data-stu-id="38613-136">If the `String` cannot be converted to `Double`, then throw an <xref:System.InvalidCastException> exception.</span></span>|  
|<span data-ttu-id="38613-137">一个表达式为数值数据类型, 另一个表达式为[Nothing](../../../visual-basic/language-reference/nothing.md)</span><span class="sxs-lookup"><span data-stu-id="38613-137">One expression is a numeric data type, and the other is [Nothing](../../../visual-basic/language-reference/nothing.md)</span></span>|<span data-ttu-id="38613-138">添加, 其`Nothing`值为零。</span><span class="sxs-lookup"><span data-stu-id="38613-138">Add, with `Nothing` valued as zero.</span></span>|  
|<span data-ttu-id="38613-139">一个表达式是字符串, 另一个表达式是`Nothing`</span><span class="sxs-lookup"><span data-stu-id="38613-139">One expression is a string, and the other is `Nothing`</span></span>|<span data-ttu-id="38613-140">串联, 其`Nothing`值为 ""。</span><span class="sxs-lookup"><span data-stu-id="38613-140">Concatenate, with `Nothing` valued as "".</span></span>|  
  
 <span data-ttu-id="38613-141">如果一个表达式是表达式`Object` , Visual Basic 会执行以下操作。</span><span class="sxs-lookup"><span data-stu-id="38613-141">If one expression is an `Object` expression, Visual Basic takes the following actions.</span></span>  
  
|<span data-ttu-id="38613-142">表达式的数据类型</span><span class="sxs-lookup"><span data-stu-id="38613-142">Data types of expressions</span></span>|<span data-ttu-id="38613-143">编译器操作</span><span class="sxs-lookup"><span data-stu-id="38613-143">Action by compiler</span></span>|  
|---|---|  
|<span data-ttu-id="38613-144">`Object`表达式保存数字值, 另一种是数值数据类型</span><span class="sxs-lookup"><span data-stu-id="38613-144">`Object` expression holds a numeric value and the other is a numeric data type</span></span>|<span data-ttu-id="38613-145">如果`Option Strict` 为`On`, 则生成编译器错误。</span><span class="sxs-lookup"><span data-stu-id="38613-145">If `Option Strict` is `On`, then generate a compiler error.</span></span><br /><br /> <span data-ttu-id="38613-146">如果`Option Strict` 为`Off`, 则添加。</span><span class="sxs-lookup"><span data-stu-id="38613-146">If `Option Strict` is `Off`, then add.</span></span>|  
|<span data-ttu-id="38613-147">`Object`表达式保存一个数字值, 另一个的类型为`String`</span><span class="sxs-lookup"><span data-stu-id="38613-147">`Object` expression holds a numeric value and the other is of type `String`</span></span>|<span data-ttu-id="38613-148">如果`Option Strict` 为`On`, 则生成编译器错误。</span><span class="sxs-lookup"><span data-stu-id="38613-148">If `Option Strict` is `On`, then generate a compiler error.</span></span><br /><br /> <span data-ttu-id="38613-149">如果`Option Strict`为`Off` ,则`Double`将隐式转换为并添加。`String`</span><span class="sxs-lookup"><span data-stu-id="38613-149">If `Option Strict` is `Off`, then implicitly convert the `String` to `Double` and add.</span></span><br /><br /> <span data-ttu-id="38613-150">如果无法转换为`Double`, 则引发<xref:System.InvalidCastException>异常。 `String`</span><span class="sxs-lookup"><span data-stu-id="38613-150">If the `String` cannot be converted to `Double`, then throw an <xref:System.InvalidCastException> exception.</span></span>|  
|<span data-ttu-id="38613-151">`Object`表达式保存一个字符串, 另一个表达式为数值数据类型</span><span class="sxs-lookup"><span data-stu-id="38613-151">`Object` expression holds a string and the other is a numeric data type</span></span>|<span data-ttu-id="38613-152">如果`Option Strict` 为`On`, 则生成编译器错误。</span><span class="sxs-lookup"><span data-stu-id="38613-152">If `Option Strict` is `On`, then generate a compiler error.</span></span><br /><br /> <span data-ttu-id="38613-153">如果`Option Strict` `Object` `Double`为`Off`, 则将字符串隐式转换为并添加。</span><span class="sxs-lookup"><span data-stu-id="38613-153">If `Option Strict` is `Off`, then implicitly convert the string `Object` to `Double` and add.</span></span><br /><br /> <span data-ttu-id="38613-154">如果字符串`Object`无法转换为`Double`, 则引发<xref:System.InvalidCastException>异常。</span><span class="sxs-lookup"><span data-stu-id="38613-154">If the string `Object` cannot be converted to `Double`, then throw an <xref:System.InvalidCastException> exception.</span></span>|  
|<span data-ttu-id="38613-155">`Object`表达式保存了一个字符串, 另一个的类型为`String`</span><span class="sxs-lookup"><span data-stu-id="38613-155">`Object` expression holds a string and the other is of type `String`</span></span>|<span data-ttu-id="38613-156">如果`Option Strict` 为`On`, 则生成编译器错误。</span><span class="sxs-lookup"><span data-stu-id="38613-156">If `Option Strict` is `On`, then generate a compiler error.</span></span><br /><br /> <span data-ttu-id="38613-157">如果`Option Strict` `Object` `String`为`Off`, 则隐式转换到并连接。</span><span class="sxs-lookup"><span data-stu-id="38613-157">If `Option Strict` is `Off`, then implicitly convert `Object` to `String` and concatenate.</span></span>|  
  
 <span data-ttu-id="38613-158">如果两个表达式`Object`都是表达式, Visual Basic 将采取以下`Option Strict Off`操作 (仅限)。</span><span class="sxs-lookup"><span data-stu-id="38613-158">If both expressions are `Object` expressions, Visual Basic takes the following actions (`Option Strict Off` only).</span></span>  
  
|<span data-ttu-id="38613-159">表达式的数据类型</span><span class="sxs-lookup"><span data-stu-id="38613-159">Data types of expressions</span></span>|<span data-ttu-id="38613-160">编译器操作</span><span class="sxs-lookup"><span data-stu-id="38613-160">Action by compiler</span></span>|  
|---|---|  
|<span data-ttu-id="38613-161">两`Object`个表达式都保存数字值</span><span class="sxs-lookup"><span data-stu-id="38613-161">Both `Object` expressions hold numeric values</span></span>|<span data-ttu-id="38613-162">把.</span><span class="sxs-lookup"><span data-stu-id="38613-162">Add.</span></span>|  
|<span data-ttu-id="38613-163">这`Object`两个表达式的类型为`String`</span><span class="sxs-lookup"><span data-stu-id="38613-163">Both `Object` expressions are of type `String`</span></span>|<span data-ttu-id="38613-164">起来.</span><span class="sxs-lookup"><span data-stu-id="38613-164">Concatenate.</span></span>|  
|<span data-ttu-id="38613-165">一个`Object`表达式保存一个数字值, 另一个表达式保存一个字符串</span><span class="sxs-lookup"><span data-stu-id="38613-165">One `Object` expression holds a numeric value and the other holds a string</span></span>|<span data-ttu-id="38613-166">将字符串`Object`隐式转换`Double`为并添加。</span><span class="sxs-lookup"><span data-stu-id="38613-166">Implicitly convert the string `Object` to `Double` and add.</span></span><br /><br /> <span data-ttu-id="38613-167">如果字符串`Object`不能转换为数字值, 则<xref:System.InvalidCastException>引发异常。</span><span class="sxs-lookup"><span data-stu-id="38613-167">If the string `Object` cannot be converted to a numeric value, then throw an <xref:System.InvalidCastException> exception.</span></span>|  
  
 <span data-ttu-id="38613-168">如果其中`Object`一个表达式的计算结果<xref:System.DBNull>为[Nothing](../../../visual-basic/language-reference/nothing.md)或`String` , 则`+`运算符将其视为值为 "" 的。</span><span class="sxs-lookup"><span data-stu-id="38613-168">If either `Object` expression evaluates to [Nothing](../../../visual-basic/language-reference/nothing.md) or <xref:System.DBNull>, the `+` operator treats it as a `String` with a value of "".</span></span>  
  
> [!NOTE]
> <span data-ttu-id="38613-169">使用`+`运算符时, 可能无法确定是进行加法还是字符串串联。</span><span class="sxs-lookup"><span data-stu-id="38613-169">When you use the `+` operator, you might not be able to determine whether addition or string concatenation will occur.</span></span> <span data-ttu-id="38613-170">`&`使用运算符进行串联以消除多义性, 并提供自文档代码。</span><span class="sxs-lookup"><span data-stu-id="38613-170">Use the `&` operator for concatenation to eliminate ambiguity and to provide self-documenting code.</span></span>  
  
## <a name="overloading"></a><span data-ttu-id="38613-171">重载</span><span class="sxs-lookup"><span data-stu-id="38613-171">Overloading</span></span>  
 <span data-ttu-id="38613-172">运算符可以重载, 这意味着当操作数具有该类或结构的类型时, 该类或结构可以重新定义其行为。 `+`</span><span class="sxs-lookup"><span data-stu-id="38613-172">The `+` operator can be *overloaded*, which means that a class or structure can redefine its behavior when an operand has the type of that class or structure.</span></span> <span data-ttu-id="38613-173">如果你的代码在该类或结构上使用此运算符, 请确保了解其重新定义的行为。</span><span class="sxs-lookup"><span data-stu-id="38613-173">If your code uses this operator on such a class or structure, be sure you understand its redefined behavior.</span></span> <span data-ttu-id="38613-174">有关详细信息，请参阅 [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md)。</span><span class="sxs-lookup"><span data-stu-id="38613-174">For more information, see [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="38613-175">示例</span><span class="sxs-lookup"><span data-stu-id="38613-175">Example</span></span>  
 <span data-ttu-id="38613-176">下面的示例使用`+`运算符来添加数字。</span><span class="sxs-lookup"><span data-stu-id="38613-176">The following example uses the `+` operator to add numbers.</span></span> <span data-ttu-id="38613-177">如果操作数均为数值, 则 Visual Basic 计算算术结果。</span><span class="sxs-lookup"><span data-stu-id="38613-177">If the operands are both numeric, Visual Basic computes the arithmetic result.</span></span> <span data-ttu-id="38613-178">算术结果表示两个操作数之和。</span><span class="sxs-lookup"><span data-stu-id="38613-178">The arithmetic result represents the sum of the two operands.</span></span>  
  
 [!code-vb[VbVbalrOperators#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#6)]  
  
 <span data-ttu-id="38613-179">还可以使用`+`运算符来串联字符串。</span><span class="sxs-lookup"><span data-stu-id="38613-179">You can also use the `+` operator to concatenate strings.</span></span> <span data-ttu-id="38613-180">如果两个操作数都是字符串, Visual Basic 将它们连接起来。</span><span class="sxs-lookup"><span data-stu-id="38613-180">If the operands are both strings, Visual Basic concatenates them.</span></span> <span data-ttu-id="38613-181">连接结果表示一个字符串, 该字符串包含两个操作数的内容。</span><span class="sxs-lookup"><span data-stu-id="38613-181">The concatenation result represents a single string consisting of the contents of the two operands one after the other.</span></span>  
  
 <span data-ttu-id="38613-182">如果操作数属于混合类型, 则结果取决于[Option Strict 语句](../../../visual-basic/language-reference/statements/option-strict-statement.md)的设置。</span><span class="sxs-lookup"><span data-stu-id="38613-182">If the operands are of mixed types, the result depends on the setting of the [Option Strict Statement](../../../visual-basic/language-reference/statements/option-strict-statement.md).</span></span> <span data-ttu-id="38613-183">下面的示例演示了在为`Option Strict` `On`时的结果。</span><span class="sxs-lookup"><span data-stu-id="38613-183">The following example illustrates the result when `Option Strict` is `On`.</span></span>  
  
 [!code-vb[VbVbalrOperators#53](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class3.vb#53)]  
  
 [!code-vb[VbVbalrOperators#50](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class2.vb#50)]  
[!code-vb[VbVbalrOperators#51](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class2.vb#51)]  
  
 <span data-ttu-id="38613-184">下面的示例演示了在为`Option Strict` `Off`时的结果。</span><span class="sxs-lookup"><span data-stu-id="38613-184">The following example illustrates the result when `Option Strict` is `Off`.</span></span>  
  
 [!code-vb[VbVbalrOperators#54](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class2.vb#54)]  
  
 [!code-vb[VbVbalrOperators#50](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class2.vb#50)]  
[!code-vb[VbVbalrOperators#52](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class2.vb#52)]  
  
 <span data-ttu-id="38613-185">为了消除多义性, 应使用`&`运算符`+`而不是串联。</span><span class="sxs-lookup"><span data-stu-id="38613-185">To eliminate ambiguity, you should use the `&` operator instead of `+` for concatenation.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="38613-186">请参阅</span><span class="sxs-lookup"><span data-stu-id="38613-186">See also</span></span>

- [<span data-ttu-id="38613-187">& 运算符</span><span class="sxs-lookup"><span data-stu-id="38613-187">& Operator</span></span>](../../../visual-basic/language-reference/operators/concatenation-operator.md)
- [<span data-ttu-id="38613-188">串联运算符</span><span class="sxs-lookup"><span data-stu-id="38613-188">Concatenation Operators</span></span>](../../../visual-basic/language-reference/operators/concatenation-operators.md)
- [<span data-ttu-id="38613-189">算术运算符</span><span class="sxs-lookup"><span data-stu-id="38613-189">Arithmetic Operators</span></span>](../../../visual-basic/language-reference/operators/arithmetic-operators.md)
- [<span data-ttu-id="38613-190">按功能列出的运算符</span><span class="sxs-lookup"><span data-stu-id="38613-190">Operators Listed by Functionality</span></span>](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)
- [<span data-ttu-id="38613-191">Visual Basic 中的运算符优先级</span><span class="sxs-lookup"><span data-stu-id="38613-191">Operator Precedence in Visual Basic</span></span>](../../../visual-basic/language-reference/operators/operator-precedence.md)
- [<span data-ttu-id="38613-192">Visual Basic 中的算术运算符</span><span class="sxs-lookup"><span data-stu-id="38613-192">Arithmetic Operators in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/operators-and-expressions/arithmetic-operators.md)
- [<span data-ttu-id="38613-193">Option Strict 语句</span><span class="sxs-lookup"><span data-stu-id="38613-193">Option Strict Statement</span></span>](../../../visual-basic/language-reference/statements/option-strict-statement.md)
