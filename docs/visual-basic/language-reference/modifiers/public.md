---
title: Public (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.Public
helpviewer_keywords:
- Public keyword [Visual Basic]
- Public keyword [Visual Basic], syntax
- Public access modifier
ms.assetid: 284c9e1b-ed23-499b-9bc9-ad87c11485a5
ms.openlocfilehash: a5e9161132ba6d571daa30ce82e1bfb1dd2b064f
ms.sourcegitcommit: 22c3c8f74eaa138dbbbb02eb7d720fce87fc30a9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/17/2018
ms.locfileid: "34235913"
---
# <a name="public-visual-basic"></a>Public (Visual Basic)
指定一个或多个已声明的编程元素具有任何访问限制。  
  
## <a name="remarks"></a>备注  
 如果您要发布的组件或组组件，如类库，你通常想要可由程序集与互操作的任何代码的编程元素。 若要授予此类不限的访问权限，在元素上，可以将其与声明`Public`。  
  
 公共访问时不需要限制对其的访问，将编程元素的正常级别。 请注意，接口、 模块、 类或结构中声明的元素的访问级别将默认为`Public`如果未另行声明。  
  
## <a name="rules"></a>规则  
  
-   **声明上下文。** 你可以使用`Public`只能在模块、 接口或命名空间级别。 这意味着的声明上下文`Public`元素必须是源文件、 命名空间、 接口、 模块、 类或结构，并且不能为一个过程。  
  
## <a name="behavior"></a>行为  
  
-   **访问级别。** 所有代码都可以都访问模块、 类或结构可以都访问其`Public`元素。  
  
-   **默认访问权限。** 内部过程默认为公共访问，并且你的本地变量不能在其上使用任何访问修饰符。  
  
-   **访问修饰符。** 指定的访问级别的关键字称为*访问修饰符*。 访问修饰符的比较，请参阅[访问 Visual Basic 中的级别](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md)。  
  
 `Public` 修饰符可用于下面的上下文中：  
  
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
  
 [Operator Statement](../../../visual-basic/language-reference/statements/operator-statement.md)  
  
 [Property 语句](../../../visual-basic/language-reference/statements/property-statement.md)  
  
 [Structure 语句](../../../visual-basic/language-reference/statements/structure-statement.md)  
  
 [Sub 语句](../../../visual-basic/language-reference/statements/sub-statement.md)  
  
## <a name="see-also"></a>请参阅  
 [Protected](../../../visual-basic/language-reference/modifiers/protected.md)  
 [Friend](../../../visual-basic/language-reference/modifiers/friend.md)  
 [Private](../../../visual-basic/language-reference/modifiers/private.md)  
 [私有受保护](private-protected.md)   
 [受保护的友元](protected-friend.md)   
 [在 Visual Basic 中的访问级别](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md)  
 [过程](../../../visual-basic/programming-guide/language-features/procedures/index.md)  
 [结构](../../../visual-basic/programming-guide/language-features/data-types/structures.md)  
 [对象和类](../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md)
