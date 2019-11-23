---
title: Let 子句 (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.QueryLet
helpviewer_keywords:
- queries [Visual Basic], Let
- Let clause [Visual Basic]
- Let statement [Visual Basic]
ms.assetid: 981aa516-16eb-4c53-b1f1-5aa3e82f316e
ms.openlocfilehash: 88166a040823cfefe623f672e556c364d652a7fc
ms.sourcegitcommit: eff6adb61852369ab690f3f047818c90580e7eb1
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/07/2019
ms.locfileid: "72004725"
---
# <a name="let-clause-visual-basic"></a><span data-ttu-id="2584c-102">Let 子句 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="2584c-102">Let Clause (Visual Basic)</span></span>
<span data-ttu-id="2584c-103">计算值并将其分配给查询中的新变量。</span><span class="sxs-lookup"><span data-stu-id="2584c-103">Computes a value and assigns it to a new variable within the query.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2584c-104">语法</span><span class="sxs-lookup"><span data-stu-id="2584c-104">Syntax</span></span>  
  
```vb  
Let variable = expression [, ...]  
```  
  
## <a name="parts"></a><span data-ttu-id="2584c-105">部件</span><span class="sxs-lookup"><span data-stu-id="2584c-105">Parts</span></span>  
  
|<span data-ttu-id="2584c-106">术语</span><span class="sxs-lookup"><span data-stu-id="2584c-106">Term</span></span>|<span data-ttu-id="2584c-107">Definition</span><span class="sxs-lookup"><span data-stu-id="2584c-107">Definition</span></span>|  
|---|---|  
|`variable`|<span data-ttu-id="2584c-108">必需。</span><span class="sxs-lookup"><span data-stu-id="2584c-108">Required.</span></span> <span data-ttu-id="2584c-109">可用于引用所提供表达式的结果的别名。</span><span class="sxs-lookup"><span data-stu-id="2584c-109">An alias that can be used to reference the results of the supplied expression.</span></span>|  
|`expression`|<span data-ttu-id="2584c-110">必需。</span><span class="sxs-lookup"><span data-stu-id="2584c-110">Required.</span></span> <span data-ttu-id="2584c-111">将进行计算并分配给指定变量的表达式。</span><span class="sxs-lookup"><span data-stu-id="2584c-111">An expression that will be evaluated and assigned to the specified variable.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="2584c-112">备注</span><span class="sxs-lookup"><span data-stu-id="2584c-112">Remarks</span></span>  
 <span data-ttu-id="2584c-113">使用 `Let` 子句可以计算每个查询结果的值，并使用别名引用这些值。</span><span class="sxs-lookup"><span data-stu-id="2584c-113">The `Let` clause enables you to compute values for each query result and reference them by using an alias.</span></span> <span data-ttu-id="2584c-114">别名可用于其他子句，如 `Where` 子句。</span><span class="sxs-lookup"><span data-stu-id="2584c-114">The alias can be used in other clauses, such as the `Where` clause.</span></span> <span data-ttu-id="2584c-115">使用 `Let` 子句可以创建更易于阅读的查询语句，因为您可以为查询中包含的 expression 子句指定一个别名，并在每次使用 expression 子句时替换该别名。</span><span class="sxs-lookup"><span data-stu-id="2584c-115">The `Let` clause enables you to create a query statement that is easier to read because you can specify an alias for an expression clause included in the query and substitute the alias each time the expression clause is used.</span></span>  
  
 <span data-ttu-id="2584c-116">可在 `Let` 子句中包含任意数量的 `variable` 和 `expression` 分配。</span><span class="sxs-lookup"><span data-stu-id="2584c-116">You can include any number of `variable` and `expression` assignments in the `Let` clause.</span></span> <span data-ttu-id="2584c-117">使用逗号（，）分隔每个赋值。</span><span class="sxs-lookup"><span data-stu-id="2584c-117">Separate each assignment with a comma (,).</span></span>  
  
## <a name="example"></a><span data-ttu-id="2584c-118">示例</span><span class="sxs-lookup"><span data-stu-id="2584c-118">Example</span></span>  
 <span data-ttu-id="2584c-119">下面的代码示例使用 `Let` 子句来计算产品10% 的折扣。</span><span class="sxs-lookup"><span data-stu-id="2584c-119">The following code example uses the `Let` clause to compute a 10 percent discount on products.</span></span>  
  
 [!code-vb[VbSimpleQuerySamples#16](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbSimpleQuerySamples/VB/QuerySamples1.vb#16)]  
  
## <a name="see-also"></a><span data-ttu-id="2584c-120">另请参阅</span><span class="sxs-lookup"><span data-stu-id="2584c-120">See also</span></span>

- [<span data-ttu-id="2584c-121">Visual Basic 中的 LINQ 简介</span><span class="sxs-lookup"><span data-stu-id="2584c-121">Introduction to LINQ in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)
- [<span data-ttu-id="2584c-122">查询</span><span class="sxs-lookup"><span data-stu-id="2584c-122">Queries</span></span>](../../../visual-basic/language-reference/queries/index.md)
- [<span data-ttu-id="2584c-123">Select 子句</span><span class="sxs-lookup"><span data-stu-id="2584c-123">Select Clause</span></span>](../../../visual-basic/language-reference/queries/select-clause.md)
- [<span data-ttu-id="2584c-124">From 子句</span><span class="sxs-lookup"><span data-stu-id="2584c-124">From Clause</span></span>](../../../visual-basic/language-reference/queries/from-clause.md)
- [<span data-ttu-id="2584c-125">Where 子句</span><span class="sxs-lookup"><span data-stu-id="2584c-125">Where Clause</span></span>](../../../visual-basic/language-reference/queries/where-clause.md)
