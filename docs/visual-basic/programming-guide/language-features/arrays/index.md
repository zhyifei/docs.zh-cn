---
title: "Visual Basic 中的数组"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords: vb.Array
helpviewer_keywords:
- arrays [Visual Basic]
- Visual Basic, arrays
ms.assetid: dbf29737-b589-4443-bee6-a27588d9c67e
caps.latest.revision: "47"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 04deeccd19fd4edb3f2c88310d660eedf5c707d5
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="arrays-in-visual-basic"></a><span data-ttu-id="c06f2-102">Visual Basic 中的数组</span><span class="sxs-lookup"><span data-stu-id="c06f2-102">Arrays in Visual Basic</span></span>
<span data-ttu-id="c06f2-103">数组是一组在逻辑上彼此相关的值，如语法学校中每个年级学生的数量。</span><span class="sxs-lookup"><span data-stu-id="c06f2-103">An array is a set of values that are logically related to each other, such as the number of students in each grade in a grammar school.</span></span>  <span data-ttu-id="c06f2-104">如果你要查找有关 Visual Basic for Applications (VBA) 中的数组的帮助，请参阅 [语言参考](https://msdn.microsoft.com/library/office/gg264383\(v=office.14\).aspx)。</span><span class="sxs-lookup"><span data-stu-id="c06f2-104">If you are looking for help on arrays in Visual Basic for Applications (VBA), see the [language reference](https://msdn.microsoft.com/library/office/gg264383\(v=office.14\).aspx).</span></span>  
  
 <span data-ttu-id="c06f2-105">通过使用数组，你可以按相同的名称引用这些相关的值，然后使用调用了索引或下标的数字来区分它们。</span><span class="sxs-lookup"><span data-stu-id="c06f2-105">By using an array, you can refer to these related values by the same name, and use a number that’s called an index or subscript to tell them apart.</span></span> <span data-ttu-id="c06f2-106">单个值称为数组的元素。</span><span class="sxs-lookup"><span data-stu-id="c06f2-106">The individual values are called the elements of the array.</span></span> <span data-ttu-id="c06f2-107">它们的索引值从 0 到最大值都是连续的。</span><span class="sxs-lookup"><span data-stu-id="c06f2-107">They’re contiguous from index 0 through the highest index value.</span></span>  
  
 <span data-ttu-id="c06f2-108">与数组相反，包含单个值的变量称为 *“标量”* 变量。</span><span class="sxs-lookup"><span data-stu-id="c06f2-108">In contrast to an array, a variable that contain a single value is called a *scalar* variable.</span></span>  
  
 <span data-ttu-id="c06f2-109">在进行说明之前，请看几个简单的示例：</span><span class="sxs-lookup"><span data-stu-id="c06f2-109">Some quick examples before explanation:</span></span>  
  
```vb  
'Declare a single-dimension array of 5 values  
Dim numbers(4) As Integer   
  
'Declare a single-dimension array and set array element values  
Dim numbers = New Integer() {1, 2, 4, 8}  
  
'Redefine the size of an existing array retaining the current values  
ReDim Preserve numbers(15)  
  
'Redefine the size of an existing array, resetting the values  
ReDim numbers(15)  
  
'Declare a multi-dimensional array  
Dim matrix(5, 5) As Double  
  
'Declare a multi-dimensional array and set array element values  
Dim matrix = New Integer(4, 4) {{1, 2}, {3, 4}, {5, 6}, {7, 8}}  
  
'Declare a jagged array  
Dim sales()() As Double = New Double(11)() {}  
```  
  
 <span data-ttu-id="c06f2-110">**在本主题中**</span><span class="sxs-lookup"><span data-stu-id="c06f2-110">**In this topic**</span></span>  
  
-   [<span data-ttu-id="c06f2-111">简单数组中的数组元素</span><span class="sxs-lookup"><span data-stu-id="c06f2-111">Array Elements in a Simple Array</span></span>](#BKMK_ArrayElements)  
  
-   [<span data-ttu-id="c06f2-112">创建数组</span><span class="sxs-lookup"><span data-stu-id="c06f2-112">Creating an Array</span></span>](#BKMK_CreatingAnArray)  
  
-   [<span data-ttu-id="c06f2-113">存储数组中的值</span><span class="sxs-lookup"><span data-stu-id="c06f2-113">Storing Values in an Array</span></span>](#BKMK_StoringValues)  
  
-   [<span data-ttu-id="c06f2-114">使用初始值填充数组</span><span class="sxs-lookup"><span data-stu-id="c06f2-114">Populating an Array with Initial Values</span></span>](#BKMK_Populating)  
  
    -   [<span data-ttu-id="c06f2-115">嵌套的数组文本</span><span class="sxs-lookup"><span data-stu-id="c06f2-115">Nested Array Literals</span></span>](#BKMK_NestedArrayLiterals)  
  
-   [<span data-ttu-id="c06f2-116">循环访问数组</span><span class="sxs-lookup"><span data-stu-id="c06f2-116">Iterating Through an Array</span></span>](#BKMK_Iterating)  
  
-   [<span data-ttu-id="c06f2-117">作为返回值和参数的数组</span><span class="sxs-lookup"><span data-stu-id="c06f2-117">Arrays as Return Values and Parameters</span></span>](#BKMK_ReturnValues)  
  
-   [<span data-ttu-id="c06f2-118">交错数组</span><span class="sxs-lookup"><span data-stu-id="c06f2-118">Jagged Arrays</span></span>](#BKMK_JaggedArrays)  
  
-   [<span data-ttu-id="c06f2-119">零长度数组</span><span class="sxs-lookup"><span data-stu-id="c06f2-119">Zero-Length Arrays</span></span>](#BKMK_ZeroLength)  
  
-   [<span data-ttu-id="c06f2-120">数组大小</span><span class="sxs-lookup"><span data-stu-id="c06f2-120">Array Size</span></span>](#BKMK_ArraySize)  
  
-   [<span data-ttu-id="c06f2-121">数组类型和其他类型</span><span class="sxs-lookup"><span data-stu-id="c06f2-121">Array Types and Other Types</span></span>](#BKMK_ArrayTypes)  
  
-   [<span data-ttu-id="c06f2-122">作为数组的替代方法的集合</span><span class="sxs-lookup"><span data-stu-id="c06f2-122">Collections as an Alternative to Arrays</span></span>](#BKMK_Collections)  
  
##  <a name="BKMK_ArrayElements"></a> <span data-ttu-id="c06f2-123">简单数组中的数组元素</span><span class="sxs-lookup"><span data-stu-id="c06f2-123">Array Elements in a Simple Array</span></span>  
 <span data-ttu-id="c06f2-124">下例声明了一个数组变量来表示语法学校每个年级的学生数。</span><span class="sxs-lookup"><span data-stu-id="c06f2-124">The following example declares an array variable to hold the number of students in each grade in a grammar school.</span></span>  
  
 [!code-vb[VbVbalrArrays#2](../../../../../samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrArrays/VB/Class1.vb#2)]  
  
 <span data-ttu-id="c06f2-125">前面的示例中的数组 `students` 包含七个元素。</span><span class="sxs-lookup"><span data-stu-id="c06f2-125">The array `students` in the preceding example contains seven elements.</span></span> <span data-ttu-id="c06f2-126">这些元素的索引范围为 0 到 6。</span><span class="sxs-lookup"><span data-stu-id="c06f2-126">The indexes of the elements range from 0 through 6.</span></span> <span data-ttu-id="c06f2-127">拥有此数组比声明七个变量更简单。</span><span class="sxs-lookup"><span data-stu-id="c06f2-127">Having this array is simpler than declaring seven variables.</span></span>  
  
 <span data-ttu-id="c06f2-128">下图显示了数组 `students`。</span><span class="sxs-lookup"><span data-stu-id="c06f2-128">The following illustration shows the array `students`.</span></span> <span data-ttu-id="c06f2-129">对于数组的每个元素：</span><span class="sxs-lookup"><span data-stu-id="c06f2-129">For each element of the array:</span></span>  
  
-   <span data-ttu-id="c06f2-130">元素索引表示年级（索引 0 表示幼儿园）。</span><span class="sxs-lookup"><span data-stu-id="c06f2-130">The index of the element represents the grade (index 0 represents kindergarten).</span></span>  
  
-   <span data-ttu-id="c06f2-131">元素中包含的值表示每个年级的学生数量。</span><span class="sxs-lookup"><span data-stu-id="c06f2-131">The value that’s contained in the element represents the number of students in that grade.</span></span>  
  
 <span data-ttu-id="c06f2-132">![显示学生人数的数组图片](../../../../visual-basic/programming-guide/language-features/arrays/media/arrayexampleschool.gif " ArrayExampleSchool ")</span><span class="sxs-lookup"><span data-stu-id="c06f2-132">![Picture of array showing numbers of students](../../../../visual-basic/programming-guide/language-features/arrays/media/arrayexampleschool.gif "ArrayExampleSchool")</span></span>  
<span data-ttu-id="c06f2-133">“学生”数组中的元素</span><span class="sxs-lookup"><span data-stu-id="c06f2-133">Elements of the "students" array</span></span>  
  
 <span data-ttu-id="c06f2-134">下面的示例演示了如何引用数组 `students`的第一、第二和最后一个元素。</span><span class="sxs-lookup"><span data-stu-id="c06f2-134">The following example shows how to refer to the first, second, and last element of the array `students`.</span></span>  
  
 [!code-vb[VbVbalrArrays#3](../../../../../samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrArrays/VB/Class1.vb#3)]  
  
 <span data-ttu-id="c06f2-135">你可以通过使用不带索引的数组变量名称来引用作为一个整体的数组。</span><span class="sxs-lookup"><span data-stu-id="c06f2-135">You can refer to the array as a whole by using just the array variable name without indexes.</span></span>  
  
 <span data-ttu-id="c06f2-136">前面的示例中的数组 `students` 使用一个索引，则称其为一维。</span><span class="sxs-lookup"><span data-stu-id="c06f2-136">The array `students` in the preceding example uses one index and is said to be one-dimensional.</span></span> <span data-ttu-id="c06f2-137">使用多个索引或下标的数组则称为多维。</span><span class="sxs-lookup"><span data-stu-id="c06f2-137">An array that uses more than one index or subscript is called multidimensional.</span></span> <span data-ttu-id="c06f2-138">有关详细信息，请参阅本主题剩余部分和 [Array Dimensions in Visual Basic](../../../../visual-basic/programming-guide/language-features/arrays/array-dimensions.md)。</span><span class="sxs-lookup"><span data-stu-id="c06f2-138">For more information, see the rest of this topic and [Array Dimensions in Visual Basic](../../../../visual-basic/programming-guide/language-features/arrays/array-dimensions.md).</span></span>  
  
##  <a name="BKMK_CreatingAnArray"></a> <span data-ttu-id="c06f2-139">创建数组</span><span class="sxs-lookup"><span data-stu-id="c06f2-139">Creating an Array</span></span>  
 <span data-ttu-id="c06f2-140">你可以用几种方法定义数组的大小。</span><span class="sxs-lookup"><span data-stu-id="c06f2-140">You can define the size of an array several ways.</span></span> <span data-ttu-id="c06f2-141">当声明数组时，你可以提供其大小，如以下示例所示。</span><span class="sxs-lookup"><span data-stu-id="c06f2-141">You can supply the size when the array is declared, as the following example shows.</span></span>  
  
 [!code-vb[VbVbalrArrays#12](../../../../../samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrArrays/VB/Class1.vb#12)]  
  
 <span data-ttu-id="c06f2-142">你还可以使用 `New` 子句提供数组大小，如以下示例所示。</span><span class="sxs-lookup"><span data-stu-id="c06f2-142">You can also use a `New` clause to supply the size of an array when it’s created, as the following example shows.</span></span>  
  
 [!code-vb[VbVbalrArrays#11](../../../../../samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrArrays/VB/Class1.vb#11)]  
  
 <span data-ttu-id="c06f2-143">如果你具有现有数组，你可以通过使用 `Redim` 语句来重新定义其大小。</span><span class="sxs-lookup"><span data-stu-id="c06f2-143">If you have an existing array, you can redefine its size by using the `Redim` statement.</span></span> <span data-ttu-id="c06f2-144">你可以指定 `Redim` 语句应保留的数组中的值，也可以指定它创建一个空数组。</span><span class="sxs-lookup"><span data-stu-id="c06f2-144">You can specify that the `Redim` statement should keep the values that are in the array, or you can specify that it create an empty array.</span></span> <span data-ttu-id="c06f2-145">下面的示例演示了用 `Redim` 语句来修改现有数组的大小的不同用法。</span><span class="sxs-lookup"><span data-stu-id="c06f2-145">The following example shows different uses of the `Redim` statement to modify the size of an existing array.</span></span>  
  
 [!code-vb[VbVbalrArrays#13](../../../../../samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrArrays/VB/Class1.vb#13)]  
  
 <span data-ttu-id="c06f2-146">有关详细信息，请参阅 [ReDim 语句](../../../../visual-basic/language-reference/statements/redim-statement.md)。</span><span class="sxs-lookup"><span data-stu-id="c06f2-146">For more information, see [ReDim Statement](../../../../visual-basic/language-reference/statements/redim-statement.md).</span></span>  
  
##  <a name="BKMK_StoringValues"></a><span data-ttu-id="c06f2-147">在数组中存储值</span><span class="sxs-lookup"><span data-stu-id="c06f2-147">Storing Values in an Array</span></span>  
 <span data-ttu-id="c06f2-148">你可以通过使用类型 `Integer`的索引访问数组中的每个位置。</span><span class="sxs-lookup"><span data-stu-id="c06f2-148">You can access each location in an array by using an index of type `Integer`.</span></span> <span data-ttu-id="c06f2-149">你可以使用括号内的索引来引用每个数组位置，从而存储和检索数组中的值。</span><span class="sxs-lookup"><span data-stu-id="c06f2-149">You can store and retrieve values in an array by referencing each array location by using its index enclosed in parentheses.</span></span> <span data-ttu-id="c06f2-150">多维数组的索引用逗号 (,) 分隔。</span><span class="sxs-lookup"><span data-stu-id="c06f2-150">Indexes for multi-dimensional arrays are separated by commas (,).</span></span> <span data-ttu-id="c06f2-151">每个数组维度都需要一个索引。</span><span class="sxs-lookup"><span data-stu-id="c06f2-151">You need one index for each array dimension.</span></span> <span data-ttu-id="c06f2-152">下例介绍了用于存储数组中的值的一些语句。</span><span class="sxs-lookup"><span data-stu-id="c06f2-152">The following example shows some statements that store values in arrays.</span></span>  
  
 [!code-vb[VbVbalrArrays#5](../../../../../samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrArrays/VB/Class1.vb#5)]  
  
 <span data-ttu-id="c06f2-153">下例介绍了用于获取数组中的值的一些语句。</span><span class="sxs-lookup"><span data-stu-id="c06f2-153">The following example shows some statements that get values from arrays.</span></span>  
  
 [!code-vb[VbVbalrArrays#6](../../../../../samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrArrays/VB/Class1.vb#6)]  
  
##  <a name="BKMK_Populating"></a> <span data-ttu-id="c06f2-154">使用初始值填充数组</span><span class="sxs-lookup"><span data-stu-id="c06f2-154">Populating an Array with Initial Values</span></span>  
 <span data-ttu-id="c06f2-155">通过使用数组文本，可以创建包含一组初始值的数组。</span><span class="sxs-lookup"><span data-stu-id="c06f2-155">By using an array literal, you can create an array that contains an initial set of values.</span></span> <span data-ttu-id="c06f2-156">数组文本包含用逗号分隔的值列表，这些值被括在括号内 (`{}`)。</span><span class="sxs-lookup"><span data-stu-id="c06f2-156">An array literal consists of a list of comma-separated values that are enclosed in braces (`{}`).</span></span>  
  
 <span data-ttu-id="c06f2-157">通过使用数组文本创建数组时，可以提供数组类型或使用类型推理功能来确定数组类型。</span><span class="sxs-lookup"><span data-stu-id="c06f2-157">When you create an array by using an array literal, you can either supply the array type or use type inference to determine the array type.</span></span> <span data-ttu-id="c06f2-158">下面的代码演示了两种选项。</span><span class="sxs-lookup"><span data-stu-id="c06f2-158">The following code shows both options.</span></span>  
  
 [!code-vb[VbVbalrCollectionInitializers#3](../../../../../samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrCollectionInitializers/VB/Module1.vb#3)]  
  
 <span data-ttu-id="c06f2-159">使用类型推理时，将根据为数组文本提供的值列表中的基准类型确定数组类型。</span><span class="sxs-lookup"><span data-stu-id="c06f2-159">When you use type inference, the type of the array is determined by the dominant type in the list of values that’s supplied for the array literal.</span></span> <span data-ttu-id="c06f2-160">基准类型是数组文本中所有其他类型可以扩大到的唯一类型。</span><span class="sxs-lookup"><span data-stu-id="c06f2-160">The dominant type is a unique type to which all other types in the array literal can widen.</span></span> <span data-ttu-id="c06f2-161">如果无法确定此唯一类型，基准类型是数组中所有其他类型可以缩小到的唯一类型。</span><span class="sxs-lookup"><span data-stu-id="c06f2-161">If this unique type can’t be determined, the dominant type is the unique type to which all other types in the array can narrow.</span></span> <span data-ttu-id="c06f2-162">如果无法确定为这两种唯一类型之一，则基准类型是 `Object`。</span><span class="sxs-lookup"><span data-stu-id="c06f2-162">If neither of these unique types can be determined, the dominant type is `Object`.</span></span> <span data-ttu-id="c06f2-163">例如，如果提供给数组文本的值的列表包含 `Integer`、 `Long`和 `Double`类型的值，则生成的数组类型是 `Double`。</span><span class="sxs-lookup"><span data-stu-id="c06f2-163">For example, if the list of values that’s supplied to the array literal contains values of type `Integer`, `Long`, and `Double`, the resulting array is of type `Double`.</span></span> <span data-ttu-id="c06f2-164">`Integer` 和 `Long` 都仅扩大到 `Double`。</span><span class="sxs-lookup"><span data-stu-id="c06f2-164">Both `Integer` and `Long` widen only to `Double`.</span></span> <span data-ttu-id="c06f2-165">因此， `Double` 是基准类型。</span><span class="sxs-lookup"><span data-stu-id="c06f2-165">Therefore, `Double` is the dominant type.</span></span> <span data-ttu-id="c06f2-166">有关详细信息，请参阅 [Widening and Narrowing Conversions](../../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md)。</span><span class="sxs-lookup"><span data-stu-id="c06f2-166">For more information, see [Widening and Narrowing Conversions](../../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md).</span></span> <span data-ttu-id="c06f2-167">这些推理规则适用于为作为在类成员中定义的本地变量的数组所推理出来的类型。</span><span class="sxs-lookup"><span data-stu-id="c06f2-167">These inference rules apply to types that are inferred for arrays that are local variables that are defined in a class member.</span></span> <span data-ttu-id="c06f2-168">虽然在创建类级别变量时可以使用数组文本，但你不能在类级别上使用类型推理。</span><span class="sxs-lookup"><span data-stu-id="c06f2-168">Although you can use array literals when you create class-level variables, you can’t use type inference at the class level.</span></span> <span data-ttu-id="c06f2-169">因此，在类级别上指定的数组文本推理出作为类型 `Object`数组文本提供的值。</span><span class="sxs-lookup"><span data-stu-id="c06f2-169">As a result, array literals that are specified at the class level infer the values that are supplied for the array literal as type `Object`.</span></span>  
  
 <span data-ttu-id="c06f2-170">在使用数组文本创建的数组中，可以显式指定元素的类型。</span><span class="sxs-lookup"><span data-stu-id="c06f2-170">You can explicitly specify the type of the elements in an array that’s created by using an array literal.</span></span> <span data-ttu-id="c06f2-171">在这种情况下，数组文本中的值必须扩大到数组的元素类型。</span><span class="sxs-lookup"><span data-stu-id="c06f2-171">In this case, the values in the array literal must widen to the type of the elements of the array.</span></span> <span data-ttu-id="c06f2-172">下面的代码示例从整数列表创建了一个 `Double` 类型的数组。</span><span class="sxs-lookup"><span data-stu-id="c06f2-172">The following code example creates an array of type `Double` from a list of integers.</span></span>  
  
 [!code-vb[VbVbalrCollectionInitializers#4](../../../../../samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrCollectionInitializers/VB/Module1.vb#4)]  
  
###  <a name="BKMK_NestedArrayLiterals"></a> <span data-ttu-id="c06f2-173">嵌套的数组文本</span><span class="sxs-lookup"><span data-stu-id="c06f2-173">Nested Array Literals</span></span>  
 <span data-ttu-id="c06f2-174">可以通过使用嵌套的数组文本创建多维数组。</span><span class="sxs-lookup"><span data-stu-id="c06f2-174">You can create a multidimensional array by using nested array literals.</span></span> <span data-ttu-id="c06f2-175">嵌套的数组文本必须具有维度和维度数目或排名，这与生成的数组保持一致。</span><span class="sxs-lookup"><span data-stu-id="c06f2-175">Nested array literals must have a dimension and number of dimensions, or rank, that’s consistent with the resulting array.</span></span> <span data-ttu-id="c06f2-176">下面的代码示例通过使用数组文本创建了一个二维的整数数组。</span><span class="sxs-lookup"><span data-stu-id="c06f2-176">The following code example creates a two-dimensional array of integers by using an array literal.</span></span>  
  
 [!code-vb[VbVbalrCollectionInitializers#7](../../../../../samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrCollectionInitializers/VB/Module1.vb#7)]  
  
 <span data-ttu-id="c06f2-177">在前面的示例中，如果嵌套的数组文本中的元素数目不匹配，则会出现错误。</span><span class="sxs-lookup"><span data-stu-id="c06f2-177">In the previous example, an error would occur if the number of elements in the nested array literals didn’t match.</span></span> <span data-ttu-id="c06f2-178">如果显式声明的数组变量为非二维，也会出现错误。</span><span class="sxs-lookup"><span data-stu-id="c06f2-178">An error would also occur if you explicitly declared the array variable to be other than two-dimensional.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="c06f2-179">你可以在提供不同维度的嵌套数组文本时，将内部数组文本括在括号内以避免出错。</span><span class="sxs-lookup"><span data-stu-id="c06f2-179">You can avoid an error when you supply nested array literals of different dimensions by enclosing the inner array literals in parentheses.</span></span> <span data-ttu-id="c06f2-180">圆括号会强制计算数组文字表达式，并将生成的值用于外部数组文本，如以下代码所示。</span><span class="sxs-lookup"><span data-stu-id="c06f2-180">The parentheses force the array literal expression to be evaluated, and the resulting values are used with the outer array literal, as the following code shows.</span></span>  
  
 [!code-vb[VbVbalrCollectionInitializers#11](../../../../../samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrCollectionInitializers/VB/Module1.vb#11)]  
  
 <span data-ttu-id="c06f2-181">当你通过使用嵌套的数组文本创建多维数组时，可以使用类型推理。</span><span class="sxs-lookup"><span data-stu-id="c06f2-181">When you create a multidimensional array by using nested array literals, you can use type inference.</span></span> <span data-ttu-id="c06f2-182">当使用类型推理时，推理出的类型是用于嵌套级别的所有数组文本中的所有值的基准类型。</span><span class="sxs-lookup"><span data-stu-id="c06f2-182">When you use type inference, the inferred type is the dominant type for all the values in all the array literals for a nesting level.</span></span> <span data-ttu-id="c06f2-183">下面的代码示例从类型为 `Double` 和 `Integer` 的值中创建了一个类型为 `Double`的二维数组。</span><span class="sxs-lookup"><span data-stu-id="c06f2-183">The following code example creates a two-dimensional array of type `Double` from values that are of type `Integer` and `Double`.</span></span>  
  
 [!code-vb[VbVbalrCollectionInitializers#8](../../../../../samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrCollectionInitializers/VB/Module1.vb#8)]  
  
 <span data-ttu-id="c06f2-184">有关其他示例，请参阅[如何：在 Visual Basic 中初始化数组变量](../../../../visual-basic/programming-guide/language-features/arrays/how-to-initialize-an-array-variable.md)。</span><span class="sxs-lookup"><span data-stu-id="c06f2-184">For additional examples, see [How to: Initialize an Array Variable in Visual Basic](../../../../visual-basic/programming-guide/language-features/arrays/how-to-initialize-an-array-variable.md).</span></span>  
  
##  <a name="BKMK_Iterating"></a><span data-ttu-id="c06f2-185">循环访问数组</span><span class="sxs-lookup"><span data-stu-id="c06f2-185">Iterating Through an Array</span></span>  
 <span data-ttu-id="c06f2-186">循环访问数组时，你可以从最低到最高的索引访问数组中的每个元素。</span><span class="sxs-lookup"><span data-stu-id="c06f2-186">When you iterate through an array, you access each element in the array from the lowest index to the highest index.</span></span>  
  
 <span data-ttu-id="c06f2-187">下面的示例使用 [For...Next 语句](../../../../visual-basic/language-reference/statements/for-next-statement.md)循环访问一维数组。</span><span class="sxs-lookup"><span data-stu-id="c06f2-187">The following example iterates through a one-dimensional array by using the [For...Next Statement](../../../../visual-basic/language-reference/statements/for-next-statement.md).</span></span> <span data-ttu-id="c06f2-188"><xref:System.Array.GetUpperBound%2A> 方法可以返回索引所具有的最大值。</span><span class="sxs-lookup"><span data-stu-id="c06f2-188">The <xref:System.Array.GetUpperBound%2A> method returns the highest value that the index can have.</span></span> <span data-ttu-id="c06f2-189">最小的索引值始终是 0。</span><span class="sxs-lookup"><span data-stu-id="c06f2-189">The lowest index value is always 0.</span></span>  
  
 [!code-vb[VbVbalrArrays#41](../../../../../samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrArrays/VB/Class1.vb#41)]  
  
 <span data-ttu-id="c06f2-190">下面的示例使用 `For...Next` 语句循环访问一个多维数组。</span><span class="sxs-lookup"><span data-stu-id="c06f2-190">The following example iterates through a multidimensional array by using a `For...Next` statement.</span></span> <span data-ttu-id="c06f2-191"><xref:System.Array.GetUpperBound%2A> 方法具有用于指定维度的参数。</span><span class="sxs-lookup"><span data-stu-id="c06f2-191">The <xref:System.Array.GetUpperBound%2A> method has a parameter that specifies the dimension.</span></span> <span data-ttu-id="c06f2-192">`GetUpperBound(0)` 返回的第一个维度的高索引值， `GetUpperBound(1)` 返回第二个维度的高索引值。</span><span class="sxs-lookup"><span data-stu-id="c06f2-192">`GetUpperBound(0)` returns the high index value for the first dimension, and `GetUpperBound(1)` returns the high index value for the second dimension.</span></span>  
  
 [!code-vb[VbVbalrArrays#42](../../../../../samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrArrays/VB/Class1.vb#42)]  
  
 <span data-ttu-id="c06f2-193">下面的示例使用 [For Each...Next 语句](../../../../visual-basic/language-reference/statements/for-each-next-statement.md) 循环访问一维数组。</span><span class="sxs-lookup"><span data-stu-id="c06f2-193">The following example iterates through a one-dimensional array by using a [For Each...Next Statement](../../../../visual-basic/language-reference/statements/for-each-next-statement.md).</span></span>  
  
 [!code-vb[VbVbalrArrays#43](../../../../../samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrArrays/VB/Class1.vb#43)]  
  
 <span data-ttu-id="c06f2-194">下面的示例使用 `For Each...Next` 语句循环访问一个多维数组。</span><span class="sxs-lookup"><span data-stu-id="c06f2-194">The following example iterates through a multidimensional array by using a `For Each...Next` statement.</span></span> <span data-ttu-id="c06f2-195">但是，如果使用一个嵌套的 `For…Next` 语句（如上例所示）而非一个 `For Each…Next` 语句，你能更好地控制多维数组中的元素。</span><span class="sxs-lookup"><span data-stu-id="c06f2-195">However, you have more control over the elements of a multidimensional array if you use a nested `For…Next` statement, as in a previous example, instead of a `For Each…Next` statement.</span></span>  
  
 [!code-vb[VbVbalrArrays#44](../../../../../samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrArrays/VB/Class1.vb#44)]  
  
##  <a name="BKMK_ReturnValues"></a><span data-ttu-id="c06f2-196">作为返回值和参数的数组</span><span class="sxs-lookup"><span data-stu-id="c06f2-196">Arrays as Return Values and Parameters</span></span>  
 <span data-ttu-id="c06f2-197">若要通过 `Function` 过程返回数组，请将数组数据类型和维度数指定为 [Function 语句](../../../../visual-basic/language-reference/statements/function-statement.md)的返回类型。</span><span class="sxs-lookup"><span data-stu-id="c06f2-197">To return an array from a `Function` procedure, specify the array data type and the number of dimensions as the return type of the [Function Statement](../../../../visual-basic/language-reference/statements/function-statement.md).</span></span> <span data-ttu-id="c06f2-198">在函数内，声明一个具有相同数据类型和维度数的本地数组变量。</span><span class="sxs-lookup"><span data-stu-id="c06f2-198">Within the function, declare a local array variable with same data type and number of dimensions.</span></span> <span data-ttu-id="c06f2-199">在 [Return 语句](../../../../visual-basic/language-reference/statements/return-statement.md)中，添加不带括号的局部数组变量。</span><span class="sxs-lookup"><span data-stu-id="c06f2-199">In the [Return Statement](../../../../visual-basic/language-reference/statements/return-statement.md), include the local array variable without parentheses.</span></span>  
  
 <span data-ttu-id="c06f2-200">若要将作为参数的数组指定到 `Sub` 或 `Function` 步骤中，可将此参数定义为具有指定数据类型和维度数量的数组。</span><span class="sxs-lookup"><span data-stu-id="c06f2-200">To specify an array as a parameter to a `Sub` or `Function` procedure, define the parameter as an array with a specified data type and number of dimensions.</span></span> <span data-ttu-id="c06f2-201">在对过程的调用中，发送一个具有相同数据类型和维度数量的数组变量。</span><span class="sxs-lookup"><span data-stu-id="c06f2-201">In the call to the procedure, send an array variable with the same data type and number of dimensions.</span></span>  
  
 <span data-ttu-id="c06f2-202">在下面的示例中， `GetNumbers` 函数将返回 `Integer()`。</span><span class="sxs-lookup"><span data-stu-id="c06f2-202">In the following example, the `GetNumbers` function returns an `Integer()`.</span></span> <span data-ttu-id="c06f2-203">此数组类型是一个类型为 `Integer`的一维数组。</span><span class="sxs-lookup"><span data-stu-id="c06f2-203">This array type is a one dimensional array of type `Integer`.</span></span> <span data-ttu-id="c06f2-204">`ShowNumbers` 过程接受 `Integer()` 参数。</span><span class="sxs-lookup"><span data-stu-id="c06f2-204">The `ShowNumbers` procedure accepts an `Integer()` argument.</span></span>  
  
 [!code-vb[VbVbalrArrays#51](../../../../../samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrArrays/VB/Class1.vb#51)]  
  
 <span data-ttu-id="c06f2-205">在下面的示例中， `GetNumbersMultiDim` 函数将返回 `Integer(,)`。</span><span class="sxs-lookup"><span data-stu-id="c06f2-205">In the following example, the `GetNumbersMultiDim` function returns an `Integer(,)`.</span></span> <span data-ttu-id="c06f2-206">此数组类型是一个类型为 `Integer`的二维数组。</span><span class="sxs-lookup"><span data-stu-id="c06f2-206">This array type is a two dimensional array of type `Integer`.</span></span>  <span data-ttu-id="c06f2-207">`ShowNumbersMultiDim` 过程接受 `Integer(,)` 参数。</span><span class="sxs-lookup"><span data-stu-id="c06f2-207">The `ShowNumbersMultiDim` procedure accepts an `Integer(,)` argument.</span></span>  
  
 [!code-vb[VbVbalrArrays#52](../../../../../samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrArrays/VB/Class1.vb#52)]  
  
##  <a name="BKMK_JaggedArrays"></a> <span data-ttu-id="c06f2-208">交错数组</span><span class="sxs-lookup"><span data-stu-id="c06f2-208">Jagged Arrays</span></span>  
 <span data-ttu-id="c06f2-209">保留其他数组作为元素的数组被称为数组的数组或交错数组。</span><span class="sxs-lookup"><span data-stu-id="c06f2-209">An array that holds other arrays as elements is known as an array of arrays or a jagged array.</span></span> <span data-ttu-id="c06f2-210">交错数组和交错数组中的每个元素都可以具有一个或多个维度。</span><span class="sxs-lookup"><span data-stu-id="c06f2-210">A jagged array and each element in a jagged array can have one or more dimensions.</span></span> <span data-ttu-id="c06f2-211">有时应用程序中的数据结构是二维而不是矩形。</span><span class="sxs-lookup"><span data-stu-id="c06f2-211">Sometimes the data structure in your application is two-dimensional but not rectangular.</span></span>  
  
 <span data-ttu-id="c06f2-212">下面的示例是月份数组，其中每个元素是天数数组。</span><span class="sxs-lookup"><span data-stu-id="c06f2-212">The following example has an array of months, each element of which is an array of days.</span></span> <span data-ttu-id="c06f2-213">由于不同的月份具有的天数也不同，因此元素不构成矩形二维数组。</span><span class="sxs-lookup"><span data-stu-id="c06f2-213">Because different months have different numbers of days, the elements don’t form a rectangular two-dimensional array.</span></span> <span data-ttu-id="c06f2-214">因此，使用交错数组而不是多维数组。</span><span class="sxs-lookup"><span data-stu-id="c06f2-214">Therefore, a jagged array is used instead of a multidimensional array.</span></span>  
  
 [!code-vb[VbVbalrArrays#21](../../../../../samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrArrays/VB/Class1.vb#21)]  
  
##  <a name="BKMK_ZeroLength"></a> <span data-ttu-id="c06f2-215">零长度数组</span><span class="sxs-lookup"><span data-stu-id="c06f2-215">Zero-Length Arrays</span></span>  
 <span data-ttu-id="c06f2-216">不包含任何元素的数组也称为零长度数组。</span><span class="sxs-lookup"><span data-stu-id="c06f2-216">An array that contains no elements is also called a zero-length array.</span></span> <span data-ttu-id="c06f2-217">保留零长度数组的变量不具有值 `Nothing`。</span><span class="sxs-lookup"><span data-stu-id="c06f2-217">A variable that holds a zero-length array doesn’t have the value `Nothing`.</span></span> <span data-ttu-id="c06f2-218">若要创建一个不包含任何元素的数组，可声明数组的维度之一为 -1，如以下示例所示。</span><span class="sxs-lookup"><span data-stu-id="c06f2-218">To create an array that has no elements, declare one of the array's dimensions to be -1, as the following example shows.</span></span>  
  
 [!code-vb[VbVbalrArrays#14](../../../../../samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrArrays/VB/Class1.vb#14)]  
  
 <span data-ttu-id="c06f2-219">在下列情况下，你可能需要创建一个零长度数组：</span><span class="sxs-lookup"><span data-stu-id="c06f2-219">You might need to create a zero-length array under the following circumstances:</span></span>  
  
-   <span data-ttu-id="c06f2-220">为避免 <xref:System.NullReferenceException> 异常的风险，你的代码必须访问 <xref:System.Array> 类的成员（如 <xref:System.Array.Length%2A> 或 <xref:System.Array.Rank%2A>），或调用一个 [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] 函数（如 <xref:Microsoft.VisualBasic.Information.UBound%2A>）。</span><span class="sxs-lookup"><span data-stu-id="c06f2-220">Without risking a <xref:System.NullReferenceException> exception, your code must access members of the <xref:System.Array> class, such as <xref:System.Array.Length%2A> or <xref:System.Array.Rank%2A>, or call a [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] function such as <xref:Microsoft.VisualBasic.Information.UBound%2A>.</span></span>  
  
-   <span data-ttu-id="c06f2-221">你想通过无需将 `Nothing` 作为特殊情况检查而使得使用的代码更简单。</span><span class="sxs-lookup"><span data-stu-id="c06f2-221">You want to keep the consuming code simpler by not having to check for `Nothing` as a special case.</span></span>  
  
-   <span data-ttu-id="c06f2-222">你的代码与应用程序编程接口 (API) 交互，该接口要求你将一个零长度数组传递到一个或多个过程，或将一个零长度数组返回到一个或多个过程。</span><span class="sxs-lookup"><span data-stu-id="c06f2-222">Your code interacts with an application programming interface (API) that either requires you to pass a zero-length array to one or more procedures or returns a zero-length array from one or more procedures.</span></span>  
  
##  <a name="BKMK_ArraySize"></a> <span data-ttu-id="c06f2-223">数组大小</span><span class="sxs-lookup"><span data-stu-id="c06f2-223">Array Size</span></span>  
 <span data-ttu-id="c06f2-224">数组的大小是数组所有维度的长度的产物。</span><span class="sxs-lookup"><span data-stu-id="c06f2-224">The size of an array is the product of the lengths of all its dimensions.</span></span> <span data-ttu-id="c06f2-225">它表示数组中当前所包含的元素总数。</span><span class="sxs-lookup"><span data-stu-id="c06f2-225">It represents the total number of elements currently contained in the array.</span></span>  
  
 <span data-ttu-id="c06f2-226">下面的示例声明了一个三维数组。</span><span class="sxs-lookup"><span data-stu-id="c06f2-226">The following example declares a three-dimensional array.</span></span>  
  
```vb
Dim prices(3, 4, 5) As Long  
```  
  
 <span data-ttu-id="c06f2-227">变量 `prices` 中数组的总大小为 (3 + 1) x (4 + 1) x (5 + 1) = 120。</span><span class="sxs-lookup"><span data-stu-id="c06f2-227">The overall size of the array in variable `prices` is (3 + 1) x (4 + 1) x (5 + 1) = 120.</span></span>  
  
 <span data-ttu-id="c06f2-228">可以通过使用 <xref:System.Array.Length%2A> 属性查找数组大小。</span><span class="sxs-lookup"><span data-stu-id="c06f2-228">You can find the size of an array by using the <xref:System.Array.Length%2A> property.</span></span> <span data-ttu-id="c06f2-229">可以通过使用 <xref:System.Array.GetLength%2A> 方法查找多维数组的每个维度长度。</span><span class="sxs-lookup"><span data-stu-id="c06f2-229">You can find the length of each dimension of a multi-dimensional array by using the <xref:System.Array.GetLength%2A> method.</span></span>  
  
 <span data-ttu-id="c06f2-230">可以通过向数组变量分配新数组对象或使用 `ReDim` 语句来调整它的大小。</span><span class="sxs-lookup"><span data-stu-id="c06f2-230">You can resize an array variable by assigning a new array object to it or by using the `ReDim` statement.</span></span>  
  
 <span data-ttu-id="c06f2-231">当处理数组大小时，需要记住几件事情。</span><span class="sxs-lookup"><span data-stu-id="c06f2-231">There are several things to keep in mind when dealing with the size of an array.</span></span>  
  
|||  
|---|---|  
|<span data-ttu-id="c06f2-232">维度长度</span><span class="sxs-lookup"><span data-stu-id="c06f2-232">Dimension Length</span></span>|<span data-ttu-id="c06f2-233">每个维度的索引都是从 0 开始，这意味着它的范围介于 0 到其上限之间。</span><span class="sxs-lookup"><span data-stu-id="c06f2-233">The index of each dimension is 0-based, which means it ranges from 0 through its upper bound.</span></span> <span data-ttu-id="c06f2-234">因此，给定维度的长度比该维度已声明的上限大 1。</span><span class="sxs-lookup"><span data-stu-id="c06f2-234">Therefore, the length of a given dimension is greater by 1 than the declared upper bound for that dimension.</span></span>|  
|<span data-ttu-id="c06f2-235">长度限制</span><span class="sxs-lookup"><span data-stu-id="c06f2-235">Length Limits</span></span>|<span data-ttu-id="c06f2-236">数组的每个维度的长度不能超过 `Integer` 数据类型的最大值，即 (2 ^ 31) - 1。</span><span class="sxs-lookup"><span data-stu-id="c06f2-236">The length of every dimension of an array is limited to the maximum value of the `Integer` data type, which is (2 ^ 31) - 1.</span></span> <span data-ttu-id="c06f2-237">但是，数组的总大小还受到系统上可用的内存限制。</span><span class="sxs-lookup"><span data-stu-id="c06f2-237">However, the total size of an array is also limited by the memory available on your system.</span></span> <span data-ttu-id="c06f2-238">如果你尝试初始化的数组超过了可用的 RAM 量，则公共语言运行时将引发 <xref:System.OutOfMemoryException> 异常。</span><span class="sxs-lookup"><span data-stu-id="c06f2-238">If you attempt to initialize an array that exceeds the amount of available RAM, the common language runtime throws an <xref:System.OutOfMemoryException> exception.</span></span>|  
|<span data-ttu-id="c06f2-239">大小和元素大小</span><span class="sxs-lookup"><span data-stu-id="c06f2-239">Size and Element Size</span></span>|<span data-ttu-id="c06f2-240">数组的大小独立于其元素的数据类型。</span><span class="sxs-lookup"><span data-stu-id="c06f2-240">An array's size is independent of the data type of its elements.</span></span> <span data-ttu-id="c06f2-241">大小始终表示元素总数，而不是所占用的存储的字节数。</span><span class="sxs-lookup"><span data-stu-id="c06f2-241">The size always represents the total number of elements, not the number of bytes that they consume in storage.</span></span>|  
|<span data-ttu-id="c06f2-242">内存消耗</span><span class="sxs-lookup"><span data-stu-id="c06f2-242">Memory Consumption</span></span>|<span data-ttu-id="c06f2-243">做出关于数组如何存储在内存中的假设是不可靠的。</span><span class="sxs-lookup"><span data-stu-id="c06f2-243">It is not safe to make any assumptions regarding how an array is stored in memory.</span></span> <span data-ttu-id="c06f2-244">由于不同数据宽度的平台上的存储会有所变化，因此同一数组在 64 位系统上可以占用比在 32 位系统上更多的内存。</span><span class="sxs-lookup"><span data-stu-id="c06f2-244">Storage varies on platforms of different data widths, so the same array can consume more memory on a 64-bit system than on a 32-bit system.</span></span> <span data-ttu-id="c06f2-245">具体取决于数组初始化时的系统配置，公共语言运行时 (CLR) 可以尽可能地将存储分配到靠近包元素的地方，或者将它们全部在自然硬件边界上对齐。</span><span class="sxs-lookup"><span data-stu-id="c06f2-245">Depending on system configuration when you initialize an array, the common language runtime (CLR) can assign storage either to pack elements as close together as possible, or to align them all on natural hardware boundaries.</span></span> <span data-ttu-id="c06f2-246">此外，数组需要存储开销的控制信息，而且每添加一个维度，这种开销随之增加。</span><span class="sxs-lookup"><span data-stu-id="c06f2-246">Also, an array requires a storage overhead for its control information, and this overhead increases with each added dimension.</span></span>|  
  
##  <a name="BKMK_ArrayTypes"></a> <span data-ttu-id="c06f2-247">数组类型和其他类型</span><span class="sxs-lookup"><span data-stu-id="c06f2-247">Array Types and Other Types</span></span>  
 <span data-ttu-id="c06f2-248">每个数组都具有一个数据类型，但不同于它的元素的数据类型。</span><span class="sxs-lookup"><span data-stu-id="c06f2-248">Every array has a data type, but it differs from the data type of its elements.</span></span> <span data-ttu-id="c06f2-249">没有一种数据类型能用于所有数组。</span><span class="sxs-lookup"><span data-stu-id="c06f2-249">There is no single data type for all arrays.</span></span> <span data-ttu-id="c06f2-250">相反，数组的数据类型由数组的维度数量或 *“排名”*，以及数组中元素的数据类型确定。</span><span class="sxs-lookup"><span data-stu-id="c06f2-250">Instead, the data type of an array is determined by the number of dimensions, or *rank*, of the array, and the data type of the elements in the array.</span></span> <span data-ttu-id="c06f2-251">仅当两个数组变量具有相同的排名且它们的元素具有相同的数据类型时，它们才被视为具有相同的数据类型。</span><span class="sxs-lookup"><span data-stu-id="c06f2-251">Two array variables are considered to be of the same data type only when they have the same rank and their elements have the same data type.</span></span> <span data-ttu-id="c06f2-252">数组中维度长度不会影响数组数据类型。</span><span class="sxs-lookup"><span data-stu-id="c06f2-252">The lengths of the dimensions in an array do not influence the array data type.</span></span>  
  
 <span data-ttu-id="c06f2-253">每个数组都继承自 <xref:System.Array?displayProperty=nameWithType> 类，并且你可以声明一个类型为 `Array` 的变量，但不能创建一个类型为 `Array` 的数组。</span><span class="sxs-lookup"><span data-stu-id="c06f2-253">Every array inherits from the <xref:System.Array?displayProperty=nameWithType> class, and you can declare a variable to be of type `Array`, but you cannot create an array of type `Array`.</span></span> <span data-ttu-id="c06f2-254">此外，[ReDim 语句](../../../../visual-basic/language-reference/statements/redim-statement.md)无法对声明为类型 `Array` 的变量执行运算。</span><span class="sxs-lookup"><span data-stu-id="c06f2-254">Also, the [ReDim Statement](../../../../visual-basic/language-reference/statements/redim-statement.md) cannot operate on a variable declared as type `Array`.</span></span> <span data-ttu-id="c06f2-255">出于这些原因，以及为类型安全考虑，最好将每个数组声明为特定类型，例如前面示例中的 `Integer` 。</span><span class="sxs-lookup"><span data-stu-id="c06f2-255">For these reasons, and for type safety, it is advisable to declare every array as a specific type, such as `Integer` in the preceding example.</span></span>  
  
 <span data-ttu-id="c06f2-256">你可以通过几种方式了解到数组及其元素的数据类型。</span><span class="sxs-lookup"><span data-stu-id="c06f2-256">You can find out the data type of either an array or its elements in several ways.</span></span>  
  
-   <span data-ttu-id="c06f2-257">你可以调用变量上的 <xref:System.Object.GetType%2A?displayProperty=nameWithType> 方法来接收此变量的运行时类型的 <xref:System.Type> 对象。</span><span class="sxs-lookup"><span data-stu-id="c06f2-257">You can call the <xref:System.Object.GetType%2A?displayProperty=nameWithType> method on the variable to receive a <xref:System.Type> object for the run-time type of the variable.</span></span> <span data-ttu-id="c06f2-258"><xref:System.Type> 对象可在其属性和方法中保存大量信息。</span><span class="sxs-lookup"><span data-stu-id="c06f2-258">The <xref:System.Type> object holds extensive information in its properties and methods.</span></span>  
  
-   <span data-ttu-id="c06f2-259">你可以将该变量传递到 <xref:Microsoft.VisualBasic.Information.TypeName%2A> 函数来接收包含运行时类型名称的 `String` 。</span><span class="sxs-lookup"><span data-stu-id="c06f2-259">You can pass the variable to the <xref:Microsoft.VisualBasic.Information.TypeName%2A> function to receive a `String` containing the name of run-time type.</span></span>  
  
-   <span data-ttu-id="c06f2-260">你可以将该变量传递到 <xref:Microsoft.VisualBasic.Information.VarType%2A> 函数来接收 `VariantType` 值，该值表示该变量的类型分类。</span><span class="sxs-lookup"><span data-stu-id="c06f2-260">You can pass the variable to the <xref:Microsoft.VisualBasic.Information.VarType%2A> function to receive a `VariantType` value representing the type classification of the variable.</span></span>  
  
 <span data-ttu-id="c06f2-261">下面的示例调用 `TypeName` 函数来确定数组的类型和数组中元素的类型。</span><span class="sxs-lookup"><span data-stu-id="c06f2-261">The following example calls the `TypeName` function to determine the type of the array and the type of the elements in the array.</span></span> <span data-ttu-id="c06f2-262">数组类型是 `Integer(,)` 而数组中的元素的类型是 `Integer`。</span><span class="sxs-lookup"><span data-stu-id="c06f2-262">The array type is `Integer(,)` and the elements in the array are of type `Integer`.</span></span>  
  
 [!code-vb[VbVbalrArrays#15](../../../../../samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrArrays/VB/Class1.vb#15)]  
  
##  <a name="BKMK_Collections"></a> <span data-ttu-id="c06f2-263">作为数组的替代方法的集合</span><span class="sxs-lookup"><span data-stu-id="c06f2-263">Collections as an Alternative to Arrays</span></span>  
 <span data-ttu-id="c06f2-264">数组最适用于创建和使用固定数量的强类型化对象。</span><span class="sxs-lookup"><span data-stu-id="c06f2-264">Arrays are most useful for creating and working with a fixed number of strongly typed objects.</span></span> <span data-ttu-id="c06f2-265">集合提供更灵活的方式来使用对象组。</span><span class="sxs-lookup"><span data-stu-id="c06f2-265">Collections provide a more flexible way to work with groups of objects.</span></span> <span data-ttu-id="c06f2-266">与数组不同，你使用的对象组会随着应用程序更改的需要动态地放大和缩小。</span><span class="sxs-lookup"><span data-stu-id="c06f2-266">Unlike arrays, the group of objects that you work with can grow and shrink dynamically as the needs of the application change.</span></span>  
  
 <span data-ttu-id="c06f2-267">如果需要更改数组大小，必须使用 [ReDim 语句](../../../../visual-basic/language-reference/statements/redim-statement.md)。</span><span class="sxs-lookup"><span data-stu-id="c06f2-267">If you need to change the size of an array, you must use the [ReDim Statement](../../../../visual-basic/language-reference/statements/redim-statement.md).</span></span> <span data-ttu-id="c06f2-268">当你这样做时，[!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] 会新建一个数组，并释放旧数组以供处置。</span><span class="sxs-lookup"><span data-stu-id="c06f2-268">When you do this, [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] creates a new array and releases the previous array for disposal.</span></span> <span data-ttu-id="c06f2-269">这需要执行时间。</span><span class="sxs-lookup"><span data-stu-id="c06f2-269">This takes execution time.</span></span> <span data-ttu-id="c06f2-270">因此，如果你正在使用的项目数量频繁变化，或者你无法预测你所需的最大项目数量，使用集合也许能够获得更好的性能。</span><span class="sxs-lookup"><span data-stu-id="c06f2-270">Therefore, if the number of items you are working with changes frequently, or you cannot predict the maximum number of items you need, you might obtain better performance using a collection.</span></span>  
  
 <span data-ttu-id="c06f2-271">对于某些集合，你可以为放入集合中的任何对象分配一个密钥，这样你便可以使用该密钥快速检索此对象。</span><span class="sxs-lookup"><span data-stu-id="c06f2-271">For some collections, you can assign a key to any object that you put into the collection so that you can quickly retrieve the object by using the key.</span></span>  
  
 <span data-ttu-id="c06f2-272">如果你的集合中只包含一种数据类型的元素，你可以使用 <xref:System.Collections.Generic?displayProperty=nameWithType> 命名空间中的一个类。</span><span class="sxs-lookup"><span data-stu-id="c06f2-272">If your collection contains elements of only one data type, you can use one of the classes in the <xref:System.Collections.Generic?displayProperty=nameWithType> namespace.</span></span> <span data-ttu-id="c06f2-273">泛型集合强制类型安全，因此无法向其添加任何其他数据类型。</span><span class="sxs-lookup"><span data-stu-id="c06f2-273">A generic collection enforces type safety so that no other data type can be added to it.</span></span> <span data-ttu-id="c06f2-274">当你从泛型集合检索元素时，你无需确定其数据类型或对其进行转换。</span><span class="sxs-lookup"><span data-stu-id="c06f2-274">When you retrieve an element from a generic collection, you do not have to determine its data type or convert it.</span></span>  
  
 <span data-ttu-id="c06f2-275">有关集合的详细信息，请参阅[集合](http://msdn.microsoft.com/library/e76533a9-5033-4a0b-b003-9c2be60d185b)。</span><span class="sxs-lookup"><span data-stu-id="c06f2-275">For more information about collections, see [Collections](http://msdn.microsoft.com/library/e76533a9-5033-4a0b-b003-9c2be60d185b).</span></span>  
  
### <a name="example"></a><span data-ttu-id="c06f2-276">示例</span><span class="sxs-lookup"><span data-stu-id="c06f2-276">Example</span></span>  
 <span data-ttu-id="c06f2-277">下面的示例使用 [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] 泛型类 <xref:System.Collections.Generic.List%601?displayProperty=nameWithType> 创建 `Customer` 对象的列表集合。</span><span class="sxs-lookup"><span data-stu-id="c06f2-277">The following example uses the [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] generic class <xref:System.Collections.Generic.List%601?displayProperty=nameWithType> to create a list collection of `Customer` objects.</span></span>  
  
 [!code-vb[VbVbalrArrays#1](../../../../../samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrArrays/VB/Class1.vb#1)]  
  
 <span data-ttu-id="c06f2-278">`CustomerFile` 集合的声明指示，它仅可以包含类型为 `Customer`的元素。</span><span class="sxs-lookup"><span data-stu-id="c06f2-278">The declaration of the `CustomerFile` collection specifies that it can contain elements only of type `Customer`.</span></span> <span data-ttu-id="c06f2-279">它还提供了大小为 200 个元素的初始容量。</span><span class="sxs-lookup"><span data-stu-id="c06f2-279">It also provides for an initial capacity of 200 elements.</span></span> <span data-ttu-id="c06f2-280">过程 `AddNewCustomer` 检查新元素的有效性，然后将其添加到集合。</span><span class="sxs-lookup"><span data-stu-id="c06f2-280">The procedure `AddNewCustomer` checks the new element for validity and then adds it to the collection.</span></span> <span data-ttu-id="c06f2-281">过程 `PrintCustomers` 使用 `For Each` 循环来遍历该集合并显示其元素。</span><span class="sxs-lookup"><span data-stu-id="c06f2-281">The procedure `PrintCustomers` uses a `For Each` loop to traverse the collection and display its elements.</span></span>  
  
## <a name="related-topics"></a><span data-ttu-id="c06f2-282">相关主题</span><span class="sxs-lookup"><span data-stu-id="c06f2-282">Related Topics</span></span>  
  
|<span data-ttu-id="c06f2-283">术语</span><span class="sxs-lookup"><span data-stu-id="c06f2-283">Term</span></span>|<span data-ttu-id="c06f2-284">定义</span><span class="sxs-lookup"><span data-stu-id="c06f2-284">Definition</span></span>|  
|----------|----------------|  
|[<span data-ttu-id="c06f2-285">Array Dimensions in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="c06f2-285">Array Dimensions in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/arrays/array-dimensions.md)|<span data-ttu-id="c06f2-286">在数组中解释级别和维度。</span><span class="sxs-lookup"><span data-stu-id="c06f2-286">Explains rank and dimensions in arrays.</span></span>|  
|[<span data-ttu-id="c06f2-287">如何：在 Visual Basic 中初始化数组变量</span><span class="sxs-lookup"><span data-stu-id="c06f2-287">How to: Initialize an Array Variable in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/arrays/how-to-initialize-an-array-variable.md)|<span data-ttu-id="c06f2-288">说明如何用初始值填充数组。</span><span class="sxs-lookup"><span data-stu-id="c06f2-288">Describes how to populate arrays with initial values.</span></span>|  
|[<span data-ttu-id="c06f2-289">如何：在 Visual Basic 中对数组进行排序</span><span class="sxs-lookup"><span data-stu-id="c06f2-289">How to: Sort An Array in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/arrays/how-to-sort-an-array.md)|<span data-ttu-id="c06f2-290">显示如何按字母先后顺序对数组元素进行排序。</span><span class="sxs-lookup"><span data-stu-id="c06f2-290">Shows how to sort the elements of an array alphabetically.</span></span>|  
|[<span data-ttu-id="c06f2-291">如何：将一个数组赋给另一个数组</span><span class="sxs-lookup"><span data-stu-id="c06f2-291">How to: Assign One Array to Another Array</span></span>](../../../../visual-basic/programming-guide/language-features/arrays/how-to-assign-one-array-to-another-array.md)|<span data-ttu-id="c06f2-292">说明将数组分配到另一个数组变量的规则和步骤。</span><span class="sxs-lookup"><span data-stu-id="c06f2-292">Describes the rules and steps for assigning an array to another array variable.</span></span>|  
|[<span data-ttu-id="c06f2-293">数组疑难解答</span><span class="sxs-lookup"><span data-stu-id="c06f2-293">Troubleshooting Arrays</span></span>](../../../../visual-basic/programming-guide/language-features/arrays/troubleshooting-arrays.md)|<span data-ttu-id="c06f2-294">讨论在使用数组时出现的一些常见问题。</span><span class="sxs-lookup"><span data-stu-id="c06f2-294">Discusses some common problems that arise when working with arrays.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="c06f2-295">另请参阅</span><span class="sxs-lookup"><span data-stu-id="c06f2-295">See Also</span></span>  
 <xref:System.Array>  
 [<span data-ttu-id="c06f2-296">Dim 语句</span><span class="sxs-lookup"><span data-stu-id="c06f2-296">Dim Statement</span></span>](../../../../visual-basic/language-reference/statements/dim-statement.md)  
 [<span data-ttu-id="c06f2-297">ReDim 语句</span><span class="sxs-lookup"><span data-stu-id="c06f2-297">ReDim Statement</span></span>](../../../../visual-basic/language-reference/statements/redim-statement.md)
