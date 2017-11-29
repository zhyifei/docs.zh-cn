---
title: "&amp; 运算符（C# 参考）"
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
f1_keywords: '&_CSharpKeyword'
helpviewer_keywords:
- bitwise AND operator [C#]
- ampersand operator (&) [C#]
- '& operator [C#]'
- AND operator (&) [C#]
ms.assetid: afa346d5-90ec-4b1f-a2c8-3881f018741d
caps.latest.revision: "19"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: eceee8e01ba46f65c6b182a40d14e62aaba5dd53
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="amp-operator-c-reference"></a><span data-ttu-id="2d88e-102">&amp; 运算符（C# 参考）</span><span class="sxs-lookup"><span data-stu-id="2d88e-102">&amp; Operator (C# Reference)</span></span>
<span data-ttu-id="2d88e-103">& 运算符既可作为一元运算符，也可作为二元运算符。</span><span class="sxs-lookup"><span data-stu-id="2d88e-103">The & operator can function as either a unary or a binary operator.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="2d88e-104">备注</span><span class="sxs-lookup"><span data-stu-id="2d88e-104">Remarks</span></span>  
 <span data-ttu-id="2d88e-105">一元 & 运算符返回其操作数的地址（需要 [unsafe](../../../csharp/language-reference/keywords/unsafe.md) 上下文）。</span><span class="sxs-lookup"><span data-stu-id="2d88e-105">The unary & operator returns the address of its operand (requires [unsafe](../../../csharp/language-reference/keywords/unsafe.md) context).</span></span>  
  
 <span data-ttu-id="2d88e-106">为整型类型和 `bool` 预定义了二元 & 运算符。</span><span class="sxs-lookup"><span data-stu-id="2d88e-106">Binary & operators are predefined for the integral types and `bool`.</span></span> <span data-ttu-id="2d88e-107">对于整型类型，& 计算其操作数的逻辑按位 AND。</span><span class="sxs-lookup"><span data-stu-id="2d88e-107">For integral types, & computes the logical bitwise AND of its operands.</span></span> <span data-ttu-id="2d88e-108">对于 `bool` 操作数，& 计算其操作数的逻辑 AND；即，当且仅当其两个操作数皆为 `true` 时，结果才为 `true`。</span><span class="sxs-lookup"><span data-stu-id="2d88e-108">For `bool` operands, & computes the logical AND of its operands; that is, the result is `true` if and only if both its operands are `true`.</span></span>  
  
 <span data-ttu-id="2d88e-109">`&` 运算符计算两个运算符，无论第一个运算符的值是什么。</span><span class="sxs-lookup"><span data-stu-id="2d88e-109">The `&` operator evaluates both operators regardless of the first one's value.</span></span> <span data-ttu-id="2d88e-110">例如: </span><span class="sxs-lookup"><span data-stu-id="2d88e-110">For example:</span></span>  
  
 [!code-csharp[csRefOperators#37](../../../csharp/language-reference/operators/codesnippet/CSharp/and-operator_1.cs)]  
  
 <span data-ttu-id="2d88e-111">用户定义的类型可以重载二元 `&` 运算符（请参阅[运算符](../../../csharp/language-reference/keywords/operator.md)）。</span><span class="sxs-lookup"><span data-stu-id="2d88e-111">User-defined types can overload the binary `&` operator (see [operator](../../../csharp/language-reference/keywords/operator.md)).</span></span> <span data-ttu-id="2d88e-112">对整数类型的操作通常可用于枚举。</span><span class="sxs-lookup"><span data-stu-id="2d88e-112">Operations on integral types are generally allowed on enumeration.</span></span> <span data-ttu-id="2d88e-113">重载二元运算符时，也会隐式重载相应的赋值运算符（若有）。</span><span class="sxs-lookup"><span data-stu-id="2d88e-113">When a binary operator is overloaded, the corresponding assignment operator, if any, is also implicitly overloaded.</span></span>  
  
## <a name="example"></a><span data-ttu-id="2d88e-114">示例</span><span class="sxs-lookup"><span data-stu-id="2d88e-114">Example</span></span>  
 [!code-csharp[csRefOperators#38](../../../csharp/language-reference/operators/codesnippet/CSharp/and-operator_2.cs)]  
  
## <a name="see-also"></a><span data-ttu-id="2d88e-115">另请参阅</span><span class="sxs-lookup"><span data-stu-id="2d88e-115">See Also</span></span>  
 [<span data-ttu-id="2d88e-116">C# 参考</span><span class="sxs-lookup"><span data-stu-id="2d88e-116">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
 [<span data-ttu-id="2d88e-117">C# 编程指南</span><span class="sxs-lookup"><span data-stu-id="2d88e-117">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="2d88e-118">C# 运算符</span><span class="sxs-lookup"><span data-stu-id="2d88e-118">C# Operators</span></span>](../../../csharp/language-reference/operators/index.md)
