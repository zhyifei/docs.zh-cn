---
title: RemoveHandler 语句（Visual Basic）
ms.date: 07/20/2015
f1_keywords:
- vb.RemoveHandlerMethod
- vb.RemoveHandler
- RemoveHandler
helpviewer_keywords:
- RemoveHandler keyword [Visual Basic]
- RemoveHandler statement [Visual Basic]
ms.assetid: 647cd825-e877-4910-b4f1-8d168beebe6a
ms.openlocfilehash: 47f35bd76d7734878e7b5b206b4aecd856276593
ms.sourcegitcommit: 1f12db2d852d05bed8c53845f0b5a57a762979c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2019
ms.locfileid: "72582023"
---
# <a name="removehandler-statement"></a><span data-ttu-id="01b81-102">RemoveHandler 语句</span><span class="sxs-lookup"><span data-stu-id="01b81-102">RemoveHandler Statement</span></span>
<span data-ttu-id="01b81-103">删除事件和事件处理程序之间的关联。</span><span class="sxs-lookup"><span data-stu-id="01b81-103">Removes the association between an event and an event handler.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="01b81-104">语法</span><span class="sxs-lookup"><span data-stu-id="01b81-104">Syntax</span></span>  
  
```vb  
RemoveHandler event, AddressOf eventhandler  
```  
  
## <a name="parts"></a><span data-ttu-id="01b81-105">部件</span><span class="sxs-lookup"><span data-stu-id="01b81-105">Parts</span></span>  
  
|<span data-ttu-id="01b81-106">术语</span><span class="sxs-lookup"><span data-stu-id="01b81-106">Term</span></span>|<span data-ttu-id="01b81-107">定义</span><span class="sxs-lookup"><span data-stu-id="01b81-107">Definition</span></span>|  
|---|---|  
|`event`|<span data-ttu-id="01b81-108">正在处理的事件的名称。</span><span class="sxs-lookup"><span data-stu-id="01b81-108">The name of the event being handled.</span></span>|  
|`eventhandler`|<span data-ttu-id="01b81-109">当前处理事件的过程的名称。</span><span class="sxs-lookup"><span data-stu-id="01b81-109">The name of the procedure currently handling the event.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="01b81-110">备注</span><span class="sxs-lookup"><span data-stu-id="01b81-110">Remarks</span></span>  
 <span data-ttu-id="01b81-111">使用 `AddHandler` 和 `RemoveHandler` 语句，可以在程序执行过程中随时启动和停止特定事件的事件处理。</span><span class="sxs-lookup"><span data-stu-id="01b81-111">The `AddHandler` and `RemoveHandler` statements allow you to start and stop event handling for a specific event at any time during program execution.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="01b81-112">对于自定义事件，`RemoveHandler` 语句调用事件的 `RemoveHandler` 访问器。</span><span class="sxs-lookup"><span data-stu-id="01b81-112">For custom events, the `RemoveHandler` statement invokes the event's `RemoveHandler` accessor.</span></span> <span data-ttu-id="01b81-113">有关自定义事件的详细信息，请参阅[Event 语句](../../../visual-basic/language-reference/statements/event-statement.md)。</span><span class="sxs-lookup"><span data-stu-id="01b81-113">For more information on custom events, see [Event Statement](../../../visual-basic/language-reference/statements/event-statement.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="01b81-114">示例</span><span class="sxs-lookup"><span data-stu-id="01b81-114">Example</span></span>  
 [!code-vb[VbVbalrEvents#17](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrEvents/VB/Class1.vb#17)]  
  
## <a name="see-also"></a><span data-ttu-id="01b81-115">请参阅</span><span class="sxs-lookup"><span data-stu-id="01b81-115">See also</span></span>

- [<span data-ttu-id="01b81-116">AddHandler 语句</span><span class="sxs-lookup"><span data-stu-id="01b81-116">AddHandler Statement</span></span>](../../../visual-basic/language-reference/statements/addhandler-statement.md)
- [<span data-ttu-id="01b81-117">Handles</span><span class="sxs-lookup"><span data-stu-id="01b81-117">Handles</span></span>](../../../visual-basic/language-reference/statements/handles-clause.md)
- [<span data-ttu-id="01b81-118">Event 语句</span><span class="sxs-lookup"><span data-stu-id="01b81-118">Event Statement</span></span>](../../../visual-basic/language-reference/statements/event-statement.md)
- [<span data-ttu-id="01b81-119">事件</span><span class="sxs-lookup"><span data-stu-id="01b81-119">Events</span></span>](../../../visual-basic/programming-guide/language-features/events/index.md)
