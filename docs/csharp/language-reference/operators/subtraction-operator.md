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
ms.openlocfilehash: 9f43a863de69122e251204668af2ea989fcc993c
ms.sourcegitcommit: 621a5f6df00152006160987395b93b5b55f7ffcd
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/29/2019
ms.locfileid: "66300087"
---
# <a name="--and---operators-c-reference"></a><span data-ttu-id="ccc92-102">- 和 -= 运算符（C# 参考）</span><span class="sxs-lookup"><span data-stu-id="ccc92-102">- and -= operators (C# Reference)</span></span>

<span data-ttu-id="ccc92-103">`-` 运算符受内置数字类型和[委托](../keywords/delegate.md)类型的支持。</span><span class="sxs-lookup"><span data-stu-id="ccc92-103">The `-` operator is supported by the built-in numeric types and [delegate](../keywords/delegate.md) types.</span></span>

<span data-ttu-id="ccc92-104">有关算术 `-` 运算符的信息，请参阅[一元加和减运算符](arithmetic-operators.md#unary-plus-and-minus-operators)和[算术运算符](arithmetic-operators.md)文章的[减法运算符 -](arithmetic-operators.md#subtraction-operator--) 部分。</span><span class="sxs-lookup"><span data-stu-id="ccc92-104">For information about the arithmetic `-` operator, see the [Unary plus and minus operators](arithmetic-operators.md#unary-plus-and-minus-operators) and [Subtraction operator -](arithmetic-operators.md#subtraction-operator--) sections of the [Arithmetic operators](arithmetic-operators.md) article.</span></span>

## <a name="delegate-removal"></a><span data-ttu-id="ccc92-105">委托删除</span><span class="sxs-lookup"><span data-stu-id="ccc92-105">Delegate removal</span></span>

<span data-ttu-id="ccc92-106">对于[委托](../keywords/delegate.md)类型相同的操作数，`-` 运算符返回如下计算的委托实例：</span><span class="sxs-lookup"><span data-stu-id="ccc92-106">For operands of the same [delegate](../keywords/delegate.md) type, the `-` operator returns a delegate instance that is calculated as follows:</span></span>

- <span data-ttu-id="ccc92-107">如果两个操作数都为非空，并且第二个操作数的调用列表是第一个操作数调用列表的正确连续子列表，则该操作的结果是通过从第一个操作数的调用列表中删除第二个操作数的条目而获得的新调用列表。</span><span class="sxs-lookup"><span data-stu-id="ccc92-107">If both operands are non-null and the invocation list of the second operand is a proper contiguous sublist of the invocation list of the first operand, the result of the operation is a new invocation list that is obtained by removing the second operand's entries from the invocation list of the first operand.</span></span> <span data-ttu-id="ccc92-108">如果第二个操作数的列表与第一个操作数列表中的多个连续子列表匹配，则仅删除最右侧的匹配子列表。</span><span class="sxs-lookup"><span data-stu-id="ccc92-108">If the second operand's list matches multiple contiguous sublists in the first operand's list, only the right-most matching sublist is removed.</span></span> <span data-ttu-id="ccc92-109">如果删除行为导致出现空列表，则结果为 `null`。</span><span class="sxs-lookup"><span data-stu-id="ccc92-109">If removal results in an empty list, the result is `null`.</span></span>
- <span data-ttu-id="ccc92-110">如果第二个操作数的调用列表不是第一个操作数调用列表的正确连续子列表，则该操作的结果是第一个操作数。</span><span class="sxs-lookup"><span data-stu-id="ccc92-110">If the invocation list of the second operand is not a proper contiguous sublist of the invocation list of the first operand, the result of the operation is the first operand.</span></span>
- <span data-ttu-id="ccc92-111">如果第一个操作数为 `null`，则操作结果为 `null`。</span><span class="sxs-lookup"><span data-stu-id="ccc92-111">If the first operand is `null`, the result of the operation is `null`.</span></span> <span data-ttu-id="ccc92-112">如果第二个操作数为 `null`，则操作的结果是第一个操作数。</span><span class="sxs-lookup"><span data-stu-id="ccc92-112">If the second operand is `null`, the result of the operation is the first operand.</span></span>

<span data-ttu-id="ccc92-113">以下示例显示了 `-` 操作如何执行委托删除：</span><span class="sxs-lookup"><span data-stu-id="ccc92-113">The following example shows how the `-` operation performs delegate removal:</span></span>

[!code-csharp-interactive[delegate removal](~/samples/csharp/language-reference/operators/SubtractionOperator.cs#DelegateRemoval)]

## <a name="subtraction-assignment-operator--"></a><span data-ttu-id="ccc92-114">减法赋值运算符 -=</span><span class="sxs-lookup"><span data-stu-id="ccc92-114">Subtraction assignment operator -=</span></span>

<span data-ttu-id="ccc92-115">使用 `-=` 运算符的表达式，例如</span><span class="sxs-lookup"><span data-stu-id="ccc92-115">An expression using the `-=` operator, such as</span></span>

```csharp
x -= y
```

<span data-ttu-id="ccc92-116">等效于</span><span class="sxs-lookup"><span data-stu-id="ccc92-116">is equivalent to</span></span>

```csharp
x = x - y
```

<span data-ttu-id="ccc92-117">不同的是 `x` 只计算一次。</span><span class="sxs-lookup"><span data-stu-id="ccc92-117">except that `x` is only evaluated once.</span></span>
  
<span data-ttu-id="ccc92-118">下面的示例演示 `-=` 运算符的用法：</span><span class="sxs-lookup"><span data-stu-id="ccc92-118">The following example demonstrates the usage of the `-=` operator:</span></span>

[!code-csharp-interactive[-= examples](~/samples/csharp/language-reference/operators/SubtractionOperator.cs#SubtractAndAssign)]

<span data-ttu-id="ccc92-119">还可以使用 `-=` 运算符指定在取消订阅[事件](../keywords/event.md)时要删除的事件处理程序方法。</span><span class="sxs-lookup"><span data-stu-id="ccc92-119">You also use the `-=` operator to specify an event handler method to remove when you unsubscribe from an [event](../keywords/event.md).</span></span> <span data-ttu-id="ccc92-120">有关详细信息，请参阅[如何：订阅和取消订阅事件](../../programming-guide/events/how-to-subscribe-to-and-unsubscribe-from-events.md)。</span><span class="sxs-lookup"><span data-stu-id="ccc92-120">For more information, see [How to: subscribe to and unsubscribe from events](../../programming-guide/events/how-to-subscribe-to-and-unsubscribe-from-events.md).</span></span>

## <a name="operator-overloadability"></a><span data-ttu-id="ccc92-121">运算符可重载性</span><span class="sxs-lookup"><span data-stu-id="ccc92-121">Operator overloadability</span></span>

<span data-ttu-id="ccc92-122">用户定义的类型可以[重载](../keywords/operator.md) `-` 运算符。</span><span class="sxs-lookup"><span data-stu-id="ccc92-122">A user-defined type can [overload](../keywords/operator.md) the `-` operator.</span></span> <span data-ttu-id="ccc92-123">重载二元 `-` 运算符后，也会隐式重载 `-=` 运算符。</span><span class="sxs-lookup"><span data-stu-id="ccc92-123">When a binary `-` operator is overloaded, the `-=` operator is also implicitly overloaded.</span></span> <span data-ttu-id="ccc92-124">用户定义类型不能显式重载 `-=` 运算符。</span><span class="sxs-lookup"><span data-stu-id="ccc92-124">A user-defined type cannot explicitly overload the `-=` operator.</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="ccc92-125">C# 语言规范</span><span class="sxs-lookup"><span data-stu-id="ccc92-125">C# language specification</span></span>

<span data-ttu-id="ccc92-126">有关详细信息，请参阅 [C# 语言规范](../language-specification/index.md)的[一元减运算符](~/_csharplang/spec/expressions.md#unary-minus-operator)和[减法运算符](~/_csharplang/spec/expressions.md#subtraction-operator)部分。</span><span class="sxs-lookup"><span data-stu-id="ccc92-126">For more information, see the [Unary minus operator](~/_csharplang/spec/expressions.md#unary-minus-operator) and [Subtraction operator](~/_csharplang/spec/expressions.md#subtraction-operator) sections of the [C# language specification](../language-specification/index.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="ccc92-127">请参阅</span><span class="sxs-lookup"><span data-stu-id="ccc92-127">See also</span></span>

- [<span data-ttu-id="ccc92-128">C# 参考</span><span class="sxs-lookup"><span data-stu-id="ccc92-128">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="ccc92-129">C# 编程指南</span><span class="sxs-lookup"><span data-stu-id="ccc92-129">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="ccc92-130">C# 运算符</span><span class="sxs-lookup"><span data-stu-id="ccc92-130">C# Operators</span></span>](index.md)
- [<span data-ttu-id="ccc92-131">委托</span><span class="sxs-lookup"><span data-stu-id="ccc92-131">Delegates</span></span>](../../programming-guide/delegates/index.md)
- [<span data-ttu-id="ccc92-132">事件</span><span class="sxs-lookup"><span data-stu-id="ccc92-132">Events</span></span>](../../programming-guide/events/index.md)
- [<span data-ttu-id="ccc92-133">Checked 和 unchecked</span><span class="sxs-lookup"><span data-stu-id="ccc92-133">Checked and unchecked</span></span>](../keywords/checked-and-unchecked.md)
- [<span data-ttu-id="ccc92-134">算术运算符</span><span class="sxs-lookup"><span data-stu-id="ccc92-134">Arithmetic operators</span></span>](arithmetic-operators.md)
- [<span data-ttu-id="ccc92-135">+ 和 += 运算符</span><span class="sxs-lookup"><span data-stu-id="ccc92-135">+ and += operators</span></span>](addition-operator.md)
