---
title: "|= 运算符（C# 参考）"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- '|=_CSharpKeyword'
dev_langs:
- CSharp
helpviewer_keywords:
- OR assignment operator (|=) [C#]
- '|= operator (OR assignment) [C#]'
ms.assetid: 8315b8cf-dd15-402f-92f0-c7db931696ca
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
ms.openlocfilehash: f1c0a92414739efc2ab091871e80852737fdf931
ms.contentlocale: zh-cn
ms.lasthandoff: 07/28/2017

---
# <a name="-operator-c-reference"></a><span data-ttu-id="63ede-102">|= 运算符（C# 参考）</span><span class="sxs-lookup"><span data-stu-id="63ede-102">|= Operator (C# Reference)</span></span>
<span data-ttu-id="63ede-103">OR 赋值运算符。</span><span class="sxs-lookup"><span data-stu-id="63ede-103">The OR assignment operator.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="63ede-104">备注</span><span class="sxs-lookup"><span data-stu-id="63ede-104">Remarks</span></span>  
 <span data-ttu-id="63ede-105">使用 `|=` 赋值运算符的表达式，如</span><span class="sxs-lookup"><span data-stu-id="63ede-105">An expression using the `|=` assignment operator, such as</span></span>  
  
```  
x |= y  
```  
  
 <span data-ttu-id="63ede-106">等效于</span><span class="sxs-lookup"><span data-stu-id="63ede-106">is equivalent to</span></span>  
  
```  
x = x | y  
```  
  
 <span data-ttu-id="63ede-107">不同的是 `x` 只计算一次。</span><span class="sxs-lookup"><span data-stu-id="63ede-107">except that `x` is only evaluated once.</span></span> <span data-ttu-id="63ede-108">[&#124; 运算符](../../../csharp/language-reference/operators/or-operator.md) 对整型操作数执行按位逻辑 OR 运算，对 bool 操作数执行逻辑 OR 运算。</span><span class="sxs-lookup"><span data-stu-id="63ede-108">The [&#124; operator](../../../csharp/language-reference/operators/or-operator.md) performs a bitwise logical OR operation on integral operands and logical OR on bool operands.</span></span>  
  
 <span data-ttu-id="63ede-109">不能直接重载 `|=` 运算符，但用户定义的类型可重载 [&#124; 运算符](../../../csharp/language-reference/operators/or-operator.md)（请参阅[运算符](../../../csharp/language-reference/keywords/operator.md)）。</span><span class="sxs-lookup"><span data-stu-id="63ede-109">The `|=` operator cannot be overloaded directly, but user-defined types can overload the [&#124; operator](../../../csharp/language-reference/operators/or-operator.md) (see [operator](../../../csharp/language-reference/keywords/operator.md)).</span></span>  
  
## <a name="example"></a><span data-ttu-id="63ede-110">示例</span><span class="sxs-lookup"><span data-stu-id="63ede-110">Example</span></span>  
 <span data-ttu-id="63ede-111">[!code-cs[csRefOperators#10](../../../csharp/language-reference/operators/codesnippet/CSharp/or-assignment-operator_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="63ede-111">[!code-cs[csRefOperators#10](../../../csharp/language-reference/operators/codesnippet/CSharp/or-assignment-operator_1.cs)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="63ede-112">另请参阅</span><span class="sxs-lookup"><span data-stu-id="63ede-112">See Also</span></span>  
 <span data-ttu-id="63ede-113">[C# 参考](../../../csharp/language-reference/index.md) </span><span class="sxs-lookup"><span data-stu-id="63ede-113">[C# Reference](../../../csharp/language-reference/index.md) </span></span>  
 <span data-ttu-id="63ede-114">[C# 编程指南](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="63ede-114">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 [<span data-ttu-id="63ede-115">C# 运算符</span><span class="sxs-lookup"><span data-stu-id="63ede-115">C# Operators</span></span>](../../../csharp/language-reference/operators/index.md)

