---
title: RemoveHandler 语句
ms.date: 07/20/2015
f1_keywords:
- vb.RemoveHandlerMethod
- vb.RemoveHandler
- RemoveHandler
helpviewer_keywords:
- RemoveHandler keyword [Visual Basic]
- RemoveHandler statement [Visual Basic]
ms.assetid: 647cd825-e877-4910-b4f1-8d168beebe6a
ms.openlocfilehash: 177952acf362ccb36a36b5f09b11a1a93dbefa29
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/22/2019
ms.locfileid: "74333040"
---
# <a name="removehandler-statement"></a><span data-ttu-id="334e1-102">RemoveHandler 语句</span><span class="sxs-lookup"><span data-stu-id="334e1-102">RemoveHandler Statement</span></span>
<span data-ttu-id="334e1-103">删除事件和事件处理程序之间的关联。</span><span class="sxs-lookup"><span data-stu-id="334e1-103">Removes the association between an event and an event handler.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="334e1-104">语法</span><span class="sxs-lookup"><span data-stu-id="334e1-104">Syntax</span></span>  
  
```vb  
RemoveHandler event, AddressOf eventhandler  
```  
  
## <a name="parts"></a><span data-ttu-id="334e1-105">部件</span><span class="sxs-lookup"><span data-stu-id="334e1-105">Parts</span></span>  
  
|<span data-ttu-id="334e1-106">术语</span><span class="sxs-lookup"><span data-stu-id="334e1-106">Term</span></span>|<span data-ttu-id="334e1-107">Definition</span><span class="sxs-lookup"><span data-stu-id="334e1-107">Definition</span></span>|  
|---|---|  
|`event`|<span data-ttu-id="334e1-108">正在处理的事件的名称。</span><span class="sxs-lookup"><span data-stu-id="334e1-108">The name of the event being handled.</span></span>|  
|`eventhandler`|<span data-ttu-id="334e1-109">当前处理事件的过程的名称。</span><span class="sxs-lookup"><span data-stu-id="334e1-109">The name of the procedure currently handling the event.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="334e1-110">备注</span><span class="sxs-lookup"><span data-stu-id="334e1-110">Remarks</span></span>  
 <span data-ttu-id="334e1-111">使用 `AddHandler` 和 `RemoveHandler` 语句，可以在程序执行过程中随时启动和停止特定事件的事件处理。</span><span class="sxs-lookup"><span data-stu-id="334e1-111">The `AddHandler` and `RemoveHandler` statements allow you to start and stop event handling for a specific event at any time during program execution.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="334e1-112">对于自定义事件，`RemoveHandler` 语句调用事件的 `RemoveHandler` 访问器。</span><span class="sxs-lookup"><span data-stu-id="334e1-112">For custom events, the `RemoveHandler` statement invokes the event's `RemoveHandler` accessor.</span></span> <span data-ttu-id="334e1-113">有关自定义事件的详细信息，请参阅[Event 语句](../../../visual-basic/language-reference/statements/event-statement.md)。</span><span class="sxs-lookup"><span data-stu-id="334e1-113">For more information on custom events, see [Event Statement](../../../visual-basic/language-reference/statements/event-statement.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="334e1-114">示例</span><span class="sxs-lookup"><span data-stu-id="334e1-114">Example</span></span>  
 [!code-vb[VbVbalrEvents#17](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrEvents/VB/Class1.vb#17)]  
  
## <a name="see-also"></a><span data-ttu-id="334e1-115">另请参阅</span><span class="sxs-lookup"><span data-stu-id="334e1-115">See also</span></span>

- [<span data-ttu-id="334e1-116">AddHandler 语句</span><span class="sxs-lookup"><span data-stu-id="334e1-116">AddHandler Statement</span></span>](../../../visual-basic/language-reference/statements/addhandler-statement.md)
- <span data-ttu-id="334e1-117">[!](../../../visual-basic/language-reference/statements/handles-clause.md)</span><span class="sxs-lookup"><span data-stu-id="334e1-117">[Handles](../../../visual-basic/language-reference/statements/handles-clause.md)</span></span>
- [<span data-ttu-id="334e1-118">Event 语句</span><span class="sxs-lookup"><span data-stu-id="334e1-118">Event Statement</span></span>](../../../visual-basic/language-reference/statements/event-statement.md)
- [<span data-ttu-id="334e1-119">事件</span><span class="sxs-lookup"><span data-stu-id="334e1-119">Events</span></span>](../../../visual-basic/programming-guide/language-features/events/index.md)
