---
title: "*= 运算符（C# 参考）"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- '*=_CSharpKeyword'
dev_langs:
- CSharp
helpviewer_keywords:
- '*= operator [C#]'
- binary multiplication assignment operator (*=) [C#]
ms.assetid: 2e472155-59db-4dbf-bb94-bcccfa1a794d
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
ms.openlocfilehash: 2969ba3ce303da591353fd0114dccf752e63f2c3
ms.contentlocale: zh-cn
ms.lasthandoff: 07/28/2017

---
# <a name="-operator-c-reference"></a><span data-ttu-id="4d10f-102">*= 运算符（C# 参考）</span><span class="sxs-lookup"><span data-stu-id="4d10f-102">*= Operator (C# Reference)</span></span>
<span data-ttu-id="4d10f-103">二进制乘法赋值运算符。</span><span class="sxs-lookup"><span data-stu-id="4d10f-103">The binary multiplication assignment operator.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="4d10f-104">备注</span><span class="sxs-lookup"><span data-stu-id="4d10f-104">Remarks</span></span>  
 <span data-ttu-id="4d10f-105">使用 `*=` 赋值运算符的表达式，如</span><span class="sxs-lookup"><span data-stu-id="4d10f-105">An expression using the `*=` assignment operator, such as</span></span>  
  
```  
x *= y  
```  
  
 <span data-ttu-id="4d10f-106">等效于</span><span class="sxs-lookup"><span data-stu-id="4d10f-106">is equivalent to</span></span>  
  
```  
x = x * y  
```  
  
 <span data-ttu-id="4d10f-107">不同的是 `x` 只计算一次。</span><span class="sxs-lookup"><span data-stu-id="4d10f-107">except that `x` is only evaluated once.</span></span> <span data-ttu-id="4d10f-108">针对数值类型预定义了 [* 运算符](../../../csharp/language-reference/operators/multiplication-operator.md)以进行乘法运算。</span><span class="sxs-lookup"><span data-stu-id="4d10f-108">The [* operator](../../../csharp/language-reference/operators/multiplication-operator.md) is predefined for numeric types to perform multiplication.</span></span>  
  
 <span data-ttu-id="4d10f-109">不能直接重载 `*=` 运算符，但用户定义的类型可重载 [* 运算符](../../../csharp/language-reference/operators/multiplication-operator.md)（请参阅[运算符](../../../csharp/language-reference/keywords/operator.md)）。</span><span class="sxs-lookup"><span data-stu-id="4d10f-109">The `*=` operator cannot be overloaded directly, but user-defined types can overload the [* operator](../../../csharp/language-reference/operators/multiplication-operator.md) (see [operator](../../../csharp/language-reference/keywords/operator.md)).</span></span>  
  
## <a name="example"></a><span data-ttu-id="4d10f-110">示例</span><span class="sxs-lookup"><span data-stu-id="4d10f-110">Example</span></span>  
 <span data-ttu-id="4d10f-111">[!code-cs[csRefOperators#13](../../../csharp/language-reference/operators/codesnippet/CSharp/multiplication-assignment-operator_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="4d10f-111">[!code-cs[csRefOperators#13](../../../csharp/language-reference/operators/codesnippet/CSharp/multiplication-assignment-operator_1.cs)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4d10f-112">另请参阅</span><span class="sxs-lookup"><span data-stu-id="4d10f-112">See Also</span></span>  
 <span data-ttu-id="4d10f-113">[C# 参考](../../../csharp/language-reference/index.md) </span><span class="sxs-lookup"><span data-stu-id="4d10f-113">[C# Reference](../../../csharp/language-reference/index.md) </span></span>  
 <span data-ttu-id="4d10f-114">[C# 编程指南](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="4d10f-114">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 [<span data-ttu-id="4d10f-115">C# 运算符</span><span class="sxs-lookup"><span data-stu-id="4d10f-115">C# Operators</span></span>](../../../csharp/language-reference/operators/index.md)

