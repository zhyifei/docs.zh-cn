---
title: Key (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.AnonymousKey
helpviewer_keywords:
- anonymous types [Visual Basic], key
- Key [Visual Basic]
- Key keyword [Visual Basic]
ms.assetid: 7697a928-7d14-4430-a72a-c9e96e8d6c11
ms.openlocfilehash: 92d54e3135142bc02a17f3ce5ac078a356c139be
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
---
# <a name="key-visual-basic"></a>Key (Visual Basic)
`Key`关键字允许您指定的属性的匿名类型的行为。 仅属性你指派为键属性参与的匿名类型实例或计算的哈希代码值之间的相等性测试。 无法更改的键属性的值。  
  
 你可以指定匿名类型的属性为键属性放置关键字`Key`其声明的初始化列表中的前面。 在下面的示例中，`Airline`和`FlightNo`是键属性，但`Gate`不是。  
  
 [!code-vb[VbVbalrAnonymousTypes#26](../../../visual-basic/language-reference/modifiers/codesnippet/VisualBasic/key_1.vb)]  
  
 创建新的匿名类型后，它直接继承自<xref:System.Object>。 编译器将重写继承的三个成员： <xref:System.Object.Equals%2A>， <xref:System.Object.GetHashCode%2A>，和<xref:System.Object.ToString%2A>。 为生成的重写代码<xref:System.Object.Equals%2A>和<xref:System.Object.GetHashCode%2A>基于键属性。 如果在类型中，没有密钥属性<xref:System.Object.GetHashCode%2A>和<xref:System.Object.Equals%2A>不重写。  
  
## <a name="equality"></a>相等  
 匿名类型的两个实例相等，如果它们相同类型的实例，并且它们的键属性的值是否相等。 在以下示例中，`flight2`等同于`flight1`从前面的示例因为它们是相同的匿名的实例类型和它们具有匹配它们的键属性的值。 但是，`flight3`是否不等于`flight1`因为它有键属性的不同值`FlightNo`。 实例`flight4`不与相同的类型`flight1`因为它们将不同属性指定为键属性。  
  
 [!code-vb[VbVbalrAnonymousTypes#27](../../../visual-basic/language-reference/modifiers/codesnippet/VisualBasic/key_2.vb)]  
  
 如果两个实例使用只有非键属性，同样的名称、 类型、 顺序和值，声明两个实例不相等。 不使用密钥的属性实例是仅等于其自身。  
  
 有关在其下两个匿名类型实例是相同的匿名类型的实例的条件的详细信息，请参阅[匿名类型](../../../visual-basic/programming-guide/language-features/objects-and-classes/anonymous-types.md)。  
  
## <a name="hash-code-calculation"></a>哈希代码计算  
 如<xref:System.Object.Equals%2A>，在中定义的哈希函数<xref:System.Object.GetHashCode%2A>匿名类型基于键属性的类型。 下面的示例显示之间的交互键属性以及哈希代码值。  
  
 具有相同的值的所有键属性的匿名类型的实例具有相同的哈希代码值，即使非键属性时，没有匹配值。 下面的语句返回`True`。  
  
 [!code-vb[VbVbalrAnonymousTypes#37](../../../visual-basic/language-reference/modifiers/codesnippet/VisualBasic/key_3.vb)]  
  
 具有不同的值的一个或多个键属性的匿名类型的实例具有不同的哈希代码值。 下面的语句返回`False`。  
  
 [!code-vb[VbVbalrAnonymousTypes#38](../../../visual-basic/language-reference/modifiers/codesnippet/VisualBasic/key_4.vb)]  
  
 将不同属性指定为键属性的匿名类型的实例不是同一类型的实例。 即使的名称和所有属性的值相同时，它们具有不同的哈希代码值。 下面的语句返回`False`。  
  
 [!code-vb[VbVbalrAnonymousTypes#39](../../../visual-basic/language-reference/modifiers/codesnippet/VisualBasic/key_5.vb)]  
  
## <a name="read-only-values"></a>只读的值  
 无法更改的键属性的值。 例如，在`flight1`前面的示例中，`Airline`和`FlightNo`字段是只读的但`Gate`可以更改。  
  
 [!code-vb[VbVbalrAnonymousTypes#28](../../../visual-basic/language-reference/modifiers/codesnippet/VisualBasic/key_6.vb)]  
  
## <a name="see-also"></a>请参阅  
 [匿名类型定义](../../../visual-basic/programming-guide/language-features/objects-and-classes/anonymous-type-definition.md)  
 [如何：推断匿名类型声明中的属性名和类型](../../../visual-basic/programming-guide/language-features/objects-and-classes/how-to-infer-property-names-and-types-in-anonymous-type-declarations.md)  
 [匿名类型](../../../visual-basic/programming-guide/language-features/objects-and-classes/anonymous-types.md)
