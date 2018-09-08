---
title: 查询示例
ms.date: 03/30/2017
ms.assetid: 137f8677-494c-4d49-95ce-c17742f2d01f
ms.openlocfilehash: 38454890e05b00cd92bca909ce0c7975f5ef1f6e
ms.sourcegitcommit: c7f3e2e9d6ead6cc3acd0d66b10a251d0c66e59d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/08/2018
ms.locfileid: "44211861"
---
# <a name="query-examples"></a><span data-ttu-id="46b72-102">查询示例</span><span class="sxs-lookup"><span data-stu-id="46b72-102">Query Examples</span></span>
<span data-ttu-id="46b72-103">本部分提供了典型的 Visual Basic 和 C# 示例[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]查询。</span><span class="sxs-lookup"><span data-stu-id="46b72-103">This section provides Visual Basic and C# examples of typical [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] queries.</span></span> <span data-ttu-id="46b72-104">在示例部分中，使用 Visual Studio 的开发人员可以提供的示例解决方案中找到更多示例。</span><span class="sxs-lookup"><span data-stu-id="46b72-104">Developers using Visual Studio can find many more examples in a sample solution available in the Samples section.</span></span> <span data-ttu-id="46b72-105">有关详细信息，请参阅[示例](../../../../../../docs/framework/data/adonet/sql/linq/samples.md)。</span><span class="sxs-lookup"><span data-stu-id="46b72-105">For more information, see [Samples](../../../../../../docs/framework/data/adonet/sql/linq/samples.md).</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="46b72-106">*db*中的代码示例中通常使用[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]文档。</span><span class="sxs-lookup"><span data-stu-id="46b72-106">*db* is often used in code examples in [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] documentation.</span></span> <span data-ttu-id="46b72-107">*db*被假定为的实例*Northwind*类，该类继承自<xref:System.Data.Linq.DataContext>。</span><span class="sxs-lookup"><span data-stu-id="46b72-107">*db* is assumed to be an instance of a *Northwind* class, which inherits from <xref:System.Data.Linq.DataContext>.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="46b72-108">本节内容</span><span class="sxs-lookup"><span data-stu-id="46b72-108">In This Section</span></span>  
 [<span data-ttu-id="46b72-109">聚合查询</span><span class="sxs-lookup"><span data-stu-id="46b72-109">Aggregate Queries</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/aggregate-queries.md)  
 <span data-ttu-id="46b72-110">介绍如何使用 <xref:System.Linq.Enumerable.Average%2A>、<xref:System.Linq.Enumerable.Count%2A> 等。</span><span class="sxs-lookup"><span data-stu-id="46b72-110">Describes how to use <xref:System.Linq.Enumerable.Average%2A>, <xref:System.Linq.Enumerable.Count%2A>, and so forth.</span></span>  
  
 [<span data-ttu-id="46b72-111">返回序列中的第一个元素</span><span class="sxs-lookup"><span data-stu-id="46b72-111">Return the First Element in a Sequence</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/return-the-first-element-in-a-sequence.md)  
 <span data-ttu-id="46b72-112">提供使用 <xref:System.Linq.Enumerable.First%2A> 的示例。</span><span class="sxs-lookup"><span data-stu-id="46b72-112">Provides examples of using <xref:System.Linq.Enumerable.First%2A>.</span></span>  
  
 [<span data-ttu-id="46b72-113">返回或跳过序列中的元素</span><span class="sxs-lookup"><span data-stu-id="46b72-113">Return Or Skip Elements in a Sequence</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/return-or-skip-elements-in-a-sequence.md)  
 <span data-ttu-id="46b72-114">提供使用 <xref:System.Linq.Enumerable.Take%2A> 和 <xref:System.Linq.Enumerable.Skip%2A> 的示例。</span><span class="sxs-lookup"><span data-stu-id="46b72-114">Provides examples of using <xref:System.Linq.Enumerable.Take%2A> and <xref:System.Linq.Enumerable.Skip%2A>.</span></span>  
  
 [<span data-ttu-id="46b72-115">在序列中对元素进行排序</span><span class="sxs-lookup"><span data-stu-id="46b72-115">Sort Elements in a Sequence</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/sort-elements-in-a-sequence.md)  
 <span data-ttu-id="46b72-116">提供使用 <xref:System.Linq.Enumerable.OrderBy%2A> 的示例。</span><span class="sxs-lookup"><span data-stu-id="46b72-116">Provides examples of using <xref:System.Linq.Enumerable.OrderBy%2A>.</span></span>  
  
 [<span data-ttu-id="46b72-117">对序列中的元素进行分组</span><span class="sxs-lookup"><span data-stu-id="46b72-117">Group Elements in a Sequence</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/group-elements-in-a-sequence.md)  
 <span data-ttu-id="46b72-118">提供使用 <xref:System.Linq.Enumerable.GroupBy%2A> 的示例。</span><span class="sxs-lookup"><span data-stu-id="46b72-118">Provides examples of using <xref:System.Linq.Enumerable.GroupBy%2A>.</span></span>  
  
 [<span data-ttu-id="46b72-119">从序列中消除重复的元素</span><span class="sxs-lookup"><span data-stu-id="46b72-119">Eliminate Duplicate Elements from a Sequence</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/eliminate-duplicate-elements-from-a-sequence.md)  
 <span data-ttu-id="46b72-120">提供使用 <xref:System.Linq.Enumerable.Distinct%2A> 的示例。</span><span class="sxs-lookup"><span data-stu-id="46b72-120">Provides examples of using <xref:System.Linq.Enumerable.Distinct%2A>.</span></span>  
  
 [<span data-ttu-id="46b72-121">确定序列中任何或所有元素是否满足某一条件</span><span class="sxs-lookup"><span data-stu-id="46b72-121">Determine if Any or All Elements in a Sequence Satisfy a Condition</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/determine-if-any-or-all-elements-in-a-sequence-satisfy-a-condition.md)  
 <span data-ttu-id="46b72-122">提供使用 <xref:System.Linq.Enumerable.All%2A> 和 <xref:System.Linq.Enumerable.Any%2A> 的示例。</span><span class="sxs-lookup"><span data-stu-id="46b72-122">Provides examples of using <xref:System.Linq.Enumerable.All%2A> and <xref:System.Linq.Enumerable.Any%2A>.</span></span>  
  
 [<span data-ttu-id="46b72-123">连接两个序列</span><span class="sxs-lookup"><span data-stu-id="46b72-123">Concatenate Two Sequences</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/concatenate-two-sequences.md)  
 <span data-ttu-id="46b72-124">提供使用 <xref:System.Linq.Enumerable.Concat%2A> 的示例。</span><span class="sxs-lookup"><span data-stu-id="46b72-124">Provides examples of using <xref:System.Linq.Enumerable.Concat%2A>.</span></span>  
  
 [<span data-ttu-id="46b72-125">返回两个序列之间的差集</span><span class="sxs-lookup"><span data-stu-id="46b72-125">Return the Set Difference Between Two Sequences</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/return-the-set-difference-between-two-sequences.md)  
 <span data-ttu-id="46b72-126">提供使用 <xref:System.Linq.Enumerable.Except%2A> 的示例。</span><span class="sxs-lookup"><span data-stu-id="46b72-126">Provides examples of using <xref:System.Linq.Enumerable.Except%2A>.</span></span>  
  
 [<span data-ttu-id="46b72-127">返回两个序列的交集</span><span class="sxs-lookup"><span data-stu-id="46b72-127">Return the Set Intersection of Two Sequences</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/return-the-set-intersection-of-two-sequences.md)  
 <span data-ttu-id="46b72-128">提供使用 <xref:System.Linq.Enumerable.Intersect%2A> 的示例。</span><span class="sxs-lookup"><span data-stu-id="46b72-128">Provides examples of using <xref:System.Linq.Enumerable.Intersect%2A>.</span></span>  
  
 [<span data-ttu-id="46b72-129">返回两个序列的并集</span><span class="sxs-lookup"><span data-stu-id="46b72-129">Return the Set Union of Two Sequences</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/return-the-set-union-of-two-sequences.md)  
 <span data-ttu-id="46b72-130">提供使用 <xref:System.Linq.Enumerable.Union%2A> 的示例。</span><span class="sxs-lookup"><span data-stu-id="46b72-130">Provides examples of using <xref:System.Linq.Enumerable.Union%2A>.</span></span>  
  
 [<span data-ttu-id="46b72-131">将序列转换为数组</span><span class="sxs-lookup"><span data-stu-id="46b72-131">Convert a Sequence to an Array</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/convert-a-sequence-to-an-array.md)  
 <span data-ttu-id="46b72-132">提供使用 <xref:System.Linq.Enumerable.ToArray%2A> 的示例。</span><span class="sxs-lookup"><span data-stu-id="46b72-132">Provides examples of using <xref:System.Linq.Enumerable.ToArray%2A>.</span></span>  
  
 [<span data-ttu-id="46b72-133">将某一序列转换为泛型列表</span><span class="sxs-lookup"><span data-stu-id="46b72-133">Convert a Sequence to a Generic List</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/convert-a-sequence-to-a-generic-list.md)  
 <span data-ttu-id="46b72-134">提供使用 <xref:System.Linq.Enumerable.ToList%2A> 的示例。</span><span class="sxs-lookup"><span data-stu-id="46b72-134">Provides examples of using <xref:System.Linq.Enumerable.ToList%2A>.</span></span>  
  
 [<span data-ttu-id="46b72-135">将某一类型转换为泛型 IEnumerable</span><span class="sxs-lookup"><span data-stu-id="46b72-135">Convert a Type to a Generic IEnumerable</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/convert-a-type-to-a-generic-ienumerable.md)  
 <span data-ttu-id="46b72-136">提供使用 <xref:System.Linq.Enumerable.AsEnumerable%2A> 的示例。</span><span class="sxs-lookup"><span data-stu-id="46b72-136">Provides examples of using <xref:System.Linq.Enumerable.AsEnumerable%2A>.</span></span>  
  
 [<span data-ttu-id="46b72-137">构建联接和叉积查询</span><span class="sxs-lookup"><span data-stu-id="46b72-137">Formulate Joins and Cross-Product Queries</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/formulate-joins-and-cross-product-queries.md)  
 <span data-ttu-id="46b72-138">提供在 `from`、`where` 和 `select` 子句中使用外键导航的示例。</span><span class="sxs-lookup"><span data-stu-id="46b72-138">Provides examples of using foreign-key navigation in the `from`, `where`, and `select` clauses.</span></span>  
  
 [<span data-ttu-id="46b72-139">构建投影</span><span class="sxs-lookup"><span data-stu-id="46b72-139">Formulate Projections</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/formulate-projections.md)  
 <span data-ttu-id="46b72-140">提供了示例的组合`select`与其他功能 (例如，*匿名类型*) 构建查询投影。</span><span class="sxs-lookup"><span data-stu-id="46b72-140">Provides examples of combining `select` with other features (for example, *anonymous types*) to form query projections.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="46b72-141">相关章节</span><span class="sxs-lookup"><span data-stu-id="46b72-141">Related Sections</span></span>  
 [<span data-ttu-id="46b72-142">标准查询运算符概述</span><span class="sxs-lookup"><span data-stu-id="46b72-142">Standard Query Operators Overview</span></span>](https://msdn.microsoft.com/library/24cda21e-8af8-4632-b519-c404a839b9b2)  
 <span data-ttu-id="46b72-143">解释标准查询运算符的概念。</span><span class="sxs-lookup"><span data-stu-id="46b72-143">Explains the concept of standard query operators.</span></span>  
  
 [<span data-ttu-id="46b72-144">查询概念</span><span class="sxs-lookup"><span data-stu-id="46b72-144">Query Concepts</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/query-concepts.md)  
 <span data-ttu-id="46b72-145">解释 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] 如何使用适用于查询的概念。</span><span class="sxs-lookup"><span data-stu-id="46b72-145">Explains how [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] uses concepts that apply to queries.</span></span>  
  
 [<span data-ttu-id="46b72-146">编程指南</span><span class="sxs-lookup"><span data-stu-id="46b72-146">Programming Guide</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/programming-guide.md)  
 <span data-ttu-id="46b72-147">提供用于访问一些主题的门户，这些主题解释了与 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] 相关的编程概念。</span><span class="sxs-lookup"><span data-stu-id="46b72-147">Provides a portal to topics that explain programming concepts related to [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)].</span></span>
