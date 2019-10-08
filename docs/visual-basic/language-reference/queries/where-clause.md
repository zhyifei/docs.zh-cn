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
ms.openlocfilehash: 404dd848058f7e5c9bc8a74b6d89df18c6c55fad
ms.sourcegitcommit: eff6adb61852369ab690f3f047818c90580e7eb1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/07/2019
ms.locfileid: "72005001"
---
# <a name="where-clause-visual-basic"></a><span data-ttu-id="12cc8-102">Where 子句 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="12cc8-102">Where Clause (Visual Basic)</span></span>
<span data-ttu-id="12cc8-103">指定查询的筛选条件。</span><span class="sxs-lookup"><span data-stu-id="12cc8-103">Specifies the filtering condition for a query.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="12cc8-104">语法</span><span class="sxs-lookup"><span data-stu-id="12cc8-104">Syntax</span></span>  
  
```vb  
Where condition  
```  
  
## <a name="parts"></a><span data-ttu-id="12cc8-105">部件</span><span class="sxs-lookup"><span data-stu-id="12cc8-105">Parts</span></span>  
 `condition`  
 <span data-ttu-id="12cc8-106">必需。</span><span class="sxs-lookup"><span data-stu-id="12cc8-106">Required.</span></span> <span data-ttu-id="12cc8-107">确定集合中当前项的值是否包含在输出集合中的表达式。</span><span class="sxs-lookup"><span data-stu-id="12cc8-107">An expression that determines whether the values for the current item in the collection are included in the output collection.</span></span> <span data-ttu-id="12cc8-108">表达式的计算结果必须为 `Boolean` 值或等效于 @no__t 1 值。</span><span class="sxs-lookup"><span data-stu-id="12cc8-108">The expression must evaluate to a `Boolean` value or the equivalent of a `Boolean` value.</span></span> <span data-ttu-id="12cc8-109">如果条件的计算结果为 `True`，则查询结果中将包含元素;否则，元素会从查询结果中排除。</span><span class="sxs-lookup"><span data-stu-id="12cc8-109">If the condition evaluates to `True`, the element is included in the query result; otherwise, the element is excluded from the query result.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="12cc8-110">备注</span><span class="sxs-lookup"><span data-stu-id="12cc8-110">Remarks</span></span>  
 <span data-ttu-id="12cc8-111">使用 `Where` 子句可以通过仅选择符合特定条件的元素来筛选查询数据。</span><span class="sxs-lookup"><span data-stu-id="12cc8-111">The `Where` clause enables you to filter query data by selecting only elements that meet certain criteria.</span></span> <span data-ttu-id="12cc8-112">如果元素的值导致 `Where` 子句的计算结果为 `True`，则包含在查询结果中;排除其他元素。</span><span class="sxs-lookup"><span data-stu-id="12cc8-112">Elements whose values cause the `Where` clause to evaluate to `True` are included in the query result; other elements are excluded.</span></span> <span data-ttu-id="12cc8-113">在 `Where` 子句中使用的表达式的计算结果必须为 @no__t 1 或等效的 `Boolean`，例如，当其值为零时，计算结果为 `False` 的整数。</span><span class="sxs-lookup"><span data-stu-id="12cc8-113">The expression that is used in a `Where` clause must evaluate to a `Boolean` or the equivalent of a `Boolean`, such as an Integer that evaluates to `False` when its value is zero.</span></span> <span data-ttu-id="12cc8-114">可以通过使用逻辑运算符（如 `And`、`Or`、`AndAlso`、`OrElse`、`Is` 和 `IsNot`）在 `Where` 子句中组合多个表达式。</span><span class="sxs-lookup"><span data-stu-id="12cc8-114">You can combine multiple expressions in a `Where` clause by using logical operators such as `And`, `Or`, `AndAlso`, `OrElse`, `Is`, and `IsNot`.</span></span>  
  
 <span data-ttu-id="12cc8-115">默认情况下，在访问查询表达式之前，不会对其进行计算（例如，当它们在 `For` 循环中进行数据绑定或循环访问时）。</span><span class="sxs-lookup"><span data-stu-id="12cc8-115">By default, query expressions are not evaluated until they are accessed—for example, when they are data-bound or iterated through in a `For` loop.</span></span> <span data-ttu-id="12cc8-116">因此，在访问查询之前，不会计算 `Where` 子句。</span><span class="sxs-lookup"><span data-stu-id="12cc8-116">As a result, the `Where` clause is not evaluated until the query is accessed.</span></span> <span data-ttu-id="12cc8-117">如果在 `Where` 子句中使用的查询外部存在值，请确保在执行查询时在 `Where` 子句中使用适当的值。</span><span class="sxs-lookup"><span data-stu-id="12cc8-117">If you have values external to the query that are used in the `Where` clause, ensure that the appropriate value is used in the `Where` clause at the time the query is executed.</span></span> <span data-ttu-id="12cc8-118">有关查询执行的详细信息，请参阅[编写第一个 LINQ 查询](../../../visual-basic/programming-guide/concepts/linq/writing-your-first-linq-query.md)。</span><span class="sxs-lookup"><span data-stu-id="12cc8-118">For more information about query execution, see [Writing Your First LINQ Query](../../../visual-basic/programming-guide/concepts/linq/writing-your-first-linq-query.md).</span></span>  
  
 <span data-ttu-id="12cc8-119">可以在 `Where` 子句中调用函数，以对集合中的当前元素中的值执行计算或运算。</span><span class="sxs-lookup"><span data-stu-id="12cc8-119">You can call functions within a `Where` clause to perform a calculation or operation on a value from the current element in the collection.</span></span> <span data-ttu-id="12cc8-120">调用 `Where` 子句中的函数可能会导致在定义查询时（而不是在访问时）立即执行查询。</span><span class="sxs-lookup"><span data-stu-id="12cc8-120">Calling a function in a `Where` clause can cause the query to be executed immediately when it is defined instead of when it is accessed.</span></span> <span data-ttu-id="12cc8-121">有关查询执行的详细信息，请参阅[编写第一个 LINQ 查询](../../../visual-basic/programming-guide/concepts/linq/writing-your-first-linq-query.md)。</span><span class="sxs-lookup"><span data-stu-id="12cc8-121">For more information about query execution, see [Writing Your First LINQ Query](../../../visual-basic/programming-guide/concepts/linq/writing-your-first-linq-query.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="12cc8-122">示例</span><span class="sxs-lookup"><span data-stu-id="12cc8-122">Example</span></span>  
 <span data-ttu-id="12cc8-123">下面的查询表达式使用 `From` 子句为 @no__t 集合中的每个 `Customer` 对象声明一个范围变量 `cust`。</span><span class="sxs-lookup"><span data-stu-id="12cc8-123">The following query expression uses a `From` clause to declare a range variable `cust` for each `Customer` object in the `customers` collection.</span></span> <span data-ttu-id="12cc8-124">@No__t-0 子句使用范围变量将输出限制为指定区域的客户。</span><span class="sxs-lookup"><span data-stu-id="12cc8-124">The `Where` clause uses the range variable to restrict the output to customers from the specified region.</span></span> <span data-ttu-id="12cc8-125">@No__t-0 循环显示查询结果中每个客户的公司名称。</span><span class="sxs-lookup"><span data-stu-id="12cc8-125">The `For Each` loop displays the company name for each customer in the query result.</span></span>  
  
 [!code-vb[VbSimpleQuerySamples#23](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbSimpleQuerySamples/VB/QuerySamples1.vb#23)]  
  
## <a name="example"></a><span data-ttu-id="12cc8-126">示例</span><span class="sxs-lookup"><span data-stu-id="12cc8-126">Example</span></span>  
 <span data-ttu-id="12cc8-127">下面的示例使用了 `Where` 子句中的 @no__t 0 和 @no__t 逻辑运算符。</span><span class="sxs-lookup"><span data-stu-id="12cc8-127">The following example uses `And` and `Or` logical operators in the `Where` clause.</span></span>  
  
 [!code-vb[VbSimpleQuerySamples#31](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbSimpleQuerySamples/VB/QuerySamples1.vb#31)]  
  
## <a name="see-also"></a><span data-ttu-id="12cc8-128">请参阅</span><span class="sxs-lookup"><span data-stu-id="12cc8-128">See also</span></span>

- [<span data-ttu-id="12cc8-129">Visual Basic 中的 LINQ 简介</span><span class="sxs-lookup"><span data-stu-id="12cc8-129">Introduction to LINQ in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)
- [<span data-ttu-id="12cc8-130">查询</span><span class="sxs-lookup"><span data-stu-id="12cc8-130">Queries</span></span>](../../../visual-basic/language-reference/queries/index.md)
- [<span data-ttu-id="12cc8-131">From 子句</span><span class="sxs-lookup"><span data-stu-id="12cc8-131">From Clause</span></span>](../../../visual-basic/language-reference/queries/from-clause.md)
- [<span data-ttu-id="12cc8-132">Select 子句</span><span class="sxs-lookup"><span data-stu-id="12cc8-132">Select Clause</span></span>](../../../visual-basic/language-reference/queries/select-clause.md)
- [<span data-ttu-id="12cc8-133">For Each...Next 语句</span><span class="sxs-lookup"><span data-stu-id="12cc8-133">For Each...Next Statement</span></span>](../../../visual-basic/language-reference/statements/for-each-next-statement.md)
