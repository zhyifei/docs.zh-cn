---
title: 基本查询操作
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
ms.openlocfilehash: efae72c65ad67b4a1b157b67dcc4d4d65f31f77b
ms.sourcegitcommit: 43d10ef65f0f1fd6c3b515e363bde11a3fcd8d6d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/04/2020
ms.locfileid: "78266373"
---
# <a name="basic-query-operations-visual-basic"></a><span data-ttu-id="0e22f-102">基本查询操作 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="0e22f-102">Basic Query Operations (Visual Basic)</span></span>
<span data-ttu-id="0e22f-103">本主题简要介绍了可视化基础知识中的语言集成查询 （LINQ） 表达式，以及您在查询中执行的一些典型操作类型。</span><span class="sxs-lookup"><span data-stu-id="0e22f-103">This topic provides a brief introduction to Language-Integrated Query (LINQ) expressions in Visual Basic, and to some of the typical kinds of operations that you perform in a query.</span></span> <span data-ttu-id="0e22f-104">有关详情，请参阅以下主题：</span><span class="sxs-lookup"><span data-stu-id="0e22f-104">For more information, see the following topics:</span></span>  
  
 [<span data-ttu-id="0e22f-105">Visual Basic 中的 LINQ 简介</span><span class="sxs-lookup"><span data-stu-id="0e22f-105">Introduction to LINQ in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)  
  
 [<span data-ttu-id="0e22f-106">查询</span><span class="sxs-lookup"><span data-stu-id="0e22f-106">Queries</span></span>](../../../../visual-basic/language-reference/queries/index.md)  
  
 [<span data-ttu-id="0e22f-107">演练：用 Visual Basic 编写查询</span><span class="sxs-lookup"><span data-stu-id="0e22f-107">Walkthrough: Writing Queries in Visual Basic</span></span>](../../../../visual-basic/programming-guide/concepts/linq/walkthrough-writing-queries.md)  
  
## <a name="specifying-the-data-source-from"></a><span data-ttu-id="0e22f-108">指定数据源（来自）</span><span class="sxs-lookup"><span data-stu-id="0e22f-108">Specifying the Data Source (From)</span></span>  
 <span data-ttu-id="0e22f-109">在 LINQ 查询中，第一步是指定要查询的数据源。</span><span class="sxs-lookup"><span data-stu-id="0e22f-109">In a LINQ query, the first step is to specify the data source that you want to query.</span></span> <span data-ttu-id="0e22f-110">因此，`From`查询中的子句始终排在第一位。</span><span class="sxs-lookup"><span data-stu-id="0e22f-110">Therefore, the `From` clause in a query always comes first.</span></span> <span data-ttu-id="0e22f-111">查询运算符根据源的类型选择和塑造结果。</span><span class="sxs-lookup"><span data-stu-id="0e22f-111">Query operators select and shape the result based on the type of the source.</span></span>  
  
 [!code-vb[VbLINQBasicOps#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQBasicOps/VB/Class1.vb#1)]  
  
 <span data-ttu-id="0e22f-112">子`From`句指定数据源`customers`和*范围变量*。 `cust`</span><span class="sxs-lookup"><span data-stu-id="0e22f-112">The `From` clause specifies the data source, `customers`, and a *range variable*, `cust`.</span></span> <span data-ttu-id="0e22f-113">范围变量类似于循环迭代变量，只不过在查询表达式中，不会发生实际迭代。</span><span class="sxs-lookup"><span data-stu-id="0e22f-113">The range variable is like a loop iteration variable, except that in a query expression, no actual iteration occurs.</span></span> <span data-ttu-id="0e22f-114">执行查询时（通常通过使用`For Each`循环）时，范围变量充当 对 中每个连续元素的`customers`引用。</span><span class="sxs-lookup"><span data-stu-id="0e22f-114">When the query is executed, often by using a `For Each` loop, the range variable serves as a reference to each successive element in `customers`.</span></span> <span data-ttu-id="0e22f-115">由于编译器可以推断 `cust` 的类型，因此无需显式指定它。</span><span class="sxs-lookup"><span data-stu-id="0e22f-115">Because the compiler can infer the type of `cust`, you do not have to specify it explicitly.</span></span> <span data-ttu-id="0e22f-116">有关使用显式键入和未进行显式键入的查询的示例，请参阅[查询操作中的类型关系（可视基本）。](../../../../visual-basic/programming-guide/concepts/linq/type-relationships-in-query-operations.md)</span><span class="sxs-lookup"><span data-stu-id="0e22f-116">For examples of queries written with and without explicit typing, see [Type Relationships in Query Operations (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/type-relationships-in-query-operations.md).</span></span>  
  
 <span data-ttu-id="0e22f-117">有关如何在 Visual Basic 中使用`From`子句的详细信息，请参阅[From 子句](../../../../visual-basic/language-reference/queries/from-clause.md)。</span><span class="sxs-lookup"><span data-stu-id="0e22f-117">For more information about how to use the `From` clause in Visual Basic, see [From Clause](../../../../visual-basic/language-reference/queries/from-clause.md).</span></span>  
  
## <a name="filtering-data-where"></a><span data-ttu-id="0e22f-118">筛选数据（在哪里）</span><span class="sxs-lookup"><span data-stu-id="0e22f-118">Filtering Data (Where)</span></span>  
 <span data-ttu-id="0e22f-119">最常见的查询操作可能是以布尔表达式的形式应用筛选器。</span><span class="sxs-lookup"><span data-stu-id="0e22f-119">Probably the most common query operation is applying a filter in the form of a Boolean expression.</span></span> <span data-ttu-id="0e22f-120">然后，查询仅返回表达式为 true 的元素。</span><span class="sxs-lookup"><span data-stu-id="0e22f-120">The query then returns only those elements for which the expression is true.</span></span> <span data-ttu-id="0e22f-121">子`Where`句用于执行筛选。</span><span class="sxs-lookup"><span data-stu-id="0e22f-121">A `Where` clause is used to perform the filtering.</span></span> <span data-ttu-id="0e22f-122">筛选器指定数据源中要包含在结果序列中的元素。</span><span class="sxs-lookup"><span data-stu-id="0e22f-122">The filter specifies which elements in the data source to include in the resulting sequence.</span></span> <span data-ttu-id="0e22f-123">在下面的示例中，仅包括在伦敦有地址的客户。</span><span class="sxs-lookup"><span data-stu-id="0e22f-123">In the following example, only those customers who have an address in London are included.</span></span>  
  
 [!code-vb[VbLINQBasicOps#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQBasicOps/VB/Class1.vb#2)]  
  
 <span data-ttu-id="0e22f-124">可以使用逻辑运算符（如 和`And``Or`）在`Where`子句中组合筛选器表达式。</span><span class="sxs-lookup"><span data-stu-id="0e22f-124">You can use logical operators such as `And` and `Or` to combine filter expressions in a `Where` clause.</span></span> <span data-ttu-id="0e22f-125">例如，要仅返回来自伦敦且名称为 Devon 的客户，请使用以下代码：</span><span class="sxs-lookup"><span data-stu-id="0e22f-125">For example, to return only those customers who are from London and whose name is Devon, use the following code:</span></span>  
  
```vb  
Where cust.City = "London" And cust.Name = "Devon"
```  
  
 <span data-ttu-id="0e22f-126">要从伦敦或巴黎返回客户，请使用以下代码：</span><span class="sxs-lookup"><span data-stu-id="0e22f-126">To return customers from London or Paris, use the following code:</span></span>  
  
```vb  
Where cust.City = "London" Or cust.City = "Paris"
```  
  
 <span data-ttu-id="0e22f-127">有关如何在 Visual Basic 中使用`Where`子句的详细信息，请参阅[子句](../../../../visual-basic/language-reference/queries/where-clause.md)的位置 。</span><span class="sxs-lookup"><span data-stu-id="0e22f-127">For more information about how to use the `Where` clause in Visual Basic, see [Where Clause](../../../../visual-basic/language-reference/queries/where-clause.md).</span></span>  
  
## <a name="ordering-data-order-by"></a><span data-ttu-id="0e22f-128">订购数据（按订单）</span><span class="sxs-lookup"><span data-stu-id="0e22f-128">Ordering Data (Order By)</span></span>  
 <span data-ttu-id="0e22f-129">将返回的数据按特定顺序排序通常很方便。</span><span class="sxs-lookup"><span data-stu-id="0e22f-129">It often is convenient to sort returned data into a particular order.</span></span> <span data-ttu-id="0e22f-130">子`Order By`句将导致返回序列中的元素在指定的字段或字段上进行排序。</span><span class="sxs-lookup"><span data-stu-id="0e22f-130">The `Order By` clause will cause the elements in the returned sequence to be sorted on a specified field or fields.</span></span> <span data-ttu-id="0e22f-131">例如，以下查询根据`Name`属性对结果进行排序。</span><span class="sxs-lookup"><span data-stu-id="0e22f-131">For example, the following query sorts the results based on the `Name` property.</span></span> <span data-ttu-id="0e22f-132">因为`Name`是一个字符串，返回的数据将按字母顺序排序，从 A 到 Z。</span><span class="sxs-lookup"><span data-stu-id="0e22f-132">Because `Name` is a string, the returned data will be sorted alphabetically, from A to Z.</span></span>  
  
 [!code-vb[VbLINQBasicOps#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQBasicOps/VB/Class1.vb#3)]  
  
 <span data-ttu-id="0e22f-133">要对结果进行从 Z 到 A 的逆序排序，请使用 `Order By...Descending` 子句。</span><span class="sxs-lookup"><span data-stu-id="0e22f-133">To order the results in reverse order, from Z to A, use the `Order By...Descending` clause.</span></span> <span data-ttu-id="0e22f-134">默认值为`Ascending`既不`Ascending`指定也不`Descending`指定时。</span><span class="sxs-lookup"><span data-stu-id="0e22f-134">The default is `Ascending` when neither `Ascending` nor `Descending` is specified.</span></span>  
  
 <span data-ttu-id="0e22f-135">有关如何在可视化基本版中使用`Order By`子句的详细信息，请参阅[按子句排序](../../../../visual-basic/language-reference/queries/order-by-clause.md)。</span><span class="sxs-lookup"><span data-stu-id="0e22f-135">For more information about how to use the `Order By` clause in Visual Basic, see [Order By Clause](../../../../visual-basic/language-reference/queries/order-by-clause.md).</span></span>  
  
## <a name="selecting-data-select"></a><span data-ttu-id="0e22f-136">选择数据（选择）</span><span class="sxs-lookup"><span data-stu-id="0e22f-136">Selecting Data (Select)</span></span>  
 <span data-ttu-id="0e22f-137">子`Select`句指定返回元素的形式和内容。</span><span class="sxs-lookup"><span data-stu-id="0e22f-137">The `Select` clause specifies the form and content of returned elements.</span></span> <span data-ttu-id="0e22f-138">例如，可以指定结果是包含完整的`Customer`对象、一个`Customer`属性、属性子集、来自各种数据源的属性的组合，还是基于计算的一些新的结果类型。</span><span class="sxs-lookup"><span data-stu-id="0e22f-138">For example, you can specify whether your results will consist of complete `Customer` objects, just one `Customer` property, a subset of properties, a combination of properties from various data sources, or some new result type based on a computation.</span></span> <span data-ttu-id="0e22f-139">当 `Select` 子句生成除源元素副本以外的内容时，该操作称为投影\*\*。</span><span class="sxs-lookup"><span data-stu-id="0e22f-139">When the `Select` clause produces something other than a copy of the source element, the operation is called a *projection*.</span></span>  
  
 <span data-ttu-id="0e22f-140">要检索由完整`Customer`对象组成的集合，请选择范围变量本身：</span><span class="sxs-lookup"><span data-stu-id="0e22f-140">To retrieve a collection that consists of complete `Customer` objects, select the range variable itself:</span></span>  
  
 [!code-vb[VbLINQBasicOps#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQBasicOps/VB/Class1.vb#4)]  
  
 <span data-ttu-id="0e22f-141">如果`Customer`实例是具有许多字段的大型对象，并且要检索的只是名称，则可以选择`cust.Name`，如下例所示。</span><span class="sxs-lookup"><span data-stu-id="0e22f-141">If a `Customer` instance is a large object that has many fields, and all that you want to retrieve is the name, you can select `cust.Name`, as shown in the following example.</span></span> <span data-ttu-id="0e22f-142">本地类型推理认识到，这将结果类型从`Customer`对象集合更改为字符串集合。</span><span class="sxs-lookup"><span data-stu-id="0e22f-142">Local type inference recognizes that this changes the result type from a collection of `Customer` objects to a collection of strings.</span></span>  
  
 [!code-vb[VbLINQBasicOps#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQBasicOps/VB/Class1.vb#5)]  
  
 <span data-ttu-id="0e22f-143">要从数据源中选择多个字段，有两种选择：</span><span class="sxs-lookup"><span data-stu-id="0e22f-143">To select multiple fields from the data source, you have two choices:</span></span>  
  
- <span data-ttu-id="0e22f-144">在子`Select`句中，指定要包含在结果中的字段。</span><span class="sxs-lookup"><span data-stu-id="0e22f-144">In the `Select` clause, specify the fields you want to include in the result.</span></span> <span data-ttu-id="0e22f-145">编译器将定义一个匿名类型，该类型以这些字段作为其属性。</span><span class="sxs-lookup"><span data-stu-id="0e22f-145">The compiler will define an anonymous type that has those fields as its properties.</span></span> <span data-ttu-id="0e22f-146">有关详细信息，请参阅[匿名类型](../../../../visual-basic/programming-guide/language-features/objects-and-classes/anonymous-types.md)。</span><span class="sxs-lookup"><span data-stu-id="0e22f-146">For more information, see [Anonymous Types](../../../../visual-basic/programming-guide/language-features/objects-and-classes/anonymous-types.md).</span></span>  
  
     <span data-ttu-id="0e22f-147">由于以下示例中返回的元素是匿名类型的实例，因此无法按代码的其他位置引用类型。</span><span class="sxs-lookup"><span data-stu-id="0e22f-147">Because the returned elements in the following example are instances of an anonymous type, you cannot refer to the type by name elsewhere in your code.</span></span> <span data-ttu-id="0e22f-148">类型的编译器指定名称包含在正常 Visual Basic 代码中无效的字符。</span><span class="sxs-lookup"><span data-stu-id="0e22f-148">The compiler-designated name for the type contains characters that are not valid in normal Visual Basic code.</span></span> <span data-ttu-id="0e22f-149">在下面的示例中，查询返回的集合中的元素`londonCusts4`是匿名类型的实例</span><span class="sxs-lookup"><span data-stu-id="0e22f-149">In the following example, the elements in the collection that is returned by the query in `londonCusts4` are instances of an anonymous type</span></span>  
  
     [!code-vb[VbLINQBasicOps#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQBasicOps/VB/Class1.vb#6)]  
  
     <span data-ttu-id="0e22f-150">-或-</span><span class="sxs-lookup"><span data-stu-id="0e22f-150">-or-</span></span>  
  
- <span data-ttu-id="0e22f-151">定义包含要包含在结果中的特定字段的命名类型，并在`Select`子句中创建和初始化该类型的实例。</span><span class="sxs-lookup"><span data-stu-id="0e22f-151">Define a named type that contains the particular fields that you want to include in the result, and create and initialize instances of the type in the `Select` clause.</span></span> <span data-ttu-id="0e22f-152">仅当必须使用返回结果的集合之外的单个结果，或者您必须在方法调用中将它们作为参数传递时，才使用此选项。</span><span class="sxs-lookup"><span data-stu-id="0e22f-152">Use this option only if you have to use individual results outside the collection in which they are returned, or if you have to pass them as parameters in method calls.</span></span> <span data-ttu-id="0e22f-153">以下示例中的类型`londonCusts5`为 IE无枚（NamePhone）。</span><span class="sxs-lookup"><span data-stu-id="0e22f-153">The type of `londonCusts5` in the following example is IEnumerable(Of NamePhone).</span></span>  
  
     [!code-vb[VbLINQBasicOps#7](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQBasicOps/VB/Class1.vb#7)]  
  
     [!code-vb[VbLINQBasicOps#8](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQBasicOps/VB/Class1.vb#8)]  
  
 <span data-ttu-id="0e22f-154">有关如何在 Visual Basic 中使用`Select`子句的详细信息，请参阅[选择子句](../../../../visual-basic/language-reference/queries/select-clause.md)。</span><span class="sxs-lookup"><span data-stu-id="0e22f-154">For more information about how to use the `Select` clause in Visual Basic, see [Select Clause](../../../../visual-basic/language-reference/queries/select-clause.md).</span></span>  
  
## <a name="joining-data-join-and-group-join"></a><span data-ttu-id="0e22f-155">加入数据（加入和组加入）</span><span class="sxs-lookup"><span data-stu-id="0e22f-155">Joining Data (Join and Group Join)</span></span>  
 <span data-ttu-id="0e22f-156">您可以通过多种方式将`From`子句中的多个数据源合并。</span><span class="sxs-lookup"><span data-stu-id="0e22f-156">You can combine more than one data source in the `From` clause in several ways.</span></span> <span data-ttu-id="0e22f-157">例如，以下代码使用两个数据源，并在结果中隐式合并两个数据源的属性。</span><span class="sxs-lookup"><span data-stu-id="0e22f-157">For example, the following code uses two data sources and implicitly combines properties from both of them in the result.</span></span> <span data-ttu-id="0e22f-158">查询选择姓氏以元音开头的学生。</span><span class="sxs-lookup"><span data-stu-id="0e22f-158">The query selects students whose last names start with a vowel.</span></span>  
  
 [!code-vb[VbLINQBasicOps#9](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQBasicOps/VB/Class1.vb#9)]  
  
> [!NOTE]
> <span data-ttu-id="0e22f-159">您可以使用在["如何：创建项目列表](../../../../visual-basic/programming-guide/concepts/linq/how-to-create-a-list-of-items.md)"中创建的学生列表运行此代码。</span><span class="sxs-lookup"><span data-stu-id="0e22f-159">You can run this code with the list of students created in [How to: Create a List of Items](../../../../visual-basic/programming-guide/concepts/linq/how-to-create-a-list-of-items.md).</span></span>  
  
 <span data-ttu-id="0e22f-160">关键字`Join`等效于 SQL`INNER JOIN`中。</span><span class="sxs-lookup"><span data-stu-id="0e22f-160">The `Join` keyword is equivalent to an `INNER JOIN` in SQL.</span></span> <span data-ttu-id="0e22f-161">它基于两个集合中元素之间的匹配键值组合两个集合。</span><span class="sxs-lookup"><span data-stu-id="0e22f-161">It combines two collections based on matching key values between elements in the two collections.</span></span> <span data-ttu-id="0e22f-162">查询返回具有匹配键值的全部或部分集合元素。</span><span class="sxs-lookup"><span data-stu-id="0e22f-162">The query returns all or part of the collection elements that have matching key values.</span></span> <span data-ttu-id="0e22f-163">例如，以下代码复制前一个隐式联接的操作。</span><span class="sxs-lookup"><span data-stu-id="0e22f-163">For example, the following code duplicates the action of the previous implicit join.</span></span>  
  
 [!code-vb[VbLINQBasicOps#10](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQBasicOps/VB/Class1.vb#10)]  
  
 <span data-ttu-id="0e22f-164">`Group Join`将集合合并到单个分层集合中，就像`LEFT JOIN`SQL 中的集合一样。</span><span class="sxs-lookup"><span data-stu-id="0e22f-164">`Group Join` combines collections into a single hierarchical collection, just like a `LEFT JOIN` in SQL.</span></span> <span data-ttu-id="0e22f-165">有关详细信息，请参阅[加入子句](../../../../visual-basic/language-reference/queries/join-clause.md)和[组加入子句](../../../../visual-basic/language-reference/queries/group-join-clause.md)。</span><span class="sxs-lookup"><span data-stu-id="0e22f-165">For more information, see [Join Clause](../../../../visual-basic/language-reference/queries/join-clause.md) and [Group Join Clause](../../../../visual-basic/language-reference/queries/group-join-clause.md).</span></span>  
  
## <a name="grouping-data-group-by"></a><span data-ttu-id="0e22f-166">分组数据（分组）</span><span class="sxs-lookup"><span data-stu-id="0e22f-166">Grouping Data (Group By)</span></span>  
 <span data-ttu-id="0e22f-167">您可以根据元素的`Group By`一个或多个字段添加子句来对查询结果中的元素进行分组。</span><span class="sxs-lookup"><span data-stu-id="0e22f-167">You can add a `Group By` clause to group the elements in a query result according to one or more fields of the elements.</span></span> <span data-ttu-id="0e22f-168">例如，以下代码按班级年份对学生进行分组。</span><span class="sxs-lookup"><span data-stu-id="0e22f-168">For example, the following code groups students by class year.</span></span>  
  
 [!code-vb[VbLINQBasicOps#11](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQBasicOps/VB/Class1.vb#11)]  
  
 <span data-ttu-id="0e22f-169">如果使用"[如何创建：创建项目列表"](../../../../visual-basic/programming-guide/concepts/linq/how-to-create-a-list-of-items.md)中创建的学生列表运行此代码，则语句中的`For Each`输出为：</span><span class="sxs-lookup"><span data-stu-id="0e22f-169">If you run this code using the list of students created in [How to: Create a List of Items](../../../../visual-basic/programming-guide/concepts/linq/how-to-create-a-list-of-items.md), the output from the `For Each` statement is:</span></span>  
  
 <span data-ttu-id="0e22f-170">年： 初级</span><span class="sxs-lookup"><span data-stu-id="0e22f-170">Year: Junior</span></span>  
  
 <span data-ttu-id="0e22f-171">塔克， 迈克尔</span><span class="sxs-lookup"><span data-stu-id="0e22f-171">Tucker, Michael</span></span>  
  
 <span data-ttu-id="0e22f-172">加西亚， 雨果</span><span class="sxs-lookup"><span data-stu-id="0e22f-172">Garcia, Hugo</span></span>  
  
 <span data-ttu-id="0e22f-173">加西亚， 黛布拉</span><span class="sxs-lookup"><span data-stu-id="0e22f-173">Garcia, Debra</span></span>  
  
 <span data-ttu-id="0e22f-174">塔克， 兰斯</span><span class="sxs-lookup"><span data-stu-id="0e22f-174">Tucker, Lance</span></span>  
  
 <span data-ttu-id="0e22f-175">年份： 高级</span><span class="sxs-lookup"><span data-stu-id="0e22f-175">Year: Senior</span></span>  
  
 <span data-ttu-id="0e22f-176">奥梅利琴科， 斯韦特兰娜</span><span class="sxs-lookup"><span data-stu-id="0e22f-176">Omelchenko, Svetlana</span></span>  
  
 <span data-ttu-id="0e22f-177">奥萨达， 米奇科</span><span class="sxs-lookup"><span data-stu-id="0e22f-177">Osada, Michiko</span></span>  
  
 <span data-ttu-id="0e22f-178">法库里， 法迪</span><span class="sxs-lookup"><span data-stu-id="0e22f-178">Fakhouri, Fadi</span></span>  
  
 <span data-ttu-id="0e22f-179">冯汉英</span><span class="sxs-lookup"><span data-stu-id="0e22f-179">Feng, Hanying</span></span>  
  
 <span data-ttu-id="0e22f-180">亚当斯， 特里</span><span class="sxs-lookup"><span data-stu-id="0e22f-180">Adams, Terry</span></span>  
  
 <span data-ttu-id="0e22f-181">年份： 新生</span><span class="sxs-lookup"><span data-stu-id="0e22f-181">Year: Freshman</span></span>  
  
 <span data-ttu-id="0e22f-182">莫滕森， 斯文</span><span class="sxs-lookup"><span data-stu-id="0e22f-182">Mortensen, Sven</span></span>  
  
 <span data-ttu-id="0e22f-183">加西亚， 塞萨尔</span><span class="sxs-lookup"><span data-stu-id="0e22f-183">Garcia, Cesar</span></span>  
  
 <span data-ttu-id="0e22f-184">以下代码中显示的变体对班级年数进行排序，然后按姓氏每年对学生进行订单。</span><span class="sxs-lookup"><span data-stu-id="0e22f-184">The variation shown in the following code orders the class years, and then orders the students within each year by last name.</span></span>  
  
 [!code-vb[VbLINQBasicOps#12](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQBasicOps/VB/Class1.vb#12)]  
  
 <span data-ttu-id="0e22f-185">有关 的详细信息`Group By`，请参阅[按子项分组](../../../../visual-basic/language-reference/queries/group-by-clause.md)。</span><span class="sxs-lookup"><span data-stu-id="0e22f-185">For more information about `Group By`, see [Group By Clause](../../../../visual-basic/language-reference/queries/group-by-clause.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0e22f-186">另请参阅</span><span class="sxs-lookup"><span data-stu-id="0e22f-186">See also</span></span>

- <xref:System.Collections.Generic.IEnumerable%601>
- [<span data-ttu-id="0e22f-187">Visual Basic 中的 LINQ 入门</span><span class="sxs-lookup"><span data-stu-id="0e22f-187">Getting Started with LINQ in Visual Basic</span></span>](../../../../visual-basic/programming-guide/concepts/linq/getting-started-with-linq.md)
- [<span data-ttu-id="0e22f-188">查询</span><span class="sxs-lookup"><span data-stu-id="0e22f-188">Queries</span></span>](../../../../visual-basic/language-reference/queries/index.md)
- [<span data-ttu-id="0e22f-189">标准查询运算符概述 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="0e22f-189">Standard Query Operators Overview (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/standard-query-operators-overview.md)
- [<span data-ttu-id="0e22f-190">Linq</span><span class="sxs-lookup"><span data-stu-id="0e22f-190">LINQ</span></span>](../../../../visual-basic/programming-guide/language-features/linq/index.md)
