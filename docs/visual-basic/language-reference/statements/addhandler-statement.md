---
title: AddHandler 语句
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vb.AddHandlerMethod
- addhandler
- vb.addhandler
helpviewer_keywords:
- AddHandler statement [Visual Basic]
ms.assetid: cfe69799-2a0f-42c0-a99e-09fed954da01
caps.latest.revision: 15
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 07fbfe04ccd01b7d0f99338ef2682238830099dc
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="addhandler-statement"></a><span data-ttu-id="f8e2d-102">AddHandler 语句</span><span class="sxs-lookup"><span data-stu-id="f8e2d-102">AddHandler Statement</span></span>
<span data-ttu-id="f8e2d-103">将事件与事件处理程序关联在运行时。</span><span class="sxs-lookup"><span data-stu-id="f8e2d-103">Associates an event with an event handler at run time.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f8e2d-104">语法</span><span class="sxs-lookup"><span data-stu-id="f8e2d-104">Syntax</span></span>  
  
```  
AddHandler event, AddressOf eventhandler  
```  
  
## <a name="parts"></a><span data-ttu-id="f8e2d-105">部件</span><span class="sxs-lookup"><span data-stu-id="f8e2d-105">Parts</span></span>  
 `event`  
 <span data-ttu-id="f8e2d-106">要处理的事件名称。</span><span class="sxs-lookup"><span data-stu-id="f8e2d-106">The name of the event to handle.</span></span>  
  
 `eventhandler`  
 <span data-ttu-id="f8e2d-107">处理事件的过程的名称。</span><span class="sxs-lookup"><span data-stu-id="f8e2d-107">The name of a procedure that handles the event.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f8e2d-108">备注</span><span class="sxs-lookup"><span data-stu-id="f8e2d-108">Remarks</span></span>  
 <span data-ttu-id="f8e2d-109">`AddHandler`和`RemoveHandler`语句使您可以启动和停止程序执行期间的任何时候的事件处理。</span><span class="sxs-lookup"><span data-stu-id="f8e2d-109">The `AddHandler` and `RemoveHandler` statements allow you to start and stop event handling at any time during program execution.</span></span>  
  
 <span data-ttu-id="f8e2d-110">签名`eventhandler`过程必须与匹配的事件的签名`event`。</span><span class="sxs-lookup"><span data-stu-id="f8e2d-110">The signature of the `eventhandler` procedure must match the signature of the event `event`.</span></span>  
  
 <span data-ttu-id="f8e2d-111">`Handles` 关键字和 `AddHandler` 语句都允许你指定特定过程处理特定事件，但存在差异。</span><span class="sxs-lookup"><span data-stu-id="f8e2d-111">The `Handles` keyword and the `AddHandler` statement both allow you to specify that particular procedures handle particular events, but there are differences.</span></span> <span data-ttu-id="f8e2d-112">`AddHandler` 语句在运行时将过程连接到事件。</span><span class="sxs-lookup"><span data-stu-id="f8e2d-112">The `AddHandler` statement connects procedures to events at run time.</span></span> <span data-ttu-id="f8e2d-113">定义过程时使用 `Handles` 关键字，以指定它处理特定事件。</span><span class="sxs-lookup"><span data-stu-id="f8e2d-113">Use the `Handles` keyword when defining a procedure to specify that it handles a particular event.</span></span> <span data-ttu-id="f8e2d-114">有关详细信息，请参阅[处理](../../../visual-basic/language-reference/statements/handles-clause.md)。</span><span class="sxs-lookup"><span data-stu-id="f8e2d-114">For more information, see [Handles](../../../visual-basic/language-reference/statements/handles-clause.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="f8e2d-115">对于自定义事件，`AddHandler`语句调用事件的`AddHandler`访问器。</span><span class="sxs-lookup"><span data-stu-id="f8e2d-115">For custom events, the `AddHandler` statement invokes the event's `AddHandler` accessor.</span></span> <span data-ttu-id="f8e2d-116">有关自定义事件的详细信息，请参阅[Event 语句](../../../visual-basic/language-reference/statements/event-statement.md)。</span><span class="sxs-lookup"><span data-stu-id="f8e2d-116">For more information on custom events, see [Event Statement](../../../visual-basic/language-reference/statements/event-statement.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="f8e2d-117">示例</span><span class="sxs-lookup"><span data-stu-id="f8e2d-117">Example</span></span>  
 [!code-vb[VbVbalrEvents#17](../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/addhandler-statement_1.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="f8e2d-118">另请参阅</span><span class="sxs-lookup"><span data-stu-id="f8e2d-118">See Also</span></span>  
 [<span data-ttu-id="f8e2d-119">RemoveHandler 语句</span><span class="sxs-lookup"><span data-stu-id="f8e2d-119">RemoveHandler Statement</span></span>](../../../visual-basic/language-reference/statements/removehandler-statement.md)  
 [<span data-ttu-id="f8e2d-120">Handles</span><span class="sxs-lookup"><span data-stu-id="f8e2d-120">Handles</span></span>](../../../visual-basic/language-reference/statements/handles-clause.md)  
 [<span data-ttu-id="f8e2d-121">Event 语句</span><span class="sxs-lookup"><span data-stu-id="f8e2d-121">Event Statement</span></span>](../../../visual-basic/language-reference/statements/event-statement.md)  
 [<span data-ttu-id="f8e2d-122">事件</span><span class="sxs-lookup"><span data-stu-id="f8e2d-122">Events</span></span>](../../../visual-basic/programming-guide/language-features/events/index.md)
