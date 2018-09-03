---
title: '- 运算符（C# 参考）'
ms.date: 07/20/2015
f1_keywords:
- -_CSharpKeyword
helpviewer_keywords:
- '- operator [C#]'
- subtraction operator (-) [C#]
ms.assetid: 4de7a4fa-c69d-48e6-aff1-3130af970b2d
ms.openlocfilehash: bd852f96ece9c8d5d5e2ec42e802596e795ce04a
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/02/2018
ms.locfileid: "43393423"
---
# <a name="--operator-c-reference"></a><span data-ttu-id="1fc06-102">- 运算符（C# 参考）</span><span class="sxs-lookup"><span data-stu-id="1fc06-102">- Operator (C# Reference)</span></span>
<span data-ttu-id="1fc06-103">`-` 运算符既可作为一元运算符也可作为二元运算符。</span><span class="sxs-lookup"><span data-stu-id="1fc06-103">The `-` operator can function as either a unary or a binary operator.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="1fc06-104">备注</span><span class="sxs-lookup"><span data-stu-id="1fc06-104">Remarks</span></span>  
 <span data-ttu-id="1fc06-105">为所有数值类型预定义了一元 `-` 运算符。</span><span class="sxs-lookup"><span data-stu-id="1fc06-105">Unary `-` operators are predefined for all numeric types.</span></span> <span data-ttu-id="1fc06-106">对数值类型进行一元 `-` 运算的结果是操作数的数值求反运算。</span><span class="sxs-lookup"><span data-stu-id="1fc06-106">The result of a unary `-` operation on a numeric type is the numeric negation of the operand.</span></span>  
  
 <span data-ttu-id="1fc06-107">针对所有数值和枚举类型预定义二元 `-` 运算符，从第一个操作数中减去第一个操作数。</span><span class="sxs-lookup"><span data-stu-id="1fc06-107">Binary `-` operators are predefined for all numeric and enumeration types to subtract the second operand from the first.</span></span>  
  
 <span data-ttu-id="1fc06-108">委托类型也提供二元 `-` 运算符，该运算符执行委托移除。</span><span class="sxs-lookup"><span data-stu-id="1fc06-108">Delegate types also provide a binary `-` operator, which performs delegate removal.</span></span>  
  
 <span data-ttu-id="1fc06-109">用户定义的类型可重载一元 `-` 运算符和二元 `-` 运算符。</span><span class="sxs-lookup"><span data-stu-id="1fc06-109">User-defined types can overload the unary `-` and binary `-` operators.</span></span> <span data-ttu-id="1fc06-110">有关详细信息，请参阅[运算符（C# 参考）](../../../csharp/language-reference/keywords/operator.md)。</span><span class="sxs-lookup"><span data-stu-id="1fc06-110">For more information, see [operator (C# Reference)](../../../csharp/language-reference/keywords/operator.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="1fc06-111">示例</span><span class="sxs-lookup"><span data-stu-id="1fc06-111">Example</span></span>  
 [!code-csharp[csRefOperators#40](../../../csharp/language-reference/operators/codesnippet/CSharp/subtraction-operator_1.cs)]  
  
## <a name="see-also"></a><span data-ttu-id="1fc06-112">请参阅</span><span class="sxs-lookup"><span data-stu-id="1fc06-112">See Also</span></span>

- [<span data-ttu-id="1fc06-113">C# 参考</span><span class="sxs-lookup"><span data-stu-id="1fc06-113">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
- [<span data-ttu-id="1fc06-114">C# 编程指南</span><span class="sxs-lookup"><span data-stu-id="1fc06-114">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
- [<span data-ttu-id="1fc06-115">C# 运算符</span><span class="sxs-lookup"><span data-stu-id="1fc06-115">C# Operators</span></span>](../../../csharp/language-reference/operators/index.md)
