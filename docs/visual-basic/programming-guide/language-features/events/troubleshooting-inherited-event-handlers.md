---
title: "疑难解答继承在 Visual Basic 中的事件处理程序 |Microsoft 文档"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- troubleshooting events
- inherited events
- troubleshooting Visual Basic, event handlers
- event handling, troubleshooting
- event handlers, troubleshooting
ms.assetid: e1c8759f-5370-4308-8476-8c48b73509bf
caps.latest.revision: 11
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: f64395975821226d42664bbf78b04120d49a38bc
ms.contentlocale: zh-cn
ms.lasthandoff: 04/12/2017

---
# <a name="troubleshooting-inherited-event-handlers-in-visual-basic"></a><span data-ttu-id="0ce12-102">有关 Visual Basic 中继承的事件处理程序的疑难解答</span><span class="sxs-lookup"><span data-stu-id="0ce12-102">Troubleshooting Inherited Event Handlers in Visual Basic</span></span>
<span data-ttu-id="0ce12-103">本主题列出了使用继承的组件中的事件处理程序时出现的常见问题。</span><span class="sxs-lookup"><span data-stu-id="0ce12-103">This topic lists common issues that arise with event handlers in inherited components.</span></span>  
  
## <a name="procedures"></a><span data-ttu-id="0ce12-104">过程</span><span class="sxs-lookup"><span data-stu-id="0ce12-104">Procedures</span></span>  
  
#### <a name="code-in-event-handler-executes-twice-for-every-call"></a><span data-ttu-id="0ce12-105">对于每次调用两次执行事件处理程序中的代码</span><span class="sxs-lookup"><span data-stu-id="0ce12-105">Code in Event Handler Executes Twice for Every Call</span></span>  
  
-   <span data-ttu-id="0ce12-106">继承的事件处理程序中不能包含[处理](../../../../visual-basic/language-reference/statements/handles-clause.md)子句。</span><span class="sxs-lookup"><span data-stu-id="0ce12-106">An inherited event handler must not include a [Handles](../../../../visual-basic/language-reference/statements/handles-clause.md) clause.</span></span> <span data-ttu-id="0ce12-107">方法在基类中的已有与事件相关联，并将相应地激发。</span><span class="sxs-lookup"><span data-stu-id="0ce12-107">The method in the base class is already associated with the event and will fire accordingly.</span></span> <span data-ttu-id="0ce12-108">删除`Handles`子句从继承的方法。</span><span class="sxs-lookup"><span data-stu-id="0ce12-108">Remove the `Handles` clause from the inherited method.</span></span>  
  
     <span data-ttu-id="0ce12-109">[!code-vb[VbVbalrEvents #&32;](../../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/troubleshooting-inherited-event-handlers_1.vb)]</span><span class="sxs-lookup"><span data-stu-id="0ce12-109">[!code-vb[VbVbalrEvents#32](../../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/troubleshooting-inherited-event-handlers_1.vb)]</span></span>  
  
-   <span data-ttu-id="0ce12-110">如果继承的方法没有`Handles`关键字，验证您的代码不包含额外[AddHandler 语句](../../../../visual-basic/language-reference/statements/addhandler-statement.md)或任何其他方法，用于处理同一个事件。</span><span class="sxs-lookup"><span data-stu-id="0ce12-110">If the inherited method does not have a `Handles` keyword, verify that your code does not contain an extra [AddHandler Statement](../../../../visual-basic/language-reference/statements/addhandler-statement.md) or any additional methods that handle the same event.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0ce12-111">另请参阅</span><span class="sxs-lookup"><span data-stu-id="0ce12-111">See Also</span></span>  
 [<span data-ttu-id="0ce12-112">事件</span><span class="sxs-lookup"><span data-stu-id="0ce12-112">Events</span></span>](../../../../visual-basic/programming-guide/language-features/events/index.md)
