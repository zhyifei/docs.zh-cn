---
title: var（C# 参考）
ms.date: 07/20/2015
f1_keywords:
- var
- var_CSharpKeyword
helpviewer_keywords:
- var keyword [C#]
ms.assetid: 0777850a-2691-4e3e-927f-0c850f5efe15
ms.openlocfilehash: c311993ebcc5b5072959b2e79242bcdabd6de913
ms.sourcegitcommit: 89c93d05c2281b4c834f48f6c8df1047e1410980
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/15/2018
---
# <a name="var-c-reference"></a><span data-ttu-id="0607c-102">var（C# 参考）</span><span class="sxs-lookup"><span data-stu-id="0607c-102">var (C# Reference)</span></span>
<span data-ttu-id="0607c-103">从 Visual C# 3.0 开始，在方法范围内声明的变量可以具有隐式“类型”`var`。</span><span class="sxs-lookup"><span data-stu-id="0607c-103">Beginning in Visual C# 3.0, variables that are declared at method scope can have an implicit "type" `var`.</span></span> <span data-ttu-id="0607c-104">隐式类型本地变量为强类型，就像用户已经自行声明该类型，但编译器决定类型一样。</span><span class="sxs-lookup"><span data-stu-id="0607c-104">An implicitly typed local variable is strongly typed just as if you had declared the type yourself, but the compiler determines the type.</span></span> <span data-ttu-id="0607c-105">`i` 的以下两个声明在功能上是等效的：</span><span class="sxs-lookup"><span data-stu-id="0607c-105">The following two declarations of `i` are functionally equivalent:</span></span>  
  
```csharp  
var i = 10; // implicitly typed  
int i = 10; //explicitly typed  
```  
  
 <span data-ttu-id="0607c-106">有关详细信息，请参阅[隐式类型的局部变量](../../../csharp/programming-guide/classes-and-structs/implicitly-typed-local-variables.md)和 [LINQ 查询操作中的类型关系](../../../csharp/programming-guide/concepts/linq/type-relationships-in-linq-query-operations.md)。</span><span class="sxs-lookup"><span data-stu-id="0607c-106">For more information, see [Implicitly Typed Local Variables](../../../csharp/programming-guide/classes-and-structs/implicitly-typed-local-variables.md) and [Type Relationships in LINQ Query Operations](../../../csharp/programming-guide/concepts/linq/type-relationships-in-linq-query-operations.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="0607c-107">示例</span><span class="sxs-lookup"><span data-stu-id="0607c-107">Example</span></span>  
 <span data-ttu-id="0607c-108">下面的示例演示两个查询表达式。</span><span class="sxs-lookup"><span data-stu-id="0607c-108">The following example shows two query expressions.</span></span> <span data-ttu-id="0607c-109">在第一个表达式中，`var` 的使用是允许的，但不是必需的，因为查询结果的类型可以明确表述为 `IEnumerable<string>`。</span><span class="sxs-lookup"><span data-stu-id="0607c-109">In the first expression, the use of `var` is permitted but is not required, because the type of the query result can be stated explicitly as an `IEnumerable<string>`.</span></span> <span data-ttu-id="0607c-110">不过，在第二个表达式中，`var` 允许结果是一系列匿名类型，且相应类型的名称只可供编译器本身访问。</span><span class="sxs-lookup"><span data-stu-id="0607c-110">However, in the second expression, `var` allows the result to be a collection of anonymous types, and the name of that type is not accessible except to the compiler itself.</span></span> <span data-ttu-id="0607c-111">如果使用 `var`，便无法为结果新建类。</span><span class="sxs-lookup"><span data-stu-id="0607c-111">Use of `var` eliminates the requirement to create a new class for the result.</span></span> <span data-ttu-id="0607c-112">请注意，在示例 #2 中，`foreach` 迭代变量 `item` 必须也为隐式类型。</span><span class="sxs-lookup"><span data-stu-id="0607c-112">Note that in Example #2, the `foreach` iteration variable `item` must also be implicitly typed.</span></span>  
  
 [!code-csharp[csrefKeywordsTypes#18](../../../csharp/language-reference/keywords/codesnippet/CSharp/var_1.cs)]  
  
## <a name="see-also"></a><span data-ttu-id="0607c-113">请参阅</span><span class="sxs-lookup"><span data-stu-id="0607c-113">See Also</span></span>  
 [<span data-ttu-id="0607c-114">C# 参考</span><span class="sxs-lookup"><span data-stu-id="0607c-114">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
 [<span data-ttu-id="0607c-115">C# 编程指南</span><span class="sxs-lookup"><span data-stu-id="0607c-115">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="0607c-116">隐式类型的局部变量</span><span class="sxs-lookup"><span data-stu-id="0607c-116">Implicitly Typed Local Variables</span></span>](../../../csharp/programming-guide/classes-and-structs/implicitly-typed-local-variables.md)
