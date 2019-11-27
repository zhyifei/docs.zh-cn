---
title: 如何：测试两个对象是否相同
ms.date: 07/20/2015
helpviewer_keywords:
- variables [Visual Basic], reference
- Is operator [Visual Basic], comparing objects
- reference variables [Visual Basic]
- variables [Visual Basic], referring to same object
- objects [Visual Basic], variables referring to same
- Visual Basic code, operators
ms.assetid: f760e828-8704-4256-bc2d-c22a4c93b524
ms.openlocfilehash: 22e8e1e688d9e3bc3804899103ee78814aac235b
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/22/2019
ms.locfileid: "74343619"
---
# <a name="how-to-test-whether-two-objects-are-the-same-visual-basic"></a>如何：测试两个对象是否相同 (Visual Basic)
如果有两个引用对象的变量，则可以使用 `Is` 或 `IsNot` 运算符，或同时使用这两个变量来确定它们是否引用相同的实例。  
  
### <a name="to-test-whether-two-objects-are-the-same"></a>测试两个对象是否相同  
  
- 使用[Is 运算符](../../../../visual-basic/language-reference/operators/is-operator.md)或将两个变量作为操作数的[IsNot 运算符](../../../../visual-basic/language-reference/operators/isnot-operator.md)。  
  
     [!code-vb[VbVbalrOperators#69](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#69)]  
  
 您可能想要执行特定的操作，具体取决于两个对象是否引用相同的实例。 前面的示例将控件 `c` 与窗体 `f`上的活动控件进行比较。 如果没有活动的控件，或如果存在，但它不是与 `c`相同的控件实例，则 `If` 语句将失败，并且过程将返回，而不进行进一步的处理。  
  
 你使用 `Is` 还是 `IsNot` 对于你而言是一种个人便利。 比给定表达式中的另一个更易于读取。  
  
## <a name="see-also"></a>另请参阅

- [Visual Basic 中的比较运算符](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/comparison-operators.md)
