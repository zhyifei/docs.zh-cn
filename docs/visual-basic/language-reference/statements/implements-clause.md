---
title: Implements 子句 (Visual Basic)
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
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
caps.latest.revision: 15
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 73f66eda29e37fda15b4c838da5a0458684131da
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="implements-clause-visual-basic"></a>Implements 子句 (Visual Basic)
指示类或结构成员提供在接口中定义的成员的实现。  
  
## <a name="remarks"></a>备注  
`Implements`关键字不与相同[Implements 语句](../../../visual-basic/language-reference/statements/implements-statement.md)。 你使用`Implements`语句指定的类或结构实现一个或多个接口，证书，然后为每个成员你使用`Implements`关键字来指定哪个接口和哪个成员它实现。

如果类或结构实现接口时，它必须包含`Implements`语句后立即[类语句](../../../visual-basic/language-reference/statements/class-statement.md)或[Structure 语句](../../../visual-basic/language-reference/statements/structure-statement.md)，并且它必须实现的所有成员定义由接口。

## <a name="reimplementation"></a>重新实现  
在派生类中，你可以重新实现接口成员的基类实现。 这是不同于重写基类成员在以下方面：

- 基类成员不需要为[可重写](../../../visual-basic/language-reference/modifiers/overridable.md)若要将根据。
- 你可以重新实现具有不同名称的成员。

`Implements`关键字可以在以下上下文中使用：
- [Event 语句](../../../visual-basic/language-reference/statements/event-statement.md)
- [Function 语句](../../../visual-basic/language-reference/statements/function-statement.md)
- [Property 语句](../../../visual-basic/language-reference/statements/property-statement.md)
- [Sub 语句](../../../visual-basic/language-reference/statements/sub-statement.md)  
  
## <a name="see-also"></a>另请参阅  
 [Implements 语句](../../../visual-basic/language-reference/statements/implements-statement.md)  
 [Interface 语句](../../../visual-basic/language-reference/statements/interface-statement.md)  
 [Class 语句](../../../visual-basic/language-reference/statements/class-statement.md)  
 [Structure 语句](../../../visual-basic/language-reference/statements/structure-statement.md)
