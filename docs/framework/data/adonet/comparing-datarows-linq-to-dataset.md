---
title: "比较 DataRow (LINQ to DataSet)"
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
ms.assetid: 8fe0eadf-297b-487c-8d4b-7816753c2883
caps.latest.revision: "2"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: 9f17a73d2d6349d4fc35668d7251877034e5e29f
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="comparing-datarows-linq-to-dataset"></a><span data-ttu-id="829ee-102">比较 DataRow (LINQ to DataSet)</span><span class="sxs-lookup"><span data-stu-id="829ee-102">Comparing DataRows (LINQ to DataSet)</span></span>
[!INCLUDE[vbteclinqext](../../../../includes/vbteclinqext-md.md)]<span data-ttu-id="829ee-103"> 定义多种用于比较源元素的集合运算符以查看它们是否相等。</span><span class="sxs-lookup"><span data-stu-id="829ee-103"> defines various set operators to compare source elements to see if they are equal.</span></span> [!INCLUDE[vbteclinq](../../../../includes/vbteclinq-md.md)]<span data-ttu-id="829ee-104"> 提供下面的集合运算符：</span><span class="sxs-lookup"><span data-stu-id="829ee-104"> provides the following set operators:</span></span>  
  
-   <xref:System.Linq.Enumerable.Distinct%2A>  
  
-   <xref:System.Linq.Enumerable.Union%2A>  
  
-   <xref:System.Linq.Enumerable.Intersect%2A>  
  
-   <xref:System.Linq.Enumerable.Except%2A>  
  
 <span data-ttu-id="829ee-105">这些运算符通过对每个元素集合调用 <xref:System.Collections.Generic.IEqualityComparer%601.GetHashCode%2A> 和 <xref:System.Collections.Generic.IEqualityComparer%601.Equals%2A> 方法来比较源元素。</span><span class="sxs-lookup"><span data-stu-id="829ee-105">These operators compare source elements by calling the <xref:System.Collections.Generic.IEqualityComparer%601.GetHashCode%2A> and <xref:System.Collections.Generic.IEqualityComparer%601.Equals%2A> methods on each collection of elements.</span></span> <span data-ttu-id="829ee-106">对于 <xref:System.Data.DataRow>，这些运算符执行引用比较，在对表格格式数据执行集合操作的情况下，这通常不是理想的行为。</span><span class="sxs-lookup"><span data-stu-id="829ee-106">In the case of a <xref:System.Data.DataRow>, these operators perform a reference comparison, which is generally not the ideal behavior for set operations over tabular data.</span></span> <span data-ttu-id="829ee-107">对于集合运算，通常需要确定元素值而不是元素引用是否相等。</span><span class="sxs-lookup"><span data-stu-id="829ee-107">For set operations, you usually want to determine whether the element values are equal and not the element references.</span></span> <span data-ttu-id="829ee-108">因此，向 <xref:System.Data.DataRowComparer> 中添加了 [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)] 类。</span><span class="sxs-lookup"><span data-stu-id="829ee-108">Therefore, the <xref:System.Data.DataRowComparer> class has been added to [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)].</span></span> <span data-ttu-id="829ee-109">此类可用于比较行值。</span><span class="sxs-lookup"><span data-stu-id="829ee-109">This class can be used to compare row values.</span></span>  
  
 <span data-ttu-id="829ee-110"><xref:System.Data.DataRowComparer> 类包含 <xref:System.Data.DataRow> 的值比较实现，所以此类可用于设置集合操作，例如 <xref:System.Linq.Enumerable.Distinct%2A>。</span><span class="sxs-lookup"><span data-stu-id="829ee-110">The <xref:System.Data.DataRowComparer> class contains a value comparison implementation for <xref:System.Data.DataRow>, so this class can be used for set operations such as <xref:System.Linq.Enumerable.Distinct%2A>.</span></span> <span data-ttu-id="829ee-111">此类不能直接实例化，而必须使用 <xref:System.Data.DataRowComparer.Default%2A> 属性返回 <xref:System.Data.DataRowComparer%601> 的实例。</span><span class="sxs-lookup"><span data-stu-id="829ee-111">This class cannot be directly instantiated; instead, the <xref:System.Data.DataRowComparer.Default%2A> property must be used to return an instance of the <xref:System.Data.DataRowComparer%601>.</span></span> <span data-ttu-id="829ee-112">然后调用 <xref:System.Data.DataRowComparer%601.Equals%2A> 方法并作为输入参数传入要进行比较的两个 <xref:System.Data.DataRow> 对象。</span><span class="sxs-lookup"><span data-stu-id="829ee-112">The <xref:System.Data.DataRowComparer%601.Equals%2A> method is then called and the two <xref:System.Data.DataRow> objects to be compared are passed in as input parameters.</span></span> <span data-ttu-id="829ee-113">如果两个 <xref:System.Data.DataRowComparer%601.Equals%2A> 对象中排序的列值集合相等，则 `true` 方法返回 <xref:System.Data.DataRow>，否则返回 `false`。</span><span class="sxs-lookup"><span data-stu-id="829ee-113">The <xref:System.Data.DataRowComparer%601.Equals%2A> method returns `true` if the ordered set of column values in both <xref:System.Data.DataRow> objects are equal; otherwise, `false`.</span></span>  
  
## <a name="example"></a><span data-ttu-id="829ee-114">示例</span><span class="sxs-lookup"><span data-stu-id="829ee-114">Example</span></span>  
 <span data-ttu-id="829ee-115">此示例使用 `Intersect` 返回两个表中都存在的联系人。</span><span class="sxs-lookup"><span data-stu-id="829ee-115">This example uses `Intersect` to return contacts that appear in both tables.</span></span>  
  
 [!code-csharp[DP LINQ to DataSet Examples#Intersect2](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#intersect2)]
 [!code-vb[DP LINQ to DataSet Examples#Intersect2](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#intersect2)]  
  
### <a name="example"></a><span data-ttu-id="829ee-116">示例</span><span class="sxs-lookup"><span data-stu-id="829ee-116">Example</span></span>  
 <span data-ttu-id="829ee-117">下面的示例比较两个行并获取它们的哈希代码。</span><span class="sxs-lookup"><span data-stu-id="829ee-117">The following example compares two rows and gets their hash codes.</span></span>  
  
 [!code-vb[DP LINQ to DataSet Examples#CompareDifferentRows](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#comparedifferentrows)]  
  
## <a name="see-also"></a><span data-ttu-id="829ee-118">另请参阅</span><span class="sxs-lookup"><span data-stu-id="829ee-118">See Also</span></span>  
 <xref:System.Data.DataRowComparer>  
 [<span data-ttu-id="829ee-119">数据加载到数据集</span><span class="sxs-lookup"><span data-stu-id="829ee-119">Loading Data Into a DataSet</span></span>](../../../../docs/framework/data/adonet/loading-data-into-a-dataset.md)  
 [<span data-ttu-id="829ee-120">LINQ to DataSet 示例</span><span class="sxs-lookup"><span data-stu-id="829ee-120">LINQ to DataSet Examples</span></span>](../../../../docs/framework/data/adonet/linq-to-dataset-examples.md)
