---
title: 对 join 子句的结果进行排序
description: 如何对 join 子句的结果进行排序。
ms.date: 12/1/2016
ms.assetid: a7458901-1201-4c25-b8d9-c04ca52e0eb9
ms.openlocfilehash: f426152e614ed9a9c4aa41d7ba7cb8ddf1cd3063
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33269695"
---
# <a name="order-the-results-of-a-join-clause"></a><span data-ttu-id="eb0b2-103">对 join 子句的结果进行排序</span><span class="sxs-lookup"><span data-stu-id="eb0b2-103">Order the results of a join clause</span></span>
<span data-ttu-id="eb0b2-104">此示例演示如何对联接运算的结果进行排序。</span><span class="sxs-lookup"><span data-stu-id="eb0b2-104">This example shows how to order the results of a join operation.</span></span> <span data-ttu-id="eb0b2-105">请注意，排序在联接之后执行。</span><span class="sxs-lookup"><span data-stu-id="eb0b2-105">Note that the ordering is performed after the join.</span></span> <span data-ttu-id="eb0b2-106">虽然可以在联接之前将 `orderby` 子句用于一个或多个源序列，不过通常不建议这样做。</span><span class="sxs-lookup"><span data-stu-id="eb0b2-106">Although you can use an `orderby` clause with one or more of the source sequences before the join, generally we do not recommend it.</span></span> <span data-ttu-id="eb0b2-107">某些 LINQ 提供程序可能不会在联接之后保留该排序。</span><span class="sxs-lookup"><span data-stu-id="eb0b2-107">Some LINQ providers might not preserve that ordering after the join.</span></span>  
  
## <a name="example"></a><span data-ttu-id="eb0b2-108">示例</span><span class="sxs-lookup"><span data-stu-id="eb0b2-108">Example</span></span>  
 <span data-ttu-id="eb0b2-109">此查询创建一个分组联接，然后基于类别元素（仍处于范围中）对组进行排序。</span><span class="sxs-lookup"><span data-stu-id="eb0b2-109">This query creates a group join, and then sorts the groups based on the category element, which is still in scope.</span></span> <span data-ttu-id="eb0b2-110">在匿名类型初始值设定项内，一个子查询对来自产品序列的所有匹配元素进行排序。</span><span class="sxs-lookup"><span data-stu-id="eb0b2-110">Inside the anonymous type initializer, a sub-query orders all the matching elements from the products sequence.</span></span>  
  
 [!code-csharp[csProgGuideLINQ#81](../../../samples/snippets/csharp/concepts/linq/how-to-order-the-results-of-a-join-clause_1.cs)]  
 
## <a name="see-also"></a><span data-ttu-id="eb0b2-111">请参阅</span><span class="sxs-lookup"><span data-stu-id="eb0b2-111">See also</span></span>  
 [<span data-ttu-id="eb0b2-112">LINQ 查询表达式</span><span class="sxs-lookup"><span data-stu-id="eb0b2-112">LINQ query expressions</span></span>](index.md)  
 [<span data-ttu-id="eb0b2-113">orderby 子句</span><span class="sxs-lookup"><span data-stu-id="eb0b2-113">orderby clause</span></span>](../language-reference/keywords/orderby-clause.md)  
 [<span data-ttu-id="eb0b2-114">join 子句</span><span class="sxs-lookup"><span data-stu-id="eb0b2-114">join clause</span></span>](../language-reference/keywords/join-clause.md) 
