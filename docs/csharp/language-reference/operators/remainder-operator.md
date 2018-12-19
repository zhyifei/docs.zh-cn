---
title: '% 运算符 - C# 参考'
ms.custom: seodec18
ms.date: 09/04/2018
f1_keywords:
- '%_CSharpKeyword'
helpviewer_keywords:
- remainder operator [C#]
- '% operator [C#]'
ms.assetid: 3b74f4f9-fd9c-45e7-84fa-c8d71a0dfad7
ms.openlocfilehash: a5c12b6683e35cc1ec2d40446dd0ed068c3d2552
ms.sourcegitcommit: bdd930b5df20a45c29483d905526a2a3e4d17c5b
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2018
ms.locfileid: "53236474"
---
# <a name="-operator-c-reference"></a><span data-ttu-id="393f1-102">% 运算符（C# 参考）</span><span class="sxs-lookup"><span data-stu-id="393f1-102">% Operator (C# Reference)</span></span>

<span data-ttu-id="393f1-103">余数运算符 `%` 计算第一个操作数除以第二个操作数后的余数。</span><span class="sxs-lookup"><span data-stu-id="393f1-103">The remainder operator `%` computes the remainder after dividing its first operand by its second operand.</span></span>

<span data-ttu-id="393f1-104">用户定义的类型可以[重载](../keywords/operator.md) `%` 运算符。</span><span class="sxs-lookup"><span data-stu-id="393f1-104">User-defined types can [overload](../keywords/operator.md) the `%` operator.</span></span> <span data-ttu-id="393f1-105">当 `%` 重载时，[余数赋值运算符](remainder-assignment-operator.md) `%=` 也会隐式重载。</span><span class="sxs-lookup"><span data-stu-id="393f1-105">When the `%` is overloaded, the [remainder assignment operator](remainder-assignment-operator.md) `%=` is also implicitly overloaded.</span></span>

<span data-ttu-id="393f1-106">所有数值类型都支持余数运算符。</span><span class="sxs-lookup"><span data-stu-id="393f1-106">All numeric types support the remainder operator.</span></span>

## <a name="integer-remainder"></a><span data-ttu-id="393f1-107">整数余数</span><span class="sxs-lookup"><span data-stu-id="393f1-107">Integer remainder</span></span>
  
<span data-ttu-id="393f1-108">对于整数操作数，`a % b` 的结果是由 `a - (a / b) * b` 生成的值。</span><span class="sxs-lookup"><span data-stu-id="393f1-108">For the integer operands, the result of `a % b` is the value produced by `a - (a / b) * b`.</span></span> <span data-ttu-id="393f1-109">非零余数的符号与第一个操作数的符号相同，如下例所示：</span><span class="sxs-lookup"><span data-stu-id="393f1-109">The sign of the non-zero remainder is the same as that of the first operand, as the following example shows:</span></span>

[!code-csharp-interactive[integer remainder](~/samples/snippets/csharp/language-reference/operators/RemainderExamples.cs#1)]

## <a name="floating-point-remainder"></a><span data-ttu-id="393f1-110">浮点余数</span><span class="sxs-lookup"><span data-stu-id="393f1-110">Floating-point remainder</span></span>

<span data-ttu-id="393f1-111">对于[浮点](../keywords/float.md)和[双精度型](../keywords/double.md)操作数，有限的 `x` 和 `y` 的 `x % y` 的结果是值 `z`，使得</span><span class="sxs-lookup"><span data-stu-id="393f1-111">For the [float](../keywords/float.md) and [double](../keywords/double.md) operands, the result of `x % y` for the finite `x` and `y` is the value `z` such that</span></span>

- <span data-ttu-id="393f1-112">如果不是零，则 `z` 的符号与 `x` 的符号相同；</span><span class="sxs-lookup"><span data-stu-id="393f1-112">the sign of `z`, if non-zero, is the same as the sign of `x`;</span></span>
- <span data-ttu-id="393f1-113">`z` 的绝对值是 `|x| - n * |y|` 生成的值，其中 `n` 是小于或等于 `|x| / |y|` 的最大可能整数，`|x|` 和 `|y|` 分别是 `x` 和 `y` 的绝对值。</span><span class="sxs-lookup"><span data-stu-id="393f1-113">the absolute value of `z` is the value produced by `|x| - n * |y|` where `n` is the largest possible integer that is less than or equal to `|x| / |y|` and `|x|` and `|y|` are the absolute values of `x` and `y`, respectively.</span></span>

<span data-ttu-id="393f1-114">有关非限定操作数的 `%` 运算符行为的信息，请参阅 [C# 语言规范](../language-specification/index.md)的[余数运算符](~/_csharplang/spec/expressions.md#remainder-operator)章节。</span><span class="sxs-lookup"><span data-stu-id="393f1-114">For information about the behavior of the `%` operator with non-finite operands, see the [Remainder operator](~/_csharplang/spec/expressions.md#remainder-operator) section of the [C# language specification](../language-specification/index.md).</span></span>

> [!NOTE]
> <span data-ttu-id="393f1-115">计算余数的此方法类似于用于整数操作数的方法，但与 IEEE 754 不同。</span><span class="sxs-lookup"><span data-stu-id="393f1-115">This method of computing the remainder is analogous to that used for integer operands, but differs from the IEEE 754.</span></span> <span data-ttu-id="393f1-116">如果需要符合 IEEE 754 的余数运算，使用 <xref:System.Math.IEEERemainder%2A?displayProperty=nameWithType> 方法。</span><span class="sxs-lookup"><span data-stu-id="393f1-116">If you need the remainder operation that complies with the IEEE 754, use the <xref:System.Math.IEEERemainder%2A?displayProperty=nameWithType> method.</span></span>

<span data-ttu-id="393f1-117">下面的示例演示 `float` 和 `double` 操作数的余数运算符的行为：</span><span class="sxs-lookup"><span data-stu-id="393f1-117">The following example demonstrates the behavior of the remainder operator for `float` and `double` operands:</span></span>

[!code-csharp-interactive[float and double remainder](~/samples/snippets/csharp/language-reference/operators/RemainderExamples.cs#2)]

<span data-ttu-id="393f1-118">请注意与浮点类型相关联的舍入错误。</span><span class="sxs-lookup"><span data-stu-id="393f1-118">Note the round-off errors that can be associated with the floating-point types.</span></span>

<span data-ttu-id="393f1-119">有关[十进制](../keywords/decimal.md)操作数，余数运算符 `%` 等效于 <xref:System.Decimal?displayProperty=nameWithType> 类型的[余数运算符](<xref:System.Decimal.op_Modulus(System.Decimal,System.Decimal)>)。</span><span class="sxs-lookup"><span data-stu-id="393f1-119">For the [decimal](../keywords/decimal.md) operands, the remainder operator `%` is equivalent to the [remainder operator](<xref:System.Decimal.op_Modulus(System.Decimal,System.Decimal)>) of the <xref:System.Decimal?displayProperty=nameWithType> type.</span></span>

## <a name="see-also"></a><span data-ttu-id="393f1-120">请参阅</span><span class="sxs-lookup"><span data-stu-id="393f1-120">See also</span></span>

- [<span data-ttu-id="393f1-121">C# 参考</span><span class="sxs-lookup"><span data-stu-id="393f1-121">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="393f1-122">C# 编程指南</span><span class="sxs-lookup"><span data-stu-id="393f1-122">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="393f1-123">C# 运算符</span><span class="sxs-lookup"><span data-stu-id="393f1-123">C# Operators</span></span>](index.md)
- <xref:System.Math.IEEERemainder%2A?displayProperty=nameWithType>
- <xref:System.Math.DivRem%2A?displayProperty=nameWithType>
