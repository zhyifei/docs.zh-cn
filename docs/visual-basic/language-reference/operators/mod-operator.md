---
title: "Mod 运算符 (Visual Basic)"
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords: vb.Mod
helpviewer_keywords:
- remainder (Mod operator)
- division operator [Visual Basic], Mod operator
- modulus operator [Visual Basic], Visual Basic
- Mod operator [Visual Basic]
- operators [Visual Basic], division
- arithmetic operators [Visual Basic], Mod
- math operators [Visual Basic]
ms.assetid: 6ff7e40e-cec8-4c77-bff6-8ddd2791c25b
caps.latest.revision: "22"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 5464b57c993e5703c09529b527a7bc714e045870
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="mod-operator-visual-basic"></a><span data-ttu-id="0d8ea-102">Mod 运算符 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="0d8ea-102">Mod Operator (Visual Basic)</span></span>
<span data-ttu-id="0d8ea-103">使两个数字相除，仅返回余数。</span><span class="sxs-lookup"><span data-stu-id="0d8ea-103">Divides two numbers and returns only the remainder.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0d8ea-104">语法</span><span class="sxs-lookup"><span data-stu-id="0d8ea-104">Syntax</span></span>  
  
```  
number1 Mod number2  
```  
  
## <a name="parts"></a><span data-ttu-id="0d8ea-105">部件</span><span class="sxs-lookup"><span data-stu-id="0d8ea-105">Parts</span></span>  
 `number1`  
 <span data-ttu-id="0d8ea-106">必需。</span><span class="sxs-lookup"><span data-stu-id="0d8ea-106">Required.</span></span> <span data-ttu-id="0d8ea-107">任何数值表达式。</span><span class="sxs-lookup"><span data-stu-id="0d8ea-107">Any numeric expression.</span></span>  
  
 `number2`  
 <span data-ttu-id="0d8ea-108">必需。</span><span class="sxs-lookup"><span data-stu-id="0d8ea-108">Required.</span></span> <span data-ttu-id="0d8ea-109">任何数值表达式。</span><span class="sxs-lookup"><span data-stu-id="0d8ea-109">Any numeric expression.</span></span>  
  
## <a name="supported-types"></a><span data-ttu-id="0d8ea-110">支持的类型</span><span class="sxs-lookup"><span data-stu-id="0d8ea-110">Supported Types</span></span>  
 <span data-ttu-id="0d8ea-111">所有数值类型。</span><span class="sxs-lookup"><span data-stu-id="0d8ea-111">All numeric types.</span></span> <span data-ttu-id="0d8ea-112">这包括的无符号和浮点类型和`Decimal`。</span><span class="sxs-lookup"><span data-stu-id="0d8ea-112">This includes the unsigned and floating-point types and `Decimal`.</span></span>  
  
## <a name="result"></a><span data-ttu-id="0d8ea-113">结果</span><span class="sxs-lookup"><span data-stu-id="0d8ea-113">Result</span></span>  
 <span data-ttu-id="0d8ea-114">结果是后的余数`number1`除以`number2`。</span><span class="sxs-lookup"><span data-stu-id="0d8ea-114">The result is the remainder after `number1` is divided by `number2`.</span></span> <span data-ttu-id="0d8ea-115">例如，表达式`14 Mod 4`计算结果为 2。</span><span class="sxs-lookup"><span data-stu-id="0d8ea-115">For example, the expression `14 Mod 4` evaluates to 2.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="0d8ea-116">备注</span><span class="sxs-lookup"><span data-stu-id="0d8ea-116">Remarks</span></span>  
 <span data-ttu-id="0d8ea-117">如果任一`number1`或`number2`为浮点值，则返回除法运算的浮点余数。</span><span class="sxs-lookup"><span data-stu-id="0d8ea-117">If either `number1` or `number2` is a floating-point value, the floating-point remainder of the division is returned.</span></span> <span data-ttu-id="0d8ea-118">结果的数据类型是可保存的数据类型的除法运算的结果的所有可能值的最小数据类型`number1`和`number2`。</span><span class="sxs-lookup"><span data-stu-id="0d8ea-118">The data type of the result is the smallest data type that can hold all possible values that result from division with the data types of `number1` and `number2`.</span></span>  
  
 <span data-ttu-id="0d8ea-119">如果`number1`或`number2`计算结果为[执行任何操作](../../../visual-basic/language-reference/nothing.md)，它将被视为零。</span><span class="sxs-lookup"><span data-stu-id="0d8ea-119">If `number1` or `number2` evaluates to [Nothing](../../../visual-basic/language-reference/nothing.md), it is treated as zero.</span></span>  
  
 <span data-ttu-id="0d8ea-120">相关的运算符如下所示：</span><span class="sxs-lookup"><span data-stu-id="0d8ea-120">Related operators include the following:</span></span>  
  
-   <span data-ttu-id="0d8ea-121">[\ 运算符 (Visual Basic)](../../../visual-basic/language-reference/operators/integer-division-operator.md)返回除法结果的整数商。</span><span class="sxs-lookup"><span data-stu-id="0d8ea-121">The [\ Operator (Visual Basic)](../../../visual-basic/language-reference/operators/integer-division-operator.md) returns the integer quotient of a division.</span></span> <span data-ttu-id="0d8ea-122">例如，表达式`14 \ 4`计算结果为 3。</span><span class="sxs-lookup"><span data-stu-id="0d8ea-122">For example, the expression `14 \ 4` evaluates to 3.</span></span>  
  
-   <span data-ttu-id="0d8ea-123">[/ 运算符 (Visual Basic)](../../../visual-basic/language-reference/operators/floating-point-division-operator.md)返回完整的商，包括其余部分中的，作为浮点数。</span><span class="sxs-lookup"><span data-stu-id="0d8ea-123">The [/ Operator (Visual Basic)](../../../visual-basic/language-reference/operators/floating-point-division-operator.md) returns the full quotient, including the remainder, as a floating-point number.</span></span> <span data-ttu-id="0d8ea-124">例如，表达式`14 / 4`计算结果为 3.5。</span><span class="sxs-lookup"><span data-stu-id="0d8ea-124">For example, the expression `14 / 4` evaluates to 3.5.</span></span>  
  
## <a name="attempted-division-by-zero"></a><span data-ttu-id="0d8ea-125">尝试的除数为零</span><span class="sxs-lookup"><span data-stu-id="0d8ea-125">Attempted Division by Zero</span></span>  
 <span data-ttu-id="0d8ea-126">如果`number2`的计算结果为零的行为`Mod`运算符取决于操作数的数据类型。</span><span class="sxs-lookup"><span data-stu-id="0d8ea-126">If `number2` evaluates to zero, the behavior of the `Mod` operator depends on the data type of the operands.</span></span> <span data-ttu-id="0d8ea-127">整数除法引发<xref:System.DivideByZeroException>异常。</span><span class="sxs-lookup"><span data-stu-id="0d8ea-127">An integral division throws a <xref:System.DivideByZeroException> exception.</span></span> <span data-ttu-id="0d8ea-128">浮点除法运算返回<xref:System.Double.NaN>。</span><span class="sxs-lookup"><span data-stu-id="0d8ea-128">A floating-point division returns <xref:System.Double.NaN>.</span></span>  
  
## <a name="equivalent-formula"></a><span data-ttu-id="0d8ea-129">等效的公式</span><span class="sxs-lookup"><span data-stu-id="0d8ea-129">Equivalent Formula</span></span>  
 <span data-ttu-id="0d8ea-130">表达式`a Mod b`等效于任一以下公式：</span><span class="sxs-lookup"><span data-stu-id="0d8ea-130">The expression `a Mod b` is equivalent to either of the following formulas:</span></span>  
  
 `a - (b * (a \ b))`  
  
 `a - (b * Fix(a / b))`  
  
## <a name="floating-point-imprecision"></a><span data-ttu-id="0d8ea-131">浮点不精确性</span><span class="sxs-lookup"><span data-stu-id="0d8ea-131">Floating-Point Imprecision</span></span>  
 <span data-ttu-id="0d8ea-132">在使用浮点数，请记得在内存中不始终具有精确的表示形式。</span><span class="sxs-lookup"><span data-stu-id="0d8ea-132">When you work with floating-point numbers, remember that they do not always have a precise representation in memory.</span></span> <span data-ttu-id="0d8ea-133">这可能导致意外的结果从某些操作，如值比较和`Mod`运算符。</span><span class="sxs-lookup"><span data-stu-id="0d8ea-133">This could lead to unexpected results from certain operations, such as value comparison and the `Mod` operator.</span></span> <span data-ttu-id="0d8ea-134">有关详细信息，请参阅[故障排除数据类型](../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md)。</span><span class="sxs-lookup"><span data-stu-id="0d8ea-134">For more information, see [Troubleshooting Data Types](../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md).</span></span>  
  
## <a name="overloading"></a><span data-ttu-id="0d8ea-135">重载</span><span class="sxs-lookup"><span data-stu-id="0d8ea-135">Overloading</span></span>  
 <span data-ttu-id="0d8ea-136">`Mod`运算符可以被*重载*，这意味着某个类或结构可以重新定义其行为。</span><span class="sxs-lookup"><span data-stu-id="0d8ea-136">The `Mod` operator can be *overloaded*, which means that a class or structure can redefine its behavior.</span></span> <span data-ttu-id="0d8ea-137">如果你的代码适用`Mod`到类或结构，其中包含此类重载的实例，请确保你已了解其重新定义的行为。</span><span class="sxs-lookup"><span data-stu-id="0d8ea-137">If your code applies `Mod` to an instance of a class or structure that includes such an overload, be sure you understand its redefined behavior.</span></span> <span data-ttu-id="0d8ea-138">有关详细信息，请参阅[运算符过程](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md)。</span><span class="sxs-lookup"><span data-stu-id="0d8ea-138">For more information, see [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="0d8ea-139">示例</span><span class="sxs-lookup"><span data-stu-id="0d8ea-139">Example</span></span>  
 <span data-ttu-id="0d8ea-140">下面的示例使用`Mod`运算符将两个数相除，并只返回余数。</span><span class="sxs-lookup"><span data-stu-id="0d8ea-140">The following example uses the `Mod` operator to divide two numbers and return only the remainder.</span></span> <span data-ttu-id="0d8ea-141">如果一个数是浮点数，结果将是一个表示余数的浮点数。</span><span class="sxs-lookup"><span data-stu-id="0d8ea-141">If either number is a floating-point number, the result is a floating-point number that represents the remainder.</span></span>  
  
 [!code-vb[VbVbalrOperators#31](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/mod-operator_1.vb)]  
  
## <a name="example"></a><span data-ttu-id="0d8ea-142">示例</span><span class="sxs-lookup"><span data-stu-id="0d8ea-142">Example</span></span>  
 <span data-ttu-id="0d8ea-143">下面的示例演示了潜在的浮点操作数不精确性。</span><span class="sxs-lookup"><span data-stu-id="0d8ea-143">The following example demonstrates the potential imprecision of floating-point operands.</span></span> <span data-ttu-id="0d8ea-144">在第一个语句中，操作数都是`Double`，和 0.2 是存储的值是为 0.20000000000000001 的无限期重复二进制小数。</span><span class="sxs-lookup"><span data-stu-id="0d8ea-144">In the first statement, the operands are `Double`, and 0.2 is an infinitely repeating binary fraction with a stored value of 0.20000000000000001.</span></span> <span data-ttu-id="0d8ea-145">在第二个语句中，文本类型字符`D`强制的两个操作数`Decimal`，，0.2 具有精确的表示形式。</span><span class="sxs-lookup"><span data-stu-id="0d8ea-145">In the second statement, the literal type character `D` forces both operands to `Decimal`, and 0.2 has a precise representation.</span></span>  
  
 [!code-vb[VbVbalrOperators#32](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/mod-operator_2.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="0d8ea-146">另请参阅</span><span class="sxs-lookup"><span data-stu-id="0d8ea-146">See Also</span></span>  
 <xref:Microsoft.VisualBasic.Conversion.Int%2A>  
 <xref:Microsoft.VisualBasic.Conversion.Fix%2A>  
 [<span data-ttu-id="0d8ea-147">算术运算符</span><span class="sxs-lookup"><span data-stu-id="0d8ea-147">Arithmetic Operators</span></span>](../../../visual-basic/language-reference/operators/arithmetic-operators.md)  
 [<span data-ttu-id="0d8ea-148">Visual Basic 中的运算符优先级</span><span class="sxs-lookup"><span data-stu-id="0d8ea-148">Operator Precedence in Visual Basic</span></span>](../../../visual-basic/language-reference/operators/operator-precedence.md)  
 [<span data-ttu-id="0d8ea-149">按功能列出的运算符</span><span class="sxs-lookup"><span data-stu-id="0d8ea-149">Operators Listed by Functionality</span></span>](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)  
 [<span data-ttu-id="0d8ea-150">数据类型疑难解答</span><span class="sxs-lookup"><span data-stu-id="0d8ea-150">Troubleshooting Data Types</span></span>](../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md)  
 [<span data-ttu-id="0d8ea-151">在 Visual Basic 中的算术运算符</span><span class="sxs-lookup"><span data-stu-id="0d8ea-151">Arithmetic Operators in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/operators-and-expressions/arithmetic-operators.md)  
 [<span data-ttu-id="0d8ea-152">\ 运算符 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="0d8ea-152">\ Operator (Visual Basic)</span></span>](../../../visual-basic/language-reference/operators/integer-division-operator.md)
