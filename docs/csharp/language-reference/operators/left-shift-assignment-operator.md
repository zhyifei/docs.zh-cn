---
title: "&lt;&lt;= 运算符（C# 参考）"
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
f1_keywords: <<=_CSharpKeyword
helpviewer_keywords:
- <<= operator (left-shift assignment) [C#]
- left shift assignment operator (<<=) [C#]
ms.assetid: 3bc99c78-1edb-4827-86fc-bce6c3048871
caps.latest.revision: "16"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: b5c2a177182561075442afc3f1b76603c6646bd6
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="ltlt-operator-c-reference"></a><span data-ttu-id="453ec-102">&lt;&lt;= 运算符（C# 参考）</span><span class="sxs-lookup"><span data-stu-id="453ec-102">&lt;&lt;= Operator (C# Reference)</span></span>
<span data-ttu-id="453ec-103">左移赋值运算符。</span><span class="sxs-lookup"><span data-stu-id="453ec-103">The left-shift assignment operator.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="453ec-104">备注</span><span class="sxs-lookup"><span data-stu-id="453ec-104">Remarks</span></span>  
 <span data-ttu-id="453ec-105">形式如下的表达式</span><span class="sxs-lookup"><span data-stu-id="453ec-105">An expression of the form</span></span>  
  
```  
x <<= y  
```  
  
 <span data-ttu-id="453ec-106">计算结果为</span><span class="sxs-lookup"><span data-stu-id="453ec-106">is evaluated as</span></span>  
  
```  
x = x << y  
```  
  
 <span data-ttu-id="453ec-107">不同的是 `x` 只计算一次。</span><span class="sxs-lookup"><span data-stu-id="453ec-107">except that `x` is only evaluated once.</span></span> <span data-ttu-id="453ec-108">[<< 运算符](../../../csharp/language-reference/operators/left-shift-operator.md) 将 `x` 向左移动 `y` 指定的位数。</span><span class="sxs-lookup"><span data-stu-id="453ec-108">The [<< operator](../../../csharp/language-reference/operators/left-shift-operator.md) shifts `x` left by the number of bits specified by `y`.</span></span>  
  
 <span data-ttu-id="453ec-109">不能直接重载 `<<=` 运算符，但用户定义的类型可重载 [<< 运算符](../../../csharp/language-reference/operators/left-shift-operator.md)（参阅[运算符](../../../csharp/language-reference/keywords/operator.md)）。</span><span class="sxs-lookup"><span data-stu-id="453ec-109">The `<<=` operator cannot be overloaded directly, but user-defined types can overload the [<< operator](../../../csharp/language-reference/operators/left-shift-operator.md) (see [operator](../../../csharp/language-reference/keywords/operator.md)).</span></span>  
  
## <a name="example"></a><span data-ttu-id="453ec-110">示例</span><span class="sxs-lookup"><span data-stu-id="453ec-110">Example</span></span>  
 [!code-csharp[csRefOperators#12](../../../csharp/language-reference/operators/codesnippet/CSharp/left-shift-assignment-operator_1.cs)]  
  
## <a name="see-also"></a><span data-ttu-id="453ec-111">另请参阅</span><span class="sxs-lookup"><span data-stu-id="453ec-111">See Also</span></span>  
 [<span data-ttu-id="453ec-112">C# 参考</span><span class="sxs-lookup"><span data-stu-id="453ec-112">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
 [<span data-ttu-id="453ec-113">C# 编程指南</span><span class="sxs-lookup"><span data-stu-id="453ec-113">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="453ec-114">C# 运算符</span><span class="sxs-lookup"><span data-stu-id="453ec-114">C# Operators</span></span>](../../../csharp/language-reference/operators/index.md)
