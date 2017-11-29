---
title: "值的比较 (Visual Basic)"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- variables [Visual Basic], comparing values
- Visual Basic code, operators
- Visual Basic code, expressions
- comparison operators [Visual Basic], comparing expressions
- numeric expressions
- operators [Visual Basic], comparison
- expressions [Visual Basic], comparing
ms.assetid: 60da0c76-9458-4afc-97e9-44a7939c064c
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: c11f12bbaf261c0853e96802f03322c5e7fdc706
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="value-comparisons-visual-basic"></a>值的比较 (Visual Basic)
比较运算符可以用于构造比较数值变量的值的表达式。 这些表达式返回`Boolean`值基于比较是否为 true 或 false。 此类表达式的示例如下所示。  
  
 `45 > 26`  
  
 `26 > 45`  
  
 第一个表达式的计算结果为`True`，这是因为 45 大于 26。 第二个示例的计算结果为`False`，这是因为 26 不大于 45。  
  
 你还可以比较数值表达式以这种方式。 要比较的表达式本身可以是复杂表达式，如以下示例所示。  
  
 `x / 45 * (y +17) >= System.Math.Sqrt(z) / (p - (x * 16))`  
  
 前面的复杂表达式包括文本、 变量和函数调用。 两端的比较运算符对表达式进行计算，并且将生成的值会然后比较使用`>=`比较运算符。 如果左侧表达式的值大于或等于右侧表达式的值，则整个表达式的计算结果为`True`; 否则为其计算结果为`False`。  
  
 比较值的表达式最常用于`If...Then`构造，如以下示例所示。  
  
 [!code-vb[VbVbalrOperators#84](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/value-comparisons_1.vb)]  
  
 `=`符号是比较运算符也是赋值运算符。 当用作比较运算符，它会在下面的示例中所示，在左侧的值是否等于右侧，值评估。  
  
 [!code-vb[VbVbalrOperators#85](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/value-comparisons_2.vb)]  
  
 你还可以使用比较表达式任意位置`Boolean`值是所需，例如，在`If`， `While`， `Loop`，或`ElseIf`语句，或者当将分配到或将值传递给`Boolean`变量。 在下面的示例中，比较表达式返回的值分配给`Boolean`变量。  
  
 [!code-vb[VbVbalrOperators#86](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/value-comparisons_3.vb)]  
  
## <a name="see-also"></a>另请参阅  
 [布尔表达式](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/boolean-expressions.md)  
 [运算符和表达式](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/index.md)  
 [在 Visual Basic 中的比较运算符](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/comparison-operators.md)  
 [如何：计算数值](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/how-to-calculate-numeric-values.md)  
 [Visual Basic 中的运算符优先级](../../../../visual-basic/language-reference/operators/operator-precedence.md)
