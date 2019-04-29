---
title: 查询示例
ms.date: 03/30/2017
ms.assetid: 137f8677-494c-4d49-95ce-c17742f2d01f
ms.openlocfilehash: 74664dd98ac067153894edc934c8f15eec407261
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "61783105"
---
# <a name="query-examples"></a><span data-ttu-id="cec5c-102">查询示例</span><span class="sxs-lookup"><span data-stu-id="cec5c-102">Query Examples</span></span>
<span data-ttu-id="cec5c-103">本部分提供了典型的 Visual Basic 和 C# 示例[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]查询。</span><span class="sxs-lookup"><span data-stu-id="cec5c-103">This section provides Visual Basic and C# examples of typical [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] queries.</span></span> <span data-ttu-id="cec5c-104">在示例部分中，使用 Visual Studio 的开发人员可以提供的示例解决方案中找到更多示例。</span><span class="sxs-lookup"><span data-stu-id="cec5c-104">Developers using Visual Studio can find many more examples in a sample solution available in the Samples section.</span></span> <span data-ttu-id="cec5c-105">有关详细信息，请参阅[示例](../../../../../../docs/framework/data/adonet/sql/linq/samples.md)。</span><span class="sxs-lookup"><span data-stu-id="cec5c-105">For more information, see [Samples](../../../../../../docs/framework/data/adonet/sql/linq/samples.md).</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="cec5c-106">*db*中的代码示例中通常使用[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]文档。</span><span class="sxs-lookup"><span data-stu-id="cec5c-106">*db* is often used in code examples in [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] documentation.</span></span> <span data-ttu-id="cec5c-107">*db*被假定为的实例*Northwind*类，该类继承自<xref:System.Data.Linq.DataContext>。</span><span class="sxs-lookup"><span data-stu-id="cec5c-107">*db* is assumed to be an instance of a *Northwind* class, which inherits from <xref:System.Data.Linq.DataContext>.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="cec5c-108">本节内容</span><span class="sxs-lookup"><span data-stu-id="cec5c-108">In This Section</span></span>  
 [<span data-ttu-id="cec5c-109">聚合查询</span><span class="sxs-lookup"><span data-stu-id="cec5c-109">Aggregate Queries</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/aggregate-queries.md)  
 <span data-ttu-id="cec5c-110">介绍如何使用 <xref:System.Linq.Enumerable.Average%2A>、<xref:System.Linq.Enumerable.Count%2A> 等。</span><span class="sxs-lookup"><span data-stu-id="cec5c-110">Describes how to use <xref:System.Linq.Enumerable.Average%2A>, <xref:System.Linq.Enumerable.Count%2A>, and so forth.</span></span>  
  
 [<span data-ttu-id="cec5c-111">返回序列中的第一个元素</span><span class="sxs-lookup"><span data-stu-id="cec5c-111">Return the First Element in a Sequence</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/return-the-first-element-in-a-sequence.md)  
 <span data-ttu-id="cec5c-112">提供使用 <xref:System.Linq.Enumerable.First%2A> 的示例。</span><span class="sxs-lookup"><span data-stu-id="cec5c-112">Provides examples of using <xref:System.Linq.Enumerable.First%2A>.</span></span>  
  
 [<span data-ttu-id="cec5c-113">返回或跳过序列中的元素</span><span class="sxs-lookup"><span data-stu-id="cec5c-113">Return Or Skip Elements in a Sequence</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/return-or-skip-elements-in-a-sequence.md)  
 <span data-ttu-id="cec5c-114">提供使用 <xref:System.Linq.Enumerable.Take%2A> 和 <xref:System.Linq.Enumerable.Skip%2A> 的示例。</span><span class="sxs-lookup"><span data-stu-id="cec5c-114">Provides examples of using <xref:System.Linq.Enumerable.Take%2A> and <xref:System.Linq.Enumerable.Skip%2A>.</span></span>  
  
 [<span data-ttu-id="cec5c-115">在序列中对元素进行排序</span><span class="sxs-lookup"><span data-stu-id="cec5c-115">Sort Elements in a Sequence</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/sort-elements-in-a-sequence.md)  
 <span data-ttu-id="cec5c-116">提供使用 <xref:System.Linq.Enumerable.OrderBy%2A> 的示例。</span><span class="sxs-lookup"><span data-stu-id="cec5c-116">Provides examples of using <xref:System.Linq.Enumerable.OrderBy%2A>.</span></span>  
  
 [<span data-ttu-id="cec5c-117">对序列中的元素进行分组</span><span class="sxs-lookup"><span data-stu-id="cec5c-117">Group Elements in a Sequence</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/group-elements-in-a-sequence.md)  
 <span data-ttu-id="cec5c-118">提供使用 <xref:System.Linq.Enumerable.GroupBy%2A> 的示例。</span><span class="sxs-lookup"><span data-stu-id="cec5c-118">Provides examples of using <xref:System.Linq.Enumerable.GroupBy%2A>.</span></span>  
  
 [<span data-ttu-id="cec5c-119">从序列中消除重复的元素</span><span class="sxs-lookup"><span data-stu-id="cec5c-119">Eliminate Duplicate Elements from a Sequence</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/eliminate-duplicate-elements-from-a-sequence.md)  
 <span data-ttu-id="cec5c-120">提供使用 <xref:System.Linq.Enumerable.Distinct%2A> 的示例。</span><span class="sxs-lookup"><span data-stu-id="cec5c-120">Provides examples of using <xref:System.Linq.Enumerable.Distinct%2A>.</span></span>  
  
 [<span data-ttu-id="cec5c-121">确定序列中任何或所有元素是否满足某一条件</span><span class="sxs-lookup"><span data-stu-id="cec5c-121">Determine if Any or All Elements in a Sequence Satisfy a Condition</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/determine-if-any-or-all-elements-in-a-sequence-satisfy-a-condition.md)  
 <span data-ttu-id="cec5c-122">提供使用 <xref:System.Linq.Enumerable.All%2A> 和 <xref:System.Linq.Enumerable.Any%2A> 的示例。</span><span class="sxs-lookup"><span data-stu-id="cec5c-122">Provides examples of using <xref:System.Linq.Enumerable.All%2A> and <xref:System.Linq.Enumerable.Any%2A>.</span></span>  
  
 [<span data-ttu-id="cec5c-123">连接两个序列</span><span class="sxs-lookup"><span data-stu-id="cec5c-123">Concatenate Two Sequences</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/concatenate-two-sequences.md)  
 <span data-ttu-id="cec5c-124">提供使用 <xref:System.Linq.Enumerable.Concat%2A> 的示例。</span><span class="sxs-lookup"><span data-stu-id="cec5c-124">Provides examples of using <xref:System.Linq.Enumerable.Concat%2A>.</span></span>  
  
 [<span data-ttu-id="cec5c-125">返回两个序列之间的差集</span><span class="sxs-lookup"><span data-stu-id="cec5c-125">Return the Set Difference Between Two Sequences</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/return-the-set-difference-between-two-sequences.md)  
 <span data-ttu-id="cec5c-126">提供使用 <xref:System.Linq.Enumerable.Except%2A> 的示例。</span><span class="sxs-lookup"><span data-stu-id="cec5c-126">Provides examples of using <xref:System.Linq.Enumerable.Except%2A>.</span></span>  
  
 [<span data-ttu-id="cec5c-127">返回两个序列的交集</span><span class="sxs-lookup"><span data-stu-id="cec5c-127">Return the Set Intersection of Two Sequences</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/return-the-set-intersection-of-two-sequences.md)  
 <span data-ttu-id="cec5c-128">提供使用 <xref:System.Linq.Enumerable.Intersect%2A> 的示例。</span><span class="sxs-lookup"><span data-stu-id="cec5c-128">Provides examples of using <xref:System.Linq.Enumerable.Intersect%2A>.</span></span>  
  
 [<span data-ttu-id="cec5c-129">返回两个序列的并集</span><span class="sxs-lookup"><span data-stu-id="cec5c-129">Return the Set Union of Two Sequences</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/return-the-set-union-of-two-sequences.md)  
 <span data-ttu-id="cec5c-130">提供使用 <xref:System.Linq.Enumerable.Union%2A> 的示例。</span><span class="sxs-lookup"><span data-stu-id="cec5c-130">Provides examples of using <xref:System.Linq.Enumerable.Union%2A>.</span></span>  
  
 [<span data-ttu-id="cec5c-131">将序列转换为数组</span><span class="sxs-lookup"><span data-stu-id="cec5c-131">Convert a Sequence to an Array</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/convert-a-sequence-to-an-array.md)  
 <span data-ttu-id="cec5c-132">提供使用 <xref:System.Linq.Enumerable.ToArray%2A> 的示例。</span><span class="sxs-lookup"><span data-stu-id="cec5c-132">Provides examples of using <xref:System.Linq.Enumerable.ToArray%2A>.</span></span>  
  
 [<span data-ttu-id="cec5c-133">将某一序列转换为泛型列表</span><span class="sxs-lookup"><span data-stu-id="cec5c-133">Convert a Sequence to a Generic List</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/convert-a-sequence-to-a-generic-list.md)  
 <span data-ttu-id="cec5c-134">提供使用 <xref:System.Linq.Enumerable.ToList%2A> 的示例。</span><span class="sxs-lookup"><span data-stu-id="cec5c-134">Provides examples of using <xref:System.Linq.Enumerable.ToList%2A>.</span></span>  
  
 [<span data-ttu-id="cec5c-135">将某一类型转换为泛型 IEnumerable</span><span class="sxs-lookup"><span data-stu-id="cec5c-135">Convert a Type to a Generic IEnumerable</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/convert-a-type-to-a-generic-ienumerable.md)  
 <span data-ttu-id="cec5c-136">提供使用 <xref:System.Linq.Enumerable.AsEnumerable%2A> 的示例。</span><span class="sxs-lookup"><span data-stu-id="cec5c-136">Provides examples of using <xref:System.Linq.Enumerable.AsEnumerable%2A>.</span></span>  
  
 [<span data-ttu-id="cec5c-137">构建联接和叉积查询</span><span class="sxs-lookup"><span data-stu-id="cec5c-137">Formulate Joins and Cross-Product Queries</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/formulate-joins-and-cross-product-queries.md)  
 <span data-ttu-id="cec5c-138">提供在 `from`、`where` 和 `select` 子句中使用外键导航的示例。</span><span class="sxs-lookup"><span data-stu-id="cec5c-138">Provides examples of using foreign-key navigation in the `from`, `where`, and `select` clauses.</span></span>  
  
 [<span data-ttu-id="cec5c-139">构建投影</span><span class="sxs-lookup"><span data-stu-id="cec5c-139">Formulate Projections</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/formulate-projections.md)  
 <span data-ttu-id="cec5c-140">提供了示例的组合`select`与其他功能 (例如，*匿名类型*) 构建查询投影。</span><span class="sxs-lookup"><span data-stu-id="cec5c-140">Provides examples of combining `select` with other features (for example, *anonymous types*) to form query projections.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="cec5c-141">相关章节</span><span class="sxs-lookup"><span data-stu-id="cec5c-141">Related Sections</span></span>  
 [<span data-ttu-id="cec5c-142">标准查询运算符概述 (C#)</span><span class="sxs-lookup"><span data-stu-id="cec5c-142">Standard Query Operators Overview (C#)</span></span>](../../../../../csharp/programming-guide/concepts/linq/standard-query-operators-overview.md)  
 <span data-ttu-id="cec5c-143">介绍了使用标准查询运算符的概念， C#。</span><span class="sxs-lookup"><span data-stu-id="cec5c-143">Explains the concept of standard query operators using C#.</span></span>  
  
 [<span data-ttu-id="cec5c-144">标准查询运算符概述 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="cec5c-144">Standard Query Operators Overview (Visual Basic)</span></span>](../../../../../visual-basic/programming-guide/concepts/linq/standard-query-operators-overview.md)  
 <span data-ttu-id="cec5c-145">介绍了使用 Visual Basic 的标准查询运算符的概念。</span><span class="sxs-lookup"><span data-stu-id="cec5c-145">Explains the concept of standard query operators using Visual Basic.</span></span>  
  
 [<span data-ttu-id="cec5c-146">查询概念</span><span class="sxs-lookup"><span data-stu-id="cec5c-146">Query Concepts</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/query-concepts.md)  
 <span data-ttu-id="cec5c-147">解释 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] 如何使用适用于查询的概念。</span><span class="sxs-lookup"><span data-stu-id="cec5c-147">Explains how [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] uses concepts that apply to queries.</span></span>  
  
 [<span data-ttu-id="cec5c-148">编程指南</span><span class="sxs-lookup"><span data-stu-id="cec5c-148">Programming Guide</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/programming-guide.md)  
 <span data-ttu-id="cec5c-149">提供用于访问一些主题的门户，这些主题解释了与 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] 相关的编程概念。</span><span class="sxs-lookup"><span data-stu-id="cec5c-149">Provides a portal to topics that explain programming concepts related to [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)].</span></span>
