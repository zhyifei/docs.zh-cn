---
title: MustInherit (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- MustInherit
- vb.MustInherit
helpviewer_keywords:
- classes [Visual Basic], abstract
- MustInherit classes [Visual Basic], MustInherit keyword
- abstract classes [Visual Basic], MustInherit class
- MustInherit keyword [Visual Basic]
ms.assetid: b8f05185-90e3-4dd7-adc2-90d852fab5b4
ms.openlocfilehash: 5d622c1cff77a45c8de7772af7efbb73586f4400
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
---
# <a name="mustinherit-visual-basic"></a>MustInherit (Visual Basic)
指定一个类可以仅用作基类，您不能直接从它创建一个对象。  
  
## <a name="remarks"></a>备注  
 用途*基类*(也称为*抽象类*) 是定义普遍适用于所有从它派生的类的功能。 这可以节省派生的类无需重新定义的常用元素。 在某些情况下，此常用的功能不足够完成，以使可用对象，并且每个派生的类定义所缺少的功能。 在这种情况下，你希望使用的代码只能从派生类中创建对象。 你使用`MustInherit`来强制执行此基本类。  
  
 另一个用途`MustInherit`类是限制对一组相关的类的变量。 你可以定义一个基类，并从其派生所有这些相关的类。 基类不需要提供任何功能普遍适用于所有派生的类，但其可用作筛选器将值赋给变量。 如果你使用的代码声明一个变量，作为类的基类，则 Visual Basic，可从派生类之一仅对象分配给该变量。  
  
 .NET Framework 定义了几个`MustInherit`类，它们之间<xref:System.Array>， <xref:System.Enum>，和<xref:System.ValueType>。 <xref:System.ValueType> 是一个基类，用于限制变量的示例。 所有值类型都派生自<xref:System.ValueType>。 如果你声明一个变量，作为<xref:System.ValueType>，可以将只有值类型分配给该变量。  
  
## <a name="rules"></a>规则  
  
-   **声明上下文。** 你可以使用`MustInherit`仅在`Class`语句。  
  
-   **组合的修饰符。** 不能指定`MustInherit`连同`NotInheritable`同一声明中。  
  
## <a name="example"></a>示例  
 下面的示例演示强制的继承和强制重写。 基类`shape`定义变量`acrossLine`。 类`circle`和`square`派生自`shape`。 他们会继承的定义`acrossLine`，但它们必须定义函数`area`因为该计算每种类型的形状不同。  
  
 [!code-vb[VbVbalrKeywords#2](../../../visual-basic/language-reference/codesnippet/VisualBasic/mustinherit_1.vb)]  
  
 你可以声明`shape1`和`shape2`类型`shape`。 但是，你无法从其创建对象`shape`因为它缺少的功能函数`area`和标记`MustInherit`。  
  
 因为它们被声明为`shape`，变量`shape1`和`shape2`限于对象派生的类从`circle`和`square`。 Visual Basic 不允许您将任何其他对象分配给这些变量，这为你提供类型安全的高级别。  
  
## <a name="usage"></a>用法  
 `MustInherit`修饰符可用于在此上下文中：  
  
 [Class 语句](../../../visual-basic/language-reference/statements/class-statement.md)  
  
## <a name="see-also"></a>请参阅  
 [Inherits 语句](../../../visual-basic/language-reference/statements/inherits-statement.md)  
 [NotInheritable](../../../visual-basic/language-reference/modifiers/notinheritable.md)  
 [关键字](../../../visual-basic/language-reference/keywords/index.md)  
 [继承的基础知识](../../../visual-basic/programming-guide/language-features/objects-and-classes/inheritance-basics.md)
