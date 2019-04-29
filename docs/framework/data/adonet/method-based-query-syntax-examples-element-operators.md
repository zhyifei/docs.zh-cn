---
title: 基于方法的查询语法示例：元素运算符 (LINQ to DataSet)
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: eedf2fbd-f407-4f62-bb1a-c00eb001b1dd
ms.openlocfilehash: 49a2665240f5f35e0d4937e55c39eccf04b1444d
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "61772159"
---
# <a name="method-based-query-syntax-examples-element-operators-linq-to-dataset"></a><span data-ttu-id="e691e-102">基于方法的查询语法示例：元素运算符 (LINQ to DataSet)</span><span class="sxs-lookup"><span data-stu-id="e691e-102">Method-Based Query Syntax Examples: Element Operators (LINQ to DataSet)</span></span>
<span data-ttu-id="e691e-103">本主题中的示例演示如何使用 <xref:System.Linq.Enumerable.First%2A> 和 <xref:System.Linq.Enumerable.ElementAt%2A> 方法以便使用查询表达式语法从 <xref:System.Data.DataRow> 中获取 <xref:System.Data.DataSet> 元素。</span><span class="sxs-lookup"><span data-stu-id="e691e-103">The examples in this topic demonstrate how to use the <xref:System.Linq.Enumerable.First%2A> and <xref:System.Linq.Enumerable.ElementAt%2A> methods to get <xref:System.Data.DataRow> elements from a <xref:System.Data.DataSet> using the query expression syntax.</span></span>  
  
 <span data-ttu-id="e691e-104">`FillDataSet`中指定这些示例中使用的方法[加载数据到数据集](../../../../docs/framework/data/adonet/loading-data-into-a-dataset.md)。</span><span class="sxs-lookup"><span data-stu-id="e691e-104">The `FillDataSet` method used in these examples is specified in [Loading Data Into a DataSet](../../../../docs/framework/data/adonet/loading-data-into-a-dataset.md).</span></span>  
  
 <span data-ttu-id="e691e-105">本主题中的示例使用 AdventureWorks 示例数据库中的 Contact、Address、Product、SalesOrderHeader 和 SalesOrderDetail 表。</span><span class="sxs-lookup"><span data-stu-id="e691e-105">The examples in this topic use the Contact, Address, Product, SalesOrderHeader, and SalesOrderDetail tables in the AdventureWorks sample database.</span></span>  
  
 <span data-ttu-id="e691e-106">本主题中的示例使用以下`using` / `Imports`语句：</span><span class="sxs-lookup"><span data-stu-id="e691e-106">The examples in this topic use the following `using`/`Imports` statements:</span></span>  
  
[!code-csharp[DP LINQ to DataSet Examples#ImportsUsing](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#importsusing)]   
[!code-vb[DP LINQ to DataSet Examples#ImportsUsing](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#importsusing)]     

 <span data-ttu-id="e691e-107">有关详细信息，请参阅[如何：在 Visual Studio 中创建 LINQ to DataSet 项目](../../../../docs/framework/data/adonet/how-to-create-a-linq-to-dataset-project-in-vs.md)。</span><span class="sxs-lookup"><span data-stu-id="e691e-107">For more information, see [How to: Create a LINQ to DataSet Project In Visual Studio](../../../../docs/framework/data/adonet/how-to-create-a-linq-to-dataset-project-in-vs.md).</span></span>  
  
## <a name="elementat"></a><span data-ttu-id="e691e-108">ElementAt</span><span class="sxs-lookup"><span data-stu-id="e691e-108">ElementAt</span></span>  
  
### <a name="example"></a><span data-ttu-id="e691e-109">示例</span><span class="sxs-lookup"><span data-stu-id="e691e-109">Example</span></span>  
 <span data-ttu-id="e691e-110">此示例使用 <xref:System.Linq.Enumerable.ElementAt%2A> 方法检索 `PostalCode` == "M4B 1V7" 的第五个地址。</span><span class="sxs-lookup"><span data-stu-id="e691e-110">This example uses the <xref:System.Linq.Enumerable.ElementAt%2A> method to retrieve the fifth address where `PostalCode` == "M4B 1V7".</span></span>  
  
[!code-csharp[DP LINQ to DataSet Examples#ElementAt](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#elementat)]   
[!code-vb[DP LINQ to DataSet Examples#ElementAt](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#elementat)]     
  
## <a name="first"></a><span data-ttu-id="e691e-111">First</span><span class="sxs-lookup"><span data-stu-id="e691e-111">First</span></span>  
  
### <a name="example"></a><span data-ttu-id="e691e-112">示例</span><span class="sxs-lookup"><span data-stu-id="e691e-112">Example</span></span>  
 <span data-ttu-id="e691e-113">此示例使用 <xref:System.Linq.Enumerable.First%2A> 方法返回名字为“Brooke”的第一个联系人。</span><span class="sxs-lookup"><span data-stu-id="e691e-113">This example uses the <xref:System.Linq.Enumerable.First%2A> method to return the first contact whose first name is 'Brooke'.</span></span>  
  
[!code-csharp[DP LINQ to DataSet Examples#FirstSimple](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#firstsimple)]   
[!code-vb[DP LINQ to DataSet Examples#FirstSimple](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#firstsimple)] 
  
## <a name="see-also"></a><span data-ttu-id="e691e-114">请参阅</span><span class="sxs-lookup"><span data-stu-id="e691e-114">See also</span></span>

- [<span data-ttu-id="e691e-115">将数据加载到数据集中</span><span class="sxs-lookup"><span data-stu-id="e691e-115">Loading Data Into a DataSet</span></span>](../../../../docs/framework/data/adonet/loading-data-into-a-dataset.md)
- [<span data-ttu-id="e691e-116">LINQ to DataSet 示例</span><span class="sxs-lookup"><span data-stu-id="e691e-116">LINQ to DataSet Examples</span></span>](../../../../docs/framework/data/adonet/linq-to-dataset-examples.md)
- [<span data-ttu-id="e691e-117">标准查询运算符概述 (C#)</span><span class="sxs-lookup"><span data-stu-id="e691e-117">Standard Query Operators Overview (C#)</span></span>](../../../csharp/programming-guide/concepts/linq/standard-query-operators-overview.md)
- [<span data-ttu-id="e691e-118">标准查询运算符概述 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="e691e-118">Standard Query Operators Overview (Visual Basic)</span></span>](../../../visual-basic/programming-guide/concepts/linq/standard-query-operators-overview.md)
