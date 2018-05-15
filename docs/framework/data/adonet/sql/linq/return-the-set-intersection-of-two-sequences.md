---
title: 返回两个序列的交集
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: d09c344e-3548-4944-a3ed-051880e3f5b8
ms.openlocfilehash: 9fd2a5dc435829d08594ea3c2f1c129328386250
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
---
# <a name="return-the-set-intersection-of-two-sequences"></a><span data-ttu-id="32d0b-102">返回两个序列的交集</span><span class="sxs-lookup"><span data-stu-id="32d0b-102">Return the Set Intersection of Two Sequences</span></span>
<span data-ttu-id="32d0b-103">使用 <xref:System.Linq.Queryable.Intersect%2A> 运算符可返回两个序列的交集。</span><span class="sxs-lookup"><span data-stu-id="32d0b-103">Use the <xref:System.Linq.Queryable.Intersect%2A> operator to return the set intersection of two sequences.</span></span>  
  
## <a name="example"></a><span data-ttu-id="32d0b-104">示例</span><span class="sxs-lookup"><span data-stu-id="32d0b-104">Example</span></span>  
 <span data-ttu-id="32d0b-105">此示例使用 <xref:System.Linq.Queryable.Intersect%2A> 返回既有 `Customers` 居住又有 `Employees` 居住的所有国家/地区的序列。</span><span class="sxs-lookup"><span data-stu-id="32d0b-105">This example uses <xref:System.Linq.Queryable.Intersect%2A> to return a sequence of all countries in which both `Customers` and `Employees` live.</span></span>  
  
 [!code-csharp[DLinqQueryExamples#42](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#42)]
 [!code-vb[DLinqQueryExamples#42](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#42)]  
  
 <span data-ttu-id="32d0b-106">在 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] 中，<xref:System.Linq.Queryable.Intersect%2A> 运算仅对集合而言是定义完善的。</span><span class="sxs-lookup"><span data-stu-id="32d0b-106">In [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)], the <xref:System.Linq.Queryable.Intersect%2A> operation is well defined only on sets.</span></span> <span data-ttu-id="32d0b-107">针对多重集的语义尚未定义。</span><span class="sxs-lookup"><span data-stu-id="32d0b-107">The semantics for multisets is undefined.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="32d0b-108">请参阅</span><span class="sxs-lookup"><span data-stu-id="32d0b-108">See Also</span></span>  
 [<span data-ttu-id="32d0b-109">查询示例</span><span class="sxs-lookup"><span data-stu-id="32d0b-109">Query Examples</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/query-examples.md)  
 [<span data-ttu-id="32d0b-110">标准查询运算符转换</span><span class="sxs-lookup"><span data-stu-id="32d0b-110">Standard Query Operator Translation</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/standard-query-operator-translation.md)
