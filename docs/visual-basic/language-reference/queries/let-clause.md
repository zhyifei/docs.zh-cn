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
ms.openlocfilehash: 545eefc67d52428470c19b62085fd87927505c7e
ms.sourcegitcommit: 40364ded04fa6cdcb2b6beca7f68412e2e12f633
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/28/2019
ms.locfileid: "56972698"
---
# <a name="let-clause-visual-basic"></a><span data-ttu-id="8f65e-102">Let 子句 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="8f65e-102">Let Clause (Visual Basic)</span></span>
<span data-ttu-id="8f65e-103">计算一个值，并将其分配给在查询中的新变量。</span><span class="sxs-lookup"><span data-stu-id="8f65e-103">Computes a value and assigns it to a new variable within the query.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8f65e-104">语法</span><span class="sxs-lookup"><span data-stu-id="8f65e-104">Syntax</span></span>  
  
```  
Let variable = expression [, ...]  
```  
  
## <a name="parts"></a><span data-ttu-id="8f65e-105">部件</span><span class="sxs-lookup"><span data-stu-id="8f65e-105">Parts</span></span>  
  
|<span data-ttu-id="8f65e-106">术语</span><span class="sxs-lookup"><span data-stu-id="8f65e-106">Term</span></span>|<span data-ttu-id="8f65e-107">定义</span><span class="sxs-lookup"><span data-stu-id="8f65e-107">Definition</span></span>|  
|---|---|  
|`variable`|<span data-ttu-id="8f65e-108">必需。</span><span class="sxs-lookup"><span data-stu-id="8f65e-108">Required.</span></span> <span data-ttu-id="8f65e-109">别名可用于引用提供的表达式的结果。</span><span class="sxs-lookup"><span data-stu-id="8f65e-109">An alias that can be used to reference the results of the supplied expression.</span></span>|  
|`expression`|<span data-ttu-id="8f65e-110">必需。</span><span class="sxs-lookup"><span data-stu-id="8f65e-110">Required.</span></span> <span data-ttu-id="8f65e-111">一个表达式，将计算并分配给指定的变量。</span><span class="sxs-lookup"><span data-stu-id="8f65e-111">An expression that will be evaluated and assigned to the specified variable.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="8f65e-112">备注</span><span class="sxs-lookup"><span data-stu-id="8f65e-112">Remarks</span></span>  
 <span data-ttu-id="8f65e-113">`Let`子句，可计算每个值的查询结果，可以使用别名来引用它们。</span><span class="sxs-lookup"><span data-stu-id="8f65e-113">The `Let` clause enables you to compute values for each query result and reference them by using an alias.</span></span> <span data-ttu-id="8f65e-114">别名可在其他子句，如`Where`子句。</span><span class="sxs-lookup"><span data-stu-id="8f65e-114">The alias can be used in other clauses, such as the `Where` clause.</span></span> <span data-ttu-id="8f65e-115">`Let`子句，可创建的查询语句，从而更易于进行读取，因为可以为包含在查询表达式子句指定别名，并将每次使用该表达式子句的别名。</span><span class="sxs-lookup"><span data-stu-id="8f65e-115">The `Let` clause enables you to create a query statement that is easier to read because you can specify an alias for an expression clause included in the query and substitute the alias each time the expression clause is used.</span></span>  
  
 <span data-ttu-id="8f65e-116">可以包含任意数量的`variable`并`expression`中的分配`Let`子句。</span><span class="sxs-lookup"><span data-stu-id="8f65e-116">You can include any number of `variable` and `expression` assignments in the `Let` clause.</span></span> <span data-ttu-id="8f65e-117">请用逗号 （，） 分隔每个分配。</span><span class="sxs-lookup"><span data-stu-id="8f65e-117">Separate each assignment with a comma (,).</span></span>  
  
## <a name="example"></a><span data-ttu-id="8f65e-118">示例</span><span class="sxs-lookup"><span data-stu-id="8f65e-118">Example</span></span>  
 <span data-ttu-id="8f65e-119">下面的代码示例使用`Let`子句来计算产品上有 10%的折扣。</span><span class="sxs-lookup"><span data-stu-id="8f65e-119">The following code example uses the `Let` clause to compute a 10 percent discount on products.</span></span>  
  
 [!code-vb[VbSimpleQuerySamples#16](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbSimpleQuerySamples/VB/QuerySamples1.vb#16)]  
  
## <a name="see-also"></a><span data-ttu-id="8f65e-120">请参阅</span><span class="sxs-lookup"><span data-stu-id="8f65e-120">See also</span></span>
- [<span data-ttu-id="8f65e-121">Visual Basic 中的 LINQ 简介</span><span class="sxs-lookup"><span data-stu-id="8f65e-121">Introduction to LINQ in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)
- [<span data-ttu-id="8f65e-122">查询</span><span class="sxs-lookup"><span data-stu-id="8f65e-122">Queries</span></span>](../../../visual-basic/language-reference/queries/index.md)
- [<span data-ttu-id="8f65e-123">Select 子句</span><span class="sxs-lookup"><span data-stu-id="8f65e-123">Select Clause</span></span>](../../../visual-basic/language-reference/queries/select-clause.md)
- [<span data-ttu-id="8f65e-124">From 子句</span><span class="sxs-lookup"><span data-stu-id="8f65e-124">From Clause</span></span>](../../../visual-basic/language-reference/queries/from-clause.md)
- [<span data-ttu-id="8f65e-125">Where 子句</span><span class="sxs-lookup"><span data-stu-id="8f65e-125">Where Clause</span></span>](../../../visual-basic/language-reference/queries/where-clause.md)
