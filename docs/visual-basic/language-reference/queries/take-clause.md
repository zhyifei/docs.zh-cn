---
title: Take 子句 (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.QueryTake
helpviewer_keywords:
- Take statement [Visual Basic]
- queries [Visual Basic], Take
- Take clause [Visual Basic]
ms.assetid: 77bf87b2-1476-4456-957f-fee922fbad8c
ms.openlocfilehash: 0dddb411af1b4ee269e091c07553a94589d90b2c
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33604024"
---
# <a name="take-clause-visual-basic"></a><span data-ttu-id="b804d-102">Take 子句 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="b804d-102">Take Clause (Visual Basic)</span></span>
<span data-ttu-id="b804d-103">从集合的开头返回指定数量的连续元素。</span><span class="sxs-lookup"><span data-stu-id="b804d-103">Returns a specified number of contiguous elements from the start of a collection.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b804d-104">语法</span><span class="sxs-lookup"><span data-stu-id="b804d-104">Syntax</span></span>  
  
```  
Take count  
```  
  
## <a name="parts"></a><span data-ttu-id="b804d-105">部件</span><span class="sxs-lookup"><span data-stu-id="b804d-105">Parts</span></span>  
 `count`  
 <span data-ttu-id="b804d-106">必须的。</span><span class="sxs-lookup"><span data-stu-id="b804d-106">Required.</span></span> <span data-ttu-id="b804d-107">一个值或表达式计算结果为要返回的序列的元素的数目。</span><span class="sxs-lookup"><span data-stu-id="b804d-107">A value or an expression that evaluates to the number of elements of the sequence to return.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="b804d-108">备注</span><span class="sxs-lookup"><span data-stu-id="b804d-108">Remarks</span></span>  
 <span data-ttu-id="b804d-109">`Take`子句将使查询以包含指定的数量的结果列表的开始的连续元素。</span><span class="sxs-lookup"><span data-stu-id="b804d-109">The `Take` clause causes a query to include a specified number of contiguous elements from the start of a results list.</span></span> <span data-ttu-id="b804d-110">指定要包括的元素数`count`参数。</span><span class="sxs-lookup"><span data-stu-id="b804d-110">The number of elements to include is specified by the `count` parameter.</span></span>  
  
 <span data-ttu-id="b804d-111">你可以使用`Take`子句`Skip`子句从查询的任何段返回的数据范围。</span><span class="sxs-lookup"><span data-stu-id="b804d-111">You can use the `Take` clause with the `Skip` clause to return a range of data from any segment of a query.</span></span> <span data-ttu-id="b804d-112">若要执行此操作，将传递到范围的第一个元素的索引`Skip`子句和的范围的大小`Take`子句。</span><span class="sxs-lookup"><span data-stu-id="b804d-112">To do this, pass the index of the first element of the range to the `Skip` clause and the size of the range to the `Take` clause.</span></span> <span data-ttu-id="b804d-113">在这种情况下，`Take`子句必须指定后`Skip`子句。</span><span class="sxs-lookup"><span data-stu-id="b804d-113">In this case, the `Take` clause must be specified after the `Skip` clause.</span></span>  
  
 <span data-ttu-id="b804d-114">当你使用`Take`子句在查询中的，你可能还需要确保，将启用顺序返回的结果`Take`子句，以包括预期的结果。</span><span class="sxs-lookup"><span data-stu-id="b804d-114">When you use the `Take` clause in a query, you may also need to ensure that the results are returned in an order that will enable the `Take` clause to include the intended results.</span></span> <span data-ttu-id="b804d-115">有关对查询结果进行排序的详细信息，请参阅[Order By 子句](../../../visual-basic/language-reference/queries/order-by-clause.md)。</span><span class="sxs-lookup"><span data-stu-id="b804d-115">For more information about ordering query results, see [Order By Clause](../../../visual-basic/language-reference/queries/order-by-clause.md).</span></span>  
  
 <span data-ttu-id="b804d-116">你可以使用`TakeWhile`子句，以指定只有某些元素可返回，具体取决于提供的条件。</span><span class="sxs-lookup"><span data-stu-id="b804d-116">You can use the `TakeWhile` clause to specify that only certain elements be returned, depending on a supplied condition.</span></span>  
  
## <a name="example"></a><span data-ttu-id="b804d-117">示例</span><span class="sxs-lookup"><span data-stu-id="b804d-117">Example</span></span>  
 <span data-ttu-id="b804d-118">下面的代码示例使用`Take`连同子句`Skip`子句，以从页中的某个查询返回数据。</span><span class="sxs-lookup"><span data-stu-id="b804d-118">The following code example uses the `Take` clause together with the `Skip` clause to return data from a query in pages.</span></span> <span data-ttu-id="b804d-119">GetCustomers 函数使用`Skip`子句以跳过列表中的客户，直到提供的起始索引值，并使用`Take`子句返回客户从该索引值开始页。</span><span class="sxs-lookup"><span data-stu-id="b804d-119">The GetCustomers function uses the `Skip` clause to bypass the customers in the list until the supplied starting index value, and uses the `Take` clause to return a page of customers starting from that index value.</span></span>  
  
 [!code-vb[VbSimpleQuerySamples#1](../../../visual-basic/language-reference/queries/codesnippet/VisualBasic/take-clause_1.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="b804d-120">请参阅</span><span class="sxs-lookup"><span data-stu-id="b804d-120">See Also</span></span>  
 [<span data-ttu-id="b804d-121">Visual Basic 中的 LINQ 简介</span><span class="sxs-lookup"><span data-stu-id="b804d-121">Introduction to LINQ in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)  
 [<span data-ttu-id="b804d-122">查询</span><span class="sxs-lookup"><span data-stu-id="b804d-122">Queries</span></span>](../../../visual-basic/language-reference/queries/queries.md)  
 [<span data-ttu-id="b804d-123">Select 子句</span><span class="sxs-lookup"><span data-stu-id="b804d-123">Select Clause</span></span>](../../../visual-basic/language-reference/queries/select-clause.md)  
 [<span data-ttu-id="b804d-124">From 子句</span><span class="sxs-lookup"><span data-stu-id="b804d-124">From Clause</span></span>](../../../visual-basic/language-reference/queries/from-clause.md)  
 [<span data-ttu-id="b804d-125">Order By 子句</span><span class="sxs-lookup"><span data-stu-id="b804d-125">Order By Clause</span></span>](../../../visual-basic/language-reference/queries/order-by-clause.md)  
 [<span data-ttu-id="b804d-126">Take While 子句</span><span class="sxs-lookup"><span data-stu-id="b804d-126">Take While Clause</span></span>](../../../visual-basic/language-reference/queries/take-while-clause.md)  
 [<span data-ttu-id="b804d-127">Skip 子句</span><span class="sxs-lookup"><span data-stu-id="b804d-127">Skip Clause</span></span>](../../../visual-basic/language-reference/queries/skip-clause.md)
