---
title: 运算符的有效组合 (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- expressions [Visual Basic], parentheses
- operators [Visual Basic], associativity
- expressions [Visual Basic], operators
- operators [Visual Basic], precedence
- Visual Basic code, operators
- Visual Basic code, expressions
- operators [Visual Basic], complex expressions
- expressions [Visual Basic], complex
- parentheses [Visual Basic], complex expressions
- numeric expressions
ms.assetid: bd22340e-b5be-458b-8772-3916c02309a4
ms.openlocfilehash: 8ced464cb0cc8e1bec3c3449dccb827575599905
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
---
# <a name="efficient-combination-of-operators-visual-basic"></a>运算符的有效组合 (Visual Basic)
复杂表达式可以包含许多不同的运算符。 下面的示例阐释了这一点。  
  
 `x = (45 * (y + z)) ^ (2 / 85) * 5 + z`  
  
 创建复杂表达式，例如前面示例中需要的运算符优先顺序规则的全面了解。 有关详细信息，请参阅[Visual Basic 中的运算符优先级](../../../../visual-basic/language-reference/operators/operator-precedence.md)。  
  
## <a name="parenthetical-expressions"></a>带括号的表达式  
 通常，你想以不同的由运算符优先级确定顺序来执行运算。 请看下面的示例。  
  
 `x = z * y + 4`  
  
 前面的示例乘以`z`通过`y`，然后将添加到结果`4`。 但是，如果你想要添加`y`和`4`之前将由结果乘以`z`，你可以使用括号来覆盖正常运算符优先级。 通过表达式括在括号中，你可以强制而不考虑运算符优先级首先，计算该表达式。 若要强制前面的示例先计算加法，你无法重写如以下示例所示。  
  
 `x = z * (y + 4)`  
  
 前面的示例将`y`和`4`，然后乘以由其总和`z`。  
  
### <a name="nested-parenthetical-expressions"></a>嵌套的括号表达式  
 你可以嵌套的括号以进一步重写优先级的多个级别中的表达式。 最深嵌套在括号中的表达式都将先评估跟嵌套最深的依次类推至少深度嵌套的并最后外部括号的表达式到下一步。 下面的示例阐释了这一点。  
  
 `x = (z * 4) ^ (y * (z + 2))`  
  
 在前面的示例中，`z + 2`为首先进行评估，则其他带括号的表达式。 求幂，通常具有优先权要高于加法或乘法，是在此示例中上次评估，因为其他表达式括在括号中。  
  
## <a name="see-also"></a>请参阅  
 [在 Visual Basic 中的算术运算符](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/arithmetic-operators.md)  
 [在 Visual Basic 中的比较运算符](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/comparison-operators.md)  
 [在 Visual Basic 中的逻辑和按位运算符](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/logical-and-bitwise-operators.md)  
 [逻辑/按位运算符 (Visual Basic)](../../../../visual-basic/language-reference/operators/logical-bitwise-operators.md)  
 [布尔表达式](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/boolean-expressions.md)  
 [值的比较](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/value-comparisons.md)  
 [如何：计算数值](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/how-to-calculate-numeric-values.md)  
 [Visual Basic 中的运算符优先级](../../../../visual-basic/language-reference/operators/operator-precedence.md)
