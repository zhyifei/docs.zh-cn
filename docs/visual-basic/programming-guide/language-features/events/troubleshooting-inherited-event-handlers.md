---
title: 有关 Visual Basic 中继承的事件处理程序的疑难解答
ms.date: 07/20/2015
helpviewer_keywords:
- troubleshooting events [Visual Basic]
- inherited events [Visual Basic]
- troubleshooting Visual Basic, event handlers
- event handling, troubleshooting
- event handlers, troubleshooting
ms.assetid: e1c8759f-5370-4308-8476-8c48b73509bf
ms.openlocfilehash: f6355cf7fc2e43651c1112d048220a8179968c76
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
---
# <a name="troubleshooting-inherited-event-handlers-in-visual-basic"></a>有关 Visual Basic 中继承的事件处理程序的疑难解答
本主题列出使用继承的组件中的事件处理程序时出现的常见问题。  
  
## <a name="procedures"></a>过程  
  
#### <a name="code-in-event-handler-executes-twice-for-every-call"></a>为每个调用两次执行中事件处理程序代码  
  
-   继承的事件处理程序中不能包含[处理](../../../../visual-basic/language-reference/statements/handles-clause.md)子句。 基类中的方法已与事件相关联，并且会相应地触发。 删除`Handles`子句从继承的方法。  
  
     [!code-vb[VbVbalrEvents#32](../../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/troubleshooting-inherited-event-handlers_1.vb)]  
  
-   如果继承的方法不具有`Handles`关键字，验证你的代码不包含一个额外[AddHandler 语句](../../../../visual-basic/language-reference/statements/addhandler-statement.md)或任何其他方法，用于处理同一事件。  
  
## <a name="see-also"></a>请参阅  
 [事件](../../../../visual-basic/programming-guide/language-features/events/index.md)
