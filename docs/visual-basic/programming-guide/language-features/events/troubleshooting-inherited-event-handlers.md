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
ms.openlocfilehash: 704ca667a6d14ade7be0192e872f5e40791cb864
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/18/2019
ms.locfileid: "58830183"
---
# <a name="troubleshooting-inherited-event-handlers-in-visual-basic"></a><span data-ttu-id="fdad1-102">有关 Visual Basic 中继承的事件处理程序的疑难解答</span><span class="sxs-lookup"><span data-stu-id="fdad1-102">Troubleshooting Inherited Event Handlers in Visual Basic</span></span>
<span data-ttu-id="fdad1-103">本主题列出了使用继承的组件中的事件处理程序时出现的常见问题。</span><span class="sxs-lookup"><span data-stu-id="fdad1-103">This topic lists common issues that arise with event handlers in inherited components.</span></span>  
  
## <a name="procedures"></a><span data-ttu-id="fdad1-104">过程</span><span class="sxs-lookup"><span data-stu-id="fdad1-104">Procedures</span></span>  
  
#### <a name="code-in-event-handler-executes-twice-for-every-call"></a><span data-ttu-id="fdad1-105">为每个调用两次执行事件处理程序中的代码</span><span class="sxs-lookup"><span data-stu-id="fdad1-105">Code in Event Handler Executes Twice for Every Call</span></span>  
  
-   <span data-ttu-id="fdad1-106">继承的事件处理程序中不能包含[处理](../../../../visual-basic/language-reference/statements/handles-clause.md)子句。</span><span class="sxs-lookup"><span data-stu-id="fdad1-106">An inherited event handler must not include a [Handles](../../../../visual-basic/language-reference/statements/handles-clause.md) clause.</span></span> <span data-ttu-id="fdad1-107">中的基类的方法已与事件相关联，并且将相应地触发。</span><span class="sxs-lookup"><span data-stu-id="fdad1-107">The method in the base class is already associated with the event and will fire accordingly.</span></span> <span data-ttu-id="fdad1-108">删除`Handles`子句从继承的方法。</span><span class="sxs-lookup"><span data-stu-id="fdad1-108">Remove the `Handles` clause from the inherited method.</span></span>  
  
     [!code-vb[VbVbalrEvents#32](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrEvents/VB/Class1.vb#32)]  
  
-   <span data-ttu-id="fdad1-109">如果继承的方法没有`Handles`关键字，验证你的代码不包含一个额外[AddHandler 语句](../../../../visual-basic/language-reference/statements/addhandler-statement.md)或处理相同事件的任何其他方法。</span><span class="sxs-lookup"><span data-stu-id="fdad1-109">If the inherited method does not have a `Handles` keyword, verify that your code does not contain an extra [AddHandler Statement](../../../../visual-basic/language-reference/statements/addhandler-statement.md) or any additional methods that handle the same event.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fdad1-110">请参阅</span><span class="sxs-lookup"><span data-stu-id="fdad1-110">See also</span></span>

- [<span data-ttu-id="fdad1-111">事件</span><span class="sxs-lookup"><span data-stu-id="fdad1-111">Events</span></span>](../../../../visual-basic/programming-guide/language-features/events/index.md)
