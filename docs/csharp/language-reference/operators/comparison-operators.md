---
title: 比较运算符 - C# 参考
description: 了解可用于检查数值顺序的 C# 比较运算符。
ms.date: 04/25/2019
author: pkulikov
f1_keywords:
- <_CSharpKeyword
- '>_CSharpKeyword'
- <=_CSharpKeyword
- '>=_CSharpKeyword'
helpviewer_keywords:
- comparison operators [C#]
- relational operators [C#]
- less than operator [C#]
- < operator [C#]
- greater than operator [C#]
- '> operator [C#]'
- less than or equal to operator [C#]
- <= operator [C#]
- greater than or equal to operator [C#]
- '>= operator [C#]'
ms.openlocfilehash: 7d8a6b7f5bf83719f96009c301867056da755822
ms.sourcegitcommit: 5bc85ad81d96b8dc2a90ce53bada475ee5662c44
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/12/2019
ms.locfileid: "67025218"
---
# <a name="comparison-operators-c-reference"></a><span data-ttu-id="f71f8-103">比较运算符（C# 参考）</span><span class="sxs-lookup"><span data-stu-id="f71f8-103">Comparison operators (C# reference)</span></span>

<span data-ttu-id="f71f8-104">[`<`（小于）](#less-than-operator-)、[`>`（大于）](#greater-than-operator-)、[`<=`（小于或等于）](#less-than-or-equal-operator-)和 [`>=`（大于或等于）](#greater-than-or-equal-operator-)比较（也称为关系）运算符比较其操作数。</span><span class="sxs-lookup"><span data-stu-id="f71f8-104">The [`<` (less than)](#less-than-operator-), [`>` (greater than)](#greater-than-operator-), [`<=` (less than or equal)](#less-than-or-equal-operator-), and [`>=` (greater than or equal)](#greater-than-or-equal-operator-) comparison, also known as relational, operators compare their operands.</span></span> <span data-ttu-id="f71f8-105">这些运算符支持所有[整型](../keywords/integral-types-table.md)和[浮动](../keywords/floating-point-types-table.md)数值类型。</span><span class="sxs-lookup"><span data-stu-id="f71f8-105">Those operators support all [integral](../keywords/integral-types-table.md) and [floating-point](../keywords/floating-point-types-table.md) numeric types.</span></span>

> [!NOTE]
> <span data-ttu-id="f71f8-106">对于 `==`、`<`、`>`、`<=` 和 `>=` 运算符，如果所有操作数都不是数字（<xref:System.Double.NaN?displayProperty=nameWithType> 或 <xref:System.Single.NaN?displayProperty=nameWithType>），则运算结果为 `false`。</span><span class="sxs-lookup"><span data-stu-id="f71f8-106">For the `==`, `<`, `>`, `<=`, and `>=` operators, if any of the operands is not a number (<xref:System.Double.NaN?displayProperty=nameWithType> or <xref:System.Single.NaN?displayProperty=nameWithType>), the result of operation is `false`.</span></span> <span data-ttu-id="f71f8-107">这意味着 `NaN` 值不大于、小于或等于任何其他 `double`（或 `float`）值，包括 `NaN`。</span><span class="sxs-lookup"><span data-stu-id="f71f8-107">That means that the `NaN` value is neither greater than, less than, nor equal to any other `double` (or `float`) value, including `NaN`.</span></span> <span data-ttu-id="f71f8-108">有关更多信息和示例，请参阅 <xref:System.Double.NaN?displayProperty=nameWithType> 或 <xref:System.Single.NaN?displayProperty=nameWithType> 参考文章。</span><span class="sxs-lookup"><span data-stu-id="f71f8-108">For more information and examples, see the <xref:System.Double.NaN?displayProperty=nameWithType> or <xref:System.Single.NaN?displayProperty=nameWithType> reference article.</span></span>

<span data-ttu-id="f71f8-109">枚举类型也支持比较运算符。</span><span class="sxs-lookup"><span data-stu-id="f71f8-109">Enumeration types also support comparison operators.</span></span> <span data-ttu-id="f71f8-110">对于相同[枚举](../keywords/enum.md)类型的操作数，基础整数类型的相应值会进行比较。</span><span class="sxs-lookup"><span data-stu-id="f71f8-110">For operands of the same [enum](../keywords/enum.md) type, the corresponding values of the underlying integral type are compared.</span></span>

<span data-ttu-id="f71f8-111">[`==` 和 `!=` 运算符](equality-operators.md)检查其操作数是否相等。</span><span class="sxs-lookup"><span data-stu-id="f71f8-111">The [`==` and `!=` operators](equality-operators.md) check if their operands are equal or not.</span></span>

## <a name="less-than-operator-"></a><span data-ttu-id="f71f8-112">小于运算符 \<</span><span class="sxs-lookup"><span data-stu-id="f71f8-112">Less than operator \<</span></span>

<span data-ttu-id="f71f8-113">如果第一个操作数小于第二个操作数，`<` 运算符返回 `true`，否则返回 `false`：</span><span class="sxs-lookup"><span data-stu-id="f71f8-113">The `<` operator returns `true` if its first operand is less than its second operand, `false` otherwise:</span></span>

[!code-csharp-interactive[less than example](~/samples/csharp/language-reference/operators/ComparisonOperators.cs#Less)]

## <a name="greater-than-operator-"></a><span data-ttu-id="f71f8-114">大于运算符 ></span><span class="sxs-lookup"><span data-stu-id="f71f8-114">Greater than operator ></span></span>

<span data-ttu-id="f71f8-115">如果第一个操作数大于第二个操作数，`>` 运算符返回 `true`，否则返回 `false`：</span><span class="sxs-lookup"><span data-stu-id="f71f8-115">The `>` operator returns `true` if its first operand is greater than its second operand, `false` otherwise:</span></span>

[!code-csharp-interactive[greater than example](~/samples/csharp/language-reference/operators/ComparisonOperators.cs#Greater)]

## <a name="less-than-or-equal-operator-"></a><span data-ttu-id="f71f8-116">小于或等于运算符 \<=</span><span class="sxs-lookup"><span data-stu-id="f71f8-116">Less than or equal operator \<=</span></span>

<span data-ttu-id="f71f8-117">如果第一个操作数小于或等于第二个操作数，`<=` 运算符返回 `true`，否则返回 `false`：</span><span class="sxs-lookup"><span data-stu-id="f71f8-117">The `<=` operator returns `true` if its first operand is less than or equal to its second operand, `false` otherwise:</span></span>

[!code-csharp-interactive[less than or equal example](~/samples/csharp/language-reference/operators/ComparisonOperators.cs#LessOrEqual)]

## <a name="greater-than-or-equal-operator-"></a><span data-ttu-id="f71f8-118">大于或等于运算符 >=</span><span class="sxs-lookup"><span data-stu-id="f71f8-118">Greater than or equal operator >=</span></span>

<span data-ttu-id="f71f8-119">如果第一个操作数大于或等于第二个操作数，`>=` 运算符返回 `true`，否则返回 `false`：</span><span class="sxs-lookup"><span data-stu-id="f71f8-119">The `>=` operator returns `true` if its first operand is greater than or equal to its second operand, `false` otherwise:</span></span>

[!code-csharp-interactive[greater than or equal example](~/samples/csharp/language-reference/operators/ComparisonOperators.cs#GreaterOrEqual)]

## <a name="operator-overloadability"></a><span data-ttu-id="f71f8-120">运算符可重载性</span><span class="sxs-lookup"><span data-stu-id="f71f8-120">Operator overloadability</span></span>

<span data-ttu-id="f71f8-121">用户定义类型可以[重载](../keywords/operator.md) `<`、`>`、`<=` 和 `>=` 运算符。</span><span class="sxs-lookup"><span data-stu-id="f71f8-121">A user-defined type can [overload](../keywords/operator.md) the `<`, `>`, `<=`, and `>=` operators.</span></span>

<span data-ttu-id="f71f8-122">如果某类型重载 `<` 或 `>` 运算符之一，它必须同时重载 `<` 和 `>`。</span><span class="sxs-lookup"><span data-stu-id="f71f8-122">If a type overloads one of the `<` or `>` operators, it must overload both `<` and `>`.</span></span> <span data-ttu-id="f71f8-123">如果某类型重载 `<=` 或 `>=` 运算符之一，它必须同时重载 `<=` 和 `>=`。</span><span class="sxs-lookup"><span data-stu-id="f71f8-123">If a type overloads one of the `<=` or `>=` operators, it must overload both `<=` and `>=`.</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="f71f8-124">C# 语言规范</span><span class="sxs-lookup"><span data-stu-id="f71f8-124">C# language specification</span></span>

<span data-ttu-id="f71f8-125">有关详细信息，请参阅 [C# 语言规范](~/_csharplang/spec/introduction.md)中的[关系和类型测试运算符](~/_csharplang/spec/expressions.md#relational-and-type-testing-operators)部分。</span><span class="sxs-lookup"><span data-stu-id="f71f8-125">For more information, see the [Relational and type-testing operators](~/_csharplang/spec/expressions.md#relational-and-type-testing-operators) section of the [C# language specification](~/_csharplang/spec/introduction.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="f71f8-126">请参阅</span><span class="sxs-lookup"><span data-stu-id="f71f8-126">See also</span></span>

- [<span data-ttu-id="f71f8-127">C# 参考</span><span class="sxs-lookup"><span data-stu-id="f71f8-127">C# reference</span></span>](../index.md)
- [<span data-ttu-id="f71f8-128">C# 运算符</span><span class="sxs-lookup"><span data-stu-id="f71f8-128">C# operators</span></span>](index.md)
- <xref:System.IComparable%601?displayProperty=nameWithType>
- [<span data-ttu-id="f71f8-129">相等运算符</span><span class="sxs-lookup"><span data-stu-id="f71f8-129">Equality operators</span></span>](equality-operators.md)
