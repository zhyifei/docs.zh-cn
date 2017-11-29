---
title: "/ 运算符 (Visual Basic)"
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords: vb./
helpviewer_keywords:
- division operator [Visual Basic], floating point
- floating-point numbers [Visual Basic], division operator
- slash (/) operator
- zero, division by zero
- operators [Visual Basic], arithmetic
- arithmetic operators [Visual Basic], division
- division [Visual Basic], by zero
- operators [Visual Basic], division
- division operator [Visual Basic], syntax
- / operator [Visual Basic]
- math operators [Visual Basic]
ms.assetid: 335e97f2-c434-439e-9064-76973a051101
caps.latest.revision: "18"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 2f221e863725b9aeb0b3fa3219b3a881541e2be0
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="-operator-visual-basic"></a><span data-ttu-id="16051-102">/ 运算符 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="16051-102">/ Operator (Visual Basic)</span></span>
<span data-ttu-id="16051-103">使两个数字相除，返回浮点结果。</span><span class="sxs-lookup"><span data-stu-id="16051-103">Divides two numbers and returns a floating-point result.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="16051-104">语法</span><span class="sxs-lookup"><span data-stu-id="16051-104">Syntax</span></span>  
  
```  
expression1 / expression2  
```  
  
## <a name="parts"></a><span data-ttu-id="16051-105">部件</span><span class="sxs-lookup"><span data-stu-id="16051-105">Parts</span></span>  
 `expression1`  
 <span data-ttu-id="16051-106">必需。</span><span class="sxs-lookup"><span data-stu-id="16051-106">Required.</span></span> <span data-ttu-id="16051-107">任何数值表达式。</span><span class="sxs-lookup"><span data-stu-id="16051-107">Any numeric expression.</span></span>  
  
 `expression2`  
 <span data-ttu-id="16051-108">必需。</span><span class="sxs-lookup"><span data-stu-id="16051-108">Required.</span></span> <span data-ttu-id="16051-109">任何数值表达式。</span><span class="sxs-lookup"><span data-stu-id="16051-109">Any numeric expression.</span></span>  
  
## <a name="supported-types"></a><span data-ttu-id="16051-110">支持的类型</span><span class="sxs-lookup"><span data-stu-id="16051-110">Supported Types</span></span>  
 <span data-ttu-id="16051-111">所有数值类型，包括未签名和浮点类型和`Decimal`。</span><span class="sxs-lookup"><span data-stu-id="16051-111">All numeric types, including the unsigned and floating-point types and `Decimal`.</span></span>  
  
## <a name="result"></a><span data-ttu-id="16051-112">结果</span><span class="sxs-lookup"><span data-stu-id="16051-112">Result</span></span>  
 <span data-ttu-id="16051-113">结果为完整的商`expression1`除以`expression2`，包括所有余数。</span><span class="sxs-lookup"><span data-stu-id="16051-113">The result is the full quotient of `expression1` divided by `expression2`, including any remainder.</span></span>  
  
 <span data-ttu-id="16051-114">[\ 运算符 (Visual Basic)](../../../visual-basic/language-reference/operators/integer-division-operator.md)返回的整数的商，这会导致断开其余部分。</span><span class="sxs-lookup"><span data-stu-id="16051-114">The [\ Operator (Visual Basic)](../../../visual-basic/language-reference/operators/integer-division-operator.md) returns the integer quotient, which drops the remainder.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="16051-115">备注</span><span class="sxs-lookup"><span data-stu-id="16051-115">Remarks</span></span>  
 <span data-ttu-id="16051-116">结果的数据类型取决于操作数的类型。</span><span class="sxs-lookup"><span data-stu-id="16051-116">The data type of the result depends on the types of the operands.</span></span> <span data-ttu-id="16051-117">下表显示如何确定结果的数据类型。</span><span class="sxs-lookup"><span data-stu-id="16051-117">The following table shows how the data type of the result is determined.</span></span>  
  
|<span data-ttu-id="16051-118">操作数数据类型</span><span class="sxs-lookup"><span data-stu-id="16051-118">Operand data types</span></span>|<span data-ttu-id="16051-119">结果数据类型</span><span class="sxs-lookup"><span data-stu-id="16051-119">Result data type</span></span>|  
|------------------------|----------------------|  
|<span data-ttu-id="16051-120">两个表达式均整数数据类型 ([SByte](../../../visual-basic/language-reference/data-types/sbyte-data-type.md)，[字节](../../../visual-basic/language-reference/data-types/byte-data-type.md)，[短](../../../visual-basic/language-reference/data-types/short-data-type.md)， [UShort](../../../visual-basic/language-reference/data-types/ushort-data-type.md)，[整数](../../../visual-basic/language-reference/data-types/integer-data-type.md)，[UInteger](../../../visual-basic/language-reference/data-types/uinteger-data-type.md)，[长](../../../visual-basic/language-reference/data-types/long-data-type.md)， [ULong](../../../visual-basic/language-reference/data-types/ulong-data-type.md))</span><span class="sxs-lookup"><span data-stu-id="16051-120">Both expressions are integral data types ([SByte](../../../visual-basic/language-reference/data-types/sbyte-data-type.md), [Byte](../../../visual-basic/language-reference/data-types/byte-data-type.md), [Short](../../../visual-basic/language-reference/data-types/short-data-type.md), [UShort](../../../visual-basic/language-reference/data-types/ushort-data-type.md), [Integer](../../../visual-basic/language-reference/data-types/integer-data-type.md), [UInteger](../../../visual-basic/language-reference/data-types/uinteger-data-type.md), [Long](../../../visual-basic/language-reference/data-types/long-data-type.md), [ULong](../../../visual-basic/language-reference/data-types/ulong-data-type.md))</span></span>|`Double`|  
|<span data-ttu-id="16051-121">一个表达式是[单个](../../../visual-basic/language-reference/data-types/single-data-type.md)数据类型和其他不是[Double](../../../visual-basic/language-reference/data-types/double-data-type.md)</span><span class="sxs-lookup"><span data-stu-id="16051-121">One expression is a [Single](../../../visual-basic/language-reference/data-types/single-data-type.md) data type and the other is not a [Double](../../../visual-basic/language-reference/data-types/double-data-type.md)</span></span>|`Single`|  
|<span data-ttu-id="16051-122">一个表达式是[十进制](../../../visual-basic/language-reference/data-types/decimal-data-type.md)数据类型和其他不是[单个](../../../visual-basic/language-reference/data-types/single-data-type.md)或[Double](../../../visual-basic/language-reference/data-types/double-data-type.md)</span><span class="sxs-lookup"><span data-stu-id="16051-122">One expression is a [Decimal](../../../visual-basic/language-reference/data-types/decimal-data-type.md) data type and the other is not a [Single](../../../visual-basic/language-reference/data-types/single-data-type.md) or a [Double](../../../visual-basic/language-reference/data-types/double-data-type.md)</span></span>|`Decimal`|  
|<span data-ttu-id="16051-123">其中任何一个表达式是[Double](../../../visual-basic/language-reference/data-types/double-data-type.md)数据类型</span><span class="sxs-lookup"><span data-stu-id="16051-123">Either expression is a [Double](../../../visual-basic/language-reference/data-types/double-data-type.md) data type</span></span>|`Double`|  
  
 <span data-ttu-id="16051-124">执行除法运算之前，任何整型的数值表达式都将加宽到`Double`。</span><span class="sxs-lookup"><span data-stu-id="16051-124">Before division is performed, any integral numeric expressions are widened to `Double`.</span></span> <span data-ttu-id="16051-125">如果你将结果赋给整型数据类型时，Visual Basic 将尝试将转换的结果`Double`为该类型。</span><span class="sxs-lookup"><span data-stu-id="16051-125">If you assign the result to an integral data type, Visual Basic attempts to convert the result from `Double` to that type.</span></span> <span data-ttu-id="16051-126">如果结果不符合该类型，这可以引发异常。</span><span class="sxs-lookup"><span data-stu-id="16051-126">This can throw an exception if the result does not fit in that type.</span></span> <span data-ttu-id="16051-127">具体而言，此帮助页上看到"尝试用零作除数"。</span><span class="sxs-lookup"><span data-stu-id="16051-127">In particular, see "Attempted Division by Zero" on this Help page.</span></span>  
  
 <span data-ttu-id="16051-128">如果`expression1`或`expression2`计算结果为[执行任何操作](../../../visual-basic/language-reference/nothing.md)，它将被视为零。</span><span class="sxs-lookup"><span data-stu-id="16051-128">If `expression1` or `expression2` evaluates to [Nothing](../../../visual-basic/language-reference/nothing.md), it is treated as zero.</span></span>  
  
## <a name="attempted-division-by-zero"></a><span data-ttu-id="16051-129">尝试的除数为零</span><span class="sxs-lookup"><span data-stu-id="16051-129">Attempted Division by Zero</span></span>  
 <span data-ttu-id="16051-130">如果`expression2`计算结果为零，`/`运算符的操作数数据类型不同的行为有所不同。</span><span class="sxs-lookup"><span data-stu-id="16051-130">If `expression2` evaluates to zero, the `/` operator behaves differently for different operand data types.</span></span> <span data-ttu-id="16051-131">下表显示可能的行为。</span><span class="sxs-lookup"><span data-stu-id="16051-131">The following table shows the possible behaviors.</span></span>  
  
|<span data-ttu-id="16051-132">操作数数据类型</span><span class="sxs-lookup"><span data-stu-id="16051-132">Operand data types</span></span>|<span data-ttu-id="16051-133">行为如果`expression2`为零</span><span class="sxs-lookup"><span data-stu-id="16051-133">Behavior if `expression2` is zero</span></span>|  
|------------------------|---------------------------------------|  
|<span data-ttu-id="16051-134">浮点 (`Single`或`Double`)</span><span class="sxs-lookup"><span data-stu-id="16051-134">Floating-point (`Single` or `Double`)</span></span>|<span data-ttu-id="16051-135">返回无穷大 (<xref:System.Double.PositiveInfinity>或<xref:System.Double.NegativeInfinity>)，或<xref:System.Double.NaN>（而不是数字） 如果`expression1`也为零</span><span class="sxs-lookup"><span data-stu-id="16051-135">Returns infinity (<xref:System.Double.PositiveInfinity> or <xref:System.Double.NegativeInfinity>), or <xref:System.Double.NaN> (not a number) if `expression1` is also zero</span></span>|  
|`Decimal`|<span data-ttu-id="16051-136">引发<xref:System.DivideByZeroException></span><span class="sxs-lookup"><span data-stu-id="16051-136">Throws <xref:System.DivideByZeroException></span></span>|  
|<span data-ttu-id="16051-137">整数 （有符号或无符号）</span><span class="sxs-lookup"><span data-stu-id="16051-137">Integral (signed or unsigned)</span></span>|<span data-ttu-id="16051-138">尝试转换回整数类型会引发<xref:System.OverflowException>因为整数类型不能接受<xref:System.Double.PositiveInfinity>， <xref:System.Double.NegativeInfinity>，或<xref:System.Double.NaN></span><span class="sxs-lookup"><span data-stu-id="16051-138">Attempted conversion back to integral type throws <xref:System.OverflowException> because integral types cannot accept <xref:System.Double.PositiveInfinity>, <xref:System.Double.NegativeInfinity>, or <xref:System.Double.NaN></span></span>|  
  
> [!NOTE]
>  <span data-ttu-id="16051-139">`/`运算符可以被*重载*，这意味着，一个类或结构可以重新定义其行为时，操作数的类或结构的类型。</span><span class="sxs-lookup"><span data-stu-id="16051-139">The `/` operator can be *overloaded*, which means that a class or structure can redefine its behavior when an operand has the type of that class or structure.</span></span> <span data-ttu-id="16051-140">如果你的代码使用此运算符对这样的类或结构，请确保你了解其重新定义的行为。</span><span class="sxs-lookup"><span data-stu-id="16051-140">If your code uses this operator on such a class or structure, be sure you understand its redefined behavior.</span></span> <span data-ttu-id="16051-141">有关详细信息，请参阅[运算符过程](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md)。</span><span class="sxs-lookup"><span data-stu-id="16051-141">For more information, see [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="16051-142">示例</span><span class="sxs-lookup"><span data-stu-id="16051-142">Example</span></span>  
 <span data-ttu-id="16051-143">此示例使用`/`执行浮点除法运算的运算符。</span><span class="sxs-lookup"><span data-stu-id="16051-143">This example uses the `/` operator to perform floating-point division.</span></span> <span data-ttu-id="16051-144">结果是两个操作数的商。</span><span class="sxs-lookup"><span data-stu-id="16051-144">The result is the quotient of the two operands.</span></span>  
  
 [!code-vb[VbVbalrOperators#16](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/floating-point-division-operator_1.vb)]  
  
 <span data-ttu-id="16051-145">在前面的示例表达式返回 2.5 和 3.333333 的值。</span><span class="sxs-lookup"><span data-stu-id="16051-145">The expressions in the preceding example return values of 2.5 and 3.333333.</span></span> <span data-ttu-id="16051-146">请注意结果始终是浮点 (`Double`)，即使这两个操作数都是整数常量。</span><span class="sxs-lookup"><span data-stu-id="16051-146">Note that the result is always floating-point (`Double`), even though both operands are integer constants.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="16051-147">另请参阅</span><span class="sxs-lookup"><span data-stu-id="16051-147">See Also</span></span>  
 [<span data-ttu-id="16051-148">/ = 运算符 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="16051-148">/= Operator (Visual Basic)</span></span>](../../../visual-basic/language-reference/operators/floating-point-division-assignment-operator.md)  
 [<span data-ttu-id="16051-149">\ 运算符 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="16051-149">\ Operator (Visual Basic)</span></span>](../../../visual-basic/language-reference/operators/integer-division-operator.md)  
 [<span data-ttu-id="16051-150">运算符结果的数据类型</span><span class="sxs-lookup"><span data-stu-id="16051-150">Data Types of Operator Results</span></span>](../../../visual-basic/language-reference/operators/data-types-of-operator-results.md)  
 [<span data-ttu-id="16051-151">算术运算符</span><span class="sxs-lookup"><span data-stu-id="16051-151">Arithmetic Operators</span></span>](../../../visual-basic/language-reference/operators/arithmetic-operators.md)  
 [<span data-ttu-id="16051-152">Visual Basic 中的运算符优先级</span><span class="sxs-lookup"><span data-stu-id="16051-152">Operator Precedence in Visual Basic</span></span>](../../../visual-basic/language-reference/operators/operator-precedence.md)  
 [<span data-ttu-id="16051-153">按功能列出的运算符</span><span class="sxs-lookup"><span data-stu-id="16051-153">Operators Listed by Functionality</span></span>](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)  
 [<span data-ttu-id="16051-154">在 Visual Basic 中的算术运算符</span><span class="sxs-lookup"><span data-stu-id="16051-154">Arithmetic Operators in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/operators-and-expressions/arithmetic-operators.md)
