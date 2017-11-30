---
title: "限定符操作 (Visual Basic)"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: ae1a2b73-503c-4f4b-a3fd-31b5adbee67c
caps.latest.revision: "3"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 9bc48c69179b1f8876efaa465295e94a9a0e0fb6
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="quantifier-operations-visual-basic"></a><span data-ttu-id="9931e-102">限定符操作 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="9931e-102">Quantifier Operations (Visual Basic)</span></span>
<span data-ttu-id="9931e-103">限定符运算返回一个 <xref:System.Boolean> 值，该值指示序列中是否有一些元素满足条件或是否所有元素都满足条件。</span><span class="sxs-lookup"><span data-stu-id="9931e-103">Quantifier operations return a <xref:System.Boolean> value that indicates whether some or all of the elements in a sequence satisfy a condition.</span></span>  
  
 <span data-ttu-id="9931e-104">下图描述了两个不同源序列上的两个不同限定符运算。</span><span class="sxs-lookup"><span data-stu-id="9931e-104">The following illustration depicts two different quantifier operations on two different source sequences.</span></span> <span data-ttu-id="9931e-105">第一个运算询问是否有一个或多个元素为字符“A”，结果为 `true`。</span><span class="sxs-lookup"><span data-stu-id="9931e-105">The first operation asks if one or more of the elements are the character 'A', and the result is `true`.</span></span> <span data-ttu-id="9931e-106">第二个运算询问是否所有元素都为字符“A”，结果为 `true`。</span><span class="sxs-lookup"><span data-stu-id="9931e-106">The second operation asks if all the elements are the character 'A', and the result is `true`.</span></span>  
  
 <span data-ttu-id="9931e-107">![LINQ 限定符运算](../../../../csharp/programming-guide/concepts/linq/media/linq_quantifier.png "LINQ_Quantifier")</span><span class="sxs-lookup"><span data-stu-id="9931e-107">![LINQ Quantifier Operations](../../../../csharp/programming-guide/concepts/linq/media/linq_quantifier.png "LINQ_Quantifier")</span></span>  
  
 <span data-ttu-id="9931e-108">下节列出了执行限定符运算的标准查询运算符方法。</span><span class="sxs-lookup"><span data-stu-id="9931e-108">The standard query operator methods that perform quantifier operations are listed in the following section.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="9931e-109">方法</span><span class="sxs-lookup"><span data-stu-id="9931e-109">Methods</span></span>  
  
|<span data-ttu-id="9931e-110">方法名</span><span class="sxs-lookup"><span data-stu-id="9931e-110">Method Name</span></span>|<span data-ttu-id="9931e-111">描述</span><span class="sxs-lookup"><span data-stu-id="9931e-111">Description</span></span>|<span data-ttu-id="9931e-112">Visual Basic 查询表达式语法</span><span class="sxs-lookup"><span data-stu-id="9931e-112">Visual Basic Query Expression Syntax</span></span>|<span data-ttu-id="9931e-113">详细信息</span><span class="sxs-lookup"><span data-stu-id="9931e-113">More Information</span></span>|  
|-----------------|-----------------|------------------------------------------|----------------------|  
|<span data-ttu-id="9931e-114">全部</span><span class="sxs-lookup"><span data-stu-id="9931e-114">All</span></span>|<span data-ttu-id="9931e-115">确定是否序列中的所有元素都满足条件。</span><span class="sxs-lookup"><span data-stu-id="9931e-115">Determines whether all the elements in a sequence satisfy a condition.</span></span>|`Aggregate … In … Into All(…)`|<xref:System.Linq.Enumerable.All%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.All%2A?displayProperty=nameWithType>|  
|<span data-ttu-id="9931e-116">任意</span><span class="sxs-lookup"><span data-stu-id="9931e-116">Any</span></span>|<span data-ttu-id="9931e-117">确定序列中是否有元素满足条件。</span><span class="sxs-lookup"><span data-stu-id="9931e-117">Determines whether any elements in a sequence satisfy a condition.</span></span>|`Aggregate … In … Into Any()`|<xref:System.Linq.Enumerable.Any%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.Any%2A?displayProperty=nameWithType>|  
|<span data-ttu-id="9931e-118">包含</span><span class="sxs-lookup"><span data-stu-id="9931e-118">Contains</span></span>|<span data-ttu-id="9931e-119">确定序列是否包含指定的元素。</span><span class="sxs-lookup"><span data-stu-id="9931e-119">Determines whether a sequence contains a specified element.</span></span>|<span data-ttu-id="9931e-120">不适用。</span><span class="sxs-lookup"><span data-stu-id="9931e-120">Not applicable.</span></span>|<xref:System.Linq.Enumerable.Contains%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.Contains%2A?displayProperty=nameWithType>|  
  
## <a name="query-expression-syntax-examples"></a><span data-ttu-id="9931e-121">查询表达式语法示例</span><span class="sxs-lookup"><span data-stu-id="9931e-121">Query Expression Syntax Examples</span></span>  
 <span data-ttu-id="9931e-122">这些示例使用`Aggregate`作为 LINQ 查询中的筛选条件的一部分的 Visual Basic 中的子句。</span><span class="sxs-lookup"><span data-stu-id="9931e-122">These examples use the `Aggregate` clause in Visual Basic as part of the filtering condition in a LINQ query.</span></span>  
  
 <span data-ttu-id="9931e-123">下面的示例使用`Aggregate`子句和<xref:System.Linq.Enumerable.All%2A>扩展方法以从集合中返回其宠物是所有早于指定的期限那些人。</span><span class="sxs-lookup"><span data-stu-id="9931e-123">The following example uses the `Aggregate` clause and the <xref:System.Linq.Enumerable.All%2A> extension method to return from a collection those people whose pets are all older than a specified age.</span></span>  
  
 [!code-vb[CsLINQAnyAll#1](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/quantifier-operations_1.vb)]  
  
 <span data-ttu-id="9931e-124">下一个示例使用`Aggregate`子句和<xref:System.Linq.Enumerable.Any%2A>扩展方法以从集合返回至少具有一个那些人只宠物的是早于指定的期限。</span><span class="sxs-lookup"><span data-stu-id="9931e-124">The next example uses the `Aggregate` clause and the <xref:System.Linq.Enumerable.Any%2A> extension method to return from a collection those people who have at least one pet that is older than a specified age.</span></span>  
  
 [!code-vb[CsLINQAnyAll#2](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/quantifier-operations_2.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="9931e-125">另请参阅</span><span class="sxs-lookup"><span data-stu-id="9931e-125">See Also</span></span>  
 <xref:System.Linq>  
 [<span data-ttu-id="9931e-126">标准查询运算符概述 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="9931e-126">Standard Query Operators Overview (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/standard-query-operators-overview.md)  
 [<span data-ttu-id="9931e-127">Aggregate 子句</span><span class="sxs-lookup"><span data-stu-id="9931e-127">Aggregate Clause</span></span>](../../../../visual-basic/language-reference/queries/aggregate-clause.md)  
 [<span data-ttu-id="9931e-128">如何： 查询包含一组指定的单词 (LINQ) (Visual Basic) 的句子</span><span class="sxs-lookup"><span data-stu-id="9931e-128">How to: Query for Sentences that Contain a Specified Set of Words (LINQ) (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/how-to-query-for-sentences-that-contain-a-specified-set-of-words.md)
