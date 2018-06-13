---
title: AddHandler 语句
ms.date: 07/20/2015
f1_keywords:
- vb.AddHandlerMethod
- addhandler
- vb.addhandler
helpviewer_keywords:
- AddHandler statement [Visual Basic]
ms.assetid: cfe69799-2a0f-42c0-a99e-09fed954da01
ms.openlocfilehash: db8131dc82aed40e725c9375efef274fb6917d41
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33603647"
---
# <a name="addhandler-statement"></a><span data-ttu-id="d6792-102">AddHandler 语句</span><span class="sxs-lookup"><span data-stu-id="d6792-102">AddHandler Statement</span></span>
<span data-ttu-id="d6792-103">将事件与事件处理程序关联在运行时。</span><span class="sxs-lookup"><span data-stu-id="d6792-103">Associates an event with an event handler at run time.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d6792-104">语法</span><span class="sxs-lookup"><span data-stu-id="d6792-104">Syntax</span></span>  
  
```  
AddHandler event, AddressOf eventhandler  
```  
  
## <a name="parts"></a><span data-ttu-id="d6792-105">部件</span><span class="sxs-lookup"><span data-stu-id="d6792-105">Parts</span></span>  
 `event`  
 <span data-ttu-id="d6792-106">要处理的事件名称。</span><span class="sxs-lookup"><span data-stu-id="d6792-106">The name of the event to handle.</span></span>  
  
 `eventhandler`  
 <span data-ttu-id="d6792-107">处理事件的过程的名称。</span><span class="sxs-lookup"><span data-stu-id="d6792-107">The name of a procedure that handles the event.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="d6792-108">备注</span><span class="sxs-lookup"><span data-stu-id="d6792-108">Remarks</span></span>  
 <span data-ttu-id="d6792-109">`AddHandler`和`RemoveHandler`语句使您可以启动和停止程序执行期间的任何时候的事件处理。</span><span class="sxs-lookup"><span data-stu-id="d6792-109">The `AddHandler` and `RemoveHandler` statements allow you to start and stop event handling at any time during program execution.</span></span>  
  
 <span data-ttu-id="d6792-110">签名`eventhandler`过程必须与匹配的事件的签名`event`。</span><span class="sxs-lookup"><span data-stu-id="d6792-110">The signature of the `eventhandler` procedure must match the signature of the event `event`.</span></span>  
  
 <span data-ttu-id="d6792-111">`Handles` 关键字和 `AddHandler` 语句都允许你指定特定过程处理特定事件，但存在差异。</span><span class="sxs-lookup"><span data-stu-id="d6792-111">The `Handles` keyword and the `AddHandler` statement both allow you to specify that particular procedures handle particular events, but there are differences.</span></span> <span data-ttu-id="d6792-112">`AddHandler` 语句在运行时将过程连接到事件。</span><span class="sxs-lookup"><span data-stu-id="d6792-112">The `AddHandler` statement connects procedures to events at run time.</span></span> <span data-ttu-id="d6792-113">定义过程时使用 `Handles` 关键字，以指定它处理特定事件。</span><span class="sxs-lookup"><span data-stu-id="d6792-113">Use the `Handles` keyword when defining a procedure to specify that it handles a particular event.</span></span> <span data-ttu-id="d6792-114">有关详细信息，请参阅[处理](../../../visual-basic/language-reference/statements/handles-clause.md)。</span><span class="sxs-lookup"><span data-stu-id="d6792-114">For more information, see [Handles](../../../visual-basic/language-reference/statements/handles-clause.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="d6792-115">对于自定义事件，`AddHandler`语句调用事件的`AddHandler`访问器。</span><span class="sxs-lookup"><span data-stu-id="d6792-115">For custom events, the `AddHandler` statement invokes the event's `AddHandler` accessor.</span></span> <span data-ttu-id="d6792-116">有关自定义事件的详细信息，请参阅[Event 语句](../../../visual-basic/language-reference/statements/event-statement.md)。</span><span class="sxs-lookup"><span data-stu-id="d6792-116">For more information on custom events, see [Event Statement](../../../visual-basic/language-reference/statements/event-statement.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="d6792-117">示例</span><span class="sxs-lookup"><span data-stu-id="d6792-117">Example</span></span>  
 [!code-vb[VbVbalrEvents#17](../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/addhandler-statement_1.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="d6792-118">请参阅</span><span class="sxs-lookup"><span data-stu-id="d6792-118">See Also</span></span>  
 [<span data-ttu-id="d6792-119">RemoveHandler 语句</span><span class="sxs-lookup"><span data-stu-id="d6792-119">RemoveHandler Statement</span></span>](../../../visual-basic/language-reference/statements/removehandler-statement.md)  
 [<span data-ttu-id="d6792-120">Handles</span><span class="sxs-lookup"><span data-stu-id="d6792-120">Handles</span></span>](../../../visual-basic/language-reference/statements/handles-clause.md)  
 [<span data-ttu-id="d6792-121">Event 语句</span><span class="sxs-lookup"><span data-stu-id="d6792-121">Event Statement</span></span>](../../../visual-basic/language-reference/statements/event-statement.md)  
 [<span data-ttu-id="d6792-122">事件</span><span class="sxs-lookup"><span data-stu-id="d6792-122">Events</span></span>](../../../visual-basic/programming-guide/language-features/events/index.md)
