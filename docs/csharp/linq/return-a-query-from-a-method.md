---
title: "从方法中返回查询"
description: "如何返回查询。"
keywords: .NET, .NET Core, C#
author: BillWagner
manager: wpickett
ms.author: wiwagn
ms.date: 11/30/2016
ms.topic: article
ms.prod: .net
ms.technology: devlang-csharp
ms.assetid: db220f79-c35b-41f2-886c-cd068672d42d
ms.openlocfilehash: c1b69e3f5f0cd2c50ae80d2454e6b7f13dc30344
ms.sourcegitcommit: 7e99f66ef09d2903e22c789c67ff5a10aa953b2f
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/18/2017
---
# <a name="how-to-return-a-query-from-a-method-c-programming-guide"></a><span data-ttu-id="9d16b-104">如何：从方法中返回查询（C# 编程指南）</span><span class="sxs-lookup"><span data-stu-id="9d16b-104">How to: Return a Query from a Method (C# Programming Guide)</span></span>
<span data-ttu-id="9d16b-105">此示例演示如何以返回值和 `out` 参数形式从方法中返回查询。</span><span class="sxs-lookup"><span data-stu-id="9d16b-105">This example shows how to return a query from a method as the return value and as an `out` parameter.</span></span>  
  
 <span data-ttu-id="9d16b-106">查询对象可编写，这意味着你可以从方法中返回查询。</span><span class="sxs-lookup"><span data-stu-id="9d16b-106">Query objects are composable, meaning that you can return a query from a method.</span></span> <span data-ttu-id="9d16b-107">表示查询的对象不会存储生成的集合，而会根据需要存储生成结果的步骤。</span><span class="sxs-lookup"><span data-stu-id="9d16b-107">Objects that represent queries do not store the resulting collection, but rather the steps to produce the results when needed.</span></span> <span data-ttu-id="9d16b-108">从方法中返回查询对象的好处是可以进一步编写或修改这些对象。</span><span class="sxs-lookup"><span data-stu-id="9d16b-108">The advantage of returning query objects from methods is that they can be further composed or modified.</span></span> <span data-ttu-id="9d16b-109">因此，返回查询的方法的任何返回值或 `out` 输出参数也必须具有该类型。</span><span class="sxs-lookup"><span data-stu-id="9d16b-109">Therefore any return value or `out` parameter of a method that returns a query must also have that type.</span></span> <span data-ttu-id="9d16b-110">如果某个方法可将查询具体化为具体的 <xref:System.Collections.Generic.List%601> 或 <xref:System.Array> 类型，则认为该方法在返回查询结果（而不是查询本身）。</span><span class="sxs-lookup"><span data-stu-id="9d16b-110">If a method materializes a query into a concrete <xref:System.Collections.Generic.List%601> or <xref:System.Array> type, it is considered to be returning the query results instead of the query itself.</span></span> <span data-ttu-id="9d16b-111">仍然能够编写或修改从方法中返回的查询变量。</span><span class="sxs-lookup"><span data-stu-id="9d16b-111">A query variable that is returned from a method can still be composed or modified.</span></span>  
  
## <a name="example"></a><span data-ttu-id="9d16b-112">示例</span><span class="sxs-lookup"><span data-stu-id="9d16b-112">Example</span></span>  
 <span data-ttu-id="9d16b-113">在下面的示例中，第一个方法以返回值的形式返回查询，第二个方法以 `out` 参数的形式返回查询。</span><span class="sxs-lookup"><span data-stu-id="9d16b-113">In the following example, the first method returns a query as a return value, and the second method returns a query as an `out` parameter.</span></span> <span data-ttu-id="9d16b-114">请注意，在这两种情况下，返回的都是查询，而不是查询结果。</span><span class="sxs-lookup"><span data-stu-id="9d16b-114">Note that in both cases it is a query that is  returned, not query results.</span></span>  
  
 [!code-csharp[csProgGuideLINQ#80](../../../samples/snippets/csharp/concepts/linq/how-to-return-a-query-from-a-method_1.cs)]  

## <a name="see-also"></a><span data-ttu-id="9d16b-115">另请参阅</span><span class="sxs-lookup"><span data-stu-id="9d16b-115">See Also</span></span>  
 [<span data-ttu-id="9d16b-116">LINQ 查询表达式</span><span class="sxs-lookup"><span data-stu-id="9d16b-116">LINQ Query Expressions</span></span>](index.md)
