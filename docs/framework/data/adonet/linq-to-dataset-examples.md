---
title: LINQ to DataSet 示例
ms.date: 03/30/2017
ms.assetid: dfd91658-8d8a-45a4-a356-e327e809f21d
ms.openlocfilehash: 8e6cce8ba79cad42ade6ac373631094f9e2d4e04
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54634527"
---
# <a name="linq-to-dataset-examples"></a><span data-ttu-id="45191-102">LINQ to DataSet 示例</span><span class="sxs-lookup"><span data-stu-id="45191-102">LINQ to DataSet Examples</span></span>
<span data-ttu-id="45191-103">本部分提供了[!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)]编程使用标准查询运算符的示例。</span><span class="sxs-lookup"><span data-stu-id="45191-103">This section provides [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)] programming examples that use the standard query operators.</span></span> <span data-ttu-id="45191-104"><xref:System.Data.DataSet>这些示例中使用通过使用填充`FillDataSet`方法中指定[加载数据到数据集](../../../../docs/framework/data/adonet/loading-data-into-a-dataset.md)。</span><span class="sxs-lookup"><span data-stu-id="45191-104">The <xref:System.Data.DataSet> used in these examples is populated by using the `FillDataSet` method, which is specified in [Loading Data Into a DataSet](../../../../docs/framework/data/adonet/loading-data-into-a-dataset.md).</span></span> <span data-ttu-id="45191-105">有关详细信息，请参阅[标准查询运算符概述](https://msdn.microsoft.com/library/24cda21e-8af8-4632-b519-c404a839b9b2)。</span><span class="sxs-lookup"><span data-stu-id="45191-105">For more information, see [Standard Query Operators Overview](https://msdn.microsoft.com/library/24cda21e-8af8-4632-b519-c404a839b9b2).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="45191-106">本节内容</span><span class="sxs-lookup"><span data-stu-id="45191-106">In This Section</span></span>  
 [<span data-ttu-id="45191-107">查询表达式示例</span><span class="sxs-lookup"><span data-stu-id="45191-107">Query Expression Examples</span></span>](../../../../docs/framework/data/adonet/query-expression-examples-linq-to-dataset.md)  
 <span data-ttu-id="45191-108">包含下面的示例：</span><span class="sxs-lookup"><span data-stu-id="45191-108">Contains the following examples:</span></span>  
  
-   [<span data-ttu-id="45191-109">投影</span><span class="sxs-lookup"><span data-stu-id="45191-109">Projection</span></span>](../../../../docs/framework/data/adonet/query-expression-syntax-examples-projection-linq-to-dataset.md)  
  
-   [<span data-ttu-id="45191-110">限制</span><span class="sxs-lookup"><span data-stu-id="45191-110">Restriction</span></span>](../../../../docs/framework/data/adonet/query-expression-syntax-examples-restriction-linq-to-dataset.md)  
  
-   [<span data-ttu-id="45191-111">分区</span><span class="sxs-lookup"><span data-stu-id="45191-111">Partitioning</span></span>](../../../../docs/framework/data/adonet/query-expression-syntax-examples-partitioning.md)  
  
-   [<span data-ttu-id="45191-112">订购</span><span class="sxs-lookup"><span data-stu-id="45191-112">Ordering</span></span>](../../../../docs/framework/data/adonet/query-expression-syntax-examples-ordering-linq-to-dataset.md)  
  
-   [<span data-ttu-id="45191-113">元素运算符</span><span class="sxs-lookup"><span data-stu-id="45191-113">Element Operators</span></span>](../../../../docs/framework/data/adonet/query-expression-syntax-examples-element-operators.md)  
  
-   [<span data-ttu-id="45191-114">聚合运算符</span><span class="sxs-lookup"><span data-stu-id="45191-114">Aggregate Operators</span></span>](../../../../docs/framework/data/adonet/query-expression-syntax-examples-aggregate-operators.md)  
  
-   [<span data-ttu-id="45191-115">联接运算符</span><span class="sxs-lookup"><span data-stu-id="45191-115">Join Operators</span></span>](../../../../docs/framework/data/adonet/query-expression-syntax-examples-join-operators.md)  
  
 [<span data-ttu-id="45191-116">基于方法的查询示例</span><span class="sxs-lookup"><span data-stu-id="45191-116">Method-Based Query Examples</span></span>](../../../../docs/framework/data/adonet/method-based-query-examples-linq-to-dataset.md)  
 <span data-ttu-id="45191-117">包含下面的示例：</span><span class="sxs-lookup"><span data-stu-id="45191-117">Contains the following examples:</span></span>  
  
-   [<span data-ttu-id="45191-118">投影</span><span class="sxs-lookup"><span data-stu-id="45191-118">Projection</span></span>](../../../../docs/framework/data/adonet/method-based-query-syntax-examples-projection.md)  
  
-   [<span data-ttu-id="45191-119">分区</span><span class="sxs-lookup"><span data-stu-id="45191-119">Partitioning</span></span>](../../../../docs/framework/data/adonet/method-based-query-syntax-examples-partitioning-linq.md)  
  
-   [<span data-ttu-id="45191-120">订购</span><span class="sxs-lookup"><span data-stu-id="45191-120">Ordering</span></span>](../../../../docs/framework/data/adonet/method-based-query-syntax-examples-ordering-linq-to-dataset.md)  
  
-   [<span data-ttu-id="45191-121">set 运算符</span><span class="sxs-lookup"><span data-stu-id="45191-121">Set Operators</span></span>](../../../../docs/framework/data/adonet/method-based-query-syntax-examples-set-operators.md)  
  
-   [<span data-ttu-id="45191-122">转换运算符</span><span class="sxs-lookup"><span data-stu-id="45191-122">Conversion Operators</span></span>](../../../../docs/framework/data/adonet/method-based-query-syntax-examples-conversion-operators.md)  
  
-   [<span data-ttu-id="45191-123">元素运算符</span><span class="sxs-lookup"><span data-stu-id="45191-123">Element Operators</span></span>](../../../../docs/framework/data/adonet/method-based-query-syntax-examples-element-operators.md)  
  
-   [<span data-ttu-id="45191-124">聚合运算符</span><span class="sxs-lookup"><span data-stu-id="45191-124">Aggregate Operators</span></span>](../../../../docs/framework/data/adonet/method-based-query-syntax-examples-aggregate-operators.md)  
  
-   [<span data-ttu-id="45191-125">Join</span><span class="sxs-lookup"><span data-stu-id="45191-125">Join</span></span>](../../../../docs/framework/data/adonet/method-based-query-syntax-examples-join-linq-to-dataset.md)  
  
 [<span data-ttu-id="45191-126">数据集特定的运算符示例</span><span class="sxs-lookup"><span data-stu-id="45191-126">DataSet-Specific Operator Examples</span></span>](../../../../docs/framework/data/adonet/dataset-specific-operator-examples-linq-to-dataset.md)  
 <span data-ttu-id="45191-127">包含演示如何使用 <xref:System.Data.DataTableExtensions.CopyToDataTable%2A> 方法和 <xref:System.Data.DataRowComparer> 类的示例。</span><span class="sxs-lookup"><span data-stu-id="45191-127">Contains examples that demonstrate how to use the <xref:System.Data.DataTableExtensions.CopyToDataTable%2A> method and the <xref:System.Data.DataRowComparer> class.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="45191-128">请参阅</span><span class="sxs-lookup"><span data-stu-id="45191-128">See also</span></span>
- [<span data-ttu-id="45191-129">编程指南</span><span class="sxs-lookup"><span data-stu-id="45191-129">Programming Guide</span></span>](../../../../docs/framework/data/adonet/programming-guide-linq-to-dataset.md)
- [<span data-ttu-id="45191-130">将数据加载到数据集中</span><span class="sxs-lookup"><span data-stu-id="45191-130">Loading Data Into a DataSet</span></span>](../../../../docs/framework/data/adonet/loading-data-into-a-dataset.md)
