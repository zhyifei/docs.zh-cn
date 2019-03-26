---
title: 查询操作中的类型关系 (Visual Basic)
ms.date: 07/20/2015
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
ms.openlocfilehash: 4dc5497f2e9bacac3062fde6e7dc48270697f1df
ms.sourcegitcommit: 7156c0b9e4ce4ce5ecf48ce3d925403b638b680c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/26/2019
ms.locfileid: "58465212"
---
# <a name="type-relationships-in-query-operations-visual-basic"></a><span data-ttu-id="28889-102">查询操作中的类型关系 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="28889-102">Type Relationships in Query Operations (Visual Basic)</span></span>
<span data-ttu-id="28889-103">中使用的变量[!INCLUDE[vbteclinqext](~/includes/vbteclinqext-md.md)]查询操作为强类型，必须相互兼容。</span><span class="sxs-lookup"><span data-stu-id="28889-103">Variables used in [!INCLUDE[vbteclinqext](~/includes/vbteclinqext-md.md)] query operations are strongly typed and must be compatible with each other.</span></span> <span data-ttu-id="28889-104">数据源中、 查询本身，以及在查询执行过程中，使用强类型化。</span><span class="sxs-lookup"><span data-stu-id="28889-104">Strong typing is used in the data source, in the query itself, and in the query execution.</span></span> <span data-ttu-id="28889-105">下图标识术语用于描述[!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)]查询。</span><span class="sxs-lookup"><span data-stu-id="28889-105">The following illustration identifies terms used to describe a [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] query.</span></span> <span data-ttu-id="28889-106">有关查询的部分的详细信息，请参阅[基本查询操作 (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/basic-query-operations.md)。</span><span class="sxs-lookup"><span data-stu-id="28889-106">For more information about the parts of a query, see [Basic Query Operations (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/basic-query-operations.md).</span></span>  
  
 ![显示与突出显示的元素的伪代码查询屏幕截图。](./media/type-relationships-in-query-operations/linq-query-description-terms.png)  
  
 <span data-ttu-id="28889-108">在查询中范围变量的类型必须与数据源中的元素的类型兼容。</span><span class="sxs-lookup"><span data-stu-id="28889-108">The type of the range variable in the query must be compatible with the type of the elements in the data source.</span></span> <span data-ttu-id="28889-109">查询变量的类型必须与在中定义的序列元素兼容`Select`子句。</span><span class="sxs-lookup"><span data-stu-id="28889-109">The type of the query variable must be compatible with the sequence element defined in the `Select` clause.</span></span> <span data-ttu-id="28889-110">最后，序列元素的类型还必须与兼容的类型中使用循环控制变量`For Each`执行查询的语句。</span><span class="sxs-lookup"><span data-stu-id="28889-110">Finally, the type of the sequence elements also must be compatible with the type of the loop control variable that is used in the `For Each` statement that executes the query.</span></span> <span data-ttu-id="28889-111">此强类型化便于在编译时识别类型错误。</span><span class="sxs-lookup"><span data-stu-id="28889-111">This strong typing facilitates identification of type errors at compile time.</span></span>  
  
 <span data-ttu-id="28889-112">Visual Basic 使强类型方便通过也称为实现局部类型推理*隐式类型化*。</span><span class="sxs-lookup"><span data-stu-id="28889-112">Visual Basic makes strong typing convenient by implementing local type inference, also known as *implicit typing*.</span></span> <span data-ttu-id="28889-113">在上一示例中，使用功能，您将看到在所有[!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)]示例和文档。</span><span class="sxs-lookup"><span data-stu-id="28889-113">That feature is used in the previous example, and you will see it used throughout the [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] samples and documentation.</span></span> <span data-ttu-id="28889-114">在 Visual Basic 中，局部类型推理是只需通过实现`Dim`语句不带`As`子句。</span><span class="sxs-lookup"><span data-stu-id="28889-114">In Visual Basic, local type inference is accomplished simply by using a `Dim` statement without an `As` clause.</span></span> <span data-ttu-id="28889-115">在以下示例中，`city`强类型化为字符串。</span><span class="sxs-lookup"><span data-stu-id="28889-115">In the following example, `city` is strongly typed as a string.</span></span>  
  
 [!code-vb[VbLINQTypeRels#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQTypeRels/VB/Class1.vb#1)]  
  
> [!NOTE]
>  <span data-ttu-id="28889-116">局部类型推理时才起作用`Option Infer`设置为`On`。</span><span class="sxs-lookup"><span data-stu-id="28889-116">Local type inference works only when `Option Infer` is set to `On`.</span></span> <span data-ttu-id="28889-117">有关详细信息，请参阅[Option Infer 语句](../../../../visual-basic/language-reference/statements/option-infer-statement.md)。</span><span class="sxs-lookup"><span data-stu-id="28889-117">For more information, see [Option Infer Statement](../../../../visual-basic/language-reference/statements/option-infer-statement.md).</span></span>  
  
 <span data-ttu-id="28889-118">但是，即使在查询中使用局部类型推理，是在数据源中的变量、 查询变量和查询执行循环之间存在相同的类型关系。</span><span class="sxs-lookup"><span data-stu-id="28889-118">However, even if you use local type inference in a query, the same type relationships are present among the variables in the data source, the query variable, and the query execution loop.</span></span> <span data-ttu-id="28889-119">最好在编写时已基本了解对这些类型关系[!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)]查询或使用的示例和文档中的代码示例。</span><span class="sxs-lookup"><span data-stu-id="28889-119">It is useful to have a basic understanding of these type relationships when you are writing [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] queries, or working with the samples and code examples in the documentation.</span></span>  
  
 <span data-ttu-id="28889-120">您可能需要指定显式类型从数据源返回的类型不匹配的范围变量。</span><span class="sxs-lookup"><span data-stu-id="28889-120">You may need to specify an explicit type for a range variable that does not match the type returned from the data source.</span></span> <span data-ttu-id="28889-121">可以通过使用指定的范围变量的类型`As`子句。</span><span class="sxs-lookup"><span data-stu-id="28889-121">You can specify the type of the range variable by using an `As` clause.</span></span> <span data-ttu-id="28889-122">但是，这会导致错误如果转换[收缩转换](../../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md)并`Option Strict`设置为`On`。</span><span class="sxs-lookup"><span data-stu-id="28889-122">However, this results in an error if the conversion is a [narrowing conversion](../../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md) and `Option Strict` is set to `On`.</span></span> <span data-ttu-id="28889-123">因此，我们建议在从数据源检索的值上执行转换。</span><span class="sxs-lookup"><span data-stu-id="28889-123">Therefore, we recommend that you perform the conversion on the values retrieved from the data source.</span></span> <span data-ttu-id="28889-124">您可以将值转换从数据源为显式的范围变量类型使用<xref:System.Linq.Enumerable.Cast%2A>方法。</span><span class="sxs-lookup"><span data-stu-id="28889-124">You can convert the values from the data source to the explicit range variable type by using the <xref:System.Linq.Enumerable.Cast%2A> method.</span></span> <span data-ttu-id="28889-125">此外可以强制转换中所选值`Select`范围变量的类型不同的显式类型的子句。</span><span class="sxs-lookup"><span data-stu-id="28889-125">You can also cast the values selected in the `Select` clause to an explicit type that is different from the type of the range variable.</span></span> <span data-ttu-id="28889-126">在下面的代码说明了这些点。</span><span class="sxs-lookup"><span data-stu-id="28889-126">These points are illustrated in the following code.</span></span>  
  
 [!code-vb[VbLINQTypeRels#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQTypeRels/VB/Class1.vb#4)]  
  
## <a name="queries-that-return-entire-elements-of-the-source-data"></a><span data-ttu-id="28889-127">返回源数据的整个元素的查询</span><span class="sxs-lookup"><span data-stu-id="28889-127">Queries That Return Entire Elements of the Source Data</span></span>  
 <span data-ttu-id="28889-128">下面的示例演示[!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)]查询返回的源数据中的选定元素的序列的操作。</span><span class="sxs-lookup"><span data-stu-id="28889-128">The following example shows a [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] query operation that returns a sequence of elements selected from the source data.</span></span> <span data-ttu-id="28889-129">源`names`，包含数组的字符串，并将查询输出是包含以字母 M 开头的字符串序列。</span><span class="sxs-lookup"><span data-stu-id="28889-129">The source, `names`, contains an array of strings, and the query output is a sequence containing strings that start with the letter M.</span></span>  
  
 [!code-vb[VbLINQTypeRels#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQTypeRels/VB/Class1.vb#2)]  
  
 <span data-ttu-id="28889-130">这等效于下面的代码，但它更简短、 更轻松地编写。</span><span class="sxs-lookup"><span data-stu-id="28889-130">This is equivalent to the following code, but is much shorter and easier to write.</span></span> <span data-ttu-id="28889-131">依赖于在查询中的局部类型推理是在 Visual Basic 中的首选的样式。</span><span class="sxs-lookup"><span data-stu-id="28889-131">Reliance on local type inference in queries is the preferred style in Visual Basic.</span></span>  
  
 [!code-vb[VbLINQTypeRels#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQTypeRels/VB/Class1.vb#3)]  
  
 <span data-ttu-id="28889-132">以下关系存在于这两个前面的代码示例，是否隐式或显式确定类型。</span><span class="sxs-lookup"><span data-stu-id="28889-132">The following relationships exist in both of the previous code examples, whether the types are determined implicitly or explicitly.</span></span>  
  
1.  <span data-ttu-id="28889-133">数据源中的元素的类型`names`，是范围变量的类型`name`，在查询中。</span><span class="sxs-lookup"><span data-stu-id="28889-133">The type of the elements in the data source, `names`, is the type of the range variable, `name`, in the query.</span></span>  
  
2.  <span data-ttu-id="28889-134">选择后，该对象的类型`name`，确定查询变量的类型`mNames`。</span><span class="sxs-lookup"><span data-stu-id="28889-134">The type of the object that is selected, `name`, determines the type of the query variable, `mNames`.</span></span> <span data-ttu-id="28889-135">此处`name`是一个字符串，因此查询变量是在 Visual Basic 中的 IEnumerable (Of String)。</span><span class="sxs-lookup"><span data-stu-id="28889-135">Here `name` is a string, so the query variable is IEnumerable(Of String) in Visual Basic.</span></span>  
  
3.  <span data-ttu-id="28889-136">中定义的查询`mNames`中执行`For Each`循环。</span><span class="sxs-lookup"><span data-stu-id="28889-136">The query defined in `mNames` is executed in the `For Each` loop.</span></span> <span data-ttu-id="28889-137">循环将循环执行查询的结果。</span><span class="sxs-lookup"><span data-stu-id="28889-137">The loop iterates over the result of executing the query.</span></span> <span data-ttu-id="28889-138">因为`mNames`，在执行时将返回一个字符串，循环迭代变量序列`nm`，也是一个字符串。</span><span class="sxs-lookup"><span data-stu-id="28889-138">Because `mNames`, when it is executed, will return a sequence of strings, the loop iteration variable, `nm`, also is a string.</span></span>  
  
## <a name="queries-that-return-one-field-from-selected-elements"></a><span data-ttu-id="28889-139">返回从所选元素的一个字段的查询</span><span class="sxs-lookup"><span data-stu-id="28889-139">Queries That Return One Field from Selected Elements</span></span>  
 <span data-ttu-id="28889-140">下面的示例演示[!INCLUDE[vbtecdlinq](~/includes/vbtecdlinq-md.md)]查询返回的序列包含仅选择数据源中的每个元素的一部分的操作。</span><span class="sxs-lookup"><span data-stu-id="28889-140">The following example shows a [!INCLUDE[vbtecdlinq](~/includes/vbtecdlinq-md.md)] query operation that returns a sequence containing only one part of each element selected from the data source.</span></span> <span data-ttu-id="28889-141">查询采用一系列`Customer`对象作为其数据源，并仅适用于项目`Name`结果中的属性。</span><span class="sxs-lookup"><span data-stu-id="28889-141">The query takes a collection of `Customer` objects as its data source and projects only the `Name` property in the result.</span></span> <span data-ttu-id="28889-142">客户名称是一个字符串，因为查询将生成一个字符串序列作为输出。</span><span class="sxs-lookup"><span data-stu-id="28889-142">Because the customer name is a string, the query produces a sequence of strings as output.</span></span>  
  
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
  
 <span data-ttu-id="28889-143">变量之间的关系是类似于更简单的示例中。</span><span class="sxs-lookup"><span data-stu-id="28889-143">The relationships between variables are like those in the simpler example.</span></span>  
  
1.  <span data-ttu-id="28889-144">数据源中的元素的类型`customers`，是范围变量的类型`cust`，在查询中。</span><span class="sxs-lookup"><span data-stu-id="28889-144">The type of the elements in the data source, `customers`, is the type of the range variable, `cust`, in the query.</span></span> <span data-ttu-id="28889-145">在此示例中，类型为`Customer`。</span><span class="sxs-lookup"><span data-stu-id="28889-145">In this example, that type is `Customer`.</span></span>  
  
2.  <span data-ttu-id="28889-146">`Select`语句返回`Name`每个属性`Customer`对象而不是整个对象。</span><span class="sxs-lookup"><span data-stu-id="28889-146">The `Select` statement returns the `Name` property of each `Customer` object instead of the whole object.</span></span> <span data-ttu-id="28889-147">因为`Name`是一个字符串，查询变量`custNames`，再次将 IEnumerable (Of String)，不属于`Customer`。</span><span class="sxs-lookup"><span data-stu-id="28889-147">Because `Name` is a string, the query variable, `custNames`, will again be IEnumerable(Of String), not of `Customer`.</span></span>  
  
3.  <span data-ttu-id="28889-148">因为`custNames`表示一个字符串，序列`For Each`循环的迭代变量`custName`，必须为字符串。</span><span class="sxs-lookup"><span data-stu-id="28889-148">Because `custNames` represents a sequence of strings, the `For Each` loop's iteration variable, `custName`, must be a string.</span></span>  
  
 <span data-ttu-id="28889-149">而无需本地类型推断，前面的示例将很难编写和理解，如以下示例所示。</span><span class="sxs-lookup"><span data-stu-id="28889-149">Without local type inference, the previous example would be more cumbersome to write and to understand, as the following example shows.</span></span>  
  
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
  
## <a name="queries-that-require-anonymous-types"></a><span data-ttu-id="28889-150">需要匿名类型的查询</span><span class="sxs-lookup"><span data-stu-id="28889-150">Queries That Require Anonymous Types</span></span>  
 <span data-ttu-id="28889-151">下面的示例显示了更复杂的情况。</span><span class="sxs-lookup"><span data-stu-id="28889-151">The following example shows a more complex situation.</span></span> <span data-ttu-id="28889-152">在上一示例中，不便于显式指定所有变量的类型。</span><span class="sxs-lookup"><span data-stu-id="28889-152">In the previous example, it was inconvenient to specify types for all the variables explicitly.</span></span> <span data-ttu-id="28889-153">在此示例中，是不可能。</span><span class="sxs-lookup"><span data-stu-id="28889-153">In this example, it is impossible.</span></span> <span data-ttu-id="28889-154">而不是选择整个`Customer`数据源或从每个元素的单个字段中的元素`Select`子句在此查询将返回两个属性的原始`Customer`对象：`Name`和`City`。</span><span class="sxs-lookup"><span data-stu-id="28889-154">Instead of selecting entire `Customer` elements from the data source, or a single field from each element, the `Select` clause in this query returns two properties of the original `Customer` object: `Name` and `City`.</span></span> <span data-ttu-id="28889-155">在响应`Select`子句中，编译器会定义包含这两个属性的匿名类型。</span><span class="sxs-lookup"><span data-stu-id="28889-155">In response to the `Select` clause, the compiler defines an anonymous type that contains those two properties.</span></span> <span data-ttu-id="28889-156">执行的结果`nameCityQuery`在`For Each`循环是一系列新的匿名类型的实例。</span><span class="sxs-lookup"><span data-stu-id="28889-156">The result of executing `nameCityQuery` in the `For Each` loop is a collection of instances of the new anonymous type.</span></span> <span data-ttu-id="28889-157">因为匿名类型具有没有可用的名称，不能指定的类型`nameCityQuery`或`custInfo`显式。</span><span class="sxs-lookup"><span data-stu-id="28889-157">Because the anonymous type has no usable name, you cannot specify the type of `nameCityQuery` or `custInfo` explicitly.</span></span> <span data-ttu-id="28889-158">也就是说，与匿名类型，有没有类型名称来代替`String`在`IEnumerable(Of String)`。</span><span class="sxs-lookup"><span data-stu-id="28889-158">That is, with an anonymous type, you have no type name to use in place of `String` in `IEnumerable(Of String)`.</span></span> <span data-ttu-id="28889-159">有关详细信息，请参阅[匿名类型](../../../../visual-basic/programming-guide/language-features/objects-and-classes/anonymous-types.md)。</span><span class="sxs-lookup"><span data-stu-id="28889-159">For more information, see [Anonymous Types](../../../../visual-basic/programming-guide/language-features/objects-and-classes/anonymous-types.md).</span></span>  
  
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
  
 <span data-ttu-id="28889-160">尽管不能为指定类型的变量上一示例中，关系保持不变。</span><span class="sxs-lookup"><span data-stu-id="28889-160">Although it is not possible to specify types for all the variables in the previous example, the relationships remain the same.</span></span>  
  
1.  <span data-ttu-id="28889-161">数据源中的元素的类型同样是在查询中范围变量的类型。</span><span class="sxs-lookup"><span data-stu-id="28889-161">The type of the elements in the data source is again the type of the range variable in the query.</span></span> <span data-ttu-id="28889-162">在此示例中，`cust`的一个实例`Customer`。</span><span class="sxs-lookup"><span data-stu-id="28889-162">In this example, `cust` is an instance of `Customer`.</span></span>  
  
2.  <span data-ttu-id="28889-163">因为`Select`语句生成匿名类型，查询变量`nameCityQuery`，必须为匿名类型隐式类型。</span><span class="sxs-lookup"><span data-stu-id="28889-163">Because the `Select` statement produces an anonymous type, the query variable, `nameCityQuery`, must be implicitly typed as an anonymous type.</span></span> <span data-ttu-id="28889-164">匿名类型没有可用的名称，并因此不能显式指定。</span><span class="sxs-lookup"><span data-stu-id="28889-164">An anonymous type has no usable name, and therefore cannot be specified explicitly.</span></span>  
  
3.  <span data-ttu-id="28889-165">中的迭代变量的类型`For Each`循环是在步骤 2 中创建的匿名类型。</span><span class="sxs-lookup"><span data-stu-id="28889-165">The type of the iteration variable in the `For Each` loop is the anonymous type created in step 2.</span></span> <span data-ttu-id="28889-166">该类型具有没有可用的名称，因为必须隐式确定循环迭代变量的类型。</span><span class="sxs-lookup"><span data-stu-id="28889-166">Because the type has no usable name, the type of the loop iteration variable must be determined implicitly.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="28889-167">请参阅</span><span class="sxs-lookup"><span data-stu-id="28889-167">See also</span></span>
- [<span data-ttu-id="28889-168">Visual Basic 中的 LINQ 入门</span><span class="sxs-lookup"><span data-stu-id="28889-168">Getting Started with LINQ in Visual Basic</span></span>](../../../../visual-basic/programming-guide/concepts/linq/getting-started-with-linq.md)
- [<span data-ttu-id="28889-169">匿名类型</span><span class="sxs-lookup"><span data-stu-id="28889-169">Anonymous Types</span></span>](../../../../visual-basic/programming-guide/language-features/objects-and-classes/anonymous-types.md)
- [<span data-ttu-id="28889-170">局部类型推理</span><span class="sxs-lookup"><span data-stu-id="28889-170">Local Type Inference</span></span>](../../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md)
- [<span data-ttu-id="28889-171">Visual Basic 中的 LINQ 简介</span><span class="sxs-lookup"><span data-stu-id="28889-171">Introduction to LINQ in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)
- [<span data-ttu-id="28889-172">LINQ</span><span class="sxs-lookup"><span data-stu-id="28889-172">LINQ</span></span>](../../../../visual-basic/programming-guide/language-features/linq/index.md)
- [<span data-ttu-id="28889-173">查询</span><span class="sxs-lookup"><span data-stu-id="28889-173">Queries</span></span>](../../../../visual-basic/language-reference/queries/index.md)
