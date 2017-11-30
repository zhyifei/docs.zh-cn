---
title: "Skip 子句 (Visual Basic)"
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords: vb.QuerySkip
helpviewer_keywords:
- queries [Visual Basic], Skip
- Skip statement [Visual Basic]
- Skip clause [Visual Basic]
ms.assetid: f00eb172-3907-4c43-9745-d8546ab86234
caps.latest.revision: "17"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 508f3c094df4c834305bcb4a78223c1cee82b1c8
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="skip-clause-visual-basic"></a><span data-ttu-id="764fa-102">Skip 子句 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="764fa-102">Skip Clause (Visual Basic)</span></span>
<span data-ttu-id="764fa-103">绕过集合中指定数量的元素，然后返回剩余的元素。</span><span class="sxs-lookup"><span data-stu-id="764fa-103">Bypasses a specified number of elements in a collection and then returns the remaining elements.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="764fa-104">语法</span><span class="sxs-lookup"><span data-stu-id="764fa-104">Syntax</span></span>  
  
```  
Skip count  
```  
  
## <a name="parts"></a><span data-ttu-id="764fa-105">部件</span><span class="sxs-lookup"><span data-stu-id="764fa-105">Parts</span></span>  
 `count`  
 <span data-ttu-id="764fa-106">必需。</span><span class="sxs-lookup"><span data-stu-id="764fa-106">Required.</span></span> <span data-ttu-id="764fa-107">一个值或表达式计算结果为要跳过的序列的元素的数目。</span><span class="sxs-lookup"><span data-stu-id="764fa-107">A value or an expression that evaluates to the number of elements of the sequence to skip.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="764fa-108">备注</span><span class="sxs-lookup"><span data-stu-id="764fa-108">Remarks</span></span>  
 <span data-ttu-id="764fa-109">`Skip`子句将使查询以绕过结果列表的开头处的元素，并返回剩余元素。</span><span class="sxs-lookup"><span data-stu-id="764fa-109">The `Skip` clause causes a query to bypass elements at the beginning of a results list and return the remaining elements.</span></span> <span data-ttu-id="764fa-110">要跳过的元素数由`count`参数。</span><span class="sxs-lookup"><span data-stu-id="764fa-110">The number of elements to skip is identified by the `count` parameter.</span></span>  
  
 <span data-ttu-id="764fa-111">你可以使用`Skip`子句`Take`子句从查询的任何段返回的数据范围。</span><span class="sxs-lookup"><span data-stu-id="764fa-111">You can use the `Skip` clause with the `Take` clause to return a range of data from any segment of a query.</span></span> <span data-ttu-id="764fa-112">若要执行此操作，将传递到范围的第一个元素的索引`Skip`子句和的范围的大小`Take`子句。</span><span class="sxs-lookup"><span data-stu-id="764fa-112">To do this, pass the index of the first element of the range to the `Skip` clause and the size of the range to the `Take` clause.</span></span>  
  
 <span data-ttu-id="764fa-113">当你使用`Skip`子句在查询中的，你可能还需要确保，将启用顺序返回的结果`Skip`子句，以绕过预期的结果。</span><span class="sxs-lookup"><span data-stu-id="764fa-113">When you use the `Skip` clause in a query, you may also need to ensure that the results are returned in an order that will enable the `Skip` clause to bypass the intended results.</span></span> <span data-ttu-id="764fa-114">有关对查询结果进行排序的详细信息，请参阅[Order By 子句](../../../visual-basic/language-reference/queries/order-by-clause.md)。</span><span class="sxs-lookup"><span data-stu-id="764fa-114">For more information about ordering query results, see [Order By Clause](../../../visual-basic/language-reference/queries/order-by-clause.md).</span></span>  
  
 <span data-ttu-id="764fa-115">你可以使用`SkipWhile`子句来指定，只有某些元素将被忽略，具体取决于提供的条件。</span><span class="sxs-lookup"><span data-stu-id="764fa-115">You can use the `SkipWhile` clause to specify that only certain elements are ignored, depending on a supplied condition.</span></span>  
  
## <a name="example"></a><span data-ttu-id="764fa-116">示例</span><span class="sxs-lookup"><span data-stu-id="764fa-116">Example</span></span>  
 <span data-ttu-id="764fa-117">下面的代码示例使用`Skip`连同子句`Take`子句，以从页中的某个查询返回数据。</span><span class="sxs-lookup"><span data-stu-id="764fa-117">The following code example uses the `Skip` clause together with the `Take` clause to return data from a query in pages.</span></span> <span data-ttu-id="764fa-118">`GetCustomers`函数使用`Skip`子句以跳过列表中的客户，直到提供的起始索引值，并使用`Take`子句返回客户从该索引值开始页。</span><span class="sxs-lookup"><span data-stu-id="764fa-118">The `GetCustomers` function uses the `Skip` clause to bypass the customers in the list until the supplied starting index value, and uses the `Take` clause to return a page of customers starting from that index value.</span></span>  
  
 [!code-vb[VbSimpleQuerySamples#1](../../../visual-basic/language-reference/queries/codesnippet/VisualBasic/skip-clause_1.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="764fa-119">另请参阅</span><span class="sxs-lookup"><span data-stu-id="764fa-119">See Also</span></span>  
 [<span data-ttu-id="764fa-120">Visual Basic 中的 LINQ 简介</span><span class="sxs-lookup"><span data-stu-id="764fa-120">Introduction to LINQ in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)  
 [<span data-ttu-id="764fa-121">查询</span><span class="sxs-lookup"><span data-stu-id="764fa-121">Queries</span></span>](../../../visual-basic/language-reference/queries/queries.md)  
 [<span data-ttu-id="764fa-122">Select 子句</span><span class="sxs-lookup"><span data-stu-id="764fa-122">Select Clause</span></span>](../../../visual-basic/language-reference/queries/select-clause.md)  
 [<span data-ttu-id="764fa-123">From 子句</span><span class="sxs-lookup"><span data-stu-id="764fa-123">From Clause</span></span>](../../../visual-basic/language-reference/queries/from-clause.md)  
 [<span data-ttu-id="764fa-124">Order By 子句</span><span class="sxs-lookup"><span data-stu-id="764fa-124">Order By Clause</span></span>](../../../visual-basic/language-reference/queries/order-by-clause.md)  
 [<span data-ttu-id="764fa-125">Skip While 子句</span><span class="sxs-lookup"><span data-stu-id="764fa-125">Skip While Clause</span></span>](../../../visual-basic/language-reference/queries/skip-while-clause.md)  
 [<span data-ttu-id="764fa-126">Take 子句</span><span class="sxs-lookup"><span data-stu-id="764fa-126">Take Clause</span></span>](../../../visual-basic/language-reference/queries/take-clause.md)
