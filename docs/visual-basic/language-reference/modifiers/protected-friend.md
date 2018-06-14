---
title: 受保护的友元 (Visual Basic)
ms.date: 05/10/2018
helpviewer_keywords:
- Protected Friend keyword [Visual Basic]
- Protected Friend keyword [Visual Basic], syntax
ms.openlocfilehash: b72cbee0394043620e792d1c014bfe55121e175e
ms.sourcegitcommit: 22c3c8f74eaa138dbbbb02eb7d720fce87fc30a9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/18/2018
ms.locfileid: "34306536"
---
# <a name="protected-friend-visual-basic"></a>受保护的友元 (Visual Basic)

`Protected Friend`关键字组合都是成员访问修饰符。 它授予同时[友元](friend.md)访问和[受保护](protected.md)上已声明的元素，这样便可从同一程序集，从其自身的类，以及从派生类中的任何位置访问的访问权限。 你可以指定`Protected Friend`仅能对成员的类; 不能应用`Protected Friend`结构的成员由于结构不能被继承。

> [!NOTE]
> 在 Visual Studio 中，选择 F1 帮助上`protected friend`提供为帮助[保护](protected.md)或[友元](friend.md)。 IDE 选取下光标，而不是复合 word 单个标记。

## <a name="rules"></a>规则

- **声明上下文。** 你可以使用`Protected Friend`只能在类级别。 这意味着的声明上下文`Protected`元素必须是类，并且不能为源文件、 命名空间、 接口、 模块、 结构或过程。 


## <a name="see-also"></a>请参阅

[Public](../../../visual-basic/language-reference/modifiers/public.md)  
[Protected](../../../visual-basic/language-reference/modifiers/protected.md)  
[友元](friend.md)   
[Private](../../../visual-basic/language-reference/modifiers/private.md)  
[私有受保护](./private-protected.md)   
[在 Visual Basic 中的访问级别](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md)  
[过程](../../../visual-basic/programming-guide/language-features/procedures/index.md)  
[结构](../../../visual-basic/programming-guide/language-features/data-types/structures.md)  
[对象和类](../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md)
