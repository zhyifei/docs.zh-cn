---
title: RemoveHandler 语句 (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.RemoveHandlerMethod
- vb.RemoveHandler
- RemoveHandler
helpviewer_keywords:
- RemoveHandler keyword [Visual Basic]
- RemoveHandler statement [Visual Basic]
ms.assetid: 647cd825-e877-4910-b4f1-8d168beebe6a
ms.openlocfilehash: c1e6ffec64bc01936955a2e94aa9c110b317109f
ms.sourcegitcommit: 412bbc2e43c3b6ca25b358cdf394be97336f0c24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/25/2018
ms.locfileid: "42925161"
---
# <a name="removehandler-statement"></a><span data-ttu-id="6c8ce-102">RemoveHandler 语句</span><span class="sxs-lookup"><span data-stu-id="6c8ce-102">RemoveHandler Statement</span></span>
<span data-ttu-id="6c8ce-103">删除的事件和事件处理程序之间的关联。</span><span class="sxs-lookup"><span data-stu-id="6c8ce-103">Removes the association between an event and an event handler.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6c8ce-104">语法</span><span class="sxs-lookup"><span data-stu-id="6c8ce-104">Syntax</span></span>  
  
```  
RemoveHandler event, AddressOf eventhandler  
```  
  
## <a name="parts"></a><span data-ttu-id="6c8ce-105">部件</span><span class="sxs-lookup"><span data-stu-id="6c8ce-105">Parts</span></span>  
  
|<span data-ttu-id="6c8ce-106">术语</span><span class="sxs-lookup"><span data-stu-id="6c8ce-106">Term</span></span>|<span data-ttu-id="6c8ce-107">定义</span><span class="sxs-lookup"><span data-stu-id="6c8ce-107">Definition</span></span>|  
|---|---|  
|`event`|<span data-ttu-id="6c8ce-108">要处理的事件的名称。</span><span class="sxs-lookup"><span data-stu-id="6c8ce-108">The name of the event being handled.</span></span>|  
|`eventhandler`|<span data-ttu-id="6c8ce-109">当前正在处理该事件的过程的名称。</span><span class="sxs-lookup"><span data-stu-id="6c8ce-109">The name of the procedure currently handling the event.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="6c8ce-110">备注</span><span class="sxs-lookup"><span data-stu-id="6c8ce-110">Remarks</span></span>  
 <span data-ttu-id="6c8ce-111">`AddHandler`和`RemoveHandler`语句可用于启动和停止程序执行期间任何时候特定事件的事件处理。</span><span class="sxs-lookup"><span data-stu-id="6c8ce-111">The `AddHandler` and `RemoveHandler` statements allow you to start and stop event handling for a specific event at any time during program execution.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="6c8ce-112">用于自定义事件`RemoveHandler`语句调用事件的`RemoveHandler`访问器。</span><span class="sxs-lookup"><span data-stu-id="6c8ce-112">For custom events, the `RemoveHandler` statement invokes the event's `RemoveHandler` accessor.</span></span> <span data-ttu-id="6c8ce-113">自定义事件的详细信息，请参阅[Event 语句](../../../visual-basic/language-reference/statements/event-statement.md)。</span><span class="sxs-lookup"><span data-stu-id="6c8ce-113">For more information on custom events, see [Event Statement](../../../visual-basic/language-reference/statements/event-statement.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="6c8ce-114">示例</span><span class="sxs-lookup"><span data-stu-id="6c8ce-114">Example</span></span>  
 [!code-vb[VbVbalrEvents#17](../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/removehandler-statement_1.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="6c8ce-115">请参阅</span><span class="sxs-lookup"><span data-stu-id="6c8ce-115">See Also</span></span>  
 [<span data-ttu-id="6c8ce-116">AddHandler 语句</span><span class="sxs-lookup"><span data-stu-id="6c8ce-116">AddHandler Statement</span></span>](../../../visual-basic/language-reference/statements/addhandler-statement.md)  
 [<span data-ttu-id="6c8ce-117">Handles</span><span class="sxs-lookup"><span data-stu-id="6c8ce-117">Handles</span></span>](../../../visual-basic/language-reference/statements/handles-clause.md)  
 [<span data-ttu-id="6c8ce-118">Event 语句</span><span class="sxs-lookup"><span data-stu-id="6c8ce-118">Event Statement</span></span>](../../../visual-basic/language-reference/statements/event-statement.md)  
 [<span data-ttu-id="6c8ce-119">事件</span><span class="sxs-lookup"><span data-stu-id="6c8ce-119">Events</span></span>](../../../visual-basic/programming-guide/language-features/events/index.md)
