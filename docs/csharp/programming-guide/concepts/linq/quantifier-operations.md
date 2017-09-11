---
title: "限定符运算 (C#)"
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
ms.assetid: 84ac2ac2-7a63-4581-bc4c-14e34be1493b
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
ms.openlocfilehash: f82df05693dffec64bcbc66cc2c0b9db2a7deb20
ms.contentlocale: zh-cn
ms.lasthandoff: 07/28/2017

---
# <a name="quantifier-operations-c"></a><span data-ttu-id="30292-102">限定符运算 (C#)</span><span class="sxs-lookup"><span data-stu-id="30292-102">Quantifier Operations (C#)</span></span>
<span data-ttu-id="30292-103">限定符运算返回一个 <xref:System.Boolean> 值，该值指示序列中是否有一些元素满足条件或是否所有元素都满足条件。</span><span class="sxs-lookup"><span data-stu-id="30292-103">Quantifier operations return a <xref:System.Boolean> value that indicates whether some or all of the elements in a sequence satisfy a condition.</span></span>  
  
 <span data-ttu-id="30292-104">下图描述了两个不同源序列上的两个不同限定符运算。</span><span class="sxs-lookup"><span data-stu-id="30292-104">The following illustration depicts two different quantifier operations on two different source sequences.</span></span> <span data-ttu-id="30292-105">第一个运算询问是否有一个或多个元素为字符“A”，结果为 `true`。</span><span class="sxs-lookup"><span data-stu-id="30292-105">The first operation asks if one or more of the elements are the character 'A', and the result is `true`.</span></span> <span data-ttu-id="30292-106">第二个运算询问是否所有元素都为字符“A”，结果为 `true`。</span><span class="sxs-lookup"><span data-stu-id="30292-106">The second operation asks if all the elements are the character 'A', and the result is `true`.</span></span>  
  
 <span data-ttu-id="30292-107">![LINQ 限定符运算](../../../../csharp/programming-guide/concepts/linq/media/linq_quantifier.png "LINQ_Quantifier")</span><span class="sxs-lookup"><span data-stu-id="30292-107">![LINQ Quantifier Operations](../../../../csharp/programming-guide/concepts/linq/media/linq_quantifier.png "LINQ_Quantifier")</span></span>  
  
 <span data-ttu-id="30292-108">下节列出了执行限定符运算的标准查询运算符方法。</span><span class="sxs-lookup"><span data-stu-id="30292-108">The standard query operator methods that perform quantifier operations are listed in the following section.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="30292-109">方法</span><span class="sxs-lookup"><span data-stu-id="30292-109">Methods</span></span>  
  
|<span data-ttu-id="30292-110">方法名</span><span class="sxs-lookup"><span data-stu-id="30292-110">Method Name</span></span>|<span data-ttu-id="30292-111">描述</span><span class="sxs-lookup"><span data-stu-id="30292-111">Description</span></span>|<span data-ttu-id="30292-112">C# 查询表达式语法</span><span class="sxs-lookup"><span data-stu-id="30292-112">C# Query Expression Syntax</span></span>|<span data-ttu-id="30292-113">详细信息</span><span class="sxs-lookup"><span data-stu-id="30292-113">More Information</span></span>|  
|-----------------|-----------------|---------------------------------|----------------------|  
|<span data-ttu-id="30292-114">全部</span><span class="sxs-lookup"><span data-stu-id="30292-114">All</span></span>|<span data-ttu-id="30292-115">确定是否序列中的所有元素都满足条件。</span><span class="sxs-lookup"><span data-stu-id="30292-115">Determines whether all the elements in a sequence satisfy a condition.</span></span>|<span data-ttu-id="30292-116">不适用。</span><span class="sxs-lookup"><span data-stu-id="30292-116">Not applicable.</span></span>|<xref:System.Linq.Enumerable.All%2A?displayProperty=fullName><br /><br /> <xref:System.Linq.Queryable.All%2A?displayProperty=fullName>|  
|<span data-ttu-id="30292-117">任意</span><span class="sxs-lookup"><span data-stu-id="30292-117">Any</span></span>|<span data-ttu-id="30292-118">确定序列中是否有元素满足条件。</span><span class="sxs-lookup"><span data-stu-id="30292-118">Determines whether any elements in a sequence satisfy a condition.</span></span>|<span data-ttu-id="30292-119">不适用。</span><span class="sxs-lookup"><span data-stu-id="30292-119">Not applicable.</span></span>|<xref:System.Linq.Enumerable.Any%2A?displayProperty=fullName><br /><br /> <xref:System.Linq.Queryable.Any%2A?displayProperty=fullName>|  
|<span data-ttu-id="30292-120">包含</span><span class="sxs-lookup"><span data-stu-id="30292-120">Contains</span></span>|<span data-ttu-id="30292-121">确定序列是否包含指定的元素。</span><span class="sxs-lookup"><span data-stu-id="30292-121">Determines whether a sequence contains a specified element.</span></span>|<span data-ttu-id="30292-122">不适用。</span><span class="sxs-lookup"><span data-stu-id="30292-122">Not applicable.</span></span>|<xref:System.Linq.Enumerable.Contains%2A?displayProperty=fullName><br /><br /> <xref:System.Linq.Queryable.Contains%2A?displayProperty=fullName>|  
  
## <a name="see-also"></a><span data-ttu-id="30292-123">另请参阅</span><span class="sxs-lookup"><span data-stu-id="30292-123">See Also</span></span>  
 <span data-ttu-id="30292-124"><xref:System.Linq></span><span class="sxs-lookup"><span data-stu-id="30292-124"><xref:System.Linq></span></span>   
 <span data-ttu-id="30292-125">[标准查询运算符概述 (C#)](../../../../csharp/programming-guide/concepts/linq/standard-query-operators-overview.md) </span><span class="sxs-lookup"><span data-stu-id="30292-125">[Standard Query Operators Overview (C#)](../../../../csharp/programming-guide/concepts/linq/standard-query-operators-overview.md) </span></span>  
 <span data-ttu-id="30292-126">[如何：在运行时动态指定谓词筛选器](../../../../csharp/programming-guide/linq-query-expressions/how-to-dynamically-specify-predicate-filters-at-runtime.md) </span><span class="sxs-lookup"><span data-stu-id="30292-126">[How to: Dynamically Specify Predicate Filters at Runtime](../../../../csharp/programming-guide/linq-query-expressions/how-to-dynamically-specify-predicate-filters-at-runtime.md) </span></span>  
 [<span data-ttu-id="30292-127">如何：查询包含一组指定词语的句子 (LINQ) (C#)</span><span class="sxs-lookup"><span data-stu-id="30292-127">How to: Query for Sentences that Contain a Specified Set of Words (LINQ) (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/how-to-query-for-sentences-that-contain-a-specified-set-of-words-linq.md)

