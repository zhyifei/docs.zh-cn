---
title: "在 Visual Basic 中的算术运算符 |Microsoft 文档"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- type safety
- operators [Visual Basic], bitwise
- operators [Visual Basic], bit-shift
- bitwise operators
- bit-shift operators
- zero, division by zero
- operators [Visual Basic], arithmetic
- division, by zero
- Visual Basic code, operators
- arithmetic operators, about arithmetic operators
ms.assetid: 325dac7a-ea4f-41d5-8b48-f6e904211569
caps.latest.revision: 20
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
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: e80e7950abe035efe5294974937589a1af40f17c
ms.contentlocale: zh-cn
ms.lasthandoff: 04/12/2017

---
# <a name="arithmetic-operators-in-visual-basic"></a><span data-ttu-id="61822-102">算术运算符 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="61822-102">Arithmetic Operators in Visual Basic</span></span>
<span data-ttu-id="61822-103">算术运算符用于执行很多熟悉的算术运算，涉及通过文字、 变量、 其他表达式、 函数和属性调用和常量表示的数值计算。</span><span class="sxs-lookup"><span data-stu-id="61822-103">Arithmetic operators are used to perform many of the familiar arithmetic operations that involve the calculation of numeric values represented by literals, variables, other expressions, function and property calls, and constants.</span></span> <span data-ttu-id="61822-104">算术运算符也属于是移位运算符，该级别的单个位进行运算的操作数执行操作和向左或向右移动其位模式。</span><span class="sxs-lookup"><span data-stu-id="61822-104">Also classified with arithmetic operators are the bit-shift operators, which act at the level of the individual bits of the operands and shift their bit patterns to the left or right.</span></span>  
  
## <a name="arithmetic-operations"></a><span data-ttu-id="61822-105">算术运算</span><span class="sxs-lookup"><span data-stu-id="61822-105">Arithmetic Operations</span></span>  
 <span data-ttu-id="61822-106">您可以添加两个值一起使用的表达式中[+ 运算符](../../../../visual-basic/language-reference/operators/addition-operator.md)，或从另一个具有中减去&1; [-运算符 (Visual Basic)](../../../../visual-basic/language-reference/operators/subtraction-operator.md)，如下面的示例所示。</span><span class="sxs-lookup"><span data-stu-id="61822-106">You can add two values in an expression together with the [+ Operator](../../../../visual-basic/language-reference/operators/addition-operator.md), or subtract one from another with the [- Operator (Visual Basic)](../../../../visual-basic/language-reference/operators/subtraction-operator.md), as the following example demonstrates.</span></span>  
  
 <span data-ttu-id="61822-107">[!code-vb[VbVbalrOperators #&57;](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/arithmetic-operators_1.vb)]</span><span class="sxs-lookup"><span data-stu-id="61822-107">[!code-vb[VbVbalrOperators#57](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/arithmetic-operators_1.vb)]</span></span>  
  
 <span data-ttu-id="61822-108">求反也使用[-运算符 (Visual Basic)](../../../../visual-basic/language-reference/operators/subtraction-operator.md)，但只带一个操作数，如下面的示例演示了。</span><span class="sxs-lookup"><span data-stu-id="61822-108">Negation also uses the [- Operator (Visual Basic)](../../../../visual-basic/language-reference/operators/subtraction-operator.md), but with only one operand, as the following example demonstrates.</span></span>  
  
 <span data-ttu-id="61822-109">[!code-vb[VbVbalrOperators #&58; 页](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/arithmetic-operators_2.vb)]</span><span class="sxs-lookup"><span data-stu-id="61822-109">[!code-vb[VbVbalrOperators#58](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/arithmetic-operators_2.vb)]</span></span>  
  
 <span data-ttu-id="61822-110">乘法和除法使用[* 运算符](../../../../visual-basic/language-reference/operators/multiplication-operator.md)和[/ 运算符 (Visual Basic)](../../../../visual-basic/language-reference/operators/floating-point-division-operator.md)分别，如下面的示例所示。</span><span class="sxs-lookup"><span data-stu-id="61822-110">Multiplication and division use the [* Operator](../../../../visual-basic/language-reference/operators/multiplication-operator.md) and [/ Operator (Visual Basic)](../../../../visual-basic/language-reference/operators/floating-point-division-operator.md), respectively, as the following example demonstrates.</span></span>  
  
 <span data-ttu-id="61822-111">[!code-vb[VbVbalrOperators #&59;](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/arithmetic-operators_3.vb)]</span><span class="sxs-lookup"><span data-stu-id="61822-111">[!code-vb[VbVbalrOperators#59](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/arithmetic-operators_3.vb)]</span></span>  
  
 <span data-ttu-id="61822-112">求幂使用[^ 运算符](../../../../visual-basic/language-reference/operators/exponentiation-operator.md)，如下面的示例所示。</span><span class="sxs-lookup"><span data-stu-id="61822-112">Exponentiation uses the [^ Operator](../../../../visual-basic/language-reference/operators/exponentiation-operator.md), as the following example demonstrates.</span></span>  
  
 <span data-ttu-id="61822-113">[!code-vb[VbVbalrOperators #&60;](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/arithmetic-operators_4.vb)]</span><span class="sxs-lookup"><span data-stu-id="61822-113">[!code-vb[VbVbalrOperators#60](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/arithmetic-operators_4.vb)]</span></span>  
  
 <span data-ttu-id="61822-114">整数除法利用执行[\ 运算符 (Visual Basic)](../../../../visual-basic/language-reference/operators/integer-division-operator.md)。</span><span class="sxs-lookup"><span data-stu-id="61822-114">Integer division is carried out using the [\ Operator (Visual Basic)](../../../../visual-basic/language-reference/operators/integer-division-operator.md).</span></span> <span data-ttu-id="61822-115">整数除法返回商，即表示的次数的整数除数可以除被除数而无需考虑了所有余数。</span><span class="sxs-lookup"><span data-stu-id="61822-115">Integer division returns the quotient, that is, the integer that represents the number of times the divisor can divide into the dividend without consideration of any remainder.</span></span> <span data-ttu-id="61822-116">除数和被除数必须是整数类型 (`SByte`， `Byte`， `Short`， `UShort`， `Integer`， `UInteger`， `Long`，和`ULong`) 为此运算符。</span><span class="sxs-lookup"><span data-stu-id="61822-116">Both the divisor and the dividend must be integral types (`SByte`, `Byte`, `Short`, `UShort`, `Integer`, `UInteger`, `Long`, and `ULong`) for this operator.</span></span> <span data-ttu-id="61822-117">必须首先将所有其他类型转换为整数类型。</span><span class="sxs-lookup"><span data-stu-id="61822-117">All other types must be converted to an integral type first.</span></span> <span data-ttu-id="61822-118">下面的示例演示整数除法。</span><span class="sxs-lookup"><span data-stu-id="61822-118">The following example demonstrates integer division.</span></span>  
  
 <span data-ttu-id="61822-119">[!code-vb[VbVbalrOperators #&61;](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/arithmetic-operators_5.vb)]</span><span class="sxs-lookup"><span data-stu-id="61822-119">[!code-vb[VbVbalrOperators#61](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/arithmetic-operators_5.vb)]</span></span>  
  
 <span data-ttu-id="61822-120">使用执行求模算术[Mod 运算符](../../../../visual-basic/language-reference/operators/mod-operator.md)。</span><span class="sxs-lookup"><span data-stu-id="61822-120">Modulus arithmetic is performed using the [Mod Operator](../../../../visual-basic/language-reference/operators/mod-operator.md).</span></span> <span data-ttu-id="61822-121">此运算符返回其余部分被除数除以除数后的次数的整数。</span><span class="sxs-lookup"><span data-stu-id="61822-121">This operator returns the remainder after dividing the divisor into the dividend an integral number of times.</span></span> <span data-ttu-id="61822-122">如果除数和被除数可以是整数类型，则返回的值是整数。</span><span class="sxs-lookup"><span data-stu-id="61822-122">If both divisor and dividend are integral types, the returned value is integral.</span></span> <span data-ttu-id="61822-123">如果除数和除数都是浮点类型，则返回的值也是浮点。</span><span class="sxs-lookup"><span data-stu-id="61822-123">If divisor and dividend are floating-point types, the returned value is also floating-point.</span></span> <span data-ttu-id="61822-124">下面的示例演示此行为。</span><span class="sxs-lookup"><span data-stu-id="61822-124">The following example demonstrates this behavior.</span></span>  
  
 <span data-ttu-id="61822-125">[!code-vb[VbVbalrOperators #&62;](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/arithmetic-operators_6.vb)]</span><span class="sxs-lookup"><span data-stu-id="61822-125">[!code-vb[VbVbalrOperators#62](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/arithmetic-operators_6.vb)]</span></span>  
  
 <span data-ttu-id="61822-126">[!code-vb[VbVbalrOperators #&63;](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/arithmetic-operators_7.vb)]</span><span class="sxs-lookup"><span data-stu-id="61822-126">[!code-vb[VbVbalrOperators#63](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/arithmetic-operators_7.vb)]</span></span>  
  
### <a name="attempted-division-by-zero"></a><span data-ttu-id="61822-127">尝试被零除</span><span class="sxs-lookup"><span data-stu-id="61822-127">Attempted Division by Zero</span></span>  
 <span data-ttu-id="61822-128">被零除具有不同的结果，具体取决于涉及的数据类型。</span><span class="sxs-lookup"><span data-stu-id="61822-128">Division by zero has different results depending on the data types involved.</span></span> <span data-ttu-id="61822-129">In integral divisions (`SByte`, `Byte`, `Short`, `UShort`, `Integer`, `UInteger`, `Long`, `ULong`), the [!INCLUDE[dnprdnshort](../../../../csharp/getting-started/includes/dnprdnshort_md.md)] throws a <xref:System.DivideByZeroException> exception.</xref:System.DivideByZeroException></span><span class="sxs-lookup"><span data-stu-id="61822-129">In integral divisions (`SByte`, `Byte`, `Short`, `UShort`, `Integer`, `UInteger`, `Long`, `ULong`), the [!INCLUDE[dnprdnshort](../../../../csharp/getting-started/includes/dnprdnshort_md.md)] throws a <xref:System.DivideByZeroException> exception.</span></span> <span data-ttu-id="61822-130">在除法运算`Decimal`或`Single`数据类型，[!INCLUDE[dnprdnshort](../../../../csharp/getting-started/includes/dnprdnshort_md.md)]还会抛出<xref:System.DivideByZeroException>异常。</xref:System.DivideByZeroException></span><span class="sxs-lookup"><span data-stu-id="61822-130">In division operations on the `Decimal` or `Single` data type, the [!INCLUDE[dnprdnshort](../../../../csharp/getting-started/includes/dnprdnshort_md.md)] also throws a <xref:System.DivideByZeroException> exception.</span></span>  
  
 <span data-ttu-id="61822-131">在涉及浮点部门`Double`数据类型，不会引发异常，并且结果是表示的类成员<xref:System.Double.NaN>， <xref:System.Double.PositiveInfinity>，或<xref:System.Double.NegativeInfinity>，取决于被除数。</xref:System.Double.NegativeInfinity> </xref:System.Double.PositiveInfinity> </xref:System.Double.NaN></span><span class="sxs-lookup"><span data-stu-id="61822-131">In floating-point divisions involving the `Double` data type, no exception is thrown, and the result is the class member representing <xref:System.Double.NaN>, <xref:System.Double.PositiveInfinity>, or <xref:System.Double.NegativeInfinity>, depending on the dividend.</span></span> <span data-ttu-id="61822-132">下表汇总了各个结果的尝试除`Double`被零除的值。</span><span class="sxs-lookup"><span data-stu-id="61822-132">The following table summarizes the various results of attempting to divide a `Double` value by zero.</span></span>  
  
|<span data-ttu-id="61822-133">被除数的数据类型</span><span class="sxs-lookup"><span data-stu-id="61822-133">Dividend data type</span></span>|<span data-ttu-id="61822-134">除数数据类型</span><span class="sxs-lookup"><span data-stu-id="61822-134">Divisor data type</span></span>|<span data-ttu-id="61822-135">被除数的值</span><span class="sxs-lookup"><span data-stu-id="61822-135">Dividend value</span></span>|<span data-ttu-id="61822-136">结果</span><span class="sxs-lookup"><span data-stu-id="61822-136">Result</span></span>|  
|---|---|---|---|  
|`Double`|`Double`|<span data-ttu-id="61822-137">0</span><span class="sxs-lookup"><span data-stu-id="61822-137">0</span></span>|<span data-ttu-id="61822-138"><xref:System.Double.NaN>（不是数学上定义的数字）</xref:System.Double.NaN></span><span class="sxs-lookup"><span data-stu-id="61822-138"><xref:System.Double.NaN> (not a mathematically defined number)</span></span>|  
|`Double`|`Double`|<span data-ttu-id="61822-139">> 0</span><span class="sxs-lookup"><span data-stu-id="61822-139">> 0</span></span>|<span data-ttu-id="61822-140"><xref:System.Double.PositiveInfinity></xref:System.Double.PositiveInfinity></span><span class="sxs-lookup"><span data-stu-id="61822-140"><xref:System.Double.PositiveInfinity></span></span>|  
|`Double`|`Double`|<span data-ttu-id="61822-141">\< 0</span><span class="sxs-lookup"><span data-stu-id="61822-141">\< 0</span></span>|<span data-ttu-id="61822-142"><xref:System.Double.NegativeInfinity></xref:System.Double.NegativeInfinity></span><span class="sxs-lookup"><span data-stu-id="61822-142"><xref:System.Double.NegativeInfinity></span></span>|  
  
 <span data-ttu-id="61822-143">当捕获的<xref:System.DivideByZeroException>异常，您可以使用其成员可以帮助您处理它。</xref:System.DivideByZeroException></span><span class="sxs-lookup"><span data-stu-id="61822-143">When you catch a <xref:System.DivideByZeroException> exception, you can use its members to help you handle it.</span></span> <span data-ttu-id="61822-144">例如，<xref:System.Exception.Message%2A>属性保留了该异常的消息文本。</xref:System.Exception.Message%2A></span><span class="sxs-lookup"><span data-stu-id="61822-144">For example, the <xref:System.Exception.Message%2A> property holds the message text for the exception.</span></span> <span data-ttu-id="61822-145">有关详细信息，请参阅[重试...Catch...Finally 语句](../../../../visual-basic/language-reference/statements/try-catch-finally-statement.md)。</span><span class="sxs-lookup"><span data-stu-id="61822-145">For more information, see [Try...Catch...Finally Statement](../../../../visual-basic/language-reference/statements/try-catch-finally-statement.md).</span></span>  
  
## <a name="bit-shift-operations"></a><span data-ttu-id="61822-146">移位运算</span><span class="sxs-lookup"><span data-stu-id="61822-146">Bit-Shift Operations</span></span>  
 <span data-ttu-id="61822-147">移位运算对位模式执行算术移位运算。</span><span class="sxs-lookup"><span data-stu-id="61822-147">A bit-shift operation performs an arithmetic shift on a bit pattern.</span></span> <span data-ttu-id="61822-148">模式包含在左侧，操作数中，而右侧操作数指定的位数移动模式。</span><span class="sxs-lookup"><span data-stu-id="61822-148">The pattern is contained in the operand on the left, while the operand on the right specifies the number of positions to shift the pattern.</span></span> <span data-ttu-id="61822-149">将模式切换到右[>> 运算符](../../../../visual-basic/language-reference/operators/right-shift-operator.md)滑动到左侧则与[ <> </> ](../../../../visual-basic/language-reference/operators/left-shift-operator.md)。</span><span class="sxs-lookup"><span data-stu-id="61822-149">You can shift the pattern to the right with the [>> Operator](../../../../visual-basic/language-reference/operators/right-shift-operator.md) or to the left with the [<< Operator](../../../../visual-basic/language-reference/operators/left-shift-operator.md).</span></span>  
  
 <span data-ttu-id="61822-150">模式操作数的数据类型必须是`SByte`， `Byte`， `Short`， `UShort`， `Integer`， `UInteger`， `Long`，或`ULong`。</span><span class="sxs-lookup"><span data-stu-id="61822-150">The data type of the pattern operand must be `SByte`, `Byte`, `Short`, `UShort`, `Integer`, `UInteger`, `Long`, or `ULong`.</span></span> <span data-ttu-id="61822-151">Shift 量操作数的数据类型必须是`Integer`或者必须扩大到`Integer`。</span><span class="sxs-lookup"><span data-stu-id="61822-151">The data type of the shift amount operand must be `Integer` or must widen to `Integer`.</span></span>  
  
 <span data-ttu-id="61822-152">算术移位不是循环性的这意味着从结果的一端移掉的位在另一端不重新移入。</span><span class="sxs-lookup"><span data-stu-id="61822-152">Arithmetic shifts are not circular, which means the bits shifted off one end of the result are not reintroduced at the other end.</span></span> <span data-ttu-id="61822-153">因移位而空出的位上将设置，如下所示︰</span><span class="sxs-lookup"><span data-stu-id="61822-153">The bit positions vacated by a shift are set as follows:</span></span>  
  
-   <span data-ttu-id="61822-154">0 表示算术左移位运算</span><span class="sxs-lookup"><span data-stu-id="61822-154">0 for an arithmetic left shift</span></span>  
  
-   <span data-ttu-id="61822-155">0 的正数值的算术右移位</span><span class="sxs-lookup"><span data-stu-id="61822-155">0 for an arithmetic right shift of a positive number</span></span>  
  
-   <span data-ttu-id="61822-156">算术右移位运算的无符号的数据类型为&0; (`Byte`， `UShort`， `UInteger`， `ULong`)</span><span class="sxs-lookup"><span data-stu-id="61822-156">0 for an arithmetic right shift of an unsigned data type (`Byte`, `UShort`, `UInteger`, `ULong`)</span></span>  
  
-   <span data-ttu-id="61822-157">1 表示负数的算术右移位 (`SByte`， `Short`， `Integer`，或`Long`)</span><span class="sxs-lookup"><span data-stu-id="61822-157">1 for an arithmetic right shift of a negative number (`SByte`, `Short`, `Integer`, or `Long`)</span></span>  
  
 <span data-ttu-id="61822-158">以下示例将推`Integer`左侧和右侧的值。</span><span class="sxs-lookup"><span data-stu-id="61822-158">The following example shifts an `Integer` value both left and right.</span></span>  
  
 <span data-ttu-id="61822-159">[!code-vb[VbVbalrOperators #&64;](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/arithmetic-operators_8.vb)]</span><span class="sxs-lookup"><span data-stu-id="61822-159">[!code-vb[VbVbalrOperators#64](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/arithmetic-operators_8.vb)]</span></span>  
  
 <span data-ttu-id="61822-160">算术移位永远不会产生溢出异常。</span><span class="sxs-lookup"><span data-stu-id="61822-160">Arithmetic shifts never generate overflow exceptions.</span></span>  
  
## <a name="bitwise-operations"></a><span data-ttu-id="61822-161">按位运算</span><span class="sxs-lookup"><span data-stu-id="61822-161">Bitwise Operations</span></span>  
 <span data-ttu-id="61822-162">逻辑运算符，除了`Not`， `Or`， `And`，和`Xor`还执行按位算术运算在数值中使用时。</span><span class="sxs-lookup"><span data-stu-id="61822-162">In addition to being logical operators, `Not`, `Or`, `And`, and `Xor` also perform bitwise arithmetic when used on numeric values.</span></span> <span data-ttu-id="61822-163">有关详细信息，请参阅 》 的"按位操作"[逻辑和按位运算符在 Visual Basic 中](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/logical-and-bitwise-operators.md)。</span><span class="sxs-lookup"><span data-stu-id="61822-163">For more information, see "Bitwise Operations" in [Logical and Bitwise Operators in Visual Basic](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/logical-and-bitwise-operators.md).</span></span>  
  
## <a name="type-safety"></a><span data-ttu-id="61822-164">类型安全</span><span class="sxs-lookup"><span data-stu-id="61822-164">Type Safety</span></span>  
 <span data-ttu-id="61822-165">操作数通常应属于同一类型。</span><span class="sxs-lookup"><span data-stu-id="61822-165">Operands should normally be of the same type.</span></span> <span data-ttu-id="61822-166">例如，如果你正在添加`Integer`变量时，您应将其添加到另一个`Integer`变量，并且您应将结果赋给一个类型的变量`Integer`以及。</span><span class="sxs-lookup"><span data-stu-id="61822-166">For example, if you are doing addition with an `Integer` variable, you should add it to another `Integer` variable, and you should assign the result to a variable of type `Integer` as well.</span></span>  
  
 <span data-ttu-id="61822-167">一种方法以确保良好的类型安全编码做法是使用[Option Strict 语句](../../../../visual-basic/language-reference/statements/option-strict-statement.md)。</span><span class="sxs-lookup"><span data-stu-id="61822-167">One way to ensure good type-safe coding practice is to use the [Option Strict Statement](../../../../visual-basic/language-reference/statements/option-strict-statement.md).</span></span> <span data-ttu-id="61822-168">如果您设置`Option Strict On`，[!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]自动执行*类型安全*转换。</span><span class="sxs-lookup"><span data-stu-id="61822-168">If you set `Option Strict On`, [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] automatically performs *type-safe* conversions.</span></span> <span data-ttu-id="61822-169">例如，如果你尝试添加`Integer`变量`Double`变量并将值赋给`Double`变量时，该操作将正常进行，因为`Integer`值可以转换为`Double`而不丢失数据。</span><span class="sxs-lookup"><span data-stu-id="61822-169">For example, if you try to add an `Integer` variable to a `Double` variable and assign the value to a `Double` variable, the operation proceeds normally, because an `Integer` value can be converted to `Double` without loss of data.</span></span> <span data-ttu-id="61822-170">类型不安全的转换，另一方面，导致编译器错误与`Option Strict On`。</span><span class="sxs-lookup"><span data-stu-id="61822-170">Type-unsafe conversions, on the other hand, cause a compiler error with `Option Strict On`.</span></span> <span data-ttu-id="61822-171">例如，如果你尝试添加`Integer`变量`Double`变量并将值赋给`Integer`变量时，会导致编译器错误，因为`Double`变量不能隐式转换为键入`Integer`。</span><span class="sxs-lookup"><span data-stu-id="61822-171">For example, if you try to add an `Integer` variable to a `Double` variable and assign the value to an `Integer` variable, a compiler error results, because a `Double` variable cannot be implicitly converted to type `Integer`.</span></span>  
  
 <span data-ttu-id="61822-172">如果您设置`Option Strict Off`，但[!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]允许隐式收缩转换完成，但是它们可能会导致意外丢失的数据或精度。</span><span class="sxs-lookup"><span data-stu-id="61822-172">If you set `Option Strict Off`, however, [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] allows implicit narrowing conversions to take place, although they can result in the unexpected loss of data or precision.</span></span> <span data-ttu-id="61822-173">出于此原因，我们建议你使用`Option Strict On`编写生产代码时。</span><span class="sxs-lookup"><span data-stu-id="61822-173">For this reason, we recommend that you use `Option Strict On` when writing production code.</span></span> <span data-ttu-id="61822-174">有关详细信息，请参阅[扩大和收缩转换](../../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md)。</span><span class="sxs-lookup"><span data-stu-id="61822-174">For more information, see [Widening and Narrowing Conversions](../../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="61822-175">另请参阅</span><span class="sxs-lookup"><span data-stu-id="61822-175">See Also</span></span>  
 <span data-ttu-id="61822-176">[算术运算符](../../../../visual-basic/language-reference/operators/arithmetic-operators.md) </span><span class="sxs-lookup"><span data-stu-id="61822-176">[Arithmetic Operators](../../../../visual-basic/language-reference/operators/arithmetic-operators.md) </span></span>  
<span data-ttu-id="61822-177"> [移位运算符](../../../../visual-basic/language-reference/operators/bit-shift-operators.md) </span><span class="sxs-lookup"><span data-stu-id="61822-177"> [Bit Shift Operators](../../../../visual-basic/language-reference/operators/bit-shift-operators.md) </span></span>  
<span data-ttu-id="61822-178"> [在 Visual Basic 中的比较运算符](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/comparison-operators.md) </span><span class="sxs-lookup"><span data-stu-id="61822-178"> [Comparison Operators in Visual Basic](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/comparison-operators.md) </span></span>  
<span data-ttu-id="61822-179"> [在 Visual Basic 中的串联运算符](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/concatenation-operators.md) </span><span class="sxs-lookup"><span data-stu-id="61822-179"> [Concatenation Operators in Visual Basic](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/concatenation-operators.md) </span></span>  
<span data-ttu-id="61822-180"> [在 Visual Basic 中的逻辑和按位运算符](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/logical-and-bitwise-operators.md) </span><span class="sxs-lookup"><span data-stu-id="61822-180"> [Logical and Bitwise Operators in Visual Basic](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/logical-and-bitwise-operators.md) </span></span>  
<span data-ttu-id="61822-181"> [运算符的有效组合](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/efficient-combination-of-operators.md)</span><span class="sxs-lookup"><span data-stu-id="61822-181"> [Efficient Combination of Operators](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/efficient-combination-of-operators.md)</span></span>
