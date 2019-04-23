---
title: 对象或类不支持事件集
ms.date: 07/20/2015
f1_keywords:
- vbrID459
ms.assetid: 785df3f3-2aae-4a25-af36-1f9879d4e5fd
ms.openlocfilehash: ad9176b5332a75f03968e742501c3fce541055de
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/18/2019
ms.locfileid: "59342877"
---
# <a name="object-or-class-does-not-support-the-set-of-events"></a><span data-ttu-id="668d1-102">对象或类不支持事件集</span><span class="sxs-lookup"><span data-stu-id="668d1-102">Object or class does not support the set of events</span></span>
<span data-ttu-id="668d1-103">您尝试使用`WithEvents`变量替换为指定的事件集的事件源不能工作的组件。</span><span class="sxs-lookup"><span data-stu-id="668d1-103">You tried to use a `WithEvents` variable with a component that cannot work as an event source for the specified set of events.</span></span> <span data-ttu-id="668d1-104">例如，你想要接收的事件对象，然后创建另一个对象`Implements`的第一个对象。</span><span class="sxs-lookup"><span data-stu-id="668d1-104">For example, you wanted to sink the events of an object, then create another object that `Implements` the first object.</span></span> <span data-ttu-id="668d1-105">尽管您可能认为可以实现的对象接收的事件，但这并不总是这种情况。</span><span class="sxs-lookup"><span data-stu-id="668d1-105">Although you might think you could sink the events from the implemented object, this is not always the case.</span></span> <span data-ttu-id="668d1-106">`Implements` 仅实现的接口方法和属性。</span><span class="sxs-lookup"><span data-stu-id="668d1-106">`Implements` only implements an interface for methods and properties.</span></span> <span data-ttu-id="668d1-107">`WithEvents` 不支持私有`UserControls`，因为类型信息所需引发`ObjectEvent`在运行时不可用。</span><span class="sxs-lookup"><span data-stu-id="668d1-107">`WithEvents` is not supported for private `UserControls`, because the type info needed to raise the `ObjectEvent` is not available at run time.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="668d1-108">更正此错误</span><span class="sxs-lookup"><span data-stu-id="668d1-108">To correct this error</span></span>  
  
1. <span data-ttu-id="668d1-109">不能接收事件不是事件源的组件。</span><span class="sxs-lookup"><span data-stu-id="668d1-109">You cannot sink events for a component that does not source events.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="668d1-110">请参阅</span><span class="sxs-lookup"><span data-stu-id="668d1-110">See also</span></span>

- [<span data-ttu-id="668d1-111">WithEvents</span><span class="sxs-lookup"><span data-stu-id="668d1-111">WithEvents</span></span>](../../../visual-basic/language-reference/modifiers/withevents.md)
- [<span data-ttu-id="668d1-112">Implements 语句</span><span class="sxs-lookup"><span data-stu-id="668d1-112">Implements Statement</span></span>](../../../visual-basic/language-reference/statements/implements-statement.md)
