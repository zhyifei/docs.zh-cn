---
title: 编程指南 (LINQ to DataSet)
ms.date: 03/30/2017
ms.assetid: 977aedd7-0084-46a0-b56f-345787a55da1
ms.openlocfilehash: dc13af06cf6c439d739d76904f206ebc50ba3187
ms.sourcegitcommit: 7bc6887ab658550baa78f1520ea735838249345e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/03/2020
ms.locfileid: "75634802"
---
# <a name="programming-guide-linq-to-dataset"></a><span data-ttu-id="4851c-102">编程指南 (LINQ to DataSet)</span><span class="sxs-lookup"><span data-stu-id="4851c-102">Programming Guide (LINQ to DataSet)</span></span>
<span data-ttu-id="4851c-103">本部分提供有关用 LINQ to DataSet 进行编程的概念性信息和示例。</span><span class="sxs-lookup"><span data-stu-id="4851c-103">This section provides conceptual information and examples for programming with LINQ to DataSet.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="4851c-104">本节内容</span><span class="sxs-lookup"><span data-stu-id="4851c-104">In This Section</span></span>  
 [<span data-ttu-id="4851c-105">在 LINQ to DataSet 中查询</span><span class="sxs-lookup"><span data-stu-id="4851c-105">Queries in LINQ to DataSet</span></span>](queries-in-linq-to-dataset.md)  
 <span data-ttu-id="4851c-106">提供有关如何编写 LINQ to DataSet 查询的信息。</span><span class="sxs-lookup"><span data-stu-id="4851c-106">Provides information about how to write LINQ to DataSet queries.</span></span>  
  
 [<span data-ttu-id="4851c-107">查询数据集</span><span class="sxs-lookup"><span data-stu-id="4851c-107">Querying DataSets</span></span>](querying-datasets-linq-to-dataset.md)  
 <span data-ttu-id="4851c-108">说明如何查询 <xref:System.Data.DataSet> 对象。</span><span class="sxs-lookup"><span data-stu-id="4851c-108">Describes how to query <xref:System.Data.DataSet> objects.</span></span>  
  
 [<span data-ttu-id="4851c-109">比较 DataRow</span><span class="sxs-lookup"><span data-stu-id="4851c-109">Comparing DataRows</span></span>](comparing-datarows-linq-to-dataset.md)  
 <span data-ttu-id="4851c-110">说明如何使用 <xref:System.Data.DataRowComparer> 对象来比较数据行。</span><span class="sxs-lookup"><span data-stu-id="4851c-110">Describes how to use the <xref:System.Data.DataRowComparer> object to compare data rows.</span></span>  
  
 [<span data-ttu-id="4851c-111">从查询创建数据表</span><span class="sxs-lookup"><span data-stu-id="4851c-111">Creating a DataTable From a Query</span></span>](creating-a-datatable-from-a-query-linq-to-dataset.md)  
 <span data-ttu-id="4851c-112">提供有关使用 <xref:System.Data.DataTableExtensions.CopyToDataTable%2A> 方法从 LINQ to DataSet 查询创建 <xref:System.Data.DataTable> 的信息。</span><span class="sxs-lookup"><span data-stu-id="4851c-112">Provides information about creating a <xref:System.Data.DataTable> from a LINQ to DataSet query by using the <xref:System.Data.DataTableExtensions.CopyToDataTable%2A> method.</span></span>  
  
 [<span data-ttu-id="4851c-113">如何：实现 CopyToDataTable\<T >，其中泛型类型 T 不是 DataRow</span><span class="sxs-lookup"><span data-stu-id="4851c-113">How to: Implement CopyToDataTable\<T> Where the Generic Type T Is Not a DataRow</span></span>](implement-copytodatatable-where-type-not-a-datarow.md)  
 <span data-ttu-id="4851c-114">描述如何实现自定义的 `CopyToDataTable<T>` 方法，其中泛型参数 T 的类型不是 <xref:System.Data.DataRow>。</span><span class="sxs-lookup"><span data-stu-id="4851c-114">Describes how to implement a custom `CopyToDataTable<T>` method where the generic parameter T is not of type <xref:System.Data.DataRow>.</span></span>  
  
 [<span data-ttu-id="4851c-115">泛型字段和 SetField 方法</span><span class="sxs-lookup"><span data-stu-id="4851c-115">Generic Field and SetField Methods</span></span>](generic-field-and-setfield-methods-linq-to-dataset.md)  
 <span data-ttu-id="4851c-116">提供有关泛型 <xref:System.Data.DataRowExtensions.Field%2A> 和 <xref:System.Data.DataRowExtensions.SetField%2A> 方法的信息。</span><span class="sxs-lookup"><span data-stu-id="4851c-116">Provides information about the generic <xref:System.Data.DataRowExtensions.Field%2A> and <xref:System.Data.DataRowExtensions.SetField%2A> methods.</span></span>  
  
 [<span data-ttu-id="4851c-117">数据绑定和 LINQ to DataSet</span><span class="sxs-lookup"><span data-stu-id="4851c-117">Data Binding and LINQ to DataSet</span></span>](data-binding-and-linq-to-dataset.md)  
 <span data-ttu-id="4851c-118">说明使用 <xref:System.Data.DataView> 对象的数据绑定。</span><span class="sxs-lookup"><span data-stu-id="4851c-118">Describes databinding using the <xref:System.Data.DataView> object.</span></span>  
  
 [<span data-ttu-id="4851c-119">调试 LINQ to DataSet 查询</span><span class="sxs-lookup"><span data-stu-id="4851c-119">Debugging LINQ to DataSet Queries</span></span>](debugging-linq-to-dataset-queries.md)  
 <span data-ttu-id="4851c-120">提供有关 LINQ to DataSet 查询进行调试和故障排除的信息。</span><span class="sxs-lookup"><span data-stu-id="4851c-120">Provides information about debugging and troubleshooting LINQ to DataSet queries.</span></span>  
  
 [<span data-ttu-id="4851c-121">安全</span><span class="sxs-lookup"><span data-stu-id="4851c-121">Security</span></span>](security-linq-to-dataset.md)  
 <span data-ttu-id="4851c-122">描述 LINQ to DataSet 中的安全问题。</span><span class="sxs-lookup"><span data-stu-id="4851c-122">Describes security issues in LINQ to DataSet.</span></span>  
  
 [<span data-ttu-id="4851c-123">LINQ to DataSet 示例</span><span class="sxs-lookup"><span data-stu-id="4851c-123">LINQ to DataSet Examples</span></span>](linq-to-dataset-examples.md)  
 <span data-ttu-id="4851c-124">提供使用 LINQ 运算符的查询示例。</span><span class="sxs-lookup"><span data-stu-id="4851c-124">Provides query examples that use the LINQ operators.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="4851c-125">引用</span><span class="sxs-lookup"><span data-stu-id="4851c-125">Reference</span></span>  
 <xref:System.Data.DataRowComparer>  
  
 <xref:System.Data.DataRowExtensions>  
  
 <xref:System.Data.DataTableExtensions>  
  
 <xref:System.Data.DataView>  
  
## <a name="see-also"></a><span data-ttu-id="4851c-126">另请参阅</span><span class="sxs-lookup"><span data-stu-id="4851c-126">See also</span></span>

- [<span data-ttu-id="4851c-127">LINQ 和 ADO.NET</span><span class="sxs-lookup"><span data-stu-id="4851c-127">LINQ and ADO.NET</span></span>](linq-and-ado-net.md)
- [<span data-ttu-id="4851c-128">语言集成查询 (LINQ)</span><span class="sxs-lookup"><span data-stu-id="4851c-128">Language Integrated Query (LINQ)</span></span>](../../../csharp/programming-guide/concepts/linq/index.md)
