---
title: '&lt;&lt; 运算符 - C# 参考'
ms.custom: seodec18
ms.date: 07/20/2015
f1_keywords:
- <<_CSharpKeyword
helpviewer_keywords:
- left shift operator (<<) [C#]
- << operator [C#]
ms.assetid: a654eb56-1ff7-4bf3-9064-b631be0cdccc
ms.openlocfilehash: 79a48d88e2c83b5ad78804367ee3c07f78622c08
ms.sourcegitcommit: 5c36aaa8299a2437c155700c810585aff19edbec
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/16/2019
ms.locfileid: "54333520"
---
# <a name="ltlt-operator-c-reference"></a><span data-ttu-id="ea0e4-102">&lt;&lt; 运算符（C# 参考）</span><span class="sxs-lookup"><span data-stu-id="ea0e4-102">&lt;&lt; operator (C# Reference)</span></span>

<span data-ttu-id="ea0e4-103">左移运算符 (`<<`) 将第一个操作数向左移动第二个操作数指定的位数。</span><span class="sxs-lookup"><span data-stu-id="ea0e4-103">The left-shift operator (`<<`) shifts its first operand left by the number of bits specified by its second operand.</span></span> <span data-ttu-id="ea0e4-104">第二个操作数的类型必须为 [int](../keywords/int.md) 或预定义隐式数值转换为 `int` 的类型。</span><span class="sxs-lookup"><span data-stu-id="ea0e4-104">The type of the second operand must be an [int](../keywords/int.md) or a type that has a predefined implicit numeric conversion to `int`.</span></span>

## <a name="remarks"></a><span data-ttu-id="ea0e4-105">备注</span><span class="sxs-lookup"><span data-stu-id="ea0e4-105">Remarks</span></span>

<span data-ttu-id="ea0e4-106">如果第一个操作数是 [int](../keywords/int.md) 或 [uint](../keywords/uint.md)（32 位数），则移位计数由第二个操作数的低序五位给定。</span><span class="sxs-lookup"><span data-stu-id="ea0e4-106">If the first operand is an [int](../keywords/int.md) or [uint](../keywords/uint.md) (32-bit quantity), the shift count is given by the low-order five bits of the second operand.</span></span> <span data-ttu-id="ea0e4-107">也就是说，实际的移位计数为 0 到 31 位。</span><span class="sxs-lookup"><span data-stu-id="ea0e4-107">That is, the actual shift count is 0 to 31 bits.</span></span>

<span data-ttu-id="ea0e4-108">如果第一个操作数是 [long](../keywords/long.md) 或 [ulong](../keywords/ulong.md)（64 位数），则移位计数由第二个操作数的低序六位给定。</span><span class="sxs-lookup"><span data-stu-id="ea0e4-108">If the first operand is a [long](../keywords/long.md) or [ulong](../keywords/ulong.md) (64-bit quantity), the shift count is given by the low-order six bits of the second operand.</span></span> <span data-ttu-id="ea0e4-109">也就是说，实际的移位计数为 0 到 63 位。</span><span class="sxs-lookup"><span data-stu-id="ea0e4-109">That is, the actual shift count is 0 to 63 bits.</span></span>

<span data-ttu-id="ea0e4-110">将丢弃移位后不在第一个操作数类型范围内的任何高序位，低序空位补零。</span><span class="sxs-lookup"><span data-stu-id="ea0e4-110">Any high-order bits that are not within the range of the type of the first operand after the shift are discarded, and the low-order empty bits are zero-filled.</span></span> <span data-ttu-id="ea0e4-111">移位操作从不导致溢位。</span><span class="sxs-lookup"><span data-stu-id="ea0e4-111">Shift operations never cause overflows.</span></span>

<span data-ttu-id="ea0e4-112">用户定义的类型可以重载 `<<` 运算符（参阅[运算符](../keywords/operator.md)）；第一个操作数的类型必须是用户定义的类型，第二个操作数的类型必须是 `int`。</span><span class="sxs-lookup"><span data-stu-id="ea0e4-112">User-defined types can overload the `<<` operator (see [operator](../keywords/operator.md)); the type of the first operand must be the user-defined type, and the type of the second operand must be `int`.</span></span> <span data-ttu-id="ea0e4-113">重载二元运算符时，也会隐式重载相应的赋值运算符（若有）。</span><span class="sxs-lookup"><span data-stu-id="ea0e4-113">When a binary operator is overloaded, the corresponding assignment operator, if any, is also implicitly overloaded.</span></span>

## <a name="example"></a><span data-ttu-id="ea0e4-114">示例</span><span class="sxs-lookup"><span data-stu-id="ea0e4-114">Example</span></span>

[!code-csharp[csRefOperators#14](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefOperators/CS/csrefOperators.cs#14)]

## <a name="comments"></a><span data-ttu-id="ea0e4-115">注释</span><span class="sxs-lookup"><span data-stu-id="ea0e4-115">Comments</span></span>

<span data-ttu-id="ea0e4-116">请注意，`i<<1` 和 `i<<33` 的结果相同，因为 1 和 33 的低序五位相同。</span><span class="sxs-lookup"><span data-stu-id="ea0e4-116">Note that `i<<1` and `i<<33` give the same result, because 1 and 33 have the same low-order five bits.</span></span>

## <a name="see-also"></a><span data-ttu-id="ea0e4-117">请参阅</span><span class="sxs-lookup"><span data-stu-id="ea0e4-117">See also</span></span>

- [<span data-ttu-id="ea0e4-118">C# 参考</span><span class="sxs-lookup"><span data-stu-id="ea0e4-118">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="ea0e4-119">C# 编程指南</span><span class="sxs-lookup"><span data-stu-id="ea0e4-119">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="ea0e4-120">C# 运算符</span><span class="sxs-lookup"><span data-stu-id="ea0e4-120">C# Operators</span></span>](index.md)
