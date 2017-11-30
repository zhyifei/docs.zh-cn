---
title: "Where 子句 (Visual Basic)"
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords: vb.QueryWhere
helpviewer_keywords:
- Where statement [Visual Basic]
- queries [Visual Basic], Where
- Where clause [Visual Basic]
ms.assetid: 48b5c2c5-3181-429c-8545-894296798c89
caps.latest.revision: "18"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 8c2572f513d00bc72e869cf28d382be799f7a303
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="where-clause-visual-basic"></a><span data-ttu-id="be4b3-102">Where 子句 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="be4b3-102">Where Clause (Visual Basic)</span></span>
<span data-ttu-id="be4b3-103">指定查询的筛选条件。</span><span class="sxs-lookup"><span data-stu-id="be4b3-103">Specifies the filtering condition for a query.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="be4b3-104">语法</span><span class="sxs-lookup"><span data-stu-id="be4b3-104">Syntax</span></span>  
  
```  
Where condition  
```  
  
## <a name="parts"></a><span data-ttu-id="be4b3-105">部件</span><span class="sxs-lookup"><span data-stu-id="be4b3-105">Parts</span></span>  
 `condition`  
 <span data-ttu-id="be4b3-106">必需。</span><span class="sxs-lookup"><span data-stu-id="be4b3-106">Required.</span></span> <span data-ttu-id="be4b3-107">一个表达式，确定输出集合中是否包含集合中的当前项的值。</span><span class="sxs-lookup"><span data-stu-id="be4b3-107">An expression that determines whether the values for the current item in the collection are included in the output collection.</span></span> <span data-ttu-id="be4b3-108">表达式的计算结果必须为`Boolean`值或等效于`Boolean`值。</span><span class="sxs-lookup"><span data-stu-id="be4b3-108">The expression must evaluate to a `Boolean` value or the equivalent of a `Boolean` value.</span></span> <span data-ttu-id="be4b3-109">如果条件计算结果为`True`，该元素是包含在查询结果; 否则为查询结果中排除该元素。</span><span class="sxs-lookup"><span data-stu-id="be4b3-109">If the condition evaluates to `True`, the element is included in the query result; otherwise, the element is excluded from the query result.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="be4b3-110">备注</span><span class="sxs-lookup"><span data-stu-id="be4b3-110">Remarks</span></span>  
 <span data-ttu-id="be4b3-111">`Where`子句，可以通过选择满足特定条件的元素来筛选查询数据。</span><span class="sxs-lookup"><span data-stu-id="be4b3-111">The `Where` clause enables you to filter query data by selecting only elements that meet certain criteria.</span></span> <span data-ttu-id="be4b3-112">其值会导致的元素`Where`子句计算结果为`True`包含在查询结果; 排除其他元素。</span><span class="sxs-lookup"><span data-stu-id="be4b3-112">Elements whose values cause the `Where` clause to evaluate to `True` are included in the query result; other elements are excluded.</span></span> <span data-ttu-id="be4b3-113">使用中的表达式`Where`子句的计算结果必须为`Boolean`或等效于`Boolean`，如计算结果为一个整数`False`时其值为零。</span><span class="sxs-lookup"><span data-stu-id="be4b3-113">The expression that is used in a `Where` clause must evaluate to a `Boolean` or the equivalent of a `Boolean`, such as an Integer that evaluates to `False` when its value is zero.</span></span> <span data-ttu-id="be4b3-114">你可以组合多个表达式中的`Where`子句通过使用逻辑运算符，如`And`， `Or`， `AndAlso`， `OrElse`， `Is`，和`IsNot`。</span><span class="sxs-lookup"><span data-stu-id="be4b3-114">You can combine multiple expressions in a `Where` clause by using logical operators such as `And`, `Or`, `AndAlso`, `OrElse`, `Is`, and `IsNot`.</span></span>  
  
 <span data-ttu-id="be4b3-115">默认情况下，查询无法计算的表达式直到被访问-例如，当它们进行数据绑定或中进行循环访问时`For`循环。</span><span class="sxs-lookup"><span data-stu-id="be4b3-115">By default, query expressions are not evaluated until they are accessed—for example, when they are data-bound or iterated through in a `For` loop.</span></span> <span data-ttu-id="be4b3-116">因此，`Where`访问查询之前，则不会评估子句。</span><span class="sxs-lookup"><span data-stu-id="be4b3-116">As a result, the `Where` clause is not evaluated until the query is accessed.</span></span> <span data-ttu-id="be4b3-117">如果你具有值中使用的查询外部`Where`子句中，确保适当的值在中使用`Where`子句在执行查询的时间。</span><span class="sxs-lookup"><span data-stu-id="be4b3-117">If you have values external to the query that are used in the `Where` clause, ensure that the appropriate value is used in the `Where` clause at the time the query is executed.</span></span> <span data-ttu-id="be4b3-118">有关执行查询的详细信息，请参阅[编写你的第一个 LINQ 查询](../../../visual-basic/programming-guide/concepts/linq/writing-your-first-linq-query.md)。</span><span class="sxs-lookup"><span data-stu-id="be4b3-118">For more information about query execution, see [Writing Your First LINQ Query](../../../visual-basic/programming-guide/concepts/linq/writing-your-first-linq-query.md).</span></span>  
  
 <span data-ttu-id="be4b3-119">你可以调用中的函数`Where`子句，从集合中的当前元素执行计算或上一个值的操作。</span><span class="sxs-lookup"><span data-stu-id="be4b3-119">You can call functions within a `Where` clause to perform a calculation or operation on a value from the current element in the collection.</span></span> <span data-ttu-id="be4b3-120">调用函数`Where`子句可能会导致立即时它定义而不是它访问时执行的查询。</span><span class="sxs-lookup"><span data-stu-id="be4b3-120">Calling a function in a `Where` clause can cause the query to be executed immediately when it is defined instead of when it is accessed.</span></span> <span data-ttu-id="be4b3-121">有关执行查询的详细信息，请参阅[编写你的第一个 LINQ 查询](../../../visual-basic/programming-guide/concepts/linq/writing-your-first-linq-query.md)。</span><span class="sxs-lookup"><span data-stu-id="be4b3-121">For more information about query execution, see [Writing Your First LINQ Query](../../../visual-basic/programming-guide/concepts/linq/writing-your-first-linq-query.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="be4b3-122">示例</span><span class="sxs-lookup"><span data-stu-id="be4b3-122">Example</span></span>  
 <span data-ttu-id="be4b3-123">下面的查询表达式使用`From`子句来声明范围变量`cust`每个`Customer`对象在`customers`集合。</span><span class="sxs-lookup"><span data-stu-id="be4b3-123">The following query expression uses a `From` clause to declare a range variable `cust` for each `Customer` object in the `customers` collection.</span></span> <span data-ttu-id="be4b3-124">`Where`子句使用的范围变量以将输出限制为客户，从指定的区域。</span><span class="sxs-lookup"><span data-stu-id="be4b3-124">The `Where` clause uses the range variable to restrict the output to customers from the specified region.</span></span> <span data-ttu-id="be4b3-125">`For Each`循环显示查询结果中的每个客户的公司名称。</span><span class="sxs-lookup"><span data-stu-id="be4b3-125">The `For Each` loop displays the company name for each customer in the query result.</span></span>  
  
 [!code-vb[VbSimpleQuerySamples#23](../../../visual-basic/language-reference/queries/codesnippet/VisualBasic/where-clause_1.vb)]  
  
## <a name="example"></a><span data-ttu-id="be4b3-126">示例</span><span class="sxs-lookup"><span data-stu-id="be4b3-126">Example</span></span>  
 <span data-ttu-id="be4b3-127">下面的示例使用`And`和`Or`中的逻辑运算符`Where`子句。</span><span class="sxs-lookup"><span data-stu-id="be4b3-127">The following example uses `And` and `Or` logical operators in the `Where` clause.</span></span>  
  
 [!code-vb[VbSimpleQuerySamples#31](../../../visual-basic/language-reference/queries/codesnippet/VisualBasic/where-clause_2.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="be4b3-128">另请参阅</span><span class="sxs-lookup"><span data-stu-id="be4b3-128">See Also</span></span>  
 [<span data-ttu-id="be4b3-129">Visual Basic 中的 LINQ 简介</span><span class="sxs-lookup"><span data-stu-id="be4b3-129">Introduction to LINQ in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)  
 [<span data-ttu-id="be4b3-130">查询</span><span class="sxs-lookup"><span data-stu-id="be4b3-130">Queries</span></span>](../../../visual-basic/language-reference/queries/queries.md)  
 [<span data-ttu-id="be4b3-131">From 子句</span><span class="sxs-lookup"><span data-stu-id="be4b3-131">From Clause</span></span>](../../../visual-basic/language-reference/queries/from-clause.md)  
 [<span data-ttu-id="be4b3-132">Select 子句</span><span class="sxs-lookup"><span data-stu-id="be4b3-132">Select Clause</span></span>](../../../visual-basic/language-reference/queries/select-clause.md)  
 [<span data-ttu-id="be4b3-133">For Each...Next 语句</span><span class="sxs-lookup"><span data-stu-id="be4b3-133">For Each...Next Statement</span></span>](../../../visual-basic/language-reference/statements/for-each-next-statement.md)
