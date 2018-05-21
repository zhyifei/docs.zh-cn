---
title: '&gt;&gt; 运算符（C# 参考）'
ms.date: 07/20/2015
f1_keywords:
- '>>_CSharpKeyword'
helpviewer_keywords:
- '>> operator [C#]'
- right shift operator (>>) [C#]
ms.assetid: a07f8679-d318-4ef8-b38b-65903efb8056
ms.openlocfilehash: 061a69250ef5524fa6b5f7bb4b9527057dd86e05
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
---
# <a name="gtgt-operator-c-reference"></a><span data-ttu-id="883ac-102">&gt;&gt; 运算符（C# 参考）</span><span class="sxs-lookup"><span data-stu-id="883ac-102">&gt;&gt; Operator (C# Reference)</span></span>
<span data-ttu-id="883ac-103">右移运算符 (`>>`) 将第一个操作数向右移动第二个操作数指定的位数。</span><span class="sxs-lookup"><span data-stu-id="883ac-103">The right-shift operator (`>>`) shifts its first operand right by the number of bits specified by its second operand.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="883ac-104">备注</span><span class="sxs-lookup"><span data-stu-id="883ac-104">Remarks</span></span>  
 <span data-ttu-id="883ac-105">如果第一个操作数是 [int](../../../csharp/language-reference/keywords/int.md) 或 [uint](../../../csharp/language-reference/keywords/uint.md)（32 位数），则移位计数由第二个操作数的低序五位给定（第二个操作数 & 0x1f）。</span><span class="sxs-lookup"><span data-stu-id="883ac-105">If the first operand is an [int](../../../csharp/language-reference/keywords/int.md) or [uint](../../../csharp/language-reference/keywords/uint.md) (32-bit quantity), the shift count is given by the low-order five bits of the second operand (second operand & 0x1f).</span></span>  
  
 <span data-ttu-id="883ac-106">如果第一个操作数是 [long](../../../csharp/language-reference/keywords/long.md) 或 [ulong](../../../csharp/language-reference/keywords/ulong.md)（64 位数），则移位计数由第二个操作数的低序六位给定（第二个操作数 & 0x3f）。</span><span class="sxs-lookup"><span data-stu-id="883ac-106">If the first operand is a [long](../../../csharp/language-reference/keywords/long.md) or [ulong](../../../csharp/language-reference/keywords/ulong.md) (64-bit quantity), the shift count is given by the low-order six bits of the second operand (second operand & 0x3f).</span></span>  
  
 <span data-ttu-id="883ac-107">如果第一个操作数是 [int](../../../csharp/language-reference/keywords/int.md) 或 [long](../../../csharp/language-reference/keywords/long.md)，则右移是一种算术移位（高阶空位设置为符号位）。</span><span class="sxs-lookup"><span data-stu-id="883ac-107">If the first operand is an [int](../../../csharp/language-reference/keywords/int.md) or [long](../../../csharp/language-reference/keywords/long.md), the right-shift is an arithmetic shift (high-order empty bits are set to the sign bit).</span></span> <span data-ttu-id="883ac-108">如果第一个操作数的类型为 [uint](../../../csharp/language-reference/keywords/uint.md) 或 [ulong](../../../csharp/language-reference/keywords/ulong.md)，则右移是一种逻辑移位（高序位补零）。</span><span class="sxs-lookup"><span data-stu-id="883ac-108">If the first operand is of type [uint](../../../csharp/language-reference/keywords/uint.md) or [ulong](../../../csharp/language-reference/keywords/ulong.md), the right-shift is a logical shift (high-order bits are zero-filled).</span></span>  
  
 <span data-ttu-id="883ac-109">用户定义的类型可以重载 `>>` 运算符；第一个操作数的类型必须是用户定义的类型，第二个操作数的类型必须是 [int](../../../csharp/language-reference/keywords/int.md)。有关详细信息，请参阅[运算符](../../../csharp/language-reference/keywords/operator.md)。</span><span class="sxs-lookup"><span data-stu-id="883ac-109">User-defined types can overload the `>>` operator; the type of the first operand must be the user-defined type, and the type of the second operand must be [int](../../../csharp/language-reference/keywords/int.md). For more information, see [operator](../../../csharp/language-reference/keywords/operator.md).</span></span> <span data-ttu-id="883ac-110">重载二元运算符时，也会隐式重载相应的赋值运算符（若有）。</span><span class="sxs-lookup"><span data-stu-id="883ac-110">When a binary operator is overloaded, the corresponding assignment operator, if any, is also implicitly overloaded.</span></span>  
  
## <a name="example"></a><span data-ttu-id="883ac-111">示例</span><span class="sxs-lookup"><span data-stu-id="883ac-111">Example</span></span>  
 [!code-csharp[csRefOperators#26](../../../csharp/language-reference/operators/codesnippet/CSharp/right-shift-operator_1.cs)]  
  
## <a name="see-also"></a><span data-ttu-id="883ac-112">请参阅</span><span class="sxs-lookup"><span data-stu-id="883ac-112">See Also</span></span>  
 [<span data-ttu-id="883ac-113">C# 参考</span><span class="sxs-lookup"><span data-stu-id="883ac-113">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
 [<span data-ttu-id="883ac-114">C# 编程指南</span><span class="sxs-lookup"><span data-stu-id="883ac-114">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="883ac-115">C# 运算符</span><span class="sxs-lookup"><span data-stu-id="883ac-115">C# Operators</span></span>](../../../csharp/language-reference/operators/index.md)
