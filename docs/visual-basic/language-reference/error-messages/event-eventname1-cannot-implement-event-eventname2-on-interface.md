---
title: 事件“<eventname1>”无法实现接口“<eventname2>”上的事件“<interface>”，因为它们的委托类型“<delegate1>”和“<delegate2>”不匹配
ms.date: 07/20/2015
f1_keywords:
- vbc31423
- bc31423
helpviewer_keywords:
- BC31423
ms.assetid: 2e754b66-5836-48ff-9697-b9c0d7085f18
ms.openlocfilehash: 3ec3e7bb2f28bf8c4dd38bc71e11193456860021
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/05/2019
ms.locfileid: "57379752"
---
# <a name="event-eventname1-cannot-implement-event-eventname2-on-interface-interface-because-their-delegate-types-delegate1-and-delegate2-do-not-match"></a><span data-ttu-id="542f9-102">事件\<eventname1 > 不能实现事件\<eventname2 > 接口上 '\<界面 > 因为它们的委托类型的\<delegate1 > 和\<delegate2 > 不匹配</span><span class="sxs-lookup"><span data-stu-id="542f9-102">Event '\<eventname1>' cannot implement event '\<eventname2>' on interface '\<interface>' because their delegate types '\<delegate1>' and '\<delegate2>' do not match</span></span>
<span data-ttu-id="542f9-103">Visual Basic 不能实现某个事件，因为该事件的委托类型与该接口中的事件的委托类型不匹配。</span><span class="sxs-lookup"><span data-stu-id="542f9-103">Visual Basic cannot implement an event because the delegate type of the event does not match the delegate type of the event in the interface.</span></span> <span data-ttu-id="542f9-104">如果在接口中定义了多个事件，然后试图用一个事件同时实现这些事件，则可能发生此错误。</span><span class="sxs-lookup"><span data-stu-id="542f9-104">This error can occur when you define multiple events in an interface and then attempt to implement them together with the same event.</span></span> <span data-ttu-id="542f9-105">只有当所有要实现的事件都使用 `As` 语法进行声明并指定相同的委托类型时，事件才能实现两个或更多个事件。</span><span class="sxs-lookup"><span data-stu-id="542f9-105">An event can implement two or more events only if all implemented events are declared using the `As` syntax and specify the same delegate type.</span></span>  
  
 <span data-ttu-id="542f9-106">**错误 ID:** BC31423</span><span class="sxs-lookup"><span data-stu-id="542f9-106">**Error ID:** BC31423</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="542f9-107">更正此错误</span><span class="sxs-lookup"><span data-stu-id="542f9-107">To correct this error</span></span>  
  
-   <span data-ttu-id="542f9-108">单独实现事件。</span><span class="sxs-lookup"><span data-stu-id="542f9-108">Implement the events separately.</span></span>  
  
     <span data-ttu-id="542f9-109">- 或 -</span><span class="sxs-lookup"><span data-stu-id="542f9-109">—or—</span></span>  
  
-   <span data-ttu-id="542f9-110">使用在接口中定义的事件`As`语法，并指定相同的委托类型。</span><span class="sxs-lookup"><span data-stu-id="542f9-110">Define the events in the interface using the `As` syntax and specify the same delegate type.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="542f9-111">请参阅</span><span class="sxs-lookup"><span data-stu-id="542f9-111">See also</span></span>
- [<span data-ttu-id="542f9-112">Event 语句</span><span class="sxs-lookup"><span data-stu-id="542f9-112">Event Statement</span></span>](../../../visual-basic/language-reference/statements/event-statement.md)
- [<span data-ttu-id="542f9-113">Delegate 语句</span><span class="sxs-lookup"><span data-stu-id="542f9-113">Delegate Statement</span></span>](../../../visual-basic/language-reference/statements/delegate-statement.md)
- [<span data-ttu-id="542f9-114">事件</span><span class="sxs-lookup"><span data-stu-id="542f9-114">Events</span></span>](../../../visual-basic/programming-guide/language-features/events/index.md)
