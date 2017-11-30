---
title: "如何：测试两个对象是否相同 (Visual Basic)"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- variables [Visual Basic], reference
- Is operator [Visual Basic], comparing objects
- reference variables [Visual Basic]
- variables [Visual Basic], referring to same object
- objects [Visual Basic], variables referring to same
- Visual Basic code, operators
ms.assetid: f760e828-8704-4256-bc2d-c22a4c93b524
caps.latest.revision: "11"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 76f5c19386cce84207f80d217326d2e3babf4e44
ms.sourcegitcommit: c2e216692ef7576a213ae16af2377cd98d1a67fa
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/22/2017
---
# <a name="how-to-test-whether-two-objects-are-the-same-visual-basic"></a>如何：测试两个对象是否相同 (Visual Basic)
如果你有两个引用对象的变量，可以使用`Is`或`IsNot`运算符，或两者，来确定它们是否引用相同实例。  
  
### <a name="to-test-whether-two-objects-are-the-same"></a>若要测试两个对象是否相同  
  
-   使用[Is 运算符](../../../../visual-basic/language-reference/operators/is-operator.md)或[IsNot 运算符](../../../../visual-basic/language-reference/operators/isnot-operator.md)与两个变量作为操作数。  
  
     [!code-vb[VbVbalrOperators#69](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-test-whether-two-objects-are-the-same_1.vb)]  
  
 你可能想要执行某些操作具体取决于两个对象是否引用相同实例。 前面的示例比较控件`c`针对窗体上的活动控件`f`。 如果没有活动的控件，或如果没有一个但这不是相同的控件实例`c`，则`If`语句将失败并且过程将返回而不会进一步处理。  
  
 是否使用`Is`或`IsNot`个人方便你只是。 一个可能更易读比另一个给定表达式中。  
  
## <a name="see-also"></a>另请参阅  
 [在 Visual Basic 中的比较运算符](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/comparison-operators.md)
