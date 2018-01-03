---
title: "基于方法的查询语法示例：联接 (LINQ to DataSet)"
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
ms.assetid: 4fd5ed2c-b03a-4054-a3ed-3ddb380d7d9d
caps.latest.revision: "2"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.workload: dotnet
ms.openlocfilehash: c4f5e5d975627377c8d2098e42637076a5e04db5
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="method-based-query-syntax-examples-join-linq-to-dataset"></a><span data-ttu-id="0cad9-102">基于方法的查询语法示例：联接 (LINQ to DataSet)</span><span class="sxs-lookup"><span data-stu-id="0cad9-102">Method-Based Query Syntax Examples: Join (LINQ to DataSet)</span></span>
<span data-ttu-id="0cad9-103">联接是面向相互之间没有可导航关系的数据源（如关系数据库表）的查询中的一项重要操作。</span><span class="sxs-lookup"><span data-stu-id="0cad9-103">Joining is an important operation in queries that target data sources that have no navigable relationships to each other, such as relational database tables.</span></span> <span data-ttu-id="0cad9-104">联接两个数据源就是将一个数据源中的对象与另一个数据源中具有相同公共属性的对象相关联。</span><span class="sxs-lookup"><span data-stu-id="0cad9-104">A join of two data sources is the association of objects in one data source with objects that share a common attribute in the other data source.</span></span> <span data-ttu-id="0cad9-105">有关详细信息，请参阅[标准查询运算符概述](http://msdn.microsoft.com/library/24cda21e-8af8-4632-b519-c404a839b9b2)。</span><span class="sxs-lookup"><span data-stu-id="0cad9-105">For more information, see [Standard Query Operators Overview](http://msdn.microsoft.com/library/24cda21e-8af8-4632-b519-c404a839b9b2).</span></span>  
  
 <span data-ttu-id="0cad9-106">本主题中的示例演示如何使用 <xref:System.Linq.Enumerable.Join%2A> 方法以便使用该方法的查询语法来查询 <xref:System.Data.DataSet>。</span><span class="sxs-lookup"><span data-stu-id="0cad9-106">The examples in this topic demonstrate how to use the <xref:System.Linq.Enumerable.Join%2A> method to query a <xref:System.Data.DataSet> using the method query syntax.</span></span>  
  
 <span data-ttu-id="0cad9-107">`FillDataSet`中指定这些示例中使用的方法[加载数据到数据集](../../../../docs/framework/data/adonet/loading-data-into-a-dataset.md)。</span><span class="sxs-lookup"><span data-stu-id="0cad9-107">The `FillDataSet` method used in these examples is specified in [Loading Data Into a DataSet](../../../../docs/framework/data/adonet/loading-data-into-a-dataset.md).</span></span>  
  
 <span data-ttu-id="0cad9-108">本主题中的示例使用 AdventureWorks 示例数据库中的 Contact、Address、Product、SalesOrderHeader 和 SalesOrderDetail 表。</span><span class="sxs-lookup"><span data-stu-id="0cad9-108">The examples in this topic use the Contact, Address, Product, SalesOrderHeader, and SalesOrderDetail tables in the AdventureWorks sample database.</span></span>  
  
 <span data-ttu-id="0cad9-109">本主题中的示例使用以下`using` / `Imports`语句：</span><span class="sxs-lookup"><span data-stu-id="0cad9-109">The examples in this topic use the following `using`/`Imports` statements:</span></span>  
  
 [!code-csharp[DP LINQ to DataSet Examples#ImportsUsing](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#importsusing)]
 [!code-vb[DP LINQ to DataSet Examples#ImportsUsing](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#importsusing)]  
  
 <span data-ttu-id="0cad9-110">有关详细信息，请参阅[如何： 创建 LINQ to DataSet 项目在 Visual Studio 中](../../../../docs/framework/data/adonet/how-to-create-a-linq-to-dataset-project-in-vs.md)。</span><span class="sxs-lookup"><span data-stu-id="0cad9-110">For more information, see [How to: Create a LINQ to DataSet Project In Visual Studio](../../../../docs/framework/data/adonet/how-to-create-a-linq-to-dataset-project-in-vs.md).</span></span>  
  
## <a name="join"></a><span data-ttu-id="0cad9-111">联接</span><span class="sxs-lookup"><span data-stu-id="0cad9-111">Join</span></span>  
  
### <a name="example"></a><span data-ttu-id="0cad9-112">示例</span><span class="sxs-lookup"><span data-stu-id="0cad9-112">Example</span></span>  
 <span data-ttu-id="0cad9-113">此示例对 `Contact` 和 `SalesOrderHeader` 表执行联接。</span><span class="sxs-lookup"><span data-stu-id="0cad9-113">This example performs a join over the `Contact` and `SalesOrderHeader` tables.</span></span>  
  
 [!code-csharp[DP LINQ to DataSet Examples#JoinSimple_MQ](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#joinsimple_mq)]
 [!code-vb[DP LINQ to DataSet Examples#JoinSimple_MQ](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#joinsimple_mq)]  
  
### <a name="example"></a><span data-ttu-id="0cad9-114">示例</span><span class="sxs-lookup"><span data-stu-id="0cad9-114">Example</span></span>  
 <span data-ttu-id="0cad9-115">此示例对 `Contact` 和 `SalesOrderHeader` 表执行联接，并对结果按联系人 ID 进行分组。</span><span class="sxs-lookup"><span data-stu-id="0cad9-115">This example performs a join over the `Contact` and `SalesOrderHeader` tables, grouping the results by contact ID.</span></span>  
  
 [!code-csharp[DP LINQ to DataSet Examples#JoinWithGroupedResults_MQ](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#joinwithgroupedresults_mq)]
 [!code-vb[DP LINQ to DataSet Examples#JoinWithGroupedResults_MQ](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#joinwithgroupedresults_mq)]  
  
## <a name="see-also"></a><span data-ttu-id="0cad9-116">请参阅</span><span class="sxs-lookup"><span data-stu-id="0cad9-116">See Also</span></span>  
 [<span data-ttu-id="0cad9-117">将数据加载到数据集中</span><span class="sxs-lookup"><span data-stu-id="0cad9-117">Loading Data Into a DataSet</span></span>](../../../../docs/framework/data/adonet/loading-data-into-a-dataset.md)  
 [<span data-ttu-id="0cad9-118">LINQ to DataSet 示例</span><span class="sxs-lookup"><span data-stu-id="0cad9-118">LINQ to DataSet Examples</span></span>](../../../../docs/framework/data/adonet/linq-to-dataset-examples.md)  
 [<span data-ttu-id="0cad9-119">标准查询运算符概述</span><span class="sxs-lookup"><span data-stu-id="0cad9-119">Standard Query Operators Overview</span></span>](http://msdn.microsoft.com/library/24cda21e-8af8-4632-b519-c404a839b9b2)  
 [<span data-ttu-id="0cad9-120">加入示例</span><span class="sxs-lookup"><span data-stu-id="0cad9-120">Join Samples</span></span>](http://go.microsoft.com/fwlink/?LinkId=187357)  
 [<span data-ttu-id="0cad9-121">数据集示例</span><span class="sxs-lookup"><span data-stu-id="0cad9-121">Dataset Samples</span></span>](http://go.microsoft.com/fwlink/?LinkId=187358)
