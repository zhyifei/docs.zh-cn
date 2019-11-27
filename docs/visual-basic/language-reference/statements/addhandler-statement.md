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
ms.openlocfilehash: c110116af75d4fb39c016b8d6afcdb707fa6599b
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/22/2019
ms.locfileid: "74350193"
---
# <a name="addhandler-statement"></a><span data-ttu-id="a4433-102">AddHandler 语句</span><span class="sxs-lookup"><span data-stu-id="a4433-102">AddHandler Statement</span></span>
<span data-ttu-id="a4433-103">在运行时将事件与事件处理程序相关联。</span><span class="sxs-lookup"><span data-stu-id="a4433-103">Associates an event with an event handler at run time.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a4433-104">语法</span><span class="sxs-lookup"><span data-stu-id="a4433-104">Syntax</span></span>  
  
```vb  
AddHandler event, AddressOf eventhandler  
```  
  
## <a name="parts"></a><span data-ttu-id="a4433-105">部件</span><span class="sxs-lookup"><span data-stu-id="a4433-105">Parts</span></span>  
|||
|---|---|
|<span data-ttu-id="a4433-106">事件</span><span class="sxs-lookup"><span data-stu-id="a4433-106">event</span></span>|<span data-ttu-id="a4433-107">要处理的事件的名称。</span><span class="sxs-lookup"><span data-stu-id="a4433-107">The name of the event to handle.</span></span>|  
|`eventhandler`|<span data-ttu-id="a4433-108">处理事件的过程的名称。</span><span class="sxs-lookup"><span data-stu-id="a4433-108">The name of a procedure that handles the event.</span></span>|
|||
  
## <a name="remarks"></a><span data-ttu-id="a4433-109">备注</span><span class="sxs-lookup"><span data-stu-id="a4433-109">Remarks</span></span>  
 <span data-ttu-id="a4433-110">`AddHandler` 和 `RemoveHandler` 语句允许您在程序执行过程中随时启动和停止事件处理。</span><span class="sxs-lookup"><span data-stu-id="a4433-110">The `AddHandler` and `RemoveHandler` statements allow you to start and stop event handling at any time during program execution.</span></span>  
  
 <span data-ttu-id="a4433-111">`eventhandler` 过程的签名必须与事件 `event`的签名相匹配。</span><span class="sxs-lookup"><span data-stu-id="a4433-111">The signature of the `eventhandler` procedure must match the signature of the event `event`.</span></span>  
  
 <span data-ttu-id="a4433-112">`Handles` 关键字和 `AddHandler` 语句都允许你指定特定过程处理特定事件，但存在差异。</span><span class="sxs-lookup"><span data-stu-id="a4433-112">The `Handles` keyword and the `AddHandler` statement both allow you to specify that particular procedures handle particular events, but there are differences.</span></span> <span data-ttu-id="a4433-113">`AddHandler` 语句在运行时将过程连接到事件。</span><span class="sxs-lookup"><span data-stu-id="a4433-113">The `AddHandler` statement connects procedures to events at run time.</span></span> <span data-ttu-id="a4433-114">定义过程时使用 `Handles` 关键字，以指定它处理特定事件。</span><span class="sxs-lookup"><span data-stu-id="a4433-114">Use the `Handles` keyword when defining a procedure to specify that it handles a particular event.</span></span> <span data-ttu-id="a4433-115">有关详细信息，请参阅[句柄](../../../visual-basic/language-reference/statements/handles-clause.md)。</span><span class="sxs-lookup"><span data-stu-id="a4433-115">For more information, see [Handles](../../../visual-basic/language-reference/statements/handles-clause.md).</span></span>  
  
> [!NOTE]
> <span data-ttu-id="a4433-116">对于自定义事件，`AddHandler` 语句调用事件的 `AddHandler` 访问器。</span><span class="sxs-lookup"><span data-stu-id="a4433-116">For custom events, the `AddHandler` statement invokes the event's `AddHandler` accessor.</span></span> <span data-ttu-id="a4433-117">有关自定义事件的详细信息，请参阅[Event 语句](../../../visual-basic/language-reference/statements/event-statement.md)。</span><span class="sxs-lookup"><span data-stu-id="a4433-117">For more information on custom events, see [Event Statement](../../../visual-basic/language-reference/statements/event-statement.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="a4433-118">示例</span><span class="sxs-lookup"><span data-stu-id="a4433-118">Example</span></span>  
 [!code-vb[VbVbalrEvents#17](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrEvents/VB/Class1.vb#17)]  
  
## <a name="see-also"></a><span data-ttu-id="a4433-119">另请参阅</span><span class="sxs-lookup"><span data-stu-id="a4433-119">See also</span></span>

- [<span data-ttu-id="a4433-120">RemoveHandler 语句</span><span class="sxs-lookup"><span data-stu-id="a4433-120">RemoveHandler Statement</span></span>](../../../visual-basic/language-reference/statements/removehandler-statement.md)
- <span data-ttu-id="a4433-121">[!](../../../visual-basic/language-reference/statements/handles-clause.md)</span><span class="sxs-lookup"><span data-stu-id="a4433-121">[Handles](../../../visual-basic/language-reference/statements/handles-clause.md)</span></span>
- [<span data-ttu-id="a4433-122">Event 语句</span><span class="sxs-lookup"><span data-stu-id="a4433-122">Event Statement</span></span>](../../../visual-basic/language-reference/statements/event-statement.md)
- [<span data-ttu-id="a4433-123">事件</span><span class="sxs-lookup"><span data-stu-id="a4433-123">Events</span></span>](../../../visual-basic/programming-guide/language-features/events/index.md)
