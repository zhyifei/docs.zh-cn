---
title: "&gt; 运算符（C# 参考）"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- '>_CSharpKeyword'
dev_langs:
- CSharp
helpviewer_keywords:
- '> operator [C#]'
- greater than operator (>) [C#]
ms.assetid: 26d3cb69-9c0b-4cc5-858b-5be1abd6659d
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
ms.openlocfilehash: 5b4eb1f6fcca311fc772e4dbe0ce0391201af3de
ms.contentlocale: zh-cn
ms.lasthandoff: 07/28/2017

---
# <a name="gt-operator-c-reference"></a><span data-ttu-id="6f7db-102">&gt; 运算符（C# 参考）</span><span class="sxs-lookup"><span data-stu-id="6f7db-102">&gt; Operator (C# Reference)</span></span>
<span data-ttu-id="6f7db-103">所有数值和枚举类型定义“大于”关系运算符 (`>`)，如果第一个操作数大于第二个操作数，此运算符返回 `true`，否则返回 `false`。</span><span class="sxs-lookup"><span data-stu-id="6f7db-103">All numeric and enumeration types define a "greater than" relational operator (`>`) that returns `true` if the first operand is greater than the second, `false` otherwise.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="6f7db-104">备注</span><span class="sxs-lookup"><span data-stu-id="6f7db-104">Remarks</span></span>  
 <span data-ttu-id="6f7db-105">用户定义的类型可以重载 `>` 运算符（请参阅[运算符](../../../csharp/language-reference/keywords/operator.md)）。</span><span class="sxs-lookup"><span data-stu-id="6f7db-105">User-defined types can overload the `>` operator (see [operator](../../../csharp/language-reference/keywords/operator.md)).</span></span> <span data-ttu-id="6f7db-106">如果已重载 `>`，则必须同时重载 [<](../../../csharp/language-reference/operators/less-than-operator.md)。</span><span class="sxs-lookup"><span data-stu-id="6f7db-106">If `>` is overloaded, [<](../../../csharp/language-reference/operators/less-than-operator.md) must also be overloaded.</span></span> <span data-ttu-id="6f7db-107">重载二元运算符时，也会隐式重载相应的赋值运算符（若有）。</span><span class="sxs-lookup"><span data-stu-id="6f7db-107">When a binary operator is overloaded, the corresponding assignment operator, if any, is also implicitly overloaded.</span></span>  
  
## <a name="example"></a><span data-ttu-id="6f7db-108">示例</span><span class="sxs-lookup"><span data-stu-id="6f7db-108">Example</span></span>  
 <span data-ttu-id="6f7db-109">[!code-cs[csRefOperators#29](../../../csharp/language-reference/operators/codesnippet/CSharp/greater-than-operator_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="6f7db-109">[!code-cs[csRefOperators#29](../../../csharp/language-reference/operators/codesnippet/CSharp/greater-than-operator_1.cs)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6f7db-110">另请参阅</span><span class="sxs-lookup"><span data-stu-id="6f7db-110">See Also</span></span>  
 <span data-ttu-id="6f7db-111">[C# 参考](../../../csharp/language-reference/index.md) </span><span class="sxs-lookup"><span data-stu-id="6f7db-111">[C# Reference](../../../csharp/language-reference/index.md) </span></span>  
 <span data-ttu-id="6f7db-112">[C# 编程指南](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="6f7db-112">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 <span data-ttu-id="6f7db-113">[C# 运算符](../../../csharp/language-reference/operators/index.md) </span><span class="sxs-lookup"><span data-stu-id="6f7db-113">[C# Operators](../../../csharp/language-reference/operators/index.md) </span></span>  
 [<span data-ttu-id="6f7db-114">explicit</span><span class="sxs-lookup"><span data-stu-id="6f7db-114">explicit</span></span>](../../../csharp/language-reference/keywords/explicit.md)

