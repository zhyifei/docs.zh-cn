---
title: LINQ to DataSet 示例
ms.date: 03/30/2017
ms.assetid: dfd91658-8d8a-45a4-a356-e327e809f21d
ms.openlocfilehash: 09a5d652d1d75a02966f3ed38fe9d3aa7901a87b
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/04/2018
ms.locfileid: "43524837"
---
# <a name="linq-to-dataset-examples"></a><span data-ttu-id="c42a2-102">LINQ to DataSet 示例</span><span class="sxs-lookup"><span data-stu-id="c42a2-102">LINQ to DataSet Examples</span></span>
<span data-ttu-id="c42a2-103">本部分提供了[!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)]编程使用标准查询运算符的示例。</span><span class="sxs-lookup"><span data-stu-id="c42a2-103">This section provides [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)] programming examples that use the standard query operators.</span></span> <span data-ttu-id="c42a2-104"><xref:System.Data.DataSet>这些示例中使用通过使用填充`FillDataSet`方法中指定[加载数据到数据集](../../../../docs/framework/data/adonet/loading-data-into-a-dataset.md)。</span><span class="sxs-lookup"><span data-stu-id="c42a2-104">The <xref:System.Data.DataSet> used in these examples is populated by using the `FillDataSet` method, which is specified in [Loading Data Into a DataSet](../../../../docs/framework/data/adonet/loading-data-into-a-dataset.md).</span></span> <span data-ttu-id="c42a2-105">有关详细信息，请参阅[标准查询运算符概述](https://msdn.microsoft.com/library/24cda21e-8af8-4632-b519-c404a839b9b2)。</span><span class="sxs-lookup"><span data-stu-id="c42a2-105">For more information, see [Standard Query Operators Overview](https://msdn.microsoft.com/library/24cda21e-8af8-4632-b519-c404a839b9b2).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="c42a2-106">本节内容</span><span class="sxs-lookup"><span data-stu-id="c42a2-106">In This Section</span></span>  
 [<span data-ttu-id="c42a2-107">查询表达式示例</span><span class="sxs-lookup"><span data-stu-id="c42a2-107">Query Expression Examples</span></span>](../../../../docs/framework/data/adonet/query-expression-examples-linq-to-dataset.md)  
 <span data-ttu-id="c42a2-108">包含下面的示例：</span><span class="sxs-lookup"><span data-stu-id="c42a2-108">Contains the following examples:</span></span>  
  
-   [<span data-ttu-id="c42a2-109">投影</span><span class="sxs-lookup"><span data-stu-id="c42a2-109">Projection</span></span>](../../../../docs/framework/data/adonet/query-expression-syntax-examples-projection-linq-to-dataset.md)  
  
-   [<span data-ttu-id="c42a2-110">限制</span><span class="sxs-lookup"><span data-stu-id="c42a2-110">Restriction</span></span>](../../../../docs/framework/data/adonet/query-expression-syntax-examples-restriction-linq-to-dataset.md)  
  
-   [<span data-ttu-id="c42a2-111">分区</span><span class="sxs-lookup"><span data-stu-id="c42a2-111">Partitioning</span></span>](../../../../docs/framework/data/adonet/query-expression-syntax-examples-partitioning.md)  
  
-   [<span data-ttu-id="c42a2-112">订购</span><span class="sxs-lookup"><span data-stu-id="c42a2-112">Ordering</span></span>](../../../../docs/framework/data/adonet/query-expression-syntax-examples-ordering-linq-to-dataset.md)  
  
-   [<span data-ttu-id="c42a2-113">元素运算符</span><span class="sxs-lookup"><span data-stu-id="c42a2-113">Element Operators</span></span>](../../../../docs/framework/data/adonet/query-expression-syntax-examples-element-operators.md)  
  
-   [<span data-ttu-id="c42a2-114">聚合运算符</span><span class="sxs-lookup"><span data-stu-id="c42a2-114">Aggregate Operators</span></span>](../../../../docs/framework/data/adonet/query-expression-syntax-examples-aggregate-operators.md)  
  
-   [<span data-ttu-id="c42a2-115">联接运算符</span><span class="sxs-lookup"><span data-stu-id="c42a2-115">Join Operators</span></span>](../../../../docs/framework/data/adonet/query-expression-syntax-examples-join-operators.md)  
  
 [<span data-ttu-id="c42a2-116">基于方法的查询示例</span><span class="sxs-lookup"><span data-stu-id="c42a2-116">Method-Based Query Examples</span></span>](../../../../docs/framework/data/adonet/method-based-query-examples-linq-to-dataset.md)  
 <span data-ttu-id="c42a2-117">包含下面的示例：</span><span class="sxs-lookup"><span data-stu-id="c42a2-117">Contains the following examples:</span></span>  
  
-   [<span data-ttu-id="c42a2-118">投影</span><span class="sxs-lookup"><span data-stu-id="c42a2-118">Projection</span></span>](../../../../docs/framework/data/adonet/method-based-query-syntax-examples-projection.md)  
  
-   [<span data-ttu-id="c42a2-119">分区</span><span class="sxs-lookup"><span data-stu-id="c42a2-119">Partitioning</span></span>](../../../../docs/framework/data/adonet/method-based-query-syntax-examples-partitioning-linq.md)  
  
-   [<span data-ttu-id="c42a2-120">订购</span><span class="sxs-lookup"><span data-stu-id="c42a2-120">Ordering</span></span>](../../../../docs/framework/data/adonet/method-based-query-syntax-examples-ordering-linq-to-dataset.md)  
  
-   [<span data-ttu-id="c42a2-121">set 运算符</span><span class="sxs-lookup"><span data-stu-id="c42a2-121">Set Operators</span></span>](../../../../docs/framework/data/adonet/method-based-query-syntax-examples-set-operators.md)  
  
-   [<span data-ttu-id="c42a2-122">转换运算符</span><span class="sxs-lookup"><span data-stu-id="c42a2-122">Conversion Operators</span></span>](../../../../docs/framework/data/adonet/method-based-query-syntax-examples-conversion-operators.md)  
  
-   [<span data-ttu-id="c42a2-123">元素运算符</span><span class="sxs-lookup"><span data-stu-id="c42a2-123">Element Operators</span></span>](../../../../docs/framework/data/adonet/method-based-query-syntax-examples-element-operators.md)  
  
-   [<span data-ttu-id="c42a2-124">聚合运算符</span><span class="sxs-lookup"><span data-stu-id="c42a2-124">Aggregate Operators</span></span>](../../../../docs/framework/data/adonet/method-based-query-syntax-examples-aggregate-operators.md)  
  
-   [<span data-ttu-id="c42a2-125">Join</span><span class="sxs-lookup"><span data-stu-id="c42a2-125">Join</span></span>](../../../../docs/framework/data/adonet/method-based-query-syntax-examples-join-linq-to-dataset.md)  
  
 [<span data-ttu-id="c42a2-126">数据集特定的运算符示例</span><span class="sxs-lookup"><span data-stu-id="c42a2-126">DataSet-Specific Operator Examples</span></span>](../../../../docs/framework/data/adonet/dataset-specific-operator-examples-linq-to-dataset.md)  
 <span data-ttu-id="c42a2-127">包含演示如何使用 <xref:System.Data.DataTableExtensions.CopyToDataTable%2A> 方法和 <xref:System.Data.DataRowComparer> 类的示例。</span><span class="sxs-lookup"><span data-stu-id="c42a2-127">Contains examples that demonstrate how to use the <xref:System.Data.DataTableExtensions.CopyToDataTable%2A> method and the <xref:System.Data.DataRowComparer> class.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c42a2-128">请参阅</span><span class="sxs-lookup"><span data-stu-id="c42a2-128">See Also</span></span>  
 [<span data-ttu-id="c42a2-129">编程指南</span><span class="sxs-lookup"><span data-stu-id="c42a2-129">Programming Guide</span></span>](../../../../docs/framework/data/adonet/programming-guide-linq-to-dataset.md)  
 [<span data-ttu-id="c42a2-130">将数据加载到数据集中</span><span class="sxs-lookup"><span data-stu-id="c42a2-130">Loading Data Into a DataSet</span></span>](../../../../docs/framework/data/adonet/loading-data-into-a-dataset.md)
