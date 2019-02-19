---
title: << 运算符 - C# 参考
ms.custom: seodec18
ms.date: 02/12/2019
f1_keywords:
- <<_CSharpKeyword
helpviewer_keywords:
- left shift operator (<<) [C#]
- << operator [C#]
ms.assetid: a654eb56-1ff7-4bf3-9064-b631be0cdccc
ms.openlocfilehash: deea2d0f720ba7f096e65c67378586bc88f24673
ms.sourcegitcommit: 30e2fe5cc4165aa6dde7218ec80a13def3255e98
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/13/2019
ms.locfileid: "56219428"
---
# <a name="-operator-c-reference"></a><span data-ttu-id="18883-102">\<\< 运算符（C# 参考）</span><span class="sxs-lookup"><span data-stu-id="18883-102">\<\< operator (C# Reference)</span></span>

<span data-ttu-id="18883-103">左移运算符 `<<` 将第一个操作数向左移动第二个操作数定义的位数。</span><span class="sxs-lookup"><span data-stu-id="18883-103">The left-shift operator `<<` shifts its first operand left by the number of bits defined by its second operand.</span></span> <span data-ttu-id="18883-104">所有整数类型都支持 `<<` 运算符。</span><span class="sxs-lookup"><span data-stu-id="18883-104">All integer types support the `<<` operator.</span></span> <span data-ttu-id="18883-105">但是，第二个操作数的类型必须为 [int](../keywords/int.md) 或[预定义隐式数值转换](../keywords/implicit-numeric-conversions-table.md)为 `int` 的类型。</span><span class="sxs-lookup"><span data-stu-id="18883-105">However, the type of the second operand must be [int](../keywords/int.md) or a type that has a [predefined implicit numeric conversion](../keywords/implicit-numeric-conversions-table.md) to `int`.</span></span>

<span data-ttu-id="18883-106">放弃结果类型范围之外的高顺序位，将低顺序空位位置设置为零，如下例所示：</span><span class="sxs-lookup"><span data-stu-id="18883-106">The high-order bits that are outside the range of the result type are discarded, and the low-order empty bit positions are set to zero, as the following example shows:</span></span>

[!code-csharp-interactive[left shift example](~/samples/snippets/csharp/language-reference/operators/ShiftOperatorsExamples.cs#LeftShift)]

## <a name="shift-count"></a><span data-ttu-id="18883-107">移位计数</span><span class="sxs-lookup"><span data-stu-id="18883-107">Shift count</span></span>

<span data-ttu-id="18883-108">对于表达式 `x << count`，实际移位计数取决于 `x` 的类型，如下所示：</span><span class="sxs-lookup"><span data-stu-id="18883-108">For the expression `x << count`, the actual shift count depends on the type of `x` as follows:</span></span>

- <span data-ttu-id="18883-109">如果 `x` 的类型是 [int](../keywords/int.md) 或 [uint](../keywords/uint.md)，则移位计数由第二个操作数的低顺序五位给定。</span><span class="sxs-lookup"><span data-stu-id="18883-109">If the type of `x` is [int](../keywords/int.md) or [uint](../keywords/uint.md), the shift count is given by the low-order *five* bits of the second operand.</span></span> <span data-ttu-id="18883-110">也就是说，移位计数通过 `count & 0x1F`（或 `count & 0b_1_1111`）计算得出。</span><span class="sxs-lookup"><span data-stu-id="18883-110">That is, the shift count is computed from `count & 0x1F` (or `count & 0b_1_1111`).</span></span>

- <span data-ttu-id="18883-111">如果 `x` 的类型是 [long](../keywords/long.md) 或 [ulong](../keywords/ulong.md)，则移位计数由第二个操作数的低顺序六位给定。</span><span class="sxs-lookup"><span data-stu-id="18883-111">If the type of `x` is [long](../keywords/long.md) or [ulong](../keywords/ulong.md), the shift count is given by the low-order *six* bits of the second operand.</span></span> <span data-ttu-id="18883-112">也就是说，移位计数通过 `count & 0x3F`（或 `count & 0b_11_1111`）计算得出。</span><span class="sxs-lookup"><span data-stu-id="18883-112">That is, the shift count is computed from `count & 0x3F` (or `count & 0b_11_1111`).</span></span>

<span data-ttu-id="18883-113">以下示例演示了该行为：</span><span class="sxs-lookup"><span data-stu-id="18883-113">The following example demonstrates that behavior:</span></span>

[!code-csharp-interactive[shift count example](~/samples/snippets/csharp/language-reference/operators/ShiftOperatorsExamples.cs#LeftShiftByLargeCount)]

## <a name="remarks"></a><span data-ttu-id="18883-114">备注</span><span class="sxs-lookup"><span data-stu-id="18883-114">Remarks</span></span>

<span data-ttu-id="18883-115">移位运算绝对不会导致溢出并在[选中和未选中](../keywords/checked-and-unchecked.md)上下文中产生相同结果。</span><span class="sxs-lookup"><span data-stu-id="18883-115">Shift operations never cause overflows and produce the same results in [checked and unchecked](../keywords/checked-and-unchecked.md) contexts.</span></span>

## <a name="operator-overloadability"></a><span data-ttu-id="18883-116">运算符可重载性</span><span class="sxs-lookup"><span data-stu-id="18883-116">Operator overloadability</span></span>

<span data-ttu-id="18883-117">用户定义的类型可以[重载](../keywords/operator.md) `<<` 运算符。</span><span class="sxs-lookup"><span data-stu-id="18883-117">User-defined types can [overload](../keywords/operator.md) the `<<` operator.</span></span> <span data-ttu-id="18883-118">如果用户定义类型 `T` 重载 `<<` 运算符，则第一个操作数的类型必须是 `T`，第二个操作数的类型必须是 `int`。</span><span class="sxs-lookup"><span data-stu-id="18883-118">If a user-defined type `T` overloads the `<<` operator, the type of the first operand must be `T` and the type of the second operand must be `int`.</span></span> <span data-ttu-id="18883-119">在重载 `<<` 运算符后，还会隐式重载[左移赋值运算符](left-shift-assignment-operator.md) `<<=`。</span><span class="sxs-lookup"><span data-stu-id="18883-119">When the `<<` operator is overloaded, the [left-shift assignment operator](left-shift-assignment-operator.md) `<<=` is also implicitly overloaded.</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="18883-120">C# 语言规范</span><span class="sxs-lookup"><span data-stu-id="18883-120">C# language specification</span></span>

<span data-ttu-id="18883-121">有关详细信息，请参阅 [C# 语言规范](../language-specification/index.md)中的[移位运算符](~/_csharplang/spec/expressions.md#shift-operators)部分。</span><span class="sxs-lookup"><span data-stu-id="18883-121">For more information, see the [Shift operators](~/_csharplang/spec/expressions.md#shift-operators) section of the [C# language specification](../language-specification/index.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="18883-122">请参阅</span><span class="sxs-lookup"><span data-stu-id="18883-122">See also</span></span>

- [<span data-ttu-id="18883-123">C# 参考</span><span class="sxs-lookup"><span data-stu-id="18883-123">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="18883-124">C# 编程指南</span><span class="sxs-lookup"><span data-stu-id="18883-124">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="18883-125">C# 运算符</span><span class="sxs-lookup"><span data-stu-id="18883-125">C# Operators</span></span>](index.md)
- [<span data-ttu-id="18883-126">>> 运算符</span><span class="sxs-lookup"><span data-stu-id="18883-126">>> operator</span></span>](right-shift-operator.md)
