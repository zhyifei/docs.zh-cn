---
title: "对 join 子句的结果进行排序"
description: "如何对 join 子句的结果进行排序。"
keywords: .NET, .NET Core, C#
author: BillWagner
manager: wpickett
ms.author: wiwagn
ms.date: 12/1/2016
ms.topic: article
ms.prod: .net
ms.technology: devlang-csharp
ms.assetid: a7458901-1201-4c25-b8d9-c04ca52e0eb9
ms.openlocfilehash: f948c18fb16a4f3ac02945b4a63583f1b01cad40
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="order-the-results-of-a-join-clause"></a><span data-ttu-id="f1903-104">对 join 子句的结果进行排序</span><span class="sxs-lookup"><span data-stu-id="f1903-104">Order the results of a join clause</span></span>
<span data-ttu-id="f1903-105">此示例演示如何对联接运算的结果进行排序。</span><span class="sxs-lookup"><span data-stu-id="f1903-105">This example shows how to order the results of a join operation.</span></span> <span data-ttu-id="f1903-106">请注意，排序在联接之后执行。</span><span class="sxs-lookup"><span data-stu-id="f1903-106">Note that the ordering is performed after the join.</span></span> <span data-ttu-id="f1903-107">虽然可以在联接之前将 `orderby` 子句用于一个或多个源序列，不过通常不建议这样做。</span><span class="sxs-lookup"><span data-stu-id="f1903-107">Although you can use an `orderby` clause with one or more of the source sequences before the join, generally we do not recommend it.</span></span> <span data-ttu-id="f1903-108">某些 LINQ 提供程序可能不会在联接之后保留该排序。</span><span class="sxs-lookup"><span data-stu-id="f1903-108">Some LINQ providers might not preserve that ordering after the join.</span></span>  
  
## <a name="example"></a><span data-ttu-id="f1903-109">示例</span><span class="sxs-lookup"><span data-stu-id="f1903-109">Example</span></span>  
 <span data-ttu-id="f1903-110">此查询创建一个分组联接，然后基于类别元素（仍处于范围中）对组进行排序。</span><span class="sxs-lookup"><span data-stu-id="f1903-110">This query creates a group join, and then sorts the groups based on the category element, which is still in scope.</span></span> <span data-ttu-id="f1903-111">在匿名类型初始值设定项内，一个子查询对来自产品序列的所有匹配元素进行排序。</span><span class="sxs-lookup"><span data-stu-id="f1903-111">Inside the anonymous type initializer, a sub-query orders all the matching elements from the products sequence.</span></span>  
  
 [!code-csharp[csProgGuideLINQ#81](../../../samples/snippets/csharp/concepts/linq/how-to-order-the-results-of-a-join-clause_1.cs)]  
 
## <a name="see-also"></a><span data-ttu-id="f1903-112">请参阅</span><span class="sxs-lookup"><span data-stu-id="f1903-112">See also</span></span>  
 [<span data-ttu-id="f1903-113">LINQ 查询表达式</span><span class="sxs-lookup"><span data-stu-id="f1903-113">LINQ query expressions</span></span>](index.md)  
 [<span data-ttu-id="f1903-114">orderby 子句</span><span class="sxs-lookup"><span data-stu-id="f1903-114">orderby clause</span></span>](../language-reference/keywords/orderby-clause.md)  
 [<span data-ttu-id="f1903-115">join 子句</span><span class="sxs-lookup"><span data-stu-id="f1903-115">join clause</span></span>](../language-reference/keywords/join-clause.md) 
