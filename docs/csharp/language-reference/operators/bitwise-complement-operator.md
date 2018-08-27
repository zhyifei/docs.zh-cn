---
title: ~ 运算符（C# 参考）
ms.date: 07/20/2015
f1_keywords:
- ~_CSharpKeyword
helpviewer_keywords:
- tilde (~) one's complement operator [C#]
- ~ operator [C#]
- ~ [C#], bitwise complement operator
- bitwise complement operator [C#]
ms.assetid: 11bc078a-50e2-4d7e-9896-67ef669dc602
ms.openlocfilehash: 8af25217f9e7e66796192783a0b8e3415604dc90
ms.sourcegitcommit: e614e0f3b031293e4107f37f752be43652f3f253
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/26/2018
ms.locfileid: "42933177"
---
# <a name="-operator-c-reference"></a><span data-ttu-id="1625f-102">~ 运算符（C# 参考）</span><span class="sxs-lookup"><span data-stu-id="1625f-102">~ Operator (C# Reference)</span></span>
<span data-ttu-id="1625f-103">`~` 运算符对其操作数执行按位求补运算，这对反转每一个位都有影响。</span><span class="sxs-lookup"><span data-stu-id="1625f-103">The `~` operator performs a bitwise complement operation on its operand, which has the effect of reversing each bit.</span></span> <span data-ttu-id="1625f-104">按位求补运算符针对 [int](../../../csharp/language-reference/keywords/int.md)、[uint](../../../csharp/language-reference/keywords/uint.md)、[long](../../../csharp/language-reference/keywords/long.md) 和 [ulong](../../../csharp/language-reference/keywords/ulong.md) 进行了预定义。</span><span class="sxs-lookup"><span data-stu-id="1625f-104">Bitwise complement operators are predefined for [int](../../../csharp/language-reference/keywords/int.md), [uint](../../../csharp/language-reference/keywords/uint.md), [long](../../../csharp/language-reference/keywords/long.md), and [ulong](../../../csharp/language-reference/keywords/ulong.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="1625f-105">`~` 符号还用于声明终结器。</span><span class="sxs-lookup"><span data-stu-id="1625f-105">The `~` symbol also is used to declare finalizers.</span></span> <span data-ttu-id="1625f-106">有关详细信息，请参阅[终结器](../../../csharp/programming-guide/classes-and-structs/destructors.md)。</span><span class="sxs-lookup"><span data-stu-id="1625f-106">For more information, see [Finalizers](../../../csharp/programming-guide/classes-and-structs/destructors.md).</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="1625f-107">备注</span><span class="sxs-lookup"><span data-stu-id="1625f-107">Remarks</span></span>  
 <span data-ttu-id="1625f-108">用户定义的类型可以重载 `~` 运算符。</span><span class="sxs-lookup"><span data-stu-id="1625f-108">User-defined types can overload the `~` operator.</span></span> <span data-ttu-id="1625f-109">有关详细信息，请参阅[运算符](../../../csharp/language-reference/keywords/operator.md)。</span><span class="sxs-lookup"><span data-stu-id="1625f-109">For more information, see [operator](../../../csharp/language-reference/keywords/operator.md).</span></span> <span data-ttu-id="1625f-110">对整数类型的操作通常可用于枚举。</span><span class="sxs-lookup"><span data-stu-id="1625f-110">Operations on integral types are generally allowed on enumeration.</span></span>  
  
## <a name="example"></a><span data-ttu-id="1625f-111">示例</span><span class="sxs-lookup"><span data-stu-id="1625f-111">Example</span></span>  
 [!code-csharp[csRefOperators#25](../../../csharp/language-reference/operators/codesnippet/CSharp/bitwise-complement-operator_1.cs)]  
  
## <a name="see-also"></a><span data-ttu-id="1625f-112">请参阅</span><span class="sxs-lookup"><span data-stu-id="1625f-112">See Also</span></span>

- [<span data-ttu-id="1625f-113">C# 参考</span><span class="sxs-lookup"><span data-stu-id="1625f-113">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
- [<span data-ttu-id="1625f-114">C# 编程指南</span><span class="sxs-lookup"><span data-stu-id="1625f-114">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
- [<span data-ttu-id="1625f-115">C# 运算符</span><span class="sxs-lookup"><span data-stu-id="1625f-115">C# Operators</span></span>](../../../csharp/language-reference/operators/index.md)  
- [<span data-ttu-id="1625f-116">终结器</span><span class="sxs-lookup"><span data-stu-id="1625f-116">Finalizers</span></span>](../../../csharp/programming-guide/classes-and-structs/destructors.md)
