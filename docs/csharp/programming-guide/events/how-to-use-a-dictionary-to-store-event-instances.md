---
title: 操作说明：使用字典存储事件实例 - C# 编程指南
ms.custom: seodec18
ms.date: 03/11/2019
helpviewer_keywords:
- events [C#], storing instances in a Dictionary
ms.assetid: 9512c64d-5aaf-40cd-b941-ca2a592f0064
ms.openlocfilehash: f8522e499887398402f63c7788bbc6c6c4f57782
ms.sourcegitcommit: 16aefeb2d265e69c0d80967580365fabf0c5d39a
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/18/2019
ms.locfileid: "57845264"
---
# <a name="how-to-use-a-dictionary-to-store-event-instances-c-programming-guide"></a><span data-ttu-id="1c24f-102">操作说明：使用字典存储事件实例（C# 编程指南）</span><span class="sxs-lookup"><span data-stu-id="1c24f-102">How to: use a dictionary to store event instances (C# Programming Guide)</span></span>

<span data-ttu-id="1c24f-103">`add` 和 `remove` 自定义事件访问器的一个用途是，公开多个事件，但不为每个事件分配字段，而是改用 <xref:System.Collections.Generic.Dictionary%602> 实例来存储事件实例，如下面的示例所示。</span><span class="sxs-lookup"><span data-stu-id="1c24f-103">One use for the `add` and `remove` custom event accessors is to expose many events without allocating a field for each event, but instead using a <xref:System.Collections.Generic.Dictionary%602> instance to store the event instances, as the example below demonstrates.</span></span> <span data-ttu-id="1c24f-104">这仅在一个类型有多个事件，但预计不会订阅大多数事件时有用。</span><span class="sxs-lookup"><span data-stu-id="1c24f-104">This is only useful if a type has many events, but you expect that most of the events will not be subscribed to.</span></span>

[!code-csharp[csProgGuideEvents#9](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideEvents/CS/Events.cs#9)]

<span data-ttu-id="1c24f-105">此实现符合 C# 语言规范中的[添加和删除委托](~/_csharplang/spec/delegates.md#delegate-invocation)行为。</span><span class="sxs-lookup"><span data-stu-id="1c24f-105">This implementation conforms to the behavior for [adding and removing delegates](~/_csharplang/spec/delegates.md#delegate-invocation) in the C# language specification.</span></span>

<span data-ttu-id="1c24f-106">请注意，[lock](../../language-reference/keywords/lock-statement.md) 语句仅用于通过事件处理程序访问字典。</span><span class="sxs-lookup"><span data-stu-id="1c24f-106">Note that the [lock](../../language-reference/keywords/lock-statement.md) statement is used only to *access* the dictionary with event handlers.</span></span> <span data-ttu-id="1c24f-107">不要在 `lock` 语句的主体内调用事件处理程序，因为它可能会导致死锁或锁争用。</span><span class="sxs-lookup"><span data-stu-id="1c24f-107">Don't invoke an event handler inside the body of the `lock` statement, as it could lead to deadlocks or lock contention.</span></span>

## <a name="see-also"></a><span data-ttu-id="1c24f-108">请参阅</span><span class="sxs-lookup"><span data-stu-id="1c24f-108">See also</span></span>

- [<span data-ttu-id="1c24f-109">C# 编程指南</span><span class="sxs-lookup"><span data-stu-id="1c24f-109">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)
- [<span data-ttu-id="1c24f-110">事件</span><span class="sxs-lookup"><span data-stu-id="1c24f-110">Events</span></span>](../../../csharp/programming-guide/events/index.md)
- [<span data-ttu-id="1c24f-111">委托</span><span class="sxs-lookup"><span data-stu-id="1c24f-111">Delegates</span></span>](../../../csharp/programming-guide/delegates/index.md)
