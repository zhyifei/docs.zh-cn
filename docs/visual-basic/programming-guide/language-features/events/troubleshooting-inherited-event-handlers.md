---
title: "有关 Visual Basic 中继承的事件处理程序的疑难解答"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- troubleshooting events [Visual Basic]
- inherited events [Visual Basic]
- troubleshooting Visual Basic, event handlers
- event handling, troubleshooting
- event handlers, troubleshooting
ms.assetid: e1c8759f-5370-4308-8476-8c48b73509bf
caps.latest.revision: "11"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: e0e8f0b669566bbee6530931bfba9808fad0c085
ms.sourcegitcommit: c2e216692ef7576a213ae16af2377cd98d1a67fa
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/22/2017
---
# <a name="troubleshooting-inherited-event-handlers-in-visual-basic"></a>有关 Visual Basic 中继承的事件处理程序的疑难解答
本主题列出使用继承的组件中的事件处理程序时出现的常见问题。  
  
## <a name="procedures"></a>过程  
  
#### <a name="code-in-event-handler-executes-twice-for-every-call"></a>为每个调用两次执行中事件处理程序代码  
  
-   继承的事件处理程序中不能包含[处理](../../../../visual-basic/language-reference/statements/handles-clause.md)子句。 基类中的方法已与事件相关联，并且会相应地触发。 删除`Handles`子句从继承的方法。  
  
     [!code-vb[VbVbalrEvents#32](../../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/troubleshooting-inherited-event-handlers_1.vb)]  
  
-   如果继承的方法不具有`Handles`关键字，验证你的代码不包含一个额外[AddHandler 语句](../../../../visual-basic/language-reference/statements/addhandler-statement.md)或任何其他方法，用于处理同一事件。  
  
## <a name="see-also"></a>另请参阅  
 [事件](../../../../visual-basic/programming-guide/language-features/events/index.md)
