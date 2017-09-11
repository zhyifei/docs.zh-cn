---
title: "限定符操作 (Visual Basic 中) |Microsoft 文档"
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
ms.assetid: ae1a2b73-503c-4f4b-a3fd-31b5adbee67c
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
ms.openlocfilehash: 4e0c982508640ef1ecb47d477d3e9330198474ca
ms.contentlocale: zh-cn
ms.lasthandoff: 04/12/2017

---
# <a name="quantifier-operations-visual-basic"></a><span data-ttu-id="3d1fe-102">限定符操作 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="3d1fe-102">Quantifier Operations (Visual Basic)</span></span>
<span data-ttu-id="3d1fe-103">限定符操作返回<xref:System.Boolean>值，该值指示是否在序列中元素的部分或全部都满足条件。</xref:System.Boolean></span><span class="sxs-lookup"><span data-stu-id="3d1fe-103">Quantifier operations return a <xref:System.Boolean> value that indicates whether some or all of the elements in a sequence satisfy a condition.</span></span>  
  
 <span data-ttu-id="3d1fe-104">下图描绘了对两个不同的源序列的两个不同的限定符操作。</span><span class="sxs-lookup"><span data-stu-id="3d1fe-104">The following illustration depicts two different quantifier operations on two different source sequences.</span></span> <span data-ttu-id="3d1fe-105">第一次操作询问是否有一个或多个元素都字符 A，结果是`true`。</span><span class="sxs-lookup"><span data-stu-id="3d1fe-105">The first operation asks if one or more of the elements are the character 'A', and the result is `true`.</span></span> <span data-ttu-id="3d1fe-106">第二个操作询问是否所有元素都是字符 A，则结果为`true`。</span><span class="sxs-lookup"><span data-stu-id="3d1fe-106">The second operation asks if all the elements are the character 'A', and the result is `true`.</span></span>  
  
 <span data-ttu-id="3d1fe-107">![LINQ 限定符操作](../../../../csharp/programming-guide/concepts/linq/media/linq_quantifier.png "LINQ_Quantifier")</span><span class="sxs-lookup"><span data-stu-id="3d1fe-107">![LINQ Quantifier Operations](../../../../csharp/programming-guide/concepts/linq/media/linq_quantifier.png "LINQ_Quantifier")</span></span>  
  
 <span data-ttu-id="3d1fe-108">下一节中列出执行限定符操作的标准查询运算符方法。</span><span class="sxs-lookup"><span data-stu-id="3d1fe-108">The standard query operator methods that perform quantifier operations are listed in the following section.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="3d1fe-109">方法</span><span class="sxs-lookup"><span data-stu-id="3d1fe-109">Methods</span></span>  
  
|<span data-ttu-id="3d1fe-110">方法名</span><span class="sxs-lookup"><span data-stu-id="3d1fe-110">Method Name</span></span>|<span data-ttu-id="3d1fe-111">描述</span><span class="sxs-lookup"><span data-stu-id="3d1fe-111">Description</span></span>|<span data-ttu-id="3d1fe-112">Visual Basic 查询表达式语法</span><span class="sxs-lookup"><span data-stu-id="3d1fe-112">Visual Basic Query Expression Syntax</span></span>|<span data-ttu-id="3d1fe-113">更多信息</span><span class="sxs-lookup"><span data-stu-id="3d1fe-113">More Information</span></span>|  
|-----------------|-----------------|------------------------------------------|----------------------|  
|<span data-ttu-id="3d1fe-114">全部</span><span class="sxs-lookup"><span data-stu-id="3d1fe-114">All</span></span>|<span data-ttu-id="3d1fe-115">确定是否在序列中的所有元素都满足条件。</span><span class="sxs-lookup"><span data-stu-id="3d1fe-115">Determines whether all the elements in a sequence satisfy a condition.</span></span>|`Aggregate … In … Into All(…)`|<span data-ttu-id="3d1fe-116"><xref:System.Linq.Enumerable.All%2A?displayProperty=fullName></xref:System.Linq.Enumerable.All%2A?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="3d1fe-116"><xref:System.Linq.Enumerable.All%2A?displayProperty=fullName></span></span><br /><br /> <span data-ttu-id="3d1fe-117"><xref:System.Linq.Queryable.All%2A?displayProperty=fullName></xref:System.Linq.Queryable.All%2A?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="3d1fe-117"><xref:System.Linq.Queryable.All%2A?displayProperty=fullName></span></span>|  
|<span data-ttu-id="3d1fe-118">任意</span><span class="sxs-lookup"><span data-stu-id="3d1fe-118">Any</span></span>|<span data-ttu-id="3d1fe-119">确定是否在序列中的任何元素都满足条件。</span><span class="sxs-lookup"><span data-stu-id="3d1fe-119">Determines whether any elements in a sequence satisfy a condition.</span></span>|`Aggregate … In … Into Any()`|<span data-ttu-id="3d1fe-120"><xref:System.Linq.Enumerable.Any%2A?displayProperty=fullName></xref:System.Linq.Enumerable.Any%2A?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="3d1fe-120"><xref:System.Linq.Enumerable.Any%2A?displayProperty=fullName></span></span><br /><br /> <span data-ttu-id="3d1fe-121"><xref:System.Linq.Queryable.Any%2A?displayProperty=fullName></xref:System.Linq.Queryable.Any%2A?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="3d1fe-121"><xref:System.Linq.Queryable.Any%2A?displayProperty=fullName></span></span>|  
|<span data-ttu-id="3d1fe-122">包含</span><span class="sxs-lookup"><span data-stu-id="3d1fe-122">Contains</span></span>|<span data-ttu-id="3d1fe-123">确定序列是否包含指定的元素。</span><span class="sxs-lookup"><span data-stu-id="3d1fe-123">Determines whether a sequence contains a specified element.</span></span>|<span data-ttu-id="3d1fe-124">不适用。</span><span class="sxs-lookup"><span data-stu-id="3d1fe-124">Not applicable.</span></span>|<span data-ttu-id="3d1fe-125"><xref:System.Linq.Enumerable.Contains%2A?displayProperty=fullName></xref:System.Linq.Enumerable.Contains%2A?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="3d1fe-125"><xref:System.Linq.Enumerable.Contains%2A?displayProperty=fullName></span></span><br /><br /> <span data-ttu-id="3d1fe-126"><xref:System.Linq.Queryable.Contains%2A?displayProperty=fullName></xref:System.Linq.Queryable.Contains%2A?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="3d1fe-126"><xref:System.Linq.Queryable.Contains%2A?displayProperty=fullName></span></span>|  
  
## <a name="query-expression-syntax-examples"></a><span data-ttu-id="3d1fe-127">查询表达式语法示例</span><span class="sxs-lookup"><span data-stu-id="3d1fe-127">Query Expression Syntax Examples</span></span>  
 <span data-ttu-id="3d1fe-128">这些示例使用`Aggregate`子句在 Visual Basic 中为 LINQ 查询中的筛选条件的一部分。</span><span class="sxs-lookup"><span data-stu-id="3d1fe-128">These examples use the `Aggregate` clause in Visual Basic as part of the filtering condition in a LINQ query.</span></span>  
  
 <span data-ttu-id="3d1fe-129">下面的示例使用`Aggregate`子句和<xref:System.Linq.Enumerable.All%2A>扩展方法，以从集合中返回这些人其宠物是所有早于指定的期限。</xref:System.Linq.Enumerable.All%2A></span><span class="sxs-lookup"><span data-stu-id="3d1fe-129">The following example uses the `Aggregate` clause and the <xref:System.Linq.Enumerable.All%2A> extension method to return from a collection those people whose pets are all older than a specified age.</span></span>  
  
 <span data-ttu-id="3d1fe-130">[!code-vb[CsLINQAnyAll #&1;](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/quantifier-operations_1.vb)]</span><span class="sxs-lookup"><span data-stu-id="3d1fe-130">[!code-vb[CsLINQAnyAll#1](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/quantifier-operations_1.vb)]</span></span>  
  
 <span data-ttu-id="3d1fe-131">下面的示例使用`Aggregate`子句和<xref:System.Linq.Enumerable.Any%2A>扩展方法以返回集合中至少有一个人们只宠物的是早于指定的期限。</xref:System.Linq.Enumerable.Any%2A></span><span class="sxs-lookup"><span data-stu-id="3d1fe-131">The next example uses the `Aggregate` clause and the <xref:System.Linq.Enumerable.Any%2A> extension method to return from a collection those people who have at least one pet that is older than a specified age.</span></span>  
  
 <span data-ttu-id="3d1fe-132">[!code-vb[CsLINQAnyAll #&2;](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/quantifier-operations_2.vb)]</span><span class="sxs-lookup"><span data-stu-id="3d1fe-132">[!code-vb[CsLINQAnyAll#2](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/quantifier-operations_2.vb)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3d1fe-133">另请参阅</span><span class="sxs-lookup"><span data-stu-id="3d1fe-133">See Also</span></span>  
 <span data-ttu-id="3d1fe-134"><xref:System.Linq></xref:System.Linq></span><span class="sxs-lookup"><span data-stu-id="3d1fe-134"><xref:System.Linq></span></span>   
<span data-ttu-id="3d1fe-135"> [标准查询运算符概述 (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/standard-query-operators-overview.md) </span><span class="sxs-lookup"><span data-stu-id="3d1fe-135"> [Standard Query Operators Overview (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/standard-query-operators-overview.md) </span></span>  
<span data-ttu-id="3d1fe-136"> [Aggregate 子句](../../../../visual-basic/language-reference/queries/aggregate-clause.md) </span><span class="sxs-lookup"><span data-stu-id="3d1fe-136"> [Aggregate Clause](../../../../visual-basic/language-reference/queries/aggregate-clause.md) </span></span>  
<span data-ttu-id="3d1fe-137"> [如何︰ 查询包含一组指定的字数 (LINQ) (Visual Basic 中) 的句子](../../../../visual-basic/programming-guide/concepts/linq/how-to-query-for-sentences-that-contain-a-specified-set-of-words.md)</span><span class="sxs-lookup"><span data-stu-id="3d1fe-137"> [How to: Query for Sentences that Contain a Specified Set of Words (LINQ) (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/how-to-query-for-sentences-that-contain-a-specified-set-of-words.md)</span></span>
