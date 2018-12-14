---
title: ++ 运算符（C# 参考）
ms.date: 11/26/2018
f1_keywords:
- ++_CSharpKeyword
helpviewer_keywords:
- increment operator (++) [C#]
- ++ operator [C#]
ms.assetid: e9dec353-070b-44fb-98ed-eb8fdf753feb
ms.openlocfilehash: b29f4f1ab00c0f8026f118cb72b090e3b728bfc5
ms.sourcegitcommit: 6ae7cdd0437a32884556dd4826ca90e957b7a4e3
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/06/2018
ms.locfileid: "48030458"
---
# <a name="-operator-c-reference"></a><span data-ttu-id="6ccce-102">++ 运算符（C# 参考）</span><span class="sxs-lookup"><span data-stu-id="6ccce-102">++ Operator (C# Reference)</span></span>

<span data-ttu-id="6ccce-103">一元增量运算符 `++` 按 1 递增其操作数。</span><span class="sxs-lookup"><span data-stu-id="6ccce-103">The unary increment operator `++` increments its operand by 1.</span></span> <span data-ttu-id="6ccce-104">它以两种形式进行支持：后缀增量运算符`x++` 和前缀增量运算符 `++x`。</span><span class="sxs-lookup"><span data-stu-id="6ccce-104">It's supported in two forms: the postfix increment operator, `x++`, and the prefix increment operator, `++x`.</span></span>

## <a name="postfix-increment-operator"></a><span data-ttu-id="6ccce-105">后缀递增运算符</span><span class="sxs-lookup"><span data-stu-id="6ccce-105">Postfix increment operator</span></span>

<span data-ttu-id="6ccce-106">`x++` 的结果是此操作前的 `x` 的值，如以下示例所示：</span><span class="sxs-lookup"><span data-stu-id="6ccce-106">The result of `x++` is the value of `x` *before* the operation, as the following example shows:</span></span>

[!code-csharp-interactive[postfix increment](~/samples/snippets/csharp/language-reference/operators/DecrementAndIncrementExamples.cs#PostfixIncrement)]

## <a name="prefix-increment-operator"></a><span data-ttu-id="6ccce-107">前缀增量运算符</span><span class="sxs-lookup"><span data-stu-id="6ccce-107">Prefix increment operator</span></span>

<span data-ttu-id="6ccce-108">`++x` 的结果是此操作后的 `x` 的值，如以下示例所示：</span><span class="sxs-lookup"><span data-stu-id="6ccce-108">The result of `++x` is the value of `x` *after* the operation, as the following example shows:</span></span>

[!code-csharp-interactive[prefix increment](~/samples/snippets/csharp/language-reference/operators/DecrementAndIncrementExamples.cs#PrefixIncrement)]

## <a name="remarks"></a><span data-ttu-id="6ccce-109">备注</span><span class="sxs-lookup"><span data-stu-id="6ccce-109">Remarks</span></span>

<span data-ttu-id="6ccce-110">增量运算符是为所有[整型类型](../keywords/integral-types-table.md)（包括[字符](../keywords/char.md)型）、[浮点型](../keywords/floating-point-types-table.md)和任何[枚举](../keywords/enum.md)类型预定义的。</span><span class="sxs-lookup"><span data-stu-id="6ccce-110">The increment operator is predefined for all [integral types](../keywords/integral-types-table.md) (including the [char](../keywords/char.md) type), [floating-point types](../keywords/floating-point-types-table.md), and any [enum](../keywords/enum.md) type.</span></span>

<span data-ttu-id="6ccce-111">增量运算符的操作数必须是变量、[属性](../../programming-guide/classes-and-structs/properties.md)访问或[索引器](../../../csharp/programming-guide/indexers/index.md)访问。</span><span class="sxs-lookup"><span data-stu-id="6ccce-111">An operand of the increment operator must be a variable, a [property](../../programming-guide/classes-and-structs/properties.md) access, or an [indexer](../../../csharp/programming-guide/indexers/index.md) access.</span></span>

## <a name="operator-overloadability"></a><span data-ttu-id="6ccce-112">运算符可重载性</span><span class="sxs-lookup"><span data-stu-id="6ccce-112">Operator overloadability</span></span>

<span data-ttu-id="6ccce-113">用户定义的类型可以[重载](../keywords/operator.md) `++` 运算符。</span><span class="sxs-lookup"><span data-stu-id="6ccce-113">User-defined types can [overload](../keywords/operator.md) the `++` operator.</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="6ccce-114">C# 语言规范</span><span class="sxs-lookup"><span data-stu-id="6ccce-114">C# language specification</span></span>

<span data-ttu-id="6ccce-115">有关详细信息，请参阅 [C# 语言规范](../language-specification/index.md)的[后缀增量和减量运算符](~/_csharplang/spec/expressions.md#postfix-increment-and-decrement-operators)和[前缀增量和减量运算符](~/_csharplang/spec/expressions.md#prefix-increment-and-decrement-operators)部分。</span><span class="sxs-lookup"><span data-stu-id="6ccce-115">For more information, see the [Postfix increment and decrement operators](~/_csharplang/spec/expressions.md#postfix-increment-and-decrement-operators) and [Prefix increment and decrement operators](~/_csharplang/spec/expressions.md#prefix-increment-and-decrement-operators) sections of the [C# language specification](../language-specification/index.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="6ccce-116">请参阅</span><span class="sxs-lookup"><span data-stu-id="6ccce-116">See also</span></span>

- [<span data-ttu-id="6ccce-117">C# 参考</span><span class="sxs-lookup"><span data-stu-id="6ccce-117">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="6ccce-118">C# 编程指南</span><span class="sxs-lookup"><span data-stu-id="6ccce-118">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="6ccce-119">C# 运算符</span><span class="sxs-lookup"><span data-stu-id="6ccce-119">C# Operators</span></span>](index.md)
- [<span data-ttu-id="6ccce-120">-- 运算符</span><span class="sxs-lookup"><span data-stu-id="6ccce-120">-- Operator</span></span>](decrement-operator.md)
- [<span data-ttu-id="6ccce-121">如何：递增和递减指针</span><span class="sxs-lookup"><span data-stu-id="6ccce-121">How to: increment and decrement pointers</span></span>](../../programming-guide/unsafe-code-pointers/how-to-increment-and-decrement-pointers.md)
