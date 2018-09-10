---
title: () 运算符（C# 参考）
ms.date: 07/20/2015
f1_keywords:
- ()_CSharpKeyword
helpviewer_keywords:
- type conversion [C#], () operator
- cast operator [C#]
- () operator [C#]
ms.assetid: 846e1f94-8a8c-42fc-a42c-fbd38e70d8cc
ms.openlocfilehash: 29097dc4aa0bf712b9b2beda4450820a66472ba7
ms.sourcegitcommit: c7f3e2e9d6ead6cc3acd0d66b10a251d0c66e59d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/09/2018
ms.locfileid: "44179663"
---
# <a name="-operator-c-reference"></a><span data-ttu-id="28551-102">() 运算符（C# 参考）</span><span class="sxs-lookup"><span data-stu-id="28551-102">() Operator (C# Reference)</span></span>
<span data-ttu-id="28551-103">除了用于指定表达式中的运算顺序外，圆括号还用于执行以下任务：</span><span class="sxs-lookup"><span data-stu-id="28551-103">In addition to being used to specify the order of operations in an expression, parentheses are used to perform the following tasks:</span></span>  
  
1.  <span data-ttu-id="28551-104">指定强制转换或类型转换。</span><span class="sxs-lookup"><span data-stu-id="28551-104">Specify casts, or type conversions.</span></span>  
  
     [!code-csharp[csRefOperators#1](../../../csharp/language-reference/operators/codesnippet/CSharp/invocation-operator_1.cs)]  
  
2.  <span data-ttu-id="28551-105">调用方法或委托。</span><span class="sxs-lookup"><span data-stu-id="28551-105">Invoke methods or delegates.</span></span>  
  
     [!code-csharp[csRefOperators#2](../../../csharp/language-reference/operators/codesnippet/CSharp/invocation-operator_2.cs)]  
  
## <a name="remarks"></a><span data-ttu-id="28551-106">备注</span><span class="sxs-lookup"><span data-stu-id="28551-106">Remarks</span></span>  
 <span data-ttu-id="28551-107">强制转换显式调用从一种类型到另一种类型的转换运算符；如果未定义这样的转换运算符，则强制转换失败。</span><span class="sxs-lookup"><span data-stu-id="28551-107">A cast explicitly invokes the conversion operator from one type to another; the cast fails if no such conversion operator is defined.</span></span> <span data-ttu-id="28551-108">若要定义转换运算符，请参阅 [explicit](../../../csharp/language-reference/keywords/explicit.md) 和 [implicit](../../../csharp/language-reference/keywords/implicit.md)。</span><span class="sxs-lookup"><span data-stu-id="28551-108">To define a conversion operator, see [explicit](../../../csharp/language-reference/keywords/explicit.md) and [implicit](../../../csharp/language-reference/keywords/implicit.md).</span></span>  
  
 <span data-ttu-id="28551-109">不能重载 `()` 运算符。</span><span class="sxs-lookup"><span data-stu-id="28551-109">The `()` operator cannot be overloaded.</span></span>  
  
 <span data-ttu-id="28551-110">有关详细信息，请参阅[显式转换和类型转换](../../../csharp/programming-guide/types/casting-and-type-conversions.md)。</span><span class="sxs-lookup"><span data-stu-id="28551-110">For more information, see [Casting and Type Conversions](../../../csharp/programming-guide/types/casting-and-type-conversions.md).</span></span>  
  
 <span data-ttu-id="28551-111">有关方法调用的详细信息，请参阅[方法](../../../csharp/programming-guide/classes-and-structs/methods.md)。</span><span class="sxs-lookup"><span data-stu-id="28551-111">For more information about method invocation, see [Methods](../../../csharp/programming-guide/classes-and-structs/methods.md).</span></span>  
  
## <a name="c-language-specification"></a><span data-ttu-id="28551-112">C# 语言规范</span><span class="sxs-lookup"><span data-stu-id="28551-112">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="28551-113">请参阅</span><span class="sxs-lookup"><span data-stu-id="28551-113">See Also</span></span>

- [<span data-ttu-id="28551-114">C# 参考</span><span class="sxs-lookup"><span data-stu-id="28551-114">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
- [<span data-ttu-id="28551-115">C# 编程指南</span><span class="sxs-lookup"><span data-stu-id="28551-115">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
- [<span data-ttu-id="28551-116">C# 运算符</span><span class="sxs-lookup"><span data-stu-id="28551-116">C# Operators</span></span>](../../../csharp/language-reference/operators/index.md)
