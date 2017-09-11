---
title: "&amp; 运算符（C# 参考）"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- '&_CSharpKeyword'
dev_langs:
- CSharp
helpviewer_keywords:
- bitwise AND operator [C#]
- ampersand operator (&) [C#]
- '& operator [C#]'
- AND operator (&) [C#]
ms.assetid: afa346d5-90ec-4b1f-a2c8-3881f018741d
caps.latest.revision: 19
author: BillWagner
ms.author: wiwagn
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: d92a860df6fcc9acf14aab4ec558556735ac8aac
ms.contentlocale: zh-cn
ms.lasthandoff: 07/28/2017

---
# <a name="amp-operator-c-reference"></a><span data-ttu-id="3edd6-102">&amp; 运算符（C# 参考）</span><span class="sxs-lookup"><span data-stu-id="3edd6-102">&amp; Operator (C# Reference)</span></span>
<span data-ttu-id="3edd6-103">& 运算符既可作为一元运算符，也可作为二元运算符。</span><span class="sxs-lookup"><span data-stu-id="3edd6-103">The & operator can function as either a unary or a binary operator.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="3edd6-104">备注</span><span class="sxs-lookup"><span data-stu-id="3edd6-104">Remarks</span></span>  
 <span data-ttu-id="3edd6-105">一元 & 运算符返回其操作数的地址（需要 [unsafe](../../../csharp/language-reference/keywords/unsafe.md) 上下文）。</span><span class="sxs-lookup"><span data-stu-id="3edd6-105">The unary & operator returns the address of its operand (requires [unsafe](../../../csharp/language-reference/keywords/unsafe.md) context).</span></span>  
  
 <span data-ttu-id="3edd6-106">为整型类型和 `bool` 预定义了二元 & 运算符。</span><span class="sxs-lookup"><span data-stu-id="3edd6-106">Binary & operators are predefined for the integral types and `bool`.</span></span> <span data-ttu-id="3edd6-107">对于整型类型，& 计算其操作数的逻辑按位 AND。</span><span class="sxs-lookup"><span data-stu-id="3edd6-107">For integral types, & computes the logical bitwise AND of its operands.</span></span> <span data-ttu-id="3edd6-108">对于 `bool` 操作数，& 计算其操作数的逻辑 AND；即，当且仅当其两个操作数皆为 `true` 时，结果才为 `true`。</span><span class="sxs-lookup"><span data-stu-id="3edd6-108">For `bool` operands, & computes the logical AND of its operands; that is, the result is `true` if and only if both its operands are `true`.</span></span>  
  
 <span data-ttu-id="3edd6-109">`&` 运算符计算两个运算符，无论第一个运算符的值是什么。</span><span class="sxs-lookup"><span data-stu-id="3edd6-109">The `&` operator evaluates both operators regardless of the first one's value.</span></span> <span data-ttu-id="3edd6-110">例如: </span><span class="sxs-lookup"><span data-stu-id="3edd6-110">For example:</span></span>  
  
 <span data-ttu-id="3edd6-111">[!code-cs[csRefOperators#37](../../../csharp/language-reference/operators/codesnippet/CSharp/and-operator_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="3edd6-111">[!code-cs[csRefOperators#37](../../../csharp/language-reference/operators/codesnippet/CSharp/and-operator_1.cs)]</span></span>  
  
 <span data-ttu-id="3edd6-112">用户定义的类型可以重载二元 `&` 运算符（请参阅[运算符](../../../csharp/language-reference/keywords/operator.md)）。</span><span class="sxs-lookup"><span data-stu-id="3edd6-112">User-defined types can overload the binary `&` operator (see [operator](../../../csharp/language-reference/keywords/operator.md)).</span></span> <span data-ttu-id="3edd6-113">对整数类型的操作通常可用于枚举。</span><span class="sxs-lookup"><span data-stu-id="3edd6-113">Operations on integral types are generally allowed on enumeration.</span></span> <span data-ttu-id="3edd6-114">重载二元运算符时，也会隐式重载相应的赋值运算符（若有）。</span><span class="sxs-lookup"><span data-stu-id="3edd6-114">When a binary operator is overloaded, the corresponding assignment operator, if any, is also implicitly overloaded.</span></span>  
  
## <a name="example"></a><span data-ttu-id="3edd6-115">示例</span><span class="sxs-lookup"><span data-stu-id="3edd6-115">Example</span></span>  
 <span data-ttu-id="3edd6-116">[!code-cs[csRefOperators#38](../../../csharp/language-reference/operators/codesnippet/CSharp/and-operator_2.cs)]</span><span class="sxs-lookup"><span data-stu-id="3edd6-116">[!code-cs[csRefOperators#38](../../../csharp/language-reference/operators/codesnippet/CSharp/and-operator_2.cs)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3edd6-117">另请参阅</span><span class="sxs-lookup"><span data-stu-id="3edd6-117">See Also</span></span>  
 <span data-ttu-id="3edd6-118">[C# 参考](../../../csharp/language-reference/index.md) </span><span class="sxs-lookup"><span data-stu-id="3edd6-118">[C# Reference](../../../csharp/language-reference/index.md) </span></span>  
 <span data-ttu-id="3edd6-119">[C# 编程指南](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="3edd6-119">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 [<span data-ttu-id="3edd6-120">C# 运算符</span><span class="sxs-lookup"><span data-stu-id="3edd6-120">C# Operators</span></span>](../../../csharp/language-reference/operators/index.md)

