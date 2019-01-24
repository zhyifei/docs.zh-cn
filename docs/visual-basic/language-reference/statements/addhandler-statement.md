---
title: AddHandler 语句 (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.AddHandlerMethod
- addhandler
- vb.addhandler
helpviewer_keywords:
- AddHandler statement [Visual Basic]
ms.assetid: cfe69799-2a0f-42c0-a99e-09fed954da01
ms.openlocfilehash: 6ed6f3d4fd77d714ab554d641c0c0fc4f403bbf8
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54715096"
---
# <a name="addhandler-statement"></a><span data-ttu-id="2a1b9-102">AddHandler 语句</span><span class="sxs-lookup"><span data-stu-id="2a1b9-102">AddHandler Statement</span></span>
<span data-ttu-id="2a1b9-103">在运行时将事件与事件处理程序。</span><span class="sxs-lookup"><span data-stu-id="2a1b9-103">Associates an event with an event handler at run time.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2a1b9-104">语法</span><span class="sxs-lookup"><span data-stu-id="2a1b9-104">Syntax</span></span>  
  
```  
AddHandler event, AddressOf eventhandler  
```  
  
## <a name="parts"></a><span data-ttu-id="2a1b9-105">部件</span><span class="sxs-lookup"><span data-stu-id="2a1b9-105">Parts</span></span>  
|||
|---|---|
|<span data-ttu-id="2a1b9-106">Event — 事件</span><span class="sxs-lookup"><span data-stu-id="2a1b9-106">event</span></span>|<span data-ttu-id="2a1b9-107">要处理的事件的名称。</span><span class="sxs-lookup"><span data-stu-id="2a1b9-107">The name of the event to handle.</span></span>|  
|`eventhandler`|<span data-ttu-id="2a1b9-108">处理事件的过程的名称。</span><span class="sxs-lookup"><span data-stu-id="2a1b9-108">The name of a procedure that handles the event.</span></span>|
|||
  
## <a name="remarks"></a><span data-ttu-id="2a1b9-109">备注</span><span class="sxs-lookup"><span data-stu-id="2a1b9-109">Remarks</span></span>  
 <span data-ttu-id="2a1b9-110">`AddHandler`和`RemoveHandler`语句可用于启动和停止事件处理程序执行期间任何时候。</span><span class="sxs-lookup"><span data-stu-id="2a1b9-110">The `AddHandler` and `RemoveHandler` statements allow you to start and stop event handling at any time during program execution.</span></span>  
  
 <span data-ttu-id="2a1b9-111">签名`eventhandler`过程必须与该事件的签名匹配`event`。</span><span class="sxs-lookup"><span data-stu-id="2a1b9-111">The signature of the `eventhandler` procedure must match the signature of the event `event`.</span></span>  
  
 <span data-ttu-id="2a1b9-112">`Handles` 关键字和 `AddHandler` 语句都允许你指定特定过程处理特定事件，但存在差异。</span><span class="sxs-lookup"><span data-stu-id="2a1b9-112">The `Handles` keyword and the `AddHandler` statement both allow you to specify that particular procedures handle particular events, but there are differences.</span></span> <span data-ttu-id="2a1b9-113">`AddHandler` 语句在运行时将过程连接到事件。</span><span class="sxs-lookup"><span data-stu-id="2a1b9-113">The `AddHandler` statement connects procedures to events at run time.</span></span> <span data-ttu-id="2a1b9-114">定义过程时使用 `Handles` 关键字，以指定它处理特定事件。</span><span class="sxs-lookup"><span data-stu-id="2a1b9-114">Use the `Handles` keyword when defining a procedure to specify that it handles a particular event.</span></span> <span data-ttu-id="2a1b9-115">有关详细信息，请参阅[处理](../../../visual-basic/language-reference/statements/handles-clause.md)。</span><span class="sxs-lookup"><span data-stu-id="2a1b9-115">For more information, see [Handles](../../../visual-basic/language-reference/statements/handles-clause.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="2a1b9-116">用于自定义事件`AddHandler`语句调用事件的`AddHandler`访问器。</span><span class="sxs-lookup"><span data-stu-id="2a1b9-116">For custom events, the `AddHandler` statement invokes the event's `AddHandler` accessor.</span></span> <span data-ttu-id="2a1b9-117">自定义事件的详细信息，请参阅[Event 语句](../../../visual-basic/language-reference/statements/event-statement.md)。</span><span class="sxs-lookup"><span data-stu-id="2a1b9-117">For more information on custom events, see [Event Statement](../../../visual-basic/language-reference/statements/event-statement.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="2a1b9-118">示例</span><span class="sxs-lookup"><span data-stu-id="2a1b9-118">Example</span></span>  
 [!code-vb[VbVbalrEvents#17](../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/addhandler-statement_1.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="2a1b9-119">请参阅</span><span class="sxs-lookup"><span data-stu-id="2a1b9-119">See also</span></span>
- [<span data-ttu-id="2a1b9-120">RemoveHandler 语句</span><span class="sxs-lookup"><span data-stu-id="2a1b9-120">RemoveHandler Statement</span></span>](../../../visual-basic/language-reference/statements/removehandler-statement.md)
- [<span data-ttu-id="2a1b9-121">Handles</span><span class="sxs-lookup"><span data-stu-id="2a1b9-121">Handles</span></span>](../../../visual-basic/language-reference/statements/handles-clause.md)
- [<span data-ttu-id="2a1b9-122">Event 语句</span><span class="sxs-lookup"><span data-stu-id="2a1b9-122">Event Statement</span></span>](../../../visual-basic/language-reference/statements/event-statement.md)
- [<span data-ttu-id="2a1b9-123">事件</span><span class="sxs-lookup"><span data-stu-id="2a1b9-123">Events</span></span>](../../../visual-basic/programming-guide/language-features/events/index.md)
