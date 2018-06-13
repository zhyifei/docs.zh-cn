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
ms.openlocfilehash: 55c1e79b9e8e26483c1b7374a755bf977129169b
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33604401"
---
# <a name="select-clause-visual-basic"></a><span data-ttu-id="8b58d-102">Select 子句 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="8b58d-102">Select Clause (Visual Basic)</span></span>
<span data-ttu-id="8b58d-103">定义查询的结果。</span><span class="sxs-lookup"><span data-stu-id="8b58d-103">Defines the result of a query.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8b58d-104">语法</span><span class="sxs-lookup"><span data-stu-id="8b58d-104">Syntax</span></span>  
  
```  
Select [ var1 = ] fieldName1 [, [ var2 = ] fieldName2 [...] ]  
```  
  
## <a name="parts"></a><span data-ttu-id="8b58d-105">部件</span><span class="sxs-lookup"><span data-stu-id="8b58d-105">Parts</span></span>  
 `var1`  
 <span data-ttu-id="8b58d-106">可选。</span><span class="sxs-lookup"><span data-stu-id="8b58d-106">Optional.</span></span> <span data-ttu-id="8b58d-107">可以用于引用列表达式的结果的别名。</span><span class="sxs-lookup"><span data-stu-id="8b58d-107">An alias that can be used to reference the results of the column expression.</span></span>  
  
 `fieldName1`  
 <span data-ttu-id="8b58d-108">必须的。</span><span class="sxs-lookup"><span data-stu-id="8b58d-108">Required.</span></span> <span data-ttu-id="8b58d-109">要返回查询结果中的字段的名称。</span><span class="sxs-lookup"><span data-stu-id="8b58d-109">The name of the field to return in the query result.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="8b58d-110">备注</span><span class="sxs-lookup"><span data-stu-id="8b58d-110">Remarks</span></span>  
 <span data-ttu-id="8b58d-111">你可以使用`Select`子句定义要从查询返回的结果。</span><span class="sxs-lookup"><span data-stu-id="8b58d-111">You can use the `Select` clause to define the results to return from a query.</span></span> <span data-ttu-id="8b58d-112">这使你可以定义通过查询创建新的匿名类型的成员或目标的命名查询返回的类型的成员。</span><span class="sxs-lookup"><span data-stu-id="8b58d-112">This enables you to either define the members of a new anonymous type that is created by a query, or to target the members of a named type that is returned by a query.</span></span> <span data-ttu-id="8b58d-113">`Select`子句不需要查询。</span><span class="sxs-lookup"><span data-stu-id="8b58d-113">The `Select` clause is not required for a query.</span></span> <span data-ttu-id="8b58d-114">如果没有`Select`指定子句，则查询将返回基于标识为当前作用域的范围变量的所有成员的类型。</span><span class="sxs-lookup"><span data-stu-id="8b58d-114">If no `Select` clause is specified, the query will return a type based on all members of the range variables identified for the current scope.</span></span> <span data-ttu-id="8b58d-115">有关详细信息，请参阅[匿名类型](../../../visual-basic/programming-guide/language-features/objects-and-classes/anonymous-types.md)。</span><span class="sxs-lookup"><span data-stu-id="8b58d-115">For more information, see [Anonymous Types](../../../visual-basic/programming-guide/language-features/objects-and-classes/anonymous-types.md).</span></span> <span data-ttu-id="8b58d-116">当查询创建命名的类型时，它将返回的结果类型<xref:System.Collections.Generic.IEnumerable%601>其中`T`是创建的类型。</span><span class="sxs-lookup"><span data-stu-id="8b58d-116">When a query creates a named type, it will return a result of type <xref:System.Collections.Generic.IEnumerable%601> where `T` is the created type.</span></span>  
  
 <span data-ttu-id="8b58d-117">`Select`子句可引用当前作用域中的任何变量。</span><span class="sxs-lookup"><span data-stu-id="8b58d-117">The `Select` clause can reference any variables in the current scope.</span></span> <span data-ttu-id="8b58d-118">这包括在中标识的范围变量`From`子句 (或`From`子句)。</span><span class="sxs-lookup"><span data-stu-id="8b58d-118">This includes range variables identified in the `From` clause (or `From` clauses).</span></span> <span data-ttu-id="8b58d-119">它还包括任何新的变量，以通过别名创建`Aggregate`， `Let`， `Group By`，或`Group Join`子句或从以前的变量`Select`在查询表达式的子句。</span><span class="sxs-lookup"><span data-stu-id="8b58d-119">It also includes any new variables created with an alias by the `Aggregate`, `Let`, `Group By`, or `Group Join` clauses, or variables from a previous `Select` clause in the query expression.</span></span> <span data-ttu-id="8b58d-120">`Select`子句还可以包含静态值。</span><span class="sxs-lookup"><span data-stu-id="8b58d-120">The `Select` clause can also include static values.</span></span> <span data-ttu-id="8b58d-121">例如，下面的代码示例中演示了一个查询表达式`Select`子句定义为具有四个成员的新的匿名类型的查询结果： `ProductName`， `Price`， `Discount`，和`DiscountedPrice`。</span><span class="sxs-lookup"><span data-stu-id="8b58d-121">For example, the following code example shows a query expression in which the `Select` clause defines the query result as a new anonymous type with four members: `ProductName`, `Price`, `Discount`, and `DiscountedPrice`.</span></span> <span data-ttu-id="8b58d-122">`ProductName`和`Price`成员值，将从中定义的产品范围变量`From`子句。</span><span class="sxs-lookup"><span data-stu-id="8b58d-122">The `ProductName` and `Price` member values are taken from the product range variable that is defined in the `From` clause.</span></span> <span data-ttu-id="8b58d-123">`DiscountedPrice`中计算成员值`Let`子句。</span><span class="sxs-lookup"><span data-stu-id="8b58d-123">The `DiscountedPrice` member value is calculated in the `Let` clause.</span></span> <span data-ttu-id="8b58d-124">`Discount`成员是静态值。</span><span class="sxs-lookup"><span data-stu-id="8b58d-124">The `Discount` member is a static value.</span></span>  
  
 [!code-vb[VbSimpleQuerySamples#27](../../../visual-basic/language-reference/queries/codesnippet/VisualBasic/select-clause_1.vb)]  
  
 <span data-ttu-id="8b58d-125">`Select`子句引入了一组新的后续查询子句的范围变量和之前的范围变量将不再在作用域中。</span><span class="sxs-lookup"><span data-stu-id="8b58d-125">The `Select` clause introduces a new set of range variables for subsequent query clauses, and previous range variables are no longer in scope.</span></span> <span data-ttu-id="8b58d-126">最后一个`Select`子句在查询表达式确定查询的返回值。</span><span class="sxs-lookup"><span data-stu-id="8b58d-126">The last `Select` clause in a query expression determines the return value of the query.</span></span> <span data-ttu-id="8b58d-127">例如，以下查询将返回公司总数超过 500 的每个客户订单的名称和顺序 ID。</span><span class="sxs-lookup"><span data-stu-id="8b58d-127">For example, the following query returns the company name and order ID for every customer order for which the total exceeds 500.</span></span> <span data-ttu-id="8b58d-128">第一个`Select`子句标识的范围变量`Where`子句和第二个`Select`子句。</span><span class="sxs-lookup"><span data-stu-id="8b58d-128">The first `Select` clause identifies the range variables for the `Where` clause and the second `Select` clause.</span></span> <span data-ttu-id="8b58d-129">第二个`Select`子句标识作为新的匿名类型的查询返回的值。</span><span class="sxs-lookup"><span data-stu-id="8b58d-129">The second `Select` clause identifies the values returned by the query as a new anonymous type.</span></span>  
  
 [!code-vb[VbSimpleQuerySamples#28](../../../visual-basic/language-reference/queries/codesnippet/VisualBasic/select-clause_2.vb)]  
  
 <span data-ttu-id="8b58d-130">如果`Select`子句标识要返回的单个项，查询表达式将返回该单个项的类型的集合。</span><span class="sxs-lookup"><span data-stu-id="8b58d-130">If the `Select` clause identifies a single item to return, the query expression returns a collection of the type of that single item.</span></span> <span data-ttu-id="8b58d-131">如果`Select`子句标识要返回的多个项，查询表达式将返回新的匿名类型，基于所选项目的集合。</span><span class="sxs-lookup"><span data-stu-id="8b58d-131">If the `Select` clause identifies multiple items to return, the query expression returns a collection of a new anonymous type, based on the selected items.</span></span> <span data-ttu-id="8b58d-132">例如，以下两个查询返回基于两个不同类型的集合`Select`子句。</span><span class="sxs-lookup"><span data-stu-id="8b58d-132">For example, the following two queries return collections of two different types based on the `Select` clause.</span></span> <span data-ttu-id="8b58d-133">第一个查询返回公司名称作为字符串的的集合。</span><span class="sxs-lookup"><span data-stu-id="8b58d-133">The first query returns a collection of company names as strings.</span></span> <span data-ttu-id="8b58d-134">第二个查询返回的集合`Customer`填充有的公司名称和地址信息的对象。</span><span class="sxs-lookup"><span data-stu-id="8b58d-134">The second query returns a collection of `Customer` objects populated with the company names and address information.</span></span>  
  
 [!code-vb[VbSimpleQuerySamples#29](../../../visual-basic/language-reference/queries/codesnippet/VisualBasic/select-clause_3.vb)]  
  
## <a name="example"></a><span data-ttu-id="8b58d-135">示例</span><span class="sxs-lookup"><span data-stu-id="8b58d-135">Example</span></span>  
 <span data-ttu-id="8b58d-136">下面的查询表达式使用`From`子句来声明范围变量`cust`为`customers`集合。</span><span class="sxs-lookup"><span data-stu-id="8b58d-136">The following query expression uses a `From` clause to declare a range variable `cust` for the `customers` collection.</span></span> <span data-ttu-id="8b58d-137">`Select`子句选择的客户名称和 ID 值并填充`CompanyName`和`CustomerID`新的范围变量的列。</span><span class="sxs-lookup"><span data-stu-id="8b58d-137">The `Select` clause selects the customer name and ID value and populates the `CompanyName` and `CustomerID` columns of the new range variable.</span></span> <span data-ttu-id="8b58d-138">`For Each`语句循环访问每个返回的对象，并显示`CompanyName`和`CustomerID`为每个记录的列。</span><span class="sxs-lookup"><span data-stu-id="8b58d-138">The `For Each` statement loops over each returned object and displays the `CompanyName` and `CustomerID` columns for each record.</span></span>  
  
 [!code-vb[VbSimpleQuerySamples#30](../../../visual-basic/language-reference/queries/codesnippet/VisualBasic/select-clause_4.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="8b58d-139">请参阅</span><span class="sxs-lookup"><span data-stu-id="8b58d-139">See Also</span></span>  
 [<span data-ttu-id="8b58d-140">Visual Basic 中的 LINQ 简介</span><span class="sxs-lookup"><span data-stu-id="8b58d-140">Introduction to LINQ in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)  
 [<span data-ttu-id="8b58d-141">查询</span><span class="sxs-lookup"><span data-stu-id="8b58d-141">Queries</span></span>](../../../visual-basic/language-reference/queries/queries.md)  
 [<span data-ttu-id="8b58d-142">From 子句</span><span class="sxs-lookup"><span data-stu-id="8b58d-142">From Clause</span></span>](../../../visual-basic/language-reference/queries/from-clause.md)  
 [<span data-ttu-id="8b58d-143">Where 子句</span><span class="sxs-lookup"><span data-stu-id="8b58d-143">Where Clause</span></span>](../../../visual-basic/language-reference/queries/where-clause.md)  
 [<span data-ttu-id="8b58d-144">Order By 子句</span><span class="sxs-lookup"><span data-stu-id="8b58d-144">Order By Clause</span></span>](../../../visual-basic/language-reference/queries/order-by-clause.md)  
 [<span data-ttu-id="8b58d-145">匿名类型</span><span class="sxs-lookup"><span data-stu-id="8b58d-145">Anonymous Types</span></span>](../../../visual-basic/programming-guide/language-features/objects-and-classes/anonymous-types.md)
