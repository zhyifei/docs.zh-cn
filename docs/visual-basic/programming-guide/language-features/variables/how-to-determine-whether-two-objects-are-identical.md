---
title: 如何：确定两个对象是否相同 (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- testing [Visual Basic], objects
- objects [Visual Basic], comparing
- object variables [Visual Basic], determining identity
ms.assetid: 7829f817-0d1f-4749-a707-de0b95e0cf5c
ms.openlocfilehash: bbcac2fc51e57427b125ec2f5e68f017a60186d8
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-determine-whether-two-objects-are-identical-visual-basic"></a>如何：确定两个对象是否相同 (Visual Basic)
在 Visual Basic 中，两个变量的引用将被视为同一如果其指针相同，即，如果两个变量指向内存中的同一个类实例。 例如，在 Windows 窗体应用程序中，你可能想要进行比较以确定是否当前的实例 (`Me`) 等同于一个特定实例，如`Form2`。  
  
 Visual Basic 提供两个运算符比较指针。 [Is 运算符](../../../../visual-basic/language-reference/operators/is-operator.md)返回`True`如果对象是相同的与[IsNot 运算符](../../../../visual-basic/language-reference/operators/isnot-operator.md)返回`True`如果它们不是。  
  
## <a name="determining-if-two-objects-are-identical"></a>确定两个对象是否相同  
  
#### <a name="to-determine-if-two-objects-are-identical"></a>若要确定两个对象是否相同  
  
1.  设置`Boolean`要测试两个对象表达式。  
  
2.  在测试表达式中，使用`Is`运算符具有两个对象作为操作数。  
  
     `Is` 返回`True`如果对象指向相同的类实例。  
  
## <a name="determining-if-two-objects-are-not-identical"></a>确定两个对象是否不相同  
 有时你想要执行的操作，如果两个对象不完全相同，并且它可能难以合并`Not`和`Is`，例如`If Not obj1 Is obj2`。 在这种情况下可以使用`IsNot`运算符。  
  
#### <a name="to-determine-if-two-objects-are-not-identical"></a>若要确定两个对象是否不相同  
  
1.  设置`Boolean`要测试两个对象表达式。  
  
2.  在测试表达式中，使用`IsNot`运算符具有两个对象作为操作数。  
  
     `IsNot` 返回`True`如果对象未指向相同的类实例。  
  
## <a name="example"></a>示例  
 下面的示例测试对`Object`变量上以查看它们是否指向相同的类实例。  
  
 [!code-vb[VbVbalrKeywords#14](../../../../visual-basic/language-reference/codesnippet/VisualBasic/how-to-determine-whether-two-objects-are-identical_1.vb)]  
  
 前面的示例显示下面的输出。  
  
 `objA different from objB? True`  
  
 `objA identical to objC? True`  
  
## <a name="see-also"></a>请参阅  
 [Object 数据类型](../../../../visual-basic/language-reference/data-types/object-data-type.md)  
 [对象变量](../../../../visual-basic/programming-guide/language-features/variables/object-variables.md)  
 [对象变量值](../../../../visual-basic/programming-guide/language-features/variables/object-variable-values.md)  
 [Is 运算符](../../../../visual-basic/language-reference/operators/is-operator.md)  
 [IsNot 运算符](../../../../visual-basic/language-reference/operators/isnot-operator.md)  
 [如何：确定两个对象是否相关](../../../../visual-basic/programming-guide/language-features/variables/how-to-determine-whether-two-objects-are-related.md)  
 [Me、My、MyBase 和 MyClass](../../../../visual-basic/programming-guide/program-structure/me-my-mybase-and-myclass.md)
