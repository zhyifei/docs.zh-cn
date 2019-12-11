---
title: 集运算 (C#)
ms.date: 07/20/2015
ms.assetid: 7c589367-ef8f-4161-9050-642c47e6bf63
ms.openlocfilehash: 22079b1d41533803f694af210f98bc9fb8a5b322
ms.sourcegitcommit: 5fb5b6520b06d7f5e6131ec2ad854da302a28f2e
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/03/2019
ms.locfileid: "74711873"
---
# <a name="set-operations-c"></a><span data-ttu-id="646ee-102">集运算 (C#)</span><span class="sxs-lookup"><span data-stu-id="646ee-102">Set Operations (C#)</span></span>
<span data-ttu-id="646ee-103">LINQ 中的集运算是指根据相同或不同集合（或集）中是否存在等效元素来生成结果集的查询运算。</span><span class="sxs-lookup"><span data-stu-id="646ee-103">Set operations in LINQ refer to query operations that produce a result set that is based on the presence or absence of equivalent elements within the same or separate collections (or sets).</span></span>  
  
 <span data-ttu-id="646ee-104">下节列出了执行集运算的标准查询运算符方法。</span><span class="sxs-lookup"><span data-stu-id="646ee-104">The standard query operator methods that perform set operations are listed in the following section.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="646ee-105">方法</span><span class="sxs-lookup"><span data-stu-id="646ee-105">Methods</span></span>  
  
|<span data-ttu-id="646ee-106">方法名</span><span class="sxs-lookup"><span data-stu-id="646ee-106">Method Name</span></span>|<span data-ttu-id="646ee-107">说明</span><span class="sxs-lookup"><span data-stu-id="646ee-107">Description</span></span>|<span data-ttu-id="646ee-108">C# 查询表达式语法</span><span class="sxs-lookup"><span data-stu-id="646ee-108">C# Query Expression Syntax</span></span>|<span data-ttu-id="646ee-109">详细信息</span><span class="sxs-lookup"><span data-stu-id="646ee-109">More Information</span></span>|  
|-----------------|-----------------|---------------------------------|----------------------|  
|<span data-ttu-id="646ee-110">Distinct</span><span class="sxs-lookup"><span data-stu-id="646ee-110">Distinct</span></span>|<span data-ttu-id="646ee-111">删除集合中的重复值。</span><span class="sxs-lookup"><span data-stu-id="646ee-111">Removes duplicate values from a collection.</span></span>|<span data-ttu-id="646ee-112">不适用。</span><span class="sxs-lookup"><span data-stu-id="646ee-112">Not applicable.</span></span>|<xref:System.Linq.Enumerable.Distinct%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.Distinct%2A?displayProperty=nameWithType>|  
|<span data-ttu-id="646ee-113">Except</span><span class="sxs-lookup"><span data-stu-id="646ee-113">Except</span></span>|<span data-ttu-id="646ee-114">返回差集，差集指位于一个集合但不位于另一个集合的元素。</span><span class="sxs-lookup"><span data-stu-id="646ee-114">Returns the set difference, which means the elements of one collection that do not appear in a second collection.</span></span>|<span data-ttu-id="646ee-115">不适用。</span><span class="sxs-lookup"><span data-stu-id="646ee-115">Not applicable.</span></span>|<xref:System.Linq.Enumerable.Except%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.Except%2A?displayProperty=nameWithType>|  
|<span data-ttu-id="646ee-116">相交</span><span class="sxs-lookup"><span data-stu-id="646ee-116">Intersect</span></span>|<span data-ttu-id="646ee-117">返回交集，交集指同时出现在两个集合中的元素。</span><span class="sxs-lookup"><span data-stu-id="646ee-117">Returns the set intersection, which means elements that appear in each of two collections.</span></span>|<span data-ttu-id="646ee-118">不适用。</span><span class="sxs-lookup"><span data-stu-id="646ee-118">Not applicable.</span></span>|<xref:System.Linq.Enumerable.Intersect%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.Intersect%2A?displayProperty=nameWithType>|  
|<span data-ttu-id="646ee-119">联合</span><span class="sxs-lookup"><span data-stu-id="646ee-119">Union</span></span>|<span data-ttu-id="646ee-120">返回并集，并集指位于两个集合中任一集合的唯一的元素。</span><span class="sxs-lookup"><span data-stu-id="646ee-120">Returns the set union, which means unique elements that appear in either of two collections.</span></span>|<span data-ttu-id="646ee-121">不适用。</span><span class="sxs-lookup"><span data-stu-id="646ee-121">Not applicable.</span></span>|<xref:System.Linq.Enumerable.Union%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.Union%2A?displayProperty=nameWithType>|  
  
## <a name="comparison-of-set-operations"></a><span data-ttu-id="646ee-122">比较集运算</span><span class="sxs-lookup"><span data-stu-id="646ee-122">Comparison of Set Operations</span></span>  
  
### <a name="distinct"></a><span data-ttu-id="646ee-123">Distinct</span><span class="sxs-lookup"><span data-stu-id="646ee-123">Distinct</span></span>  
 <span data-ttu-id="646ee-124">以下示例演示字符序列上 <xref:System.Linq.Enumerable.Distinct%2A?displayProperty=nameWithType> 方法的行为。</span><span class="sxs-lookup"><span data-stu-id="646ee-124">The following example depicts the behavior of the <xref:System.Linq.Enumerable.Distinct%2A?displayProperty=nameWithType> method on a sequence of characters.</span></span> <span data-ttu-id="646ee-125">返回的序列包含输入序列的唯一元素。</span><span class="sxs-lookup"><span data-stu-id="646ee-125">The returned sequence contains the unique elements from the input sequence.</span></span>  
  
 ![显示 Distinct() 的行为的图。](./media/set-operations/distinct-method-behavior.png)  
 
 [!code-csharp-interactive[Distinct](~/samples/snippets/csharp/VS_Snippets_VBCSharp/CsLINQSetOperation/CS/SetOperation.cs#1)]
  
### <a name="except"></a><span data-ttu-id="646ee-127">Except</span><span class="sxs-lookup"><span data-stu-id="646ee-127">Except</span></span>  
 <span data-ttu-id="646ee-128">以下示例演示 <xref:System.Linq.Enumerable.Except%2A?displayProperty=nameWithType> 的行为。</span><span class="sxs-lookup"><span data-stu-id="646ee-128">The following example depicts the behavior of <xref:System.Linq.Enumerable.Except%2A?displayProperty=nameWithType>.</span></span> <span data-ttu-id="646ee-129">返回的序列只包含位于第一个输入序列但不位于第二个输入序列的元素。</span><span class="sxs-lookup"><span data-stu-id="646ee-129">The returned sequence contains only the elements from the first input sequence that are not in the second input sequence.</span></span>  
  
 <span data-ttu-id="646ee-130">![显示 Except() 的操作的图](./media/set-operations/except-behavior-graphic.png "显示 Except 的行为。")</span><span class="sxs-lookup"><span data-stu-id="646ee-130">![Graphic showing the action of Except&#40;&#41;.](./media/set-operations/except-behavior-graphic.png "Shows the behavior of Except.")</span></span>  
  
[!code-csharp-interactive[Except](~/samples/snippets/csharp/VS_Snippets_VBCSharp/CsLINQSetOperation/CS/SetOperation.cs#2)]

### <a name="intersect"></a><span data-ttu-id="646ee-131">相交</span><span class="sxs-lookup"><span data-stu-id="646ee-131">Intersect</span></span>  
 <span data-ttu-id="646ee-132">以下示例演示 <xref:System.Linq.Enumerable.Intersect%2A?displayProperty=nameWithType> 的行为。</span><span class="sxs-lookup"><span data-stu-id="646ee-132">The following example depicts the behavior of <xref:System.Linq.Enumerable.Intersect%2A?displayProperty=nameWithType>.</span></span> <span data-ttu-id="646ee-133">返回的序列包含两个输入序列共有的元素。</span><span class="sxs-lookup"><span data-stu-id="646ee-133">The returned sequence contains the elements that are common to both of the input sequences.</span></span>  
  
 ![显示两个序列的交集的图。](./media/set-operations/intersection-two-sequences.png)  
 
[!code-csharp-interactive[Intersect](~/samples/snippets/csharp/VS_Snippets_VBCSharp/CsLINQSetOperation/CS/SetOperation.cs#3)]

### <a name="union"></a><span data-ttu-id="646ee-135">联合</span><span class="sxs-lookup"><span data-stu-id="646ee-135">Union</span></span>  
 <span data-ttu-id="646ee-136">以下示例演示对两个字符序列执行的联合操作。</span><span class="sxs-lookup"><span data-stu-id="646ee-136">The following example depicts a union operation on two sequences of characters.</span></span> <span data-ttu-id="646ee-137">返回的序列包含两个输入序列的唯一元素。</span><span class="sxs-lookup"><span data-stu-id="646ee-137">The returned sequence contains the unique elements from both input sequences.</span></span>  
  
 ![显示两个序列的并集的图。](./media/set-operations/union-operation-two-sequences.png)  

[!code-csharp-interactive[Union](~/samples/snippets/csharp/VS_Snippets_VBCSharp/CsLINQSetOperation/CS/SetOperation.cs#4)]
 
## <a name="see-also"></a><span data-ttu-id="646ee-139">请参阅</span><span class="sxs-lookup"><span data-stu-id="646ee-139">See also</span></span>

- <xref:System.Linq>
- [<span data-ttu-id="646ee-140">标准查询运算符概述 (C#)</span><span class="sxs-lookup"><span data-stu-id="646ee-140">Standard Query Operators Overview (C#)</span></span>](./standard-query-operators-overview.md)
- [<span data-ttu-id="646ee-141">如何合并和比较字符串集合 (LINQ) (C#)</span><span class="sxs-lookup"><span data-stu-id="646ee-141">How to combine and compare string collections (LINQ) (C#)</span></span>](./how-to-combine-and-compare-string-collections-linq.md)
- [<span data-ttu-id="646ee-142">如何：查找两个列表之间的差集 (LINQ) (C#)</span><span class="sxs-lookup"><span data-stu-id="646ee-142">How to: Find the Set Difference Between Two Lists (LINQ) (C#)</span></span>](./how-to-find-the-set-difference-between-two-lists-linq.md)
