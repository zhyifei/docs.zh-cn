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
# <a name="troubleshooting-inherited-event-handlers-in-visual-basic"></a><span data-ttu-id="10d42-102">有关 Visual Basic 中继承的事件处理程序的疑难解答</span><span class="sxs-lookup"><span data-stu-id="10d42-102">Troubleshooting Inherited Event Handlers in Visual Basic</span></span>
<span data-ttu-id="10d42-103">本主题列出使用继承的组件中的事件处理程序时出现的常见问题。</span><span class="sxs-lookup"><span data-stu-id="10d42-103">This topic lists common issues that arise with event handlers in inherited components.</span></span>  
  
## <a name="procedures"></a><span data-ttu-id="10d42-104">过程</span><span class="sxs-lookup"><span data-stu-id="10d42-104">Procedures</span></span>  
  
#### <a name="code-in-event-handler-executes-twice-for-every-call"></a><span data-ttu-id="10d42-105">为每个调用两次执行中事件处理程序代码</span><span class="sxs-lookup"><span data-stu-id="10d42-105">Code in Event Handler Executes Twice for Every Call</span></span>  
  
-   <span data-ttu-id="10d42-106">继承的事件处理程序中不能包含[处理](../../../../visual-basic/language-reference/statements/handles-clause.md)子句。</span><span class="sxs-lookup"><span data-stu-id="10d42-106">An inherited event handler must not include a [Handles](../../../../visual-basic/language-reference/statements/handles-clause.md) clause.</span></span> <span data-ttu-id="10d42-107">基类中的方法已与事件相关联，并且会相应地触发。</span><span class="sxs-lookup"><span data-stu-id="10d42-107">The method in the base class is already associated with the event and will fire accordingly.</span></span> <span data-ttu-id="10d42-108">删除`Handles`子句从继承的方法。</span><span class="sxs-lookup"><span data-stu-id="10d42-108">Remove the `Handles` clause from the inherited method.</span></span>  
  
     [!code-vb[VbVbalrEvents#32](../../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/troubleshooting-inherited-event-handlers_1.vb)]  
  
-   <span data-ttu-id="10d42-109">如果继承的方法不具有`Handles`关键字，验证你的代码不包含一个额外[AddHandler 语句](../../../../visual-basic/language-reference/statements/addhandler-statement.md)或任何其他方法，用于处理同一事件。</span><span class="sxs-lookup"><span data-stu-id="10d42-109">If the inherited method does not have a `Handles` keyword, verify that your code does not contain an extra [AddHandler Statement](../../../../visual-basic/language-reference/statements/addhandler-statement.md) or any additional methods that handle the same event.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="10d42-110">另请参阅</span><span class="sxs-lookup"><span data-stu-id="10d42-110">See Also</span></span>  
 [<span data-ttu-id="10d42-111">事件</span><span class="sxs-lookup"><span data-stu-id="10d42-111">Events</span></span>](../../../../visual-basic/programming-guide/language-features/events/index.md)
