---
title: "基于方法的查询语法示例：聚合运算符 (LINQ to DataSet)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
ms.assetid: 5ed5f01d-acb2-4dd4-be60-f04c2d570fa8
caps.latest.revision: "2"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.workload: dotnet
ms.openlocfilehash: bfb558c1904af7ba5f0cbfeaf63ee02b1c736553
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="method-based-query-syntax-examples-aggregate-operators-linq-to-dataset"></a><span data-ttu-id="2803b-102">基于方法的查询语法示例：聚合运算符 (LINQ to DataSet)</span><span class="sxs-lookup"><span data-stu-id="2803b-102">Method-Based Query Syntax Examples: Aggregate Operators (LINQ to DataSet)</span></span>
<span data-ttu-id="2803b-103">本主题中的示例演示如何使用 <xref:System.Linq.Enumerable.Aggregate%2A>、<xref:System.Linq.Enumerable.Average%2A>、<xref:System.Linq.Enumerable.Count%2A>、<xref:System.Linq.Enumerable.LongCount%2A>、<xref:System.Linq.Enumerable.Max%2A>、<xref:System.Linq.Enumerable.Min%2A> 和 <xref:System.Linq.Enumerable.Sum%2A> 运算符来查询 <xref:System.Data.DataSet> 并使用方法查询语法聚合数据。</span><span class="sxs-lookup"><span data-stu-id="2803b-103">The examples in this topic demonstrate how to use the <xref:System.Linq.Enumerable.Aggregate%2A>, <xref:System.Linq.Enumerable.Average%2A>, <xref:System.Linq.Enumerable.Count%2A>, <xref:System.Linq.Enumerable.LongCount%2A>, <xref:System.Linq.Enumerable.Max%2A>, <xref:System.Linq.Enumerable.Min%2A>, and <xref:System.Linq.Enumerable.Sum%2A> operators to query a <xref:System.Data.DataSet> and aggregate data using method query syntax.</span></span>  
  
 <span data-ttu-id="2803b-104">`FillDataSet`中指定这些示例中使用的方法[加载数据到数据集](../../../../docs/framework/data/adonet/loading-data-into-a-dataset.md)。</span><span class="sxs-lookup"><span data-stu-id="2803b-104">The `FillDataSet` method used in these examples is specified in [Loading Data Into a DataSet](../../../../docs/framework/data/adonet/loading-data-into-a-dataset.md).</span></span>  
  
 <span data-ttu-id="2803b-105">本主题中的示例使用 AdventureWorks 示例数据库中的 Contact、Address、Product、SalesOrderHeader 和 SalesOrderDetail 表。</span><span class="sxs-lookup"><span data-stu-id="2803b-105">The examples in this topic use the Contact, Address, Product, SalesOrderHeader, and SalesOrderDetail tables in the AdventureWorks sample database.</span></span>  
  
 <span data-ttu-id="2803b-106">本主题中的示例使用以下`using` / `Imports`语句：</span><span class="sxs-lookup"><span data-stu-id="2803b-106">The examples in this topic use the following `using`/`Imports` statements:</span></span>  
  
 [!code-csharp[DP LINQ to DataSet Examples#ImportsUsing](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#importsusing)]
 [!code-vb[DP LINQ to DataSet Examples#ImportsUsing](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#importsusing)]  
  
 <span data-ttu-id="2803b-107">有关详细信息，请参阅[如何： 创建 LINQ to DataSet 项目在 Visual Studio 中](../../../../docs/framework/data/adonet/how-to-create-a-linq-to-dataset-project-in-vs.md)。</span><span class="sxs-lookup"><span data-stu-id="2803b-107">For more information, see [How to: Create a LINQ to DataSet Project In Visual Studio](../../../../docs/framework/data/adonet/how-to-create-a-linq-to-dataset-project-in-vs.md).</span></span>  
  
## <a name="aggregate"></a><span data-ttu-id="2803b-108">聚合</span><span class="sxs-lookup"><span data-stu-id="2803b-108">Aggregate</span></span>  
  
### <a name="example"></a><span data-ttu-id="2803b-109">示例</span><span class="sxs-lookup"><span data-stu-id="2803b-109">Example</span></span>  
 <span data-ttu-id="2803b-110">此示例使用 <xref:System.Linq.Enumerable.Aggregate%2A> 方法获取 `Contact` 表中前 5 个联系人并生成逗号分隔的姓氏列表。</span><span class="sxs-lookup"><span data-stu-id="2803b-110">This example uses the <xref:System.Linq.Enumerable.Aggregate%2A> method to get the first 5 contacts from the `Contact` table and build a comma-delimited list of the last names.</span></span>  
  
 [!code-csharp[DP LINQ to DataSet Examples#Aggregate_MQ](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#aggregate_mq)]
 [!code-vb[DP LINQ to DataSet Examples#Aggregate_MQ](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#aggregate_mq)]  
  
## <a name="average"></a><span data-ttu-id="2803b-111">Average</span><span class="sxs-lookup"><span data-stu-id="2803b-111">Average</span></span>  
  
### <a name="example"></a><span data-ttu-id="2803b-112">示例</span><span class="sxs-lookup"><span data-stu-id="2803b-112">Example</span></span>  
 <span data-ttu-id="2803b-113">此示例使用 <xref:System.Linq.Enumerable.Average%2A> 方法来计算产品的平均定价。</span><span class="sxs-lookup"><span data-stu-id="2803b-113">This example uses the <xref:System.Linq.Enumerable.Average%2A> method to find the average list price of the products.</span></span>  
  
 [!code-csharp[DP LINQ to DataSet Examples#Average_MQ](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#average_mq)]
 [!code-vb[DP LINQ to DataSet Examples#Average_MQ](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#average_mq)]  
  
### <a name="example"></a><span data-ttu-id="2803b-114">示例</span><span class="sxs-lookup"><span data-stu-id="2803b-114">Example</span></span>  
 <span data-ttu-id="2803b-115">此示例使用 <xref:System.Linq.Enumerable.Average%2A> 方法来计算每种款式的产品的平均定价。</span><span class="sxs-lookup"><span data-stu-id="2803b-115">This example uses the <xref:System.Linq.Enumerable.Average%2A> method to find the average list price of the products of each style.</span></span>  
  
 [!code-csharp[DP LINQ to DataSet Examples#Average2_MQ](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#average2_mq)]
 [!code-vb[DP LINQ to DataSet Examples#Average2_MQ](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#average2_mq)]  
  
### <a name="example"></a><span data-ttu-id="2803b-116">示例</span><span class="sxs-lookup"><span data-stu-id="2803b-116">Example</span></span>  
 <span data-ttu-id="2803b-117">此示例使用 <xref:System.Linq.Enumerable.Average%2A> 方法来计算总平均应付金额。</span><span class="sxs-lookup"><span data-stu-id="2803b-117">This example uses the <xref:System.Linq.Enumerable.Average%2A> method to find the average total due.</span></span>  
  
 [!code-csharp[DP LINQ to DataSet Examples#AverageProjection_MQ](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#averageprojection_mq)]
 [!code-vb[DP LINQ to DataSet Examples#AverageProjection_MQ](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#averageprojection_mq)]  
  
### <a name="example"></a><span data-ttu-id="2803b-118">示例</span><span class="sxs-lookup"><span data-stu-id="2803b-118">Example</span></span>  
 <span data-ttu-id="2803b-119">此示例使用 <xref:System.Linq.Enumerable.Average%2A> 方法获取每个联系人 ID 的总平均应付金额。</span><span class="sxs-lookup"><span data-stu-id="2803b-119">This example uses the <xref:System.Linq.Enumerable.Average%2A> method to get the average total due for each contact ID.</span></span>  
  
 [!code-csharp[DP LINQ to DataSet Examples#AverageGrouped_MQ](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#averagegrouped_mq)]
 [!code-vb[DP LINQ to DataSet Examples#AverageGrouped_MQ](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#averagegrouped_mq)]  
  
### <a name="example"></a><span data-ttu-id="2803b-120">示例</span><span class="sxs-lookup"><span data-stu-id="2803b-120">Example</span></span>  
 <span data-ttu-id="2803b-121">此示例使用 <xref:System.Linq.Enumerable.Average%2A> 方法获取每个联系人的具有平均 `TotalDue` 的订单。</span><span class="sxs-lookup"><span data-stu-id="2803b-121">This example uses the <xref:System.Linq.Enumerable.Average%2A> method to get the orders with the average `TotalDue` for each contact.</span></span>  
  
 [!code-csharp[DP LINQ to DataSet Examples#AverageElements_MQ](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#averageelements_mq)]
 [!code-vb[DP LINQ to DataSet Examples#AverageElements_MQ](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#averageelements_mq)]  
  
## <a name="count"></a><span data-ttu-id="2803b-122">计数</span><span class="sxs-lookup"><span data-stu-id="2803b-122">Count</span></span>  
  
### <a name="example"></a><span data-ttu-id="2803b-123">示例</span><span class="sxs-lookup"><span data-stu-id="2803b-123">Example</span></span>  
 <span data-ttu-id="2803b-124">此示例使用 <xref:System.Linq.Enumerable.Count%2A> 方法返回 `Product` 表中的产品数目。</span><span class="sxs-lookup"><span data-stu-id="2803b-124">This example uses the <xref:System.Linq.Enumerable.Count%2A> method to return the number of products in the `Product` table.</span></span>  
  
 [!code-csharp[DP LINQ to DataSet Examples#Count](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#count)]
 [!code-vb[DP LINQ to DataSet Examples#Count](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#count)]  
  
### <a name="example"></a><span data-ttu-id="2803b-125">示例</span><span class="sxs-lookup"><span data-stu-id="2803b-125">Example</span></span>  
 <span data-ttu-id="2803b-126">此示例使用 <xref:System.Linq.Enumerable.Count%2A> 方法返回联系人 ID 的列表及每个联系人 ID 的订单数。</span><span class="sxs-lookup"><span data-stu-id="2803b-126">This example uses the <xref:System.Linq.Enumerable.Count%2A> method to return a list of contact IDs and how many orders each has.</span></span>  
  
 [!code-csharp[DP LINQ to DataSet Examples#CountNested](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#countnested)]
 [!code-vb[DP LINQ to DataSet Examples#CountNested](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#countnested)]  
  
### <a name="example"></a><span data-ttu-id="2803b-127">示例</span><span class="sxs-lookup"><span data-stu-id="2803b-127">Example</span></span>  
 <span data-ttu-id="2803b-128">此示例按颜色对产品分组并使用 <xref:System.Linq.Enumerable.Count%2A> 方法返回每个颜色组中的产品数目。</span><span class="sxs-lookup"><span data-stu-id="2803b-128">This example groups products by color and uses the <xref:System.Linq.Enumerable.Count%2A> method to return the number of products in each color group.</span></span>  
  
 [!code-csharp[DP LINQ to DataSet Examples#CountGrouped](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#countgrouped)]
 [!code-vb[DP LINQ to DataSet Examples#CountGrouped](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#countgrouped)]  
  
## <a name="longcount"></a><span data-ttu-id="2803b-129">LongCount</span><span class="sxs-lookup"><span data-stu-id="2803b-129">LongCount</span></span>  
  
### <a name="example"></a><span data-ttu-id="2803b-130">示例</span><span class="sxs-lookup"><span data-stu-id="2803b-130">Example</span></span>  
 <span data-ttu-id="2803b-131">此示例获取长整型的联系人计数。</span><span class="sxs-lookup"><span data-stu-id="2803b-131">This example gets the contact count as a long integer.</span></span>  
  
 [!code-csharp[DP LINQ to DataSet Examples#LongCountSimple](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#longcountsimple)]
 [!code-vb[DP LINQ to DataSet Examples#LongCountSimple](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#longcountsimple)]  
  
## <a name="max"></a><span data-ttu-id="2803b-132">最大值</span><span class="sxs-lookup"><span data-stu-id="2803b-132">Max</span></span>  
  
### <a name="example"></a><span data-ttu-id="2803b-133">示例</span><span class="sxs-lookup"><span data-stu-id="2803b-133">Example</span></span>  
 <span data-ttu-id="2803b-134">此示例使用 <xref:System.Linq.Enumerable.Max%2A> 方法来获取最大总应付金额。</span><span class="sxs-lookup"><span data-stu-id="2803b-134">This example uses the <xref:System.Linq.Enumerable.Max%2A> method to get the largest total due.</span></span>  
  
 [!code-csharp[DP LINQ to DataSet Examples#MaxProjection_MQ](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#maxprojection_mq)]
 [!code-vb[DP LINQ to DataSet Examples#MaxProjection_MQ](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#maxprojection_mq)]  
  
### <a name="example"></a><span data-ttu-id="2803b-135">示例</span><span class="sxs-lookup"><span data-stu-id="2803b-135">Example</span></span>  
 <span data-ttu-id="2803b-136">此示例使用 <xref:System.Linq.Enumerable.Max%2A> 方法获取每个联系人 ID 的最大总应付金额。</span><span class="sxs-lookup"><span data-stu-id="2803b-136">This example uses the <xref:System.Linq.Enumerable.Max%2A> method to get the largest total due for each contact ID.</span></span>  
  
 [!code-csharp[DP LINQ to DataSet Examples#MaxGrouped_MQ](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#maxgrouped_mq)]
 [!code-vb[DP LINQ to DataSet Examples#MaxGrouped_MQ](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#maxgrouped_mq)]  
  
### <a name="example"></a><span data-ttu-id="2803b-137">示例</span><span class="sxs-lookup"><span data-stu-id="2803b-137">Example</span></span>  
 <span data-ttu-id="2803b-138">此示例使用 <xref:System.Linq.Enumerable.Max%2A> 方法获取每个联系人 ID 的具有最大 `TotalDue` 的订单。</span><span class="sxs-lookup"><span data-stu-id="2803b-138">This example uses the <xref:System.Linq.Enumerable.Max%2A> method to get the orders with the largest `TotalDue` for each contact ID.</span></span>  
  
 [!code-csharp[DP LINQ to DataSet Examples#MaxElements_MQ](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#maxelements_mq)]
 [!code-vb[DP LINQ to DataSet Examples#MaxElements_MQ](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#maxelements_mq)]  
  
## <a name="min"></a><span data-ttu-id="2803b-139">最小值</span><span class="sxs-lookup"><span data-stu-id="2803b-139">Min</span></span>  
  
### <a name="example"></a><span data-ttu-id="2803b-140">示例</span><span class="sxs-lookup"><span data-stu-id="2803b-140">Example</span></span>  
 <span data-ttu-id="2803b-141">此示例使用 <xref:System.Linq.Enumerable.Min%2A> 方法来获取最小总应付金额。</span><span class="sxs-lookup"><span data-stu-id="2803b-141">This example uses the <xref:System.Linq.Enumerable.Min%2A> method to get the smallest total due.</span></span>  
  
 [!code-csharp[DP LINQ to DataSet Examples#MinProjection_MQ](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#minprojection_mq)]
 [!code-vb[DP LINQ to DataSet Examples#MinProjection_MQ](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#minprojection_mq)]  
  
### <a name="example"></a><span data-ttu-id="2803b-142">示例</span><span class="sxs-lookup"><span data-stu-id="2803b-142">Example</span></span>  
 <span data-ttu-id="2803b-143">此示例使用 <xref:System.Linq.Enumerable.Min%2A> 方法获取每个联系人 ID 的最小总应付金额。</span><span class="sxs-lookup"><span data-stu-id="2803b-143">This example uses the <xref:System.Linq.Enumerable.Min%2A> method to get the smallest total due for each contact ID.</span></span>  
  
 [!code-csharp[DP LINQ to DataSet Examples#MinGrouped_MQ](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#mingrouped_mq)]
 [!code-vb[DP LINQ to DataSet Examples#MinGrouped_MQ](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#mingrouped_mq)]  
  
### <a name="example"></a><span data-ttu-id="2803b-144">示例</span><span class="sxs-lookup"><span data-stu-id="2803b-144">Example</span></span>  
 <span data-ttu-id="2803b-145">此示例使用 <xref:System.Linq.Enumerable.Min%2A> 方法获取每个联系人的具有最小总应付金额的订单。</span><span class="sxs-lookup"><span data-stu-id="2803b-145">This example uses the <xref:System.Linq.Enumerable.Min%2A> method to get the orders with the smallest total due for each contact.</span></span>  
  
 [!code-csharp[DP LINQ to DataSet Examples#MinElements_MQ](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#minelements_mq)]
 [!code-vb[DP LINQ to DataSet Examples#MinElements_MQ](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#minelements_mq)]  
  
## <a name="sum"></a><span data-ttu-id="2803b-146">Sum</span><span class="sxs-lookup"><span data-stu-id="2803b-146">Sum</span></span>  
  
### <a name="example"></a><span data-ttu-id="2803b-147">示例</span><span class="sxs-lookup"><span data-stu-id="2803b-147">Example</span></span>  
 <span data-ttu-id="2803b-148">此示例使用 <xref:System.Linq.Enumerable.Sum%2A> 方法获取 `SalesOrderDetail` 表中订单数量的总数目。</span><span class="sxs-lookup"><span data-stu-id="2803b-148">This example uses the <xref:System.Linq.Enumerable.Sum%2A> method to get the total number of order quantities in the `SalesOrderDetail` table.</span></span>  
  
 [!code-csharp[DP LINQ to DataSet Examples#SumProjection_MQ](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#sumprojection_mq)]  
  
### <a name="example"></a><span data-ttu-id="2803b-149">示例</span><span class="sxs-lookup"><span data-stu-id="2803b-149">Example</span></span>  
 <span data-ttu-id="2803b-150">此示例使用 <xref:System.Linq.Enumerable.Sum%2A> 方法获取每个联系人 ID 的总应付金额。</span><span class="sxs-lookup"><span data-stu-id="2803b-150">This example uses the <xref:System.Linq.Enumerable.Sum%2A> method to get the total due for each contact ID.</span></span>  
  
 [!code-csharp[DP LINQ to DataSet Examples#SumGrouped_MQ](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#sumgrouped_mq)]
 [!code-vb[DP LINQ to DataSet Examples#SumGrouped_MQ](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#sumgrouped_mq)]  
  
## <a name="see-also"></a><span data-ttu-id="2803b-151">请参阅</span><span class="sxs-lookup"><span data-stu-id="2803b-151">See Also</span></span>  
 [<span data-ttu-id="2803b-152">将数据加载到数据集中</span><span class="sxs-lookup"><span data-stu-id="2803b-152">Loading Data Into a DataSet</span></span>](../../../../docs/framework/data/adonet/loading-data-into-a-dataset.md)  
 [<span data-ttu-id="2803b-153">LINQ to DataSet 示例</span><span class="sxs-lookup"><span data-stu-id="2803b-153">LINQ to DataSet Examples</span></span>](../../../../docs/framework/data/adonet/linq-to-dataset-examples.md)  
 [<span data-ttu-id="2803b-154">标准查询运算符概述</span><span class="sxs-lookup"><span data-stu-id="2803b-154">Standard Query Operators Overview</span></span>](http://msdn.microsoft.com/library/24cda21e-8af8-4632-b519-c404a839b9b2)
