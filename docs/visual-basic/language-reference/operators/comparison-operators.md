---
title: "比较运算符 (Visual Basic)"
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords:
- vb.<>
- vb.>=
- vb.<=
- vb.>
- vb.<
helpviewer_keywords:
- greater than or equal to operator [Visual Basic]
- '>= operator [Visual Basic]'
- = operator [Visual Basic]
- < operator [Visual Basic]
- less than operator [Visual Basic]
- relational operators [Visual Basic], syntax
- Like operator [Visual Basic]
- <> operator [Visual Basic]
- '> operator [Visual Basic]'
- equal operator [Visual Basic]
- less than or equal to operator [Visual Basic]
- symbols, operators
- greater than operator [Visual Basic]
- comparing values [Visual Basic]
- operators [Visual Basic], relational
- string comparison [Visual Basic]
- not equal to comparison operator [Visual Basic]
- <= operator [Visual Basic]
- operators [Visual Basic], comparison
- Is operator [Visual Basic]
- comparison operators [Visual Basic], Visual Basicl
ms.assetid: d6cb12a8-e52e-46a7-8aaf-f804d634a825
caps.latest.revision: "20"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: aa450f7978f46196663c7534b31597b04d80482a
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="comparison-operators-visual-basic"></a>比较运算符 (Visual Basic)
以下是定义在 Visual Basic 中的比较运算符。  
  
 `<`运算符  
  
 `<=`运算符  
  
 `>`运算符  
  
 `>=`运算符  
  
 `=`运算符  
  
 `<>`运算符  
  
 [Is 运算符](../../../visual-basic/language-reference/operators/is-operator.md)  
  
 [IsNot 运算符](../../../visual-basic/language-reference/operators/isnot-operator.md)  
  
 [Like 运算符](../../../visual-basic/language-reference/operators/like-operator.md)  
  
 这些运算符比较两个表达式以确定它们相等，以及如果不是，有何不同。 `Is``IsNot`，和`Like`详细地讨论了在单独的帮助页上。 关系的比较运算符在此页上详细讨论。  
  
## <a name="syntax"></a>语法  
  
```  
      result = expression1 comparisonoperator expression2  
result = object1 [Is | IsNot] object2  
result = string Like pattern  
```  
  
## <a name="parts"></a>部件  
 `result`  
 必需。 A`Boolean`表示结果的比较的值。  
  
 `expression`  
 必需。 任何表达式。  
  
 `comparisonoperator`  
 必需。 任何关系的比较运算符。  
  
 `object1`, `object2`  
 必需。 对象名称的任何引用。  
  
 `string`  
 必需。 任何 `String` 表达式。  
  
 `pattern`  
 必需。 任何`String`表达式或范围的字符。  
  
## <a name="remarks"></a>备注  
 下表包含关系的比较运算符和确定的条件的列表是否`result`是`True`或`False`。  
  
|运算符|`True`如果|`False`如果|  
|--------------|---------------|----------------|  
|`<`（小于）|`expression1` < `expression2`|`expression1` >= `expression2`|  
|`<=`（小于或等于）|`expression1` <= `expression2`|`expression1` > `expression2`|  
|`>`（大于）|`expression1` > `expression2`|`expression1` <= `expression2`|  
|`>=`（大于或等于）|`expression1` >= `expression2`|`expression1` < `expression2`|  
|`=`（等于）|`expression1` = `expression2`|`expression1` <> `expression2`|  
|`<>`（不等于）|`expression1` <> `expression2`|`expression1` = `expression2`|  
  
> [!NOTE]
>  [= 运算符](../../../visual-basic/language-reference/operators/assignment-operator.md)还用作赋值运算符。  
  
 `Is`运算符，`IsNot`运算符，与`Like`运算符具有特定的比较功能不同于前面的表中的运算符。  
  
## <a name="comparing-numbers"></a>将数字进行比较  
 类型的类型的表达式的比较时`Single`类型之一`Double`、`Single`表达式转换为`Double`。 此行为是相反的行为在 Visual Basic 6 中找到。  
  
 同样，当比较类型的表达式`Decimal`到类型的表达式`Single`或`Double`、`Decimal`表达式转换为`Single`或`Double`。 有关`Decimal`表达式，任何小数部分的值小于 1E-28 可能会丢失。 此类小数部分值丢失可能导致两个值的比较结果相等时它们就不是。 为此，您需要采取措施时使用相等 (`=`) 要比较两个浮点变量。 它会更加安全，来测试两个数字之间的差异的绝对值的数值是否早于一个小的可接受容差。  
  
### <a name="floating-point-imprecision"></a>浮点不精确性  
 当使用浮点数时，请注意在内存中不始终具有精确的表示形式。 这可能导致意外的结果从某些操作，如值比较和[Mod 运算符](../../../visual-basic/language-reference/operators/mod-operator.md)。 有关详细信息，请参阅[故障排除数据类型](../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md)。  
  
## <a name="comparing-strings"></a>比较字符串  
 当比较字符串时，根据其按字母顺序排序顺序，具体取决于对的字符串表达式进行计算`Option Compare`设置。  
  
 `Option Compare Binary`基的字符串比较派生自字符的内部二进制表示的排序顺序。 排序顺序取决于代码页。 下面的示例演示典型的二进制排序顺序。  
  
 `A < B < E < Z < a < b < e < z < À < Ê < Ø < à < ê < ø`  
  
 `Option Compare Text`基的字符串由应用程序的区域设置的不区分大小写、 文本排序顺序的比较。 当你将设置`Option Compare Text`和排序的字符在前面的示例，请应用以下文本排序顺序：  
  
 `(A=a) < (À= à) < (B=b) < (E=e) < (Ê= ê) < (Ø = ø) < (Z=z)`  
  
### <a name="locale-dependence"></a>区域设置依赖项  
 当你将设置`Option Compare Text`，字符串比较的结果的可能取决于运行该应用程序的区域设置。 两个字符可能比较结果相等，但不是在另一个区域设置中。 如果你使用的字符串比较来做出重要决定，例如是否接受尝试登录，你应与区域设置敏感度警报。 请考虑这两个设置`Option Compare Binary`或调用<xref:Microsoft.VisualBasic.Strings.StrComp%2A>，这将考虑在内的区域设置。  
  
## <a name="typeless-programming-with-relational-comparison-operators"></a>使用关系比较运算符的无类型编程  
 使用关系比较运算符和`Object`表达式不允许在`Option Strict On`。 当`Option Strict`是`Off`，并且`expression1`或`expression2`是`Object`表达式中，运行时类型确定如何对它们进行比较。 下表显示如何比较表达式和比较，具体取决于操作数的运行时类型的结果。  
  
|如果操作数都是|比较是|  
|---------------------|-------------------|  
|同时`String`|排序基于字符串排序特征进行比较。|  
|这两个数字|对象转换为`Double`，数值比较。|  
|一个数值而另一个`String`|`String`转换为`Double`和执行数值比较。 如果`String`不能转换为`Double`、<xref:System.InvalidCastException>引发。|  
|一种或两是以外的其他引用类型`String`|引发 <xref:System.InvalidCastException>。|  
  
 数值比较将`Nothing`为 0。 字符串比较将`Nothing`作为`""`（空字符串）。  
  
## <a name="overloading"></a>重载  
 关系的比较运算符 (`<`。 `<=``>`， `>=`， `=`， `<>`) 可以是*重载*，这意味着，一个类或结构可以重新定义它们的行为时，操作数的类或结构的类型。 如果你的代码使用以上任意运算符对这样的类或结构，请确保你了解重新定义的行为。 有关详细信息，请参阅[运算符过程](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md)。  
  
 请注意， [= 运算符](../../../visual-basic/language-reference/operators/assignment-operator.md)仅为关系的比较运算符，而不是赋值运算符可以重载。  
  
## <a name="example"></a>示例  
 下面的示例演示关系的比较运算符，用于比较表达式的各种的用法。 关系的比较运算符返回`Boolean`表示无论是否规定的表达式计算结果为结果`True`。 当你将`>`和`<`为字符串的运算符，比较使用进行的字符串的正常按字母顺序排序顺序。 可以按此顺序依赖于区域设置。 是否排序是区分大小写或不依赖于[Option Compare](../../../visual-basic/language-reference/statements/option-compare-statement.md)设置。  
  
 [!code-vb[VbVbalrOperators#1](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/comparison-operators_1.vb)]  
  
 在前面的示例中，返回的第一个比较`False`和其余的比较返回`True`。  
  
## <a name="see-also"></a>另请参阅  
 <xref:System.InvalidCastException>  
 [= 运算符](../../../visual-basic/language-reference/operators/assignment-operator.md)  
 [Visual Basic 中的运算符优先级](../../../visual-basic/language-reference/operators/operator-precedence.md)  
 [按功能列出的运算符](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)  
 [数据类型疑难解答](../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md)  
 [在 Visual Basic 中的比较运算符](../../../visual-basic/programming-guide/language-features/operators-and-expressions/comparison-operators.md)
