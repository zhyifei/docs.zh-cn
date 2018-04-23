---
title: '%= 运算符（C# 参考）'
ms.date: 04/04/2018
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- '%=_CSharpKeyword'
helpviewer_keywords:
- remainder assignment operator (%=) [C#]
- '%= assignment operator (remainder assignment) [C#]'
ms.assetid: 47e5f068-1d97-4010-bd3b-e21b5d3a77f5
caps.latest.revision: 20
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 864b96dcf16e4756cd0e74a6e02297660e72357e
ms.sourcegitcommit: b750a8e3979749b214e7e10c82efb0a0524dfcb1
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/09/2018
---
# <a name="-operator-c-reference"></a><span data-ttu-id="6eca4-102">%= 运算符（C# 参考）</span><span class="sxs-lookup"><span data-stu-id="6eca4-102">%= Operator (C# Reference)</span></span>
<span data-ttu-id="6eca4-103">余数赋值运算符。</span><span class="sxs-lookup"><span data-stu-id="6eca4-103">The remainder assignment operator.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="6eca4-104">备注</span><span class="sxs-lookup"><span data-stu-id="6eca4-104">Remarks</span></span>  
 <span data-ttu-id="6eca4-105">使用 `%=` 赋值运算符的表达式，如</span><span class="sxs-lookup"><span data-stu-id="6eca4-105">An expression using the `%=` assignment operator, such as</span></span>  
  
```  
x %= y  
```  
  
 <span data-ttu-id="6eca4-106">等效于</span><span class="sxs-lookup"><span data-stu-id="6eca4-106">is equivalent to</span></span>  
  
```  
x = x % y  
```  
  
 <span data-ttu-id="6eca4-107">不同的是 `x` 只计算一次。</span><span class="sxs-lookup"><span data-stu-id="6eca4-107">except that `x` is only evaluated once.</span></span> <span data-ttu-id="6eca4-108">针对数值类型预定义了 [% 运算符](../../../csharp/language-reference/operators/remainder-operator.md)以计算除法的余数。</span><span class="sxs-lookup"><span data-stu-id="6eca4-108">The [% operator](../../../csharp/language-reference/operators/remainder-operator.md) is predefined for numeric types to compute the remainder after division.</span></span>  
  
 <span data-ttu-id="6eca4-109">不能直接重载 `%=` 运算符，但用户定义的类型可重载 [% 运算符](../../../csharp/language-reference/operators/remainder-operator.md)（请参阅[运算符（C# 参考）](../../../csharp/language-reference/keywords/operator.md)）。</span><span class="sxs-lookup"><span data-stu-id="6eca4-109">The `%=` operator cannot be overloaded directly, but user-defined types can overload the [% operator](../../../csharp/language-reference/operators/remainder-operator.md) (see [operator (C# Reference)](../../../csharp/language-reference/keywords/operator.md)).</span></span>  
  
## <a name="example"></a><span data-ttu-id="6eca4-110">示例</span><span class="sxs-lookup"><span data-stu-id="6eca4-110">Example</span></span>  
 [!code-csharp[csRefOperators#4](../../../csharp/language-reference/operators/codesnippet/CSharp/modulus-assignment-operator_1.cs)]  
  
## <a name="see-also"></a><span data-ttu-id="6eca4-111">请参阅</span><span class="sxs-lookup"><span data-stu-id="6eca4-111">See Also</span></span>  
 [<span data-ttu-id="6eca4-112">C# 参考</span><span class="sxs-lookup"><span data-stu-id="6eca4-112">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
 [<span data-ttu-id="6eca4-113">C# 编程指南</span><span class="sxs-lookup"><span data-stu-id="6eca4-113">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="6eca4-114">C# 运算符</span><span class="sxs-lookup"><span data-stu-id="6eca4-114">C# Operators</span></span>](../../../csharp/language-reference/operators/index.md)
