---
title: "/= 运算符（C# 参考）"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- /=_CSharpKeyword
dev_langs:
- CSharp
helpviewer_keywords:
- division assignment operator (/=) [C#]
- /= (division assignment operator) [C#]
ms.assetid: 50fc02b0-ee9c-4c3e-b58d-d591282caf1c
caps.latest.revision: 17
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
ms.openlocfilehash: 5e105bf11f5413d77d62be4177ed22ba420312c3
ms.contentlocale: zh-cn
ms.lasthandoff: 07/28/2017

---
# <a name="-operator-c-reference"></a><span data-ttu-id="3242a-102">/= 运算符（C# 参考）</span><span class="sxs-lookup"><span data-stu-id="3242a-102">/= Operator (C# Reference)</span></span>
<span data-ttu-id="3242a-103">除法赋值运算符。</span><span class="sxs-lookup"><span data-stu-id="3242a-103">The division assignment operator.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="3242a-104">备注</span><span class="sxs-lookup"><span data-stu-id="3242a-104">Remarks</span></span>  
 <span data-ttu-id="3242a-105">使用 `/=` 赋值运算符的表达式，如</span><span class="sxs-lookup"><span data-stu-id="3242a-105">An expression using the `/=` assignment operator, such as</span></span>  
  
```  
x /= y  
```  
  
 <span data-ttu-id="3242a-106">等效于</span><span class="sxs-lookup"><span data-stu-id="3242a-106">is equivalent to</span></span>  
  
```  
x = x / y  
```  
  
 <span data-ttu-id="3242a-107">不同的是 `x` 只计算一次。</span><span class="sxs-lookup"><span data-stu-id="3242a-107">except that `x` is only evaluated once.</span></span> <span data-ttu-id="3242a-108">为数值类型预定义了 [/ 运算符](../../../csharp/language-reference/operators/division-operator.md)以进行除法运算。</span><span class="sxs-lookup"><span data-stu-id="3242a-108">The [/ operator](../../../csharp/language-reference/operators/division-operator.md) is predefined for numeric types to perform division.</span></span>  
  
 <span data-ttu-id="3242a-109">不能直接重载 `/=` 运算符，但用户定义的类型可重载 [/ 运算符](../../../csharp/language-reference/operators/division-operator.md)（请参阅[运算符](../../../csharp/language-reference/keywords/operator.md)）。</span><span class="sxs-lookup"><span data-stu-id="3242a-109">The `/=` operator cannot be overloaded directly, but user-defined types can overload the [/ operator](../../../csharp/language-reference/operators/division-operator.md) (see [operator](../../../csharp/language-reference/keywords/operator.md)).</span></span> <span data-ttu-id="3242a-110">对于所有复合赋值运算符，隐式重载二元运算符会重载等效的复合赋值。</span><span class="sxs-lookup"><span data-stu-id="3242a-110">On all compound assignment operators, overloading the binary operator implicitly overloads the equivalent compound assignment.</span></span>  
  
## <a name="example"></a><span data-ttu-id="3242a-111">示例</span><span class="sxs-lookup"><span data-stu-id="3242a-111">Example</span></span>  
 <span data-ttu-id="3242a-112">[!code-cs[csRefOperators#5](codesnippet/CSharp/division-assignment-operator_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="3242a-112">[!code-cs[csRefOperators#5](codesnippet/CSharp/division-assignment-operator_1.cs)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3242a-113">请参阅</span><span class="sxs-lookup"><span data-stu-id="3242a-113">See Also</span></span>  
 <span data-ttu-id="3242a-114">[C# 参考](../../../csharp/language-reference/index.md) </span><span class="sxs-lookup"><span data-stu-id="3242a-114">[C# Reference](../../../csharp/language-reference/index.md) </span></span>  
 <span data-ttu-id="3242a-115">[C# 编程指南](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="3242a-115">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 [<span data-ttu-id="3242a-116">C# 运算符</span><span class="sxs-lookup"><span data-stu-id="3242a-116">C# Operators</span></span>](../../../csharp/language-reference/operators/index.md)

