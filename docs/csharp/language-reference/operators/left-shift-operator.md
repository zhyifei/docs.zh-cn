---
title: "&lt;&lt; 运算符（C# 参考）"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- <<_CSharpKeyword
dev_langs:
- CSharp
helpviewer_keywords:
- left shift operator (<<) [C#]
- << operator [C#]
ms.assetid: a654eb56-1ff7-4bf3-9064-b631be0cdccc
caps.latest.revision: 18
author: BillWagner
ms.author: wiwagn
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 4e6ad17232ec4eb087ca300342331af6a30789b1
ms.contentlocale: zh-cn
ms.lasthandoff: 07/28/2017

---
# <a name="ltlt-operator-c-reference"></a><span data-ttu-id="cf12c-102">&lt;&lt; 运算符（C# 参考）</span><span class="sxs-lookup"><span data-stu-id="cf12c-102">&lt;&lt; Operator (C# Reference)</span></span>
<span data-ttu-id="cf12c-103">左移运算符 (`<<`) 将第一个操作数向左移动第二个操作数指定的位数。</span><span class="sxs-lookup"><span data-stu-id="cf12c-103">The left-shift operator (`<<`) shifts its first operand left by the number of bits specified by its second operand.</span></span> <span data-ttu-id="cf12c-104">第二个操作数的类型必须为 [int](../../../csharp/language-reference/keywords/int.md) 或预定义隐式数值转换为 `int` 的类型。</span><span class="sxs-lookup"><span data-stu-id="cf12c-104">The type of the second operand must be an [int](../../../csharp/language-reference/keywords/int.md) or a type that has a predefined implicit numeric conversion to `int`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="cf12c-105">备注</span><span class="sxs-lookup"><span data-stu-id="cf12c-105">Remarks</span></span>  
 <span data-ttu-id="cf12c-106">如果第一个操作数是 [int](../../../csharp/language-reference/keywords/int.md) 或 [uint](../../../csharp/language-reference/keywords/uint.md)（32 位数），则移位计数由第二个操作数的低序五位给定。</span><span class="sxs-lookup"><span data-stu-id="cf12c-106">If the first operand is an [int](../../../csharp/language-reference/keywords/int.md) or [uint](../../../csharp/language-reference/keywords/uint.md) (32-bit quantity), the shift count is given by the low-order five bits of the second operand.</span></span> <span data-ttu-id="cf12c-107">也就是说，实际的移位计数为 0 到 31 位。</span><span class="sxs-lookup"><span data-stu-id="cf12c-107">That is, the actual shift count is 0 to 31 bits.</span></span>  
  
 <span data-ttu-id="cf12c-108">如果第一个操作数是 [long](../../../csharp/language-reference/keywords/long.md) 或 [ulong](../../../csharp/language-reference/keywords/ulong.md)（64 位数），则移位计数由第二个操作数的低序六位给定。</span><span class="sxs-lookup"><span data-stu-id="cf12c-108">If the first operand is a [long](../../../csharp/language-reference/keywords/long.md) or [ulong](../../../csharp/language-reference/keywords/ulong.md) (64-bit quantity), the shift count is given by the low-order six bits of the second operand.</span></span> <span data-ttu-id="cf12c-109">也就是说，实际的移位计数为 0 到 63 位。</span><span class="sxs-lookup"><span data-stu-id="cf12c-109">That is, the actual shift count is 0 to 63 bits.</span></span>  
  
 <span data-ttu-id="cf12c-110">将丢弃移位后不在第一个操作数类型范围内的任何高序位，低序空位补零。</span><span class="sxs-lookup"><span data-stu-id="cf12c-110">Any high-order bits that are not within the range of the type of the first operand after the shift are discarded, and the low-order empty bits are zero-filled.</span></span> <span data-ttu-id="cf12c-111">移位操作从不导致溢位。</span><span class="sxs-lookup"><span data-stu-id="cf12c-111">Shift operations never cause overflows.</span></span>  
  
 <span data-ttu-id="cf12c-112">用户定义的类型可以重载 `<<` 运算符（参阅[运算符](../../../csharp/language-reference/keywords/operator.md)）；第一个操作数的类型必须是用户定义的类型，第二个操作数的类型必须是 `int`。</span><span class="sxs-lookup"><span data-stu-id="cf12c-112">User-defined types can overload the `<<` operator (see [operator](../../../csharp/language-reference/keywords/operator.md)); the type of the first operand must be the user-defined type, and the type of the second operand must be `int`.</span></span> <span data-ttu-id="cf12c-113">重载二元运算符时，也会隐式重载相应的赋值运算符（若有）。</span><span class="sxs-lookup"><span data-stu-id="cf12c-113">When a binary operator is overloaded, the corresponding assignment operator, if any, is also implicitly overloaded.</span></span>  
  
## <a name="example"></a><span data-ttu-id="cf12c-114">示例</span><span class="sxs-lookup"><span data-stu-id="cf12c-114">Example</span></span>  
 <span data-ttu-id="cf12c-115">[!code-cs[csRefOperators#14](../../../csharp/language-reference/operators/codesnippet/CSharp/left-shift-operator_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="cf12c-115">[!code-cs[csRefOperators#14](../../../csharp/language-reference/operators/codesnippet/CSharp/left-shift-operator_1.cs)]</span></span>  
  
## <a name="comments"></a><span data-ttu-id="cf12c-116">注释</span><span class="sxs-lookup"><span data-stu-id="cf12c-116">Comments</span></span>  
 <span data-ttu-id="cf12c-117">请注意，`i<<1` 和 `i<<33` 的结果相同，因为 1 和 33 的低序五位相同。</span><span class="sxs-lookup"><span data-stu-id="cf12c-117">Note that `i<<1` and `i<<33` give the same result, because 1 and 33 have the same low-order five bits.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cf12c-118">另请参阅</span><span class="sxs-lookup"><span data-stu-id="cf12c-118">See Also</span></span>  
 <span data-ttu-id="cf12c-119">[C# 参考](../../../csharp/language-reference/index.md) </span><span class="sxs-lookup"><span data-stu-id="cf12c-119">[C# Reference](../../../csharp/language-reference/index.md) </span></span>  
 <span data-ttu-id="cf12c-120">[C# 编程指南](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="cf12c-120">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 [<span data-ttu-id="cf12c-121">C# 运算符</span><span class="sxs-lookup"><span data-stu-id="cf12c-121">C# Operators</span></span>](../../../csharp/language-reference/operators/index.md)

