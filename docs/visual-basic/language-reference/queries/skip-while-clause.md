---
title: Skip While 子句 (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.QuerySkipWhile
helpviewer_keywords:
- Skip While statement [Visual Basic]
- Skip While clause [Visual Basic]
- queries [Visual Basic], Skip While
ms.assetid: 5dee8350-7520-4f1a-b00d-590cacd572d6
ms.openlocfilehash: 7da5f50a9d0fa867244a569e03685cc637bf3ce6
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54692514"
---
# <a name="skip-while-clause-visual-basic"></a><span data-ttu-id="daf40-102">Skip While 子句 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="daf40-102">Skip While Clause (Visual Basic)</span></span>
<span data-ttu-id="daf40-103">跳过集合中指定条件为 `true` 的任何元素，然后返回剩余元素。</span><span class="sxs-lookup"><span data-stu-id="daf40-103">Bypasses elements in a collection as long as a specified condition is `true` and then returns the remaining elements.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="daf40-104">语法</span><span class="sxs-lookup"><span data-stu-id="daf40-104">Syntax</span></span>  
  
```  
Skip While expression  
```  
  
## <a name="parts"></a><span data-ttu-id="daf40-105">部件</span><span class="sxs-lookup"><span data-stu-id="daf40-105">Parts</span></span>  
  
|<span data-ttu-id="daf40-106">术语</span><span class="sxs-lookup"><span data-stu-id="daf40-106">Term</span></span>|<span data-ttu-id="daf40-107">定义</span><span class="sxs-lookup"><span data-stu-id="daf40-107">Definition</span></span>|  
|---|---|  
|`expression`|<span data-ttu-id="daf40-108">必需。</span><span class="sxs-lookup"><span data-stu-id="daf40-108">Required.</span></span> <span data-ttu-id="daf40-109">一个表达式，表示要测试的元素的条件。</span><span class="sxs-lookup"><span data-stu-id="daf40-109">An expression that represents a condition to test elements for.</span></span> <span data-ttu-id="daf40-110">该表达式必须返回`Boolean`值或功能上等效，如`Integer`被视为`Boolean`。</span><span class="sxs-lookup"><span data-stu-id="daf40-110">The expression must return a `Boolean` value or a functional equivalent, such as an `Integer` to be evaluated as a `Boolean`.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="daf40-111">备注</span><span class="sxs-lookup"><span data-stu-id="daf40-111">Remarks</span></span>  
 <span data-ttu-id="daf40-112">`Skip While`子句跳过从之前所提供的查询结果开头的元素`expression`返回`false`。</span><span class="sxs-lookup"><span data-stu-id="daf40-112">The `Skip While` clause bypasses elements from the beginning of a query result until the supplied `expression` returns `false`.</span></span> <span data-ttu-id="daf40-113">之后`expression`返回`false`，该查询返回所有剩余元素。</span><span class="sxs-lookup"><span data-stu-id="daf40-113">After `expression` returns `false`, the query returns all the remaining elements.</span></span> <span data-ttu-id="daf40-114">`expression`忽略其余的结果。</span><span class="sxs-lookup"><span data-stu-id="daf40-114">The `expression` is ignored for the remaining results.</span></span>  
  
 <span data-ttu-id="daf40-115">`Skip While`子句不同于`Where`中的子句`Where`子句可用于排除不满足特定条件的查询，在所有元素。</span><span class="sxs-lookup"><span data-stu-id="daf40-115">The `Skip While` clause differs from the `Where` clause in that the `Where` clause can be used to exclude all elements from a query that do not meet a particular condition.</span></span> <span data-ttu-id="daf40-116">`Skip While`子句排除仅在未满足的条件的第一个时间前的元素。</span><span class="sxs-lookup"><span data-stu-id="daf40-116">The `Skip While` clause excludes elements only until the first time that the condition is not satisfied.</span></span> <span data-ttu-id="daf40-117">`Skip While`子句正在使用排序的查询结果时最有用。</span><span class="sxs-lookup"><span data-stu-id="daf40-117">The `Skip While` clause is most useful when you are working with an ordered query result.</span></span>  
  
 <span data-ttu-id="daf40-118">可以通过使用特定数目的结果从一开始对查询结果的绕过`Skip`子句。</span><span class="sxs-lookup"><span data-stu-id="daf40-118">You can bypass a specific number of results from the beginning of a query result by using the `Skip` clause.</span></span>  
  
## <a name="example"></a><span data-ttu-id="daf40-119">示例</span><span class="sxs-lookup"><span data-stu-id="daf40-119">Example</span></span>  
 <span data-ttu-id="daf40-120">下面的代码示例使用`Skip While`子句以跳过的结果，直到找到从美国的第一个客户。</span><span class="sxs-lookup"><span data-stu-id="daf40-120">The following code example uses the `Skip While` clause to bypass results until the first customer from the United States is found.</span></span>  
  
 [!code-vb[VbSimpleQuerySamples#3](../../../visual-basic/language-reference/queries/codesnippet/VisualBasic/skip-while-clause_1.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="daf40-121">请参阅</span><span class="sxs-lookup"><span data-stu-id="daf40-121">See also</span></span>
- [<span data-ttu-id="daf40-122">Visual Basic 中的 LINQ 简介</span><span class="sxs-lookup"><span data-stu-id="daf40-122">Introduction to LINQ in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)
- [<span data-ttu-id="daf40-123">查询</span><span class="sxs-lookup"><span data-stu-id="daf40-123">Queries</span></span>](../../../visual-basic/language-reference/queries/index.md)
- [<span data-ttu-id="daf40-124">Select 子句</span><span class="sxs-lookup"><span data-stu-id="daf40-124">Select Clause</span></span>](../../../visual-basic/language-reference/queries/select-clause.md)
- [<span data-ttu-id="daf40-125">From 子句</span><span class="sxs-lookup"><span data-stu-id="daf40-125">From Clause</span></span>](../../../visual-basic/language-reference/queries/from-clause.md)
- [<span data-ttu-id="daf40-126">Skip 子句</span><span class="sxs-lookup"><span data-stu-id="daf40-126">Skip Clause</span></span>](../../../visual-basic/language-reference/queries/skip-clause.md)
- [<span data-ttu-id="daf40-127">Take While 子句</span><span class="sxs-lookup"><span data-stu-id="daf40-127">Take While Clause</span></span>](../../../visual-basic/language-reference/queries/take-while-clause.md)
- [<span data-ttu-id="daf40-128">Where 子句</span><span class="sxs-lookup"><span data-stu-id="daf40-128">Where Clause</span></span>](../../../visual-basic/language-reference/queries/where-clause.md)
