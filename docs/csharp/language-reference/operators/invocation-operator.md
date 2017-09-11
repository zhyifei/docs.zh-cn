---
title: "() 运算符（C# 参考）"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- ()_CSharpKeyword
dev_langs:
- CSharp
helpviewer_keywords:
- type conversion [C#], () operator
- cast operator [C#]
- () operator [C#]
ms.assetid: 846e1f94-8a8c-42fc-a42c-fbd38e70d8cc
caps.latest.revision: 22
author: BillWagner
ms.author: wiwagn
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 1b0a683880f0791ee69ea5971756d104323b4303
ms.contentlocale: zh-cn
ms.lasthandoff: 07/28/2017

---
# <a name="-operator-c-reference"></a><span data-ttu-id="51a56-102">() 运算符（C# 参考）</span><span class="sxs-lookup"><span data-stu-id="51a56-102">() Operator (C# Reference)</span></span>
<span data-ttu-id="51a56-103">除了用于指定表达式中的运算顺序外，圆括号还用于执行以下任务：</span><span class="sxs-lookup"><span data-stu-id="51a56-103">In addition to being used to specify the order of operations in an expression, parentheses are used to perform the following tasks:</span></span>  
  
1.  <span data-ttu-id="51a56-104">指定强制转换或类型转换。</span><span class="sxs-lookup"><span data-stu-id="51a56-104">Specify casts, or type conversions.</span></span>  
  
     <span data-ttu-id="51a56-105">[!code-cs[csRefOperators#1](../../../csharp/language-reference/operators/codesnippet/CSharp/invocation-operator_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="51a56-105">[!code-cs[csRefOperators#1](../../../csharp/language-reference/operators/codesnippet/CSharp/invocation-operator_1.cs)]</span></span>  
  
2.  <span data-ttu-id="51a56-106">调用方法或委托。</span><span class="sxs-lookup"><span data-stu-id="51a56-106">Invoke methods or delegates.</span></span>  
  
     <span data-ttu-id="51a56-107">[!code-cs[csRefOperators#2](../../../csharp/language-reference/operators/codesnippet/CSharp/invocation-operator_2.cs)]</span><span class="sxs-lookup"><span data-stu-id="51a56-107">[!code-cs[csRefOperators#2](../../../csharp/language-reference/operators/codesnippet/CSharp/invocation-operator_2.cs)]</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="51a56-108">备注</span><span class="sxs-lookup"><span data-stu-id="51a56-108">Remarks</span></span>  
 <span data-ttu-id="51a56-109">强制转换显式调用从一种类型到另一种类型的转换运算符；如果未定义这样的转换运算符，则强制转换失败。</span><span class="sxs-lookup"><span data-stu-id="51a56-109">A cast explicitly invokes the conversion operator from one type to another; the cast fails if no such conversion operator is defined.</span></span> <span data-ttu-id="51a56-110">若要定义转换运算符，请参阅 [explicit](../../../csharp/language-reference/keywords/explicit.md) 和 [implicit](../../../csharp/language-reference/keywords/implicit.md)。</span><span class="sxs-lookup"><span data-stu-id="51a56-110">To define a conversion operator, see [explicit](../../../csharp/language-reference/keywords/explicit.md) and [implicit](../../../csharp/language-reference/keywords/implicit.md).</span></span>  
  
 <span data-ttu-id="51a56-111">不能重载 `()` 运算符。</span><span class="sxs-lookup"><span data-stu-id="51a56-111">The `()` operator cannot be overloaded.</span></span>  
  
 <span data-ttu-id="51a56-112">有关详细信息，请参阅[强制转换和类型转换](../../../csharp/programming-guide/types/casting-and-type-conversions.md)。</span><span class="sxs-lookup"><span data-stu-id="51a56-112">For more information, see [Casting and Type Conversions](../../../csharp/programming-guide/types/casting-and-type-conversions.md).</span></span>  
  
 <span data-ttu-id="51a56-113">强制转换表达式可能会使语法发生歧义。</span><span class="sxs-lookup"><span data-stu-id="51a56-113">A cast expression could lead to ambiguous syntax.</span></span> <span data-ttu-id="51a56-114">例如，表达式 `(x)–y` 既可以解释为强制转换表达式（将 –y 强制转换为类型 x），也可以解释为结合了带括号表达式的相加表达式（计算 x – y 的值）。</span><span class="sxs-lookup"><span data-stu-id="51a56-114">For example, the expression `(x)–y` could be either interpreted as a cast expression (a cast of –y to type x) or as an additive expression combined with a parenthesized expression, which computes the value x – y.</span></span>  
  
 <span data-ttu-id="51a56-115">有关方法调用的详细信息，请参阅[方法](../../../csharp/programming-guide/classes-and-structs/methods.md)。</span><span class="sxs-lookup"><span data-stu-id="51a56-115">For more information about method invocation, see [Methods](../../../csharp/programming-guide/classes-and-structs/methods.md).</span></span>  
  
## <a name="c-language-specification"></a><span data-ttu-id="51a56-116">C# 语言规范</span><span class="sxs-lookup"><span data-stu-id="51a56-116">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="51a56-117">请参阅</span><span class="sxs-lookup"><span data-stu-id="51a56-117">See Also</span></span>  
 <span data-ttu-id="51a56-118">[C# 参考](../../../csharp/language-reference/index.md) </span><span class="sxs-lookup"><span data-stu-id="51a56-118">[C# Reference](../../../csharp/language-reference/index.md) </span></span>  
 <span data-ttu-id="51a56-119">[C# 编程指南](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="51a56-119">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 [<span data-ttu-id="51a56-120">C# 运算符</span><span class="sxs-lookup"><span data-stu-id="51a56-120">C# Operators</span></span>](../../../csharp/language-reference/operators/index.md)

