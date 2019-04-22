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
ms.openlocfilehash: 080a106fc1deeb54165511ed03d7c7c5d2060f21
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/18/2019
ms.locfileid: "58818744"
---
# <a name="take-while-clause-visual-basic"></a><span data-ttu-id="7157d-102">Take While 子句 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="7157d-102">Take While Clause (Visual Basic)</span></span>
<span data-ttu-id="7157d-103">包括集合中指定条件为 `true` 的任何元素，并绕过剩余元素。</span><span class="sxs-lookup"><span data-stu-id="7157d-103">Includes elements in a collection as long as a specified condition is `true` and bypasses the remaining elements.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7157d-104">语法</span><span class="sxs-lookup"><span data-stu-id="7157d-104">Syntax</span></span>  
  
```  
Take While expression  
```  
  
## <a name="parts"></a><span data-ttu-id="7157d-105">部件</span><span class="sxs-lookup"><span data-stu-id="7157d-105">Parts</span></span>  
  
|<span data-ttu-id="7157d-106">术语</span><span class="sxs-lookup"><span data-stu-id="7157d-106">Term</span></span>|<span data-ttu-id="7157d-107">定义</span><span class="sxs-lookup"><span data-stu-id="7157d-107">Definition</span></span>|  
|---|---|  
|`expression`|<span data-ttu-id="7157d-108">必需。</span><span class="sxs-lookup"><span data-stu-id="7157d-108">Required.</span></span> <span data-ttu-id="7157d-109">一个表达式，表示要测试的元素的条件。</span><span class="sxs-lookup"><span data-stu-id="7157d-109">An expression that represents a condition to test elements for.</span></span> <span data-ttu-id="7157d-110">该表达式必须返回`Boolean`值或功能上等效，如`Integer`被视为`Boolean`。</span><span class="sxs-lookup"><span data-stu-id="7157d-110">The expression must return a `Boolean` value or a functional equivalent, such as an `Integer` to be evaluated as a `Boolean`.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="7157d-111">备注</span><span class="sxs-lookup"><span data-stu-id="7157d-111">Remarks</span></span>  
 <span data-ttu-id="7157d-112">`Take While`子句之前提供包括查询结果的开始元素`expression`返回`false`。</span><span class="sxs-lookup"><span data-stu-id="7157d-112">The `Take While` clause includes elements from the start of a query result until the supplied `expression` returns `false`.</span></span> <span data-ttu-id="7157d-113">之后`expression`返回`false`，查询将跳过所有剩余元素。</span><span class="sxs-lookup"><span data-stu-id="7157d-113">After the `expression` returns `false`, the query will bypass all remaining elements.</span></span> <span data-ttu-id="7157d-114">`expression`忽略其余的结果。</span><span class="sxs-lookup"><span data-stu-id="7157d-114">The `expression` is ignored for the remaining results.</span></span>  
  
 <span data-ttu-id="7157d-115">`Take While`子句不同于`Where`中的子句`Where`子句可用于包括从查询满足特定条件的所有元素。</span><span class="sxs-lookup"><span data-stu-id="7157d-115">The `Take While` clause differs from the `Where` clause in that the `Where` clause can be used to include all elements from a query that meet a particular condition.</span></span> <span data-ttu-id="7157d-116">`Take While`子句仅在未满足的条件的第一个时间前包括元素。</span><span class="sxs-lookup"><span data-stu-id="7157d-116">The `Take While` clause includes elements only until the first time that the condition is not satisfied.</span></span> <span data-ttu-id="7157d-117">`Take While`子句正在使用排序的查询结果时最有用。</span><span class="sxs-lookup"><span data-stu-id="7157d-117">The `Take While` clause is most useful when you are working with an ordered query result.</span></span>  
  
## <a name="example"></a><span data-ttu-id="7157d-118">示例</span><span class="sxs-lookup"><span data-stu-id="7157d-118">Example</span></span>  
 <span data-ttu-id="7157d-119">下面的代码示例使用`Take While`子句来检索结果，直到找到第一个客户，而无需任何订单。</span><span class="sxs-lookup"><span data-stu-id="7157d-119">The following code example uses the `Take While` clause to retrieve results until the first customer without any orders is found.</span></span>  
  
 [!code-vb[VbSimpleQuerySamples#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbSimpleQuerySamples/VB/QuerySamples1.vb#2)]  
  
## <a name="see-also"></a><span data-ttu-id="7157d-120">请参阅</span><span class="sxs-lookup"><span data-stu-id="7157d-120">See also</span></span>

- [<span data-ttu-id="7157d-121">Visual Basic 中的 LINQ 简介</span><span class="sxs-lookup"><span data-stu-id="7157d-121">Introduction to LINQ in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)
- [<span data-ttu-id="7157d-122">查询</span><span class="sxs-lookup"><span data-stu-id="7157d-122">Queries</span></span>](../../../visual-basic/language-reference/queries/index.md)
- [<span data-ttu-id="7157d-123">Select 子句</span><span class="sxs-lookup"><span data-stu-id="7157d-123">Select Clause</span></span>](../../../visual-basic/language-reference/queries/select-clause.md)
- [<span data-ttu-id="7157d-124">From 子句</span><span class="sxs-lookup"><span data-stu-id="7157d-124">From Clause</span></span>](../../../visual-basic/language-reference/queries/from-clause.md)
- [<span data-ttu-id="7157d-125">Take 子句</span><span class="sxs-lookup"><span data-stu-id="7157d-125">Take Clause</span></span>](../../../visual-basic/language-reference/queries/take-clause.md)
- [<span data-ttu-id="7157d-126">Skip While 子句</span><span class="sxs-lookup"><span data-stu-id="7157d-126">Skip While Clause</span></span>](../../../visual-basic/language-reference/queries/skip-while-clause.md)
- [<span data-ttu-id="7157d-127">Where 子句</span><span class="sxs-lookup"><span data-stu-id="7157d-127">Where Clause</span></span>](../../../visual-basic/language-reference/queries/where-clause.md)
