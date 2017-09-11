---
title: "~ 运算符（C# 参考）"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- ~_CSharpKeyword
dev_langs:
- CSharp
helpviewer_keywords:
- tilde (~) one's complement operator [C#]
- ~ operator [C#]
- ~ [C#], bitwise complement operator
- bitwise complement operator [C#]
ms.assetid: 11bc078a-50e2-4d7e-9896-67ef669dc602
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
ms.openlocfilehash: ffbfc379b7c021ccd8fbed9b796aa9fda6618b55
ms.contentlocale: zh-cn
ms.lasthandoff: 07/28/2017

---
# <a name="-operator-c-reference"></a><span data-ttu-id="38a7d-102">~ 运算符（C# 参考）</span><span class="sxs-lookup"><span data-stu-id="38a7d-102">~ Operator (C# Reference)</span></span>
<span data-ttu-id="38a7d-103">`~` 运算符对其操作数执行按位求补运算，这对反转每一个位都有影响。</span><span class="sxs-lookup"><span data-stu-id="38a7d-103">The `~` operator performs a bitwise complement operation on its operand, which has the effect of reversing each bit.</span></span> <span data-ttu-id="38a7d-104">按位求补运算符针对 [int](../../../csharp/language-reference/keywords/int.md)、[uint](../../../csharp/language-reference/keywords/uint.md)、[long](../../../csharp/language-reference/keywords/long.md) 和 [ulong](../../../csharp/language-reference/keywords/ulong.md) 进行了预定义。</span><span class="sxs-lookup"><span data-stu-id="38a7d-104">Bitwise complement operators are predefined for [int](../../../csharp/language-reference/keywords/int.md), [uint](../../../csharp/language-reference/keywords/uint.md), [long](../../../csharp/language-reference/keywords/long.md), and [ulong](../../../csharp/language-reference/keywords/ulong.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="38a7d-105">`~` 符号还用于声明终结器。</span><span class="sxs-lookup"><span data-stu-id="38a7d-105">The `~` symbol also is used to declare finalizers.</span></span> <span data-ttu-id="38a7d-106">有关详细信息，请参阅[终结器](../../../csharp/programming-guide/classes-and-structs/destructors.md)。</span><span class="sxs-lookup"><span data-stu-id="38a7d-106">For more information, see [Finalizers](../../../csharp/programming-guide/classes-and-structs/destructors.md).</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="38a7d-107">备注</span><span class="sxs-lookup"><span data-stu-id="38a7d-107">Remarks</span></span>  
 <span data-ttu-id="38a7d-108">用户定义的类型可以重载 `~` 运算符。</span><span class="sxs-lookup"><span data-stu-id="38a7d-108">User-defined types can overload the `~` operator.</span></span> <span data-ttu-id="38a7d-109">有关详细信息，请参阅[运算符](../../../csharp/language-reference/keywords/operator.md)。</span><span class="sxs-lookup"><span data-stu-id="38a7d-109">For more information, see [operator](../../../csharp/language-reference/keywords/operator.md).</span></span> <span data-ttu-id="38a7d-110">对整数类型的操作通常可用于枚举。</span><span class="sxs-lookup"><span data-stu-id="38a7d-110">Operations on integral types are generally allowed on enumeration.</span></span>  
  
## <a name="example"></a><span data-ttu-id="38a7d-111">示例</span><span class="sxs-lookup"><span data-stu-id="38a7d-111">Example</span></span>  
 <span data-ttu-id="38a7d-112">[!code-cs[csRefOperators#25](../../../csharp/language-reference/operators/codesnippet/CSharp/bitwise-complement-operator_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="38a7d-112">[!code-cs[csRefOperators#25](../../../csharp/language-reference/operators/codesnippet/CSharp/bitwise-complement-operator_1.cs)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="38a7d-113">另请参阅</span><span class="sxs-lookup"><span data-stu-id="38a7d-113">See Also</span></span>  
 <span data-ttu-id="38a7d-114">[C# 参考](../../../csharp/language-reference/index.md) </span><span class="sxs-lookup"><span data-stu-id="38a7d-114">[C# Reference](../../../csharp/language-reference/index.md) </span></span>  
 <span data-ttu-id="38a7d-115">[C# 编程指南](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="38a7d-115">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 <span data-ttu-id="38a7d-116">[C# 运算符](../../../csharp/language-reference/operators/index.md) </span><span class="sxs-lookup"><span data-stu-id="38a7d-116">[C# Operators](../../../csharp/language-reference/operators/index.md) </span></span>  
 [<span data-ttu-id="38a7d-117">终结器</span><span class="sxs-lookup"><span data-stu-id="38a7d-117">Finalizers</span></span>](../../../csharp/programming-guide/classes-and-structs/destructors.md)

