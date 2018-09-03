---
title: 基于方法的查询语法示例：聚合运算符
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 0e306067-5720-4782-9719-2286570a7e47
ms.openlocfilehash: 1f4090cbffc4177c4b9edd08381e8dd294ae0c41
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/03/2018
ms.locfileid: "43476100"
---
# <a name="method-based-query-syntax-examples-aggregate-operators"></a><span data-ttu-id="29761-102">基于方法的查询语法示例：聚合运算符</span><span class="sxs-lookup"><span data-stu-id="29761-102">Method-Based Query Syntax Examples: Aggregate Operators</span></span>
<span data-ttu-id="29761-103">本主题中的示例演示如何使用<xref:System.Linq.Enumerable.Aggregate%2A>， <xref:System.Linq.Enumerable.Average%2A>， <xref:System.Linq.Enumerable.Count%2A>， <xref:System.Linq.Enumerable.LongCount%2A>， <xref:System.Linq.Enumerable.Max%2A>， <xref:System.Linq.Enumerable.Min%2A>，以及<xref:System.Linq.Enumerable.Sum%2A>方法来查询[AdventureWorks 销售模型](https://msdn.microsoft.com/library/f16cd988-673f-4376-b034-129ca93c7832)使用基于方法的查询语法。</span><span class="sxs-lookup"><span data-stu-id="29761-103">The examples in this topic demonstrate how to use the <xref:System.Linq.Enumerable.Aggregate%2A>, <xref:System.Linq.Enumerable.Average%2A>, <xref:System.Linq.Enumerable.Count%2A>, <xref:System.Linq.Enumerable.LongCount%2A>, <xref:System.Linq.Enumerable.Max%2A>, <xref:System.Linq.Enumerable.Min%2A>, and <xref:System.Linq.Enumerable.Sum%2A> methods to query the [AdventureWorks Sales Model](https://msdn.microsoft.com/library/f16cd988-673f-4376-b034-129ca93c7832) using method-based query syntax.</span></span> <span data-ttu-id="29761-104">这些示例中使用的 AdventureWorks 销售模型从 AdventureWorks 示例数据库中的 Contact、Address、Product、SalesOrderHeader 和 SalesOrderDetail 等表生成。</span><span class="sxs-lookup"><span data-stu-id="29761-104">The AdventureWorks Sales Model used in these examples is built from the Contact, Address, Product, SalesOrderHeader, and SalesOrderDetail tables in the AdventureWorks sample database.</span></span>  
  
 <span data-ttu-id="29761-105">本主题中的示例使用以下`using` / `Imports`语句：</span><span class="sxs-lookup"><span data-stu-id="29761-105">The examples in this topic use the following `using`/`Imports` statements:</span></span>  
  
 [!code-csharp[DP L2E Examples#ImportsUsing](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#importsusing)]
 [!code-vb[DP L2E Examples#ImportsUsing](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#importsusing)]  
  
## <a name="average"></a><span data-ttu-id="29761-106">平均值</span><span class="sxs-lookup"><span data-stu-id="29761-106">Average</span></span>  
  
### <a name="example"></a><span data-ttu-id="29761-107">示例</span><span class="sxs-lookup"><span data-stu-id="29761-107">Example</span></span>  
 <span data-ttu-id="29761-108">以下示例使用 <xref:System.Linq.Enumerable.Average%2A> 方法以查找产品的平均标价。</span><span class="sxs-lookup"><span data-stu-id="29761-108">The following example uses the <xref:System.Linq.Enumerable.Average%2A> method to find the average list price of the products.</span></span>  
  
 [!code-csharp[DP L2E Examples#Average_MQ](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#average_mq)]
 [!code-vb[DP L2E Examples#Average_MQ](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#average_mq)]  
  
### <a name="example"></a><span data-ttu-id="29761-109">示例</span><span class="sxs-lookup"><span data-stu-id="29761-109">Example</span></span>  
 <span data-ttu-id="29761-110">以下示例使用 <xref:System.Linq.Enumerable.Average%2A> 方法以查找每种样式的产品的平均标价。</span><span class="sxs-lookup"><span data-stu-id="29761-110">The following example uses the <xref:System.Linq.Enumerable.Average%2A> method to find the average list price of the products of each style.</span></span>  
  
 [!code-csharp[DP L2E Examples#Average2_MQ](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#average2_mq)]
 [!code-vb[DP L2E Examples#Average2_MQ](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#average2_mq)]  
  
### <a name="example"></a><span data-ttu-id="29761-111">示例</span><span class="sxs-lookup"><span data-stu-id="29761-111">Example</span></span>  
 <span data-ttu-id="29761-112">以下示例使用 <xref:System.Linq.Enumerable.Average%2A> 方法以查找平均应付款总计。</span><span class="sxs-lookup"><span data-stu-id="29761-112">The following example uses the <xref:System.Linq.Enumerable.Average%2A> method to find the average total due.</span></span>  
  
 [!code-csharp[DP L2E Examples#AverageProjection_MQ](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#averageprojection_mq)]
 [!code-vb[DP L2E Examples#AverageProjection_MQ](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#averageprojection_mq)]  
  
### <a name="example"></a><span data-ttu-id="29761-113">示例</span><span class="sxs-lookup"><span data-stu-id="29761-113">Example</span></span>  
 <span data-ttu-id="29761-114">以下示例使用 <xref:System.Linq.Enumerable.Average%2A> 方法以获取每个联系人 ID 的平均应付款总计。</span><span class="sxs-lookup"><span data-stu-id="29761-114">The following example uses the <xref:System.Linq.Enumerable.Average%2A> method to get the average total due for each contact ID.</span></span>  
  
 [!code-csharp[DP L2E Examples#AverageGrouped_MQ](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#averagegrouped_mq)]
 [!code-vb[DP L2E Examples#AverageGrouped_MQ](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#averagegrouped_mq)]  
  
### <a name="example"></a><span data-ttu-id="29761-115">示例</span><span class="sxs-lookup"><span data-stu-id="29761-115">Example</span></span>  
 <span data-ttu-id="29761-116">以下示例使用 <xref:System.Linq.Enumerable.Average%2A> 方法以针对每个联系人获取具有平均应付款总计的订单。</span><span class="sxs-lookup"><span data-stu-id="29761-116">The following example uses the <xref:System.Linq.Enumerable.Average%2A> method to get the orders with the average total due for each contact.</span></span>  
  
 [!code-csharp[DP L2E Examples#AverageElements_MQ](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#averageelements_mq)]
 [!code-vb[DP L2E Examples#AverageElements_MQ](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#averageelements_mq)]  
  
## <a name="count"></a><span data-ttu-id="29761-117">计数</span><span class="sxs-lookup"><span data-stu-id="29761-117">Count</span></span>  
  
### <a name="example"></a><span data-ttu-id="29761-118">示例</span><span class="sxs-lookup"><span data-stu-id="29761-118">Example</span></span>  
 <span data-ttu-id="29761-119">以下示例使用 <xref:System.Linq.Enumerable.Count%2A> 方法以返回 Product 表中的产品数量。</span><span class="sxs-lookup"><span data-stu-id="29761-119">The following example uses the <xref:System.Linq.Enumerable.Count%2A> method to return the number of products in the Product table.</span></span>  
  
 [!code-csharp[DP L2E Examples#Count](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#count)]
 [!code-vb[DP L2E Examples#Count](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#count)]  
  
### <a name="example"></a><span data-ttu-id="29761-120">示例</span><span class="sxs-lookup"><span data-stu-id="29761-120">Example</span></span>  
 <span data-ttu-id="29761-121">以下示例使用 <xref:System.Linq.Enumerable.Count%2A> 方法以返回联系人 ID 的列表和每个联系人 ID 所具有的订单数。</span><span class="sxs-lookup"><span data-stu-id="29761-121">The following example uses the <xref:System.Linq.Enumerable.Count%2A> method to return a list of contact IDs and how many orders each has.</span></span>  
  
 [!code-csharp[DP L2E Examples#CountNested](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#countnested)]
 [!code-vb[DP L2E Examples#CountNested](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#countnested)]  
  
### <a name="example"></a><span data-ttu-id="29761-122">示例</span><span class="sxs-lookup"><span data-stu-id="29761-122">Example</span></span>  
 <span data-ttu-id="29761-123">以下示例按颜色对产品进行分组，并使用 <xref:System.Linq.Enumerable.Count%2A> 方法以返回每个颜色组中的产品数量。</span><span class="sxs-lookup"><span data-stu-id="29761-123">The following example groups products by color and uses the <xref:System.Linq.Enumerable.Count%2A> method to return the number of products in each color group.</span></span>  
  
 [!code-csharp[DP L2E Examples#CountGrouped](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#countgrouped)]
 [!code-vb[DP L2E Examples#CountGrouped](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#countgrouped)]  
  
## <a name="longcount"></a><span data-ttu-id="29761-124">LongCount</span><span class="sxs-lookup"><span data-stu-id="29761-124">LongCount</span></span>  
  
### <a name="example"></a><span data-ttu-id="29761-125">示例</span><span class="sxs-lookup"><span data-stu-id="29761-125">Example</span></span>  
 <span data-ttu-id="29761-126">以下示例以长整型获取联系人计数。</span><span class="sxs-lookup"><span data-stu-id="29761-126">The following example gets the contact count as a long integer.</span></span>  
  
 [!code-csharp[DP L2E Examples#LongCountSimple](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#longcountsimple)]
 [!code-vb[DP L2E Examples#LongCountSimple](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#longcountsimple)]  
  
## <a name="max"></a><span data-ttu-id="29761-127">最大值</span><span class="sxs-lookup"><span data-stu-id="29761-127">Max</span></span>  
  
### <a name="example"></a><span data-ttu-id="29761-128">示例</span><span class="sxs-lookup"><span data-stu-id="29761-128">Example</span></span>  
 <span data-ttu-id="29761-129">以下示例使用 <xref:System.Linq.Enumerable.Max%2A> 方法以获取最大应付款总计。</span><span class="sxs-lookup"><span data-stu-id="29761-129">The following example uses the <xref:System.Linq.Enumerable.Max%2A> method to get the largest total due.</span></span>  
  
 [!code-csharp[DP L2E Examples#MaxProjection_MQ](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#maxprojection_mq)]
 [!code-vb[DP L2E Examples#MaxProjection_MQ](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#maxprojection_mq)]  
  
### <a name="example"></a><span data-ttu-id="29761-130">示例</span><span class="sxs-lookup"><span data-stu-id="29761-130">Example</span></span>  
 <span data-ttu-id="29761-131">以下示例使用 <xref:System.Linq.Enumerable.Max%2A> 方法以获取每个联系人 ID 的最大应付款总计。</span><span class="sxs-lookup"><span data-stu-id="29761-131">The following example uses the <xref:System.Linq.Enumerable.Max%2A> method to get the largest total due for each contact ID.</span></span>  
  
 [!code-csharp[DP L2E Examples#MaxGrouped_MQ](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#maxgrouped_mq)]
 [!code-vb[DP L2E Examples#MaxGrouped_MQ](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#maxgrouped_mq)]  
  
### <a name="example"></a><span data-ttu-id="29761-132">示例</span><span class="sxs-lookup"><span data-stu-id="29761-132">Example</span></span>  
 <span data-ttu-id="29761-133">以下示例使用 <xref:System.Linq.Enumerable.Max%2A> 方法以针对每个联系人 ID 获取具有最大应付款总计的订单。</span><span class="sxs-lookup"><span data-stu-id="29761-133">The following example uses the <xref:System.Linq.Enumerable.Max%2A> method to get the orders with the largest total due for each contact ID.</span></span>  
  
 [!code-csharp[DP L2E Examples#MaxElements_MQ](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#maxelements_mq)]
 [!code-vb[DP L2E Examples#MaxElements_MQ](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#maxelements_mq)]  
  
## <a name="min"></a><span data-ttu-id="29761-134">最小值</span><span class="sxs-lookup"><span data-stu-id="29761-134">Min</span></span>  
  
### <a name="example"></a><span data-ttu-id="29761-135">示例</span><span class="sxs-lookup"><span data-stu-id="29761-135">Example</span></span>  
 <span data-ttu-id="29761-136">以下示例使用 <xref:System.Linq.Enumerable.Min%2A> 方法以获取最小应付款总计。</span><span class="sxs-lookup"><span data-stu-id="29761-136">The following example uses the <xref:System.Linq.Enumerable.Min%2A> method to get the smallest total due.</span></span>  
  
 [!code-csharp[DP L2E Examples#MinProjection_MQ](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#minprojection_mq)]
 [!code-vb[DP L2E Examples#MinProjection_MQ](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#minprojection_mq)]  
  
### <a name="example"></a><span data-ttu-id="29761-137">示例</span><span class="sxs-lookup"><span data-stu-id="29761-137">Example</span></span>  
 <span data-ttu-id="29761-138">以下示例使用 <xref:System.Linq.Enumerable.Min%2A> 方法以获取每个联系人 ID 的最小应付款总计。</span><span class="sxs-lookup"><span data-stu-id="29761-138">The following example uses the <xref:System.Linq.Enumerable.Min%2A> method to get the smallest total due for each contact ID.</span></span>  
  
 [!code-csharp[DP L2E Examples#MinGrouped_MQ](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#mingrouped_mq)]
 [!code-vb[DP L2E Examples#MinGrouped_MQ](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#mingrouped_mq)]  
  
### <a name="example"></a><span data-ttu-id="29761-139">示例</span><span class="sxs-lookup"><span data-stu-id="29761-139">Example</span></span>  
 <span data-ttu-id="29761-140">以下示例使用 <xref:System.Linq.Enumerable.Min%2A> 方法以针对每个联系人获取具有最小应付款总计的订单。</span><span class="sxs-lookup"><span data-stu-id="29761-140">The following example uses the <xref:System.Linq.Enumerable.Min%2A> method to get the orders with the smallest total due for each contact.</span></span>  
  
 [!code-csharp[DP L2E Examples#MinElements_MQ](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#minelements_mq)]
 [!code-vb[DP L2E Examples#MinElements_MQ](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#minelements_mq)]  
  
## <a name="sum"></a><span data-ttu-id="29761-141">Sum</span><span class="sxs-lookup"><span data-stu-id="29761-141">Sum</span></span>  
  
### <a name="example"></a><span data-ttu-id="29761-142">示例</span><span class="sxs-lookup"><span data-stu-id="29761-142">Example</span></span>  
 <span data-ttu-id="29761-143">以下示例使用 <xref:System.Linq.Enumerable.Sum%2A> 方法以获取 SalesOrderDetail 表中订单数量的总数。</span><span class="sxs-lookup"><span data-stu-id="29761-143">The following example uses the <xref:System.Linq.Enumerable.Sum%2A> method to get the total number of order quantities in the SalesOrderDetail table.</span></span>  
  
 [!code-csharp[DP L2E Examples#SumProjection_MQ](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#sumprojection_mq)]
 [!code-vb[DP L2E Examples#SumProjection_MQ](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#sumprojection_mq)]  
  
### <a name="example"></a><span data-ttu-id="29761-144">示例</span><span class="sxs-lookup"><span data-stu-id="29761-144">Example</span></span>  
 <span data-ttu-id="29761-145">以下示例使用 <xref:System.Linq.Enumerable.Sum%2A> 方法以获取每个联系人 ID 的应付款总计。</span><span class="sxs-lookup"><span data-stu-id="29761-145">The following example uses the <xref:System.Linq.Enumerable.Sum%2A> method to get the total due for each contact ID.</span></span>  
  
 [!code-csharp[DP L2E Examples#SumGrouped_MQ](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#sumgrouped_mq)]
 [!code-vb[DP L2E Examples#SumGrouped_MQ](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#sumgrouped_mq)]  
  
## <a name="see-also"></a><span data-ttu-id="29761-146">请参阅</span><span class="sxs-lookup"><span data-stu-id="29761-146">See Also</span></span>  
 [<span data-ttu-id="29761-147">LINQ to Entities 中的查询</span><span class="sxs-lookup"><span data-stu-id="29761-147">Queries in LINQ to Entities</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/queries-in-linq-to-entities.md)
