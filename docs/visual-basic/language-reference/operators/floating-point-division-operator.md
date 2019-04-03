---
title: / 运算符 (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb./
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
ms.openlocfilehash: af2316f92e2904eee1e8c046b34b8147e40cb513
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/02/2019
ms.locfileid: "58825061"
---
# <a name="-operator-visual-basic"></a><span data-ttu-id="05d89-102">/ 运算符 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="05d89-102">/ Operator (Visual Basic)</span></span>
<span data-ttu-id="05d89-103">使两个数字相除，返回浮点结果。</span><span class="sxs-lookup"><span data-stu-id="05d89-103">Divides two numbers and returns a floating-point result.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="05d89-104">语法</span><span class="sxs-lookup"><span data-stu-id="05d89-104">Syntax</span></span>  
  
```  
expression1 / expression2  
```  
  
## <a name="parts"></a><span data-ttu-id="05d89-105">部件</span><span class="sxs-lookup"><span data-stu-id="05d89-105">Parts</span></span>  
 `expression1`  
 <span data-ttu-id="05d89-106">必需。</span><span class="sxs-lookup"><span data-stu-id="05d89-106">Required.</span></span> <span data-ttu-id="05d89-107">任何数值表达式。</span><span class="sxs-lookup"><span data-stu-id="05d89-107">Any numeric expression.</span></span>  
  
 `expression2`  
 <span data-ttu-id="05d89-108">必需。</span><span class="sxs-lookup"><span data-stu-id="05d89-108">Required.</span></span> <span data-ttu-id="05d89-109">任何数值表达式。</span><span class="sxs-lookup"><span data-stu-id="05d89-109">Any numeric expression.</span></span>  
  
## <a name="supported-types"></a><span data-ttu-id="05d89-110">支持的类型</span><span class="sxs-lookup"><span data-stu-id="05d89-110">Supported Types</span></span>  
 <span data-ttu-id="05d89-111">所有数值类型，包括未签名和浮点类型和`Decimal`。</span><span class="sxs-lookup"><span data-stu-id="05d89-111">All numeric types, including the unsigned and floating-point types and `Decimal`.</span></span>  
  
## <a name="result"></a><span data-ttu-id="05d89-112">结果</span><span class="sxs-lookup"><span data-stu-id="05d89-112">Result</span></span>  
 <span data-ttu-id="05d89-113">结果是完整的商`expression1`除以`expression2`，包括任何余数。</span><span class="sxs-lookup"><span data-stu-id="05d89-113">The result is the full quotient of `expression1` divided by `expression2`, including any remainder.</span></span>  
  
 <span data-ttu-id="05d89-114">[\ 运算符 (Visual Basic)](../../../visual-basic/language-reference/operators/integer-division-operator.md)返回整数商，将删除其余部分。</span><span class="sxs-lookup"><span data-stu-id="05d89-114">The [\ Operator (Visual Basic)](../../../visual-basic/language-reference/operators/integer-division-operator.md) returns the integer quotient, which drops the remainder.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="05d89-115">备注</span><span class="sxs-lookup"><span data-stu-id="05d89-115">Remarks</span></span>  
 <span data-ttu-id="05d89-116">结果的数据类型取决于操作数的类型。</span><span class="sxs-lookup"><span data-stu-id="05d89-116">The data type of the result depends on the types of the operands.</span></span> <span data-ttu-id="05d89-117">下表显示了如何确定结果的数据类型。</span><span class="sxs-lookup"><span data-stu-id="05d89-117">The following table shows how the data type of the result is determined.</span></span>  
  
|<span data-ttu-id="05d89-118">操作数数据类型</span><span class="sxs-lookup"><span data-stu-id="05d89-118">Operand data types</span></span>|<span data-ttu-id="05d89-119">结果数据类型</span><span class="sxs-lookup"><span data-stu-id="05d89-119">Result data type</span></span>|  
|------------------------|----------------------|  
|<span data-ttu-id="05d89-120">这两个表达式是整数数据类型 ([SByte](../../../visual-basic/language-reference/data-types/sbyte-data-type.md)，[字节](../../../visual-basic/language-reference/data-types/byte-data-type.md)，[短](../../../visual-basic/language-reference/data-types/short-data-type.md)， [UShort](../../../visual-basic/language-reference/data-types/ushort-data-type.md)，[整数](../../../visual-basic/language-reference/data-types/integer-data-type.md)，[UInteger](../../../visual-basic/language-reference/data-types/uinteger-data-type.md)，[长](../../../visual-basic/language-reference/data-types/long-data-type.md)， [ULong](../../../visual-basic/language-reference/data-types/ulong-data-type.md))</span><span class="sxs-lookup"><span data-stu-id="05d89-120">Both expressions are integral data types ([SByte](../../../visual-basic/language-reference/data-types/sbyte-data-type.md), [Byte](../../../visual-basic/language-reference/data-types/byte-data-type.md), [Short](../../../visual-basic/language-reference/data-types/short-data-type.md), [UShort](../../../visual-basic/language-reference/data-types/ushort-data-type.md), [Integer](../../../visual-basic/language-reference/data-types/integer-data-type.md), [UInteger](../../../visual-basic/language-reference/data-types/uinteger-data-type.md), [Long](../../../visual-basic/language-reference/data-types/long-data-type.md), [ULong](../../../visual-basic/language-reference/data-types/ulong-data-type.md))</span></span>|`Double`|  
|<span data-ttu-id="05d89-121">一个表达式是[单个](../../../visual-basic/language-reference/data-types/single-data-type.md)数据类型和其他不是[双精度](../../../visual-basic/language-reference/data-types/double-data-type.md)</span><span class="sxs-lookup"><span data-stu-id="05d89-121">One expression is a [Single](../../../visual-basic/language-reference/data-types/single-data-type.md) data type and the other is not a [Double](../../../visual-basic/language-reference/data-types/double-data-type.md)</span></span>|`Single`|  
|<span data-ttu-id="05d89-122">一个表达式是[十进制](../../../visual-basic/language-reference/data-types/decimal-data-type.md)数据类型和其他不是[单个](../../../visual-basic/language-reference/data-types/single-data-type.md)或[双精度](../../../visual-basic/language-reference/data-types/double-data-type.md)</span><span class="sxs-lookup"><span data-stu-id="05d89-122">One expression is a [Decimal](../../../visual-basic/language-reference/data-types/decimal-data-type.md) data type and the other is not a [Single](../../../visual-basic/language-reference/data-types/single-data-type.md) or a [Double](../../../visual-basic/language-reference/data-types/double-data-type.md)</span></span>|`Decimal`|  
|<span data-ttu-id="05d89-123">其中任何一个表达式是[Double](../../../visual-basic/language-reference/data-types/double-data-type.md)数据类型</span><span class="sxs-lookup"><span data-stu-id="05d89-123">Either expression is a [Double](../../../visual-basic/language-reference/data-types/double-data-type.md) data type</span></span>|`Double`|  
  
 <span data-ttu-id="05d89-124">执行除法运算之前，将任何整数数值表达式被扩展为`Double`。</span><span class="sxs-lookup"><span data-stu-id="05d89-124">Before division is performed, any integral numeric expressions are widened to `Double`.</span></span> <span data-ttu-id="05d89-125">如果将结果分配到整数数据类型，请尝试将转换的结果 Visual Basic`Double`为该类型。</span><span class="sxs-lookup"><span data-stu-id="05d89-125">If you assign the result to an integral data type, Visual Basic attempts to convert the result from `Double` to that type.</span></span> <span data-ttu-id="05d89-126">如果结果无法容纳在该类型，这可以引发异常。</span><span class="sxs-lookup"><span data-stu-id="05d89-126">This can throw an exception if the result does not fit in that type.</span></span> <span data-ttu-id="05d89-127">具体而言，此帮助页上看到"尝试用零作除数"。</span><span class="sxs-lookup"><span data-stu-id="05d89-127">In particular, see "Attempted Division by Zero" on this Help page.</span></span>  
  
 <span data-ttu-id="05d89-128">如果`expression1`或`expression2`的计算结果为[Nothing](../../../visual-basic/language-reference/nothing.md)，它将被视为零。</span><span class="sxs-lookup"><span data-stu-id="05d89-128">If `expression1` or `expression2` evaluates to [Nothing](../../../visual-basic/language-reference/nothing.md), it is treated as zero.</span></span>  
  
## <a name="attempted-division-by-zero"></a><span data-ttu-id="05d89-129">尝试的除数为零</span><span class="sxs-lookup"><span data-stu-id="05d89-129">Attempted Division by Zero</span></span>  
 <span data-ttu-id="05d89-130">如果`expression2`计算结果为零，`/`运算符在行为上以不同的方式不同操作数数据类型。</span><span class="sxs-lookup"><span data-stu-id="05d89-130">If `expression2` evaluates to zero, the `/` operator behaves differently for different operand data types.</span></span> <span data-ttu-id="05d89-131">下表显示了可能的行为。</span><span class="sxs-lookup"><span data-stu-id="05d89-131">The following table shows the possible behaviors.</span></span>  
  
|<span data-ttu-id="05d89-132">操作数数据类型</span><span class="sxs-lookup"><span data-stu-id="05d89-132">Operand data types</span></span>|<span data-ttu-id="05d89-133">行为如果`expression2`为零</span><span class="sxs-lookup"><span data-stu-id="05d89-133">Behavior if `expression2` is zero</span></span>|  
|------------------------|---------------------------------------|  
|<span data-ttu-id="05d89-134">浮点 (`Single`或`Double`)</span><span class="sxs-lookup"><span data-stu-id="05d89-134">Floating-point (`Single` or `Double`)</span></span>|<span data-ttu-id="05d89-135">返回无穷大 (<xref:System.Double.PositiveInfinity>或<xref:System.Double.NegativeInfinity>)，或<xref:System.Double.NaN>（而不是数字） 如果`expression1`也为零</span><span class="sxs-lookup"><span data-stu-id="05d89-135">Returns infinity (<xref:System.Double.PositiveInfinity> or <xref:System.Double.NegativeInfinity>), or <xref:System.Double.NaN> (not a number) if `expression1` is also zero</span></span>|  
|`Decimal`|<span data-ttu-id="05d89-136">将引发 <xref:System.DivideByZeroException></span><span class="sxs-lookup"><span data-stu-id="05d89-136">Throws <xref:System.DivideByZeroException></span></span>|  
|<span data-ttu-id="05d89-137">整型 （带符号或无符号）</span><span class="sxs-lookup"><span data-stu-id="05d89-137">Integral (signed or unsigned)</span></span>|<span data-ttu-id="05d89-138">尝试转换回整数类型，则会引发<xref:System.OverflowException>因为整型类型不能接受<xref:System.Double.PositiveInfinity>， <xref:System.Double.NegativeInfinity>，或 <xref:System.Double.NaN></span><span class="sxs-lookup"><span data-stu-id="05d89-138">Attempted conversion back to integral type throws <xref:System.OverflowException> because integral types cannot accept <xref:System.Double.PositiveInfinity>, <xref:System.Double.NegativeInfinity>, or <xref:System.Double.NaN></span></span>|  
  
> [!NOTE]
>  <span data-ttu-id="05d89-139">`/`运算符可以被*重载*，这意味着，某个类或结构可以重新定义其行为时，操作数的类或结构的类型。</span><span class="sxs-lookup"><span data-stu-id="05d89-139">The `/` operator can be *overloaded*, which means that a class or structure can redefine its behavior when an operand has the type of that class or structure.</span></span> <span data-ttu-id="05d89-140">如果你的代码对此类的类或结构使用此运算符，请确保了解其被重新定义的行为。</span><span class="sxs-lookup"><span data-stu-id="05d89-140">If your code uses this operator on such a class or structure, be sure you understand its redefined behavior.</span></span> <span data-ttu-id="05d89-141">有关详细信息，请参阅 [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md)。</span><span class="sxs-lookup"><span data-stu-id="05d89-141">For more information, see [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="05d89-142">示例</span><span class="sxs-lookup"><span data-stu-id="05d89-142">Example</span></span>  
 <span data-ttu-id="05d89-143">此示例使用`/`运算符执行浮点除法。</span><span class="sxs-lookup"><span data-stu-id="05d89-143">This example uses the `/` operator to perform floating-point division.</span></span> <span data-ttu-id="05d89-144">结果是两个操作数的商。</span><span class="sxs-lookup"><span data-stu-id="05d89-144">The result is the quotient of the two operands.</span></span>  
  
 [!code-vb[VbVbalrOperators#16](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#16)]  
  
 <span data-ttu-id="05d89-145">在前面的示例表达式返回值为 2.5 3.333333。</span><span class="sxs-lookup"><span data-stu-id="05d89-145">The expressions in the preceding example return values of 2.5 and 3.333333.</span></span> <span data-ttu-id="05d89-146">请注意，结果始终是浮点 (`Double`)，即使这两个操作数都是整数常量。</span><span class="sxs-lookup"><span data-stu-id="05d89-146">Note that the result is always floating-point (`Double`), even though both operands are integer constants.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="05d89-147">请参阅</span><span class="sxs-lookup"><span data-stu-id="05d89-147">See also</span></span>

- [<span data-ttu-id="05d89-148">/ = 运算符 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="05d89-148">/= Operator (Visual Basic)</span></span>](../../../visual-basic/language-reference/operators/floating-point-division-assignment-operator.md)
- [<span data-ttu-id="05d89-149">\ 运算符 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="05d89-149">\ Operator (Visual Basic)</span></span>](../../../visual-basic/language-reference/operators/integer-division-operator.md)
- [<span data-ttu-id="05d89-150">运算符结果的数据类型</span><span class="sxs-lookup"><span data-stu-id="05d89-150">Data Types of Operator Results</span></span>](../../../visual-basic/language-reference/operators/data-types-of-operator-results.md)
- [<span data-ttu-id="05d89-151">算术运算符</span><span class="sxs-lookup"><span data-stu-id="05d89-151">Arithmetic Operators</span></span>](../../../visual-basic/language-reference/operators/arithmetic-operators.md)
- [<span data-ttu-id="05d89-152">Visual Basic 中的运算符优先级</span><span class="sxs-lookup"><span data-stu-id="05d89-152">Operator Precedence in Visual Basic</span></span>](../../../visual-basic/language-reference/operators/operator-precedence.md)
- [<span data-ttu-id="05d89-153">按功能列出的运算符</span><span class="sxs-lookup"><span data-stu-id="05d89-153">Operators Listed by Functionality</span></span>](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)
- [<span data-ttu-id="05d89-154">在 Visual Basic 中的算术运算符</span><span class="sxs-lookup"><span data-stu-id="05d89-154">Arithmetic Operators in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/operators-and-expressions/arithmetic-operators.md)
