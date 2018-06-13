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
ms.openlocfilehash: 0d982768707948bd6c616445509e16a462b86f2c
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33597983"
---
# <a name="removehandler-statement"></a><span data-ttu-id="ea32f-102">RemoveHandler 语句</span><span class="sxs-lookup"><span data-stu-id="ea32f-102">RemoveHandler Statement</span></span>
<span data-ttu-id="ea32f-103">删除的事件和事件处理程序之间的关联。</span><span class="sxs-lookup"><span data-stu-id="ea32f-103">Removes the association between an event and an event handler.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ea32f-104">语法</span><span class="sxs-lookup"><span data-stu-id="ea32f-104">Syntax</span></span>  
  
```  
RemoveHandler event, AddressOf eventhandler  
```  
  
## <a name="parts"></a><span data-ttu-id="ea32f-105">部件</span><span class="sxs-lookup"><span data-stu-id="ea32f-105">Parts</span></span>  
  
|<span data-ttu-id="ea32f-106">术语</span><span class="sxs-lookup"><span data-stu-id="ea32f-106">Term</span></span>|<span data-ttu-id="ea32f-107">定义</span><span class="sxs-lookup"><span data-stu-id="ea32f-107">Definition</span></span>|  
|---|---|  
|`event`|<span data-ttu-id="ea32f-108">正在处理的事件的名称。</span><span class="sxs-lookup"><span data-stu-id="ea32f-108">The name of the event being handled.</span></span>|  
|`eventhandler`|<span data-ttu-id="ea32f-109">当前正在处理该事件过程的名称。</span><span class="sxs-lookup"><span data-stu-id="ea32f-109">The name of the procedure currently handling the event.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="ea32f-110">备注</span><span class="sxs-lookup"><span data-stu-id="ea32f-110">Remarks</span></span>  
 <span data-ttu-id="ea32f-111">`AddHandler`和`RemoveHandler`语句使您可以启动和停止程序执行期间随时特定事件的事件处理。</span><span class="sxs-lookup"><span data-stu-id="ea32f-111">The `AddHandler` and `RemoveHandler` statements allow you to start and stop event handling for a specific event at any time during program execution.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="ea32f-112">对于自定义事件，`RemoveHandler`语句调用事件的`RemoveHandler`访问器。</span><span class="sxs-lookup"><span data-stu-id="ea32f-112">For custom events, the `RemoveHandler` statement invokes the event's `RemoveHandler` accessor.</span></span> <span data-ttu-id="ea32f-113">有关自定义事件的详细信息，请参阅[Event 语句](../../../visual-basic/language-reference/statements/event-statement.md)。</span><span class="sxs-lookup"><span data-stu-id="ea32f-113">For more information on custom events, see [Event Statement](../../../visual-basic/language-reference/statements/event-statement.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="ea32f-114">示例</span><span class="sxs-lookup"><span data-stu-id="ea32f-114">Example</span></span>  
 [!code-vb[VbVbalrEvents#17](../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/removehandler-statement_1.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="ea32f-115">请参阅</span><span class="sxs-lookup"><span data-stu-id="ea32f-115">See Also</span></span>  
 [<span data-ttu-id="ea32f-116">AddHandler 语句</span><span class="sxs-lookup"><span data-stu-id="ea32f-116">AddHandler Statement</span></span>](../../../visual-basic/language-reference/statements/addhandler-statement.md)  
 [<span data-ttu-id="ea32f-117">Handles</span><span class="sxs-lookup"><span data-stu-id="ea32f-117">Handles</span></span>](../../../visual-basic/language-reference/statements/handles-clause.md)  
 [<span data-ttu-id="ea32f-118">Event 语句</span><span class="sxs-lookup"><span data-stu-id="ea32f-118">Event Statement</span></span>](../../../visual-basic/language-reference/statements/event-statement.md)  
 [<span data-ttu-id="ea32f-119">事件</span><span class="sxs-lookup"><span data-stu-id="ea32f-119">Events</span></span>](../../../visual-basic/programming-guide/language-features/events/index.md)
