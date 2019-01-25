---
title: 设置操作 (Visual Basic)
ms.date: 07/20/2015
ms.assetid: 2b06e822-e030-438f-9db7-ee402bd3a706
ms.openlocfilehash: b1b515c7eee11f7aadc1d34223dbb4ea1367842d
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54741868"
---
# <a name="set-operations-visual-basic"></a><span data-ttu-id="87a62-102">设置操作 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="87a62-102">Set Operations (Visual Basic)</span></span>
<span data-ttu-id="87a62-103">LINQ 中的集运算是指根据相同或不同集合（或集）中是否存在等效元素来生成结果集的查询运算。</span><span class="sxs-lookup"><span data-stu-id="87a62-103">Set operations in LINQ refer to query operations that produce a result set that is based on the presence or absence of equivalent elements within the same or separate collections (or sets).</span></span>  
  
 <span data-ttu-id="87a62-104">下节列出了执行集运算的标准查询运算符方法。</span><span class="sxs-lookup"><span data-stu-id="87a62-104">The standard query operator methods that perform set operations are listed in the following section.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="87a62-105">方法</span><span class="sxs-lookup"><span data-stu-id="87a62-105">Methods</span></span>  
  
|<span data-ttu-id="87a62-106">方法名</span><span class="sxs-lookup"><span data-stu-id="87a62-106">Method Name</span></span>|<span data-ttu-id="87a62-107">描述</span><span class="sxs-lookup"><span data-stu-id="87a62-107">Description</span></span>|<span data-ttu-id="87a62-108">Visual Basic 查询表达式语法</span><span class="sxs-lookup"><span data-stu-id="87a62-108">Visual Basic Query Expression Syntax</span></span>|<span data-ttu-id="87a62-109">详细信息</span><span class="sxs-lookup"><span data-stu-id="87a62-109">More Information</span></span>|  
|-----------------|-----------------|------------------------------------------|----------------------|  
|<span data-ttu-id="87a62-110">Distinct</span><span class="sxs-lookup"><span data-stu-id="87a62-110">Distinct</span></span>|<span data-ttu-id="87a62-111">删除集合中的重复值。</span><span class="sxs-lookup"><span data-stu-id="87a62-111">Removes duplicate values from a collection.</span></span>|`Distinct`|<xref:System.Linq.Enumerable.Distinct%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.Distinct%2A?displayProperty=nameWithType>|  
|<span data-ttu-id="87a62-112">Except</span><span class="sxs-lookup"><span data-stu-id="87a62-112">Except</span></span>|<span data-ttu-id="87a62-113">返回差集，差集指位于一个集合但不位于另一个集合的元素。</span><span class="sxs-lookup"><span data-stu-id="87a62-113">Returns the set difference, which means the elements of one collection that do not appear in a second collection.</span></span>|<span data-ttu-id="87a62-114">不适用。</span><span class="sxs-lookup"><span data-stu-id="87a62-114">Not applicable.</span></span>|<xref:System.Linq.Enumerable.Except%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.Except%2A?displayProperty=nameWithType>|  
|<span data-ttu-id="87a62-115">相交</span><span class="sxs-lookup"><span data-stu-id="87a62-115">Intersect</span></span>|<span data-ttu-id="87a62-116">返回交集，交集指同时出现在两个集合中的元素。</span><span class="sxs-lookup"><span data-stu-id="87a62-116">Returns the set intersection, which means elements that appear in each of two collections.</span></span>|<span data-ttu-id="87a62-117">不适用。</span><span class="sxs-lookup"><span data-stu-id="87a62-117">Not applicable.</span></span>|<xref:System.Linq.Enumerable.Intersect%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.Intersect%2A?displayProperty=nameWithType>|  
|<span data-ttu-id="87a62-118">联合</span><span class="sxs-lookup"><span data-stu-id="87a62-118">Union</span></span>|<span data-ttu-id="87a62-119">返回并集，并集指位于两个集合中任一集合的唯一的元素。</span><span class="sxs-lookup"><span data-stu-id="87a62-119">Returns the set union, which means unique elements that appear in either of two collections.</span></span>|<span data-ttu-id="87a62-120">不适用。</span><span class="sxs-lookup"><span data-stu-id="87a62-120">Not applicable.</span></span>|<xref:System.Linq.Enumerable.Union%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.Union%2A?displayProperty=nameWithType>|  
  
## <a name="comparison-of-set-operations"></a><span data-ttu-id="87a62-121">比较集运算</span><span class="sxs-lookup"><span data-stu-id="87a62-121">Comparison of Set Operations</span></span>  
  
### <a name="distinct"></a><span data-ttu-id="87a62-122">Distinct</span><span class="sxs-lookup"><span data-stu-id="87a62-122">Distinct</span></span>  
 <span data-ttu-id="87a62-123">下图演示字符序列上 <xref:System.Linq.Enumerable.Distinct%2A?displayProperty=nameWithType> 方法的行为。</span><span class="sxs-lookup"><span data-stu-id="87a62-123">The following illustration depicts the behavior of the <xref:System.Linq.Enumerable.Distinct%2A?displayProperty=nameWithType> method on a sequence of characters.</span></span> <span data-ttu-id="87a62-124">返回的序列包含输入序列的唯一元素。</span><span class="sxs-lookup"><span data-stu-id="87a62-124">The returned sequence contains the unique elements from the input sequence.</span></span>  
  
 <span data-ttu-id="87a62-125">![演示 Distinct&#40;&#41; 的行为的图。](../../../../csharp/programming-guide/concepts/linq/media/distinct.png "Distinct")</span><span class="sxs-lookup"><span data-stu-id="87a62-125">![Graphic showing the behavior of Distinct&#40;&#41;.](../../../../csharp/programming-guide/concepts/linq/media/distinct.png "Distinct")</span></span>  
  
### <a name="except"></a><span data-ttu-id="87a62-126">Except</span><span class="sxs-lookup"><span data-stu-id="87a62-126">Except</span></span>  
 <span data-ttu-id="87a62-127">下图演示 <xref:System.Linq.Enumerable.Except%2A?displayProperty=nameWithType> 的行为。</span><span class="sxs-lookup"><span data-stu-id="87a62-127">The following illustration depicts the behavior of <xref:System.Linq.Enumerable.Except%2A?displayProperty=nameWithType>.</span></span> <span data-ttu-id="87a62-128">返回的序列只包含位于第一个输入序列但不位于第二个输入序列的元素。</span><span class="sxs-lookup"><span data-stu-id="87a62-128">The returned sequence contains only the elements from the first input sequence that are not in the second input sequence.</span></span>  
  
 <span data-ttu-id="87a62-129">![显示 Except&#40;&#41; 的操作的图。](../../../../csharp/programming-guide/concepts/linq/media/except.png "Except")</span><span class="sxs-lookup"><span data-stu-id="87a62-129">![Graphic showing the action of Except&#40;&#41;.](../../../../csharp/programming-guide/concepts/linq/media/except.png "Except")</span></span>  
  
### <a name="intersect"></a><span data-ttu-id="87a62-130">相交</span><span class="sxs-lookup"><span data-stu-id="87a62-130">Intersect</span></span>  
 <span data-ttu-id="87a62-131">下图演示 <xref:System.Linq.Enumerable.Intersect%2A?displayProperty=nameWithType> 的行为。</span><span class="sxs-lookup"><span data-stu-id="87a62-131">The following illustration depicts the behavior of <xref:System.Linq.Enumerable.Intersect%2A?displayProperty=nameWithType>.</span></span> <span data-ttu-id="87a62-132">返回的序列包含两个输入序列共有的元素。</span><span class="sxs-lookup"><span data-stu-id="87a62-132">The returned sequence contains the elements that are common to both of the input sequences.</span></span>  
  
 <span data-ttu-id="87a62-133">![显示两个序列的交集的图。](../../../../csharp/programming-guide/concepts/linq/media/intersect.png "Intersect")</span><span class="sxs-lookup"><span data-stu-id="87a62-133">![Graphic showing the intersection of two sequences.](../../../../csharp/programming-guide/concepts/linq/media/intersect.png "Intersect")</span></span>  
  
### <a name="union"></a><span data-ttu-id="87a62-134">联合</span><span class="sxs-lookup"><span data-stu-id="87a62-134">Union</span></span>  
 <span data-ttu-id="87a62-135">下图演示对两个字符序列执行的联合操作。</span><span class="sxs-lookup"><span data-stu-id="87a62-135">The following illustration depicts a union operation on two sequences of characters.</span></span> <span data-ttu-id="87a62-136">返回的序列包含两个输入序列的唯一元素。</span><span class="sxs-lookup"><span data-stu-id="87a62-136">The returned sequence contains the unique elements from both input sequences.</span></span>  
  
 <span data-ttu-id="87a62-137">![显示两个序列的联合的图。](../../../../csharp/programming-guide/concepts/linq/media/union.png "Union")</span><span class="sxs-lookup"><span data-stu-id="87a62-137">![Graphic showing the union of two sequences.](../../../../csharp/programming-guide/concepts/linq/media/union.png "Union")</span></span>  
  
## <a name="query-expression-syntax-example"></a><span data-ttu-id="87a62-138">查询表达式语法示例</span><span class="sxs-lookup"><span data-stu-id="87a62-138">Query Expression Syntax Example</span></span>  
 <span data-ttu-id="87a62-139">下面的示例使用`Distinct`LINQ 查询从整数列表返回的唯一数字中的子句。</span><span class="sxs-lookup"><span data-stu-id="87a62-139">The following example uses the `Distinct` clause in a LINQ query to return the unique numbers from a list of integers.</span></span>  
  
 [!code-vb[CsLINQSetOps#1](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/set-operations_1.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="87a62-140">请参阅</span><span class="sxs-lookup"><span data-stu-id="87a62-140">See also</span></span>
- <xref:System.Linq>
- [<span data-ttu-id="87a62-141">标准查询运算符概述 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="87a62-141">Standard Query Operators Overview (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/standard-query-operators-overview.md)
- [<span data-ttu-id="87a62-142">Distinct 子句</span><span class="sxs-lookup"><span data-stu-id="87a62-142">Distinct Clause</span></span>](../../../../visual-basic/language-reference/queries/distinct-clause.md)
- [<span data-ttu-id="87a62-143">如何：合并和比较字符串集合 (LINQ) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="87a62-143">How to: Combine and Compare String Collections (LINQ) (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/how-to-combine-and-compare-string-collections-linq.md)
- [<span data-ttu-id="87a62-144">如何：查找两个列表 (LINQ) (Visual Basic 中) 之间的差集</span><span class="sxs-lookup"><span data-stu-id="87a62-144">How to: Find the Set Difference Between Two Lists (LINQ) (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/how-to-find-the-set-difference-between-two-lists-linq.md)
