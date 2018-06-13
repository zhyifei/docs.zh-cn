---
title: '! 运算符（C# 参考）'
ms.date: 07/20/2015
f1_keywords:
- '!_CSharpKeyword'
helpviewer_keywords:
- '! operator [C#]'
- logical negation operator (!) [C#]
- NOT operator [C#]
ms.assetid: f5ae133f-8f64-4560-b34f-cd9cd5eed4ad
ms.openlocfilehash: 13a210f76cfdb006133243e9ae99e7bd47f35402
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33273918"
---
# <a name="-operator-c-reference"></a><span data-ttu-id="97d72-103">!</span><span class="sxs-lookup"><span data-stu-id="97d72-103">!</span></span> <span data-ttu-id="97d72-104">运算符（C# 参考）</span><span class="sxs-lookup"><span data-stu-id="97d72-104">Operator (C# Reference)</span></span>
<span data-ttu-id="97d72-105">逻辑非运算符 (`!`) 是一种否定其操作数的一元运算符。</span><span class="sxs-lookup"><span data-stu-id="97d72-105">The logical negation operator (`!`) is a unary operator that negates its operand.</span></span> <span data-ttu-id="97d72-106">它针对 `bool` 定义，当且仅当其操作数为 `false` 时返回 `true`。</span><span class="sxs-lookup"><span data-stu-id="97d72-106">It is defined for `bool` and returns `true` if and only if its operand is `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="97d72-107">备注</span><span class="sxs-lookup"><span data-stu-id="97d72-107">Remarks</span></span>  
 <span data-ttu-id="97d72-108">用户定义的类型可以重载 `!` 运算符（请参阅[运算符](../../../csharp/language-reference/keywords/operator.md)）。</span><span class="sxs-lookup"><span data-stu-id="97d72-108">User-defined types can overload the `!` operator (see [operator](../../../csharp/language-reference/keywords/operator.md)).</span></span>  
  
## <a name="example"></a><span data-ttu-id="97d72-109">示例</span><span class="sxs-lookup"><span data-stu-id="97d72-109">Example</span></span>  
 [!code-csharp[csRefOperators#7](../../../csharp/language-reference/operators/codesnippet/CSharp/logical-negation-operator_1.cs)]  
  
## <a name="see-also"></a><span data-ttu-id="97d72-110">请参阅</span><span class="sxs-lookup"><span data-stu-id="97d72-110">See Also</span></span>  
 [<span data-ttu-id="97d72-111">C# 参考</span><span class="sxs-lookup"><span data-stu-id="97d72-111">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
 [<span data-ttu-id="97d72-112">C# 编程指南</span><span class="sxs-lookup"><span data-stu-id="97d72-112">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="97d72-113">C# 运算符</span><span class="sxs-lookup"><span data-stu-id="97d72-113">C# Operators</span></span>](../../../csharp/language-reference/operators/index.md)
