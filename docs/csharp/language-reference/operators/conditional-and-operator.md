---
title: '&amp;&amp; 运算符（C# 参考）'
ms.date: 11/06/2018
f1_keywords:
- '&&_CSharpKeyword'
helpviewer_keywords:
- '&& operator [C#]'
- logical AND operator [C#]
ms.assetid: 2e4f0a1c-92a3-40f8-8e3b-17b607f20c31
ms.openlocfilehash: d0e6d9a5aedc7dc87393e3dea070bf442b3268dc
ms.sourcegitcommit: b5cd9d5d3b75a5537fc9ad8a3f085f0bb1845ee0
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/07/2018
ms.locfileid: "43529230"
---
# <a name="ampamp-operator-c-reference"></a><span data-ttu-id="5a6f9-102">&amp;&amp; 运算符（C# 参考）</span><span class="sxs-lookup"><span data-stu-id="5a6f9-102">&amp;&amp; Operator (C# Reference)</span></span>

<span data-ttu-id="5a6f9-103">条件逻辑 AND 运算符 `&&`（也称为“短路”逻辑 AND 运算符）计算其 [bool](../keywords/bool.md) 操作数的逻辑 AND。</span><span class="sxs-lookup"><span data-stu-id="5a6f9-103">The conditional logical AND operator `&&`, also known as the "short-circuiting" logical AND operator, computes the logical AND of its [bool](../keywords/bool.md) operands.</span></span> <span data-ttu-id="5a6f9-104">如果 `x` 和 `y` 的计算结果都为 `true`，则 `x && y` 的结果为 `true`。</span><span class="sxs-lookup"><span data-stu-id="5a6f9-104">The result of `x && y` is `true` if both `x` and `y` evaluate to `true`.</span></span> <span data-ttu-id="5a6f9-105">否则，结果为 `false`。</span><span class="sxs-lookup"><span data-stu-id="5a6f9-105">Otherwise, the result is `false`.</span></span> <span data-ttu-id="5a6f9-106">如果第一个操作数的计算结果为 `false`，则不会计算第二个操作数且运算结果为 `false`。</span><span class="sxs-lookup"><span data-stu-id="5a6f9-106">If the first operand evaluates to `false`, the second operand is not evaluated and the result of operation is `false`.</span></span> <span data-ttu-id="5a6f9-107">以下示例演示了该行为：</span><span class="sxs-lookup"><span data-stu-id="5a6f9-107">The following example demonstrates that behavior:</span></span>

[!code-csharp-interactive[conditional logical AND](~/samples/snippets/csharp/language-reference/operators/ConditionalLogicalOperatorsExamples.cs#And)]

<span data-ttu-id="5a6f9-108">[逻辑 AND 运算符](and-operator.md) `&` 也会计算其 `bool` 操作数的逻辑 AND，但始终会计算两个操作数。</span><span class="sxs-lookup"><span data-stu-id="5a6f9-108">The [logical AND operator](and-operator.md) `&` also computes the logical AND of its `bool` operands, but always evaluates both operands.</span></span>

## <a name="operator-overloadability"></a><span data-ttu-id="5a6f9-109">运算符可重载性</span><span class="sxs-lookup"><span data-stu-id="5a6f9-109">Operator overloadability</span></span>

<span data-ttu-id="5a6f9-110">用户定义类型不能重载条件逻辑 AND 运算符。</span><span class="sxs-lookup"><span data-stu-id="5a6f9-110">A user-defined type cannot overload the conditional logical AND operator.</span></span> <span data-ttu-id="5a6f9-111">但是，如果用户定义类型以某种方式重载了 [逻辑 AND](and-operator.md)、[true](../keywords/true-operator.md) 和 [false](../keywords/false-operator.md) 运算符，则可以对该类型的操作数进行 `&&` 运算。</span><span class="sxs-lookup"><span data-stu-id="5a6f9-111">However, if a user-defined type overloads the [logical AND](and-operator.md), [true](../keywords/true-operator.md), and [false](../keywords/false-operator.md) operators in a certain way, the `&&` operation can be evaluated for the operands of that type.</span></span> <span data-ttu-id="5a6f9-112">有关详细信息，请参阅 [C# 语言规范](../language-specification/index.md)的[用户定义条件逻辑运算符](~/_csharplang/spec/expressions.md#user-defined-conditional-logical-operators)部分。</span><span class="sxs-lookup"><span data-stu-id="5a6f9-112">For more information, see the [User-defined conditional logical operators](~/_csharplang/spec/expressions.md#user-defined-conditional-logical-operators) section of the [C# language specification](../language-specification/index.md).</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="5a6f9-113">C# 语言规范</span><span class="sxs-lookup"><span data-stu-id="5a6f9-113">C# language specification</span></span>

<span data-ttu-id="5a6f9-114">有关详细信息，请参阅 [C# 语言规范](../language-specification/index.md)的[条件逻辑运算符](~/_csharplang/spec/expressions.md#conditional-logical-operators)部分。</span><span class="sxs-lookup"><span data-stu-id="5a6f9-114">For more information, see the [Conditional logical operators](~/_csharplang/spec/expressions.md#conditional-logical-operators) section of the [C# language specification](../language-specification/index.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="5a6f9-115">请参阅</span><span class="sxs-lookup"><span data-stu-id="5a6f9-115">See also</span></span>

- [<span data-ttu-id="5a6f9-116">C# 参考</span><span class="sxs-lookup"><span data-stu-id="5a6f9-116">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="5a6f9-117">C# 编程指南</span><span class="sxs-lookup"><span data-stu-id="5a6f9-117">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="5a6f9-118">C# 运算符</span><span class="sxs-lookup"><span data-stu-id="5a6f9-118">C# Operators</span></span>](index.md)
- [<span data-ttu-id="5a6f9-119">|| 运算符</span><span class="sxs-lookup"><span data-stu-id="5a6f9-119">|| operator</span></span>](conditional-or-operator.md)
- [<span data-ttu-id="5a6f9-120">\! 运算符</span><span class="sxs-lookup"><span data-stu-id="5a6f9-120">! operator</span></span>](logical-negation-operator.md)
- [<span data-ttu-id="5a6f9-121">& 运算符</span><span class="sxs-lookup"><span data-stu-id="5a6f9-121">& operator</span></span>](and-operator.md)
