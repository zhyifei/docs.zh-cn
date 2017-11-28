---
title: "聚合运算 (C#)"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-csharp
ms.topic: article
ms.assetid: 6fc035e5-7639-48b8-bc7f-b093dd31b039
caps.latest.revision: "3"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: f3bb029d2b7f9115d1c68db2844127329d34fe2e
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="aggregation-operations-c"></a><span data-ttu-id="afa44-102">聚合运算 (C#)</span><span class="sxs-lookup"><span data-stu-id="afa44-102">Aggregation Operations (C#)</span></span>
<span data-ttu-id="afa44-103">聚合运算从值的集合中计算出单个值。</span><span class="sxs-lookup"><span data-stu-id="afa44-103">An aggregation operation computes a single value from a collection of values.</span></span> <span data-ttu-id="afa44-104">例如，从一个月累计的每日温度值计算出日平均温度值就是一个聚合运算。</span><span class="sxs-lookup"><span data-stu-id="afa44-104">An example of an aggregation operation is calculating the average daily temperature from a month's worth of daily temperature values.</span></span>  
  
 <span data-ttu-id="afa44-105">下图显示对数字序列进行两种不同聚合操作所得结果。</span><span class="sxs-lookup"><span data-stu-id="afa44-105">The following illustration shows the results of two different aggregation operations on a sequence of numbers.</span></span> <span data-ttu-id="afa44-106">第一个操作累加数字。</span><span class="sxs-lookup"><span data-stu-id="afa44-106">The first operation sums the numbers.</span></span> <span data-ttu-id="afa44-107">第二个操作返回序列中的最大值。</span><span class="sxs-lookup"><span data-stu-id="afa44-107">The second operation returns the maximum value in the sequence.</span></span>  
  
 <span data-ttu-id="afa44-108">![LINQ 聚合操作](../../../../csharp/programming-guide/concepts/linq/media/linq_aggregation.png "LINQ_Aggregation")</span><span class="sxs-lookup"><span data-stu-id="afa44-108">![LINQ Aggregation Operations](../../../../csharp/programming-guide/concepts/linq/media/linq_aggregation.png "LINQ_Aggregation")</span></span>  
  
 <span data-ttu-id="afa44-109">下节列出了执行聚合运算的标准查询运算符方法。</span><span class="sxs-lookup"><span data-stu-id="afa44-109">The standard query operator methods that perform aggregation operations are listed in the following section.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="afa44-110">方法</span><span class="sxs-lookup"><span data-stu-id="afa44-110">Methods</span></span>  
  
|<span data-ttu-id="afa44-111">方法名</span><span class="sxs-lookup"><span data-stu-id="afa44-111">Method Name</span></span>|<span data-ttu-id="afa44-112">描述</span><span class="sxs-lookup"><span data-stu-id="afa44-112">Description</span></span>|<span data-ttu-id="afa44-113">C# 查询表达式语法</span><span class="sxs-lookup"><span data-stu-id="afa44-113">C# Query Expression Syntax</span></span>|<span data-ttu-id="afa44-114">更多信息</span><span class="sxs-lookup"><span data-stu-id="afa44-114">More Information</span></span>|  
|-----------------|-----------------|---------------------------------|----------------------|  
|<span data-ttu-id="afa44-115">聚合</span><span class="sxs-lookup"><span data-stu-id="afa44-115">Aggregate</span></span>|<span data-ttu-id="afa44-116">对集合的值执行自定义聚合运算。</span><span class="sxs-lookup"><span data-stu-id="afa44-116">Performs a custom aggregation operation on the values of a collection.</span></span>|<span data-ttu-id="afa44-117">不适用。</span><span class="sxs-lookup"><span data-stu-id="afa44-117">Not applicable.</span></span>|<xref:System.Linq.Enumerable.Aggregate%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.Aggregate%2A?displayProperty=nameWithType>|  
|<span data-ttu-id="afa44-118">平均值</span><span class="sxs-lookup"><span data-stu-id="afa44-118">Average</span></span>|<span data-ttu-id="afa44-119">计算值集合的平均值。</span><span class="sxs-lookup"><span data-stu-id="afa44-119">Calculates the average value of a collection of values.</span></span>|<span data-ttu-id="afa44-120">不适用。</span><span class="sxs-lookup"><span data-stu-id="afa44-120">Not applicable.</span></span>|<xref:System.Linq.Enumerable.Average%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.Average%2A?displayProperty=nameWithType>|  
|<span data-ttu-id="afa44-121">计数</span><span class="sxs-lookup"><span data-stu-id="afa44-121">Count</span></span>|<span data-ttu-id="afa44-122">对集合中元素计数，可选择仅对满足谓词函数的元素计数。</span><span class="sxs-lookup"><span data-stu-id="afa44-122">Counts the elements in a collection, optionally only those elements that satisfy a predicate function.</span></span>|<span data-ttu-id="afa44-123">不适用。</span><span class="sxs-lookup"><span data-stu-id="afa44-123">Not applicable.</span></span>|<xref:System.Linq.Enumerable.Count%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.Count%2A?displayProperty=nameWithType>|  
|<span data-ttu-id="afa44-124">LongCount</span><span class="sxs-lookup"><span data-stu-id="afa44-124">LongCount</span></span>|<span data-ttu-id="afa44-125">对大型集合中元素计数，可选择仅对满足谓词函数的元素计数。</span><span class="sxs-lookup"><span data-stu-id="afa44-125">Counts the elements in a large collection, optionally only those elements that satisfy a predicate function.</span></span>|<span data-ttu-id="afa44-126">不适用。</span><span class="sxs-lookup"><span data-stu-id="afa44-126">Not applicable.</span></span>|<xref:System.Linq.Enumerable.LongCount%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.LongCount%2A?displayProperty=nameWithType>|  
|<span data-ttu-id="afa44-127">最大值</span><span class="sxs-lookup"><span data-stu-id="afa44-127">Max</span></span>|<span data-ttu-id="afa44-128">确定集合中的最大值。</span><span class="sxs-lookup"><span data-stu-id="afa44-128">Determines the maximum value in a collection.</span></span>|<span data-ttu-id="afa44-129">不适用。</span><span class="sxs-lookup"><span data-stu-id="afa44-129">Not applicable.</span></span>|<xref:System.Linq.Enumerable.Max%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.Max%2A?displayProperty=nameWithType>|  
|<span data-ttu-id="afa44-130">最小值</span><span class="sxs-lookup"><span data-stu-id="afa44-130">Min</span></span>|<span data-ttu-id="afa44-131">确定集合中的最小值。</span><span class="sxs-lookup"><span data-stu-id="afa44-131">Determines the minimum value in a collection.</span></span>|<span data-ttu-id="afa44-132">不适用。</span><span class="sxs-lookup"><span data-stu-id="afa44-132">Not applicable.</span></span>|<xref:System.Linq.Enumerable.Min%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.Min%2A?displayProperty=nameWithType>|  
|<span data-ttu-id="afa44-133">Sum</span><span class="sxs-lookup"><span data-stu-id="afa44-133">Sum</span></span>|<span data-ttu-id="afa44-134">对集合中的值求和。</span><span class="sxs-lookup"><span data-stu-id="afa44-134">Calculates the sum of the values in a collection.</span></span>|<span data-ttu-id="afa44-135">不适用。</span><span class="sxs-lookup"><span data-stu-id="afa44-135">Not applicable.</span></span>|<xref:System.Linq.Enumerable.Sum%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.Sum%2A?displayProperty=nameWithType>|  
  
## <a name="see-also"></a><span data-ttu-id="afa44-136">另请参阅</span><span class="sxs-lookup"><span data-stu-id="afa44-136">See Also</span></span>  
 <xref:System.Linq>  
 [<span data-ttu-id="afa44-137">标准查询运算符概述 (C#)</span><span class="sxs-lookup"><span data-stu-id="afa44-137">Standard Query Operators Overview (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/standard-query-operators-overview.md)  
 [<span data-ttu-id="afa44-138">如何：在 CSV 文本文件中计算列值 (LINQ) (C#)</span><span class="sxs-lookup"><span data-stu-id="afa44-138">How to: Compute Column Values in a CSV Text File (LINQ) (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/how-to-compute-column-values-in-a-csv-text-file-linq.md)  
 [<span data-ttu-id="afa44-139">如何：查询目录树中的一个或多个最大的文件 (LINQ) (C#)</span><span class="sxs-lookup"><span data-stu-id="afa44-139">How to: Query for the Largest File or Files in a Directory Tree (LINQ) (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/how-to-query-for-the-largest-file-or-files-in-a-directory-tree-linq.md)  
 [<span data-ttu-id="afa44-140">如何：查询一组文件夹中的总字节数 (LINQ) (C#)</span><span class="sxs-lookup"><span data-stu-id="afa44-140">How to: Query for the Total Number of Bytes in a Set of Folders (LINQ) (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/how-to-query-for-the-total-number-of-bytes-in-a-set-of-folders-linq.md)
