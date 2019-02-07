---
title: 基于方法的查询语法示例：排序
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 5d21b178-d731-471a-8534-1f8184a2ef06
ms.openlocfilehash: 73ea7a11353c83995bee6457c1fed12cd9c936d2
ms.sourcegitcommit: 3500c4845f96a91a438a02ef2c6b4eef45a5e2af
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/07/2019
ms.locfileid: "55828054"
---
# <a name="method-based-query-syntax-examples-ordering"></a><span data-ttu-id="6e91d-102">基于方法的查询语法示例：排序</span><span class="sxs-lookup"><span data-stu-id="6e91d-102">Method-Based Query Syntax Examples: Ordering</span></span>
<span data-ttu-id="6e91d-103">本主题中的示例演示如何使用<xref:System.Linq.Enumerable.ThenBy%2A>方法来查询[AdventureWorks 销售模型](https://archive.codeplex.com/?p=msftdbprodsamples)使用基于方法的查询语法。</span><span class="sxs-lookup"><span data-stu-id="6e91d-103">The examples in this topic demonstrate how to use the <xref:System.Linq.Enumerable.ThenBy%2A> method to query the [AdventureWorks Sales Model](https://archive.codeplex.com/?p=msftdbprodsamples) using method-based query syntax.</span></span> <span data-ttu-id="6e91d-104">这些示例中使用的 AdventureWorks 销售模型从 AdventureWorks 示例数据库中的 Contact、Address、Product、SalesOrderHeader 和 SalesOrderDetail 等表生成。</span><span class="sxs-lookup"><span data-stu-id="6e91d-104">The AdventureWorks Sales Model used in these examples is built from the Contact, Address, Product, SalesOrderHeader, and SalesOrderDetail tables in the AdventureWorks sample database.</span></span>  
  
 <span data-ttu-id="6e91d-105">本主题中的示例使用以下`using` / `Imports`语句：</span><span class="sxs-lookup"><span data-stu-id="6e91d-105">The examples in this topic use the following `using`/`Imports` statements:</span></span>  
  
 [!code-csharp[DP L2E Examples#ImportsUsing](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#importsusing)]
 [!code-vb[DP L2E Examples#ImportsUsing](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#importsusing)]  
  
## <a name="thenby"></a><span data-ttu-id="6e91d-106">ThenBy</span><span class="sxs-lookup"><span data-stu-id="6e91d-106">ThenBy</span></span>  
  
### <a name="example"></a><span data-ttu-id="6e91d-107">示例</span><span class="sxs-lookup"><span data-stu-id="6e91d-107">Example</span></span>  
 <span data-ttu-id="6e91d-108">采用基于方法的查询语法的以下示例使用 <xref:System.Linq.Queryable.OrderBy%2A> 和 <xref:System.Linq.Queryable.ThenBy%2A> 以返回先按姓氏后按名字排序的联系人列表。</span><span class="sxs-lookup"><span data-stu-id="6e91d-108">The following example in method-based query syntax uses <xref:System.Linq.Queryable.OrderBy%2A> and <xref:System.Linq.Queryable.ThenBy%2A> to return a list of contacts ordered by last name and then by first name.</span></span>  
  
 [!code-csharp[DP L2E Examples#OrderByThenBy_MQ](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#orderbythenby_mq)]
 [!code-vb[DP L2E Examples#OrderByThenBy_MQ](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#orderbythenby_mq)]  
  
## <a name="thenbydescending"></a><span data-ttu-id="6e91d-109">ThenByDescending</span><span class="sxs-lookup"><span data-stu-id="6e91d-109">ThenByDescending</span></span>  
  
### <a name="example"></a><span data-ttu-id="6e91d-110">示例</span><span class="sxs-lookup"><span data-stu-id="6e91d-110">Example</span></span>  
 <span data-ttu-id="6e91d-111">以下示例使用 <xref:System.Linq.Queryable.OrderBy%2A> 和 <xref:System.Linq.Queryable.ThenByDescending%2A> 方法以首先按标价排序，然后执行产品名称的降序排序。</span><span class="sxs-lookup"><span data-stu-id="6e91d-111">The following example uses the <xref:System.Linq.Queryable.OrderBy%2A> and <xref:System.Linq.Queryable.ThenByDescending%2A> methods to first sort by list price, and then perform a descending sort of the product names.</span></span>  
  
 [!code-csharp[DP L2E Examples#ThenByDescending_MQ](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#thenbydescending_mq)]
 [!code-vb[DP L2E Examples#ThenByDescending_MQ](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#thenbydescending_mq)]  
  
## <a name="see-also"></a><span data-ttu-id="6e91d-112">请参阅</span><span class="sxs-lookup"><span data-stu-id="6e91d-112">See also</span></span>
- [<span data-ttu-id="6e91d-113">LINQ to Entities 中的查询</span><span class="sxs-lookup"><span data-stu-id="6e91d-113">Queries in LINQ to Entities</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/queries-in-linq-to-entities.md)
