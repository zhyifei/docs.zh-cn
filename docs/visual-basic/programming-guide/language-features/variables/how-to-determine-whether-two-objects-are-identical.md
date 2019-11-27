---
title: 如何：确定两个对象是否相同
ms.date: 07/20/2015
helpviewer_keywords:
- testing [Visual Basic], objects
- objects [Visual Basic], comparing
- object variables [Visual Basic], determining identity
ms.assetid: 7829f817-0d1f-4749-a707-de0b95e0cf5c
ms.openlocfilehash: 5deebd4ffc5b277c94f5ae36c00fd6e5010a1551
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/22/2019
ms.locfileid: "74348602"
---
# <a name="how-to-determine-whether-two-objects-are-identical-visual-basic"></a>如何：确定两个对象是否相同 (Visual Basic)
在 Visual Basic 中，如果两个变量引用相同，即两个变量都指向内存中的同一个类实例，则将其视为相同。 例如，在 Windows 窗体应用程序中，您可能需要进行比较以确定当前实例（`Me`）与特定实例（例如 `Form2`）是否相同。  
  
 Visual Basic 提供了两个运算符来比较指针。 如果对象相同，[则 Is 运算符](../../../../visual-basic/language-reference/operators/is-operator.md)返回 `True`; 如果不是，则为[IsNot 运算符](../../../../visual-basic/language-reference/operators/isnot-operator.md)返回 `True`。  
  
## <a name="determining-if-two-objects-are-identical"></a>确定两个对象是否相同  
  
#### <a name="to-determine-if-two-objects-are-identical"></a>确定两个对象是否相同  
  
1. 设置 `Boolean` 表达式来测试两个对象。  
  
2. 在测试表达式中，将 `Is` 运算符用于将两个对象作为操作数。  
  
     如果对象指向相同的类实例，则 `Is` 返回 `True`。  
  
## <a name="determining-if-two-objects-are-not-identical"></a>确定两个对象是否不相同  
 有时，如果两个对象不完全相同，则需要执行一个操作，并将 `Not` 和 `Is`结合起来（例如 `If Not obj1 Is obj2`）会很难。 在这种情况下，可以使用 `IsNot` 运算符。  
  
#### <a name="to-determine-if-two-objects-are-not-identical"></a>确定两个对象是否不相同  
  
1. 设置 `Boolean` 表达式来测试两个对象。  
  
2. 在测试表达式中，将 `IsNot` 运算符用于将两个对象作为操作数。  
  
     如果对象不指向同一个类实例，`IsNot` 将返回 `True`。  
  
## <a name="example"></a>示例  
 下面的示例测试 `Object` 变量的对，以确定它们是否指向相同的类实例。  
  
 [!code-vb[VbVbalrKeywords#14](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrKeywords/VB/class7.vb#14)]  
  
 前面的示例显示以下输出。  
  
 `objA different from objB? True`  
  
 `objA identical to objC? True`  
  
## <a name="see-also"></a>另请参阅

- [Object 数据类型](../../../../visual-basic/language-reference/data-types/object-data-type.md)
- [对象变量](../../../../visual-basic/programming-guide/language-features/variables/object-variables.md)
- [对象变量值](../../../../visual-basic/programming-guide/language-features/variables/object-variable-values.md)
- [Is 运算符](../../../../visual-basic/language-reference/operators/is-operator.md)
- [IsNot 运算符](../../../../visual-basic/language-reference/operators/isnot-operator.md)
- [如何：确定两个对象是否相关](../../../../visual-basic/programming-guide/language-features/variables/how-to-determine-whether-two-objects-are-related.md)
- [Me、My、MyBase 和 MyClass](../../../../visual-basic/programming-guide/program-structure/me-my-mybase-and-myclass.md)
