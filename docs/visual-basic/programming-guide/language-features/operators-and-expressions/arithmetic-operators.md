---
title: 算术运算符 (Visual Basic)
ms.custom: ''
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- type safety
- operators [Visual Basic], bitwise
- operators [Visual Basic], bit-shift
- bitwise operators [Visual Basic]
- bit-shift operators [Visual Basic]
- zero, division by zero
- operators [Visual Basic], arithmetic
- division [Visual Basic], by zero
- Visual Basic code, operators
- arithmetic operators [Visual Basic], about arithmetic operators
ms.assetid: 325dac7a-ea4f-41d5-8b48-f6e904211569
caps.latest.revision: 20
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: cef1e3610d885a0f3a2bae718641f7b8ca1062dc
ms.sourcegitcommit: 86adcc06e35390f13c1e372c36d2e044f1fc31ef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/26/2018
---
# <a name="arithmetic-operators-in-visual-basic"></a><span data-ttu-id="d2432-102">算术运算符 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="d2432-102">Arithmetic Operators in Visual Basic</span></span>
<span data-ttu-id="d2432-103">算术运算符用于执行很多熟悉的算术运算，涉及计算的文本、 变量、 其他表达式、 函数和属性调用和常量所表示的数字值。</span><span class="sxs-lookup"><span data-stu-id="d2432-103">Arithmetic operators are used to perform many of the familiar arithmetic operations that involve the calculation of numeric values represented by literals, variables, other expressions, function and property calls, and constants.</span></span> <span data-ttu-id="d2432-104">算术运算符也属于是移位运算符，它们充当级别的单个位进行运算的操作数和向左或向右移动其位模式。</span><span class="sxs-lookup"><span data-stu-id="d2432-104">Also classified with arithmetic operators are the bit-shift operators, which act at the level of the individual bits of the operands and shift their bit patterns to the left or right.</span></span>  
  
## <a name="arithmetic-operations"></a><span data-ttu-id="d2432-105">算术运算</span><span class="sxs-lookup"><span data-stu-id="d2432-105">Arithmetic Operations</span></span>  
 <span data-ttu-id="d2432-106">你可以添加两个值一起使用的表达式中[+ 运算符](../../../../visual-basic/language-reference/operators/addition-operator.md)，或从另一个具有减去 1 [-运算符 (Visual Basic)](../../../../visual-basic/language-reference/operators/subtraction-operator.md)，如下面的示例所示。</span><span class="sxs-lookup"><span data-stu-id="d2432-106">You can add two values in an expression together with the [+ Operator](../../../../visual-basic/language-reference/operators/addition-operator.md), or subtract one from another with the [- Operator (Visual Basic)](../../../../visual-basic/language-reference/operators/subtraction-operator.md), as the following example demonstrates.</span></span>  
  
 [!code-vb[VbVbalrOperators#57](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/arithmetic-operators_1.vb)]  
  
 <span data-ttu-id="d2432-107">求反也使用[-运算符 (Visual Basic)](../../../../visual-basic/language-reference/operators/subtraction-operator.md)，但只带一个操作数，如下面的示例所示。</span><span class="sxs-lookup"><span data-stu-id="d2432-107">Negation also uses the [- Operator (Visual Basic)](../../../../visual-basic/language-reference/operators/subtraction-operator.md), but with only one operand, as the following example demonstrates.</span></span>  
  
 [!code-vb[VbVbalrOperators#58](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/arithmetic-operators_2.vb)]  
  
 <span data-ttu-id="d2432-108">乘法和除法使用[\* 运算符](../../../../visual-basic/language-reference/operators/multiplication-operator.md)和[/ 运算符 (Visual Basic)](../../../../visual-basic/language-reference/operators/floating-point-division-operator.md)分别，如以下示例所示。</span><span class="sxs-lookup"><span data-stu-id="d2432-108">Multiplication and division use the [\* Operator](../../../../visual-basic/language-reference/operators/multiplication-operator.md) and [/ Operator (Visual Basic)](../../../../visual-basic/language-reference/operators/floating-point-division-operator.md), respectively, as the following example demonstrates.</span></span>  
  
 [!code-vb[VbVbalrOperators#59](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/arithmetic-operators_3.vb)]  
  
 <span data-ttu-id="d2432-109">求幂使用[^ 运算符](../../../../visual-basic/language-reference/operators/exponentiation-operator.md)，如下面的示例所示。</span><span class="sxs-lookup"><span data-stu-id="d2432-109">Exponentiation uses the [^ Operator](../../../../visual-basic/language-reference/operators/exponentiation-operator.md), as the following example demonstrates.</span></span>  
  
 [!code-vb[VbVbalrOperators#60](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/arithmetic-operators_4.vb)]  
  
 <span data-ttu-id="d2432-110">整数除法执行使用[\ 运算符 (Visual Basic)](../../../../visual-basic/language-reference/operators/integer-division-operator.md)。</span><span class="sxs-lookup"><span data-stu-id="d2432-110">Integer division is carried out using the [\ Operator (Visual Basic)](../../../../visual-basic/language-reference/operators/integer-division-operator.md).</span></span> <span data-ttu-id="d2432-111">整数除法返回的商，即表示的次数的整数除数可以将划分为而无需考虑的任何其余部分被除数。</span><span class="sxs-lookup"><span data-stu-id="d2432-111">Integer division returns the quotient, that is, the integer that represents the number of times the divisor can divide into the dividend without consideration of any remainder.</span></span> <span data-ttu-id="d2432-112">除数和被除数必须是整数类型 (`SByte`， `Byte`， `Short`， `UShort`， `Integer`， `UInteger`， `Long`，和`ULong`) 为此运算符。</span><span class="sxs-lookup"><span data-stu-id="d2432-112">Both the divisor and the dividend must be integral types (`SByte`, `Byte`, `Short`, `UShort`, `Integer`, `UInteger`, `Long`, and `ULong`) for this operator.</span></span> <span data-ttu-id="d2432-113">必须首先将所有其他类型转换为整数类型。</span><span class="sxs-lookup"><span data-stu-id="d2432-113">All other types must be converted to an integral type first.</span></span> <span data-ttu-id="d2432-114">下面的示例演示整数除法。</span><span class="sxs-lookup"><span data-stu-id="d2432-114">The following example demonstrates integer division.</span></span>  
  
 [!code-vb[VbVbalrOperators#61](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/arithmetic-operators_5.vb)]  
  
 <span data-ttu-id="d2432-115">使用执行取模算术[Mod 运算符](../../../../visual-basic/language-reference/operators/mod-operator.md)。</span><span class="sxs-lookup"><span data-stu-id="d2432-115">Modulus arithmetic is performed using the [Mod Operator](../../../../visual-basic/language-reference/operators/mod-operator.md).</span></span> <span data-ttu-id="d2432-116">此运算符返回余数除数除以除数后的整数的次数。</span><span class="sxs-lookup"><span data-stu-id="d2432-116">This operator returns the remainder after dividing the divisor into the dividend an integral number of times.</span></span> <span data-ttu-id="d2432-117">如果除数和被除数是整型类型，则返回的值是整数。</span><span class="sxs-lookup"><span data-stu-id="d2432-117">If both divisor and dividend are integral types, the returned value is integral.</span></span> <span data-ttu-id="d2432-118">如果除数和被除数是浮点类型，返回的值也是浮点。</span><span class="sxs-lookup"><span data-stu-id="d2432-118">If divisor and dividend are floating-point types, the returned value is also floating-point.</span></span> <span data-ttu-id="d2432-119">下面的示例演示此行为。</span><span class="sxs-lookup"><span data-stu-id="d2432-119">The following example demonstrates this behavior.</span></span>  
  
 [!code-vb[VbVbalrOperators#62](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/arithmetic-operators_6.vb)]  
  
 [!code-vb[VbVbalrOperators#63](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/arithmetic-operators_7.vb)]  
  
### <a name="attempted-division-by-zero"></a><span data-ttu-id="d2432-120">尝试的除数为零</span><span class="sxs-lookup"><span data-stu-id="d2432-120">Attempted Division by Zero</span></span>  
 <span data-ttu-id="d2432-121">被零除会得到不同的结果，具体取决于涉及的数据类型。</span><span class="sxs-lookup"><span data-stu-id="d2432-121">Division by zero has different results depending on the data types involved.</span></span> <span data-ttu-id="d2432-122">整型部门中 (`SByte`， `Byte`， `Short`， `UShort`， `Integer`， `UInteger`， `Long`， `ULong`)，则[!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)]引发<xref:System.DivideByZeroException>异常。</span><span class="sxs-lookup"><span data-stu-id="d2432-122">In integral divisions (`SByte`, `Byte`, `Short`, `UShort`, `Integer`, `UInteger`, `Long`, `ULong`), the [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] throws a <xref:System.DivideByZeroException> exception.</span></span> <span data-ttu-id="d2432-123">在除法运算`Decimal`或`Single`数据类型，[!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)]也会引发<xref:System.DivideByZeroException>异常。</span><span class="sxs-lookup"><span data-stu-id="d2432-123">In division operations on the `Decimal` or `Single` data type, the [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] also throws a <xref:System.DivideByZeroException> exception.</span></span>  
  
 <span data-ttu-id="d2432-124">涉及的浮点部门中`Double`数据类型，不会引发异常，并且结果是表示的类成员<xref:System.Double.NaN>， <xref:System.Double.PositiveInfinity>，或<xref:System.Double.NegativeInfinity>，取决于被除数。</span><span class="sxs-lookup"><span data-stu-id="d2432-124">In floating-point divisions involving the `Double` data type, no exception is thrown, and the result is the class member representing <xref:System.Double.NaN>, <xref:System.Double.PositiveInfinity>, or <xref:System.Double.NegativeInfinity>, depending on the dividend.</span></span> <span data-ttu-id="d2432-125">下表汇总了尝试将划分的各种结果`Double`被零的值。</span><span class="sxs-lookup"><span data-stu-id="d2432-125">The following table summarizes the various results of attempting to divide a `Double` value by zero.</span></span>  
  
|<span data-ttu-id="d2432-126">被除数数据类型</span><span class="sxs-lookup"><span data-stu-id="d2432-126">Dividend data type</span></span>|<span data-ttu-id="d2432-127">除数数据类型</span><span class="sxs-lookup"><span data-stu-id="d2432-127">Divisor data type</span></span>|<span data-ttu-id="d2432-128">被除数的值</span><span class="sxs-lookup"><span data-stu-id="d2432-128">Dividend value</span></span>|<span data-ttu-id="d2432-129">结果</span><span class="sxs-lookup"><span data-stu-id="d2432-129">Result</span></span>|  
|---|---|---|---|  
|`Double`|`Double`|<span data-ttu-id="d2432-130">0</span><span class="sxs-lookup"><span data-stu-id="d2432-130">0</span></span>|<span data-ttu-id="d2432-131"><xref:System.Double.NaN> （不是数学上定义的数字）</span><span class="sxs-lookup"><span data-stu-id="d2432-131"><xref:System.Double.NaN> (not a mathematically defined number)</span></span>|  
|`Double`|`Double`|<span data-ttu-id="d2432-132">> 0</span><span class="sxs-lookup"><span data-stu-id="d2432-132">> 0</span></span>|<xref:System.Double.PositiveInfinity>|  
|`Double`|`Double`|<span data-ttu-id="d2432-133">\< 0</span><span class="sxs-lookup"><span data-stu-id="d2432-133">\< 0</span></span>|<xref:System.Double.NegativeInfinity>|  
  
 <span data-ttu-id="d2432-134">当捕获<xref:System.DivideByZeroException>异常，你可以使用其成员来帮助你处理它。</span><span class="sxs-lookup"><span data-stu-id="d2432-134">When you catch a <xref:System.DivideByZeroException> exception, you can use its members to help you handle it.</span></span> <span data-ttu-id="d2432-135">例如，<xref:System.Exception.Message%2A>属性包含异常的消息文本。</span><span class="sxs-lookup"><span data-stu-id="d2432-135">For example, the <xref:System.Exception.Message%2A> property holds the message text for the exception.</span></span> <span data-ttu-id="d2432-136">有关详细信息，请参阅 [Try...Catch...Finally 语句](../../../../visual-basic/language-reference/statements/try-catch-finally-statement.md)。</span><span class="sxs-lookup"><span data-stu-id="d2432-136">For more information, see [Try...Catch...Finally Statement](../../../../visual-basic/language-reference/statements/try-catch-finally-statement.md).</span></span>  
  
## <a name="bit-shift-operations"></a><span data-ttu-id="d2432-137">移位运算</span><span class="sxs-lookup"><span data-stu-id="d2432-137">Bit-Shift Operations</span></span>  
 <span data-ttu-id="d2432-138">移位操作对位模式执行算术移位运算。</span><span class="sxs-lookup"><span data-stu-id="d2432-138">A bit-shift operation performs an arithmetic shift on a bit pattern.</span></span> <span data-ttu-id="d2432-139">而右侧操作数中指定的位置，若要将切换模式数，在左侧，操作数中包含模式。</span><span class="sxs-lookup"><span data-stu-id="d2432-139">The pattern is contained in the operand on the left, while the operand on the right specifies the number of positions to shift the pattern.</span></span> <span data-ttu-id="d2432-140">你可以向与右上移模式[>> 运算符](../../../../visual-basic/language-reference/operators/right-shift-operator.md)或左侧[<< 运算符](../../../../visual-basic/language-reference/operators/left-shift-operator.md)。</span><span class="sxs-lookup"><span data-stu-id="d2432-140">You can shift the pattern to the right with the [>> Operator](../../../../visual-basic/language-reference/operators/right-shift-operator.md) or to the left with the [<< Operator](../../../../visual-basic/language-reference/operators/left-shift-operator.md).</span></span>  
  
 <span data-ttu-id="d2432-141">模式操作数的数据类型必须是`SByte`， `Byte`， `Short`， `UShort`， `Integer`， `UInteger`， `Long`，或`ULong`。</span><span class="sxs-lookup"><span data-stu-id="d2432-141">The data type of the pattern operand must be `SByte`, `Byte`, `Short`, `UShort`, `Integer`, `UInteger`, `Long`, or `ULong`.</span></span> <span data-ttu-id="d2432-142">Shift 量操作数的数据类型必须是`Integer`或必须扩大到`Integer`。</span><span class="sxs-lookup"><span data-stu-id="d2432-142">The data type of the shift amount operand must be `Integer` or must widen to `Integer`.</span></span>  
  
 <span data-ttu-id="d2432-143">算术移位不是循环，这意味着移出结果的一个 end 的数位另一端不重新移入。</span><span class="sxs-lookup"><span data-stu-id="d2432-143">Arithmetic shifts are not circular, which means the bits shifted off one end of the result are not reintroduced at the other end.</span></span> <span data-ttu-id="d2432-144">因 shift 空出的位设置，如下所示：</span><span class="sxs-lookup"><span data-stu-id="d2432-144">The bit positions vacated by a shift are set as follows:</span></span>  
  
-   <span data-ttu-id="d2432-145">算术左移位运算的 0</span><span class="sxs-lookup"><span data-stu-id="d2432-145">0 for an arithmetic left shift</span></span>  
  
-   <span data-ttu-id="d2432-146">0 表示算术右移位运算的正数值</span><span class="sxs-lookup"><span data-stu-id="d2432-146">0 for an arithmetic right shift of a positive number</span></span>  
  
-   <span data-ttu-id="d2432-147">0 表示无符号的数据类型的算术右移位 (`Byte`， `UShort`， `UInteger`， `ULong`)</span><span class="sxs-lookup"><span data-stu-id="d2432-147">0 for an arithmetic right shift of an unsigned data type (`Byte`, `UShort`, `UInteger`, `ULong`)</span></span>  
  
-   <span data-ttu-id="d2432-148">1 表示负数算术右移位 (`SByte`， `Short`， `Integer`，或`Long`)</span><span class="sxs-lookup"><span data-stu-id="d2432-148">1 for an arithmetic right shift of a negative number (`SByte`, `Short`, `Integer`, or `Long`)</span></span>  
  
 <span data-ttu-id="d2432-149">下面的示例会转而`Integer`值左侧和右侧。</span><span class="sxs-lookup"><span data-stu-id="d2432-149">The following example shifts an `Integer` value both left and right.</span></span>  
  
 [!code-vb[VbVbalrOperators#64](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/arithmetic-operators_8.vb)]  
  
 <span data-ttu-id="d2432-150">算术移位永远不会生成溢出异常。</span><span class="sxs-lookup"><span data-stu-id="d2432-150">Arithmetic shifts never generate overflow exceptions.</span></span>  
  
## <a name="bitwise-operations"></a><span data-ttu-id="d2432-151">按位运算</span><span class="sxs-lookup"><span data-stu-id="d2432-151">Bitwise Operations</span></span>  
 <span data-ttu-id="d2432-152">除了成为逻辑运算符， `Not`， `Or`， `And`，和`Xor`还执行按位算术运算在数值中使用时。</span><span class="sxs-lookup"><span data-stu-id="d2432-152">In addition to being logical operators, `Not`, `Or`, `And`, and `Xor` also perform bitwise arithmetic when used on numeric values.</span></span> <span data-ttu-id="d2432-153">有关详细信息，请参阅"按位运算"[逻辑和按位运算符在 Visual Basic 中](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/logical-and-bitwise-operators.md)。</span><span class="sxs-lookup"><span data-stu-id="d2432-153">For more information, see "Bitwise Operations" in [Logical and Bitwise Operators in Visual Basic](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/logical-and-bitwise-operators.md).</span></span>  
  
## <a name="type-safety"></a><span data-ttu-id="d2432-154">类型安全</span><span class="sxs-lookup"><span data-stu-id="d2432-154">Type Safety</span></span>  
 <span data-ttu-id="d2432-155">操作数通常应是类型的相同。</span><span class="sxs-lookup"><span data-stu-id="d2432-155">Operands should normally be of the same type.</span></span> <span data-ttu-id="d2432-156">例如，如果你正在添加`Integer`变量，你应将其添加到另一个`Integer`变量，并且你应将结果赋给变量的类型`Integer`以及。</span><span class="sxs-lookup"><span data-stu-id="d2432-156">For example, if you are doing addition with an `Integer` variable, you should add it to another `Integer` variable, and you should assign the result to a variable of type `Integer` as well.</span></span>  
  
 <span data-ttu-id="d2432-157">一种方法以确保良好的类型安全编码做法是使用[Option Strict 语句](../../../../visual-basic/language-reference/statements/option-strict-statement.md)。</span><span class="sxs-lookup"><span data-stu-id="d2432-157">One way to ensure good type-safe coding practice is to use the [Option Strict Statement](../../../../visual-basic/language-reference/statements/option-strict-statement.md).</span></span> <span data-ttu-id="d2432-158">如果你设置`Option Strict On`，Visual Basic 会自动执行*类型安全*转换。</span><span class="sxs-lookup"><span data-stu-id="d2432-158">If you set `Option Strict On`, Visual Basic automatically performs *type-safe* conversions.</span></span> <span data-ttu-id="d2432-159">例如，如果你尝试添加`Integer`变量`Double`变量并将值赋给`Double`变量，该操作将正常进行，因为`Integer`值可以转换为`Double`而不会丢失数据。</span><span class="sxs-lookup"><span data-stu-id="d2432-159">For example, if you try to add an `Integer` variable to a `Double` variable and assign the value to a `Double` variable, the operation proceeds normally, because an `Integer` value can be converted to `Double` without loss of data.</span></span> <span data-ttu-id="d2432-160">类型不安全的转换，另一方面，导致编译器错误与`Option Strict On`。</span><span class="sxs-lookup"><span data-stu-id="d2432-160">Type-unsafe conversions, on the other hand, cause a compiler error with `Option Strict On`.</span></span> <span data-ttu-id="d2432-161">例如，如果你尝试添加`Integer`变量`Double`变量并将值赋给`Integer`变量，会导致编译器错误，因为`Double`变量不能隐式转换为类型`Integer`。</span><span class="sxs-lookup"><span data-stu-id="d2432-161">For example, if you try to add an `Integer` variable to a `Double` variable and assign the value to an `Integer` variable, a compiler error results, because a `Double` variable cannot be implicitly converted to type `Integer`.</span></span>  
  
 <span data-ttu-id="d2432-162">如果你设置`Option Strict Off`，但是，Visual Basic 将允许隐式收缩转换完成，尽管它们会导致意外丢失数据或精度。</span><span class="sxs-lookup"><span data-stu-id="d2432-162">If you set `Option Strict Off`, however, Visual Basic allows implicit narrowing conversions to take place, although they can result in the unexpected loss of data or precision.</span></span> <span data-ttu-id="d2432-163">为此，我们建议你使用`Option Strict On`编写生产代码时。</span><span class="sxs-lookup"><span data-stu-id="d2432-163">For this reason, we recommend that you use `Option Strict On` when writing production code.</span></span> <span data-ttu-id="d2432-164">有关详细信息，请参阅 [Widening and Narrowing Conversions](../../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md)。</span><span class="sxs-lookup"><span data-stu-id="d2432-164">For more information, see [Widening and Narrowing Conversions](../../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d2432-165">请参阅</span><span class="sxs-lookup"><span data-stu-id="d2432-165">See Also</span></span>  
 [<span data-ttu-id="d2432-166">算术运算符</span><span class="sxs-lookup"><span data-stu-id="d2432-166">Arithmetic Operators</span></span>](../../../../visual-basic/language-reference/operators/arithmetic-operators.md)  
 [<span data-ttu-id="d2432-167">移位运算符</span><span class="sxs-lookup"><span data-stu-id="d2432-167">Bit Shift Operators</span></span>](../../../../visual-basic/language-reference/operators/bit-shift-operators.md)  
 [<span data-ttu-id="d2432-168">在 Visual Basic 中的比较运算符</span><span class="sxs-lookup"><span data-stu-id="d2432-168">Comparison Operators in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/comparison-operators.md)  
 [<span data-ttu-id="d2432-169">在 Visual Basic 中的串联运算符</span><span class="sxs-lookup"><span data-stu-id="d2432-169">Concatenation Operators in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/concatenation-operators.md)  
 [<span data-ttu-id="d2432-170">在 Visual Basic 中的逻辑和按位运算符</span><span class="sxs-lookup"><span data-stu-id="d2432-170">Logical and Bitwise Operators in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/logical-and-bitwise-operators.md)  
 [<span data-ttu-id="d2432-171">运算符的有效组合</span><span class="sxs-lookup"><span data-stu-id="d2432-171">Efficient Combination of Operators</span></span>](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/efficient-combination-of-operators.md)
