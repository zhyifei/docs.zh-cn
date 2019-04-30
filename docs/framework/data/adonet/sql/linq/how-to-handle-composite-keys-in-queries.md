---
title: 如何：处理查询中的复合键
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: ce2f14fd-1038-458a-91e3-a078c61f0d10
ms.openlocfilehash: 2621ab4db207d1b868fbe3778c30c744201b0506
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "62033808"
---
# <a name="how-to-handle-composite-keys-in-queries"></a><span data-ttu-id="71579-102">如何：处理查询中的复合键</span><span class="sxs-lookup"><span data-stu-id="71579-102">How to: Handle Composite Keys in Queries</span></span>
<span data-ttu-id="71579-103">有些运算符只能带一个自变量。</span><span class="sxs-lookup"><span data-stu-id="71579-103">Some operators can take only one argument.</span></span> <span data-ttu-id="71579-104">如果您的参数必须包含数据库中的多个列，则您必须创建一个匿名类型来表示这种组合。</span><span class="sxs-lookup"><span data-stu-id="71579-104">If your argument must include more than one column from the database, you must create an anonymous type to represent the combination.</span></span>  
  
## <a name="example"></a><span data-ttu-id="71579-105">示例</span><span class="sxs-lookup"><span data-stu-id="71579-105">Example</span></span>  
 <span data-ttu-id="71579-106">下面的示例显示了调用 `GroupBy` 运算符的查询，此运算符只能带一个 `key` 自变量。</span><span class="sxs-lookup"><span data-stu-id="71579-106">The following example shows a query that invokes the `GroupBy` operator, which can take only one `key` argument.</span></span>  
  
 [!code-csharp[DLinqCompositeKeys#1](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqCompositeKeys/cs/Program.cs#1)]
 [!code-vb[DLinqCompositeKeys#1](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqCompositeKeys/vb/Module1.vb#1)]  
  
## <a name="example"></a><span data-ttu-id="71579-107">示例</span><span class="sxs-lookup"><span data-stu-id="71579-107">Example</span></span>  
 <span data-ttu-id="71579-108">联接也属于这种情况，如下例中所示：</span><span class="sxs-lookup"><span data-stu-id="71579-108">The same situation pertains to joins, as in the following example:</span></span>  
  
 [!code-csharp[DLinqCompositeKeys#2](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqCompositeKeys/cs/Program.cs#2)]
 [!code-vb[DLinqCompositeKeys#2](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqCompositeKeys/vb/Module1.vb#2)]  
  
## <a name="see-also"></a><span data-ttu-id="71579-109">请参阅</span><span class="sxs-lookup"><span data-stu-id="71579-109">See also</span></span>

- [<span data-ttu-id="71579-110">查询概念</span><span class="sxs-lookup"><span data-stu-id="71579-110">Query Concepts</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/query-concepts.md)
