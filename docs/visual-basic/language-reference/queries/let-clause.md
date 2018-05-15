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
ms.openlocfilehash: 6484da5329c8240735b7c35f506637dd01cbeda4
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
---
# <a name="let-clause-visual-basic"></a><span data-ttu-id="7035c-102">Let 子句 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="7035c-102">Let Clause (Visual Basic)</span></span>
<span data-ttu-id="7035c-103">计算一个值，并将其分配给查询中的新变量。</span><span class="sxs-lookup"><span data-stu-id="7035c-103">Computes a value and assigns it to a new variable within the query.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7035c-104">语法</span><span class="sxs-lookup"><span data-stu-id="7035c-104">Syntax</span></span>  
  
```  
Let variable = expression [, ...]  
```  
  
## <a name="parts"></a><span data-ttu-id="7035c-105">部件</span><span class="sxs-lookup"><span data-stu-id="7035c-105">Parts</span></span>  
  
|<span data-ttu-id="7035c-106">术语</span><span class="sxs-lookup"><span data-stu-id="7035c-106">Term</span></span>|<span data-ttu-id="7035c-107">定义</span><span class="sxs-lookup"><span data-stu-id="7035c-107">Definition</span></span>|  
|---|---|  
|`variable`|<span data-ttu-id="7035c-108">必须的。</span><span class="sxs-lookup"><span data-stu-id="7035c-108">Required.</span></span> <span data-ttu-id="7035c-109">可以用于引用提供表达式的结果的别名。</span><span class="sxs-lookup"><span data-stu-id="7035c-109">An alias that can be used to reference the results of the supplied expression.</span></span>|  
|`expression`|<span data-ttu-id="7035c-110">必须的。</span><span class="sxs-lookup"><span data-stu-id="7035c-110">Required.</span></span> <span data-ttu-id="7035c-111">一个表达式，将进行计算并分配到指定的变量。</span><span class="sxs-lookup"><span data-stu-id="7035c-111">An expression that will be evaluated and assigned to the specified variable.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="7035c-112">备注</span><span class="sxs-lookup"><span data-stu-id="7035c-112">Remarks</span></span>  
 <span data-ttu-id="7035c-113">`Let`子句可用于计算值为每个查询结果，通过使用别名引用它们。</span><span class="sxs-lookup"><span data-stu-id="7035c-113">The `Let` clause enables you to compute values for each query result and reference them by using an alias.</span></span> <span data-ttu-id="7035c-114">别名可在其他子句，如`Where`子句。</span><span class="sxs-lookup"><span data-stu-id="7035c-114">The alias can be used in other clauses, such as the `Where` clause.</span></span> <span data-ttu-id="7035c-115">`Let`子句可用于创建可以更轻松地读取，因为可以指定包含在查询表达式子句的别名，还可以用该别名替代每次使用该表达式子句的查询语句。</span><span class="sxs-lookup"><span data-stu-id="7035c-115">The `Let` clause enables you to create a query statement that is easier to read because you can specify an alias for an expression clause included in the query and substitute the alias each time the expression clause is used.</span></span>  
  
 <span data-ttu-id="7035c-116">可以包含任意数量的`variable`和`expression`中的赋值`Let`子句。</span><span class="sxs-lookup"><span data-stu-id="7035c-116">You can include any number of `variable` and `expression` assignments in the `Let` clause.</span></span> <span data-ttu-id="7035c-117">用逗号 （，） 分隔每个分配。</span><span class="sxs-lookup"><span data-stu-id="7035c-117">Separate each assignment with a comma (,).</span></span>  
  
## <a name="example"></a><span data-ttu-id="7035c-118">示例</span><span class="sxs-lookup"><span data-stu-id="7035c-118">Example</span></span>  
 <span data-ttu-id="7035c-119">下面的代码示例使用`Let`子句来计算产品 10%的折扣。</span><span class="sxs-lookup"><span data-stu-id="7035c-119">The following code example uses the `Let` clause to compute a 10 percent discount on products.</span></span>  
  
 [!code-vb[VbSimpleQuerySamples#16](../../../visual-basic/language-reference/queries/codesnippet/VisualBasic/let-clause_1.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="7035c-120">请参阅</span><span class="sxs-lookup"><span data-stu-id="7035c-120">See Also</span></span>  
 [<span data-ttu-id="7035c-121">Visual Basic 中的 LINQ 简介</span><span class="sxs-lookup"><span data-stu-id="7035c-121">Introduction to LINQ in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)  
 [<span data-ttu-id="7035c-122">查询</span><span class="sxs-lookup"><span data-stu-id="7035c-122">Queries</span></span>](../../../visual-basic/language-reference/queries/queries.md)  
 [<span data-ttu-id="7035c-123">Select 子句</span><span class="sxs-lookup"><span data-stu-id="7035c-123">Select Clause</span></span>](../../../visual-basic/language-reference/queries/select-clause.md)  
 [<span data-ttu-id="7035c-124">From 子句</span><span class="sxs-lookup"><span data-stu-id="7035c-124">From Clause</span></span>](../../../visual-basic/language-reference/queries/from-clause.md)  
 [<span data-ttu-id="7035c-125">Where 子句</span><span class="sxs-lookup"><span data-stu-id="7035c-125">Where Clause</span></span>](../../../visual-basic/language-reference/queries/where-clause.md)
