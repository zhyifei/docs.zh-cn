---
title: LINQ to DataSet 示例
ms.date: 03/30/2017
ms.assetid: dfd91658-8d8a-45a4-a356-e327e809f21d
ms.openlocfilehash: f0b836e4f19011dc3d75f0681f7205cec6cb9110
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/03/2018
---
# <a name="linq-to-dataset-examples"></a><span data-ttu-id="2da65-102">LINQ to DataSet 示例</span><span class="sxs-lookup"><span data-stu-id="2da65-102">LINQ to DataSet Examples</span></span>
<span data-ttu-id="2da65-103">本部分提供[!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)]编程使用标准查询运算符的示例。</span><span class="sxs-lookup"><span data-stu-id="2da65-103">This section provides [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)] programming examples that use the standard query operators.</span></span> <span data-ttu-id="2da65-104"><xref:System.Data.DataSet>这些示例中使用填充使用`FillDataSet`方法，指定在[加载数据到数据集](../../../../docs/framework/data/adonet/loading-data-into-a-dataset.md)。</span><span class="sxs-lookup"><span data-stu-id="2da65-104">The <xref:System.Data.DataSet> used in these examples is populated by using the `FillDataSet` method, which is specified in [Loading Data Into a DataSet](../../../../docs/framework/data/adonet/loading-data-into-a-dataset.md).</span></span> <span data-ttu-id="2da65-105">有关详细信息，请参阅[标准查询运算符概述](http://msdn.microsoft.com/library/24cda21e-8af8-4632-b519-c404a839b9b2)。</span><span class="sxs-lookup"><span data-stu-id="2da65-105">For more information, see [Standard Query Operators Overview](http://msdn.microsoft.com/library/24cda21e-8af8-4632-b519-c404a839b9b2).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="2da65-106">本节内容</span><span class="sxs-lookup"><span data-stu-id="2da65-106">In This Section</span></span>  
 [<span data-ttu-id="2da65-107">查询表达式示例</span><span class="sxs-lookup"><span data-stu-id="2da65-107">Query Expression Examples</span></span>](../../../../docs/framework/data/adonet/query-expression-examples-linq-to-dataset.md)  
 <span data-ttu-id="2da65-108">包含下面的示例：</span><span class="sxs-lookup"><span data-stu-id="2da65-108">Contains the following examples:</span></span>  
  
-   [<span data-ttu-id="2da65-109">投影</span><span class="sxs-lookup"><span data-stu-id="2da65-109">Projection</span></span>](../../../../docs/framework/data/adonet/query-expression-syntax-examples-projection-linq-to-dataset.md)  
  
-   [<span data-ttu-id="2da65-110">限制</span><span class="sxs-lookup"><span data-stu-id="2da65-110">Restriction</span></span>](../../../../docs/framework/data/adonet/query-expression-syntax-examples-restriction-linq-to-dataset.md)  
  
-   [<span data-ttu-id="2da65-111">分区</span><span class="sxs-lookup"><span data-stu-id="2da65-111">Partitioning</span></span>](../../../../docs/framework/data/adonet/query-expression-syntax-examples-partitioning.md)  
  
-   [<span data-ttu-id="2da65-112">订购</span><span class="sxs-lookup"><span data-stu-id="2da65-112">Ordering</span></span>](../../../../docs/framework/data/adonet/query-expression-syntax-examples-ordering-linq-to-dataset.md)  
  
-   [<span data-ttu-id="2da65-113">元素运算符</span><span class="sxs-lookup"><span data-stu-id="2da65-113">Element Operators</span></span>](../../../../docs/framework/data/adonet/query-expression-syntax-examples-element-operators.md)  
  
-   [<span data-ttu-id="2da65-114">聚合运算符</span><span class="sxs-lookup"><span data-stu-id="2da65-114">Aggregate Operators</span></span>](../../../../docs/framework/data/adonet/query-expression-syntax-examples-aggregate-operators.md)  
  
-   [<span data-ttu-id="2da65-115">联接运算符</span><span class="sxs-lookup"><span data-stu-id="2da65-115">Join Operators</span></span>](../../../../docs/framework/data/adonet/query-expression-syntax-examples-join-operators.md)  
  
 [<span data-ttu-id="2da65-116">基于方法的查询示例</span><span class="sxs-lookup"><span data-stu-id="2da65-116">Method-Based Query Examples</span></span>](../../../../docs/framework/data/adonet/method-based-query-examples-linq-to-dataset.md)  
 <span data-ttu-id="2da65-117">包含下面的示例：</span><span class="sxs-lookup"><span data-stu-id="2da65-117">Contains the following examples:</span></span>  
  
-   [<span data-ttu-id="2da65-118">投影</span><span class="sxs-lookup"><span data-stu-id="2da65-118">Projection</span></span>](../../../../docs/framework/data/adonet/method-based-query-syntax-examples-projection.md)  
  
-   [<span data-ttu-id="2da65-119">分区</span><span class="sxs-lookup"><span data-stu-id="2da65-119">Partitioning</span></span>](../../../../docs/framework/data/adonet/method-based-query-syntax-examples-partitioning-linq.md)  
  
-   [<span data-ttu-id="2da65-120">订购</span><span class="sxs-lookup"><span data-stu-id="2da65-120">Ordering</span></span>](../../../../docs/framework/data/adonet/method-based-query-syntax-examples-ordering-linq-to-dataset.md)  
  
-   [<span data-ttu-id="2da65-121">set 运算符</span><span class="sxs-lookup"><span data-stu-id="2da65-121">Set Operators</span></span>](../../../../docs/framework/data/adonet/method-based-query-syntax-examples-set-operators.md)  
  
-   [<span data-ttu-id="2da65-122">转换运算符</span><span class="sxs-lookup"><span data-stu-id="2da65-122">Conversion Operators</span></span>](../../../../docs/framework/data/adonet/method-based-query-syntax-examples-conversion-operators.md)  
  
-   [<span data-ttu-id="2da65-123">元素运算符</span><span class="sxs-lookup"><span data-stu-id="2da65-123">Element Operators</span></span>](../../../../docs/framework/data/adonet/method-based-query-syntax-examples-element-operators.md)  
  
-   [<span data-ttu-id="2da65-124">聚合运算符</span><span class="sxs-lookup"><span data-stu-id="2da65-124">Aggregate Operators</span></span>](../../../../docs/framework/data/adonet/method-based-query-syntax-examples-aggregate-operators.md)  
  
-   [<span data-ttu-id="2da65-125">Join</span><span class="sxs-lookup"><span data-stu-id="2da65-125">Join</span></span>](../../../../docs/framework/data/adonet/method-based-query-syntax-examples-join-linq-to-dataset.md)  
  
 [<span data-ttu-id="2da65-126">数据集特定的运算符示例</span><span class="sxs-lookup"><span data-stu-id="2da65-126">DataSet-Specific Operator Examples</span></span>](../../../../docs/framework/data/adonet/dataset-specific-operator-examples-linq-to-dataset.md)  
 <span data-ttu-id="2da65-127">包含演示如何使用 <xref:System.Data.DataTableExtensions.CopyToDataTable%2A> 方法和 <xref:System.Data.DataRowComparer> 类的示例。</span><span class="sxs-lookup"><span data-stu-id="2da65-127">Contains examples that demonstrate how to use the <xref:System.Data.DataTableExtensions.CopyToDataTable%2A> method and the <xref:System.Data.DataRowComparer> class.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2da65-128">请参阅</span><span class="sxs-lookup"><span data-stu-id="2da65-128">See Also</span></span>  
 [<span data-ttu-id="2da65-129">编程指南</span><span class="sxs-lookup"><span data-stu-id="2da65-129">Programming Guide</span></span>](../../../../docs/framework/data/adonet/programming-guide-linq-to-dataset.md)  
 [<span data-ttu-id="2da65-130">将数据加载到数据集中</span><span class="sxs-lookup"><span data-stu-id="2da65-130">Loading Data Into a DataSet</span></span>](../../../../docs/framework/data/adonet/loading-data-into-a-dataset.md)
