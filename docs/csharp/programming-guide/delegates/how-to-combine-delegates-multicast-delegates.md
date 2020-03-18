---
title: 如何合并委托（多播委托）- C# 编程指南
ms.date: 07/20/2015
helpviewer_keywords:
- delegates [C#], combining
- multicast delegates [C#]
ms.assetid: 4e689450-6d0c-46de-acfd-f961018ae5dd
ms.openlocfilehash: 7b5b9ba5c9bf70983fac9f869836b4c8c5449eca
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/14/2020
ms.locfileid: "75705374"
---
# <a name="how-to-combine-delegates-multicast-delegates-c-programming-guide"></a><span data-ttu-id="30e51-102">如何合并委托（多播委托）（C# 编程指南）</span><span class="sxs-lookup"><span data-stu-id="30e51-102">How to combine delegates (Multicast Delegates) (C# Programming Guide)</span></span>
<span data-ttu-id="30e51-103">此示例演示如何创建多播委托。</span><span class="sxs-lookup"><span data-stu-id="30e51-103">This example demonstrates how to create multicast delegates.</span></span> <span data-ttu-id="30e51-104">[委托](../../language-reference/builtin-types/reference-types.md)对象的一个有用属性在于可通过使用 `+` 运算符将多个对象分配到一个委托实例。</span><span class="sxs-lookup"><span data-stu-id="30e51-104">A useful property of [delegate](../../language-reference/builtin-types/reference-types.md) objects is that multiple objects can be assigned to one delegate instance by using the `+` operator.</span></span> <span data-ttu-id="30e51-105">多播委托包含已分配委托列表。</span><span class="sxs-lookup"><span data-stu-id="30e51-105">The multicast delegate contains a list of the assigned delegates.</span></span> <span data-ttu-id="30e51-106">此多播委托被调用时会依次调用列表中的委托。</span><span class="sxs-lookup"><span data-stu-id="30e51-106">When the multicast delegate is called, it invokes the delegates in the list, in order.</span></span> <span data-ttu-id="30e51-107">仅可合并类型相同的委托。</span><span class="sxs-lookup"><span data-stu-id="30e51-107">Only delegates of the same type can be combined.</span></span>  
  
 <span data-ttu-id="30e51-108">`-` 运算符可用于从多播委托中删除组件委托。</span><span class="sxs-lookup"><span data-stu-id="30e51-108">The `-` operator can be used to remove a component delegate from a multicast delegate.</span></span>  
  
## <a name="example"></a><span data-ttu-id="30e51-109">示例</span><span class="sxs-lookup"><span data-stu-id="30e51-109">Example</span></span>  
 [!code-csharp[csProgGuideDelegates#11](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideDelegates/CS/Delegates.cs#11)]  
  
## <a name="see-also"></a><span data-ttu-id="30e51-110">另请参阅</span><span class="sxs-lookup"><span data-stu-id="30e51-110">See also</span></span>

- <xref:System.MulticastDelegate>
- [<span data-ttu-id="30e51-111">C# 编程指南</span><span class="sxs-lookup"><span data-stu-id="30e51-111">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="30e51-112">事件</span><span class="sxs-lookup"><span data-stu-id="30e51-112">Events</span></span>](../events/index.md)
