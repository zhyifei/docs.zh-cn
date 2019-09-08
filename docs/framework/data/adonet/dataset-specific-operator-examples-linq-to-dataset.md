---
title: 数据集特定的运算符示例 (LINQ to DataSet)
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 8fdd64af-6ad0-46cd-91c8-dbe26620eeb1
ms.openlocfilehash: 6a9dc82e0bb065b455c0208daaf2d28a74cd7e34
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/07/2019
ms.locfileid: "70784199"
---
# <a name="dataset-specific-operator-examples-linq-to-dataset"></a><span data-ttu-id="c5b83-102">数据集特定的运算符示例 (LINQ to DataSet)</span><span class="sxs-lookup"><span data-stu-id="c5b83-102">DataSet-Specific Operator Examples (LINQ to DataSet)</span></span>
<span data-ttu-id="c5b83-103">本主题中的示例演示如何使用 <xref:System.Data.DataTableExtensions.CopyToDataTable%2A> 方法和 <xref:System.Data.DataRowComparer> 类。</span><span class="sxs-lookup"><span data-stu-id="c5b83-103">The examples in this topic demonstrate how to use the <xref:System.Data.DataTableExtensions.CopyToDataTable%2A> method and the <xref:System.Data.DataRowComparer> class.</span></span>  
  
 <span data-ttu-id="c5b83-104">在`FillDataSet`这些示例中使用的方法是在将[数据加载到数据集](loading-data-into-a-dataset.md)时指定的。</span><span class="sxs-lookup"><span data-stu-id="c5b83-104">The `FillDataSet` method used in these examples is specified in [Loading Data Into a DataSet](loading-data-into-a-dataset.md).</span></span>  
  
 <span data-ttu-id="c5b83-105">本主题中的示例使用 AdventureWorks 示例数据库中的 Contact、Address、Product、SalesOrderHeader 和 SalesOrderDetail 表。</span><span class="sxs-lookup"><span data-stu-id="c5b83-105">The examples in this topic use the Contact, Address, Product, SalesOrderHeader, and SalesOrderDetail tables in the AdventureWorks sample database.</span></span>  
  
 <span data-ttu-id="c5b83-106">本主题中的示例使用以下`using` / `Imports`语句：</span><span class="sxs-lookup"><span data-stu-id="c5b83-106">The examples in this topic use the following `using`/`Imports` statements:</span></span>  
  
 [!code-csharp[DP LINQ to DataSet Examples#ImportsUsing](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#importsusing)]
 [!code-vb[DP LINQ to DataSet Examples#ImportsUsing](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#importsusing)]  
  
 <span data-ttu-id="c5b83-107">有关详细信息，请参阅[如何：在 Visual Studio](how-to-create-a-linq-to-dataset-project-in-vs.md)中创建 LINQ to DataSet 项目。</span><span class="sxs-lookup"><span data-stu-id="c5b83-107">For more information, see [How to: Create a LINQ to DataSet Project In Visual Studio](how-to-create-a-linq-to-dataset-project-in-vs.md).</span></span>  
  
## <a name="copytodatatable"></a><span data-ttu-id="c5b83-108">CopyToDataTable</span><span class="sxs-lookup"><span data-stu-id="c5b83-108">CopyToDataTable</span></span>  
  
### <a name="example"></a><span data-ttu-id="c5b83-109">示例</span><span class="sxs-lookup"><span data-stu-id="c5b83-109">Example</span></span>  
 <span data-ttu-id="c5b83-110">此示例通过使用 <xref:System.Data.DataTable> 方法加载包含查询结果的 <xref:System.Data.DataTableExtensions.CopyToDataTable%2A>。</span><span class="sxs-lookup"><span data-stu-id="c5b83-110">This example loads a <xref:System.Data.DataTable> with query results by using the <xref:System.Data.DataTableExtensions.CopyToDataTable%2A> method.</span></span>  
  
 [!code-csharp[DP LINQ to DataSet Examples#LoadDataTableWithQueryResults](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#loaddatatablewithqueryresults)]
 [!code-vb[DP LINQ to DataSet Examples#LoadDataTableWithQueryResults](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#loaddatatablewithqueryresults)]  
  
## <a name="datarowcomparer"></a><span data-ttu-id="c5b83-111">DataRowComparer</span><span class="sxs-lookup"><span data-stu-id="c5b83-111">DataRowComparer</span></span>  
  
### <a name="example"></a><span data-ttu-id="c5b83-112">示例</span><span class="sxs-lookup"><span data-stu-id="c5b83-112">Example</span></span>  
 <span data-ttu-id="c5b83-113">此示例通过使用 <xref:System.Data.DataRowComparer> 比较两个不同的数据行。</span><span class="sxs-lookup"><span data-stu-id="c5b83-113">This example compares two different data rows by using <xref:System.Data.DataRowComparer>.</span></span>  
  
 [!code-csharp[DP LINQ to DataSet Examples#CompareDifferentDataRows](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#comparedifferentdatarows)]  
  
## <a name="see-also"></a><span data-ttu-id="c5b83-114">请参阅</span><span class="sxs-lookup"><span data-stu-id="c5b83-114">See also</span></span>

- [<span data-ttu-id="c5b83-115">将数据加载到数据集中</span><span class="sxs-lookup"><span data-stu-id="c5b83-115">Loading Data Into a DataSet</span></span>](loading-data-into-a-dataset.md)
- [<span data-ttu-id="c5b83-116">LINQ to DataSet 示例</span><span class="sxs-lookup"><span data-stu-id="c5b83-116">LINQ to DataSet Examples</span></span>](linq-to-dataset-examples.md)
