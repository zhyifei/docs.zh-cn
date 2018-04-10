---
title: '! 运算符（C# 参考）'
ms.date: 07/20/2015
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- '!_CSharpKeyword'
helpviewer_keywords:
- '! operator [C#]'
- logical negation operator (!) [C#]
- NOT operator [C#]
ms.assetid: f5ae133f-8f64-4560-b34f-cd9cd5eed4ad
caps.latest.revision: 13
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 3560be4067fdb7a51c6073d2ec159b7d04c00eaa
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="-operator-c-reference"></a><span data-ttu-id="3e8c4-103">!</span><span class="sxs-lookup"><span data-stu-id="3e8c4-103">!</span></span> <span data-ttu-id="3e8c4-104">运算符（C# 参考）</span><span class="sxs-lookup"><span data-stu-id="3e8c4-104">Operator (C# Reference)</span></span>
<span data-ttu-id="3e8c4-105">逻辑非运算符 (`!`) 是一种否定其操作数的一元运算符。</span><span class="sxs-lookup"><span data-stu-id="3e8c4-105">The logical negation operator (`!`) is a unary operator that negates its operand.</span></span> <span data-ttu-id="3e8c4-106">它针对 `bool` 定义，当且仅当其操作数为 `false` 时返回 `true`。</span><span class="sxs-lookup"><span data-stu-id="3e8c4-106">It is defined for `bool` and returns `true` if and only if its operand is `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="3e8c4-107">备注</span><span class="sxs-lookup"><span data-stu-id="3e8c4-107">Remarks</span></span>  
 <span data-ttu-id="3e8c4-108">用户定义的类型可以重载 `!` 运算符（请参阅[运算符](../../../csharp/language-reference/keywords/operator.md)）。</span><span class="sxs-lookup"><span data-stu-id="3e8c4-108">User-defined types can overload the `!` operator (see [operator](../../../csharp/language-reference/keywords/operator.md)).</span></span>  
  
## <a name="example"></a><span data-ttu-id="3e8c4-109">示例</span><span class="sxs-lookup"><span data-stu-id="3e8c4-109">Example</span></span>  
 [!code-csharp[csRefOperators#7](../../../csharp/language-reference/operators/codesnippet/CSharp/logical-negation-operator_1.cs)]  
  
## <a name="see-also"></a><span data-ttu-id="3e8c4-110">另请参阅</span><span class="sxs-lookup"><span data-stu-id="3e8c4-110">See Also</span></span>  
 [<span data-ttu-id="3e8c4-111">C# 参考</span><span class="sxs-lookup"><span data-stu-id="3e8c4-111">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
 [<span data-ttu-id="3e8c4-112">C# 编程指南</span><span class="sxs-lookup"><span data-stu-id="3e8c4-112">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="3e8c4-113">C# 运算符</span><span class="sxs-lookup"><span data-stu-id="3e8c4-113">C# Operators</span></span>](../../../csharp/language-reference/operators/index.md)
