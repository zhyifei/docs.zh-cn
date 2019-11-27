---
title: 公共
ms.date: 07/20/2015
f1_keywords:
- vb.Public
helpviewer_keywords:
- Public keyword [Visual Basic]
- Public keyword [Visual Basic], syntax
- Public access modifier
ms.assetid: 284c9e1b-ed23-499b-9bc9-ad87c11485a5
ms.openlocfilehash: 35bf1a65e0b8f24a1263adc480719c69b95dff9b
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/22/2019
ms.locfileid: "74351296"
---
# <a name="public-visual-basic"></a>Public (Visual Basic)
指定一个或多个已声明的编程元素不具有访问限制。  
  
## <a name="remarks"></a>备注  
 如果要发布一个组件或一组组件（如类库），通常会希望与程序集互操作的任何代码都可以访问编程元素。 若要对某个元素授予这种无限制的访问权限，可以使用 `Public`来声明它。  
  
 当不需要限制对编程元素的访问权限时，公共访问是该元素的正常级别。 请注意，在接口、模块、类或结构中声明的元素的访问级别默认为 `Public` 如果您不另行声明。  
  
## <a name="rules"></a>规则  
  
- **声明上下文。** 只能在模块、接口或命名空间级别使用 `Public`。 这意味着 `Public` 元素的声明上下文必须是源文件、命名空间、接口、模块、类或结构，不能是过程。  
  
## <a name="behavior"></a>行为  
  
- **访问级别。** 可以访问模块、类或结构的所有代码都可以访问其 `Public` 元素。  
  
- **默认访问权限。** 过程中的局部变量默认为公共访问，您不能对其使用任何访问修饰符。  
  
- **访问修饰符。** 指定访问级别的关键字称为*访问修饰符*。 有关访问修饰符的比较，请参阅[Visual Basic 中的访问级别](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md)。  
  
 `Public` 修饰符可用于下面的上下文中：  
  
 [Class 语句](../../../visual-basic/language-reference/statements/class-statement.md)  
  
 [Const 语句](../../../visual-basic/language-reference/statements/const-statement.md)  
  
 [Declare Statement](../../../visual-basic/language-reference/statements/declare-statement.md)  
  
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
  
## <a name="see-also"></a>另请参阅

- [Protected](../../../visual-basic/language-reference/modifiers/protected.md)
- [Friend](../../../visual-basic/language-reference/modifiers/friend.md)
- [Private](../../../visual-basic/language-reference/modifiers/private.md)
- [Private Protected](private-protected.md)
- [Protected Friend](protected-friend.md)
- [Visual Basic 中的访问级别](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md)
- [过程](../../../visual-basic/programming-guide/language-features/procedures/index.md)
- [结构](../../../visual-basic/programming-guide/language-features/data-types/structures.md)
- [对象和类](../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md)
