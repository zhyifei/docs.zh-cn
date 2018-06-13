---
title: '&gt; 运算符（C# 参考）'
ms.date: 07/20/2015
f1_keywords:
- '>_CSharpKeyword'
helpviewer_keywords:
- '> operator [C#]'
- greater than operator (>) [C#]
ms.assetid: 26d3cb69-9c0b-4cc5-858b-5be1abd6659d
ms.openlocfilehash: 1589c5e785b33db6106a0ef0a58202e771db9fa0
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33273493"
---
# <a name="gt-operator-c-reference"></a><span data-ttu-id="42f34-102">&gt; 运算符（C# 参考）</span><span class="sxs-lookup"><span data-stu-id="42f34-102">&gt; Operator (C# Reference)</span></span>
<span data-ttu-id="42f34-103">所有数值和枚举类型定义“大于”关系运算符 (`>`)，如果第一个操作数大于第二个操作数，此运算符返回 `true`，否则返回 `false`。</span><span class="sxs-lookup"><span data-stu-id="42f34-103">All numeric and enumeration types define a "greater than" relational operator (`>`) that returns `true` if the first operand is greater than the second, `false` otherwise.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="42f34-104">备注</span><span class="sxs-lookup"><span data-stu-id="42f34-104">Remarks</span></span>  
 <span data-ttu-id="42f34-105">用户定义的类型可以重载 `>` 运算符（请参阅[运算符](../../../csharp/language-reference/keywords/operator.md)）。</span><span class="sxs-lookup"><span data-stu-id="42f34-105">User-defined types can overload the `>` operator (see [operator](../../../csharp/language-reference/keywords/operator.md)).</span></span> <span data-ttu-id="42f34-106">如果已重载 `>`，则必须同时重载 [<](../../../csharp/language-reference/operators/less-than-operator.md)。</span><span class="sxs-lookup"><span data-stu-id="42f34-106">If `>` is overloaded, [<](../../../csharp/language-reference/operators/less-than-operator.md) must also be overloaded.</span></span> <span data-ttu-id="42f34-107">重载二元运算符时，也会隐式重载相应的赋值运算符（若有）。</span><span class="sxs-lookup"><span data-stu-id="42f34-107">When a binary operator is overloaded, the corresponding assignment operator, if any, is also implicitly overloaded.</span></span>  
  
## <a name="example"></a><span data-ttu-id="42f34-108">示例</span><span class="sxs-lookup"><span data-stu-id="42f34-108">Example</span></span>  
 [!code-csharp[csRefOperators#29](../../../csharp/language-reference/operators/codesnippet/CSharp/greater-than-operator_1.cs)]  
  
## <a name="see-also"></a><span data-ttu-id="42f34-109">请参阅</span><span class="sxs-lookup"><span data-stu-id="42f34-109">See Also</span></span>  
 [<span data-ttu-id="42f34-110">C# 参考</span><span class="sxs-lookup"><span data-stu-id="42f34-110">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
 [<span data-ttu-id="42f34-111">C# 编程指南</span><span class="sxs-lookup"><span data-stu-id="42f34-111">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="42f34-112">C# 运算符</span><span class="sxs-lookup"><span data-stu-id="42f34-112">C# Operators</span></span>](../../../csharp/language-reference/operators/index.md)  
 [<span data-ttu-id="42f34-113">explicit</span><span class="sxs-lookup"><span data-stu-id="42f34-113">explicit</span></span>](../../../csharp/language-reference/keywords/explicit.md)
