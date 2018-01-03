---
title: "如何：处理查询中的复合键"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
ms.assetid: ce2f14fd-1038-458a-91e3-a078c61f0d10
caps.latest.revision: "2"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.workload: dotnet
ms.openlocfilehash: 2b0954d4659d1cc39cead0658fbd21dcd6dd12e5
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-handle-composite-keys-in-queries"></a><span data-ttu-id="7587f-102">如何：处理查询中的复合键</span><span class="sxs-lookup"><span data-stu-id="7587f-102">How to: Handle Composite Keys in Queries</span></span>
<span data-ttu-id="7587f-103">有些运算符只能带一个自变量。</span><span class="sxs-lookup"><span data-stu-id="7587f-103">Some operators can take only one argument.</span></span> <span data-ttu-id="7587f-104">如果你的自变量必须包含数据库中的多个列，则你必须创建一个匿名类型来表示这种组合。</span><span class="sxs-lookup"><span data-stu-id="7587f-104">If your argument must include more than one column from the database, you must create an anonymous type to represent the combination.</span></span>  
  
## <a name="example"></a><span data-ttu-id="7587f-105">示例</span><span class="sxs-lookup"><span data-stu-id="7587f-105">Example</span></span>  
 <span data-ttu-id="7587f-106">下面的示例显示了调用 `GroupBy` 运算符的查询，此运算符只能带一个 `key` 参数。</span><span class="sxs-lookup"><span data-stu-id="7587f-106">The following example shows a query that invokes the `GroupBy` operator, which can take only one `key` argument.</span></span>  
  
 [!code-csharp[DLinqCompositeKeys#1](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqCompositeKeys/cs/Program.cs#1)]
 [!code-vb[DLinqCompositeKeys#1](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqCompositeKeys/vb/Module1.vb#1)]  
  
## <a name="example"></a><span data-ttu-id="7587f-107">示例</span><span class="sxs-lookup"><span data-stu-id="7587f-107">Example</span></span>  
 <span data-ttu-id="7587f-108">联接也属于这种情况，如下例中所示：</span><span class="sxs-lookup"><span data-stu-id="7587f-108">The same situation pertains to joins, as in the following example:</span></span>  
  
 [!code-csharp[DLinqCompositeKeys#2](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqCompositeKeys/cs/Program.cs#2)]
 [!code-vb[DLinqCompositeKeys#2](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqCompositeKeys/vb/Module1.vb#2)]  
  
## <a name="see-also"></a><span data-ttu-id="7587f-109">请参阅</span><span class="sxs-lookup"><span data-stu-id="7587f-109">See Also</span></span>  
 [<span data-ttu-id="7587f-110">查询概念</span><span class="sxs-lookup"><span data-stu-id="7587f-110">Query Concepts</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/query-concepts.md)
