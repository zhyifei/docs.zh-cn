---
title: "数据类型疑难解答 (Visual Basic)"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- Char data type [Visual Basic], converting
- Decimal data type [Visual Basic], conversions
- data types [Visual Basic], troubleshooting
- literals [Visual Basic], default types
- type characters [Visual Basic], literal
- Mod operator [Visual Basic], in floating-point operations
- troubleshooting Visual Basic, data types
- troubleshooting data types [Visual Basic]
- floating-point numbers [Visual Basic], precision
- Boolean data type [Visual Basic], converting
- literal types [Visual Basic]
- literal type characters [Visual Basic]
- floating-point numbers [Visual Basic], imprecision
- String data type [Visual Basic], converting
- floating-point numbers [Visual Basic], comparison
- floating-point numbers
ms.assetid: 90040d67-b630-4125-a6ae-37195b079042
caps.latest.revision: "29"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 4d2fb1cd1be9c88ad0dd413eedb8a226fe59f41e
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="troubleshooting-data-types-visual-basic"></a>数据类型疑难解答 (Visual Basic)
此页列出了一些对内部数据类型执行操作时可能发生的常见问题。  
  
## <a name="floating-point-expressions-do-not-compare-as-equal"></a>浮点表达式不为相等比较  
 当你处理的浮点数 ([单一数据类型](../../../../visual-basic/language-reference/data-types/single-data-type.md)和[Double 数据类型](../../../../visual-basic/language-reference/data-types/double-data-type.md))，请记住，它们存储为二进制分数 （竖式）。 这意味着它们不能包含不是二进制分数任何数量的精确地表示 (的窗体 k / (2 ^ n) 其中 k 和 n 为整数)。 例如，0.5 （= 1/2） 和 0.3125 （= 5/16） 可以将保存为精确值，而 （= 1/5） 的 0.2 和 0.3 （= 3/10） 只能是近似值。  
  
 因此不精确性，则不能依赖准确的结果时浮点值上运行。 具体而言，理论上相等的两个值可能有略有不同的表示形式。  
  
| 要比较浮点数 | 
|---| 
|1.通过使用计算绝对值的数值之间的差值的<xref:System.Math.Abs%2A>方法<xref:System.Math>类<xref:System>命名空间。<br />2.确定可接受的最大偏差，以便你可以考虑要相等实用的角度而言之间的差值是否不超过两个数量。<br />3.到可接受的差异的差异绝对值进行比较。|  
  
 下面的示例演示两个正确和错误比较`Double`值。  
  
 [!code-vb[VbVbalrDataTypes#10](../../../../visual-basic/language-reference/data-types/codesnippet/VisualBasic/troubleshooting-data-types_1.vb)]  
  
 上一个示例使用<xref:System.Double.ToString%2A>方法<xref:System.Double>结构，以便它可以指定比更好的精度`CStr`关键字使用。 默认值为 15 位，但是"G17"格式将其扩展到 17 位。  
  
## <a name="mod-operator-does-not-return-accurate-result"></a>Mod 运算符不会返回准确的结果  
 由于浮点存储的不精确性[Mod 运算符](../../../../visual-basic/language-reference/operators/mod-operator.md)可以在至少其中一个操作数为浮点时返回了意外的结果。  
  
 [十进制数据类型](../../../../visual-basic/language-reference/data-types/decimal-data-type.md)不使用浮点表示形式。 许多的数字，则在准确`Single`和`Double`精确中`Decimal`（例如 0.2 和 0.3）。 尽管算术慢中`Decimal`比在浮点数，它可能值得性能的下降实现更好的精度。  
  
|若要查找浮点数的整数余数|  
|---|  
|1.将变量声明为`Decimal`。<br />2.使用文本类型字符`D`强制转换为`Decimal`，以防其值来说太大`Long`数据类型。|  
  
 下面的示例演示了潜在的浮点操作数不精确性。  
  
 [!code-vb[VbVbalrDataTypes#11](../../../../visual-basic/language-reference/data-types/codesnippet/VisualBasic/troubleshooting-data-types_2.vb)]  
  
 上一个示例使用<xref:System.Double.ToString%2A>方法<xref:System.Double>结构，以便它可以指定比更好的精度`CStr`关键字使用。 默认值为 15 位，但是"G17"格式将其扩展到 17 位。  
  
 因为`zeroPointTwo`是`Double`，0.2 其值是存储的值是为 0.20000000000000001 的无限期重复二进制小数。 根据此数量除以 2.0 将得到 9.9999999999999995，余数为 0.19999999999999991。  
  
 中的表达式`decimalRemainder`，文本类型字符`D`强制的两个操作数`Decimal`，，0.2 具有精确的表示形式。 因此`Mod`运算符产生 0.0 的预期的余数。  
  
 请注意，不足以声明`decimalRemainder`作为`Decimal`。 你还必须强制转换为`Decimal`，或它们使用`Double`默认情况下和`decimalRemainder`接收相同的不准确值`doubleRemainder`。  
  
## <a name="boolean-type-does-not-convert-to-numeric-type-accurately"></a>布尔值类型不准确地转换为数值类型  
 [Boolean 数据类型](../../../../visual-basic/language-reference/data-types/boolean-data-type.md)值不会存储为数字，并且存储的值不应为等效于数字。 为了与早期版本中，兼容[!INCLUDE[vbprvb](~/includes/vbprvb-md.md)]提供转换关键字 ([CType 函数](../../../../visual-basic/language-reference/functions/ctype-function.md)， `CBool`， `CInt`，依次类推) 之间进行转换`Boolean`与数值类型。 但是，其他语言有时执行这些转换以不同方式，如同[!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)]方法。  
  
 绝不应编写依赖于等效数字值的代码`True`和`False`。 只要有可能，应限制使用`Boolean`到为其设计的逻辑值的变量。 如果您需要混合`Boolean`和数字值，请确保你了解你选择的转换方法。  
  
### <a name="conversion-in-visual-basic"></a>在 Visual Basic 中的转换  
 当你使用`CType`或`CBool`转换关键字，若要将数值数据类型转换`Boolean`，0 会变为`False`和所有其他值将成为`True`。 当转换`Boolean`为通过使用转换关键字，数值类型的值`False`变为 0 和`True`会变为-1。  
  
### <a name="conversion-in-the-framework"></a>框架中的转换  
 <xref:System.Convert.ToInt32%2A>方法<xref:System.Convert>类<xref:System>命名空间将转换`True`到 + 1。  
  
 如果必须将转换`Boolean`值为数值数据类型，请小心使用有关哪些转换方法。  
  
## <a name="character-literal-generates-compiler-error"></a>字符文本生成编译器错误  
 如果未指定任何类型的字符，[!INCLUDE[vbprvb](~/includes/vbprvb-md.md)]将采用默认的文本的数据类型。 字符文本的默认类型-用引号引起来 (`" "`) — 是`String`。  
  
 `String`数据类型不会扩大到[Char 数据类型](../../../../visual-basic/language-reference/data-types/char-data-type.md)。 这意味着，如果你想要分配到文本`Char`变量，必须进行收缩转换，或将文本强制转换到`Char`类型。  

|若要创建字符文本要分配给变量或常量|
|---|  
|1.声明变量或常量作为`Char`。<br />2.将字符值括在双引号 (`" "`)。<br />3.请按照右双引号文本类型字符`C`强制到文本`Char`。 这是必需的如果类型检查开关 ([Option Strict 语句](../../../../visual-basic/language-reference/statements/option-strict-statement.md)) 是`On`，和最好在任何情况下。|  
  
 下面的示例演示了将文本赋予的失败和成功分配`Char`变量。  
  
 [!code-vb[VbVbalrDataTypes#12](../../../../visual-basic/language-reference/data-types/codesnippet/VisualBasic/troubleshooting-data-types_3.vb)]  
  
 始终风险中没有使用收缩转换，因为它们可以在运行时失败。 例如，从转换`String`到`Char`如果可能会失败`String`值包含多个字符。 因此，它更好地编程为使用`C`类型字符。  
  
## <a name="string-conversion-fails-at-run-time"></a>字符串转换将在运行时失败  
 [字符串数据类型](../../../../visual-basic/language-reference/data-types/string-data-type.md)参与非常少的扩大转换。 `String`只扩大到自身和`Object`，且仅`Char`和`Char()`(`Char`数组) 扩大到`String`。 这是因为`String`变量和常量可以包含其他数据类型不能包含的值。  
  
 当类型检查开关 ([Option Strict 语句](../../../../visual-basic/language-reference/statements/option-strict-statement.md)) 是`On`，编译器不允许所有隐式收缩转换。 这包括涉及`String`。 你的代码仍可以使用转换关键字如`CStr`和[CType 函数](../../../../visual-basic/language-reference/functions/ctype-function.md)，以指示[!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)]尝试转换。  
  
> [!NOTE]
>  收缩转换错误则会取消对转换中的元素从`For Each…Next`向循环控制变量的集合。 有关详细信息和示例，请参阅中的"收缩转换"一节[每个...下一条语句](../../../../visual-basic/language-reference/statements/for-each-next-statement.md)。  
  
### <a name="narrowing-conversion-protection"></a>收缩转换保护  
 收缩转换的缺点是它们可能会在运行时失败。 例如，如果`String`变量包含任何内容而非"True"或"False，"它无法转换为`Boolean`。 如果它包含标点字符，则为任何数值类型的转换将失败。 除非你知道你`String`变量始终保存目标类型可以接受的值，否则不应尝试进行转换。  
  
 如果你必须转换转换`String`最安全的过程是将括在尝试的转换为另一个数据类型，[重试...Catch...Finally 语句](../../../../visual-basic/language-reference/statements/try-catch-finally-statement.md)。 这样就可以处理运行时失败。  
  
### <a name="character-arrays"></a>字符数组  
 单个`Char`和数组`Char`元素均扩大到`String`。 但是，`String`未扩大到`Char()`。 要转换`String`值赋给`Char`阵列，你可以使用<xref:System.String.ToCharArray%2A>方法<xref:System.String?displayProperty=nameWithType>类。  
  
### <a name="meaningless-values"></a>无意义的值  
 一般情况下，`String`值不是在其他数据类型，有意义，转换是高度人工和危险。 只要有可能，应限制使用`String`它们设计作为字符序列的变量。 绝不应编写依赖于其他类型中的等效值的代码。  
  
## <a name="see-also"></a>另请参阅  
 [数据类型](../../../../visual-basic/programming-guide/language-features/data-types/index.md)  
 [类型字符](../../../../visual-basic/programming-guide/language-features/data-types/type-characters.md)  
 [值类型和引用类型](../../../../visual-basic/programming-guide/language-features/data-types/value-types-and-reference-types.md)  
 [在 Visual Basic 中的类型转换](../../../../visual-basic/programming-guide/language-features/data-types/type-conversions.md)  
 [数据类型](../../../../visual-basic/language-reference/data-types/data-type-summary.md)  
 [类型转换函数](../../../../visual-basic/language-reference/functions/type-conversion-functions.md)  
 [有效使用数据类型](../../../../visual-basic/programming-guide/language-features/data-types/efficient-use-of-data-types.md)
