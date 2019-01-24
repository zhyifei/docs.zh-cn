---
title: -= 运算符 - C# 参考
ms.custom: seodec18
ms.date: 07/20/2015
f1_keywords:
- -=_CSharpKeyword
helpviewer_keywords:
- subtraction assignment operator (-=) [C#]
- -= operator (subtraction assignment ) [C#]
ms.assetid: 05c7d68a-423f-4de8-891b-cf24e8fb6ed7
ms.openlocfilehash: 3b6890be4460a599a5d2f5f5f6ee1627be933f0b
ms.sourcegitcommit: 5c36aaa8299a2437c155700c810585aff19edbec
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/16/2019
ms.locfileid: "54333325"
---
# <a name="--operator-c-reference"></a><span data-ttu-id="d2d25-102">-= 运算符（C# 参考）</span><span class="sxs-lookup"><span data-stu-id="d2d25-102">-= operator (C# Reference)</span></span>

<span data-ttu-id="d2d25-103">减法赋值运算符。</span><span class="sxs-lookup"><span data-stu-id="d2d25-103">The subtraction assignment operator.</span></span>

## <a name="remarks"></a><span data-ttu-id="d2d25-104">备注</span><span class="sxs-lookup"><span data-stu-id="d2d25-104">Remarks</span></span>

<span data-ttu-id="d2d25-105">使用 `-=` 赋值运算符的表达式，如</span><span class="sxs-lookup"><span data-stu-id="d2d25-105">An expression using the `-=` assignment operator, such as</span></span>

```csharp
x -= y
```

 <span data-ttu-id="d2d25-106">等效于</span><span class="sxs-lookup"><span data-stu-id="d2d25-106">is equivalent to</span></span>

```csharp
x = x - y
```

<span data-ttu-id="d2d25-107">不同的是 `x` 只计算一次。</span><span class="sxs-lookup"><span data-stu-id="d2d25-107">except that `x` is only evaluated once.</span></span> <span data-ttu-id="d2d25-108">[- 运算符](subtraction-operator.md)的含义取决于 `x` 和 `y` 的类型（例如，对于数值操作数，其含义为相减；对于委托操作数，其含义为移除委托）。</span><span class="sxs-lookup"><span data-stu-id="d2d25-108">The meaning of the [- operator](subtraction-operator.md) is dependent on the types of `x` and `y` (subtraction for numeric operands, delegate removal for delegate operands, and so forth).</span></span>

<span data-ttu-id="d2d25-109">不能直接重载 `-=` 运算符，但用户定义的类型可重载 [- 运算符](subtraction-operator.md)（请参阅[运算符](../keywords/operator.md)）。</span><span class="sxs-lookup"><span data-stu-id="d2d25-109">The `-=` operator cannot be overloaded directly, but user-defined types can overload the [- operator](subtraction-operator.md) (see [operator](../keywords/operator.md)).</span></span>

<span data-ttu-id="d2d25-110">C# 中也使用 -= 运算符来取消订阅事件。</span><span class="sxs-lookup"><span data-stu-id="d2d25-110">The -= operator is also used in C# to unsubscribe from an event.</span></span> <span data-ttu-id="d2d25-111">有关详细信息，请参阅[如何：订阅和取消订阅事件](../../programming-guide/events/how-to-subscribe-to-and-unsubscribe-from-events.md)。</span><span class="sxs-lookup"><span data-stu-id="d2d25-111">For more information, see [How to: Subscribe to and Unsubscribe from Events](../../programming-guide/events/how-to-subscribe-to-and-unsubscribe-from-events.md).</span></span>

## <a name="example"></a><span data-ttu-id="d2d25-112">示例</span><span class="sxs-lookup"><span data-stu-id="d2d25-112">Example</span></span>

[!code-csharp[csRefOperators#6](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefOperators/CS/csrefOperators.cs#6)]

## <a name="see-also"></a><span data-ttu-id="d2d25-113">请参阅</span><span class="sxs-lookup"><span data-stu-id="d2d25-113">See also</span></span>

- [<span data-ttu-id="d2d25-114">C# 参考</span><span class="sxs-lookup"><span data-stu-id="d2d25-114">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="d2d25-115">C# 编程指南</span><span class="sxs-lookup"><span data-stu-id="d2d25-115">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="d2d25-116">C# 运算符</span><span class="sxs-lookup"><span data-stu-id="d2d25-116">C# operators</span></span>](index.md)
