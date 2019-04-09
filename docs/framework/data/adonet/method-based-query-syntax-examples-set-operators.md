---
title: 基于方法的查询语法示例：集合运算符 (LINQ to DataSet)
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: fa93af15-28af-4b5e-846b-897308410edb
ms.openlocfilehash: 48aa6044f39be93f144b6c4af5137b131dda0b30
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/08/2019
ms.locfileid: "59085813"
---
# <a name="method-based-query-syntax-examples-set-operators-linq-to-dataset"></a><span data-ttu-id="ca3f3-102">基于方法的查询语法示例：集合运算符 (LINQ to DataSet)</span><span class="sxs-lookup"><span data-stu-id="ca3f3-102">Method-Based Query Syntax Examples: Set Operators (LINQ to DataSet)</span></span>
<span data-ttu-id="ca3f3-103">本主题中的示例演示如何使用<xref:System.Linq.Enumerable.Distinct%2A>， <xref:System.Linq.Enumerable.Except%2A>， <xref:System.Linq.Enumerable.Intersect%2A>，和<xref:System.Linq.Enumerable.Union%2A>运算符以对数据行集执行基于值的比较运算。[正在加载数据到数据集](../../../../docs/framework/data/adonet/loading-data-into-a-dataset.md)请参阅[比较 Datarow](../../../../docs/framework/data/adonet/comparing-datarows-linq-to-dataset.md)有关详细信息<xref:System.Data.DataRowComparer>。</span><span class="sxs-lookup"><span data-stu-id="ca3f3-103">The examples in this topic demonstrate how to use the <xref:System.Linq.Enumerable.Distinct%2A>, <xref:System.Linq.Enumerable.Except%2A>, <xref:System.Linq.Enumerable.Intersect%2A>, and <xref:System.Linq.Enumerable.Union%2A> operators to perform value-based comparison operations on sets of data rows.[Loading Data Into a DataSet](../../../../docs/framework/data/adonet/loading-data-into-a-dataset.md) See [Comparing DataRows](../../../../docs/framework/data/adonet/comparing-datarows-linq-to-dataset.md) for more information on <xref:System.Data.DataRowComparer>.</span></span>  
  
 <span data-ttu-id="ca3f3-104">`FillDataSet`中指定这些示例中使用的方法[加载数据到数据集](../../../../docs/framework/data/adonet/loading-data-into-a-dataset.md)。</span><span class="sxs-lookup"><span data-stu-id="ca3f3-104">The `FillDataSet` method used in these examples is specified in [Loading Data Into a DataSet](../../../../docs/framework/data/adonet/loading-data-into-a-dataset.md).</span></span>  
  
 <span data-ttu-id="ca3f3-105">本主题中的示例使用 AdventureWorks 示例数据库中的 Contact、Address、Product、SalesOrderHeader 和 SalesOrderDetail 表。</span><span class="sxs-lookup"><span data-stu-id="ca3f3-105">The examples in this topic use the Contact, Address, Product, SalesOrderHeader, and SalesOrderDetail tables in the AdventureWorks sample database.</span></span>  
  
 <span data-ttu-id="ca3f3-106">本主题中的示例使用以下`using` / `Imports`语句：</span><span class="sxs-lookup"><span data-stu-id="ca3f3-106">The examples in this topic use the following `using`/`Imports` statements:</span></span>  
  
 [!code-csharp[DP LINQ to DataSet Examples#ImportsUsing](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#importsusing)]
 [!code-vb[DP LINQ to DataSet Examples#ImportsUsing](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#importsusing)]  
  
 <span data-ttu-id="ca3f3-107">有关详细信息，请参阅[如何：在 Visual Studio 中创建 LINQ to DataSet 项目](../../../../docs/framework/data/adonet/how-to-create-a-linq-to-dataset-project-in-vs.md)。</span><span class="sxs-lookup"><span data-stu-id="ca3f3-107">For more information, see [How to: Create a LINQ to DataSet Project In Visual Studio](../../../../docs/framework/data/adonet/how-to-create-a-linq-to-dataset-project-in-vs.md).</span></span>  
  
## <a name="distinct"></a><span data-ttu-id="ca3f3-108">Distinct</span><span class="sxs-lookup"><span data-stu-id="ca3f3-108">Distinct</span></span>  
  
### <a name="example"></a><span data-ttu-id="ca3f3-109">示例</span><span class="sxs-lookup"><span data-stu-id="ca3f3-109">Example</span></span>  
 <span data-ttu-id="ca3f3-110">此示例使用 <xref:System.Linq.Enumerable.Distinct%2A> 方法移除序列中的重复元素。</span><span class="sxs-lookup"><span data-stu-id="ca3f3-110">This example uses the <xref:System.Linq.Enumerable.Distinct%2A> method to remove duplicate elements in a sequence.</span></span>  
  
 [!code-csharp[DP LINQ to DataSet Examples#DistinctRows](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#distinctrows)]
 [!code-vb[DP LINQ to DataSet Examples#DistinctRows](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#distinctrows)]  
  
## <a name="except"></a><span data-ttu-id="ca3f3-111">Except</span><span class="sxs-lookup"><span data-stu-id="ca3f3-111">Except</span></span>  
  
### <a name="example"></a><span data-ttu-id="ca3f3-112">示例</span><span class="sxs-lookup"><span data-stu-id="ca3f3-112">Example</span></span>  
 <span data-ttu-id="ca3f3-113">此示例使用 <xref:System.Linq.Enumerable.Except%2A> 方法返回出现在第一个表中但不出现在第二个表中的联系人。</span><span class="sxs-lookup"><span data-stu-id="ca3f3-113">This example uses the <xref:System.Linq.Enumerable.Except%2A> method to return contacts that appear in the first table but not in the second.</span></span>  
  
 [!code-csharp[DP LINQ to DataSet Examples#Except2](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#except2)]
 [!code-vb[DP LINQ to DataSet Examples#Except2](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#except2)]  
  
## <a name="intersect"></a><span data-ttu-id="ca3f3-114">相交</span><span class="sxs-lookup"><span data-stu-id="ca3f3-114">Intersect</span></span>  
  
### <a name="example"></a><span data-ttu-id="ca3f3-115">示例</span><span class="sxs-lookup"><span data-stu-id="ca3f3-115">Example</span></span>  
 <span data-ttu-id="ca3f3-116">此示例使用 <xref:System.Linq.Enumerable.Intersect%2A> 方法返回同时出现在两个表中的联系人。</span><span class="sxs-lookup"><span data-stu-id="ca3f3-116">This example uses the <xref:System.Linq.Enumerable.Intersect%2A> method to return contacts that appear in both tables.</span></span>  
  
 [!code-csharp[DP LINQ to DataSet Examples#Intersect2](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#intersect2)]
 [!code-vb[DP LINQ to DataSet Examples#Intersect2](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#intersect2)]  
  
## <a name="union"></a><span data-ttu-id="ca3f3-117">联合</span><span class="sxs-lookup"><span data-stu-id="ca3f3-117">Union</span></span>  
  
### <a name="example"></a><span data-ttu-id="ca3f3-118">示例</span><span class="sxs-lookup"><span data-stu-id="ca3f3-118">Example</span></span>  
 <span data-ttu-id="ca3f3-119">此示例使用 <xref:System.Linq.Enumerable.Union%2A> 方法返回这两个表的任一表中特有的联系人。</span><span class="sxs-lookup"><span data-stu-id="ca3f3-119">This example uses the <xref:System.Linq.Enumerable.Union%2A> method to return unique contacts from either of the two tables.</span></span>  
  
 [!code-csharp[DP LINQ to DataSet Examples#Union2](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#union2)]
 [!code-vb[DP LINQ to DataSet Examples#Union2](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#union2)]  
  
## <a name="see-also"></a><span data-ttu-id="ca3f3-120">请参阅</span><span class="sxs-lookup"><span data-stu-id="ca3f3-120">See also</span></span>

- [<span data-ttu-id="ca3f3-121">将数据加载到数据集中</span><span class="sxs-lookup"><span data-stu-id="ca3f3-121">Loading Data Into a DataSet</span></span>](../../../../docs/framework/data/adonet/loading-data-into-a-dataset.md)
- [<span data-ttu-id="ca3f3-122">LINQ to DataSet 示例</span><span class="sxs-lookup"><span data-stu-id="ca3f3-122">LINQ to DataSet Examples</span></span>](../../../../docs/framework/data/adonet/linq-to-dataset-examples.md)
- [<span data-ttu-id="ca3f3-123">标准查询运算符概述 (C#)</span><span class="sxs-lookup"><span data-stu-id="ca3f3-123">Standard Query Operators Overview (C#)</span></span>](../../../csharp/programming-guide/concepts/linq/standard-query-operators-overview.md)
- [<span data-ttu-id="ca3f3-124">标准查询运算符概述 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="ca3f3-124">Standard Query Operators Overview (Visual Basic)</span></span>](../../../visual-basic/programming-guide/concepts/linq/standard-query-operators-overview.md)
