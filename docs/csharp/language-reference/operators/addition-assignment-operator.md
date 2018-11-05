---
title: += 运算符（C# 参考）
ms.date: 10/22/2018
f1_keywords:
- +=_CSharpKeyword
helpviewer_keywords:
- += operator [C#]
- addition assignment operator (+=) [C#]
- event subscription [C#]
ms.assetid: 9cdf97e6-331d-492b-85e1-3ec3171484e9
ms.openlocfilehash: ee335e3e2e7d352d4e26b802bad2b08a05c666ab
ms.sourcegitcommit: c93fd5139f9efcf6db514e3474301738a6d1d649
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2018
ms.locfileid: "50192026"
---
# <a name="-operator-c-reference"></a><span data-ttu-id="ec9e0-102">+= 运算符（C# 参考）</span><span class="sxs-lookup"><span data-stu-id="ec9e0-102">+= Operator (C# Reference)</span></span>

<span data-ttu-id="ec9e0-103">加法赋值运算符。</span><span class="sxs-lookup"><span data-stu-id="ec9e0-103">The addition assignment operator.</span></span>

<span data-ttu-id="ec9e0-104">使用 `+=` 运算符的表达式，例如</span><span class="sxs-lookup"><span data-stu-id="ec9e0-104">An expression using the `+=` operator, such as</span></span>  

```csharp
x += y
```  

<span data-ttu-id="ec9e0-105">等效于</span><span class="sxs-lookup"><span data-stu-id="ec9e0-105">is equivalent to</span></span>  

```csharp
x = x + y
```  

<span data-ttu-id="ec9e0-106">不同的是 `x` 只计算一次。</span><span class="sxs-lookup"><span data-stu-id="ec9e0-106">except that `x` is only evaluated once.</span></span>
  
<span data-ttu-id="ec9e0-107">对于数字类型，[加法运算符](addition-operator.md) `+`计算其操作数的和。</span><span class="sxs-lookup"><span data-stu-id="ec9e0-107">For numeric types, the [addition operator](addition-operator.md) `+` computes the sum of its operands.</span></span> <span data-ttu-id="ec9e0-108">如果其中的一个操作数是 [string](../keywords/string.md) 类型或两个操作数都是该类型，它会将操作数的字符串表示形式串联在一起。</span><span class="sxs-lookup"><span data-stu-id="ec9e0-108">If one or both operands is of type [string](../keywords/string.md), it concatenates the string representations of its operands.</span></span> <span data-ttu-id="ec9e0-109">对于委托类型，`+` 运算符返回一个新的委托实例，该实例是其操作数的组合。</span><span class="sxs-lookup"><span data-stu-id="ec9e0-109">For delegate types, the `+` operator returns a new delegate instance that is combination of its operands.</span></span>

<span data-ttu-id="ec9e0-110">如果用户定义类型[重载](../keywords/operator.md)[加法运算符](addition-operator.md) `+`，则加法赋值运算符 `+=` 为隐式重载。</span><span class="sxs-lookup"><span data-stu-id="ec9e0-110">If a user-defined type [overloads](../keywords/operator.md) the [addition operator](addition-operator.md) `+`, the addition assignment operator `+=` is implicitly overloaded.</span></span>

<span data-ttu-id="ec9e0-111">在订阅[事件](../keywords/event.md)时，还可以使用 `+=` 运算符来指定事件处理程序方法。</span><span class="sxs-lookup"><span data-stu-id="ec9e0-111">You also use the `+=` operator to specify an event handler method when you subscribe to an [event](../keywords/event.md).</span></span> <span data-ttu-id="ec9e0-112">有关详细信息，请参阅[如何：订阅和取消订阅事件](../../programming-guide/events/how-to-subscribe-to-and-unsubscribe-from-events.md)。</span><span class="sxs-lookup"><span data-stu-id="ec9e0-112">For more information, see [How to: Subscribe to and Unsubscribe from Events](../../programming-guide/events/how-to-subscribe-to-and-unsubscribe-from-events.md).</span></span>

<span data-ttu-id="ec9e0-113">下面的示例演示 `+=` 运算符的用法：</span><span class="sxs-lookup"><span data-stu-id="ec9e0-113">The following example demonstrates the usage of the `+=` operator:</span></span>

[!code-csharp-interactive[+= examples](~/samples/snippets/csharp/language-reference/operators/AdditionExamples.cs#AddAndAssign)]
  
## <a name="see-also"></a><span data-ttu-id="ec9e0-114">请参阅</span><span class="sxs-lookup"><span data-stu-id="ec9e0-114">See also</span></span>

- [<span data-ttu-id="ec9e0-115">C# 参考</span><span class="sxs-lookup"><span data-stu-id="ec9e0-115">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="ec9e0-116">C# 编程指南</span><span class="sxs-lookup"><span data-stu-id="ec9e0-116">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="ec9e0-117">C# 运算符</span><span class="sxs-lookup"><span data-stu-id="ec9e0-117">C# Operators</span></span>](index.md)
- [<span data-ttu-id="ec9e0-118">事件</span><span class="sxs-lookup"><span data-stu-id="ec9e0-118">Events</span></span>](../../programming-guide/events/index.md)
- [<span data-ttu-id="ec9e0-119">委托</span><span class="sxs-lookup"><span data-stu-id="ec9e0-119">Delegates</span></span>](../../programming-guide/delegates/index.md)
