---
title: 限定符运算 (C#)
ms.date: 07/20/2015
ms.assetid: 84ac2ac2-7a63-4581-bc4c-14e34be1493b
ms.openlocfilehash: 090bc53c3dcedc82972ab7d16fa2968011a7db65
ms.sourcegitcommit: 3630c2515809e6f4b7dbb697a3354efec105a5cd
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/25/2019
ms.locfileid: "58412248"
---
# <a name="quantifier-operations-c"></a><span data-ttu-id="bcc6a-102">限定符运算 (C#)</span><span class="sxs-lookup"><span data-stu-id="bcc6a-102">Quantifier Operations (C#)</span></span>
<span data-ttu-id="bcc6a-103">限定符运算返回一个 <xref:System.Boolean> 值，该值指示序列中是否有一些元素满足条件或是否所有元素都满足条件。</span><span class="sxs-lookup"><span data-stu-id="bcc6a-103">Quantifier operations return a <xref:System.Boolean> value that indicates whether some or all of the elements in a sequence satisfy a condition.</span></span>  
  
 <span data-ttu-id="bcc6a-104">下图描述了两个不同源序列上的两个不同限定符运算。</span><span class="sxs-lookup"><span data-stu-id="bcc6a-104">The following illustration depicts two different quantifier operations on two different source sequences.</span></span> <span data-ttu-id="bcc6a-105">第一个运算询问是否有一个或多个元素为字符“A”，结果为 `true`。</span><span class="sxs-lookup"><span data-stu-id="bcc6a-105">The first operation asks if one or more of the elements are the character 'A', and the result is `true`.</span></span> <span data-ttu-id="bcc6a-106">第二个运算询问是否所有元素都为字符“A”，结果为 `true`。</span><span class="sxs-lookup"><span data-stu-id="bcc6a-106">The second operation asks if all the elements are the character 'A', and the result is `true`.</span></span>  
  
 ![LINQ 限定符运算](./media/quantifier-operations/linq-quantifier-operations.png)  
  
 <span data-ttu-id="bcc6a-108">下节列出了执行限定符运算的标准查询运算符方法。</span><span class="sxs-lookup"><span data-stu-id="bcc6a-108">The standard query operator methods that perform quantifier operations are listed in the following section.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="bcc6a-109">方法</span><span class="sxs-lookup"><span data-stu-id="bcc6a-109">Methods</span></span>  
  
|<span data-ttu-id="bcc6a-110">方法名</span><span class="sxs-lookup"><span data-stu-id="bcc6a-110">Method Name</span></span>|<span data-ttu-id="bcc6a-111">说明</span><span class="sxs-lookup"><span data-stu-id="bcc6a-111">Description</span></span>|<span data-ttu-id="bcc6a-112">C# 查询表达式语法</span><span class="sxs-lookup"><span data-stu-id="bcc6a-112">C# Query Expression Syntax</span></span>|<span data-ttu-id="bcc6a-113">详细信息</span><span class="sxs-lookup"><span data-stu-id="bcc6a-113">More Information</span></span>|  
|-----------------|-----------------|---------------------------------|----------------------|  
|<span data-ttu-id="bcc6a-114">全部</span><span class="sxs-lookup"><span data-stu-id="bcc6a-114">All</span></span>|<span data-ttu-id="bcc6a-115">确定是否序列中的所有元素都满足条件。</span><span class="sxs-lookup"><span data-stu-id="bcc6a-115">Determines whether all the elements in a sequence satisfy a condition.</span></span>|<span data-ttu-id="bcc6a-116">不适用。</span><span class="sxs-lookup"><span data-stu-id="bcc6a-116">Not applicable.</span></span>|<xref:System.Linq.Enumerable.All%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.All%2A?displayProperty=nameWithType>|  
|<span data-ttu-id="bcc6a-117">任意</span><span class="sxs-lookup"><span data-stu-id="bcc6a-117">Any</span></span>|<span data-ttu-id="bcc6a-118">确定序列中是否有元素满足条件。</span><span class="sxs-lookup"><span data-stu-id="bcc6a-118">Determines whether any elements in a sequence satisfy a condition.</span></span>|<span data-ttu-id="bcc6a-119">不适用。</span><span class="sxs-lookup"><span data-stu-id="bcc6a-119">Not applicable.</span></span>|<xref:System.Linq.Enumerable.Any%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.Any%2A?displayProperty=nameWithType>|  
|<span data-ttu-id="bcc6a-120">包含</span><span class="sxs-lookup"><span data-stu-id="bcc6a-120">Contains</span></span>|<span data-ttu-id="bcc6a-121">确定序列是否包含指定的元素。</span><span class="sxs-lookup"><span data-stu-id="bcc6a-121">Determines whether a sequence contains a specified element.</span></span>|<span data-ttu-id="bcc6a-122">不适用。</span><span class="sxs-lookup"><span data-stu-id="bcc6a-122">Not applicable.</span></span>|<xref:System.Linq.Enumerable.Contains%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.Contains%2A?displayProperty=nameWithType>|  
  
## <a name="see-also"></a><span data-ttu-id="bcc6a-123">请参阅</span><span class="sxs-lookup"><span data-stu-id="bcc6a-123">See also</span></span>

- <xref:System.Linq>
- [<span data-ttu-id="bcc6a-124">标准查询运算符概述 (C#)</span><span class="sxs-lookup"><span data-stu-id="bcc6a-124">Standard Query Operators Overview (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/standard-query-operators-overview.md)
- [<span data-ttu-id="bcc6a-125">如何：在运行时动态指定谓词筛选器</span><span class="sxs-lookup"><span data-stu-id="bcc6a-125">How to: Dynamically Specify Predicate Filters at Runtime</span></span>](../../../../csharp/programming-guide/linq-query-expressions/how-to-dynamically-specify-predicate-filters-at-runtime.md)
- [<span data-ttu-id="bcc6a-126">如何：查询包含一组指定词语的句子 (LINQ) (C#)</span><span class="sxs-lookup"><span data-stu-id="bcc6a-126">How to: Query for Sentences that Contain a Specified Set of Words (LINQ) (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/how-to-query-for-sentences-that-contain-a-specified-set-of-words-linq.md)
