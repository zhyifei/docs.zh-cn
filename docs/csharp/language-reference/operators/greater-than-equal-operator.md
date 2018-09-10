---
title: '&gt;= 运算符（C# 参考）'
ms.date: 07/20/2015
f1_keywords:
- '>=_CSharpKeyword'
helpviewer_keywords:
- greater than or equal to operator (>=) [C#]
- '>= operator [C#]'
ms.assetid: 0db4dcaf-56a3-4884-a7ad-35f64978a58d
ms.openlocfilehash: 8749d1dc0670a5a76bda5ee0d69a4a142671c1e6
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/04/2018
ms.locfileid: "43511088"
---
# <a name="gt-operator-c-reference"></a><span data-ttu-id="adbae-102">&gt;= 运算符（C# 参考）</span><span class="sxs-lookup"><span data-stu-id="adbae-102">&gt;= Operator (C# Reference)</span></span>
<span data-ttu-id="adbae-103">所有数值和枚举类型定义“大于或等于”关系运算符 `>=`，如果第一个操作数大于或等于第二个操作数，此运算符返回 `true`，否则返回 `false`。</span><span class="sxs-lookup"><span data-stu-id="adbae-103">All numeric and enumeration types define a "greater than or equal" relational operator, `>=` that returns `true` if the first operand is greater than or equal to the second, `false` otherwise.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="adbae-104">备注</span><span class="sxs-lookup"><span data-stu-id="adbae-104">Remarks</span></span>  
 <span data-ttu-id="adbae-105">用户定义的类型可以重载 `>=` 运算符。</span><span class="sxs-lookup"><span data-stu-id="adbae-105">User-defined types can overload the `>=` operator.</span></span> <span data-ttu-id="adbae-106">有关详细信息，请参阅[运算符](../../../csharp/language-reference/keywords/operator.md)。</span><span class="sxs-lookup"><span data-stu-id="adbae-106">For more information, see [operator](../../../csharp/language-reference/keywords/operator.md).</span></span> <span data-ttu-id="adbae-107">如果已重载 `>=`，则必须同时重载 [<=](../../../csharp/language-reference/operators/less-than-equal-operator.md)。</span><span class="sxs-lookup"><span data-stu-id="adbae-107">If `>=` is overloaded, [<=](../../../csharp/language-reference/operators/less-than-equal-operator.md) must also be overloaded.</span></span> <span data-ttu-id="adbae-108">对整数类型的操作通常可用于枚举。</span><span class="sxs-lookup"><span data-stu-id="adbae-108">Operations on integral types are generally allowed on enumeration.</span></span>  
  
## <a name="example"></a><span data-ttu-id="adbae-109">示例</span><span class="sxs-lookup"><span data-stu-id="adbae-109">Example</span></span>  
 [!code-csharp[csRefOperators#39](../../../csharp/language-reference/operators/codesnippet/CSharp/greater-than-equal-operator_1.cs)]  
  
## <a name="see-also"></a><span data-ttu-id="adbae-110">请参阅</span><span class="sxs-lookup"><span data-stu-id="adbae-110">See Also</span></span>

- [<span data-ttu-id="adbae-111">C# 参考</span><span class="sxs-lookup"><span data-stu-id="adbae-111">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
- [<span data-ttu-id="adbae-112">C# 编程指南</span><span class="sxs-lookup"><span data-stu-id="adbae-112">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
- [<span data-ttu-id="adbae-113">C# 运算符</span><span class="sxs-lookup"><span data-stu-id="adbae-113">C# Operators</span></span>](../../../csharp/language-reference/operators/index.md)
