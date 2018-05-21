---
title: 转换运算符（C# 编程指南）
ms.date: 07/20/2015
helpviewer_keywords:
- C# language, conversion operators
- conversion operators [C#]
- operators [C#], conversion
- user-defined conversions [C#]
ms.assetid: c5ad73a3-d57b-4d2b-b4c9-24e3c2856efc
ms.openlocfilehash: 97e93230658b5d1da676b029169b63bc9006ddb1
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
---
# <a name="conversion-operators-c-programming-guide"></a><span data-ttu-id="1ff13-102">转换运算符（C# 编程指南）</span><span class="sxs-lookup"><span data-stu-id="1ff13-102">Conversion Operators (C# Programming Guide)</span></span>
<span data-ttu-id="1ff13-103">C# 允许程序员在类或结构上声明转换，以便类或结构能够与其他类或结构或者基本类型进行相互转换。</span><span class="sxs-lookup"><span data-stu-id="1ff13-103">C# enables programmers to declare conversions on classes or structs so that classes or structs can be converted to and/or from other classes or structs, or basic types.</span></span> <span data-ttu-id="1ff13-104">以类似于运算符的方式定义转换，并根据它们所转换为的类型命名。</span><span class="sxs-lookup"><span data-stu-id="1ff13-104">Conversions are defined like operators and are named for the type to which they convert.</span></span> <span data-ttu-id="1ff13-105">要转换的参数类型或转换结果的类型必须是包含类型（但不能两者同时都是）。</span><span class="sxs-lookup"><span data-stu-id="1ff13-105">Either the type of the argument to be converted, or the type of the result of the conversion, but not both, must be the containing type.</span></span>  
  
 [!code-csharp[csProgGuideStatements#10](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/conversion-operators_1.cs)]  
  
## <a name="conversion-operators-overview"></a><span data-ttu-id="1ff13-106">转换运算符概述</span><span class="sxs-lookup"><span data-stu-id="1ff13-106">Conversion Operators Overview</span></span>  
 <span data-ttu-id="1ff13-107">转换运算符具有以下属性：</span><span class="sxs-lookup"><span data-stu-id="1ff13-107">Conversion operators have the following properties:</span></span>  
  
-   <span data-ttu-id="1ff13-108">声明为 `implicit` 的转换在需要时自动执行。</span><span class="sxs-lookup"><span data-stu-id="1ff13-108">Conversions declared as `implicit` occur automatically when it is required.</span></span>  
  
-   <span data-ttu-id="1ff13-109">声明为 `explicit` 的转换需要调用强制转换。</span><span class="sxs-lookup"><span data-stu-id="1ff13-109">Conversions declared as `explicit` require a cast to be called.</span></span>  
  
-   <span data-ttu-id="1ff13-110">所有转换都必须都声明为 `static`。</span><span class="sxs-lookup"><span data-stu-id="1ff13-110">All conversions must be declared as `static`.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="1ff13-111">相关章节</span><span class="sxs-lookup"><span data-stu-id="1ff13-111">Related Sections</span></span>  
 <span data-ttu-id="1ff13-112">更多相关信息：</span><span class="sxs-lookup"><span data-stu-id="1ff13-112">For more information:</span></span>  
  
-   [<span data-ttu-id="1ff13-113">使用转换运算符</span><span class="sxs-lookup"><span data-stu-id="1ff13-113">Using Conversion Operators</span></span>](../../../csharp/programming-guide/statements-expressions-operators/using-conversion-operators.md)  
  
-   [<span data-ttu-id="1ff13-114">强制转换和类型转换</span><span class="sxs-lookup"><span data-stu-id="1ff13-114">Casting and Type Conversions</span></span>](../../../csharp/programming-guide/types/casting-and-type-conversions.md)  
  
-   [<span data-ttu-id="1ff13-115">如何：在结构之间实现用户定义的转换</span><span class="sxs-lookup"><span data-stu-id="1ff13-115">How to: Implement User-Defined Conversions Between Structs</span></span>](../../../csharp/programming-guide/statements-expressions-operators/how-to-implement-user-defined-conversions-between-structs.md)  
  
-   [<span data-ttu-id="1ff13-116">explicit</span><span class="sxs-lookup"><span data-stu-id="1ff13-116">explicit</span></span>](../../../csharp/language-reference/keywords/explicit.md)  
  
-   [<span data-ttu-id="1ff13-117">implicit</span><span class="sxs-lookup"><span data-stu-id="1ff13-117">implicit</span></span>](../../../csharp/language-reference/keywords/implicit.md)  
  
-   [<span data-ttu-id="1ff13-118">static</span><span class="sxs-lookup"><span data-stu-id="1ff13-118">static</span></span>](../../../csharp/language-reference/keywords/static.md)  
  
## <a name="see-also"></a><span data-ttu-id="1ff13-119">请参阅</span><span class="sxs-lookup"><span data-stu-id="1ff13-119">See Also</span></span>  
 <xref:System.Convert>  
 [<span data-ttu-id="1ff13-120">C# 编程指南</span><span class="sxs-lookup"><span data-stu-id="1ff13-120">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 <span data-ttu-id="1ff13-121">[Chained user-defined explicit conversions in C#](https://blogs.msdn.microsoft.com/ericlippert/2007/04/16/chained-user-defined-explicit-conversions-in-c/)（C# 中链接在一起的用户定义的显式转换）</span><span class="sxs-lookup"><span data-stu-id="1ff13-121">[Chained user-defined explicit conversions in C#](https://blogs.msdn.microsoft.com/ericlippert/2007/04/16/chained-user-defined-explicit-conversions-in-c/)</span></span>
