---
title: + 运算符（C# 参考）
ms.date: 07/20/2015
f1_keywords:
- +_CSharpKeyword
helpviewer_keywords:
- + operator [C#]
- concatenation operator [C#]
- addition operator [C#]
ms.assetid: 93e56486-bb42-43c1-bd43-60af11e64e67
ms.openlocfilehash: b49694bc8937c58bd295f0f8e57c378802d0dfb9
ms.sourcegitcommit: e614e0f3b031293e4107f37f752be43652f3f253
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/26/2018
ms.locfileid: "42930707"
---
# <a name="-operator-c-reference"></a><span data-ttu-id="d0401-102">+ 运算符（C# 参考）</span><span class="sxs-lookup"><span data-stu-id="d0401-102">+ Operator (C# Reference)</span></span>
<span data-ttu-id="d0401-103">`+` 运算符既可作为一元运算符也可作为二元运算符。</span><span class="sxs-lookup"><span data-stu-id="d0401-103">The `+` operator can function as either a unary or a binary operator.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="d0401-104">备注</span><span class="sxs-lookup"><span data-stu-id="d0401-104">Remarks</span></span>  
 <span data-ttu-id="d0401-105">为所有数值类型预定义了一元 `+` 运算符。</span><span class="sxs-lookup"><span data-stu-id="d0401-105">Unary `+` operators are predefined for all numeric types.</span></span> <span data-ttu-id="d0401-106">对数值类型进行一元 `+` 运算的结果就是操作数的值。</span><span class="sxs-lookup"><span data-stu-id="d0401-106">The result of a unary `+` operation on a numeric type is just the value of the operand.</span></span>  
  
 <span data-ttu-id="d0401-107">为数值类型和字符串类型预定义了二元 `+` 运算符。</span><span class="sxs-lookup"><span data-stu-id="d0401-107">Binary `+` operators are predefined for numeric and string types.</span></span> <span data-ttu-id="d0401-108">对于数值类型，+ 计算两个操作数之和。</span><span class="sxs-lookup"><span data-stu-id="d0401-108">For numeric types, + computes the sum of its two operands.</span></span> <span data-ttu-id="d0401-109">当其中的一个操作数是字符串类型或两个操作数都是字符串类型时，+ 将操作数的字符串表示形式串联在一起。</span><span class="sxs-lookup"><span data-stu-id="d0401-109">When one or both operands are of type string, + concatenates the string representations of the operands.</span></span>  
  
 <span data-ttu-id="d0401-110">委托类型也提供二元 `+` 运算符，该运算符执行委托串联。</span><span class="sxs-lookup"><span data-stu-id="d0401-110">Delegate types also provide a binary `+` operator, which performs delegate concatenation.</span></span>  
  
 <span data-ttu-id="d0401-111">用户定义的类型可重载一元 `+` 运算符和二元 `+` 运算符。</span><span class="sxs-lookup"><span data-stu-id="d0401-111">User-defined types can overload the unary `+` and binary `+` operators.</span></span> <span data-ttu-id="d0401-112">对整数类型的操作通常可用于枚举。</span><span class="sxs-lookup"><span data-stu-id="d0401-112">Operations on integral types are generally allowed on enumeration.</span></span> <span data-ttu-id="d0401-113">有关详细信息，请参阅[运算符（C# 参考）](../../../csharp/language-reference/keywords/operator.md)。</span><span class="sxs-lookup"><span data-stu-id="d0401-113">For more information, see [operator (C# Reference)](../../../csharp/language-reference/keywords/operator.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="d0401-114">示例</span><span class="sxs-lookup"><span data-stu-id="d0401-114">Example</span></span>  
 [!code-csharp[csRefOperators#28](../../../csharp/language-reference/operators/codesnippet/CSharp/addition-operator_1.cs)]  
  
## <a name="c-language-specification"></a><span data-ttu-id="d0401-115">C# 语言规范</span><span class="sxs-lookup"><span data-stu-id="d0401-115">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="d0401-116">请参阅</span><span class="sxs-lookup"><span data-stu-id="d0401-116">See Also</span></span>

- [<span data-ttu-id="d0401-117">C# 参考</span><span class="sxs-lookup"><span data-stu-id="d0401-117">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
- [<span data-ttu-id="d0401-118">C# 编程指南</span><span class="sxs-lookup"><span data-stu-id="d0401-118">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
- [<span data-ttu-id="d0401-119">C# 运算符</span><span class="sxs-lookup"><span data-stu-id="d0401-119">C# Operators</span></span>](../../../csharp/language-reference/operators/index.md)  
- [<span data-ttu-id="d0401-120">运算符（C# 参考）</span><span class="sxs-lookup"><span data-stu-id="d0401-120">operator (C# Reference)</span></span>](../../../csharp/language-reference/keywords/operator.md)
