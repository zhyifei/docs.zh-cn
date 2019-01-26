---
title: 如何：测试两个对象是否相同 (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- variables [Visual Basic], reference
- Is operator [Visual Basic], comparing objects
- reference variables [Visual Basic]
- variables [Visual Basic], referring to same object
- objects [Visual Basic], variables referring to same
- Visual Basic code, operators
ms.assetid: f760e828-8704-4256-bc2d-c22a4c93b524
ms.openlocfilehash: 4130dfbe70682e28b6bb15db633ede2790e20aa3
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54595547"
---
# <a name="how-to-test-whether-two-objects-are-the-same-visual-basic"></a>如何：测试两个对象是否相同 (Visual Basic)
如果您有两个引用的对象的变量，可以使用`Is`或`IsNot`运算符，或两者，以确定它们是否引用同一个实例。  
  
### <a name="to-test-whether-two-objects-are-the-same"></a>若要测试两个对象是否相同  
  
-   使用[Is 运算符](../../../../visual-basic/language-reference/operators/is-operator.md)或[IsNot 运算符](../../../../visual-basic/language-reference/operators/isnot-operator.md)与两个变量作为操作数。  
  
     [!code-vb[VbVbalrOperators#69](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-test-whether-two-objects-are-the-same_1.vb)]  
  
 您可能想要执行的具体操作取决于两个对象是否引用相同的实例。 前面的示例进行比较的控件`c`窗体上的活动控件针对`f`。 如果没有活动的控件，或者如果没有一个但这不是相同的控件实例作为`c`，则`If`语句将失败，该过程将返回而不会进一步处理。  
  
 无论是使用`Is`或`IsNot`是对您的个人方便起见。 一个可能更易读比另一个给定表达式中。  
  
## <a name="see-also"></a>请参阅
- [在 Visual Basic 中的比较运算符](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/comparison-operators.md)
