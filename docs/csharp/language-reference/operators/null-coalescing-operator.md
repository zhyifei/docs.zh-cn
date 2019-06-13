---
title: ?? 运算符 - C# 参考
ms.custom: seodec18
ms.date: 06/07/2019
f1_keywords:
- ??_CSharpKeyword
helpviewer_keywords:
- null-coalescing operator [C#]
- ?? operator [C#]
ms.assetid: 088b1f0d-c1af-4fe1-b4b8-196fd5ea9132
ms.openlocfilehash: 8ca97261b348b7813ab179abbc1f2c5f535966a1
ms.sourcegitcommit: 5ae6affa0b171be3bb5f4729fb68ea4fe799f959
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/10/2019
ms.locfileid: "66816006"
---
# <a name="-operator-c-reference"></a><span data-ttu-id="bb260-103">??</span><span class="sxs-lookup"><span data-stu-id="bb260-103">??</span></span> <span data-ttu-id="bb260-104">运算符（C# 参考）</span><span class="sxs-lookup"><span data-stu-id="bb260-104">operator (C# Reference)</span></span>

<span data-ttu-id="bb260-105">Null 合并运算符`??`返回其左操作数的值，如果不是`null`; 否则为它右操作数的计算结果并返回其结果。</span><span class="sxs-lookup"><span data-stu-id="bb260-105">The null-coalescing operator `??` returns the value of its left-hand operand if it isn't `null`; otherwise, it evaluates the right-hand operand and returns its result.</span></span> <span data-ttu-id="bb260-106">`??`运算符不会评估其右操作数，如果左操作数的计算结果为非 null。</span><span class="sxs-lookup"><span data-stu-id="bb260-106">The `??` operator doesn't evaluate its right-hand operand if the left-hand operand evaluates to non-null.</span></span>

<span data-ttu-id="bb260-107">Null 合并运算符是右结合运算符，即在窗体的表达式</span><span class="sxs-lookup"><span data-stu-id="bb260-107">The null-coalescing operator is right-associative, that is, an expression of the form</span></span>

```csharp
a ?? b ?? c
```

<span data-ttu-id="bb260-108">计算结果为</span><span class="sxs-lookup"><span data-stu-id="bb260-108">is evaluated as</span></span>

```csharp
a ?? (b ?? c)
```

<span data-ttu-id="bb260-109">`??`运算符可用于以下方案：</span><span class="sxs-lookup"><span data-stu-id="bb260-109">The `??` operator can be useful in the following scenarios:</span></span>

- <span data-ttu-id="bb260-110">在表达式中使用[null 条件运算符？。 和？]](member-access-operators.md#null-conditional-operators--and-)，可以使用 null 合并运算符以提供用于计算表达式与 null 条件操作的结果是替代表达式`null`:</span><span class="sxs-lookup"><span data-stu-id="bb260-110">In expressions with the [null-conditional operators ?. and ?[]](member-access-operators.md#null-conditional-operators--and-), you can use the null-coalescing operator to provide an alternative expression to evaluate in case the result of the expression with null-conditional operations is `null`:</span></span>

  [!code-csharp-interactive[with null-conditional](~/samples/csharp/language-reference/operators/NullCoalescingOperator.cs#WithNullConditional)]

- <span data-ttu-id="bb260-111">当您处理[可以为 null 的值类型](../../programming-guide/nullable-types/index.md)，需要提供基础值类型的值，请使用 null 合并运算符来指定要为 null 的类型值时提供的值`null`:</span><span class="sxs-lookup"><span data-stu-id="bb260-111">When you work with [nullable value types](../../programming-guide/nullable-types/index.md) and need to provide a value of an underlying value type, use the null-coalescing operator to specify the value to provide in case a nullable type value is `null`:</span></span>

  [!code-csharp-interactive[with nullable types](~/samples/csharp/language-reference/operators/NullCoalescingOperator.cs#WithNullableTypes)]

  <span data-ttu-id="bb260-112">使用<xref:System.Nullable%601.GetValueOrDefault?displayProperty=nameWithType>方法如果值为 null 的类型值时要使用`null`应基础值类型的默认值。</span><span class="sxs-lookup"><span data-stu-id="bb260-112">Use the <xref:System.Nullable%601.GetValueOrDefault?displayProperty=nameWithType> method if the value to be used when a nullable type value is `null` should be the default value of the underlying value type.</span></span>

- <span data-ttu-id="bb260-113">从C#7.0 中，可以使用[`throw`表达式](../keywords/throw.md#the-throw-expression)为要使参数检查代码更加简洁的 null 合并运算符的右侧操作数：</span><span class="sxs-lookup"><span data-stu-id="bb260-113">Starting with C# 7.0, you can use a [`throw` expression](../keywords/throw.md#the-throw-expression) as the right-hand operand of the null-coalescing operator to make the argument-checking code more concise:</span></span>

  [!code-csharp[with throw expression](~/samples/csharp/language-reference/operators/NullCoalescingOperator.cs#WithThrowExpression)]

  <span data-ttu-id="bb260-114">前面的示例还演示如何使用[expression-bodied 成员](../../programming-guide/statements-expressions-operators/expression-bodied-members.md)定义属性。</span><span class="sxs-lookup"><span data-stu-id="bb260-114">The preceding example also demonstrates how to use [expression-bodied members](../../programming-guide/statements-expressions-operators/expression-bodied-members.md) to define a property.</span></span>

## <a name="operator-overloadability"></a><span data-ttu-id="bb260-115">运算符可重载性</span><span class="sxs-lookup"><span data-stu-id="bb260-115">Operator overloadability</span></span>

<span data-ttu-id="bb260-116">Null 合并运算符无法进行重载。</span><span class="sxs-lookup"><span data-stu-id="bb260-116">The null-coalescing operator cannot be overloaded.</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="bb260-117">C# 语言规范</span><span class="sxs-lookup"><span data-stu-id="bb260-117">C# language specification</span></span>

<span data-ttu-id="bb260-118">有关详细信息，请参阅[null 合并运算符](~/_csharplang/spec/expressions.md#the-null-coalescing-operator)一部分[C#语言规范](~/_csharplang/spec/introduction.md)。</span><span class="sxs-lookup"><span data-stu-id="bb260-118">For more information, see [The null coalescing operator](~/_csharplang/spec/expressions.md#the-null-coalescing-operator) section of the [C# language specification](~/_csharplang/spec/introduction.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="bb260-119">请参阅</span><span class="sxs-lookup"><span data-stu-id="bb260-119">See also</span></span>

- [<span data-ttu-id="bb260-120">C# 参考</span><span class="sxs-lookup"><span data-stu-id="bb260-120">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="bb260-121">C# 编程指南</span><span class="sxs-lookup"><span data-stu-id="bb260-121">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="bb260-122">C# 运算符</span><span class="sxs-lookup"><span data-stu-id="bb260-122">C# operators</span></span>](index.md)
- <span data-ttu-id="bb260-123">[?. 和 ?[] 运算符](member-access-operators.md#null-conditional-operators--and-)</span><span class="sxs-lookup"><span data-stu-id="bb260-123">[?. and ?[] operators](member-access-operators.md#null-conditional-operators--and-)</span></span>
- [<span data-ttu-id="bb260-124">?: 运算符</span><span class="sxs-lookup"><span data-stu-id="bb260-124">?: operator</span></span>](conditional-operator.md)
