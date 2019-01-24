---
title: 对象或类不支持事件集
ms.date: 07/20/2015
f1_keywords:
- vbrID459
ms.assetid: 785df3f3-2aae-4a25-af36-1f9879d4e5fd
ms.openlocfilehash: 82f3acff1730b4b31b0118a46376825c8807e1da
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54552146"
---
# <a name="object-or-class-does-not-support-the-set-of-events"></a><span data-ttu-id="c17a7-102">对象或类不支持事件集</span><span class="sxs-lookup"><span data-stu-id="c17a7-102">Object or class does not support the set of events</span></span>
<span data-ttu-id="c17a7-103">您尝试使用`WithEvents`变量替换为指定的事件集的事件源不能工作的组件。</span><span class="sxs-lookup"><span data-stu-id="c17a7-103">You tried to use a `WithEvents` variable with a component that cannot work as an event source for the specified set of events.</span></span> <span data-ttu-id="c17a7-104">例如，你想要接收的事件对象，然后创建另一个对象`Implements`的第一个对象。</span><span class="sxs-lookup"><span data-stu-id="c17a7-104">For example, you wanted to sink the events of an object, then create another object that `Implements` the first object.</span></span> <span data-ttu-id="c17a7-105">尽管您可能认为可以实现的对象接收的事件，但这并不总是这种情况。</span><span class="sxs-lookup"><span data-stu-id="c17a7-105">Although you might think you could sink the events from the implemented object, this is not always the case.</span></span> <span data-ttu-id="c17a7-106">`Implements` 仅实现的接口方法和属性。</span><span class="sxs-lookup"><span data-stu-id="c17a7-106">`Implements` only implements an interface for methods and properties.</span></span> <span data-ttu-id="c17a7-107">`WithEvents` 不支持私有`UserControls`，因为类型信息所需引发`ObjectEvent`在运行时不可用。</span><span class="sxs-lookup"><span data-stu-id="c17a7-107">`WithEvents` is not supported for private `UserControls`, because the type info needed to raise the `ObjectEvent` is not available at run time.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="c17a7-108">更正此错误</span><span class="sxs-lookup"><span data-stu-id="c17a7-108">To correct this error</span></span>  
  
1.  <span data-ttu-id="c17a7-109">不能接收事件不是事件源的组件。</span><span class="sxs-lookup"><span data-stu-id="c17a7-109">You cannot sink events for a component that does not source events.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c17a7-110">请参阅</span><span class="sxs-lookup"><span data-stu-id="c17a7-110">See also</span></span>
- [<span data-ttu-id="c17a7-111">WithEvents</span><span class="sxs-lookup"><span data-stu-id="c17a7-111">WithEvents</span></span>](../../../visual-basic/language-reference/modifiers/withevents.md)
- [<span data-ttu-id="c17a7-112">Implements 语句</span><span class="sxs-lookup"><span data-stu-id="c17a7-112">Implements Statement</span></span>](../../../visual-basic/language-reference/statements/implements-statement.md)
