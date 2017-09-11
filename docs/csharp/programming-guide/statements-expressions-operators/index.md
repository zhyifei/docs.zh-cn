---
title: "语句、表达式和运算符（C# 编程指南）"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- expressions [C#]
- operators [C#]
- C# language, statements
- C# language, operators
- C# language, expressions
- statements [C#]
ms.assetid: 20f8469d-5a6a-4084-ad90-0856b7e97e45
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
ms.openlocfilehash: 71988a5b9aa59b2655b4fd7b91522fe69c8064b6
ms.contentlocale: zh-cn
ms.lasthandoff: 07/28/2017

---
# <a name="statements-expressions-and-operators-c-programming-guide"></a><span data-ttu-id="fb3b5-102">语句、表达式和运算符（C# 编程指南）</span><span class="sxs-lookup"><span data-stu-id="fb3b5-102">Statements, Expressions, and Operators (C# Programming Guide)</span></span>
<span data-ttu-id="fb3b5-103">构成应用程序的 C# 代码由关键字、表达式和运算符组成的语句所组成。</span><span class="sxs-lookup"><span data-stu-id="fb3b5-103">The C# code that comprises an application consists of statements made up of keywords, expressions and operators.</span></span> <span data-ttu-id="fb3b5-104">本节包含有关这些 C# 程序基本元素的信息。</span><span class="sxs-lookup"><span data-stu-id="fb3b5-104">This section contains information regarding these fundamental elements of a C# program.</span></span>  
  
 <span data-ttu-id="fb3b5-105">有关详细信息，请参见:</span><span class="sxs-lookup"><span data-stu-id="fb3b5-105">For more information, see:</span></span>  
  
-   [<span data-ttu-id="fb3b5-106">语句</span><span class="sxs-lookup"><span data-stu-id="fb3b5-106">Statements</span></span>](../../../csharp/programming-guide/statements-expressions-operators/statements.md)  
  
-   [<span data-ttu-id="fb3b5-107">表达式</span><span class="sxs-lookup"><span data-stu-id="fb3b5-107">Expressions</span></span>](../../../csharp/programming-guide/statements-expressions-operators/expressions.md)  
  
    -   [<span data-ttu-id="fb3b5-108">Expression-Bodied 成员</span><span class="sxs-lookup"><span data-stu-id="fb3b5-108">Expression-bodied members</span></span>](expression-bodied-members.md)
 
-   [<span data-ttu-id="fb3b5-109">运算符</span><span class="sxs-lookup"><span data-stu-id="fb3b5-109">Operators</span></span>](../../../csharp/programming-guide/statements-expressions-operators/operators.md)  
  
-   [<span data-ttu-id="fb3b5-110">匿名函数</span><span class="sxs-lookup"><span data-stu-id="fb3b5-110">Anonymous Functions</span></span>](../../../csharp/programming-guide/statements-expressions-operators/anonymous-functions.md)  
  
-   [<span data-ttu-id="fb3b5-111">可重载运算符</span><span class="sxs-lookup"><span data-stu-id="fb3b5-111">Overloadable Operators</span></span>](../../../csharp/programming-guide/statements-expressions-operators/overloadable-operators.md)  
  
-   [<span data-ttu-id="fb3b5-112">转换运算符</span><span class="sxs-lookup"><span data-stu-id="fb3b5-112">Conversion Operators</span></span>](../../../csharp/programming-guide/statements-expressions-operators/conversion-operators.md)  
  
    -   [<span data-ttu-id="fb3b5-113">使用转换运算符</span><span class="sxs-lookup"><span data-stu-id="fb3b5-113">Using Conversion Operators</span></span>](../../../csharp/programming-guide/statements-expressions-operators/using-conversion-operators.md)  
  
    -   [<span data-ttu-id="fb3b5-114">如何：在结构之间实现用户定义的转换</span><span class="sxs-lookup"><span data-stu-id="fb3b5-114">How to: Implement User-Defined Conversions Between Structs</span></span>](../../../csharp/programming-guide/statements-expressions-operators/how-to-implement-user-defined-conversions-between-structs.md)  
  
-   [<span data-ttu-id="fb3b5-115">如何：使用运算符重载创建复数类</span><span class="sxs-lookup"><span data-stu-id="fb3b5-115">How to: Use Operator Overloading to Create a Complex Number Class</span></span>](../../../csharp/programming-guide/statements-expressions-operators/how-to-use-operator-overloading-to-create-a-complex-number-class.md)  
  
-   [<span data-ttu-id="fb3b5-116">相等比较</span><span class="sxs-lookup"><span data-stu-id="fb3b5-116">Equality Comparisons</span></span>](../../../csharp/programming-guide/statements-expressions-operators/equality-comparisons.md)  
  
## <a name="c-language-specification"></a><span data-ttu-id="fb3b5-117">C# 语言规范</span><span class="sxs-lookup"><span data-stu-id="fb3b5-117">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="fb3b5-118">请参阅</span><span class="sxs-lookup"><span data-stu-id="fb3b5-118">See Also</span></span>  
 <span data-ttu-id="fb3b5-119">[C# 编程指南](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="fb3b5-119">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 [<span data-ttu-id="fb3b5-120">强制转换和类型转换</span><span class="sxs-lookup"><span data-stu-id="fb3b5-120">Casting and Type Conversions</span></span>](../../../csharp/programming-guide/types/casting-and-type-conversions.md)

