---
title: 编程指南 (LINQ to DataSet)
ms.date: 03/30/2017
ms.assetid: 977aedd7-0084-46a0-b56f-345787a55da1
ms.openlocfilehash: 0c6b026d86a898aa52d93833ac3e447d6f6cba11
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/04/2018
ms.locfileid: "43513365"
---
# <a name="programming-guide-linq-to-dataset"></a><span data-ttu-id="b0e21-102">编程指南 (LINQ to DataSet)</span><span class="sxs-lookup"><span data-stu-id="b0e21-102">Programming Guide (LINQ to DataSet)</span></span>
<span data-ttu-id="b0e21-103">本节提供有关使用 [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)] 进行编程的概念性信息和示例。</span><span class="sxs-lookup"><span data-stu-id="b0e21-103">This section provides conceptual information and examples for programming with [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)].</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="b0e21-104">本节内容</span><span class="sxs-lookup"><span data-stu-id="b0e21-104">In This Section</span></span>  
 [<span data-ttu-id="b0e21-105">在 LINQ to DataSet 中查询</span><span class="sxs-lookup"><span data-stu-id="b0e21-105">Queries in LINQ to DataSet</span></span>](../../../../docs/framework/data/adonet/queries-in-linq-to-dataset.md)  
 <span data-ttu-id="b0e21-106">提供有关如何编写 [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)] 查询的信息。</span><span class="sxs-lookup"><span data-stu-id="b0e21-106">Provides information about how to write [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)] queries.</span></span>  
  
 [<span data-ttu-id="b0e21-107">查询数据集</span><span class="sxs-lookup"><span data-stu-id="b0e21-107">Querying DataSets</span></span>](../../../../docs/framework/data/adonet/querying-datasets-linq-to-dataset.md)  
 <span data-ttu-id="b0e21-108">说明如何查询 <xref:System.Data.DataSet> 对象。</span><span class="sxs-lookup"><span data-stu-id="b0e21-108">Describes how to query <xref:System.Data.DataSet> objects.</span></span>  
  
 [<span data-ttu-id="b0e21-109">比较 DataRow</span><span class="sxs-lookup"><span data-stu-id="b0e21-109">Comparing DataRows</span></span>](../../../../docs/framework/data/adonet/comparing-datarows-linq-to-dataset.md)  
 <span data-ttu-id="b0e21-110">说明如何使用 <xref:System.Data.DataRowComparer> 对象来比较数据行。</span><span class="sxs-lookup"><span data-stu-id="b0e21-110">Describes how to use the <xref:System.Data.DataRowComparer> object to compare data rows.</span></span>  
  
 [<span data-ttu-id="b0e21-111">从查询创建数据表</span><span class="sxs-lookup"><span data-stu-id="b0e21-111">Creating a DataTable From a Query</span></span>](../../../../docs/framework/data/adonet/creating-a-datatable-from-a-query-linq-to-dataset.md)  
 <span data-ttu-id="b0e21-112">提供有关创建信息<xref:System.Data.DataTable>从[!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)]通过使用查询<xref:System.Data.DataTableExtensions.CopyToDataTable%2A>方法。</span><span class="sxs-lookup"><span data-stu-id="b0e21-112">Provides information about creating a <xref:System.Data.DataTable> from a [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)] query by using the <xref:System.Data.DataTableExtensions.CopyToDataTable%2A> method.</span></span>  
  
 [<span data-ttu-id="b0e21-113">如何： 实现 CopyToDataTable\<T > 的泛型类型 T 不是 DataRow</span><span class="sxs-lookup"><span data-stu-id="b0e21-113">How to: Implement CopyToDataTable\<T> Where the Generic Type T Is Not a DataRow</span></span>](../../../../docs/framework/data/adonet/implement-copytodatatable-where-type-not-a-datarow.md)  
 <span data-ttu-id="b0e21-114">描述如何实现自定义的 `CopyToDataTable<T>` 方法，其中泛型参数 T 的类型不是 <xref:System.Data.DataRow>。</span><span class="sxs-lookup"><span data-stu-id="b0e21-114">Describes how to implement a custom `CopyToDataTable<T>` method where the generic parameter T is not of type <xref:System.Data.DataRow>.</span></span>  
  
 [<span data-ttu-id="b0e21-115">泛型字段和 SetField 方法</span><span class="sxs-lookup"><span data-stu-id="b0e21-115">Generic Field and SetField Methods</span></span>](../../../../docs/framework/data/adonet/generic-field-and-setfield-methods-linq-to-dataset.md)  
 <span data-ttu-id="b0e21-116">提供有关泛型 <xref:System.Data.DataRowExtensions.Field%2A> 和 <xref:System.Data.DataRowExtensions.SetField%2A> 方法的信息。</span><span class="sxs-lookup"><span data-stu-id="b0e21-116">Provides information about the generic <xref:System.Data.DataRowExtensions.Field%2A> and <xref:System.Data.DataRowExtensions.SetField%2A> methods.</span></span>  
  
 [<span data-ttu-id="b0e21-117">数据绑定和 LINQ to DataSet</span><span class="sxs-lookup"><span data-stu-id="b0e21-117">Data Binding and LINQ to DataSet</span></span>](../../../../docs/framework/data/adonet/data-binding-and-linq-to-dataset.md)  
 <span data-ttu-id="b0e21-118">说明使用 <xref:System.Data.DataView> 对象的数据绑定。</span><span class="sxs-lookup"><span data-stu-id="b0e21-118">Describes databinding using the <xref:System.Data.DataView> object.</span></span>  
  
 [<span data-ttu-id="b0e21-119">调试 LINQ to DataSet 查询</span><span class="sxs-lookup"><span data-stu-id="b0e21-119">Debugging LINQ to DataSet Queries</span></span>](../../../../docs/framework/data/adonet/debugging-linq-to-dataset-queries.md)  
 <span data-ttu-id="b0e21-120">提供有关调试和故障排除信息[!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)]查询。</span><span class="sxs-lookup"><span data-stu-id="b0e21-120">Provides information about debugging and troubleshooting [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)] queries.</span></span>  
  
 [<span data-ttu-id="b0e21-121">安全性</span><span class="sxs-lookup"><span data-stu-id="b0e21-121">Security</span></span>](../../../../docs/framework/data/adonet/security-linq-to-dataset.md)  
 <span data-ttu-id="b0e21-122">说明 [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)] 中的安全问题。</span><span class="sxs-lookup"><span data-stu-id="b0e21-122">Describes security issues in [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)].</span></span>  
  
 [<span data-ttu-id="b0e21-123">LINQ to DataSet 示例</span><span class="sxs-lookup"><span data-stu-id="b0e21-123">LINQ to DataSet Examples</span></span>](../../../../docs/framework/data/adonet/linq-to-dataset-examples.md)  
 <span data-ttu-id="b0e21-124">提供使用 [!INCLUDE[vbteclinq](../../../../includes/vbteclinq-md.md)] 运算符的查询示例。</span><span class="sxs-lookup"><span data-stu-id="b0e21-124">Provides query examples that use the [!INCLUDE[vbteclinq](../../../../includes/vbteclinq-md.md)] operators.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="b0e21-125">参考</span><span class="sxs-lookup"><span data-stu-id="b0e21-125">Reference</span></span>  
 <xref:System.Data.DataRowComparer>  
  
 <xref:System.Data.DataRowExtensions>  
  
 <xref:System.Data.DataTableExtensions>  
  
 <xref:System.Data.DataView>  
  
## <a name="see-also"></a><span data-ttu-id="b0e21-126">请参阅</span><span class="sxs-lookup"><span data-stu-id="b0e21-126">See also</span></span>

- [<span data-ttu-id="b0e21-127">LINQ 和 ADO.NET</span><span class="sxs-lookup"><span data-stu-id="b0e21-127">LINQ and ADO.NET</span></span>](linq-and-ado-net.md)  
- [<span data-ttu-id="b0e21-128">语言集成查询 (LINQ)</span><span class="sxs-lookup"><span data-stu-id="b0e21-128">Language Integrated Query (LINQ)</span></span>](../../../csharp/programming-guide/concepts/linq/index.md)
