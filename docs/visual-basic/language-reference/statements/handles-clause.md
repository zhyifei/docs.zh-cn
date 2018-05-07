---
title: Handles 子句 (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- Handles
- vb.Handles
helpviewer_keywords:
- Handles keyword [Visual Basic]
ms.assetid: 1b051c0e-f499-42f6-acb5-6f4f27824b40
ms.openlocfilehash: 15ce6a25aa5f403a2e55beb57b3693095743e52f
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
---
# <a name="handles-clause-visual-basic"></a>Handles 子句 (Visual Basic)
声明某一过程可处理指定的事件。  
  
## <a name="syntax"></a>语法  
  
```  
proceduredeclaration Handles eventlist  
```  
  
## <a name="parts"></a>部件  
 `proceduredeclaration`  
 将处理事件的过程的 `Sub` 过程声明。  
  
 `eventlist`  
 `proceduredeclaration` 要处理的事件的列表，以逗号分隔。 事件必须由当前类的基类引发，或由使用 `WithEvents` 关键字声明的对象引发。  
  
## <a name="remarks"></a>备注  
 在过程声明的结尾使用 `Handles` 关键字，以使其处理由使用 `WithEvents` 关键字声明的对象变量引发的事件。 `Handles` 关键字还可在派生类中用于处理来自基类的事件。  
  
 `Handles` 关键字和 `AddHandler` 语句都允许你指定特定过程处理特定事件，但存在差异。 定义过程时使用 `Handles` 关键字，以指定它处理特定事件。 `AddHandler` 语句在运行时将过程连接到事件。 有关详细信息，请参阅[AddHandler 语句](../../../visual-basic/language-reference/statements/addhandler-statement.md)。  
  
 对于自定义事件，应用程序会在添加过程作为事件处理程序时，调用事件的 `AddHandler` 取值函数。 有关自定义事件的详细信息，请参阅[Event 语句](../../../visual-basic/language-reference/statements/event-statement.md)。  
  
## <a name="example"></a>示例  
 [!code-vb[VbVbalrEvents#2](../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/handles-clause_1.vb)]  
  
 下面的示例演示派生类可以如何使用 `Handles` 语句处理来自基类的事件。  
  
 [!code-vb[VbVbalrEvents#3](../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/handles-clause_2.vb)]  
  
## <a name="example"></a>示例  
 下面的示例包含两个按钮事件处理程序**WPF 应用程序**项目。  
  
 [!code-vb[VbVbalrEvents#41](../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/handles-clause_3.vb)]  
  
## <a name="example"></a>示例  
 下面的示例与前面的示例等效。 `Handles` 子句中的 `eventlist` 包含两个按钮的事件。  
  
 [!code-vb[VbVbalrEvents#42](../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/handles-clause_4.vb)]  
  
## <a name="see-also"></a>请参阅  
 [WithEvents](../../../visual-basic/language-reference/modifiers/withevents.md)  
 [AddHandler 语句](../../../visual-basic/language-reference/statements/addhandler-statement.md)  
 [RemoveHandler 语句](../../../visual-basic/language-reference/statements/removehandler-statement.md)  
 [Event 语句](../../../visual-basic/language-reference/statements/event-statement.md)  
 [RaiseEvent 语句](../../../visual-basic/language-reference/statements/raiseevent-statement.md)  
 [事件](../../../visual-basic/programming-guide/language-features/events/index.md)
