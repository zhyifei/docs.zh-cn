---
title: "如何：合并委托（多路广播委托）（C# 编程指南）"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- delegates [C#], combining
- multicast delegates [C#]
ms.assetid: 4e689450-6d0c-46de-acfd-f961018ae5dd
caps.latest.revision: 17
author: BillWagner
ms.author: wiwagn
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
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 617af10d3fb5f9371d5893b87a91a48639d44a53
ms.contentlocale: zh-cn
ms.lasthandoff: 07/28/2017

---
# <a name="how-to-combine-delegates-multicast-delegatesc-programming-guide"></a><span data-ttu-id="ad7cb-102">如何：合并委托（多路广播委托）（C# 编程指南）</span><span class="sxs-lookup"><span data-stu-id="ad7cb-102">How to: Combine Delegates (Multicast Delegates)(C# Programming Guide)</span></span>
<span data-ttu-id="ad7cb-103">此示例演示如何创建多播委托。</span><span class="sxs-lookup"><span data-stu-id="ad7cb-103">This example demonstrates how to create multicast delegates.</span></span> <span data-ttu-id="ad7cb-104">[委托](../../../csharp/language-reference/keywords/delegate.md)对象的一个有用属性在于可通过使用 `+` 运算符将多个对象分配到一个委托实例。</span><span class="sxs-lookup"><span data-stu-id="ad7cb-104">A useful property of [delegate](../../../csharp/language-reference/keywords/delegate.md) objects is that multiple objects can be assigned to one delegate instance by using the `+` operator.</span></span> <span data-ttu-id="ad7cb-105">多播委托包含已分配委托列表。</span><span class="sxs-lookup"><span data-stu-id="ad7cb-105">The multicast delegate contains a list of the assigned delegates.</span></span> <span data-ttu-id="ad7cb-106">此多播委托被调用时会依次调用列表中的委托。</span><span class="sxs-lookup"><span data-stu-id="ad7cb-106">When the multicast delegate is called, it invokes the delegates in the list, in order.</span></span> <span data-ttu-id="ad7cb-107">仅可合并类型相同的委托。</span><span class="sxs-lookup"><span data-stu-id="ad7cb-107">Only delegates of the same type can be combined.</span></span>  
  
 <span data-ttu-id="ad7cb-108">`-` 运算符可用于从多播委托中删除组件委托。</span><span class="sxs-lookup"><span data-stu-id="ad7cb-108">The `-` operator can be used to remove a component delegate from a multicast delegate.</span></span>  
  
## <a name="example"></a><span data-ttu-id="ad7cb-109">示例</span><span class="sxs-lookup"><span data-stu-id="ad7cb-109">Example</span></span>  
 <span data-ttu-id="ad7cb-110">[!code-cs[csProgGuideDelegates#11](../../../csharp/programming-guide/delegates/codesnippet/CSharp/how-to-combine-delegates-multicast-delegates_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="ad7cb-110">[!code-cs[csProgGuideDelegates#11](../../../csharp/programming-guide/delegates/codesnippet/CSharp/how-to-combine-delegates-multicast-delegates_1.cs)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ad7cb-111">另请参阅</span><span class="sxs-lookup"><span data-stu-id="ad7cb-111">See Also</span></span>  
 <span data-ttu-id="ad7cb-112"><xref:System.MulticastDelegate></span><span class="sxs-lookup"><span data-stu-id="ad7cb-112"><xref:System.MulticastDelegate></span></span>   
 <span data-ttu-id="ad7cb-113">[C# 编程指南](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="ad7cb-113">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 [<span data-ttu-id="ad7cb-114">事件</span><span class="sxs-lookup"><span data-stu-id="ad7cb-114">Events</span></span>](../../../csharp/programming-guide/events/index.md)

