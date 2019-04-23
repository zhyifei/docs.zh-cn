---
title: 连接两个序列
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 76767e7c-0607-4e1d-9ca2-a94f311f45eb
ms.openlocfilehash: a2f2510cb334f4e22a7b0c6015a0a93b4dc11579
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/18/2019
ms.locfileid: "59142774"
---
# <a name="concatenate-two-sequences"></a><span data-ttu-id="ff76f-102">连接两个序列</span><span class="sxs-lookup"><span data-stu-id="ff76f-102">Concatenate Two Sequences</span></span>
<span data-ttu-id="ff76f-103">使用 <xref:System.Linq.Queryable.Concat%2A> 运算符可串联两个序列。</span><span class="sxs-lookup"><span data-stu-id="ff76f-103">Use the <xref:System.Linq.Queryable.Concat%2A> operator to concatenate two sequences.</span></span>  
  
 <span data-ttu-id="ff76f-104"><xref:System.Linq.Queryable.Concat%2A> 运算符是为有序多重集定义的，其中接收方的顺序与参数的顺序相同。</span><span class="sxs-lookup"><span data-stu-id="ff76f-104">The <xref:System.Linq.Queryable.Concat%2A> operator is defined for ordered multisets where the orders of the receiver and the argument are the same.</span></span>  
  
 <span data-ttu-id="ff76f-105">在 SQL 中排序是产生结果前的最后一步。</span><span class="sxs-lookup"><span data-stu-id="ff76f-105">Ordering in SQL is the final step before results are produced.</span></span> <span data-ttu-id="ff76f-106">因此，<xref:System.Linq.Queryable.Concat%2A> 运算符是通过使用 `UNION ALL` 实现的，并且不保留其自变量的顺序。</span><span class="sxs-lookup"><span data-stu-id="ff76f-106">For this reason, the <xref:System.Linq.Queryable.Concat%2A> operator is implemented by using `UNION ALL` and does not preserve the order of its arguments.</span></span> <span data-ttu-id="ff76f-107">为确保结果中的顺序正确，一定要显式地对结果进行排序。</span><span class="sxs-lookup"><span data-stu-id="ff76f-107">To make sure ordering is correct in the results, make sure to explicitly order the results.</span></span>  
  
## <a name="example"></a><span data-ttu-id="ff76f-108">示例</span><span class="sxs-lookup"><span data-stu-id="ff76f-108">Example</span></span>  
 <span data-ttu-id="ff76f-109">此示例使用 <xref:System.Linq.Queryable.Concat%2A> 返回由所有 `Customer` 和 `Employee` 的电话和传真号码组成的序列。</span><span class="sxs-lookup"><span data-stu-id="ff76f-109">This example uses <xref:System.Linq.Queryable.Concat%2A> to return a sequence of all `Customer` and `Employee` telephone and fax numbers.</span></span>  
  
 [!code-csharp[DLinqQueryExamples#39](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#39)]
 [!code-vb[DLinqQueryExamples#39](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#39)]  
  
## <a name="example"></a><span data-ttu-id="ff76f-110">示例</span><span class="sxs-lookup"><span data-stu-id="ff76f-110">Example</span></span>  
 <span data-ttu-id="ff76f-111">此示例使用 <xref:System.Linq.Queryable.Concat%2A> 返回由所有 `Customer` 和 `Employee` 的名字和电话号码映射组成的序列。</span><span class="sxs-lookup"><span data-stu-id="ff76f-111">This example uses <xref:System.Linq.Queryable.Concat%2A> to return a sequence of all `Customer` and `Employee` name and telephone number mappings.</span></span>  
  
 [!code-csharp[DLinqQueryExamples#40](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#40)]
 [!code-vb[DLinqQueryExamples#40](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#40)]  
  
## <a name="see-also"></a><span data-ttu-id="ff76f-112">请参阅</span><span class="sxs-lookup"><span data-stu-id="ff76f-112">See also</span></span>

- [<span data-ttu-id="ff76f-113">查询示例</span><span class="sxs-lookup"><span data-stu-id="ff76f-113">Query Examples</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/query-examples.md)
- [<span data-ttu-id="ff76f-114">标准查询运算符转换</span><span class="sxs-lookup"><span data-stu-id="ff76f-114">Standard Query Operator Translation</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/standard-query-operator-translation.md)
