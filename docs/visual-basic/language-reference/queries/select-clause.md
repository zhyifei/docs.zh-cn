---
title: Select 子句 (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.QuerySelect
helpviewer_keywords:
- Select statement [Visual Basic]
- Select clause [Visual Basic]
- queries [Visual Basic], Select
ms.assetid: 27a3f61c-5960-4692-9b91-4d0c4b6178fe
ms.openlocfilehash: 7d959c0717a3ef44dfc23c90d99ec7b83421efaa
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/04/2018
ms.locfileid: "43529796"
---
# <a name="select-clause-visual-basic"></a><span data-ttu-id="6ebc5-102">Select 子句 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="6ebc5-102">Select Clause (Visual Basic)</span></span>
<span data-ttu-id="6ebc5-103">定义查询的结果。</span><span class="sxs-lookup"><span data-stu-id="6ebc5-103">Defines the result of a query.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6ebc5-104">语法</span><span class="sxs-lookup"><span data-stu-id="6ebc5-104">Syntax</span></span>  
  
```  
Select [ var1 = ] fieldName1 [, [ var2 = ] fieldName2 [...] ]  
```  
  
## <a name="parts"></a><span data-ttu-id="6ebc5-105">部件</span><span class="sxs-lookup"><span data-stu-id="6ebc5-105">Parts</span></span>  
 `var1`  
 <span data-ttu-id="6ebc5-106">可选。</span><span class="sxs-lookup"><span data-stu-id="6ebc5-106">Optional.</span></span> <span data-ttu-id="6ebc5-107">一个可用于引用的列表达式结果的别名。</span><span class="sxs-lookup"><span data-stu-id="6ebc5-107">An alias that can be used to reference the results of the column expression.</span></span>  
  
 `fieldName1`  
 <span data-ttu-id="6ebc5-108">必须的。</span><span class="sxs-lookup"><span data-stu-id="6ebc5-108">Required.</span></span> <span data-ttu-id="6ebc5-109">要返回查询结果中的字段的名称。</span><span class="sxs-lookup"><span data-stu-id="6ebc5-109">The name of the field to return in the query result.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="6ebc5-110">备注</span><span class="sxs-lookup"><span data-stu-id="6ebc5-110">Remarks</span></span>  
 <span data-ttu-id="6ebc5-111">可以使用`Select`子句定义要从查询返回的结果。</span><span class="sxs-lookup"><span data-stu-id="6ebc5-111">You can use the `Select` clause to define the results to return from a query.</span></span> <span data-ttu-id="6ebc5-112">这使你可以定义的查询，创建的新匿名类型成员或目标的查询返回的命名类型的成员。</span><span class="sxs-lookup"><span data-stu-id="6ebc5-112">This enables you to either define the members of a new anonymous type that is created by a query, or to target the members of a named type that is returned by a query.</span></span> <span data-ttu-id="6ebc5-113">`Select`子句不是必需的查询。</span><span class="sxs-lookup"><span data-stu-id="6ebc5-113">The `Select` clause is not required for a query.</span></span> <span data-ttu-id="6ebc5-114">如果没有`Select`指定子句，则查询将返回基于为当前作用域标识的范围变量的所有成员的类型。</span><span class="sxs-lookup"><span data-stu-id="6ebc5-114">If no `Select` clause is specified, the query will return a type based on all members of the range variables identified for the current scope.</span></span> <span data-ttu-id="6ebc5-115">有关详细信息，请参阅[匿名类型](../../../visual-basic/programming-guide/language-features/objects-and-classes/anonymous-types.md)。</span><span class="sxs-lookup"><span data-stu-id="6ebc5-115">For more information, see [Anonymous Types](../../../visual-basic/programming-guide/language-features/objects-and-classes/anonymous-types.md).</span></span> <span data-ttu-id="6ebc5-116">当查询创建一个已命名的类型时，它将返回类型的结果<xref:System.Collections.Generic.IEnumerable%601>其中`T`是创建的类型。</span><span class="sxs-lookup"><span data-stu-id="6ebc5-116">When a query creates a named type, it will return a result of type <xref:System.Collections.Generic.IEnumerable%601> where `T` is the created type.</span></span>  
  
 <span data-ttu-id="6ebc5-117">`Select`子句可以引用当前作用域中的任何变量。</span><span class="sxs-lookup"><span data-stu-id="6ebc5-117">The `Select` clause can reference any variables in the current scope.</span></span> <span data-ttu-id="6ebc5-118">这包括中标识的范围变量`From`子句 (或`From`子句)。</span><span class="sxs-lookup"><span data-stu-id="6ebc5-118">This includes range variables identified in the `From` clause (or `From` clauses).</span></span> <span data-ttu-id="6ebc5-119">它还包括使用的别名创建任何新变量`Aggregate`， `Let`， `Group By`，或`Group Join`子句或从以前的变量`Select`查询表达式中的子句。</span><span class="sxs-lookup"><span data-stu-id="6ebc5-119">It also includes any new variables created with an alias by the `Aggregate`, `Let`, `Group By`, or `Group Join` clauses, or variables from a previous `Select` clause in the query expression.</span></span> <span data-ttu-id="6ebc5-120">`Select`子句还可以包含静态值。</span><span class="sxs-lookup"><span data-stu-id="6ebc5-120">The `Select` clause can also include static values.</span></span> <span data-ttu-id="6ebc5-121">例如，下面的代码示例演示查询表达式所在`Select`子句将查询结果定义为具有四个成员的新匿名类型： `ProductName`， `Price`， `Discount`，和`DiscountedPrice`。</span><span class="sxs-lookup"><span data-stu-id="6ebc5-121">For example, the following code example shows a query expression in which the `Select` clause defines the query result as a new anonymous type with four members: `ProductName`, `Price`, `Discount`, and `DiscountedPrice`.</span></span> <span data-ttu-id="6ebc5-122">`ProductName`并`Price`成员值取自中定义的产品范围变量`From`子句。</span><span class="sxs-lookup"><span data-stu-id="6ebc5-122">The `ProductName` and `Price` member values are taken from the product range variable that is defined in the `From` clause.</span></span> <span data-ttu-id="6ebc5-123">`DiscountedPrice`中计算成员值`Let`子句。</span><span class="sxs-lookup"><span data-stu-id="6ebc5-123">The `DiscountedPrice` member value is calculated in the `Let` clause.</span></span> <span data-ttu-id="6ebc5-124">`Discount`成员是静态值。</span><span class="sxs-lookup"><span data-stu-id="6ebc5-124">The `Discount` member is a static value.</span></span>  
  
 [!code-vb[VbSimpleQuerySamples#27](../../../visual-basic/language-reference/queries/codesnippet/VisualBasic/select-clause_1.vb)]  
  
 <span data-ttu-id="6ebc5-125">`Select`子句引入了一组新的后续查询子句的范围变量和之前的范围变量将不再在作用域中。</span><span class="sxs-lookup"><span data-stu-id="6ebc5-125">The `Select` clause introduces a new set of range variables for subsequent query clauses, and previous range variables are no longer in scope.</span></span> <span data-ttu-id="6ebc5-126">最后一个`Select`查询表达式中的子句将确定查询的返回值。</span><span class="sxs-lookup"><span data-stu-id="6ebc5-126">The last `Select` clause in a query expression determines the return value of the query.</span></span> <span data-ttu-id="6ebc5-127">例如，以下查询将返回公司名称和订单总计超过 500 的每个客户订单 ID。</span><span class="sxs-lookup"><span data-stu-id="6ebc5-127">For example, the following query returns the company name and order ID for every customer order for which the total exceeds 500.</span></span> <span data-ttu-id="6ebc5-128">第一个`Select`子句标识的范围变量`Where`子句和第二个`Select`子句。</span><span class="sxs-lookup"><span data-stu-id="6ebc5-128">The first `Select` clause identifies the range variables for the `Where` clause and the second `Select` clause.</span></span> <span data-ttu-id="6ebc5-129">第二个`Select`子句标识作为新的匿名类型的查询返回的值。</span><span class="sxs-lookup"><span data-stu-id="6ebc5-129">The second `Select` clause identifies the values returned by the query as a new anonymous type.</span></span>  
  
 [!code-vb[VbSimpleQuerySamples#28](../../../visual-basic/language-reference/queries/codesnippet/VisualBasic/select-clause_2.vb)]  
  
 <span data-ttu-id="6ebc5-130">如果`Select`子句标识要返回的单个项，在查询表达式返回的单个项的类型的集合。</span><span class="sxs-lookup"><span data-stu-id="6ebc5-130">If the `Select` clause identifies a single item to return, the query expression returns a collection of the type of that single item.</span></span> <span data-ttu-id="6ebc5-131">如果`Select`子句标识要返回的多个项，在查询表达式返回基于所选的项的新匿名类型的集合。</span><span class="sxs-lookup"><span data-stu-id="6ebc5-131">If the `Select` clause identifies multiple items to return, the query expression returns a collection of a new anonymous type, based on the selected items.</span></span> <span data-ttu-id="6ebc5-132">例如，以下两个查询返回基于两个不同类型的集合`Select`子句。</span><span class="sxs-lookup"><span data-stu-id="6ebc5-132">For example, the following two queries return collections of two different types based on the `Select` clause.</span></span> <span data-ttu-id="6ebc5-133">第一个查询返回以字符串形式的公司名称的集合。</span><span class="sxs-lookup"><span data-stu-id="6ebc5-133">The first query returns a collection of company names as strings.</span></span> <span data-ttu-id="6ebc5-134">第二个查询返回的集合`Customer`使用公司名称和地址信息填充的对象。</span><span class="sxs-lookup"><span data-stu-id="6ebc5-134">The second query returns a collection of `Customer` objects populated with the company names and address information.</span></span>  
  
 [!code-vb[VbSimpleQuerySamples#29](../../../visual-basic/language-reference/queries/codesnippet/VisualBasic/select-clause_3.vb)]  
  
## <a name="example"></a><span data-ttu-id="6ebc5-135">示例</span><span class="sxs-lookup"><span data-stu-id="6ebc5-135">Example</span></span>  
 <span data-ttu-id="6ebc5-136">下面的查询中使用表达式`From`子句来声明范围变量`cust`为`customers`集合。</span><span class="sxs-lookup"><span data-stu-id="6ebc5-136">The following query expression uses a `From` clause to declare a range variable `cust` for the `customers` collection.</span></span> <span data-ttu-id="6ebc5-137">`Select`子句中选择客户名称和 ID 值并填充`CompanyName`和`CustomerID`的新范围变量的列。</span><span class="sxs-lookup"><span data-stu-id="6ebc5-137">The `Select` clause selects the customer name and ID value and populates the `CompanyName` and `CustomerID` columns of the new range variable.</span></span> <span data-ttu-id="6ebc5-138">`For Each`语句循环访问每个返回的对象，并显示`CompanyName`和`CustomerID`为每个记录的列。</span><span class="sxs-lookup"><span data-stu-id="6ebc5-138">The `For Each` statement loops over each returned object and displays the `CompanyName` and `CustomerID` columns for each record.</span></span>  
  
 [!code-vb[VbSimpleQuerySamples#30](../../../visual-basic/language-reference/queries/codesnippet/VisualBasic/select-clause_4.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="6ebc5-139">请参阅</span><span class="sxs-lookup"><span data-stu-id="6ebc5-139">See Also</span></span>  
 [<span data-ttu-id="6ebc5-140">Visual Basic 中的 LINQ 简介</span><span class="sxs-lookup"><span data-stu-id="6ebc5-140">Introduction to LINQ in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)  
 [<span data-ttu-id="6ebc5-141">查询</span><span class="sxs-lookup"><span data-stu-id="6ebc5-141">Queries</span></span>](../../../visual-basic/language-reference/queries/index.md)  
 [<span data-ttu-id="6ebc5-142">From 子句</span><span class="sxs-lookup"><span data-stu-id="6ebc5-142">From Clause</span></span>](../../../visual-basic/language-reference/queries/from-clause.md)  
 [<span data-ttu-id="6ebc5-143">Where 子句</span><span class="sxs-lookup"><span data-stu-id="6ebc5-143">Where Clause</span></span>](../../../visual-basic/language-reference/queries/where-clause.md)  
 [<span data-ttu-id="6ebc5-144">Order By 子句</span><span class="sxs-lookup"><span data-stu-id="6ebc5-144">Order By Clause</span></span>](../../../visual-basic/language-reference/queries/order-by-clause.md)  
 [<span data-ttu-id="6ebc5-145">匿名类型</span><span class="sxs-lookup"><span data-stu-id="6ebc5-145">Anonymous Types</span></span>](../../../visual-basic/programming-guide/language-features/objects-and-classes/anonymous-types.md)
