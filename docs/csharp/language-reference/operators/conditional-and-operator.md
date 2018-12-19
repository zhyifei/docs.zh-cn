---
title: '&amp;&amp; 运算符 - C# 参考'
ms.custom: seodec18
ms.date: 11/06/2018
f1_keywords:
- '&&_CSharpKeyword'
helpviewer_keywords:
- '&& operator [C#]'
- logical AND operator [C#]
ms.assetid: 2e4f0a1c-92a3-40f8-8e3b-17b607f20c31
ms.openlocfilehash: 82442f50275f21e0a0748951dc50628a8d7e11bb
ms.sourcegitcommit: bdd930b5df20a45c29483d905526a2a3e4d17c5b
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2018
ms.locfileid: "53243571"
---
# <a name="ampamp-operator-c-reference"></a><span data-ttu-id="5ef74-102">&amp;&amp; 运算符（C# 参考）</span><span class="sxs-lookup"><span data-stu-id="5ef74-102">&amp;&amp; Operator (C# Reference)</span></span>

<span data-ttu-id="5ef74-103">条件逻辑 AND 运算符 `&&`（也称为“短路”逻辑 AND 运算符）计算其 [bool](../keywords/bool.md) 操作数的逻辑 AND。</span><span class="sxs-lookup"><span data-stu-id="5ef74-103">The conditional logical AND operator `&&`, also known as the "short-circuiting" logical AND operator, computes the logical AND of its [bool](../keywords/bool.md) operands.</span></span> <span data-ttu-id="5ef74-104">如果 `x` 和 `y` 的计算结果都为 `true`，则 `x && y` 的结果为 `true`。</span><span class="sxs-lookup"><span data-stu-id="5ef74-104">The result of `x && y` is `true` if both `x` and `y` evaluate to `true`.</span></span> <span data-ttu-id="5ef74-105">否则，结果为 `false`。</span><span class="sxs-lookup"><span data-stu-id="5ef74-105">Otherwise, the result is `false`.</span></span> <span data-ttu-id="5ef74-106">如果第一个操作数的计算结果为 `false`，则不会计算第二个操作数且运算结果为 `false`。</span><span class="sxs-lookup"><span data-stu-id="5ef74-106">If the first operand evaluates to `false`, the second operand is not evaluated and the result of operation is `false`.</span></span> <span data-ttu-id="5ef74-107">以下示例演示了该行为：</span><span class="sxs-lookup"><span data-stu-id="5ef74-107">The following example demonstrates that behavior:</span></span>

[!code-csharp-interactive[conditional logical AND](~/samples/snippets/csharp/language-reference/operators/ConditionalLogicalOperatorsExamples.cs#And)]

<span data-ttu-id="5ef74-108">[逻辑 AND 运算符](and-operator.md) `&` 也会计算其 `bool` 操作数的逻辑 AND，但始终会计算两个操作数。</span><span class="sxs-lookup"><span data-stu-id="5ef74-108">The [logical AND operator](and-operator.md) `&` also computes the logical AND of its `bool` operands, but always evaluates both operands.</span></span>

## <a name="operator-overloadability"></a><span data-ttu-id="5ef74-109">运算符可重载性</span><span class="sxs-lookup"><span data-stu-id="5ef74-109">Operator overloadability</span></span>

<span data-ttu-id="5ef74-110">用户定义类型不能重载条件逻辑 AND 运算符。</span><span class="sxs-lookup"><span data-stu-id="5ef74-110">A user-defined type cannot overload the conditional logical AND operator.</span></span> <span data-ttu-id="5ef74-111">不过，如果用户定义类型以某种方式重载[逻辑 AND](and-operator.md) 以及 [true 和 false 运算符](../keywords/true-false-operators.md)，可以对相应类型的操作数执行 `&&` 运算。</span><span class="sxs-lookup"><span data-stu-id="5ef74-111">However, if a user-defined type overloads the [logical AND](and-operator.md) and [true and false operators](../keywords/true-false-operators.md) in a certain way, the `&&` operation can be evaluated for the operands of that type.</span></span> <span data-ttu-id="5ef74-112">有关详细信息，请参阅 [C# 语言规范](../language-specification/index.md)的[用户定义条件逻辑运算符](~/_csharplang/spec/expressions.md#user-defined-conditional-logical-operators)部分。</span><span class="sxs-lookup"><span data-stu-id="5ef74-112">For more information, see the [User-defined conditional logical operators](~/_csharplang/spec/expressions.md#user-defined-conditional-logical-operators) section of the [C# language specification](../language-specification/index.md).</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="5ef74-113">C# 语言规范</span><span class="sxs-lookup"><span data-stu-id="5ef74-113">C# language specification</span></span>

<span data-ttu-id="5ef74-114">有关详细信息，请参阅 [C# 语言规范](../language-specification/index.md)的[条件逻辑运算符](~/_csharplang/spec/expressions.md#conditional-logical-operators)部分。</span><span class="sxs-lookup"><span data-stu-id="5ef74-114">For more information, see the [Conditional logical operators](~/_csharplang/spec/expressions.md#conditional-logical-operators) section of the [C# language specification](../language-specification/index.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="5ef74-115">请参阅</span><span class="sxs-lookup"><span data-stu-id="5ef74-115">See also</span></span>

- [<span data-ttu-id="5ef74-116">C# 参考</span><span class="sxs-lookup"><span data-stu-id="5ef74-116">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="5ef74-117">C# 编程指南</span><span class="sxs-lookup"><span data-stu-id="5ef74-117">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="5ef74-118">C# 运算符</span><span class="sxs-lookup"><span data-stu-id="5ef74-118">C# Operators</span></span>](index.md)
- [<span data-ttu-id="5ef74-119">|| 运算符</span><span class="sxs-lookup"><span data-stu-id="5ef74-119">|| operator</span></span>](conditional-or-operator.md)
- [<span data-ttu-id="5ef74-120">\! 运算符</span><span class="sxs-lookup"><span data-stu-id="5ef74-120">! operator</span></span>](logical-negation-operator.md)
- [<span data-ttu-id="5ef74-121">& 运算符</span><span class="sxs-lookup"><span data-stu-id="5ef74-121">& operator</span></span>](and-operator.md)
