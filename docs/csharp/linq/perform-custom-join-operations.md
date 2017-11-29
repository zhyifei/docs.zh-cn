---
title: "执行自定义联接操作"
description: "如何执行自定义联接操作。"
keywords: .NET, .NET Core, C#
author: BillWagner
manager: wpickett
ms.author: wiwagn
ms.date: 12/1/2016
ms.topic: article
ms.prod: .net
ms.technology: devlang-csharp
ms.assetid: 56a2a4a5-7299-497d-b3c3-23c848678911
ms.openlocfilehash: fef146c92a5cbbf21f8f1688f221c2bd45c99de7
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="perform-custom-join-operations"></a><span data-ttu-id="6c268-104">执行自定义联接操作</span><span class="sxs-lookup"><span data-stu-id="6c268-104">Perform custom join operations</span></span>

<span data-ttu-id="6c268-105">此示例演示如何执行无法使用 `join` 子句实现的联接操作。</span><span class="sxs-lookup"><span data-stu-id="6c268-105">This example shows how to perform join operations that are not possible with the `join` clause.</span></span> <span data-ttu-id="6c268-106">在查询表达式中，`join` 子句只限于同等联接（并针对其进行优化），这类联接到目前为止是最常见的联接操作类型。</span><span class="sxs-lookup"><span data-stu-id="6c268-106">In a query expression, the `join` clause is limited to, and optimized for, equijoins, which are by far the most common type of join operation.</span></span> <span data-ttu-id="6c268-107">执行同等联接时，可能会始终使用 `join` 子句获得最佳性能。</span><span class="sxs-lookup"><span data-stu-id="6c268-107">When performing an equijoin, you will probably always get the best performance by using the `join` clause.</span></span>  
  
 <span data-ttu-id="6c268-108">但是，在以下情况下不能使用 `join` 子句：</span><span class="sxs-lookup"><span data-stu-id="6c268-108">However, the `join` clause cannot be used in the following cases:</span></span>  
  
-   <span data-ttu-id="6c268-109">当联接依据不等式表达式时（非同等联接）。</span><span class="sxs-lookup"><span data-stu-id="6c268-109">When the join is predicated on an expression of inequality (a non-equijoin).</span></span>  
  
-   <span data-ttu-id="6c268-110">当联接依据多个等式或不等式表达式时。</span><span class="sxs-lookup"><span data-stu-id="6c268-110">When the join is predicated on more than one expression of equality or inequality.</span></span>  
  
-   <span data-ttu-id="6c268-111">当必须为联接操作前的右侧（内部）序列引入临时范围变量。</span><span class="sxs-lookup"><span data-stu-id="6c268-111">When you have to introduce a temporary range variable for the right side (inner) sequence before the join operation.</span></span>  
  
 <span data-ttu-id="6c268-112">若要执行不是同等联接的联接，可以使用多个 `from` 子句独立引入每个数据源。</span><span class="sxs-lookup"><span data-stu-id="6c268-112">To perform joins that are not equijoins, you can use multiple `from` clauses to introduce each data source independently.</span></span> <span data-ttu-id="6c268-113">随后可在 `where` 子句中将谓词表达式应用于每个源的范围变量。</span><span class="sxs-lookup"><span data-stu-id="6c268-113">You then apply a predicate expression in a `where` clause to the range variable for each source.</span></span> <span data-ttu-id="6c268-114">表达式还可以采用方法调用的形式。</span><span class="sxs-lookup"><span data-stu-id="6c268-114">The expression also can take the form of a method call.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="6c268-115">不要将这种类型的自定义联接操作与使用多个 `from` 子句访问内部集合相混淆。</span><span class="sxs-lookup"><span data-stu-id="6c268-115">Do not confuse this kind of custom join operation with the use of multiple `from` clauses to access inner collections.</span></span> <span data-ttu-id="6c268-116">有关详细信息，请参阅 [join 子句](../language-reference/keywords/join-clause.md)。</span><span class="sxs-lookup"><span data-stu-id="6c268-116">For more information, see [join clause](../language-reference/keywords/join-clause.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="6c268-117">示例</span><span class="sxs-lookup"><span data-stu-id="6c268-117">Example</span></span>  
 <span data-ttu-id="6c268-118">以下示例中的第一个方法演示一个简单的交叉联接。</span><span class="sxs-lookup"><span data-stu-id="6c268-118">The first method in the following example shows a simple cross join.</span></span> <span data-ttu-id="6c268-119">必须谨慎使用交叉联接，因为它们可能会生成非常大的结果集。</span><span class="sxs-lookup"><span data-stu-id="6c268-119">Cross joins must be used with caution because they can produce very large result sets.</span></span> <span data-ttu-id="6c268-120">但是，在创建针对其运行其他查询的源序列的某些情况下，它们可能会十分有用。</span><span class="sxs-lookup"><span data-stu-id="6c268-120">However, they can be useful in some scenarios for creating source sequences against which additional queries are run.</span></span>  
  
 <span data-ttu-id="6c268-121">第二个方法会生成其类别 ID 在左侧类别列表中列出的所有产品的序列。</span><span class="sxs-lookup"><span data-stu-id="6c268-121">The second method produces a sequence of all the products whose category ID is listed in the category list on the left side.</span></span> <span data-ttu-id="6c268-122">请注意，其中使用 `let` 子句和 `Contains` 方法创建临时数组。</span><span class="sxs-lookup"><span data-stu-id="6c268-122">Note the use of the `let` clause and the `Contains` method to create a temporary array.</span></span> <span data-ttu-id="6c268-123">还可以在查询前创建数组并去掉第一个 `from` 子句。</span><span class="sxs-lookup"><span data-stu-id="6c268-123">It also is possible to create the array before the query and eliminate the first `from` clause.</span></span>  
  
 [!code-csharp[csProgGuideLINQ#64](../../../samples/snippets/csharp/concepts/linq/how-to-perform-custom-join-operations_1.cs)]  
  
## <a name="example"></a><span data-ttu-id="6c268-124">示例</span><span class="sxs-lookup"><span data-stu-id="6c268-124">Example</span></span>  
 <span data-ttu-id="6c268-125">在下面的示例中，查询必须基于匹配键（对于内部（右侧）序列，无法在 join 子句本身之前获取这些键）联接两个序列。</span><span class="sxs-lookup"><span data-stu-id="6c268-125">In the following example, the query must join two sequences based on matching keys that, in the case of the inner (right side) sequence, cannot be obtained prior to the join clause itself.</span></span> <span data-ttu-id="6c268-126">如果使用 `join` 子句执行了此联接，则必须为每个元素调用 `Split` 方法。</span><span class="sxs-lookup"><span data-stu-id="6c268-126">If this join were performed with a `join` clause, then the `Split` method would have to be called for each element.</span></span> <span data-ttu-id="6c268-127">使用多个 `from` 子句可使查询避免重复进行方法调用的开销。</span><span class="sxs-lookup"><span data-stu-id="6c268-127">The use of multiple `from` clauses enables the query to avoid the overhead of the repeated method call.</span></span> <span data-ttu-id="6c268-128">但是，因为 `join` 经过了优化，所有在此特定情况下，它可能仍然比使用多个 `from` 子句更快。</span><span class="sxs-lookup"><span data-stu-id="6c268-128">However, since `join` is optimized, in this particular case it might still be faster than using multiple `from` clauses.</span></span> <span data-ttu-id="6c268-129">结果的变化主要取决于方法调用的成本高低。</span><span class="sxs-lookup"><span data-stu-id="6c268-129">The results will vary depending primarily on how expensive the method call is.</span></span>  
  
 [!code-csharp[csProgGuideLINQ#13](../../../samples/snippets/csharp/concepts/linq/how-to-perform-custom-join-operations_2.cs)]  
  
## <a name="see-also"></a><span data-ttu-id="6c268-130">请参阅</span><span class="sxs-lookup"><span data-stu-id="6c268-130">See also</span></span>  
 [<span data-ttu-id="6c268-131">LINQ 查询表达式</span><span class="sxs-lookup"><span data-stu-id="6c268-131">LINQ query expressions</span></span>](index.md)  
 [<span data-ttu-id="6c268-132">join 子句</span><span class="sxs-lookup"><span data-stu-id="6c268-132">join clause</span></span>](../language-reference/keywords/join-clause.md)  
 [<span data-ttu-id="6c268-133">对 Join 子句的结果进行排序</span><span class="sxs-lookup"><span data-stu-id="6c268-133">Order the results of a join clause</span></span>](order-the-results-of-a-join-clause.md)
