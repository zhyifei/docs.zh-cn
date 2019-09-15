---
title: Friend (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.Friend
helpviewer_keywords:
- Friend keyword [Visual Basic]
- Friend access modifier
- Friend keyword [Visual Basic], syntax
- Protected Friend keyword combination
- Friend keyword [Visual Basic], and Protected
ms.assetid: b664605e-1c79-4728-b996-aa59c50846bc
ms.openlocfilehash: 2a5a2d6b9d99693a551480fa047cedf42888fdf3
ms.sourcegitcommit: 7b1ce327e8c84f115f007be4728d29a89efe11ef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/13/2019
ms.locfileid: "70969055"
---
# <a name="friend-visual-basic"></a>Friend (Visual Basic)
指定只能从包含其声明的程序集内部访问一个或多个已声明的编程元素。  
  
## <a name="remarks"></a>备注  
 在许多情况下，需要由整个程序集使用的编程元素（如类和结构），而不是由声明它们的组件使用。 但是，可能不希望程序集外部的代码（例如，应用程序是专有的）可以访问这些文件。 如果要以这种方式限制对某个元素的访问，则可以使用`Friend`修饰符来声明它。  
  
 编译为同一程序集的其他类、结构和模块中的代码可以访问该程序集中`Friend`的所有元素。  
  
 `Friend`访问通常是应用程序编程元素的首选级别， `Friend`是接口、模块、类或结构的默认访问级别。  
  
 只能在模块`Friend` 、接口或命名空间级别使用。 因此， `Friend`元素的声明上下文必须是源文件、命名空间、接口、模块、类或结构; 它不能是过程。  

> [!NOTE]
> 你还可以使用[受保护的 Friend](protected-friend.md)访问修饰符，使类成员可从该类、派生类和类定义的同一程序集中访问。 若要从同一程序集中的类和派生类中限制对成员的访问，请使用[私有受保护](private-protected.md)的访问修饰符。

 有关和其他访问`Friend`修饰符的比较，请参阅[Visual Basic 中的访问级别](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md)。  
  
> [!NOTE]
> 可以指定另一个程序集是友元程序集，该程序集允许其访问标记为`Friend`的所有类型和成员。 有关详细信息，请参阅[友元程序集](../../../standard/assembly/friend.md)。

## <a name="example"></a>示例  
 下面的类使用`Friend`修饰符允许同一程序集中的其他编程元素访问某些成员。  
  
 [!code-vb[VbVbalrAccessModifiers#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/vbvbalraccessmodifiers/vb/class1.vb#1)]  
  
## <a name="usage"></a>用法  
 可以在以下上下文`Friend`中使用修饰符：  
  
 [Class 语句](../../../visual-basic/language-reference/statements/class-statement.md)  
  
 [Const 语句](../../../visual-basic/language-reference/statements/const-statement.md)  
  
 [Declare 语句](../../../visual-basic/language-reference/statements/declare-statement.md)  
  
 [Delegate 语句](../../../visual-basic/language-reference/statements/delegate-statement.md)  
  
 [Dim 语句](../../../visual-basic/language-reference/statements/dim-statement.md)  
  
 [Enum 语句](../../../visual-basic/language-reference/statements/enum-statement.md)  
  
 [Event 语句](../../../visual-basic/language-reference/statements/event-statement.md)  
  
 [Function 语句](../../../visual-basic/language-reference/statements/function-statement.md)  
  
 [Interface 语句](../../../visual-basic/language-reference/statements/interface-statement.md)  
  
 [Module 语句](../../../visual-basic/language-reference/statements/module-statement.md)  
  
 [Property 语句](../../../visual-basic/language-reference/statements/property-statement.md)  
  
 [Structure 语句](../../../visual-basic/language-reference/statements/structure-statement.md)  
  
 [Sub 语句](../../../visual-basic/language-reference/statements/sub-statement.md)  
  
## <a name="see-also"></a>请参阅

- <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute>
- [Public](../../../visual-basic/language-reference/modifiers/public.md)
- [Protected](../../../visual-basic/language-reference/modifiers/protected.md)
- [Private](../../../visual-basic/language-reference/modifiers/private.md)
- [Private Protected](./private-protected.md)
- [Protected Friend](./protected-friend.md)
- [Visual Basic 中的访问级别](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md)
- [过程](../../../visual-basic/programming-guide/language-features/procedures/index.md)
- [结构](../../../visual-basic/programming-guide/language-features/data-types/structures.md)
- [对象和类](../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md)
