---
title: 如何：合并委托（多路广播委托）（C# 编程指南）
ms.date: 07/20/2015
helpviewer_keywords:
- delegates [C#], combining
- multicast delegates [C#]
ms.assetid: 4e689450-6d0c-46de-acfd-f961018ae5dd
ms.openlocfilehash: e3cc3f9082bd86004a7821b64c01253408c07641
ms.sourcegitcommit: 64f4baed249341e5bf64d1385bf48e3f2e1a0211
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/07/2018
ms.locfileid: "44083272"
---
# <a name="how-to-combine-delegates-multicast-delegatesc-programming-guide"></a><span data-ttu-id="54539-102">如何：合并委托（多路广播委托）（C# 编程指南）</span><span class="sxs-lookup"><span data-stu-id="54539-102">How to: Combine Delegates (Multicast Delegates)(C# Programming Guide)</span></span>
<span data-ttu-id="54539-103">此示例演示如何创建多播委托。</span><span class="sxs-lookup"><span data-stu-id="54539-103">This example demonstrates how to create multicast delegates.</span></span> <span data-ttu-id="54539-104">[委托](../../../csharp/language-reference/keywords/delegate.md)对象的一个有用属性在于可通过使用 `+` 运算符将多个对象分配到一个委托实例。</span><span class="sxs-lookup"><span data-stu-id="54539-104">A useful property of [delegate](../../../csharp/language-reference/keywords/delegate.md) objects is that multiple objects can be assigned to one delegate instance by using the `+` operator.</span></span> <span data-ttu-id="54539-105">多播委托包含已分配委托列表。</span><span class="sxs-lookup"><span data-stu-id="54539-105">The multicast delegate contains a list of the assigned delegates.</span></span> <span data-ttu-id="54539-106">此多播委托被调用时会依次调用列表中的委托。</span><span class="sxs-lookup"><span data-stu-id="54539-106">When the multicast delegate is called, it invokes the delegates in the list, in order.</span></span> <span data-ttu-id="54539-107">仅可合并类型相同的委托。</span><span class="sxs-lookup"><span data-stu-id="54539-107">Only delegates of the same type can be combined.</span></span>  
  
 <span data-ttu-id="54539-108">`-` 运算符可用于从多播委托中删除组件委托。</span><span class="sxs-lookup"><span data-stu-id="54539-108">The `-` operator can be used to remove a component delegate from a multicast delegate.</span></span>  
  
## <a name="example"></a><span data-ttu-id="54539-109">示例</span><span class="sxs-lookup"><span data-stu-id="54539-109">Example</span></span>  
 [!code-csharp[csProgGuideDelegates#11](../../../csharp/programming-guide/delegates/codesnippet/CSharp/how-to-combine-delegates-multicast-delegates_1.cs)]  
  
## <a name="see-also"></a><span data-ttu-id="54539-110">请参阅</span><span class="sxs-lookup"><span data-stu-id="54539-110">See Also</span></span>

- <xref:System.MulticastDelegate>  
- [<span data-ttu-id="54539-111">C# 编程指南</span><span class="sxs-lookup"><span data-stu-id="54539-111">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
- [<span data-ttu-id="54539-112">事件</span><span class="sxs-lookup"><span data-stu-id="54539-112">Events</span></span>](../../../csharp/programming-guide/events/index.md)
