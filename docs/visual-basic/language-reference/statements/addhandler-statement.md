---
title: "AddHandler 语句 |Microsoft 文档"
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vb.AddHandlerMethod
- addhandler
- vb.addhandler
dev_langs:
- VB
helpviewer_keywords:
- AddHandler statement
ms.assetid: cfe69799-2a0f-42c0-a99e-09fed954da01
caps.latest.revision: 15
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
ms.openlocfilehash: cd821a568a35f33c722c1631eb7fbaf8f877cf4f
ms.contentlocale: zh-cn
ms.lasthandoff: 04/12/2017

---
# <a name="addhandler-statement"></a><span data-ttu-id="61222-102">AddHandler 语句</span><span class="sxs-lookup"><span data-stu-id="61222-102">AddHandler Statement</span></span>
<span data-ttu-id="61222-103">在运行时将事件与事件处理程序。</span><span class="sxs-lookup"><span data-stu-id="61222-103">Associates an event with an event handler at run time.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="61222-104">语法</span><span class="sxs-lookup"><span data-stu-id="61222-104">Syntax</span></span>  
  
```  
AddHandler event, AddressOf eventhandler  
```  
  
## <a name="parts"></a><span data-ttu-id="61222-105">部件</span><span class="sxs-lookup"><span data-stu-id="61222-105">Parts</span></span>  
 `event`  
 <span data-ttu-id="61222-106">要处理的事件的名称。</span><span class="sxs-lookup"><span data-stu-id="61222-106">The name of the event to handle.</span></span>  
  
 `eventhandler`  
 <span data-ttu-id="61222-107">处理事件的过程的名称。</span><span class="sxs-lookup"><span data-stu-id="61222-107">The name of a procedure that handles the event.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="61222-108">备注</span><span class="sxs-lookup"><span data-stu-id="61222-108">Remarks</span></span>  
 <span data-ttu-id="61222-109">`AddHandler`和`RemoveHandler`语句可用于启动和停止事件处理程序执行期间随时。</span><span class="sxs-lookup"><span data-stu-id="61222-109">The `AddHandler` and `RemoveHandler` statements allow you to start and stop event handling at any time during program execution.</span></span>  
  
 <span data-ttu-id="61222-110">签名`eventhandler`过程必须与该事件的签名匹配`event`。</span><span class="sxs-lookup"><span data-stu-id="61222-110">The signature of the `eventhandler` procedure must match the signature of the event `event`.</span></span>  
  
 <span data-ttu-id="61222-111">`Handles` 关键字和 `AddHandler` 语句都允许你指定特定过程处理特定事件，但存在差异。</span><span class="sxs-lookup"><span data-stu-id="61222-111">The `Handles` keyword and the `AddHandler` statement both allow you to specify that particular procedures handle particular events, but there are differences.</span></span> <span data-ttu-id="61222-112">`AddHandler` 语句在运行时将过程连接到事件。</span><span class="sxs-lookup"><span data-stu-id="61222-112">The `AddHandler` statement connects procedures to events at run time.</span></span> <span data-ttu-id="61222-113">定义过程时使用 `Handles` 关键字，以指定它处理特定事件。</span><span class="sxs-lookup"><span data-stu-id="61222-113">Use the `Handles` keyword when defining a procedure to specify that it handles a particular event.</span></span> <span data-ttu-id="61222-114">有关详细信息，请参阅[处理](../../../visual-basic/language-reference/statements/handles-clause.md)。</span><span class="sxs-lookup"><span data-stu-id="61222-114">For more information, see [Handles](../../../visual-basic/language-reference/statements/handles-clause.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="61222-115">对于自定义事件`AddHandler`语句调用的事件`AddHandler`取值函数。</span><span class="sxs-lookup"><span data-stu-id="61222-115">For custom events, the `AddHandler` statement invokes the event's `AddHandler` accessor.</span></span> <span data-ttu-id="61222-116">自定义事件的详细信息，请参阅[Event 语句](../../../visual-basic/language-reference/statements/event-statement.md)。</span><span class="sxs-lookup"><span data-stu-id="61222-116">For more information on custom events, see [Event Statement](../../../visual-basic/language-reference/statements/event-statement.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="61222-117">示例</span><span class="sxs-lookup"><span data-stu-id="61222-117">Example</span></span>  
 <span data-ttu-id="61222-118">[!code-vb[VbVbalrEvents #&17;](../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/addhandler-statement_1.vb)]</span><span class="sxs-lookup"><span data-stu-id="61222-118">[!code-vb[VbVbalrEvents#17](../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/addhandler-statement_1.vb)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="61222-119">另请参阅</span><span class="sxs-lookup"><span data-stu-id="61222-119">See Also</span></span>  
 <span data-ttu-id="61222-120">[RemoveHandler 语句](../../../visual-basic/language-reference/statements/removehandler-statement.md) </span><span class="sxs-lookup"><span data-stu-id="61222-120">[RemoveHandler Statement](../../../visual-basic/language-reference/statements/removehandler-statement.md) </span></span>  
<span data-ttu-id="61222-121"> [句柄](../../../visual-basic/language-reference/statements/handles-clause.md) </span><span class="sxs-lookup"><span data-stu-id="61222-121"> [Handles](../../../visual-basic/language-reference/statements/handles-clause.md) </span></span>  
<span data-ttu-id="61222-122"> [Event 语句](../../../visual-basic/language-reference/statements/event-statement.md) </span><span class="sxs-lookup"><span data-stu-id="61222-122"> [Event Statement](../../../visual-basic/language-reference/statements/event-statement.md) </span></span>  
<span data-ttu-id="61222-123"> [事件](../../../visual-basic/programming-guide/language-features/events/index.md)</span><span class="sxs-lookup"><span data-stu-id="61222-123"> [Events](../../../visual-basic/programming-guide/language-features/events/index.md)</span></span>
