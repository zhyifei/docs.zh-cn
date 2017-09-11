---
title: "&gt;&gt;= 运算符（C# 参考）"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- '>>=_CSharpKeyword'
dev_langs:
- CSharp
helpviewer_keywords:
- right shift assignment operator (>>=) [C#]
- '>>= operator (right-shift assignment) [C#]'
ms.assetid: b593778c-b9b4-440d-8b29-c1ac22cb81c0
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
ms.openlocfilehash: 64f387e475681ffc76f113435ba090b40780dda3
ms.contentlocale: zh-cn
ms.lasthandoff: 07/28/2017

---
# <a name="gtgt-operator-c-reference"></a><span data-ttu-id="abfb9-102">&gt;&gt;= 运算符（C# 参考）</span><span class="sxs-lookup"><span data-stu-id="abfb9-102">&gt;&gt;= Operator (C# Reference)</span></span>
<span data-ttu-id="abfb9-103">右移赋值运算符。</span><span class="sxs-lookup"><span data-stu-id="abfb9-103">The right-shift assignment operator.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="abfb9-104">备注</span><span class="sxs-lookup"><span data-stu-id="abfb9-104">Remarks</span></span>  
 <span data-ttu-id="abfb9-105">形式如下的表达式</span><span class="sxs-lookup"><span data-stu-id="abfb9-105">An expression of the form</span></span>  
  
```  
x >>= y  
```  
  
 <span data-ttu-id="abfb9-106">计算结果为</span><span class="sxs-lookup"><span data-stu-id="abfb9-106">is evaluated as</span></span>  
  
```  
x = x >> y  
```  
  
 <span data-ttu-id="abfb9-107">不同的是 `x` 只计算一次。</span><span class="sxs-lookup"><span data-stu-id="abfb9-107">except that `x` is only evaluated once.</span></span> <span data-ttu-id="abfb9-108">[>> 运算符](../../../csharp/language-reference/operators/right-shift-operator.md) 将 `x` 右移 `y` 指定的量。</span><span class="sxs-lookup"><span data-stu-id="abfb9-108">The [>> operator](../../../csharp/language-reference/operators/right-shift-operator.md) shifts `x` right by an amount specified by `y`.</span></span>  
  
 <span data-ttu-id="abfb9-109">不能直接重载 >>= 运算符，但用户定义的类型可重载 [>> 运算符](../../../csharp/language-reference/operators/right-shift-operator.md)（参阅[运算符](../../../csharp/language-reference/keywords/operator.md)）。</span><span class="sxs-lookup"><span data-stu-id="abfb9-109">The >>= operator cannot be overloaded directly, but user-defined types can overload the [>> operator](../../../csharp/language-reference/operators/right-shift-operator.md) (see [operator](../../../csharp/language-reference/keywords/operator.md)).</span></span>  
  
## <a name="example"></a><span data-ttu-id="abfb9-110">示例</span><span class="sxs-lookup"><span data-stu-id="abfb9-110">Example</span></span>  
 <span data-ttu-id="abfb9-111">[!code-cs[csRefOperators#11](../../../csharp/language-reference/operators/codesnippet/CSharp/right-shift-assignment-operator_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="abfb9-111">[!code-cs[csRefOperators#11](../../../csharp/language-reference/operators/codesnippet/CSharp/right-shift-assignment-operator_1.cs)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="abfb9-112">另请参阅</span><span class="sxs-lookup"><span data-stu-id="abfb9-112">See Also</span></span>  
 <span data-ttu-id="abfb9-113">[C# 参考](../../../csharp/language-reference/index.md) </span><span class="sxs-lookup"><span data-stu-id="abfb9-113">[C# Reference](../../../csharp/language-reference/index.md) </span></span>  
 <span data-ttu-id="abfb9-114">[C# 编程指南](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="abfb9-114">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 [<span data-ttu-id="abfb9-115">C# 运算符</span><span class="sxs-lookup"><span data-stu-id="abfb9-115">C# Operators</span></span>](../../../csharp/language-reference/operators/index.md)

