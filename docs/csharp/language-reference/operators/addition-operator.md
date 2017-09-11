---
title: "+ 运算符（C# 参考）"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- +_CSharpKeyword
dev_langs:
- CSharp
helpviewer_keywords:
- + operator [C#]
- concatenation operator [C#]
- addition operator [C#]
ms.assetid: 93e56486-bb42-43c1-bd43-60af11e64e67
caps.latest.revision: 19
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
ms.openlocfilehash: 5455375148f1924c7fe1cdb10e7924abb83a1565
ms.contentlocale: zh-cn
ms.lasthandoff: 07/28/2017

---
# <a name="-operator-c-reference"></a><span data-ttu-id="c092c-102">+ 运算符（C# 参考）</span><span class="sxs-lookup"><span data-stu-id="c092c-102">+ Operator (C# Reference)</span></span>
<span data-ttu-id="c092c-103">`+` 运算符既可作为一元运算符也可作为二元运算符。</span><span class="sxs-lookup"><span data-stu-id="c092c-103">The `+` operator can function as either a unary or a binary operator.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c092c-104">备注</span><span class="sxs-lookup"><span data-stu-id="c092c-104">Remarks</span></span>  
 <span data-ttu-id="c092c-105">为所有数值类型预定义了一元 `+` 运算符。</span><span class="sxs-lookup"><span data-stu-id="c092c-105">Unary `+` operators are predefined for all numeric types.</span></span> <span data-ttu-id="c092c-106">对数值类型进行一元 `+` 运算的结果就是操作数的值。</span><span class="sxs-lookup"><span data-stu-id="c092c-106">The result of a unary `+` operation on a numeric type is just the value of the operand.</span></span>  
  
 <span data-ttu-id="c092c-107">为数值类型和字符串类型预定义了二元 `+` 运算符。</span><span class="sxs-lookup"><span data-stu-id="c092c-107">Binary `+` operators are predefined for numeric and string types.</span></span> <span data-ttu-id="c092c-108">对于数值类型，+ 计算两个操作数之和。</span><span class="sxs-lookup"><span data-stu-id="c092c-108">For numeric types, + computes the sum of its two operands.</span></span> <span data-ttu-id="c092c-109">当其中的一个操作数是字符串类型或两个操作数都是字符串类型时，+ 将操作数的字符串表示形式串联在一起。</span><span class="sxs-lookup"><span data-stu-id="c092c-109">When one or both operands are of type string, + concatenates the string representations of the operands.</span></span>  
  
 <span data-ttu-id="c092c-110">委托类型也提供二元 `+` 运算符，该运算符执行委托串联。</span><span class="sxs-lookup"><span data-stu-id="c092c-110">Delegate types also provide a binary `+` operator, which performs delegate concatenation.</span></span>  
  
 <span data-ttu-id="c092c-111">用户定义的类型可重载一元 `+` 运算符和二元 `+` 运算符。</span><span class="sxs-lookup"><span data-stu-id="c092c-111">User-defined types can overload the unary `+` and binary `+` operators.</span></span> <span data-ttu-id="c092c-112">对整数类型的操作通常可用于枚举。</span><span class="sxs-lookup"><span data-stu-id="c092c-112">Operations on integral types are generally allowed on enumeration.</span></span> <span data-ttu-id="c092c-113">有关详细信息，请参阅[运算符（C# 参考）](../../../csharp/language-reference/keywords/operator.md)。</span><span class="sxs-lookup"><span data-stu-id="c092c-113">For more information, see [operator (C# Reference)](../../../csharp/language-reference/keywords/operator.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="c092c-114">示例</span><span class="sxs-lookup"><span data-stu-id="c092c-114">Example</span></span>  
 <span data-ttu-id="c092c-115">[!code-cs[csRefOperators#28](../../../csharp/language-reference/operators/codesnippet/CSharp/addition-operator_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="c092c-115">[!code-cs[csRefOperators#28](../../../csharp/language-reference/operators/codesnippet/CSharp/addition-operator_1.cs)]</span></span>  
  
## <a name="c-language-specification"></a><span data-ttu-id="c092c-116">C# 语言规范</span><span class="sxs-lookup"><span data-stu-id="c092c-116">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="c092c-117">请参阅</span><span class="sxs-lookup"><span data-stu-id="c092c-117">See Also</span></span>  
 <span data-ttu-id="c092c-118">[C# 参考](../../../csharp/language-reference/index.md) </span><span class="sxs-lookup"><span data-stu-id="c092c-118">[C# Reference](../../../csharp/language-reference/index.md) </span></span>  
 <span data-ttu-id="c092c-119">[C# 编程指南](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="c092c-119">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 <span data-ttu-id="c092c-120">[C# 运算符](../../../csharp/language-reference/operators/index.md) </span><span class="sxs-lookup"><span data-stu-id="c092c-120">[C# Operators](../../../csharp/language-reference/operators/index.md) </span></span>  
 [<span data-ttu-id="c092c-121">运算符（C# 参考）</span><span class="sxs-lookup"><span data-stu-id="c092c-121">operator (C# Reference)</span></span>](../../../csharp/language-reference/keywords/operator.md)

