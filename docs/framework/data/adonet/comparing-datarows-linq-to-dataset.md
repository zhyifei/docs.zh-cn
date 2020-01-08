---
title: 比较 DataRow (LINQ to DataSet)
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 8fe0eadf-297b-487c-8d4b-7816753c2883
ms.openlocfilehash: fbd642fb3da6d664df9076b8d7576865d516727e
ms.sourcegitcommit: 7bc6887ab658550baa78f1520ea735838249345e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/03/2020
ms.locfileid: "75634893"
---
# <a name="comparing-datarows-linq-to-dataset"></a><span data-ttu-id="fddb2-102">比较 DataRow (LINQ to DataSet)</span><span class="sxs-lookup"><span data-stu-id="fddb2-102">Comparing DataRows (LINQ to DataSet)</span></span>
<span data-ttu-id="fddb2-103">语言集成查询（LINQ）定义了各种集运算符来比较源元素，以确定它们是否相等。</span><span class="sxs-lookup"><span data-stu-id="fddb2-103">Language-Integrated Query (LINQ) defines various set operators to compare source elements to see if they are equal.</span></span> <span data-ttu-id="fddb2-104">LINQ 提供以下集运算符：</span><span class="sxs-lookup"><span data-stu-id="fddb2-104">LINQ provides the following set operators:</span></span>  
  
- <xref:System.Linq.Enumerable.Distinct%2A>  
  
- <xref:System.Linq.Enumerable.Union%2A>  
  
- <xref:System.Linq.Enumerable.Intersect%2A>  
  
- <xref:System.Linq.Enumerable.Except%2A>  
  
 <span data-ttu-id="fddb2-105">这些运算符通过对每个元素集合调用 <xref:System.Collections.Generic.IEqualityComparer%601.GetHashCode%2A> 和 <xref:System.Collections.Generic.IEqualityComparer%601.Equals%2A> 方法来比较源元素。</span><span class="sxs-lookup"><span data-stu-id="fddb2-105">These operators compare source elements by calling the <xref:System.Collections.Generic.IEqualityComparer%601.GetHashCode%2A> and <xref:System.Collections.Generic.IEqualityComparer%601.Equals%2A> methods on each collection of elements.</span></span> <span data-ttu-id="fddb2-106">对于 <xref:System.Data.DataRow>，这些运算符执行引用比较，在对表格格式数据执行集合操作的情况下，这通常不是理想的行为。</span><span class="sxs-lookup"><span data-stu-id="fddb2-106">In the case of a <xref:System.Data.DataRow>, these operators perform a reference comparison, which is generally not the ideal behavior for set operations over tabular data.</span></span> <span data-ttu-id="fddb2-107">对于集合运算，通常需要确定元素值而不是元素引用是否相等。</span><span class="sxs-lookup"><span data-stu-id="fddb2-107">For set operations, you usually want to determine whether the element values are equal and not the element references.</span></span> <span data-ttu-id="fddb2-108">因此，<xref:System.Data.DataRowComparer> 类已添加到 LINQ to DataSet 中。</span><span class="sxs-lookup"><span data-stu-id="fddb2-108">Therefore, the <xref:System.Data.DataRowComparer> class has been added to LINQ to DataSet.</span></span> <span data-ttu-id="fddb2-109">此类可用于比较行值。</span><span class="sxs-lookup"><span data-stu-id="fddb2-109">This class can be used to compare row values.</span></span>  
  
 <span data-ttu-id="fddb2-110"><xref:System.Data.DataRowComparer> 类包含 <xref:System.Data.DataRow> 的值比较实现，所以此类可用于设置集合操作，例如 <xref:System.Linq.Enumerable.Distinct%2A>。</span><span class="sxs-lookup"><span data-stu-id="fddb2-110">The <xref:System.Data.DataRowComparer> class contains a value comparison implementation for <xref:System.Data.DataRow>, so this class can be used for set operations such as <xref:System.Linq.Enumerable.Distinct%2A>.</span></span> <span data-ttu-id="fddb2-111">此类不能直接实例化，而必须使用 <xref:System.Data.DataRowComparer.Default%2A> 属性返回 <xref:System.Data.DataRowComparer%601> 的实例。</span><span class="sxs-lookup"><span data-stu-id="fddb2-111">This class cannot be directly instantiated; instead, the <xref:System.Data.DataRowComparer.Default%2A> property must be used to return an instance of the <xref:System.Data.DataRowComparer%601>.</span></span> <span data-ttu-id="fddb2-112">然后调用 <xref:System.Data.DataRowComparer%601.Equals%2A> 方法并作为输入参数传入要进行比较的两个 <xref:System.Data.DataRow> 对象。</span><span class="sxs-lookup"><span data-stu-id="fddb2-112">The <xref:System.Data.DataRowComparer%601.Equals%2A> method is then called and the two <xref:System.Data.DataRow> objects to be compared are passed in as input parameters.</span></span> <span data-ttu-id="fddb2-113">如果两个 <xref:System.Data.DataRowComparer%601.Equals%2A> 对象中排序的列值集合相等，则 `true` 方法返回 <xref:System.Data.DataRow>，否则返回 `false`。</span><span class="sxs-lookup"><span data-stu-id="fddb2-113">The <xref:System.Data.DataRowComparer%601.Equals%2A> method returns `true` if the ordered set of column values in both <xref:System.Data.DataRow> objects are equal; otherwise, `false`.</span></span>  
  
## <a name="example"></a><span data-ttu-id="fddb2-114">示例</span><span class="sxs-lookup"><span data-stu-id="fddb2-114">Example</span></span>  
 <span data-ttu-id="fddb2-115">此示例使用 `Intersect` 返回两个表中都存在的联系人。</span><span class="sxs-lookup"><span data-stu-id="fddb2-115">This example uses `Intersect` to return contacts that appear in both tables.</span></span>  
  
 [!code-csharp[DP LINQ to DataSet Examples#Intersect2](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#intersect2)]
 [!code-vb[DP LINQ to DataSet Examples#Intersect2](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#intersect2)]  
  
### <a name="example"></a><span data-ttu-id="fddb2-116">示例</span><span class="sxs-lookup"><span data-stu-id="fddb2-116">Example</span></span>  
 <span data-ttu-id="fddb2-117">下面的示例比较两个行并获取它们的哈希代码。</span><span class="sxs-lookup"><span data-stu-id="fddb2-117">The following example compares two rows and gets their hash codes.</span></span>  
  
 [!code-vb[DP LINQ to DataSet Examples#CompareDifferentRows](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#comparedifferentrows)]  
  
## <a name="see-also"></a><span data-ttu-id="fddb2-118">另请参阅</span><span class="sxs-lookup"><span data-stu-id="fddb2-118">See also</span></span>

- <xref:System.Data.DataRowComparer>
- [<span data-ttu-id="fddb2-119">将数据加载到数据集中</span><span class="sxs-lookup"><span data-stu-id="fddb2-119">Loading Data Into a DataSet</span></span>](loading-data-into-a-dataset.md)
- [<span data-ttu-id="fddb2-120">LINQ to DataSet 示例</span><span class="sxs-lookup"><span data-stu-id="fddb2-120">LINQ to DataSet Examples</span></span>](linq-to-dataset-examples.md)
