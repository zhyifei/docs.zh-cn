---
title: Protected (Visual Basic)
ms.date: 07/20/2015
ms.prod: .net
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vb.Protected
helpviewer_keywords:
- Protected Friend keyword combination
- Protected keyword [Visual Basic], and Friend
- Protected keyword [Visual Basic], syntax
- Protected access modifier
- Protected keyword [Visual Basic]
ms.assetid: 74ad3d56-309f-49d2-b60c-1d0157d010e8
caps.latest.revision: 16
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 2d0cc7a0cb626a9ec8e2a0e47abc02e5268aed56
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="protected-visual-basic"></a>Protected (Visual Basic)
指定的一个或多个已声明的编程元素都可以访问只能从在其自身的类或从派生类。  
  
## <a name="remarks"></a>备注  
 类中声明的编程元素有时包含敏感数据或受限制的代码，并且你想要限制对元素的访问。 但是，如果类是可继承，且希望派生类的层次结构，它可能有必要为这些派生的类进行访问的数据或代码。 在这种情况下，你希望可以访问同时从基类和所有的派生类中的元素。 若要限制到这种方式中的元素的访问，可将其与声明`Protected`。  
  
## <a name="rules"></a>规则  
  
-   **声明上下文。** 你可以使用`Protected`只能在类级别。 这意味着的声明上下文`Protected`元素必须是类，并且不能为源文件、 命名空间、 接口、 模块、 结构或过程。  
  
-   **组合的修饰符。** 你可以使用`Protected`修饰符一起与[友元](../../../visual-basic/language-reference/modifiers/friend.md)同一声明中的修饰符。 这种组合使得可以从同一程序集，从其自身的类，以及从派生类中的任何位置访问已声明的元素。 你可以指定`Protected Friend`仅适用于的类的成员。  
  
## <a name="behavior"></a>行为  
  
-   **访问级别。** 类中的所有代码可以都访问其元素。 任何派生自的基类的类中的代码可以访问所有`Protected`元素的基类。 对派生的每一代是如此。 这意味着，一个类可以访问`Protected`元素的基类的基类，依次类推。  
  
     受保护的访问不是超集或友元访问权限的子集。  
  
-   **访问修饰符。** 指定的访问级别的关键字称为*访问修饰符*。 访问修饰符的比较，请参阅[访问 Visual Basic 中的级别](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md)。  
  
 `Protected` 修饰符可用于下面的上下文中：  
  
 [Class 语句](../../../visual-basic/language-reference/statements/class-statement.md)  
  
 [Const 语句](../../../visual-basic/language-reference/statements/const-statement.md)  
  
 [Declare 语句](../../../visual-basic/language-reference/statements/declare-statement.md)  
  
 [Delegate 语句](../../../visual-basic/language-reference/statements/delegate-statement.md)  
  
 [Dim 语句](../../../visual-basic/language-reference/statements/dim-statement.md)  
  
 [Enum 语句](../../../visual-basic/language-reference/statements/enum-statement.md)  
  
 [Event 语句](../../../visual-basic/language-reference/statements/event-statement.md)  
  
 [Function 语句](../../../visual-basic/language-reference/statements/function-statement.md)  
  
 [Interface 语句](../../../visual-basic/language-reference/statements/interface-statement.md)  
  
 [Property 语句](../../../visual-basic/language-reference/statements/property-statement.md)  
  
 [Structure 语句](../../../visual-basic/language-reference/statements/structure-statement.md)  
  
 [Sub 语句](../../../visual-basic/language-reference/statements/sub-statement.md)  
  
## <a name="see-also"></a>另请参阅  
 [Public](../../../visual-basic/language-reference/modifiers/public.md)  
 [Friend](../../../visual-basic/language-reference/modifiers/friend.md)  
 [Private](../../../visual-basic/language-reference/modifiers/private.md)  
 [在 Visual Basic 中的访问级别](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md)  
 [过程](../../../visual-basic/programming-guide/language-features/procedures/index.md)  
 [结构](../../../visual-basic/programming-guide/language-features/data-types/structures.md)  
 [对象和类](../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md)
