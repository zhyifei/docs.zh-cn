---
title: "Skip While 子句 (Visual Basic)"
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords: vb.QuerySkipWhile
helpviewer_keywords:
- Skip While statement [Visual Basic]
- Skip While clause [Visual Basic]
- queries [Visual Basic], Skip While
ms.assetid: 5dee8350-7520-4f1a-b00d-590cacd572d6
caps.latest.revision: "16"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: f447a6d9b2eb58fa546ced6c96b987caf68fb3e5
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="skip-while-clause-visual-basic"></a><span data-ttu-id="b9ed6-102">Skip While 子句 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="b9ed6-102">Skip While Clause (Visual Basic)</span></span>
<span data-ttu-id="b9ed6-103">跳过集合中指定条件为 `true` 的任何元素，然后返回剩余元素。</span><span class="sxs-lookup"><span data-stu-id="b9ed6-103">Bypasses elements in a collection as long as a specified condition is `true` and then returns the remaining elements.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b9ed6-104">语法</span><span class="sxs-lookup"><span data-stu-id="b9ed6-104">Syntax</span></span>  
  
```  
Skip While expression  
```  
  
## <a name="parts"></a><span data-ttu-id="b9ed6-105">部件</span><span class="sxs-lookup"><span data-stu-id="b9ed6-105">Parts</span></span>  
  
|<span data-ttu-id="b9ed6-106">术语</span><span class="sxs-lookup"><span data-stu-id="b9ed6-106">Term</span></span>|<span data-ttu-id="b9ed6-107">定义</span><span class="sxs-lookup"><span data-stu-id="b9ed6-107">Definition</span></span>|  
|---|---|  
|`expression`|<span data-ttu-id="b9ed6-108">必需。</span><span class="sxs-lookup"><span data-stu-id="b9ed6-108">Required.</span></span> <span data-ttu-id="b9ed6-109">一个表示要测试的元素的条件的表达式。</span><span class="sxs-lookup"><span data-stu-id="b9ed6-109">An expression that represents a condition to test elements for.</span></span> <span data-ttu-id="b9ed6-110">该表达式必须返回`Boolean`值或等效的功能，如`Integer`作为计算`Boolean`。</span><span class="sxs-lookup"><span data-stu-id="b9ed6-110">The expression must return a `Boolean` value or a functional equivalent, such as an `Integer` to be evaluated as a `Boolean`.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="b9ed6-111">备注</span><span class="sxs-lookup"><span data-stu-id="b9ed6-111">Remarks</span></span>  
 <span data-ttu-id="b9ed6-112">`Skip While`子句跳过任何元素，直到所提供的查询结果从头`expression`返回`false`。</span><span class="sxs-lookup"><span data-stu-id="b9ed6-112">The `Skip While` clause bypasses elements from the beginning of a query result until the supplied `expression` returns `false`.</span></span> <span data-ttu-id="b9ed6-113">后`expression`返回`false`，查询返回所有剩余的元素。</span><span class="sxs-lookup"><span data-stu-id="b9ed6-113">After `expression` returns `false`, the query returns all the remaining elements.</span></span> <span data-ttu-id="b9ed6-114">`expression`对于剩余的结果，将忽略。</span><span class="sxs-lookup"><span data-stu-id="b9ed6-114">The `expression` is ignored for the remaining results.</span></span>  
  
 <span data-ttu-id="b9ed6-115">`Skip While`子句不同于`Where`中的子句`Where`子句可用来从不满足特定条件的查询中排除的所有元素。</span><span class="sxs-lookup"><span data-stu-id="b9ed6-115">The `Skip While` clause differs from the `Where` clause in that the `Where` clause can be used to exclude all elements from a query that do not meet a particular condition.</span></span> <span data-ttu-id="b9ed6-116">`Skip While`子句仅在未满足的条件的第一个时间排除元素。</span><span class="sxs-lookup"><span data-stu-id="b9ed6-116">The `Skip While` clause excludes elements only until the first time that the condition is not satisfied.</span></span> <span data-ttu-id="b9ed6-117">`Skip While`子句在你正在使用排序的查询结果时最有用。</span><span class="sxs-lookup"><span data-stu-id="b9ed6-117">The `Skip While` clause is most useful when you are working with an ordered query result.</span></span>  
  
 <span data-ttu-id="b9ed6-118">可以通过使用绕过特定数目的结果从开始处的查询结果`Skip`子句。</span><span class="sxs-lookup"><span data-stu-id="b9ed6-118">You can bypass a specific number of results from the beginning of a query result by using the `Skip` clause.</span></span>  
  
## <a name="example"></a><span data-ttu-id="b9ed6-119">示例</span><span class="sxs-lookup"><span data-stu-id="b9ed6-119">Example</span></span>  
 <span data-ttu-id="b9ed6-120">下面的代码示例使用`Skip While`子句以跳过的结果，直到找到第一个客户从美国。</span><span class="sxs-lookup"><span data-stu-id="b9ed6-120">The following code example uses the `Skip While` clause to bypass results until the first customer from the United States is found.</span></span>  
  
 [!code-vb[VbSimpleQuerySamples#3](../../../visual-basic/language-reference/queries/codesnippet/VisualBasic/skip-while-clause_1.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="b9ed6-121">另请参阅</span><span class="sxs-lookup"><span data-stu-id="b9ed6-121">See Also</span></span>  
 [<span data-ttu-id="b9ed6-122">Visual Basic 中的 LINQ 简介</span><span class="sxs-lookup"><span data-stu-id="b9ed6-122">Introduction to LINQ in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)  
 [<span data-ttu-id="b9ed6-123">查询</span><span class="sxs-lookup"><span data-stu-id="b9ed6-123">Queries</span></span>](../../../visual-basic/language-reference/queries/queries.md)  
 [<span data-ttu-id="b9ed6-124">Select 子句</span><span class="sxs-lookup"><span data-stu-id="b9ed6-124">Select Clause</span></span>](../../../visual-basic/language-reference/queries/select-clause.md)  
 [<span data-ttu-id="b9ed6-125">From 子句</span><span class="sxs-lookup"><span data-stu-id="b9ed6-125">From Clause</span></span>](../../../visual-basic/language-reference/queries/from-clause.md)  
 [<span data-ttu-id="b9ed6-126">Skip 子句</span><span class="sxs-lookup"><span data-stu-id="b9ed6-126">Skip Clause</span></span>](../../../visual-basic/language-reference/queries/skip-clause.md)  
 [<span data-ttu-id="b9ed6-127">Take While 子句</span><span class="sxs-lookup"><span data-stu-id="b9ed6-127">Take While Clause</span></span>](../../../visual-basic/language-reference/queries/take-while-clause.md)  
 [<span data-ttu-id="b9ed6-128">Where 子句</span><span class="sxs-lookup"><span data-stu-id="b9ed6-128">Where Clause</span></span>](../../../visual-basic/language-reference/queries/where-clause.md)
