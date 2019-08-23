---
title: 返回或跳过序列中的元素
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 81a31acd-e0f1-4bca-9a12-fa1ad5752374
ms.openlocfilehash: 75cb5ea166c36de5c0921fbbd830021719497cda
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2019
ms.locfileid: "69963862"
---
# <a name="return-or-skip-elements-in-a-sequence"></a><span data-ttu-id="d2ed6-102">返回或跳过序列中的元素</span><span class="sxs-lookup"><span data-stu-id="d2ed6-102">Return Or Skip Elements in a Sequence</span></span>
<span data-ttu-id="d2ed6-103">使用 <xref:System.Linq.Queryable.Take%2A> 运算符可返回序列中给定数目的元素，然后跳过其余元素。</span><span class="sxs-lookup"><span data-stu-id="d2ed6-103">Use the <xref:System.Linq.Queryable.Take%2A> operator to return a given number of elements in a sequence and then skip over the remainder.</span></span>  
  
 <span data-ttu-id="d2ed6-104">使用 <xref:System.Linq.Queryable.Skip%2A> 运算符可跳过序列中给定数目的元素，然后返回其余元素。</span><span class="sxs-lookup"><span data-stu-id="d2ed6-104">Use the <xref:System.Linq.Queryable.Skip%2A> operator to skip over a given number of elements in a sequence and then return the remainder.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="d2ed6-105"><xref:System.Linq.Enumerable.Take%2A> 和 <xref:System.Linq.Enumerable.Skip%2A> 用在针对 SQL Server 2000 的查询中时存在一定的限制。</span><span class="sxs-lookup"><span data-stu-id="d2ed6-105"><xref:System.Linq.Enumerable.Take%2A> and <xref:System.Linq.Enumerable.Skip%2A> have certain limitations when they are used in queries against SQL Server 2000.</span></span> <span data-ttu-id="d2ed6-106">有关详细信息, 请参阅[疑难解答](../../../../../../docs/framework/data/adonet/sql/linq/troubleshooting.md)中的 "跳过并使用 SQL Server 2000" 条目。</span><span class="sxs-lookup"><span data-stu-id="d2ed6-106">For more information, see the "Skip and Take Exceptions in SQL Server 2000" entry in [Troubleshooting](../../../../../../docs/framework/data/adonet/sql/linq/troubleshooting.md).</span></span>  
  
 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] <span data-ttu-id="d2ed6-107">通过使用带有 SQL <xref:System.Linq.Queryable.Skip%2A> 子句的子查询来转换 `NOT EXISTS`。</span><span class="sxs-lookup"><span data-stu-id="d2ed6-107">translates <xref:System.Linq.Queryable.Skip%2A> by using a subquery with the SQL `NOT EXISTS` clause.</span></span> <span data-ttu-id="d2ed6-108">这种转换存在以下局限性：</span><span class="sxs-lookup"><span data-stu-id="d2ed6-108">This translation has the following limitations:</span></span>  
  
- <span data-ttu-id="d2ed6-109">自变量必须为集合。</span><span class="sxs-lookup"><span data-stu-id="d2ed6-109">The argument must be a set.</span></span> <span data-ttu-id="d2ed6-110">不支持多重集，即便为有序多重集也不例外。</span><span class="sxs-lookup"><span data-stu-id="d2ed6-110">Multisets are not supported, even if ordered.</span></span>  
  
- <span data-ttu-id="d2ed6-111">生成的查询可能要比为应用了 <xref:System.Linq.Queryable.Skip%2A> 的基查询生成的查询复杂得多。</span><span class="sxs-lookup"><span data-stu-id="d2ed6-111">The generated query can be much more complex than the query generated for the base query on which <xref:System.Linq.Queryable.Skip%2A> is applied.</span></span> <span data-ttu-id="d2ed6-112">这种复杂性可能会导致性能降低，甚至发生超时。</span><span class="sxs-lookup"><span data-stu-id="d2ed6-112">This complexity can cause decrease in performance or even a time-out.</span></span>  
  
## <a name="example"></a><span data-ttu-id="d2ed6-113">示例</span><span class="sxs-lookup"><span data-stu-id="d2ed6-113">Example</span></span>  
 <span data-ttu-id="d2ed6-114">下面的示例使用 `Take` 选择前五个受雇的 `Employees`。</span><span class="sxs-lookup"><span data-stu-id="d2ed6-114">The following example uses `Take` to select the first five `Employees` hired.</span></span> <span data-ttu-id="d2ed6-115">请注意，此集合首先按 `HireDate` 排序。</span><span class="sxs-lookup"><span data-stu-id="d2ed6-115">Note that the collection is first sorted by `HireDate`.</span></span>  
  
 [!code-csharp[DLinqQueryExamples#16](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#16)]
 [!code-vb[DLinqQueryExamples#16](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#16)]  
  
## <a name="example"></a><span data-ttu-id="d2ed6-116">示例</span><span class="sxs-lookup"><span data-stu-id="d2ed6-116">Example</span></span>  
 <span data-ttu-id="d2ed6-117">下面的示例使用 <xref:System.Linq.Queryable.Skip%2A> 选择 10 种最贵的 `Products` 以外的所有产品。</span><span class="sxs-lookup"><span data-stu-id="d2ed6-117">The following example uses <xref:System.Linq.Queryable.Skip%2A> to select all except the 10 most expensive `Products`.</span></span>  
  
 [!code-csharp[DLinqQueryExamples#17](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#17)]
 [!code-vb[DLinqQueryExamples#17](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#17)]  
  
## <a name="example"></a><span data-ttu-id="d2ed6-118">示例</span><span class="sxs-lookup"><span data-stu-id="d2ed6-118">Example</span></span>  
 <span data-ttu-id="d2ed6-119">下面的示例结合使用 <xref:System.Linq.Queryable.Skip%2A> 和 <xref:System.Linq.Queryable.Take%2A> 方法来跳过前 50 条记录，然后返回下 10 条记录。</span><span class="sxs-lookup"><span data-stu-id="d2ed6-119">The following example combines the <xref:System.Linq.Queryable.Skip%2A> and <xref:System.Linq.Queryable.Take%2A> methods to skip the first 50 records and then return the next 10.</span></span>  
  
 [!code-csharp[DLinqQueryExamples#18](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#18)]
 [!code-vb[DLinqQueryExamples#18](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#18)]  
  
 <span data-ttu-id="d2ed6-120"><xref:System.Linq.Queryable.Take%2A> 和 <xref:System.Linq.Queryable.Skip%2A> 运算仅对有序集而言是定义完善的。</span><span class="sxs-lookup"><span data-stu-id="d2ed6-120"><xref:System.Linq.Queryable.Take%2A> and <xref:System.Linq.Queryable.Skip%2A> operations are well defined only against ordered sets.</span></span> <span data-ttu-id="d2ed6-121">未定义针对无序集或多重集的语义。</span><span class="sxs-lookup"><span data-stu-id="d2ed6-121">The semantics for unordered sets or multisets is undefined.</span></span>  
  
 <span data-ttu-id="d2ed6-122">由于 SQL 中的排序存在限制，因此 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] 会设法将 <xref:System.Linq.Queryable.Take%2A> 或 <xref:System.Linq.Queryable.Skip%2A> 运算符的参数的排序操作移到相应运算符的结果中进行。</span><span class="sxs-lookup"><span data-stu-id="d2ed6-122">Because of the limitations on ordering in SQL, [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] tries to move the ordering of the argument of the <xref:System.Linq.Queryable.Take%2A> or <xref:System.Linq.Queryable.Skip%2A> operator to the result of the operator.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="d2ed6-123">SQL Server 2000 和 SQL Server 2005 的转换不同。</span><span class="sxs-lookup"><span data-stu-id="d2ed6-123">Translation is different for SQL Server 2000 and SQL Server 2005.</span></span> <span data-ttu-id="d2ed6-124">如果你计划将与<xref:System.Linq.Queryable.Skip%2A>查询结合使用, 请使用 SQL Server 2005。</span><span class="sxs-lookup"><span data-stu-id="d2ed6-124">If you plan to use <xref:System.Linq.Queryable.Skip%2A> with a query of any complexity, use SQL Server 2005.</span></span>  
  
 <span data-ttu-id="d2ed6-125">对于 SQL Server 2000 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] , 请考虑以下查询:</span><span class="sxs-lookup"><span data-stu-id="d2ed6-125">Consider the following [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] query for SQL Server 2000:</span></span>  
  
 [!code-csharp[DLinqQueryExamples#19](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#19)]
 [!code-vb[DLinqQueryExamples#19](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#19)]  
  
 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] <span data-ttu-id="d2ed6-126">将排序操作移到 SQL 代码的结尾进行，如下所示：</span><span class="sxs-lookup"><span data-stu-id="d2ed6-126">moves the ordering to the end in the SQL code, as follows:</span></span>  
  
```  
SELECT TOP 1 [t0].[CustomerID], [t0].[CompanyName],  
FROM [Customers] AS [t0]  
WHERE (NOT (EXISTS(  
    SELECT NULL AS [EMPTY]  
    FROM (  
        SELECT TOP 1 [t1].[CustomerID]  
        FROM [Customers] AS [t1]  
        WHERE [t1].[City] = @p0  
        ORDER BY [t1].[CustomerID]  
        ) AS [t2]  
    WHERE [t0].[CustomerID] = [t2].[CustomerID]  
    ))) AND ([t0].[City] = @p1)  
ORDER BY [t0].[CustomerID]  
```  
  
 <span data-ttu-id="d2ed6-127">当 <xref:System.Linq.Queryable.Take%2A> 和 <xref:System.Linq.Queryable.Skip%2A> 链接在一起时，所有指定的排序都必须一致。</span><span class="sxs-lookup"><span data-stu-id="d2ed6-127">When <xref:System.Linq.Queryable.Take%2A> and <xref:System.Linq.Queryable.Skip%2A> are chained together, all the specified ordering must be consistent.</span></span> <span data-ttu-id="d2ed6-128">否则，结果将是不确定的。</span><span class="sxs-lookup"><span data-stu-id="d2ed6-128">Otherwise, the results are undefined.</span></span>  
  
 <span data-ttu-id="d2ed6-129">对于非负的、基于 SQL 规范的整型常量参数，<xref:System.Linq.Queryable.Take%2A> 和 <xref:System.Linq.Queryable.Skip%2A> 都是定义完善的。</span><span class="sxs-lookup"><span data-stu-id="d2ed6-129">For non-negative, constant integral arguments based on the SQL specification, both <xref:System.Linq.Queryable.Take%2A> and <xref:System.Linq.Queryable.Skip%2A> are well-defined.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d2ed6-130">请参阅</span><span class="sxs-lookup"><span data-stu-id="d2ed6-130">See also</span></span>

- [<span data-ttu-id="d2ed6-131">查询示例</span><span class="sxs-lookup"><span data-stu-id="d2ed6-131">Query Examples</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/query-examples.md)
- [<span data-ttu-id="d2ed6-132">标准查询运算符转换</span><span class="sxs-lookup"><span data-stu-id="d2ed6-132">Standard Query Operator Translation</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/standard-query-operator-translation.md)
