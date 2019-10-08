---
title: AddHandler 语句（Visual Basic）
ms.date: 07/20/2015
f1_keywords:
- vb.AddHandlerMethod
- addhandler
- vb.addhandler
helpviewer_keywords:
- AddHandler statement [Visual Basic]
ms.assetid: cfe69799-2a0f-42c0-a99e-09fed954da01
ms.openlocfilehash: 95277f532488b0cf56114e5ee94dc3528e3a2e02
ms.sourcegitcommit: eff6adb61852369ab690f3f047818c90580e7eb1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/07/2019
ms.locfileid: "72004539"
---
# <a name="addhandler-statement"></a><span data-ttu-id="f8ed0-102">AddHandler 语句</span><span class="sxs-lookup"><span data-stu-id="f8ed0-102">AddHandler Statement</span></span>
<span data-ttu-id="f8ed0-103">在运行时将事件与事件处理程序相关联。</span><span class="sxs-lookup"><span data-stu-id="f8ed0-103">Associates an event with an event handler at run time.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f8ed0-104">语法</span><span class="sxs-lookup"><span data-stu-id="f8ed0-104">Syntax</span></span>  
  
```vb  
AddHandler event, AddressOf eventhandler  
```  
  
## <a name="parts"></a><span data-ttu-id="f8ed0-105">部件</span><span class="sxs-lookup"><span data-stu-id="f8ed0-105">Parts</span></span>  
|||
|---|---|
|<span data-ttu-id="f8ed0-106">事件</span><span class="sxs-lookup"><span data-stu-id="f8ed0-106">event</span></span>|<span data-ttu-id="f8ed0-107">要处理的事件的名称。</span><span class="sxs-lookup"><span data-stu-id="f8ed0-107">The name of the event to handle.</span></span>|  
|`eventhandler`|<span data-ttu-id="f8ed0-108">处理事件的过程的名称。</span><span class="sxs-lookup"><span data-stu-id="f8ed0-108">The name of a procedure that handles the event.</span></span>|
|||
  
## <a name="remarks"></a><span data-ttu-id="f8ed0-109">备注</span><span class="sxs-lookup"><span data-stu-id="f8ed0-109">Remarks</span></span>  
 <span data-ttu-id="f8ed0-110">@No__t-0 和 @no__t 1 语句允许您在程序执行过程中随时启动和停止事件处理。</span><span class="sxs-lookup"><span data-stu-id="f8ed0-110">The `AddHandler` and `RemoveHandler` statements allow you to start and stop event handling at any time during program execution.</span></span>  
  
 <span data-ttu-id="f8ed0-111">@No__t-0 过程的签名必须与事件 @no__t 的签名相匹配。</span><span class="sxs-lookup"><span data-stu-id="f8ed0-111">The signature of the `eventhandler` procedure must match the signature of the event `event`.</span></span>  
  
 <span data-ttu-id="f8ed0-112">`Handles` 关键字和 `AddHandler` 语句都允许你指定特定过程处理特定事件，但存在差异。</span><span class="sxs-lookup"><span data-stu-id="f8ed0-112">The `Handles` keyword and the `AddHandler` statement both allow you to specify that particular procedures handle particular events, but there are differences.</span></span> <span data-ttu-id="f8ed0-113">`AddHandler` 语句在运行时将过程连接到事件。</span><span class="sxs-lookup"><span data-stu-id="f8ed0-113">The `AddHandler` statement connects procedures to events at run time.</span></span> <span data-ttu-id="f8ed0-114">定义过程时使用 `Handles` 关键字，以指定它处理特定事件。</span><span class="sxs-lookup"><span data-stu-id="f8ed0-114">Use the `Handles` keyword when defining a procedure to specify that it handles a particular event.</span></span> <span data-ttu-id="f8ed0-115">有关详细信息，请参阅[句柄](../../../visual-basic/language-reference/statements/handles-clause.md)。</span><span class="sxs-lookup"><span data-stu-id="f8ed0-115">For more information, see [Handles](../../../visual-basic/language-reference/statements/handles-clause.md).</span></span>  
  
> [!NOTE]
> <span data-ttu-id="f8ed0-116">对于自定义事件，@no__t 的 @no__t 语句调用事件的访问器。</span><span class="sxs-lookup"><span data-stu-id="f8ed0-116">For custom events, the `AddHandler` statement invokes the event's `AddHandler` accessor.</span></span> <span data-ttu-id="f8ed0-117">有关自定义事件的详细信息，请参阅[Event 语句](../../../visual-basic/language-reference/statements/event-statement.md)。</span><span class="sxs-lookup"><span data-stu-id="f8ed0-117">For more information on custom events, see [Event Statement](../../../visual-basic/language-reference/statements/event-statement.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="f8ed0-118">示例</span><span class="sxs-lookup"><span data-stu-id="f8ed0-118">Example</span></span>  
 [!code-vb[VbVbalrEvents#17](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrEvents/VB/Class1.vb#17)]  
  
## <a name="see-also"></a><span data-ttu-id="f8ed0-119">请参阅</span><span class="sxs-lookup"><span data-stu-id="f8ed0-119">See also</span></span>

- [<span data-ttu-id="f8ed0-120">RemoveHandler 语句</span><span class="sxs-lookup"><span data-stu-id="f8ed0-120">RemoveHandler Statement</span></span>](../../../visual-basic/language-reference/statements/removehandler-statement.md)
- [<span data-ttu-id="f8ed0-121">Handles</span><span class="sxs-lookup"><span data-stu-id="f8ed0-121">Handles</span></span>](../../../visual-basic/language-reference/statements/handles-clause.md)
- [<span data-ttu-id="f8ed0-122">Event 语句</span><span class="sxs-lookup"><span data-stu-id="f8ed0-122">Event Statement</span></span>](../../../visual-basic/language-reference/statements/event-statement.md)
- [<span data-ttu-id="f8ed0-123">事件</span><span class="sxs-lookup"><span data-stu-id="f8ed0-123">Events</span></span>](../../../visual-basic/programming-guide/language-features/events/index.md)
