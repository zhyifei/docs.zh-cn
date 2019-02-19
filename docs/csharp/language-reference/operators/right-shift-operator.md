---
title: '>> 运算符 - C# 参考'
ms.custom: seodec18
ms.date: 02/12/2019
f1_keywords:
- '>>_CSharpKeyword'
helpviewer_keywords:
- '>> operator [C#]'
- right shift operator (>>) [C#]
ms.assetid: a07f8679-d318-4ef8-b38b-65903efb8056
ms.openlocfilehash: 809cd2cab29d3378892ea224cf846e9d0909b073
ms.sourcegitcommit: 30e2fe5cc4165aa6dde7218ec80a13def3255e98
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/13/2019
ms.locfileid: "56219719"
---
# <a name="-operator-c-reference"></a><span data-ttu-id="92228-102">>> 运算符（C# 参考）</span><span class="sxs-lookup"><span data-stu-id="92228-102">>> operator (C# Reference)</span></span>

<span data-ttu-id="92228-103">右移运算符 `>>` 将第一个操作数向右移动第二个操作数定义的位数。</span><span class="sxs-lookup"><span data-stu-id="92228-103">The right-shift operator `>>` shifts its first operand right by the number of bits defined by its second operand.</span></span> <span data-ttu-id="92228-104">所有整数类型都支持 `>>` 运算符。</span><span class="sxs-lookup"><span data-stu-id="92228-104">All integer types support the `>>` operator.</span></span> <span data-ttu-id="92228-105">但是，第二个操作数的类型必须为 [int](../keywords/int.md) 或[预定义隐式数值转换](../keywords/implicit-numeric-conversions-table.md)为 `int` 的类型。</span><span class="sxs-lookup"><span data-stu-id="92228-105">However, the type of the second operand must be [int](../keywords/int.md) or a type that has a [predefined implicit numeric conversion](../keywords/implicit-numeric-conversions-table.md) to `int`.</span></span>

<span data-ttu-id="92228-106">右移运算将放弃低顺序位。</span><span class="sxs-lookup"><span data-stu-id="92228-106">The right-shift operation discards the low-order bits.</span></span> <span data-ttu-id="92228-107">高顺序空位位置是根据第一个操作数类型设置的，如下所示：</span><span class="sxs-lookup"><span data-stu-id="92228-107">The high-order empty bit positions are set based on the type of the first operand as follows:</span></span>

- <span data-ttu-id="92228-108">如果第一个操作数的类型是 [int](../keywords/int.md) 或 [long](../keywords/long.md)，右移运算符将执行算术移位：第一个操作数的最高有效位（符号位）的值将传播到高顺序空位位置。</span><span class="sxs-lookup"><span data-stu-id="92228-108">If the first operand is of type [int](../keywords/int.md) or [long](../keywords/long.md), the right-shift operator performs an **arithmetic** shift: the value of the most significant bit (the sign bit) of the first operand is propagated to the high-order empty bit positions.</span></span> <span data-ttu-id="92228-109">也就是说，如果第一个操作数为非负，高顺序空位位置设置为零，如果为负，则将该位置设置为 1。</span><span class="sxs-lookup"><span data-stu-id="92228-109">That is, the high-order empty bit positions are set to zero if the first operand is non-negative and set to one if it's negative.</span></span>

- <span data-ttu-id="92228-110">如果第一个操作数的类型是 [uint](../keywords/uint.md) 或 [ulong](../keywords/ulong.md)，则右移运算符执行逻辑移位：高顺序空位位置始终设置为零。</span><span class="sxs-lookup"><span data-stu-id="92228-110">If the first operand is of type [uint](../keywords/uint.md) or [ulong](../keywords/ulong.md), the right-shift operator performs a **logical** shift: the high-order empty bit positions are always set to zero.</span></span>

<span data-ttu-id="92228-111">以下示例演示了该行为：</span><span class="sxs-lookup"><span data-stu-id="92228-111">The following example demonstrates that behavior:</span></span>

[!code-csharp-interactive[right shift example](~/samples/snippets/csharp/language-reference/operators/ShiftOperatorsExamples.cs#RightShift)]

## <a name="shift-count"></a><span data-ttu-id="92228-112">移位计数</span><span class="sxs-lookup"><span data-stu-id="92228-112">Shift count</span></span>

<span data-ttu-id="92228-113">对于表达式 `x >> count`，实际移位计数取决于 `x` 的类型，如下所示：</span><span class="sxs-lookup"><span data-stu-id="92228-113">For the expression `x >> count`, the actual shift count depends on the type of `x` as follows:</span></span>

- <span data-ttu-id="92228-114">如果 `x` 的类型是 [int](../keywords/int.md) 或 [uint](../keywords/uint.md)，则移位计数由第二个操作数的低顺序五位给定。</span><span class="sxs-lookup"><span data-stu-id="92228-114">If the type of `x` is [int](../keywords/int.md) or [uint](../keywords/uint.md), the shift count is given by the low-order *five* bits of the second operand.</span></span> <span data-ttu-id="92228-115">也就是说，移位计数通过 `count & 0x1F`（或 `count & 0b_1_1111`）计算得出。</span><span class="sxs-lookup"><span data-stu-id="92228-115">That is, the shift count is computed from `count & 0x1F` (or `count & 0b_1_1111`).</span></span>

- <span data-ttu-id="92228-116">如果 `x` 的类型是 [long](../keywords/long.md) 或 [ulong](../keywords/ulong.md)，则移位计数由第二个操作数的低顺序六位给定。</span><span class="sxs-lookup"><span data-stu-id="92228-116">If the type of `x` is [long](../keywords/long.md) or [ulong](../keywords/ulong.md), the shift count is given by the low-order *six* bits of the second operand.</span></span> <span data-ttu-id="92228-117">也就是说，移位计数通过 `count & 0x3F`（或 `count & 0b_11_1111`）计算得出。</span><span class="sxs-lookup"><span data-stu-id="92228-117">That is, the shift count is computed from `count & 0x3F` (or `count & 0b_11_1111`).</span></span>

<span data-ttu-id="92228-118">以下示例演示了该行为：</span><span class="sxs-lookup"><span data-stu-id="92228-118">The following example demonstrates that behavior:</span></span>

[!code-csharp-interactive[shift count example](~/samples/snippets/csharp/language-reference/operators/ShiftOperatorsExamples.cs#RightShiftByLargeCount)]

## <a name="remarks"></a><span data-ttu-id="92228-119">备注</span><span class="sxs-lookup"><span data-stu-id="92228-119">Remarks</span></span>

<span data-ttu-id="92228-120">移位运算绝对不会导致溢出并在[选中和未选中](../keywords/checked-and-unchecked.md)上下文中产生相同结果。</span><span class="sxs-lookup"><span data-stu-id="92228-120">Shift operations never cause overflows and produce the same results in [checked and unchecked](../keywords/checked-and-unchecked.md) contexts.</span></span>

## <a name="operator-overloadability"></a><span data-ttu-id="92228-121">运算符可重载性</span><span class="sxs-lookup"><span data-stu-id="92228-121">Operator overloadability</span></span>

<span data-ttu-id="92228-122">用户定义的类型可以[重载](../keywords/operator.md) `>>` 运算符。</span><span class="sxs-lookup"><span data-stu-id="92228-122">User-defined types can [overload](../keywords/operator.md) the `>>` operator.</span></span> <span data-ttu-id="92228-123">如果用户定义的类型 `T` 重载 `>>` 运算符，则第一个操作数的类型必须是 `T`，第二个操作数的类型必须是 `int`。</span><span class="sxs-lookup"><span data-stu-id="92228-123">If a user-defined type `T` overloads the `>>` operator, the type of the first operand must be `T` and the type of the second operand must be `int`.</span></span> <span data-ttu-id="92228-124">在重载 `>>` 运算符后，也会隐式重载[右移赋值运算符](right-shift-assignment-operator.md) `>>=`。</span><span class="sxs-lookup"><span data-stu-id="92228-124">When the `>>` operator is overloaded, the [right-shift assignment operator](right-shift-assignment-operator.md) `>>=` is also implicitly overloaded.</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="92228-125">C# 语言规范</span><span class="sxs-lookup"><span data-stu-id="92228-125">C# language specification</span></span>

<span data-ttu-id="92228-126">有关详细信息，请参阅 [C# 语言规范](../language-specification/index.md)中的[移位运算符](~/_csharplang/spec/expressions.md#shift-operators)部分。</span><span class="sxs-lookup"><span data-stu-id="92228-126">For more information, see the [Shift operators](~/_csharplang/spec/expressions.md#shift-operators) section of the [C# language specification](../language-specification/index.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="92228-127">请参阅</span><span class="sxs-lookup"><span data-stu-id="92228-127">See also</span></span>

- [<span data-ttu-id="92228-128">C# 参考</span><span class="sxs-lookup"><span data-stu-id="92228-128">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="92228-129">C# 编程指南</span><span class="sxs-lookup"><span data-stu-id="92228-129">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="92228-130">C# 运算符</span><span class="sxs-lookup"><span data-stu-id="92228-130">C# operators</span></span>](index.md)
- [<span data-ttu-id="92228-131"><< 运算符</span><span class="sxs-lookup"><span data-stu-id="92228-131"><< operator</span></span>](left-shift-operator.md)