---
title: "!= 运算符（C# 参考）"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- '!=_CSharpKeyword'
dev_langs:
- CSharp
helpviewer_keywords:
- inequality operator (!=) [C#]
- not equals operator (!=) [C#]
- '!= operator [C#]'
ms.assetid: eeff7a4e-ad6f-462d-9f8d-49e9b91c6c97
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
ms.openlocfilehash: 49c5c9668c6b1169220ee4fa0babf167292a9813
ms.contentlocale: zh-cn
ms.lasthandoff: 07/28/2017

---
# <a name="-operator-c-reference"></a><span data-ttu-id="50b67-102">!= 运算符（C# 参考）</span><span class="sxs-lookup"><span data-stu-id="50b67-102">!= Operator (C# Reference)</span></span>
<span data-ttu-id="50b67-103">如果操作数相等，不相等运算符 (`!=`) 返回 false，否则返回 true。</span><span class="sxs-lookup"><span data-stu-id="50b67-103">The inequality operator (`!=`) returns false if its operands are equal, true otherwise.</span></span> <span data-ttu-id="50b67-104">不相等运算符针对 string 和 object 等所有类型进行预定义。</span><span class="sxs-lookup"><span data-stu-id="50b67-104">Inequality operators are predefined for all types, including string and object.</span></span> <span data-ttu-id="50b67-105">用户定义的类型可以重载 `!=` 运算符。</span><span class="sxs-lookup"><span data-stu-id="50b67-105">User-defined types can overload the `!=` operator.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="50b67-106">备注</span><span class="sxs-lookup"><span data-stu-id="50b67-106">Remarks</span></span>  
 <span data-ttu-id="50b67-107">对于预定义的值类型，如果其操作数的值不同，不相等运算符 (`!=`) 返回 true，否则返回 false。</span><span class="sxs-lookup"><span data-stu-id="50b67-107">For predefined value types, the inequality operator (`!=`) returns true if the values of its operands are different, false otherwise.</span></span> <span data-ttu-id="50b67-108">对于除 `string` 外的引用类型，如果两个操作数引用不同对象，`!=` 返回 true。</span><span class="sxs-lookup"><span data-stu-id="50b67-108">For reference types other than `string`, `!=` returns true if its two operands refer to different objects.</span></span> <span data-ttu-id="50b67-109">对于 `string` 类型，`!=` 会比较字符串的值。</span><span class="sxs-lookup"><span data-stu-id="50b67-109">For the `string` type, `!=` compares the values of the strings.</span></span>  
  
 <span data-ttu-id="50b67-110">用户定义的值类型可以重载 `!=` 运算符（请参阅[运算符](../../../csharp/language-reference/keywords/operator.md)）。</span><span class="sxs-lookup"><span data-stu-id="50b67-110">User-defined value types can overload the `!=` operator (see [operator](../../../csharp/language-reference/keywords/operator.md)).</span></span> <span data-ttu-id="50b67-111">用户定义的引用类型情况也相似，但是默认情况下，`!=` 的行为如上述预定义和用户定义的引用类型所述。</span><span class="sxs-lookup"><span data-stu-id="50b67-111">So can user-defined reference types, although by default `!=` behaves as described above for both predefined and user-defined reference types.</span></span> <span data-ttu-id="50b67-112">如果已重载 `!=`，则必须同时重载 [==](../../../csharp/language-reference/operators/equality-comparison-operator.md)。</span><span class="sxs-lookup"><span data-stu-id="50b67-112">If `!=` is overloaded, [==](../../../csharp/language-reference/operators/equality-comparison-operator.md) must also be overloaded.</span></span> <span data-ttu-id="50b67-113">对整数类型的操作通常可用于枚举。</span><span class="sxs-lookup"><span data-stu-id="50b67-113">Operations on integral types are generally allowed on enumeration.</span></span>  
  
## <a name="example"></a><span data-ttu-id="50b67-114">示例</span><span class="sxs-lookup"><span data-stu-id="50b67-114">Example</span></span>  
 <span data-ttu-id="50b67-115">[!code-cs[csRefOperators#33](../../../csharp/language-reference/operators/codesnippet/CSharp/not-equal-operator_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="50b67-115">[!code-cs[csRefOperators#33](../../../csharp/language-reference/operators/codesnippet/CSharp/not-equal-operator_1.cs)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="50b67-116">另请参阅</span><span class="sxs-lookup"><span data-stu-id="50b67-116">See Also</span></span>  
 <span data-ttu-id="50b67-117">[C# 参考](../../../csharp/language-reference/index.md) </span><span class="sxs-lookup"><span data-stu-id="50b67-117">[C# Reference](../../../csharp/language-reference/index.md) </span></span>  
 <span data-ttu-id="50b67-118">[C# 编程指南](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="50b67-118">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 [<span data-ttu-id="50b67-119">C# 运算符</span><span class="sxs-lookup"><span data-stu-id="50b67-119">C# Operators</span></span>](../../../csharp/language-reference/operators/index.md)

