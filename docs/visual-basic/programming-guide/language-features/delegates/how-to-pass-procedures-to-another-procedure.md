---
title: 如何：将过程传递给另一过程
ms.date: 07/20/2015
helpviewer_keywords:
- AddressOf operator [Visual Basic]
- delegates [Visual Basic], passing procedures
ms.assetid: 5adbba15-5a1d-413f-ab3e-3ff6cc0a4669
ms.openlocfilehash: 300489935ce54d78b989d09211a7f6ba95c2f514
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/22/2019
ms.locfileid: "74345250"
---
# <a name="how-to-pass-procedures-to-another-procedure-in-visual-basic"></a>如何：在 Visual Basic 中将过程传递给另一过程
此示例演示如何使用委托将过程传递给另一个过程。  
  
 委托是一种类型，您可以像在 Visual Basic 中那样使用任何其他类型。 当应用于过程名称时，`AddressOf` 运算符返回一个委托对象。  
  
 此示例包含一个带有委托参数的过程，该参数可以引用使用 `AddressOf` 运算符获得的另一个过程。  
  
### <a name="create-the-delegate-and-matching-procedures"></a>创建委托和匹配过程  
  
1. 创建一个名为 `MathOperator`的委托。  
  
     [!code-vb[VbVbalrDelegates#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrDelegates/VB/Class1.vb#1)]  
  
2. 创建一个名为 `AddNumbers` 的过程，该过程的参数和返回值与 `MathOperator`的参数和返回值匹配，以便签名匹配。  
  
     [!code-vb[VbVbalrDelegates#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrDelegates/VB/Class1.vb#2)]  
  
3. 使用与 `MathOperator`匹配的签名创建名为 `SubtractNumbers` 的过程。  
  
     [!code-vb[VbVbalrDelegates#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrDelegates/VB/Class1.vb#3)]  
  
4. 创建一个名为 `DelegateTest` 的过程，该过程采用委托作为参数。  
  
     此过程可以接受对 `AddNumbers` 或 `SubtractNumbers`的引用，因为它们的签名与 `MathOperator` 签名相匹配。  
  
     [!code-vb[VbVbalrDelegates#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrDelegates/VB/Class1.vb#4)]  
  
5. 创建一个名为 `Test` 的过程，该过程使用 `AddNumbers` 作为参数的委托调用一次 `DelegateTest`，并再次使用 `SubtractNumbers` 的委托作为参数。  
  
     [!code-vb[VbVbalrDelegates#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrDelegates/VB/Class1.vb#5)]  
  
     调用 `Test` 时，它首先显示对 `5` 和 `3`（为8） `AddNumbers` 的结果。 然后，将显示 `SubtractNumbers` 作用于 `9` 和 `3` 的结果，即6。  
  
## <a name="see-also"></a>另请参阅

- [委托](../../../../visual-basic/programming-guide/language-features/delegates/index.md)
- [AddressOf 运算符](../../../../visual-basic/language-reference/operators/addressof-operator.md)
- [Delegate 语句](../../../../visual-basic/language-reference/statements/delegate-statement.md)
- [如何：调用委托方法](../../../../visual-basic/programming-guide/language-features/delegates/how-to-invoke-a-delegate-method.md)
