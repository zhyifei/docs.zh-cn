---
title: 查询表达式语法示例：聚合运算符
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: d729120c-4c1b-4f34-bbe9-33694fca2dde
ms.openlocfilehash: 120dec2511d9a17422c3db83bb0981b74f9eebdd
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54616103"
---
# <a name="query-expression-syntax-examples-aggregate-operators"></a><span data-ttu-id="a13ce-102">查询表达式语法示例：聚合运算符</span><span class="sxs-lookup"><span data-stu-id="a13ce-102">Query Expression Syntax Examples: Aggregate Operators</span></span>
<span data-ttu-id="a13ce-103">本主题中的示例演示如何使用<xref:System.Linq.Enumerable.Average%2A>， <xref:System.Linq.Enumerable.Count%2A>， <xref:System.Linq.Enumerable.Max%2A>， <xref:System.Linq.Enumerable.Min%2A>，并<xref:System.Linq.Enumerable.Sum%2A>方法来查询[AdventureWorks 销售模型](https://msdn.microsoft.com/library/f16cd988-673f-4376-b034-129ca93c7832)使用查询表达式语法。</span><span class="sxs-lookup"><span data-stu-id="a13ce-103">The examples in this topic demonstrate how to use the <xref:System.Linq.Enumerable.Average%2A>, <xref:System.Linq.Enumerable.Count%2A>, <xref:System.Linq.Enumerable.Max%2A>, <xref:System.Linq.Enumerable.Min%2A>, and <xref:System.Linq.Enumerable.Sum%2A> methods to query the [AdventureWorks Sales Model](https://msdn.microsoft.com/library/f16cd988-673f-4376-b034-129ca93c7832) using query expression syntax.</span></span> <span data-ttu-id="a13ce-104">这些示例中使用的 AdventureWorks 销售模型从 AdventureWorks 示例数据库中的 Contact、Address、Product、SalesOrderHeader 和 SalesOrderDetail 等表生成。</span><span class="sxs-lookup"><span data-stu-id="a13ce-104">The AdventureWorks Sales Model used in these examples is built from the Contact, Address, Product, SalesOrderHeader, and SalesOrderDetail tables in the AdventureWorks sample database.</span></span>  
  
 <span data-ttu-id="a13ce-105">本主题中的示例使用以下`using` / `Imports`语句：</span><span class="sxs-lookup"><span data-stu-id="a13ce-105">The examples in this topic use the following `using`/`Imports` statements:</span></span>  
  
 [!code-csharp[DP L2E Examples#ImportsUsing](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#importsusing)]
 [!code-vb[DP L2E Examples#ImportsUsing](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#importsusing)]  
  
## <a name="average"></a><span data-ttu-id="a13ce-106">平均值</span><span class="sxs-lookup"><span data-stu-id="a13ce-106">Average</span></span>  
  
### <a name="example"></a><span data-ttu-id="a13ce-107">示例</span><span class="sxs-lookup"><span data-stu-id="a13ce-107">Example</span></span>  
 <span data-ttu-id="a13ce-108">以下示例使用 <xref:System.Linq.Enumerable.Average%2A> 方法以查找每种样式的产品的平均标价。</span><span class="sxs-lookup"><span data-stu-id="a13ce-108">The following example uses the <xref:System.Linq.Enumerable.Average%2A> method to find the average list price of the products of each style.</span></span>  
  
 [!code-csharp[DP L2E Examples#Average2_MQ](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#average2_mq)]
 [!code-vb[DP L2E Examples#Average2_MQ](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#average2_mq)]  
  
### <a name="example"></a><span data-ttu-id="a13ce-109">示例</span><span class="sxs-lookup"><span data-stu-id="a13ce-109">Example</span></span>  
 <span data-ttu-id="a13ce-110">以下示例使用 <xref:System.Linq.Enumerable.Average%2A> 以获取每个联系人 ID 的平均应付款总计。</span><span class="sxs-lookup"><span data-stu-id="a13ce-110">The following example uses <xref:System.Linq.Enumerable.Average%2A> to get the average total due for each contact ID.</span></span>  
  
 [!code-csharp[DP L2E Examples#AverageGrouped_MQ](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#averagegrouped_mq)]
 [!code-vb[DP L2E Examples#AverageGrouped_MQ](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#averagegrouped_mq)]  
  
### <a name="example"></a><span data-ttu-id="a13ce-111">示例</span><span class="sxs-lookup"><span data-stu-id="a13ce-111">Example</span></span>  
 <span data-ttu-id="a13ce-112">以下示例使用 <xref:System.Linq.Enumerable.Average%2A> 以针对每个联系人获取具有平均应付款总计的订单。</span><span class="sxs-lookup"><span data-stu-id="a13ce-112">The following example uses <xref:System.Linq.Enumerable.Average%2A> to get the orders with the average total due for each contact.</span></span>  
  
 [!code-csharp[DP L2E Examples#AverageElements_MQ](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#averageelements_mq)]
 [!code-vb[DP L2E Examples#AverageElements_MQ](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#averageelements_mq)]  
  
## <a name="count"></a><span data-ttu-id="a13ce-113">计数</span><span class="sxs-lookup"><span data-stu-id="a13ce-113">Count</span></span>  
  
### <a name="example"></a><span data-ttu-id="a13ce-114">示例</span><span class="sxs-lookup"><span data-stu-id="a13ce-114">Example</span></span>  
 <span data-ttu-id="a13ce-115">以下示例使用 <xref:System.Linq.Enumerable.Count%2A> 以返回联系人 ID 的列表和每个联系人 ID 所具有的订单数。</span><span class="sxs-lookup"><span data-stu-id="a13ce-115">The following example uses <xref:System.Linq.Enumerable.Count%2A> to return a list of contact IDs and how many orders each has.</span></span>  
  
 [!code-csharp[DP L2E Examples#CountNested](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#countnested)]
 [!code-vb[DP L2E Examples#CountNested](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#countnested)]  
  
### <a name="example"></a><span data-ttu-id="a13ce-116">示例</span><span class="sxs-lookup"><span data-stu-id="a13ce-116">Example</span></span>  
 <span data-ttu-id="a13ce-117">以下示例按颜色对产品进行分组，并使用 <xref:System.Linq.Enumerable.Count%2A> 以返回每个颜色组中的产品数量。</span><span class="sxs-lookup"><span data-stu-id="a13ce-117">The following example groups products by color and uses <xref:System.Linq.Enumerable.Count%2A> to return the number of products in each color group.</span></span>  
  
 [!code-csharp[DP L2E Examples#CountGrouped](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#countgrouped)]
 [!code-vb[DP L2E Examples#CountGrouped](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#countgrouped)]  
  
## <a name="max"></a><span data-ttu-id="a13ce-118">最大值</span><span class="sxs-lookup"><span data-stu-id="a13ce-118">Max</span></span>  
  
### <a name="example"></a><span data-ttu-id="a13ce-119">示例</span><span class="sxs-lookup"><span data-stu-id="a13ce-119">Example</span></span>  
 <span data-ttu-id="a13ce-120">以下示例使用 <xref:System.Linq.Enumerable.Max%2A> 方法以获取每个联系人 ID 的最大应付款总计。</span><span class="sxs-lookup"><span data-stu-id="a13ce-120">The following example uses the <xref:System.Linq.Enumerable.Max%2A> method to get the largest total due for each contact ID.</span></span>  
  
 [!code-csharp[DP L2E Examples#MaxGrouped_MQ](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#maxgrouped_mq)]
 [!code-vb[DP L2E Examples#MaxGrouped_MQ](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#maxgrouped_mq)]  
  
### <a name="example"></a><span data-ttu-id="a13ce-121">示例</span><span class="sxs-lookup"><span data-stu-id="a13ce-121">Example</span></span>  
 <span data-ttu-id="a13ce-122">以下示例使用 <xref:System.Linq.Enumerable.Max%2A> 方法以针对每个联系人 ID 获取具有最大应付款总计的订单。</span><span class="sxs-lookup"><span data-stu-id="a13ce-122">The following example uses the <xref:System.Linq.Enumerable.Max%2A> method to get the orders with the largest total due for each contact ID.</span></span>  
  
 [!code-csharp[DP L2E Examples#MaxElements_MQ](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#maxelements_mq)]
 [!code-vb[DP L2E Examples#MaxElements_MQ](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#maxelements_mq)]  
  
## <a name="min"></a><span data-ttu-id="a13ce-123">最小值</span><span class="sxs-lookup"><span data-stu-id="a13ce-123">Min</span></span>  
  
### <a name="example"></a><span data-ttu-id="a13ce-124">示例</span><span class="sxs-lookup"><span data-stu-id="a13ce-124">Example</span></span>  
 <span data-ttu-id="a13ce-125">以下示例使用 <xref:System.Linq.Enumerable.Min%2A> 方法以获取每个联系人 ID 的最小应付款总计。</span><span class="sxs-lookup"><span data-stu-id="a13ce-125">The following example uses the <xref:System.Linq.Enumerable.Min%2A> method to get the smallest total due for each contact ID.</span></span>  
  
 [!code-csharp[DP L2E Examples#MinGrouped_MQ](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#mingrouped_mq)]
 [!code-vb[DP L2E Examples#MinGrouped_MQ](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#mingrouped_mq)]  
  
### <a name="example"></a><span data-ttu-id="a13ce-126">示例</span><span class="sxs-lookup"><span data-stu-id="a13ce-126">Example</span></span>  
 <span data-ttu-id="a13ce-127">以下示例使用 <xref:System.Linq.Enumerable.Min%2A> 方法以针对每个联系人获取具有最小应付款总计的订单。</span><span class="sxs-lookup"><span data-stu-id="a13ce-127">The following example uses the <xref:System.Linq.Enumerable.Min%2A> method to get the orders with the smallest total due for each contact.</span></span>  
  
 [!code-csharp[DP L2E Examples#MinElements_MQ](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#minelements_mq)]
 [!code-vb[DP L2E Examples#MinElements_MQ](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#minelements_mq)]  
  
## <a name="sum"></a><span data-ttu-id="a13ce-128">Sum</span><span class="sxs-lookup"><span data-stu-id="a13ce-128">Sum</span></span>  
  
### <a name="example"></a><span data-ttu-id="a13ce-129">示例</span><span class="sxs-lookup"><span data-stu-id="a13ce-129">Example</span></span>  
 <span data-ttu-id="a13ce-130">以下示例使用 <xref:System.Linq.Enumerable.Sum%2A> 方法以获取每个联系人 ID 的应付款总计。</span><span class="sxs-lookup"><span data-stu-id="a13ce-130">The following example uses the <xref:System.Linq.Enumerable.Sum%2A> method to get the total due for each contact ID.</span></span>  
  
 [!code-csharp[DP L2E Examples#SumGrouped_MQ](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#sumgrouped_mq)]
 [!code-vb[DP L2E Examples#SumGrouped_MQ](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#sumgrouped_mq)]  
  
## <a name="see-also"></a><span data-ttu-id="a13ce-131">请参阅</span><span class="sxs-lookup"><span data-stu-id="a13ce-131">See also</span></span>
- [<span data-ttu-id="a13ce-132">LINQ to Entities 中的查询</span><span class="sxs-lookup"><span data-stu-id="a13ce-132">Queries in LINQ to Entities</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/queries-in-linq-to-entities.md)
