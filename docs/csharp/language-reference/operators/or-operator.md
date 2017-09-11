---
title: "| 运算符（C# 参考）"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- '|_CSharpKeyword'
dev_langs:
- CSharp
helpviewer_keywords:
- bitwise OR operator [C#]
- '| operator [C#]'
- binary operator (|) [C#]
ms.assetid: 82d6bb78-54c8-40bf-b679-531180ddaf70
caps.latest.revision: 15
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
ms.openlocfilehash: 7524e246df35154ac04e46f2b43edded71be34b1
ms.contentlocale: zh-cn
ms.lasthandoff: 07/28/2017

---
# <a name="-operator-c-reference"></a><span data-ttu-id="5c0a5-102">| 运算符（C# 参考）</span><span class="sxs-lookup"><span data-stu-id="5c0a5-102">| Operator (C# Reference)</span></span>
<span data-ttu-id="5c0a5-103">针对整型类型和 `bool` 预定义了二元 `|` 运算符。</span><span class="sxs-lookup"><span data-stu-id="5c0a5-103">Binary `|` operators are predefined for the integral types and `bool`.</span></span> <span data-ttu-id="5c0a5-104">对于整型类型，`|` 会计算其操作数的按位 OR。</span><span class="sxs-lookup"><span data-stu-id="5c0a5-104">For integral types, `|` computes the bitwise OR of its operands.</span></span> <span data-ttu-id="5c0a5-105">对于 `bool` 操作数，`|` 会计算其操作数的逻辑 OR；即，当且仅当其两个操作数皆为 `false` 时，结果才为 `false`。</span><span class="sxs-lookup"><span data-stu-id="5c0a5-105">For `bool` operands, `|` computes the logical OR of its operands; that is, the result is `false` if and only if both its operands are `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="5c0a5-106">备注</span><span class="sxs-lookup"><span data-stu-id="5c0a5-106">Remarks</span></span>  
 <span data-ttu-id="5c0a5-107">用户定义的类型可以重载 `|` 运算符（请参阅[运算符](../../../csharp/language-reference/keywords/operator.md)）。</span><span class="sxs-lookup"><span data-stu-id="5c0a5-107">User-defined types can overload the `|` operator (see [operator](../../../csharp/language-reference/keywords/operator.md)).</span></span>  
  
## <a name="example"></a><span data-ttu-id="5c0a5-108">示例</span><span class="sxs-lookup"><span data-stu-id="5c0a5-108">Example</span></span>  
 <span data-ttu-id="5c0a5-109">[!code-cs[csRefOperators#31](../../../csharp/language-reference/operators/codesnippet/CSharp/or-operator_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="5c0a5-109">[!code-cs[csRefOperators#31](../../../csharp/language-reference/operators/codesnippet/CSharp/or-operator_1.cs)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5c0a5-110">另请参阅</span><span class="sxs-lookup"><span data-stu-id="5c0a5-110">See Also</span></span>  
 <span data-ttu-id="5c0a5-111">[C# 参考](../../../csharp/language-reference/index.md) </span><span class="sxs-lookup"><span data-stu-id="5c0a5-111">[C# Reference](../../../csharp/language-reference/index.md) </span></span>  
 <span data-ttu-id="5c0a5-112">[C# 编程指南](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="5c0a5-112">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 [<span data-ttu-id="5c0a5-113">C# 运算符</span><span class="sxs-lookup"><span data-stu-id="5c0a5-113">C# Operators</span></span>](../../../csharp/language-reference/operators/index.md)

