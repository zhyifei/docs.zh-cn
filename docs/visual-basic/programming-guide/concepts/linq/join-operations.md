---
title: "联接操作 (Visual Basic 中) |Microsoft 文档"
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
ms.assetid: 39ab4854-ac84-4738-9d0b-3cb79be84db4
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
ms.openlocfilehash: 5b561f66069b042f3216c80c7b8b3a13df63647e
ms.contentlocale: zh-cn
ms.lasthandoff: 04/12/2017

---
# <a name="join-operations-visual-basic"></a><span data-ttu-id="7274f-102">联接操作 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="7274f-102">Join Operations (Visual Basic)</span></span>
<span data-ttu-id="7274f-103">一个*联接*两个数据源就是一个数据源中的对象具有共享一个公共属性，另一个数据源中的对象相关联。</span><span class="sxs-lookup"><span data-stu-id="7274f-103">A *join* of two data sources is the association of objects in one data source with objects that share a common attribute in another data source.</span></span>  
  
 <span data-ttu-id="7274f-104">当查询所面向的数据源相互之间具有无法直接领会的关系时，联接就成为一项重要的运算。</span><span class="sxs-lookup"><span data-stu-id="7274f-104">Joining is an important operation in queries that target data sources whose relationships to each other cannot be followed directly.</span></span> <span data-ttu-id="7274f-105">在面向对象的编程中，这可能意味着在未建模对象之间进行关联，例如对单向关系进行反向推理。</span><span class="sxs-lookup"><span data-stu-id="7274f-105">In object-oriented programming, this could mean a correlation between objects that is not modeled, such as the backwards direction of a one-way relationship.</span></span> <span data-ttu-id="7274f-106">下面是单向关系的一个示例：Customer 类有一个类型为 City 的属性，但 City 类没有作为 Customer 对象集合的属性。</span><span class="sxs-lookup"><span data-stu-id="7274f-106">An example of a one-way relationship is a Customer class that has a property of type City, but the City class does not have a property that is a collection of Customer objects.</span></span> <span data-ttu-id="7274f-107">如果你具有一个 City 对象列表，并且要查找每个城市中的所有客户，则可以使用联接运算完成此项查找。</span><span class="sxs-lookup"><span data-stu-id="7274f-107">If you have a list of City objects and you want to find all the customers in each city, you could use a join operation to find them.</span></span>  
  
 <span data-ttu-id="7274f-108">LINQ 框架中提供的联接方法有<xref:System.Linq.Enumerable.Join%2A>和<xref:System.Linq.Enumerable.GroupJoin%2A>。</xref:System.Linq.Enumerable.GroupJoin%2A> </xref:System.Linq.Enumerable.Join%2A></span><span class="sxs-lookup"><span data-stu-id="7274f-108">The join methods provided in the LINQ framework are <xref:System.Linq.Enumerable.Join%2A> and <xref:System.Linq.Enumerable.GroupJoin%2A>.</span></span> <span data-ttu-id="7274f-109">这些方法执行同等联接，即来匹配基于的键相等对两个数据源的联接。</span><span class="sxs-lookup"><span data-stu-id="7274f-109">These methods perform equijoins, or joins that match two data sources based on equality of their keys.</span></span> <span data-ttu-id="7274f-110">（与此相较，Transact-SQL 支持除“等于”之外的联接运算符，例如“小于”运算符。）在关系数据库术语<xref:System.Linq.Enumerable.Join%2A>实现内部联接中，一种联接类型仅在另一个数据集中具有匹配项的那些对象返回。</xref:System.Linq.Enumerable.Join%2A></span><span class="sxs-lookup"><span data-stu-id="7274f-110">(For comparison, Transact-SQL supports join operators other than 'equals', for example the 'less than' operator.) In relational database terms, <xref:System.Linq.Enumerable.Join%2A> implements an inner join, a type of join in which only those objects that have a match in the other data set are returned.</span></span> <span data-ttu-id="7274f-111"><xref:System.Linq.Enumerable.GroupJoin%2A>方法在关系数据库术语中，有没有直接等效项，但它实现了内部联接和左外部联接的超集。</xref:System.Linq.Enumerable.GroupJoin%2A></span><span class="sxs-lookup"><span data-stu-id="7274f-111">The <xref:System.Linq.Enumerable.GroupJoin%2A> method has no direct equivalent in relational database terms, but it implements a superset of inner joins and left outer joins.</span></span> <span data-ttu-id="7274f-112">左外部联接是一种联接，返回第一个 （左） 数据源，每个元素，即使它具有其他数据源中没有关联的元素。</span><span class="sxs-lookup"><span data-stu-id="7274f-112">A left outer join is a join that returns each element of the first (left) data source, even if it has no correlated elements in the other data source.</span></span>  
  
 <span data-ttu-id="7274f-113">下图显示了一个概念性视图，其中包含两个集合以及这两个集合中的包含在内部联接或左外部联接中的元素。</span><span class="sxs-lookup"><span data-stu-id="7274f-113">The following illustration shows a conceptual view of two sets and the elements within those sets that are included in either an inner join or a left outer join.</span></span>  
  
 <span data-ttu-id="7274f-114">![显示内部/外部的两个重叠圆圈。] (../../../../csharp/programming-guide/concepts/linq/media/joincircles.png "JoinCircles")</span><span class="sxs-lookup"><span data-stu-id="7274f-114">![Two overlapping circles showing inner&#47;outer.](../../../../csharp/programming-guide/concepts/linq/media/joincircles.png "JoinCircles")</span></span>  
  
## <a name="methods"></a><span data-ttu-id="7274f-115">方法</span><span class="sxs-lookup"><span data-stu-id="7274f-115">Methods</span></span>  
  
|<span data-ttu-id="7274f-116">方法名</span><span class="sxs-lookup"><span data-stu-id="7274f-116">Method Name</span></span>|<span data-ttu-id="7274f-117">描述</span><span class="sxs-lookup"><span data-stu-id="7274f-117">Description</span></span>|<span data-ttu-id="7274f-118">Visual Basic 查询表达式语法</span><span class="sxs-lookup"><span data-stu-id="7274f-118">Visual Basic Query Expression Syntax</span></span>|<span data-ttu-id="7274f-119">更多信息</span><span class="sxs-lookup"><span data-stu-id="7274f-119">More Information</span></span>|  
|-----------------|-----------------|------------------------------------------|----------------------|  
|<span data-ttu-id="7274f-120">联接</span><span class="sxs-lookup"><span data-stu-id="7274f-120">Join</span></span>|<span data-ttu-id="7274f-121">根据键选择器函数联接两个序列并提取值对。</span><span class="sxs-lookup"><span data-stu-id="7274f-121">Joins two sequences based on key selector functions and extracts pairs of values.</span></span>|`From x In …, y In … Where x.a = y.a`<br /><br /> <span data-ttu-id="7274f-122">- 或 -</span><span class="sxs-lookup"><span data-stu-id="7274f-122">-or-</span></span><br /><br /> `Join … [As …]In … On …`|<span data-ttu-id="7274f-123"><xref:System.Linq.Enumerable.Join%2A?displayProperty=fullName></xref:System.Linq.Enumerable.Join%2A?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="7274f-123"><xref:System.Linq.Enumerable.Join%2A?displayProperty=fullName></span></span><br /><br /> <span data-ttu-id="7274f-124"><xref:System.Linq.Queryable.Join%2A?displayProperty=fullName></xref:System.Linq.Queryable.Join%2A?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="7274f-124"><xref:System.Linq.Queryable.Join%2A?displayProperty=fullName></span></span>|  
|<span data-ttu-id="7274f-125">GroupJoin</span><span class="sxs-lookup"><span data-stu-id="7274f-125">GroupJoin</span></span>|<span data-ttu-id="7274f-126">根据键选择器函数联接两个序列，并对每个元素的结果匹配项进行分组。</span><span class="sxs-lookup"><span data-stu-id="7274f-126">Joins two sequences based on key selector functions and groups the resulting matches for each element.</span></span>|`Group Join … In … On …`|<span data-ttu-id="7274f-127"><xref:System.Linq.Enumerable.GroupJoin%2A?displayProperty=fullName></xref:System.Linq.Enumerable.GroupJoin%2A?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="7274f-127"><xref:System.Linq.Enumerable.GroupJoin%2A?displayProperty=fullName></span></span><br /><br /> <span data-ttu-id="7274f-128"><xref:System.Linq.Queryable.GroupJoin%2A?displayProperty=fullName></xref:System.Linq.Queryable.GroupJoin%2A?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="7274f-128"><xref:System.Linq.Queryable.GroupJoin%2A?displayProperty=fullName></span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="7274f-129">另请参阅</span><span class="sxs-lookup"><span data-stu-id="7274f-129">See Also</span></span>  
 <span data-ttu-id="7274f-130"><xref:System.Linq></xref:System.Linq></span><span class="sxs-lookup"><span data-stu-id="7274f-130"><xref:System.Linq></span></span>   
<span data-ttu-id="7274f-131"> [标准查询运算符概述 (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/standard-query-operators-overview.md) </span><span class="sxs-lookup"><span data-stu-id="7274f-131"> [Standard Query Operators Overview (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/standard-query-operators-overview.md) </span></span>  
<span data-ttu-id="7274f-132"> [匿名类型](../../../../visual-basic/programming-guide/language-features/objects-and-classes/anonymous-types.md) </span><span class="sxs-lookup"><span data-stu-id="7274f-132"> [Anonymous Types](../../../../visual-basic/programming-guide/language-features/objects-and-classes/anonymous-types.md) </span></span>  
<span data-ttu-id="7274f-133"> [构建联接和叉积查询](http://msdn.microsoft.com/library/d8072ede-0521-4670-9bec-1778ceeb875b) </span><span class="sxs-lookup"><span data-stu-id="7274f-133"> [Formulate Joins and Cross-Product Queries](http://msdn.microsoft.com/library/d8072ede-0521-4670-9bec-1778ceeb875b) </span></span>  
<span data-ttu-id="7274f-134"> [Join 子句](../../../../visual-basic/language-reference/queries/join-clause.md) </span><span class="sxs-lookup"><span data-stu-id="7274f-134"> [Join Clause](../../../../visual-basic/language-reference/queries/join-clause.md) </span></span>  
<span data-ttu-id="7274f-135"> [如何︰ 联接不同文件 (LINQ) (Visual Basic 中) 的内容](../../../../visual-basic/programming-guide/concepts/linq/how-to-join-content-from-dissimilar-files-linq.md) </span><span class="sxs-lookup"><span data-stu-id="7274f-135"> [How to: Join Content from Dissimilar Files (LINQ) (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/how-to-join-content-from-dissimilar-files-linq.md) </span></span>  
<span data-ttu-id="7274f-136"> [如何︰ 从多个源 (LINQ) (Visual Basic 中) 填充对象集合](../../../../visual-basic/programming-guide/concepts/linq/how-to-populate-object-collections-from-multiple-sources-linq.md)</span><span class="sxs-lookup"><span data-stu-id="7274f-136"> [How to: Populate Object Collections from Multiple Sources (LINQ) (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/how-to-populate-object-collections-from-multiple-sources-linq.md)</span></span>
