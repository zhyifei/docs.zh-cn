---
title: "对序列中的元素进行分组"
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
ms.assetid: 1d50c8b4-f550-4775-bbb6-eab6e874cb43
caps.latest.revision: "2"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.workload: dotnet
ms.openlocfilehash: 09617f147d1afc2d9f2ca76624b54f94e5164188
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="group-elements-in-a-sequence"></a><span data-ttu-id="3fc73-102">对序列中的元素进行分组</span><span class="sxs-lookup"><span data-stu-id="3fc73-102">Group Elements in a Sequence</span></span>
<span data-ttu-id="3fc73-103"><xref:System.Linq.Enumerable.GroupBy%2A> 运算符用于对序列中的元素进行分组。</span><span class="sxs-lookup"><span data-stu-id="3fc73-103">The <xref:System.Linq.Enumerable.GroupBy%2A> operator groups the elements of a sequence.</span></span> <span data-ttu-id="3fc73-104">下面的示例使用 Northwind 数据库。</span><span class="sxs-lookup"><span data-stu-id="3fc73-104">The following examples use the Northwind database.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="3fc73-105"><xref:System.Linq.Enumerable.GroupBy%2A> 查询中的 Null 列值有时可能引发 <xref:System.InvalidOperationException>。</span><span class="sxs-lookup"><span data-stu-id="3fc73-105">Null column values in <xref:System.Linq.Enumerable.GroupBy%2A> queries can sometimes throw an <xref:System.InvalidOperationException>.</span></span> <span data-ttu-id="3fc73-106">有关详细信息，请参阅的"GroupBy InvalidOperationException"部分[故障排除](../../../../../../docs/framework/data/adonet/sql/linq/troubleshooting.md)。</span><span class="sxs-lookup"><span data-stu-id="3fc73-106">For more information, see the "GroupBy InvalidOperationException" section of [Troubleshooting](../../../../../../docs/framework/data/adonet/sql/linq/troubleshooting.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="3fc73-107">示例</span><span class="sxs-lookup"><span data-stu-id="3fc73-107">Example</span></span>  
 <span data-ttu-id="3fc73-108">下面的示例按照 `Products` 对 `CategoryID` 进行分区。</span><span class="sxs-lookup"><span data-stu-id="3fc73-108">The following example partitions `Products` by `CategoryID`.</span></span>  
  
 [!code-csharp[DLinqQueryExamples#27](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#27)]
 [!code-vb[DLinqQueryExamples#27](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#27)]  
  
## <a name="example"></a><span data-ttu-id="3fc73-109">示例</span><span class="sxs-lookup"><span data-stu-id="3fc73-109">Example</span></span>  
 <span data-ttu-id="3fc73-110">下面的示例使用 <xref:System.Linq.Enumerable.Max%2A> 来查找每个 `CategoryID` 的最高单价。</span><span class="sxs-lookup"><span data-stu-id="3fc73-110">The following example uses <xref:System.Linq.Enumerable.Max%2A> to find the maximum unit price for each `CategoryID`.</span></span>  
  
 [!code-csharp[DLinqQueryExamples#28](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#28)]
 [!code-vb[DLinqQueryExamples#28](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#28)]  
  
## <a name="example"></a><span data-ttu-id="3fc73-111">示例</span><span class="sxs-lookup"><span data-stu-id="3fc73-111">Example</span></span>  
 <span data-ttu-id="3fc73-112">下面的示例使用 Average 来查找每个 `UnitPrice` 的平均 `CategoryID`。</span><span class="sxs-lookup"><span data-stu-id="3fc73-112">The following example uses Average to find the average `UnitPrice` for each `CategoryID`.</span></span>  
  
 [!code-csharp[DLinqQueryExamples#29](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#29)]
 [!code-vb[DLinqQueryExamples#29](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#29)]  
  
## <a name="example"></a><span data-ttu-id="3fc73-113">示例</span><span class="sxs-lookup"><span data-stu-id="3fc73-113">Example</span></span>  
 <span data-ttu-id="3fc73-114">下面的示例使用 <xref:System.Linq.Queryable.Sum%2A> 来查找每个 `UnitPrice` 的总 `CategoryID`。</span><span class="sxs-lookup"><span data-stu-id="3fc73-114">The following example uses <xref:System.Linq.Queryable.Sum%2A> to find the total `UnitPrice` for each `CategoryID`.</span></span>  
  
 [!code-csharp[DLinqQueryExamples#30](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#30)]
 [!code-vb[DLinqQueryExamples#30](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#30)]  
  
## <a name="example"></a><span data-ttu-id="3fc73-115">示例</span><span class="sxs-lookup"><span data-stu-id="3fc73-115">Example</span></span>  
 <span data-ttu-id="3fc73-116">下面的示例使用 <xref:System.Linq.Queryable.Count%2A> 来查找每个 `Products` 中已停产 `CategoryID` 的数量。</span><span class="sxs-lookup"><span data-stu-id="3fc73-116">The following example uses <xref:System.Linq.Queryable.Count%2A> to find the number of discontinued `Products` in each `CategoryID`.</span></span>  
  
 [!code-csharp[DLinqQueryExamples#31](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#31)]
 [!code-vb[DLinqQueryExamples#31](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#31)]  
  
## <a name="example"></a><span data-ttu-id="3fc73-117">示例</span><span class="sxs-lookup"><span data-stu-id="3fc73-117">Example</span></span>  
 <span data-ttu-id="3fc73-118">下面的示例使用后跟的 `where` 子句来查找至少包含 10 种产品的所有类别。</span><span class="sxs-lookup"><span data-stu-id="3fc73-118">The following example uses a following `where` clause to find all categories that have at least 10 products.</span></span>  
  
 [!code-csharp[DLinqQueryExamples#32](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#32)]
 [!code-vb[DLinqQueryExamples#32](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#32)]  
  
## <a name="example"></a><span data-ttu-id="3fc73-119">示例</span><span class="sxs-lookup"><span data-stu-id="3fc73-119">Example</span></span>  
 <span data-ttu-id="3fc73-120">下面的示例按 `CategoryID` 和 `SupplierID` 对产品进行分组。</span><span class="sxs-lookup"><span data-stu-id="3fc73-120">The following example groups products by `CategoryID` and `SupplierID`.</span></span>  
  
 [!code-csharp[DLinqQueryExamples#33](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#33)]
 [!code-vb[DLinqQueryExamples#33](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#33)]  
  
## <a name="example"></a><span data-ttu-id="3fc73-121">示例</span><span class="sxs-lookup"><span data-stu-id="3fc73-121">Example</span></span>  
 <span data-ttu-id="3fc73-122">下面的示例返回两个产品序列。</span><span class="sxs-lookup"><span data-stu-id="3fc73-122">The following example returns two sequences of products.</span></span> <span data-ttu-id="3fc73-123">第一个序列包含单价小于或等于 10 的产品。</span><span class="sxs-lookup"><span data-stu-id="3fc73-123">The first sequence contains products with unit price less than or equal to 10.</span></span> <span data-ttu-id="3fc73-124">第二个序列包含单价大于 10 的产品。</span><span class="sxs-lookup"><span data-stu-id="3fc73-124">The second sequence contains products with unit price greater than 10.</span></span>  
  
 [!code-csharp[DLinqQueryExamples#34](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#34)]
 [!code-vb[DLinqQueryExamples#34](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#34)]  
  
## <a name="example"></a><span data-ttu-id="3fc73-125">示例</span><span class="sxs-lookup"><span data-stu-id="3fc73-125">Example</span></span>  
 <span data-ttu-id="3fc73-126"><xref:System.Linq.Queryable.GroupBy%2A> 运算符只能采用单个键参数。</span><span class="sxs-lookup"><span data-stu-id="3fc73-126">The <xref:System.Linq.Queryable.GroupBy%2A> operator can take only a single key argument.</span></span> <span data-ttu-id="3fc73-127">如果您需要按多个键进行分组，则必须创建匿名类型，如下例所示：</span><span class="sxs-lookup"><span data-stu-id="3fc73-127">If you need to group by more than one key, you must create an anonymous type, as in the following example:</span></span>  
  
 [!code-csharp[DLinqQueryExamples#35](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#35)]
 [!code-vb[DLinqQueryExamples#35](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#35)]  
  
## <a name="see-also"></a><span data-ttu-id="3fc73-128">请参阅</span><span class="sxs-lookup"><span data-stu-id="3fc73-128">See Also</span></span>  
 [<span data-ttu-id="3fc73-129">查询示例</span><span class="sxs-lookup"><span data-stu-id="3fc73-129">Query Examples</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/query-examples.md)  
 [<span data-ttu-id="3fc73-130">下载示例数据库</span><span class="sxs-lookup"><span data-stu-id="3fc73-130">Downloading Sample Databases</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/downloading-sample-databases.md)
