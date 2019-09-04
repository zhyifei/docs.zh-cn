---
title: 基于方法的查询语法示例：联接运算符
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: d00f0efa-9084-4c17-843f-54904fcb4204
ms.openlocfilehash: 2f26f937901debd27cb936d1f642e0a5149b167a
ms.sourcegitcommit: 4e2d355baba82814fa53efd6b8bbb45bfe054d11
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/04/2019
ms.locfileid: "70250137"
---
# <a name="method-based-query-syntax-examples-join-operators"></a><span data-ttu-id="5a13b-102">基于方法的查询语法示例：联接运算符</span><span class="sxs-lookup"><span data-stu-id="5a13b-102">Method-Based Query Syntax Examples: Join Operators</span></span>
<span data-ttu-id="5a13b-103">本主题中的示例演示如何使用<xref:System.Linq.Enumerable.Join%2A>和<xref:System.Linq.Enumerable.GroupJoin%2A>方法通过基于方法的查询语法来查询[AdventureWorks 销售模型](https://archive.codeplex.com/?p=msftdbprodsamples)。</span><span class="sxs-lookup"><span data-stu-id="5a13b-103">The examples in this topic demonstrate how to use the <xref:System.Linq.Enumerable.Join%2A> and <xref:System.Linq.Enumerable.GroupJoin%2A> methods to query the [AdventureWorks Sales Model](https://archive.codeplex.com/?p=msftdbprodsamples) using method-based query syntax.</span></span> <span data-ttu-id="5a13b-104">这些示例中使用的 AdventureWorks 销售模型从 AdventureWorks 示例数据库中的 Contact、Address、Product、SalesOrderHeader 和 SalesOrderDetail 等表生成。</span><span class="sxs-lookup"><span data-stu-id="5a13b-104">The AdventureWorks Sales Model used in these examples is built from the Contact, Address, Product, SalesOrderHeader, and SalesOrderDetail tables in the AdventureWorks sample database.</span></span>  
  
 <span data-ttu-id="5a13b-105">本主题中的示例使用以下`using` / `Imports`语句：</span><span class="sxs-lookup"><span data-stu-id="5a13b-105">The examples in this topic use the following `using`/`Imports` statements:</span></span>  
  
 [!code-csharp[DP L2E Examples#ImportsUsing](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#importsusing)]
 [!code-vb[DP L2E Examples#ImportsUsing](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#importsusing)]  
  
## <a name="groupjoin"></a><span data-ttu-id="5a13b-106">GroupJoin</span><span class="sxs-lookup"><span data-stu-id="5a13b-106">GroupJoin</span></span>  
  
### <a name="example"></a><span data-ttu-id="5a13b-107">示例</span><span class="sxs-lookup"><span data-stu-id="5a13b-107">Example</span></span>  
 <span data-ttu-id="5a13b-108">以下示例针对 SalesOrderHeader 表和 SalesOrderDetail 表执行 <xref:System.Linq.Enumerable.GroupJoin%2A> 以查找每个客户的订单数。</span><span class="sxs-lookup"><span data-stu-id="5a13b-108">The following example performs a <xref:System.Linq.Enumerable.GroupJoin%2A> over the SalesOrderHeader and SalesOrderDetail tables to find the number of orders per customer.</span></span> <span data-ttu-id="5a13b-109">组联接等效于左外部联接，它返回第一个（左侧）数据源的每个元素（即使其他数据源中没有关联元素）。</span><span class="sxs-lookup"><span data-stu-id="5a13b-109">A group join is the equivalent of a left outer join, which returns each element of the first (left) data source, even if no correlated elements are in the other data source.</span></span>  
  
 [!code-csharp[DP L2E Examples#GroupJoin2_MQ](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#groupjoin2_mq)]
 [!code-vb[DP L2E Examples#GroupJoin2_MQ](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#groupjoin2_mq)]  
  
### <a name="example"></a><span data-ttu-id="5a13b-110">示例</span><span class="sxs-lookup"><span data-stu-id="5a13b-110">Example</span></span>  
 <span data-ttu-id="5a13b-111">下面的示例对 Contact 和 SalesOrderHeader 表执行 <xref:System.Linq.Enumerable.GroupJoin%2A> 以查找每个联系人的订单数。</span><span class="sxs-lookup"><span data-stu-id="5a13b-111">The following example performs a <xref:System.Linq.Enumerable.GroupJoin%2A> over the Contact and SalesOrderHeader tables to find the number of orders per contact.</span></span> <span data-ttu-id="5a13b-112">将显示每个联系人的订单数和 ID。</span><span class="sxs-lookup"><span data-stu-id="5a13b-112">The order count and IDs for each contact are displayed.</span></span>  
  
 [!code-csharp[DP L2E Examples#GroupJoin_MQ](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#groupjoin_mq)]
 [!code-vb[DP L2E Examples#GroupJoin_MQ](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#groupjoin_mq)]  
  
## <a name="join"></a><span data-ttu-id="5a13b-113">联接</span><span class="sxs-lookup"><span data-stu-id="5a13b-113">Join</span></span>  
  
### <a name="example"></a><span data-ttu-id="5a13b-114">示例</span><span class="sxs-lookup"><span data-stu-id="5a13b-114">Example</span></span>  
 <span data-ttu-id="5a13b-115">以下示例针对 Contact 表和 SalesOrderHeader 表执行联接。</span><span class="sxs-lookup"><span data-stu-id="5a13b-115">The following example performs a join over the Contact and SalesOrderHeader tables.</span></span>  
  
 [!code-csharp[DP L2E Examples#JoinSimple_MQ](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#joinsimple_mq)]
 [!code-vb[DP L2E Examples#JoinSimple_MQ](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#joinsimple_mq)]  
  
### <a name="example"></a><span data-ttu-id="5a13b-116">示例</span><span class="sxs-lookup"><span data-stu-id="5a13b-116">Example</span></span>  
 <span data-ttu-id="5a13b-117">以下示例针对 Contact 表和 SalesOrderHeader 表执行联接，同时按联系人 ID 对结果分组。</span><span class="sxs-lookup"><span data-stu-id="5a13b-117">The following example performs a join over the Contact and SalesOrderHeader tables, grouping the results by contact ID.</span></span>  
  
 [!code-csharp[DP L2E Examples#JoinWithGroupedResults_MQ](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#joinwithgroupedresults_mq)]
 [!code-vb[DP L2E Examples#JoinWithGroupedResults_MQ](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#joinwithgroupedresults_mq)]  
  
## <a name="see-also"></a><span data-ttu-id="5a13b-118">请参阅</span><span class="sxs-lookup"><span data-stu-id="5a13b-118">See also</span></span>

- [<span data-ttu-id="5a13b-119">LINQ to Entities 中的查询</span><span class="sxs-lookup"><span data-stu-id="5a13b-119">Queries in LINQ to Entities</span></span>](queries-in-linq-to-entities.md)
