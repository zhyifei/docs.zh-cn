---
title: 返回两个序列的交集
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: d09c344e-3548-4944-a3ed-051880e3f5b8
ms.openlocfilehash: 3458ebf8f5708496eef6246fa55cf528e8a32bc4
ms.sourcegitcommit: 4735bb7741555bcb870d7b42964d3774f4897a6e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/30/2019
ms.locfileid: "66380057"
---
# <a name="return-the-set-intersection-of-two-sequences"></a><span data-ttu-id="c419d-102">返回两个序列的交集</span><span class="sxs-lookup"><span data-stu-id="c419d-102">Return the Set Intersection of Two Sequences</span></span>
<span data-ttu-id="c419d-103">使用 <xref:System.Linq.Queryable.Intersect%2A> 运算符可返回两个序列的交集。</span><span class="sxs-lookup"><span data-stu-id="c419d-103">Use the <xref:System.Linq.Queryable.Intersect%2A> operator to return the set intersection of two sequences.</span></span>  
  
## <a name="example"></a><span data-ttu-id="c419d-104">示例</span><span class="sxs-lookup"><span data-stu-id="c419d-104">Example</span></span>  
 <span data-ttu-id="c419d-105">此示例使用<xref:System.Linq.Queryable.Intersect%2A>以返回所有国家/地区的序列中这两`Customers`和`Employees`live。</span><span class="sxs-lookup"><span data-stu-id="c419d-105">This example uses <xref:System.Linq.Queryable.Intersect%2A> to return a sequence of all countries/regions in which both `Customers` and `Employees` live.</span></span>  
  
 [!code-csharp[DLinqQueryExamples#42](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#42)]
 [!code-vb[DLinqQueryExamples#42](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#42)]  
  
 <span data-ttu-id="c419d-106">在 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] 中，<xref:System.Linq.Queryable.Intersect%2A> 运算仅对集合而言是定义完善的。</span><span class="sxs-lookup"><span data-stu-id="c419d-106">In [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)], the <xref:System.Linq.Queryable.Intersect%2A> operation is well defined only on sets.</span></span> <span data-ttu-id="c419d-107">针对多重集的语义尚未定义。</span><span class="sxs-lookup"><span data-stu-id="c419d-107">The semantics for multisets is undefined.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c419d-108">请参阅</span><span class="sxs-lookup"><span data-stu-id="c419d-108">See also</span></span>

- [<span data-ttu-id="c419d-109">查询示例</span><span class="sxs-lookup"><span data-stu-id="c419d-109">Query Examples</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/query-examples.md)
- [<span data-ttu-id="c419d-110">标准查询运算符转换</span><span class="sxs-lookup"><span data-stu-id="c419d-110">Standard Query Operator Translation</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/standard-query-operator-translation.md)
