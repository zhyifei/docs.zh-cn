---
title: '!= 运算符 - C# 参考'
ms.custom: seodec18
ms.date: 12/14/2018
f1_keywords:
- '!=_CSharpKeyword'
helpviewer_keywords:
- inequality operator (!=) [C#]
- not equals operator (!=) [C#]
- '!= operator [C#]'
ms.assetid: eeff7a4e-ad6f-462d-9f8d-49e9b91c6c97
ms.openlocfilehash: 939b5664dba4345e62a43fb2f8d4d5379659d6aa
ms.sourcegitcommit: fa38fe76abdc8972e37138fcb4dfdb3502ac5394
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/19/2018
ms.locfileid: "53610172"
---
# <a name="-operator-c-reference"></a><span data-ttu-id="e1746-102">!= 运算符（C# 参考）</span><span class="sxs-lookup"><span data-stu-id="e1746-102">!= Operator (C# Reference)</span></span>

<span data-ttu-id="e1746-103">如果操作数不相等，不等于运算符 `!=` 返回 `true`，否则返回 `false`。</span><span class="sxs-lookup"><span data-stu-id="e1746-103">The inequality operator `!=` returns `true` if its operands are not equal, `false` otherwise.</span></span> <span data-ttu-id="e1746-104">对于[内置类型](../keywords/built-in-types-table.md)的操作数，表达式 `x != y` 生成与表达式 `!(x == y)` 相同的结果。</span><span class="sxs-lookup"><span data-stu-id="e1746-104">For the operands of the [built-in types](../keywords/built-in-types-table.md), the expression `x != y` produces the same result as the expression `!(x == y)`.</span></span> <span data-ttu-id="e1746-105">有关详细信息，请参阅 [== 运算符](equality-comparison-operator.md)一文。</span><span class="sxs-lookup"><span data-stu-id="e1746-105">For more information, see the [== Operator](equality-comparison-operator.md) article.</span></span>

<span data-ttu-id="e1746-106">下面的示例演示 `!=` 运算符的用法：</span><span class="sxs-lookup"><span data-stu-id="e1746-106">The following example demonstrates the usage of the `!=` operator:</span></span>

[!code-csharp-interactive[non-equality examples](~/samples/snippets/csharp/language-reference/operators/EqualityAndNonEqualityExamples.cs#NonEquality)]

## <a name="operator-overloadability"></a><span data-ttu-id="e1746-107">运算符可重载性</span><span class="sxs-lookup"><span data-stu-id="e1746-107">Operator overloadability</span></span>

<span data-ttu-id="e1746-108">用户定义的类型可以[重载](../keywords/operator.md) `!=` 运算符。</span><span class="sxs-lookup"><span data-stu-id="e1746-108">User-defined types can [overload](../keywords/operator.md) the `!=` operator.</span></span> <span data-ttu-id="e1746-109">如果类型重载不等于运算符 `!=`，它也必须重载[等于运算符](equality-comparison-operator.md) `==`。</span><span class="sxs-lookup"><span data-stu-id="e1746-109">If a type overloads the inequality operator `!=`, it must also overload the [equality operator](equality-comparison-operator.md) `==`.</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="e1746-110">C# 语言规范</span><span class="sxs-lookup"><span data-stu-id="e1746-110">C# language specification</span></span>

<span data-ttu-id="e1746-111">有关详细信息，请参阅 [C# 语言规范](../language-specification/index.md)中的[关系和类型测试运算符](~/_csharplang/spec/expressions.md#relational-and-type-testing-operators)部分。</span><span class="sxs-lookup"><span data-stu-id="e1746-111">For more information, see the [Relational and type-testing operators](~/_csharplang/spec/expressions.md#relational-and-type-testing-operators) section of the [C# language specification](../language-specification/index.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="e1746-112">请参阅</span><span class="sxs-lookup"><span data-stu-id="e1746-112">See also</span></span>

- [<span data-ttu-id="e1746-113">C# 参考</span><span class="sxs-lookup"><span data-stu-id="e1746-113">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="e1746-114">C# 编程指南</span><span class="sxs-lookup"><span data-stu-id="e1746-114">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="e1746-115">C# 运算符</span><span class="sxs-lookup"><span data-stu-id="e1746-115">C# Operators</span></span>](index.md)
- [<span data-ttu-id="e1746-116">相等性比较</span><span class="sxs-lookup"><span data-stu-id="e1746-116">Equality comparisons</span></span>](../../programming-guide/statements-expressions-operators/equality-comparisons.md)
