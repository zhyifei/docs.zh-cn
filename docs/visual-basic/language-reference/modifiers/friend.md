---
title: Friend (Visual Basic)
ms.date: 07/20/2015
ms.prod: .net
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords: vb.Friend
helpviewer_keywords:
- Friend keyword [Visual Basic]
- Friend access modifier
- Friend keyword [Visual Basic], syntax
- Protected Friend keyword combination
- Friend keyword [Visual Basic], and Protected
ms.assetid: b664605e-1c79-4728-b996-aa59c50846bc
caps.latest.revision: "25"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 32f993e4b9bcd126ebb6d70310fc0781e8b137b9
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="friend-visual-basic"></a>Friend (Visual Basic)
指定一个或多个已声明的编程元素只能在包含其声明的程序集内访问。  
  
## <a name="remarks"></a>备注  
 在许多情况下，所需编程元素，如类和结构为供由整个程序集，不仅声明它们的组件。 但是，你可能不希望它们可由程序集外部的代码 （例如，如果应用程序是专有）。 如果你想要限制到这种方式中的元素的访问，可以将其声明使用`Friend`修饰符。  
  
 其他类、 结构和编译为相同的模块中的代码程序集可以访问所有`Friend`该程序集中的元素。  
  
 `Friend`访问通常是应用程序的编程元素的首选的级别和`Friend`是默认访问接口、 模块、 类或结构的级别。  
  
 你可以使用`Friend`只能在模块、 接口或命名空间级别。 因此，声明上下文`Friend`元素必须是源文件、 命名空间、 接口、 模块、 类或结构; 它不能是一个过程。  
  
 你可以使用`Friend`结合修饰符[受保护](../../../visual-basic/language-reference/modifiers/protected.md)同一声明中的修饰符。 此组合授予同时`Friend`访问和上已声明的元素，这样便可从同一程序集，从其自身的类，以及从派生类中的任何位置访问受保护的访问。 你可以指定`Protected Friend`仅适用于的类的成员。  
  
 有关的比较`Friend`以及其他访问修饰符，请参阅[访问 Visual Basic 中的级别](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md)。  
  
> [!NOTE]
>  你可以指定另一个程序集是友元程序集，从而使其可以访问所有类型和成员标记为`Friend`。 有关详细信息，请参阅[友元程序集](http://msdn.microsoft.com/library/df0c70ea-2c2a-4bdc-9526-df951ad2d055)。  
  
## <a name="example"></a>示例  
 下面的类使用`Friend`修饰符以允许访问某些成员同一程序集内的其他编程元素。  
  
 [!code-vb[VbVbalrAccessModifiers#1](../../../visual-basic/language-reference/modifiers/codesnippet/VisualBasic/friend_1.vb)]  
  
## <a name="usage"></a>用法  
 你可以使用`Friend`修饰符在这两个上下文：  
  
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
  
## <a name="see-also"></a>另请参阅  
 <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute>  
 [Public](../../../visual-basic/language-reference/modifiers/public.md)  
 [Protected](../../../visual-basic/language-reference/modifiers/protected.md)  
 [Private](../../../visual-basic/language-reference/modifiers/private.md)  
 [在 Visual Basic 中的访问级别](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md)  
 [过程](../../../visual-basic/programming-guide/language-features/procedures/index.md)  
 [结构](../../../visual-basic/programming-guide/language-features/data-types/structures.md)  
 [对象和类](../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md)
