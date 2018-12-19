---
title: 如何：使用字典存储事件实例 - C# 编程指南
ms.custom: seodec18
ms.date: 07/20/2015
helpviewer_keywords:
- events [C#], storing instances in a Dictionary
ms.assetid: 9512c64d-5aaf-40cd-b941-ca2a592f0064
ms.openlocfilehash: 819c81aed3a6f09a20e51285058dcc77749dd33a
ms.sourcegitcommit: bdd930b5df20a45c29483d905526a2a3e4d17c5b
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2018
ms.locfileid: "53245135"
---
# <a name="how-to-use-a-dictionary-to-store-event-instances-c-programming-guide"></a><span data-ttu-id="269c4-102">如何：使用字典存储事件实例（C# 编程指南）</span><span class="sxs-lookup"><span data-stu-id="269c4-102">How to: Use a Dictionary to Store Event Instances (C# Programming Guide)</span></span>
<span data-ttu-id="269c4-103">`accessor-declarations` 的一个用途是公开多个事件，无需为每个事件分配一个字段，而是改用词典存储事件实例。</span><span class="sxs-lookup"><span data-stu-id="269c4-103">One use for `accessor-declarations` is to expose many events without allocating a field for each event, but instead using a Dictionary to store the event instances.</span></span> <span data-ttu-id="269c4-104">仅当拥有多个事件，但预计不会实现大多数事件时有用。</span><span class="sxs-lookup"><span data-stu-id="269c4-104">This is only useful if you have many events, but you expect most of the events will not be implemented.</span></span>  
  
## <a name="example"></a><span data-ttu-id="269c4-105">示例</span><span class="sxs-lookup"><span data-stu-id="269c4-105">Example</span></span>  
 [!code-csharp[csProgGuideEvents#9](../../../csharp/programming-guide/events/codesnippet/CSharp/how-to-use-a-dictionary-to-store-event-instances_1.cs)]  
  
## <a name="see-also"></a><span data-ttu-id="269c4-106">请参阅</span><span class="sxs-lookup"><span data-stu-id="269c4-106">See Also</span></span>

- [<span data-ttu-id="269c4-107">C# 编程指南</span><span class="sxs-lookup"><span data-stu-id="269c4-107">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
- [<span data-ttu-id="269c4-108">事件</span><span class="sxs-lookup"><span data-stu-id="269c4-108">Events</span></span>](../../../csharp/programming-guide/events/index.md)  
- [<span data-ttu-id="269c4-109">委托</span><span class="sxs-lookup"><span data-stu-id="269c4-109">Delegates</span></span>](../../../csharp/programming-guide/delegates/index.md)
