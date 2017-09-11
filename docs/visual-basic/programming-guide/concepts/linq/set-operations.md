---
title: "Set 运算 (Visual Basic 中) |Microsoft 文档"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
ms.assetid: 2b06e822-e030-438f-9db7-ee402bd3a706
caps.latest.revision: 3
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: 2b9fd7ec122fff2601296ae3a46bb7607b2b32ef
ms.contentlocale: zh-cn
ms.lasthandoff: 04/12/2017

---
# <a name="set-operations-visual-basic"></a><span data-ttu-id="3a25f-102">Set 运算 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="3a25f-102">Set Operations (Visual Basic)</span></span>
<span data-ttu-id="3a25f-103">LINQ 中的集运算是指生成基于存在相同或不同集合 （或集） 中的等效元素的结果集的查询操作。</span><span class="sxs-lookup"><span data-stu-id="3a25f-103">Set operations in LINQ refer to query operations that produce a result set that is based on the presence or absence of equivalent elements within the same or separate collections (or sets).</span></span>  
  
 <span data-ttu-id="3a25f-104">下一节中列出了执行集合操作的标准查询运算符方法。</span><span class="sxs-lookup"><span data-stu-id="3a25f-104">The standard query operator methods that perform set operations are listed in the following section.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="3a25f-105">方法</span><span class="sxs-lookup"><span data-stu-id="3a25f-105">Methods</span></span>  
  
|<span data-ttu-id="3a25f-106">方法名</span><span class="sxs-lookup"><span data-stu-id="3a25f-106">Method Name</span></span>|<span data-ttu-id="3a25f-107">描述</span><span class="sxs-lookup"><span data-stu-id="3a25f-107">Description</span></span>|<span data-ttu-id="3a25f-108">Visual Basic 查询表达式语法</span><span class="sxs-lookup"><span data-stu-id="3a25f-108">Visual Basic Query Expression Syntax</span></span>|<span data-ttu-id="3a25f-109">更多信息</span><span class="sxs-lookup"><span data-stu-id="3a25f-109">More Information</span></span>|  
|-----------------|-----------------|------------------------------------------|----------------------|  
|<span data-ttu-id="3a25f-110">Distinct</span><span class="sxs-lookup"><span data-stu-id="3a25f-110">Distinct</span></span>|<span data-ttu-id="3a25f-111">中删除重复的集合中的值。</span><span class="sxs-lookup"><span data-stu-id="3a25f-111">Removes duplicate values from a collection.</span></span>|`Distinct`|<span data-ttu-id="3a25f-112"><xref:System.Linq.Enumerable.Distinct%2A?displayProperty=fullName></xref:System.Linq.Enumerable.Distinct%2A?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="3a25f-112"><xref:System.Linq.Enumerable.Distinct%2A?displayProperty=fullName></span></span><br /><br /> <span data-ttu-id="3a25f-113"><xref:System.Linq.Queryable.Distinct%2A?displayProperty=fullName></xref:System.Linq.Queryable.Distinct%2A?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="3a25f-113"><xref:System.Linq.Queryable.Distinct%2A?displayProperty=fullName></span></span>|  
|<span data-ttu-id="3a25f-114">不包括</span><span class="sxs-lookup"><span data-stu-id="3a25f-114">Except</span></span>|<span data-ttu-id="3a25f-115">返回的差集，这意味着第二个集合中不会出现一个集合中的元素。</span><span class="sxs-lookup"><span data-stu-id="3a25f-115">Returns the set difference, which means the elements of one collection that do not appear in a second collection.</span></span>|<span data-ttu-id="3a25f-116">不适用。</span><span class="sxs-lookup"><span data-stu-id="3a25f-116">Not applicable.</span></span>|<span data-ttu-id="3a25f-117"><xref:System.Linq.Enumerable.Except%2A?displayProperty=fullName></xref:System.Linq.Enumerable.Except%2A?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="3a25f-117"><xref:System.Linq.Enumerable.Except%2A?displayProperty=fullName></span></span><br /><br /> <span data-ttu-id="3a25f-118"><xref:System.Linq.Queryable.Except%2A?displayProperty=fullName></xref:System.Linq.Queryable.Except%2A?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="3a25f-118"><xref:System.Linq.Queryable.Except%2A?displayProperty=fullName></span></span>|  
|<span data-ttu-id="3a25f-119">相交</span><span class="sxs-lookup"><span data-stu-id="3a25f-119">Intersect</span></span>|<span data-ttu-id="3a25f-120">返回组重叠，这意味着每两个集合中显示的元素。</span><span class="sxs-lookup"><span data-stu-id="3a25f-120">Returns the set intersection, which means elements that appear in each of two collections.</span></span>|<span data-ttu-id="3a25f-121">不适用。</span><span class="sxs-lookup"><span data-stu-id="3a25f-121">Not applicable.</span></span>|<span data-ttu-id="3a25f-122"><xref:System.Linq.Enumerable.Intersect%2A?displayProperty=fullName></xref:System.Linq.Enumerable.Intersect%2A?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="3a25f-122"><xref:System.Linq.Enumerable.Intersect%2A?displayProperty=fullName></span></span><br /><br /> <span data-ttu-id="3a25f-123"><xref:System.Linq.Queryable.Intersect%2A?displayProperty=fullName></xref:System.Linq.Queryable.Intersect%2A?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="3a25f-123"><xref:System.Linq.Queryable.Intersect%2A?displayProperty=fullName></span></span>|  
|<span data-ttu-id="3a25f-124">联合</span><span class="sxs-lookup"><span data-stu-id="3a25f-124">Union</span></span>|<span data-ttu-id="3a25f-125">返回并集，这意味着显示在上述两个集合的唯一元素。</span><span class="sxs-lookup"><span data-stu-id="3a25f-125">Returns the set union, which means unique elements that appear in either of two collections.</span></span>|<span data-ttu-id="3a25f-126">不适用。</span><span class="sxs-lookup"><span data-stu-id="3a25f-126">Not applicable.</span></span>|<span data-ttu-id="3a25f-127"><xref:System.Linq.Enumerable.Union%2A?displayProperty=fullName></xref:System.Linq.Enumerable.Union%2A?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="3a25f-127"><xref:System.Linq.Enumerable.Union%2A?displayProperty=fullName></span></span><br /><br /> <span data-ttu-id="3a25f-128"><xref:System.Linq.Queryable.Union%2A?displayProperty=fullName></xref:System.Linq.Queryable.Union%2A?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="3a25f-128"><xref:System.Linq.Queryable.Union%2A?displayProperty=fullName></span></span>|  
  
## <a name="comparison-of-set-operations"></a><span data-ttu-id="3a25f-129">集运算的比较</span><span class="sxs-lookup"><span data-stu-id="3a25f-129">Comparison of Set Operations</span></span>  
  
### <a name="distinct"></a><span data-ttu-id="3a25f-130">Distinct</span><span class="sxs-lookup"><span data-stu-id="3a25f-130">Distinct</span></span>  
 <span data-ttu-id="3a25f-131">下图描绘了的行为<xref:System.Linq.Enumerable.Distinct%2A?displayProperty=fullName>方法上的字符序列。</xref:System.Linq.Enumerable.Distinct%2A?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="3a25f-131">The following illustration depicts the behavior of the <xref:System.Linq.Enumerable.Distinct%2A?displayProperty=fullName> method on a sequence of characters.</span></span> <span data-ttu-id="3a25f-132">返回的序列包含输入序列中的唯一元素。</span><span class="sxs-lookup"><span data-stu-id="3a25f-132">The returned sequence contains the unique elements from the input sequence.</span></span>  
  
 <span data-ttu-id="3a25f-133">![显示 distinct （） 的行为的图。](../../../../csharp/programming-guide/concepts/linq/media/distinct.png "不同")</span><span class="sxs-lookup"><span data-stu-id="3a25f-133">![Graphic showing the behavior of Distinct&#40;&#41;.](../../../../csharp/programming-guide/concepts/linq/media/distinct.png "Distinct")</span></span>  
  
### <a name="except"></a><span data-ttu-id="3a25f-134">不包括</span><span class="sxs-lookup"><span data-stu-id="3a25f-134">Except</span></span>  
 <span data-ttu-id="3a25f-135">下图描绘了<xref:System.Linq.Enumerable.Except%2A?displayProperty=fullName>。</xref:System.Linq.Enumerable.Except%2A?displayProperty=fullName>的行为</span><span class="sxs-lookup"><span data-stu-id="3a25f-135">The following illustration depicts the behavior of <xref:System.Linq.Enumerable.Except%2A?displayProperty=fullName>.</span></span> <span data-ttu-id="3a25f-136">返回的序列仅包含元素的第一个输入序列中不在第二个输入序列中。</span><span class="sxs-lookup"><span data-stu-id="3a25f-136">The returned sequence contains only the elements from the first input sequence that are not in the second input sequence.</span></span>  
  
 <span data-ttu-id="3a25f-137">![图形显示操作的图。](../../../../csharp/programming-guide/concepts/linq/media/except.png "Except")</span><span class="sxs-lookup"><span data-stu-id="3a25f-137">![Graphic showing the action of Except&#40;&#41;.](../../../../csharp/programming-guide/concepts/linq/media/except.png "Except")</span></span>  
  
### <a name="intersect"></a><span data-ttu-id="3a25f-138">相交</span><span class="sxs-lookup"><span data-stu-id="3a25f-138">Intersect</span></span>  
 <span data-ttu-id="3a25f-139">下图描绘了<xref:System.Linq.Enumerable.Intersect%2A?displayProperty=fullName>。</xref:System.Linq.Enumerable.Intersect%2A?displayProperty=fullName>的行为</span><span class="sxs-lookup"><span data-stu-id="3a25f-139">The following illustration depicts the behavior of <xref:System.Linq.Enumerable.Intersect%2A?displayProperty=fullName>.</span></span> <span data-ttu-id="3a25f-140">返回的序列包含的元素所共有的这两个输入序列。</span><span class="sxs-lookup"><span data-stu-id="3a25f-140">The returned sequence contains the elements that are common to both of the input sequences.</span></span>  
  
 <span data-ttu-id="3a25f-141">![显示两个序列的交集的图。](../../../../csharp/programming-guide/concepts/linq/media/intersect.png "相交")</span><span class="sxs-lookup"><span data-stu-id="3a25f-141">![Graphic showing the intersection of two sequences.](../../../../csharp/programming-guide/concepts/linq/media/intersect.png "Intersect")</span></span>  
  
### <a name="union"></a><span data-ttu-id="3a25f-142">联合</span><span class="sxs-lookup"><span data-stu-id="3a25f-142">Union</span></span>  
 <span data-ttu-id="3a25f-143">下图描绘了 union 运算对两个序列的字符。</span><span class="sxs-lookup"><span data-stu-id="3a25f-143">The following illustration depicts a union operation on two sequences of characters.</span></span> <span data-ttu-id="3a25f-144">返回的序列中不包含这两个输入序列中的唯一元素。</span><span class="sxs-lookup"><span data-stu-id="3a25f-144">The returned sequence contains the unique elements from both input sequences.</span></span>  
  
 <span data-ttu-id="3a25f-145">![显示两个序列的联合的图。](../../../../csharp/programming-guide/concepts/linq/media/union.png "Union")</span><span class="sxs-lookup"><span data-stu-id="3a25f-145">![Graphic showing the union of two sequences.](../../../../csharp/programming-guide/concepts/linq/media/union.png "Union")</span></span>  
  
## <a name="query-expression-syntax-example"></a><span data-ttu-id="3a25f-146">查询表达式语法示例</span><span class="sxs-lookup"><span data-stu-id="3a25f-146">Query Expression Syntax Example</span></span>  
 <span data-ttu-id="3a25f-147">下面的示例使用`Distinct`LINQ 查询以返回唯一的编号从整数列表中的子句。</span><span class="sxs-lookup"><span data-stu-id="3a25f-147">The following example uses the `Distinct` clause in a LINQ query to return the unique numbers from a list of integers.</span></span>  
  
 <span data-ttu-id="3a25f-148">[!code-vb[CsLINQSetOps #&1;](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/set-operations_1.vb)]</span><span class="sxs-lookup"><span data-stu-id="3a25f-148">[!code-vb[CsLINQSetOps#1](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/set-operations_1.vb)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3a25f-149">另请参阅</span><span class="sxs-lookup"><span data-stu-id="3a25f-149">See Also</span></span>  
 <span data-ttu-id="3a25f-150"><xref:System.Linq></xref:System.Linq></span><span class="sxs-lookup"><span data-stu-id="3a25f-150"><xref:System.Linq></span></span>   
<span data-ttu-id="3a25f-151"> [标准查询运算符概述 (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/standard-query-operators-overview.md) </span><span class="sxs-lookup"><span data-stu-id="3a25f-151"> [Standard Query Operators Overview (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/standard-query-operators-overview.md) </span></span>  
<span data-ttu-id="3a25f-152"> [Distinct 子句](../../../../visual-basic/language-reference/queries/distinct-clause.md) </span><span class="sxs-lookup"><span data-stu-id="3a25f-152"> [Distinct Clause](../../../../visual-basic/language-reference/queries/distinct-clause.md) </span></span>  
<span data-ttu-id="3a25f-153"> [如何︰ 组合和比较字符串集合 (LINQ) (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/how-to-combine-and-compare-string-collections-linq.md) </span><span class="sxs-lookup"><span data-stu-id="3a25f-153"> [How to: Combine and Compare String Collections (LINQ) (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/how-to-combine-and-compare-string-collections-linq.md) </span></span>  
<span data-ttu-id="3a25f-154"> [如何︰ 查找两个列表 (LINQ) (Visual Basic 中) 之间的差集](../../../../visual-basic/programming-guide/concepts/linq/how-to-find-the-set-difference-between-two-lists-linq.md)</span><span class="sxs-lookup"><span data-stu-id="3a25f-154"> [How to: Find the Set Difference Between Two Lists (LINQ) (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/how-to-find-the-set-difference-between-two-lists-linq.md)</span></span>
