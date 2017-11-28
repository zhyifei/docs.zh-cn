---
title: "在内存中存储查询结果"
description: "如何存储结果。"
keywords: .NET, .NET Core, C#
author: BillWagner
manager: wpickett
ms.author: wiwagn
ms.date: 11/30/2016
ms.topic: article
ms.prod: .net
ms.technology: devlang-csharp
ms.assetid: 5b863961-1750-4cf9-9607-acea5054d15a
ms.openlocfilehash: 86a9c2d464eac83cabb5faa68987ad580fc31248
ms.sourcegitcommit: 7e99f66ef09d2903e22c789c67ff5a10aa953b2f
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/18/2017
---
# <a name="store-the-results-of-a-query-in-memory"></a><span data-ttu-id="3d519-104">在内存中存储查询结果</span><span class="sxs-lookup"><span data-stu-id="3d519-104">Store the results of a query in memory</span></span>

<span data-ttu-id="3d519-105">查询基本上是针对如何检索和组织数据的一套说明。</span><span class="sxs-lookup"><span data-stu-id="3d519-105">A query is basically a set of instructions for how to retrieve and organize data.</span></span> <span data-ttu-id="3d519-106">当请求结果中的每个后续项目时，查询将延迟执行。</span><span class="sxs-lookup"><span data-stu-id="3d519-106">Queries are executed lazily, as each subsequent item in the result is requested.</span></span> <span data-ttu-id="3d519-107">使用 `foreach` 循环访问结果时，项将在受到访问时返回。</span><span class="sxs-lookup"><span data-stu-id="3d519-107">When you use `foreach` to iterate the results, items are returned as accessed.</span></span> <span data-ttu-id="3d519-108">若要在不执行 `foreach` 循环的情况下评估查询并存储其结果，只需调用查询变量上的以下方法之一：</span><span class="sxs-lookup"><span data-stu-id="3d519-108">To evaluate a query and store its results without executing a `foreach` loop, just call one of the following methods on the query variable:</span></span>  
  
-   <xref:System.Linq.Enumerable.ToList%2A>  
  
-   <xref:System.Linq.Enumerable.ToArray%2A>  
  
-   <xref:System.Linq.Enumerable.ToDictionary%2A>  
  
-   <xref:System.Linq.Enumerable.ToLookup%2A>  
  
 <span data-ttu-id="3d519-109">建议在存储查询结果时，将返回的集合对象分配给一个新变量，如下面的示例所示：</span><span class="sxs-lookup"><span data-stu-id="3d519-109">We recommend that when you store the query results, you assign the returned collection object to a new variable as shown in the following example:</span></span>  
  
## <a name="example"></a><span data-ttu-id="3d519-110">示例</span><span class="sxs-lookup"><span data-stu-id="3d519-110">Example</span></span>  
 [!code-csharp[csProgGuideLINQ#25](../../../samples/snippets/csharp/concepts/linq/how-to-store-the-results-of-a-query-in-memory_1.cs)]  
  

## <a name="see-also"></a><span data-ttu-id="3d519-111">另请参阅</span><span class="sxs-lookup"><span data-stu-id="3d519-111">See Also</span></span>  
 [<span data-ttu-id="3d519-112">LINQ 查询表达式</span><span class="sxs-lookup"><span data-stu-id="3d519-112">LINQ Query Expressions</span></span>](index.md)
