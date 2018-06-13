---
title: 对分组操作执行子查询
description: 如何对分组操作执行子查询。
ms.date: 12/1/2016
ms.assetid: d75a588e-9b6f-4f37-b195-f99ec8503855
ms.openlocfilehash: 209d05c2fe8719fa9116061d199272366146f465
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33277324"
---
# <a name="perform-a-subquery-on-a-grouping-operation"></a><span data-ttu-id="ab917-103">对分组操作执行子查询</span><span class="sxs-lookup"><span data-stu-id="ab917-103">Perform a subquery on a grouping operation</span></span>

<span data-ttu-id="ab917-104">本主题演示创建查询的两种不同方式，此查询将源数据排序成组，然后分别对每个组执行子查询。</span><span class="sxs-lookup"><span data-stu-id="ab917-104">This topic shows two different ways to create a query that orders the source data into groups, and then performs a subquery over each group individually.</span></span> <span data-ttu-id="ab917-105">每个示例中的基本方法是使用名为 `newGroup` 的“接续块”对源元素进行分组，然后针对 `newGroup` 生成新的子查询。</span><span class="sxs-lookup"><span data-stu-id="ab917-105">The basic technique in each example is to group the source elements by using a *continuation* named `newGroup`, and then generating a new subquery against `newGroup`.</span></span> <span data-ttu-id="ab917-106">针对由外部查询创建的每个新组运行此子查询。</span><span class="sxs-lookup"><span data-stu-id="ab917-106">This subquery is run against each new group that is created by the outer query.</span></span> <span data-ttu-id="ab917-107">请注意，在此特定示例中，最终输出不是组，而是一系列匿名类型。</span><span class="sxs-lookup"><span data-stu-id="ab917-107">Note that in this particular example the final output is not a group, but a flat sequence of anonymous types.</span></span>  
  
 <span data-ttu-id="ab917-108">有关如何分组的详细信息，请参阅 [group 子句](../language-reference/keywords/group-clause.md)。</span><span class="sxs-lookup"><span data-stu-id="ab917-108">For more information about how to group, see [group clause](../language-reference/keywords/group-clause.md).</span></span>  
  
 <span data-ttu-id="ab917-109">有关接续块的详细信息，请参阅 [into](../language-reference/keywords/into.md)。</span><span class="sxs-lookup"><span data-stu-id="ab917-109">For more information about continuations, see [into](../language-reference/keywords/into.md).</span></span> <span data-ttu-id="ab917-110">下面的示例使用内存数据结构作为数据源，但相同的原则适用于任何类型的 LINQ 数据源。</span><span class="sxs-lookup"><span data-stu-id="ab917-110">The following example uses an in-memory data structure as the data source, but the same principles apply for any kind of LINQ data source.</span></span>  
  
## <a name="example"></a><span data-ttu-id="ab917-111">示例</span><span class="sxs-lookup"><span data-stu-id="ab917-111">Example</span></span> 

 > [!NOTE]
 > <span data-ttu-id="ab917-112">此示例包含对[查询对象集合](query-a-collection-of-objects.md)内示例代码中所定义对象的引用。</span><span class="sxs-lookup"><span data-stu-id="ab917-112">This example contains references to objects that are defined in the sample code in [Query a collection of objects](query-a-collection-of-objects.md).</span></span>

 [!code-csharp[csProgGuideLINQ#23](../../../samples/snippets/csharp/concepts/linq/how-to-perform-a-subquery-on-a-grouping-operation_1.cs)]  
   
## <a name="see-also"></a><span data-ttu-id="ab917-113">请参阅</span><span class="sxs-lookup"><span data-stu-id="ab917-113">See also</span></span>  
 [<span data-ttu-id="ab917-114">LINQ 查询表达式</span><span class="sxs-lookup"><span data-stu-id="ab917-114">LINQ Query Expressions</span></span>](index.md)
