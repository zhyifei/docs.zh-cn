---
title: "联接运算 (C#)"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
ms.assetid: 5105e0da-1267-4c00-837a-f0e9602279b8
caps.latest.revision: 3
author: BillWagner
ms.author: wiwagn
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: df2f88f2988a4c91730bcfc4e39f10e3471e4ddf
ms.contentlocale: zh-cn
ms.lasthandoff: 07/28/2017

---
# <a name="join-operations-c"></a><span data-ttu-id="99ab2-102">联接运算 (C#)</span><span class="sxs-lookup"><span data-stu-id="99ab2-102">Join Operations (C#)</span></span>
<span data-ttu-id="99ab2-103">联接两个数据源就是将一个数据源中的对象与另一个数据源中具有相同公共属性的对象相关联。</span><span class="sxs-lookup"><span data-stu-id="99ab2-103">A *join* of two data sources is the association of objects in one data source with objects that share a common attribute in another data source.</span></span>  
  
 <span data-ttu-id="99ab2-104">当查询所面向的数据源相互之间具有无法直接领会的关系时，联接就成为一项重要的运算。</span><span class="sxs-lookup"><span data-stu-id="99ab2-104">Joining is an important operation in queries that target data sources whose relationships to each other cannot be followed directly.</span></span> <span data-ttu-id="99ab2-105">在面向对象的编程中，这可能意味着在未建模对象之间进行关联，例如对单向关系进行反向推理。</span><span class="sxs-lookup"><span data-stu-id="99ab2-105">In object-oriented programming, this could mean a correlation between objects that is not modeled, such as the backwards direction of a one-way relationship.</span></span> <span data-ttu-id="99ab2-106">下面是单向关系的一个示例：Customer 类有一个类型为 City 的属性，但 City 类没有作为 Customer 对象集合的属性。</span><span class="sxs-lookup"><span data-stu-id="99ab2-106">An example of a one-way relationship is a Customer class that has a property of type City, but the City class does not have a property that is a collection of Customer objects.</span></span> <span data-ttu-id="99ab2-107">如果你具有一个 City 对象列表，并且要查找每个城市中的所有客户，则可以使用联接运算完成此项查找。</span><span class="sxs-lookup"><span data-stu-id="99ab2-107">If you have a list of City objects and you want to find all the customers in each city, you could use a join operation to find them.</span></span>  
  
 <span data-ttu-id="99ab2-108">LINQ 框架中提供的 join 方法包括 <xref:System.Linq.Enumerable.Join%2A> 和 <xref:System.Linq.Enumerable.GroupJoin%2A>。</span><span class="sxs-lookup"><span data-stu-id="99ab2-108">The join methods provided in the LINQ framework are <xref:System.Linq.Enumerable.Join%2A> and <xref:System.Linq.Enumerable.GroupJoin%2A>.</span></span> <span data-ttu-id="99ab2-109">这些方法执行同等联接，即根据 2 个数据源的键是否相等来匹配这 2 个数据源的联接。</span><span class="sxs-lookup"><span data-stu-id="99ab2-109">These methods perform equijoins, or joins that match two data sources based on equality of their keys.</span></span> <span data-ttu-id="99ab2-110">（与此相较，Transact-SQL 支持除“等于”之外的联接运算符，例如“小于”运算符。）用关系数据库术语表达，就是说 <xref:System.Linq.Enumerable.Join%2A> 实现了内部联接，这种联接只返回那些在另一个数据集中具有匹配项的对象。</span><span class="sxs-lookup"><span data-stu-id="99ab2-110">(For comparison, Transact-SQL supports join operators other than 'equals', for example the 'less than' operator.) In relational database terms, <xref:System.Linq.Enumerable.Join%2A> implements an inner join, a type of join in which only those objects that have a match in the other data set are returned.</span></span> <span data-ttu-id="99ab2-111"><xref:System.Linq.Enumerable.GroupJoin%2A> 方法在关系数据库术语中没有直接等效项，但实现了内部联接和左外部联接的超集。</span><span class="sxs-lookup"><span data-stu-id="99ab2-111">The <xref:System.Linq.Enumerable.GroupJoin%2A> method has no direct equivalent in relational database terms, but it implements a superset of inner joins and left outer joins.</span></span> <span data-ttu-id="99ab2-112">左外部联接是指返回第一个（左侧）数据源的每个元素的联接，即使其他数据源中没有关联元素。</span><span class="sxs-lookup"><span data-stu-id="99ab2-112">A left outer join is a join that returns each element of the first (left) data source, even if it has no correlated elements in the other data source.</span></span>  
  
 <span data-ttu-id="99ab2-113">下图显示了一个概念性视图，其中包含两个集合以及这两个集合中的包含在内部联接或左外部联接中的元素。</span><span class="sxs-lookup"><span data-stu-id="99ab2-113">The following illustration shows a conceptual view of two sets and the elements within those sets that are included in either an inner join or a left outer join.</span></span>  
  
 <span data-ttu-id="99ab2-114">![显示内部/外部的两个重叠圆圈。](../../../../csharp/programming-guide/concepts/linq/media/joincircles.png "JoinCircles")</span><span class="sxs-lookup"><span data-stu-id="99ab2-114">![Two overlapping circles showing inner&#47;outer.](../../../../csharp/programming-guide/concepts/linq/media/joincircles.png "JoinCircles")</span></span>  
  
## <a name="methods"></a><span data-ttu-id="99ab2-115">方法</span><span class="sxs-lookup"><span data-stu-id="99ab2-115">Methods</span></span>  
  
|<span data-ttu-id="99ab2-116">方法名</span><span class="sxs-lookup"><span data-stu-id="99ab2-116">Method Name</span></span>|<span data-ttu-id="99ab2-117">描述</span><span class="sxs-lookup"><span data-stu-id="99ab2-117">Description</span></span>|<span data-ttu-id="99ab2-118">C# 查询表达式语法</span><span class="sxs-lookup"><span data-stu-id="99ab2-118">C# Query Expression Syntax</span></span>|<span data-ttu-id="99ab2-119">详细信息</span><span class="sxs-lookup"><span data-stu-id="99ab2-119">More Information</span></span>|  
|-----------------|-----------------|---------------------------------|----------------------|  
|<span data-ttu-id="99ab2-120">联接</span><span class="sxs-lookup"><span data-stu-id="99ab2-120">Join</span></span>|<span data-ttu-id="99ab2-121">根据键选择器函数联接两个序列并提取值对。</span><span class="sxs-lookup"><span data-stu-id="99ab2-121">Joins two sequences based on key selector functions and extracts pairs of values.</span></span>|`join … in … on … equals …`|<xref:System.Linq.Enumerable.Join%2A?displayProperty=fullName><br /><br /> <xref:System.Linq.Queryable.Join%2A?displayProperty=fullName>|  
|<span data-ttu-id="99ab2-122">GroupJoin</span><span class="sxs-lookup"><span data-stu-id="99ab2-122">GroupJoin</span></span>|<span data-ttu-id="99ab2-123">根据键选择器函数联接两个序列，并对每个元素的结果匹配项进行分组。</span><span class="sxs-lookup"><span data-stu-id="99ab2-123">Joins two sequences based on key selector functions and groups the resulting matches for each element.</span></span>|`join … in … on … equals … into …`|<xref:System.Linq.Enumerable.GroupJoin%2A?displayProperty=fullName><br /><br /> <xref:System.Linq.Queryable.GroupJoin%2A?displayProperty=fullName>|  
  
## <a name="see-also"></a><span data-ttu-id="99ab2-124">另请参阅</span><span class="sxs-lookup"><span data-stu-id="99ab2-124">See Also</span></span>  
 <span data-ttu-id="99ab2-125"><xref:System.Linq></span><span class="sxs-lookup"><span data-stu-id="99ab2-125"><xref:System.Linq></span></span>   
 <span data-ttu-id="99ab2-126">[标准查询运算符概述 (C#)](../../../../csharp/programming-guide/concepts/linq/standard-query-operators-overview.md) </span><span class="sxs-lookup"><span data-stu-id="99ab2-126">[Standard Query Operators Overview (C#)](../../../../csharp/programming-guide/concepts/linq/standard-query-operators-overview.md) </span></span>  
 <span data-ttu-id="99ab2-127">[匿名类型](../../../../csharp/programming-guide/classes-and-structs/anonymous-types.md) </span><span class="sxs-lookup"><span data-stu-id="99ab2-127">[Anonymous Types](../../../../csharp/programming-guide/classes-and-structs/anonymous-types.md) </span></span>  
 <span data-ttu-id="99ab2-128">[构建联接和叉积查询](http://msdn.microsoft.com/library/d8072ede-0521-4670-9bec-1778ceeb875b) </span><span class="sxs-lookup"><span data-stu-id="99ab2-128">[Formulate Joins and Cross-Product Queries](http://msdn.microsoft.com/library/d8072ede-0521-4670-9bec-1778ceeb875b) </span></span>  
 <span data-ttu-id="99ab2-129">[join 子句](../../../../csharp/language-reference/keywords/join-clause.md) </span><span class="sxs-lookup"><span data-stu-id="99ab2-129">[join clause](../../../../csharp/language-reference/keywords/join-clause.md) </span></span>  
 <span data-ttu-id="99ab2-130">[如何：使用组合键进行联接](../../../../csharp/programming-guide/linq-query-expressions/how-to-join-by-using-composite-keys.md) </span><span class="sxs-lookup"><span data-stu-id="99ab2-130">[How to: Join by Using Composite Keys](../../../../csharp/programming-guide/linq-query-expressions/how-to-join-by-using-composite-keys.md) </span></span>  
 <span data-ttu-id="99ab2-131">[如何：联接不同文件的内容 (LINQ) (C#)](../../../../csharp/programming-guide/concepts/linq/how-to-join-content-from-dissimilar-files-linq.md) </span><span class="sxs-lookup"><span data-stu-id="99ab2-131">[How to: Join Content from Dissimilar Files (LINQ) (C#)](../../../../csharp/programming-guide/concepts/linq/how-to-join-content-from-dissimilar-files-linq.md) </span></span>  
 <span data-ttu-id="99ab2-132">[如何：对 Join 子句的结果进行排序](../../../../csharp/programming-guide/linq-query-expressions/how-to-order-the-results-of-a-join-clause.md) </span><span class="sxs-lookup"><span data-stu-id="99ab2-132">[How to: Order the Results of a Join Clause](../../../../csharp/programming-guide/linq-query-expressions/how-to-order-the-results-of-a-join-clause.md) </span></span>  
 <span data-ttu-id="99ab2-133">[如何：执行自定义联接操作](../../../../csharp/programming-guide/linq-query-expressions/how-to-perform-custom-join-operations.md) </span><span class="sxs-lookup"><span data-stu-id="99ab2-133">[How to: Perform Custom Join Operations](../../../../csharp/programming-guide/linq-query-expressions/how-to-perform-custom-join-operations.md) </span></span>  
 <span data-ttu-id="99ab2-134">[如何：执行分组联接](../../../../csharp/programming-guide/linq-query-expressions/how-to-perform-grouped-joins.md) </span><span class="sxs-lookup"><span data-stu-id="99ab2-134">[How to: Perform Grouped Joins](../../../../csharp/programming-guide/linq-query-expressions/how-to-perform-grouped-joins.md) </span></span>  
 <span data-ttu-id="99ab2-135">[如何：执行内部联接](../../../../csharp/programming-guide/linq-query-expressions/how-to-perform-inner-joins.md) </span><span class="sxs-lookup"><span data-stu-id="99ab2-135">[How to: Perform Inner Joins](../../../../csharp/programming-guide/linq-query-expressions/how-to-perform-inner-joins.md) </span></span>  
 <span data-ttu-id="99ab2-136">[如何：执行左外部联接](../../../../csharp/programming-guide/linq-query-expressions/how-to-perform-left-outer-joins.md) </span><span class="sxs-lookup"><span data-stu-id="99ab2-136">[How to: Perform Left Outer Joins](../../../../csharp/programming-guide/linq-query-expressions/how-to-perform-left-outer-joins.md) </span></span>  
 [<span data-ttu-id="99ab2-137">如何：从多个源填充对象集合 (LINQ) (C#)</span><span class="sxs-lookup"><span data-stu-id="99ab2-137">How to: Populate Object Collections from Multiple Sources (LINQ) (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/how-to-populate-object-collections-from-multiple-sources-linq.md)

