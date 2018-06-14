---
title: IsFalse 运算符 (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.isfalse
helpviewer_keywords:
- AndAlso operator [Visual Basic]
- IsFalse operator [Visual Basic]
ms.assetid: 37fc9dbf-e5cc-4570-b93f-7213447974df
ms.openlocfilehash: e84b2162eb0763725f05bc52d5c4223d7c430b81
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33600040"
---
# <a name="isfalse-operator-visual-basic"></a>IsFalse 运算符 (Visual Basic)
确定表达式是否为`False`。  
  
 不能调用`IsFalse`显式中你的代码，而 Visual Basic 编译器可以用它来生成代码从`AndAlso`子句。 如果你定义的类或结构，然后使用在该类型的变量的`AndAlso`子句中，你必须定义`IsFalse`在类或结构上。  
  
 编译器认为`IsFalse`和`IsTrue`与运算符*匹配对*。 这意味着，如果其中一个定义，你必须还定义另一个。  
  
> [!NOTE]
>  `IsFalse`运算符可以被*重载*，这意味着，一个类或结构可以重新定义其行为时，其操作数的类或结构的类型。 如果你的代码使用此运算符对这样的类或结构，请确保你了解其重新定义的行为。 有关详细信息，请参阅[运算符过程](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md)。  
  
## <a name="example"></a>示例  
 下面的代码示例定义的结构，其中包含定义大纲`IsFalse`和`IsTrue`运算符。  
  
 [!code-vb[VbVbalrOperators#28](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/isfalse-operator_1.vb)]  
  
## <a name="see-also"></a>请参阅  
 [IsTrue 运算符](../../../visual-basic/language-reference/operators/istrue-operator.md)  
 [如何：定义运算符](../../../visual-basic/programming-guide/language-features/procedures/how-to-define-an-operator.md)  
 [AndAlso 运算符](../../../visual-basic/language-reference/operators/andalso-operator.md)
