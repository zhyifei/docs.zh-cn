---
title: 其他控件结构
ms.date: 07/20/2015
helpviewer_keywords:
- statements [Visual Basic], control flow
- control structures [Visual Basic]
ms.assetid: 24b811f7-98ba-40ec-8dd3-4d528cfa4574
ms.openlocfilehash: 758df361f421684655147ae288af3f350e53c4d7
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/22/2019
ms.locfileid: "74348137"
---
# <a name="other-control-structures-visual-basic"></a>其他控件结构 (Visual Basic)
Visual Basic 提供了控制结构，可帮助您释放资源或减少必须重复对象引用的次数。  
  
## <a name="usingend-using-construction"></a>使用 .。。使用构造结束  
 `Using...End Using` 构造建立了一个语句块，使用该语句块可以使用诸如 SQL 连接等资源。 您可以选择通过 `Using` 语句获取资源。 退出 `Using` 块时，Visual Basic 会自动释放资源，以便其他代码可以使用该资源。 资源必须是本地的，并且是可释放的。 有关详细信息，请参阅 [Using 语句](../../../../visual-basic/language-reference/statements/using-statement.md)。  
  
## <a name="withend-with-construction"></a>用 .。。以构造结尾  
 `With...End With` 构造使你可以指定一个对象引用一次，并运行一系列访问其成员的语句。 这可以简化代码和提高性能，因为 Visual Basic 不必为访问它的每个语句重新建立引用。 有关详细信息，请参阅[With .。。End With 语句](../../../../visual-basic/language-reference/statements/with-end-with-statement.md)。  
  
## <a name="see-also"></a>另请参阅

- [控制流](../../../../visual-basic/programming-guide/language-features/control-flow/index.md)
- [决策结构](../../../../visual-basic/programming-guide/language-features/control-flow/decision-structures.md)
- [循环结构](../../../../visual-basic/programming-guide/language-features/control-flow/loop-structures.md)
- [嵌套的控件结构](../../../../visual-basic/programming-guide/language-features/control-flow/nested-control-structures.md)
- [Using 语句](../../../../visual-basic/language-reference/statements/using-statement.md)
- [With...End With 语句](../../../../visual-basic/language-reference/statements/with-end-with-statement.md)
