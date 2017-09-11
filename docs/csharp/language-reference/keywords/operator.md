---
title: "运算符（C# 参考）"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- operator_CSharpKeyword
- operator
dev_langs:
- CSharp
helpviewer_keywords:
- operator keyword [C#]
ms.assetid: 59218cce-e90e-42f6-a6bb-30300981b86a
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
ms.openlocfilehash: 76d403493861e9c587672412cd2989c419b8717a
ms.contentlocale: zh-cn
ms.lasthandoff: 07/28/2017

---
# <a name="operator-c-reference"></a><span data-ttu-id="a815b-102">运算符（C# 参考）</span><span class="sxs-lookup"><span data-stu-id="a815b-102">operator (C# Reference)</span></span>
<span data-ttu-id="a815b-103">使用 `operator` 关键字重载内置运算符，或在类或结构声明中提供用户定义的转换。</span><span class="sxs-lookup"><span data-stu-id="a815b-103">Use the `operator` keyword to overload a built-in operator or to provide a user-defined conversion in a class or struct declaration.</span></span>  
  
## <a name="example"></a><span data-ttu-id="a815b-104">示例</span><span class="sxs-lookup"><span data-stu-id="a815b-104">Example</span></span>  
 <span data-ttu-id="a815b-105">下面是针对分数的一个非常简单的类。</span><span class="sxs-lookup"><span data-stu-id="a815b-105">The following is a very simplified class for fractional numbers.</span></span> <span data-ttu-id="a815b-106">此类重载 + 和 * 运算符以执行分数加法和乘法，并提供转换运算符将分数类型转换为双精度类型。</span><span class="sxs-lookup"><span data-stu-id="a815b-106">It overloads the + and * operators to perform fractional addition and multiplication, and also provides a conversion operator that converts a Fraction type to a double type.</span></span>  
  
 <span data-ttu-id="a815b-107">[!code-cs[csrefKeywordsConversion#6](../../../csharp/language-reference/keywords/codesnippet/CSharp/operator_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="a815b-107">[!code-cs[csrefKeywordsConversion#6](../../../csharp/language-reference/keywords/codesnippet/CSharp/operator_1.cs)]</span></span>  
  
## <a name="c-language-specification"></a><span data-ttu-id="a815b-108">C# 语言规范</span><span class="sxs-lookup"><span data-stu-id="a815b-108">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="a815b-109">请参阅</span><span class="sxs-lookup"><span data-stu-id="a815b-109">See Also</span></span>  
 <span data-ttu-id="a815b-110">[C# 参考](../../../csharp/language-reference/index.md) </span><span class="sxs-lookup"><span data-stu-id="a815b-110">[C# Reference](../../../csharp/language-reference/index.md) </span></span>  
 <span data-ttu-id="a815b-111">[C# 编程指南](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="a815b-111">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 <span data-ttu-id="a815b-112">[C# 关键字](../../../csharp/language-reference/keywords/index.md) </span><span class="sxs-lookup"><span data-stu-id="a815b-112">[C# Keywords](../../../csharp/language-reference/keywords/index.md) </span></span>  
 <span data-ttu-id="a815b-113">[implicit](../../../csharp/language-reference/keywords/implicit.md) </span><span class="sxs-lookup"><span data-stu-id="a815b-113">[implicit](../../../csharp/language-reference/keywords/implicit.md) </span></span>  
 <span data-ttu-id="a815b-114">[explicit](../../../csharp/language-reference/keywords/explicit.md) </span><span class="sxs-lookup"><span data-stu-id="a815b-114">[explicit](../../../csharp/language-reference/keywords/explicit.md) </span></span>  
 [<span data-ttu-id="a815b-115">如何：在结构之间实现用户定义的转换</span><span class="sxs-lookup"><span data-stu-id="a815b-115">How to: Implement User-Defined Conversions Between Structs</span></span>](../../../csharp/programming-guide/statements-expressions-operators/how-to-implement-user-defined-conversions-between-structs.md)

