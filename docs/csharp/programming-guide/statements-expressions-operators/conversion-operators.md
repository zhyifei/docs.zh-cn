---
title: 转换运算符 - C# 编程指南
ms.custom: seodec18
ms.date: 07/20/2015
helpviewer_keywords:
- C# language, conversion operators
- conversion operators [C#]
- operators [C#], conversion
- user-defined conversions [C#]
ms.assetid: c5ad73a3-d57b-4d2b-b4c9-24e3c2856efc
ms.openlocfilehash: 539a554da2ea2f785a54bd7e5ff81d09b908c9e4
ms.sourcegitcommit: 40364ded04fa6cdcb2b6beca7f68412e2e12f633
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/28/2019
ms.locfileid: "56965210"
---
# <a name="conversion-operators-c-programming-guide"></a><span data-ttu-id="11e27-102">转换运算符（C# 编程指南）</span><span class="sxs-lookup"><span data-stu-id="11e27-102">Conversion operators (C# Programming Guide)</span></span>

<span data-ttu-id="11e27-103">C# 允许程序员在类或结构上声明转换，以便类或结构能够与其他类或结构或者基本类型进行相互转换。</span><span class="sxs-lookup"><span data-stu-id="11e27-103">C# enables programmers to declare conversions on classes or structs so that classes or structs can be converted to and/or from other classes or structs, or basic types.</span></span> <span data-ttu-id="11e27-104">以类似于运算符的方式定义转换，并根据它们所转换为的类型命名。</span><span class="sxs-lookup"><span data-stu-id="11e27-104">Conversions are defined like operators and are named for the type to which they convert.</span></span> <span data-ttu-id="11e27-105">要转换的参数类型或转换结果的类型必须是包含类型（但不能两者同时都是）。</span><span class="sxs-lookup"><span data-stu-id="11e27-105">Either the type of the argument to be converted, or the type of the result of the conversion, but not both, must be the containing type.</span></span>  
  
 [!code-csharp[csProgGuideStatements#10](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideStatements/CS/Statements.cs#10)]  
  
## <a name="conversion-operators-overview"></a><span data-ttu-id="11e27-106">转换运算符概述</span><span class="sxs-lookup"><span data-stu-id="11e27-106">Conversion operators overview</span></span>

 <span data-ttu-id="11e27-107">转换运算符具有以下属性：</span><span class="sxs-lookup"><span data-stu-id="11e27-107">Conversion operators have the following properties:</span></span>  
  
-   <span data-ttu-id="11e27-108">声明为 `implicit` 的转换在需要时自动执行。</span><span class="sxs-lookup"><span data-stu-id="11e27-108">Conversions declared as `implicit` occur automatically when it is required.</span></span>  
  
-   <span data-ttu-id="11e27-109">声明为 `explicit` 的转换需要调用强制转换。</span><span class="sxs-lookup"><span data-stu-id="11e27-109">Conversions declared as `explicit` require a cast to be called.</span></span>  
  
-   <span data-ttu-id="11e27-110">所有转换都必须都声明为 `static`。</span><span class="sxs-lookup"><span data-stu-id="11e27-110">All conversions must be declared as `static`.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="11e27-111">相关章节</span><span class="sxs-lookup"><span data-stu-id="11e27-111">Related sections</span></span>

 <span data-ttu-id="11e27-112">更多相关信息：</span><span class="sxs-lookup"><span data-stu-id="11e27-112">For more information:</span></span>  
  
-   [<span data-ttu-id="11e27-113">使用转换运算符</span><span class="sxs-lookup"><span data-stu-id="11e27-113">Using Conversion Operators</span></span>](../../../csharp/programming-guide/statements-expressions-operators/using-conversion-operators.md)  
  
-   [<span data-ttu-id="11e27-114">强制转换和类型转换</span><span class="sxs-lookup"><span data-stu-id="11e27-114">Casting and Type Conversions</span></span>](../../../csharp/programming-guide/types/casting-and-type-conversions.md)  
  
-   [<span data-ttu-id="11e27-115">如何：在结构之间实现用户定义的转换</span><span class="sxs-lookup"><span data-stu-id="11e27-115">How to: Implement User-Defined Conversions Between Structs</span></span>](../../../csharp/programming-guide/statements-expressions-operators/how-to-implement-user-defined-conversions-between-structs.md)  
  
-   [<span data-ttu-id="11e27-116">explicit</span><span class="sxs-lookup"><span data-stu-id="11e27-116">explicit</span></span>](../../../csharp/language-reference/keywords/explicit.md)  
  
-   [<span data-ttu-id="11e27-117">implicit</span><span class="sxs-lookup"><span data-stu-id="11e27-117">implicit</span></span>](../../../csharp/language-reference/keywords/implicit.md)  
  
-   [<span data-ttu-id="11e27-118">static</span><span class="sxs-lookup"><span data-stu-id="11e27-118">static</span></span>](../../../csharp/language-reference/keywords/static.md)  
  
## <a name="see-also"></a><span data-ttu-id="11e27-119">请参阅</span><span class="sxs-lookup"><span data-stu-id="11e27-119">See also</span></span>

- <xref:System.Convert>
- [<span data-ttu-id="11e27-120">C# 编程指南</span><span class="sxs-lookup"><span data-stu-id="11e27-120">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)
- <span data-ttu-id="11e27-121">[Chained user-defined explicit conversions in C#](https://blogs.msdn.microsoft.com/ericlippert/2007/04/16/chained-user-defined-explicit-conversions-in-c/)（C# 中链接在一起的用户定义的显式转换）</span><span class="sxs-lookup"><span data-stu-id="11e27-121">[Chained user-defined explicit conversions in C#](https://blogs.msdn.microsoft.com/ericlippert/2007/04/16/chained-user-defined-explicit-conversions-in-c/)</span></span>
