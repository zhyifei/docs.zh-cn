---
title: Skip 子句 (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.QuerySkip
helpviewer_keywords:
- queries [Visual Basic], Skip
- Skip statement [Visual Basic]
- Skip clause [Visual Basic]
ms.assetid: f00eb172-3907-4c43-9745-d8546ab86234
ms.openlocfilehash: 8441e619cdbd18545be72fd701c2cc9b1cf495d9
ms.sourcegitcommit: 40364ded04fa6cdcb2b6beca7f68412e2e12f633
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/28/2019
ms.locfileid: "56971232"
---
# <a name="skip-clause-visual-basic"></a><span data-ttu-id="718b5-102">Skip 子句 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="718b5-102">Skip Clause (Visual Basic)</span></span>
<span data-ttu-id="718b5-103">绕过集合中指定数量的元素，然后返回剩余的元素。</span><span class="sxs-lookup"><span data-stu-id="718b5-103">Bypasses a specified number of elements in a collection and then returns the remaining elements.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="718b5-104">语法</span><span class="sxs-lookup"><span data-stu-id="718b5-104">Syntax</span></span>  
  
```  
Skip count  
```  
  
## <a name="parts"></a><span data-ttu-id="718b5-105">部件</span><span class="sxs-lookup"><span data-stu-id="718b5-105">Parts</span></span>  
 `count`  
 <span data-ttu-id="718b5-106">必需。</span><span class="sxs-lookup"><span data-stu-id="718b5-106">Required.</span></span> <span data-ttu-id="718b5-107">一个值或表达式的计算结果为要跳过序列中的元素数。</span><span class="sxs-lookup"><span data-stu-id="718b5-107">A value or an expression that evaluates to the number of elements of the sequence to skip.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="718b5-108">备注</span><span class="sxs-lookup"><span data-stu-id="718b5-108">Remarks</span></span>  
 <span data-ttu-id="718b5-109">`Skip`子句会使查询以绕过在结果列表的开始处的元素并返回剩余元素。</span><span class="sxs-lookup"><span data-stu-id="718b5-109">The `Skip` clause causes a query to bypass elements at the beginning of a results list and return the remaining elements.</span></span> <span data-ttu-id="718b5-110">要跳过的元素数由`count`参数。</span><span class="sxs-lookup"><span data-stu-id="718b5-110">The number of elements to skip is identified by the `count` parameter.</span></span>  
  
 <span data-ttu-id="718b5-111">可以使用`Skip`子句与`Take`子句从查询的任何段返回一系列数据。</span><span class="sxs-lookup"><span data-stu-id="718b5-111">You can use the `Skip` clause with the `Take` clause to return a range of data from any segment of a query.</span></span> <span data-ttu-id="718b5-112">若要执行此操作，将传递到范围内的第一个元素的索引`Skip`子句和范围的大小`Take`子句。</span><span class="sxs-lookup"><span data-stu-id="718b5-112">To do this, pass the index of the first element of the range to the `Skip` clause and the size of the range to the `Take` clause.</span></span>  
  
 <span data-ttu-id="718b5-113">当你使用`Skip`查询中的子句，您可能还需要确保将启用的顺序返回结果`Skip`子句，以绕过预期的结果。</span><span class="sxs-lookup"><span data-stu-id="718b5-113">When you use the `Skip` clause in a query, you may also need to ensure that the results are returned in an order that will enable the `Skip` clause to bypass the intended results.</span></span> <span data-ttu-id="718b5-114">对查询结果进行排序的详细信息，请参阅[Order By 子句](../../../visual-basic/language-reference/queries/order-by-clause.md)。</span><span class="sxs-lookup"><span data-stu-id="718b5-114">For more information about ordering query results, see [Order By Clause](../../../visual-basic/language-reference/queries/order-by-clause.md).</span></span>  
  
 <span data-ttu-id="718b5-115">可以使用`SkipWhile`子句来指定只有某些元素将忽略，具体取决于提供的条件。</span><span class="sxs-lookup"><span data-stu-id="718b5-115">You can use the `SkipWhile` clause to specify that only certain elements are ignored, depending on a supplied condition.</span></span>  
  
## <a name="example"></a><span data-ttu-id="718b5-116">示例</span><span class="sxs-lookup"><span data-stu-id="718b5-116">Example</span></span>  
 <span data-ttu-id="718b5-117">下面的代码示例使用`Skip`子句一起使用`Take`子句，以从页中的查询返回的数据。</span><span class="sxs-lookup"><span data-stu-id="718b5-117">The following code example uses the `Skip` clause together with the `Take` clause to return data from a query in pages.</span></span> <span data-ttu-id="718b5-118">`GetCustomers`函数使用`Skip`子句，以跳过列表中的客户，直到提供的起始索引值，并使用`Take`子句返回的客户从该索引值开始页。</span><span class="sxs-lookup"><span data-stu-id="718b5-118">The `GetCustomers` function uses the `Skip` clause to bypass the customers in the list until the supplied starting index value, and uses the `Take` clause to return a page of customers starting from that index value.</span></span>  
  
 [!code-vb[VbSimpleQuerySamples#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbSimpleQuerySamples/VB/QuerySamples1.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="718b5-119">请参阅</span><span class="sxs-lookup"><span data-stu-id="718b5-119">See also</span></span>
- [<span data-ttu-id="718b5-120">Visual Basic 中的 LINQ 简介</span><span class="sxs-lookup"><span data-stu-id="718b5-120">Introduction to LINQ in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)
- [<span data-ttu-id="718b5-121">查询</span><span class="sxs-lookup"><span data-stu-id="718b5-121">Queries</span></span>](../../../visual-basic/language-reference/queries/index.md)
- [<span data-ttu-id="718b5-122">Select 子句</span><span class="sxs-lookup"><span data-stu-id="718b5-122">Select Clause</span></span>](../../../visual-basic/language-reference/queries/select-clause.md)
- [<span data-ttu-id="718b5-123">From 子句</span><span class="sxs-lookup"><span data-stu-id="718b5-123">From Clause</span></span>](../../../visual-basic/language-reference/queries/from-clause.md)
- [<span data-ttu-id="718b5-124">Order By 子句</span><span class="sxs-lookup"><span data-stu-id="718b5-124">Order By Clause</span></span>](../../../visual-basic/language-reference/queries/order-by-clause.md)
- [<span data-ttu-id="718b5-125">Skip While 子句</span><span class="sxs-lookup"><span data-stu-id="718b5-125">Skip While Clause</span></span>](../../../visual-basic/language-reference/queries/skip-while-clause.md)
- [<span data-ttu-id="718b5-126">Take 子句</span><span class="sxs-lookup"><span data-stu-id="718b5-126">Take Clause</span></span>](../../../visual-basic/language-reference/queries/take-clause.md)
