---
title: IsTrue 运算符 (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.istrue
helpviewer_keywords:
- IsTrue operator [Visual Basic]
- OrElse operator [Visual Basic]
ms.assetid: b6cec0f2-61b1-4331-a7f0-4d07ee3179d6
ms.openlocfilehash: fc01b074d9aba245b1c55b75b841a7f195f7ec04
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
---
# <a name="istrue-operator-visual-basic"></a>IsTrue 运算符 (Visual Basic)
确定表达式是否为`True`。  
  
 不能调用`IsTrue`显式中你的代码，而 Visual Basic 编译器可以用它来生成代码从`OrElse`子句。 如果你定义的类或结构，然后使用在该类型的变量的`OrElse`子句中，你必须定义`IsTrue`在类或结构上。  
  
 编译器认为`IsTrue`和`IsFalse`与运算符*匹配对*。 这意味着，如果其中一个定义，你必须还定义另一个。  
  
## <a name="compiler-use-of-istrue"></a>编译器使用的 IsTrue  
 当你已定义类或结构时，可以使用在该类型的变量`For`， `If`， `Else``If`，或`While`语句，或在`When`子句。 如果这样做，则编译器会要求将转换到你的类型的运算符`Boolean`值以便可以测试条件。 它搜索合适的运算符按以下顺序：  
  
1.  从类或结构的扩大转换运算符`Boolean`。  
  
2.  从类或结构的扩大转换运算符`Boolean?`。  
  
3.  `IsTrue`在类或结构上的运算符。  
  
4.  收缩转换为`Boolean?`不涉及从转换`Boolean`到`Boolean?`。  
  
5.  从类或结构的收缩转换运算符`Boolean`。  
  
 如果你未定义任何转换为`Boolean`或`IsTrue`运算符，编译器将引发错误。  
  
> [!NOTE]
>  `IsTrue`运算符可以被*重载*，这意味着，一个类或结构可以重新定义其行为时，其操作数的类或结构的类型。 如果你的代码使用此运算符对这样的类或结构，请确保你了解其重新定义的行为。 有关详细信息，请参阅[运算符过程](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md)。  
  
## <a name="example"></a>示例  
 下面的代码示例定义的结构，其中包含定义大纲`IsFalse`和`IsTrue`运算符。  
  
 [!code-vb[VbVbalrOperators#28](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/istrue-operator_1.vb)]  
  
## <a name="see-also"></a>请参阅  
 [IsFalse 运算符](../../../visual-basic/language-reference/operators/isfalse-operator.md)  
 [如何：定义运算符](../../../visual-basic/programming-guide/language-features/procedures/how-to-define-an-operator.md)  
 [OrElse 运算符](../../../visual-basic/language-reference/operators/orelse-operator.md)
