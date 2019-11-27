---
title: Implements 子句
ms.date: 07/20/2015
f1_keywords:
- vb.ImplementsClause
helpviewer_keywords:
- interface implementation [Visual Basic], reimplementation
- interface members [Visual Basic], reimplementation
- interface members [Visual Basic], Implements keyword
- interface members
- members [Visual Basic], reimplementation
- interface implementation [Visual Basic], Implements keyword
- interface members [Visual Basic], implementing
- Implements keyword [Visual Basic]
- Implements statement [Visual Basic], about Implements
- members [Visual Basic], implementing
- members [Visual Basic], Implements keyword
- reimplementation
ms.assetid: 5252cdf9-964d-4fc6-af0f-0449b7126b5a
ms.openlocfilehash: f114aee75356e59eafd9d3ba6af9c64402cb374f
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/22/2019
ms.locfileid: "74345877"
---
# <a name="implements-clause-visual-basic"></a>Implements 子句 (Visual Basic)
指示类或结构成员正在为接口中定义的成员提供实现。  
  
## <a name="remarks"></a>备注  
`Implements` 关键字与[Implements 语句](../../../visual-basic/language-reference/statements/implements-statement.md)不同。 使用 `Implements` 语句来指定一个类或结构实现一个或多个接口，然后，对于每个成员，都使用 `Implements` 关键字指定哪个接口和它所实现的成员。

如果类或结构实现了接口，则它必须紧跟在[类语句](../../../visual-basic/language-reference/statements/class-statement.md)或[结构语句](../../../visual-basic/language-reference/statements/structure-statement.md)之后的 `Implements` 语句，并且必须实现该接口定义的所有成员。

## <a name="reimplementation"></a>重新实现  
在派生类中，您可以重新实现基类已经实现的接口成员。 这不同于在以下方面重写基类成员：

- 基类成员不需要是可[重写](../../../visual-basic/language-reference/modifiers/overridable.md)的，而重新实现。
- 您可以使用其他名称重新实现该成员。

在以下上下文中，可以使用 `Implements` 关键字：

- [Event 语句](../../../visual-basic/language-reference/statements/event-statement.md)
- [Function 语句](../../../visual-basic/language-reference/statements/function-statement.md)
- [Property 语句](../../../visual-basic/language-reference/statements/property-statement.md)
- [Sub 语句](../../../visual-basic/language-reference/statements/sub-statement.md)  
  
## <a name="see-also"></a>另请参阅

- [Implements 语句](../../../visual-basic/language-reference/statements/implements-statement.md)
- [Interface 语句](../../../visual-basic/language-reference/statements/interface-statement.md)
- [Class 语句](../../../visual-basic/language-reference/statements/class-statement.md)
- [Structure 语句](../../../visual-basic/language-reference/statements/structure-statement.md)
