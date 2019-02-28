---
title: 基本查询操作 (Visual Basic)
ms.date: 07/20/2015
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
ms.openlocfilehash: 5ca92324dec1d4fa8885a610a6e246640f4a5752
ms.sourcegitcommit: 40364ded04fa6cdcb2b6beca7f68412e2e12f633
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/28/2019
ms.locfileid: "56973023"
---
# <a name="basic-query-operations-visual-basic"></a><span data-ttu-id="5a7d9-102">基本查询操作 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="5a7d9-102">Basic Query Operations (Visual Basic)</span></span>
<span data-ttu-id="5a7d9-103">本主题提供了简要介绍了[!INCLUDE[vbteclinqext](~/includes/vbteclinqext-md.md)]表达式在 Visual Basic 中和某些典型查询中执行的操作。</span><span class="sxs-lookup"><span data-stu-id="5a7d9-103">This topic provides a brief introduction to [!INCLUDE[vbteclinqext](~/includes/vbteclinqext-md.md)] expressions in Visual Basic, and to some of the typical kinds of operations that you perform in a query.</span></span> <span data-ttu-id="5a7d9-104">有关详细信息，请参阅下列主题：</span><span class="sxs-lookup"><span data-stu-id="5a7d9-104">For more information, see the following topics:</span></span>  
  
 [<span data-ttu-id="5a7d9-105">Visual Basic 中的 LINQ 简介</span><span class="sxs-lookup"><span data-stu-id="5a7d9-105">Introduction to LINQ in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)  
  
 [<span data-ttu-id="5a7d9-106">查询</span><span class="sxs-lookup"><span data-stu-id="5a7d9-106">Queries</span></span>](../../../../visual-basic/language-reference/queries/index.md)  
  
 [<span data-ttu-id="5a7d9-107">演练：在 Visual Basic 中编写查询</span><span class="sxs-lookup"><span data-stu-id="5a7d9-107">Walkthrough: Writing Queries in Visual Basic</span></span>](../../../../visual-basic/programming-guide/concepts/linq/walkthrough-writing-queries.md)  
  
## <a name="specifying-the-data-source-from"></a><span data-ttu-id="5a7d9-108">指定数据源 (From)</span><span class="sxs-lookup"><span data-stu-id="5a7d9-108">Specifying the Data Source (From)</span></span>  
 <span data-ttu-id="5a7d9-109">在[!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)]查询，第一步是指定您想要查询的数据源。</span><span class="sxs-lookup"><span data-stu-id="5a7d9-109">In a [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] query, the first step is to specify the data source that you want to query.</span></span> <span data-ttu-id="5a7d9-110">因此，`From`在查询中的子句始终第一个出现。</span><span class="sxs-lookup"><span data-stu-id="5a7d9-110">Therefore, the `From` clause in a query always comes first.</span></span> <span data-ttu-id="5a7d9-111">查询运算符选择，并基于源的类型结果的形式。</span><span class="sxs-lookup"><span data-stu-id="5a7d9-111">Query operators select and shape the result based on the type of the source.</span></span>  
  
 [!code-vb[VbLINQBasicOps#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQBasicOps/VB/Class1.vb#1)]  
  
 <span data-ttu-id="5a7d9-112">`From`子句指定数据源`customers`，和一个*范围变量*， `cust`。</span><span class="sxs-lookup"><span data-stu-id="5a7d9-112">The `From` clause specifies the data source, `customers`, and a *range variable*, `cust`.</span></span> <span data-ttu-id="5a7d9-113">范围变量类似于循环迭代变量，只是在查询表达式中，不会真正发生迭代。</span><span class="sxs-lookup"><span data-stu-id="5a7d9-113">The range variable is like a loop iteration variable, except that in a query expression, no actual iteration occurs.</span></span> <span data-ttu-id="5a7d9-114">执行查询时，通常通过使用`For Each`循环中，范围变量可作为对中的每个后续元素的引用`customers`。</span><span class="sxs-lookup"><span data-stu-id="5a7d9-114">When the query is executed, often by using a `For Each` loop, the range variable serves as a reference to each successive element in `customers`.</span></span> <span data-ttu-id="5a7d9-115">由于编译器可以推断 `cust` 的类型，因此无需显式指定它。</span><span class="sxs-lookup"><span data-stu-id="5a7d9-115">Because the compiler can infer the type of `cust`, you do not have to specify it explicitly.</span></span> <span data-ttu-id="5a7d9-116">有关编写使用和不使用显式类型化的查询的示例，请参阅[查询操作 (Visual Basic 中) 中的类型关系](../../../../visual-basic/programming-guide/concepts/linq/type-relationships-in-query-operations.md)。</span><span class="sxs-lookup"><span data-stu-id="5a7d9-116">For examples of queries written with and without explicit typing, see [Type Relationships in Query Operations (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/type-relationships-in-query-operations.md).</span></span>  
  
 <span data-ttu-id="5a7d9-117">有关如何使用详细信息`From`子句在 Visual Basic 中，请参阅[From 子句](../../../../visual-basic/language-reference/queries/from-clause.md)。</span><span class="sxs-lookup"><span data-stu-id="5a7d9-117">For more information about how to use the `From` clause in Visual Basic, see [From Clause](../../../../visual-basic/language-reference/queries/from-clause.md).</span></span>  
  
## <a name="filtering-data-where"></a><span data-ttu-id="5a7d9-118">筛选数据 （位置）</span><span class="sxs-lookup"><span data-stu-id="5a7d9-118">Filtering Data (Where)</span></span>  
 <span data-ttu-id="5a7d9-119">可能的最常见的查询操作应用形式的布尔表达式筛选器。</span><span class="sxs-lookup"><span data-stu-id="5a7d9-119">Probably the most common query operation is applying a filter in the form of a Boolean expression.</span></span> <span data-ttu-id="5a7d9-120">然后，查询将返回仅对表达式为 true 的元素。</span><span class="sxs-lookup"><span data-stu-id="5a7d9-120">The query then returns only those elements for which the expression is true.</span></span> <span data-ttu-id="5a7d9-121">一个`Where`子句用来执行筛选。</span><span class="sxs-lookup"><span data-stu-id="5a7d9-121">A `Where` clause is used to perform the filtering.</span></span> <span data-ttu-id="5a7d9-122">筛选器指定要生成序列中包含的数据源中的哪些元素。</span><span class="sxs-lookup"><span data-stu-id="5a7d9-122">The filter specifies which elements in the data source to include in the resulting sequence.</span></span> <span data-ttu-id="5a7d9-123">在以下示例中，仅那些具有地址位于伦敦客户包含。</span><span class="sxs-lookup"><span data-stu-id="5a7d9-123">In the following example, only those customers who have an address in London are included.</span></span>  
  
 [!code-vb[VbLINQBasicOps#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQBasicOps/VB/Class1.vb#2)]  
  
 <span data-ttu-id="5a7d9-124">您可以使用逻辑运算符，如`And`并`Or`合并筛选器表达式中的`Where`子句。</span><span class="sxs-lookup"><span data-stu-id="5a7d9-124">You can use logical operators such as `And` and `Or` to combine filter expressions in a `Where` clause.</span></span> <span data-ttu-id="5a7d9-125">例如，若要返回来自伦敦谁是，其名称为 Devon 客户，请使用以下代码：</span><span class="sxs-lookup"><span data-stu-id="5a7d9-125">For example, to return only those customers who are from London and whose name is Devon, use the following code:</span></span>  
  
```vb  
Where cust.City = "London" And cust.Name = "Devon"   
```  
  
 <span data-ttu-id="5a7d9-126">若要返回来自 London 或 Paris 的客户，使用以下代码：</span><span class="sxs-lookup"><span data-stu-id="5a7d9-126">To return customers from London or Paris, use the following code:</span></span>  
  
```vb  
Where cust.City = "London" Or cust.City = "Paris"   
```  
  
 <span data-ttu-id="5a7d9-127">有关如何使用详细信息`Where`子句在 Visual Basic 中，请参阅[Where 子句](../../../../visual-basic/language-reference/queries/where-clause.md)。</span><span class="sxs-lookup"><span data-stu-id="5a7d9-127">For more information about how to use the `Where` clause in Visual Basic, see [Where Clause](../../../../visual-basic/language-reference/queries/where-clause.md).</span></span>  
  
## <a name="ordering-data-order-by"></a><span data-ttu-id="5a7d9-128">对数据 (Order By) 进行排序</span><span class="sxs-lookup"><span data-stu-id="5a7d9-128">Ordering Data (Order By)</span></span>  
 <span data-ttu-id="5a7d9-129">它通常是可以方便地对返回的数据按特定顺序进行排序。</span><span class="sxs-lookup"><span data-stu-id="5a7d9-129">It often is convenient to sort returned data into a particular order.</span></span> <span data-ttu-id="5a7d9-130">`Order By`子句会使返回按指定的一个或多个字段进行排序的序列中的元素。</span><span class="sxs-lookup"><span data-stu-id="5a7d9-130">The `Order By` clause will cause the elements in the returned sequence to be sorted on a specified field or fields.</span></span> <span data-ttu-id="5a7d9-131">例如，以下查询对基于对结果进行排序`Name`属性。</span><span class="sxs-lookup"><span data-stu-id="5a7d9-131">For example, the following query sorts the results based on the `Name` property.</span></span> <span data-ttu-id="5a7d9-132">因为`Name`是一个字符串，返回的数据将从 A 到 Z 的字母顺序，排序。</span><span class="sxs-lookup"><span data-stu-id="5a7d9-132">Because `Name` is a string, the returned data will be sorted alphabetically, from A to Z.</span></span>  
  
 [!code-vb[VbLINQBasicOps#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQBasicOps/VB/Class1.vb#3)]  
  
 <span data-ttu-id="5a7d9-133">要对结果进行从 Z 到 A 的逆序排序，请使用 `Order By...Descending` 子句。</span><span class="sxs-lookup"><span data-stu-id="5a7d9-133">To order the results in reverse order, from Z to A, use the `Order By...Descending` clause.</span></span> <span data-ttu-id="5a7d9-134">默认值是`Ascending`当没有`Ascending`也不`Descending`指定。</span><span class="sxs-lookup"><span data-stu-id="5a7d9-134">The default is `Ascending` when neither `Ascending` nor `Descending` is specified.</span></span>  
  
 <span data-ttu-id="5a7d9-135">有关如何使用详细信息`Order By`子句在 Visual Basic 中，请参阅[Order By 子句](../../../../visual-basic/language-reference/queries/order-by-clause.md)。</span><span class="sxs-lookup"><span data-stu-id="5a7d9-135">For more information about how to use the `Order By` clause in Visual Basic, see [Order By Clause](../../../../visual-basic/language-reference/queries/order-by-clause.md).</span></span>  
  
## <a name="selecting-data-select"></a><span data-ttu-id="5a7d9-136">选择数据 （选择）</span><span class="sxs-lookup"><span data-stu-id="5a7d9-136">Selecting Data (Select)</span></span>  
 <span data-ttu-id="5a7d9-137">`Select`子句指定的窗体和返回的元素的内容。</span><span class="sxs-lookup"><span data-stu-id="5a7d9-137">The `Select` clause specifies the form and content of returned elements.</span></span> <span data-ttu-id="5a7d9-138">例如，可以指定您的结果将包含的是整个`Customer`对象，只是一个`Customer`基于计算属性、 属性的子集，从各种数据源或一些新的结果类型的属性的组合。</span><span class="sxs-lookup"><span data-stu-id="5a7d9-138">For example, you can specify whether your results will consist of complete `Customer` objects, just one `Customer` property, a subset of properties, a combination of properties from various data sources, or some new result type based on a computation.</span></span> <span data-ttu-id="5a7d9-139">当 `Select` 子句生成除源元素副本以外的内容时，该操作称为投影。</span><span class="sxs-lookup"><span data-stu-id="5a7d9-139">When the `Select` clause produces something other than a copy of the source element, the operation is called a *projection*.</span></span>  
  
 <span data-ttu-id="5a7d9-140">检索一个集合，其中包含完整`Customer`对象，选择的范围变量本身：</span><span class="sxs-lookup"><span data-stu-id="5a7d9-140">To retrieve a collection that consists of complete `Customer` objects, select the range variable itself:</span></span>  
  
 [!code-vb[VbLINQBasicOps#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQBasicOps/VB/Class1.vb#4)]  
  
 <span data-ttu-id="5a7d9-141">如果`Customer`实例是具有许多字段、 一个大型对象和所有你想要检索是的名称，可以选择`cust.Name`，如以下示例所示。</span><span class="sxs-lookup"><span data-stu-id="5a7d9-141">If a `Customer` instance is a large object that has many fields, and all that you want to retrieve is the name, you can select `cust.Name`, as shown in the following example.</span></span> <span data-ttu-id="5a7d9-142">局部类型推理知道此集合中的更改的结果类型`Customer`到字符串的集合对象。</span><span class="sxs-lookup"><span data-stu-id="5a7d9-142">Local type inference recognizes that this changes the result type from a collection of `Customer` objects to a collection of strings.</span></span>  
  
 [!code-vb[VbLINQBasicOps#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQBasicOps/VB/Class1.vb#5)]  
  
 <span data-ttu-id="5a7d9-143">若要选择多个字段从数据源，您有两种选择：</span><span class="sxs-lookup"><span data-stu-id="5a7d9-143">To select multiple fields from the data source, you have two choices:</span></span>  
  
-   <span data-ttu-id="5a7d9-144">在`Select`子句中，指定你想要在结果中包含的字段。</span><span class="sxs-lookup"><span data-stu-id="5a7d9-144">In the `Select` clause, specify the fields you want to include in the result.</span></span> <span data-ttu-id="5a7d9-145">编译器将定义这些字段作为其属性的匿名类型。</span><span class="sxs-lookup"><span data-stu-id="5a7d9-145">The compiler will define an anonymous type that has those fields as its properties.</span></span> <span data-ttu-id="5a7d9-146">有关详细信息，请参阅[匿名类型](../../../../visual-basic/programming-guide/language-features/objects-and-classes/anonymous-types.md)。</span><span class="sxs-lookup"><span data-stu-id="5a7d9-146">For more information, see [Anonymous Types](../../../../visual-basic/programming-guide/language-features/objects-and-classes/anonymous-types.md).</span></span>  
  
     <span data-ttu-id="5a7d9-147">在下面的示例返回的元素为匿名类型的实例，因为你不能为类型根据名称引用其他位置在代码中。</span><span class="sxs-lookup"><span data-stu-id="5a7d9-147">Because the returned elements in the following example are instances of an anonymous type, you cannot refer to the type by name elsewhere in your code.</span></span> <span data-ttu-id="5a7d9-148">编译器指定的类型名称包含不正常的 Visual Basic 代码中有效的字符。</span><span class="sxs-lookup"><span data-stu-id="5a7d9-148">The compiler-designated name for the type contains characters that are not valid in normal Visual Basic code.</span></span> <span data-ttu-id="5a7d9-149">在下面的示例中的查询返回的集合中的元素`londonCusts4`是匿名类型的实例</span><span class="sxs-lookup"><span data-stu-id="5a7d9-149">In the following example, the elements in the collection that is returned by the query in `londonCusts4` are instances of an anonymous type</span></span>  
  
     [!code-vb[VbLINQBasicOps#6](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/basic-query-operations_6.vb)]  
  
     <span data-ttu-id="5a7d9-150">或</span><span class="sxs-lookup"><span data-stu-id="5a7d9-150">-or-</span></span>  
  
-   <span data-ttu-id="5a7d9-151">定义包含你想要包括在结果中，创建并初始化在类型的实例的特定字段的命名的类型`Select`子句。</span><span class="sxs-lookup"><span data-stu-id="5a7d9-151">Define a named type that contains the particular fields that you want to include in the result, and create and initialize instances of the type in the `Select` clause.</span></span> <span data-ttu-id="5a7d9-152">仅当您必须使用各个结果集合外部的顺序返回它们，或如果您需要将它们作为方法调用中的参数传递，请使用此选项。</span><span class="sxs-lookup"><span data-stu-id="5a7d9-152">Use this option only if you have to use individual results outside the collection in which they are returned, or if you have to pass them as parameters in method calls.</span></span> <span data-ttu-id="5a7d9-153">类型`londonCusts5`在下面的示例是 IEnumerable (Of NamePhone)。</span><span class="sxs-lookup"><span data-stu-id="5a7d9-153">The type of `londonCusts5` in the following example is IEnumerable(Of NamePhone).</span></span>  
  
     [!code-vb[VbLINQBasicOps#7](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQBasicOps/VB/Class1.vb#7)]  
  
     [!code-vb[VbLINQBasicOps#8](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQBasicOps/VB/Class1.vb#8)]  
  
 <span data-ttu-id="5a7d9-154">有关如何使用详细信息`Select`子句在 Visual Basic 中，请参阅[Select 子句](../../../../visual-basic/language-reference/queries/select-clause.md)。</span><span class="sxs-lookup"><span data-stu-id="5a7d9-154">For more information about how to use the `Select` clause in Visual Basic, see [Select Clause](../../../../visual-basic/language-reference/queries/select-clause.md).</span></span>  
  
## <a name="joining-data-join-and-group-join"></a><span data-ttu-id="5a7d9-155">联接数据 （联接和分组联接）</span><span class="sxs-lookup"><span data-stu-id="5a7d9-155">Joining Data (Join and Group Join)</span></span>  
 <span data-ttu-id="5a7d9-156">你可以组合多个数据源中的`From`几种方式的子句。</span><span class="sxs-lookup"><span data-stu-id="5a7d9-156">You can combine more than one data source in the `From` clause in several ways.</span></span> <span data-ttu-id="5a7d9-157">例如，以下代码使用两个数据源，并从它们在结果中属性隐式组合在一起。</span><span class="sxs-lookup"><span data-stu-id="5a7d9-157">For example, the following code uses two data sources and implicitly combines properties from both of them in the result.</span></span> <span data-ttu-id="5a7d9-158">该查询用于选择的学生以元音开头的姓氏和名字。</span><span class="sxs-lookup"><span data-stu-id="5a7d9-158">The query selects students whose last names start with a vowel.</span></span>  
  
 [!code-vb[VbLINQBasicOps#9](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQBasicOps/VB/Class1.vb#9)]  
  
> [!NOTE]
>  <span data-ttu-id="5a7d9-159">您可以运行此代码中创建的学生列表[如何：创建的项列表](../../../../visual-basic/programming-guide/concepts/linq/how-to-create-a-list-of-items.md)。</span><span class="sxs-lookup"><span data-stu-id="5a7d9-159">You can run this code with the list of students created in [How to: Create a List of Items](../../../../visual-basic/programming-guide/concepts/linq/how-to-create-a-list-of-items.md).</span></span>  
  
 <span data-ttu-id="5a7d9-160">`Join`关键字等效于`INNER JOIN`SQL 中。</span><span class="sxs-lookup"><span data-stu-id="5a7d9-160">The `Join` keyword is equivalent to an `INNER JOIN` in SQL.</span></span> <span data-ttu-id="5a7d9-161">它结合了两个集合根据两个集合中元素之间的匹配项的值。</span><span class="sxs-lookup"><span data-stu-id="5a7d9-161">It combines two collections based on matching key values between elements in the two collections.</span></span> <span data-ttu-id="5a7d9-162">查询将返回具有匹配的键值对集合元素的全部或部分。</span><span class="sxs-lookup"><span data-stu-id="5a7d9-162">The query returns all or part of the collection elements that have matching key values.</span></span> <span data-ttu-id="5a7d9-163">例如，下面的代码复制上一个隐式联接操作。</span><span class="sxs-lookup"><span data-stu-id="5a7d9-163">For example, the following code duplicates the action of the previous implicit join.</span></span>  
  
 [!code-vb[VbLINQBasicOps#10](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQBasicOps/VB/Class1.vb#10)]  
  
 <span data-ttu-id="5a7d9-164">`Group Join` 将集合合并为单个分层集合，就像`LEFT JOIN`SQL 中。</span><span class="sxs-lookup"><span data-stu-id="5a7d9-164">`Group Join` combines collections into a single hierarchical collection, just like a `LEFT JOIN` in SQL.</span></span> <span data-ttu-id="5a7d9-165">有关详细信息，请参阅[Join 子句](../../../../visual-basic/language-reference/queries/join-clause.md)并[Group Join 子句](../../../../visual-basic/language-reference/queries/group-join-clause.md)。</span><span class="sxs-lookup"><span data-stu-id="5a7d9-165">For more information, see [Join Clause](../../../../visual-basic/language-reference/queries/join-clause.md) and [Group Join Clause](../../../../visual-basic/language-reference/queries/group-join-clause.md).</span></span>  
  
## <a name="grouping-data-group-by"></a><span data-ttu-id="5a7d9-166">对数据进行分组 （分组依据）</span><span class="sxs-lookup"><span data-stu-id="5a7d9-166">Grouping Data (Group By)</span></span>  
 <span data-ttu-id="5a7d9-167">您可以添加`Group By`子句根据一个或多个字段的元素的查询结果中的元素进行分组。</span><span class="sxs-lookup"><span data-stu-id="5a7d9-167">You can add a `Group By` clause to group the elements in a query result according to one or more fields of the elements.</span></span> <span data-ttu-id="5a7d9-168">例如，以下代码按类年分组学生。</span><span class="sxs-lookup"><span data-stu-id="5a7d9-168">For example, the following code groups students by class year.</span></span>  
  
 [!code-vb[VbLINQBasicOps#11](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQBasicOps/VB/Class1.vb#11)]  
  
 <span data-ttu-id="5a7d9-169">如果运行此代码中使用的列表中创建的学生[如何：创建列表项](../../../../visual-basic/programming-guide/concepts/linq/how-to-create-a-list-of-items.md)，从输出`For Each`语句是：</span><span class="sxs-lookup"><span data-stu-id="5a7d9-169">If you run this code using the list of students created in [How to: Create a List of Items](../../../../visual-basic/programming-guide/concepts/linq/how-to-create-a-list-of-items.md), the output from the `For Each` statement is:</span></span>  
  
 <span data-ttu-id="5a7d9-170">年份：初级</span><span class="sxs-lookup"><span data-stu-id="5a7d9-170">Year: Junior</span></span>  
  
 <span data-ttu-id="5a7d9-171">Tucker Michael</span><span class="sxs-lookup"><span data-stu-id="5a7d9-171">Tucker, Michael</span></span>  
  
 <span data-ttu-id="5a7d9-172">Garcia Hugo</span><span class="sxs-lookup"><span data-stu-id="5a7d9-172">Garcia, Hugo</span></span>  
  
 <span data-ttu-id="5a7d9-173">Garcia Debra</span><span class="sxs-lookup"><span data-stu-id="5a7d9-173">Garcia, Debra</span></span>  
  
 <span data-ttu-id="5a7d9-174">Tucker Lance</span><span class="sxs-lookup"><span data-stu-id="5a7d9-174">Tucker, Lance</span></span>  
  
 <span data-ttu-id="5a7d9-175">年份：高级</span><span class="sxs-lookup"><span data-stu-id="5a7d9-175">Year: Senior</span></span>  
  
 <span data-ttu-id="5a7d9-176">Omelchenko, Svetlana</span><span class="sxs-lookup"><span data-stu-id="5a7d9-176">Omelchenko, Svetlana</span></span>  
  
 <span data-ttu-id="5a7d9-177">Osada Michiko</span><span class="sxs-lookup"><span data-stu-id="5a7d9-177">Osada, Michiko</span></span>  
  
 <span data-ttu-id="5a7d9-178">Fakhouri Fadi</span><span class="sxs-lookup"><span data-stu-id="5a7d9-178">Fakhouri, Fadi</span></span>  
  
 <span data-ttu-id="5a7d9-179">汉英冯</span><span class="sxs-lookup"><span data-stu-id="5a7d9-179">Feng, Hanying</span></span>  
  
 <span data-ttu-id="5a7d9-180">Terry Adams</span><span class="sxs-lookup"><span data-stu-id="5a7d9-180">Adams, Terry</span></span>  
  
 <span data-ttu-id="5a7d9-181">年份：新生</span><span class="sxs-lookup"><span data-stu-id="5a7d9-181">Year: Freshman</span></span>  
  
 <span data-ttu-id="5a7d9-182">Mortensen, Sven</span><span class="sxs-lookup"><span data-stu-id="5a7d9-182">Mortensen, Sven</span></span>  
  
 <span data-ttu-id="5a7d9-183">Garcia Cesar</span><span class="sxs-lookup"><span data-stu-id="5a7d9-183">Garcia, Cesar</span></span>  
  
 <span data-ttu-id="5a7d9-184">以下代码所示的变体订单类年，而然后按姓氏排序每个年级学生。</span><span class="sxs-lookup"><span data-stu-id="5a7d9-184">The variation shown in the following code orders the class years, and then orders the students within each year by last name.</span></span>  
  
 [!code-vb[VbLINQBasicOps#12](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQBasicOps/VB/Class1.vb#12)]  
  
 <span data-ttu-id="5a7d9-185">有关详细信息`Group By`，请参阅[组 By 子句](../../../../visual-basic/language-reference/queries/group-by-clause.md)。</span><span class="sxs-lookup"><span data-stu-id="5a7d9-185">For more information about `Group By`, see [Group By Clause](../../../../visual-basic/language-reference/queries/group-by-clause.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5a7d9-186">请参阅</span><span class="sxs-lookup"><span data-stu-id="5a7d9-186">See also</span></span>
- <xref:System.Collections.Generic.IEnumerable%601>
- [<span data-ttu-id="5a7d9-187">Visual Basic 中的 LINQ 入门</span><span class="sxs-lookup"><span data-stu-id="5a7d9-187">Getting Started with LINQ in Visual Basic</span></span>](../../../../visual-basic/programming-guide/concepts/linq/getting-started-with-linq.md)
- [<span data-ttu-id="5a7d9-188">查询</span><span class="sxs-lookup"><span data-stu-id="5a7d9-188">Queries</span></span>](../../../../visual-basic/language-reference/queries/index.md)
- [<span data-ttu-id="5a7d9-189">标准查询运算符概述 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="5a7d9-189">Standard Query Operators Overview (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/standard-query-operators-overview.md)
- [<span data-ttu-id="5a7d9-190">LINQ</span><span class="sxs-lookup"><span data-stu-id="5a7d9-190">LINQ</span></span>](../../../../visual-basic/programming-guide/language-features/linq/index.md)
