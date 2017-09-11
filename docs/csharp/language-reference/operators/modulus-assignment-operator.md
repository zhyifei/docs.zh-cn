---
title: "%= 运算符（C# 参考）"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- '%=_CSharpKeyword'
dev_langs:
- CSharp
helpviewer_keywords:
- modulus assignment operator (=%) [C#]
- '%= assignment operator (modulus assignment) [C#]'
ms.assetid: 47e5f068-1d97-4010-bd3b-e21b5d3a77f5
caps.latest.revision: 20
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
ms.openlocfilehash: 48484a0593102c92304803e5c0697501b0e26e0e
ms.contentlocale: zh-cn
ms.lasthandoff: 07/28/2017

---
# <a name="-operator-c-reference"></a><span data-ttu-id="02861-102">%= 运算符（C# 参考）</span><span class="sxs-lookup"><span data-stu-id="02861-102">%= Operator (C# Reference)</span></span>
<span data-ttu-id="02861-103">余数赋值运算符。</span><span class="sxs-lookup"><span data-stu-id="02861-103">The remainder assignment operator.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="02861-104">备注</span><span class="sxs-lookup"><span data-stu-id="02861-104">Remarks</span></span>  
 <span data-ttu-id="02861-105">使用 `%=` 赋值运算符的表达式，如</span><span class="sxs-lookup"><span data-stu-id="02861-105">An expression using the `%=` assignment operator, such as</span></span>  
  
```  
x %= y  
```  
  
 <span data-ttu-id="02861-106">等效于</span><span class="sxs-lookup"><span data-stu-id="02861-106">is equivalent to</span></span>  
  
```  
x = x % y  
```  
  
 <span data-ttu-id="02861-107">不同的是 `x` 只计算一次。</span><span class="sxs-lookup"><span data-stu-id="02861-107">except that `x` is only evaluated once.</span></span> <span data-ttu-id="02861-108">针对数值类型预定义了 [% 运算符](../../../csharp/language-reference/operators/modulus-operator.md)以计算除法的余数。</span><span class="sxs-lookup"><span data-stu-id="02861-108">The [% operator](../../../csharp/language-reference/operators/modulus-operator.md) is predefined for numeric types to compute the remainder after division.</span></span>  
  
 <span data-ttu-id="02861-109">不能直接重载 `%=` 运算符，但用户定义的类型可重载 [% 运算符](../../../csharp/language-reference/operators/modulus-operator.md)（请参阅[运算符（C# 参考）](../../../csharp/language-reference/keywords/operator.md)）。</span><span class="sxs-lookup"><span data-stu-id="02861-109">The `%=` operator cannot be overloaded directly, but user-defined types can overload the [% operator](../../../csharp/language-reference/operators/modulus-operator.md) (see [operator (C# Reference)](../../../csharp/language-reference/keywords/operator.md)).</span></span>  
  
## <a name="example"></a><span data-ttu-id="02861-110">示例</span><span class="sxs-lookup"><span data-stu-id="02861-110">Example</span></span>  
 <span data-ttu-id="02861-111">[!code-cs[csRefOperators#4](../../../csharp/language-reference/operators/codesnippet/CSharp/modulus-assignment-operator_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="02861-111">[!code-cs[csRefOperators#4](../../../csharp/language-reference/operators/codesnippet/CSharp/modulus-assignment-operator_1.cs)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="02861-112">另请参阅</span><span class="sxs-lookup"><span data-stu-id="02861-112">See Also</span></span>  
 <span data-ttu-id="02861-113">[C# 参考](../../../csharp/language-reference/index.md) </span><span class="sxs-lookup"><span data-stu-id="02861-113">[C# Reference](../../../csharp/language-reference/index.md) </span></span>  
 <span data-ttu-id="02861-114">[C# 编程指南](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="02861-114">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 [<span data-ttu-id="02861-115">C# 运算符</span><span class="sxs-lookup"><span data-stu-id="02861-115">C# Operators</span></span>](../../../csharp/language-reference/operators/index.md)

