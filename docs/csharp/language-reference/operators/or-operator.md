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
ms.openlocfilehash: d95fe29aa7ffab9938e8edc57999445268fe41a8
ms.sourcegitcommit: 64f4baed249341e5bf64d1385bf48e3f2e1a0211
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/07/2018
ms.locfileid: "44085700"
---
# <a name="-operator-c-reference"></a><span data-ttu-id="a2bf5-102">| 运算符（C# 参考）</span><span class="sxs-lookup"><span data-stu-id="a2bf5-102">| Operator (C# Reference)</span></span>
<span data-ttu-id="a2bf5-103">针对整型类型和 `bool` 预定义了二元 `|` 运算符。</span><span class="sxs-lookup"><span data-stu-id="a2bf5-103">Binary `|` operators are predefined for the integral types and `bool`.</span></span> <span data-ttu-id="a2bf5-104">对于整型类型，`|` 会计算其操作数的按位 OR。</span><span class="sxs-lookup"><span data-stu-id="a2bf5-104">For integral types, `|` computes the bitwise OR of its operands.</span></span> <span data-ttu-id="a2bf5-105">对于 `bool` 操作数，`|` 会计算其操作数的逻辑 OR；即，当且仅当其两个操作数皆为 `false` 时，结果才为 `false`。</span><span class="sxs-lookup"><span data-stu-id="a2bf5-105">For `bool` operands, `|` computes the logical OR of its operands; that is, the result is `false` if and only if both its operands are `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="a2bf5-106">备注</span><span class="sxs-lookup"><span data-stu-id="a2bf5-106">Remarks</span></span>  
 <span data-ttu-id="a2bf5-107">二元 `|` 运算符计算两个操作数，无论第一个操作数的值是什么。这与 [conditional-OR operator] (conditional-or-operator.md) `||` 相反。</span><span class="sxs-lookup"><span data-stu-id="a2bf5-107">The binary `|` operator evaluates both operands regardless of the first one's value, in contrast to the [conditional-OR operator]     (conditional-or-operator.md) `||`.</span></span>
 
 <span data-ttu-id="a2bf5-108">用户定义的类型可以重载 `|` 运算符（请参阅[运算符](../../../csharp/language-reference/keywords/operator.md)）。</span><span class="sxs-lookup"><span data-stu-id="a2bf5-108">User-defined types can overload the `|` operator (see [operator](../../../csharp/language-reference/keywords/operator.md)).</span></span>  
  
## <a name="example"></a><span data-ttu-id="a2bf5-109">示例</span><span class="sxs-lookup"><span data-stu-id="a2bf5-109">Example</span></span>  
 [!code-csharp[csRefOperators#31](../../../csharp/language-reference/operators/codesnippet/CSharp/or-operator_1.cs)]  
  
## <a name="see-also"></a><span data-ttu-id="a2bf5-110">请参阅</span><span class="sxs-lookup"><span data-stu-id="a2bf5-110">See Also</span></span>

- [<span data-ttu-id="a2bf5-111">C# 参考</span><span class="sxs-lookup"><span data-stu-id="a2bf5-111">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
- [<span data-ttu-id="a2bf5-112">C# 编程指南</span><span class="sxs-lookup"><span data-stu-id="a2bf5-112">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
- [<span data-ttu-id="a2bf5-113">C# 运算符</span><span class="sxs-lookup"><span data-stu-id="a2bf5-113">C# Operators</span></span>](../../../csharp/language-reference/operators/index.md)
