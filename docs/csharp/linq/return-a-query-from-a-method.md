---
title: 从方法中返回查询
description: 如何返回查询。
ms.date: 11/30/2016
ms.assetid: db220f79-c35b-41f2-886c-cd068672d42d
ms.openlocfilehash: 13f0839f712cb76b34c98157a30315787d300109
ms.sourcegitcommit: 4c158beee818c408d45a9609bfc06f209a523e22
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/03/2018
ms.locfileid: "37404146"
---
# <a name="how-to-return-a-query-from-a-method-c-programming-guide"></a><span data-ttu-id="00738-103">如何：从方法中返回查询（C# 编程指南）</span><span class="sxs-lookup"><span data-stu-id="00738-103">How to: Return a Query from a Method (C# Programming Guide)</span></span>
<span data-ttu-id="00738-104">此示例演示如何以返回值和 `out` 参数形式从方法中返回查询。</span><span class="sxs-lookup"><span data-stu-id="00738-104">This example shows how to return a query from a method as the return value and as an `out` parameter.</span></span>  
  
 <span data-ttu-id="00738-105">查询对象可编写，这意味着你可以从方法中返回查询。</span><span class="sxs-lookup"><span data-stu-id="00738-105">Query objects are composable, meaning that you can return a query from a method.</span></span> <span data-ttu-id="00738-106">表示查询的对象不会存储生成的集合，而会根据需要存储生成结果的步骤。</span><span class="sxs-lookup"><span data-stu-id="00738-106">Objects that represent queries do not store the resulting collection, but rather the steps to produce the results when needed.</span></span> <span data-ttu-id="00738-107">从方法中返回查询对象的好处是可以进一步编写或修改这些对象。</span><span class="sxs-lookup"><span data-stu-id="00738-107">The advantage of returning query objects from methods is that they can be further composed or modified.</span></span> <span data-ttu-id="00738-108">因此，返回查询的方法的任何返回值或 `out` 输出参数也必须具有该类型。</span><span class="sxs-lookup"><span data-stu-id="00738-108">Therefore any return value or `out` parameter of a method that returns a query must also have that type.</span></span> <span data-ttu-id="00738-109">如果某个方法可将查询具体化为具体的 <xref:System.Collections.Generic.List%601> 或 <xref:System.Array> 类型，则认为该方法在返回查询结果（而不是查询本身）。</span><span class="sxs-lookup"><span data-stu-id="00738-109">If a method materializes a query into a concrete <xref:System.Collections.Generic.List%601> or <xref:System.Array> type, it is considered to be returning the query results instead of the query itself.</span></span> <span data-ttu-id="00738-110">仍然能够编写或修改从方法中返回的查询变量。</span><span class="sxs-lookup"><span data-stu-id="00738-110">A query variable that is returned from a method can still be composed or modified.</span></span>  
  
## <a name="example"></a><span data-ttu-id="00738-111">示例</span><span class="sxs-lookup"><span data-stu-id="00738-111">Example</span></span>  
 <span data-ttu-id="00738-112">在下面的示例中，第一个方法以返回值的形式返回查询，第二个方法以 `out` 参数的形式返回查询。</span><span class="sxs-lookup"><span data-stu-id="00738-112">In the following example, the first method returns a query as a return value, and the second method returns a query as an `out` parameter.</span></span> <span data-ttu-id="00738-113">请注意，在这两种情况下，返回的都是查询，而不是查询结果。</span><span class="sxs-lookup"><span data-stu-id="00738-113">Note that in both cases it is a query that is  returned, not query results.</span></span>  
  
 [!code-csharp[csProgGuideLINQ#80](~/samples/snippets/csharp/concepts/linq/how-to-return-a-query-from-a-method_1.cs)]  

## <a name="see-also"></a><span data-ttu-id="00738-114">请参阅</span><span class="sxs-lookup"><span data-stu-id="00738-114">See Also</span></span>  
 [<span data-ttu-id="00738-115">语言集成查询 (LINQ)</span><span class="sxs-lookup"><span data-stu-id="00738-115">Language Integrated Query (LINQ)</span></span>](index.md)
