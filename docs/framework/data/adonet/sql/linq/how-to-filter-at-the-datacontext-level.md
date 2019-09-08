---
title: 如何：在 DataContext 级别进行筛选
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 15505cd7-0df2-427a-9f86-e0f96f60ee2e
ms.openlocfilehash: 0ef5ba8e975cb1c59720c96b214ae2696cc6356e
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/07/2019
ms.locfileid: "70781938"
---
# <a name="how-to-filter-at-the-datacontext-level"></a><span data-ttu-id="bc516-102">如何：在 DataContext 级别进行筛选</span><span class="sxs-lookup"><span data-stu-id="bc516-102">How to: Filter at the DataContext Level</span></span>
<span data-ttu-id="bc516-103">您可以在 `EntitySets` 级别筛选 `DataContext`。</span><span class="sxs-lookup"><span data-stu-id="bc516-103">You can filter `EntitySets` at the `DataContext` level.</span></span> <span data-ttu-id="bc516-104">此类筛选器适用于用此 <xref:System.Data.Linq.DataContext> 实例执行的所有查询。</span><span class="sxs-lookup"><span data-stu-id="bc516-104">Such filters apply to all queries done with that <xref:System.Data.Linq.DataContext> instance.</span></span>  
  
## <a name="example"></a><span data-ttu-id="bc516-105">示例</span><span class="sxs-lookup"><span data-stu-id="bc516-105">Example</span></span>  
 <span data-ttu-id="bc516-106">在下面的示例中，使用 <xref:System.Data.Linq.DataLoadOptions.AssociateWith%28System.Linq.Expressions.LambdaExpression%29?displayProperty=nameWithType> 来筛选截至 `ShippedDate` 的客户的预加载订单。</span><span class="sxs-lookup"><span data-stu-id="bc516-106">In the following example, <xref:System.Data.Linq.DataLoadOptions.AssociateWith%28System.Linq.Expressions.LambdaExpression%29?displayProperty=nameWithType> is used to filter the pre-loaded orders for customers by `ShippedDate`.</span></span>  
  
 [!code-csharp[DLinqQueryConcepts#10](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryConcepts/cs/Program.cs#10)]
 [!code-vb[DLinqQueryConcepts#10](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryConcepts/vb/Module1.vb#10)]  
  
## <a name="see-also"></a><span data-ttu-id="bc516-107">请参阅</span><span class="sxs-lookup"><span data-stu-id="bc516-107">See also</span></span>

- [<span data-ttu-id="bc516-108">查询概念</span><span class="sxs-lookup"><span data-stu-id="bc516-108">Query Concepts</span></span>](query-concepts.md)
