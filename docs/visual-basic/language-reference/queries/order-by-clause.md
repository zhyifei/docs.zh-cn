---
title: Order By 子句 (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.QueryOrderBy
- vb.QueryAscending
- vb.QueryDescending
helpviewer_keywords:
- queries [Visual Basic], Order By
- Order By clause [Visual Basic]
- Order By statement [Visual Basic]
ms.assetid: fa911282-6b81-44c7-acfa-46b5bb93df75
ms.openlocfilehash: 1c84a4cdb4a149154d459ca4d9c290ed360d1772
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/02/2019
ms.locfileid: "58835006"
---
# <a name="order-by-clause-visual-basic"></a><span data-ttu-id="d80c2-102">Order By 子句 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="d80c2-102">Order By Clause (Visual Basic)</span></span>
<span data-ttu-id="d80c2-103">指定查询结果的排序顺序。</span><span class="sxs-lookup"><span data-stu-id="d80c2-103">Specifies the sort order for a query result.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d80c2-104">语法</span><span class="sxs-lookup"><span data-stu-id="d80c2-104">Syntax</span></span>  
  
```  
Order By orderExp1 [ Ascending | Descending ] [, orderExp2 [...] ]  
```  
  
## <a name="parts"></a><span data-ttu-id="d80c2-105">部件</span><span class="sxs-lookup"><span data-stu-id="d80c2-105">Parts</span></span>  
 `orderExp1`  
 <span data-ttu-id="d80c2-106">必需。</span><span class="sxs-lookup"><span data-stu-id="d80c2-106">Required.</span></span> <span data-ttu-id="d80c2-107">一个或多个字段从当前的查询结果，确定如何对返回的值进行排序。</span><span class="sxs-lookup"><span data-stu-id="d80c2-107">One or more fields from the current query result that identify how to order the returned values.</span></span> <span data-ttu-id="d80c2-108">必须由逗号 （，） 分隔的字段名称。</span><span class="sxs-lookup"><span data-stu-id="d80c2-108">The field names must be separated by commas (,).</span></span> <span data-ttu-id="d80c2-109">您可以标识每个字段，为按升序或降序排序，通过使用`Ascending`或`Descending`关键字。</span><span class="sxs-lookup"><span data-stu-id="d80c2-109">You can identify each field as sorted in ascending or descending order by using the `Ascending` or `Descending` keywords.</span></span> <span data-ttu-id="d80c2-110">如果没有`Ascending`或`Descending`指定关键字时，默认的排序顺序为升序。</span><span class="sxs-lookup"><span data-stu-id="d80c2-110">If no `Ascending` or `Descending` keyword is specified, the default sort order is ascending.</span></span> <span data-ttu-id="d80c2-111">从左到右的优先顺序提供排序顺序字段。</span><span class="sxs-lookup"><span data-stu-id="d80c2-111">The sort order fields are given precedence from left to right.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="d80c2-112">备注</span><span class="sxs-lookup"><span data-stu-id="d80c2-112">Remarks</span></span>  
 <span data-ttu-id="d80c2-113">可以使用`Order By`子句的查询结果进行排序。</span><span class="sxs-lookup"><span data-stu-id="d80c2-113">You can use the `Order By` clause to sort the results of a query.</span></span> <span data-ttu-id="d80c2-114">`Order By`子句只能在排序基于当前作用域的范围变量的结果。</span><span class="sxs-lookup"><span data-stu-id="d80c2-114">The `Order By` clause can only sort a result based on the range variable for the current scope.</span></span> <span data-ttu-id="d80c2-115">例如，`Select`子句引入一个新作用域在查询表达式中使用新的迭代变量的作用域。</span><span class="sxs-lookup"><span data-stu-id="d80c2-115">For example, the `Select` clause introduces a new scope in a query expression with new iteration variables for that scope.</span></span> <span data-ttu-id="d80c2-116">之前定义的范围变量`Select`子句的查询中将不可用之后`Select`子句。</span><span class="sxs-lookup"><span data-stu-id="d80c2-116">Range variables defined before a `Select` clause in a query are not available after the `Select` clause.</span></span> <span data-ttu-id="d80c2-117">因此，如果你想要通过中不可用的字段对结果进行排序`Select`子句中，必须将放`Order By`之前的子句`Select`子句。</span><span class="sxs-lookup"><span data-stu-id="d80c2-117">Therefore, if you want to order your results by a field that is not available in the `Select` clause, you must put the `Order By` clause before the `Select` clause.</span></span> <span data-ttu-id="d80c2-118">一个需要执行此操作的示例是当你想不作为结果的一部分返回的字段的查询结果进行排序时。</span><span class="sxs-lookup"><span data-stu-id="d80c2-118">One example of when you would have to do this is when you want to sort your query by fields that are not returned as part of the result.</span></span>  
  
 <span data-ttu-id="d80c2-119">升序和降序顺序的实现决定字段<xref:System.IComparable>字段的数据类型的接口。</span><span class="sxs-lookup"><span data-stu-id="d80c2-119">Ascending and descending order for a field is determined by the implementation of the <xref:System.IComparable> interface for the data type of the field.</span></span> <span data-ttu-id="d80c2-120">如果数据类型不实现<xref:System.IComparable>接口，排序顺序将被忽略。</span><span class="sxs-lookup"><span data-stu-id="d80c2-120">If the data type does not implement the <xref:System.IComparable> interface, the sort order is ignored.</span></span>  
  
## <a name="example"></a><span data-ttu-id="d80c2-121">示例</span><span class="sxs-lookup"><span data-stu-id="d80c2-121">Example</span></span>  
 <span data-ttu-id="d80c2-122">下面的查询中使用表达式`From`子句来声明范围变量`book`为`books`集合。</span><span class="sxs-lookup"><span data-stu-id="d80c2-122">The following query expression uses a `From` clause to declare a range variable `book` for the `books` collection.</span></span> <span data-ttu-id="d80c2-123">`Order By`子句对查询结果进行排序的价格以升序 （默认值）。</span><span class="sxs-lookup"><span data-stu-id="d80c2-123">The `Order By` clause sorts the query result by price in ascending order (the default).</span></span> <span data-ttu-id="d80c2-124">按标题以升序排序书籍，其价格相同。</span><span class="sxs-lookup"><span data-stu-id="d80c2-124">Books with the same price are sorted by title in ascending order.</span></span> <span data-ttu-id="d80c2-125">`Select`子句中选择`Title`和`Price`由查询返回的值的属性。</span><span class="sxs-lookup"><span data-stu-id="d80c2-125">The `Select` clause selects the `Title` and `Price` properties as the values returned by the query.</span></span>  
  
 [!code-vb[VbSimpleQuerySamples#24](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbSimpleQuerySamples/VB/QuerySamples1.vb#24)]  
  
## <a name="example"></a><span data-ttu-id="d80c2-126">示例</span><span class="sxs-lookup"><span data-stu-id="d80c2-126">Example</span></span>  
 <span data-ttu-id="d80c2-127">下面的查询表达式使用`Order By`子句来按价格以降序对查询结果进行排序。</span><span class="sxs-lookup"><span data-stu-id="d80c2-127">The following query expression uses the `Order By` clause to sort the query result by price in descending order.</span></span> <span data-ttu-id="d80c2-128">按标题以升序排序书籍，其价格相同。</span><span class="sxs-lookup"><span data-stu-id="d80c2-128">Books with the same price are sorted by title in ascending order.</span></span>  
  
 [!code-vb[VbSimpleQuerySamples#25](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbSimpleQuerySamples/VB/QuerySamples1.vb#25)]  
  
## <a name="example"></a><span data-ttu-id="d80c2-129">示例</span><span class="sxs-lookup"><span data-stu-id="d80c2-129">Example</span></span>  
 <span data-ttu-id="d80c2-130">下面的查询表达式使用`Select`选择书名、 价格、 发布日期，并编写的子句。</span><span class="sxs-lookup"><span data-stu-id="d80c2-130">The following query expression uses a `Select` clause to select the book title, price, publish date, and author.</span></span> <span data-ttu-id="d80c2-131">然后填充`Title`， `Price`， `PublishDate`，和`Author`新作用域的范围变量的字段。</span><span class="sxs-lookup"><span data-stu-id="d80c2-131">It then populates the `Title`, `Price`, `PublishDate`, and `Author` fields of the range variable for the new scope.</span></span> <span data-ttu-id="d80c2-132">`Order By`子句进行排序的作者姓名、 书籍标题和价格的新范围变量。</span><span class="sxs-lookup"><span data-stu-id="d80c2-132">The `Order By` clause orders the new range variable by author name, book title, and then price.</span></span> <span data-ttu-id="d80c2-133">每个列是按默认顺序 （升序） 排序。</span><span class="sxs-lookup"><span data-stu-id="d80c2-133">Each column is sorted in the default order (ascending).</span></span>  
  
 [!code-vb[VbSimpleQuerySamples#26](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbSimpleQuerySamples/VB/QuerySamples1.vb#26)]  
  
## <a name="see-also"></a><span data-ttu-id="d80c2-134">请参阅</span><span class="sxs-lookup"><span data-stu-id="d80c2-134">See also</span></span>

- [<span data-ttu-id="d80c2-135">Visual Basic 中的 LINQ 简介</span><span class="sxs-lookup"><span data-stu-id="d80c2-135">Introduction to LINQ in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)
- [<span data-ttu-id="d80c2-136">查询</span><span class="sxs-lookup"><span data-stu-id="d80c2-136">Queries</span></span>](../../../visual-basic/language-reference/queries/index.md)
- [<span data-ttu-id="d80c2-137">Select 子句</span><span class="sxs-lookup"><span data-stu-id="d80c2-137">Select Clause</span></span>](../../../visual-basic/language-reference/queries/select-clause.md)
- [<span data-ttu-id="d80c2-138">From 子句</span><span class="sxs-lookup"><span data-stu-id="d80c2-138">From Clause</span></span>](../../../visual-basic/language-reference/queries/from-clause.md)
