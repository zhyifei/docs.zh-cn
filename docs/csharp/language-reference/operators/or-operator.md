---
title: "| 运算符（C# 参考）"
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
f1_keywords: '|_CSharpKeyword'
helpviewer_keywords:
- bitwise OR operator [C#]
- '| operator [C#]'
- binary operator (|) [C#]
ms.assetid: 82d6bb78-54c8-40bf-b679-531180ddaf70
caps.latest.revision: "15"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 374adc30e6937a68d67bfae152f2546c854b829b
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="-operator-c-reference"></a><span data-ttu-id="f7456-102">| 运算符（C# 参考）</span><span class="sxs-lookup"><span data-stu-id="f7456-102">| Operator (C# Reference)</span></span>
<span data-ttu-id="f7456-103">针对整型类型和 `bool` 预定义了二元 `|` 运算符。</span><span class="sxs-lookup"><span data-stu-id="f7456-103">Binary `|` operators are predefined for the integral types and `bool`.</span></span> <span data-ttu-id="f7456-104">对于整型类型，`|` 会计算其操作数的按位 OR。</span><span class="sxs-lookup"><span data-stu-id="f7456-104">For integral types, `|` computes the bitwise OR of its operands.</span></span> <span data-ttu-id="f7456-105">对于 `bool` 操作数，`|` 会计算其操作数的逻辑 OR；即，当且仅当其两个操作数皆为 `false` 时，结果才为 `false`。</span><span class="sxs-lookup"><span data-stu-id="f7456-105">For `bool` operands, `|` computes the logical OR of its operands; that is, the result is `false` if and only if both its operands are `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f7456-106">备注</span><span class="sxs-lookup"><span data-stu-id="f7456-106">Remarks</span></span>  
 <span data-ttu-id="f7456-107">用户定义的类型可以重载 `|` 运算符（请参阅[运算符](../../../csharp/language-reference/keywords/operator.md)）。</span><span class="sxs-lookup"><span data-stu-id="f7456-107">User-defined types can overload the `|` operator (see [operator](../../../csharp/language-reference/keywords/operator.md)).</span></span>  
  
## <a name="example"></a><span data-ttu-id="f7456-108">示例</span><span class="sxs-lookup"><span data-stu-id="f7456-108">Example</span></span>  
 [!code-csharp[csRefOperators#31](../../../csharp/language-reference/operators/codesnippet/CSharp/or-operator_1.cs)]  
  
## <a name="see-also"></a><span data-ttu-id="f7456-109">另请参阅</span><span class="sxs-lookup"><span data-stu-id="f7456-109">See Also</span></span>  
 [<span data-ttu-id="f7456-110">C# 参考</span><span class="sxs-lookup"><span data-stu-id="f7456-110">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
 [<span data-ttu-id="f7456-111">C# 编程指南</span><span class="sxs-lookup"><span data-stu-id="f7456-111">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="f7456-112">C# 运算符</span><span class="sxs-lookup"><span data-stu-id="f7456-112">C# Operators</span></span>](../../../csharp/language-reference/operators/index.md)
