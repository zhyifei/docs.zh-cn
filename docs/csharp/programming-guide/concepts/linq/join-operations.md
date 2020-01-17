---
title: 联接运算 (C#)
ms.date: 07/20/2015
ms.assetid: 5105e0da-1267-4c00-837a-f0e9602279b8
ms.openlocfilehash: 86d85c7de16887fbe3001dc548d940d9c114e634
ms.sourcegitcommit: 7bc6887ab658550baa78f1520ea735838249345e
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/03/2020
ms.locfileid: "75635595"
---
# <a name="join-operations-c"></a><span data-ttu-id="bfcab-102">联接运算 (C#)</span><span class="sxs-lookup"><span data-stu-id="bfcab-102">Join Operations (C#)</span></span>
<span data-ttu-id="bfcab-103">联接  两个数据源就是将一个数据源中的对象与另一个数据源中具有相同公共属性的对象相关联。</span><span class="sxs-lookup"><span data-stu-id="bfcab-103">A *join* of two data sources is the association of objects in one data source with objects that share a common attribute in another data source.</span></span>  
  
 <span data-ttu-id="bfcab-104">当查询所面向的数据源相互之间具有无法直接领会的关系时，联接就成为一项重要的运算。</span><span class="sxs-lookup"><span data-stu-id="bfcab-104">Joining is an important operation in queries that target data sources whose relationships to each other cannot be followed directly.</span></span> <span data-ttu-id="bfcab-105">在面向对象的编程中，这可能意味着在未建模对象之间进行关联，例如对单向关系进行反向推理。</span><span class="sxs-lookup"><span data-stu-id="bfcab-105">In object-oriented programming, this could mean a correlation between objects that is not modeled, such as the backwards direction of a one-way relationship.</span></span> <span data-ttu-id="bfcab-106">下面是单向关系的一个示例：Customer 类有一个类型为 City 的属性，但 City 类没有作为 Customer 对象集合的属性。</span><span class="sxs-lookup"><span data-stu-id="bfcab-106">An example of a one-way relationship is a Customer class that has a property of type City, but the City class does not have a property that is a collection of Customer objects.</span></span> <span data-ttu-id="bfcab-107">如果你具有一个 City 对象列表，并且要查找每个城市中的所有客户，则可以使用联接运算完成此项查找。</span><span class="sxs-lookup"><span data-stu-id="bfcab-107">If you have a list of City objects and you want to find all the customers in each city, you could use a join operation to find them.</span></span>  
  
 <span data-ttu-id="bfcab-108">LINQ 框架中提供的 join 方法包括 <xref:System.Linq.Enumerable.Join%2A> 和 <xref:System.Linq.Enumerable.GroupJoin%2A>。</span><span class="sxs-lookup"><span data-stu-id="bfcab-108">The join methods provided in the LINQ framework are <xref:System.Linq.Enumerable.Join%2A> and <xref:System.Linq.Enumerable.GroupJoin%2A>.</span></span> <span data-ttu-id="bfcab-109">这些方法执行同等联接，即根据 2 个数据源的键是否相等来匹配这 2 个数据源的联接。</span><span class="sxs-lookup"><span data-stu-id="bfcab-109">These methods perform equijoins, or joins that match two data sources based on equality of their keys.</span></span> <span data-ttu-id="bfcab-110">（与此相较，Transact-SQL 支持除“等于”之外的联接运算符，例如“小于”运算符。）用关系数据库术语表达，就是说 <xref:System.Linq.Enumerable.Join%2A> 实现了内部联接，这种联接只返回那些在另一个数据集中具有匹配项的对象。</span><span class="sxs-lookup"><span data-stu-id="bfcab-110">(For comparison, Transact-SQL supports join operators other than 'equals', for example the 'less than' operator.) In relational database terms, <xref:System.Linq.Enumerable.Join%2A> implements an inner join, a type of join in which only those objects that have a match in the other data set are returned.</span></span> <span data-ttu-id="bfcab-111"><xref:System.Linq.Enumerable.GroupJoin%2A> 方法在关系数据库术语中没有直接等效项，但实现了内部联接和左外部联接的超集。</span><span class="sxs-lookup"><span data-stu-id="bfcab-111">The <xref:System.Linq.Enumerable.GroupJoin%2A> method has no direct equivalent in relational database terms, but it implements a superset of inner joins and left outer joins.</span></span> <span data-ttu-id="bfcab-112">左外部联接是指返回第一个（左侧）数据源的每个元素的联接，即使其他数据源中没有关联元素。</span><span class="sxs-lookup"><span data-stu-id="bfcab-112">A left outer join is a join that returns each element of the first (left) data source, even if it has no correlated elements in the other data source.</span></span>  
  
 <span data-ttu-id="bfcab-113">下图显示了一个概念性视图，其中包含两个集合以及这两个集合中的包含在内部联接或左外部联接中的元素。</span><span class="sxs-lookup"><span data-stu-id="bfcab-113">The following illustration shows a conceptual view of two sets and the elements within those sets that are included in either an inner join or a left outer join.</span></span>  
  
 ![显示内部/外部的两个重叠圆圈。](./media/join-operations/join-method-overlapping-circles.png)  
  
## <a name="methods"></a><span data-ttu-id="bfcab-115">方法</span><span class="sxs-lookup"><span data-stu-id="bfcab-115">Methods</span></span>  
  
|<span data-ttu-id="bfcab-116">方法名</span><span class="sxs-lookup"><span data-stu-id="bfcab-116">Method Name</span></span>|<span data-ttu-id="bfcab-117">描述</span><span class="sxs-lookup"><span data-stu-id="bfcab-117">Description</span></span>|<span data-ttu-id="bfcab-118">C# 查询表达式语法</span><span class="sxs-lookup"><span data-stu-id="bfcab-118">C# Query Expression Syntax</span></span>|<span data-ttu-id="bfcab-119">详细信息</span><span class="sxs-lookup"><span data-stu-id="bfcab-119">More Information</span></span>|  
|-----------------|-----------------|---------------------------------|----------------------|  
|<span data-ttu-id="bfcab-120">联接</span><span class="sxs-lookup"><span data-stu-id="bfcab-120">Join</span></span>|<span data-ttu-id="bfcab-121">根据键选择器函数联接两个序列并提取值对。</span><span class="sxs-lookup"><span data-stu-id="bfcab-121">Joins two sequences based on key selector functions and extracts pairs of values.</span></span>|`join … in … on … equals …`|<xref:System.Linq.Enumerable.Join%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.Join%2A?displayProperty=nameWithType>|  
|<span data-ttu-id="bfcab-122">GroupJoin</span><span class="sxs-lookup"><span data-stu-id="bfcab-122">GroupJoin</span></span>|<span data-ttu-id="bfcab-123">根据键选择器函数联接两个序列，并对每个元素的结果匹配项进行分组。</span><span class="sxs-lookup"><span data-stu-id="bfcab-123">Joins two sequences based on key selector functions and groups the resulting matches for each element.</span></span>|`join … in … on … equals … into …`|<xref:System.Linq.Enumerable.GroupJoin%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.GroupJoin%2A?displayProperty=nameWithType>|  
  
## <a name="see-also"></a><span data-ttu-id="bfcab-124">请参阅</span><span class="sxs-lookup"><span data-stu-id="bfcab-124">See also</span></span>

- <xref:System.Linq>
- [<span data-ttu-id="bfcab-125">标准查询运算符概述 (C#)</span><span class="sxs-lookup"><span data-stu-id="bfcab-125">Standard Query Operators Overview (C#)</span></span>](./standard-query-operators-overview.md)
- [<span data-ttu-id="bfcab-126">匿名类型</span><span class="sxs-lookup"><span data-stu-id="bfcab-126">Anonymous Types</span></span>](../../classes-and-structs/anonymous-types.md)
- [<span data-ttu-id="bfcab-127">构建联接和叉积查询</span><span class="sxs-lookup"><span data-stu-id="bfcab-127">Formulate Joins and Cross-Product Queries</span></span>](../../../../framework/data/adonet/sql/linq/formulate-joins-and-cross-product-queries.md)
- [<span data-ttu-id="bfcab-128">join 子句</span><span class="sxs-lookup"><span data-stu-id="bfcab-128">join clause</span></span>](../../../language-reference/keywords/join-clause.md)
- [<span data-ttu-id="bfcab-129">使用复合键进行联接</span><span class="sxs-lookup"><span data-stu-id="bfcab-129">Join by using composite keys</span></span>](../../../linq/join-by-using-composite-keys.md)
- [<span data-ttu-id="bfcab-130">如何联接不同文件的内容 (LINQ) (C#)</span><span class="sxs-lookup"><span data-stu-id="bfcab-130">How to join content from dissimilar files (LINQ) (C#)</span></span>](./how-to-join-content-from-dissimilar-files-linq.md)
- [<span data-ttu-id="bfcab-131">对 Join 子句的结果进行排序</span><span class="sxs-lookup"><span data-stu-id="bfcab-131">Order the results of a join clause</span></span>](../../../linq/order-the-results-of-a-join-clause.md)
- [<span data-ttu-id="bfcab-132">执行自定义联接操作</span><span class="sxs-lookup"><span data-stu-id="bfcab-132">Perform custom join operations</span></span>](../../../linq/perform-custom-join-operations.md)
- [<span data-ttu-id="bfcab-133">执行分组联接</span><span class="sxs-lookup"><span data-stu-id="bfcab-133">Perform grouped joins</span></span>](../../../linq/perform-grouped-joins.md)
- [<span data-ttu-id="bfcab-134">执行内部联接</span><span class="sxs-lookup"><span data-stu-id="bfcab-134">Perform inner joins</span></span>](../../../linq/perform-inner-joins.md)
- [<span data-ttu-id="bfcab-135">执行左外部联接</span><span class="sxs-lookup"><span data-stu-id="bfcab-135">Perform left outer joins</span></span>](../../../linq/perform-left-outer-joins.md)
- [<span data-ttu-id="bfcab-136">如何从多个源填充对象集合 (LINQ) (C#)</span><span class="sxs-lookup"><span data-stu-id="bfcab-136">How to populate object collections from multiple sources (LINQ) (C#)</span></span>](./how-to-populate-object-collections-from-multiple-sources-linq.md)
