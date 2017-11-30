---
title: "Order By 子句 (Visual Basic)"
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords:
- vb.QueryOrderBy
- vb.QueryAscending
- vb.QueryDescending
helpviewer_keywords:
- queries [Visual Basic], Order By
- Order By clause [Visual Basic]
- Order By statement [Visual Basic]
ms.assetid: fa911282-6b81-44c7-acfa-46b5bb93df75
caps.latest.revision: "16"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 21ee21942b966668a67b14aba72b8f9fc5ee903c
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="order-by-clause-visual-basic"></a><span data-ttu-id="d6ccd-102">Order By 子句 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="d6ccd-102">Order By Clause (Visual Basic)</span></span>
<span data-ttu-id="d6ccd-103">指定查询结果的排序顺序。</span><span class="sxs-lookup"><span data-stu-id="d6ccd-103">Specifies the sort order for a query result.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d6ccd-104">语法</span><span class="sxs-lookup"><span data-stu-id="d6ccd-104">Syntax</span></span>  
  
```  
Order By orderExp1 [ Ascending | Descending ] [, orderExp2 [...] ]  
```  
  
## <a name="parts"></a><span data-ttu-id="d6ccd-105">部件</span><span class="sxs-lookup"><span data-stu-id="d6ccd-105">Parts</span></span>  
 `orderExp1`  
 <span data-ttu-id="d6ccd-106">必需。</span><span class="sxs-lookup"><span data-stu-id="d6ccd-106">Required.</span></span> <span data-ttu-id="d6ccd-107">一个或多个当前的查询结果中标识字段进行排序的返回的值的方式。</span><span class="sxs-lookup"><span data-stu-id="d6ccd-107">One or more fields from the current query result that identify how to order the returned values.</span></span> <span data-ttu-id="d6ccd-108">字段名称必须用逗号 （，） 分隔。</span><span class="sxs-lookup"><span data-stu-id="d6ccd-108">The field names must be separated by commas (,).</span></span> <span data-ttu-id="d6ccd-109">你可以标识每个字段，如按升序或降序使用`Ascending`或`Descending`关键字。</span><span class="sxs-lookup"><span data-stu-id="d6ccd-109">You can identify each field as sorted in ascending or descending order by using the `Ascending` or `Descending` keywords.</span></span> <span data-ttu-id="d6ccd-110">如果没有`Ascending`或`Descending`指定关键字，默认的排序顺序为升序。</span><span class="sxs-lookup"><span data-stu-id="d6ccd-110">If no `Ascending` or `Descending` keyword is specified, the default sort order is ascending.</span></span> <span data-ttu-id="d6ccd-111">排序顺序字段优先从左到右。</span><span class="sxs-lookup"><span data-stu-id="d6ccd-111">The sort order fields are given precedence from left to right.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="d6ccd-112">备注</span><span class="sxs-lookup"><span data-stu-id="d6ccd-112">Remarks</span></span>  
 <span data-ttu-id="d6ccd-113">你可以使用`Order By`子句的查询结果进行排序。</span><span class="sxs-lookup"><span data-stu-id="d6ccd-113">You can use the `Order By` clause to sort the results of a query.</span></span> <span data-ttu-id="d6ccd-114">`Order By`子句可以仅对结果进行排序基于当前作用域的范围变量。</span><span class="sxs-lookup"><span data-stu-id="d6ccd-114">The `Order By` clause can only sort a result based on the range variable for the current scope.</span></span> <span data-ttu-id="d6ccd-115">例如，`Select`子句引入该作用域在查询表达式中使用新的迭代变量的新作用域。</span><span class="sxs-lookup"><span data-stu-id="d6ccd-115">For example, the `Select` clause introduces a new scope in a query expression with new iteration variables for that scope.</span></span> <span data-ttu-id="d6ccd-116">之前定义的范围变量`Select`在查询中的子句之后不可`Select`子句。</span><span class="sxs-lookup"><span data-stu-id="d6ccd-116">Range variables defined before a `Select` clause in a query are not available after the `Select` clause.</span></span> <span data-ttu-id="d6ccd-117">因此，如果你想要按字段不是位于你结果进行排序`Select`子句中，你必须放置`Order By`子句之前`Select`子句。</span><span class="sxs-lookup"><span data-stu-id="d6ccd-117">Therefore, if you want to order your results by a field that is not available in the `Select` clause, you must put the `Order By` clause before the `Select` clause.</span></span> <span data-ttu-id="d6ccd-118">一个你将需要执行此操作的示例是当你想要对你通过不作为结果的一部分返回的字段的查询进行排序。</span><span class="sxs-lookup"><span data-stu-id="d6ccd-118">One example of when you would have to do this is when you want to sort your query by fields that are not returned as part of the result.</span></span>  
  
 <span data-ttu-id="d6ccd-119">升序和降序顺序字段的实现决定<xref:System.IComparable>字段的数据类型的接口。</span><span class="sxs-lookup"><span data-stu-id="d6ccd-119">Ascending and descending order for a field is determined by the implementation of the <xref:System.IComparable> interface for the data type of the field.</span></span> <span data-ttu-id="d6ccd-120">如果数据类型不实现<xref:System.IComparable>接口，排序顺序将被忽略。</span><span class="sxs-lookup"><span data-stu-id="d6ccd-120">If the data type does not implement the <xref:System.IComparable> interface, the sort order is ignored.</span></span>  
  
## <a name="example"></a><span data-ttu-id="d6ccd-121">示例</span><span class="sxs-lookup"><span data-stu-id="d6ccd-121">Example</span></span>  
 <span data-ttu-id="d6ccd-122">下面的查询表达式使用`From`子句来声明范围变量`book`为`books`集合。</span><span class="sxs-lookup"><span data-stu-id="d6ccd-122">The following query expression uses a `From` clause to declare a range variable `book` for the `books` collection.</span></span> <span data-ttu-id="d6ccd-123">`Order By`子句按价格按升序 （默认值） 对查询结果进行排序。</span><span class="sxs-lookup"><span data-stu-id="d6ccd-123">The `Order By` clause sorts the query result by price in ascending order (the default).</span></span> <span data-ttu-id="d6ccd-124">按标题以升序排序相同价格的书籍。</span><span class="sxs-lookup"><span data-stu-id="d6ccd-124">Books with the same price are sorted by title in ascending order.</span></span> <span data-ttu-id="d6ccd-125">`Select`子句选择`Title`和`Price`用作由查询返回的值的属性。</span><span class="sxs-lookup"><span data-stu-id="d6ccd-125">The `Select` clause selects the `Title` and `Price` properties as the values returned by the query.</span></span>  
  
 [!code-vb[VbSimpleQuerySamples#24](../../../visual-basic/language-reference/queries/codesnippet/VisualBasic/order-by-clause_1.vb)]  
  
## <a name="example"></a><span data-ttu-id="d6ccd-126">示例</span><span class="sxs-lookup"><span data-stu-id="d6ccd-126">Example</span></span>  
 <span data-ttu-id="d6ccd-127">下面的查询表达式使用`Order By`子句对查询结果按价格按降序进行排序。</span><span class="sxs-lookup"><span data-stu-id="d6ccd-127">The following query expression uses the `Order By` clause to sort the query result by price in descending order.</span></span> <span data-ttu-id="d6ccd-128">按标题以升序排序相同价格的书籍。</span><span class="sxs-lookup"><span data-stu-id="d6ccd-128">Books with the same price are sorted by title in ascending order.</span></span>  
  
 [!code-vb[VbSimpleQuerySamples#25](../../../visual-basic/language-reference/queries/codesnippet/VisualBasic/order-by-clause_2.vb)]  
  
## <a name="example"></a><span data-ttu-id="d6ccd-129">示例</span><span class="sxs-lookup"><span data-stu-id="d6ccd-129">Example</span></span>  
 <span data-ttu-id="d6ccd-130">下面的查询表达式使用`Select`子句来选择书名、 价格、 发布日期，和创作。</span><span class="sxs-lookup"><span data-stu-id="d6ccd-130">The following query expression uses a `Select` clause to select the book title, price, publish date, and author.</span></span> <span data-ttu-id="d6ccd-131">然后填充`Title`， `Price`， `PublishDate`，和`Author`为新作用域的范围变量的字段。</span><span class="sxs-lookup"><span data-stu-id="d6ccd-131">It then populates the `Title`, `Price`, `PublishDate`, and `Author` fields of the range variable for the new scope.</span></span> <span data-ttu-id="d6ccd-132">`Order By`子句顺序由作者姓名、 书名和价格的新范围变量。</span><span class="sxs-lookup"><span data-stu-id="d6ccd-132">The `Order By` clause orders the new range variable by author name, book title, and then price.</span></span> <span data-ttu-id="d6ccd-133">每个列进行排序 （升序） 的默认顺序。</span><span class="sxs-lookup"><span data-stu-id="d6ccd-133">Each column is sorted in the default order (ascending).</span></span>  
  
 [!code-vb[VbSimpleQuerySamples#26](../../../visual-basic/language-reference/queries/codesnippet/VisualBasic/order-by-clause_3.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="d6ccd-134">另请参阅</span><span class="sxs-lookup"><span data-stu-id="d6ccd-134">See Also</span></span>  
 [<span data-ttu-id="d6ccd-135">Visual Basic 中的 LINQ 简介</span><span class="sxs-lookup"><span data-stu-id="d6ccd-135">Introduction to LINQ in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)  
 [<span data-ttu-id="d6ccd-136">查询</span><span class="sxs-lookup"><span data-stu-id="d6ccd-136">Queries</span></span>](../../../visual-basic/language-reference/queries/queries.md)  
 [<span data-ttu-id="d6ccd-137">Select 子句</span><span class="sxs-lookup"><span data-stu-id="d6ccd-137">Select Clause</span></span>](../../../visual-basic/language-reference/queries/select-clause.md)  
 [<span data-ttu-id="d6ccd-138">From 子句</span><span class="sxs-lookup"><span data-stu-id="d6ccd-138">From Clause</span></span>](../../../visual-basic/language-reference/queries/from-clause.md)
