---
title: Protected Friend
ms.date: 05/10/2018
helpviewer_keywords:
- Protected Friend keyword [Visual Basic]
- Protected Friend keyword [Visual Basic], syntax
ms.openlocfilehash: f92021f5f0dab9762470c270bdd5182187d587e5
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/22/2019
ms.locfileid: "74351322"
---
# <a name="protected-friend-visual-basic"></a>受保护的朋友（Visual Basic）

`Protected Friend` 关键字组合是一种成员访问修饰符。 它在已声明的元素上授予[朋友](friend.md)访问和[受保护](protected.md)的访问，因此可以从同一程序集中的任何位置、从其自己的类和派生类中访问它们。 只能在类的成员上指定 `Protected Friend`;无法将 `Protected Friend` 应用到结构的成员，因为结构不能继承。

> [!NOTE]
> 在 Visual Studio 中，选择 `protected friend` 上的 F1 帮助为[受保护](protected.md)的或[朋友](friend.md)提供帮助。 IDE 将选取光标下的单个标记，而不是组合词。

## <a name="rules"></a>规则

**声明上下文。** 只能在类级别使用 `Protected Friend`。 这意味着 `Protected` 元素的声明上下文必须是类，且不能是源文件、命名空间、接口、模块、结构或过程。

## <a name="see-also"></a>另请参阅

- [Public](../../../visual-basic/language-reference/modifiers/public.md)
- [Protected](../../../visual-basic/language-reference/modifiers/protected.md)
- [Friend](friend.md)
- [Private](../../../visual-basic/language-reference/modifiers/private.md)
- [Private Protected](./private-protected.md)
- [Visual Basic 中的访问级别](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md)
- [过程](../../../visual-basic/programming-guide/language-features/procedures/index.md)
- [结构](../../../visual-basic/programming-guide/language-features/data-types/structures.md)
- [对象和类](../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md)
