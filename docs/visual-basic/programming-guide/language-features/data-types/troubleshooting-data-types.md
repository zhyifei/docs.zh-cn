---
title: "数据类型疑难解答 (Visual Basic) |Microsoft 文档"
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
- Char data type, converting
- Decimal data type, conversions
- data types [Visual Basic], troubleshooting
- literals, default types
- type characters, literal
- Mod operator [Visual Basic], in floating-point operations
- troubleshooting Visual Basic, data types
- troubleshooting data types
- floating-point numbers, precision
- Boolean data type, converting
- literal types
- literal type characters
- floating-point numbers, imprecision
- String data type, converting
- floating-point numbers, comparison
- floating-point numbers
ms.assetid: 90040d67-b630-4125-a6ae-37195b079042
caps.latest.revision: 29
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
ms.openlocfilehash: 7ac7dfbda8c39024fc0aa07c9830d70b3a566e50
ms.contentlocale: zh-cn
ms.lasthandoff: 04/12/2017

---
# <a name="troubleshooting-data-types-visual-basic"></a><span data-ttu-id="06d21-102">数据类型疑难解答 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="06d21-102">Troubleshooting Data Types (Visual Basic)</span></span>
<span data-ttu-id="06d21-103">此页列出了对内部数据类型执行操作时可能会出现一些常见问题。</span><span class="sxs-lookup"><span data-stu-id="06d21-103">This page lists some common problems that can occur when you perform operations on intrinsic data types.</span></span>  
  
## <a name="floating-point-expressions-do-not-compare-as-equal"></a><span data-ttu-id="06d21-104">浮点表达式不相等比较</span><span class="sxs-lookup"><span data-stu-id="06d21-104">Floating-Point Expressions Do Not Compare as Equal</span></span>  
 <span data-ttu-id="06d21-105">当您处理使用浮点数 ([单一数据类型](../../../../visual-basic/language-reference/data-types/single-data-type.md)和[Double 数据类型](../../../../visual-basic/language-reference/data-types/double-data-type.md))，请记住它们存储为二进制分数的形式。</span><span class="sxs-lookup"><span data-stu-id="06d21-105">When you work with floating-point numbers ([Single Data Type](../../../../visual-basic/language-reference/data-types/single-data-type.md) and [Double Data Type](../../../../visual-basic/language-reference/data-types/double-data-type.md)), remember that they are stored as binary fractions.</span></span> <span data-ttu-id="06d21-106">这意味着它们不能存储不是二进制分数任何数量的准确表示形式 (窗体 k / (2 ^ n) 其中 k 和 n 为整数)。</span><span class="sxs-lookup"><span data-stu-id="06d21-106">This means they cannot hold an exact representation of any quantity that is not a binary fraction (of the form k / (2 ^ n) where k and n are integers).</span></span> <span data-ttu-id="06d21-107">例如，0.5 （= 1/2） 和 0.3125 （= 5/16） 可以保存为精确值，而 （= 1/5） 的 0.2 和 0.3 （= 3/10） 只能是近似值。</span><span class="sxs-lookup"><span data-stu-id="06d21-107">For example, 0.5 (= 1/2) and 0.3125 (= 5/16) can be held as precise values, whereas 0.2 (= 1/5) and 0.3 (= 3/10) can be only approximations.</span></span>  
  
 <span data-ttu-id="06d21-108">由于这不精确，您不能依赖精确的结果在浮点值上运行时。</span><span class="sxs-lookup"><span data-stu-id="06d21-108">Because of this imprecision, you cannot rely on exact results when you operate on floating-point values.</span></span> <span data-ttu-id="06d21-109">特别是，理论上相等的两个值可能必须稍有不同的表示形式。</span><span class="sxs-lookup"><span data-stu-id="06d21-109">In particular, two values that are theoretically equal might have slightly different representations.</span></span>  
  
| <span data-ttu-id="06d21-110">若要将浮点数进行比较</span><span class="sxs-lookup"><span data-stu-id="06d21-110">To compare floating-point quantities</span></span> | 
|---| 
|<span data-ttu-id="06d21-111">1.使用计算它们的差的绝对值<xref:System.Math.Abs%2A>方法<xref:System.Math>类<xref:System>命名空间。</xref:System> </xref:System.Math> </xref:System.Math.Abs%2A></span><span class="sxs-lookup"><span data-stu-id="06d21-111">1.  Calculate the absolute value of their difference by using the <xref:System.Math.Abs%2A> method of the <xref:System.Math> class in the <xref:System> namespace.</span></span><br /><span data-ttu-id="06d21-112">2.确定可接受的最大差值，以便您可以考虑进行相等实用的角度而言如果它们的差不大于这两个数量。</span><span class="sxs-lookup"><span data-stu-id="06d21-112">2.  Determine an acceptable maximum difference, such that you can consider the two quantities to be equal for practical purposes if their difference is no larger.</span></span><br /><span data-ttu-id="06d21-113">3.将为可接受的差值差的绝对值的数值进行比较。</span><span class="sxs-lookup"><span data-stu-id="06d21-113">3.  Compare the absolute value of the difference to the acceptable difference.</span></span>|  
  
 <span data-ttu-id="06d21-114">下面的示例演示两个错误用法和正确比较`Double`值。</span><span class="sxs-lookup"><span data-stu-id="06d21-114">The following example demonstrates both incorrect and correct comparison of two `Double` values.</span></span>  
  
 <span data-ttu-id="06d21-115">[!code-vb[VbVbalrDataTypes #&10;](../../../../visual-basic/language-reference/data-types/codesnippet/VisualBasic/troubleshooting-data-types_1.vb)]</span><span class="sxs-lookup"><span data-stu-id="06d21-115">[!code-vb[VbVbalrDataTypes#10](../../../../visual-basic/language-reference/data-types/codesnippet/VisualBasic/troubleshooting-data-types_1.vb)]</span></span>  
  
 <span data-ttu-id="06d21-116">前面的示例使用<xref:System.Double.ToString%2A>方法<xref:System.Double>结构，以便它可以指定精度优于`CStr`关键字使用。</xref:System.Double> </xref:System.Double.ToString%2A></span><span class="sxs-lookup"><span data-stu-id="06d21-116">The previous example uses the <xref:System.Double.ToString%2A> method of the <xref:System.Double> structure so that it can specify better  precision than the `CStr` keyword uses.</span></span> <span data-ttu-id="06d21-117">默认值为 15 位数字，但是"G17"格式将其扩展为 17 个数位。</span><span class="sxs-lookup"><span data-stu-id="06d21-117">The default is 15 digits, but the "G17" format extends it to 17 digits.</span></span>  
  
## <a name="mod-operator-does-not-return-accurate-result"></a><span data-ttu-id="06d21-118">Mod 运算符不返回准确的结果</span><span class="sxs-lookup"><span data-stu-id="06d21-118">Mod Operator Does Not Return Accurate Result</span></span>  
 <span data-ttu-id="06d21-119">由于不精确的浮点存储[Mod 运算符](../../../../visual-basic/language-reference/operators/mod-operator.md)可以在至少其中一个操作数为浮点数时返回了意外的结果。</span><span class="sxs-lookup"><span data-stu-id="06d21-119">Because of the imprecision of floating-point storage, the [Mod Operator](../../../../visual-basic/language-reference/operators/mod-operator.md) can return an unexpected result when at least one of the operands is floating-point.</span></span>  
  
 <span data-ttu-id="06d21-120">[Decimal 数据类型](../../../../visual-basic/language-reference/data-types/decimal-data-type.md)不使用浮点表示形式。</span><span class="sxs-lookup"><span data-stu-id="06d21-120">The [Decimal Data Type](../../../../visual-basic/language-reference/data-types/decimal-data-type.md) does not use floating-point representation.</span></span> <span data-ttu-id="06d21-121">在不精确的许多数字`Single`和`Double`中精确`Decimal`（例如 0.2 和 0.3）。</span><span class="sxs-lookup"><span data-stu-id="06d21-121">Many numbers that are inexact in `Single` and `Double` are exact in `Decimal` (for example 0.2 and 0.3).</span></span> <span data-ttu-id="06d21-122">尽管算术中要慢`Decimal`比在浮点数，但可能值得性能的下降来实现更好的精度。</span><span class="sxs-lookup"><span data-stu-id="06d21-122">Although arithmetic is slower in `Decimal` than in floating-point, it might be worth the performance decrease to achieve better precision.</span></span>  
  
|<span data-ttu-id="06d21-123">若要查找的浮点数的整数余数</span><span class="sxs-lookup"><span data-stu-id="06d21-123">To find the integer remainder of floating-point quantities</span></span>|  
|---|  
|<span data-ttu-id="06d21-124">1.将变量声明为`Decimal`。</span><span class="sxs-lookup"><span data-stu-id="06d21-124">1.  Declare variables as `Decimal`.</span></span><br /><span data-ttu-id="06d21-125">2.使用文本类型字符`D`强制转换为`Decimal`，以防它们的值太大，`Long`数据类型。</span><span class="sxs-lookup"><span data-stu-id="06d21-125">2.  Use the literal type character `D` to force literals to `Decimal`, in case their values are too large for the `Long` data type.</span></span>|  
  
 <span data-ttu-id="06d21-126">下面的示例演示了潜在的浮点操作数不精确性。</span><span class="sxs-lookup"><span data-stu-id="06d21-126">The following example demonstrates the potential imprecision of floating-point operands.</span></span>  
  
 <span data-ttu-id="06d21-127">[!code-vb[VbVbalrDataTypes #&11;](../../../../visual-basic/language-reference/data-types/codesnippet/VisualBasic/troubleshooting-data-types_2.vb)]</span><span class="sxs-lookup"><span data-stu-id="06d21-127">[!code-vb[VbVbalrDataTypes#11](../../../../visual-basic/language-reference/data-types/codesnippet/VisualBasic/troubleshooting-data-types_2.vb)]</span></span>  
  
 <span data-ttu-id="06d21-128">前面的示例使用<xref:System.Double.ToString%2A>方法<xref:System.Double>结构，以便它可以指定精度优于`CStr`关键字使用。</xref:System.Double> </xref:System.Double.ToString%2A></span><span class="sxs-lookup"><span data-stu-id="06d21-128">The previous example uses the <xref:System.Double.ToString%2A> method of the <xref:System.Double> structure so that it can specify better precision than the `CStr` keyword uses.</span></span> <span data-ttu-id="06d21-129">默认值为 15 位数字，但是"G17"格式将其扩展为 17 个数位。</span><span class="sxs-lookup"><span data-stu-id="06d21-129">The default is 15 digits, but the "G17" format extends it to 17 digits.</span></span>  
  
 <span data-ttu-id="06d21-130">因为`zeroPointTwo`是`Double`，它表示的 0.2 已存储的值是为 0.20000000000000001 的无限重复二进制小数。</span><span class="sxs-lookup"><span data-stu-id="06d21-130">Because `zeroPointTwo` is `Double`, its value for 0.2 is an infinitely repeating binary fraction with a stored value of 0.20000000000000001.</span></span> <span data-ttu-id="06d21-131">此数量的值除以 2.0 将得到 9.9999999999999995，余数为 0.19999999999999991。</span><span class="sxs-lookup"><span data-stu-id="06d21-131">Dividing 2.0 by this quantity yields 9.9999999999999995 with a remainder of 0.19999999999999991.</span></span>  
  
 <span data-ttu-id="06d21-132">中的表达式`decimalRemainder`，文本类型字符`D`强制的两个操作数`Decimal`，，0.2 具有精确的表示形式。</span><span class="sxs-lookup"><span data-stu-id="06d21-132">In the expression for `decimalRemainder`, the literal type character `D` forces both operands to `Decimal`, and 0.2 has a precise representation.</span></span> <span data-ttu-id="06d21-133">因此`Mod`运算符产生预期的余数 0.0。</span><span class="sxs-lookup"><span data-stu-id="06d21-133">Therefore the `Mod` operator yields the expected remainder of 0.0.</span></span>  
  
 <span data-ttu-id="06d21-134">请注意，不不足，无法声明`decimalRemainder`作为`Decimal`。</span><span class="sxs-lookup"><span data-stu-id="06d21-134">Note that it is not sufficient to declare `decimalRemainder` as `Decimal`.</span></span> <span data-ttu-id="06d21-135">您还必须强制文字到`Decimal`，或者它们使用`Double`默认情况下和`decimalRemainder`接收相同的不准确值`doubleRemainder`。</span><span class="sxs-lookup"><span data-stu-id="06d21-135">You must also force the literals to `Decimal`, or they use `Double` by default and `decimalRemainder` receives the same inaccurate value as `doubleRemainder`.</span></span>  
  
## <a name="boolean-type-does-not-convert-to-numeric-type-accurately"></a><span data-ttu-id="06d21-136">布尔值类型不会准确地转换为数值类型</span><span class="sxs-lookup"><span data-stu-id="06d21-136">Boolean Type Does Not Convert to Numeric Type Accurately</span></span>  
 <span data-ttu-id="06d21-137">[Boolean 数据类型](../../../../visual-basic/language-reference/data-types/boolean-data-type.md)值不会存储为数字，并且存储的值不应为等效于数字。</span><span class="sxs-lookup"><span data-stu-id="06d21-137">[Boolean Data Type](../../../../visual-basic/language-reference/data-types/boolean-data-type.md) values are not stored as numbers, and the stored values are not intended to be equivalent to numbers.</span></span> <span data-ttu-id="06d21-138">为了与早期版本中，兼容[!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]提供转换关键字 ([CType 函数](../../../../visual-basic/language-reference/functions/ctype-function.md)， `CBool`，`CInt`等) 之间进行转换`Boolean`与数值类型。</span><span class="sxs-lookup"><span data-stu-id="06d21-138">For compatibility with earlier versions, [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] provides conversion keywords ([CType Function](../../../../visual-basic/language-reference/functions/ctype-function.md), `CBool`, `CInt`, and so on) to convert between `Boolean` and numeric types.</span></span> <span data-ttu-id="06d21-139">但是，其他语言有时执行这些转换方式不同，请执行[!INCLUDE[dnprdnshort](../../../../csharp/getting-started/includes/dnprdnshort_md.md)]方法。</span><span class="sxs-lookup"><span data-stu-id="06d21-139">However, other languages sometimes perform these conversions differently, as do the [!INCLUDE[dnprdnshort](../../../../csharp/getting-started/includes/dnprdnshort_md.md)] methods.</span></span>  
  
 <span data-ttu-id="06d21-140">绝不应编写代码，它依赖于等效数值`True`和`False`。</span><span class="sxs-lookup"><span data-stu-id="06d21-140">You should never write code that relies on equivalent numeric values for `True` and `False`.</span></span> <span data-ttu-id="06d21-141">只要有可能，应限制使用`Boolean`变量来为其设计的逻辑值。</span><span class="sxs-lookup"><span data-stu-id="06d21-141">Whenever possible, you should restrict usage of `Boolean` variables to the logical values for which they are designed.</span></span> <span data-ttu-id="06d21-142">如果您需要混合`Boolean`和数字值，请确保您了解您选择的转换方法。</span><span class="sxs-lookup"><span data-stu-id="06d21-142">If you must mix `Boolean` and numeric values, make sure that you understand the conversion method that you select.</span></span>  
  
### <a name="conversion-in-visual-basic"></a><span data-ttu-id="06d21-143">在 Visual Basic 中的转换</span><span class="sxs-lookup"><span data-stu-id="06d21-143">Conversion in Visual Basic</span></span>  
 <span data-ttu-id="06d21-144">当您使用`CType`或`CBool`转换关键字，若要将数值数据类型转换`Boolean`，0 会变为`False`和所有其他值会变为`True`。</span><span class="sxs-lookup"><span data-stu-id="06d21-144">When you use the `CType` or `CBool` conversion keywords to convert numeric data types to `Boolean`, 0 becomes `False` and all other values become `True`.</span></span> <span data-ttu-id="06d21-145">转换时`Boolean`为数值类型时使用了转换的关键字值`False`变为 0 和`True`会变为-1。</span><span class="sxs-lookup"><span data-stu-id="06d21-145">When you convert `Boolean` values to numeric types by using the conversion keywords, `False` becomes 0 and `True` becomes -1.</span></span>  
  
### <a name="conversion-in-the-framework"></a><span data-ttu-id="06d21-146">框架中的转换</span><span class="sxs-lookup"><span data-stu-id="06d21-146">Conversion in the Framework</span></span>  
 <span data-ttu-id="06d21-147"><xref:System.Convert.ToInt32%2A>方法<xref:System.Convert>类<xref:System>命名空间将转换`True`为 +&1;。</xref:System> </xref:System.Convert> </xref:System.Convert.ToInt32%2A></span><span class="sxs-lookup"><span data-stu-id="06d21-147">The <xref:System.Convert.ToInt32%2A> method of the <xref:System.Convert> class in the <xref:System> namespace converts `True` to +1.</span></span>  
  
 <span data-ttu-id="06d21-148">如果必须将`Boolean`值为数值数据类型时，请小心使用转换方法。</span><span class="sxs-lookup"><span data-stu-id="06d21-148">If you must convert a `Boolean` value to a numeric data type, be careful about which conversion method you use.</span></span>  
  
## <a name="character-literal-generates-compiler-error"></a><span data-ttu-id="06d21-149">字符文本将生成编译器错误</span><span class="sxs-lookup"><span data-stu-id="06d21-149">Character Literal Generates Compiler Error</span></span>  
 <span data-ttu-id="06d21-150">在任何类型的字符，缺乏[!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]将采用默认的文本的数据类型。</span><span class="sxs-lookup"><span data-stu-id="06d21-150">In the absence of any type characters, [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] assumes default data types for literals.</span></span> <span data-ttu-id="06d21-151">默认类型为字符文本，用引号引起来 (`" "`) — 是`String`。</span><span class="sxs-lookup"><span data-stu-id="06d21-151">The default type for a character literal — enclosed in quotation marks (`" "`) — is `String`.</span></span>  
  
 <span data-ttu-id="06d21-152">`String`数据类型不会扩大到[Char 数据类型](../../../../visual-basic/language-reference/data-types/char-data-type.md)。</span><span class="sxs-lookup"><span data-stu-id="06d21-152">The `String` data type does not widen to the [Char Data Type](../../../../visual-basic/language-reference/data-types/char-data-type.md).</span></span> <span data-ttu-id="06d21-153">这意味着，如果你想要分配到一个文本`Char`变量时，必须进行收缩转换，或将文本强制转换到`Char`类型。</span><span class="sxs-lookup"><span data-stu-id="06d21-153">This means that if you want to assign a literal to a `Char` variable, you must either make a narrowing conversion or force the literal to the `Char` type.</span></span>  

|<span data-ttu-id="06d21-154">若要创建字符文本以将分配给变量或常量</span><span class="sxs-lookup"><span data-stu-id="06d21-154">To create a Char literal to assign to a variable or constant</span></span>|
|---|  
|<span data-ttu-id="06d21-155">1.声明的变量或常量作为`Char`。</span><span class="sxs-lookup"><span data-stu-id="06d21-155">1.  Declare the variable or constant as `Char`.</span></span><br /><span data-ttu-id="06d21-156">2.将字符值括在双引号 (`" "`)。</span><span class="sxs-lookup"><span data-stu-id="06d21-156">2.  Enclose the character value in quotation marks (`" "`).</span></span><br /><span data-ttu-id="06d21-157">3.请按照右双引号以文本类型字符`C`若要将文本强制转换到`Char`。</span><span class="sxs-lookup"><span data-stu-id="06d21-157">3.  Follow the closing double quotation mark with the literal type character `C` to force the literal to `Char`.</span></span> <span data-ttu-id="06d21-158">如果类型检查开关，则必须 ([Option Strict 语句](../../../../visual-basic/language-reference/statements/option-strict-statement.md)) 是`On`，而且希望在任何情况下。</span><span class="sxs-lookup"><span data-stu-id="06d21-158">This is necessary if the type checking switch ([Option Strict Statement](../../../../visual-basic/language-reference/statements/option-strict-statement.md)) is `On`, and it is desirable in any case.</span></span>|  
  
 <span data-ttu-id="06d21-159">下面的示例演示了将文本赋予的失败和成功分配`Char`变量。</span><span class="sxs-lookup"><span data-stu-id="06d21-159">The following example demonstrates both unsuccessful and successful assignments of a literal to a `Char` variable.</span></span>  
  
 <span data-ttu-id="06d21-160">[!code-vb[VbVbalrDataTypes #&12;](../../../../visual-basic/language-reference/data-types/codesnippet/VisualBasic/troubleshooting-data-types_3.vb)]</span><span class="sxs-lookup"><span data-stu-id="06d21-160">[!code-vb[VbVbalrDataTypes#12](../../../../visual-basic/language-reference/data-types/codesnippet/VisualBasic/troubleshooting-data-types_3.vb)]</span></span>  
  
 <span data-ttu-id="06d21-161">始终存在风险中没有使用收缩转换，因为它们可以在运行时失败。</span><span class="sxs-lookup"><span data-stu-id="06d21-161">There is always a risk in using narrowing conversions, because they can fail at run time.</span></span> <span data-ttu-id="06d21-162">例如，从转换`String`到`Char`如果可能会失败`String`值包含多个字符。</span><span class="sxs-lookup"><span data-stu-id="06d21-162">For example, a conversion from `String` to `Char` can fail if the `String` value contains more than one character.</span></span> <span data-ttu-id="06d21-163">因此，在编程时最好使用`C`键入字符。</span><span class="sxs-lookup"><span data-stu-id="06d21-163">Therefore, it is better programming to use the `C` type character.</span></span>  
  
## <a name="string-conversion-fails-at-run-time"></a><span data-ttu-id="06d21-164">字符串转换在运行时失败</span><span class="sxs-lookup"><span data-stu-id="06d21-164">String Conversion Fails at Run Time</span></span>  
 <span data-ttu-id="06d21-165">[字符串数据类型](../../../../visual-basic/language-reference/data-types/string-data-type.md)参与了很少的扩大转换。</span><span class="sxs-lookup"><span data-stu-id="06d21-165">The [String Data Type](../../../../visual-basic/language-reference/data-types/string-data-type.md) participates in very few widening conversions.</span></span> <span data-ttu-id="06d21-166">`String`扩大到自身和`Object`，和仅`Char`和`Char()`(`Char`数组) 扩大到`String`。</span><span class="sxs-lookup"><span data-stu-id="06d21-166">`String` widens only to itself and `Object`, and only `Char` and `Char()` (a `Char` array) widen to `String`.</span></span> <span data-ttu-id="06d21-167">这是因为`String`变量和常量可以包含其他数据类型不能包含的值。</span><span class="sxs-lookup"><span data-stu-id="06d21-167">This is because `String` variables and constants can contain values that other data types cannot contain.</span></span>  
  
 <span data-ttu-id="06d21-168">类型检查开关 ([Option Strict 语句](../../../../visual-basic/language-reference/statements/option-strict-statement.md)) 是`On`，编译器不允许所有隐式收缩转换。</span><span class="sxs-lookup"><span data-stu-id="06d21-168">When the type checking switch ([Option Strict Statement](../../../../visual-basic/language-reference/statements/option-strict-statement.md)) is `On`, the compiler disallows all implicit narrowing conversions.</span></span> <span data-ttu-id="06d21-169">这包括涉及`String`。</span><span class="sxs-lookup"><span data-stu-id="06d21-169">This includes those involving `String`.</span></span> <span data-ttu-id="06d21-170">您的代码仍可以使用转换关键字如`CStr`和[CType 函数](../../../../visual-basic/language-reference/functions/ctype-function.md)，以指示[!INCLUDE[dnprdnshort](../../../../csharp/getting-started/includes/dnprdnshort_md.md)]尝试进行转换。</span><span class="sxs-lookup"><span data-stu-id="06d21-170">Your code can still use conversion keywords such as `CStr` and [CType Function](../../../../visual-basic/language-reference/functions/ctype-function.md), which direct the [!INCLUDE[dnprdnshort](../../../../csharp/getting-started/includes/dnprdnshort_md.md)] to attempt the conversion.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="06d21-171">收缩转换错误则会取消对转换中的元素从`For Each…Next`循环控制变量的集合。</span><span class="sxs-lookup"><span data-stu-id="06d21-171">The narrowing-conversion error is suppressed for conversions from the elements in a `For Each…Next` collection to the loop control variable.</span></span> <span data-ttu-id="06d21-172">有关详细信息和示例，请参阅中的"收缩转换"一节[为每个...下一条语句](../../../../visual-basic/language-reference/statements/for-each-next-statement.md)。</span><span class="sxs-lookup"><span data-stu-id="06d21-172">For more information and examples, see the "Narrowing Conversions" section in [For Each...Next Statement](../../../../visual-basic/language-reference/statements/for-each-next-statement.md).</span></span>  
  
### <a name="narrowing-conversion-protection"></a><span data-ttu-id="06d21-173">收缩转换保护</span><span class="sxs-lookup"><span data-stu-id="06d21-173">Narrowing Conversion Protection</span></span>  
 <span data-ttu-id="06d21-174">收缩转换的缺点是它们可能会在运行时失败。</span><span class="sxs-lookup"><span data-stu-id="06d21-174">The disadvantage of narrowing conversions is that they can fail at run time.</span></span> <span data-ttu-id="06d21-175">例如，如果`String`变量包含的任何内容而不是"True"或"False，"它不能转换为`Boolean`。</span><span class="sxs-lookup"><span data-stu-id="06d21-175">For example, if a `String` variable contains anything other than "True" or "False," it cannot be converted to `Boolean`.</span></span> <span data-ttu-id="06d21-176">如果它包含标点字符，为任何数值类型的转换将失败。</span><span class="sxs-lookup"><span data-stu-id="06d21-176">If it contains punctuation characters, conversion to any numeric type fails.</span></span> <span data-ttu-id="06d21-177">除非您知道您`String`变量始终保存目标类型可以接受的值，否则不应尝试进行转换。</span><span class="sxs-lookup"><span data-stu-id="06d21-177">Unless you know that your `String` variable always holds values that the destination type can accept, you should not try a conversion.</span></span>  
  
 <span data-ttu-id="06d21-178">如果必须从转换`String`最安全的过程是将在尝试的转换为另一个数据类型，[重试...Catch...Finally 语句](../../../../visual-basic/language-reference/statements/try-catch-finally-statement.md)。</span><span class="sxs-lookup"><span data-stu-id="06d21-178">If you must convert from `String` to another data type, the safest procedure is to enclose the attempted conversion in the [Try...Catch...Finally Statement](../../../../visual-basic/language-reference/statements/try-catch-finally-statement.md).</span></span> <span data-ttu-id="06d21-179">这样就可以处理运行时故障。</span><span class="sxs-lookup"><span data-stu-id="06d21-179">This lets you deal with a run-time failure.</span></span>  
  
### <a name="character-arrays"></a><span data-ttu-id="06d21-180">字符数组</span><span class="sxs-lookup"><span data-stu-id="06d21-180">Character Arrays</span></span>  
 <span data-ttu-id="06d21-181">单个`Char`和数组`Char`元素均扩大到`String`。</span><span class="sxs-lookup"><span data-stu-id="06d21-181">A single `Char` and an array of `Char` elements both widen to `String`.</span></span> <span data-ttu-id="06d21-182">但是，`String`不会扩大到`Char()`。</span><span class="sxs-lookup"><span data-stu-id="06d21-182">However, `String` does not widen to `Char()`.</span></span> <span data-ttu-id="06d21-183">若要将转换`String`值赋给`Char`数组中，您可以使用<xref:System.String.ToCharArray%2A>方法的<xref:System.String?displayProperty=fullName>类。</xref:System.String?displayProperty=fullName> </xref:System.String.ToCharArray%2A></span><span class="sxs-lookup"><span data-stu-id="06d21-183">To convert a `String` value to a `Char` array, you can use the <xref:System.String.ToCharArray%2A> method of the <xref:System.String?displayProperty=fullName> class.</span></span>  
  
### <a name="meaningless-values"></a><span data-ttu-id="06d21-184">无意义的值</span><span class="sxs-lookup"><span data-stu-id="06d21-184">Meaningless Values</span></span>  
 <span data-ttu-id="06d21-185">一般情况下，`String`值并不在其他数据类型，有意义且转换是人工，危险极低。</span><span class="sxs-lookup"><span data-stu-id="06d21-185">In general, `String` values are not meaningful in other data types, and conversion is highly artificial and dangerous.</span></span> <span data-ttu-id="06d21-186">只要有可能，应限制使用`String`变量来为其设计的字符序列。</span><span class="sxs-lookup"><span data-stu-id="06d21-186">Whenever possible, you should restrict usage of `String` variables to the character sequences for which they are designed.</span></span> <span data-ttu-id="06d21-187">绝不应编写依赖于其他类型中的等效值的代码。</span><span class="sxs-lookup"><span data-stu-id="06d21-187">You should never write code that relies on equivalent values in other types.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="06d21-188">另请参阅</span><span class="sxs-lookup"><span data-stu-id="06d21-188">See Also</span></span>  
 <span data-ttu-id="06d21-189">[数据类型](../../../../visual-basic/programming-guide/language-features/data-types/index.md) </span><span class="sxs-lookup"><span data-stu-id="06d21-189">[Data Types](../../../../visual-basic/programming-guide/language-features/data-types/index.md) </span></span>  
<span data-ttu-id="06d21-190"> [类型字符](../../../../visual-basic/programming-guide/language-features/data-types/type-characters.md) </span><span class="sxs-lookup"><span data-stu-id="06d21-190"> [Type Characters](../../../../visual-basic/programming-guide/language-features/data-types/type-characters.md) </span></span>  
<span data-ttu-id="06d21-191"> [值类型和引用类型](../../../../visual-basic/programming-guide/language-features/data-types/value-types-and-reference-types.md) </span><span class="sxs-lookup"><span data-stu-id="06d21-191"> [Value Types and Reference Types](../../../../visual-basic/programming-guide/language-features/data-types/value-types-and-reference-types.md) </span></span>  
<span data-ttu-id="06d21-192"> [在 Visual Basic 中的类型转换](../../../../visual-basic/programming-guide/language-features/data-types/type-conversions.md) </span><span class="sxs-lookup"><span data-stu-id="06d21-192"> [Type Conversions in Visual Basic](../../../../visual-basic/programming-guide/language-features/data-types/type-conversions.md) </span></span>  
<span data-ttu-id="06d21-193"> [数据类型](../../../../visual-basic/language-reference/data-types/data-type-summary.md) </span><span class="sxs-lookup"><span data-stu-id="06d21-193"> [Data Types](../../../../visual-basic/language-reference/data-types/data-type-summary.md) </span></span>  
<span data-ttu-id="06d21-194"> [类型转换函数](../../../../visual-basic/language-reference/functions/type-conversion-functions.md) </span><span class="sxs-lookup"><span data-stu-id="06d21-194"> [Type Conversion Functions](../../../../visual-basic/language-reference/functions/type-conversion-functions.md) </span></span>  
<span data-ttu-id="06d21-195"> [有效使用数据类型](../../../../visual-basic/programming-guide/language-features/data-types/efficient-use-of-data-types.md)</span><span class="sxs-lookup"><span data-stu-id="06d21-195"> [Efficient Use of Data Types](../../../../visual-basic/programming-guide/language-features/data-types/efficient-use-of-data-types.md)</span></span>
