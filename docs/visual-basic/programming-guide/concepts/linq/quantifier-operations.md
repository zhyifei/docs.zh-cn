---
title: 限定符操作
ms.date: 07/20/2015
ms.assetid: ae1a2b73-503c-4f4b-a3fd-31b5adbee67c
ms.openlocfilehash: f5b98ec09405ca4b8c715dc7da342e66a5d434d8
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/22/2019
ms.locfileid: "74346587"
---
# <a name="quantifier-operations-visual-basic"></a><span data-ttu-id="c6bd7-102">Quantifier Operations (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="c6bd7-102">Quantifier Operations (Visual Basic)</span></span>
<span data-ttu-id="c6bd7-103">限定符运算返回一个 <xref:System.Boolean> 值，该值指示序列中是否有一些元素满足条件或是否所有元素都满足条件。</span><span class="sxs-lookup"><span data-stu-id="c6bd7-103">Quantifier operations return a <xref:System.Boolean> value that indicates whether some or all of the elements in a sequence satisfy a condition.</span></span>  
  
 <span data-ttu-id="c6bd7-104">下图描述了两个不同源序列上的两个不同限定符运算。</span><span class="sxs-lookup"><span data-stu-id="c6bd7-104">The following illustration depicts two different quantifier operations on two different source sequences.</span></span> <span data-ttu-id="c6bd7-105">第一个运算询问是否有一个或多个元素为字符“A”，结果为 `true`。</span><span class="sxs-lookup"><span data-stu-id="c6bd7-105">The first operation asks if one or more of the elements are the character 'A', and the result is `true`.</span></span> <span data-ttu-id="c6bd7-106">第二个运算询问是否所有元素都为字符“A”，结果为 `true`。</span><span class="sxs-lookup"><span data-stu-id="c6bd7-106">The second operation asks if all the elements are the character 'A', and the result is `true`.</span></span>  
  
 ![LINQ 限定符操作](./media/quantifier-operations/linq-quantifier-operations.png)  
  
 <span data-ttu-id="c6bd7-108">下节列出了执行限定符运算的标准查询运算符方法。</span><span class="sxs-lookup"><span data-stu-id="c6bd7-108">The standard query operator methods that perform quantifier operations are listed in the following section.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="c6bd7-109">方法</span><span class="sxs-lookup"><span data-stu-id="c6bd7-109">Methods</span></span>  
  
|<span data-ttu-id="c6bd7-110">方法名</span><span class="sxs-lookup"><span data-stu-id="c6bd7-110">Method Name</span></span>|<span data-ttu-id="c6bd7-111">描述</span><span class="sxs-lookup"><span data-stu-id="c6bd7-111">Description</span></span>|<span data-ttu-id="c6bd7-112">Visual Basic Query Expression Syntax</span><span class="sxs-lookup"><span data-stu-id="c6bd7-112">Visual Basic Query Expression Syntax</span></span>|<span data-ttu-id="c6bd7-113">详细信息</span><span class="sxs-lookup"><span data-stu-id="c6bd7-113">More Information</span></span>|  
|-----------------|-----------------|------------------------------------------|----------------------|  
|<span data-ttu-id="c6bd7-114">全部</span><span class="sxs-lookup"><span data-stu-id="c6bd7-114">All</span></span>|<span data-ttu-id="c6bd7-115">确定是否序列中的所有元素都满足条件。</span><span class="sxs-lookup"><span data-stu-id="c6bd7-115">Determines whether all the elements in a sequence satisfy a condition.</span></span>|`Aggregate … In … Into All(…)`|<xref:System.Linq.Enumerable.All%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.All%2A?displayProperty=nameWithType>|  
|<span data-ttu-id="c6bd7-116">任意</span><span class="sxs-lookup"><span data-stu-id="c6bd7-116">Any</span></span>|<span data-ttu-id="c6bd7-117">确定序列中是否有元素满足条件。</span><span class="sxs-lookup"><span data-stu-id="c6bd7-117">Determines whether any elements in a sequence satisfy a condition.</span></span>|`Aggregate … In … Into Any()`|<xref:System.Linq.Enumerable.Any%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.Any%2A?displayProperty=nameWithType>|  
|<span data-ttu-id="c6bd7-118">包含</span><span class="sxs-lookup"><span data-stu-id="c6bd7-118">Contains</span></span>|<span data-ttu-id="c6bd7-119">确定序列是否包含指定的元素。</span><span class="sxs-lookup"><span data-stu-id="c6bd7-119">Determines whether a sequence contains a specified element.</span></span>|<span data-ttu-id="c6bd7-120">不适用。</span><span class="sxs-lookup"><span data-stu-id="c6bd7-120">Not applicable.</span></span>|<xref:System.Linq.Enumerable.Contains%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.Contains%2A?displayProperty=nameWithType>|  
  
## <a name="query-expression-syntax-examples"></a><span data-ttu-id="c6bd7-121">查询表达式语法示例</span><span class="sxs-lookup"><span data-stu-id="c6bd7-121">Query Expression Syntax Examples</span></span>  
 <span data-ttu-id="c6bd7-122">These examples use the `Aggregate` clause in Visual Basic as part of the filtering condition in a LINQ query.</span><span class="sxs-lookup"><span data-stu-id="c6bd7-122">These examples use the `Aggregate` clause in Visual Basic as part of the filtering condition in a LINQ query.</span></span>  
  
 <span data-ttu-id="c6bd7-123">The following example uses the `Aggregate` clause and the <xref:System.Linq.Enumerable.All%2A> extension method to return from a collection those people whose pets are all older than a specified age.</span><span class="sxs-lookup"><span data-stu-id="c6bd7-123">The following example uses the `Aggregate` clause and the <xref:System.Linq.Enumerable.All%2A> extension method to return from a collection those people whose pets are all older than a specified age.</span></span>  
  
 [!code-vb[CsLINQAnyAll#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/CsLINQAnyAll/VB/AnyAll.vb#1)]  
  
 <span data-ttu-id="c6bd7-124">The next example uses the `Aggregate` clause and the <xref:System.Linq.Enumerable.Any%2A> extension method to return from a collection those people who have at least one pet that is older than a specified age.</span><span class="sxs-lookup"><span data-stu-id="c6bd7-124">The next example uses the `Aggregate` clause and the <xref:System.Linq.Enumerable.Any%2A> extension method to return from a collection those people who have at least one pet that is older than a specified age.</span></span>  
  
 [!code-vb[CsLINQAnyAll#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/CsLINQAnyAll/VB/AnyAll.vb#2)]  
  
## <a name="see-also"></a><span data-ttu-id="c6bd7-125">请参阅</span><span class="sxs-lookup"><span data-stu-id="c6bd7-125">See also</span></span>

- <xref:System.Linq>
- [<span data-ttu-id="c6bd7-126">标准查询运算符概述 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="c6bd7-126">Standard Query Operators Overview (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/standard-query-operators-overview.md)
- [<span data-ttu-id="c6bd7-127">Aggregate 子句</span><span class="sxs-lookup"><span data-stu-id="c6bd7-127">Aggregate Clause</span></span>](../../../../visual-basic/language-reference/queries/aggregate-clause.md)
- [<span data-ttu-id="c6bd7-128">How to: Query for Sentences that Contain a Specified Set of Words (LINQ) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="c6bd7-128">How to: Query for Sentences that Contain a Specified Set of Words (LINQ) (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/how-to-query-for-sentences-that-contain-a-specified-set-of-words.md)
