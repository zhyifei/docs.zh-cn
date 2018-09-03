---
title: '%= 运算符（C# 参考）'
ms.date: 04/04/2018
f1_keywords:
- '%=_CSharpKeyword'
helpviewer_keywords:
- remainder assignment operator (%=) [C#]
- '%= assignment operator (remainder assignment) [C#]'
ms.assetid: 47e5f068-1d97-4010-bd3b-e21b5d3a77f5
ms.openlocfilehash: 009c162b13fab05ba349d0535fe8dfae206502f3
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/01/2018
ms.locfileid: "43399486"
---
# <a name="-operator-c-reference"></a><span data-ttu-id="38747-102">%= 运算符（C# 参考）</span><span class="sxs-lookup"><span data-stu-id="38747-102">%= Operator (C# Reference)</span></span>
<span data-ttu-id="38747-103">余数赋值运算符。</span><span class="sxs-lookup"><span data-stu-id="38747-103">The remainder assignment operator.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="38747-104">备注</span><span class="sxs-lookup"><span data-stu-id="38747-104">Remarks</span></span>  
 <span data-ttu-id="38747-105">使用 `%=` 赋值运算符的表达式，如</span><span class="sxs-lookup"><span data-stu-id="38747-105">An expression using the `%=` assignment operator, such as</span></span>  
  
```csharp  
x %= y  
```  
  
 <span data-ttu-id="38747-106">等效于</span><span class="sxs-lookup"><span data-stu-id="38747-106">is equivalent to</span></span>  
  
```csharp  
x = x % y  
```  
  
 <span data-ttu-id="38747-107">不同的是 `x` 只计算一次。</span><span class="sxs-lookup"><span data-stu-id="38747-107">except that `x` is only evaluated once.</span></span> <span data-ttu-id="38747-108">针对数值类型预定义了 [% 运算符](../../../csharp/language-reference/operators/remainder-operator.md)以计算除法的余数。</span><span class="sxs-lookup"><span data-stu-id="38747-108">The [% operator](../../../csharp/language-reference/operators/remainder-operator.md) is predefined for numeric types to compute the remainder after division.</span></span>  
  
 <span data-ttu-id="38747-109">不能直接重载 `%=` 运算符，但用户定义的类型可重载 [% 运算符](../../../csharp/language-reference/operators/remainder-operator.md)（请参阅[运算符（C# 参考）](../../../csharp/language-reference/keywords/operator.md)）。</span><span class="sxs-lookup"><span data-stu-id="38747-109">The `%=` operator cannot be overloaded directly, but user-defined types can overload the [% operator](../../../csharp/language-reference/operators/remainder-operator.md) (see [operator (C# Reference)](../../../csharp/language-reference/keywords/operator.md)).</span></span>  
  
## <a name="example"></a><span data-ttu-id="38747-110">示例</span><span class="sxs-lookup"><span data-stu-id="38747-110">Example</span></span>  
 [!code-csharp[csRefOperators#4](../../../csharp/language-reference/operators/codesnippet/CSharp/modulus-assignment-operator_1.cs)]  
  
## <a name="see-also"></a><span data-ttu-id="38747-111">请参阅</span><span class="sxs-lookup"><span data-stu-id="38747-111">See Also</span></span>

- [<span data-ttu-id="38747-112">C# 参考</span><span class="sxs-lookup"><span data-stu-id="38747-112">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
- [<span data-ttu-id="38747-113">C# 编程指南</span><span class="sxs-lookup"><span data-stu-id="38747-113">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
- [<span data-ttu-id="38747-114">C# 运算符</span><span class="sxs-lookup"><span data-stu-id="38747-114">C# Operators</span></span>](../../../csharp/language-reference/operators/index.md)
