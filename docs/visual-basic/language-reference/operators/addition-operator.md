---
title: + 运算符（Visual Basic）
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
ms.openlocfilehash: 3187551afb7d25470f48dad894188766a811bb0a
ms.sourcegitcommit: 3094dcd17141b32a570a82ae3f62a331616e2c9c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/01/2019
ms.locfileid: "71701000"
---
# <a name="-operator-visual-basic"></a><span data-ttu-id="40931-102">+ 运算符 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="40931-102">+ Operator (Visual Basic)</span></span>
<span data-ttu-id="40931-103">将两个数相加或返回数值表达式的正值。</span><span class="sxs-lookup"><span data-stu-id="40931-103">Adds two numbers or returns the positive value of a numeric expression.</span></span> <span data-ttu-id="40931-104">还可用于连接两个字符串表达式。</span><span class="sxs-lookup"><span data-stu-id="40931-104">Can also be used to concatenate two string expressions.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="40931-105">语法</span><span class="sxs-lookup"><span data-stu-id="40931-105">Syntax</span></span>  
  
```vb
expression1 + expression2
```
  
<span data-ttu-id="40931-106">或</span><span class="sxs-lookup"><span data-stu-id="40931-106">or</span></span>

```vb  
+expression1  
```  
  
## <a name="parts"></a><span data-ttu-id="40931-107">部件</span><span class="sxs-lookup"><span data-stu-id="40931-107">Parts</span></span>  
  
|<span data-ttu-id="40931-108">术语</span><span class="sxs-lookup"><span data-stu-id="40931-108">Term</span></span>|<span data-ttu-id="40931-109">定义</span><span class="sxs-lookup"><span data-stu-id="40931-109">Definition</span></span>|  
|---|---|  
|`expression1`|<span data-ttu-id="40931-110">必需。</span><span class="sxs-lookup"><span data-stu-id="40931-110">Required.</span></span> <span data-ttu-id="40931-111">任何数值或字符串表达式。</span><span class="sxs-lookup"><span data-stu-id="40931-111">Any numeric or string expression.</span></span>|  
|`expression2`|<span data-ttu-id="40931-112">必需， `+`除非操作员计算负值。</span><span class="sxs-lookup"><span data-stu-id="40931-112">Required unless the `+` operator is calculating a negative value.</span></span> <span data-ttu-id="40931-113">任何数值或字符串表达式。</span><span class="sxs-lookup"><span data-stu-id="40931-113">Any numeric or string expression.</span></span>|  
  
## <a name="result"></a><span data-ttu-id="40931-114">结果</span><span class="sxs-lookup"><span data-stu-id="40931-114">Result</span></span>  
 <span data-ttu-id="40931-115">如果 @no__t 0 和 `expression2` 均为数值，则结果为其算术和。</span><span class="sxs-lookup"><span data-stu-id="40931-115">If `expression1` and `expression2` are both numeric, the result is their arithmetic sum.</span></span>  
  
 <span data-ttu-id="40931-116">如果 `expression2` 不存在，则 `+` 运算符是表达式的未更改值的*一元*标识运算符。</span><span class="sxs-lookup"><span data-stu-id="40931-116">If `expression2` is absent, the `+` operator is the *unary* identity operator for the unchanged value of an expression.</span></span> <span data-ttu-id="40931-117">从这种意义上讲，操作包括保留 `expression1` 的符号，因此如果 `expression1` 为负数，则结果为负。</span><span class="sxs-lookup"><span data-stu-id="40931-117">In this sense, the operation consists of retaining the sign of `expression1`, so the result is negative if `expression1` is negative.</span></span>  
  
 <span data-ttu-id="40931-118">如果 @no__t 0 和 `expression2` 都是字符串，则结果是其值的串联。</span><span class="sxs-lookup"><span data-stu-id="40931-118">If `expression1` and `expression2` are both strings, the result is the concatenation of their values.</span></span>  
  
 <span data-ttu-id="40931-119">如果 @no__t 0 和 `expression2` 属于混合类型，则执行的操作取决于它们的类型、内容和[Option Strict 语句](../../../visual-basic/language-reference/statements/option-strict-statement.md)的设置。</span><span class="sxs-lookup"><span data-stu-id="40931-119">If `expression1` and `expression2` are of mixed types, the action taken depends on their types, their contents, and the setting of the [Option Strict Statement](../../../visual-basic/language-reference/statements/option-strict-statement.md).</span></span> <span data-ttu-id="40931-120">有关详细信息，请参阅 "备注" 中的表。</span><span class="sxs-lookup"><span data-stu-id="40931-120">For more information, see the tables in "Remarks."</span></span>  
  
## <a name="supported-types"></a><span data-ttu-id="40931-121">支持的类型</span><span class="sxs-lookup"><span data-stu-id="40931-121">Supported Types</span></span>  
 <span data-ttu-id="40931-122">所有数值类型，包括无符号和浮点类型和 `Decimal`，`String`。</span><span class="sxs-lookup"><span data-stu-id="40931-122">All numeric types, including the unsigned and floating-point types and `Decimal`, and `String`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="40931-123">备注</span><span class="sxs-lookup"><span data-stu-id="40931-123">Remarks</span></span>  
 <span data-ttu-id="40931-124">通常情况下，`+` 尽可能执行算术加法运算，且仅当两个表达式都是字符串时才会进行连接。</span><span class="sxs-lookup"><span data-stu-id="40931-124">In general, `+` performs arithmetic addition when possible, and concatenates only when both expressions are strings.</span></span>  
  
 <span data-ttu-id="40931-125">如果两个表达式都不是 `Object`，则 Visual Basic 执行以下操作。</span><span class="sxs-lookup"><span data-stu-id="40931-125">If neither expression is an `Object`, Visual Basic takes the following actions.</span></span>  
  
|<span data-ttu-id="40931-126">表达式的数据类型</span><span class="sxs-lookup"><span data-stu-id="40931-126">Data types of expressions</span></span>|<span data-ttu-id="40931-127">编译器操作</span><span class="sxs-lookup"><span data-stu-id="40931-127">Action by compiler</span></span>|  
|---|---|  
|<span data-ttu-id="40931-128">这两个表达式均为数值数据类型（`SByte`、`Byte`、`Short`、`UShort`、`Integer`、`UInteger`、`Long`、`ULong`、`Decimal`、`Single` 或 0）</span><span class="sxs-lookup"><span data-stu-id="40931-128">Both expressions are numeric data types (`SByte`, `Byte`, `Short`, `UShort`, `Integer`, `UInteger`, `Long`, `ULong`, `Decimal`, `Single`, or `Double`)</span></span>|<span data-ttu-id="40931-129">把.</span><span class="sxs-lookup"><span data-stu-id="40931-129">Add.</span></span> <span data-ttu-id="40931-130">Result 数据类型是适用于`expression1`和`expression2`的数据类型的数值类型。</span><span class="sxs-lookup"><span data-stu-id="40931-130">The result data type is a numeric type appropriate for the data types of `expression1` and `expression2`.</span></span> <span data-ttu-id="40931-131">请参阅[运算符结果的数据类型](../../../visual-basic/language-reference/operators/data-types-of-operator-results.md)中的 "整数算法" 表。</span><span class="sxs-lookup"><span data-stu-id="40931-131">See the "Integer Arithmetic" tables in [Data Types of Operator Results](../../../visual-basic/language-reference/operators/data-types-of-operator-results.md).</span></span>|  
|<span data-ttu-id="40931-132">这两个表达式的类型为 `String`</span><span class="sxs-lookup"><span data-stu-id="40931-132">Both expressions are of type `String`</span></span>|<span data-ttu-id="40931-133">起来.</span><span class="sxs-lookup"><span data-stu-id="40931-133">Concatenate.</span></span>|  
|<span data-ttu-id="40931-134">一个表达式为数值数据类型，另一个表达式为字符串</span><span class="sxs-lookup"><span data-stu-id="40931-134">One expression is a numeric data type and the other is a string</span></span>|<span data-ttu-id="40931-135">如果 `Option Strict` @no__t 为-1，则会生成编译器错误。</span><span class="sxs-lookup"><span data-stu-id="40931-135">If `Option Strict` is `On`, then generate a compiler error.</span></span><br /><br /> <span data-ttu-id="40931-136">如果 `Option Strict` @no__t 为-1，则将 @no__t 隐式转换为 `Double` 并添加。</span><span class="sxs-lookup"><span data-stu-id="40931-136">If `Option Strict` is `Off`, then implicitly convert the `String` to `Double` and add.</span></span><br /><br /> <span data-ttu-id="40931-137">如果 @no__t 0 不能转换为 `Double`，则会引发 <xref:System.InvalidCastException> 异常。</span><span class="sxs-lookup"><span data-stu-id="40931-137">If the `String` cannot be converted to `Double`, then throw an <xref:System.InvalidCastException> exception.</span></span>|  
|<span data-ttu-id="40931-138">一个表达式为数值数据类型，另一个表达式为[Nothing](../../../visual-basic/language-reference/nothing.md)</span><span class="sxs-lookup"><span data-stu-id="40931-138">One expression is a numeric data type, and the other is [Nothing](../../../visual-basic/language-reference/nothing.md)</span></span>|<span data-ttu-id="40931-139">添加，@no__t 值为零。</span><span class="sxs-lookup"><span data-stu-id="40931-139">Add, with `Nothing` valued as zero.</span></span>|  
|<span data-ttu-id="40931-140">一个表达式为字符串，另一个表达式为 `Nothing`</span><span class="sxs-lookup"><span data-stu-id="40931-140">One expression is a string, and the other is `Nothing`</span></span>|<span data-ttu-id="40931-141">串联，将 @no__t 值为 ""。</span><span class="sxs-lookup"><span data-stu-id="40931-141">Concatenate, with `Nothing` valued as "".</span></span>|  
  
 <span data-ttu-id="40931-142">如果一个表达式是 @no__t 0 表达式，Visual Basic 会执行以下操作。</span><span class="sxs-lookup"><span data-stu-id="40931-142">If one expression is an `Object` expression, Visual Basic takes the following actions.</span></span>  
  
|<span data-ttu-id="40931-143">表达式的数据类型</span><span class="sxs-lookup"><span data-stu-id="40931-143">Data types of expressions</span></span>|<span data-ttu-id="40931-144">编译器操作</span><span class="sxs-lookup"><span data-stu-id="40931-144">Action by compiler</span></span>|  
|---|---|  
|<span data-ttu-id="40931-145">`Object` 表达式保存数值，另一个表达式为数值数据类型</span><span class="sxs-lookup"><span data-stu-id="40931-145">`Object` expression holds a numeric value and the other is a numeric data type</span></span>|<span data-ttu-id="40931-146">如果 `Option Strict` @no__t 为-1，则会生成编译器错误。</span><span class="sxs-lookup"><span data-stu-id="40931-146">If `Option Strict` is `On`, then generate a compiler error.</span></span><br /><br /> <span data-ttu-id="40931-147">如果 `Option Strict` @no__t 为-1，则添加。</span><span class="sxs-lookup"><span data-stu-id="40931-147">If `Option Strict` is `Off`, then add.</span></span>|  
|<span data-ttu-id="40931-148">`Object` 表达式保存一个数值，另一个值的类型为 `String`</span><span class="sxs-lookup"><span data-stu-id="40931-148">`Object` expression holds a numeric value and the other is of type `String`</span></span>|<span data-ttu-id="40931-149">如果 `Option Strict` @no__t 为-1，则会生成编译器错误。</span><span class="sxs-lookup"><span data-stu-id="40931-149">If `Option Strict` is `On`, then generate a compiler error.</span></span><br /><br /> <span data-ttu-id="40931-150">如果 `Option Strict` @no__t 为-1，则将 @no__t 隐式转换为 `Double` 并添加。</span><span class="sxs-lookup"><span data-stu-id="40931-150">If `Option Strict` is `Off`, then implicitly convert the `String` to `Double` and add.</span></span><br /><br /> <span data-ttu-id="40931-151">如果 @no__t 0 不能转换为 `Double`，则会引发 <xref:System.InvalidCastException> 异常。</span><span class="sxs-lookup"><span data-stu-id="40931-151">If the `String` cannot be converted to `Double`, then throw an <xref:System.InvalidCastException> exception.</span></span>|  
|<span data-ttu-id="40931-152">`Object` 表达式保存字符串，另一种是数值数据类型</span><span class="sxs-lookup"><span data-stu-id="40931-152">`Object` expression holds a string and the other is a numeric data type</span></span>|<span data-ttu-id="40931-153">如果 `Option Strict` @no__t 为-1，则会生成编译器错误。</span><span class="sxs-lookup"><span data-stu-id="40931-153">If `Option Strict` is `On`, then generate a compiler error.</span></span><br /><br /> <span data-ttu-id="40931-154">如果 `Option Strict` @no__t 为-1，则将 `Object` 的字符串隐式转换为 `Double` 并添加。</span><span class="sxs-lookup"><span data-stu-id="40931-154">If `Option Strict` is `Off`, then implicitly convert the string `Object` to `Double` and add.</span></span><br /><br /> <span data-ttu-id="40931-155">如果字符串 `Object` 无法转换为 `Double`，则引发 @no__t 2 异常。</span><span class="sxs-lookup"><span data-stu-id="40931-155">If the string `Object` cannot be converted to `Double`, then throw an <xref:System.InvalidCastException> exception.</span></span>|  
|<span data-ttu-id="40931-156">`Object` 表达式保存字符串，另一个表达式的类型为 `String`</span><span class="sxs-lookup"><span data-stu-id="40931-156">`Object` expression holds a string and the other is of type `String`</span></span>|<span data-ttu-id="40931-157">如果 `Option Strict` @no__t 为-1，则会生成编译器错误。</span><span class="sxs-lookup"><span data-stu-id="40931-157">If `Option Strict` is `On`, then generate a compiler error.</span></span><br /><br /> <span data-ttu-id="40931-158">如果 `Option Strict` @no__t 为-1，则将 `Object` 隐式转换为 `String` 并连接。</span><span class="sxs-lookup"><span data-stu-id="40931-158">If `Option Strict` is `Off`, then implicitly convert `Object` to `String` and concatenate.</span></span>|  
  
 <span data-ttu-id="40931-159">如果两个表达式都 `Object` 表达式，则 Visual Basic 执行以下操作（仅 `Option Strict Off`）。</span><span class="sxs-lookup"><span data-stu-id="40931-159">If both expressions are `Object` expressions, Visual Basic takes the following actions (`Option Strict Off` only).</span></span>  
  
|<span data-ttu-id="40931-160">表达式的数据类型</span><span class="sxs-lookup"><span data-stu-id="40931-160">Data types of expressions</span></span>|<span data-ttu-id="40931-161">编译器操作</span><span class="sxs-lookup"><span data-stu-id="40931-161">Action by compiler</span></span>|  
|---|---|  
|<span data-ttu-id="40931-162">@No__t （0）表达式都包含数字值</span><span class="sxs-lookup"><span data-stu-id="40931-162">Both `Object` expressions hold numeric values</span></span>|<span data-ttu-id="40931-163">把.</span><span class="sxs-lookup"><span data-stu-id="40931-163">Add.</span></span>|  
|<span data-ttu-id="40931-164">@No__t-0 表达式的类型为 `String`</span><span class="sxs-lookup"><span data-stu-id="40931-164">Both `Object` expressions are of type `String`</span></span>|<span data-ttu-id="40931-165">起来.</span><span class="sxs-lookup"><span data-stu-id="40931-165">Concatenate.</span></span>|  
|<span data-ttu-id="40931-166">一个 @no__t 0 表达式保存一个数值，另一个包含一个字符串</span><span class="sxs-lookup"><span data-stu-id="40931-166">One `Object` expression holds a numeric value and the other holds a string</span></span>|<span data-ttu-id="40931-167">将字符串 @no__t 隐式转换为 `Double` 并添加。</span><span class="sxs-lookup"><span data-stu-id="40931-167">Implicitly convert the string `Object` to `Double` and add.</span></span><br /><br /> <span data-ttu-id="40931-168">如果字符串 `Object` 不能转换为数值，则引发 <xref:System.InvalidCastException> 异常。</span><span class="sxs-lookup"><span data-stu-id="40931-168">If the string `Object` cannot be converted to a numeric value, then throw an <xref:System.InvalidCastException> exception.</span></span>|  
  
 <span data-ttu-id="40931-169">如果 @no__t 0 表达式的计算结果为[Nothing](../../../visual-basic/language-reference/nothing.md)或 <xref:System.DBNull>，则 @no__t，则将其视为值为 "" 的 `String`。</span><span class="sxs-lookup"><span data-stu-id="40931-169">If either `Object` expression evaluates to [Nothing](../../../visual-basic/language-reference/nothing.md) or <xref:System.DBNull>, the `+` operator treats it as a `String` with a value of "".</span></span>  
  
> [!NOTE]
> <span data-ttu-id="40931-170">使用 @no__t 0 运算符时，可能无法确定是进行加法还是字符串串联。</span><span class="sxs-lookup"><span data-stu-id="40931-170">When you use the `+` operator, you might not be able to determine whether addition or string concatenation will occur.</span></span> <span data-ttu-id="40931-171">将 `&` 运算符用于串联以消除多义性，并提供自文档代码。</span><span class="sxs-lookup"><span data-stu-id="40931-171">Use the `&` operator for concatenation to eliminate ambiguity and to provide self-documenting code.</span></span>  
  
## <a name="overloading"></a><span data-ttu-id="40931-172">重载</span><span class="sxs-lookup"><span data-stu-id="40931-172">Overloading</span></span>  
 <span data-ttu-id="40931-173">@No__t-0 运算符可*重载*，这意味着当操作数具有该类或结构的类型时，该类或结构可以重新定义其行为。</span><span class="sxs-lookup"><span data-stu-id="40931-173">The `+` operator can be *overloaded*, which means that a class or structure can redefine its behavior when an operand has the type of that class or structure.</span></span> <span data-ttu-id="40931-174">如果你的代码在该类或结构上使用此运算符，请确保了解其重新定义的行为。</span><span class="sxs-lookup"><span data-stu-id="40931-174">If your code uses this operator on such a class or structure, be sure you understand its redefined behavior.</span></span> <span data-ttu-id="40931-175">有关详细信息，请参阅 [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md)。</span><span class="sxs-lookup"><span data-stu-id="40931-175">For more information, see [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="40931-176">示例</span><span class="sxs-lookup"><span data-stu-id="40931-176">Example</span></span>  
 <span data-ttu-id="40931-177">下面的示例使用 `+` 运算符来添加数字。</span><span class="sxs-lookup"><span data-stu-id="40931-177">The following example uses the `+` operator to add numbers.</span></span> <span data-ttu-id="40931-178">如果操作数均为数值，则 Visual Basic 计算算术结果。</span><span class="sxs-lookup"><span data-stu-id="40931-178">If the operands are both numeric, Visual Basic computes the arithmetic result.</span></span> <span data-ttu-id="40931-179">算术结果表示两个操作数之和。</span><span class="sxs-lookup"><span data-stu-id="40931-179">The arithmetic result represents the sum of the two operands.</span></span>  
  
 [!code-vb[VbVbalrOperators#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#6)]  
  
 <span data-ttu-id="40931-180">你还可以使用 @no__t 0 运算符来串联字符串。</span><span class="sxs-lookup"><span data-stu-id="40931-180">You can also use the `+` operator to concatenate strings.</span></span> <span data-ttu-id="40931-181">如果两个操作数都是字符串，Visual Basic 将它们连接起来。</span><span class="sxs-lookup"><span data-stu-id="40931-181">If the operands are both strings, Visual Basic concatenates them.</span></span> <span data-ttu-id="40931-182">连接结果表示一个字符串，该字符串包含两个操作数的内容。</span><span class="sxs-lookup"><span data-stu-id="40931-182">The concatenation result represents a single string consisting of the contents of the two operands one after the other.</span></span>  
  
 <span data-ttu-id="40931-183">如果操作数属于混合类型，则结果取决于[Option Strict 语句](../../../visual-basic/language-reference/statements/option-strict-statement.md)的设置。</span><span class="sxs-lookup"><span data-stu-id="40931-183">If the operands are of mixed types, the result depends on the setting of the [Option Strict Statement](../../../visual-basic/language-reference/statements/option-strict-statement.md).</span></span> <span data-ttu-id="40931-184">下面的示例说明 `Option Strict` @no__t 时的结果。</span><span class="sxs-lookup"><span data-stu-id="40931-184">The following example illustrates the result when `Option Strict` is `On`.</span></span>  
  
 [!code-vb[VbVbalrOperators#53](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class3.vb#53)]  
  
 [!code-vb[VbVbalrOperators#50](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class2.vb#50)]  
[!code-vb[VbVbalrOperators#51](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class2.vb#51)]  
  
 <span data-ttu-id="40931-185">下面的示例说明 `Option Strict` @no__t 时的结果。</span><span class="sxs-lookup"><span data-stu-id="40931-185">The following example illustrates the result when `Option Strict` is `Off`.</span></span>  
  
 [!code-vb[VbVbalrOperators#54](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class2.vb#54)]  
  
 [!code-vb[VbVbalrOperators#50](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class2.vb#50)]  
[!code-vb[VbVbalrOperators#52](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class2.vb#52)]  
  
 <span data-ttu-id="40931-186">为了消除多义性，应使用 `&` 运算符而不是 `+` 进行串联。</span><span class="sxs-lookup"><span data-stu-id="40931-186">To eliminate ambiguity, you should use the `&` operator instead of `+` for concatenation.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="40931-187">请参阅</span><span class="sxs-lookup"><span data-stu-id="40931-187">See also</span></span>

- [<span data-ttu-id="40931-188">& 运算符</span><span class="sxs-lookup"><span data-stu-id="40931-188">& Operator</span></span>](../../../visual-basic/language-reference/operators/concatenation-operator.md)
- [<span data-ttu-id="40931-189">串联运算符</span><span class="sxs-lookup"><span data-stu-id="40931-189">Concatenation Operators</span></span>](../../../visual-basic/language-reference/operators/concatenation-operators.md)
- [<span data-ttu-id="40931-190">算术运算符</span><span class="sxs-lookup"><span data-stu-id="40931-190">Arithmetic Operators</span></span>](../../../visual-basic/language-reference/operators/arithmetic-operators.md)
- [<span data-ttu-id="40931-191">按功能列出的运算符</span><span class="sxs-lookup"><span data-stu-id="40931-191">Operators Listed by Functionality</span></span>](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)
- [<span data-ttu-id="40931-192">Visual Basic 中的运算符优先级</span><span class="sxs-lookup"><span data-stu-id="40931-192">Operator Precedence in Visual Basic</span></span>](../../../visual-basic/language-reference/operators/operator-precedence.md)
- [<span data-ttu-id="40931-193">Visual Basic 中的算术运算符</span><span class="sxs-lookup"><span data-stu-id="40931-193">Arithmetic Operators in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/operators-and-expressions/arithmetic-operators.md)
- [<span data-ttu-id="40931-194">Option Strict 语句</span><span class="sxs-lookup"><span data-stu-id="40931-194">Option Strict Statement</span></span>](../../../visual-basic/language-reference/statements/option-strict-statement.md)
