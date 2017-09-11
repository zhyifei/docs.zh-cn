---
title: "== 运算符（C# 参考）"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- ==_CSharpKeyword
dev_langs:
- CSharp
helpviewer_keywords:
- == operator [C#]
- equality operator [C#]
ms.assetid: 34c6b597-caa2-4855-a7cd-38ecdd11bd07
caps.latest.revision: 14
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
ms.openlocfilehash: 0e3ba284bc700e943b108adfec89d14aba41851a
ms.contentlocale: zh-cn
ms.lasthandoff: 07/28/2017

---
# <a name="-operator-c-reference"></a><span data-ttu-id="9012f-102">== 运算符（C# 参考）</span><span class="sxs-lookup"><span data-stu-id="9012f-102">== Operator (C# Reference)</span></span>
<span data-ttu-id="9012f-103">对于预定义的值类型，如果其操作数的值相等，则相等运算符 (`==`) 返回 true，否则返回 `false`。</span><span class="sxs-lookup"><span data-stu-id="9012f-103">For predefined value types, the equality operator (`==`) returns true if the values of its operands are equal, `false` otherwise.</span></span> <span data-ttu-id="9012f-104">对于 [string](../../../csharp/language-reference/keywords/string.md) 外的引用类型，如果两个操作数引用同一对象，则 `==` 会返回 `true`。</span><span class="sxs-lookup"><span data-stu-id="9012f-104">For reference types other than [string](../../../csharp/language-reference/keywords/string.md), `==` returns `true` if its two operands refer to the same object.</span></span> <span data-ttu-id="9012f-105">对于 `string` 类型，`==` 会比较字符串的值。</span><span class="sxs-lookup"><span data-stu-id="9012f-105">For the `string` type, `==` compares the values of the strings.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="9012f-106">备注</span><span class="sxs-lookup"><span data-stu-id="9012f-106">Remarks</span></span>  
 <span data-ttu-id="9012f-107">用户定义的值类型可以重载 `==` 运算符（请参阅[运算符](../../../csharp/language-reference/keywords/operator.md)）。</span><span class="sxs-lookup"><span data-stu-id="9012f-107">User-defined value types can overload the `==` operator (see [operator](../../../csharp/language-reference/keywords/operator.md)).</span></span> <span data-ttu-id="9012f-108">用户定义的引用类型情况也相似，但是默认情况下，`==` 的行为如上述预定义和用户定义的引用类型所述。</span><span class="sxs-lookup"><span data-stu-id="9012f-108">So can user-defined reference types, although by default `==` behaves as described above for both predefined and user-defined reference types.</span></span> <span data-ttu-id="9012f-109">如果已重载 `==`，则必须同时重载 [!=](../../../csharp/language-reference/operators/not-equal-operator.md)。</span><span class="sxs-lookup"><span data-stu-id="9012f-109">If `==` is overloaded, [!=](../../../csharp/language-reference/operators/not-equal-operator.md) must also be overloaded.</span></span> <span data-ttu-id="9012f-110">对整数类型的操作通常可用于枚举。</span><span class="sxs-lookup"><span data-stu-id="9012f-110">Operations on integral types are generally allowed on enumeration.</span></span>  
  
## <a name="example"></a><span data-ttu-id="9012f-111">示例</span><span class="sxs-lookup"><span data-stu-id="9012f-111">Example</span></span>  
 <span data-ttu-id="9012f-112">[!code-cs[csRefOperators#36](../../../csharp/language-reference/operators/codesnippet/CSharp/equality-comparison-operator_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="9012f-112">[!code-cs[csRefOperators#36](../../../csharp/language-reference/operators/codesnippet/CSharp/equality-comparison-operator_1.cs)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9012f-113">另请参阅</span><span class="sxs-lookup"><span data-stu-id="9012f-113">See Also</span></span>  
 <span data-ttu-id="9012f-114">[C# 参考](../../../csharp/language-reference/index.md) </span><span class="sxs-lookup"><span data-stu-id="9012f-114">[C# Reference](../../../csharp/language-reference/index.md) </span></span>  
 <span data-ttu-id="9012f-115">[C# 编程指南](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="9012f-115">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 [<span data-ttu-id="9012f-116">C# 运算符</span><span class="sxs-lookup"><span data-stu-id="9012f-116">C# Operators</span></span>](../../../csharp/language-reference/operators/index.md)

