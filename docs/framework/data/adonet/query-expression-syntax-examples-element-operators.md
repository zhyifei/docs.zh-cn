---
title: 查询表达式语法示例：元素运算符 (LINQ to DataSet)
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: ca392dda-16e3-45c7-8d87-12d8d4ee0578
ms.openlocfilehash: 8690e4ec79dbe4b728695b073299ca3d21e7f098
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54632590"
---
# <a name="query-expression-syntax-examples-element-operators-linq-to-dataset"></a><span data-ttu-id="f3556-102">查询表达式语法示例：元素运算符 (LINQ to DataSet)</span><span class="sxs-lookup"><span data-stu-id="f3556-102">Query Expression Syntax Examples: Element Operators (LINQ to DataSet)</span></span>
<span data-ttu-id="f3556-103">本主题中的示例演示如何使用 <xref:System.Linq.Enumerable.First%2A> 和 <xref:System.Linq.Enumerable.ElementAt%2A> 方法以便使用查询表达式语法从 <xref:System.Data.DataRow> 中获取 <xref:System.Data.DataSet> 元素。</span><span class="sxs-lookup"><span data-stu-id="f3556-103">The examples in this topic demonstrate how to use the <xref:System.Linq.Enumerable.First%2A> and <xref:System.Linq.Enumerable.ElementAt%2A> methods to get <xref:System.Data.DataRow> elements from a <xref:System.Data.DataSet> using the query expression syntax.</span></span>  
  
 <span data-ttu-id="f3556-104">`FillDataSet`中指定这些示例中使用的方法[加载数据到数据集](../../../../docs/framework/data/adonet/loading-data-into-a-dataset.md)。</span><span class="sxs-lookup"><span data-stu-id="f3556-104">The `FillDataSet` method used in these examples is specified in [Loading Data Into a DataSet](../../../../docs/framework/data/adonet/loading-data-into-a-dataset.md).</span></span>  
  
 <span data-ttu-id="f3556-105">本主题中的示例使用 AdventureWorks 示例数据库中的 Contact、Address、Product、SalesOrderHeader 和 SalesOrderDetail 表。</span><span class="sxs-lookup"><span data-stu-id="f3556-105">The examples in this topic use the Contact, Address, Product, SalesOrderHeader, and SalesOrderDetail tables in the AdventureWorks sample database.</span></span>  
  
 <span data-ttu-id="f3556-106">本主题中的示例使用以下`using` / `Imports`语句：</span><span class="sxs-lookup"><span data-stu-id="f3556-106">The examples in this topic use the following `using`/`Imports` statements:</span></span>  
  
 [!code-csharp[DP LINQ to DataSet Examples#ImportsUsing](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#importsusing)]
 [!code-vb[DP LINQ to DataSet Examples#ImportsUsing](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#importsusing)]  
  
 <span data-ttu-id="f3556-107">有关详细信息，请参阅[如何：在 Visual Studio 中创建 LINQ to DataSet 项目](../../../../docs/framework/data/adonet/how-to-create-a-linq-to-dataset-project-in-vs.md)。</span><span class="sxs-lookup"><span data-stu-id="f3556-107">For more information, see [How to: Create a LINQ to DataSet Project In Visual Studio](../../../../docs/framework/data/adonet/how-to-create-a-linq-to-dataset-project-in-vs.md).</span></span>  
  
## <a name="elementat"></a><span data-ttu-id="f3556-108">ElementAt</span><span class="sxs-lookup"><span data-stu-id="f3556-108">ElementAt</span></span>  
  
### <a name="example"></a><span data-ttu-id="f3556-109">示例</span><span class="sxs-lookup"><span data-stu-id="f3556-109">Example</span></span>  
 <span data-ttu-id="f3556-110">此示例使用 <xref:System.Linq.Enumerable.ElementAt%2A> 方法检索 `PostalCode` == "M4B 1V7" 的第五个地址。</span><span class="sxs-lookup"><span data-stu-id="f3556-110">This example uses the <xref:System.Linq.Enumerable.ElementAt%2A> method to retrieve the fifth address where `PostalCode` == "M4B 1V7".</span></span>  
  
 [!code-csharp[DP LINQ to DataSet Examples#ElementAt](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#elementat)]
 [!code-vb[DP LINQ to DataSet Examples#ElementAt](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#elementat)]  
  
## <a name="first"></a><span data-ttu-id="f3556-111">First</span><span class="sxs-lookup"><span data-stu-id="f3556-111">First</span></span>  
  
### <a name="example"></a><span data-ttu-id="f3556-112">示例</span><span class="sxs-lookup"><span data-stu-id="f3556-112">Example</span></span>  
 <span data-ttu-id="f3556-113">此示例使用 <xref:System.Linq.Enumerable.First%2A> 方法返回名字为“Brooke”的第一个联系人。</span><span class="sxs-lookup"><span data-stu-id="f3556-113">This example uses the <xref:System.Linq.Enumerable.First%2A> method to return the first contact whose first name is 'Brooke'.</span></span>  
  
 [!code-csharp[DP LINQ to DataSet Examples#FirstSimple](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#firstsimple)]
 [!code-vb[DP LINQ to DataSet Examples#FirstSimple](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#firstsimple)]  
  
## <a name="see-also"></a><span data-ttu-id="f3556-114">请参阅</span><span class="sxs-lookup"><span data-stu-id="f3556-114">See also</span></span>
- [<span data-ttu-id="f3556-115">将数据加载到数据集中</span><span class="sxs-lookup"><span data-stu-id="f3556-115">Loading Data Into a DataSet</span></span>](../../../../docs/framework/data/adonet/loading-data-into-a-dataset.md)
- [<span data-ttu-id="f3556-116">LINQ to DataSet 示例</span><span class="sxs-lookup"><span data-stu-id="f3556-116">LINQ to DataSet Examples</span></span>](../../../../docs/framework/data/adonet/linq-to-dataset-examples.md)
- [<span data-ttu-id="f3556-117">标准查询运算符概述</span><span class="sxs-lookup"><span data-stu-id="f3556-117">Standard Query Operators Overview</span></span>](https://msdn.microsoft.com/library/24cda21e-8af8-4632-b519-c404a839b9b2)
