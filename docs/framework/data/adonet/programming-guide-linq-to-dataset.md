---
title: "编程指南 (LINQ to DataSet)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 977aedd7-0084-46a0-b56f-345787a55da1
caps.latest.revision: "3"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.workload: dotnet
ms.openlocfilehash: 298ff0c6bfc5bc251483de8e90e3a394a2337369
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="programming-guide-linq-to-dataset"></a><span data-ttu-id="d8eee-102">编程指南 (LINQ to DataSet)</span><span class="sxs-lookup"><span data-stu-id="d8eee-102">Programming Guide (LINQ to DataSet)</span></span>
<span data-ttu-id="d8eee-103">本节提供有关使用 [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)] 进行编程的概念性信息和示例。</span><span class="sxs-lookup"><span data-stu-id="d8eee-103">This section provides conceptual information and examples for programming with [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)].</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="d8eee-104">本节内容</span><span class="sxs-lookup"><span data-stu-id="d8eee-104">In This Section</span></span>  
 [<span data-ttu-id="d8eee-105">在 LINQ to DataSet 中查询</span><span class="sxs-lookup"><span data-stu-id="d8eee-105">Queries in LINQ to DataSet</span></span>](../../../../docs/framework/data/adonet/queries-in-linq-to-dataset.md)  
 <span data-ttu-id="d8eee-106">提供有关如何编写 [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)] 查询的信息。</span><span class="sxs-lookup"><span data-stu-id="d8eee-106">Provides information about how to write [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)] queries.</span></span>  
  
 [<span data-ttu-id="d8eee-107">查询数据集</span><span class="sxs-lookup"><span data-stu-id="d8eee-107">Querying DataSets</span></span>](../../../../docs/framework/data/adonet/querying-datasets-linq-to-dataset.md)  
 <span data-ttu-id="d8eee-108">说明如何查询 <xref:System.Data.DataSet> 对象。</span><span class="sxs-lookup"><span data-stu-id="d8eee-108">Describes how to query <xref:System.Data.DataSet> objects.</span></span>  
  
 [<span data-ttu-id="d8eee-109">比较 DataRow</span><span class="sxs-lookup"><span data-stu-id="d8eee-109">Comparing DataRows</span></span>](../../../../docs/framework/data/adonet/comparing-datarows-linq-to-dataset.md)  
 <span data-ttu-id="d8eee-110">说明如何使用 <xref:System.Data.DataRowComparer> 对象来比较数据行。</span><span class="sxs-lookup"><span data-stu-id="d8eee-110">Describes how to use the <xref:System.Data.DataRowComparer> object to compare data rows.</span></span>  
  
 [<span data-ttu-id="d8eee-111">从查询创建数据表</span><span class="sxs-lookup"><span data-stu-id="d8eee-111">Creating a DataTable From a Query</span></span>](../../../../docs/framework/data/adonet/creating-a-datatable-from-a-query-linq-to-dataset.md)  
 <span data-ttu-id="d8eee-112">提供有关创建信息<xref:System.Data.DataTable>从[!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)]通过使用查询<xref:System.Data.DataTableExtensions.CopyToDataTable%2A>方法。</span><span class="sxs-lookup"><span data-stu-id="d8eee-112">Provides information about creating a <xref:System.Data.DataTable> from a [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)] query by using the <xref:System.Data.DataTableExtensions.CopyToDataTable%2A> method.</span></span>  
  
 [<span data-ttu-id="d8eee-113">如何： 实现 CopyToDataTable\<T > 的泛型类型 T 不是 DataRow</span><span class="sxs-lookup"><span data-stu-id="d8eee-113">How to: Implement CopyToDataTable\<T> Where the Generic Type T Is Not a DataRow</span></span>](../../../../docs/framework/data/adonet/implement-copytodatatable-where-type-not-a-datarow.md)  
 <span data-ttu-id="d8eee-114">描述如何实现自定义的 `CopyToDataTable<T>` 方法，其中泛型参数 T 的类型不是 <xref:System.Data.DataRow>。</span><span class="sxs-lookup"><span data-stu-id="d8eee-114">Describes how to implement a custom `CopyToDataTable<T>` method where the generic parameter T is not of type <xref:System.Data.DataRow>.</span></span>  
  
 [<span data-ttu-id="d8eee-115">泛型字段和 SetField 方法</span><span class="sxs-lookup"><span data-stu-id="d8eee-115">Generic Field and SetField Methods</span></span>](../../../../docs/framework/data/adonet/generic-field-and-setfield-methods-linq-to-dataset.md)  
 <span data-ttu-id="d8eee-116">提供有关泛型 <xref:System.Data.DataRowExtensions.Field%2A> 和 <xref:System.Data.DataRowExtensions.SetField%2A> 方法的信息。</span><span class="sxs-lookup"><span data-stu-id="d8eee-116">Provides information about the generic <xref:System.Data.DataRowExtensions.Field%2A> and <xref:System.Data.DataRowExtensions.SetField%2A> methods.</span></span>  
  
 [<span data-ttu-id="d8eee-117">数据绑定和 LINQ to DataSet</span><span class="sxs-lookup"><span data-stu-id="d8eee-117">Data Binding and LINQ to DataSet</span></span>](../../../../docs/framework/data/adonet/data-binding-and-linq-to-dataset.md)  
 <span data-ttu-id="d8eee-118">说明使用 <xref:System.Data.DataView> 对象的数据绑定。</span><span class="sxs-lookup"><span data-stu-id="d8eee-118">Describes databinding using the <xref:System.Data.DataView> object.</span></span>  
  
 [<span data-ttu-id="d8eee-119">调试 LINQ to DataSet 查询</span><span class="sxs-lookup"><span data-stu-id="d8eee-119">Debugging LINQ to DataSet Queries</span></span>](../../../../docs/framework/data/adonet/debugging-linq-to-dataset-queries.md)  
 <span data-ttu-id="d8eee-120">提供有关调试和故障排除信息[!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)]查询。</span><span class="sxs-lookup"><span data-stu-id="d8eee-120">Provides information about debugging and troubleshooting [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)] queries.</span></span>  
  
 [<span data-ttu-id="d8eee-121">安全性</span><span class="sxs-lookup"><span data-stu-id="d8eee-121">Security</span></span>](../../../../docs/framework/data/adonet/security-linq-to-dataset.md)  
 <span data-ttu-id="d8eee-122">说明 [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)] 中的安全问题。</span><span class="sxs-lookup"><span data-stu-id="d8eee-122">Describes security issues in [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)].</span></span>  
  
 [<span data-ttu-id="d8eee-123">LINQ to DataSet 示例</span><span class="sxs-lookup"><span data-stu-id="d8eee-123">LINQ to DataSet Examples</span></span>](../../../../docs/framework/data/adonet/linq-to-dataset-examples.md)  
 <span data-ttu-id="d8eee-124">提供使用 [!INCLUDE[vbteclinq](../../../../includes/vbteclinq-md.md)] 运算符的查询示例。</span><span class="sxs-lookup"><span data-stu-id="d8eee-124">Provides query examples that use the [!INCLUDE[vbteclinq](../../../../includes/vbteclinq-md.md)] operators.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="d8eee-125">参考</span><span class="sxs-lookup"><span data-stu-id="d8eee-125">Reference</span></span>  
 <xref:System.Data.DataRowComparer>  
  
 <xref:System.Data.DataRowExtensions>  
  
 <xref:System.Data.DataTableExtensions>  
  
 <xref:System.Data.DataView>  
  
## <a name="see-also"></a><span data-ttu-id="d8eee-126">请参阅</span><span class="sxs-lookup"><span data-stu-id="d8eee-126">See Also</span></span>  
 [<span data-ttu-id="d8eee-127">LINQ to ADO.NET</span><span class="sxs-lookup"><span data-stu-id="d8eee-127">LINQ to ADO.NET</span></span>](http://msdn.microsoft.com/en-us/be3297b9-1b54-4d4c-82a8-add0d79c2006)  
 [<span data-ttu-id="d8eee-128">不在生成中： LINQ 常规编程指南</span><span class="sxs-lookup"><span data-stu-id="d8eee-128">NOT IN BUILD: LINQ General Programming Guide</span></span>](http://msdn.microsoft.com/en-us/609c7a6b-cbdd-429d-99f3-78d13d3bc049)  
 [<span data-ttu-id="d8eee-129">LINQ Framework</span><span class="sxs-lookup"><span data-stu-id="d8eee-129">LINQ Framework</span></span>](http://msdn.microsoft.com/en-us/897ea0fc-40db-4694-bbe5-7dd339d5bf94)
