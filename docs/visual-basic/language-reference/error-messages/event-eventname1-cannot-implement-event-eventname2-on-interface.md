---
title: 事件&#39; &lt;eventname1&gt; &#39;不能实现事件&#39; &lt;eventname2&gt; &#39;接口上&#39;&lt;接口&gt;&#39;因为其委托类型&#39; &lt;delegate1&gt; &#39;和&#39; &lt;delegate2&gt; &#39;不匹配
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vbc31423
- bc31423
helpviewer_keywords:
- BC31423
ms.assetid: 2e754b66-5836-48ff-9697-b9c0d7085f18
caps.latest.revision: 6
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 41f5984458eb17db04f20b292a0d80783093dcb4
ms.sourcegitcommit: 86adcc06e35390f13c1e372c36d2e044f1fc31ef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/26/2018
---
# <a name="event-39lteventname1gt39-cannot-implement-event-39lteventname2gt39-on-interface-39ltinterfacegt39-because-their-delegate-types-39ltdelegate1gt39-and-39ltdelegate2gt39-do-not-match"></a><span data-ttu-id="4f1dd-102">事件&#39; &lt;eventname1&gt; &#39;不能实现事件&#39; &lt;eventname2&gt; &#39;接口上&#39;&lt;接口&gt;&#39;因为其委托类型&#39; &lt;delegate1&gt; &#39;和&#39; &lt;delegate2&gt; &#39;不匹配</span><span class="sxs-lookup"><span data-stu-id="4f1dd-102">Event &#39;&lt;eventname1&gt;&#39; cannot implement event &#39;&lt;eventname2&gt;&#39; on interface &#39;&lt;interface&gt;&#39; because their delegate types &#39;&lt;delegate1&gt;&#39; and &#39;&lt;delegate2&gt;&#39; do not match</span></span>
<span data-ttu-id="4f1dd-103">Visual Basic 不能实现某个事件，因为该事件的委托类型不匹配的委托类型的接口中的事件。</span><span class="sxs-lookup"><span data-stu-id="4f1dd-103">Visual Basic cannot implement an event because the delegate type of the event does not match the delegate type of the event in the interface.</span></span> <span data-ttu-id="4f1dd-104">如果在接口中定义了多个事件，然后试图用一个事件同时实现这些事件，则可能发生此错误。</span><span class="sxs-lookup"><span data-stu-id="4f1dd-104">This error can occur when you define multiple events in an interface and then attempt to implement them together with the same event.</span></span> <span data-ttu-id="4f1dd-105">只有当所有要实现的事件都使用 `As` 语法进行声明并指定相同的委托类型时，事件才能实现两个或更多个事件。</span><span class="sxs-lookup"><span data-stu-id="4f1dd-105">An event can implement two or more events only if all implemented events are declared using the `As` syntax and specify the same delegate type.</span></span>  
  
 <span data-ttu-id="4f1dd-106">**错误 ID:** BC31423</span><span class="sxs-lookup"><span data-stu-id="4f1dd-106">**Error ID:** BC31423</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="4f1dd-107">更正此错误</span><span class="sxs-lookup"><span data-stu-id="4f1dd-107">To correct this error</span></span>  
  
-   <span data-ttu-id="4f1dd-108">单独实现事件。</span><span class="sxs-lookup"><span data-stu-id="4f1dd-108">Implement the events separately.</span></span>  
  
     <span data-ttu-id="4f1dd-109">- 或 -</span><span class="sxs-lookup"><span data-stu-id="4f1dd-109">—or—</span></span>  
  
-   <span data-ttu-id="4f1dd-110">在接口中使用定义的事件`As`语法并指定相同的委托类型。</span><span class="sxs-lookup"><span data-stu-id="4f1dd-110">Define the events in the interface using the `As` syntax and specify the same delegate type.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4f1dd-111">请参阅</span><span class="sxs-lookup"><span data-stu-id="4f1dd-111">See Also</span></span>  
 [<span data-ttu-id="4f1dd-112">Event 语句</span><span class="sxs-lookup"><span data-stu-id="4f1dd-112">Event Statement</span></span>](../../../visual-basic/language-reference/statements/event-statement.md)  
 [<span data-ttu-id="4f1dd-113">Delegate 语句</span><span class="sxs-lookup"><span data-stu-id="4f1dd-113">Delegate Statement</span></span>](../../../visual-basic/language-reference/statements/delegate-statement.md)  
 [<span data-ttu-id="4f1dd-114">事件</span><span class="sxs-lookup"><span data-stu-id="4f1dd-114">Events</span></span>](../../../visual-basic/programming-guide/language-features/events/index.md)
