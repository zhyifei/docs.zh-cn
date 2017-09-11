---
title: "&lt;&lt;= 运算符（C# 参考）"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- <<=_CSharpKeyword
dev_langs:
- CSharp
helpviewer_keywords:
- <<= operator (left-shift assignment) [C#]
- left shift assignment operator (<<=) [C#]
ms.assetid: 3bc99c78-1edb-4827-86fc-bce6c3048871
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
ms.openlocfilehash: fd562a538891a5592cc724e74cffb3d086248898
ms.contentlocale: zh-cn
ms.lasthandoff: 07/28/2017

---
# <a name="ltlt-operator-c-reference"></a><span data-ttu-id="0d8eb-102">&lt;&lt;= 运算符（C# 参考）</span><span class="sxs-lookup"><span data-stu-id="0d8eb-102">&lt;&lt;= Operator (C# Reference)</span></span>
<span data-ttu-id="0d8eb-103">左移赋值运算符。</span><span class="sxs-lookup"><span data-stu-id="0d8eb-103">The left-shift assignment operator.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="0d8eb-104">备注</span><span class="sxs-lookup"><span data-stu-id="0d8eb-104">Remarks</span></span>  
 <span data-ttu-id="0d8eb-105">形式如下的表达式</span><span class="sxs-lookup"><span data-stu-id="0d8eb-105">An expression of the form</span></span>  
  
```  
x <<= y  
```  
  
 <span data-ttu-id="0d8eb-106">计算结果为</span><span class="sxs-lookup"><span data-stu-id="0d8eb-106">is evaluated as</span></span>  
  
```  
x = x << y  
```  
  
 <span data-ttu-id="0d8eb-107">不同的是 `x` 只计算一次。</span><span class="sxs-lookup"><span data-stu-id="0d8eb-107">except that `x` is only evaluated once.</span></span> <span data-ttu-id="0d8eb-108">[<< 运算符](../../../csharp/language-reference/operators/left-shift-operator.md) 将 `x` 向左移动 `y` 指定的位数。</span><span class="sxs-lookup"><span data-stu-id="0d8eb-108">The [<< operator](../../../csharp/language-reference/operators/left-shift-operator.md) shifts `x` left by the number of bits specified by `y`.</span></span>  
  
 <span data-ttu-id="0d8eb-109">不能直接重载 `<<=` 运算符，但用户定义的类型可重载 [<< 运算符](../../../csharp/language-reference/operators/left-shift-operator.md)（参阅[运算符](../../../csharp/language-reference/keywords/operator.md)）。</span><span class="sxs-lookup"><span data-stu-id="0d8eb-109">The `<<=` operator cannot be overloaded directly, but user-defined types can overload the [<< operator](../../../csharp/language-reference/operators/left-shift-operator.md) (see [operator](../../../csharp/language-reference/keywords/operator.md)).</span></span>  
  
## <a name="example"></a><span data-ttu-id="0d8eb-110">示例</span><span class="sxs-lookup"><span data-stu-id="0d8eb-110">Example</span></span>  
 <span data-ttu-id="0d8eb-111">[!code-cs[csRefOperators#12](../../../csharp/language-reference/operators/codesnippet/CSharp/left-shift-assignment-operator_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="0d8eb-111">[!code-cs[csRefOperators#12](../../../csharp/language-reference/operators/codesnippet/CSharp/left-shift-assignment-operator_1.cs)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0d8eb-112">另请参阅</span><span class="sxs-lookup"><span data-stu-id="0d8eb-112">See Also</span></span>  
 <span data-ttu-id="0d8eb-113">[C# 参考](../../../csharp/language-reference/index.md) </span><span class="sxs-lookup"><span data-stu-id="0d8eb-113">[C# Reference](../../../csharp/language-reference/index.md) </span></span>  
 <span data-ttu-id="0d8eb-114">[C# 编程指南](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="0d8eb-114">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 [<span data-ttu-id="0d8eb-115">C# 运算符</span><span class="sxs-lookup"><span data-stu-id="0d8eb-115">C# Operators</span></span>](../../../csharp/language-reference/operators/index.md)

