---
title: '|| 运算符（C# 参考）'
ms.date: 11/06/2018
f1_keywords:
- '||_CSharpKeyword'
helpviewer_keywords:
- logical OR operator [C#]
- conditional-OR operator (||) [C#]
- '|| operator [C#]'
ms.assetid: 7d442d8e-400d-421f-b4d2-034bf82bcbdc
ms.openlocfilehash: a391078372e4ec0a3882bed4515733adedffb547
ms.sourcegitcommit: b5cd9d5d3b75a5537fc9ad8a3f085f0bb1845ee0
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/07/2018
ms.locfileid: "42925535"
---
# <a name="-operator-c-reference"></a><span data-ttu-id="26bae-102">|| 运算符（C# 参考）</span><span class="sxs-lookup"><span data-stu-id="26bae-102">|| Operator (C# Reference)</span></span>

<span data-ttu-id="26bae-103">条件逻辑 OR 运算符 `||`（也称为“短路”逻辑 OR 运算符）计算其 [bool](../keywords/bool.md) 操作数的逻辑 OR。</span><span class="sxs-lookup"><span data-stu-id="26bae-103">The conditional logical OR operator `||`, also known as the "short-circuiting" logical OR operator, computes the logical OR of its [bool](../keywords/bool.md) operands.</span></span> <span data-ttu-id="26bae-104">如果 `x` 或 `y` 的计算结果为 `true`，则 `x || y` 的结果为 `true`。</span><span class="sxs-lookup"><span data-stu-id="26bae-104">The result of `x || y` is `true` if either `x` or `y` evaluates to `true`.</span></span> <span data-ttu-id="26bae-105">否则，结果为 `false`。</span><span class="sxs-lookup"><span data-stu-id="26bae-105">Otherwise, the result is `false`.</span></span> <span data-ttu-id="26bae-106">如果第一个操作数的计算结果为 `true`，则不会计算第二个操作数且运算结果为 `true`。</span><span class="sxs-lookup"><span data-stu-id="26bae-106">If the first operand evaluates to `true`, the second operand is not evaluated and the result of operation is `true`.</span></span> <span data-ttu-id="26bae-107">以下示例演示了该行为：</span><span class="sxs-lookup"><span data-stu-id="26bae-107">The following example demonstrates that behavior:</span></span>

[!code-csharp-interactive[conditional logical OR](~/samples/snippets/csharp/language-reference/operators/ConditionalLogicalOperatorsExamples.cs#Or)]

<span data-ttu-id="26bae-108">[逻辑 OR 运算符](or-operator.md) `|` 也会计算其 `bool` 操作数的逻辑 OR，但始终会计算两个操作数。</span><span class="sxs-lookup"><span data-stu-id="26bae-108">The [logical OR operator](or-operator.md) `|` also computes the logical OR of its `bool` operands, but always evaluates both operands.</span></span>

## <a name="operator-overloadability"></a><span data-ttu-id="26bae-109">运算符可重载性</span><span class="sxs-lookup"><span data-stu-id="26bae-109">Operator overloadability</span></span>

<span data-ttu-id="26bae-110">用户定义类型不能重载条件逻辑 OR 运算符。</span><span class="sxs-lookup"><span data-stu-id="26bae-110">A user-defined type cannot overload the conditional logical OR operator.</span></span> <span data-ttu-id="26bae-111">但是，如果用户定义类型以某种方式重载了 [逻辑 OR](or-operator.md)、[true](../keywords/true-operator.md) 和 [false](../keywords/false-operator.md) 运算符，则可以对该类型的操作数进行 `||` 运算。</span><span class="sxs-lookup"><span data-stu-id="26bae-111">However, if a user-defined type overloads the [logical OR](or-operator.md), [true](../keywords/true-operator.md), and [false](../keywords/false-operator.md) operators in a certain way, the `||` operation can be evaluated for the operands of that type.</span></span> <span data-ttu-id="26bae-112">有关详细信息，请参阅 [C# 语言规范](../language-specification/index.md)的[用户定义条件逻辑运算符](~/_csharplang/spec/expressions.md#user-defined-conditional-logical-operators)部分。</span><span class="sxs-lookup"><span data-stu-id="26bae-112">For more information, see the [User-defined conditional logical operators](~/_csharplang/spec/expressions.md#user-defined-conditional-logical-operators) section of the [C# language specification](../language-specification/index.md).</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="26bae-113">C# 语言规范</span><span class="sxs-lookup"><span data-stu-id="26bae-113">C# language specification</span></span>

<span data-ttu-id="26bae-114">有关详细信息，请参阅 [C# 语言规范](../language-specification/index.md)的[条件逻辑运算符](~/_csharplang/spec/expressions.md#conditional-logical-operators)部分。</span><span class="sxs-lookup"><span data-stu-id="26bae-114">For more information, see the [Conditional logical operators](~/_csharplang/spec/expressions.md#conditional-logical-operators) section of the [C# language specification](../language-specification/index.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="26bae-115">请参阅</span><span class="sxs-lookup"><span data-stu-id="26bae-115">See also</span></span>

- [<span data-ttu-id="26bae-116">C# 参考</span><span class="sxs-lookup"><span data-stu-id="26bae-116">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="26bae-117">C# 编程指南</span><span class="sxs-lookup"><span data-stu-id="26bae-117">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="26bae-118">C# 运算符</span><span class="sxs-lookup"><span data-stu-id="26bae-118">C# Operators</span></span>](index.md)
- [<span data-ttu-id="26bae-119">&& 运算符</span><span class="sxs-lookup"><span data-stu-id="26bae-119">&& operator</span></span>](conditional-and-operator.md)
- [! 运算符]<span data-ttu-id="26bae-120">(logical-negation-operator.md)</span><span class="sxs-lookup"><span data-stu-id="26bae-120">(logical-negation-operator.md)</span></span>
- [<span data-ttu-id="26bae-121">| 运算符</span><span class="sxs-lookup"><span data-stu-id="26bae-121">| operator</span></span>](or-operator.md)
