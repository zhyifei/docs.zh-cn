---
title: "RemoveHandler 语句 |Microsoft 文档"
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vb.RemoveHandlerMethod
- vb.RemoveHandler
- RemoveHandler
dev_langs:
- VB
helpviewer_keywords:
- RemoveHandler keyword
- RemoveHandler statement
ms.assetid: 647cd825-e877-4910-b4f1-8d168beebe6a
caps.latest.revision: 14
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: 6e614a1dce4894dcd18509854f3cae149665cbf0
ms.contentlocale: zh-cn
ms.lasthandoff: 04/12/2017

---
# <a name="removehandler-statement"></a><span data-ttu-id="2ad39-102">RemoveHandler 语句</span><span class="sxs-lookup"><span data-stu-id="2ad39-102">RemoveHandler Statement</span></span>
<span data-ttu-id="2ad39-103">删除的事件和事件处理程序之间的关联。</span><span class="sxs-lookup"><span data-stu-id="2ad39-103">Removes the association between an event and an event handler.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2ad39-104">语法</span><span class="sxs-lookup"><span data-stu-id="2ad39-104">Syntax</span></span>  
  
```  
RemoveHandler event, AddressOf eventhandler  
```  
  
## <a name="parts"></a><span data-ttu-id="2ad39-105">部件</span><span class="sxs-lookup"><span data-stu-id="2ad39-105">Parts</span></span>  
  
|<span data-ttu-id="2ad39-106">术语</span><span class="sxs-lookup"><span data-stu-id="2ad39-106">Term</span></span>|<span data-ttu-id="2ad39-107">定义</span><span class="sxs-lookup"><span data-stu-id="2ad39-107">Definition</span></span>|  
|---|---|  
|`event`|<span data-ttu-id="2ad39-108">正在处理的事件的名称。</span><span class="sxs-lookup"><span data-stu-id="2ad39-108">The name of the event being handled.</span></span>|  
|`eventhandler`|<span data-ttu-id="2ad39-109">当前正在处理该事件的过程的名称。</span><span class="sxs-lookup"><span data-stu-id="2ad39-109">The name of the procedure currently handling the event.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="2ad39-110">备注</span><span class="sxs-lookup"><span data-stu-id="2ad39-110">Remarks</span></span>  
 <span data-ttu-id="2ad39-111">`AddHandler`和`RemoveHandler`语句可用于启动和停止程序执行期间随时特定事件的事件处理。</span><span class="sxs-lookup"><span data-stu-id="2ad39-111">The `AddHandler` and `RemoveHandler` statements allow you to start and stop event handling for a specific event at any time during program execution.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="2ad39-112">对于自定义事件`RemoveHandler`语句调用的事件`RemoveHandler`取值函数。</span><span class="sxs-lookup"><span data-stu-id="2ad39-112">For custom events, the `RemoveHandler` statement invokes the event's `RemoveHandler` accessor.</span></span> <span data-ttu-id="2ad39-113">自定义事件的详细信息，请参阅[Event 语句](../../../visual-basic/language-reference/statements/event-statement.md)。</span><span class="sxs-lookup"><span data-stu-id="2ad39-113">For more information on custom events, see [Event Statement](../../../visual-basic/language-reference/statements/event-statement.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="2ad39-114">示例</span><span class="sxs-lookup"><span data-stu-id="2ad39-114">Example</span></span>  
 <span data-ttu-id="2ad39-115">[!code-vb[VbVbalrEvents #&17;](../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/removehandler-statement_1.vb)]</span><span class="sxs-lookup"><span data-stu-id="2ad39-115">[!code-vb[VbVbalrEvents#17](../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/removehandler-statement_1.vb)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2ad39-116">另请参阅</span><span class="sxs-lookup"><span data-stu-id="2ad39-116">See Also</span></span>  
 <span data-ttu-id="2ad39-117">[AddHandler 语句](../../../visual-basic/language-reference/statements/addhandler-statement.md) </span><span class="sxs-lookup"><span data-stu-id="2ad39-117">[AddHandler Statement](../../../visual-basic/language-reference/statements/addhandler-statement.md) </span></span>  
<span data-ttu-id="2ad39-118"> [句柄](../../../visual-basic/language-reference/statements/handles-clause.md) </span><span class="sxs-lookup"><span data-stu-id="2ad39-118"> [Handles](../../../visual-basic/language-reference/statements/handles-clause.md) </span></span>  
<span data-ttu-id="2ad39-119"> [Event 语句](../../../visual-basic/language-reference/statements/event-statement.md) </span><span class="sxs-lookup"><span data-stu-id="2ad39-119"> [Event Statement](../../../visual-basic/language-reference/statements/event-statement.md) </span></span>  
<span data-ttu-id="2ad39-120"> [事件](../../../visual-basic/programming-guide/language-features/events/index.md)</span><span class="sxs-lookup"><span data-stu-id="2ad39-120"> [Events](../../../visual-basic/programming-guide/language-features/events/index.md)</span></span>
