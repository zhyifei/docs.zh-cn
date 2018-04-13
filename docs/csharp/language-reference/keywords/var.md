---
title: var（C# 参考）
ms.date: 07/20/2015
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- var
- var_CSharpKeyword
helpviewer_keywords:
- var keyword [C#]
ms.assetid: 0777850a-2691-4e3e-927f-0c850f5efe15
caps.latest.revision: 13
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: d2be56243f9c4ddafb3903d14fa6d6f9cb0e2f84
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="var-c-reference"></a><span data-ttu-id="561a6-102">var（C# 参考）</span><span class="sxs-lookup"><span data-stu-id="561a6-102">var (C# Reference)</span></span>
<span data-ttu-id="561a6-103">从 Visual C# 3.0 开始，在方法范围内声明的变量可以具有隐式“类型”`var`。</span><span class="sxs-lookup"><span data-stu-id="561a6-103">Beginning in Visual C# 3.0, variables that are declared at method scope can have an implicit "type" `var`.</span></span> <span data-ttu-id="561a6-104">隐式类型本地变量为强类型，就像用户已经自行声明该类型，但编译器决定类型一样。</span><span class="sxs-lookup"><span data-stu-id="561a6-104">An implicitly typed local variable is strongly typed just as if you had declared the type yourself, but the compiler determines the type.</span></span> <span data-ttu-id="561a6-105">`i` 的以下两个声明在功能上是等效的：</span><span class="sxs-lookup"><span data-stu-id="561a6-105">The following two declarations of `i` are functionally equivalent:</span></span>  
  
```  
var i = 10; // implicitly typed  
int i = 10; //explicitly typed  
```  
  
 <span data-ttu-id="561a6-106">有关详细信息，请参阅[隐式类型的局部变量](../../../csharp/programming-guide/classes-and-structs/implicitly-typed-local-variables.md)和 [LINQ 查询操作中的类型关系](../../../csharp/programming-guide/concepts/linq/type-relationships-in-linq-query-operations.md)。</span><span class="sxs-lookup"><span data-stu-id="561a6-106">For more information, see [Implicitly Typed Local Variables](../../../csharp/programming-guide/classes-and-structs/implicitly-typed-local-variables.md) and [Type Relationships in LINQ Query Operations](../../../csharp/programming-guide/concepts/linq/type-relationships-in-linq-query-operations.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="561a6-107">示例</span><span class="sxs-lookup"><span data-stu-id="561a6-107">Example</span></span>  
 <span data-ttu-id="561a6-108">下面的示例演示两个查询表达式。</span><span class="sxs-lookup"><span data-stu-id="561a6-108">The following example shows two query expressions.</span></span> <span data-ttu-id="561a6-109">在第一个表达式中，`var` 的使用是允许的，但不是必需的，因为查询结果的类型可以明确表述为 `IEnumerable<string>`。</span><span class="sxs-lookup"><span data-stu-id="561a6-109">In the first expression, the use of `var` is permitted but is not required, because the type of the query result can be stated explicitly as an `IEnumerable<string>`.</span></span> <span data-ttu-id="561a6-110">但是，在第二个表达式中，必须使用 `var`，因为结果是匿名类型的集合，并且该类型的名称只有编译器本身才可访问。</span><span class="sxs-lookup"><span data-stu-id="561a6-110">However, in the second expression, `var` must be used because the result is a collection of anonymous types, and the name of that type is not accessible except to the compiler itself.</span></span> <span data-ttu-id="561a6-111">请注意，在示例 #2 中，`foreach` 迭代变量 `item` 必须也为隐式类型。</span><span class="sxs-lookup"><span data-stu-id="561a6-111">Note that in Example #2, the `foreach` iteration variable `item` must also be implicitly typed.</span></span>  
  
 [!code-csharp[csrefKeywordsTypes#18](../../../csharp/language-reference/keywords/codesnippet/CSharp/var_1.cs)]  
  
## <a name="see-also"></a><span data-ttu-id="561a6-112">另请参阅</span><span class="sxs-lookup"><span data-stu-id="561a6-112">See Also</span></span>  
 [<span data-ttu-id="561a6-113">C# 参考</span><span class="sxs-lookup"><span data-stu-id="561a6-113">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
 [<span data-ttu-id="561a6-114">C# 编程指南</span><span class="sxs-lookup"><span data-stu-id="561a6-114">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="561a6-115">隐式类型的局部变量</span><span class="sxs-lookup"><span data-stu-id="561a6-115">Implicitly Typed Local Variables</span></span>](../../../csharp/programming-guide/classes-and-structs/implicitly-typed-local-variables.md)
