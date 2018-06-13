---
title: '| 运算符（C# 参考）'
ms.date: 07/20/2015
f1_keywords:
- '|_CSharpKeyword'
helpviewer_keywords:
- bitwise OR operator [C#]
- '| operator [C#]'
- binary operator (|) [C#]
ms.assetid: 82d6bb78-54c8-40bf-b679-531180ddaf70
ms.openlocfilehash: 7b62af53f0d8b7cba29f4496887717f1726eabf9
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33265682"
---
# <a name="-operator-c-reference"></a><span data-ttu-id="ba9da-102">| 运算符（C# 参考）</span><span class="sxs-lookup"><span data-stu-id="ba9da-102">| Operator (C# Reference)</span></span>
<span data-ttu-id="ba9da-103">针对整型类型和 `bool` 预定义了二元 `|` 运算符。</span><span class="sxs-lookup"><span data-stu-id="ba9da-103">Binary `|` operators are predefined for the integral types and `bool`.</span></span> <span data-ttu-id="ba9da-104">对于整型类型，`|` 会计算其操作数的按位 OR。</span><span class="sxs-lookup"><span data-stu-id="ba9da-104">For integral types, `|` computes the bitwise OR of its operands.</span></span> <span data-ttu-id="ba9da-105">对于 `bool` 操作数，`|` 会计算其操作数的逻辑 OR；即，当且仅当其两个操作数皆为 `false` 时，结果才为 `false`。</span><span class="sxs-lookup"><span data-stu-id="ba9da-105">For `bool` operands, `|` computes the logical OR of its operands; that is, the result is `false` if and only if both its operands are `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ba9da-106">备注</span><span class="sxs-lookup"><span data-stu-id="ba9da-106">Remarks</span></span>  
 <span data-ttu-id="ba9da-107">用户定义的类型可以重载 `|` 运算符（请参阅[运算符](../../../csharp/language-reference/keywords/operator.md)）。</span><span class="sxs-lookup"><span data-stu-id="ba9da-107">User-defined types can overload the `|` operator (see [operator](../../../csharp/language-reference/keywords/operator.md)).</span></span>  
  
## <a name="example"></a><span data-ttu-id="ba9da-108">示例</span><span class="sxs-lookup"><span data-stu-id="ba9da-108">Example</span></span>  
 [!code-csharp[csRefOperators#31](../../../csharp/language-reference/operators/codesnippet/CSharp/or-operator_1.cs)]  
  
## <a name="see-also"></a><span data-ttu-id="ba9da-109">请参阅</span><span class="sxs-lookup"><span data-stu-id="ba9da-109">See Also</span></span>  
 [<span data-ttu-id="ba9da-110">C# 参考</span><span class="sxs-lookup"><span data-stu-id="ba9da-110">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
 [<span data-ttu-id="ba9da-111">C# 编程指南</span><span class="sxs-lookup"><span data-stu-id="ba9da-111">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="ba9da-112">C# 运算符</span><span class="sxs-lookup"><span data-stu-id="ba9da-112">C# Operators</span></span>](../../../csharp/language-reference/operators/index.md)
