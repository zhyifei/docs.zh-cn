---
title: "数据分区 (C#)"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-csharp
ms.topic: article
ms.assetid: 2a5c507b-fe22-443c-a768-dec7f9ec568d
caps.latest.revision: "3"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 32b95887e05767513dd818743dd1726149503b0f
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="partitioning-data-c"></a><span data-ttu-id="62b0e-102">数据分区 (C#)</span><span class="sxs-lookup"><span data-stu-id="62b0e-102">Partitioning Data (C#)</span></span>
<span data-ttu-id="62b0e-103">LINQ 中的分区是指将输入序列划分为两个部分的操作，无需重新排列元素，然后返回其中一个部分。</span><span class="sxs-lookup"><span data-stu-id="62b0e-103">Partitioning in LINQ refers to the operation of dividing an input sequence into two sections, without rearranging the elements, and then returning one of the sections.</span></span>  
  
 <span data-ttu-id="62b0e-104">下图显示对字符序列进行三种不同的分区操作的结果。</span><span class="sxs-lookup"><span data-stu-id="62b0e-104">The following illustration shows the results of three different partitioning operations on a sequence of characters.</span></span> <span data-ttu-id="62b0e-105">第一个操作返回序列中的前三个元素。</span><span class="sxs-lookup"><span data-stu-id="62b0e-105">The first operation returns the first three elements in the sequence.</span></span> <span data-ttu-id="62b0e-106">第二个操作跳过前三个元素，返回剩余元素。</span><span class="sxs-lookup"><span data-stu-id="62b0e-106">The second operation skips the first three elements and returns the remaining elements.</span></span> <span data-ttu-id="62b0e-107">第三个操作跳过序列中的前两个元素，返回接下来的三个元素。</span><span class="sxs-lookup"><span data-stu-id="62b0e-107">The third operation skips the first two elements in the sequence and returns the next three elements.</span></span>  
  
 <span data-ttu-id="62b0e-108">![LINQ 分区操作](../../../../csharp/programming-guide/concepts/linq/media/linq_partition.png "LINQ_Partition")</span><span class="sxs-lookup"><span data-stu-id="62b0e-108">![LINQ Partitioning Operations](../../../../csharp/programming-guide/concepts/linq/media/linq_partition.png "LINQ_Partition")</span></span>  
  
 <span data-ttu-id="62b0e-109">下面一节列出了对序列进行分区的标准查询运算符方法。</span><span class="sxs-lookup"><span data-stu-id="62b0e-109">The standard query operator methods that partition sequences are listed in the following section.</span></span>  
  
## <a name="operators"></a><span data-ttu-id="62b0e-110">运算符</span><span class="sxs-lookup"><span data-stu-id="62b0e-110">Operators</span></span>  
  
|<span data-ttu-id="62b0e-111">运算符名称</span><span class="sxs-lookup"><span data-stu-id="62b0e-111">Operator Name</span></span>|<span data-ttu-id="62b0e-112">描述</span><span class="sxs-lookup"><span data-stu-id="62b0e-112">Description</span></span>|<span data-ttu-id="62b0e-113">C# 查询表达式语法</span><span class="sxs-lookup"><span data-stu-id="62b0e-113">C# Query Expression Syntax</span></span>|<span data-ttu-id="62b0e-114">详细信息</span><span class="sxs-lookup"><span data-stu-id="62b0e-114">More Information</span></span>|  
|-------------------|-----------------|---------------------------------|----------------------|  
|<span data-ttu-id="62b0e-115">Skip</span><span class="sxs-lookup"><span data-stu-id="62b0e-115">Skip</span></span>|<span data-ttu-id="62b0e-116">跳过序列中指定位置之前的元素。</span><span class="sxs-lookup"><span data-stu-id="62b0e-116">Skips elements up to a specified position in a sequence.</span></span>|<span data-ttu-id="62b0e-117">不适用。</span><span class="sxs-lookup"><span data-stu-id="62b0e-117">Not applicable.</span></span>|<xref:System.Linq.Enumerable.Skip%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.Skip%2A?displayProperty=nameWithType>|  
|<span data-ttu-id="62b0e-118">SkipWhile</span><span class="sxs-lookup"><span data-stu-id="62b0e-118">SkipWhile</span></span>|<span data-ttu-id="62b0e-119">基于谓词函数跳过元素，直到元素不符合条件。</span><span class="sxs-lookup"><span data-stu-id="62b0e-119">Skips elements based on a predicate function until an element does not satisfy the condition.</span></span>|<span data-ttu-id="62b0e-120">不适用。</span><span class="sxs-lookup"><span data-stu-id="62b0e-120">Not applicable.</span></span>|<xref:System.Linq.Enumerable.SkipWhile%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.SkipWhile%2A?displayProperty=nameWithType>|  
|<span data-ttu-id="62b0e-121">Take</span><span class="sxs-lookup"><span data-stu-id="62b0e-121">Take</span></span>|<span data-ttu-id="62b0e-122">获取序列中指定位置之前的元素。</span><span class="sxs-lookup"><span data-stu-id="62b0e-122">Takes elements up to a specified position in a sequence.</span></span>|<span data-ttu-id="62b0e-123">不适用。</span><span class="sxs-lookup"><span data-stu-id="62b0e-123">Not applicable.</span></span>|<xref:System.Linq.Enumerable.Take%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.Take%2A?displayProperty=nameWithType>|  
|<span data-ttu-id="62b0e-124">TakeWhile</span><span class="sxs-lookup"><span data-stu-id="62b0e-124">TakeWhile</span></span>|<span data-ttu-id="62b0e-125">基于谓词函数获取元素，直到元素不符合条件。</span><span class="sxs-lookup"><span data-stu-id="62b0e-125">Takes elements based on a predicate function until an element does not satisfy the condition.</span></span>|<span data-ttu-id="62b0e-126">不适用。</span><span class="sxs-lookup"><span data-stu-id="62b0e-126">Not applicable.</span></span>|<xref:System.Linq.Enumerable.TakeWhile%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.TakeWhile%2A?displayProperty=nameWithType>|  
  
## <a name="see-also"></a><span data-ttu-id="62b0e-127">另请参阅</span><span class="sxs-lookup"><span data-stu-id="62b0e-127">See Also</span></span>  
 <xref:System.Linq>  
 [<span data-ttu-id="62b0e-128">标准查询运算符概述 (C#)</span><span class="sxs-lookup"><span data-stu-id="62b0e-128">Standard Query Operators Overview (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/standard-query-operators-overview.md)
