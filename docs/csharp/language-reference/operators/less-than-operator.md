---
title: '&lt; 运算符 - C# 参考'
ms.custom: seodec18
ms.date: 07/20/2015
f1_keywords:
- <_CSharpKeyword
helpviewer_keywords:
- less than operator (<) [C#]
- < operator [C#]
ms.assetid: 38cb91e6-79a6-48ec-9c1e-7b71fd8d2b41
ms.openlocfilehash: 3cc125471eee7bf0002e9844c2a1cdc05e8d4a03
ms.sourcegitcommit: bdd930b5df20a45c29483d905526a2a3e4d17c5b
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2018
ms.locfileid: "53241216"
---
# <a name="lt-operator-c-reference"></a><span data-ttu-id="98e57-102">&lt; 运算符（C# 参考）</span><span class="sxs-lookup"><span data-stu-id="98e57-102">&lt; Operator (C# Reference)</span></span>
<span data-ttu-id="98e57-103">所有数值和枚举类型定义“小于”关系运算符 (`<`)，如果第一个操作数小于第二个操作数，此运算符返回 `true`，否则返回 `false`。</span><span class="sxs-lookup"><span data-stu-id="98e57-103">All numeric and enumeration types define a "less than" relational operator (`<`) that returns `true` if the first operand is less than the second, `false` otherwise.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="98e57-104">备注</span><span class="sxs-lookup"><span data-stu-id="98e57-104">Remarks</span></span>  
 <span data-ttu-id="98e57-105">用户定义的类型可以重载 `<` 运算符（请参阅[运算符](../../../csharp/language-reference/keywords/operator.md)）。</span><span class="sxs-lookup"><span data-stu-id="98e57-105">User-defined types can overload the `<` operator (see [operator](../../../csharp/language-reference/keywords/operator.md)).</span></span> <span data-ttu-id="98e57-106">如果已重载 `<`，则必须同时重载 [>](../../../csharp/language-reference/operators/greater-than-operator.md)。</span><span class="sxs-lookup"><span data-stu-id="98e57-106">If `<` is overloaded, [>](../../../csharp/language-reference/operators/greater-than-operator.md) must also be overloaded.</span></span>
  
## <a name="example"></a><span data-ttu-id="98e57-107">示例</span><span class="sxs-lookup"><span data-stu-id="98e57-107">Example</span></span>  
 [!code-csharp[csRefOperators#24](../../../csharp/language-reference/operators/codesnippet/CSharp/less-than-operator_1.cs)]  
  
## <a name="see-also"></a><span data-ttu-id="98e57-108">请参阅</span><span class="sxs-lookup"><span data-stu-id="98e57-108">See Also</span></span>

- [<span data-ttu-id="98e57-109">C# 参考</span><span class="sxs-lookup"><span data-stu-id="98e57-109">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
- [<span data-ttu-id="98e57-110">C# 编程指南</span><span class="sxs-lookup"><span data-stu-id="98e57-110">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
- [<span data-ttu-id="98e57-111">C# 运算符</span><span class="sxs-lookup"><span data-stu-id="98e57-111">C# Operators</span></span>](../../../csharp/language-reference/operators/index.md)
