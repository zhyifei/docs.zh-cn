---
title: 查询表达式语法示例：排序
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: bcbc9625-7cf7-476e-85d2-058f12682f54
ms.openlocfilehash: ea9e7cb61facb880a050fbfae3aa9b07c03361fc
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "61614166"
---
# <a name="query-expression-syntax-examples-ordering"></a><span data-ttu-id="caea9-102">查询表达式语法示例：排序</span><span class="sxs-lookup"><span data-stu-id="caea9-102">Query Expression Syntax Examples: Ordering</span></span>
<span data-ttu-id="caea9-103">本主题中的示例演示如何使用`OrderBy`并`OrderByDescending`方法来查询[AdventureWorks 销售模型](https://archive.codeplex.com/?p=msftdbprodsamples)使用查询表达式语法。</span><span class="sxs-lookup"><span data-stu-id="caea9-103">The examples in this topic demonstrate how to use the `OrderBy` and `OrderByDescending` methods to query the [AdventureWorks Sales Model](https://archive.codeplex.com/?p=msftdbprodsamples) using query expression syntax.</span></span> <span data-ttu-id="caea9-104">这些示例中使用的 AdventureWorks 销售模型从 AdventureWorks 示例数据库中的 Contact、Address、Product、SalesOrderHeader 和 SalesOrderDetail 等表生成。</span><span class="sxs-lookup"><span data-stu-id="caea9-104">The AdventureWorks Sales Model used in these examples is built from the Contact, Address, Product, SalesOrderHeader, and SalesOrderDetail tables in the AdventureWorks sample database.</span></span>  
  
 <span data-ttu-id="caea9-105">本主题中的示例使用以下`using` / `Imports`语句：</span><span class="sxs-lookup"><span data-stu-id="caea9-105">The examples in this topic use the following `using`/`Imports` statements:</span></span>  
  
 [!code-csharp[DP L2E Examples#ImportsUsing](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#importsusing)]
 [!code-vb[DP L2E Examples#ImportsUsing](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#importsusing)]  
  
## <a name="orderby"></a><span data-ttu-id="caea9-106">OrderBy</span><span class="sxs-lookup"><span data-stu-id="caea9-106">OrderBy</span></span>  
  
### <a name="example"></a><span data-ttu-id="caea9-107">示例</span><span class="sxs-lookup"><span data-stu-id="caea9-107">Example</span></span>  
 <span data-ttu-id="caea9-108">以下示例使用 <xref:System.Linq.Enumerable.OrderBy%2A> 以返回按姓氏排序的联系人列表。</span><span class="sxs-lookup"><span data-stu-id="caea9-108">The following example uses <xref:System.Linq.Enumerable.OrderBy%2A> to return a list of contacts ordered by last name.</span></span>  
  
 [!code-csharp[DP L2E Examples#OrderBySimple1](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#orderbysimple1)]
 [!code-vb[DP L2E Examples#OrderBySimple1](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#orderbysimple1)]  
  
### <a name="example"></a><span data-ttu-id="caea9-109">示例</span><span class="sxs-lookup"><span data-stu-id="caea9-109">Example</span></span>  
 <span data-ttu-id="caea9-110">以下示例使用 <xref:System.Linq.Enumerable.OrderBy%2A> 以按姓氏的长度对联系人列表排序。</span><span class="sxs-lookup"><span data-stu-id="caea9-110">The following example uses <xref:System.Linq.Enumerable.OrderBy%2A> to sort a list of contacts by length of last name.</span></span>  
  
 [!code-csharp[DP L2E Examples#OrderBySimple2](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#orderbysimple2)]
 [!code-vb[DP L2E Examples#OrderBySimple2](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#orderbysimple2)]  
  
## <a name="orderbydescending"></a><span data-ttu-id="caea9-111">OrderByDescending</span><span class="sxs-lookup"><span data-stu-id="caea9-111">OrderByDescending</span></span>  
  
### <a name="example"></a><span data-ttu-id="caea9-112">示例</span><span class="sxs-lookup"><span data-stu-id="caea9-112">Example</span></span>  
 <span data-ttu-id="caea9-113">以下示例使用 `orderby… descending`（等效于 `Order By … Descending` 方法，但在 Visual Basic 中为 <xref:System.Linq.Enumerable.OrderByDescending%2A>），以按照从高到低的顺序对价目表排序。</span><span class="sxs-lookup"><span data-stu-id="caea9-113">The following example uses `orderby… descending` (`Order By … Descending` in Visual Basic), which is equivalent to the <xref:System.Linq.Enumerable.OrderByDescending%2A> method, to sort the price list from highest to lowest.</span></span>  
  
 [!code-csharp[DP L2E Examples#OrderByDescendingSimple1](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#orderbydescendingsimple1)]
 [!code-vb[DP L2E Examples#OrderByDescendingSimple1](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#orderbydescendingsimple1)]  
  
## <a name="thenby"></a><span data-ttu-id="caea9-114">ThenBy</span><span class="sxs-lookup"><span data-stu-id="caea9-114">ThenBy</span></span>  
  
### <a name="example"></a><span data-ttu-id="caea9-115">示例</span><span class="sxs-lookup"><span data-stu-id="caea9-115">Example</span></span>  
 <span data-ttu-id="caea9-116">以下示例使用 <xref:System.Linq.Queryable.OrderBy%2A> 和 <xref:System.Linq.Queryable.ThenBy%2A> 以返回先按姓氏后按名字排序的联系人列表。</span><span class="sxs-lookup"><span data-stu-id="caea9-116">The following example uses <xref:System.Linq.Queryable.OrderBy%2A> and <xref:System.Linq.Queryable.ThenBy%2A> to return a list of contacts ordered by last name and then by first name.</span></span>  
  
 [!code-csharp[DP L2E Examples#OrderByThenBy](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#orderbythenby)]
 [!code-vb[DP L2E Examples#OrderByThenBy](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#orderbythenby)]  
  
## <a name="thenbydescending"></a><span data-ttu-id="caea9-117">ThenByDescending</span><span class="sxs-lookup"><span data-stu-id="caea9-117">ThenByDescending</span></span>  
  
### <a name="example"></a><span data-ttu-id="caea9-118">示例</span><span class="sxs-lookup"><span data-stu-id="caea9-118">Example</span></span>  
 <span data-ttu-id="caea9-119">以下示例使用 `OrderBy… Descending`（等效于 <xref:System.Linq.Enumerable.ThenByDescending%2A> 方法），以先按名称后按标价（从高到低）对产品列表排序。</span><span class="sxs-lookup"><span data-stu-id="caea9-119">The following example uses `OrderBy… Descending`, which is equivalent to the <xref:System.Linq.Enumerable.ThenByDescending%2A> method, to sort a list of products, first by name and then by list price from highest to lowest.</span></span>  
  
 [!code-csharp[DP L2E Examples#ThenByDescendingSimple](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#thenbydescendingsimple)]
 [!code-vb[DP L2E Examples#ThenByDescendingSimple](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#thenbydescendingsimple)]  
  
## <a name="see-also"></a><span data-ttu-id="caea9-120">请参阅</span><span class="sxs-lookup"><span data-stu-id="caea9-120">See also</span></span>

- [<span data-ttu-id="caea9-121">LINQ to Entities 中的查询</span><span class="sxs-lookup"><span data-stu-id="caea9-121">Queries in LINQ to Entities</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/queries-in-linq-to-entities.md)
