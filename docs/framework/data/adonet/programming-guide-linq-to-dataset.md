---
title: 编程指南 (LINQ to DataSet)
ms.date: 03/30/2017
ms.assetid: 977aedd7-0084-46a0-b56f-345787a55da1
ms.openlocfilehash: 6f6ab1634769a54bd8dbafe8c9d41b11ff787d50
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54636477"
---
# <a name="programming-guide-linq-to-dataset"></a><span data-ttu-id="cf693-102">编程指南 (LINQ to DataSet)</span><span class="sxs-lookup"><span data-stu-id="cf693-102">Programming Guide (LINQ to DataSet)</span></span>
<span data-ttu-id="cf693-103">本节提供有关使用 [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)] 进行编程的概念性信息和示例。</span><span class="sxs-lookup"><span data-stu-id="cf693-103">This section provides conceptual information and examples for programming with [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)].</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="cf693-104">本节内容</span><span class="sxs-lookup"><span data-stu-id="cf693-104">In This Section</span></span>  
 [<span data-ttu-id="cf693-105">在 LINQ to DataSet 中查询</span><span class="sxs-lookup"><span data-stu-id="cf693-105">Queries in LINQ to DataSet</span></span>](../../../../docs/framework/data/adonet/queries-in-linq-to-dataset.md)  
 <span data-ttu-id="cf693-106">提供有关如何编写 [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)] 查询的信息。</span><span class="sxs-lookup"><span data-stu-id="cf693-106">Provides information about how to write [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)] queries.</span></span>  
  
 [<span data-ttu-id="cf693-107">查询数据集</span><span class="sxs-lookup"><span data-stu-id="cf693-107">Querying DataSets</span></span>](../../../../docs/framework/data/adonet/querying-datasets-linq-to-dataset.md)  
 <span data-ttu-id="cf693-108">说明如何查询 <xref:System.Data.DataSet> 对象。</span><span class="sxs-lookup"><span data-stu-id="cf693-108">Describes how to query <xref:System.Data.DataSet> objects.</span></span>  
  
 [<span data-ttu-id="cf693-109">比较 DataRow</span><span class="sxs-lookup"><span data-stu-id="cf693-109">Comparing DataRows</span></span>](../../../../docs/framework/data/adonet/comparing-datarows-linq-to-dataset.md)  
 <span data-ttu-id="cf693-110">说明如何使用 <xref:System.Data.DataRowComparer> 对象来比较数据行。</span><span class="sxs-lookup"><span data-stu-id="cf693-110">Describes how to use the <xref:System.Data.DataRowComparer> object to compare data rows.</span></span>  
  
 [<span data-ttu-id="cf693-111">从查询创建数据表</span><span class="sxs-lookup"><span data-stu-id="cf693-111">Creating a DataTable From a Query</span></span>](../../../../docs/framework/data/adonet/creating-a-datatable-from-a-query-linq-to-dataset.md)  
 <span data-ttu-id="cf693-112">提供有关创建信息<xref:System.Data.DataTable>从[!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)]通过使用查询<xref:System.Data.DataTableExtensions.CopyToDataTable%2A>方法。</span><span class="sxs-lookup"><span data-stu-id="cf693-112">Provides information about creating a <xref:System.Data.DataTable> from a [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)] query by using the <xref:System.Data.DataTableExtensions.CopyToDataTable%2A> method.</span></span>  
  
 [<span data-ttu-id="cf693-113">如何：实现 CopyToDataTable\<T > 的泛型类型 T 不是 DataRow</span><span class="sxs-lookup"><span data-stu-id="cf693-113">How to: Implement CopyToDataTable\<T> Where the Generic Type T Is Not a DataRow</span></span>](../../../../docs/framework/data/adonet/implement-copytodatatable-where-type-not-a-datarow.md)  
 <span data-ttu-id="cf693-114">描述如何实现自定义的 `CopyToDataTable<T>` 方法，其中泛型参数 T 的类型不是 <xref:System.Data.DataRow>。</span><span class="sxs-lookup"><span data-stu-id="cf693-114">Describes how to implement a custom `CopyToDataTable<T>` method where the generic parameter T is not of type <xref:System.Data.DataRow>.</span></span>  
  
 [<span data-ttu-id="cf693-115">泛型字段和 SetField 方法</span><span class="sxs-lookup"><span data-stu-id="cf693-115">Generic Field and SetField Methods</span></span>](../../../../docs/framework/data/adonet/generic-field-and-setfield-methods-linq-to-dataset.md)  
 <span data-ttu-id="cf693-116">提供有关泛型 <xref:System.Data.DataRowExtensions.Field%2A> 和 <xref:System.Data.DataRowExtensions.SetField%2A> 方法的信息。</span><span class="sxs-lookup"><span data-stu-id="cf693-116">Provides information about the generic <xref:System.Data.DataRowExtensions.Field%2A> and <xref:System.Data.DataRowExtensions.SetField%2A> methods.</span></span>  
  
 [<span data-ttu-id="cf693-117">数据绑定和 LINQ to DataSet</span><span class="sxs-lookup"><span data-stu-id="cf693-117">Data Binding and LINQ to DataSet</span></span>](../../../../docs/framework/data/adonet/data-binding-and-linq-to-dataset.md)  
 <span data-ttu-id="cf693-118">说明使用 <xref:System.Data.DataView> 对象的数据绑定。</span><span class="sxs-lookup"><span data-stu-id="cf693-118">Describes databinding using the <xref:System.Data.DataView> object.</span></span>  
  
 [<span data-ttu-id="cf693-119">调试 LINQ to DataSet 查询</span><span class="sxs-lookup"><span data-stu-id="cf693-119">Debugging LINQ to DataSet Queries</span></span>](../../../../docs/framework/data/adonet/debugging-linq-to-dataset-queries.md)  
 <span data-ttu-id="cf693-120">提供有关调试和故障排除信息[!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)]查询。</span><span class="sxs-lookup"><span data-stu-id="cf693-120">Provides information about debugging and troubleshooting [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)] queries.</span></span>  
  
 [<span data-ttu-id="cf693-121">安全性</span><span class="sxs-lookup"><span data-stu-id="cf693-121">Security</span></span>](../../../../docs/framework/data/adonet/security-linq-to-dataset.md)  
 <span data-ttu-id="cf693-122">说明 [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)] 中的安全问题。</span><span class="sxs-lookup"><span data-stu-id="cf693-122">Describes security issues in [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)].</span></span>  
  
 [<span data-ttu-id="cf693-123">LINQ to DataSet 示例</span><span class="sxs-lookup"><span data-stu-id="cf693-123">LINQ to DataSet Examples</span></span>](../../../../docs/framework/data/adonet/linq-to-dataset-examples.md)  
 <span data-ttu-id="cf693-124">提供使用 [!INCLUDE[vbteclinq](../../../../includes/vbteclinq-md.md)] 运算符的查询示例。</span><span class="sxs-lookup"><span data-stu-id="cf693-124">Provides query examples that use the [!INCLUDE[vbteclinq](../../../../includes/vbteclinq-md.md)] operators.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="cf693-125">参考</span><span class="sxs-lookup"><span data-stu-id="cf693-125">Reference</span></span>  
 <xref:System.Data.DataRowComparer>  
  
 <xref:System.Data.DataRowExtensions>  
  
 <xref:System.Data.DataTableExtensions>  
  
 <xref:System.Data.DataView>  
  
## <a name="see-also"></a><span data-ttu-id="cf693-126">请参阅</span><span class="sxs-lookup"><span data-stu-id="cf693-126">See also</span></span>

- [<span data-ttu-id="cf693-127">LINQ 和 ADO.NET</span><span class="sxs-lookup"><span data-stu-id="cf693-127">LINQ and ADO.NET</span></span>](linq-and-ado-net.md)
- [<span data-ttu-id="cf693-128">语言集成查询 (LINQ)</span><span class="sxs-lookup"><span data-stu-id="cf693-128">Language Integrated Query (LINQ)</span></span>](../../../csharp/programming-guide/concepts/linq/index.md)
