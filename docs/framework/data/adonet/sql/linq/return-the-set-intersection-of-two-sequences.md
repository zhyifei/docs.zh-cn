---
title: 返回两个序列的交集
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: d09c344e-3548-4944-a3ed-051880e3f5b8
ms.openlocfilehash: 07f48ab7ef1095ba80b1a955a4bd1ea602a75aa8
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "62033418"
---
# <a name="return-the-set-intersection-of-two-sequences"></a><span data-ttu-id="3bc93-102">返回两个序列的交集</span><span class="sxs-lookup"><span data-stu-id="3bc93-102">Return the Set Intersection of Two Sequences</span></span>
<span data-ttu-id="3bc93-103">使用 <xref:System.Linq.Queryable.Intersect%2A> 运算符可返回两个序列的交集。</span><span class="sxs-lookup"><span data-stu-id="3bc93-103">Use the <xref:System.Linq.Queryable.Intersect%2A> operator to return the set intersection of two sequences.</span></span>  
  
## <a name="example"></a><span data-ttu-id="3bc93-104">示例</span><span class="sxs-lookup"><span data-stu-id="3bc93-104">Example</span></span>  
 <span data-ttu-id="3bc93-105">此示例使用 <xref:System.Linq.Queryable.Intersect%2A> 返回既有 `Customers` 居住又有 `Employees` 居住的所有国家/地区的序列。</span><span class="sxs-lookup"><span data-stu-id="3bc93-105">This example uses <xref:System.Linq.Queryable.Intersect%2A> to return a sequence of all countries in which both `Customers` and `Employees` live.</span></span>  
  
 [!code-csharp[DLinqQueryExamples#42](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#42)]
 [!code-vb[DLinqQueryExamples#42](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#42)]  
  
 <span data-ttu-id="3bc93-106">在 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] 中，<xref:System.Linq.Queryable.Intersect%2A> 运算仅对集合而言是定义完善的。</span><span class="sxs-lookup"><span data-stu-id="3bc93-106">In [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)], the <xref:System.Linq.Queryable.Intersect%2A> operation is well defined only on sets.</span></span> <span data-ttu-id="3bc93-107">针对多重集的语义尚未定义。</span><span class="sxs-lookup"><span data-stu-id="3bc93-107">The semantics for multisets is undefined.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3bc93-108">请参阅</span><span class="sxs-lookup"><span data-stu-id="3bc93-108">See also</span></span>

- [<span data-ttu-id="3bc93-109">查询示例</span><span class="sxs-lookup"><span data-stu-id="3bc93-109">Query Examples</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/query-examples.md)
- [<span data-ttu-id="3bc93-110">标准查询运算符转换</span><span class="sxs-lookup"><span data-stu-id="3bc93-110">Standard Query Operator Translation</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/standard-query-operator-translation.md)
