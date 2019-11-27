---
title: MustInherit
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
ms.openlocfilehash: 30befaaf194d78d26a57f29c59bf0a603e9f07a3
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/22/2019
ms.locfileid: "74351499"
---
# <a name="mustinherit-visual-basic"></a>MustInherit (Visual Basic)
指定类只能用作基类，并且不能直接从其创建对象。  
  
## <a name="remarks"></a>备注  
 *基类*（也称为*抽象类*）的目的是定义从其派生的所有类所共有的功能。 这会保存派生类，使其不必重新定义公共元素。 在某些情况下，这种通用功能不够完整，无法生成可用的对象，并且每个派生类都定义了缺少的功能。 在这种情况下，你希望使用代码仅在派生类中创建对象。 使用基类上的 `MustInherit` 来强制执行此类。  
  
 `MustInherit` 类的另一种用法是将变量限制为一组相关的类。 你可以定义一个基类，并从其派生所有这些相关的类。 基类不需要提供所有派生类共有的任何功能，但它可以充当用于向变量赋值的筛选器。 如果你使用的代码将变量声明为基类，则 Visual Basic 允许你仅将一个派生类中的对象分配给该变量。  
  
 .NET Framework 定义了多个 `MustInherit` 类，它们 <xref:System.Array>、<xref:System.Enum>和 <xref:System.ValueType>中。 <xref:System.ValueType> 是限制变量的基类的一个示例。 所有值类型都派生自 <xref:System.ValueType>。 如果将变量声明为 <xref:System.ValueType>，则只能将值类型分配给该变量。  
  
## <a name="rules"></a>规则  
  
- **声明上下文。** 只能在 `Class` 语句中使用 `MustInherit`。  
  
- **组合修饰符。** 不能在同一声明中同时指定 `MustInherit` 和 `NotInheritable`。  
  
## <a name="example"></a>示例  
 下面的示例演示强制的继承和强制重写。 基类 `shape` 定义 `acrossLine`变量。 类 `circle` 和 `square` 派生自 `shape`。 它们继承 `acrossLine`的定义，但必须定义函数 `area`，因为每种形状的计算都是不同的。  
  
 [!code-vb[VbVbalrKeywords#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrKeywords/VB/Class1.vb#2)]  
  
 可以将 `shape1` 和 `shape2` 声明为 `shape`类型。 但是，不能从 `shape` 创建对象，因为它缺少函数 `area` 的功能，并将其标记为 `MustInherit`。  
  
 由于它们被声明为 `shape`，因此 `shape1` 和 `shape2` 的变量仅限于派生类 `circle` 和 `square`中的对象。 Visual Basic 不允许将任何其他对象分配给这些变量，这为你提供了高级别的类型安全性。  
  
## <a name="usage"></a>用法  
 `MustInherit` 修饰符可用于以下上下文：  
  
 [Class 语句](../../../visual-basic/language-reference/statements/class-statement.md)  
  
## <a name="see-also"></a>另请参阅

- [Inherits 语句](../../../visual-basic/language-reference/statements/inherits-statement.md)
- [NotInheritable](../../../visual-basic/language-reference/modifiers/notinheritable.md)
- [关键字](../../../visual-basic/language-reference/keywords/index.md)
- [继承的基础知识](../../../visual-basic/programming-guide/language-features/objects-and-classes/inheritance-basics.md)
