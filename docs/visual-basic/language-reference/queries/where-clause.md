---
title: Where 子句 (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.QueryWhere
helpviewer_keywords:
- Where statement [Visual Basic]
- queries [Visual Basic], Where
- Where clause [Visual Basic]
ms.assetid: 48b5c2c5-3181-429c-8545-894296798c89
ms.openlocfilehash: 5632e69039baebb3d1f1fd90c04586d9e50fe40f
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/02/2019
ms.locfileid: "58834499"
---
# <a name="where-clause-visual-basic"></a><span data-ttu-id="00c21-102">Where 子句 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="00c21-102">Where Clause (Visual Basic)</span></span>
<span data-ttu-id="00c21-103">指定查询的筛选条件。</span><span class="sxs-lookup"><span data-stu-id="00c21-103">Specifies the filtering condition for a query.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="00c21-104">语法</span><span class="sxs-lookup"><span data-stu-id="00c21-104">Syntax</span></span>  
  
```  
Where condition  
```  
  
## <a name="parts"></a><span data-ttu-id="00c21-105">部件</span><span class="sxs-lookup"><span data-stu-id="00c21-105">Parts</span></span>  
 `condition`  
 <span data-ttu-id="00c21-106">必需。</span><span class="sxs-lookup"><span data-stu-id="00c21-106">Required.</span></span> <span data-ttu-id="00c21-107">一个表达式，确定输出集合中是否包含在集合中的当前项的值。</span><span class="sxs-lookup"><span data-stu-id="00c21-107">An expression that determines whether the values for the current item in the collection are included in the output collection.</span></span> <span data-ttu-id="00c21-108">该表达式的计算结果必须为`Boolean`的等效项或值`Boolean`值。</span><span class="sxs-lookup"><span data-stu-id="00c21-108">The expression must evaluate to a `Boolean` value or the equivalent of a `Boolean` value.</span></span> <span data-ttu-id="00c21-109">如果条件计算结果为`True`，该元素是包含在查询结果; 否则为查询结果中排除该元素。</span><span class="sxs-lookup"><span data-stu-id="00c21-109">If the condition evaluates to `True`, the element is included in the query result; otherwise, the element is excluded from the query result.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="00c21-110">备注</span><span class="sxs-lookup"><span data-stu-id="00c21-110">Remarks</span></span>  
 <span data-ttu-id="00c21-111">`Where`子句，可以通过选择满足特定条件的元素来筛选查询数据。</span><span class="sxs-lookup"><span data-stu-id="00c21-111">The `Where` clause enables you to filter query data by selecting only elements that meet certain criteria.</span></span> <span data-ttu-id="00c21-112">元素的值会导致`Where`子句来计算结果为`True`包含在查询结果; 中排除其他元素。</span><span class="sxs-lookup"><span data-stu-id="00c21-112">Elements whose values cause the `Where` clause to evaluate to `True` are included in the query result; other elements are excluded.</span></span> <span data-ttu-id="00c21-113">使用中的表达式`Where`子句的计算结果必须为`Boolean`或等效于`Boolean`，如计算结果为一个整数`False`时其值为 0。</span><span class="sxs-lookup"><span data-stu-id="00c21-113">The expression that is used in a `Where` clause must evaluate to a `Boolean` or the equivalent of a `Boolean`, such as an Integer that evaluates to `False` when its value is zero.</span></span> <span data-ttu-id="00c21-114">可以组合多个表达式以`Where`通过使用逻辑运算符，如子句`And`， `Or`， `AndAlso`， `OrElse`， `Is`，和`IsNot`。</span><span class="sxs-lookup"><span data-stu-id="00c21-114">You can combine multiple expressions in a `Where` clause by using logical operators such as `And`, `Or`, `AndAlso`, `OrElse`, `Is`, and `IsNot`.</span></span>  
  
 <span data-ttu-id="00c21-115">默认情况下，查询无法计算的表达式直到被访问，例如，当它们进行数据绑定或在进行循环访问时`For`循环。</span><span class="sxs-lookup"><span data-stu-id="00c21-115">By default, query expressions are not evaluated until they are accessed—for example, when they are data-bound or iterated through in a `For` loop.</span></span> <span data-ttu-id="00c21-116">因此，`Where`访问查询之前不计算子句。</span><span class="sxs-lookup"><span data-stu-id="00c21-116">As a result, the `Where` clause is not evaluated until the query is accessed.</span></span> <span data-ttu-id="00c21-117">如果您具有值的查询中使用的外部`Where`子句，确保适当的值在中使用`Where`子句在执行查询的时间。</span><span class="sxs-lookup"><span data-stu-id="00c21-117">If you have values external to the query that are used in the `Where` clause, ensure that the appropriate value is used in the `Where` clause at the time the query is executed.</span></span> <span data-ttu-id="00c21-118">有关执行查询的详细信息，请参阅[编写你的第一个 LINQ 查询](../../../visual-basic/programming-guide/concepts/linq/writing-your-first-linq-query.md)。</span><span class="sxs-lookup"><span data-stu-id="00c21-118">For more information about query execution, see [Writing Your First LINQ Query](../../../visual-basic/programming-guide/concepts/linq/writing-your-first-linq-query.md).</span></span>  
  
 <span data-ttu-id="00c21-119">可以调用中的函数`Where`子句执行计算或操作的值从集合中的当前元素。</span><span class="sxs-lookup"><span data-stu-id="00c21-119">You can call functions within a `Where` clause to perform a calculation or operation on a value from the current element in the collection.</span></span> <span data-ttu-id="00c21-120">调用函数`Where`子句可能会导致立即定义后而不是受访问时执行的查询。</span><span class="sxs-lookup"><span data-stu-id="00c21-120">Calling a function in a `Where` clause can cause the query to be executed immediately when it is defined instead of when it is accessed.</span></span> <span data-ttu-id="00c21-121">有关执行查询的详细信息，请参阅[编写你的第一个 LINQ 查询](../../../visual-basic/programming-guide/concepts/linq/writing-your-first-linq-query.md)。</span><span class="sxs-lookup"><span data-stu-id="00c21-121">For more information about query execution, see [Writing Your First LINQ Query](../../../visual-basic/programming-guide/concepts/linq/writing-your-first-linq-query.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="00c21-122">示例</span><span class="sxs-lookup"><span data-stu-id="00c21-122">Example</span></span>  
 <span data-ttu-id="00c21-123">下面的查询中使用表达式`From`子句来声明范围变量`cust`每个`Customer`对象中`customers`集合。</span><span class="sxs-lookup"><span data-stu-id="00c21-123">The following query expression uses a `From` clause to declare a range variable `cust` for each `Customer` object in the `customers` collection.</span></span> <span data-ttu-id="00c21-124">`Where`子句使用的范围变量将输出限制为客户，从指定的区域。</span><span class="sxs-lookup"><span data-stu-id="00c21-124">The `Where` clause uses the range variable to restrict the output to customers from the specified region.</span></span> <span data-ttu-id="00c21-125">`For Each`循环显示查询结果中的每个客户的公司名称。</span><span class="sxs-lookup"><span data-stu-id="00c21-125">The `For Each` loop displays the company name for each customer in the query result.</span></span>  
  
 [!code-vb[VbSimpleQuerySamples#23](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbSimpleQuerySamples/VB/QuerySamples1.vb#23)]  
  
## <a name="example"></a><span data-ttu-id="00c21-126">示例</span><span class="sxs-lookup"><span data-stu-id="00c21-126">Example</span></span>  
 <span data-ttu-id="00c21-127">下面的示例使用`And`并`Or`中的逻辑运算符`Where`子句。</span><span class="sxs-lookup"><span data-stu-id="00c21-127">The following example uses `And` and `Or` logical operators in the `Where` clause.</span></span>  
  
 [!code-vb[VbSimpleQuerySamples#31](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbSimpleQuerySamples/VB/QuerySamples1.vb#31)]  
  
## <a name="see-also"></a><span data-ttu-id="00c21-128">请参阅</span><span class="sxs-lookup"><span data-stu-id="00c21-128">See also</span></span>

- [<span data-ttu-id="00c21-129">Visual Basic 中的 LINQ 简介</span><span class="sxs-lookup"><span data-stu-id="00c21-129">Introduction to LINQ in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)
- [<span data-ttu-id="00c21-130">查询</span><span class="sxs-lookup"><span data-stu-id="00c21-130">Queries</span></span>](../../../visual-basic/language-reference/queries/index.md)
- [<span data-ttu-id="00c21-131">From 子句</span><span class="sxs-lookup"><span data-stu-id="00c21-131">From Clause</span></span>](../../../visual-basic/language-reference/queries/from-clause.md)
- [<span data-ttu-id="00c21-132">Select 子句</span><span class="sxs-lookup"><span data-stu-id="00c21-132">Select Clause</span></span>](../../../visual-basic/language-reference/queries/select-clause.md)
- [<span data-ttu-id="00c21-133">For Each...Next 语句</span><span class="sxs-lookup"><span data-stu-id="00c21-133">For Each...Next Statement</span></span>](../../../visual-basic/language-reference/statements/for-each-next-statement.md)
