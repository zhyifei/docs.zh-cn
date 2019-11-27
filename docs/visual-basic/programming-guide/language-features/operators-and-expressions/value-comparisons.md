---
title: 值的比较
ms.date: 07/20/2015
helpviewer_keywords:
- variables [Visual Basic], comparing values
- Visual Basic code, operators
- Visual Basic code, expressions
- comparison operators [Visual Basic], comparing expressions
- numeric expressions
- operators [Visual Basic], comparison
- expressions [Visual Basic], comparing
ms.assetid: 60da0c76-9458-4afc-97e9-44a7939c064c
ms.openlocfilehash: f766eaaada486a0f70838bafb754d25070ff4174
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/22/2019
ms.locfileid: "74346291"
---
# <a name="value-comparisons-visual-basic"></a>值的比较 (Visual Basic)
比较运算符可用于构造比较数值变量的值的表达式。 这些表达式根据比较结果是 true 还是 false 返回 `Boolean` 值。 此类表达式的示例如下所示。  
  
 `45 > 26`  
  
 `26 > 45`  
  
 第一个表达式的计算结果为 `True`，因为45大于26。 第二个示例的计算结果为 `False`，因为26不大于45。  
  
 您还可以采用这种方式比较数值表达式。 比较的表达式本身就是复杂表达式，如下面的示例中所示。  
  
 `x / 45 * (y +17) >= System.Math.Sqrt(z) / (p - (x * 16))`  
  
 前面的复杂表达式包括文本、变量和函数调用。 将计算比较运算符两侧的表达式，然后使用 `>=` 比较运算符比较结果值。 如果左侧表达式的值大于或等于右侧表达式的值，则整个表达式的计算结果为 `True`;否则，它的计算结果为 `False`。  
  
 比较值的表达式最常用于 `If...Then` 构造中，如下面的示例中所示。  
  
 [!code-vb[VbVbalrOperators#84](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#84)]  
  
 `=` 符号是比较运算符以及赋值运算符。 用作比较运算符时，它计算左侧的值是否等于右侧的值，如下面的示例中所示。  
  
 [!code-vb[VbVbalrOperators#85](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#85)]  
  
 你还可以在需要 `Boolean` 值的任何位置使用比较表达式，如在 `If`、`While`、`Loop`或 `ElseIf` 语句中，或者在赋值或将值传递到 `Boolean` 变量时使用。 在下面的示例中，比较表达式返回的值被分配给一个 `Boolean` 变量。  
  
 [!code-vb[VbVbalrOperators#86](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#86)]  
  
## <a name="see-also"></a>另请参阅

- [布尔表达式](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/boolean-expressions.md)
- [运算符和表达式](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/index.md)
- [Visual Basic 中的比较运算符](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/comparison-operators.md)
- [如何：计算数值](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/how-to-calculate-numeric-values.md)
- [Visual Basic 中的运算符优先级](../../../../visual-basic/language-reference/operators/operator-precedence.md)
