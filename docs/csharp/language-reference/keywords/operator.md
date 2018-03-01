---
title: "运算符（C# 参考）"
ms.date: 07/20/2015
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- operator_CSharpKeyword
- operator
helpviewer_keywords:
- operator keyword [C#]
ms.assetid: 59218cce-e90e-42f6-a6bb-30300981b86a
caps.latest.revision: 
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 1d035319318a710ccee62a0c64ce5981767a21ca
ms.sourcegitcommit: 8bde7a3432f30fc771079744955c75c58c4eb393
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/20/2018
---
# <a name="operator-c-reference"></a><span data-ttu-id="f8264-102">运算符（C# 参考）</span><span class="sxs-lookup"><span data-stu-id="f8264-102">operator (C# Reference)</span></span>
<span data-ttu-id="f8264-103">使用 `operator` 关键字重载内置运算符，或在类或结构声明中提供用户定义的转换。</span><span class="sxs-lookup"><span data-stu-id="f8264-103">Use the `operator` keyword to overload a built-in operator or to provide a user-defined conversion in a class or struct declaration.</span></span>  
  
## <a name="example"></a><span data-ttu-id="f8264-104">示例</span><span class="sxs-lookup"><span data-stu-id="f8264-104">Example</span></span>  
 <span data-ttu-id="f8264-105">下面是针对分数的一个非常简单的类。</span><span class="sxs-lookup"><span data-stu-id="f8264-105">The following is a very simplified class for fractional numbers.</span></span> <span data-ttu-id="f8264-106">此类重载 `+` 和 `*` 运算符以执行分数加法和乘法，并提供转换运算符将 `Fraction` 类型转换为 `double` 类型。</span><span class="sxs-lookup"><span data-stu-id="f8264-106">It overloads the `+` and `*` operators to perform fractional addition and multiplication, and also provides a conversion operator that converts a `Fraction` type to a `double` type.</span></span>  
  
 [!code-csharp[csrefKeywordsConversion#6](../../../csharp/language-reference/keywords/codesnippet/CSharp/operator_1.cs)]  
  
## <a name="c-language-specification"></a><span data-ttu-id="f8264-107">C# 语言规范</span><span class="sxs-lookup"><span data-stu-id="f8264-107">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="f8264-108">请参阅</span><span class="sxs-lookup"><span data-stu-id="f8264-108">See Also</span></span>  
 [<span data-ttu-id="f8264-109">C# 参考</span><span class="sxs-lookup"><span data-stu-id="f8264-109">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
 [<span data-ttu-id="f8264-110">C# 编程指南</span><span class="sxs-lookup"><span data-stu-id="f8264-110">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="f8264-111">C# 关键字</span><span class="sxs-lookup"><span data-stu-id="f8264-111">C# Keywords</span></span>](../../../csharp/language-reference/keywords/index.md)  
 [<span data-ttu-id="f8264-112">implicit</span><span class="sxs-lookup"><span data-stu-id="f8264-112">implicit</span></span>](../../../csharp/language-reference/keywords/implicit.md)  
 [<span data-ttu-id="f8264-113">explicit</span><span class="sxs-lookup"><span data-stu-id="f8264-113">explicit</span></span>](../../../csharp/language-reference/keywords/explicit.md)  
 [<span data-ttu-id="f8264-114">如何：在结构之间实现用户定义的转换</span><span class="sxs-lookup"><span data-stu-id="f8264-114">How to: Implement User-Defined Conversions Between Structs</span></span>](../../../csharp/programming-guide/statements-expressions-operators/how-to-implement-user-defined-conversions-between-structs.md)
