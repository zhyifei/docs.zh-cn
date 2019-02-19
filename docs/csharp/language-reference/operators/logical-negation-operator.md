---
title: '! 运算符 - C# 参考'
ms.custom: seodec18
ms.date: 02/14/2019
f1_keywords:
- '!_CSharpKeyword'
helpviewer_keywords:
- '! operator [C#]'
- logical negation operator (!) [C#]
- NOT operator [C#]
ms.assetid: f5ae133f-8f64-4560-b34f-cd9cd5eed4ad
ms.openlocfilehash: 464bd658c9bf430191d84d3d5ad8d57173ab87c5
ms.sourcegitcommit: bef803e2025642df39f2f1e046767d89031e0304
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/15/2019
ms.locfileid: "56303707"
---
# <a name="-operator-c-reference"></a><span data-ttu-id="683e2-103">!</span><span class="sxs-lookup"><span data-stu-id="683e2-103">!</span></span> <span data-ttu-id="683e2-104">运算符（C# 参考）</span><span class="sxs-lookup"><span data-stu-id="683e2-104">operator (C# Reference)</span></span>

<span data-ttu-id="683e2-105">逻辑非运算符 `!` 是计算其 [bool](../keywords/bool.md) 操作数的逻辑求反的一元运算符。</span><span class="sxs-lookup"><span data-stu-id="683e2-105">The logical negation operator `!` is a unary operator that computes logical negation of its [bool](../keywords/bool.md) operand.</span></span> <span data-ttu-id="683e2-106">也就是说，如果操作数是 `false`，它会生成 `true`，如果操作数为 `true`，则生成 `false`：</span><span class="sxs-lookup"><span data-stu-id="683e2-106">That is, it produces `true`, if the operand is `false`, and `false`, if the operand is `true`:</span></span>

[!code-csharp-interactive[logical negation](~/samples/snippets/csharp/language-reference/operators/LogicalNegationExamples.cs#Example)]

## <a name="operator-overloadability"></a><span data-ttu-id="683e2-107">运算符可重载性</span><span class="sxs-lookup"><span data-stu-id="683e2-107">Operator overloadability</span></span>

<span data-ttu-id="683e2-108">用户定义的类型可以[重载](../keywords/operator.md) `!` 运算符。</span><span class="sxs-lookup"><span data-stu-id="683e2-108">User-defined types can [overload](../keywords/operator.md) the `!` operator.</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="683e2-109">C# 语言规范</span><span class="sxs-lookup"><span data-stu-id="683e2-109">C# language specification</span></span>

<span data-ttu-id="683e2-110">有关详细信息，请参阅 [C# 语言规范](../language-specification/index.md)的[逻辑非运算符](~/_csharplang/spec/expressions.md#logical-negation-operator)部分。</span><span class="sxs-lookup"><span data-stu-id="683e2-110">For more information, see the [Logical negation operator](~/_csharplang/spec/expressions.md#logical-negation-operator) section of the [C# language specification](../language-specification/index.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="683e2-111">请参阅</span><span class="sxs-lookup"><span data-stu-id="683e2-111">See also</span></span>

- [<span data-ttu-id="683e2-112">C# 参考</span><span class="sxs-lookup"><span data-stu-id="683e2-112">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="683e2-113">C# 编程指南</span><span class="sxs-lookup"><span data-stu-id="683e2-113">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="683e2-114">C# 运算符</span><span class="sxs-lookup"><span data-stu-id="683e2-114">C# Operators</span></span>](index.md)