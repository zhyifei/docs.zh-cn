---
title: 返回两个序列的交集
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: d09c344e-3548-4944-a3ed-051880e3f5b8
ms.openlocfilehash: bb1785b12df2e8a835ba49ae59d0448fbebf794c
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54506818"
---
# <a name="return-the-set-intersection-of-two-sequences"></a><span data-ttu-id="4885d-102">返回两个序列的交集</span><span class="sxs-lookup"><span data-stu-id="4885d-102">Return the Set Intersection of Two Sequences</span></span>
<span data-ttu-id="4885d-103">使用 <xref:System.Linq.Queryable.Intersect%2A> 运算符可返回两个序列的交集。</span><span class="sxs-lookup"><span data-stu-id="4885d-103">Use the <xref:System.Linq.Queryable.Intersect%2A> operator to return the set intersection of two sequences.</span></span>  
  
## <a name="example"></a><span data-ttu-id="4885d-104">示例</span><span class="sxs-lookup"><span data-stu-id="4885d-104">Example</span></span>  
 <span data-ttu-id="4885d-105">此示例使用 <xref:System.Linq.Queryable.Intersect%2A> 返回既有 `Customers` 居住又有 `Employees` 居住的所有国家/地区的序列。</span><span class="sxs-lookup"><span data-stu-id="4885d-105">This example uses <xref:System.Linq.Queryable.Intersect%2A> to return a sequence of all countries in which both `Customers` and `Employees` live.</span></span>  
  
 [!code-csharp[DLinqQueryExamples#42](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#42)]
 [!code-vb[DLinqQueryExamples#42](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#42)]  
  
 <span data-ttu-id="4885d-106">在 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] 中，<xref:System.Linq.Queryable.Intersect%2A> 运算仅对集合而言是定义完善的。</span><span class="sxs-lookup"><span data-stu-id="4885d-106">In [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)], the <xref:System.Linq.Queryable.Intersect%2A> operation is well defined only on sets.</span></span> <span data-ttu-id="4885d-107">针对多重集的语义尚未定义。</span><span class="sxs-lookup"><span data-stu-id="4885d-107">The semantics for multisets is undefined.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4885d-108">请参阅</span><span class="sxs-lookup"><span data-stu-id="4885d-108">See also</span></span>
- [<span data-ttu-id="4885d-109">查询示例</span><span class="sxs-lookup"><span data-stu-id="4885d-109">Query Examples</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/query-examples.md)
- [<span data-ttu-id="4885d-110">标准查询运算符转换</span><span class="sxs-lookup"><span data-stu-id="4885d-110">Standard Query Operator Translation</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/standard-query-operator-translation.md)
