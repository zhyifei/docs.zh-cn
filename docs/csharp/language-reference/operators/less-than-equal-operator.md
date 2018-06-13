---
title: '&lt;= 运算符（C# 参考）'
ms.date: 07/20/2015
f1_keywords:
- <=_CSharpKeyword
helpviewer_keywords:
- less than or equal to operator (<=) [C#]
- <= operator [C#]
ms.assetid: bb0caec9-d253-4105-b8bc-5252233251e4
ms.openlocfilehash: 24bf274bfcb0a8e19a79aafb3bd7920054044be0
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33271157"
---
# <a name="lt-operator-c-reference"></a><span data-ttu-id="55b89-102">&lt;= 运算符（C# 参考）</span><span class="sxs-lookup"><span data-stu-id="55b89-102">&lt;= Operator (C# Reference)</span></span>
<span data-ttu-id="55b89-103">所有数值和枚举类型定义“小于或等于”关系运算符 (`<=`)，如果第一个操作数小于或等于第二个操作数，此运算符返回 `true`，否则返回 `false`。</span><span class="sxs-lookup"><span data-stu-id="55b89-103">All numeric and enumeration types define a "less than or equal" relational operator (`<=`) that returns `true` if the first operand is less than or equal to the second, `false` otherwise.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="55b89-104">备注</span><span class="sxs-lookup"><span data-stu-id="55b89-104">Remarks</span></span>  
 <span data-ttu-id="55b89-105">用户定义的类型可以重载 `<=` 运算符。</span><span class="sxs-lookup"><span data-stu-id="55b89-105">User-defined types can overload the `<=` operator.</span></span> <span data-ttu-id="55b89-106">有关详细信息，请参阅[运算符](../../../csharp/language-reference/keywords/operator.md)。</span><span class="sxs-lookup"><span data-stu-id="55b89-106">For more information, see [operator](../../../csharp/language-reference/keywords/operator.md).</span></span> <span data-ttu-id="55b89-107">如果已重载 `<=`，则必须同时重载 [>=](../../../csharp/language-reference/operators/greater-than-equal-operator.md)。</span><span class="sxs-lookup"><span data-stu-id="55b89-107">If `<=` is overloaded, [>=](../../../csharp/language-reference/operators/greater-than-equal-operator.md) must also be overloaded.</span></span> <span data-ttu-id="55b89-108">对整数类型的操作通常可用于枚举。</span><span class="sxs-lookup"><span data-stu-id="55b89-108">Operations on integral types are generally allowed on enumeration.</span></span>  
  
## <a name="example"></a><span data-ttu-id="55b89-109">示例</span><span class="sxs-lookup"><span data-stu-id="55b89-109">Example</span></span>  
 [!code-csharp[csRefOperators#32](../../../csharp/language-reference/operators/codesnippet/CSharp/less-than-equal-operator_1.cs)]  
  
## <a name="see-also"></a><span data-ttu-id="55b89-110">请参阅</span><span class="sxs-lookup"><span data-stu-id="55b89-110">See Also</span></span>  
 [<span data-ttu-id="55b89-111">C# 参考</span><span class="sxs-lookup"><span data-stu-id="55b89-111">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
 [<span data-ttu-id="55b89-112">C# 编程指南</span><span class="sxs-lookup"><span data-stu-id="55b89-112">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="55b89-113">C# 运算符</span><span class="sxs-lookup"><span data-stu-id="55b89-113">C# Operators</span></span>](../../../csharp/language-reference/operators/index.md)  
 [<span data-ttu-id="55b89-114">explicit</span><span class="sxs-lookup"><span data-stu-id="55b89-114">explicit</span></span>](../../../csharp/language-reference/keywords/explicit.md)
