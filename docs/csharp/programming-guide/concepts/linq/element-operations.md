---
title: "元素运算 (C#)"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
ms.assetid: 283206c9-3246-4c48-b01a-d9de409a7231
caps.latest.revision: 3
author: BillWagner
ms.author: wiwagn
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: da747e884960c89fabc45d3761da92f913d66362
ms.contentlocale: zh-cn
ms.lasthandoff: 07/28/2017

---
# <a name="element-operations-c"></a><span data-ttu-id="2a6d4-102">元素运算 (C#)</span><span class="sxs-lookup"><span data-stu-id="2a6d4-102">Element Operations (C#)</span></span>
<span data-ttu-id="2a6d4-103">元素运算从序列中返回唯一、特定的元素。</span><span class="sxs-lookup"><span data-stu-id="2a6d4-103">Element operations return a single, specific element from a sequence.</span></span>  
  
 <span data-ttu-id="2a6d4-104">下节列出了执行元素运算的标准查询运算符方法。</span><span class="sxs-lookup"><span data-stu-id="2a6d4-104">The standard query operator methods that perform element operations are listed in the following section.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="2a6d4-105">方法</span><span class="sxs-lookup"><span data-stu-id="2a6d4-105">Methods</span></span>  
  
|<span data-ttu-id="2a6d4-106">方法名</span><span class="sxs-lookup"><span data-stu-id="2a6d4-106">Method Name</span></span>|<span data-ttu-id="2a6d4-107">描述</span><span class="sxs-lookup"><span data-stu-id="2a6d4-107">Description</span></span>|<span data-ttu-id="2a6d4-108">C# 查询表达式语法</span><span class="sxs-lookup"><span data-stu-id="2a6d4-108">C# Query Expression Syntax</span></span>|<span data-ttu-id="2a6d4-109">更多信息</span><span class="sxs-lookup"><span data-stu-id="2a6d4-109">More Information</span></span>|  
|-----------------|-----------------|---------------------------------|----------------------|  
|<span data-ttu-id="2a6d4-110">ElementAt</span><span class="sxs-lookup"><span data-stu-id="2a6d4-110">ElementAt</span></span>|<span data-ttu-id="2a6d4-111">返回集合中指定索引处的元素。</span><span class="sxs-lookup"><span data-stu-id="2a6d4-111">Returns the element at a specified index in a collection.</span></span>|<span data-ttu-id="2a6d4-112">不适用。</span><span class="sxs-lookup"><span data-stu-id="2a6d4-112">Not applicable.</span></span>|<xref:System.Linq.Enumerable.ElementAt%2A?displayProperty=fullName><br /><br /> <xref:System.Linq.Queryable.ElementAt%2A?displayProperty=fullName>|  
|<span data-ttu-id="2a6d4-113">ElementAtOrDefault</span><span class="sxs-lookup"><span data-stu-id="2a6d4-113">ElementAtOrDefault</span></span>|<span data-ttu-id="2a6d4-114">返回集合中指定索引处的元素；如果索引超出范围，则返回默认值。</span><span class="sxs-lookup"><span data-stu-id="2a6d4-114">Returns the element at a specified index in a collection or a default value if the index is out of range.</span></span>|<span data-ttu-id="2a6d4-115">不适用。</span><span class="sxs-lookup"><span data-stu-id="2a6d4-115">Not applicable.</span></span>|<xref:System.Linq.Enumerable.ElementAtOrDefault%2A?displayProperty=fullName><br /><br /> <xref:System.Linq.Queryable.ElementAtOrDefault%2A?displayProperty=fullName>|  
|<span data-ttu-id="2a6d4-116">First</span><span class="sxs-lookup"><span data-stu-id="2a6d4-116">First</span></span>|<span data-ttu-id="2a6d4-117">返回集合的第一个元素或满足条件的第一个元素。</span><span class="sxs-lookup"><span data-stu-id="2a6d4-117">Returns the first element of a collection, or the first element that satisfies a condition.</span></span>|<span data-ttu-id="2a6d4-118">不适用。</span><span class="sxs-lookup"><span data-stu-id="2a6d4-118">Not applicable.</span></span>|<xref:System.Linq.Enumerable.First%2A?displayProperty=fullName><br /><br /> <xref:System.Linq.Queryable.First%2A?displayProperty=fullName>|  
|<span data-ttu-id="2a6d4-119">FirstOrDefault</span><span class="sxs-lookup"><span data-stu-id="2a6d4-119">FirstOrDefault</span></span>|<span data-ttu-id="2a6d4-120">返回集合的第一个元素或满足条件的第一个元素。</span><span class="sxs-lookup"><span data-stu-id="2a6d4-120">Returns the first element of a collection, or the first element that satisfies a condition.</span></span> <span data-ttu-id="2a6d4-121">如果此类元素不存在，则返回默认值。</span><span class="sxs-lookup"><span data-stu-id="2a6d4-121">Returns a default value if no such element exists.</span></span>|<span data-ttu-id="2a6d4-122">不适用。</span><span class="sxs-lookup"><span data-stu-id="2a6d4-122">Not applicable.</span></span>|<xref:System.Linq.Enumerable.FirstOrDefault%2A?displayProperty=fullName><br /><br /> <xref:System.Linq.Queryable.FirstOrDefault%2A?displayProperty=fullName><br /><br /> <xref:System.Linq.Queryable.FirstOrDefault%60%601%28System.Linq.IQueryable%7B%60%600%7D%29?displayProperty=fullName>|  
|<span data-ttu-id="2a6d4-123">上一个</span><span class="sxs-lookup"><span data-stu-id="2a6d4-123">Last</span></span>|<span data-ttu-id="2a6d4-124">返回集合的最后一个元素或满足条件的最后一个元素。</span><span class="sxs-lookup"><span data-stu-id="2a6d4-124">Returns the last element of a collection, or the last element that satisfies a condition.</span></span>|<span data-ttu-id="2a6d4-125">不适用。</span><span class="sxs-lookup"><span data-stu-id="2a6d4-125">Not applicable.</span></span>|<xref:System.Linq.Enumerable.Last%2A?displayProperty=fullName><br /><br /> <xref:System.Linq.Queryable.Last%2A?displayProperty=fullName>|  
|<span data-ttu-id="2a6d4-126">LastOrDefault</span><span class="sxs-lookup"><span data-stu-id="2a6d4-126">LastOrDefault</span></span>|<span data-ttu-id="2a6d4-127">返回集合的最后一个元素或满足条件的最后一个元素。</span><span class="sxs-lookup"><span data-stu-id="2a6d4-127">Returns the last element of a collection, or the last element that satisfies a condition.</span></span> <span data-ttu-id="2a6d4-128">如果此类元素不存在，则返回默认值。</span><span class="sxs-lookup"><span data-stu-id="2a6d4-128">Returns a default value if no such element exists.</span></span>|<span data-ttu-id="2a6d4-129">不适用。</span><span class="sxs-lookup"><span data-stu-id="2a6d4-129">Not applicable.</span></span>|<xref:System.Linq.Enumerable.LastOrDefault%2A?displayProperty=fullName><br /><br /> <xref:System.Linq.Queryable.LastOrDefault%2A?displayProperty=fullName>|  
|<span data-ttu-id="2a6d4-130">Single</span><span class="sxs-lookup"><span data-stu-id="2a6d4-130">Single</span></span>|<span data-ttu-id="2a6d4-131">返回集合的唯一一个元素或满足条件的唯一一个元素。</span><span class="sxs-lookup"><span data-stu-id="2a6d4-131">Returns the only element of a collection, or the only element that satisfies a condition.</span></span>|<span data-ttu-id="2a6d4-132">不适用。</span><span class="sxs-lookup"><span data-stu-id="2a6d4-132">Not applicable.</span></span>|<xref:System.Linq.Enumerable.Single%2A?displayProperty=fullName><br /><br /> <xref:System.Linq.Queryable.Single%2A?displayProperty=fullName>|  
|<span data-ttu-id="2a6d4-133">SingleOrDefault</span><span class="sxs-lookup"><span data-stu-id="2a6d4-133">SingleOrDefault</span></span>|<span data-ttu-id="2a6d4-134">返回集合的唯一一个元素或满足条件的唯一一个元素。</span><span class="sxs-lookup"><span data-stu-id="2a6d4-134">Returns the only element of a collection, or the only element that satisfies a condition.</span></span> <span data-ttu-id="2a6d4-135">如果此类元素不存在，或该集合不是仅包含一个元素，则返回默认值。</span><span class="sxs-lookup"><span data-stu-id="2a6d4-135">Returns a default value if no such element exists or the collection does not contain exactly one element.</span></span>|<span data-ttu-id="2a6d4-136">不适用。</span><span class="sxs-lookup"><span data-stu-id="2a6d4-136">Not applicable.</span></span>|<xref:System.Linq.Enumerable.SingleOrDefault%2A?displayProperty=fullName><br /><br /> <xref:System.Linq.Queryable.SingleOrDefault%2A?displayProperty=fullName>|  
  
## <a name="see-also"></a><span data-ttu-id="2a6d4-137">另请参阅</span><span class="sxs-lookup"><span data-stu-id="2a6d4-137">See Also</span></span>  
 <span data-ttu-id="2a6d4-138"><xref:System.Linq></span><span class="sxs-lookup"><span data-stu-id="2a6d4-138"><xref:System.Linq></span></span>   
 <span data-ttu-id="2a6d4-139">[标准查询运算符概述 (C#)](../../../../csharp/programming-guide/concepts/linq/standard-query-operators-overview.md) </span><span class="sxs-lookup"><span data-stu-id="2a6d4-139">[Standard Query Operators Overview (C#)](../../../../csharp/programming-guide/concepts/linq/standard-query-operators-overview.md) </span></span>  
 [<span data-ttu-id="2a6d4-140">如何：查询目录树中的一个或多个最大的文件 (LINQ) (C#)</span><span class="sxs-lookup"><span data-stu-id="2a6d4-140">How to: Query for the Largest File or Files in a Directory Tree (LINQ) (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/how-to-query-for-the-largest-file-or-files-in-a-directory-tree-linq.md)

