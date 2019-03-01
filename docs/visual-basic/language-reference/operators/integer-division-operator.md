---
title: '\ 运算符 (Visual Basic)'
ms.date: 07/20/2015
f1_keywords:
- vb.\
- '\'
helpviewer_keywords:
- division operator [Visual Basic], integer
- integer division operator [Visual Basic]
- zero, division by zero
- arithmetic operators [Visual Basic], division
- division [Visual Basic], by zero
- backslash (\) [Visual Basic]
- '\ operator [Visual Basic]'
- integer quotient
- math operators [Visual Basic]
- quotients, integer
- truncation [Visual Basic], integer division
ms.assetid: 4b0ee347-950c-45c9-8e23-54bc85df208e
ms.openlocfilehash: 7ce7bdaa2bcbf2ba67f24c7e129f8f9a03a28c52
ms.sourcegitcommit: 41c0637e894fbcd0713d46d6ef1866f08dc321a2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/01/2019
ms.locfileid: "57201906"
---
# <a name="-operator-visual-basic"></a><span data-ttu-id="134d0-102">\ 运算符 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="134d0-102">\ Operator (Visual Basic)</span></span>
<span data-ttu-id="134d0-103">使两个数字相除，返回结果为整数。</span><span class="sxs-lookup"><span data-stu-id="134d0-103">Divides two numbers and returns an integer result.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="134d0-104">语法</span><span class="sxs-lookup"><span data-stu-id="134d0-104">Syntax</span></span>  
  
```  
expression1 \ expression2  
```  
  
## <a name="parts"></a><span data-ttu-id="134d0-105">部件</span><span class="sxs-lookup"><span data-stu-id="134d0-105">Parts</span></span>  
 `expression1`  
 <span data-ttu-id="134d0-106">必需。</span><span class="sxs-lookup"><span data-stu-id="134d0-106">Required.</span></span> <span data-ttu-id="134d0-107">任何数值表达式。</span><span class="sxs-lookup"><span data-stu-id="134d0-107">Any numeric expression.</span></span>  
  
 `expression2`  
 <span data-ttu-id="134d0-108">必需。</span><span class="sxs-lookup"><span data-stu-id="134d0-108">Required.</span></span> <span data-ttu-id="134d0-109">任何数值表达式。</span><span class="sxs-lookup"><span data-stu-id="134d0-109">Any numeric expression.</span></span>  
  
## <a name="supported-types"></a><span data-ttu-id="134d0-110">支持的类型</span><span class="sxs-lookup"><span data-stu-id="134d0-110">Supported Types</span></span>  
 <span data-ttu-id="134d0-111">所有数值类型，包括未签名和浮点类型和`Decimal`。</span><span class="sxs-lookup"><span data-stu-id="134d0-111">All numeric types, including the unsigned and floating-point types and `Decimal`.</span></span>  
  
## <a name="result"></a><span data-ttu-id="134d0-112">结果</span><span class="sxs-lookup"><span data-stu-id="134d0-112">Result</span></span>  
 <span data-ttu-id="134d0-113">结果为整数的商的`expression1`除以`expression2`，它将放弃所有余数，并只保留整数部分。</span><span class="sxs-lookup"><span data-stu-id="134d0-113">The result is the integer quotient of `expression1` divided by `expression2`, which discards any remainder and retains only the integer portion.</span></span> <span data-ttu-id="134d0-114">这称为*截断*。</span><span class="sxs-lookup"><span data-stu-id="134d0-114">This is known as *truncation*.</span></span>  
  
 <span data-ttu-id="134d0-115">结果数据类型为数值类型的数据类型的相应`expression1`和`expression2`。</span><span class="sxs-lookup"><span data-stu-id="134d0-115">The result data type is a numeric type appropriate for the data types of `expression1` and `expression2`.</span></span> <span data-ttu-id="134d0-116">请参阅中的"整数运算"表[数据类型的运算符结果](../../../visual-basic/language-reference/operators/data-types-of-operator-results.md)。</span><span class="sxs-lookup"><span data-stu-id="134d0-116">See the "Integer Arithmetic" tables in [Data Types of Operator Results](../../../visual-basic/language-reference/operators/data-types-of-operator-results.md).</span></span>  
  
 <span data-ttu-id="134d0-117">[/ 运算符 (Visual Basic)](../../../visual-basic/language-reference/operators/floating-point-division-operator.md)返回完整商，保留其余部分中的小数部分。</span><span class="sxs-lookup"><span data-stu-id="134d0-117">The [/ Operator (Visual Basic)](../../../visual-basic/language-reference/operators/floating-point-division-operator.md) returns the full quotient, which retains the remainder in the fractional portion.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="134d0-118">备注</span><span class="sxs-lookup"><span data-stu-id="134d0-118">Remarks</span></span>  
 <span data-ttu-id="134d0-119">执行除法运算之前，先尝试将转换为任何浮点数值表达式 Visual Basic `Long`。</span><span class="sxs-lookup"><span data-stu-id="134d0-119">Before performing the division, Visual Basic attempts to convert any floating-point numeric expression to `Long`.</span></span> <span data-ttu-id="134d0-120">如果`Option Strict`是`On`，会发生编译器错误。</span><span class="sxs-lookup"><span data-stu-id="134d0-120">If `Option Strict` is `On`, a compiler error occurs.</span></span> <span data-ttu-id="134d0-121">如果`Option Strict`是`Off`，则<xref:System.OverflowException>如果的值的范围超出了，则可能[Long 数据类型](../../../visual-basic/language-reference/data-types/long-data-type.md)。</span><span class="sxs-lookup"><span data-stu-id="134d0-121">If `Option Strict` is `Off`, an <xref:System.OverflowException> is possible if the value is outside the range of the [Long Data Type](../../../visual-basic/language-reference/data-types/long-data-type.md).</span></span> <span data-ttu-id="134d0-122">转换为`Long`也都将遵守*银行家的舍入*。</span><span class="sxs-lookup"><span data-stu-id="134d0-122">The conversion to `Long` is also subject to *banker's rounding*.</span></span> <span data-ttu-id="134d0-123">详细信息，请参阅"小数部分"中[类型转换函数](../../../visual-basic/language-reference/functions/type-conversion-functions.md)。</span><span class="sxs-lookup"><span data-stu-id="134d0-123">For more information, see "Fractional Parts" in [Type Conversion Functions](../../../visual-basic/language-reference/functions/type-conversion-functions.md).</span></span>  
  
 <span data-ttu-id="134d0-124">如果`expression1`或`expression2`的计算结果为[Nothing](../../../visual-basic/language-reference/nothing.md)，它将被视为零。</span><span class="sxs-lookup"><span data-stu-id="134d0-124">If `expression1` or `expression2` evaluates to [Nothing](../../../visual-basic/language-reference/nothing.md), it is treated as zero.</span></span>  
  
## <a name="attempted-division-by-zero"></a><span data-ttu-id="134d0-125">尝试的除数为零</span><span class="sxs-lookup"><span data-stu-id="134d0-125">Attempted Division by Zero</span></span>  
 <span data-ttu-id="134d0-126">如果`expression2`计算结果为零，`\`运算符引发<xref:System.DivideByZeroException>异常。</span><span class="sxs-lookup"><span data-stu-id="134d0-126">If `expression2` evaluates to zero, the `\` operator throws a <xref:System.DivideByZeroException> exception.</span></span> <span data-ttu-id="134d0-127">这适用于所有数值数据类型的操作数。</span><span class="sxs-lookup"><span data-stu-id="134d0-127">This is true for all numeric data types of the operands.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="134d0-128">`\`运算符可以被*重载*，这意味着，某个类或结构可以重新定义其行为时，操作数的类或结构的类型。</span><span class="sxs-lookup"><span data-stu-id="134d0-128">The `\` operator can be *overloaded*, which means that a class or structure can redefine its behavior when an operand has the type of that class or structure.</span></span> <span data-ttu-id="134d0-129">如果你的代码对此类的类或结构使用此运算符，请确保了解其被重新定义的行为。</span><span class="sxs-lookup"><span data-stu-id="134d0-129">If your code uses this operator on such a class or structure, be sure you understand its redefined behavior.</span></span> <span data-ttu-id="134d0-130">有关详细信息，请参阅 [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md)。</span><span class="sxs-lookup"><span data-stu-id="134d0-130">For more information, see [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="134d0-131">示例</span><span class="sxs-lookup"><span data-stu-id="134d0-131">Example</span></span>  
 <span data-ttu-id="134d0-132">下面的示例使用`\`运算符执行整数除法。</span><span class="sxs-lookup"><span data-stu-id="134d0-132">The following example uses the `\` operator to perform integer division.</span></span> <span data-ttu-id="134d0-133">结果是一个整数，表示两个操作数的整数商丢弃剩余部分。</span><span class="sxs-lookup"><span data-stu-id="134d0-133">The result is an integer that represents the integer quotient of the two operands, with the remainder discarded.</span></span>  
  
 [!code-vb[VbVbalrOperators#18](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#18)]  
  
 <span data-ttu-id="134d0-134">在前面的示例表达式分别返回值为 2、 3、 33 和-22。</span><span class="sxs-lookup"><span data-stu-id="134d0-134">The expressions in the preceding example return values of 2, 3, 33, and -22, respectively.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="134d0-135">请参阅</span><span class="sxs-lookup"><span data-stu-id="134d0-135">See also</span></span>
- [<span data-ttu-id="134d0-136">\\= 运算符</span><span class="sxs-lookup"><span data-stu-id="134d0-136">\\= Operator</span></span>](../../../visual-basic/language-reference/operators/integer-division-assignment-operator.md)
- [<span data-ttu-id="134d0-137">/ 运算符 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="134d0-137">/ Operator (Visual Basic)</span></span>](../../../visual-basic/language-reference/operators/floating-point-division-operator.md)
- [<span data-ttu-id="134d0-138">Option Strict 语句</span><span class="sxs-lookup"><span data-stu-id="134d0-138">Option Strict Statement</span></span>](../../../visual-basic/language-reference/statements/option-strict-statement.md)
- [<span data-ttu-id="134d0-139">算术运算符</span><span class="sxs-lookup"><span data-stu-id="134d0-139">Arithmetic Operators</span></span>](../../../visual-basic/language-reference/operators/arithmetic-operators.md)
- [<span data-ttu-id="134d0-140">Visual Basic 中的运算符优先级</span><span class="sxs-lookup"><span data-stu-id="134d0-140">Operator Precedence in Visual Basic</span></span>](../../../visual-basic/language-reference/operators/operator-precedence.md)
- [<span data-ttu-id="134d0-141">按功能列出的运算符</span><span class="sxs-lookup"><span data-stu-id="134d0-141">Operators Listed by Functionality</span></span>](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)
- [<span data-ttu-id="134d0-142">在 Visual Basic 中的算术运算符</span><span class="sxs-lookup"><span data-stu-id="134d0-142">Arithmetic Operators in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/operators-and-expressions/arithmetic-operators.md)
