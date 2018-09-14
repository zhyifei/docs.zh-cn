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
ms.openlocfilehash: d4abb5f0b75ae4069c1dbe695a5c810b1f7aa6e1
ms.sourcegitcommit: 76a304c79a32aa13889ebcf4b9789a4542b48e3e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/13/2018
ms.locfileid: "45558007"
---
# <a name="order-by-clause-visual-basic"></a><span data-ttu-id="cadd5-102">Order By 子句 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="cadd5-102">Order By Clause (Visual Basic)</span></span>
<span data-ttu-id="cadd5-103">指定查询结果的排序顺序。</span><span class="sxs-lookup"><span data-stu-id="cadd5-103">Specifies the sort order for a query result.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cadd5-104">语法</span><span class="sxs-lookup"><span data-stu-id="cadd5-104">Syntax</span></span>  
  
```  
Order By orderExp1 [ Ascending | Descending ] [, orderExp2 [...] ]  
```  
  
## <a name="parts"></a><span data-ttu-id="cadd5-105">部件</span><span class="sxs-lookup"><span data-stu-id="cadd5-105">Parts</span></span>  
 `orderExp1`  
 <span data-ttu-id="cadd5-106">必须的。</span><span class="sxs-lookup"><span data-stu-id="cadd5-106">Required.</span></span> <span data-ttu-id="cadd5-107">一个或多个字段从当前的查询结果，确定如何对返回的值进行排序。</span><span class="sxs-lookup"><span data-stu-id="cadd5-107">One or more fields from the current query result that identify how to order the returned values.</span></span> <span data-ttu-id="cadd5-108">必须由逗号 （，） 分隔的字段名称。</span><span class="sxs-lookup"><span data-stu-id="cadd5-108">The field names must be separated by commas (,).</span></span> <span data-ttu-id="cadd5-109">您可以标识每个字段，为按升序或降序排序，通过使用`Ascending`或`Descending`关键字。</span><span class="sxs-lookup"><span data-stu-id="cadd5-109">You can identify each field as sorted in ascending or descending order by using the `Ascending` or `Descending` keywords.</span></span> <span data-ttu-id="cadd5-110">如果没有`Ascending`或`Descending`指定关键字时，默认的排序顺序为升序。</span><span class="sxs-lookup"><span data-stu-id="cadd5-110">If no `Ascending` or `Descending` keyword is specified, the default sort order is ascending.</span></span> <span data-ttu-id="cadd5-111">从左到右的优先顺序提供排序顺序字段。</span><span class="sxs-lookup"><span data-stu-id="cadd5-111">The sort order fields are given precedence from left to right.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="cadd5-112">备注</span><span class="sxs-lookup"><span data-stu-id="cadd5-112">Remarks</span></span>  
 <span data-ttu-id="cadd5-113">可以使用`Order By`子句的查询结果进行排序。</span><span class="sxs-lookup"><span data-stu-id="cadd5-113">You can use the `Order By` clause to sort the results of a query.</span></span> <span data-ttu-id="cadd5-114">`Order By`子句只能在排序基于当前作用域的范围变量的结果。</span><span class="sxs-lookup"><span data-stu-id="cadd5-114">The `Order By` clause can only sort a result based on the range variable for the current scope.</span></span> <span data-ttu-id="cadd5-115">例如，`Select`子句引入一个新作用域在查询表达式中使用新的迭代变量的作用域。</span><span class="sxs-lookup"><span data-stu-id="cadd5-115">For example, the `Select` clause introduces a new scope in a query expression with new iteration variables for that scope.</span></span> <span data-ttu-id="cadd5-116">之前定义的范围变量`Select`子句的查询中将不可用之后`Select`子句。</span><span class="sxs-lookup"><span data-stu-id="cadd5-116">Range variables defined before a `Select` clause in a query are not available after the `Select` clause.</span></span> <span data-ttu-id="cadd5-117">因此，如果你想要通过中不可用的字段对结果进行排序`Select`子句中，必须将放`Order By`之前的子句`Select`子句。</span><span class="sxs-lookup"><span data-stu-id="cadd5-117">Therefore, if you want to order your results by a field that is not available in the `Select` clause, you must put the `Order By` clause before the `Select` clause.</span></span> <span data-ttu-id="cadd5-118">一个需要执行此操作的示例是当你想不作为结果的一部分返回的字段的查询结果进行排序时。</span><span class="sxs-lookup"><span data-stu-id="cadd5-118">One example of when you would have to do this is when you want to sort your query by fields that are not returned as part of the result.</span></span>  
  
 <span data-ttu-id="cadd5-119">升序和降序顺序的实现决定字段<xref:System.IComparable>字段的数据类型的接口。</span><span class="sxs-lookup"><span data-stu-id="cadd5-119">Ascending and descending order for a field is determined by the implementation of the <xref:System.IComparable> interface for the data type of the field.</span></span> <span data-ttu-id="cadd5-120">如果数据类型不实现<xref:System.IComparable>接口，排序顺序将被忽略。</span><span class="sxs-lookup"><span data-stu-id="cadd5-120">If the data type does not implement the <xref:System.IComparable> interface, the sort order is ignored.</span></span>  
  
## <a name="example"></a><span data-ttu-id="cadd5-121">示例</span><span class="sxs-lookup"><span data-stu-id="cadd5-121">Example</span></span>  
 <span data-ttu-id="cadd5-122">下面的查询中使用表达式`From`子句来声明范围变量`book`为`books`集合。</span><span class="sxs-lookup"><span data-stu-id="cadd5-122">The following query expression uses a `From` clause to declare a range variable `book` for the `books` collection.</span></span> <span data-ttu-id="cadd5-123">`Order By`子句对查询结果进行排序的价格以升序 （默认值）。</span><span class="sxs-lookup"><span data-stu-id="cadd5-123">The `Order By` clause sorts the query result by price in ascending order (the default).</span></span> <span data-ttu-id="cadd5-124">按标题以升序排序书籍，其价格相同。</span><span class="sxs-lookup"><span data-stu-id="cadd5-124">Books with the same price are sorted by title in ascending order.</span></span> <span data-ttu-id="cadd5-125">`Select`子句中选择`Title`和`Price`由查询返回的值的属性。</span><span class="sxs-lookup"><span data-stu-id="cadd5-125">The `Select` clause selects the `Title` and `Price` properties as the values returned by the query.</span></span>  
  
 [!code-vb[VbSimpleQuerySamples#24](../../../visual-basic/language-reference/queries/codesnippet/VisualBasic/order-by-clause_1.vb)]  
  
## <a name="example"></a><span data-ttu-id="cadd5-126">示例</span><span class="sxs-lookup"><span data-stu-id="cadd5-126">Example</span></span>  
 <span data-ttu-id="cadd5-127">下面的查询表达式使用`Order By`子句来按价格以降序对查询结果进行排序。</span><span class="sxs-lookup"><span data-stu-id="cadd5-127">The following query expression uses the `Order By` clause to sort the query result by price in descending order.</span></span> <span data-ttu-id="cadd5-128">按标题以升序排序书籍，其价格相同。</span><span class="sxs-lookup"><span data-stu-id="cadd5-128">Books with the same price are sorted by title in ascending order.</span></span>  
  
 [!code-vb[VbSimpleQuerySamples#25](../../../visual-basic/language-reference/queries/codesnippet/VisualBasic/order-by-clause_2.vb)]  
  
## <a name="example"></a><span data-ttu-id="cadd5-129">示例</span><span class="sxs-lookup"><span data-stu-id="cadd5-129">Example</span></span>  
 <span data-ttu-id="cadd5-130">下面的查询表达式使用`Select`选择书名、 价格、 发布日期，并编写的子句。</span><span class="sxs-lookup"><span data-stu-id="cadd5-130">The following query expression uses a `Select` clause to select the book title, price, publish date, and author.</span></span> <span data-ttu-id="cadd5-131">然后填充`Title`， `Price`， `PublishDate`，和`Author`新作用域的范围变量的字段。</span><span class="sxs-lookup"><span data-stu-id="cadd5-131">It then populates the `Title`, `Price`, `PublishDate`, and `Author` fields of the range variable for the new scope.</span></span> <span data-ttu-id="cadd5-132">`Order By`子句进行排序的作者姓名、 书籍标题和价格的新范围变量。</span><span class="sxs-lookup"><span data-stu-id="cadd5-132">The `Order By` clause orders the new range variable by author name, book title, and then price.</span></span> <span data-ttu-id="cadd5-133">每个列是按默认顺序 （升序） 排序。</span><span class="sxs-lookup"><span data-stu-id="cadd5-133">Each column is sorted in the default order (ascending).</span></span>  
  
 [!code-vb[VbSimpleQuerySamples#26](../../../visual-basic/language-reference/queries/codesnippet/VisualBasic/order-by-clause_3.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="cadd5-134">请参阅</span><span class="sxs-lookup"><span data-stu-id="cadd5-134">See Also</span></span>  
 [<span data-ttu-id="cadd5-135">Visual Basic 中的 LINQ 简介</span><span class="sxs-lookup"><span data-stu-id="cadd5-135">Introduction to LINQ in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)  
 [<span data-ttu-id="cadd5-136">查询</span><span class="sxs-lookup"><span data-stu-id="cadd5-136">Queries</span></span>](../../../visual-basic/language-reference/queries/index.md)  
 [<span data-ttu-id="cadd5-137">Select 子句</span><span class="sxs-lookup"><span data-stu-id="cadd5-137">Select Clause</span></span>](../../../visual-basic/language-reference/queries/select-clause.md)  
 [<span data-ttu-id="cadd5-138">From 子句</span><span class="sxs-lookup"><span data-stu-id="cadd5-138">From Clause</span></span>](../../../visual-basic/language-reference/queries/from-clause.md)
