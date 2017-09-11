---
title: "&lt;= 运算符（C# 参考）"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- <=_CSharpKeyword
dev_langs:
- CSharp
helpviewer_keywords:
- less than or equal to operator (<=) [C#]
- <= operator [C#]
ms.assetid: bb0caec9-d253-4105-b8bc-5252233251e4
caps.latest.revision: 16
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
ms.openlocfilehash: 931843783888a844d9f90f273b2362d327e8ccbc
ms.contentlocale: zh-cn
ms.lasthandoff: 07/28/2017

---
# <a name="lt-operator-c-reference"></a><span data-ttu-id="ecbc5-102">&lt;= 运算符（C# 参考）</span><span class="sxs-lookup"><span data-stu-id="ecbc5-102">&lt;= Operator (C# Reference)</span></span>
<span data-ttu-id="ecbc5-103">所有数值和枚举类型定义“小于或等于”关系运算符 (`<=`)，如果第一个操作数小于或等于第二个操作数，此运算符返回 `true`，否则返回 `false`。</span><span class="sxs-lookup"><span data-stu-id="ecbc5-103">All numeric and enumeration types define a "less than or equal" relational operator (`<=`) that returns `true` if the first operand is less than or equal to the second, `false` otherwise.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ecbc5-104">备注</span><span class="sxs-lookup"><span data-stu-id="ecbc5-104">Remarks</span></span>  
 <span data-ttu-id="ecbc5-105">用户定义的类型可以重载 `<=` 运算符。</span><span class="sxs-lookup"><span data-stu-id="ecbc5-105">User-defined types can overload the `<=` operator.</span></span> <span data-ttu-id="ecbc5-106">有关详细信息，请参阅[运算符](../../../csharp/language-reference/keywords/operator.md)。</span><span class="sxs-lookup"><span data-stu-id="ecbc5-106">For more information, see [operator](../../../csharp/language-reference/keywords/operator.md).</span></span> <span data-ttu-id="ecbc5-107">如果已重载 `<=`，则必须同时重载 [>=](../../../csharp/language-reference/operators/greater-than-equal-operator.md)。</span><span class="sxs-lookup"><span data-stu-id="ecbc5-107">If `<=` is overloaded, [>=](../../../csharp/language-reference/operators/greater-than-equal-operator.md) must also be overloaded.</span></span> <span data-ttu-id="ecbc5-108">对整数类型的操作通常可用于枚举。</span><span class="sxs-lookup"><span data-stu-id="ecbc5-108">Operations on integral types are generally allowed on enumeration.</span></span>  
  
## <a name="example"></a><span data-ttu-id="ecbc5-109">示例</span><span class="sxs-lookup"><span data-stu-id="ecbc5-109">Example</span></span>  
 <span data-ttu-id="ecbc5-110">[!code-cs[csRefOperators#32](../../../csharp/language-reference/operators/codesnippet/CSharp/less-than-equal-operator_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="ecbc5-110">[!code-cs[csRefOperators#32](../../../csharp/language-reference/operators/codesnippet/CSharp/less-than-equal-operator_1.cs)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ecbc5-111">另请参阅</span><span class="sxs-lookup"><span data-stu-id="ecbc5-111">See Also</span></span>  
 <span data-ttu-id="ecbc5-112">[C# 参考](../../../csharp/language-reference/index.md) </span><span class="sxs-lookup"><span data-stu-id="ecbc5-112">[C# Reference](../../../csharp/language-reference/index.md) </span></span>  
 <span data-ttu-id="ecbc5-113">[C# 编程指南](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="ecbc5-113">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 <span data-ttu-id="ecbc5-114">[C# 运算符](../../../csharp/language-reference/operators/index.md) </span><span class="sxs-lookup"><span data-stu-id="ecbc5-114">[C# Operators](../../../csharp/language-reference/operators/index.md) </span></span>  
 [<span data-ttu-id="ecbc5-115">explicit</span><span class="sxs-lookup"><span data-stu-id="ecbc5-115">explicit</span></span>](../../../csharp/language-reference/keywords/explicit.md)

