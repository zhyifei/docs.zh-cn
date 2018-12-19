---
title: / 运算符 - C# 参考
ms.custom: seodec18
ms.date: 12/13/2018
f1_keywords:
- /_CSharpKeyword
helpviewer_keywords:
- / operator [C#]
- division operator [C#]
ms.assetid: d155e496-678f-4efa-bebe-2bd08da2c5af
ms.openlocfilehash: 45bcd64b60e7d13f389064faefeda815ea1f32c9
ms.sourcegitcommit: d6e419f9d9cd7e8f21ebf5acde6d016c16332579
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/12/2018
ms.locfileid: "53286528"
---
# <a name="-operator-c-reference"></a><span data-ttu-id="0774c-102">/ 运算符（C# 参考）</span><span class="sxs-lookup"><span data-stu-id="0774c-102">/ Operator (C# Reference)</span></span>

<span data-ttu-id="0774c-103">除法运算符 `/` 用它的第一个操作数除以第二个操作数。</span><span class="sxs-lookup"><span data-stu-id="0774c-103">The division operator `/` divides its first operand by its second operand.</span></span> <span data-ttu-id="0774c-104">所有数值类型都支持除法运算符。</span><span class="sxs-lookup"><span data-stu-id="0774c-104">All numeric types support the division operator.</span></span>

## <a name="integer-division"></a><span data-ttu-id="0774c-105">整数除法</span><span class="sxs-lookup"><span data-stu-id="0774c-105">Integer division</span></span>

<span data-ttu-id="0774c-106">对于整数类型的操作数，`/` 运算符的结果为整数类型，并且等于两个操作数之商向零舍入后的结果：</span><span class="sxs-lookup"><span data-stu-id="0774c-106">For the operands of integer types, the result of the `/` operator is of an integer type and equals the quotient of the two operands rounded towards zero:</span></span>

[!code-csharp-interactive[integer division](~/samples/snippets/csharp/language-reference/operators/DivisionExamples.cs#Integer)]

<span data-ttu-id="0774c-107">若要获取浮点数形式的两个操作数之商，请使用 `float`、`double` 或 `decimal` 类型：</span><span class="sxs-lookup"><span data-stu-id="0774c-107">To obtain the quotient of the two operands as a floating-point number, use the `float`, `double`, or `decimal` type:</span></span>

[!code-csharp-interactive[integer as floating-point division](~/samples/snippets/csharp/language-reference/operators/DivisionExamples.cs#IntegerAsFloatingPoint)]

## <a name="floating-point-division"></a><span data-ttu-id="0774c-108">浮点除法</span><span class="sxs-lookup"><span data-stu-id="0774c-108">Floating-point division</span></span>

<span data-ttu-id="0774c-109">对于 `float`、`double` 和 `decimal` 类型，`/` 运算符的结果为两个操作数之商：</span><span class="sxs-lookup"><span data-stu-id="0774c-109">For the `float`, `double`, and `decimal` types, the result of the `/` operator is the quotient of the two operands:</span></span>

[!code-csharp-interactive[floating-point division](~/samples/snippets/csharp/language-reference/operators/DivisionExamples.cs#FloatingPoint)]

<span data-ttu-id="0774c-110">如果操作数之一为 `decimal`，那么另一个操作数不得为 `float` 和 `double`，因为 `float` 和 `double` 都无法隐式转换为 `decimal`。</span><span class="sxs-lookup"><span data-stu-id="0774c-110">If one of the operands is `decimal`, another operand can be neither `float` nor `double`, because neither `float` nor `double` is implicitly convertible to `decimal`.</span></span> <span data-ttu-id="0774c-111">必须将 `float` 或 `double` 操作数显式转换为 `decimal` 类型。</span><span class="sxs-lookup"><span data-stu-id="0774c-111">You must explicitly convert the `float` or `double` operand to the `decimal` type.</span></span> <span data-ttu-id="0774c-112">若要详细了解数值类型之间的隐式转换，请参阅[隐式数值转换表](../keywords/implicit-numeric-conversions-table.md)。</span><span class="sxs-lookup"><span data-stu-id="0774c-112">For more information about implicit conversions between numeric types, see [Implicit numeric conversions table](../keywords/implicit-numeric-conversions-table.md).</span></span>

## <a name="operator-overloadability"></a><span data-ttu-id="0774c-113">运算符可重载性</span><span class="sxs-lookup"><span data-stu-id="0774c-113">Operator overloadability</span></span>

<span data-ttu-id="0774c-114">用户定义的类型可以[重载](../keywords/operator.md) `/` 运算符。</span><span class="sxs-lookup"><span data-stu-id="0774c-114">User-defined types can [overload](../keywords/operator.md) the `/` operator.</span></span> <span data-ttu-id="0774c-115">在 `/` 运算符重载后，[除法赋值运算符](division-assignment-operator.md) `/=` 也会隐式重载。</span><span class="sxs-lookup"><span data-stu-id="0774c-115">When the `/` operator is overloaded, the [division assignment operator](division-assignment-operator.md) `/=` is also implicitly overloaded.</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="0774c-116">C# 语言规范</span><span class="sxs-lookup"><span data-stu-id="0774c-116">C# language specification</span></span>

<span data-ttu-id="0774c-117">有关详细信息，请参阅 [C# 语言规范](../language-specification/index.md)的[除法运算符](~/_csharplang/spec/expressions.md#division-operator)部分。</span><span class="sxs-lookup"><span data-stu-id="0774c-117">For more information, see the [Division operator](~/_csharplang/spec/expressions.md#division-operator) section of the [C# language specification](../language-specification/index.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="0774c-118">请参阅</span><span class="sxs-lookup"><span data-stu-id="0774c-118">See also</span></span>

- [<span data-ttu-id="0774c-119">C# 参考</span><span class="sxs-lookup"><span data-stu-id="0774c-119">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="0774c-120">C# 编程指南</span><span class="sxs-lookup"><span data-stu-id="0774c-120">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="0774c-121">C# 运算符</span><span class="sxs-lookup"><span data-stu-id="0774c-121">C# Operators</span></span>](index.md)
- [<span data-ttu-id="0774c-122">% 运算符</span><span class="sxs-lookup"><span data-stu-id="0774c-122">% Operator</span></span>](remainder-operator.md)
