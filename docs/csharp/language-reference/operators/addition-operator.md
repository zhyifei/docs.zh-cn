---
title: + 和 += 运算符 - C# 参考
ms.custom: seodec18
ms.date: 05/24/2019
f1_keywords:
- +_CSharpKeyword
- +=_CSharpKeyword
helpviewer_keywords:
- addition operator [C#]
- concatenation operator [C#]
- delegate combination [C#]
- + operator [C#]
- addition assignment operator [C#]
- event subscription [C#]
- += operator [C#]
ms.assetid: 93e56486-bb42-43c1-bd43-60af11e64e67
ms.openlocfilehash: d03743bad47c60925462d027d18445047ebc0fc9
ms.sourcegitcommit: 621a5f6df00152006160987395b93b5b55f7ffcd
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/29/2019
ms.locfileid: "66300118"
---
# <a name="-and--operators-c-reference"></a><span data-ttu-id="3c5bb-102">+ 和 += 运算符（C# 参考）</span><span class="sxs-lookup"><span data-stu-id="3c5bb-102">+ and += operators (C# Reference)</span></span>

<span data-ttu-id="3c5bb-103">`+` 运算符受内置数字类型、[字符串](../keywords/string.md)类型和[委托](../keywords/delegate.md)类型的支持。</span><span class="sxs-lookup"><span data-stu-id="3c5bb-103">The `+` operator is supported by the built-in numeric types, [string](../keywords/string.md) type, and [delegate](../keywords/delegate.md) types.</span></span>

<span data-ttu-id="3c5bb-104">有关算术 `+` 运算符的信息，请参阅[一元加和减运算符](arithmetic-operators.md#unary-plus-and-minus-operators)和[算术运算符](arithmetic-operators.md)文章的[加法运算符 +](arithmetic-operators.md#addition-operator-) 部分。</span><span class="sxs-lookup"><span data-stu-id="3c5bb-104">For information about the arithmetic `+` operator, see the [Unary plus and minus operators](arithmetic-operators.md#unary-plus-and-minus-operators) and [Addition operator +](arithmetic-operators.md#addition-operator-) sections of the [Arithmetic operators](arithmetic-operators.md) article.</span></span>

## <a name="string-concatenation"></a><span data-ttu-id="3c5bb-105">字符串串联</span><span class="sxs-lookup"><span data-stu-id="3c5bb-105">String concatenation</span></span>

<span data-ttu-id="3c5bb-106">当其中的一个操作数是[字符串](../keywords/string.md)类型或两个操作数都是字符串类型时，`+` 运算符将其操作数的字符串表示形式串联在一起：</span><span class="sxs-lookup"><span data-stu-id="3c5bb-106">When one or both operands are of type [string](../keywords/string.md), the `+` operator concatenates the string representations of its operands:</span></span>

[!code-csharp-interactive[string concatenation](~/samples/snippets/csharp/language-reference/operators/AdditionExamples.cs#AddStrings)]

<span data-ttu-id="3c5bb-107">从 C# 6 开始，[字符串内插](../tokens/interpolated.md)提供了格式化字符串的更便捷方式：</span><span class="sxs-lookup"><span data-stu-id="3c5bb-107">Starting with C# 6, [string interpolation](../tokens/interpolated.md) provides a more convenient way to format strings:</span></span>

[!code-csharp-interactive[string interpolation](~/samples/snippets/csharp/language-reference/operators/AdditionExamples.cs#UseStringInterpolation)]

## <a name="delegate-combination"></a><span data-ttu-id="3c5bb-108">委托组合</span><span class="sxs-lookup"><span data-stu-id="3c5bb-108">Delegate combination</span></span>

<span data-ttu-id="3c5bb-109">对于[委托](../keywords/delegate.md)类型相同的操作数，`+` 运算符在调用时返回新的委托实例，调用第一个操作数，然后调用第二个操作数。</span><span class="sxs-lookup"><span data-stu-id="3c5bb-109">For operands of the same [delegate](../keywords/delegate.md) type, the `+` operator returns a new delegate instance that, when invoked, invokes the first operand and then invokes the second operand.</span></span> <span data-ttu-id="3c5bb-110">如果任何操作数均为 `null`，则 `+` 运算符将返回另一个操作数（也可能是 `null`）的值。</span><span class="sxs-lookup"><span data-stu-id="3c5bb-110">If any of the operands is `null`, the `+` operator returns the value of another operand (which also might be `null`).</span></span> <span data-ttu-id="3c5bb-111">下面的示例演示如何组合使用委托和 `+` 运算符：</span><span class="sxs-lookup"><span data-stu-id="3c5bb-111">The following example shows how delegates can be combined with the `+` operator:</span></span>

[!code-csharp-interactive[delegate combination](~/samples/snippets/csharp/language-reference/operators/AdditionExamples.cs#AddDelegates)]

<span data-ttu-id="3c5bb-112">有关委托类型的详细信息，请参阅[委托](../../programming-guide/delegates/index.md)。</span><span class="sxs-lookup"><span data-stu-id="3c5bb-112">For more information about delegate types, see [Delegates](../../programming-guide/delegates/index.md).</span></span>

## <a name="addition-assignment-operator-"></a><span data-ttu-id="3c5bb-113">加法赋值运算符 +=</span><span class="sxs-lookup"><span data-stu-id="3c5bb-113">Addition assignment operator +=</span></span>

<span data-ttu-id="3c5bb-114">使用 `+=` 运算符的表达式，例如</span><span class="sxs-lookup"><span data-stu-id="3c5bb-114">An expression using the `+=` operator, such as</span></span>

```csharp
x += y
```

<span data-ttu-id="3c5bb-115">等效于</span><span class="sxs-lookup"><span data-stu-id="3c5bb-115">is equivalent to</span></span>

```csharp
x = x + y
```

<span data-ttu-id="3c5bb-116">不同的是 `x` 只计算一次。</span><span class="sxs-lookup"><span data-stu-id="3c5bb-116">except that `x` is only evaluated once.</span></span>
  
<span data-ttu-id="3c5bb-117">下面的示例演示 `+=` 运算符的用法：</span><span class="sxs-lookup"><span data-stu-id="3c5bb-117">The following example demonstrates the usage of the `+=` operator:</span></span>

[!code-csharp-interactive[+= examples](~/samples/snippets/csharp/language-reference/operators/AdditionExamples.cs#AddAndAssign)]

<span data-ttu-id="3c5bb-118">在订阅[事件](../keywords/event.md)时，还可以使用 `+=` 运算符来指定事件处理程序方法。</span><span class="sxs-lookup"><span data-stu-id="3c5bb-118">You also use the `+=` operator to specify an event handler method when you subscribe to an [event](../keywords/event.md).</span></span> <span data-ttu-id="3c5bb-119">有关详细信息，请参阅[如何：订阅和取消订阅事件](../../programming-guide/events/how-to-subscribe-to-and-unsubscribe-from-events.md)。</span><span class="sxs-lookup"><span data-stu-id="3c5bb-119">For more information, see [How to: subscribe to and unsubscribe from events](../../programming-guide/events/how-to-subscribe-to-and-unsubscribe-from-events.md).</span></span>

## <a name="operator-overloadability"></a><span data-ttu-id="3c5bb-120">运算符可重载性</span><span class="sxs-lookup"><span data-stu-id="3c5bb-120">Operator overloadability</span></span>

<span data-ttu-id="3c5bb-121">用户定义的类型可以[重载](../keywords/operator.md) `+` 运算符。</span><span class="sxs-lookup"><span data-stu-id="3c5bb-121">A user-defined type can [overload](../keywords/operator.md) the `+` operator.</span></span> <span data-ttu-id="3c5bb-122">重载二元 `+` 运算符后，也会隐式重载 `+=` 运算符。</span><span class="sxs-lookup"><span data-stu-id="3c5bb-122">When a binary `+` operator is overloaded, the `+=` operator is also implicitly overloaded.</span></span> <span data-ttu-id="3c5bb-123">用户定义类型不能显式重载 `+=` 运算符。</span><span class="sxs-lookup"><span data-stu-id="3c5bb-123">A user-defined type cannot explicitly overload the `+=` operator.</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="3c5bb-124">C# 语言规范</span><span class="sxs-lookup"><span data-stu-id="3c5bb-124">C# language specification</span></span>

<span data-ttu-id="3c5bb-125">有关详细信息，请参阅[C# 语言规范](../language-specification/index.md)的[一元加运算符](~/_csharplang/spec/expressions.md#unary-plus-operator)和[加法运算符](~/_csharplang/spec/expressions.md#addition-operator)部分。</span><span class="sxs-lookup"><span data-stu-id="3c5bb-125">For more information, see the [Unary plus operator](~/_csharplang/spec/expressions.md#unary-plus-operator) and [Addition operator](~/_csharplang/spec/expressions.md#addition-operator) sections of the [C# language specification](../language-specification/index.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="3c5bb-126">请参阅</span><span class="sxs-lookup"><span data-stu-id="3c5bb-126">See also</span></span>

- [<span data-ttu-id="3c5bb-127">C# 参考</span><span class="sxs-lookup"><span data-stu-id="3c5bb-127">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="3c5bb-128">C# 编程指南</span><span class="sxs-lookup"><span data-stu-id="3c5bb-128">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="3c5bb-129">C# 运算符</span><span class="sxs-lookup"><span data-stu-id="3c5bb-129">C# Operators</span></span>](index.md)
- [<span data-ttu-id="3c5bb-130">字符串内插</span><span class="sxs-lookup"><span data-stu-id="3c5bb-130">String interpolation</span></span>](../tokens/interpolated.md)
- [<span data-ttu-id="3c5bb-131">如何：连接多个字符串</span><span class="sxs-lookup"><span data-stu-id="3c5bb-131">How to: concatenate multiple strings</span></span>](../../how-to/concatenate-multiple-strings.md)
- [<span data-ttu-id="3c5bb-132">委托</span><span class="sxs-lookup"><span data-stu-id="3c5bb-132">Delegates</span></span>](../../programming-guide/delegates/index.md)
- [<span data-ttu-id="3c5bb-133">事件</span><span class="sxs-lookup"><span data-stu-id="3c5bb-133">Events</span></span>](../../programming-guide/events/index.md)
- [<span data-ttu-id="3c5bb-134">Checked 和 unchecked</span><span class="sxs-lookup"><span data-stu-id="3c5bb-134">Checked and unchecked</span></span>](../keywords/checked-and-unchecked.md)
- [<span data-ttu-id="3c5bb-135">算术运算符</span><span class="sxs-lookup"><span data-stu-id="3c5bb-135">Arithmetic operators</span></span>](arithmetic-operators.md)
- [<span data-ttu-id="3c5bb-136">- 和 -= 运算符</span><span class="sxs-lookup"><span data-stu-id="3c5bb-136">- and -= operators</span></span>](subtraction-operator.md)
