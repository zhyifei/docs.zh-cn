---
title: '% 运算符（C# 参考）'
ms.date: 07/20/2015
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- '%_CSharpKeyword'
helpviewer_keywords:
- modulus operator [C#]
- '% operator [C#]'
ms.assetid: 3b74f4f9-fd9c-45e7-84fa-c8d71a0dfad7
caps.latest.revision: 15
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: cea4aa03424e93f3ec144126d73c63931a737b54
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="-operator-c-reference"></a><span data-ttu-id="94eba-102">% 运算符（C# 参考）</span><span class="sxs-lookup"><span data-stu-id="94eba-102">% Operator (C# Reference)</span></span>
<span data-ttu-id="94eba-103">`%` 运算符计算第一个操作数除以第二个操作数后的余数。</span><span class="sxs-lookup"><span data-stu-id="94eba-103">The `%` operator computes the remainder after dividing its first operand by its second.</span></span> <span data-ttu-id="94eba-104">所有数值类型都已预定义余数运算符。</span><span class="sxs-lookup"><span data-stu-id="94eba-104">All numeric types have predefined remainder operators.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="94eba-105">备注</span><span class="sxs-lookup"><span data-stu-id="94eba-105">Remarks</span></span>  
 <span data-ttu-id="94eba-106">用户定义的类型可以重载 `%` 运算符（请参阅[运算符](../../../csharp/language-reference/keywords/operator.md)）。</span><span class="sxs-lookup"><span data-stu-id="94eba-106">User-defined types can overload the `%` operator (see [operator](../../../csharp/language-reference/keywords/operator.md)).</span></span> <span data-ttu-id="94eba-107">重载二元运算符时，也会隐式重载相应的赋值运算符（若有）。</span><span class="sxs-lookup"><span data-stu-id="94eba-107">When a binary operator is overloaded, the corresponding assignment operator, if any, is also implicitly overloaded.</span></span>  
  
## <a name="example"></a><span data-ttu-id="94eba-108">示例</span><span class="sxs-lookup"><span data-stu-id="94eba-108">Example</span></span>  
 [!code-csharp[csRefOperators#9](../../../csharp/language-reference/operators/codesnippet/CSharp/modulus-operator_1.cs)]  
  
## <a name="comments"></a><span data-ttu-id="94eba-109">注释</span><span class="sxs-lookup"><span data-stu-id="94eba-109">Comments</span></span>  
 <span data-ttu-id="94eba-110">请注意与双精度类型关联的舍入误差。</span><span class="sxs-lookup"><span data-stu-id="94eba-110">Note the round-off errors associated with the double type.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="94eba-111">另请参阅</span><span class="sxs-lookup"><span data-stu-id="94eba-111">See Also</span></span>  
 [<span data-ttu-id="94eba-112">C# 参考</span><span class="sxs-lookup"><span data-stu-id="94eba-112">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
 [<span data-ttu-id="94eba-113">C# 编程指南</span><span class="sxs-lookup"><span data-stu-id="94eba-113">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="94eba-114">C# 运算符</span><span class="sxs-lookup"><span data-stu-id="94eba-114">C# Operators</span></span>](../../../csharp/language-reference/operators/index.md)
