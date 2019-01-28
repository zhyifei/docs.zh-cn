---
title: '&gt;&gt; 运算符 - C# 参考'
ms.custom: seodec18
ms.date: 07/20/2015
f1_keywords:
- '>>_CSharpKeyword'
helpviewer_keywords:
- '>> operator [C#]'
- right shift operator (>>) [C#]
ms.assetid: a07f8679-d318-4ef8-b38b-65903efb8056
ms.openlocfilehash: f7cacd740966f0716e125887568a39abf0d9e454
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54725423"
---
# <a name="gtgt-operator-c-reference"></a><span data-ttu-id="cd69f-102">&gt;&gt; 运算符（C# 参考）</span><span class="sxs-lookup"><span data-stu-id="cd69f-102">&gt;&gt; operator (C# Reference)</span></span>

<span data-ttu-id="cd69f-103">右移运算符 (`>>`) 将第一个操作数向右移动第二个操作数指定的位数。</span><span class="sxs-lookup"><span data-stu-id="cd69f-103">The right-shift operator (`>>`) shifts its first operand right by the number of bits specified by its second operand.</span></span>

## <a name="remarks"></a><span data-ttu-id="cd69f-104">备注</span><span class="sxs-lookup"><span data-stu-id="cd69f-104">Remarks</span></span>

<span data-ttu-id="cd69f-105">如果第一个操作数是 [int](../keywords/int.md) 或 [uint](../keywords/uint.md)（32 位数），则移位计数由第二个操作数的低序五位给定（第二个操作数 & 0x1f）。</span><span class="sxs-lookup"><span data-stu-id="cd69f-105">If the first operand is an [int](../keywords/int.md) or [uint](../keywords/uint.md) (32-bit quantity), the shift count is given by the low-order five bits of the second operand (second operand & 0x1f).</span></span>

<span data-ttu-id="cd69f-106">如果第一个操作数是 [long](../keywords/long.md) 或 [ulong](../keywords/ulong.md)（64 位数），则移位计数由第二个操作数的低序六位给定（第二个操作数 & 0x3f）。</span><span class="sxs-lookup"><span data-stu-id="cd69f-106">If the first operand is a [long](../keywords/long.md) or [ulong](../keywords/ulong.md) (64-bit quantity), the shift count is given by the low-order six bits of the second operand (second operand & 0x3f).</span></span>

<span data-ttu-id="cd69f-107">如果第一个操作数是 [int](../keywords/int.md) 或 [long](../keywords/long.md)，则右移是一种算术移位（高阶空位设置为符号位）。</span><span class="sxs-lookup"><span data-stu-id="cd69f-107">If the first operand is an [int](../keywords/int.md) or [long](../keywords/long.md), the right-shift is an arithmetic shift (high-order empty bits are set to the sign bit).</span></span> <span data-ttu-id="cd69f-108">如果第一个操作数的类型为 [uint](../keywords/uint.md) 或 [ulong](../keywords/ulong.md)，则右移是一种逻辑移位（高序位补零）。</span><span class="sxs-lookup"><span data-stu-id="cd69f-108">If the first operand is of type [uint](../keywords/uint.md) or [ulong](../keywords/ulong.md), the right-shift is a logical shift (high-order bits are zero-filled).</span></span>

<span data-ttu-id="cd69f-109">用户定义的类型可以重载 `>>` 运算符；第一个操作数的类型必须是用户定义的类型，第二个操作数的类型必须是 [int](../keywords/int.md)。有关详细信息，请参阅[运算符](../keywords/operator.md)。</span><span class="sxs-lookup"><span data-stu-id="cd69f-109">User-defined types can overload the `>>` operator; the type of the first operand must be the user-defined type, and the type of the second operand must be [int](../keywords/int.md). For more information, see [operator](../keywords/operator.md).</span></span> <span data-ttu-id="cd69f-110">重载二元运算符时，也会隐式重载相应的赋值运算符（若有）。</span><span class="sxs-lookup"><span data-stu-id="cd69f-110">When a binary operator is overloaded, the corresponding assignment operator, if any, is also implicitly overloaded.</span></span>

## <a name="example"></a><span data-ttu-id="cd69f-111">示例</span><span class="sxs-lookup"><span data-stu-id="cd69f-111">Example</span></span>

[!code-csharp[csRefOperators#26](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefOperators/CS/csrefOperators.cs#26)]

## <a name="see-also"></a><span data-ttu-id="cd69f-112">请参阅</span><span class="sxs-lookup"><span data-stu-id="cd69f-112">See also</span></span>

- [<span data-ttu-id="cd69f-113">C# 参考</span><span class="sxs-lookup"><span data-stu-id="cd69f-113">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="cd69f-114">C# 编程指南</span><span class="sxs-lookup"><span data-stu-id="cd69f-114">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="cd69f-115">C# 运算符</span><span class="sxs-lookup"><span data-stu-id="cd69f-115">C# operators</span></span>](index.md)