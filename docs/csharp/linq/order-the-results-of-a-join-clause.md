---
title: "对 join 子句的结果进行排序"
description: "如何对 join 子句的结果进行排序。"
keywords: .NET, .NET Core, C#
author: BillWagner
manager: wpickett
ms.author: wiwagn
ms.date: 12/1/2016
ms.topic: article
ms.prod: .net-core
ms.technology: .net-core-technologies
ms.devlang: dotnet
ms.assetid: a7458901-1201-4c25-b8d9-c04ca52e0eb9
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 6272181647bb200c18231c5fc836e3dd1a2d6d55
ms.contentlocale: zh-cn
ms.lasthandoff: 07/28/2017

---
# <a name="order-the-results-of-a-join-clause"></a><span data-ttu-id="e77fe-104">对 join 子句的结果进行排序</span><span class="sxs-lookup"><span data-stu-id="e77fe-104">Order the results of a join clause</span></span>
<span data-ttu-id="e77fe-105">此示例演示如何对联接运算的结果进行排序。</span><span class="sxs-lookup"><span data-stu-id="e77fe-105">This example shows how to order the results of a join operation.</span></span> <span data-ttu-id="e77fe-106">请注意，排序在联接之后执行。</span><span class="sxs-lookup"><span data-stu-id="e77fe-106">Note that the ordering is performed after the join.</span></span> <span data-ttu-id="e77fe-107">虽然可以在联接之前将 `orderby` 子句用于一个或多个源序列，不过通常不建议这样做。</span><span class="sxs-lookup"><span data-stu-id="e77fe-107">Although you can use an `orderby` clause with one or more of the source sequences before the join, generally we do not recommend it.</span></span> <span data-ttu-id="e77fe-108">某些 LINQ 提供程序可能不会在联接之后保留该排序。</span><span class="sxs-lookup"><span data-stu-id="e77fe-108">Some LINQ providers might not preserve that ordering after the join.</span></span>  
  
## <a name="example"></a><span data-ttu-id="e77fe-109">示例</span><span class="sxs-lookup"><span data-stu-id="e77fe-109">Example</span></span>  
 <span data-ttu-id="e77fe-110">此查询创建一个分组联接，然后基于类别元素（仍处于范围中）对组进行排序。</span><span class="sxs-lookup"><span data-stu-id="e77fe-110">This query creates a group join, and then sorts the groups based on the category element, which is still in scope.</span></span> <span data-ttu-id="e77fe-111">在匿名类型初始值设定项内，一个子查询对来自产品序列的所有匹配元素进行排序。</span><span class="sxs-lookup"><span data-stu-id="e77fe-111">Inside the anonymous type initializer, a sub-query orders all the matching elements from the products sequence.</span></span>  
  
 <span data-ttu-id="e77fe-112">[!code-cs[csProgGuideLINQ#81](../../../samples/snippets/csharp/concepts/linq/how-to-order-the-results-of-a-join-clause_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="e77fe-112">[!code-cs[csProgGuideLINQ#81](../../../samples/snippets/csharp/concepts/linq/how-to-order-the-results-of-a-join-clause_1.cs)]</span></span>  
 
## <a name="see-also"></a><span data-ttu-id="e77fe-113">请参阅</span><span class="sxs-lookup"><span data-stu-id="e77fe-113">See also</span></span>  
 <span data-ttu-id="e77fe-114">[LINQ 查询表达式](index.md) </span><span class="sxs-lookup"><span data-stu-id="e77fe-114">[LINQ query expressions](index.md) </span></span>  
 <span data-ttu-id="e77fe-115">[orderby 子句](../language-reference/keywords/orderby-clause.md) </span><span class="sxs-lookup"><span data-stu-id="e77fe-115">[orderby clause](../language-reference/keywords/orderby-clause.md) </span></span>  
 [<span data-ttu-id="e77fe-116">join 子句</span><span class="sxs-lookup"><span data-stu-id="e77fe-116">join clause</span></span>](../language-reference/keywords/join-clause.md) 

