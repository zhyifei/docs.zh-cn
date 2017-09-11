---
title: "类型查询操作 (Visual Basic 中) 中的关系 |Microsoft 文档"
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
author: stevehoag
ms.author: shoag
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
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: a966b69feca7a7021cafbccb7971913ea781c479
ms.contentlocale: zh-cn
ms.lasthandoff: 03/13/2017

---
# <a name="type-relationships-in-query-operations-visual-basic"></a><span data-ttu-id="8b23b-102">查询操作中的类型关系 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="8b23b-102">Type Relationships in Query Operations (Visual Basic)</span></span>
<span data-ttu-id="8b23b-103">在中使用变量[!INCLUDE[vbteclinqext](../../../../csharp/getting-started/includes/vbteclinqext_md.md)]查询操作都强类型，并且必须是相互兼容。</span><span class="sxs-lookup"><span data-stu-id="8b23b-103">Variables used in [!INCLUDE[vbteclinqext](../../../../csharp/getting-started/includes/vbteclinqext_md.md)] query operations are strongly typed and must be compatible with each other.</span></span> <span data-ttu-id="8b23b-104">数据源、 查询本身，以及执行查询，都使用强类型。</span><span class="sxs-lookup"><span data-stu-id="8b23b-104">Strong typing is used in the data source, in the query itself, and in the query execution.</span></span> <span data-ttu-id="8b23b-105">下图列出术语用于描述[!INCLUDE[vbteclinq](../../../../csharp/includes/vbteclinq_md.md)]查询。</span><span class="sxs-lookup"><span data-stu-id="8b23b-105">The following illustration identifies terms used to describe a [!INCLUDE[vbteclinq](../../../../csharp/includes/vbteclinq_md.md)] query.</span></span> <span data-ttu-id="8b23b-106">有关查询的部件的详细信息，请参阅[基本查询操作 (Visual Basic 中)](../../../../visual-basic/programming-guide/concepts/linq/basic-query-operations.md)。</span><span class="sxs-lookup"><span data-stu-id="8b23b-106">For more information about the parts of a query, see [Basic Query Operations (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/basic-query-operations.md).</span></span>  
  
 <span data-ttu-id="8b23b-107">![具有突出显示的元素的伪代码查询。](../../../../visual-basic/programming-guide/concepts/linq/media/sjltyperels.png "SJLtypeRels")</span><span class="sxs-lookup"><span data-stu-id="8b23b-107">![Pseudocode query with elements highlighted.](../../../../visual-basic/programming-guide/concepts/linq/media/sjltyperels.png "SJLtypeRels")</span></span>  
<span data-ttu-id="8b23b-108">LINQ 查询的各个部分</span><span class="sxs-lookup"><span data-stu-id="8b23b-108">Parts of a LINQ query</span></span>  
  
 <span data-ttu-id="8b23b-109">在查询中的范围变量的类型必须与数据源中的元素的类型兼容。</span><span class="sxs-lookup"><span data-stu-id="8b23b-109">The type of the range variable in the query must be compatible with the type of the elements in the data source.</span></span> <span data-ttu-id="8b23b-110">查询变量的类型必须与在中定义的序列元素兼容`Select`子句。</span><span class="sxs-lookup"><span data-stu-id="8b23b-110">The type of the query variable must be compatible with the sequence element defined in the `Select` clause.</span></span> <span data-ttu-id="8b23b-111">最后，序列元素的类型也必须与使用中的循环控制变量的类型兼容`For Each`执行查询的语句。</span><span class="sxs-lookup"><span data-stu-id="8b23b-111">Finally, the type of the sequence elements also must be compatible with the type of the loop control variable that is used in the `For Each` statement that executes the query.</span></span> <span data-ttu-id="8b23b-112">此强类型便于在编译时识别类型错误。</span><span class="sxs-lookup"><span data-stu-id="8b23b-112">This strong typing facilitates identification of type errors at compile time.</span></span>  
  
 [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]<span data-ttu-id="8b23b-113">使强类型方便通过实现局部类型推理，也称为*隐式类型化*。</span><span class="sxs-lookup"><span data-stu-id="8b23b-113"> makes strong typing convenient by implementing local type inference, also known as *implicit typing*.</span></span> <span data-ttu-id="8b23b-114">在上一示例中，使用功能，您将看到在整个[!INCLUDE[vbteclinq](../../../../csharp/includes/vbteclinq_md.md)]示例和文档。</span><span class="sxs-lookup"><span data-stu-id="8b23b-114">That feature is used in the previous example, and you will see it used throughout the [!INCLUDE[vbteclinq](../../../../csharp/includes/vbteclinq_md.md)] samples and documentation.</span></span> <span data-ttu-id="8b23b-115">在 Visual Basic 中，局部类型推理通过只需使用`Dim`语句而不进行`As`子句。</span><span class="sxs-lookup"><span data-stu-id="8b23b-115">In Visual Basic, local type inference is accomplished simply by using a `Dim` statement without an `As` clause.</span></span> <span data-ttu-id="8b23b-116">在下面的示例中，`city`强类型化为字符串。</span><span class="sxs-lookup"><span data-stu-id="8b23b-116">In the following example, `city` is strongly typed as a string.</span></span>  
  
 <span data-ttu-id="8b23b-117">[!code-vb[VbLINQTypeRels #&1;](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/type-relationships-in-query-operations_1.vb)]</span><span class="sxs-lookup"><span data-stu-id="8b23b-117">[!code-vb[VbLINQTypeRels#1](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/type-relationships-in-query-operations_1.vb)]</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="8b23b-118">局部类型推理时才起作用`Option Infer`设置为`On`。</span><span class="sxs-lookup"><span data-stu-id="8b23b-118">Local type inference works only when `Option Infer` is set to `On`.</span></span> <span data-ttu-id="8b23b-119">有关详细信息，请参阅[Option Infer 语句](../../../../visual-basic/language-reference/statements/option-infer-statement.md)。</span><span class="sxs-lookup"><span data-stu-id="8b23b-119">For more information, see [Option Infer Statement](../../../../visual-basic/language-reference/statements/option-infer-statement.md).</span></span>  
  
 <span data-ttu-id="8b23b-120">但是，即使在查询中使用局部类型推理，是在数据源中的变量、 查询变量和查询执行循环之间存在相同的类型关系。</span><span class="sxs-lookup"><span data-stu-id="8b23b-120">However, even if you use local type inference in a query, the same type relationships are present among the variables in the data source, the query variable, and the query execution loop.</span></span> <span data-ttu-id="8b23b-121">可用于进行基本的了解对这些类型关系，在编写时[!INCLUDE[vbteclinq](../../../../csharp/includes/vbteclinq_md.md)]查询或使用示例和文档中的代码示例。</span><span class="sxs-lookup"><span data-stu-id="8b23b-121">It is useful to have a basic understanding of these type relationships when you are writing [!INCLUDE[vbteclinq](../../../../csharp/includes/vbteclinq_md.md)] queries, or working with the samples and code examples in the documentation.</span></span>  
  
 <span data-ttu-id="8b23b-122">您可能需要指定显式类型从数据源返回的类型不匹配的范围变量。</span><span class="sxs-lookup"><span data-stu-id="8b23b-122">You may need to specify an explicit type for a range variable that does not match the type returned from the data source.</span></span> <span data-ttu-id="8b23b-123">可以通过使用指定的范围变量的类型`As`子句。</span><span class="sxs-lookup"><span data-stu-id="8b23b-123">You can specify the type of the range variable by using an `As` clause.</span></span> <span data-ttu-id="8b23b-124">但是，这会导致一个错误如果转换，则[收缩转换](../../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md)和`Option Strict`设置为`On`。</span><span class="sxs-lookup"><span data-stu-id="8b23b-124">However, this results in an error if the conversion is a [narrowing conversion](../../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md) and `Option Strict` is set to `On`.</span></span> <span data-ttu-id="8b23b-125">因此，我们建议您从数据源检索的值上执行转换。</span><span class="sxs-lookup"><span data-stu-id="8b23b-125">Therefore, we recommend that you perform the conversion on the values retrieved from the data source.</span></span> <span data-ttu-id="8b23b-126">您可以将值转换从数据源为显式范围变量类型使用<xref:System.Linq.Enumerable.Cast%2A>方法。</xref:System.Linq.Enumerable.Cast%2A></span><span class="sxs-lookup"><span data-stu-id="8b23b-126">You can convert the values from the data source to the explicit range variable type by using the <xref:System.Linq.Enumerable.Cast%2A> method.</span></span> <span data-ttu-id="8b23b-127">也可以显式转换中选定的值`Select`范围变量的类型不同的显式类型的子句。</span><span class="sxs-lookup"><span data-stu-id="8b23b-127">You can also cast the values selected in the `Select` clause to an explicit type that is different from the type of the range variable.</span></span> <span data-ttu-id="8b23b-128">在下面的代码阐释了这些点。</span><span class="sxs-lookup"><span data-stu-id="8b23b-128">These points are illustrated in the following code.</span></span>  
  
 <span data-ttu-id="8b23b-129">[!code-vb[VbLINQTypeRels #&4;](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/type-relationships-in-query-operations_2.vb)]</span><span class="sxs-lookup"><span data-stu-id="8b23b-129">[!code-vb[VbLINQTypeRels#4](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/type-relationships-in-query-operations_2.vb)]</span></span>  
  
## <a name="queries-that-return-entire-elements-of-the-source-data"></a><span data-ttu-id="8b23b-130">查询返回的源数据的整个元素</span><span class="sxs-lookup"><span data-stu-id="8b23b-130">Queries That Return Entire Elements of the Source Data</span></span>  
 <span data-ttu-id="8b23b-131">下面的示例演示[!INCLUDE[vbteclinq](../../../../csharp/includes/vbteclinq_md.md)]查询返回的源数据中的选定元素的序列的操作。</span><span class="sxs-lookup"><span data-stu-id="8b23b-131">The following example shows a [!INCLUDE[vbteclinq](../../../../csharp/includes/vbteclinq_md.md)] query operation that returns a sequence of elements selected from the source data.</span></span> <span data-ttu-id="8b23b-132">源， `names`，包含数组的字符串，并且查询输出是包含以字母 M 开头的字符串的序列。</span><span class="sxs-lookup"><span data-stu-id="8b23b-132">The source, `names`, contains an array of strings, and the query output is a sequence containing strings that start with the letter M.</span></span>  
  
 <span data-ttu-id="8b23b-133">[!code-vb[VbLINQTypeRels #&2;](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/type-relationships-in-query-operations_3.vb)]</span><span class="sxs-lookup"><span data-stu-id="8b23b-133">[!code-vb[VbLINQTypeRels#2](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/type-relationships-in-query-operations_3.vb)]</span></span>  
  
 <span data-ttu-id="8b23b-134">这等效于下面的代码，但它更简短、 更易于编写。</span><span class="sxs-lookup"><span data-stu-id="8b23b-134">This is equivalent to the following code, but is much shorter and easier to write.</span></span> <span data-ttu-id="8b23b-135">依赖于在查询中的局部类型推理是在 Visual Basic 中的首选的样式。</span><span class="sxs-lookup"><span data-stu-id="8b23b-135">Reliance on local type inference in queries is the preferred style in Visual Basic.</span></span>  
  
 <span data-ttu-id="8b23b-136">[!code-vb[VbLINQTypeRels #&3;](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/type-relationships-in-query-operations_4.vb)]</span><span class="sxs-lookup"><span data-stu-id="8b23b-136">[!code-vb[VbLINQTypeRels#3](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/type-relationships-in-query-operations_4.vb)]</span></span>  
  
 <span data-ttu-id="8b23b-137">在这两个前面的代码示例中，情况下，隐式或显式类型确定是否存在下面的关系。</span><span class="sxs-lookup"><span data-stu-id="8b23b-137">The following relationships exist in both of the previous code examples, whether the types are determined implicitly or explicitly.</span></span>  
  
1.  <span data-ttu-id="8b23b-138">数据源中的元素的类型`names`，是一种范围变量`name`，在查询中。</span><span class="sxs-lookup"><span data-stu-id="8b23b-138">The type of the elements in the data source, `names`, is the type of the range variable, `name`, in the query.</span></span>  
  
2.  <span data-ttu-id="8b23b-139">选择后，该对象的类型`name`，确定查询变量的类型`mNames`。</span><span class="sxs-lookup"><span data-stu-id="8b23b-139">The type of the object that is selected, `name`, determines the type of the query variable, `mNames`.</span></span> <span data-ttu-id="8b23b-140">此处`name`是一个字符串，因此查询变量是在 Visual Basic 中的 IEnumerable (Of String)。</span><span class="sxs-lookup"><span data-stu-id="8b23b-140">Here `name` is a string, so the query variable is IEnumerable(Of String) in Visual Basic.</span></span>  
  
3.  <span data-ttu-id="8b23b-141">中定义的查询`mNames`中执行`For Each`循环。</span><span class="sxs-lookup"><span data-stu-id="8b23b-141">The query defined in `mNames` is executed in the `For Each` loop.</span></span> <span data-ttu-id="8b23b-142">循环将循环访问查询的执行结果。</span><span class="sxs-lookup"><span data-stu-id="8b23b-142">The loop iterates over the result of executing the query.</span></span> <span data-ttu-id="8b23b-143">因为`mNames`，它在执行时，将返回一个字符串，循环迭代变量序列`nm`，也是一个字符串。</span><span class="sxs-lookup"><span data-stu-id="8b23b-143">Because `mNames`, when it is executed, will return a sequence of strings, the loop iteration variable, `nm`, also is a string.</span></span>  
  
## <a name="queries-that-return-one-field-from-selected-elements"></a><span data-ttu-id="8b23b-144">返回从所选元素的一个字段的查询</span><span class="sxs-lookup"><span data-stu-id="8b23b-144">Queries That Return One Field from Selected Elements</span></span>  
 <span data-ttu-id="8b23b-145">下面的示例演示[!INCLUDE[vbtecdlinq](../../../../csharp/includes/vbtecdlinq_md.md)]查询返回包含从数据源中选择每个元素的只有一个部件的序列的操作。</span><span class="sxs-lookup"><span data-stu-id="8b23b-145">The following example shows a [!INCLUDE[vbtecdlinq](../../../../csharp/includes/vbtecdlinq_md.md)] query operation that returns a sequence containing only one part of each element selected from the data source.</span></span> <span data-ttu-id="8b23b-146">查询采用集合`Customer`对象作为其数据源并仅投射`Name`结果中的属性。</span><span class="sxs-lookup"><span data-stu-id="8b23b-146">The query takes a collection of `Customer` objects as its data source and projects only the `Name` property in the result.</span></span> <span data-ttu-id="8b23b-147">客户名称是字符串，因为此查询将生成一个字符串序列作为输出。</span><span class="sxs-lookup"><span data-stu-id="8b23b-147">Because the customer name is a string, the query produces a sequence of strings as output.</span></span>  
  
<span data-ttu-id="8b23b-148"><CodeContentPlaceHolder>0</CodeContentPlaceHolder></span><span class="sxs-lookup"><span data-stu-id="8b23b-148"><CodeContentPlaceHolder>0</CodeContentPlaceHolder></span></span>  
 <span data-ttu-id="8b23b-149">变量之间的关系是类似于更简单的示例中。</span><span class="sxs-lookup"><span data-stu-id="8b23b-149">The relationships between variables are like those in the simpler example.</span></span>  
  
1.  <span data-ttu-id="8b23b-150">数据源中的元素的类型`customers`，是一种范围变量`cust`，在查询中。</span><span class="sxs-lookup"><span data-stu-id="8b23b-150">The type of the elements in the data source, `customers`, is the type of the range variable, `cust`, in the query.</span></span> <span data-ttu-id="8b23b-151">在此示例中，该类型为`Customer`。</span><span class="sxs-lookup"><span data-stu-id="8b23b-151">In this example, that type is `Customer`.</span></span>  
  
2.  <span data-ttu-id="8b23b-152">`Select`语句返回`Name`每个属性`Customer`对象而不是整个对象。</span><span class="sxs-lookup"><span data-stu-id="8b23b-152">The `Select` statement returns the `Name` property of each `Customer` object instead of the whole object.</span></span> <span data-ttu-id="8b23b-153">因为`Name`是一个字符串，该查询变量， `custNames`，再次将 IEnumerable (Of String)，不属于`Customer`。</span><span class="sxs-lookup"><span data-stu-id="8b23b-153">Because `Name` is a string, the query variable, `custNames`, will again be IEnumerable(Of String), not of `Customer`.</span></span>  
  
3.  <span data-ttu-id="8b23b-154">因为`custNames`代表一个字符串，序列`For Each`循环的迭代变量`custName`，必须为字符串。</span><span class="sxs-lookup"><span data-stu-id="8b23b-154">Because `custNames` represents a sequence of strings, the `For Each` loop's iteration variable, `custName`, must be a string.</span></span>  
  
 <span data-ttu-id="8b23b-155">而无需局部类型推理，前面的示例将很难编写和理解，如以下示例所示。</span><span class="sxs-lookup"><span data-stu-id="8b23b-155">Without local type inference, the previous example would be more cumbersome to write and to understand, as the following example shows.</span></span>  
  
<span data-ttu-id="8b23b-156"><CodeContentPlaceHolder>1</CodeContentPlaceHolder></span><span class="sxs-lookup"><span data-stu-id="8b23b-156"><CodeContentPlaceHolder>1</CodeContentPlaceHolder></span></span>  
## <a name="queries-that-require-anonymous-types"></a><span data-ttu-id="8b23b-157">需要匿名类型的查询</span><span class="sxs-lookup"><span data-stu-id="8b23b-157">Queries That Require Anonymous Types</span></span>  
 <span data-ttu-id="8b23b-158">下面的示例演示更复杂的情况。</span><span class="sxs-lookup"><span data-stu-id="8b23b-158">The following example shows a more complex situation.</span></span> <span data-ttu-id="8b23b-159">在上一示例中，不是很方便显式指定类型的所有变量。</span><span class="sxs-lookup"><span data-stu-id="8b23b-159">In the previous example, it was inconvenient to specify types for all the variables explicitly.</span></span> <span data-ttu-id="8b23b-160">在此示例中，不可能。</span><span class="sxs-lookup"><span data-stu-id="8b23b-160">In this example, it is impossible.</span></span> <span data-ttu-id="8b23b-161">而不是选择整个`Customer`元素从数据源或从每个元素的单个字段`Select`子句在此查询将返回两个属性的原始`Customer`对象︰`Name`和`City`。</span><span class="sxs-lookup"><span data-stu-id="8b23b-161">Instead of selecting entire `Customer` elements from the data source, or a single field from each element, the `Select` clause in this query returns two properties of the original `Customer` object: `Name` and `City`.</span></span> <span data-ttu-id="8b23b-162">在响应`Select`子句中，编译器会定义包含这两个属性的匿名类型。</span><span class="sxs-lookup"><span data-stu-id="8b23b-162">In response to the `Select` clause, the compiler defines an anonymous type that contains those two properties.</span></span> <span data-ttu-id="8b23b-163">执行的结果`nameCityQuery`中`For Each`循环是新的匿名类型的实例的集合。</span><span class="sxs-lookup"><span data-stu-id="8b23b-163">The result of executing `nameCityQuery` in the `For Each` loop is a collection of instances of the new anonymous type.</span></span> <span data-ttu-id="8b23b-164">因为匿名类型中没有可用的名称，不能指定的一种`nameCityQuery`或`custInfo`显式。</span><span class="sxs-lookup"><span data-stu-id="8b23b-164">Because the anonymous type has no usable name, you cannot specify the type of `nameCityQuery` or `custInfo` explicitly.</span></span> <span data-ttu-id="8b23b-165">也就是说，使用匿名类型，有没有类型名称来代替了`String`中`IEnumerable(Of String)`。</span><span class="sxs-lookup"><span data-stu-id="8b23b-165">That is, with an anonymous type, you have no type name to use in place of `String` in `IEnumerable(Of String)`.</span></span> <span data-ttu-id="8b23b-166">有关详细信息，请参阅[匿名类型](../../../../visual-basic/programming-guide/language-features/objects-and-classes/anonymous-types.md)。</span><span class="sxs-lookup"><span data-stu-id="8b23b-166">For more information, see [Anonymous Types](../../../../visual-basic/programming-guide/language-features/objects-and-classes/anonymous-types.md).</span></span>  
  
<span data-ttu-id="8b23b-167"><CodeContentPlaceHolder>2</CodeContentPlaceHolder></span><span class="sxs-lookup"><span data-stu-id="8b23b-167"><CodeContentPlaceHolder>2</CodeContentPlaceHolder></span></span>  
 <span data-ttu-id="8b23b-168">尽管不能为指定类型的变量上一示例中，关系保持不变。</span><span class="sxs-lookup"><span data-stu-id="8b23b-168">Although it is not possible to specify types for all the variables in the previous example, the relationships remain the same.</span></span>  
  
1.  <span data-ttu-id="8b23b-169">数据源中的元素的类型同样是在查询中的范围变量的类型。</span><span class="sxs-lookup"><span data-stu-id="8b23b-169">The type of the elements in the data source is again the type of the range variable in the query.</span></span> <span data-ttu-id="8b23b-170">在此示例中，`cust`的一个实例`Customer`。</span><span class="sxs-lookup"><span data-stu-id="8b23b-170">In this example, `cust` is an instance of `Customer`.</span></span>  
  
2.  <span data-ttu-id="8b23b-171">因为`Select`语句生成一个匿名类型，则查询变量， `nameCityQuery`，必须以匿名类型隐式类型。</span><span class="sxs-lookup"><span data-stu-id="8b23b-171">Because the `Select` statement produces an anonymous type, the query variable, `nameCityQuery`, must be implicitly typed as an anonymous type.</span></span> <span data-ttu-id="8b23b-172">匿名类型没有可用的名称，并因此无法显式指定它。</span><span class="sxs-lookup"><span data-stu-id="8b23b-172">An anonymous type has no usable name, and therefore cannot be specified explicitly.</span></span>  
  
3.  <span data-ttu-id="8b23b-173">中的迭代变量的类型`For Each`循环是在步骤 2 中创建的匿名类型。</span><span class="sxs-lookup"><span data-stu-id="8b23b-173">The type of the iteration variable in the `For Each` loop is the anonymous type created in step 2.</span></span> <span data-ttu-id="8b23b-174">因为该类型没有可用的名称，则必须隐式确定循环迭代变量的类型。</span><span class="sxs-lookup"><span data-stu-id="8b23b-174">Because the type has no usable name, the type of the loop iteration variable must be determined implicitly.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8b23b-175">另请参阅</span><span class="sxs-lookup"><span data-stu-id="8b23b-175">See Also</span></span>  
 <span data-ttu-id="8b23b-176">[在 Visual Basic 中的 LINQ 入门](../../../../visual-basic/programming-guide/concepts/linq/getting-started-with-linq.md) </span><span class="sxs-lookup"><span data-stu-id="8b23b-176">[Getting Started with LINQ in Visual Basic](../../../../visual-basic/programming-guide/concepts/linq/getting-started-with-linq.md) </span></span>  
<span data-ttu-id="8b23b-177"> [匿名类型](../../../../visual-basic/programming-guide/language-features/objects-and-classes/anonymous-types.md) </span><span class="sxs-lookup"><span data-stu-id="8b23b-177"> [Anonymous Types](../../../../visual-basic/programming-guide/language-features/objects-and-classes/anonymous-types.md) </span></span>  
<span data-ttu-id="8b23b-178"> [局部类型推理](../../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md) </span><span class="sxs-lookup"><span data-stu-id="8b23b-178"> [Local Type Inference](../../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md) </span></span>  
<span data-ttu-id="8b23b-179"> [在 Visual Basic 中的 LINQ 简介](../../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md) </span><span class="sxs-lookup"><span data-stu-id="8b23b-179"> [Introduction to LINQ in Visual Basic](../../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md) </span></span>  
<span data-ttu-id="8b23b-180"> [LINQ](../../../../visual-basic/programming-guide/language-features/linq/index.md) </span><span class="sxs-lookup"><span data-stu-id="8b23b-180"> [LINQ](../../../../visual-basic/programming-guide/language-features/linq/index.md) </span></span>  
<span data-ttu-id="8b23b-181"> [查询](../../../../visual-basic/language-reference/queries/queries.md)</span><span class="sxs-lookup"><span data-stu-id="8b23b-181"> [Queries](../../../../visual-basic/language-reference/queries/queries.md)</span></span>
