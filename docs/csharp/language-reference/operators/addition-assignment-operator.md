---
title: += 运算符（C# 参考）
ms.date: 10/29/2018
f1_keywords:
- +=_CSharpKeyword
helpviewer_keywords:
- += operator [C#]
- addition assignment operator (+=) [C#]
- event subscription [C#]
ms.assetid: 9cdf97e6-331d-492b-85e1-3ec3171484e9
ms.openlocfilehash: ac9330e283cb58ae4e0ee7b644aa2c22bdf64c46
ms.sourcegitcommit: 3b1cb8467bd73dee854b604e306c0e7e3882d91a
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/07/2018
ms.locfileid: "50192026"
---
# <a name="-operator-c-reference"></a><span data-ttu-id="49dac-102">+= 运算符（C# 参考）</span><span class="sxs-lookup"><span data-stu-id="49dac-102">+= Operator (C# Reference)</span></span>

<span data-ttu-id="49dac-103">加法赋值运算符。</span><span class="sxs-lookup"><span data-stu-id="49dac-103">The addition assignment operator.</span></span>

<span data-ttu-id="49dac-104">使用 `+=` 运算符的表达式，例如</span><span class="sxs-lookup"><span data-stu-id="49dac-104">An expression using the `+=` operator, such as</span></span>

```csharp
x += y
```

<span data-ttu-id="49dac-105">等效于</span><span class="sxs-lookup"><span data-stu-id="49dac-105">is equivalent to</span></span>

```csharp
x = x + y
```

<span data-ttu-id="49dac-106">不同的是 `x` 只计算一次。</span><span class="sxs-lookup"><span data-stu-id="49dac-106">except that `x` is only evaluated once.</span></span>
  
<span data-ttu-id="49dac-107">对于数字类型，[加法运算符](addition-operator.md) `+`计算其操作数的和。</span><span class="sxs-lookup"><span data-stu-id="49dac-107">For numeric types, the [addition operator](addition-operator.md) `+` computes the sum of its operands.</span></span> <span data-ttu-id="49dac-108">如果其中的一个操作数是 [string](../keywords/string.md) 类型或两个操作数都是该类型，它会将操作数的字符串表示形式串联在一起。</span><span class="sxs-lookup"><span data-stu-id="49dac-108">If one or both operands is of type [string](../keywords/string.md), it concatenates the string representations of its operands.</span></span> <span data-ttu-id="49dac-109">对于委托类型，`+` 运算符返回一个新的委托实例，该实例是其操作数的组合。</span><span class="sxs-lookup"><span data-stu-id="49dac-109">For delegate types, the `+` operator returns a new delegate instance that is combination of its operands.</span></span>

<span data-ttu-id="49dac-110">在订阅[事件](../keywords/event.md)时，还可以使用 `+=` 运算符来指定事件处理程序方法。</span><span class="sxs-lookup"><span data-stu-id="49dac-110">You also use the `+=` operator to specify an event handler method when you subscribe to an [event](../keywords/event.md).</span></span> <span data-ttu-id="49dac-111">有关详细信息，请参阅[如何：订阅和取消订阅事件](../../programming-guide/events/how-to-subscribe-to-and-unsubscribe-from-events.md)。</span><span class="sxs-lookup"><span data-stu-id="49dac-111">For more information, see [How to: Subscribe to and Unsubscribe from Events](../../programming-guide/events/how-to-subscribe-to-and-unsubscribe-from-events.md).</span></span>

<span data-ttu-id="49dac-112">下面的示例演示 `+=` 运算符的用法：</span><span class="sxs-lookup"><span data-stu-id="49dac-112">The following example demonstrates the usage of the `+=` operator:</span></span>

[!code-csharp-interactive[+= examples](~/samples/snippets/csharp/language-reference/operators/AdditionExamples.cs#AddAndAssign)]

## <a name="operator-overloadability"></a><span data-ttu-id="49dac-113">运算符可重载性</span><span class="sxs-lookup"><span data-stu-id="49dac-113">Operator overloadability</span></span>

<span data-ttu-id="49dac-114">如果用户定义类型[重载](../keywords/operator.md)[加法运算符](addition-operator.md) `+`，则加法赋值运算符 `+=` 为隐式重载。</span><span class="sxs-lookup"><span data-stu-id="49dac-114">If a user-defined type [overloads](../keywords/operator.md) the [addition operator](addition-operator.md) `+`, the addition assignment operator `+=` is implicitly overloaded.</span></span> <span data-ttu-id="49dac-115">用户定义类型不能显式重载加法赋值运算符。</span><span class="sxs-lookup"><span data-stu-id="49dac-115">A user-defined type cannot explicitly overload the addition assignment operator.</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="49dac-116">C# 语言规范</span><span class="sxs-lookup"><span data-stu-id="49dac-116">C# language specification</span></span>

<span data-ttu-id="49dac-117">有关详细信息，请参阅 [C# 语言规范](../language-specification/index.md)中的[复合赋值](~/_csharplang/spec/expressions.md#compound-assignment)和[事件赋值](~/_csharplang/spec/expressions.md#event-assignment)部分。</span><span class="sxs-lookup"><span data-stu-id="49dac-117">For more information, see the [Compound assignment](~/_csharplang/spec/expressions.md#compound-assignment) and [Event assignment](~/_csharplang/spec/expressions.md#event-assignment) sections of the [C# language specification](../language-specification/index.md).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="49dac-118">请参阅</span><span class="sxs-lookup"><span data-stu-id="49dac-118">See also</span></span>

- [<span data-ttu-id="49dac-119">C# 参考</span><span class="sxs-lookup"><span data-stu-id="49dac-119">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="49dac-120">C# 编程指南</span><span class="sxs-lookup"><span data-stu-id="49dac-120">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="49dac-121">C# 运算符</span><span class="sxs-lookup"><span data-stu-id="49dac-121">C# Operators</span></span>](index.md)
- [<span data-ttu-id="49dac-122">事件</span><span class="sxs-lookup"><span data-stu-id="49dac-122">Events</span></span>](../../programming-guide/events/index.md)
- [<span data-ttu-id="49dac-123">委托</span><span class="sxs-lookup"><span data-stu-id="49dac-123">Delegates</span></span>](../../programming-guide/delegates/index.md)
