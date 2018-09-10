---
title: '&amp; 运算符（C# 参考）'
ms.date: 04/04/2018
f1_keywords:
- '&_CSharpKeyword'
helpviewer_keywords:
- bitwise AND operator [C#]
- ampersand operator (&) [C#]
- '& operator [C#]'
- AND operator (&) [C#]
ms.assetid: afa346d5-90ec-4b1f-a2c8-3881f018741d
ms.openlocfilehash: b257c7d41618464e26ab3b54bcfb1f1e2c2e420e
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/04/2018
ms.locfileid: "43510973"
---
# <a name="amp-operator-c-reference"></a><span data-ttu-id="e398c-102">&amp; 运算符（C# 参考）</span><span class="sxs-lookup"><span data-stu-id="e398c-102">&amp; Operator (C# Reference)</span></span>
<span data-ttu-id="e398c-103">`&` 运算符既可作为一元运算符也可作为二元运算符。</span><span class="sxs-lookup"><span data-stu-id="e398c-103">The `&` operator can function as either a unary or a binary operator.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="e398c-104">备注</span><span class="sxs-lookup"><span data-stu-id="e398c-104">Remarks</span></span>  
 <span data-ttu-id="e398c-105">一元 `&` 运算符返回操作数的地址（需要 [unsafe](../../../csharp/language-reference/keywords/unsafe.md) 上下文）。</span><span class="sxs-lookup"><span data-stu-id="e398c-105">The unary `&` operator returns the address of its operand (requires [unsafe](../../../csharp/language-reference/keywords/unsafe.md) context).</span></span>  
  
 <span data-ttu-id="e398c-106">针对整型类型和 `bool` 预定义了二元 `&` 运算符。</span><span class="sxs-lookup"><span data-stu-id="e398c-106">Binary `&` operators are predefined for the integral types and `bool`.</span></span> <span data-ttu-id="e398c-107">对于整型类型，& 计算其操作数的逻辑按位 AND。</span><span class="sxs-lookup"><span data-stu-id="e398c-107">For integral types, & computes the logical bitwise AND of its operands.</span></span> <span data-ttu-id="e398c-108">对于 `bool` 操作数，& 计算其操作数的逻辑 AND；即，当且仅当其两个操作数皆为 `true` 时，结果才为 `true`。</span><span class="sxs-lookup"><span data-stu-id="e398c-108">For `bool` operands, & computes the logical AND of its operands; that is, the result is `true` if and only if both its operands are `true`.</span></span>  
  
 <span data-ttu-id="e398c-109">二元 `&` 运算符计算两个操作数，无论第一个操作数的值是什么。这与[条件 AND 运算符](../../../csharp/language-reference/operators/conditional-and-operator.md) `&&` 相反。</span><span class="sxs-lookup"><span data-stu-id="e398c-109">The binary `&` operator evaluates both operands regardless of the first one's value, in contrast to the [conditional AND operator](../../../csharp/language-reference/operators/conditional-and-operator.md) `&&`.</span></span> <span data-ttu-id="e398c-110">例如:</span><span class="sxs-lookup"><span data-stu-id="e398c-110">For example:</span></span>  
  
 [!code-csharp[csRefOperators#37](../../../csharp/language-reference/operators/codesnippet/CSharp/and-operator_1.cs)]  
  
 <span data-ttu-id="e398c-111">用户定义的类型可以重载二元 `&` 运算符（请参阅[运算符](../../../csharp/language-reference/keywords/operator.md)）。</span><span class="sxs-lookup"><span data-stu-id="e398c-111">User-defined types can overload the binary `&` operator (see [operator](../../../csharp/language-reference/keywords/operator.md)).</span></span> <span data-ttu-id="e398c-112">对整数类型的操作通常可用于枚举。</span><span class="sxs-lookup"><span data-stu-id="e398c-112">Operations on integral types are generally allowed on enumeration.</span></span> <span data-ttu-id="e398c-113">重载二元运算符时，也会隐式重载相应的赋值运算符（若有）。</span><span class="sxs-lookup"><span data-stu-id="e398c-113">When a binary operator is overloaded, the corresponding assignment operator, if any, is also implicitly overloaded.</span></span>  
  
## <a name="example"></a><span data-ttu-id="e398c-114">示例</span><span class="sxs-lookup"><span data-stu-id="e398c-114">Example</span></span>  
 [!code-csharp[csRefOperators#38](../../../csharp/language-reference/operators/codesnippet/CSharp/and-operator_2.cs)]  
  
## <a name="see-also"></a><span data-ttu-id="e398c-115">请参阅</span><span class="sxs-lookup"><span data-stu-id="e398c-115">See Also</span></span>

- [<span data-ttu-id="e398c-116">C# 参考</span><span class="sxs-lookup"><span data-stu-id="e398c-116">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
- [<span data-ttu-id="e398c-117">C# 编程指南</span><span class="sxs-lookup"><span data-stu-id="e398c-117">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
- [<span data-ttu-id="e398c-118">C# 运算符</span><span class="sxs-lookup"><span data-stu-id="e398c-118">C# Operators</span></span>](../../../csharp/language-reference/operators/index.md)
