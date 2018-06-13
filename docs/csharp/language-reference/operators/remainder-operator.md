---
title: '% 运算符（C# 参考）'
ms.date: 04/04/2018
f1_keywords:
- '%_CSharpKeyword'
helpviewer_keywords:
- remainder operator [C#]
- '% operator [C#]'
ms.assetid: 3b74f4f9-fd9c-45e7-84fa-c8d71a0dfad7
ms.openlocfilehash: b906feb22aaec97e58da562b615baae01f3e0719
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33271062"
---
# <a name="-operator-c-reference"></a><span data-ttu-id="a170f-102">% 运算符（C# 参考）</span><span class="sxs-lookup"><span data-stu-id="a170f-102">% Operator (C# Reference)</span></span>
<span data-ttu-id="a170f-103">余数运算符 (`%`) 计算第一个操作数除以第二个操作数后的余数。</span><span class="sxs-lookup"><span data-stu-id="a170f-103">The remainder operator (`%`) computes the remainder after dividing its first operand by its second.</span></span> <span data-ttu-id="a170f-104">所有数值类型都已预定义余数运算符。</span><span class="sxs-lookup"><span data-stu-id="a170f-104">All numeric types have predefined remainder operators.</span></span> 
  
## <a name="remarks"></a><span data-ttu-id="a170f-105">备注</span><span class="sxs-lookup"><span data-stu-id="a170f-105">Remarks</span></span>  
 <span data-ttu-id="a170f-106">公式 `a % b` 始终返回介于 `(-b, b)` 范围（不含边界值）内的值（绝不会返回 `b` 或 `-b`），同时保留被除数的符号。</span><span class="sxs-lookup"><span data-stu-id="a170f-106">The formula `a % b` will always return a value on the range `(-b, b)`, exclusive (it can never return `b` or `-b`), keeping the sign of the dividend.</span></span> <span data-ttu-id="a170f-107">对于整数除法，余数运算符执行规则 `a % b = a - (a / b) * b`。</span><span class="sxs-lookup"><span data-stu-id="a170f-107">For integer division, the remainder operator satisfies the rule `a % b = a - (a / b) * b`.</span></span>
  
 <span data-ttu-id="a170f-108">不要将这与规范取模相混淆，后者虽然执行类似的规则，但采用 Floor 除法，并返回介于 `[0, b)` 范围内的值。</span><span class="sxs-lookup"><span data-stu-id="a170f-108">This is not to be confused with canonical modulus, which satisfies a similar rule but with floored division and returns values on the range `[0, b)`.</span></span> <span data-ttu-id="a170f-109">C# 没有规范取模运算符。</span><span class="sxs-lookup"><span data-stu-id="a170f-109">C# does not have an operator for canonical modulus.</span></span> <span data-ttu-id="a170f-110">不过，行为与正被除数相同。</span><span class="sxs-lookup"><span data-stu-id="a170f-110">However, the behavior is the same for positive dividends.</span></span>
  
 <span data-ttu-id="a170f-111">用户定义的类型可以重载 `%` 运算符（请参阅[运算符](../../../csharp/language-reference/keywords/operator.md)）。</span><span class="sxs-lookup"><span data-stu-id="a170f-111">User-defined types can overload the `%` operator (see [operator](../../../csharp/language-reference/keywords/operator.md)).</span></span> <span data-ttu-id="a170f-112">重载二元运算符时，也会隐式重载相应的赋值运算符（若有）。</span><span class="sxs-lookup"><span data-stu-id="a170f-112">When a binary operator is overloaded, the corresponding assignment operator, if any, is also implicitly overloaded.</span></span>  
  
## <a name="example"></a><span data-ttu-id="a170f-113">示例</span><span class="sxs-lookup"><span data-stu-id="a170f-113">Example</span></span>  
 [!code-csharp[csRefOperators#9](../../../csharp/language-reference/operators/codesnippet/CSharp/remainder-operator_1.cs)]  
  
## <a name="comments"></a><span data-ttu-id="a170f-114">注释</span><span class="sxs-lookup"><span data-stu-id="a170f-114">Comments</span></span>  
 <span data-ttu-id="a170f-115">请注意与双精度类型关联的舍入误差。</span><span class="sxs-lookup"><span data-stu-id="a170f-115">Note the round-off errors associated with the double type.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a170f-116">请参阅</span><span class="sxs-lookup"><span data-stu-id="a170f-116">See Also</span></span>  
 [<span data-ttu-id="a170f-117">C# 参考</span><span class="sxs-lookup"><span data-stu-id="a170f-117">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
 [<span data-ttu-id="a170f-118">C# 编程指南</span><span class="sxs-lookup"><span data-stu-id="a170f-118">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="a170f-119">C# 运算符</span><span class="sxs-lookup"><span data-stu-id="a170f-119">C# Operators</span></span>](../../../csharp/language-reference/operators/index.md)
