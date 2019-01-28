---
title: 如何：使用字典存储事件实例 - C# 编程指南
ms.custom: seodec18
ms.date: 07/20/2015
helpviewer_keywords:
- events [C#], storing instances in a Dictionary
ms.assetid: 9512c64d-5aaf-40cd-b941-ca2a592f0064
ms.openlocfilehash: 8f0284c5637890f35642346880d035619bc0e1e5
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54560056"
---
# <a name="how-to-use-a-dictionary-to-store-event-instances-c-programming-guide"></a><span data-ttu-id="49718-102">如何：使用字典存储事件实例（C# 编程指南）</span><span class="sxs-lookup"><span data-stu-id="49718-102">How to: Use a Dictionary to Store Event Instances (C# Programming Guide)</span></span>
<span data-ttu-id="49718-103">`accessor-declarations` 的一个用途是公开多个事件，无需为每个事件分配一个字段，而是改用词典存储事件实例。</span><span class="sxs-lookup"><span data-stu-id="49718-103">One use for `accessor-declarations` is to expose many events without allocating a field for each event, but instead using a Dictionary to store the event instances.</span></span> <span data-ttu-id="49718-104">仅当拥有多个事件，但预计不会实现大多数事件时有用。</span><span class="sxs-lookup"><span data-stu-id="49718-104">This is only useful if you have many events, but you expect most of the events will not be implemented.</span></span>  
  
## <a name="example"></a><span data-ttu-id="49718-105">示例</span><span class="sxs-lookup"><span data-stu-id="49718-105">Example</span></span>  
 [!code-csharp[csProgGuideEvents#9](../../../csharp/programming-guide/events/codesnippet/CSharp/how-to-use-a-dictionary-to-store-event-instances_1.cs)]  
  
## <a name="see-also"></a><span data-ttu-id="49718-106">请参阅</span><span class="sxs-lookup"><span data-stu-id="49718-106">See also</span></span>

- [<span data-ttu-id="49718-107">C# 编程指南</span><span class="sxs-lookup"><span data-stu-id="49718-107">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)
- [<span data-ttu-id="49718-108">事件</span><span class="sxs-lookup"><span data-stu-id="49718-108">Events</span></span>](../../../csharp/programming-guide/events/index.md)
- [<span data-ttu-id="49718-109">委托</span><span class="sxs-lookup"><span data-stu-id="49718-109">Delegates</span></span>](../../../csharp/programming-guide/delegates/index.md)
