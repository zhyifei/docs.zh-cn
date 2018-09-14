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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 456c19fc8e28517a0662b58e338028e1c75cd8c8
ms.sourcegitcommit: ba5c189bf44d44204a3e8838e59ec378a62d82f3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/13/2018
ms.locfileid: "44756894"
---
# <a name="mod-operator-visual-basic"></a><span data-ttu-id="9bdd3-102">Mod 运算符 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="9bdd3-102">Mod operator (Visual Basic)</span></span>
<span data-ttu-id="9bdd3-103">使两个数字相除，仅返回余数。</span><span class="sxs-lookup"><span data-stu-id="9bdd3-103">Divides two numbers and returns only the remainder.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9bdd3-104">语法</span><span class="sxs-lookup"><span data-stu-id="9bdd3-104">Syntax</span></span>  
  
```  
number1 Mod number2  
```  
  
## <a name="parts"></a><span data-ttu-id="9bdd3-105">部件</span><span class="sxs-lookup"><span data-stu-id="9bdd3-105">Parts</span></span>  
 `number1`  
 <span data-ttu-id="9bdd3-106">必须的。</span><span class="sxs-lookup"><span data-stu-id="9bdd3-106">Required.</span></span> <span data-ttu-id="9bdd3-107">任何数值表达式。</span><span class="sxs-lookup"><span data-stu-id="9bdd3-107">Any numeric expression.</span></span>  
  
 `number2`  
 <span data-ttu-id="9bdd3-108">必须的。</span><span class="sxs-lookup"><span data-stu-id="9bdd3-108">Required.</span></span> <span data-ttu-id="9bdd3-109">任何数值表达式。</span><span class="sxs-lookup"><span data-stu-id="9bdd3-109">Any numeric expression.</span></span>  
  
## <a name="supported-types"></a><span data-ttu-id="9bdd3-110">支持的类型</span><span class="sxs-lookup"><span data-stu-id="9bdd3-110">Supported types</span></span>  
 <span data-ttu-id="9bdd3-111">所有数值类型。</span><span class="sxs-lookup"><span data-stu-id="9bdd3-111">All numeric types.</span></span> <span data-ttu-id="9bdd3-112">这包括未签名和浮点类型和`Decimal`。</span><span class="sxs-lookup"><span data-stu-id="9bdd3-112">This includes the unsigned and floating-point types and `Decimal`.</span></span>  
  
## <a name="result"></a><span data-ttu-id="9bdd3-113">结果</span><span class="sxs-lookup"><span data-stu-id="9bdd3-113">Result</span></span>

<span data-ttu-id="9bdd3-114">结果是后的余数`number1`除以`number2`。</span><span class="sxs-lookup"><span data-stu-id="9bdd3-114">The result is the remainder after `number1` is divided by `number2`.</span></span> <span data-ttu-id="9bdd3-115">例如，表达式`14 Mod 4`计算结果为 2。</span><span class="sxs-lookup"><span data-stu-id="9bdd3-115">For example, the expression `14 Mod 4` evaluates to 2.</span></span>  

> [!NOTE]
> <span data-ttu-id="9bdd3-116">没有之间的差异*余数*并*取模*在数学中，使用不同的结果为负数。</span><span class="sxs-lookup"><span data-stu-id="9bdd3-116">There is a difference between *remainder* and *modulus* in mathematics, with different results for negative numbers.</span></span> <span data-ttu-id="9bdd3-117">`Mod`运算符在 Visual Basic 中，.NET Framework`op_Modulus`运算符，并且基础[rem](<xref:System.Reflection.Emit.OpCodes.Rem>) IL 指令执行其余操作。</span><span class="sxs-lookup"><span data-stu-id="9bdd3-117">The `Mod` operator in Visual Basic, the .NET Framework `op_Modulus` operator, and the underlying [rem](<xref:System.Reflection.Emit.OpCodes.Rem>) IL instruction all perform a remainder operation.</span></span>

<span data-ttu-id="9bdd3-118">结果`Mod`操作将保留被除数，符号`number1`，因此它可以是正数或负数。</span><span class="sxs-lookup"><span data-stu-id="9bdd3-118">The result of a `Mod` operation retains the sign of the dividend, `number1`, and so it may be positive or negative.</span></span> <span data-ttu-id="9bdd3-119">结果始终处于范围内 (-`number2`， `number2`)、 排他。</span><span class="sxs-lookup"><span data-stu-id="9bdd3-119">The result is always in the range (-`number2`, `number2`), exclusive.</span></span> <span data-ttu-id="9bdd3-120">例如：</span><span class="sxs-lookup"><span data-stu-id="9bdd3-120">For example:</span></span>

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

## <a name="remarks"></a><span data-ttu-id="9bdd3-121">备注</span><span class="sxs-lookup"><span data-stu-id="9bdd3-121">Remarks</span></span>  
 <span data-ttu-id="9bdd3-122">如果任一`number1`或`number2`是浮点值，返回浮点除法运算的余数。</span><span class="sxs-lookup"><span data-stu-id="9bdd3-122">If either `number1` or `number2` is a floating-point value, the floating-point remainder of the division is returned.</span></span> <span data-ttu-id="9bdd3-123">结果的数据类型是可以容纳所有可能的值而导致的部门使用的数据类型的最小数据类型`number1`和`number2`。</span><span class="sxs-lookup"><span data-stu-id="9bdd3-123">The data type of the result is the smallest data type that can hold all possible values that result from division with the data types of `number1` and `number2`.</span></span>  
  
 <span data-ttu-id="9bdd3-124">如果`number1`或`number2`的计算结果为[Nothing](../../../visual-basic/language-reference/nothing.md)，它将被视为零。</span><span class="sxs-lookup"><span data-stu-id="9bdd3-124">If `number1` or `number2` evaluates to [Nothing](../../../visual-basic/language-reference/nothing.md), it is treated as zero.</span></span>  
  
 <span data-ttu-id="9bdd3-125">相关的运算符包括：</span><span class="sxs-lookup"><span data-stu-id="9bdd3-125">Related operators include the following:</span></span>  
  
-   <span data-ttu-id="9bdd3-126">[\ 运算符 (Visual Basic)](../../../visual-basic/language-reference/operators/integer-division-operator.md)返回整数除法运算的商。</span><span class="sxs-lookup"><span data-stu-id="9bdd3-126">The [\ Operator (Visual Basic)](../../../visual-basic/language-reference/operators/integer-division-operator.md) returns the integer quotient of a division.</span></span> <span data-ttu-id="9bdd3-127">例如，表达式`14 \ 4`的计算结果为 3。</span><span class="sxs-lookup"><span data-stu-id="9bdd3-127">For example, the expression `14 \ 4` evaluates to 3.</span></span>  
  
-   <span data-ttu-id="9bdd3-128">[/ 运算符 (Visual Basic)](../../../visual-basic/language-reference/operators/floating-point-division-operator.md)返回完整商，包括其余部分中的，作为浮点数。</span><span class="sxs-lookup"><span data-stu-id="9bdd3-128">The [/ Operator (Visual Basic)](../../../visual-basic/language-reference/operators/floating-point-division-operator.md) returns the full quotient, including the remainder, as a floating-point number.</span></span> <span data-ttu-id="9bdd3-129">例如，表达式`14 / 4`的计算结果为 3.5。</span><span class="sxs-lookup"><span data-stu-id="9bdd3-129">For example, the expression `14 / 4` evaluates to 3.5.</span></span>  
  
## <a name="attempted-division-by-zero"></a><span data-ttu-id="9bdd3-130">尝试的除数为零</span><span class="sxs-lookup"><span data-stu-id="9bdd3-130">Attempted division by zero</span></span>  
 <span data-ttu-id="9bdd3-131">如果`number2`的计算结果为零的行为`Mod`运算符取决于操作数的数据类型。</span><span class="sxs-lookup"><span data-stu-id="9bdd3-131">If `number2` evaluates to zero, the behavior of the `Mod` operator depends on the data type of the operands.</span></span> <span data-ttu-id="9bdd3-132">整数除法引发<xref:System.DivideByZeroException>异常。</span><span class="sxs-lookup"><span data-stu-id="9bdd3-132">An integral division throws a <xref:System.DivideByZeroException> exception.</span></span> <span data-ttu-id="9bdd3-133">浮点除法运算返回<xref:System.Double.NaN>。</span><span class="sxs-lookup"><span data-stu-id="9bdd3-133">A floating-point division returns <xref:System.Double.NaN>.</span></span>  
  
## <a name="equivalent-formula"></a><span data-ttu-id="9bdd3-134">等效公式</span><span class="sxs-lookup"><span data-stu-id="9bdd3-134">Equivalent formula</span></span>  
 <span data-ttu-id="9bdd3-135">表达式`a Mod b`等效于以下公式之一：</span><span class="sxs-lookup"><span data-stu-id="9bdd3-135">The expression `a Mod b` is equivalent to either of the following formulas:</span></span>  
  
 `a - (b * (a \ b))`  
  
 `a - (b * Fix(a / b))`  
  
## <a name="floating-point-imprecision"></a><span data-ttu-id="9bdd3-136">浮点不精确性</span><span class="sxs-lookup"><span data-stu-id="9bdd3-136">Floating-point imprecision</span></span>  
 <span data-ttu-id="9bdd3-137">当使用浮点数时，请记住在内存中不一定有精确的十进制表示形式。</span><span class="sxs-lookup"><span data-stu-id="9bdd3-137">When you work with floating-point numbers, remember that they do not always have a precise decimal representation in memory.</span></span> <span data-ttu-id="9bdd3-138">这可能会导致意外的结果从某些操作，如值比较和`Mod`运算符。</span><span class="sxs-lookup"><span data-stu-id="9bdd3-138">This can lead to unexpected results from certain operations, such as value comparison and the `Mod` operator.</span></span> <span data-ttu-id="9bdd3-139">有关详细信息，请参阅[故障排除数据类型](../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md)。</span><span class="sxs-lookup"><span data-stu-id="9bdd3-139">For more information, see [Troubleshooting Data Types](../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md).</span></span>  
  
## <a name="overloading"></a><span data-ttu-id="9bdd3-140">重载</span><span class="sxs-lookup"><span data-stu-id="9bdd3-140">Overloading</span></span>  
 <span data-ttu-id="9bdd3-141">`Mod`运算符可以被*重载*，这意味着类或结构可以重新定义其行为。</span><span class="sxs-lookup"><span data-stu-id="9bdd3-141">The `Mod` operator can be *overloaded*, which means that a class or structure can redefine its behavior.</span></span> <span data-ttu-id="9bdd3-142">如果你的代码适用`Mod`到类或结构，其中包含此类重载的实例，请确保了解其被重新定义的行为。</span><span class="sxs-lookup"><span data-stu-id="9bdd3-142">If your code applies `Mod` to an instance of a class or structure that includes such an overload, be sure you understand its redefined behavior.</span></span> <span data-ttu-id="9bdd3-143">有关详细信息，请参阅[运算符过程](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md)。</span><span class="sxs-lookup"><span data-stu-id="9bdd3-143">For more information, see [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="9bdd3-144">示例</span><span class="sxs-lookup"><span data-stu-id="9bdd3-144">Example</span></span>  
 <span data-ttu-id="9bdd3-145">下面的示例使用`Mod`运算符将两个数相除，并只返回余数。</span><span class="sxs-lookup"><span data-stu-id="9bdd3-145">The following example uses the `Mod` operator to divide two numbers and return only the remainder.</span></span> <span data-ttu-id="9bdd3-146">如果一个数是浮点数，结果是表示余数的浮点数。</span><span class="sxs-lookup"><span data-stu-id="9bdd3-146">If either number is a floating-point number, the result is a floating-point number that represents the remainder.</span></span>  
  
 [!code-vb[VbVbalrOperators#31](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/mod-operator_1.vb)]  
  
## <a name="example"></a><span data-ttu-id="9bdd3-147">示例</span><span class="sxs-lookup"><span data-stu-id="9bdd3-147">Example</span></span>  
 <span data-ttu-id="9bdd3-148">下面的示例演示可能不精确的浮点操作数。</span><span class="sxs-lookup"><span data-stu-id="9bdd3-148">The following example demonstrates the potential imprecision of floating-point operands.</span></span> <span data-ttu-id="9bdd3-149">在第一个语句中，操作数均为`Double`，0.2，存储的值是为 0.20000000000000001 的无限重复二进制小数。</span><span class="sxs-lookup"><span data-stu-id="9bdd3-149">In the first statement, the operands are `Double`, and 0.2 is an infinitely repeating binary fraction with a stored value of 0.20000000000000001.</span></span> <span data-ttu-id="9bdd3-150">在第二个语句中，文本类型字符`D`强制的两个操作数`Decimal`，，0.2 具有精确的表示形式。</span><span class="sxs-lookup"><span data-stu-id="9bdd3-150">In the second statement, the literal type character `D` forces both operands to `Decimal`, and 0.2 has a precise representation.</span></span>  
  
 [!code-vb[VbVbalrOperators#32](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/mod-operator_2.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="9bdd3-151">请参阅</span><span class="sxs-lookup"><span data-stu-id="9bdd3-151">See also</span></span>  
 <xref:Microsoft.VisualBasic.Conversion.Int%2A>  
 <xref:Microsoft.VisualBasic.Conversion.Fix%2A>  
 [<span data-ttu-id="9bdd3-152">算术运算符</span><span class="sxs-lookup"><span data-stu-id="9bdd3-152">Arithmetic Operators</span></span>](../../../visual-basic/language-reference/operators/arithmetic-operators.md)  
 [<span data-ttu-id="9bdd3-153">Visual Basic 中的运算符优先级</span><span class="sxs-lookup"><span data-stu-id="9bdd3-153">Operator Precedence in Visual Basic</span></span>](../../../visual-basic/language-reference/operators/operator-precedence.md)  
 [<span data-ttu-id="9bdd3-154">按功能列出的运算符</span><span class="sxs-lookup"><span data-stu-id="9bdd3-154">Operators Listed by Functionality</span></span>](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)  
 [<span data-ttu-id="9bdd3-155">数据类型疑难解答</span><span class="sxs-lookup"><span data-stu-id="9bdd3-155">Troubleshooting Data Types</span></span>](../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md)  
 [<span data-ttu-id="9bdd3-156">在 Visual Basic 中的算术运算符</span><span class="sxs-lookup"><span data-stu-id="9bdd3-156">Arithmetic Operators in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/operators-and-expressions/arithmetic-operators.md)  
 [<span data-ttu-id="9bdd3-157">\ 运算符 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="9bdd3-157">\ Operator (Visual Basic)</span></span>](../../../visual-basic/language-reference/operators/integer-division-operator.md)
