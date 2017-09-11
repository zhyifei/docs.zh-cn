---
title: "/ 运算符 (Visual Basic 中) |Microsoft 文档"
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vb./
dev_langs:
- VB
helpviewer_keywords:
- division operator, floating point
- floating-point numbers, division operator
- slash (/) operator
- zero, division by zero
- operators [Visual Basic], arithmetic
- arithmetic operators, division
- division, by zero
- operators [Visual Basic], division
- division operator, syntax
- / operator [Visual Basic]
- math operators
ms.assetid: 335e97f2-c434-439e-9064-76973a051101
caps.latest.revision: 18
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Machine Translation
ms.sourcegitcommit: 14abadaf548e228244a1ff7ca72fa3896ef4eb5d
ms.openlocfilehash: 82255339c3bdab7f6e760de9bef073f463260877
ms.contentlocale: zh-cn
ms.lasthandoff: 05/23/2017

---
# <a name="-operator-visual-basic"></a><span data-ttu-id="69de6-102">/ 运算符 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="69de6-102">/ Operator (Visual Basic)</span></span>
<span data-ttu-id="69de6-103">使两个数字相除，返回浮点结果。</span><span class="sxs-lookup"><span data-stu-id="69de6-103">Divides two numbers and returns a floating-point result.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="69de6-104">语法</span><span class="sxs-lookup"><span data-stu-id="69de6-104">Syntax</span></span>  
  
```  
expression1 / expression2  
```  
  
## <a name="parts"></a><span data-ttu-id="69de6-105">部件</span><span class="sxs-lookup"><span data-stu-id="69de6-105">Parts</span></span>  
 `expression1`  
 <span data-ttu-id="69de6-106">必需。</span><span class="sxs-lookup"><span data-stu-id="69de6-106">Required.</span></span> <span data-ttu-id="69de6-107">任何数值表达式。</span><span class="sxs-lookup"><span data-stu-id="69de6-107">Any numeric expression.</span></span>  
  
 `expression2`  
 <span data-ttu-id="69de6-108">必需。</span><span class="sxs-lookup"><span data-stu-id="69de6-108">Required.</span></span> <span data-ttu-id="69de6-109">任何数值表达式。</span><span class="sxs-lookup"><span data-stu-id="69de6-109">Any numeric expression.</span></span>  
  
## <a name="supported-types"></a><span data-ttu-id="69de6-110">支持的类型</span><span class="sxs-lookup"><span data-stu-id="69de6-110">Supported Types</span></span>  
 <span data-ttu-id="69de6-111">所有数值类型，包括无符号和浮点类型和`Decimal`。</span><span class="sxs-lookup"><span data-stu-id="69de6-111">All numeric types, including the unsigned and floating-point types and `Decimal`.</span></span>  
  
## <a name="result"></a><span data-ttu-id="69de6-112">结果</span><span class="sxs-lookup"><span data-stu-id="69de6-112">Result</span></span>  
 <span data-ttu-id="69de6-113">结果是完整的商`expression1`除以`expression2`，包括任何余数。</span><span class="sxs-lookup"><span data-stu-id="69de6-113">The result is the full quotient of `expression1` divided by `expression2`, including any remainder.</span></span>  
  
 <span data-ttu-id="69de6-114">[\ 运算符 (Visual Basic)](../../../visual-basic/language-reference/operators/integer-division-operator.md)返回整数的商，将删除其余部分。</span><span class="sxs-lookup"><span data-stu-id="69de6-114">The [\ Operator (Visual Basic)](../../../visual-basic/language-reference/operators/integer-division-operator.md) returns the integer quotient, which drops the remainder.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="69de6-115">备注</span><span class="sxs-lookup"><span data-stu-id="69de6-115">Remarks</span></span>  
 <span data-ttu-id="69de6-116">结果的数据类型取决于操作数的类型。</span><span class="sxs-lookup"><span data-stu-id="69de6-116">The data type of the result depends on the types of the operands.</span></span> <span data-ttu-id="69de6-117">下表显示如何确定结果的数据类型。</span><span class="sxs-lookup"><span data-stu-id="69de6-117">The following table shows how the data type of the result is determined.</span></span>  
  
|<span data-ttu-id="69de6-118">操作数数据类型</span><span class="sxs-lookup"><span data-stu-id="69de6-118">Operand data types</span></span>|<span data-ttu-id="69de6-119">结果数据类型</span><span class="sxs-lookup"><span data-stu-id="69de6-119">Result data type</span></span>|  
|------------------------|----------------------|  
|<span data-ttu-id="69de6-120">这两个表达式都是整数数据类型 ([SByte](../../../visual-basic/language-reference/data-types/sbyte-data-type.md)，[字节](../../../visual-basic/language-reference/data-types/byte-data-type.md)，[短](../../../visual-basic/language-reference/data-types/short-data-type.md)， [UShort](../../../visual-basic/language-reference/data-types/ushort-data-type.md)，[整数](../../../visual-basic/language-reference/data-types/integer-data-type.md)， [UInteger](../../../visual-basic/language-reference/data-types/uinteger-data-type.md)，[长](../../../visual-basic/language-reference/data-types/long-data-type.md)， [ULong](../../../visual-basic/language-reference/data-types/ulong-data-type.md))</span><span class="sxs-lookup"><span data-stu-id="69de6-120">Both expressions are integral data types ([SByte](../../../visual-basic/language-reference/data-types/sbyte-data-type.md), [Byte](../../../visual-basic/language-reference/data-types/byte-data-type.md), [Short](../../../visual-basic/language-reference/data-types/short-data-type.md), [UShort](../../../visual-basic/language-reference/data-types/ushort-data-type.md), [Integer](../../../visual-basic/language-reference/data-types/integer-data-type.md), [UInteger](../../../visual-basic/language-reference/data-types/uinteger-data-type.md), [Long](../../../visual-basic/language-reference/data-types/long-data-type.md), [ULong](../../../visual-basic/language-reference/data-types/ulong-data-type.md))</span></span>|`Double`|  
|<span data-ttu-id="69de6-121">一个表达式是[单个](../../../visual-basic/language-reference/data-types/single-data-type.md)数据类型，另一个不是[Double](../../../visual-basic/language-reference/data-types/double-data-type.md)</span><span class="sxs-lookup"><span data-stu-id="69de6-121">One expression is a [Single](../../../visual-basic/language-reference/data-types/single-data-type.md) data type and the other is not a [Double](../../../visual-basic/language-reference/data-types/double-data-type.md)</span></span>|`Single`|  
|<span data-ttu-id="69de6-122">一个表达式是[十进制](../../../visual-basic/language-reference/data-types/decimal-data-type.md)数据类型，另一个不是[单个](../../../visual-basic/language-reference/data-types/single-data-type.md)或[Double](../../../visual-basic/language-reference/data-types/double-data-type.md)</span><span class="sxs-lookup"><span data-stu-id="69de6-122">One expression is a [Decimal](../../../visual-basic/language-reference/data-types/decimal-data-type.md) data type and the other is not a [Single](../../../visual-basic/language-reference/data-types/single-data-type.md) or a [Double](../../../visual-basic/language-reference/data-types/double-data-type.md)</span></span>|`Decimal`|  
|<span data-ttu-id="69de6-123">其中任何一个表达式是[Double](../../../visual-basic/language-reference/data-types/double-data-type.md)数据类型</span><span class="sxs-lookup"><span data-stu-id="69de6-123">Either expression is a [Double](../../../visual-basic/language-reference/data-types/double-data-type.md) data type</span></span>|`Double`|  
  
 <span data-ttu-id="69de6-124">执行除法运算之前，将任何整数数值表达式被扩展为`Double`。</span><span class="sxs-lookup"><span data-stu-id="69de6-124">Before division is performed, any integral numeric expressions are widened to `Double`.</span></span> <span data-ttu-id="69de6-125">如果将结果分配给整型数据类型，请尝试将转换的结果 Visual Basic`Double`为该类型。</span><span class="sxs-lookup"><span data-stu-id="69de6-125">If you assign the result to an integral data type, Visual Basic attempts to convert the result from `Double` to that type.</span></span> <span data-ttu-id="69de6-126">如果结果无法容纳在该类型，这可以引发异常。</span><span class="sxs-lookup"><span data-stu-id="69de6-126">This can throw an exception if the result does not fit in that type.</span></span> <span data-ttu-id="69de6-127">请参见此帮助页上的"尝试用零作除数"。</span><span class="sxs-lookup"><span data-stu-id="69de6-127">In particular, see "Attempted Division by Zero" on this Help page.</span></span>  
  
 <span data-ttu-id="69de6-128">如果`expression1`或`expression2`的计算结果为[Nothing](../../../visual-basic/language-reference/nothing.md)，它将被视为零。</span><span class="sxs-lookup"><span data-stu-id="69de6-128">If `expression1` or `expression2` evaluates to [Nothing](../../../visual-basic/language-reference/nothing.md), it is treated as zero.</span></span>  
  
## <a name="attempted-division-by-zero"></a><span data-ttu-id="69de6-129">尝试被零除</span><span class="sxs-lookup"><span data-stu-id="69de6-129">Attempted Division by Zero</span></span>  
 <span data-ttu-id="69de6-130">如果`expression2`计算结果为零，`/`运算符的操作数数据类型不同的行为以不同的方式。</span><span class="sxs-lookup"><span data-stu-id="69de6-130">If `expression2` evaluates to zero, the `/` operator behaves differently for different operand data types.</span></span> <span data-ttu-id="69de6-131">下表显示可能的行为。</span><span class="sxs-lookup"><span data-stu-id="69de6-131">The following table shows the possible behaviors.</span></span>  
  
|<span data-ttu-id="69de6-132">操作数数据类型</span><span class="sxs-lookup"><span data-stu-id="69de6-132">Operand data types</span></span>|<span data-ttu-id="69de6-133">行为如果`expression2`为零</span><span class="sxs-lookup"><span data-stu-id="69de6-133">Behavior if `expression2` is zero</span></span>|  
|------------------------|---------------------------------------|  
|<span data-ttu-id="69de6-134">浮点 (`Single`或`Double`)</span><span class="sxs-lookup"><span data-stu-id="69de6-134">Floating-point (`Single` or `Double`)</span></span>|<span data-ttu-id="69de6-135">返回无穷大 (<xref:System.Double.PositiveInfinity>或<xref:System.Double.NegativeInfinity>)，或<xref:System.Double.NaN>（而不是数字） 如果`expression1`也为零</xref:System.Double.NaN></xref:System.Double.NegativeInfinity></xref:System.Double.PositiveInfinity></span><span class="sxs-lookup"><span data-stu-id="69de6-135">Returns infinity (<xref:System.Double.PositiveInfinity> or <xref:System.Double.NegativeInfinity>), or <xref:System.Double.NaN> (not a number) if `expression1` is also zero</span></span>|  
|`Decimal`|<span data-ttu-id="69de6-136">将引发<xref:System.DivideByZeroException></xref:System.DivideByZeroException></span><span class="sxs-lookup"><span data-stu-id="69de6-136">Throws <xref:System.DivideByZeroException></span></span>|  
|<span data-ttu-id="69de6-137">整数 （有符号或无符号）</span><span class="sxs-lookup"><span data-stu-id="69de6-137">Integral (signed or unsigned)</span></span>|<span data-ttu-id="69de6-138">尝试转换回整数类型，则会引发<xref:System.OverflowException>因为整数类型不能接受<xref:System.Double.PositiveInfinity>， <xref:System.Double.NegativeInfinity>，或<xref:System.Double.NaN></xref:System.Double.NaN></xref:System.Double.NegativeInfinity></xref:System.Double.PositiveInfinity></xref:System.OverflowException></span><span class="sxs-lookup"><span data-stu-id="69de6-138">Attempted conversion back to integral type throws <xref:System.OverflowException> because integral types cannot accept <xref:System.Double.PositiveInfinity>, <xref:System.Double.NegativeInfinity>, or <xref:System.Double.NaN></span></span>|  
  
> [!NOTE]
>  <span data-ttu-id="69de6-139">`/`运算符可以被*重载*，这意味着，某个类或结构可以重新定义其行为时，操作数的类或结构的类型。</span><span class="sxs-lookup"><span data-stu-id="69de6-139">The `/` operator can be *overloaded*, which means that a class or structure can redefine its behavior when an operand has the type of that class or structure.</span></span> <span data-ttu-id="69de6-140">如果您的代码对这样的类或结构中使用此运算符，请确保您了解其被重新定义的行为。</span><span class="sxs-lookup"><span data-stu-id="69de6-140">If your code uses this operator on such a class or structure, be sure you understand its redefined behavior.</span></span> <span data-ttu-id="69de6-141">有关详细信息，请参阅[运算符过程](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md)。</span><span class="sxs-lookup"><span data-stu-id="69de6-141">For more information, see [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="69de6-142">示例</span><span class="sxs-lookup"><span data-stu-id="69de6-142">Example</span></span>  
 <span data-ttu-id="69de6-143">此示例使用`/`运算符执行浮点除法运算。</span><span class="sxs-lookup"><span data-stu-id="69de6-143">This example uses the `/` operator to perform floating-point division.</span></span> <span data-ttu-id="69de6-144">结果是两个操作数的商。</span><span class="sxs-lookup"><span data-stu-id="69de6-144">The result is the quotient of the two operands.</span></span>  
  
 <span data-ttu-id="69de6-145">[!code-vb[VbVbalrOperators #&16;](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/floating-point-division-operator_1.vb)]</span><span class="sxs-lookup"><span data-stu-id="69de6-145">[!code-vb[VbVbalrOperators#16](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/floating-point-division-operator_1.vb)]</span></span>  
  
 <span data-ttu-id="69de6-146">在前面的示例表达式返回 2.5 和 3.333333 的值。</span><span class="sxs-lookup"><span data-stu-id="69de6-146">The expressions in the preceding example return values of 2.5 and 3.333333.</span></span> <span data-ttu-id="69de6-147">请注意，结果始终是浮点 (`Double`)，即使这两个操作数都是整数常量。</span><span class="sxs-lookup"><span data-stu-id="69de6-147">Note that the result is always floating-point (`Double`), even though both operands are integer constants.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="69de6-148">另请参阅</span><span class="sxs-lookup"><span data-stu-id="69de6-148">See Also</span></span>  
 <span data-ttu-id="69de6-149">[/ = 运算符 (Visual Basic)](../../../visual-basic/language-reference/operators/floating-point-division-assignment-operator.md) </span><span class="sxs-lookup"><span data-stu-id="69de6-149">[/= Operator (Visual Basic)](../../../visual-basic/language-reference/operators/floating-point-division-assignment-operator.md) </span></span>  
<span data-ttu-id="69de6-150"> [\ 运算符 (Visual Basic)](../../../visual-basic/language-reference/operators/integer-division-operator.md) </span><span class="sxs-lookup"><span data-stu-id="69de6-150"> [\ Operator (Visual Basic)](../../../visual-basic/language-reference/operators/integer-division-operator.md) </span></span>  
<span data-ttu-id="69de6-151"> [运算符结果的数据类型](../../../visual-basic/language-reference/operators/data-types-of-operator-results.md) </span><span class="sxs-lookup"><span data-stu-id="69de6-151"> [Data Types of Operator Results](../../../visual-basic/language-reference/operators/data-types-of-operator-results.md) </span></span>  
<span data-ttu-id="69de6-152"> [算术运算符](../../../visual-basic/language-reference/operators/arithmetic-operators.md) </span><span class="sxs-lookup"><span data-stu-id="69de6-152"> [Arithmetic Operators](../../../visual-basic/language-reference/operators/arithmetic-operators.md) </span></span>  
<span data-ttu-id="69de6-153"> [在 Visual Basic 中的运算符优先级](../../../visual-basic/language-reference/operators/operator-precedence.md) </span><span class="sxs-lookup"><span data-stu-id="69de6-153"> [Operator Precedence in Visual Basic](../../../visual-basic/language-reference/operators/operator-precedence.md) </span></span>  
<span data-ttu-id="69de6-154"> [按功能列出的运算符](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md) </span><span class="sxs-lookup"><span data-stu-id="69de6-154"> [Operators Listed by Functionality](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md) </span></span>  
<span data-ttu-id="69de6-155"> [在 Visual Basic 中的算术运算符](../../../visual-basic/programming-guide/language-features/operators-and-expressions/arithmetic-operators.md)</span><span class="sxs-lookup"><span data-stu-id="69de6-155"> [Arithmetic Operators in Visual Basic](../../../visual-basic/programming-guide/language-features/operators-and-expressions/arithmetic-operators.md)</span></span>

