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
ms.openlocfilehash: 4e53398f97cbd320c0c98250ac5abbc2e4e98027
ms.sourcegitcommit: 40364ded04fa6cdcb2b6beca7f68412e2e12f633
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/28/2019
ms.locfileid: "56981031"
---
# <a name="removehandler-statement"></a><span data-ttu-id="a5ff3-102">RemoveHandler 语句</span><span class="sxs-lookup"><span data-stu-id="a5ff3-102">RemoveHandler Statement</span></span>
<span data-ttu-id="a5ff3-103">删除的事件和事件处理程序之间的关联。</span><span class="sxs-lookup"><span data-stu-id="a5ff3-103">Removes the association between an event and an event handler.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a5ff3-104">语法</span><span class="sxs-lookup"><span data-stu-id="a5ff3-104">Syntax</span></span>  
  
```  
RemoveHandler event, AddressOf eventhandler  
```  
  
## <a name="parts"></a><span data-ttu-id="a5ff3-105">部件</span><span class="sxs-lookup"><span data-stu-id="a5ff3-105">Parts</span></span>  
  
|<span data-ttu-id="a5ff3-106">术语</span><span class="sxs-lookup"><span data-stu-id="a5ff3-106">Term</span></span>|<span data-ttu-id="a5ff3-107">定义</span><span class="sxs-lookup"><span data-stu-id="a5ff3-107">Definition</span></span>|  
|---|---|  
|`event`|<span data-ttu-id="a5ff3-108">要处理的事件的名称。</span><span class="sxs-lookup"><span data-stu-id="a5ff3-108">The name of the event being handled.</span></span>|  
|`eventhandler`|<span data-ttu-id="a5ff3-109">当前正在处理该事件的过程的名称。</span><span class="sxs-lookup"><span data-stu-id="a5ff3-109">The name of the procedure currently handling the event.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="a5ff3-110">备注</span><span class="sxs-lookup"><span data-stu-id="a5ff3-110">Remarks</span></span>  
 <span data-ttu-id="a5ff3-111">`AddHandler`和`RemoveHandler`语句可用于启动和停止程序执行期间任何时候特定事件的事件处理。</span><span class="sxs-lookup"><span data-stu-id="a5ff3-111">The `AddHandler` and `RemoveHandler` statements allow you to start and stop event handling for a specific event at any time during program execution.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="a5ff3-112">用于自定义事件`RemoveHandler`语句调用事件的`RemoveHandler`访问器。</span><span class="sxs-lookup"><span data-stu-id="a5ff3-112">For custom events, the `RemoveHandler` statement invokes the event's `RemoveHandler` accessor.</span></span> <span data-ttu-id="a5ff3-113">自定义事件的详细信息，请参阅[Event 语句](../../../visual-basic/language-reference/statements/event-statement.md)。</span><span class="sxs-lookup"><span data-stu-id="a5ff3-113">For more information on custom events, see [Event Statement](../../../visual-basic/language-reference/statements/event-statement.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="a5ff3-114">示例</span><span class="sxs-lookup"><span data-stu-id="a5ff3-114">Example</span></span>  
 [!code-vb[VbVbalrEvents#17](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrEvents/VB/Class1.vb#17)]  
  
## <a name="see-also"></a><span data-ttu-id="a5ff3-115">请参阅</span><span class="sxs-lookup"><span data-stu-id="a5ff3-115">See also</span></span>
- [<span data-ttu-id="a5ff3-116">AddHandler 语句</span><span class="sxs-lookup"><span data-stu-id="a5ff3-116">AddHandler Statement</span></span>](../../../visual-basic/language-reference/statements/addhandler-statement.md)
- [<span data-ttu-id="a5ff3-117">Handles</span><span class="sxs-lookup"><span data-stu-id="a5ff3-117">Handles</span></span>](../../../visual-basic/language-reference/statements/handles-clause.md)
- [<span data-ttu-id="a5ff3-118">Event 语句</span><span class="sxs-lookup"><span data-stu-id="a5ff3-118">Event Statement</span></span>](../../../visual-basic/language-reference/statements/event-statement.md)
- [<span data-ttu-id="a5ff3-119">事件</span><span class="sxs-lookup"><span data-stu-id="a5ff3-119">Events</span></span>](../../../visual-basic/programming-guide/language-features/events/index.md)
