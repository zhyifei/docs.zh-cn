---
title: 限定符运算 (C#)
ms.date: 07/20/2015
ms.assetid: 84ac2ac2-7a63-4581-bc4c-14e34be1493b
ms.openlocfilehash: 5c931e0971a2ae7970415905be8772a64a82ee39
ms.sourcegitcommit: 7bc6887ab658550baa78f1520ea735838249345e
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/03/2020
ms.locfileid: "75635478"
---
# <a name="quantifier-operations-c"></a><span data-ttu-id="3fd4a-102">限定符运算 (C#)</span><span class="sxs-lookup"><span data-stu-id="3fd4a-102">Quantifier Operations (C#)</span></span>
<span data-ttu-id="3fd4a-103">限定符运算返回一个 <xref:System.Boolean> 值，该值指示序列中是否有一些元素满足条件或是否所有元素都满足条件。</span><span class="sxs-lookup"><span data-stu-id="3fd4a-103">Quantifier operations return a <xref:System.Boolean> value that indicates whether some or all of the elements in a sequence satisfy a condition.</span></span>  
  
 <span data-ttu-id="3fd4a-104">下图描述了两个不同源序列上的两个不同限定符运算。</span><span class="sxs-lookup"><span data-stu-id="3fd4a-104">The following illustration depicts two different quantifier operations on two different source sequences.</span></span> <span data-ttu-id="3fd4a-105">第一个运算询问是否有一个或多个元素为字符“A”，结果为 `true`。</span><span class="sxs-lookup"><span data-stu-id="3fd4a-105">The first operation asks if one or more of the elements are the character 'A', and the result is `true`.</span></span> <span data-ttu-id="3fd4a-106">第二个运算询问是否所有元素都为字符“A”，结果为 `true`。</span><span class="sxs-lookup"><span data-stu-id="3fd4a-106">The second operation asks if all the elements are the character 'A', and the result is `true`.</span></span>  
  
 ![LINQ 限定符运算](./media/quantifier-operations/linq-quantifier-operations.png)  
  
 <span data-ttu-id="3fd4a-108">下节列出了执行限定符运算的标准查询运算符方法。</span><span class="sxs-lookup"><span data-stu-id="3fd4a-108">The standard query operator methods that perform quantifier operations are listed in the following section.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="3fd4a-109">方法</span><span class="sxs-lookup"><span data-stu-id="3fd4a-109">Methods</span></span>  
  
|<span data-ttu-id="3fd4a-110">方法名</span><span class="sxs-lookup"><span data-stu-id="3fd4a-110">Method Name</span></span>|<span data-ttu-id="3fd4a-111">描述</span><span class="sxs-lookup"><span data-stu-id="3fd4a-111">Description</span></span>|<span data-ttu-id="3fd4a-112">C# 查询表达式语法</span><span class="sxs-lookup"><span data-stu-id="3fd4a-112">C# Query Expression Syntax</span></span>|<span data-ttu-id="3fd4a-113">详细信息</span><span class="sxs-lookup"><span data-stu-id="3fd4a-113">More Information</span></span>|  
|-----------------|-----------------|---------------------------------|----------------------|  
|<span data-ttu-id="3fd4a-114">全部</span><span class="sxs-lookup"><span data-stu-id="3fd4a-114">All</span></span>|<span data-ttu-id="3fd4a-115">确定是否序列中的所有元素都满足条件。</span><span class="sxs-lookup"><span data-stu-id="3fd4a-115">Determines whether all the elements in a sequence satisfy a condition.</span></span>|<span data-ttu-id="3fd4a-116">不适用。</span><span class="sxs-lookup"><span data-stu-id="3fd4a-116">Not applicable.</span></span>|<xref:System.Linq.Enumerable.All%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.All%2A?displayProperty=nameWithType>|  
|<span data-ttu-id="3fd4a-117">任意</span><span class="sxs-lookup"><span data-stu-id="3fd4a-117">Any</span></span>|<span data-ttu-id="3fd4a-118">确定序列中是否有元素满足条件。</span><span class="sxs-lookup"><span data-stu-id="3fd4a-118">Determines whether any elements in a sequence satisfy a condition.</span></span>|<span data-ttu-id="3fd4a-119">不适用。</span><span class="sxs-lookup"><span data-stu-id="3fd4a-119">Not applicable.</span></span>|<xref:System.Linq.Enumerable.Any%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.Any%2A?displayProperty=nameWithType>|  
|<span data-ttu-id="3fd4a-120">包含</span><span class="sxs-lookup"><span data-stu-id="3fd4a-120">Contains</span></span>|<span data-ttu-id="3fd4a-121">确定序列是否包含指定的元素。</span><span class="sxs-lookup"><span data-stu-id="3fd4a-121">Determines whether a sequence contains a specified element.</span></span>|<span data-ttu-id="3fd4a-122">不适用。</span><span class="sxs-lookup"><span data-stu-id="3fd4a-122">Not applicable.</span></span>|<xref:System.Linq.Enumerable.Contains%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.Contains%2A?displayProperty=nameWithType>|  

## <a name="query-expression-syntax-examples"></a><span data-ttu-id="3fd4a-123">查询表达式语法示例</span><span class="sxs-lookup"><span data-stu-id="3fd4a-123">Query Expression Syntax Examples</span></span>  
  
### <a name="all"></a><span data-ttu-id="3fd4a-124">全部</span><span class="sxs-lookup"><span data-stu-id="3fd4a-124">All</span></span>  
<span data-ttu-id="3fd4a-125">以下示例使用 `All` 检查所有字符串是否为特定长度。</span><span class="sxs-lookup"><span data-stu-id="3fd4a-125">The following example uses the `All` to check that all strings are of a specific length.</span></span>
  
[!code-csharp[All](~/samples/snippets/csharp/VS_Snippets_VBCSharp/CsLINQQuantifier/CS/Quantifier.cs#All)]  
  
### <a name="any"></a><span data-ttu-id="3fd4a-126">任意</span><span class="sxs-lookup"><span data-stu-id="3fd4a-126">Any</span></span>  
<span data-ttu-id="3fd4a-127">以下示例使用 `Any` 检查所有字符串是否以“o”开头。</span><span class="sxs-lookup"><span data-stu-id="3fd4a-127">The following example uses the `Any` to check that any strings are start with 'o'.</span></span>  
  
[!code-csharp[Any](~/samples/snippets/csharp/VS_Snippets_VBCSharp/CsLINQQuantifier/CS/Quantifier.cs#Any)]  
  
### <a name="contains"></a><span data-ttu-id="3fd4a-128">包含</span><span class="sxs-lookup"><span data-stu-id="3fd4a-128">Contains</span></span>  
<span data-ttu-id="3fd4a-129">以下示例使用 `Contains` 检查所有数组是否具有特定元素。</span><span class="sxs-lookup"><span data-stu-id="3fd4a-129">The following example uses the `Contains` to check an array have a specific element.</span></span>  
  
[!code-csharp[Contains](~/samples/snippets/csharp/VS_Snippets_VBCSharp/CsLINQQuantifier/CS/Quantifier.cs#Contains)]  
  
## <a name="see-also"></a><span data-ttu-id="3fd4a-130">请参阅</span><span class="sxs-lookup"><span data-stu-id="3fd4a-130">See also</span></span>

- <xref:System.Linq>
- [<span data-ttu-id="3fd4a-131">标准查询运算符概述 (C#)</span><span class="sxs-lookup"><span data-stu-id="3fd4a-131">Standard Query Operators Overview (C#)</span></span>](./standard-query-operators-overview.md)
- [<span data-ttu-id="3fd4a-132">在运行时动态指定谓词筛选器</span><span class="sxs-lookup"><span data-stu-id="3fd4a-132">Dynamically specify predicate filters at runtime</span></span>](../../../linq/dynamically-specify-predicate-filters-at-runtime.md)
- [<span data-ttu-id="3fd4a-133">如何查询包含一组指定词语的句子 (LINQ) (C#)</span><span class="sxs-lookup"><span data-stu-id="3fd4a-133">How to query for sentences that contain a specified set of words (LINQ) (C#)</span></span>](./how-to-query-for-sentences-that-contain-a-specified-set-of-words-linq.md)
