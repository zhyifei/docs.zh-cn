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
ms.openlocfilehash: 2705b61f4ebc839a9db98f037f303b4df78bbe5f
ms.sourcegitcommit: 40364ded04fa6cdcb2b6beca7f68412e2e12f633
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/28/2019
ms.locfileid: "56976208"
---
# <a name="take-clause-visual-basic"></a><span data-ttu-id="79ac7-102">Take 子句 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="79ac7-102">Take Clause (Visual Basic)</span></span>
<span data-ttu-id="79ac7-103">从集合的开头返回指定数量的连续元素。</span><span class="sxs-lookup"><span data-stu-id="79ac7-103">Returns a specified number of contiguous elements from the start of a collection.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="79ac7-104">语法</span><span class="sxs-lookup"><span data-stu-id="79ac7-104">Syntax</span></span>  
  
```  
Take count  
```  
  
## <a name="parts"></a><span data-ttu-id="79ac7-105">部件</span><span class="sxs-lookup"><span data-stu-id="79ac7-105">Parts</span></span>  
 `count`  
 <span data-ttu-id="79ac7-106">必需。</span><span class="sxs-lookup"><span data-stu-id="79ac7-106">Required.</span></span> <span data-ttu-id="79ac7-107">一个值或表达式的计算结果为要返回的序列的元素数量。</span><span class="sxs-lookup"><span data-stu-id="79ac7-107">A value or an expression that evaluates to the number of elements of the sequence to return.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="79ac7-108">备注</span><span class="sxs-lookup"><span data-stu-id="79ac7-108">Remarks</span></span>  
 <span data-ttu-id="79ac7-109">`Take`子句会使查询，以便包括指定的数量的结果列表的开始的连续元素。</span><span class="sxs-lookup"><span data-stu-id="79ac7-109">The `Take` clause causes a query to include a specified number of contiguous elements from the start of a results list.</span></span> <span data-ttu-id="79ac7-110">指定要包括的元素数`count`参数。</span><span class="sxs-lookup"><span data-stu-id="79ac7-110">The number of elements to include is specified by the `count` parameter.</span></span>  
  
 <span data-ttu-id="79ac7-111">可以使用`Take`子句与`Skip`子句从查询的任何段返回一系列数据。</span><span class="sxs-lookup"><span data-stu-id="79ac7-111">You can use the `Take` clause with the `Skip` clause to return a range of data from any segment of a query.</span></span> <span data-ttu-id="79ac7-112">若要执行此操作，将传递到范围内的第一个元素的索引`Skip`子句和范围的大小`Take`子句。</span><span class="sxs-lookup"><span data-stu-id="79ac7-112">To do this, pass the index of the first element of the range to the `Skip` clause and the size of the range to the `Take` clause.</span></span> <span data-ttu-id="79ac7-113">在这种情况下，`Take`子句必须指定后`Skip`子句。</span><span class="sxs-lookup"><span data-stu-id="79ac7-113">In this case, the `Take` clause must be specified after the `Skip` clause.</span></span>  
  
 <span data-ttu-id="79ac7-114">当你使用`Take`查询中的子句，您可能还需要确保将启用的顺序返回结果`Take`子句，以包括预期的结果。</span><span class="sxs-lookup"><span data-stu-id="79ac7-114">When you use the `Take` clause in a query, you may also need to ensure that the results are returned in an order that will enable the `Take` clause to include the intended results.</span></span> <span data-ttu-id="79ac7-115">对查询结果进行排序的详细信息，请参阅[Order By 子句](../../../visual-basic/language-reference/queries/order-by-clause.md)。</span><span class="sxs-lookup"><span data-stu-id="79ac7-115">For more information about ordering query results, see [Order By Clause](../../../visual-basic/language-reference/queries/order-by-clause.md).</span></span>  
  
 <span data-ttu-id="79ac7-116">可以使用`TakeWhile`子句来指定只有某些元素返回，具体取决于提供的条件。</span><span class="sxs-lookup"><span data-stu-id="79ac7-116">You can use the `TakeWhile` clause to specify that only certain elements be returned, depending on a supplied condition.</span></span>  
  
## <a name="example"></a><span data-ttu-id="79ac7-117">示例</span><span class="sxs-lookup"><span data-stu-id="79ac7-117">Example</span></span>  
 <span data-ttu-id="79ac7-118">下面的代码示例使用`Take`子句一起使用`Skip`子句，以从页中的查询返回的数据。</span><span class="sxs-lookup"><span data-stu-id="79ac7-118">The following code example uses the `Take` clause together with the `Skip` clause to return data from a query in pages.</span></span> <span data-ttu-id="79ac7-119">GetCustomers 函数使用`Skip`子句以跳过列表中的客户，直到提供的起始索引值，并使用`Take`子句返回的客户从该索引值开始页。</span><span class="sxs-lookup"><span data-stu-id="79ac7-119">The GetCustomers function uses the `Skip` clause to bypass the customers in the list until the supplied starting index value, and uses the `Take` clause to return a page of customers starting from that index value.</span></span>  
  
 [!code-vb[VbSimpleQuerySamples#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbSimpleQuerySamples/VB/QuerySamples1.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="79ac7-120">请参阅</span><span class="sxs-lookup"><span data-stu-id="79ac7-120">See also</span></span>
- [<span data-ttu-id="79ac7-121">Visual Basic 中的 LINQ 简介</span><span class="sxs-lookup"><span data-stu-id="79ac7-121">Introduction to LINQ in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)
- [<span data-ttu-id="79ac7-122">查询</span><span class="sxs-lookup"><span data-stu-id="79ac7-122">Queries</span></span>](../../../visual-basic/language-reference/queries/index.md)
- [<span data-ttu-id="79ac7-123">Select 子句</span><span class="sxs-lookup"><span data-stu-id="79ac7-123">Select Clause</span></span>](../../../visual-basic/language-reference/queries/select-clause.md)
- [<span data-ttu-id="79ac7-124">From 子句</span><span class="sxs-lookup"><span data-stu-id="79ac7-124">From Clause</span></span>](../../../visual-basic/language-reference/queries/from-clause.md)
- [<span data-ttu-id="79ac7-125">Order By 子句</span><span class="sxs-lookup"><span data-stu-id="79ac7-125">Order By Clause</span></span>](../../../visual-basic/language-reference/queries/order-by-clause.md)
- [<span data-ttu-id="79ac7-126">Take While 子句</span><span class="sxs-lookup"><span data-stu-id="79ac7-126">Take While Clause</span></span>](../../../visual-basic/language-reference/queries/take-while-clause.md)
- [<span data-ttu-id="79ac7-127">Skip 子句</span><span class="sxs-lookup"><span data-stu-id="79ac7-127">Skip Clause</span></span>](../../../visual-basic/language-reference/queries/skip-clause.md)
