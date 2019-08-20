---
title: Mod 运算符 (Visual Basic)
ms.date: 04/24/2018
f1_keywords:
- vb.Mod
helpviewer_keywords:
- remainder (Mod operator)
- division operator [Visual Basic], Mod operator
- modulus operator [Visual Basic], Visual Basic
- Mod operator [Visual Basic]
- operators [Visual Basic], division
- arithmetic operators [Visual Basic], Mod
- math operators [Visual Basic]
ms.assetid: 6ff7e40e-cec8-4c77-bff6-8ddd2791c25b
ms.openlocfilehash: c801facd95d93652414409549bb5ff2fa633748b
ms.sourcegitcommit: 986f836f72ef10876878bd6217174e41464c145a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/19/2019
ms.locfileid: "69611524"
---
# <a name="mod-operator-visual-basic"></a><span data-ttu-id="da582-102">Mod 运算符 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="da582-102">Mod operator (Visual Basic)</span></span>
<span data-ttu-id="da582-103">将两个数字相除, 仅返回余数。</span><span class="sxs-lookup"><span data-stu-id="da582-103">Divides two numbers and returns only the remainder.</span></span>

## <a name="syntax"></a><span data-ttu-id="da582-104">语法</span><span class="sxs-lookup"><span data-stu-id="da582-104">Syntax</span></span>

```vb
result = number1 Mod number2
```
  
## <a name="parts"></a><span data-ttu-id="da582-105">部件</span><span class="sxs-lookup"><span data-stu-id="da582-105">Parts</span></span>  
 <span data-ttu-id="da582-106">`result`（必需）。</span><span class="sxs-lookup"><span data-stu-id="da582-106">`result` Required.</span></span> <span data-ttu-id="da582-107">任何数值变量或属性。</span><span class="sxs-lookup"><span data-stu-id="da582-107">Any numeric variable or property.</span></span>

 <span data-ttu-id="da582-108">`number1`（必需）。</span><span class="sxs-lookup"><span data-stu-id="da582-108">`number1` Required.</span></span> <span data-ttu-id="da582-109">任何数值表达式。</span><span class="sxs-lookup"><span data-stu-id="da582-109">Any numeric expression.</span></span>

 <span data-ttu-id="da582-110">`number2`（必需）。</span><span class="sxs-lookup"><span data-stu-id="da582-110">`number2` Required.</span></span> <span data-ttu-id="da582-111">任何数值表达式。</span><span class="sxs-lookup"><span data-stu-id="da582-111">Any numeric expression.</span></span>

## <a name="supported-types"></a><span data-ttu-id="da582-112">支持的类型</span><span class="sxs-lookup"><span data-stu-id="da582-112">Supported types</span></span>
 <span data-ttu-id="da582-113">所有数值类型。</span><span class="sxs-lookup"><span data-stu-id="da582-113">All numeric types.</span></span> <span data-ttu-id="da582-114">这包括无符号和浮点类型和`Decimal`。</span><span class="sxs-lookup"><span data-stu-id="da582-114">This includes the unsigned and floating-point types and `Decimal`.</span></span>

## <a name="result"></a><span data-ttu-id="da582-115">结果</span><span class="sxs-lookup"><span data-stu-id="da582-115">Result</span></span>

<span data-ttu-id="da582-116">结果是`number1` `number2`除以后的余数。</span><span class="sxs-lookup"><span data-stu-id="da582-116">The result is the remainder after `number1` is divided by `number2`.</span></span> <span data-ttu-id="da582-117">例如, 表达式`14 Mod 4`的计算结果为2。</span><span class="sxs-lookup"><span data-stu-id="da582-117">For example, the expression `14 Mod 4` evaluates to 2.</span></span>

> [!NOTE]
> <span data-ttu-id="da582-118">在数学中,*余数*和*模数*之间存在差异, 但负数的结果不同。</span><span class="sxs-lookup"><span data-stu-id="da582-118">There is a difference between *remainder* and *modulus* in mathematics, with different results for negative numbers.</span></span> <span data-ttu-id="da582-119">Visual Basic `Mod` 、.NET Framework `op_Modulus`运算符和基础[rem](<xref:System.Reflection.Emit.OpCodes.Rem>) IL 指令中的运算符都执行了余数运算。</span><span class="sxs-lookup"><span data-stu-id="da582-119">The `Mod` operator in Visual Basic, the .NET Framework `op_Modulus` operator, and the underlying [rem](<xref:System.Reflection.Emit.OpCodes.Rem>) IL instruction all perform a remainder operation.</span></span>

<span data-ttu-id="da582-120">`Mod`操作的结果保留被`number1`除数的符号, 因此它可以是正数也可以是负数。</span><span class="sxs-lookup"><span data-stu-id="da582-120">The result of a `Mod` operation retains the sign of the dividend, `number1`, and so it may be positive or negative.</span></span> <span data-ttu-id="da582-121">结果始终处于范围内 (-`number2`, `number2`), 而不是排他。</span><span class="sxs-lookup"><span data-stu-id="da582-121">The result is always in the range (-`number2`, `number2`), exclusive.</span></span> <span data-ttu-id="da582-122">例如:</span><span class="sxs-lookup"><span data-stu-id="da582-122">For example:</span></span>

```vb
Public Module Example
   Public Sub Main()
      Console.WriteLine($" 8 Mod  3 = {8 Mod 3}")
      Console.WriteLine($"-8 Mod  3 = {-8 Mod 3}")
      Console.WriteLine($" 8 Mod -3 = {8 Mod -3}")
      Console.WriteLine($"-8 Mod -3 = {-8 Mod -3}")
   End Sub
End Module
' The example displays the following output:
'       8 Mod  3 = 2
'      -8 Mod  3 = -2
'       8 Mod -3 = 2
'      -8 Mod -3 = -2
```

## <a name="remarks"></a><span data-ttu-id="da582-123">备注</span><span class="sxs-lookup"><span data-stu-id="da582-123">Remarks</span></span>
 <span data-ttu-id="da582-124">`number1`如果或`number2`是浮点值, 则返回相除的浮点余数。</span><span class="sxs-lookup"><span data-stu-id="da582-124">If either `number1` or `number2` is a floating-point value, the floating-point remainder of the division is returned.</span></span> <span data-ttu-id="da582-125">结果的数据类型是最小的数据类型, 该数据类型可以包含与`number1`和`number2`的数据类型相除所得的所有可能值。</span><span class="sxs-lookup"><span data-stu-id="da582-125">The data type of the result is the smallest data type that can hold all possible values that result from division with the data types of `number1` and `number2`.</span></span>

 <span data-ttu-id="da582-126">如果`number1` 或`number2`的计算结果不为[空](../../../visual-basic/language-reference/nothing.md), 则将其视为零。</span><span class="sxs-lookup"><span data-stu-id="da582-126">If `number1` or `number2` evaluates to [Nothing](../../../visual-basic/language-reference/nothing.md), it is treated as zero.</span></span>

 <span data-ttu-id="da582-127">相关运算符包括:</span><span class="sxs-lookup"><span data-stu-id="da582-127">Related operators include the following:</span></span>

- <span data-ttu-id="da582-128">[\ 运算符 (Visual Basic)](../../../visual-basic/language-reference/operators/integer-division-operator.md)返回相除的整数商。</span><span class="sxs-lookup"><span data-stu-id="da582-128">The [\ Operator (Visual Basic)](../../../visual-basic/language-reference/operators/integer-division-operator.md) returns the integer quotient of a division.</span></span> <span data-ttu-id="da582-129">例如, 表达式`14 \ 4`的计算结果为3。</span><span class="sxs-lookup"><span data-stu-id="da582-129">For example, the expression `14 \ 4` evaluates to 3.</span></span>

- <span data-ttu-id="da582-130">[/运算符 (Visual Basic)](../../../visual-basic/language-reference/operators/floating-point-division-operator.md)以浮点数的形式返回所有商, 包括余数。</span><span class="sxs-lookup"><span data-stu-id="da582-130">The [/ Operator (Visual Basic)](../../../visual-basic/language-reference/operators/floating-point-division-operator.md) returns the full quotient, including the remainder, as a floating-point number.</span></span> <span data-ttu-id="da582-131">例如, 表达式`14 / 4`的计算结果为3.5。</span><span class="sxs-lookup"><span data-stu-id="da582-131">For example, the expression `14 / 4` evaluates to 3.5.</span></span>

## <a name="attempted-division-by-zero"></a><span data-ttu-id="da582-132">尝试被零除</span><span class="sxs-lookup"><span data-stu-id="da582-132">Attempted division by zero</span></span>
 <span data-ttu-id="da582-133">如果`number2`计算结果为零, 则`Mod`运算符的行为取决于操作数的数据类型:</span><span class="sxs-lookup"><span data-stu-id="da582-133">If `number2` evaluates to zero, the behavior of the `Mod` operator depends on the data type of the operands:</span></span>
 - <span data-ttu-id="da582-134"><xref:System.DivideByZeroException>如果在编译时`number2`无法确定, 则整数除法会引发异常, 并在编译时计算结果为零`number2`时生成编译时错误`BC30542    Division by zero occurred while evaluating this expression` 。</span><span class="sxs-lookup"><span data-stu-id="da582-134">An integral division throws a <xref:System.DivideByZeroException> exception if `number2` cannot be determined in compile-time and generates a compile-time error `BC30542    Division by zero occurred while evaluating this expression` if `number2` is evaluated to zero at compile-time.</span></span>
 - <span data-ttu-id="da582-135">浮点除法返回<xref:System.Double.NaN?displayProperty=nameWithType>。</span><span class="sxs-lookup"><span data-stu-id="da582-135">A floating-point division returns <xref:System.Double.NaN?displayProperty=nameWithType>.</span></span>

## <a name="equivalent-formula"></a><span data-ttu-id="da582-136">等效公式</span><span class="sxs-lookup"><span data-stu-id="da582-136">Equivalent formula</span></span>
 <span data-ttu-id="da582-137">表达式`a Mod b`等效于以下公式之一:</span><span class="sxs-lookup"><span data-stu-id="da582-137">The expression `a Mod b` is equivalent to either of the following formulas:</span></span>

 `a - (b * (a \ b))`

 `a - (b * Fix(a / b))`

## <a name="floating-point-imprecision"></a><span data-ttu-id="da582-138">浮点不精确性</span><span class="sxs-lookup"><span data-stu-id="da582-138">Floating-point imprecision</span></span>
 <span data-ttu-id="da582-139">使用浮点数时, 请记住, 内存中不一定有精确的十进制表示形式。</span><span class="sxs-lookup"><span data-stu-id="da582-139">When you work with floating-point numbers, remember that they do not always have a precise decimal representation in memory.</span></span> <span data-ttu-id="da582-140">这可能会导致某些操作产生意外结果, 如值比较和`Mod`运算符。</span><span class="sxs-lookup"><span data-stu-id="da582-140">This can lead to unexpected results from certain operations, such as value comparison and the `Mod` operator.</span></span> <span data-ttu-id="da582-141">有关详细信息, 请参阅[数据类型疑难解答](../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md)。</span><span class="sxs-lookup"><span data-stu-id="da582-141">For more information, see [Troubleshooting Data Types](../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md).</span></span>

## <a name="overloading"></a><span data-ttu-id="da582-142">重载</span><span class="sxs-lookup"><span data-stu-id="da582-142">Overloading</span></span>
 <span data-ttu-id="da582-143">运算符可以重载, 这意味着类或结构可以重新定义它的行为。 `Mod`</span><span class="sxs-lookup"><span data-stu-id="da582-143">The `Mod` operator can be *overloaded*, which means that a class or structure can redefine its behavior.</span></span> <span data-ttu-id="da582-144">如果你的代码`Mod`应用于包含此类重载的类或结构的实例, 请确保了解其重新定义的行为。</span><span class="sxs-lookup"><span data-stu-id="da582-144">If your code applies `Mod` to an instance of a class or structure that includes such an overload, be sure you understand its redefined behavior.</span></span> <span data-ttu-id="da582-145">有关详细信息，请参阅 [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md)。</span><span class="sxs-lookup"><span data-stu-id="da582-145">For more information, see [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span></span>

## <a name="example"></a><span data-ttu-id="da582-146">示例</span><span class="sxs-lookup"><span data-stu-id="da582-146">Example</span></span>
 <span data-ttu-id="da582-147">下面的示例使用`Mod`运算符将两个数字相除, 仅返回余数。</span><span class="sxs-lookup"><span data-stu-id="da582-147">The following example uses the `Mod` operator to divide two numbers and return only the remainder.</span></span> <span data-ttu-id="da582-148">如果其中一个数字为浮点数, 则结果为一个表示余数的浮点数。</span><span class="sxs-lookup"><span data-stu-id="da582-148">If either number is a floating-point number, the result is a floating-point number that represents the remainder.</span></span>

 [!code-vb[VbVbalrOperators#31](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#31)]

## <a name="example"></a><span data-ttu-id="da582-149">示例</span><span class="sxs-lookup"><span data-stu-id="da582-149">Example</span></span>
 <span data-ttu-id="da582-150">下面的示例演示了浮点操作数的潜在不精确性。</span><span class="sxs-lookup"><span data-stu-id="da582-150">The following example demonstrates the potential imprecision of floating-point operands.</span></span> <span data-ttu-id="da582-151">在第一个语句中, 操作数为`Double`, 0.2 是一个无限重复的二进制小数, 其存储值为0.20000000000000001。</span><span class="sxs-lookup"><span data-stu-id="da582-151">In the first statement, the operands are `Double`, and 0.2 is an infinitely repeating binary fraction with a stored value of 0.20000000000000001.</span></span> <span data-ttu-id="da582-152">在第二个语句中, 文本类型`D`字符强制两个`Decimal`操作数为, 0.2 具有精确的表示形式。</span><span class="sxs-lookup"><span data-stu-id="da582-152">In the second statement, the literal type character `D` forces both operands to `Decimal`, and 0.2 has a precise representation.</span></span>

 [!code-vb[VbVbalrOperators#32](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#32)]

## <a name="see-also"></a><span data-ttu-id="da582-153">请参阅</span><span class="sxs-lookup"><span data-stu-id="da582-153">See also</span></span>

- <xref:Microsoft.VisualBasic.Conversion.Int%2A>
- <xref:Microsoft.VisualBasic.Conversion.Fix%2A>
- [<span data-ttu-id="da582-154">算术运算符</span><span class="sxs-lookup"><span data-stu-id="da582-154">Arithmetic Operators</span></span>](../../../visual-basic/language-reference/operators/arithmetic-operators.md)
- [<span data-ttu-id="da582-155">Visual Basic 中的运算符优先级</span><span class="sxs-lookup"><span data-stu-id="da582-155">Operator Precedence in Visual Basic</span></span>](../../../visual-basic/language-reference/operators/operator-precedence.md)
- [<span data-ttu-id="da582-156">按功能列出的运算符</span><span class="sxs-lookup"><span data-stu-id="da582-156">Operators Listed by Functionality</span></span>](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)
- [<span data-ttu-id="da582-157">数据类型疑难解答</span><span class="sxs-lookup"><span data-stu-id="da582-157">Troubleshooting Data Types</span></span>](../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md)
- [<span data-ttu-id="da582-158">Visual Basic 中的算术运算符</span><span class="sxs-lookup"><span data-stu-id="da582-158">Arithmetic Operators in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/operators-and-expressions/arithmetic-operators.md)
- [<span data-ttu-id="da582-159">\ 运算符 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="da582-159">\ Operator (Visual Basic)</span></span>](../../../visual-basic/language-reference/operators/integer-division-operator.md)
