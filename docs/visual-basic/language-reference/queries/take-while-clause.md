---
title: Take While 子句 (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.QueryTakeWhile
helpviewer_keywords:
- queries [Visual Basic], Take While
- Take While clause [Visual Basic]
- Take While statement [Visual Basic]
ms.assetid: db8f9f2f-fc9f-4a6c-b0b8-1bf048147e11
ms.openlocfilehash: fe6ee470698504bc0434930cc9aa6de712e04254
ms.sourcegitcommit: eff6adb61852369ab690f3f047818c90580e7eb1
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/07/2019
ms.locfileid: "72004678"
---
# <a name="take-while-clause-visual-basic"></a><span data-ttu-id="70542-102">Take While 子句 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="70542-102">Take While Clause (Visual Basic)</span></span>
<span data-ttu-id="70542-103">包括集合中指定条件为 `true` 的任何元素，并绕过剩余元素。</span><span class="sxs-lookup"><span data-stu-id="70542-103">Includes elements in a collection as long as a specified condition is `true` and bypasses the remaining elements.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="70542-104">语法</span><span class="sxs-lookup"><span data-stu-id="70542-104">Syntax</span></span>  
  
```vb  
Take While expression  
```  
  
## <a name="parts"></a><span data-ttu-id="70542-105">部件</span><span class="sxs-lookup"><span data-stu-id="70542-105">Parts</span></span>  
  
|<span data-ttu-id="70542-106">术语</span><span class="sxs-lookup"><span data-stu-id="70542-106">Term</span></span>|<span data-ttu-id="70542-107">Definition</span><span class="sxs-lookup"><span data-stu-id="70542-107">Definition</span></span>|  
|---|---|  
|`expression`|<span data-ttu-id="70542-108">必需。</span><span class="sxs-lookup"><span data-stu-id="70542-108">Required.</span></span> <span data-ttu-id="70542-109">表示要为其测试元素的条件的表达式。</span><span class="sxs-lookup"><span data-stu-id="70542-109">An expression that represents a condition to test elements for.</span></span> <span data-ttu-id="70542-110">表达式必须返回 `Boolean` 值或函数等效项，例如要作为 `Boolean`计算的 `Integer`。</span><span class="sxs-lookup"><span data-stu-id="70542-110">The expression must return a `Boolean` value or a functional equivalent, such as an `Integer` to be evaluated as a `Boolean`.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="70542-111">备注</span><span class="sxs-lookup"><span data-stu-id="70542-111">Remarks</span></span>  
 <span data-ttu-id="70542-112">在提供的 `expression` 返回 `false`之前，`Take While` 子句包括从查询结果开始的元素。</span><span class="sxs-lookup"><span data-stu-id="70542-112">The `Take While` clause includes elements from the start of a query result until the supplied `expression` returns `false`.</span></span> <span data-ttu-id="70542-113">`expression` 返回 `false`后，查询将跳过所有剩余的元素。</span><span class="sxs-lookup"><span data-stu-id="70542-113">After the `expression` returns `false`, the query will bypass all remaining elements.</span></span> <span data-ttu-id="70542-114">对于剩余的结果，将忽略 `expression`。</span><span class="sxs-lookup"><span data-stu-id="70542-114">The `expression` is ignored for the remaining results.</span></span>  
  
 <span data-ttu-id="70542-115">`Take While` 子句与 `Where` 子句不同，因为 `Where` 子句可用于包括查询中满足特定条件的所有元素。</span><span class="sxs-lookup"><span data-stu-id="70542-115">The `Take While` clause differs from the `Where` clause in that the `Where` clause can be used to include all elements from a query that meet a particular condition.</span></span> <span data-ttu-id="70542-116">仅在第一次未满足条件之前，`Take While` 子句包括元素。</span><span class="sxs-lookup"><span data-stu-id="70542-116">The `Take While` clause includes elements only until the first time that the condition is not satisfied.</span></span> <span data-ttu-id="70542-117">当使用排序的查询结果时，`Take While` 子句最有用。</span><span class="sxs-lookup"><span data-stu-id="70542-117">The `Take While` clause is most useful when you are working with an ordered query result.</span></span>  
  
## <a name="example"></a><span data-ttu-id="70542-118">示例</span><span class="sxs-lookup"><span data-stu-id="70542-118">Example</span></span>  
 <span data-ttu-id="70542-119">下面的代码示例使用 `Take While` 子句来检索结果，直到找到第一个不含任何订单的客户。</span><span class="sxs-lookup"><span data-stu-id="70542-119">The following code example uses the `Take While` clause to retrieve results until the first customer without any orders is found.</span></span>  
  
 [!code-vb[VbSimpleQuerySamples#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbSimpleQuerySamples/VB/QuerySamples1.vb#2)]  
  
## <a name="see-also"></a><span data-ttu-id="70542-120">另请参阅</span><span class="sxs-lookup"><span data-stu-id="70542-120">See also</span></span>

- [<span data-ttu-id="70542-121">Visual Basic 中的 LINQ 简介</span><span class="sxs-lookup"><span data-stu-id="70542-121">Introduction to LINQ in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)
- [<span data-ttu-id="70542-122">查询</span><span class="sxs-lookup"><span data-stu-id="70542-122">Queries</span></span>](../../../visual-basic/language-reference/queries/index.md)
- [<span data-ttu-id="70542-123">Select 子句</span><span class="sxs-lookup"><span data-stu-id="70542-123">Select Clause</span></span>](../../../visual-basic/language-reference/queries/select-clause.md)
- [<span data-ttu-id="70542-124">From 子句</span><span class="sxs-lookup"><span data-stu-id="70542-124">From Clause</span></span>](../../../visual-basic/language-reference/queries/from-clause.md)
- [<span data-ttu-id="70542-125">Take 子句</span><span class="sxs-lookup"><span data-stu-id="70542-125">Take Clause</span></span>](../../../visual-basic/language-reference/queries/take-clause.md)
- [<span data-ttu-id="70542-126">Skip While 子句</span><span class="sxs-lookup"><span data-stu-id="70542-126">Skip While Clause</span></span>](../../../visual-basic/language-reference/queries/skip-while-clause.md)
- [<span data-ttu-id="70542-127">Where 子句</span><span class="sxs-lookup"><span data-stu-id="70542-127">Where Clause</span></span>](../../../visual-basic/language-reference/queries/where-clause.md)
