---
title: 对象或类不支持事件集
ms.date: 07/20/2015
f1_keywords:
- vbrID459
ms.assetid: 785df3f3-2aae-4a25-af36-1f9879d4e5fd
ms.openlocfilehash: ad9176b5332a75f03968e742501c3fce541055de
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/09/2019
ms.locfileid: "59342877"
---
# <a name="object-or-class-does-not-support-the-set-of-events"></a><span data-ttu-id="55c6c-102">对象或类不支持事件集</span><span class="sxs-lookup"><span data-stu-id="55c6c-102">Object or class does not support the set of events</span></span>
<span data-ttu-id="55c6c-103">您尝试使用`WithEvents`变量替换为指定的事件集的事件源不能工作的组件。</span><span class="sxs-lookup"><span data-stu-id="55c6c-103">You tried to use a `WithEvents` variable with a component that cannot work as an event source for the specified set of events.</span></span> <span data-ttu-id="55c6c-104">例如，你想要接收的事件对象，然后创建另一个对象`Implements`的第一个对象。</span><span class="sxs-lookup"><span data-stu-id="55c6c-104">For example, you wanted to sink the events of an object, then create another object that `Implements` the first object.</span></span> <span data-ttu-id="55c6c-105">尽管您可能认为可以实现的对象接收的事件，但这并不总是这种情况。</span><span class="sxs-lookup"><span data-stu-id="55c6c-105">Although you might think you could sink the events from the implemented object, this is not always the case.</span></span> `Implements` <span data-ttu-id="55c6c-106">仅实现的接口方法和属性。</span><span class="sxs-lookup"><span data-stu-id="55c6c-106">only implements an interface for methods and properties.</span></span> `WithEvents` <span data-ttu-id="55c6c-107">不支持私有`UserControls`，因为类型信息所需引发`ObjectEvent`在运行时不可用。</span><span class="sxs-lookup"><span data-stu-id="55c6c-107">is not supported for private `UserControls`, because the type info needed to raise the `ObjectEvent` is not available at run time.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="55c6c-108">更正此错误</span><span class="sxs-lookup"><span data-stu-id="55c6c-108">To correct this error</span></span>  
  
1. <span data-ttu-id="55c6c-109">不能接收事件不是事件源的组件。</span><span class="sxs-lookup"><span data-stu-id="55c6c-109">You cannot sink events for a component that does not source events.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="55c6c-110">请参阅</span><span class="sxs-lookup"><span data-stu-id="55c6c-110">See also</span></span>

- [<span data-ttu-id="55c6c-111">WithEvents</span><span class="sxs-lookup"><span data-stu-id="55c6c-111">WithEvents</span></span>](../../../visual-basic/language-reference/modifiers/withevents.md)
- [<span data-ttu-id="55c6c-112">Implements 语句</span><span class="sxs-lookup"><span data-stu-id="55c6c-112">Implements Statement</span></span>](../../../visual-basic/language-reference/statements/implements-statement.md)
