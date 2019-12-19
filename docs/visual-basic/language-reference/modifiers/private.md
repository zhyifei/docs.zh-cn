---
title: Private
ms.date: 07/20/2015
f1_keywords:
- vb.Private
helpviewer_keywords:
- Private keyword [Visual Basic]
- Private keyword [Visual Basic], syntax
ms.assetid: aba74a2e-5824-4613-bf63-b9ec7787f4e6
ms.openlocfilehash: 5600744aeca79a54f51a1f9ecd0ef00fed4b00fd
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/22/2019
ms.locfileid: "74351333"
---
# <a name="private-visual-basic"></a>Private (Visual Basic)
指定一个或多个已声明的编程元素只能从其声明上下文中访问，包括从任何包含的类型中。  
  
## <a name="remarks"></a>备注  
 如果编程元素表示专有功能，或包含机密数据，则通常需要尽可能严格地限制对其的访问。 通过只允许定义它的模块、类或结构可以实现最大限制。 若要以这种方式限制对某个元素的访问，可使用 `Private`声明该元素。  

> [!NOTE]
> 你还可以使用[私有受保护](private-protected.md)的访问修饰符，这使得成员可从该类内和其包含的程序集中的派生类中访问。

## <a name="rules"></a>规则  

- **声明上下文。** 只能在模块级别使用 `Private`。 这意味着 `Private` 元素的声明上下文必须是模块、类或结构，并且不能是源文件、命名空间、接口或过程。  
  
## <a name="behavior"></a>行为  
  
- **访问级别。** 声明上下文内的所有代码都可以访问其 `Private` 元素。 这包括包含类型中的代码，如枚举中的嵌套类或赋值表达式。 声明上下文外的任何代码都不能访问其 `Private` 元素。  
  
- **访问修饰符。** 指定访问级别的关键字称为*访问修饰符*。 有关访问修饰符的比较，请参阅[Visual Basic 中的访问级别](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md)。  
  
 `Private` 修饰符可用于下面的上下文中：  
  
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
  
## <a name="see-also"></a>请参阅

- [Public](../../../visual-basic/language-reference/modifiers/public.md)
- [Protected](../../../visual-basic/language-reference/modifiers/protected.md)
- [Friend](../../../visual-basic/language-reference/modifiers/friend.md)
- [Private Protected](./private-protected.md)
- [Visual Basic 中的](./protected-friend.md)[受保护的 Friend](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md) 访问级别
- [过程](../../../visual-basic/programming-guide/language-features/procedures/index.md)
- [结构](../../../visual-basic/programming-guide/language-features/data-types/structures.md)
- [对象和类](../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md)
