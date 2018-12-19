---
title: '|| 运算符 - C# 参考'
ms.custom: seodec18
ms.date: 11/06/2018
f1_keywords:
- '||_CSharpKeyword'
helpviewer_keywords:
- logical OR operator [C#]
- conditional-OR operator (||) [C#]
- '|| operator [C#]'
ms.assetid: 7d442d8e-400d-421f-b4d2-034bf82bcbdc
ms.openlocfilehash: f4bb7ada12fbcebcb90fb7cd22d6e6bccad5fb57
ms.sourcegitcommit: bdd930b5df20a45c29483d905526a2a3e4d17c5b
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2018
ms.locfileid: "53244565"
---
# <a name="-operator-c-reference"></a><span data-ttu-id="afdf3-102">|| 运算符（C# 参考）</span><span class="sxs-lookup"><span data-stu-id="afdf3-102">|| Operator (C# Reference)</span></span>

<span data-ttu-id="afdf3-103">条件逻辑 OR 运算符 `||`（也称为“短路”逻辑 OR 运算符）计算其 [bool](../keywords/bool.md) 操作数的逻辑 OR。</span><span class="sxs-lookup"><span data-stu-id="afdf3-103">The conditional logical OR operator `||`, also known as the "short-circuiting" logical OR operator, computes the logical OR of its [bool](../keywords/bool.md) operands.</span></span> <span data-ttu-id="afdf3-104">如果 `x` 或 `y` 的计算结果为 `true`，则 `x || y` 的结果为 `true`。</span><span class="sxs-lookup"><span data-stu-id="afdf3-104">The result of `x || y` is `true` if either `x` or `y` evaluates to `true`.</span></span> <span data-ttu-id="afdf3-105">否则，结果为 `false`。</span><span class="sxs-lookup"><span data-stu-id="afdf3-105">Otherwise, the result is `false`.</span></span> <span data-ttu-id="afdf3-106">如果第一个操作数的计算结果为 `true`，则不会计算第二个操作数且运算结果为 `true`。</span><span class="sxs-lookup"><span data-stu-id="afdf3-106">If the first operand evaluates to `true`, the second operand is not evaluated and the result of operation is `true`.</span></span> <span data-ttu-id="afdf3-107">以下示例演示了该行为：</span><span class="sxs-lookup"><span data-stu-id="afdf3-107">The following example demonstrates that behavior:</span></span>

[!code-csharp-interactive[conditional logical OR](~/samples/snippets/csharp/language-reference/operators/ConditionalLogicalOperatorsExamples.cs#Or)]

<span data-ttu-id="afdf3-108">[逻辑 OR 运算符](or-operator.md) `|` 也会计算其 `bool` 操作数的逻辑 OR，但始终会计算两个操作数。</span><span class="sxs-lookup"><span data-stu-id="afdf3-108">The [logical OR operator](or-operator.md) `|` also computes the logical OR of its `bool` operands, but always evaluates both operands.</span></span>

## <a name="operator-overloadability"></a><span data-ttu-id="afdf3-109">运算符可重载性</span><span class="sxs-lookup"><span data-stu-id="afdf3-109">Operator overloadability</span></span>

<span data-ttu-id="afdf3-110">用户定义类型不能重载条件逻辑 OR 运算符。</span><span class="sxs-lookup"><span data-stu-id="afdf3-110">A user-defined type cannot overload the conditional logical OR operator.</span></span> <span data-ttu-id="afdf3-111">不过，如果用户定义类型以某种方式重载[逻辑 OR](or-operator.md) 以及 [true 和 false 运算符](../keywords/true-false-operators.md)，可以对相应类型的操作数执行 `||` 运算。</span><span class="sxs-lookup"><span data-stu-id="afdf3-111">However, if a user-defined type overloads the [logical OR](or-operator.md) and [true and false operators](../keywords/true-false-operators.md) in a certain way, the `||` operation can be evaluated for the operands of that type.</span></span> <span data-ttu-id="afdf3-112">有关详细信息，请参阅 [C# 语言规范](../language-specification/index.md)的[用户定义条件逻辑运算符](~/_csharplang/spec/expressions.md#user-defined-conditional-logical-operators)部分。</span><span class="sxs-lookup"><span data-stu-id="afdf3-112">For more information, see the [User-defined conditional logical operators](~/_csharplang/spec/expressions.md#user-defined-conditional-logical-operators) section of the [C# language specification](../language-specification/index.md).</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="afdf3-113">C# 语言规范</span><span class="sxs-lookup"><span data-stu-id="afdf3-113">C# language specification</span></span>

<span data-ttu-id="afdf3-114">有关详细信息，请参阅 [C# 语言规范](../language-specification/index.md)的[条件逻辑运算符](~/_csharplang/spec/expressions.md#conditional-logical-operators)部分。</span><span class="sxs-lookup"><span data-stu-id="afdf3-114">For more information, see the [Conditional logical operators](~/_csharplang/spec/expressions.md#conditional-logical-operators) section of the [C# language specification](../language-specification/index.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="afdf3-115">请参阅</span><span class="sxs-lookup"><span data-stu-id="afdf3-115">See also</span></span>

- [<span data-ttu-id="afdf3-116">C# 参考</span><span class="sxs-lookup"><span data-stu-id="afdf3-116">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="afdf3-117">C# 编程指南</span><span class="sxs-lookup"><span data-stu-id="afdf3-117">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="afdf3-118">C# 运算符</span><span class="sxs-lookup"><span data-stu-id="afdf3-118">C# Operators</span></span>](index.md)
- [<span data-ttu-id="afdf3-119">&& 运算符</span><span class="sxs-lookup"><span data-stu-id="afdf3-119">&& operator</span></span>](conditional-and-operator.md)
- [! 运算符]<span data-ttu-id="afdf3-120">(logical-negation-operator.md)</span><span class="sxs-lookup"><span data-stu-id="afdf3-120">(logical-negation-operator.md)</span></span>
- [<span data-ttu-id="afdf3-121">| 运算符</span><span class="sxs-lookup"><span data-stu-id="afdf3-121">| operator</span></span>](or-operator.md)
