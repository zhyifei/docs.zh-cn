---
title: 基于方法的查询语法示例：联接 (LINQ to DataSet)
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 4fd5ed2c-b03a-4054-a3ed-3ddb380d7d9d
ms.openlocfilehash: ba6e33f98e063aab946db27b97106272c5adef63
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/07/2019
ms.locfileid: "70783669"
---
# <a name="method-based-query-syntax-examples-join-linq-to-dataset"></a><span data-ttu-id="e0613-102">基于方法的查询语法示例：联接 (LINQ to DataSet)</span><span class="sxs-lookup"><span data-stu-id="e0613-102">Method-Based Query Syntax Examples: Join (LINQ to DataSet)</span></span>
<span data-ttu-id="e0613-103">联接是面向相互之间没有可导航关系的数据源（如关系数据库表）的查询中的一项重要操作。</span><span class="sxs-lookup"><span data-stu-id="e0613-103">Joining is an important operation in queries that target data sources that have no navigable relationships to each other, such as relational database tables.</span></span> <span data-ttu-id="e0613-104">联接两个数据源就是将一个数据源中的对象与另一个数据源中具有相同公共属性的对象相关联。</span><span class="sxs-lookup"><span data-stu-id="e0613-104">A join of two data sources is the association of objects in one data source with objects that share a common attribute in the other data source.</span></span> <span data-ttu-id="e0613-105">有关详细信息，请参阅[标准查询运算符概述C#（）](../../../csharp/programming-guide/concepts/linq/standard-query-operators-overview.md)或[标准查询运算符概述（Visual Basic）](../../../visual-basic/programming-guide/concepts/linq/standard-query-operators-overview.md)。</span><span class="sxs-lookup"><span data-stu-id="e0613-105">For more information, see [Standard Query Operators Overview (C#)](../../../csharp/programming-guide/concepts/linq/standard-query-operators-overview.md) or [Standard Query Operators Overview (Visual Basic)](../../../visual-basic/programming-guide/concepts/linq/standard-query-operators-overview.md).</span></span>  
  
 <span data-ttu-id="e0613-106">本主题中的示例演示如何使用 <xref:System.Linq.Enumerable.Join%2A> 方法以便使用该方法的查询语法来查询 <xref:System.Data.DataSet>。</span><span class="sxs-lookup"><span data-stu-id="e0613-106">The examples in this topic demonstrate how to use the <xref:System.Linq.Enumerable.Join%2A> method to query a <xref:System.Data.DataSet> using the method query syntax.</span></span>  
  
 <span data-ttu-id="e0613-107">在`FillDataSet`这些示例中使用的方法是在将[数据加载到数据集](loading-data-into-a-dataset.md)时指定的。</span><span class="sxs-lookup"><span data-stu-id="e0613-107">The `FillDataSet` method used in these examples is specified in [Loading Data Into a DataSet](loading-data-into-a-dataset.md).</span></span>  
  
 <span data-ttu-id="e0613-108">本主题中的示例使用 AdventureWorks 示例数据库中的 Contact、Address、Product、SalesOrderHeader 和 SalesOrderDetail 表。</span><span class="sxs-lookup"><span data-stu-id="e0613-108">The examples in this topic use the Contact, Address, Product, SalesOrderHeader, and SalesOrderDetail tables in the AdventureWorks sample database.</span></span>  
  
 <span data-ttu-id="e0613-109">本主题中的示例使用以下`using` / `Imports`语句：</span><span class="sxs-lookup"><span data-stu-id="e0613-109">The examples in this topic use the following `using`/`Imports` statements:</span></span>  
  
 [!code-csharp[DP LINQ to DataSet Examples#ImportsUsing](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#importsusing)]
 [!code-vb[DP LINQ to DataSet Examples#ImportsUsing](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#importsusing)]  
  
 <span data-ttu-id="e0613-110">有关详细信息，请参阅[如何：在 Visual Studio](how-to-create-a-linq-to-dataset-project-in-vs.md)中创建 LINQ to DataSet 项目。</span><span class="sxs-lookup"><span data-stu-id="e0613-110">For more information, see [How to: Create a LINQ to DataSet Project In Visual Studio](how-to-create-a-linq-to-dataset-project-in-vs.md).</span></span>  
  
## <a name="join"></a><span data-ttu-id="e0613-111">联接</span><span class="sxs-lookup"><span data-stu-id="e0613-111">Join</span></span>  
  
### <a name="example"></a><span data-ttu-id="e0613-112">示例</span><span class="sxs-lookup"><span data-stu-id="e0613-112">Example</span></span>  
 <span data-ttu-id="e0613-113">此示例对 `Contact` 和 `SalesOrderHeader` 表执行联接。</span><span class="sxs-lookup"><span data-stu-id="e0613-113">This example performs a join over the `Contact` and `SalesOrderHeader` tables.</span></span>  
  
 [!code-csharp[DP LINQ to DataSet Examples#JoinSimple_MQ](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#joinsimple_mq)]
 [!code-vb[DP LINQ to DataSet Examples#JoinSimple_MQ](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#joinsimple_mq)]  
  
### <a name="example"></a><span data-ttu-id="e0613-114">示例</span><span class="sxs-lookup"><span data-stu-id="e0613-114">Example</span></span>  
 <span data-ttu-id="e0613-115">此示例对 `Contact` 和 `SalesOrderHeader` 表执行联接，并对结果按联系人 ID 进行分组。</span><span class="sxs-lookup"><span data-stu-id="e0613-115">This example performs a join over the `Contact` and `SalesOrderHeader` tables, grouping the results by contact ID.</span></span>  
  
 [!code-csharp[DP LINQ to DataSet Examples#JoinWithGroupedResults_MQ](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#joinwithgroupedresults_mq)]
 [!code-vb[DP LINQ to DataSet Examples#JoinWithGroupedResults_MQ](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#joinwithgroupedresults_mq)]  
  
## <a name="see-also"></a><span data-ttu-id="e0613-116">请参阅</span><span class="sxs-lookup"><span data-stu-id="e0613-116">See also</span></span>

- [<span data-ttu-id="e0613-117">将数据加载到数据集中</span><span class="sxs-lookup"><span data-stu-id="e0613-117">Loading Data Into a DataSet</span></span>](loading-data-into-a-dataset.md)
- [<span data-ttu-id="e0613-118">LINQ to DataSet 示例</span><span class="sxs-lookup"><span data-stu-id="e0613-118">LINQ to DataSet Examples</span></span>](linq-to-dataset-examples.md)
- [<span data-ttu-id="e0613-119">标准查询运算符概述 (C#)</span><span class="sxs-lookup"><span data-stu-id="e0613-119">Standard Query Operators Overview (C#)</span></span>](../../../csharp/programming-guide/concepts/linq/standard-query-operators-overview.md)
- [<span data-ttu-id="e0613-120">标准查询运算符概述 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="e0613-120">Standard Query Operators Overview (Visual Basic)</span></span>](../../../visual-basic/programming-guide/concepts/linq/standard-query-operators-overview.md)
- [<span data-ttu-id="e0613-121">联接示例</span><span class="sxs-lookup"><span data-stu-id="e0613-121">Join Samples</span></span>](https://go.microsoft.com/fwlink/?LinkId=187357)
- [<span data-ttu-id="e0613-122">数据集示例</span><span class="sxs-lookup"><span data-stu-id="e0613-122">Dataset Samples</span></span>](https://go.microsoft.com/fwlink/?LinkId=187358)
