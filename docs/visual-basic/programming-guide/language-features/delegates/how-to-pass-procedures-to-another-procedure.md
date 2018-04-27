---
title: 如何：在 Visual Basic 中将过程传递给另一过程
ms.custom: ''
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- AddressOf operator [Visual Basic]
- delegates [Visual Basic], passing procedures
ms.assetid: 5adbba15-5a1d-413f-ab3e-3ff6cc0a4669
caps.latest.revision: 9
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 30264e0480b603b21f8f71893af0fd742af40286
ms.sourcegitcommit: 86adcc06e35390f13c1e372c36d2e044f1fc31ef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/26/2018
---
# <a name="how-to-pass-procedures-to-another-procedure-in-visual-basic"></a>如何：在 Visual Basic 中将过程传递给另一过程
此示例演示如何使用委托将传递给另一个过程的过程。  
  
 委托是一种可以使用与在 Visual Basic 中的任何其他类型一样。 `AddressOf`运算符返回委托对象时应用于过程名称。  
  
 此示例具有带可以采用另一个过程，通过获取引用委托参数的过程`AddressOf`运算符。  
  
### <a name="create-the-delegate-and-matching-procedures"></a>创建的委托和匹配的过程  
  
1.  创建名为的委托`MathOperator`。  
  
     [!code-vb[VbVbalrDelegates#1](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-pass-procedures-to-another-procedure_1.vb)]  
  
2.  创建名为的过程`AddNumbers`使用参数和返回值相匹配的`MathOperator`，以便的签名匹配。  
  
     [!code-vb[VbVbalrDelegates#2](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-pass-procedures-to-another-procedure_2.vb)]  
  
3.  创建名为的过程`SubtractNumbers`相匹配的签名与`MathOperator`。  
  
     [!code-vb[VbVbalrDelegates#3](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-pass-procedures-to-another-procedure_3.vb)]  
  
4.  创建名为的过程`DelegateTest`采用委托作为参数。  
  
     此过程可以接受对引用`AddNumbers`或`SubtractNumbers`，因为它们的签名匹配`MathOperator`签名。  
  
     [!code-vb[VbVbalrDelegates#4](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-pass-procedures-to-another-procedure_4.vb)]  
  
5.  创建名为的过程`Test`调用`DelegateTest`一次使用的委托`AddNumbers`作为参数，并再次使用的委托`SubtractNumbers`作为参数。  
  
     [!code-vb[VbVbalrDelegates#5](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-pass-procedures-to-another-procedure_5.vb)]  
  
     当`Test`是它调用，首先显示的结果`AddNumbers`活动上`5`和`3`，也就是 8。 然后的结果`SubtractNumbers`作用于`9`和`3`显示时，也就是 6。  
  
## <a name="see-also"></a>请参阅  
 [委托](../../../../visual-basic/programming-guide/language-features/delegates/index.md)  
 [AddressOf 运算符](../../../../visual-basic/language-reference/operators/addressof-operator.md)  
 [Delegate 语句](../../../../visual-basic/language-reference/statements/delegate-statement.md)  
 [如何：调用委托方法](../../../../visual-basic/programming-guide/language-features/delegates/how-to-invoke-a-delegate-method.md)
