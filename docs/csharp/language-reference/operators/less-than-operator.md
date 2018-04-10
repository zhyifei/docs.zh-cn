---
title: '&lt; 运算符（C# 参考）'
ms.date: 07/20/2015
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- <_CSharpKeyword
helpviewer_keywords:
- less than operator (<) [C#]
- < operator [C#]
ms.assetid: 38cb91e6-79a6-48ec-9c1e-7b71fd8d2b41
caps.latest.revision: 14
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 76d53d4c943c886f6b8c8a68e2b8bb12bc9a9d6c
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="lt-operator-c-reference"></a><span data-ttu-id="64a71-102">&lt; 运算符（C# 参考）</span><span class="sxs-lookup"><span data-stu-id="64a71-102">&lt; Operator (C# Reference)</span></span>
<span data-ttu-id="64a71-103">所有数值和枚举类型定义“小于”关系运算符 (`<`)，如果第一个操作数小于第二个操作数，此运算符返回 `true`，否则返回 `false`。</span><span class="sxs-lookup"><span data-stu-id="64a71-103">All numeric and enumeration types define a "less than" relational operator (`<`) that returns `true` if the first operand is less than the second, `false` otherwise.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="64a71-104">备注</span><span class="sxs-lookup"><span data-stu-id="64a71-104">Remarks</span></span>  
 <span data-ttu-id="64a71-105">用户定义的类型可以重载 `<` 运算符（请参阅[运算符](../../../csharp/language-reference/keywords/operator.md)）。</span><span class="sxs-lookup"><span data-stu-id="64a71-105">User-defined types can overload the `<` operator (see [operator](../../../csharp/language-reference/keywords/operator.md)).</span></span> <span data-ttu-id="64a71-106">如果已重载 `<`，则必须同时重载 [>](../../../csharp/language-reference/operators/greater-than-operator.md)。</span><span class="sxs-lookup"><span data-stu-id="64a71-106">If `<` is overloaded, [>](../../../csharp/language-reference/operators/greater-than-operator.md) must also be overloaded.</span></span> <span data-ttu-id="64a71-107">重载二元运算符时，也会隐式重载相应的赋值运算符（若有）。</span><span class="sxs-lookup"><span data-stu-id="64a71-107">When a binary operator is overloaded, the corresponding assignment operator, if any, is also implicitly overloaded.</span></span>  
  
## <a name="example"></a><span data-ttu-id="64a71-108">示例</span><span class="sxs-lookup"><span data-stu-id="64a71-108">Example</span></span>  
 [!code-csharp[csRefOperators#24](../../../csharp/language-reference/operators/codesnippet/CSharp/less-than-operator_1.cs)]  
  
## <a name="see-also"></a><span data-ttu-id="64a71-109">另请参阅</span><span class="sxs-lookup"><span data-stu-id="64a71-109">See Also</span></span>  
 [<span data-ttu-id="64a71-110">C# 参考</span><span class="sxs-lookup"><span data-stu-id="64a71-110">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
 [<span data-ttu-id="64a71-111">C# 编程指南</span><span class="sxs-lookup"><span data-stu-id="64a71-111">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="64a71-112">C# 运算符</span><span class="sxs-lookup"><span data-stu-id="64a71-112">C# Operators</span></span>](../../../csharp/language-reference/operators/index.md)
