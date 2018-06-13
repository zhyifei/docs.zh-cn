---
title: implicit（C# 参考）
ms.date: 07/20/2015
f1_keywords:
- implicit
- implicit_CSharpKeyword
helpviewer_keywords:
- implicit keyword [C#]
ms.assetid: 34db590e-eb3a-4f11-88d0-ffb3cd753dab
ms.openlocfilehash: 160d9f7c0d58abd685bf1d799b53cc96a26aebe8
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33215012"
---
# <a name="implicit-c-reference"></a><span data-ttu-id="1712f-102">implicit（C# 参考）</span><span class="sxs-lookup"><span data-stu-id="1712f-102">implicit (C# Reference)</span></span>
<span data-ttu-id="1712f-103">`implicit` 关键字用于声明隐式的用户定义类型转换运算符。</span><span class="sxs-lookup"><span data-stu-id="1712f-103">The `implicit` keyword is used to declare an implicit user-defined type conversion operator.</span></span> <span data-ttu-id="1712f-104">如果可以确保转换过程不会造成数据丢失，则可使用该关键字在用户定义类型和其他类型之间进行隐式转换。</span><span class="sxs-lookup"><span data-stu-id="1712f-104">Use it to enable implicit conversions between a user-defined type and another type, if the conversion is guaranteed not to cause a loss of data.</span></span>  
  
## <a name="example"></a><span data-ttu-id="1712f-105">示例</span><span class="sxs-lookup"><span data-stu-id="1712f-105">Example</span></span>  
 [!code-csharp[csrefKeywordsConversion#5](../../../csharp/language-reference/keywords/codesnippet/CSharp/implicit_1.cs)]  
  
 <span data-ttu-id="1712f-106">隐式转换可以通过消除不必要的强制转换来提高源代码的可读性。</span><span class="sxs-lookup"><span data-stu-id="1712f-106">By eliminating unnecessary casts, implicit conversions can improve source code readability.</span></span> <span data-ttu-id="1712f-107">但是，因为隐式转换不需要程序员将一种类型显式强制转换为另一种类型，所以使用隐式转换时必须格外小心，以免出现意外结果。</span><span class="sxs-lookup"><span data-stu-id="1712f-107">However, because implicit conversions do not require programmers to explicitly cast from one type to the other, care must be taken to prevent unexpected results.</span></span> <span data-ttu-id="1712f-108">一般情况下，隐式转换运算符应当从不引发异常并且从不丢失信息，以便可以在程序员不知晓的情况下安全使用它们。</span><span class="sxs-lookup"><span data-stu-id="1712f-108">In general, implicit conversion operators should never throw exceptions and never lose information so that they can be used safely without the programmer's awareness.</span></span> <span data-ttu-id="1712f-109">如果转换运算符不能满足那些条件，则应将其标记为 `explicit`。</span><span class="sxs-lookup"><span data-stu-id="1712f-109">If a conversion operator cannot meet those criteria, it should be marked `explicit`.</span></span> <span data-ttu-id="1712f-110">有关详细信息，请参阅[使用转换运算符](../../../csharp/programming-guide/statements-expressions-operators/using-conversion-operators.md)。</span><span class="sxs-lookup"><span data-stu-id="1712f-110">For more information, see [Using Conversion Operators](../../../csharp/programming-guide/statements-expressions-operators/using-conversion-operators.md).</span></span>  
  
## <a name="c-language-specification"></a><span data-ttu-id="1712f-111">C# 语言规范</span><span class="sxs-lookup"><span data-stu-id="1712f-111">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="1712f-112">请参阅</span><span class="sxs-lookup"><span data-stu-id="1712f-112">See Also</span></span>  
 [<span data-ttu-id="1712f-113">C# 参考</span><span class="sxs-lookup"><span data-stu-id="1712f-113">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
 [<span data-ttu-id="1712f-114">C# 编程指南</span><span class="sxs-lookup"><span data-stu-id="1712f-114">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="1712f-115">C# 关键字</span><span class="sxs-lookup"><span data-stu-id="1712f-115">C# Keywords</span></span>](../../../csharp/language-reference/keywords/index.md)  
 [<span data-ttu-id="1712f-116">explicit</span><span class="sxs-lookup"><span data-stu-id="1712f-116">explicit</span></span>](../../../csharp/language-reference/keywords/explicit.md)  
 [<span data-ttu-id="1712f-117">运算符（C# 参考）</span><span class="sxs-lookup"><span data-stu-id="1712f-117">operator (C# Reference)</span></span>](../../../csharp/language-reference/keywords/operator.md)  
 [<span data-ttu-id="1712f-118">如何：在结构之间实现用户定义的转换</span><span class="sxs-lookup"><span data-stu-id="1712f-118">How to: Implement User-Defined Conversions Between Structs</span></span>](../../../csharp/programming-guide/statements-expressions-operators/how-to-implement-user-defined-conversions-between-structs.md)
