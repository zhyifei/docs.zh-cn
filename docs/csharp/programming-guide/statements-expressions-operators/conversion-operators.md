---
title: "转换运算符（C# 编程指南）"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- C# language, conversion operators
- conversion operators [C#]
- operators [C#], conversion
- user-defined conversions [C#]
ms.assetid: c5ad73a3-d57b-4d2b-b4c9-24e3c2856efc
caps.latest.revision: 22
author: BillWagner
ms.author: wiwagn
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: c12fd13d6526d79363f973ce2a944c4823bf4104
ms.contentlocale: zh-cn
ms.lasthandoff: 07/28/2017

---
# <a name="conversion-operators-c-programming-guide"></a><span data-ttu-id="868e9-102">转换运算符（C# 编程指南）</span><span class="sxs-lookup"><span data-stu-id="868e9-102">Conversion Operators (C# Programming Guide)</span></span>
<span data-ttu-id="868e9-103">C# 允许程序员在类或结构上声明转换，以便类或结构能够与其他类或结构或者基本类型进行相互转换。</span><span class="sxs-lookup"><span data-stu-id="868e9-103">C# enables programmers to declare conversions on classes or structs so that classes or structs can be converted to and/or from other classes or structs, or basic types.</span></span> <span data-ttu-id="868e9-104">以类似于运算符的方式定义转换，并根据它们所转换为的类型命名。</span><span class="sxs-lookup"><span data-stu-id="868e9-104">Conversions are defined like operators and are named for the type to which they convert.</span></span> <span data-ttu-id="868e9-105">要转换的参数类型或转换结果的类型必须是包含类型（但不能两者同时都是）。</span><span class="sxs-lookup"><span data-stu-id="868e9-105">Either the type of the argument to be converted, or the type of the result of the conversion, but not both, must be the containing type.</span></span>  
  
 <span data-ttu-id="868e9-106">[!code-cs[csProgGuideStatements#10](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/conversion-operators_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="868e9-106">[!code-cs[csProgGuideStatements#10](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/conversion-operators_1.cs)]</span></span>  
  
## <a name="conversion-operators-overview"></a><span data-ttu-id="868e9-107">转换运算符概述</span><span class="sxs-lookup"><span data-stu-id="868e9-107">Conversion Operators Overview</span></span>  
 <span data-ttu-id="868e9-108">转换运算符具有以下属性：</span><span class="sxs-lookup"><span data-stu-id="868e9-108">Conversion operators have the following properties:</span></span>  
  
-   <span data-ttu-id="868e9-109">声明为 `implicit` 的转换在需要时自动执行。</span><span class="sxs-lookup"><span data-stu-id="868e9-109">Conversions declared as `implicit` occur automatically when it is required.</span></span>  
  
-   <span data-ttu-id="868e9-110">声明为 `explicit` 的转换需要调用强制转换。</span><span class="sxs-lookup"><span data-stu-id="868e9-110">Conversions declared as `explicit` require a cast to be called.</span></span>  
  
-   <span data-ttu-id="868e9-111">所有转换都必须都声明为 `static`。</span><span class="sxs-lookup"><span data-stu-id="868e9-111">All conversions must be declared as `static`.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="868e9-112">相关章节</span><span class="sxs-lookup"><span data-stu-id="868e9-112">Related Sections</span></span>  
 <span data-ttu-id="868e9-113">更多相关信息：</span><span class="sxs-lookup"><span data-stu-id="868e9-113">For more information:</span></span>  
  
-   [<span data-ttu-id="868e9-114">使用转换运算符</span><span class="sxs-lookup"><span data-stu-id="868e9-114">Using Conversion Operators</span></span>](../../../csharp/programming-guide/statements-expressions-operators/using-conversion-operators.md)  
  
-   [<span data-ttu-id="868e9-115">强制转换和类型转换</span><span class="sxs-lookup"><span data-stu-id="868e9-115">Casting and Type Conversions</span></span>](../../../csharp/programming-guide/types/casting-and-type-conversions.md)  
  
-   [<span data-ttu-id="868e9-116">如何：在结构之间实现用户定义的转换</span><span class="sxs-lookup"><span data-stu-id="868e9-116">How to: Implement User-Defined Conversions Between Structs</span></span>](../../../csharp/programming-guide/statements-expressions-operators/how-to-implement-user-defined-conversions-between-structs.md)  
  
-   [<span data-ttu-id="868e9-117">explicit</span><span class="sxs-lookup"><span data-stu-id="868e9-117">explicit</span></span>](../../../csharp/language-reference/keywords/explicit.md)  
  
-   [<span data-ttu-id="868e9-118">implicit</span><span class="sxs-lookup"><span data-stu-id="868e9-118">implicit</span></span>](../../../csharp/language-reference/keywords/implicit.md)  
  
-   [<span data-ttu-id="868e9-119">static</span><span class="sxs-lookup"><span data-stu-id="868e9-119">static</span></span>](../../../csharp/language-reference/keywords/static.md)  
  
## <a name="see-also"></a><span data-ttu-id="868e9-120">另请参阅</span><span class="sxs-lookup"><span data-stu-id="868e9-120">See Also</span></span>  
 <span data-ttu-id="868e9-121"><xref:System.Convert></span><span class="sxs-lookup"><span data-stu-id="868e9-121"><xref:System.Convert></span></span>   
 <span data-ttu-id="868e9-122">[C# 编程指南](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="868e9-122">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 <span data-ttu-id="868e9-123">[Chained user-defined explicit conversions in C#](http://go.microsoft.com/fwlink/?LinkId=112384)（C# 中链接在一起的用户定义的显式转换）</span><span class="sxs-lookup"><span data-stu-id="868e9-123">[Chained user-defined explicit conversions in C#](http://go.microsoft.com/fwlink/?LinkId=112384)</span></span>

