---
title: 在内存中存储查询结果
description: 如何存储结果。
ms.date: 11/30/2016
ms.assetid: 5b863961-1750-4cf9-9607-acea5054d15a
ms.openlocfilehash: 52d502a841c428bd90a26c803ba577e76c17197c
ms.sourcegitcommit: 4c158beee818c408d45a9609bfc06f209a523e22
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/03/2018
ms.locfileid: "37404296"
---
# <a name="store-the-results-of-a-query-in-memory"></a><span data-ttu-id="a27e3-103">在内存中存储查询结果</span><span class="sxs-lookup"><span data-stu-id="a27e3-103">Store the results of a query in memory</span></span>

<span data-ttu-id="a27e3-104">查询基本上是针对如何检索和组织数据的一套说明。</span><span class="sxs-lookup"><span data-stu-id="a27e3-104">A query is basically a set of instructions for how to retrieve and organize data.</span></span> <span data-ttu-id="a27e3-105">当请求结果中的每个后续项目时，查询将延迟执行。</span><span class="sxs-lookup"><span data-stu-id="a27e3-105">Queries are executed lazily, as each subsequent item in the result is requested.</span></span> <span data-ttu-id="a27e3-106">使用 `foreach` 循环访问结果时，项将在受到访问时返回。</span><span class="sxs-lookup"><span data-stu-id="a27e3-106">When you use `foreach` to iterate the results, items are returned as accessed.</span></span> <span data-ttu-id="a27e3-107">若要在不执行 `foreach` 循环的情况下评估查询并存储其结果，只需调用查询变量上的以下方法之一：</span><span class="sxs-lookup"><span data-stu-id="a27e3-107">To evaluate a query and store its results without executing a `foreach` loop, just call one of the following methods on the query variable:</span></span>

- <xref:System.Linq.Enumerable.ToList%2A>

- <xref:System.Linq.Enumerable.ToArray%2A>

- <xref:System.Linq.Enumerable.ToDictionary%2A>

- <xref:System.Linq.Enumerable.ToLookup%2A>

 <span data-ttu-id="a27e3-108">建议在存储查询结果时，将返回的集合对象分配给一个新变量，如下面的示例所示：</span><span class="sxs-lookup"><span data-stu-id="a27e3-108">We recommend that when you store the query results, you assign the returned collection object to a new variable as shown in the following example:</span></span>

## <a name="example"></a><span data-ttu-id="a27e3-109">示例</span><span class="sxs-lookup"><span data-stu-id="a27e3-109">Example</span></span>

[!code-csharp[csProgGuideLINQ#25](~/samples/snippets/csharp/concepts/linq/how-to-store-the-results-of-a-query-in-memory_1.cs)]

## <a name="see-also"></a><span data-ttu-id="a27e3-110">请参阅</span><span class="sxs-lookup"><span data-stu-id="a27e3-110">See also</span></span>

[<span data-ttu-id="a27e3-111">语言集成查询 (LINQ)</span><span class="sxs-lookup"><span data-stu-id="a27e3-111">Language Integrated Query (LINQ)</span></span>](index.md)