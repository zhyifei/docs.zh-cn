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
ms.openlocfilehash: 7f37a6fa1c9ba7fdf7978ac6853e4c2985bf72e7
ms.sourcegitcommit: eff6adb61852369ab690f3f047818c90580e7eb1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/07/2019
ms.locfileid: "72004707"
---
# <a name="skip-while-clause-visual-basic"></a><span data-ttu-id="c587f-102">Skip While 子句 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="c587f-102">Skip While Clause (Visual Basic)</span></span>
<span data-ttu-id="c587f-103">跳过集合中指定条件为 `true` 的任何元素，然后返回剩余元素。</span><span class="sxs-lookup"><span data-stu-id="c587f-103">Bypasses elements in a collection as long as a specified condition is `true` and then returns the remaining elements.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c587f-104">语法</span><span class="sxs-lookup"><span data-stu-id="c587f-104">Syntax</span></span>  
  
```vb  
Skip While expression  
```  
  
## <a name="parts"></a><span data-ttu-id="c587f-105">部件</span><span class="sxs-lookup"><span data-stu-id="c587f-105">Parts</span></span>  
  
|<span data-ttu-id="c587f-106">术语</span><span class="sxs-lookup"><span data-stu-id="c587f-106">Term</span></span>|<span data-ttu-id="c587f-107">定义</span><span class="sxs-lookup"><span data-stu-id="c587f-107">Definition</span></span>|  
|---|---|  
|`expression`|<span data-ttu-id="c587f-108">必需。</span><span class="sxs-lookup"><span data-stu-id="c587f-108">Required.</span></span> <span data-ttu-id="c587f-109">表示要为其测试元素的条件的表达式。</span><span class="sxs-lookup"><span data-stu-id="c587f-109">An expression that represents a condition to test elements for.</span></span> <span data-ttu-id="c587f-110">表达式必须返回 @no__t 0 值或函数等效项，例如，要将 `Integer` 计算为 `Boolean`。</span><span class="sxs-lookup"><span data-stu-id="c587f-110">The expression must return a `Boolean` value or a functional equivalent, such as an `Integer` to be evaluated as a `Boolean`.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="c587f-111">备注</span><span class="sxs-lookup"><span data-stu-id="c587f-111">Remarks</span></span>  
 <span data-ttu-id="c587f-112">@No__t-0 子句会绕过查询结果开头的元素，直到提供的 @no__t 返回 `false`。</span><span class="sxs-lookup"><span data-stu-id="c587f-112">The `Skip While` clause bypasses elements from the beginning of a query result until the supplied `expression` returns `false`.</span></span> <span data-ttu-id="c587f-113">@No__t 返回 `false` 后，查询将返回所有剩余元素。</span><span class="sxs-lookup"><span data-stu-id="c587f-113">After `expression` returns `false`, the query returns all the remaining elements.</span></span> <span data-ttu-id="c587f-114">对于剩余的结果，将忽略 `expression`。</span><span class="sxs-lookup"><span data-stu-id="c587f-114">The `expression` is ignored for the remaining results.</span></span>  
  
 <span data-ttu-id="c587f-115">@No__t-0 子句与 @no__t 子句不同，因为 `Where` 子句可用于从查询中排除不满足特定条件的所有元素。</span><span class="sxs-lookup"><span data-stu-id="c587f-115">The `Skip While` clause differs from the `Where` clause in that the `Where` clause can be used to exclude all elements from a query that do not meet a particular condition.</span></span> <span data-ttu-id="c587f-116">@No__t-0 子句仅排除元素，直到第一次未满足条件。</span><span class="sxs-lookup"><span data-stu-id="c587f-116">The `Skip While` clause excludes elements only until the first time that the condition is not satisfied.</span></span> <span data-ttu-id="c587f-117">当使用排序的查询结果时，`Skip While` 子句最有用。</span><span class="sxs-lookup"><span data-stu-id="c587f-117">The `Skip While` clause is most useful when you are working with an ordered query result.</span></span>  
  
 <span data-ttu-id="c587f-118">您可以通过使用 `Skip` 子句，绕过查询结果开头的特定数目的结果。</span><span class="sxs-lookup"><span data-stu-id="c587f-118">You can bypass a specific number of results from the beginning of a query result by using the `Skip` clause.</span></span>  
  
## <a name="example"></a><span data-ttu-id="c587f-119">示例</span><span class="sxs-lookup"><span data-stu-id="c587f-119">Example</span></span>  
 <span data-ttu-id="c587f-120">下面的代码示例使用 `Skip While` 子句来绕过美国中的第一个客户。</span><span class="sxs-lookup"><span data-stu-id="c587f-120">The following code example uses the `Skip While` clause to bypass results until the first customer from the United States is found.</span></span>  
  
 [!code-vb[VbSimpleQuerySamples#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbSimpleQuerySamples/VB/QuerySamples1.vb#3)]  
  
## <a name="see-also"></a><span data-ttu-id="c587f-121">请参阅</span><span class="sxs-lookup"><span data-stu-id="c587f-121">See also</span></span>

- [<span data-ttu-id="c587f-122">Visual Basic 中的 LINQ 简介</span><span class="sxs-lookup"><span data-stu-id="c587f-122">Introduction to LINQ in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)
- [<span data-ttu-id="c587f-123">查询</span><span class="sxs-lookup"><span data-stu-id="c587f-123">Queries</span></span>](../../../visual-basic/language-reference/queries/index.md)
- [<span data-ttu-id="c587f-124">Select 子句</span><span class="sxs-lookup"><span data-stu-id="c587f-124">Select Clause</span></span>](../../../visual-basic/language-reference/queries/select-clause.md)
- [<span data-ttu-id="c587f-125">From 子句</span><span class="sxs-lookup"><span data-stu-id="c587f-125">From Clause</span></span>](../../../visual-basic/language-reference/queries/from-clause.md)
- [<span data-ttu-id="c587f-126">Skip 子句</span><span class="sxs-lookup"><span data-stu-id="c587f-126">Skip Clause</span></span>](../../../visual-basic/language-reference/queries/skip-clause.md)
- [<span data-ttu-id="c587f-127">Take While 子句</span><span class="sxs-lookup"><span data-stu-id="c587f-127">Take While Clause</span></span>](../../../visual-basic/language-reference/queries/take-while-clause.md)
- [<span data-ttu-id="c587f-128">Where 子句</span><span class="sxs-lookup"><span data-stu-id="c587f-128">Where Clause</span></span>](../../../visual-basic/language-reference/queries/where-clause.md)
