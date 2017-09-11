---
title: "从方法中返回查询"
description: "如何返回查询。"
keywords: .NET, .NET Core, C#
author: BillWagner
manager: wpickett
ms.author: wiwagn
ms.date: 11/30/2016
ms.topic: article
ms.prod: .net-core
ms.technology: .net-core-technologies
ms.devlang: dotnet
ms.assetid: db220f79-c35b-41f2-886c-cd068672d42d
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 747345f0a765bc6cbe947a2b0c7bc025eb599550
ms.contentlocale: zh-cn
ms.lasthandoff: 07/28/2017

---
# <a name="how-to-return-a-query-from-a-method-c-programming-guide"></a><span data-ttu-id="e9cdf-104">如何：从方法中返回查询（C# 编程指南）</span><span class="sxs-lookup"><span data-stu-id="e9cdf-104">How to: Return a Query from a Method (C# Programming Guide)</span></span>
<span data-ttu-id="e9cdf-105">此示例演示如何以返回值和 `out` 参数形式从方法中返回查询。</span><span class="sxs-lookup"><span data-stu-id="e9cdf-105">This example shows how to return a query from a method as the return value and as an `out` parameter.</span></span>  
  
 <span data-ttu-id="e9cdf-106">查询对象可编写，这意味着你可以从方法中返回查询。</span><span class="sxs-lookup"><span data-stu-id="e9cdf-106">Query objects are composable, meaning that you can return a query from a method.</span></span> <span data-ttu-id="e9cdf-107">表示查询的对象不会存储生成的集合，而会根据需要存储生成结果的步骤。</span><span class="sxs-lookup"><span data-stu-id="e9cdf-107">Objects that represent queries do not store the resulting collection, but rather the steps to produce the results when needed.</span></span> <span data-ttu-id="e9cdf-108">从方法中返回查询对象的好处是可以进一步编写或修改这些对象。</span><span class="sxs-lookup"><span data-stu-id="e9cdf-108">The advantage of returning query objects from methods is that they can be further composed or modified.</span></span> <span data-ttu-id="e9cdf-109">因此，返回查询的方法的任何返回值或 `out` 输出参数也必须具有该类型。</span><span class="sxs-lookup"><span data-stu-id="e9cdf-109">Therefore any return value or `out` parameter of a method that returns a query must also have that type.</span></span> <span data-ttu-id="e9cdf-110">如果某个方法可将查询具体化为具体的 <xref:System.Collections.Generic.List%601> 或 <xref:System.Array> 类型，则认为该方法在返回查询结果（而不是查询本身）。</span><span class="sxs-lookup"><span data-stu-id="e9cdf-110">If a method materializes a query into a concrete <xref:System.Collections.Generic.List%601> or <xref:System.Array> type, it is considered to be returning the query results instead of the query itself.</span></span> <span data-ttu-id="e9cdf-111">仍然能够编写或修改从方法中返回的查询变量。</span><span class="sxs-lookup"><span data-stu-id="e9cdf-111">A query variable that is returned from a method can still be composed or modified.</span></span>  
  
## <a name="example"></a><span data-ttu-id="e9cdf-112">示例</span><span class="sxs-lookup"><span data-stu-id="e9cdf-112">Example</span></span>  
 <span data-ttu-id="e9cdf-113">在下面的示例中，第一个方法以返回值的形式返回查询，第二个方法以 `out` 参数的形式返回查询。</span><span class="sxs-lookup"><span data-stu-id="e9cdf-113">In the following example, the first method returns a query as a return value, and the second method returns a query as an `out` parameter.</span></span> <span data-ttu-id="e9cdf-114">请注意，在这两种情况下，返回的都是查询，而不是查询结果。</span><span class="sxs-lookup"><span data-stu-id="e9cdf-114">Note that in both cases it is a query that is  returned, not query results.</span></span>  
  
 <span data-ttu-id="e9cdf-115">[!code-cs[csProgGuideLINQ#80](../../../samples/snippets/csharp/concepts/linq/how-to-return-a-query-from-a-method_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="e9cdf-115">[!code-cs[csProgGuideLINQ#80](../../../samples/snippets/csharp/concepts/linq/how-to-return-a-query-from-a-method_1.cs)]</span></span>  

## <a name="see-also"></a><span data-ttu-id="e9cdf-116">请参阅</span><span class="sxs-lookup"><span data-stu-id="e9cdf-116">See Also</span></span>  
 [<span data-ttu-id="e9cdf-117">LINQ 查询表达式</span><span class="sxs-lookup"><span data-stu-id="e9cdf-117">LINQ Query Expressions</span></span>](index.md)

