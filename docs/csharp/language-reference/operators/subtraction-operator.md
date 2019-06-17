---
title: '- 和 -= 运算符 - C# 参考'
ms.custom: seodec18
ms.date: 05/27/2019
f1_keywords:
- -_CSharpKeyword
- -=_CSharpKeyword
helpviewer_keywords:
- subtraction operator [C#]
- delegate removal [C#]
- '- operator [C#]'
- subtraction assignment operator [C#]
- event unsubscription [C#]
- -= operator [C#]
ms.assetid: 4de7a4fa-c69d-48e6-aff1-3130af970b2d
ms.openlocfilehash: aae10f8b03a16e55f0b26981f17585c8790e00c1
ms.sourcegitcommit: 5ae6affa0b171be3bb5f4729fb68ea4fe799f959
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/10/2019
ms.locfileid: "66816081"
---
# <a name="--and---operators-c-reference"></a><span data-ttu-id="b9eed-102">- 和 -= 运算符（C# 参考）</span><span class="sxs-lookup"><span data-stu-id="b9eed-102">- and -= operators (C# Reference)</span></span>

<span data-ttu-id="b9eed-103">`-` 运算符受内置数字类型和[委托](../keywords/delegate.md)类型的支持。</span><span class="sxs-lookup"><span data-stu-id="b9eed-103">The `-` operator is supported by the built-in numeric types and [delegate](../keywords/delegate.md) types.</span></span>

<span data-ttu-id="b9eed-104">有关算术 `-` 运算符的信息，请参阅[一元加和减运算符](arithmetic-operators.md#unary-plus-and-minus-operators)和[算术运算符](arithmetic-operators.md)文章的[减法运算符 -](arithmetic-operators.md#subtraction-operator--) 部分。</span><span class="sxs-lookup"><span data-stu-id="b9eed-104">For information about the arithmetic `-` operator, see the [Unary plus and minus operators](arithmetic-operators.md#unary-plus-and-minus-operators) and [Subtraction operator -](arithmetic-operators.md#subtraction-operator--) sections of the [Arithmetic operators](arithmetic-operators.md) article.</span></span>

## <a name="delegate-removal"></a><span data-ttu-id="b9eed-105">委托删除</span><span class="sxs-lookup"><span data-stu-id="b9eed-105">Delegate removal</span></span>

<span data-ttu-id="b9eed-106">对于[委托](../keywords/delegate.md)类型相同的操作数，`-` 运算符返回如下计算的委托实例：</span><span class="sxs-lookup"><span data-stu-id="b9eed-106">For operands of the same [delegate](../keywords/delegate.md) type, the `-` operator returns a delegate instance that is calculated as follows:</span></span>

- <span data-ttu-id="b9eed-107">如果两个操作数都为非空，并且第二个操作数的调用列表是第一个操作数调用列表的正确连续子列表，则该操作的结果是通过从第一个操作数的调用列表中删除第二个操作数的条目而获得的新调用列表。</span><span class="sxs-lookup"><span data-stu-id="b9eed-107">If both operands are non-null and the invocation list of the second operand is a proper contiguous sublist of the invocation list of the first operand, the result of the operation is a new invocation list that is obtained by removing the second operand's entries from the invocation list of the first operand.</span></span> <span data-ttu-id="b9eed-108">如果第二个操作数的列表与第一个操作数列表中的多个连续子列表匹配，则仅删除最右侧的匹配子列表。</span><span class="sxs-lookup"><span data-stu-id="b9eed-108">If the second operand's list matches multiple contiguous sublists in the first operand's list, only the right-most matching sublist is removed.</span></span> <span data-ttu-id="b9eed-109">如果删除行为导致出现空列表，则结果为 `null`。</span><span class="sxs-lookup"><span data-stu-id="b9eed-109">If removal results in an empty list, the result is `null`.</span></span>

  [!code-csharp-interactive[delegate removal](~/samples/csharp/language-reference/operators/SubtractionOperator.cs#DelegateRemoval)]

- <span data-ttu-id="b9eed-110">如果第二个操作数的调用列表不是第一个操作数调用列表的正确连续子列表，则该操作的结果是第一个操作数。</span><span class="sxs-lookup"><span data-stu-id="b9eed-110">If the invocation list of the second operand is not a proper contiguous sublist of the invocation list of the first operand, the result of the operation is the first operand.</span></span> <span data-ttu-id="b9eed-111">例如，删除不属于多播委托的委托不会执行任何操作，从而导致不变的多播委托。</span><span class="sxs-lookup"><span data-stu-id="b9eed-111">For example, removing a delegate that is not part of the multicast delegate does nothing and results in the unchanged multicast delegate.</span></span>

  [!code-csharp-interactive[delegate removal with no effect](~/samples/csharp/language-reference/operators/SubtractionOperator.cs#DelegateRemovalNoChange)]

  <span data-ttu-id="b9eed-112">前面的示例还演示了在删除委托期间对委托实例进行比较。</span><span class="sxs-lookup"><span data-stu-id="b9eed-112">The preceding example also demonstrates that during delegate removal delegate instances are compared.</span></span> <span data-ttu-id="b9eed-113">例如，通过计算相同的 [Lambda 表达式](../../programming-guide/statements-expressions-operators/lambda-expressions.md)生成的委托不相等。</span><span class="sxs-lookup"><span data-stu-id="b9eed-113">For example, delegates that are produced from evaluation of identical [lambda expressions](../../programming-guide/statements-expressions-operators/lambda-expressions.md) are not equal.</span></span> <span data-ttu-id="b9eed-114">有关委托相等性的详细信息，请参阅 [C# 语言规范](../language-specification/index.md)的[委托相等运算符](~/_csharplang/spec/expressions.md#delegate-equality-operators)部分。</span><span class="sxs-lookup"><span data-stu-id="b9eed-114">For more information about delegate equality, see the [Delegate equality operators](~/_csharplang/spec/expressions.md#delegate-equality-operators) section of the [C# language specification](../language-specification/index.md).</span></span>

- <span data-ttu-id="b9eed-115">如果第一个操作数为 `null`，则操作结果为 `null`。</span><span class="sxs-lookup"><span data-stu-id="b9eed-115">If the first operand is `null`, the result of the operation is `null`.</span></span> <span data-ttu-id="b9eed-116">如果第二个操作数为 `null`，则操作的结果是第一个操作数。</span><span class="sxs-lookup"><span data-stu-id="b9eed-116">If the second operand is `null`, the result of the operation is the first operand.</span></span>

  [!code-csharp-interactive[delegate removal and null](~/samples/csharp/language-reference/operators/SubtractionOperator.cs#DelegateRemovalAndNull)]

<span data-ttu-id="b9eed-117">若要合并委托，请使用 [`+` 运算符](addition-operator.md#delegate-combination)。</span><span class="sxs-lookup"><span data-stu-id="b9eed-117">To combine delegates, use the [`+` operator](addition-operator.md#delegate-combination).</span></span>

<span data-ttu-id="b9eed-118">有关委托类型的详细信息，请参阅[委托](../../programming-guide/delegates/index.md)。</span><span class="sxs-lookup"><span data-stu-id="b9eed-118">For more information about delegate types, see [Delegates](../../programming-guide/delegates/index.md).</span></span>

## <a name="subtraction-assignment-operator--"></a><span data-ttu-id="b9eed-119">减法赋值运算符 -=</span><span class="sxs-lookup"><span data-stu-id="b9eed-119">Subtraction assignment operator -=</span></span>

<span data-ttu-id="b9eed-120">使用 `-=` 运算符的表达式，例如</span><span class="sxs-lookup"><span data-stu-id="b9eed-120">An expression using the `-=` operator, such as</span></span>

```csharp
x -= y
```

<span data-ttu-id="b9eed-121">等效于</span><span class="sxs-lookup"><span data-stu-id="b9eed-121">is equivalent to</span></span>

```csharp
x = x - y
```

<span data-ttu-id="b9eed-122">不同的是 `x` 只计算一次。</span><span class="sxs-lookup"><span data-stu-id="b9eed-122">except that `x` is only evaluated once.</span></span>
  
<span data-ttu-id="b9eed-123">下面的示例演示 `-=` 运算符的用法：</span><span class="sxs-lookup"><span data-stu-id="b9eed-123">The following example demonstrates the usage of the `-=` operator:</span></span>

[!code-csharp-interactive[-= examples](~/samples/csharp/language-reference/operators/SubtractionOperator.cs#SubtractAndAssign)]

<span data-ttu-id="b9eed-124">还可以使用 `-=` 运算符指定在取消订阅[事件](../keywords/event.md)时要删除的事件处理程序方法。</span><span class="sxs-lookup"><span data-stu-id="b9eed-124">You also use the `-=` operator to specify an event handler method to remove when you unsubscribe from an [event](../keywords/event.md).</span></span> <span data-ttu-id="b9eed-125">有关详细信息，请参阅[如何：订阅和取消订阅事件](../../programming-guide/events/how-to-subscribe-to-and-unsubscribe-from-events.md)。</span><span class="sxs-lookup"><span data-stu-id="b9eed-125">For more information, see [How to: subscribe to and unsubscribe from events](../../programming-guide/events/how-to-subscribe-to-and-unsubscribe-from-events.md).</span></span>

## <a name="operator-overloadability"></a><span data-ttu-id="b9eed-126">运算符可重载性</span><span class="sxs-lookup"><span data-stu-id="b9eed-126">Operator overloadability</span></span>

<span data-ttu-id="b9eed-127">用户定义的类型可以[重载](../keywords/operator.md) `-` 运算符。</span><span class="sxs-lookup"><span data-stu-id="b9eed-127">A user-defined type can [overload](../keywords/operator.md) the `-` operator.</span></span> <span data-ttu-id="b9eed-128">重载二元 `-` 运算符后，也会隐式重载 `-=` 运算符。</span><span class="sxs-lookup"><span data-stu-id="b9eed-128">When a binary `-` operator is overloaded, the `-=` operator is also implicitly overloaded.</span></span> <span data-ttu-id="b9eed-129">用户定义类型不能显式重载 `-=` 运算符。</span><span class="sxs-lookup"><span data-stu-id="b9eed-129">A user-defined type cannot explicitly overload the `-=` operator.</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="b9eed-130">C# 语言规范</span><span class="sxs-lookup"><span data-stu-id="b9eed-130">C# language specification</span></span>

<span data-ttu-id="b9eed-131">有关详细信息，请参阅 [C# 语言规范](~/_csharplang/spec/introduction.md)的[一元减运算符](~/_csharplang/spec/expressions.md#unary-minus-operator)和[减法运算符](~/_csharplang/spec/expressions.md#subtraction-operator)部分。</span><span class="sxs-lookup"><span data-stu-id="b9eed-131">For more information, see the [Unary minus operator](~/_csharplang/spec/expressions.md#unary-minus-operator) and [Subtraction operator](~/_csharplang/spec/expressions.md#subtraction-operator) sections of the [C# language specification](~/_csharplang/spec/introduction.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="b9eed-132">请参阅</span><span class="sxs-lookup"><span data-stu-id="b9eed-132">See also</span></span>

- [<span data-ttu-id="b9eed-133">C# 参考</span><span class="sxs-lookup"><span data-stu-id="b9eed-133">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="b9eed-134">C# 编程指南</span><span class="sxs-lookup"><span data-stu-id="b9eed-134">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="b9eed-135">C# 运算符</span><span class="sxs-lookup"><span data-stu-id="b9eed-135">C# Operators</span></span>](index.md)
- [<span data-ttu-id="b9eed-136">委托</span><span class="sxs-lookup"><span data-stu-id="b9eed-136">Delegates</span></span>](../../programming-guide/delegates/index.md)
- [<span data-ttu-id="b9eed-137">事件</span><span class="sxs-lookup"><span data-stu-id="b9eed-137">Events</span></span>](../../programming-guide/events/index.md)
- [<span data-ttu-id="b9eed-138">Checked 和 unchecked</span><span class="sxs-lookup"><span data-stu-id="b9eed-138">Checked and unchecked</span></span>](../keywords/checked-and-unchecked.md)
- [<span data-ttu-id="b9eed-139">算术运算符</span><span class="sxs-lookup"><span data-stu-id="b9eed-139">Arithmetic operators</span></span>](arithmetic-operators.md)
- [<span data-ttu-id="b9eed-140">+ 和 += 运算符</span><span class="sxs-lookup"><span data-stu-id="b9eed-140">+ and += operators</span></span>](addition-operator.md)
