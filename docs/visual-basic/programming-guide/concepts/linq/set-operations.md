---
title: 设置操作 (Visual Basic)
ms.date: 07/20/2015
ms.assetid: 2b06e822-e030-438f-9db7-ee402bd3a706
ms.openlocfilehash: 7b8dcaaa82ac5a30c35222417245153e55a522cc
ms.sourcegitcommit: 3630c2515809e6f4b7dbb697a3354efec105a5cd
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/25/2019
ms.locfileid: "58409245"
---
# <a name="set-operations-visual-basic"></a><span data-ttu-id="721c3-102">设置操作 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="721c3-102">Set Operations (Visual Basic)</span></span>
<span data-ttu-id="721c3-103">LINQ 中的集运算是指根据相同或不同集合（或集）中是否存在等效元素来生成结果集的查询运算。</span><span class="sxs-lookup"><span data-stu-id="721c3-103">Set operations in LINQ refer to query operations that produce a result set that is based on the presence or absence of equivalent elements within the same or separate collections (or sets).</span></span>  
  
 <span data-ttu-id="721c3-104">下节列出了执行集运算的标准查询运算符方法。</span><span class="sxs-lookup"><span data-stu-id="721c3-104">The standard query operator methods that perform set operations are listed in the following section.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="721c3-105">方法</span><span class="sxs-lookup"><span data-stu-id="721c3-105">Methods</span></span>  
  
|<span data-ttu-id="721c3-106">方法名</span><span class="sxs-lookup"><span data-stu-id="721c3-106">Method Name</span></span>|<span data-ttu-id="721c3-107">描述</span><span class="sxs-lookup"><span data-stu-id="721c3-107">Description</span></span>|<span data-ttu-id="721c3-108">Visual Basic 查询表达式语法</span><span class="sxs-lookup"><span data-stu-id="721c3-108">Visual Basic Query Expression Syntax</span></span>|<span data-ttu-id="721c3-109">详细信息</span><span class="sxs-lookup"><span data-stu-id="721c3-109">More Information</span></span>|  
|-----------------|-----------------|------------------------------------------|----------------------|  
|<span data-ttu-id="721c3-110">Distinct</span><span class="sxs-lookup"><span data-stu-id="721c3-110">Distinct</span></span>|<span data-ttu-id="721c3-111">删除集合中的重复值。</span><span class="sxs-lookup"><span data-stu-id="721c3-111">Removes duplicate values from a collection.</span></span>|`Distinct`|<xref:System.Linq.Enumerable.Distinct%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.Distinct%2A?displayProperty=nameWithType>|  
|<span data-ttu-id="721c3-112">Except</span><span class="sxs-lookup"><span data-stu-id="721c3-112">Except</span></span>|<span data-ttu-id="721c3-113">返回差集，差集指位于一个集合但不位于另一个集合的元素。</span><span class="sxs-lookup"><span data-stu-id="721c3-113">Returns the set difference, which means the elements of one collection that do not appear in a second collection.</span></span>|<span data-ttu-id="721c3-114">不适用。</span><span class="sxs-lookup"><span data-stu-id="721c3-114">Not applicable.</span></span>|<xref:System.Linq.Enumerable.Except%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.Except%2A?displayProperty=nameWithType>|  
|<span data-ttu-id="721c3-115">相交</span><span class="sxs-lookup"><span data-stu-id="721c3-115">Intersect</span></span>|<span data-ttu-id="721c3-116">返回交集，交集指同时出现在两个集合中的元素。</span><span class="sxs-lookup"><span data-stu-id="721c3-116">Returns the set intersection, which means elements that appear in each of two collections.</span></span>|<span data-ttu-id="721c3-117">不适用。</span><span class="sxs-lookup"><span data-stu-id="721c3-117">Not applicable.</span></span>|<xref:System.Linq.Enumerable.Intersect%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.Intersect%2A?displayProperty=nameWithType>|  
|<span data-ttu-id="721c3-118">联合</span><span class="sxs-lookup"><span data-stu-id="721c3-118">Union</span></span>|<span data-ttu-id="721c3-119">返回并集，并集指位于两个集合中任一集合的唯一的元素。</span><span class="sxs-lookup"><span data-stu-id="721c3-119">Returns the set union, which means unique elements that appear in either of two collections.</span></span>|<span data-ttu-id="721c3-120">不适用。</span><span class="sxs-lookup"><span data-stu-id="721c3-120">Not applicable.</span></span>|<xref:System.Linq.Enumerable.Union%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.Union%2A?displayProperty=nameWithType>|  
  
## <a name="comparison-of-set-operations"></a><span data-ttu-id="721c3-121">比较集运算</span><span class="sxs-lookup"><span data-stu-id="721c3-121">Comparison of Set Operations</span></span>  
  
### <a name="distinct"></a><span data-ttu-id="721c3-122">Distinct</span><span class="sxs-lookup"><span data-stu-id="721c3-122">Distinct</span></span>  
 <span data-ttu-id="721c3-123">下图演示字符序列上 <xref:System.Linq.Enumerable.Distinct%2A?displayProperty=nameWithType> 方法的行为。</span><span class="sxs-lookup"><span data-stu-id="721c3-123">The following illustration depicts the behavior of the <xref:System.Linq.Enumerable.Distinct%2A?displayProperty=nameWithType> method on a sequence of characters.</span></span> <span data-ttu-id="721c3-124">返回的序列包含输入序列的唯一元素。</span><span class="sxs-lookup"><span data-stu-id="721c3-124">The returned sequence contains the unique elements from the input sequence.</span></span>  
  
 ![图示： Distinct 的行为&#40;&#41;。](./media/set-operations/distinct-method-behavior.png)  
  
### <a name="except"></a><span data-ttu-id="721c3-126">Except</span><span class="sxs-lookup"><span data-stu-id="721c3-126">Except</span></span>  
 <span data-ttu-id="721c3-127">下图演示 <xref:System.Linq.Enumerable.Except%2A?displayProperty=nameWithType> 的行为。</span><span class="sxs-lookup"><span data-stu-id="721c3-127">The following illustration depicts the behavior of <xref:System.Linq.Enumerable.Except%2A?displayProperty=nameWithType>.</span></span> <span data-ttu-id="721c3-128">返回的序列只包含位于第一个输入序列但不位于第二个输入序列的元素。</span><span class="sxs-lookup"><span data-stu-id="721c3-128">The returned sequence contains only the elements from the first input sequence that are not in the second input sequence.</span></span>  
  
 <span data-ttu-id="721c3-129">![显示 Except&#40;&#41; 操作的图形](./media/set-operations/except-behavior-graphic.png "显示 Except 的行为。")</span><span class="sxs-lookup"><span data-stu-id="721c3-129">![Graphic showing the action of Except&#40;&#41;.](./media/set-operations/except-behavior-graphic.png "Shows the behavior of Except.")</span></span>  
  
### <a name="intersect"></a><span data-ttu-id="721c3-130">相交</span><span class="sxs-lookup"><span data-stu-id="721c3-130">Intersect</span></span>  
 <span data-ttu-id="721c3-131">下图演示 <xref:System.Linq.Enumerable.Intersect%2A?displayProperty=nameWithType> 的行为。</span><span class="sxs-lookup"><span data-stu-id="721c3-131">The following illustration depicts the behavior of <xref:System.Linq.Enumerable.Intersect%2A?displayProperty=nameWithType>.</span></span> <span data-ttu-id="721c3-132">返回的序列包含两个输入序列共有的元素。</span><span class="sxs-lookup"><span data-stu-id="721c3-132">The returned sequence contains the elements that are common to both of the input sequences.</span></span>  
  
 ![显示两个序列的交集的图。](./media/set-operations/intersection-two-sequences.png)    
### <a name="union"></a><span data-ttu-id="721c3-134">联合</span><span class="sxs-lookup"><span data-stu-id="721c3-134">Union</span></span>  
 <span data-ttu-id="721c3-135">下图演示对两个字符序列执行的联合操作。</span><span class="sxs-lookup"><span data-stu-id="721c3-135">The following illustration depicts a union operation on two sequences of characters.</span></span> <span data-ttu-id="721c3-136">返回的序列包含两个输入序列的唯一元素。</span><span class="sxs-lookup"><span data-stu-id="721c3-136">The returned sequence contains the unique elements from both input sequences.</span></span>  
  
 ![显示两个序列的联合的图。](./media/set-operations/union-operation-two-sequences.png)    
## <a name="query-expression-syntax-example"></a><span data-ttu-id="721c3-138">查询表达式语法示例</span><span class="sxs-lookup"><span data-stu-id="721c3-138">Query Expression Syntax Example</span></span>  
 <span data-ttu-id="721c3-139">下面的示例使用`Distinct`LINQ 查询从整数列表返回的唯一数字中的子句。</span><span class="sxs-lookup"><span data-stu-id="721c3-139">The following example uses the `Distinct` clause in a LINQ query to return the unique numbers from a list of integers.</span></span>  
  
 [!code-vb[CsLINQSetOps#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/CsLINQSetOps/VB/setops.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="721c3-140">请参阅</span><span class="sxs-lookup"><span data-stu-id="721c3-140">See also</span></span>
- <xref:System.Linq>
- [<span data-ttu-id="721c3-141">标准查询运算符概述 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="721c3-141">Standard Query Operators Overview (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/standard-query-operators-overview.md)
- [<span data-ttu-id="721c3-142">Distinct 子句</span><span class="sxs-lookup"><span data-stu-id="721c3-142">Distinct Clause</span></span>](../../../../visual-basic/language-reference/queries/distinct-clause.md)
- [<span data-ttu-id="721c3-143">如何：合并和比较字符串集合 (LINQ) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="721c3-143">How to: Combine and Compare String Collections (LINQ) (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/how-to-combine-and-compare-string-collections-linq.md)
- [<span data-ttu-id="721c3-144">如何：查找两个列表 (LINQ) (Visual Basic 中) 之间的差集</span><span class="sxs-lookup"><span data-stu-id="721c3-144">How to: Find the Set Difference Between Two Lists (LINQ) (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/how-to-find-the-set-difference-between-two-lists-linq.md)
