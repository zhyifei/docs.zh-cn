---
title: 查询操作中的类型关系 (Visual Basic)
ms.custom: ''
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- variable relationships [LINQ in Visual Basic]
- type information inferred [LINQ in Visual Basic]
- type relationships [LINQ in Visual Basic]
- queries [LINQ in Visual Basic], type relationships
- data sources [LINQ in Visual Basic], type relationships
- LINQ [Visual Basic], type relationships
- inferring type information [LINQ in Visual Basic]
- relationships [LINQ in Visual Basic]
ms.assetid: b5ff4da5-f3fd-4a8e-aaac-1cbf52fa16f6
caps.latest.revision: 34
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: e38f51d77869dcca8a81fdcbc70aed32c4146935
ms.sourcegitcommit: 86adcc06e35390f13c1e372c36d2e044f1fc31ef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/26/2018
---
# <a name="type-relationships-in-query-operations-visual-basic"></a><span data-ttu-id="c76fb-102">查询操作中的类型关系 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="c76fb-102">Type Relationships in Query Operations (Visual Basic)</span></span>
<span data-ttu-id="c76fb-103">在中使用变量[!INCLUDE[vbteclinqext](~/includes/vbteclinqext-md.md)]查询操作强类型和必须彼此兼容。</span><span class="sxs-lookup"><span data-stu-id="c76fb-103">Variables used in [!INCLUDE[vbteclinqext](~/includes/vbteclinqext-md.md)] query operations are strongly typed and must be compatible with each other.</span></span> <span data-ttu-id="c76fb-104">数据源中、 在查询本身、 和的查询执行过程中，都使用强类型。</span><span class="sxs-lookup"><span data-stu-id="c76fb-104">Strong typing is used in the data source, in the query itself, and in the query execution.</span></span> <span data-ttu-id="c76fb-105">下图列出术语用于描述[!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)]查询。</span><span class="sxs-lookup"><span data-stu-id="c76fb-105">The following illustration identifies terms used to describe a [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] query.</span></span> <span data-ttu-id="c76fb-106">有关查询的部件的详细信息，请参阅[基本查询操作 (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/basic-query-operations.md)。</span><span class="sxs-lookup"><span data-stu-id="c76fb-106">For more information about the parts of a query, see [Basic Query Operations (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/basic-query-operations.md).</span></span>  
  
 <span data-ttu-id="c76fb-107">![具有突出显示的元素的伪代码查询。] (../../../../visual-basic/programming-guide/concepts/linq/media/sjltyperels.png "SJLtypeRels")</span><span class="sxs-lookup"><span data-stu-id="c76fb-107">![Pseudocode query with elements highlighted.](../../../../visual-basic/programming-guide/concepts/linq/media/sjltyperels.png "SJLtypeRels")</span></span>  
<span data-ttu-id="c76fb-108">LINQ 查询部分</span><span class="sxs-lookup"><span data-stu-id="c76fb-108">Parts of a LINQ query</span></span>  
  
 <span data-ttu-id="c76fb-109">在查询中的范围变量的类型必须与数据源中元素的类型兼容。</span><span class="sxs-lookup"><span data-stu-id="c76fb-109">The type of the range variable in the query must be compatible with the type of the elements in the data source.</span></span> <span data-ttu-id="c76fb-110">查询变量的类型必须与在中定义的序列元素兼容`Select`子句。</span><span class="sxs-lookup"><span data-stu-id="c76fb-110">The type of the query variable must be compatible with the sequence element defined in the `Select` clause.</span></span> <span data-ttu-id="c76fb-111">最后，序列元素的类型也必须与兼容的类型中使用的循环控制变量`For Each`执行查询的语句。</span><span class="sxs-lookup"><span data-stu-id="c76fb-111">Finally, the type of the sequence elements also must be compatible with the type of the loop control variable that is used in the `For Each` statement that executes the query.</span></span> <span data-ttu-id="c76fb-112">此强类型便于在编译时类型错误的标识。</span><span class="sxs-lookup"><span data-stu-id="c76fb-112">This strong typing facilitates identification of type errors at compile time.</span></span>  
  
 <span data-ttu-id="c76fb-113">Visual Basic，使强类型便捷通过也称为实现本地类型推断、*隐式类型化*。</span><span class="sxs-lookup"><span data-stu-id="c76fb-113">Visual Basic makes strong typing convenient by implementing local type inference, also known as *implicit typing*.</span></span> <span data-ttu-id="c76fb-114">在前面的示例中，使用功能，你将看到它使用在整个[!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)]示例和文档。</span><span class="sxs-lookup"><span data-stu-id="c76fb-114">That feature is used in the previous example, and you will see it used throughout the [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] samples and documentation.</span></span> <span data-ttu-id="c76fb-115">在 Visual Basic，局部类型推理实现只需通过使用`Dim`语句而不用`As`子句。</span><span class="sxs-lookup"><span data-stu-id="c76fb-115">In Visual Basic, local type inference is accomplished simply by using a `Dim` statement without an `As` clause.</span></span> <span data-ttu-id="c76fb-116">在下面的示例中，`city`强类型化为一个字符串。</span><span class="sxs-lookup"><span data-stu-id="c76fb-116">In the following example, `city` is strongly typed as a string.</span></span>  
  
 [!code-vb[VbLINQTypeRels#1](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/type-relationships-in-query-operations_1.vb)]  
  
> [!NOTE]
>  <span data-ttu-id="c76fb-117">局部类型推理时才起作用`Option Infer`设置为`On`。</span><span class="sxs-lookup"><span data-stu-id="c76fb-117">Local type inference works only when `Option Infer` is set to `On`.</span></span> <span data-ttu-id="c76fb-118">有关详细信息，请参阅[Option Infer 语句](../../../../visual-basic/language-reference/statements/option-infer-statement.md)。</span><span class="sxs-lookup"><span data-stu-id="c76fb-118">For more information, see [Option Infer Statement](../../../../visual-basic/language-reference/statements/option-infer-statement.md).</span></span>  
  
 <span data-ttu-id="c76fb-119">但是，即使在查询中使用局部类型推理时，也没有数据源中的变量、 查询变量和查询执行循环相同的类型关系。</span><span class="sxs-lookup"><span data-stu-id="c76fb-119">However, even if you use local type inference in a query, the same type relationships are present among the variables in the data source, the query variable, and the query execution loop.</span></span> <span data-ttu-id="c76fb-120">可用于具有这些类型关系的一个基本的了解，在编写时[!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)]查询或使用的示例和文档中的代码示例。</span><span class="sxs-lookup"><span data-stu-id="c76fb-120">It is useful to have a basic understanding of these type relationships when you are writing [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] queries, or working with the samples and code examples in the documentation.</span></span>  
  
 <span data-ttu-id="c76fb-121">你可能需要指定从数据源返回的类型不匹配的范围变量显式类型。</span><span class="sxs-lookup"><span data-stu-id="c76fb-121">You may need to specify an explicit type for a range variable that does not match the type returned from the data source.</span></span> <span data-ttu-id="c76fb-122">你可以通过使用指定的范围变量的类型`As`子句。</span><span class="sxs-lookup"><span data-stu-id="c76fb-122">You can specify the type of the range variable by using an `As` clause.</span></span> <span data-ttu-id="c76fb-123">但是，这会导致出现错误转换是否[收缩转换](../../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md)和`Option Strict`设置为`On`。</span><span class="sxs-lookup"><span data-stu-id="c76fb-123">However, this results in an error if the conversion is a [narrowing conversion](../../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md) and `Option Strict` is set to `On`.</span></span> <span data-ttu-id="c76fb-124">因此，我们建议在从数据源检索到的值上执行转换。</span><span class="sxs-lookup"><span data-stu-id="c76fb-124">Therefore, we recommend that you perform the conversion on the values retrieved from the data source.</span></span> <span data-ttu-id="c76fb-125">你可以将值转换从数据源为显式范围变量类型使用<xref:System.Linq.Enumerable.Cast%2A>方法。</span><span class="sxs-lookup"><span data-stu-id="c76fb-125">You can convert the values from the data source to the explicit range variable type by using the <xref:System.Linq.Enumerable.Cast%2A> method.</span></span> <span data-ttu-id="c76fb-126">此外可以强制转换中选定的值`Select`子句的显式类型的范围变量的类型不同。</span><span class="sxs-lookup"><span data-stu-id="c76fb-126">You can also cast the values selected in the `Select` clause to an explicit type that is different from the type of the range variable.</span></span> <span data-ttu-id="c76fb-127">这些点下面的代码所示。</span><span class="sxs-lookup"><span data-stu-id="c76fb-127">These points are illustrated in the following code.</span></span>  
  
 [!code-vb[VbLINQTypeRels#4](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/type-relationships-in-query-operations_2.vb)]  
  
## <a name="queries-that-return-entire-elements-of-the-source-data"></a><span data-ttu-id="c76fb-128">查询返回的源数据的整个元素</span><span class="sxs-lookup"><span data-stu-id="c76fb-128">Queries That Return Entire Elements of the Source Data</span></span>  
 <span data-ttu-id="c76fb-129">下面的示例演示[!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)]查询返回的源数据中的选定元素的序列的操作。</span><span class="sxs-lookup"><span data-stu-id="c76fb-129">The following example shows a [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] query operation that returns a sequence of elements selected from the source data.</span></span> <span data-ttu-id="c76fb-130">源， `names`，包含数组的字符串，并将查询输出是一个序列包含以字母 M 开头的字符串。</span><span class="sxs-lookup"><span data-stu-id="c76fb-130">The source, `names`, contains an array of strings, and the query output is a sequence containing strings that start with the letter M.</span></span>  
  
 [!code-vb[VbLINQTypeRels#2](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/type-relationships-in-query-operations_3.vb)]  
  
 <span data-ttu-id="c76fb-131">这等效于下面的代码，但得更短且更易于编写。</span><span class="sxs-lookup"><span data-stu-id="c76fb-131">This is equivalent to the following code, but is much shorter and easier to write.</span></span> <span data-ttu-id="c76fb-132">依赖于在查询中的局部类型推理是在 Visual Basic 中的首选的样式。</span><span class="sxs-lookup"><span data-stu-id="c76fb-132">Reliance on local type inference in queries is the preferred style in Visual Basic.</span></span>  
  
 [!code-vb[VbLINQTypeRels#3](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/type-relationships-in-query-operations_4.vb)]  
  
 <span data-ttu-id="c76fb-133">在这两个前面的代码示例中，情况下，是否隐式或显式类型确定存在下面的关系。</span><span class="sxs-lookup"><span data-stu-id="c76fb-133">The following relationships exist in both of the previous code examples, whether the types are determined implicitly or explicitly.</span></span>  
  
1.  <span data-ttu-id="c76fb-134">数据源中元素的类型`names`，是一种范围变量`name`，在查询中。</span><span class="sxs-lookup"><span data-stu-id="c76fb-134">The type of the elements in the data source, `names`, is the type of the range variable, `name`, in the query.</span></span>  
  
2.  <span data-ttu-id="c76fb-135">选择后，该对象的类型`name`，确定查询变量的类型`mNames`。</span><span class="sxs-lookup"><span data-stu-id="c76fb-135">The type of the object that is selected, `name`, determines the type of the query variable, `mNames`.</span></span> <span data-ttu-id="c76fb-136">此处`name`是一个字符串，因此查询变量是在 Visual Basic 中的 IEnumerable (Of 字符串）。</span><span class="sxs-lookup"><span data-stu-id="c76fb-136">Here `name` is a string, so the query variable is IEnumerable(Of String) in Visual Basic.</span></span>  
  
3.  <span data-ttu-id="c76fb-137">中定义的查询`mNames`中执行`For Each`循环。</span><span class="sxs-lookup"><span data-stu-id="c76fb-137">The query defined in `mNames` is executed in the `For Each` loop.</span></span> <span data-ttu-id="c76fb-138">循环将循环访问执行查询的结果。</span><span class="sxs-lookup"><span data-stu-id="c76fb-138">The loop iterates over the result of executing the query.</span></span> <span data-ttu-id="c76fb-139">因为`mNames`，它执行时，将返回一个字符串，循环迭代变量，序列`nm`，也是一个字符串。</span><span class="sxs-lookup"><span data-stu-id="c76fb-139">Because `mNames`, when it is executed, will return a sequence of strings, the loop iteration variable, `nm`, also is a string.</span></span>  
  
## <a name="queries-that-return-one-field-from-selected-elements"></a><span data-ttu-id="c76fb-140">返回从所选元素的一个字段的查询</span><span class="sxs-lookup"><span data-stu-id="c76fb-140">Queries That Return One Field from Selected Elements</span></span>  
 <span data-ttu-id="c76fb-141">下面的示例演示[!INCLUDE[vbtecdlinq](~/includes/vbtecdlinq-md.md)]查询返回包含只有一个属于从数据源选择每个元素的序列的操作。</span><span class="sxs-lookup"><span data-stu-id="c76fb-141">The following example shows a [!INCLUDE[vbtecdlinq](~/includes/vbtecdlinq-md.md)] query operation that returns a sequence containing only one part of each element selected from the data source.</span></span> <span data-ttu-id="c76fb-142">查询采用集合`Customer`对象，以作为其数据源，并仅投影`Name`结果中的属性。</span><span class="sxs-lookup"><span data-stu-id="c76fb-142">The query takes a collection of `Customer` objects as its data source and projects only the `Name` property in the result.</span></span> <span data-ttu-id="c76fb-143">客户名称是一个字符串，因为此查询将生成一个序列的字符串作为输出。</span><span class="sxs-lookup"><span data-stu-id="c76fb-143">Because the customer name is a string, the query produces a sequence of strings as output.</span></span>  
  
```vb  
' Method GetTable returns a table of Customer objects.  
Dim customers = db.GetTable(Of Customer)()  
Dim custNames = From cust In customers   
                Where cust.City = "London"   
                Select cust.Name  
  
For Each custName In custNames  
    Console.WriteLine(custName)  
Next  
```  
  
 <span data-ttu-id="c76fb-144">变量之间的关系是类似于更简单的示例中。</span><span class="sxs-lookup"><span data-stu-id="c76fb-144">The relationships between variables are like those in the simpler example.</span></span>  
  
1.  <span data-ttu-id="c76fb-145">数据源中元素的类型`customers`，是一种范围变量`cust`，在查询中。</span><span class="sxs-lookup"><span data-stu-id="c76fb-145">The type of the elements in the data source, `customers`, is the type of the range variable, `cust`, in the query.</span></span> <span data-ttu-id="c76fb-146">在此示例中，该类型为`Customer`。</span><span class="sxs-lookup"><span data-stu-id="c76fb-146">In this example, that type is `Customer`.</span></span>  
  
2.  <span data-ttu-id="c76fb-147">`Select`语句返回`Name`每个属性`Customer`而不是整个对象的对象。</span><span class="sxs-lookup"><span data-stu-id="c76fb-147">The `Select` statement returns the `Name` property of each `Customer` object instead of the whole object.</span></span> <span data-ttu-id="c76fb-148">因为`Name`是一个字符串，查询变量， `custNames`，将再次 IEnumerable (Of 字符串），不能的`Customer`。</span><span class="sxs-lookup"><span data-stu-id="c76fb-148">Because `Name` is a string, the query variable, `custNames`, will again be IEnumerable(Of String), not of `Customer`.</span></span>  
  
3.  <span data-ttu-id="c76fb-149">因为`custNames`表示一个字符串，序列`For Each`循环的迭代变量`custName`，必须是字符串。</span><span class="sxs-lookup"><span data-stu-id="c76fb-149">Because `custNames` represents a sequence of strings, the `For Each` loop's iteration variable, `custName`, must be a string.</span></span>  
  
 <span data-ttu-id="c76fb-150">如果没有本地类型推断、 前面的示例将比较麻烦，若要编写，若要了解，如以下示例所示。</span><span class="sxs-lookup"><span data-stu-id="c76fb-150">Without local type inference, the previous example would be more cumbersome to write and to understand, as the following example shows.</span></span>  
  
```vb  
' Method GetTable returns a table of Customer objects.  
 Dim customers As Table(Of Customer) = db.GetTable(Of Customer)()  
 Dim custNames As IEnumerable(Of String) =  
     From cust As Customer In customers   
     Where cust.City = "London"   
     Select cust.Name  
  
 For Each custName As String In custNames  
     Console.WriteLine(custName)  
 Next  
```  
  
## <a name="queries-that-require-anonymous-types"></a><span data-ttu-id="c76fb-151">需要匿名类型的查询</span><span class="sxs-lookup"><span data-stu-id="c76fb-151">Queries That Require Anonymous Types</span></span>  
 <span data-ttu-id="c76fb-152">下面的示例演示更复杂的情况。</span><span class="sxs-lookup"><span data-stu-id="c76fb-152">The following example shows a more complex situation.</span></span> <span data-ttu-id="c76fb-153">在前面的示例中，已显式指定类型的所有变量很不方便。</span><span class="sxs-lookup"><span data-stu-id="c76fb-153">In the previous example, it was inconvenient to specify types for all the variables explicitly.</span></span> <span data-ttu-id="c76fb-154">在此示例中，不可能。</span><span class="sxs-lookup"><span data-stu-id="c76fb-154">In this example, it is impossible.</span></span> <span data-ttu-id="c76fb-155">而不是选择整个`Customer`从数据源或单个字段从每个元素的元素`Select`子句在此查询将返回两个属性的原始`Customer`对象：`Name`和`City`。</span><span class="sxs-lookup"><span data-stu-id="c76fb-155">Instead of selecting entire `Customer` elements from the data source, or a single field from each element, the `Select` clause in this query returns two properties of the original `Customer` object: `Name` and `City`.</span></span> <span data-ttu-id="c76fb-156">以响应`Select`子句，编译器定义包含这两个属性的匿名类型。</span><span class="sxs-lookup"><span data-stu-id="c76fb-156">In response to the `Select` clause, the compiler defines an anonymous type that contains those two properties.</span></span> <span data-ttu-id="c76fb-157">执行的结果`nameCityQuery`中`For Each`循环是一套新的匿名类型的实例。</span><span class="sxs-lookup"><span data-stu-id="c76fb-157">The result of executing `nameCityQuery` in the `For Each` loop is a collection of instances of the new anonymous type.</span></span> <span data-ttu-id="c76fb-158">因为匿名类型具有没有可用的名称，则无法指定的类型`nameCityQuery`或`custInfo`显式。</span><span class="sxs-lookup"><span data-stu-id="c76fb-158">Because the anonymous type has no usable name, you cannot specify the type of `nameCityQuery` or `custInfo` explicitly.</span></span> <span data-ttu-id="c76fb-159">这就是，使用匿名类型，具有任何类型名称来代替了`String`中`IEnumerable(Of String)`。</span><span class="sxs-lookup"><span data-stu-id="c76fb-159">That is, with an anonymous type, you have no type name to use in place of `String` in `IEnumerable(Of String)`.</span></span> <span data-ttu-id="c76fb-160">有关详细信息，请参阅[匿名类型](../../../../visual-basic/programming-guide/language-features/objects-and-classes/anonymous-types.md)。</span><span class="sxs-lookup"><span data-stu-id="c76fb-160">For more information, see [Anonymous Types](../../../../visual-basic/programming-guide/language-features/objects-and-classes/anonymous-types.md).</span></span>  
  
```vb  
' Method GetTable returns a table of Customer objects.  
Dim customers = db.GetTable(Of Customer)()  
Dim nameCityQuery = From cust In customers   
                    Where cust.City = "London"   
                    Select cust.Name, cust.City  
  
For Each custInfo In nameCityQuery  
    Console.WriteLine(custInfo.Name)  
Next  
```  
  
 <span data-ttu-id="c76fb-161">尽管不能在前面的示例中指定的所有变量的类型，但关系保持不变。</span><span class="sxs-lookup"><span data-stu-id="c76fb-161">Although it is not possible to specify types for all the variables in the previous example, the relationships remain the same.</span></span>  
  
1.  <span data-ttu-id="c76fb-162">数据源中元素的类型又中查询的范围变量的类型。</span><span class="sxs-lookup"><span data-stu-id="c76fb-162">The type of the elements in the data source is again the type of the range variable in the query.</span></span> <span data-ttu-id="c76fb-163">在此示例中，`cust`是的一个实例`Customer`。</span><span class="sxs-lookup"><span data-stu-id="c76fb-163">In this example, `cust` is an instance of `Customer`.</span></span>  
  
2.  <span data-ttu-id="c76fb-164">因为`Select`语句生成的匿名类型，查询变量， `nameCityQuery`，必须以匿名类型隐式键入。</span><span class="sxs-lookup"><span data-stu-id="c76fb-164">Because the `Select` statement produces an anonymous type, the query variable, `nameCityQuery`, must be implicitly typed as an anonymous type.</span></span> <span data-ttu-id="c76fb-165">匿名类型没有可用的名称，因此不能显式指定。</span><span class="sxs-lookup"><span data-stu-id="c76fb-165">An anonymous type has no usable name, and therefore cannot be specified explicitly.</span></span>  
  
3.  <span data-ttu-id="c76fb-166">中的迭代变量的类型`For Each`循环是在步骤 2 中创建的匿名类型。</span><span class="sxs-lookup"><span data-stu-id="c76fb-166">The type of the iteration variable in the `For Each` loop is the anonymous type created in step 2.</span></span> <span data-ttu-id="c76fb-167">因为该类型具有没有可用的名称，则必须隐式确定循环迭代变量的类型。</span><span class="sxs-lookup"><span data-stu-id="c76fb-167">Because the type has no usable name, the type of the loop iteration variable must be determined implicitly.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c76fb-168">请参阅</span><span class="sxs-lookup"><span data-stu-id="c76fb-168">See Also</span></span>  
 [<span data-ttu-id="c76fb-169">Visual Basic 中的 LINQ 入门</span><span class="sxs-lookup"><span data-stu-id="c76fb-169">Getting Started with LINQ in Visual Basic</span></span>](../../../../visual-basic/programming-guide/concepts/linq/getting-started-with-linq.md)  
 [<span data-ttu-id="c76fb-170">匿名类型</span><span class="sxs-lookup"><span data-stu-id="c76fb-170">Anonymous Types</span></span>](../../../../visual-basic/programming-guide/language-features/objects-and-classes/anonymous-types.md)  
 [<span data-ttu-id="c76fb-171">局部类型推理</span><span class="sxs-lookup"><span data-stu-id="c76fb-171">Local Type Inference</span></span>](../../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md)  
 [<span data-ttu-id="c76fb-172">Visual Basic 中的 LINQ 简介</span><span class="sxs-lookup"><span data-stu-id="c76fb-172">Introduction to LINQ in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)  
 [<span data-ttu-id="c76fb-173">LINQ</span><span class="sxs-lookup"><span data-stu-id="c76fb-173">LINQ</span></span>](../../../../visual-basic/programming-guide/language-features/linq/index.md)  
 [<span data-ttu-id="c76fb-174">查询</span><span class="sxs-lookup"><span data-stu-id="c76fb-174">Queries</span></span>](../../../../visual-basic/language-reference/queries/queries.md)
