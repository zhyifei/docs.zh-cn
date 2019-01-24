---
title: 基于方法的查询语法示例：分区 (LINQ
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: a582c53f-f203-44ae-a797-d7f169a4fbb5
ms.openlocfilehash: a18f19ead84d3b91b3ddd724360f3800abe286b8
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54524736"
---
# <a name="method-based-query-syntax-examples-partitioning-linq"></a><span data-ttu-id="33924-102">基于方法的查询语法示例：分区 (LINQ</span><span class="sxs-lookup"><span data-stu-id="33924-102">Method-Based Query Syntax Examples: Partitioning (LINQ</span></span>
<span data-ttu-id="33924-103">本主题中的示例演示如何使用 <xref:System.Linq.Enumerable.Skip%2A>、<xref:System.Linq.Enumerable.SkipWhile%2A>、<xref:System.Linq.Enumerable.Take%2A> 和 <xref:System.Linq.Enumerable.TakeWhile%2A> 方法以便使用查询表达式语法来查询 <xref:System.Data.DataSet>。</span><span class="sxs-lookup"><span data-stu-id="33924-103">The examples in this topic demonstrate how to use the <xref:System.Linq.Enumerable.Skip%2A>, <xref:System.Linq.Enumerable.SkipWhile%2A>, <xref:System.Linq.Enumerable.Take%2A>, and <xref:System.Linq.Enumerable.TakeWhile%2A> methods to query a <xref:System.Data.DataSet> using the query expression syntax.</span></span>  
  
 <span data-ttu-id="33924-104">`FillDataSet`中指定这些示例中使用的方法[加载数据到数据集](../../../../docs/framework/data/adonet/loading-data-into-a-dataset.md)。</span><span class="sxs-lookup"><span data-stu-id="33924-104">The `FillDataSet` method used in these examples is specified in [Loading Data Into a DataSet](../../../../docs/framework/data/adonet/loading-data-into-a-dataset.md).</span></span>  
  
 <span data-ttu-id="33924-105">本主题中的示例使用 AdventureWorks 示例数据库中的 Contact、Address、Product、SalesOrderHeader 和 SalesOrderDetail 表。</span><span class="sxs-lookup"><span data-stu-id="33924-105">The examples in this topic use the Contact, Address, Product, SalesOrderHeader, and SalesOrderDetail tables in the AdventureWorks sample database.</span></span>  
  
 <span data-ttu-id="33924-106">本主题中的示例使用以下`using` / `Imports`语句：</span><span class="sxs-lookup"><span data-stu-id="33924-106">The examples in this topic use the following `using`/`Imports` statements:</span></span>  
  
 [!code-csharp[DP LINQ to DataSet Examples#ImportsUsing](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#importsusing)]
 [!code-vb[DP LINQ to DataSet Examples#ImportsUsing](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#importsusing)]  
  
 <span data-ttu-id="33924-107">有关详细信息，请参阅[如何：在 Visual Studio 中创建 LINQ to DataSet 项目](../../../../docs/framework/data/adonet/how-to-create-a-linq-to-dataset-project-in-vs.md)。</span><span class="sxs-lookup"><span data-stu-id="33924-107">For more information, see [How to: Create a LINQ to DataSet Project In Visual Studio](../../../../docs/framework/data/adonet/how-to-create-a-linq-to-dataset-project-in-vs.md).</span></span>  
  
## <a name="skip"></a><span data-ttu-id="33924-108">Skip</span><span class="sxs-lookup"><span data-stu-id="33924-108">Skip</span></span>  
  
### <a name="example"></a><span data-ttu-id="33924-109">示例</span><span class="sxs-lookup"><span data-stu-id="33924-109">Example</span></span>  
 <span data-ttu-id="33924-110">此示例使用 <xref:System.Linq.Enumerable.Skip%2A> 方法获取 `Contact` 表中除前五个联系人以外的所有联系人。</span><span class="sxs-lookup"><span data-stu-id="33924-110">This example uses the <xref:System.Linq.Enumerable.Skip%2A> method to get all but the first five contacts of the `Contact` table.</span></span>  
  
 [!code-csharp[DP LINQ to DataSet Examples#SkipSimple](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#skipsimple)]
 [!code-vb[DP LINQ to DataSet Examples#SkipSimple](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#skipsimple)]  
  
### <a name="example"></a><span data-ttu-id="33924-111">示例</span><span class="sxs-lookup"><span data-stu-id="33924-111">Example</span></span>  
 <span data-ttu-id="33924-112">此示例使用 <xref:System.Linq.Enumerable.Skip%2A> 方法获取 Seattle 中除前两个地址以外的所有地址。</span><span class="sxs-lookup"><span data-stu-id="33924-112">This example uses the <xref:System.Linq.Enumerable.Skip%2A> method to get all but the first two addresses in Seattle.</span></span>  
  
 [!code-csharp[DP LINQ to DataSet Examples#SkipNested](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#skipnested)]
 [!code-vb[DP LINQ to DataSet Examples#SkipNested](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#skipnested)]  
  
## <a name="skipwhile"></a><span data-ttu-id="33924-113">SkipWhile</span><span class="sxs-lookup"><span data-stu-id="33924-113">SkipWhile</span></span>  
  
### <a name="example"></a><span data-ttu-id="33924-114">示例</span><span class="sxs-lookup"><span data-stu-id="33924-114">Example</span></span>  
 <span data-ttu-id="33924-115">此示例使用 <xref:System.Linq.Enumerable.OrderBy%2A> 和 <xref:System.Linq.Enumerable.SkipWhile%2A> 方法返回 `Product` 表中定价大于 300.00 的产品。</span><span class="sxs-lookup"><span data-stu-id="33924-115">This example uses <xref:System.Linq.Enumerable.OrderBy%2A> and <xref:System.Linq.Enumerable.SkipWhile%2A> methods to return products from the `Product` table with a list price greater than 300.00.</span></span>  
  
 [!code-csharp[DP LINQ to DataSet Examples#SkipWhileSimple_MQ](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#skipwhilesimple_mq)]
 [!code-vb[DP LINQ to DataSet Examples#SkipWhileSimple_MQ](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#skipwhilesimple_mq)]  
  
## <a name="take"></a><span data-ttu-id="33924-116">Take</span><span class="sxs-lookup"><span data-stu-id="33924-116">Take</span></span>  
  
### <a name="example"></a><span data-ttu-id="33924-117">示例</span><span class="sxs-lookup"><span data-stu-id="33924-117">Example</span></span>  
 <span data-ttu-id="33924-118">此示例使用 <xref:System.Linq.Enumerable.Take%2A> 方法只获取 `Contact` 表中的前五个联系人。</span><span class="sxs-lookup"><span data-stu-id="33924-118">This example uses the <xref:System.Linq.Enumerable.Take%2A> method to get only the first five contacts from the `Contact` table.</span></span>  
  
 [!code-csharp[DP LINQ to DataSet Examples#TakeSimple](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#takesimple)]
 [!code-vb[DP LINQ to DataSet Examples#TakeSimple](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#takesimple)]  
  
### <a name="example"></a><span data-ttu-id="33924-119">示例</span><span class="sxs-lookup"><span data-stu-id="33924-119">Example</span></span>  
 <span data-ttu-id="33924-120">此示例使用 <xref:System.Linq.Enumerable.Take%2A> 方法获取 Seattle 中的前三个地址。</span><span class="sxs-lookup"><span data-stu-id="33924-120">This example uses the <xref:System.Linq.Enumerable.Take%2A> method to get the first three addresses in Seattle.</span></span>  
  
 [!code-csharp[DP LINQ to DataSet Examples#TakeNested](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#takenested)]
 [!code-vb[DP LINQ to DataSet Examples#TakeNested](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#takenested)]  
  
## <a name="takewhile"></a><span data-ttu-id="33924-121">TakeWhile</span><span class="sxs-lookup"><span data-stu-id="33924-121">TakeWhile</span></span>  
  
### <a name="example"></a><span data-ttu-id="33924-122">示例</span><span class="sxs-lookup"><span data-stu-id="33924-122">Example</span></span>  
 <span data-ttu-id="33924-123">此示例使用 <xref:System.Linq.Enumerable.OrderBy%2A> 和 <xref:System.Linq.Enumerable.TakeWhile%2A> 返回 `Product` 表中定价小于 300.00 的产品。</span><span class="sxs-lookup"><span data-stu-id="33924-123">This example uses <xref:System.Linq.Enumerable.OrderBy%2A> and <xref:System.Linq.Enumerable.TakeWhile%2A> to return products from the `Product` table with a list price less than 300.00.</span></span>  
  
 [!code-csharp[DP LINQ to DataSet Examples#TakeWhileSimple_MQ](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#takewhilesimple_mq)]
 [!code-vb[DP LINQ to DataSet Examples#TakeWhileSimple_MQ](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#takewhilesimple_mq)]  
  
## <a name="see-also"></a><span data-ttu-id="33924-124">请参阅</span><span class="sxs-lookup"><span data-stu-id="33924-124">See also</span></span>
- [<span data-ttu-id="33924-125">将数据加载到数据集中</span><span class="sxs-lookup"><span data-stu-id="33924-125">Loading Data Into a DataSet</span></span>](../../../../docs/framework/data/adonet/loading-data-into-a-dataset.md)
- [<span data-ttu-id="33924-126">LINQ to DataSet 示例</span><span class="sxs-lookup"><span data-stu-id="33924-126">LINQ to DataSet Examples</span></span>](../../../../docs/framework/data/adonet/linq-to-dataset-examples.md)
- [<span data-ttu-id="33924-127">标准查询运算符概述</span><span class="sxs-lookup"><span data-stu-id="33924-127">Standard Query Operators Overview</span></span>](https://msdn.microsoft.com/library/24cda21e-8af8-4632-b519-c404a839b9b2)
