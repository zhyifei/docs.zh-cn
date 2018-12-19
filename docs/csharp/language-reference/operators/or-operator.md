---
title: '| 运算符 - C# 参考'
ms.custom: seodec18
ms.date: 07/20/2015
f1_keywords:
- '|_CSharpKeyword'
helpviewer_keywords:
- bitwise OR operator [C#]
- '| operator [C#]'
- binary operator (|) [C#]
ms.assetid: 82d6bb78-54c8-40bf-b679-531180ddaf70
ms.openlocfilehash: 19a37bbb54d2ef3e15e4465df05c9b6df705206c
ms.sourcegitcommit: bdd930b5df20a45c29483d905526a2a3e4d17c5b
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2018
ms.locfileid: "53240354"
---
# <a name="-operator-c-reference"></a><span data-ttu-id="4323f-102">| 运算符（C# 参考）</span><span class="sxs-lookup"><span data-stu-id="4323f-102">| Operator (C# Reference)</span></span>
<span data-ttu-id="4323f-103">针对整型类型和 `bool` 预定义了二元 `|` 运算符。</span><span class="sxs-lookup"><span data-stu-id="4323f-103">Binary `|` operators are predefined for the integral types and `bool`.</span></span> <span data-ttu-id="4323f-104">对于整型类型，`|` 会计算其操作数的按位 OR。</span><span class="sxs-lookup"><span data-stu-id="4323f-104">For integral types, `|` computes the bitwise OR of its operands.</span></span> <span data-ttu-id="4323f-105">对于 `bool` 操作数，`|` 会计算其操作数的逻辑 OR；即，当且仅当其两个操作数皆为 `false` 时，结果才为 `false`。</span><span class="sxs-lookup"><span data-stu-id="4323f-105">For `bool` operands, `|` computes the logical OR of its operands; that is, the result is `false` if and only if both its operands are `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="4323f-106">备注</span><span class="sxs-lookup"><span data-stu-id="4323f-106">Remarks</span></span>  
 <span data-ttu-id="4323f-107">二元 `|` 运算符计算两个操作数，无论第一个操作数的值是什么。这与[条件 OR 运算符](conditional-or-operator.md) `||` 相反。</span><span class="sxs-lookup"><span data-stu-id="4323f-107">The binary `|` operator evaluates both operands regardless of the first one's value, in contrast to the [conditional-OR operator](conditional-or-operator.md) `||`.</span></span>
 
 <span data-ttu-id="4323f-108">用户定义的类型可以重载 `|` 运算符（请参阅[运算符](../../../csharp/language-reference/keywords/operator.md)）。</span><span class="sxs-lookup"><span data-stu-id="4323f-108">User-defined types can overload the `|` operator (see [operator](../../../csharp/language-reference/keywords/operator.md)).</span></span>  
  
## <a name="example"></a><span data-ttu-id="4323f-109">示例</span><span class="sxs-lookup"><span data-stu-id="4323f-109">Example</span></span>  
 [!code-csharp[csRefOperators#31](../../../csharp/language-reference/operators/codesnippet/CSharp/or-operator_1.cs)]  
  
## <a name="see-also"></a><span data-ttu-id="4323f-110">请参阅</span><span class="sxs-lookup"><span data-stu-id="4323f-110">See Also</span></span>

- [<span data-ttu-id="4323f-111">C# 参考</span><span class="sxs-lookup"><span data-stu-id="4323f-111">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
- [<span data-ttu-id="4323f-112">C# 编程指南</span><span class="sxs-lookup"><span data-stu-id="4323f-112">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
- [<span data-ttu-id="4323f-113">C# 运算符</span><span class="sxs-lookup"><span data-stu-id="4323f-113">C# Operators</span></span>](../../../csharp/language-reference/operators/index.md)
