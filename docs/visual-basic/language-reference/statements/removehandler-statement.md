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
ms.openlocfilehash: 8a9dc5874629c1687318496bd7c4016eb318c25a
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/02/2019
ms.locfileid: "58831678"
---
# <a name="removehandler-statement"></a><span data-ttu-id="cb89d-102">RemoveHandler 语句</span><span class="sxs-lookup"><span data-stu-id="cb89d-102">RemoveHandler Statement</span></span>
<span data-ttu-id="cb89d-103">删除的事件和事件处理程序之间的关联。</span><span class="sxs-lookup"><span data-stu-id="cb89d-103">Removes the association between an event and an event handler.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cb89d-104">语法</span><span class="sxs-lookup"><span data-stu-id="cb89d-104">Syntax</span></span>  
  
```  
RemoveHandler event, AddressOf eventhandler  
```  
  
## <a name="parts"></a><span data-ttu-id="cb89d-105">部件</span><span class="sxs-lookup"><span data-stu-id="cb89d-105">Parts</span></span>  
  
|<span data-ttu-id="cb89d-106">术语</span><span class="sxs-lookup"><span data-stu-id="cb89d-106">Term</span></span>|<span data-ttu-id="cb89d-107">定义</span><span class="sxs-lookup"><span data-stu-id="cb89d-107">Definition</span></span>|  
|---|---|  
|`event`|<span data-ttu-id="cb89d-108">要处理的事件的名称。</span><span class="sxs-lookup"><span data-stu-id="cb89d-108">The name of the event being handled.</span></span>|  
|`eventhandler`|<span data-ttu-id="cb89d-109">当前正在处理该事件的过程的名称。</span><span class="sxs-lookup"><span data-stu-id="cb89d-109">The name of the procedure currently handling the event.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="cb89d-110">备注</span><span class="sxs-lookup"><span data-stu-id="cb89d-110">Remarks</span></span>  
 <span data-ttu-id="cb89d-111">`AddHandler`和`RemoveHandler`语句可用于启动和停止程序执行期间任何时候特定事件的事件处理。</span><span class="sxs-lookup"><span data-stu-id="cb89d-111">The `AddHandler` and `RemoveHandler` statements allow you to start and stop event handling for a specific event at any time during program execution.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="cb89d-112">用于自定义事件`RemoveHandler`语句调用事件的`RemoveHandler`访问器。</span><span class="sxs-lookup"><span data-stu-id="cb89d-112">For custom events, the `RemoveHandler` statement invokes the event's `RemoveHandler` accessor.</span></span> <span data-ttu-id="cb89d-113">自定义事件的详细信息，请参阅[Event 语句](../../../visual-basic/language-reference/statements/event-statement.md)。</span><span class="sxs-lookup"><span data-stu-id="cb89d-113">For more information on custom events, see [Event Statement](../../../visual-basic/language-reference/statements/event-statement.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="cb89d-114">示例</span><span class="sxs-lookup"><span data-stu-id="cb89d-114">Example</span></span>  
 [!code-vb[VbVbalrEvents#17](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrEvents/VB/Class1.vb#17)]  
  
## <a name="see-also"></a><span data-ttu-id="cb89d-115">请参阅</span><span class="sxs-lookup"><span data-stu-id="cb89d-115">See also</span></span>

- [<span data-ttu-id="cb89d-116">AddHandler 语句</span><span class="sxs-lookup"><span data-stu-id="cb89d-116">AddHandler Statement</span></span>](../../../visual-basic/language-reference/statements/addhandler-statement.md)
- [<span data-ttu-id="cb89d-117">Handles</span><span class="sxs-lookup"><span data-stu-id="cb89d-117">Handles</span></span>](../../../visual-basic/language-reference/statements/handles-clause.md)
- [<span data-ttu-id="cb89d-118">Event 语句</span><span class="sxs-lookup"><span data-stu-id="cb89d-118">Event Statement</span></span>](../../../visual-basic/language-reference/statements/event-statement.md)
- [<span data-ttu-id="cb89d-119">事件</span><span class="sxs-lookup"><span data-stu-id="cb89d-119">Events</span></span>](../../../visual-basic/programming-guide/language-features/events/index.md)
