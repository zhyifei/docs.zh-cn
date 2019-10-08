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
ms.openlocfilehash: 087472c51d203be083fea0d39ade6f12066cfcb4
ms.sourcegitcommit: eff6adb61852369ab690f3f047818c90580e7eb1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/07/2019
ms.locfileid: "72004748"
---
# <a name="select-clause-visual-basic"></a><span data-ttu-id="b7cc5-102">Select 子句 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="b7cc5-102">Select Clause (Visual Basic)</span></span>
<span data-ttu-id="b7cc5-103">定义查询的结果。</span><span class="sxs-lookup"><span data-stu-id="b7cc5-103">Defines the result of a query.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b7cc5-104">语法</span><span class="sxs-lookup"><span data-stu-id="b7cc5-104">Syntax</span></span>  
  
```vb  
Select [ var1 = ] fieldName1 [, [ var2 = ] fieldName2 [...] ]  
```  
  
## <a name="parts"></a><span data-ttu-id="b7cc5-105">部件</span><span class="sxs-lookup"><span data-stu-id="b7cc5-105">Parts</span></span>  
 `var1`  
 <span data-ttu-id="b7cc5-106">可选。</span><span class="sxs-lookup"><span data-stu-id="b7cc5-106">Optional.</span></span> <span data-ttu-id="b7cc5-107">可用于引用列表达式的结果的别名。</span><span class="sxs-lookup"><span data-stu-id="b7cc5-107">An alias that can be used to reference the results of the column expression.</span></span>  
  
 `fieldName1`  
 <span data-ttu-id="b7cc5-108">必需。</span><span class="sxs-lookup"><span data-stu-id="b7cc5-108">Required.</span></span> <span data-ttu-id="b7cc5-109">要在查询结果中返回的字段的名称。</span><span class="sxs-lookup"><span data-stu-id="b7cc5-109">The name of the field to return in the query result.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="b7cc5-110">备注</span><span class="sxs-lookup"><span data-stu-id="b7cc5-110">Remarks</span></span>  
 <span data-ttu-id="b7cc5-111">您可以使用 `Select` 子句来定义从查询返回的结果。</span><span class="sxs-lookup"><span data-stu-id="b7cc5-111">You can use the `Select` clause to define the results to return from a query.</span></span> <span data-ttu-id="b7cc5-112">这使您可以定义由查询创建的新匿名类型的成员，或指定查询所返回的命名类型的成员。</span><span class="sxs-lookup"><span data-stu-id="b7cc5-112">This enables you to either define the members of a new anonymous type that is created by a query, or to target the members of a named type that is returned by a query.</span></span> <span data-ttu-id="b7cc5-113">查询不需要 `Select` 子句。</span><span class="sxs-lookup"><span data-stu-id="b7cc5-113">The `Select` clause is not required for a query.</span></span> <span data-ttu-id="b7cc5-114">如果未指定 `Select` 子句，则查询将基于为当前作用域标识的范围变量的所有成员返回一个类型。</span><span class="sxs-lookup"><span data-stu-id="b7cc5-114">If no `Select` clause is specified, the query will return a type based on all members of the range variables identified for the current scope.</span></span> <span data-ttu-id="b7cc5-115">有关详细信息，请参阅[匿名类型](../../../visual-basic/programming-guide/language-features/objects-and-classes/anonymous-types.md)。</span><span class="sxs-lookup"><span data-stu-id="b7cc5-115">For more information, see [Anonymous Types](../../../visual-basic/programming-guide/language-features/objects-and-classes/anonymous-types.md).</span></span> <span data-ttu-id="b7cc5-116">当查询创建命名类型时，它将返回类型为 <xref:System.Collections.Generic.IEnumerable%601> 的结果，其中 @no__t 为创建的类型。</span><span class="sxs-lookup"><span data-stu-id="b7cc5-116">When a query creates a named type, it will return a result of type <xref:System.Collections.Generic.IEnumerable%601> where `T` is the created type.</span></span>  
  
 <span data-ttu-id="b7cc5-117">@No__t-0 子句可以引用当前作用域中的任何变量。</span><span class="sxs-lookup"><span data-stu-id="b7cc5-117">The `Select` clause can reference any variables in the current scope.</span></span> <span data-ttu-id="b7cc5-118">这包括 `From` 子句中标识的范围变量（或 `From` 子句）。</span><span class="sxs-lookup"><span data-stu-id="b7cc5-118">This includes range variables identified in the `From` clause (or `From` clauses).</span></span> <span data-ttu-id="b7cc5-119">它还包括使用别名创建的任何新变量，这些变量由 `Aggregate`、`Let`、`Group By` 或 `Group Join` 子句创建，或者是查询表达式中先前 `Select` 子句中的变量。</span><span class="sxs-lookup"><span data-stu-id="b7cc5-119">It also includes any new variables created with an alias by the `Aggregate`, `Let`, `Group By`, or `Group Join` clauses, or variables from a previous `Select` clause in the query expression.</span></span> <span data-ttu-id="b7cc5-120">@No__t-0 子句还可以包括静态值。</span><span class="sxs-lookup"><span data-stu-id="b7cc5-120">The `Select` clause can also include static values.</span></span> <span data-ttu-id="b7cc5-121">例如，下面的代码示例演示一个查询表达式，其中 `Select` 子句将查询结果定义为具有四个成员的新匿名类型： `ProductName`、`Price`、`Discount` 和 @no__t。</span><span class="sxs-lookup"><span data-stu-id="b7cc5-121">For example, the following code example shows a query expression in which the `Select` clause defines the query result as a new anonymous type with four members: `ProductName`, `Price`, `Discount`, and `DiscountedPrice`.</span></span> <span data-ttu-id="b7cc5-122">@No__t 0 和 @no__t 1 成员值取自 `From` 子句中定义的产品范围变量。</span><span class="sxs-lookup"><span data-stu-id="b7cc5-122">The `ProductName` and `Price` member values are taken from the product range variable that is defined in the `From` clause.</span></span> <span data-ttu-id="b7cc5-123">在 @no__t 子句中计算 @no__t 的成员值。</span><span class="sxs-lookup"><span data-stu-id="b7cc5-123">The `DiscountedPrice` member value is calculated in the `Let` clause.</span></span> <span data-ttu-id="b7cc5-124">@No__t 0 成员是一个静态值。</span><span class="sxs-lookup"><span data-stu-id="b7cc5-124">The `Discount` member is a static value.</span></span>  
  
 [!code-vb[VbSimpleQuerySamples#27](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbSimpleQuerySamples/VB/QuerySamples1.vb#27)]  
  
 <span data-ttu-id="b7cc5-125">@No__t-0 子句为后面的查询子句引入了一组新的范围变量，并且以前的范围变量不再位于范围内。</span><span class="sxs-lookup"><span data-stu-id="b7cc5-125">The `Select` clause introduces a new set of range variables for subsequent query clauses, and previous range variables are no longer in scope.</span></span> <span data-ttu-id="b7cc5-126">查询表达式中的最后一个 `Select` 子句决定了查询的返回值。</span><span class="sxs-lookup"><span data-stu-id="b7cc5-126">The last `Select` clause in a query expression determines the return value of the query.</span></span> <span data-ttu-id="b7cc5-127">例如，以下查询将返回总计超过500的每个客户订单的公司名称和订单 ID。</span><span class="sxs-lookup"><span data-stu-id="b7cc5-127">For example, the following query returns the company name and order ID for every customer order for which the total exceeds 500.</span></span> <span data-ttu-id="b7cc5-128">第一个 `Select` 子句标识了 @no__t 子句和第二个 @no__t 为2子句的范围变量。</span><span class="sxs-lookup"><span data-stu-id="b7cc5-128">The first `Select` clause identifies the range variables for the `Where` clause and the second `Select` clause.</span></span> <span data-ttu-id="b7cc5-129">第二个 `Select` 子句将查询返回的值标识为新的匿名类型。</span><span class="sxs-lookup"><span data-stu-id="b7cc5-129">The second `Select` clause identifies the values returned by the query as a new anonymous type.</span></span>  
  
 [!code-vb[VbSimpleQuerySamples#28](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbSimpleQuerySamples/VB/QuerySamples1.vb#28)]  
  
 <span data-ttu-id="b7cc5-130">如果 @no__t 0 子句标识要返回的单个项，则查询表达式返回该项的类型的集合。</span><span class="sxs-lookup"><span data-stu-id="b7cc5-130">If the `Select` clause identifies a single item to return, the query expression returns a collection of the type of that single item.</span></span> <span data-ttu-id="b7cc5-131">如果 `Select` 子句标识要返回的多个项，则查询表达式将返回基于选定项的新匿名类型的集合。</span><span class="sxs-lookup"><span data-stu-id="b7cc5-131">If the `Select` clause identifies multiple items to return, the query expression returns a collection of a new anonymous type, based on the selected items.</span></span> <span data-ttu-id="b7cc5-132">例如，以下两个查询根据 @no__t 的子句返回两个不同类型的集合。</span><span class="sxs-lookup"><span data-stu-id="b7cc5-132">For example, the following two queries return collections of two different types based on the `Select` clause.</span></span> <span data-ttu-id="b7cc5-133">第一个查询以字符串的形式返回公司名称的集合。</span><span class="sxs-lookup"><span data-stu-id="b7cc5-133">The first query returns a collection of company names as strings.</span></span> <span data-ttu-id="b7cc5-134">第二个查询返回使用公司名称和地址信息填充的 @no__t 0 对象的集合。</span><span class="sxs-lookup"><span data-stu-id="b7cc5-134">The second query returns a collection of `Customer` objects populated with the company names and address information.</span></span>  
  
 [!code-vb[VbSimpleQuerySamples#29](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbSimpleQuerySamples/VB/QuerySamples1.vb#29)]  
  
## <a name="example"></a><span data-ttu-id="b7cc5-135">示例</span><span class="sxs-lookup"><span data-stu-id="b7cc5-135">Example</span></span>  
 <span data-ttu-id="b7cc5-136">下面的查询表达式使用 `From` 子句为 `customers` 集合声明范围变量 `cust`。</span><span class="sxs-lookup"><span data-stu-id="b7cc5-136">The following query expression uses a `From` clause to declare a range variable `cust` for the `customers` collection.</span></span> <span data-ttu-id="b7cc5-137">@No__t-0 子句选择客户名称和 ID 值，并填充新范围变量的 @no__t 1 和 @no__t 2 列。</span><span class="sxs-lookup"><span data-stu-id="b7cc5-137">The `Select` clause selects the customer name and ID value and populates the `CompanyName` and `CustomerID` columns of the new range variable.</span></span> <span data-ttu-id="b7cc5-138">@No__t-0 语句会遍历返回的每个对象，并为每个记录显示 @no__t 1 和 @no__t 2 列。</span><span class="sxs-lookup"><span data-stu-id="b7cc5-138">The `For Each` statement loops over each returned object and displays the `CompanyName` and `CustomerID` columns for each record.</span></span>  
  
 [!code-vb[VbSimpleQuerySamples#30](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbSimpleQuerySamples/VB/QuerySamples1.vb#30)]  
  
## <a name="see-also"></a><span data-ttu-id="b7cc5-139">请参阅</span><span class="sxs-lookup"><span data-stu-id="b7cc5-139">See also</span></span>

- [<span data-ttu-id="b7cc5-140">Visual Basic 中的 LINQ 简介</span><span class="sxs-lookup"><span data-stu-id="b7cc5-140">Introduction to LINQ in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)
- [<span data-ttu-id="b7cc5-141">查询</span><span class="sxs-lookup"><span data-stu-id="b7cc5-141">Queries</span></span>](../../../visual-basic/language-reference/queries/index.md)
- [<span data-ttu-id="b7cc5-142">From 子句</span><span class="sxs-lookup"><span data-stu-id="b7cc5-142">From Clause</span></span>](../../../visual-basic/language-reference/queries/from-clause.md)
- [<span data-ttu-id="b7cc5-143">Where 子句</span><span class="sxs-lookup"><span data-stu-id="b7cc5-143">Where Clause</span></span>](../../../visual-basic/language-reference/queries/where-clause.md)
- [<span data-ttu-id="b7cc5-144">Order By 子句</span><span class="sxs-lookup"><span data-stu-id="b7cc5-144">Order By Clause</span></span>](../../../visual-basic/language-reference/queries/order-by-clause.md)
- [<span data-ttu-id="b7cc5-145">匿名类型</span><span class="sxs-lookup"><span data-stu-id="b7cc5-145">Anonymous Types</span></span>](../../../visual-basic/programming-guide/language-features/objects-and-classes/anonymous-types.md)
