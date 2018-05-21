---
title: '%= 运算符（C# 参考）'
ms.date: 04/04/2018
f1_keywords:
- '%=_CSharpKeyword'
helpviewer_keywords:
- remainder assignment operator (%=) [C#]
- '%= assignment operator (remainder assignment) [C#]'
ms.assetid: 47e5f068-1d97-4010-bd3b-e21b5d3a77f5
ms.openlocfilehash: aadcb5ef969ff408cc1e738fc0f5b67152fdc78b
ms.sourcegitcommit: 89c93d05c2281b4c834f48f6c8df1047e1410980
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/15/2018
---
# <a name="-operator-c-reference"></a><span data-ttu-id="33386-102">%= 运算符（C# 参考）</span><span class="sxs-lookup"><span data-stu-id="33386-102">%= Operator (C# Reference)</span></span>
<span data-ttu-id="33386-103">余数赋值运算符。</span><span class="sxs-lookup"><span data-stu-id="33386-103">The remainder assignment operator.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="33386-104">备注</span><span class="sxs-lookup"><span data-stu-id="33386-104">Remarks</span></span>  
 <span data-ttu-id="33386-105">使用 `%=` 赋值运算符的表达式，如</span><span class="sxs-lookup"><span data-stu-id="33386-105">An expression using the `%=` assignment operator, such as</span></span>  
  
```csharp  
x %= y  
```  
  
 <span data-ttu-id="33386-106">等效于</span><span class="sxs-lookup"><span data-stu-id="33386-106">is equivalent to</span></span>  
  
```csharp  
x = x % y  
```  
  
 <span data-ttu-id="33386-107">不同的是 `x` 只计算一次。</span><span class="sxs-lookup"><span data-stu-id="33386-107">except that `x` is only evaluated once.</span></span> <span data-ttu-id="33386-108">针对数值类型预定义了 [% 运算符](../../../csharp/language-reference/operators/remainder-operator.md)以计算除法的余数。</span><span class="sxs-lookup"><span data-stu-id="33386-108">The [% operator](../../../csharp/language-reference/operators/remainder-operator.md) is predefined for numeric types to compute the remainder after division.</span></span>  
  
 <span data-ttu-id="33386-109">不能直接重载 `%=` 运算符，但用户定义的类型可重载 [% 运算符](../../../csharp/language-reference/operators/remainder-operator.md)（请参阅[运算符（C# 参考）](../../../csharp/language-reference/keywords/operator.md)）。</span><span class="sxs-lookup"><span data-stu-id="33386-109">The `%=` operator cannot be overloaded directly, but user-defined types can overload the [% operator](../../../csharp/language-reference/operators/remainder-operator.md) (see [operator (C# Reference)](../../../csharp/language-reference/keywords/operator.md)).</span></span>  
  
## <a name="example"></a><span data-ttu-id="33386-110">示例</span><span class="sxs-lookup"><span data-stu-id="33386-110">Example</span></span>  
 [!code-csharp[csRefOperators#4](../../../csharp/language-reference/operators/codesnippet/CSharp/modulus-assignment-operator_1.cs)]  
  
## <a name="see-also"></a><span data-ttu-id="33386-111">请参阅</span><span class="sxs-lookup"><span data-stu-id="33386-111">See Also</span></span>  
 [<span data-ttu-id="33386-112">C# 参考</span><span class="sxs-lookup"><span data-stu-id="33386-112">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
 [<span data-ttu-id="33386-113">C# 编程指南</span><span class="sxs-lookup"><span data-stu-id="33386-113">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="33386-114">C# 运算符</span><span class="sxs-lookup"><span data-stu-id="33386-114">C# Operators</span></span>](../../../csharp/language-reference/operators/index.md)
