---
title: "基本查询操作 (Visual Basic 中) |Microsoft 文档"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- data sources [LINQ in Visual Basic]
- Join clause [LINQ in Visual Basic]
- ordering data [LINQ in Visual Basic]
- projections [LINQ in Visual Basic]
- LINQ [Visual Basic], query operations
- Order By clause [LINQ in Visual Basic]
- joining data [LINQ in Visual Basic]
- queries [LINQ in Visual Basic], basic operations
- selecting data [LINQ in Visual Basic]
- Group By clause [LINQ in Visual Basic]
- grouping data [LINQ in Visual Basic]
- Select clause [LINQ in Visual Basic]
ms.assetid: 1146f6d0-fcb8-4f4d-8223-c9db52620d21
caps.latest.revision: 37
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: 1ced446d6646bd26b9169f5894138e12a38efde7
ms.contentlocale: zh-cn
ms.lasthandoff: 04/12/2017

---
# <a name="basic-query-operations-visual-basic"></a><span data-ttu-id="e34b7-102">基本查询操作 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="e34b7-102">Basic Query Operations (Visual Basic)</span></span>
<span data-ttu-id="e34b7-103">本主题提供了简要介绍了[!INCLUDE[vbteclinqext](../../../../csharp/getting-started/includes/vbteclinqext_md.md)]表达式在 Visual Basic 和一些典型的一种在查询中执行的操作。</span><span class="sxs-lookup"><span data-stu-id="e34b7-103">This topic provides a brief introduction to [!INCLUDE[vbteclinqext](../../../../csharp/getting-started/includes/vbteclinqext_md.md)] expressions in Visual Basic, and to some of the typical kinds of operations that you perform in a query.</span></span> <span data-ttu-id="e34b7-104">有关详细信息，请参阅下列主题：</span><span class="sxs-lookup"><span data-stu-id="e34b7-104">For more information, see the following topics:</span></span>  
  
 [<span data-ttu-id="e34b7-105">在 Visual Basic 中的 LINQ 简介</span><span class="sxs-lookup"><span data-stu-id="e34b7-105">Introduction to LINQ in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)  
  
 [<span data-ttu-id="e34b7-106">查询</span><span class="sxs-lookup"><span data-stu-id="e34b7-106">Queries</span></span>](../../../../visual-basic/language-reference/queries/queries.md)  
  
 [<span data-ttu-id="e34b7-107">演练︰ 在 Visual Basic 中编写查询</span><span class="sxs-lookup"><span data-stu-id="e34b7-107">Walkthrough: Writing Queries in Visual Basic</span></span>](../../../../visual-basic/programming-guide/concepts/linq/walkthrough-writing-queries.md)  
  
## <a name="specifying-the-data-source-from"></a><span data-ttu-id="e34b7-108">指定数据源 （从）</span><span class="sxs-lookup"><span data-stu-id="e34b7-108">Specifying the Data Source (From)</span></span>  
 <span data-ttu-id="e34b7-109">在[!INCLUDE[vbteclinq](../../../../csharp/includes/vbteclinq_md.md)]查询中，第一步是指定您想要查询的数据源。</span><span class="sxs-lookup"><span data-stu-id="e34b7-109">In a [!INCLUDE[vbteclinq](../../../../csharp/includes/vbteclinq_md.md)] query, the first step is to specify the data source that you want to query.</span></span> <span data-ttu-id="e34b7-110">因此，`From`查询中的子句始终最先出现。</span><span class="sxs-lookup"><span data-stu-id="e34b7-110">Therefore, the `From` clause in a query always comes first.</span></span> <span data-ttu-id="e34b7-111">查询运算符选择和形状基于源的类型的结果。</span><span class="sxs-lookup"><span data-stu-id="e34b7-111">Query operators select and shape the result based on the type of the source.</span></span>  
  
 <span data-ttu-id="e34b7-112">[!code-vb[VbLINQBasicOps #&1;](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/basic-query-operations_1.vb)]</span><span class="sxs-lookup"><span data-stu-id="e34b7-112">[!code-vb[VbLINQBasicOps#1](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/basic-query-operations_1.vb)]</span></span>  
  
 <span data-ttu-id="e34b7-113">`From`子句指定数据源， `customers`，和一个*范围变量*， `cust`。</span><span class="sxs-lookup"><span data-stu-id="e34b7-113">The `From` clause specifies the data source, `customers`, and a *range variable*, `cust`.</span></span> <span data-ttu-id="e34b7-114">范围变量循环迭代与变量一样，只是在查询表达式中，实际上不发生迭代。</span><span class="sxs-lookup"><span data-stu-id="e34b7-114">The range variable is like a loop iteration variable, except that in a query expression, no actual iteration occurs.</span></span> <span data-ttu-id="e34b7-115">执行查询时，通常使用`For Each`循环中，作为对中的每个后续元素的引用的范围变量`customers`。</span><span class="sxs-lookup"><span data-stu-id="e34b7-115">When the query is executed, often by using a `For Each` loop, the range variable serves as a reference to each successive element in `customers`.</span></span> <span data-ttu-id="e34b7-116">因为编译器可以推断的一种`cust`，无需显式指定。</span><span class="sxs-lookup"><span data-stu-id="e34b7-116">Because the compiler can infer the type of `cust`, you do not have to specify it explicitly.</span></span> <span data-ttu-id="e34b7-117">有关编写显式超时和没有显式类型化的查询的示例，请参阅[查询操作 (Visual Basic 中) 中的类型关系](../../../../visual-basic/programming-guide/concepts/linq/type-relationships-in-query-operations.md)。</span><span class="sxs-lookup"><span data-stu-id="e34b7-117">For examples of queries written with and without explicit typing, see [Type Relationships in Query Operations (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/type-relationships-in-query-operations.md).</span></span>  
  
 <span data-ttu-id="e34b7-118">有关如何使用`From`子句在 Visual Basic 中，请参阅[From 子句](../../../../visual-basic/language-reference/queries/from-clause.md)。</span><span class="sxs-lookup"><span data-stu-id="e34b7-118">For more information about how to use the `From` clause in Visual Basic, see [From Clause](../../../../visual-basic/language-reference/queries/from-clause.md).</span></span>  
  
## <a name="filtering-data-where"></a><span data-ttu-id="e34b7-119">筛选数据 （位置）</span><span class="sxs-lookup"><span data-stu-id="e34b7-119">Filtering Data (Where)</span></span>  
 <span data-ttu-id="e34b7-120">可能最常见的查询操作应用布尔表达式的窗体中的筛选器。</span><span class="sxs-lookup"><span data-stu-id="e34b7-120">Probably the most common query operation is applying a filter in the form of a Boolean expression.</span></span> <span data-ttu-id="e34b7-121">然后，查询将返回仅对表达式为 true 的元素。</span><span class="sxs-lookup"><span data-stu-id="e34b7-121">The query then returns only those elements for which the expression is true.</span></span> <span data-ttu-id="e34b7-122">一个`Where`子句用来执行筛选。</span><span class="sxs-lookup"><span data-stu-id="e34b7-122">A `Where` clause is used to perform the filtering.</span></span> <span data-ttu-id="e34b7-123">筛选器指定要包括在结果序列中的数据源中的哪些元素。</span><span class="sxs-lookup"><span data-stu-id="e34b7-123">The filter specifies which elements in the data source to include in the resulting sequence.</span></span> <span data-ttu-id="e34b7-124">在下面的示例中，只有这些地址位于伦敦的客户是包括在内。</span><span class="sxs-lookup"><span data-stu-id="e34b7-124">In the following example, only those customers who have an address in London are included.</span></span>  
  
 <span data-ttu-id="e34b7-125">[!code-vb[VbLINQBasicOps #&2;](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/basic-query-operations_2.vb)]</span><span class="sxs-lookup"><span data-stu-id="e34b7-125">[!code-vb[VbLINQBasicOps#2](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/basic-query-operations_2.vb)]</span></span>  
  
 <span data-ttu-id="e34b7-126">您可以使用逻辑运算符，如`And`和`Or`组合中的筛选器表达式`Where`子句。</span><span class="sxs-lookup"><span data-stu-id="e34b7-126">You can use logical operators such as `And` and `Or` to combine filter expressions in a `Where` clause.</span></span> <span data-ttu-id="e34b7-127">例如，若要返回的客户，只有那些来自伦敦，并姓名为 Devon，使用下面的代码︰</span><span class="sxs-lookup"><span data-stu-id="e34b7-127">For example, to return only those customers who are from London and whose name is Devon, use the following code:</span></span>  
  
```vb  
Where cust.City = "London" And cust.Name = "Devon"   
```  
  
 <span data-ttu-id="e34b7-128">若要返回客户位于伦敦或巴黎，请使用下面的代码︰</span><span class="sxs-lookup"><span data-stu-id="e34b7-128">To return customers from London or Paris, use the following code:</span></span>  
  
```vb  
Where cust.City = "London" Or cust.City = "Paris"   
```  
  
 <span data-ttu-id="e34b7-129">有关如何使用`Where`子句在 Visual Basic 中，请参阅[Where 子句](../../../../visual-basic/language-reference/queries/where-clause.md)。</span><span class="sxs-lookup"><span data-stu-id="e34b7-129">For more information about how to use the `Where` clause in Visual Basic, see [Where Clause](../../../../visual-basic/language-reference/queries/where-clause.md).</span></span>  
  
## <a name="ordering-data-order-by"></a><span data-ttu-id="e34b7-130">对数据 (Order By) 进行排序</span><span class="sxs-lookup"><span data-stu-id="e34b7-130">Ordering Data (Order By)</span></span>  
 <span data-ttu-id="e34b7-131">它通常很方便地对返回的数据按特定顺序进行排序。</span><span class="sxs-lookup"><span data-stu-id="e34b7-131">It often is convenient to sort returned data into a particular order.</span></span> <span data-ttu-id="e34b7-132">`Order By`子句将使返回的序列进行排序的指定的字段或字段中的元素。</span><span class="sxs-lookup"><span data-stu-id="e34b7-132">The `Order By` clause will cause the elements in the returned sequence to be sorted on a specified field or fields.</span></span> <span data-ttu-id="e34b7-133">例如，下面的查询进行排序的结果基于`Name`属性。</span><span class="sxs-lookup"><span data-stu-id="e34b7-133">For example, the following query sorts the results based on the `Name` property.</span></span> <span data-ttu-id="e34b7-134">因为`Name`是一个字符串，返回的数据将从 A 到 Z 的按字母顺序排序。</span><span class="sxs-lookup"><span data-stu-id="e34b7-134">Because `Name` is a string, the returned data will be sorted alphabetically, from A to Z.</span></span>  
  
 <span data-ttu-id="e34b7-135">[!code-vb[VbLINQBasicOps #&3;](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/basic-query-operations_3.vb)]</span><span class="sxs-lookup"><span data-stu-id="e34b7-135">[!code-vb[VbLINQBasicOps#3](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/basic-query-operations_3.vb)]</span></span>  
  
 <span data-ttu-id="e34b7-136">对结果进行排序以相反顺序，从 Z 到 A，使用`Order By...Descending`子句。</span><span class="sxs-lookup"><span data-stu-id="e34b7-136">To order the results in reverse order, from Z to A, use the `Order By...Descending` clause.</span></span> <span data-ttu-id="e34b7-137">默认值是`Ascending`当没有`Ascending`，也不`Descending`指定。</span><span class="sxs-lookup"><span data-stu-id="e34b7-137">The default is `Ascending` when neither `Ascending` nor `Descending` is specified.</span></span>  
  
 <span data-ttu-id="e34b7-138">有关如何使用`Order By`子句在 Visual Basic 中，请参阅[Order By 子句](../../../../visual-basic/language-reference/queries/order-by-clause.md)。</span><span class="sxs-lookup"><span data-stu-id="e34b7-138">For more information about how to use the `Order By` clause in Visual Basic, see [Order By Clause](../../../../visual-basic/language-reference/queries/order-by-clause.md).</span></span>  
  
## <a name="selecting-data-select"></a><span data-ttu-id="e34b7-139">选择数据 （选择）</span><span class="sxs-lookup"><span data-stu-id="e34b7-139">Selecting Data (Select)</span></span>  
 <span data-ttu-id="e34b7-140">`Select`子句指定窗体和返回的元素的内容。</span><span class="sxs-lookup"><span data-stu-id="e34b7-140">The `Select` clause specifies the form and content of returned elements.</span></span> <span data-ttu-id="e34b7-141">例如，可以指定您的结果将包含的是整个`Customer`对象时，只是一个`Customer`根据计算的属性、 属性的子集、 从各种数据源或某些新的结果类型的属性的组合。</span><span class="sxs-lookup"><span data-stu-id="e34b7-141">For example, you can specify whether your results will consist of complete `Customer` objects, just one `Customer` property, a subset of properties, a combination of properties from various data sources, or some new result type based on a computation.</span></span> <span data-ttu-id="e34b7-142">当`Select`子句生成以外的源元素的副本，则调用该操作*投影*。</span><span class="sxs-lookup"><span data-stu-id="e34b7-142">When the `Select` clause produces something other than a copy of the source element, the operation is called a *projection*.</span></span>  
  
 <span data-ttu-id="e34b7-143">检索集合，其中包含的是整个`Customer`对象，选择范围变量本身︰</span><span class="sxs-lookup"><span data-stu-id="e34b7-143">To retrieve a collection that consists of complete `Customer` objects, select the range variable itself:</span></span>  
  
 <span data-ttu-id="e34b7-144">[!code-vb[VbLINQBasicOps #&4;](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/basic-query-operations_4.vb)]</span><span class="sxs-lookup"><span data-stu-id="e34b7-144">[!code-vb[VbLINQBasicOps#4](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/basic-query-operations_4.vb)]</span></span>  
  
 <span data-ttu-id="e34b7-145">如果`Customer`实例是一个大型对象，有很多字段和您想要检索的就是名称，则可以选择`cust.Name`，如在下面的示例所示。</span><span class="sxs-lookup"><span data-stu-id="e34b7-145">If a `Customer` instance is a large object that has many fields, and all that you want to retrieve is the name, you can select `cust.Name`, as shown in the following example.</span></span> <span data-ttu-id="e34b7-146">局部类型推理知道这会从集合中更改的结果类型`Customer`对象与字符串的集合。</span><span class="sxs-lookup"><span data-stu-id="e34b7-146">Local type inference recognizes that this changes the result type from a collection of `Customer` objects to a collection of strings.</span></span>  
  
 <span data-ttu-id="e34b7-147">[!code-vb[VbLINQBasicOps #&5;](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/basic-query-operations_5.vb)]</span><span class="sxs-lookup"><span data-stu-id="e34b7-147">[!code-vb[VbLINQBasicOps#5](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/basic-query-operations_5.vb)]</span></span>  
  
 <span data-ttu-id="e34b7-148">若要从数据源选择多个字段，您有两个选择︰</span><span class="sxs-lookup"><span data-stu-id="e34b7-148">To select multiple fields from the data source, you have two choices:</span></span>  
  
-   <span data-ttu-id="e34b7-149">在`Select`子句中，指定你想要在结果中包括的字段。</span><span class="sxs-lookup"><span data-stu-id="e34b7-149">In the `Select` clause, specify the fields you want to include in the result.</span></span> <span data-ttu-id="e34b7-150">编译器将定义这些字段作为其属性的匿名类型。</span><span class="sxs-lookup"><span data-stu-id="e34b7-150">The compiler will define an anonymous type that has those fields as its properties.</span></span> <span data-ttu-id="e34b7-151">有关详细信息，请参阅[匿名类型](../../../../visual-basic/programming-guide/language-features/objects-and-classes/anonymous-types.md)。</span><span class="sxs-lookup"><span data-stu-id="e34b7-151">For more information, see [Anonymous Types](../../../../visual-basic/programming-guide/language-features/objects-and-classes/anonymous-types.md).</span></span>  
  
     <span data-ttu-id="e34b7-152">在下面的示例返回的元素是匿名类型的实例，因为您不能为类型名称来引用在其他地方在代码中。</span><span class="sxs-lookup"><span data-stu-id="e34b7-152">Because the returned elements in the following example are instances of an anonymous type, you cannot refer to the type by name elsewhere in your code.</span></span> <span data-ttu-id="e34b7-153">该编译器指定类型的名称包含在普通 Visual Basic 代码中无效的字符。</span><span class="sxs-lookup"><span data-stu-id="e34b7-153">The compiler-designated name for the type contains characters that are not valid in normal Visual Basic code.</span></span> <span data-ttu-id="e34b7-154">在下面的示例中的查询返回的集合中的元素`londonCusts4`是匿名类型的实例</span><span class="sxs-lookup"><span data-stu-id="e34b7-154">In the following example, the elements in the collection that is returned by the query in `londonCusts4` are instances of an anonymous type</span></span>  
  
     <span data-ttu-id="e34b7-155">[!code-vb[VbLINQBasicOps #&6;](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/basic-query-operations_6.vb)]</span><span class="sxs-lookup"><span data-stu-id="e34b7-155">[!code-vb[VbLINQBasicOps#6](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/basic-query-operations_6.vb)]</span></span>  
  
     <span data-ttu-id="e34b7-156">- 或 -</span><span class="sxs-lookup"><span data-stu-id="e34b7-156">-or-</span></span>  
  
-   <span data-ttu-id="e34b7-157">定义包含您想要包括在结果中，创建并初始化中的类型的实例的特定字段的已命名的类型`Select`子句。</span><span class="sxs-lookup"><span data-stu-id="e34b7-157">Define a named type that contains the particular fields that you want to include in the result, and create and initialize instances of the type in the `Select` clause.</span></span> <span data-ttu-id="e34b7-158">仅当您需要使用各个结果集合外部的顺序返回它们，或者如果您必须将它们作为方法调用中的参数传递，请使用此选项。</span><span class="sxs-lookup"><span data-stu-id="e34b7-158">Use this option only if you have to use individual results outside the collection in which they are returned, or if you have to pass them as parameters in method calls.</span></span> <span data-ttu-id="e34b7-159">一种`londonCusts5`在下面的示例是 IEnumerable (Of NamePhone)。</span><span class="sxs-lookup"><span data-stu-id="e34b7-159">The type of `londonCusts5` in the following example is IEnumerable(Of NamePhone).</span></span>  
  
     <span data-ttu-id="e34b7-160">[!code-vb[VbLINQBasicOps #&7;](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/basic-query-operations_7.vb)]</span><span class="sxs-lookup"><span data-stu-id="e34b7-160">[!code-vb[VbLINQBasicOps#7](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/basic-query-operations_7.vb)]</span></span>  
  
     <span data-ttu-id="e34b7-161">[!code-vb[VbLINQBasicOps #&8;](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/basic-query-operations_8.vb)]</span><span class="sxs-lookup"><span data-stu-id="e34b7-161">[!code-vb[VbLINQBasicOps#8](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/basic-query-operations_8.vb)]</span></span>  
  
 <span data-ttu-id="e34b7-162">有关如何使用`Select`子句在 Visual Basic 中，请参阅[Select 子句](../../../../visual-basic/language-reference/queries/select-clause.md)。</span><span class="sxs-lookup"><span data-stu-id="e34b7-162">For more information about how to use the `Select` clause in Visual Basic, see [Select Clause](../../../../visual-basic/language-reference/queries/select-clause.md).</span></span>  
  
## <a name="joining-data-join-and-group-join"></a><span data-ttu-id="e34b7-163">联接数据 （联接和分组联接）</span><span class="sxs-lookup"><span data-stu-id="e34b7-163">Joining Data (Join and Group Join)</span></span>  
 <span data-ttu-id="e34b7-164">您可以组合使用多个数据源中的`From`子句中有多种。</span><span class="sxs-lookup"><span data-stu-id="e34b7-164">You can combine more than one data source in the `From` clause in several ways.</span></span> <span data-ttu-id="e34b7-165">例如，下面的代码使用两个数据源并隐式将从这两个结果中的属性进行合并。</span><span class="sxs-lookup"><span data-stu-id="e34b7-165">For example, the following code uses two data sources and implicitly combines properties from both of them in the result.</span></span> <span data-ttu-id="e34b7-166">该查询用于选择的学生以元音开头的姓氏和名字。</span><span class="sxs-lookup"><span data-stu-id="e34b7-166">The query selects students whose last names start with a vowel.</span></span>  
  
 <span data-ttu-id="e34b7-167">[!code-vb[VbLINQBasicOps #&9;](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/basic-query-operations_9.vb)]</span><span class="sxs-lookup"><span data-stu-id="e34b7-167">[!code-vb[VbLINQBasicOps#9](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/basic-query-operations_9.vb)]</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="e34b7-168">您可以运行此代码中创建的学生列表[如何︰ 创建列表项](../../../../visual-basic/programming-guide/concepts/linq/how-to-create-a-list-of-items.md)。</span><span class="sxs-lookup"><span data-stu-id="e34b7-168">You can run this code with the list of students created in [How to: Create a List of Items](../../../../visual-basic/programming-guide/concepts/linq/how-to-create-a-list-of-items.md).</span></span>  
  
 <span data-ttu-id="e34b7-169">`Join`关键字等效于`INNER JOIN`SQL 中。</span><span class="sxs-lookup"><span data-stu-id="e34b7-169">The `Join` keyword is equivalent to an `INNER JOIN` in SQL.</span></span> <span data-ttu-id="e34b7-170">它结合了基于两个集合中的元素之间的匹配项的值的两个集合。</span><span class="sxs-lookup"><span data-stu-id="e34b7-170">It combines two collections based on matching key values between elements in the two collections.</span></span> <span data-ttu-id="e34b7-171">查询将返回具有匹配的键值对集合元素的全部或部分。</span><span class="sxs-lookup"><span data-stu-id="e34b7-171">The query returns all or part of the collection elements that have matching key values.</span></span> <span data-ttu-id="e34b7-172">例如，下面的代码重复项上一个隐式联接的操作。</span><span class="sxs-lookup"><span data-stu-id="e34b7-172">For example, the following code duplicates the action of the previous implicit join.</span></span>  
  
 <span data-ttu-id="e34b7-173">[!code-vb[VbLINQBasicOps #&10;](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/basic-query-operations_10.vb)]</span><span class="sxs-lookup"><span data-stu-id="e34b7-173">[!code-vb[VbLINQBasicOps#10](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/basic-query-operations_10.vb)]</span></span>  
  
 <span data-ttu-id="e34b7-174">`Group Join`将集合组合为单个的分层集合，就像`LEFT JOIN`在 SQL 中。</span><span class="sxs-lookup"><span data-stu-id="e34b7-174">`Group Join` combines collections into a single hierarchical collection, just like a `LEFT JOIN` in SQL.</span></span> <span data-ttu-id="e34b7-175">有关详细信息，请参阅[Join 子句](../../../../visual-basic/language-reference/queries/join-clause.md)和[Group Join 子句](../../../../visual-basic/language-reference/queries/group-join-clause.md)。</span><span class="sxs-lookup"><span data-stu-id="e34b7-175">For more information, see [Join Clause](../../../../visual-basic/language-reference/queries/join-clause.md) and [Group Join Clause](../../../../visual-basic/language-reference/queries/group-join-clause.md).</span></span>  
  
## <a name="grouping-data-group-by"></a><span data-ttu-id="e34b7-176">对数据进行分组 (Group By)</span><span class="sxs-lookup"><span data-stu-id="e34b7-176">Grouping Data (Group By)</span></span>  
 <span data-ttu-id="e34b7-177">您可以添加`Group By`子句进行分组元素的一个或多个字段根据查询结果中的元素。</span><span class="sxs-lookup"><span data-stu-id="e34b7-177">You can add a `Group By` clause to group the elements in a query result according to one or more fields of the elements.</span></span> <span data-ttu-id="e34b7-178">例如，下面的代码进行分组的学生类年度。</span><span class="sxs-lookup"><span data-stu-id="e34b7-178">For example, the following code groups students by class year.</span></span>  
  
 <span data-ttu-id="e34b7-179">[!code-vb[VbLINQBasicOps #&11;](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/basic-query-operations_11.vb)]</span><span class="sxs-lookup"><span data-stu-id="e34b7-179">[!code-vb[VbLINQBasicOps#11](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/basic-query-operations_11.vb)]</span></span>  
  
 <span data-ttu-id="e34b7-180">如果您运行此代码中使用的列表中创建的学生[如何︰ 创建列表项](../../../../visual-basic/programming-guide/concepts/linq/how-to-create-a-list-of-items.md)，从输出`For Each`语句是︰</span><span class="sxs-lookup"><span data-stu-id="e34b7-180">If you run this code using the list of students created in [How to: Create a List of Items](../../../../visual-basic/programming-guide/concepts/linq/how-to-create-a-list-of-items.md), the output from the `For Each` statement is:</span></span>  
  
 <span data-ttu-id="e34b7-181">年份︰ 初级</span><span class="sxs-lookup"><span data-stu-id="e34b7-181">Year: Junior</span></span>  
  
 <span data-ttu-id="e34b7-182">Tucker Michael</span><span class="sxs-lookup"><span data-stu-id="e34b7-182">Tucker, Michael</span></span>  
  
 <span data-ttu-id="e34b7-183">Garcia Hugo</span><span class="sxs-lookup"><span data-stu-id="e34b7-183">Garcia, Hugo</span></span>  
  
 <span data-ttu-id="e34b7-184">Garcia Debra</span><span class="sxs-lookup"><span data-stu-id="e34b7-184">Garcia, Debra</span></span>  
  
 <span data-ttu-id="e34b7-185">Tucker Lance</span><span class="sxs-lookup"><span data-stu-id="e34b7-185">Tucker, Lance</span></span>  
  
 <span data-ttu-id="e34b7-186">年份︰ 高级</span><span class="sxs-lookup"><span data-stu-id="e34b7-186">Year: Senior</span></span>  
  
 <span data-ttu-id="e34b7-187">Omelchenko Svetlana</span><span class="sxs-lookup"><span data-stu-id="e34b7-187">Omelchenko, Svetlana</span></span>  
  
 <span data-ttu-id="e34b7-188">Osada Michiko</span><span class="sxs-lookup"><span data-stu-id="e34b7-188">Osada, Michiko</span></span>  
  
 <span data-ttu-id="e34b7-189">Ä Fadi</span><span class="sxs-lookup"><span data-stu-id="e34b7-189">Fakhouri, Fadi</span></span>  
  
 <span data-ttu-id="e34b7-190">Feng 汉英</span><span class="sxs-lookup"><span data-stu-id="e34b7-190">Feng, Hanying</span></span>  
  
 <span data-ttu-id="e34b7-191">Terry Adams</span><span class="sxs-lookup"><span data-stu-id="e34b7-191">Adams, Terry</span></span>  
  
 <span data-ttu-id="e34b7-192">年份︰ 新生</span><span class="sxs-lookup"><span data-stu-id="e34b7-192">Year: Freshman</span></span>  
  
 <span data-ttu-id="e34b7-193">Mortensen Sven</span><span class="sxs-lookup"><span data-stu-id="e34b7-193">Mortensen, Sven</span></span>  
  
 <span data-ttu-id="e34b7-194">Garcia Cesar</span><span class="sxs-lookup"><span data-stu-id="e34b7-194">Garcia, Cesar</span></span>  
  
 <span data-ttu-id="e34b7-195">在下面的代码所示的变体年级，并按姓氏进行每年内然后排序学生。</span><span class="sxs-lookup"><span data-stu-id="e34b7-195">The variation shown in the following code orders the class years, and then orders the students within each year by last name.</span></span>  
  
 <span data-ttu-id="e34b7-196">[!code-vb[VbLINQBasicOps #&12;](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/basic-query-operations_12.vb)]</span><span class="sxs-lookup"><span data-stu-id="e34b7-196">[!code-vb[VbLINQBasicOps#12](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/basic-query-operations_12.vb)]</span></span>  
  
 <span data-ttu-id="e34b7-197">有关详细信息`Group By`，请参阅[组 By 子句](../../../../visual-basic/language-reference/queries/group-by-clause.md)。</span><span class="sxs-lookup"><span data-stu-id="e34b7-197">For more information about `Group By`, see [Group By Clause](../../../../visual-basic/language-reference/queries/group-by-clause.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e34b7-198">请参见</span><span class="sxs-lookup"><span data-stu-id="e34b7-198">See Also</span></span>  
 <span data-ttu-id="e34b7-199"><xref:System.Collections.Generic.IEnumerable%601></xref:System.Collections.Generic.IEnumerable%601></span><span class="sxs-lookup"><span data-stu-id="e34b7-199"><xref:System.Collections.Generic.IEnumerable%601></span></span>   
<span data-ttu-id="e34b7-200"> [在 Visual Basic 中的 LINQ 入门](../../../../visual-basic/programming-guide/concepts/linq/getting-started-with-linq.md) </span><span class="sxs-lookup"><span data-stu-id="e34b7-200"> [Getting Started with LINQ in Visual Basic](../../../../visual-basic/programming-guide/concepts/linq/getting-started-with-linq.md) </span></span>  
<span data-ttu-id="e34b7-201"> [查询](../../../../visual-basic/language-reference/queries/queries.md) </span><span class="sxs-lookup"><span data-stu-id="e34b7-201"> [Queries](../../../../visual-basic/language-reference/queries/queries.md) </span></span>  
<span data-ttu-id="e34b7-202"> [标准查询运算符概述 (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/standard-query-operators-overview.md) </span><span class="sxs-lookup"><span data-stu-id="e34b7-202"> [Standard Query Operators Overview (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/standard-query-operators-overview.md) </span></span>  
<span data-ttu-id="e34b7-203"> [LINQ](../../../../visual-basic/programming-guide/language-features/linq/index.md)</span><span class="sxs-lookup"><span data-stu-id="e34b7-203"> [LINQ](../../../../visual-basic/programming-guide/language-features/linq/index.md)</span></span>
