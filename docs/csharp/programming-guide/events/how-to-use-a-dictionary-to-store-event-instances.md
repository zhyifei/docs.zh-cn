---
title: 如何：使用字典存储事件实例 - C# 编程指南
ms.custom: seodec18
ms.date: 07/20/2015
helpviewer_keywords:
- events [C#], storing instances in a Dictionary
ms.assetid: 9512c64d-5aaf-40cd-b941-ca2a592f0064
ms.openlocfilehash: f3b8e313bd0b1bd3973102caebb9bbc9da620ae6
ms.sourcegitcommit: 41c0637e894fbcd0713d46d6ef1866f08dc321a2
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/01/2019
ms.locfileid: "57203027"
---
# <a name="how-to-use-a-dictionary-to-store-event-instances-c-programming-guide"></a><span data-ttu-id="c2c5c-102">如何：使用字典存储事件实例（C# 编程指南）</span><span class="sxs-lookup"><span data-stu-id="c2c5c-102">How to: Use a Dictionary to Store Event Instances (C# Programming Guide)</span></span>
<span data-ttu-id="c2c5c-103">`accessor-declarations` 的一个用途是公开多个事件，无需为每个事件分配一个字段，而是改用词典存储事件实例。</span><span class="sxs-lookup"><span data-stu-id="c2c5c-103">One use for `accessor-declarations` is to expose many events without allocating a field for each event, but instead using a Dictionary to store the event instances.</span></span> <span data-ttu-id="c2c5c-104">仅当拥有多个事件，但预计不会实现大多数事件时有用。</span><span class="sxs-lookup"><span data-stu-id="c2c5c-104">This is only useful if you have many events, but you expect most of the events will not be implemented.</span></span>  
  
## <a name="example"></a><span data-ttu-id="c2c5c-105">示例</span><span class="sxs-lookup"><span data-stu-id="c2c5c-105">Example</span></span>  
 [!code-csharp[csProgGuideEvents#9](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideEvents/CS/Events.cs#9)]  
  
## <a name="see-also"></a><span data-ttu-id="c2c5c-106">请参阅</span><span class="sxs-lookup"><span data-stu-id="c2c5c-106">See also</span></span>

- [<span data-ttu-id="c2c5c-107">C# 编程指南</span><span class="sxs-lookup"><span data-stu-id="c2c5c-107">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)
- [<span data-ttu-id="c2c5c-108">事件</span><span class="sxs-lookup"><span data-stu-id="c2c5c-108">Events</span></span>](../../../csharp/programming-guide/events/index.md)
- [<span data-ttu-id="c2c5c-109">委托</span><span class="sxs-lookup"><span data-stu-id="c2c5c-109">Delegates</span></span>](../../../csharp/programming-guide/delegates/index.md)
