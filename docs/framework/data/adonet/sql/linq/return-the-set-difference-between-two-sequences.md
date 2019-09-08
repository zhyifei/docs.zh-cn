---
title: 返回两个序列之间的差集
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 62efb546-c898-408f-af21-36e7c6fed217
ms.openlocfilehash: 92513ed33e2afb785edbdd462ba7bc14923aa6b0
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/07/2019
ms.locfileid: "70781146"
---
# <a name="return-the-set-difference-between-two-sequences"></a><span data-ttu-id="39411-102">返回两个序列之间的差集</span><span class="sxs-lookup"><span data-stu-id="39411-102">Return the Set Difference Between Two Sequences</span></span>
<span data-ttu-id="39411-103">使用 <xref:System.Linq.Queryable.Except%2A> 运算符可返回两个序列之间的差集。</span><span class="sxs-lookup"><span data-stu-id="39411-103">Use the <xref:System.Linq.Queryable.Except%2A> operator to return the set difference between two sequences.</span></span>  
  
## <a name="example"></a><span data-ttu-id="39411-104">示例</span><span class="sxs-lookup"><span data-stu-id="39411-104">Example</span></span>  
 <span data-ttu-id="39411-105">此示例使用<xref:System.Linq.Queryable.Except%2A>返回`Customers`居住但不`Employees`居住的所有国家/地区的序列。</span><span class="sxs-lookup"><span data-stu-id="39411-105">This example uses <xref:System.Linq.Queryable.Except%2A> to return a sequence of all countries/regions in which `Customers` live but in which no `Employees` live.</span></span>  
  
 [!code-csharp[DLinqQueryExamples#41](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#41)]
 [!code-vb[DLinqQueryExamples#41](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#41)]  
  
 <span data-ttu-id="39411-106">在 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] 中，<xref:System.Linq.Queryable.Except%2A> 运算仅对集合而言是定义完善的。</span><span class="sxs-lookup"><span data-stu-id="39411-106">In [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)], the <xref:System.Linq.Queryable.Except%2A> operation is well defined only on sets.</span></span> <span data-ttu-id="39411-107">针对多重集的语义尚未定义。</span><span class="sxs-lookup"><span data-stu-id="39411-107">The semantics for multisets is undefined.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="39411-108">请参阅</span><span class="sxs-lookup"><span data-stu-id="39411-108">See also</span></span>

- [<span data-ttu-id="39411-109">查询示例</span><span class="sxs-lookup"><span data-stu-id="39411-109">Query Examples</span></span>](query-examples.md)
- [<span data-ttu-id="39411-110">标准查询运算符转换</span><span class="sxs-lookup"><span data-stu-id="39411-110">Standard Query Operator Translation</span></span>](standard-query-operator-translation.md)
