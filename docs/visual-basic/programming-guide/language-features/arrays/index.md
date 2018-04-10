---
title: Visual Basic 中的数组
ms.custom: ''
ms.date: 12/06/2017
ms.prod: .net
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vb.Array
helpviewer_keywords:
- arrays [Visual Basic]
- Visual Basic, arrays
ms.assetid: dbf29737-b589-4443-bee6-a27588d9c67e
author: rpetrusha
ms.author: ronpet
ms.manager: wpickett
ms.openlocfilehash: d223ca8b0ff59a13c31fa777e5cb6a97918421c6
ms.sourcegitcommit: 01ea3686e74ff05e4f6de3d8d46dc603d051ec00
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/13/2017
---
# <a name="arrays-in-visual-basic"></a><span data-ttu-id="dfa60-102">Visual Basic 中的数组</span><span class="sxs-lookup"><span data-stu-id="dfa60-102">Arrays in Visual Basic</span></span>
<span data-ttu-id="dfa60-103">数组是一组值，称为*元素*，，逻辑上彼此相关。</span><span class="sxs-lookup"><span data-stu-id="dfa60-103">An array is a set of values, which are termed *elements*, that are logically related to each other.</span></span> <span data-ttu-id="dfa60-104">例如，数组可能包含的语法学校; 每个年级的学生的数量数组的每个元素是单个年级的学生的数量。</span><span class="sxs-lookup"><span data-stu-id="dfa60-104">For example, an array may consist of the number of students in each grade in a grammar school; each element of the array is the number of students in a single grade.</span></span> <span data-ttu-id="dfa60-105">同样，数组可能包含的类，则的学生成绩数组的每个元素是单个评分。</span><span class="sxs-lookup"><span data-stu-id="dfa60-105">Similarly, an array may consist of a student's grades for a class; each element of the array is a single grade.</span></span>    

<span data-ttu-id="dfa60-106">它是可能的单个变量来存储每个数据项。</span><span class="sxs-lookup"><span data-stu-id="dfa60-106">It is possible individual variables to store each of our data items.</span></span> <span data-ttu-id="dfa60-107">例如，如果我们的应用程序分析学生成绩，我们可以使用单独的变量的每个学生成绩，如`englishGrade1`， `englishGrade2`，等等。此方法具有三个主要限制：</span><span class="sxs-lookup"><span data-stu-id="dfa60-107">For example, if our application analyzes student grades, we can use a separate variable for each student's grade, such as `englishGrade1`, `englishGrade2`, etc. This approach has three major limitations:</span></span>
- <span data-ttu-id="dfa60-108">我们必须知道在设计时，我们需要处理完全多少年级。</span><span class="sxs-lookup"><span data-stu-id="dfa60-108">We have to know at design time exactly how many grades we have to handle.</span></span>
- <span data-ttu-id="dfa60-109">快速处理大量年级变得非常笨拙。</span><span class="sxs-lookup"><span data-stu-id="dfa60-109">Handling large numbers of grades quickly becomes unwieldy.</span></span> <span data-ttu-id="dfa60-110">这反过来会使应用程序更可能有严重的 bug。</span><span class="sxs-lookup"><span data-stu-id="dfa60-110">This in turn makes an application much more likely to have serious bugs.</span></span>
- <span data-ttu-id="dfa60-111">很难维护。</span><span class="sxs-lookup"><span data-stu-id="dfa60-111">It is difficult to maintain.</span></span> <span data-ttu-id="dfa60-112">我们添加每个新年级，需要应用程序进行修改、 重新编译，并重新部署。</span><span class="sxs-lookup"><span data-stu-id="dfa60-112">Each new grade that we add requires that the application be modified, recompiled, and redeployed.</span></span>  
 
 <span data-ttu-id="dfa60-113">通过使用一个数组，你可以通过相同的名称，请参阅这些相关的值并使用一个数字，称为*索引*或*下标*若要确定基于数组中其位置的单个元素。</span><span class="sxs-lookup"><span data-stu-id="dfa60-113">By using an array, you can refer to these related values by the same name, and use a number that’s called an *index* or *subscript* to identify an individual element based on its position in the array.</span></span> <span data-ttu-id="dfa60-114">数组范围从 0 到减 1 所得的数组中的元素总数的索引。</span><span class="sxs-lookup"><span data-stu-id="dfa60-114">The indexes of an array range from 0 to one less than the total number of elements in the array.</span></span> <span data-ttu-id="dfa60-115">当你使用 Visual Basic 语法来定义数组的大小时，你将指定其最高的索引，不的数组中的元素总数。</span><span class="sxs-lookup"><span data-stu-id="dfa60-115">When you use Visual Basic syntax to define the size of an array, you specify its highest index, not the total number of elements in the array.</span></span> <span data-ttu-id="dfa60-116">你可以使用作为一个单元中，数组和来循环访问其元素的功能使你无需知道它包含在设计时完全多少个元素。</span><span class="sxs-lookup"><span data-stu-id="dfa60-116">You can work with the array as a unit, and the ability to iterate its elements frees you from needing to know exactly how many elements it contains at design time.</span></span>
  
 <span data-ttu-id="dfa60-117">在进行说明之前，请看几个简单的示例：</span><span class="sxs-lookup"><span data-stu-id="dfa60-117">Some quick examples before explanation:</span></span>  
  
```vb  
' Declare a single-dimension array of 5 numbers.  
Dim numbers(4) As Integer   
  
'Declare a single-dimension array and set its 4 values.  
Dim numbers = New Integer() {1, 2, 4, 8}  
  
' Change the size of an existing array to 16 elements and retain the current values.
ReDim Preserve numbers(15)
  
' Redefine the size of an existing array and reset the values.
ReDim numbers(15)  
  
' Declare a 6 x 6 multidimensional array.
Dim matrix(5, 5) As Double  
  
' Declare a 4 x 3 multidimensional array and set array element values.  
Dim matrix = New Integer(3, 2) {{1, 2, 3}, {2, 3, 4}, {3, 4, 5}, {4, 5, 6}}  
  
' Declare a jagged array  
Dim sales()() As Double = New Double(11)() {}  
```  
  
 ## <a name="in-this-article"></a><span data-ttu-id="dfa60-118">本文内容</span><span class="sxs-lookup"><span data-stu-id="dfa60-118">In this article</span></span>
  
- [<span data-ttu-id="dfa60-119">简单数组中的数组元素</span><span class="sxs-lookup"><span data-stu-id="dfa60-119">Array elements in a simple array</span></span>](#array-elements-in-a-simple-array)  
  
- [<span data-ttu-id="dfa60-120">创建的数组</span><span class="sxs-lookup"><span data-stu-id="dfa60-120">Creating an array</span></span>](#creating-an-array)  
  
- [<span data-ttu-id="dfa60-121">将值存储在数组中</span><span class="sxs-lookup"><span data-stu-id="dfa60-121">Storing values in an array</span></span>](#storing-values-in-an-array)  
  
- [<span data-ttu-id="dfa60-122">填充数组与数组文本</span><span class="sxs-lookup"><span data-stu-id="dfa60-122">Populating an array with array literals</span></span>](#populating-an-array-with-array-literals)  
  
- [<span data-ttu-id="dfa60-123">循环访问数组</span><span class="sxs-lookup"><span data-stu-id="dfa60-123">Iterating through an array</span></span>](#iterating-through-an-array)  
  
- [<span data-ttu-id="dfa60-124">数组大小</span><span class="sxs-lookup"><span data-stu-id="dfa60-124">Array size</span></span>](#BKMK_ArraySize)  

- [<span data-ttu-id="dfa60-125">数组类型</span><span class="sxs-lookup"><span data-stu-id="dfa60-125">The array type</span></span>](#the-array-type)  
  
- [<span data-ttu-id="dfa60-126">作为返回值和参数的数组</span><span class="sxs-lookup"><span data-stu-id="dfa60-126">Arrays as return values and parameters</span></span>](#arrays-as-return-values-and-parameters)  
- [<span data-ttu-id="dfa60-127">交错的数组</span><span class="sxs-lookup"><span data-stu-id="dfa60-127">Jagged arrays</span></span>](#jagged-arrays)  
  
- [<span data-ttu-id="dfa60-128">零长度数组</span><span class="sxs-lookup"><span data-stu-id="dfa60-128">Zero-length arrays</span></span>](#zero-length-arrays)  

- [<span data-ttu-id="dfa60-129">拆分数组</span><span class="sxs-lookup"><span data-stu-id="dfa60-129">Splitting an array</span></span>](#splitting-an-array)
  
- [<span data-ttu-id="dfa60-130">作为数组的替代方法的集合</span><span class="sxs-lookup"><span data-stu-id="dfa60-130">Collections as an alternative to arrays</span></span>](#collections-as-an-alternative-to-arrays)  
  
##  <a name="array-elements-in-a-simple-array"></a><span data-ttu-id="dfa60-131">简单数组中的数组元素</span><span class="sxs-lookup"><span data-stu-id="dfa60-131">Array elements in a simple array</span></span>  

<span data-ttu-id="dfa60-132">让我们创建一个名为数组`students`存储语法学校中每个年级的学生的数量。</span><span class="sxs-lookup"><span data-stu-id="dfa60-132">Let's create an array named `students` to store the number of students in each grade in a grammar school.</span></span> <span data-ttu-id="dfa60-133">这些元素的索引范围为 0 到 6。</span><span class="sxs-lookup"><span data-stu-id="dfa60-133">The indexes of the elements range from 0 through 6.</span></span> <span data-ttu-id="dfa60-134">使用此数组是比声明七个变量更简单。</span><span class="sxs-lookup"><span data-stu-id="dfa60-134">Using this array is simpler than declaring seven variables.</span></span>

<span data-ttu-id="dfa60-135">下图显示`students`数组。</span><span class="sxs-lookup"><span data-stu-id="dfa60-135">The following illustration shows the `students` array.</span></span> <span data-ttu-id="dfa60-136">对于数组的每个元素：</span><span class="sxs-lookup"><span data-stu-id="dfa60-136">For each element of the array:</span></span>  
  
-   <span data-ttu-id="dfa60-137">元素索引表示年级（索引 0 表示幼儿园）。</span><span class="sxs-lookup"><span data-stu-id="dfa60-137">The index of the element represents the grade (index 0 represents kindergarten).</span></span>
  
-   <span data-ttu-id="dfa60-138">元素中包含的值表示每个年级的学生数量。</span><span class="sxs-lookup"><span data-stu-id="dfa60-138">The value that’s contained in the element represents the number of students in that grade.</span></span>
  
 <span data-ttu-id="dfa60-139">![显示学生人数的数组图片](../../../../visual-basic/programming-guide/language-features/arrays/media/arrayexampleschool.gif " ArrayExampleSchool ")</span><span class="sxs-lookup"><span data-stu-id="dfa60-139">![Picture of array showing numbers of students](../../../../visual-basic/programming-guide/language-features/arrays/media/arrayexampleschool.gif "ArrayExampleSchool")</span></span>  
<span data-ttu-id="dfa60-140">“学生”数组中的元素</span><span class="sxs-lookup"><span data-stu-id="dfa60-140">Elements of the "students" array</span></span>  
 
<span data-ttu-id="dfa60-141">下面的示例包含 Visual Basic 代码中创建和使用数组：</span><span class="sxs-lookup"><span data-stu-id="dfa60-141">The following example contains the Visual Basic code that creates and uses the array:</span></span>

 [!code-vb[simple-array](../../../../../samples/snippets/visualbasic/programming-guide/language-features/arrays/simple-array.vb)]  

<span data-ttu-id="dfa60-142">该示例执行三项操作：</span><span class="sxs-lookup"><span data-stu-id="dfa60-142">The example does three things:</span></span>

- <span data-ttu-id="dfa60-143">它声明`students`具有七个元素的数组。</span><span class="sxs-lookup"><span data-stu-id="dfa60-143">It declares a `students` array with seven elements.</span></span> <span data-ttu-id="dfa60-144">数`6`数组中声明指示数组中的最后一个索引; 它是一个小于数组中元素的数目。</span><span class="sxs-lookup"><span data-stu-id="dfa60-144">The number `6` in the array declaration indicates the last index in the array; it is one less than the number of elements in the array.</span></span>
- <span data-ttu-id="dfa60-145">它将值分配给数组中每个元素。</span><span class="sxs-lookup"><span data-stu-id="dfa60-145">It assigns values to each element in the array.</span></span> <span data-ttu-id="dfa60-146">通过使用数组名称并在括号中包括单个元素的索引访问数组元素。</span><span class="sxs-lookup"><span data-stu-id="dfa60-146">Array elements are accessed by using the array name and including the index of the individual element in parentheses.</span></span>
- <span data-ttu-id="dfa60-147">它将列出该数组的每个值。</span><span class="sxs-lookup"><span data-stu-id="dfa60-147">It lists each value of the array.</span></span> <span data-ttu-id="dfa60-148">该示例使用[ `For` ](../../../language-reference/statements/for-next-statement.md)语句可以访问该数组的每个元素按其索引号。</span><span class="sxs-lookup"><span data-stu-id="dfa60-148">The example uses a [`For`](../../../language-reference/statements/for-next-statement.md) statement to access each element of the array by its index number.</span></span>
  
 <span data-ttu-id="dfa60-149">`students`数组在前面的示例是一个一维数组，因为它使用一个索引。</span><span class="sxs-lookup"><span data-stu-id="dfa60-149">The `students` array in the preceding example is a one-dimensional array because it uses one index.</span></span> <span data-ttu-id="dfa60-150">使用多个索引或下标的数组称为*多维*。</span><span class="sxs-lookup"><span data-stu-id="dfa60-150">An array that uses more than one index or subscript is called *multidimensional*.</span></span> <span data-ttu-id="dfa60-151">有关详细信息，请参阅本文的其余部分和[在 Visual Basic 中的数组维数](../../../../visual-basic/programming-guide/language-features/arrays/array-dimensions.md)。</span><span class="sxs-lookup"><span data-stu-id="dfa60-151">For more information, see the rest of this article and [Array Dimensions in Visual Basic](../../../../visual-basic/programming-guide/language-features/arrays/array-dimensions.md).</span></span>  
  
##  <a name="creating-an-array"></a><span data-ttu-id="dfa60-152">创建数组</span><span class="sxs-lookup"><span data-stu-id="dfa60-152">Creating an Array</span></span>  
 
<span data-ttu-id="dfa60-153">你可以通过多种方式来定义非数组的大小：</span><span class="sxs-lookup"><span data-stu-id="dfa60-153">You can define the size of an array in several ways:</span></span> 

- <span data-ttu-id="dfa60-154">声明数组时，你可以指定大小：</span><span class="sxs-lookup"><span data-stu-id="dfa60-154">You can specify the size when the array is declared:</span></span>
  
    [!code-vb[creating1](../../../../../samples/snippets/visualbasic/programming-guide/language-features/arrays/create-array.vb#1)]  
  
 - <span data-ttu-id="dfa60-155">你可以使用`New`子句提供数组的大小，创建时：</span><span class="sxs-lookup"><span data-stu-id="dfa60-155">You can use a `New` clause to supply the size of an array when it’s created:</span></span>  
  
    [!code-vb[creating2](../../../../../samples/snippets/visualbasic/programming-guide/language-features/arrays/create-array.vb#2)]  
  
 <span data-ttu-id="dfa60-156">如果你有现有数组，你可以通过使用来重新定义其大小[ `Redim` ](../../../../visual-basic/language-reference/statements/redim-statement.md)语句。</span><span class="sxs-lookup"><span data-stu-id="dfa60-156">If you have an existing array, you can redefine its size by using the [`Redim`](../../../../visual-basic/language-reference/statements/redim-statement.md) statement.</span></span> <span data-ttu-id="dfa60-157">你可以指定`Redim`语句保留在阵列，值也可以指定它创建一个空数组。</span><span class="sxs-lookup"><span data-stu-id="dfa60-157">You can specify that the `Redim` statement keep the values that are in the array, or you can specify that it create an empty array.</span></span> <span data-ttu-id="dfa60-158">下面的示例演示了用 `Redim` 语句来修改现有数组的大小的不同用法。</span><span class="sxs-lookup"><span data-stu-id="dfa60-158">The following example shows different uses of the `Redim` statement to modify the size of an existing array.</span></span>  
  
 [!code-vb[redimensioning](../../../../../samples/snippets/visualbasic/programming-guide/language-features/arrays/create-array.vb#3)]  
  
 <span data-ttu-id="dfa60-159">有关详细信息，请参阅[ReDim 语句](../../../../visual-basic/language-reference/statements/redim-statement.md)。</span><span class="sxs-lookup"><span data-stu-id="dfa60-159">For more information, see the [ReDim Statement](../../../../visual-basic/language-reference/statements/redim-statement.md).</span></span>  
  
##  <a name="storing-values-in-an-array"></a><span data-ttu-id="dfa60-160">存储数组中的值</span><span class="sxs-lookup"><span data-stu-id="dfa60-160">Storing Values in an Array</span></span>
 
 <span data-ttu-id="dfa60-161">你可以通过使用类型 `Integer`的索引访问数组中的每个位置。</span><span class="sxs-lookup"><span data-stu-id="dfa60-161">You can access each location in an array by using an index of type `Integer`.</span></span> <span data-ttu-id="dfa60-162">你可以使用括号内的索引来引用每个数组位置，从而存储和检索数组中的值。</span><span class="sxs-lookup"><span data-stu-id="dfa60-162">You can store and retrieve values in an array by referencing each array location by using its index enclosed in parentheses.</span></span> <span data-ttu-id="dfa60-163">对于多维数组的索引用逗号 （，） 分隔。</span><span class="sxs-lookup"><span data-stu-id="dfa60-163">Indexes for multidimensional arrays are separated by commas (,).</span></span> <span data-ttu-id="dfa60-164">每个数组维度都需要一个索引。</span><span class="sxs-lookup"><span data-stu-id="dfa60-164">You need one index for each array dimension.</span></span> 

<span data-ttu-id="dfa60-165">下面的示例演示用于存储和检索值在数组中的一些语句。</span><span class="sxs-lookup"><span data-stu-id="dfa60-165">The following example shows some statements that store and retrieve values in arrays.</span></span>
  
 [!code-vb[store-and-retrieve](../../../../../samples/snippets/visualbasic/programming-guide/language-features/arrays/store-and-retrieve.vb)]  
  
## <a name="populating-an-array-with-array-literals"></a><span data-ttu-id="dfa60-166">填充数组与数组文本</span><span class="sxs-lookup"><span data-stu-id="dfa60-166">Populating an array with array literals</span></span>
 <span data-ttu-id="dfa60-167">通过使用数组文本，你可以创建它时填充一组初始的值的数组。</span><span class="sxs-lookup"><span data-stu-id="dfa60-167">By using an array literal, you can populate an array with an initial set of values at the same time that you create it.</span></span> <span data-ttu-id="dfa60-168">数组文本包含用逗号分隔的值列表，这些值被括在括号内 (`{}`)。</span><span class="sxs-lookup"><span data-stu-id="dfa60-168">An array literal consists of a list of comma-separated values that are enclosed in braces (`{}`).</span></span>  
  
 <span data-ttu-id="dfa60-169">通过使用数组文本创建数组时，可以提供数组类型或使用类型推理功能来确定数组类型。</span><span class="sxs-lookup"><span data-stu-id="dfa60-169">When you create an array by using an array literal, you can either supply the array type or use type inference to determine the array type.</span></span> <span data-ttu-id="dfa60-170">下面的示例演示这两个选项。</span><span class="sxs-lookup"><span data-stu-id="dfa60-170">The following example shows both options.</span></span>  
  
 [!code-vb[create-with-literals](../../../../../samples/snippets/visualbasic/programming-guide/language-features/arrays/create-array.vb#4)]  
  
 <span data-ttu-id="dfa60-171">当你使用类型推理时，数组的类型由*基准类型*中的文本值列表。</span><span class="sxs-lookup"><span data-stu-id="dfa60-171">When you use type inference, the type of the array is determined by the *dominant type* in the list of literal values.</span></span> <span data-ttu-id="dfa60-172">基准类型是数组中的所有其他类型可以扩大到其中的类型。</span><span class="sxs-lookup"><span data-stu-id="dfa60-172">The dominant type is the type to which all other types in the array can widen.</span></span> <span data-ttu-id="dfa60-173">如果无法确定此唯一类型，基准类型是数组中所有其他类型可以缩小到的唯一类型。</span><span class="sxs-lookup"><span data-stu-id="dfa60-173">If this unique type can’t be determined, the dominant type is the unique type to which all other types in the array can narrow.</span></span> <span data-ttu-id="dfa60-174">如果无法确定为这两种唯一类型之一，则基准类型是 `Object`。</span><span class="sxs-lookup"><span data-stu-id="dfa60-174">If neither of these unique types can be determined, the dominant type is `Object`.</span></span> <span data-ttu-id="dfa60-175">例如，如果提供给数组文本的值的列表包含 `Integer`、 `Long`和 `Double`类型的值，则生成的数组类型是 `Double`。</span><span class="sxs-lookup"><span data-stu-id="dfa60-175">For example, if the list of values that’s supplied to the array literal contains values of type `Integer`, `Long`, and `Double`, the resulting array is of type `Double`.</span></span> <span data-ttu-id="dfa60-176">因为`Integer`和`Long`都仅扩大到`Double`，`Double`是基准类型。</span><span class="sxs-lookup"><span data-stu-id="dfa60-176">Because `Integer` and `Long` widen only to `Double`, `Double` is the dominant type.</span></span> <span data-ttu-id="dfa60-177">有关详细信息，请参阅 [Widening and Narrowing Conversions](../../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md)。</span><span class="sxs-lookup"><span data-stu-id="dfa60-177">For more information, see [Widening and Narrowing Conversions](../../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md).</span></span> 
 
> [!NOTE] 
> <span data-ttu-id="dfa60-178">类型推理仅用于定义为类型成员中的本地变量的数组。</span><span class="sxs-lookup"><span data-stu-id="dfa60-178">You can use type inference only for arrays that are defined as local variables in a type member.</span></span> <span data-ttu-id="dfa60-179">如果缺少显式类型定义，则使用数组文本，在类级别定义的数组是类型的`Object[]`。</span><span class="sxs-lookup"><span data-stu-id="dfa60-179">If an explicit type definition is absent, arrays defined with array literals at the class level are of type `Object[]`.</span></span> <span data-ttu-id="dfa60-180">有关详细信息，请参阅[局部类型推理](../variables/local-type-inference.md)。</span><span class="sxs-lookup"><span data-stu-id="dfa60-180">For more information, see [Local type inference](../variables/local-type-inference.md).</span></span> 

<span data-ttu-id="dfa60-181">请注意，上面的示例定义`values`类型的数组作为`Double`即使所有数组文本的类型都是`Integer`。</span><span class="sxs-lookup"><span data-stu-id="dfa60-181">Note that the previous example defines `values` as an array of type `Double` even though all the array literals are of type `Integer`.</span></span> <span data-ttu-id="dfa60-182">您可以创建此数组，因为数组文本中的值可以扩大到`Double`值。</span><span class="sxs-lookup"><span data-stu-id="dfa60-182">You can create this array because the values in the array literal can widen to `Double` values.</span></span> 
  
 <span data-ttu-id="dfa60-183">你还可以创建和使用填充多维数组*嵌套数组文本*。</span><span class="sxs-lookup"><span data-stu-id="dfa60-183">You can also create and populate a multidimensional array by using *nested array literals*.</span></span> <span data-ttu-id="dfa60-184">嵌套的数组文本必须具有与生成的数组保持一致维度的数目。</span><span class="sxs-lookup"><span data-stu-id="dfa60-184">Nested array literals must have a number of dimensions that’s consistent with the resulting array.</span></span> <span data-ttu-id="dfa60-185">下面的示例通过使用嵌套的数组文本创建二维整数数组。</span><span class="sxs-lookup"><span data-stu-id="dfa60-185">The following example creates a two-dimensional array of integers by using nested array literals.</span></span>  
  
 [!code-vb[nested-array-literals](../../../../../samples/snippets/visualbasic/programming-guide/language-features/arrays/create-array.vb#5)]  
  
<span data-ttu-id="dfa60-186">在使用嵌套的数组文本创建并填充数组时，如果嵌套的数组文本中的元素的数目不匹配，则会发生错误。</span><span class="sxs-lookup"><span data-stu-id="dfa60-186">When using nested array literals to create and populate an array, an error occurs if the number of elements in the nested array literals don't match.</span></span> <span data-ttu-id="dfa60-187">如果你显式声明的数组变量具有不同数量的维度比数组文本，也会发生错误。</span><span class="sxs-lookup"><span data-stu-id="dfa60-187">An error also occurs if you explicitly declare the array variable to have a different number of dimensions than the array literals.</span></span> 
  
<span data-ttu-id="dfa60-188">就像可以对于一维数组，你可以依赖类型推断，使用嵌套的数组文本创建多维数组时。</span><span class="sxs-lookup"><span data-stu-id="dfa60-188">Just as you can for one-dimensional arrays, you can rely on type inference when creating a multidimensional array with nested array literals.</span></span> <span data-ttu-id="dfa60-189">推断出的类型是所有嵌套级别的所有数组文本中的所有值的基准类型。</span><span class="sxs-lookup"><span data-stu-id="dfa60-189">The inferred type is the dominant type for all the values in all the array literals for all nesting level.</span></span> <span data-ttu-id="dfa60-190">下面的示例创建类型的一个二维数组`Double[,]`的类型的值从`Integer`和`Double`。</span><span class="sxs-lookup"><span data-stu-id="dfa60-190">The following example creates a two-dimensional array of type `Double[,]` from values that are of type `Integer` and `Double`.</span></span>  
  
 [!code-vb[nested-type-inference](../../../../../samples/snippets/visualbasic/programming-guide/language-features/arrays/create-array.vb#6)]  
  
 <span data-ttu-id="dfa60-191">有关其他示例，请参阅[如何：在 Visual Basic 中初始化数组变量](../../../../visual-basic/programming-guide/language-features/arrays/how-to-initialize-an-array-variable.md)。</span><span class="sxs-lookup"><span data-stu-id="dfa60-191">For additional examples, see [How to: Initialize an Array Variable in Visual Basic](../../../../visual-basic/programming-guide/language-features/arrays/how-to-initialize-an-array-variable.md).</span></span>  
  
##  <a name="iterating-through-an-array"></a><span data-ttu-id="dfa60-192">循环访问数组</span><span class="sxs-lookup"><span data-stu-id="dfa60-192">Iterating through an array</span></span>  
 <span data-ttu-id="dfa60-193">当循环访问数组时，你可以访问数组中的每个元素，从最低到最高或从高到低的顺序。</span><span class="sxs-lookup"><span data-stu-id="dfa60-193">When you iterate through an array, you access each element in the array from the lowest index to the highest or from the highest to the lowest.</span></span> <span data-ttu-id="dfa60-194">通常情况下，使用这两个使用[为...下一条语句](../../../../visual-basic/language-reference/statements/for-next-statement.md)或[每个...下一条语句](../../../../visual-basic/language-reference/statements/for-each-next-statement.md)循环访问数组的元素。</span><span class="sxs-lookup"><span data-stu-id="dfa60-194">Typically, use use either the [For...Next Statement](../../../../visual-basic/language-reference/statements/for-next-statement.md) or the [For Each...Next Statement](../../../../visual-basic/language-reference/statements/for-each-next-statement.md) to iterate through the elements of an array.</span></span> <span data-ttu-id="dfa60-195">如果您不知道数组的上限，可以调用<xref:System.Array.GetUpperBound%2A?displayProperty=nameWithType>方法以获取索引的最高值。</span><span class="sxs-lookup"><span data-stu-id="dfa60-195">When you don't know the upper bounds of the array, you can call the <xref:System.Array.GetUpperBound%2A?displayProperty=nameWithType> method to get the highest value of the index.</span></span> <span data-ttu-id="dfa60-196">虽然几乎是最低的索引值始终为 0，可以调用<xref:System.Array.GetLowerBound%2A?displayProperty=nameWithType>方法以获取索引的最低值。</span><span class="sxs-lookup"><span data-stu-id="dfa60-196">Although lowest index value is almost always 0, you can call the <xref:System.Array.GetLowerBound%2A?displayProperty=nameWithType> method to get the lowest value of the index.</span></span>   
  
 <span data-ttu-id="dfa60-197">下面的示例循环访问一个一维数组使用[ `For...Next` ](../../../../visual-basic/language-reference/statements/for-next-statement.md)语句。</span><span class="sxs-lookup"><span data-stu-id="dfa60-197">The following example iterates through a one-dimensional array by using the [`For...Next`](../../../../visual-basic/language-reference/statements/for-next-statement.md) statement.</span></span> 
  
 [!code-vb[iterate-one-dimensional-array](../../../../../samples/snippets/visualbasic/programming-guide/language-features/arrays/iterate1d.vb)]  
  
 <span data-ttu-id="dfa60-198">下面的示例循环访问一个多维数组使用[ `For...Next` ](../../../../visual-basic/language-reference/statements/for-next-statement.md)语句。</span><span class="sxs-lookup"><span data-stu-id="dfa60-198">The following example iterates through a multidimensional array by using a [`For...Next`](../../../../visual-basic/language-reference/statements/for-next-statement.md) statement.</span></span> <span data-ttu-id="dfa60-199"><xref:System.Array.GetUpperBound%2A> 方法具有用于指定维度的参数。</span><span class="sxs-lookup"><span data-stu-id="dfa60-199">The <xref:System.Array.GetUpperBound%2A> method has a parameter that specifies the dimension.</span></span> <span data-ttu-id="dfa60-200">`GetUpperBound(0)`返回的最高的第一个维度的索引和`GetUpperBound(1)`返回第二个维度的最高的索引。</span><span class="sxs-lookup"><span data-stu-id="dfa60-200">`GetUpperBound(0)` returns the highest index of the first dimension, and `GetUpperBound(1)` returns the highest index of the second dimension.</span></span>
  
 [!code-vb[iterate-two-dimensional-array](../../../../../samples/snippets/visualbasic/programming-guide/language-features/arrays/iterate2d.vb)]  
  
 <span data-ttu-id="dfa60-201">下面的示例使用[每个...下一条语句](../../../../visual-basic/language-reference/statements/for-each-next-statement.md)来循环访问一个一维数组和一个二维数组。</span><span class="sxs-lookup"><span data-stu-id="dfa60-201">The following example uses a [For Each...Next Statement](../../../../visual-basic/language-reference/statements/for-each-next-statement.md)to iterate through a one-dimensional array and a two-dimensional array.</span></span>  
  
 [!code-vb[iterate-for-each-next](../../../../../samples/snippets/visualbasic/programming-guide/language-features/arrays/iterate-for-each-next.vb)]  
  
## <a name="array-size"></a><span data-ttu-id="dfa60-202">数组大小</span><span class="sxs-lookup"><span data-stu-id="dfa60-202">Array Size</span></span>  

 <span data-ttu-id="dfa60-203">数组的大小是数组所有维度的长度的产物。</span><span class="sxs-lookup"><span data-stu-id="dfa60-203">The size of an array is the product of the lengths of all its dimensions.</span></span> <span data-ttu-id="dfa60-204">它表示数组中当前所包含的元素总数。</span><span class="sxs-lookup"><span data-stu-id="dfa60-204">It represents the total number of elements currently contained in the array.</span></span>  <span data-ttu-id="dfa60-205">例如，下面的示例声明每个维度中的四个元素的二维数组。</span><span class="sxs-lookup"><span data-stu-id="dfa60-205">For example, the following example declares a 2-dimensional array with four elements in each dimension.</span></span> <span data-ttu-id="dfa60-206">如示例输出所示，数组的大小为 16 (或 (3 + 1) \* (3 + 1)。</span><span class="sxs-lookup"><span data-stu-id="dfa60-206">As the output from the example shows, the array's size is 16 (or (3 + 1) \* (3 + 1).</span></span>

 [!code-vb[array-size](../../../../../samples/snippets/visualbasic/programming-guide/language-features/arrays/array-size.vb)]  

> [!NOTE] 
> <span data-ttu-id="dfa60-207">数组大小的这一讨论不适用于交错数组。</span><span class="sxs-lookup"><span data-stu-id="dfa60-207">This discussion of array size does not apply to jagged arrays.</span></span> <span data-ttu-id="dfa60-208">交错的数组并确定交错数组的大小的信息，请参阅[交错数组](#jagged-arrays)部分。</span><span class="sxs-lookup"><span data-stu-id="dfa60-208">For information on jagged arrays and determining the size of a jagged array, see the [Jagged arrays](#jagged-arrays) section.</span></span>
  
  <span data-ttu-id="dfa60-209">可以通过使用 <xref:System.Array.Length%2A?displayProperty=nameWithType> 属性查找数组大小。</span><span class="sxs-lookup"><span data-stu-id="dfa60-209">You can find the size of an array by using the <xref:System.Array.Length%2A?displayProperty=nameWithType> property.</span></span> <span data-ttu-id="dfa60-210">你可以通过使用查找每个维度的多维数组的长度<xref:System.Array.GetLength%2A?displayProperty=nameWithType>方法。</span><span class="sxs-lookup"><span data-stu-id="dfa60-210">You can find the length of each dimension of a multidimensional array by using the <xref:System.Array.GetLength%2A?displayProperty=nameWithType> method.</span></span>  
  
 <span data-ttu-id="dfa60-211">可以调整一个数组变量的大小分配给它的新数组对象或使用[`ReDim`语句](../../../../visual-basic/language-reference/statements/redim-statement.md)语句。</span><span class="sxs-lookup"><span data-stu-id="dfa60-211">You can resize an array variable by assigning a new array object to it or by using the [`ReDim` Statement](../../../../visual-basic/language-reference/statements/redim-statement.md) statement.</span></span> <span data-ttu-id="dfa60-212">下面的示例使用`ReDim`语句来切换到一个 51 元素的数组的一个 100 元素的数组。</span><span class="sxs-lookup"><span data-stu-id="dfa60-212">The following example uses the `ReDim` statement to change a 100-element array to a 51-element array.</span></span>

 [!code-vb[resize-an-array](../../../../../samples/snippets/visualbasic/programming-guide/language-features/arrays/array-size2.vb)]  
  
 <span data-ttu-id="dfa60-213">当处理数组大小时，需要记住几件事情。</span><span class="sxs-lookup"><span data-stu-id="dfa60-213">There are several things to keep in mind when dealing with the size of an array.</span></span>  
  
|||  
|---|---|  
|<span data-ttu-id="dfa60-214">维度长度</span><span class="sxs-lookup"><span data-stu-id="dfa60-214">Dimension Length</span></span>|<span data-ttu-id="dfa60-215">每个维度的索引是基于 0 的这意味着它范围从 0 到其上限。</span><span class="sxs-lookup"><span data-stu-id="dfa60-215">The index of each dimension is 0-based, which means it ranges from 0 to its upper bound.</span></span> <span data-ttu-id="dfa60-216">因此，给定维度的长度是一个大于该维度的声明的上限。</span><span class="sxs-lookup"><span data-stu-id="dfa60-216">Therefore, the length of a given dimension is one greater than the declared upper bound of that dimension.</span></span>|  
|<span data-ttu-id="dfa60-217">长度限制</span><span class="sxs-lookup"><span data-stu-id="dfa60-217">Length Limits</span></span>|<span data-ttu-id="dfa60-218">每个维度的数组的长度最多的最大值`Integer`数据类型，即<xref:System.Int32.MaxValue?displayProperty=nameWithType>或 (2 ^31)-1。</span><span class="sxs-lookup"><span data-stu-id="dfa60-218">The length of every dimension of an array is limited to the maximum value of the `Integer` data type, which is <xref:System.Int32.MaxValue?displayProperty=nameWithType> or (2 ^ 31) - 1.</span></span> <span data-ttu-id="dfa60-219">但是，数组的总大小还受到系统上可用的内存限制。</span><span class="sxs-lookup"><span data-stu-id="dfa60-219">However, the total size of an array is also limited by the memory available on your system.</span></span> <span data-ttu-id="dfa60-220">如果你尝试初始化数组，超过了可用内存量，则运行时会引发<xref:System.OutOfMemoryException>。</span><span class="sxs-lookup"><span data-stu-id="dfa60-220">If you attempt to initialize an array that exceeds the amount of available memory, the runtime throws an <xref:System.OutOfMemoryException>.</span></span>|  
|<span data-ttu-id="dfa60-221">大小和元素大小</span><span class="sxs-lookup"><span data-stu-id="dfa60-221">Size and Element Size</span></span>|<span data-ttu-id="dfa60-222">数组的大小独立于其元素的数据类型。</span><span class="sxs-lookup"><span data-stu-id="dfa60-222">An array's size is independent of the data type of its elements.</span></span> <span data-ttu-id="dfa60-223">大小始终表示元素，不占用的内存的字节数的总数目。</span><span class="sxs-lookup"><span data-stu-id="dfa60-223">The size always represents the total number of elements, not the number of bytes that they consume in memory.</span></span>|  
|<span data-ttu-id="dfa60-224">内存消耗</span><span class="sxs-lookup"><span data-stu-id="dfa60-224">Memory Consumption</span></span>|<span data-ttu-id="dfa60-225">做出关于数组如何存储在内存中的假设是不可靠的。</span><span class="sxs-lookup"><span data-stu-id="dfa60-225">It is not safe to make any assumptions regarding how an array is stored in memory.</span></span> <span data-ttu-id="dfa60-226">由于不同数据宽度的平台上的存储会有所变化，因此同一数组在 64 位系统上可以占用比在 32 位系统上更多的内存。</span><span class="sxs-lookup"><span data-stu-id="dfa60-226">Storage varies on platforms of different data widths, so the same array can consume more memory on a 64-bit system than on a 32-bit system.</span></span> <span data-ttu-id="dfa60-227">具体取决于数组初始化时的系统配置，公共语言运行时 (CLR) 可以尽可能地将存储分配到靠近包元素的地方，或者将它们全部在自然硬件边界上对齐。</span><span class="sxs-lookup"><span data-stu-id="dfa60-227">Depending on system configuration when you initialize an array, the common language runtime (CLR) can assign storage either to pack elements as close together as possible, or to align them all on natural hardware boundaries.</span></span> <span data-ttu-id="dfa60-228">此外，数组需要存储开销的控制信息，而且每添加一个维度，这种开销随之增加。</span><span class="sxs-lookup"><span data-stu-id="dfa60-228">Also, an array requires a storage overhead for its control information, and this overhead increases with each added dimension.</span></span>|  

## <a name="the-array-type"></a><span data-ttu-id="dfa60-229">数组类型</span><span class="sxs-lookup"><span data-stu-id="dfa60-229">The array type</span></span> 
 <span data-ttu-id="dfa60-230">每个数组具有不同于其元素的数据类型的数据类型。</span><span class="sxs-lookup"><span data-stu-id="dfa60-230">Every array has a data type, which differs from the data type of its elements.</span></span> <span data-ttu-id="dfa60-231">没有一种数据类型能用于所有数组。</span><span class="sxs-lookup"><span data-stu-id="dfa60-231">There is no single data type for all arrays.</span></span> <span data-ttu-id="dfa60-232">相反，数组的数据类型由数组的维度数量或 *“排名”*，以及数组中元素的数据类型确定。</span><span class="sxs-lookup"><span data-stu-id="dfa60-232">Instead, the data type of an array is determined by the number of dimensions, or *rank*, of the array, and the data type of the elements in the array.</span></span> <span data-ttu-id="dfa60-233">两个数组变量为相同的数据仅它们具有相同的排名且它们的元素具有相同的数据类型。</span><span class="sxs-lookup"><span data-stu-id="dfa60-233">Two array variables are of the same data type only when they have the same rank and their elements have the same data type.</span></span> <span data-ttu-id="dfa60-234">数组的维度的长度不会影响数组数据类型。</span><span class="sxs-lookup"><span data-stu-id="dfa60-234">The lengths of the dimensions of an array do not influence the array data type.</span></span>  
  
 <span data-ttu-id="dfa60-235">每个数组都继承自 <xref:System.Array?displayProperty=nameWithType> 类，并且你可以声明一个类型为 `Array` 的变量，但不能创建一个类型为 `Array` 的数组。</span><span class="sxs-lookup"><span data-stu-id="dfa60-235">Every array inherits from the <xref:System.Array?displayProperty=nameWithType> class, and you can declare a variable to be of type `Array`, but you cannot create an array of type `Array`.</span></span> <span data-ttu-id="dfa60-236">例如，尽管下面的代码声明`arr`变量的类型为`Array`和调用<xref:System.Array.CreateInstance%2A?displayProperty=nameWithType>方法可实例化的数组，数组的类型证明是对象 []。</span><span class="sxs-lookup"><span data-stu-id="dfa60-236">For example, although the following code declares the `arr` variable to be of type `Array` and calls the <xref:System.Array.CreateInstance%2A?displayProperty=nameWithType> method to instantiate the array, the array's type proves to be Object[].</span></span>

 [!code-vb[array-class](../../../../../samples/snippets/visualbasic/programming-guide/language-features/arrays/array-class.vb)] 

<span data-ttu-id="dfa60-237">此外，[ReDim 语句](../../../../visual-basic/language-reference/statements/redim-statement.md)无法对声明为类型 `Array` 的变量执行运算。</span><span class="sxs-lookup"><span data-stu-id="dfa60-237">Also, the [ReDim Statement](../../../../visual-basic/language-reference/statements/redim-statement.md) cannot operate on a variable declared as type `Array`.</span></span> <span data-ttu-id="dfa60-238">出于这些原因，以及为类型安全，则最好声明为特定类型的每个数组。</span><span class="sxs-lookup"><span data-stu-id="dfa60-238">For these reasons, and for type safety, it is advisable to declare every array as a specific type.</span></span>  
  
 <span data-ttu-id="dfa60-239">你可以通过几种方式了解到数组及其元素的数据类型。</span><span class="sxs-lookup"><span data-stu-id="dfa60-239">You can find out the data type of either an array or its elements in several ways.</span></span> 
  
-   <span data-ttu-id="dfa60-240">你可以调用<xref:System.Object.GetType%2A>方法变量以获取<xref:System.Type>表示变量的运行时类型的对象。</span><span class="sxs-lookup"><span data-stu-id="dfa60-240">You can call the <xref:System.Object.GetType%2A> method on the variable to get a <xref:System.Type> object that represents the run-time type of the variable.</span></span> <span data-ttu-id="dfa60-241"><xref:System.Type> 对象可在其属性和方法中保存大量信息。</span><span class="sxs-lookup"><span data-stu-id="dfa60-241">The <xref:System.Type> object holds extensive information in its properties and methods.</span></span>  
  
-   <span data-ttu-id="dfa60-242">你可以将该变量传递到<xref:Microsoft.VisualBasic.Information.TypeName%2A>函数可获取`String`运行时类型的名称。</span><span class="sxs-lookup"><span data-stu-id="dfa60-242">You can pass the variable to the <xref:Microsoft.VisualBasic.Information.TypeName%2A> function to get a `String` with the name of run-time type.</span></span>  
  
 <span data-ttu-id="dfa60-243">下面的示例调用同时`GetType`方法和`TypeName`函数来确定数组的类型。</span><span class="sxs-lookup"><span data-stu-id="dfa60-243">The following example calls the both the `GetType` method and the `TypeName` function to determine the type of an array.</span></span> <span data-ttu-id="dfa60-244">数组类型是`Byte(,)`。</span><span class="sxs-lookup"><span data-stu-id="dfa60-244">The array type is `Byte(,)`.</span></span> <span data-ttu-id="dfa60-245">请注意，<xref:System.Type.BaseType%2A?displayProperty=nameWithType>属性还指示的字节数组的基类型是<xref:System.Array>类。</span><span class="sxs-lookup"><span data-stu-id="dfa60-245">Note that the <xref:System.Type.BaseType%2A?displayProperty=nameWithType> property also indicates that the base type of the byte array is the <xref:System.Array> class.</span></span>  
  
 [!code-vb[array-type](../../../../../samples/snippets/visualbasic/programming-guide/language-features/arrays/array-type.vb)]  
  
##  <a name="arrays-as-return-values-and-parameters"></a><span data-ttu-id="dfa60-246">作为返回值和参数的数组</span><span class="sxs-lookup"><span data-stu-id="dfa60-246">Arrays as return values and parameters</span></span>  
 <span data-ttu-id="dfa60-247">若要通过 `Function` 过程返回数组，请将数组数据类型和维度数指定为 [Function 语句](../../../../visual-basic/language-reference/statements/function-statement.md)的返回类型。</span><span class="sxs-lookup"><span data-stu-id="dfa60-247">To return an array from a `Function` procedure, specify the array data type and the number of dimensions as the return type of the [Function Statement](../../../../visual-basic/language-reference/statements/function-statement.md).</span></span> <span data-ttu-id="dfa60-248">在函数内，声明一个具有相同数据类型和维度数的本地数组变量。</span><span class="sxs-lookup"><span data-stu-id="dfa60-248">Within the function, declare a local array variable with same data type and number of dimensions.</span></span> <span data-ttu-id="dfa60-249">在 [Return 语句](../../../../visual-basic/language-reference/statements/return-statement.md)中，添加不带括号的局部数组变量。</span><span class="sxs-lookup"><span data-stu-id="dfa60-249">In the [Return Statement](../../../../visual-basic/language-reference/statements/return-statement.md), include the local array variable without parentheses.</span></span>  
  
 <span data-ttu-id="dfa60-250">若要将作为参数的数组指定到 `Sub` 或 `Function` 步骤中，可将此参数定义为具有指定数据类型和维度数量的数组。</span><span class="sxs-lookup"><span data-stu-id="dfa60-250">To specify an array as a parameter to a `Sub` or `Function` procedure, define the parameter as an array with a specified data type and number of dimensions.</span></span> <span data-ttu-id="dfa60-251">在调用的过程，将传递一个数组变量具有相同的数据类型和维度数。</span><span class="sxs-lookup"><span data-stu-id="dfa60-251">In the call to the procedure, pass an array variable with the same data type and number of dimensions.</span></span>  
  
 <span data-ttu-id="dfa60-252">在下面的示例中，`GetNumbers`函数返回`Integer()`，类型的一维数组`Integer`。</span><span class="sxs-lookup"><span data-stu-id="dfa60-252">In the following example, the `GetNumbers` function returns an `Integer()`, a one-dimensional array of type `Integer`.</span></span> <span data-ttu-id="dfa60-253">`ShowNumbers` 过程接受 `Integer()` 参数。</span><span class="sxs-lookup"><span data-stu-id="dfa60-253">The `ShowNumbers` procedure accepts an `Integer()` argument.</span></span> 
  
 [!code-vb[return-value-and-params](../../../../../samples/snippets/visualbasic/programming-guide/language-features/arrays/return-values-and-params.vb)]  
  
 <span data-ttu-id="dfa60-254">在下面的示例中，`GetNumbersMultiDim`函数返回`Integer(,)`，类型的一个二维数组`Integer`。</span><span class="sxs-lookup"><span data-stu-id="dfa60-254">In the following example, the `GetNumbersMultiDim` function returns an `Integer(,)`, a two-dimensional array of type `Integer`.</span></span>  <span data-ttu-id="dfa60-255">`ShowNumbersMultiDim` 过程接受 `Integer(,)` 参数。</span><span class="sxs-lookup"><span data-stu-id="dfa60-255">The `ShowNumbersMultiDim` procedure accepts an `Integer(,)` argument.</span></span>  
  
 [!code-vb[multidimensional-return-value](../../../../../samples/snippets/visualbasic/programming-guide/language-features/arrays/return-values-and-params-2d.vb)]  
  
## <a name="jagged-arrays"></a><span data-ttu-id="dfa60-256">交错数组</span><span class="sxs-lookup"><span data-stu-id="dfa60-256">Jagged Arrays</span></span>  
 
<span data-ttu-id="dfa60-257">有时应用程序中的数据结构是二维而不是矩形。</span><span class="sxs-lookup"><span data-stu-id="dfa60-257">Sometimes the data structure in your application is two-dimensional but not rectangular.</span></span> <span data-ttu-id="dfa60-258">例如，可能使用一个数组来存储每一天的月的高温度有关的数据。</span><span class="sxs-lookup"><span data-stu-id="dfa60-258">For example, you might use an array to store data about the high temperature of each day of the month.</span></span> <span data-ttu-id="dfa60-259">数组的第一个维度表示的月份，但第二个维度则表示的天数，并且在一个月天数不统一。</span><span class="sxs-lookup"><span data-stu-id="dfa60-259">The first dimension of the array represents the month, but the second dimension represents the number of days, and the number of days in a month is not uniform.</span></span> <span data-ttu-id="dfa60-260">A*交错的数组*，这也称为*数组组成的数组*，专为这种情况。</span><span class="sxs-lookup"><span data-stu-id="dfa60-260">A *jagged array*, which is also called an *array of arrays*, is designed for such scenarios.</span></span> <span data-ttu-id="dfa60-261">交错的数组是一个数组，其元素也是数组。</span><span class="sxs-lookup"><span data-stu-id="dfa60-261">A jagged array is an array whose elements are also arrays.</span></span> <span data-ttu-id="dfa60-262">交错数组和交错数组中的每个元素都可以具有一个或多个维度。</span><span class="sxs-lookup"><span data-stu-id="dfa60-262">A jagged array and each element in a jagged array can have one or more dimensions.</span></span>  
  
 <span data-ttu-id="dfa60-263">下面的示例使用月份数组，其中每个元素是天数数组。</span><span class="sxs-lookup"><span data-stu-id="dfa60-263">The following example uses an array of months, each element of which is an array of days.</span></span> <span data-ttu-id="dfa60-264">该示例使用交错的数组，因为不同的月份具有不同数量的天数。</span><span class="sxs-lookup"><span data-stu-id="dfa60-264">The example uses a jagged array because different months have different numbers of days.</span></span>  <span data-ttu-id="dfa60-265">该示例演示如何创建交错的数组、 将值分配给它，并检索和显示其值。</span><span class="sxs-lookup"><span data-stu-id="dfa60-265">The example shows how to create a jagged array, assign values to it, and retrieve and display its values.</span></span>
  
 [!code-vb[jagged-arrays](../../../../../samples/snippets/visualbasic/programming-guide/language-features/arrays/jagged.vb)]  

<span data-ttu-id="dfa60-266">前面的示例将值分配给元素的元素按交错数组，通过使用`For...Next`循环。</span><span class="sxs-lookup"><span data-stu-id="dfa60-266">The previous example assigns values to the jagged array on an element-by-element basis by using a `For...Next` loop.</span></span> <span data-ttu-id="dfa60-267">通过使用嵌套的数组文本，也可以将值分配给交错数组的元素。</span><span class="sxs-lookup"><span data-stu-id="dfa60-267">You can also assign values to the elements of a jagged array by using nested array literals.</span></span> <span data-ttu-id="dfa60-268">但是，尝试使用嵌套数组文本 (例如， ```Dim valuesjagged = {{1, 2}, {2, 3, 4}}```) 将生成编译器错误[BC30568](../../../,,/../misc/bc30568.md)。</span><span class="sxs-lookup"><span data-stu-id="dfa60-268">However, the attempt to use nested array literals (for example, ```Dim valuesjagged = {{1, 2}, {2, 3, 4}}```) generates compiler error [BC30568](../../../,,/../misc/bc30568.md).</span></span> <span data-ttu-id="dfa60-269">若要更正错误，请用括号括起来将内部数组文本。</span><span class="sxs-lookup"><span data-stu-id="dfa60-269">To correct the error, enclose the inner array literals in parentheses.</span></span> <span data-ttu-id="dfa60-270">圆括号强制数组文字表达式进行计算，并将生成的值用于外部数组文本，如以下示例所示。</span><span class="sxs-lookup"><span data-stu-id="dfa60-270">The parentheses force the array literal expression to be evaluated, and the resulting values are used with the outer array literal, as the following example shows.</span></span>  
  
 [!code-vb[jagged-array-initialization](../../../../../samples/snippets/visualbasic/programming-guide/language-features/arrays/jagged-assign.vb)] 

<span data-ttu-id="dfa60-271">交错的数组是其元素包含数组的一维数组。</span><span class="sxs-lookup"><span data-stu-id="dfa60-271">A jagged array is a one-dimensional array whose elements contain arrays.</span></span> <span data-ttu-id="dfa60-272">因此，<xref:System.Array.Length%2A?displayProperty=nameWithType>属性和`Array.GetLength(0)`方法返回的一维数组中的元素的数目和`Array.GetLength(1)`引发<xref:System.IndexOutOfRangeException>因为交错的数组不是多维。</span><span class="sxs-lookup"><span data-stu-id="dfa60-272">Therefore, the <xref:System.Array.Length%2A?displayProperty=nameWithType> property and the `Array.GetLength(0)` method return the number of elements in the one-dimensional array, and `Array.GetLength(1)` throws an <xref:System.IndexOutOfRangeException> because a jagged array is not multidimensional.</span></span> <span data-ttu-id="dfa60-273">检索的值的每个子数组确定每个子数组中的元素数<xref:System.Array.Length%2A?displayProperty=nameWithType>属性。</span><span class="sxs-lookup"><span data-stu-id="dfa60-273">You determine the number of elements in each subarray by retrieving the value of each subarray's <xref:System.Array.Length%2A?displayProperty=nameWithType> property.</span></span> <span data-ttu-id="dfa60-274">下面的示例演示如何确定交错数组中的元素数。</span><span class="sxs-lookup"><span data-stu-id="dfa60-274">The following example illustrates how to determine the number of elements in a jagged array.</span></span>

[!code-vb[jagged-array-size](../../../../../samples/snippets/visualbasic/programming-guide/language-features/arrays/jagged-length.vb)] 

## <a name="zero-length-arrays"></a><span data-ttu-id="dfa60-275">零长度数组</span><span class="sxs-lookup"><span data-stu-id="dfa60-275">Zero-length arrays</span></span>  
<span data-ttu-id="dfa60-276">Visual Basic 区分未初始化的数组 (其值是一个数组`Nothing`) 和一个*零长度数组*或空数组 （不包含任何元素的数组。）未初始化的数组是指不维度化或已分配给它的任何值。</span><span class="sxs-lookup"><span data-stu-id="dfa60-276">Visual Basic differentiates between a uninitialized array (an array whose value is `Nothing`) and a *zero-length array* or empty array (an array that has no elements.) An uninitialized array is one that has not been dimensioned or had any values assigned to it.</span></span> <span data-ttu-id="dfa60-277">例如: </span><span class="sxs-lookup"><span data-stu-id="dfa60-277">For example:</span></span>

```vb
Dim arr() As String
```
<span data-ttu-id="dfa60-278">一个零长度数组声明一个尺寸为-1。</span><span class="sxs-lookup"><span data-stu-id="dfa60-278">A zero-length array is declared with a dimension of -1.</span></span> <span data-ttu-id="dfa60-279">例如: </span><span class="sxs-lookup"><span data-stu-id="dfa60-279">For example:</span></span>

```vb
Dim arrZ(-1) As String
```
<span data-ttu-id="dfa60-280">在下列情况下，你可能需要创建一个零长度数组：</span><span class="sxs-lookup"><span data-stu-id="dfa60-280">You might need to create a zero-length array under the following circumstances:</span></span>  
  
-   <span data-ttu-id="dfa60-281">不会面临的风险的情况下<xref:System.NullReferenceException>异常，你的代码必须访问的成员<xref:System.Array>类，如<xref:System.Array.Length%2A>或<xref:System.Array.Rank%2A>，或如调用 Visual Basic 函数<xref:Microsoft.VisualBasic.Information.UBound%2A>。</span><span class="sxs-lookup"><span data-stu-id="dfa60-281">Without risking a <xref:System.NullReferenceException> exception, your code must access members of the <xref:System.Array> class, such as <xref:System.Array.Length%2A> or <xref:System.Array.Rank%2A>, or call a Visual Basic function such as <xref:Microsoft.VisualBasic.Information.UBound%2A>.</span></span>  
  
-   <span data-ttu-id="dfa60-282">你想要保留你的代码，而不必检查简单`Nothing`作为一种特殊情况。</span><span class="sxs-lookup"><span data-stu-id="dfa60-282">You want to keep the your code simple by not having to check for `Nothing` as a special case.</span></span>  
  
-   <span data-ttu-id="dfa60-283">你的代码与应用程序编程接口 (API) 交互，该接口要求你将一个零长度数组传递到一个或多个过程，或将一个零长度数组返回到一个或多个过程。</span><span class="sxs-lookup"><span data-stu-id="dfa60-283">Your code interacts with an application programming interface (API) that either requires you to pass a zero-length array to one or more procedures or returns a zero-length array from one or more procedures.</span></span>

## <a name="splitting-an-array"></a><span data-ttu-id="dfa60-284">拆分数组</span><span class="sxs-lookup"><span data-stu-id="dfa60-284">Splitting an array</span></span>

<span data-ttu-id="dfa60-285">在某些情况下，你可能需要将单个数组拆分为多个阵列。</span><span class="sxs-lookup"><span data-stu-id="dfa60-285">In some cases, you may need to split a single array into multiple arrays.</span></span> <span data-ttu-id="dfa60-286">这涉及到标识点或从该处的数组是进行拆分，数据点，然后 spitting 到两个或多个单独的数组的数组。</span><span class="sxs-lookup"><span data-stu-id="dfa60-286">This involves identifying the point or points at which the array is to be split, and then spitting the array into two or more separate arrays.</span></span> 

> [!NOTE] 
> <span data-ttu-id="dfa60-287">本部分不讨论将单个字符串拆分为基于某些分隔符的字符串数组。</span><span class="sxs-lookup"><span data-stu-id="dfa60-287">This section does not discuss splitting a single string into a string array based on some delimiter.</span></span> <span data-ttu-id="dfa60-288">有关将字符串拆分的信息，请参阅<xref:System.String.Split%2A?displayProperty=nameWithType>方法。</span><span class="sxs-lookup"><span data-stu-id="dfa60-288">For information on splitting a string, see the <xref:System.String.Split%2A?displayProperty=nameWithType> method.</span></span>

<span data-ttu-id="dfa60-289">将拆分为数组的最常见条件是：</span><span class="sxs-lookup"><span data-stu-id="dfa60-289">The most common criteria for splitting an array are:</span></span>

- <span data-ttu-id="dfa60-290">数组中的元素数。</span><span class="sxs-lookup"><span data-stu-id="dfa60-290">The number of elements in the array.</span></span> <span data-ttu-id="dfa60-291">例如，你可能想要拆分为多个相等部分大约的多个指定数量的元素数组。</span><span class="sxs-lookup"><span data-stu-id="dfa60-291">For example, you might want to split an array of more than a specified number of elements into a number of approximately equal parts.</span></span> <span data-ttu-id="dfa60-292">为此，你可以使用通过以下任一方法返回的值<xref:System.Array.Length%2A?displayProperty=nameWithType>或<xref:System.Array.GetLength%2A?displayProperty=nameWithType>方法。</span><span class="sxs-lookup"><span data-stu-id="dfa60-292">For this purpose, you can use the value returned by either the <xref:System.Array.Length%2A?displayProperty=nameWithType> or <xref:System.Array.GetLength%2A?displayProperty=nameWithType> method.</span></span>

- <span data-ttu-id="dfa60-293">元素，它可作为分隔符，该值指示应在何处拆分数组值。</span><span class="sxs-lookup"><span data-stu-id="dfa60-293">The value of an element, which serves as a delimiter that indicates where the array should be split.</span></span> <span data-ttu-id="dfa60-294">可以在多用户环境中搜索特定值，通过调用<xref:System.Array.FindIndex%2A?displayProperty=nameWithType>和<xref:System.Array.FindLastIndex%2A?displayProperty=nameWithType>方法。</span><span class="sxs-lookup"><span data-stu-id="dfa60-294">You can search for a specific value by calling the <xref:System.Array.FindIndex%2A?displayProperty=nameWithType> and <xref:System.Array.FindLastIndex%2A?displayProperty=nameWithType> methods.</span></span>
 
<span data-ttu-id="dfa60-295">一旦确定或多个应从该处拆分数组的索引，然后可以通过调用创建单个数组<xref:System.Array.Copy%2A?displayProperty=nameWithType>方法。</span><span class="sxs-lookup"><span data-stu-id="dfa60-295">Once you've determined the index or indexes at which the array should be split, you can then create the individual arrays by calling the <xref:System.Array.Copy%2A?displayProperty=nameWithType> method.</span></span> 

<span data-ttu-id="dfa60-296">下面的示例将拆分为大小大约相等的两个数组的数组。</span><span class="sxs-lookup"><span data-stu-id="dfa60-296">The following example splits an array into two arrays of approximately equal size.</span></span> <span data-ttu-id="dfa60-297">（如果数组元素的总数目为奇数，第一个数组具有多个元素的第二个。）</span><span class="sxs-lookup"><span data-stu-id="dfa60-297">(If the total number of array elements is odd, the first array has one more element than the second.)</span></span> 

[!code-vb[splitting-an-array-by-length](../../../../../samples/snippets/visualbasic/programming-guide/language-features/arrays/split1.vb)] 

<span data-ttu-id="dfa60-298">下面的示例将字符串数组拆分为两个数组根据其值是"zzz"，用作数组分隔符的元素存在。</span><span class="sxs-lookup"><span data-stu-id="dfa60-298">The following example splits a string array into two arrays based on the presence of an element whose value is "zzz", which serves as the array delimiter.</span></span> <span data-ttu-id="dfa60-299">新的阵列不包括包含分隔符的元素。</span><span class="sxs-lookup"><span data-stu-id="dfa60-299">The new arrays do not include the element that contains the delimiter.</span></span>

[!code-vb[splitting-an-array-by-delimiter](../../../../../samples/snippets/visualbasic/programming-guide/language-features/arrays/split2.vb)] 

## <a name="joining-arrays"></a><span data-ttu-id="dfa60-300">联接数组</span><span class="sxs-lookup"><span data-stu-id="dfa60-300">Joining arrays</span></span>

<span data-ttu-id="dfa60-301">你还可以将大量的数组组合到单个更大的阵列。</span><span class="sxs-lookup"><span data-stu-id="dfa60-301">You can also combine a number of arrays into a single larger array.</span></span> <span data-ttu-id="dfa60-302">若要执行此操作，也使用<xref:System.Array.Copy%2A?displayProperty=nameWithType>方法。</span><span class="sxs-lookup"><span data-stu-id="dfa60-302">To do this, you also use the <xref:System.Array.Copy%2A?displayProperty=nameWithType> method.</span></span> 

> [!NOTE] 
> <span data-ttu-id="dfa60-303">本部分不讨论连接成单个字符串的字符串数组。</span><span class="sxs-lookup"><span data-stu-id="dfa60-303">This section does not discuss joining a string array into a single string.</span></span> <span data-ttu-id="dfa60-304">有关联接的字符串数组的信息，请参阅<xref:System.String.Join%2A?displayProperty=nameWithType>方法。</span><span class="sxs-lookup"><span data-stu-id="dfa60-304">For information on joining a string array, see the <xref:System.String.Join%2A?displayProperty=nameWithType> method.</span></span>

<span data-ttu-id="dfa60-305">在将每个数组的元素复制到新数组之前, 你首先必须确保，这样就足够大到 accompodate 新数组初始化数组。</span><span class="sxs-lookup"><span data-stu-id="dfa60-305">Before copying the elements of each array into the new array, you must first ensure that you have initialized the array so that it is large enough to accompodate the new array.</span></span> <span data-ttu-id="dfa60-306">可以通过两种方法执行此操作：</span><span class="sxs-lookup"><span data-stu-id="dfa60-306">You can do this in one of two ways:</span></span>

- <span data-ttu-id="dfa60-307">使用[ `ReDim Preserve` ](../../../../visual-basic/language-reference/statements/redim-statement.md)动态展开数组，然后将新元素添加到它的语句。</span><span class="sxs-lookup"><span data-stu-id="dfa60-307">Use the [`ReDim Preserve`](../../../../visual-basic/language-reference/statements/redim-statement.md) statement to dynamically expand the array before adding new elements to it.</span></span> <span data-ttu-id="dfa60-308">这是最简单的技术，但它可能导致性能降低或过多的内存消耗复制大型数组时。</span><span class="sxs-lookup"><span data-stu-id="dfa60-308">This is the easiest technique, but it can result in performance degradation and excessive memory consumption when you are copying large arrays.</span></span>
- <span data-ttu-id="dfa60-309">计算所需的新的大型数组的元素总数，然后向其添加每个源数组的元素。</span><span class="sxs-lookup"><span data-stu-id="dfa60-309">Calculate the total number of elements needed for the new large array, then add the elements of each source array to it.</span></span>

<span data-ttu-id="dfa60-310">下面的示例使用第二种方法添加到单个数组十个元素的四个阵列。</span><span class="sxs-lookup"><span data-stu-id="dfa60-310">The following example uses the second approach to add four arrays with ten elements each to a single array.</span></span>  

[!code-vb[joining-an-array](../../../../../samples/snippets/visualbasic/programming-guide/language-features/arrays/join.vb)] 

<span data-ttu-id="dfa60-311">因为在这种情况下源数组也是所有小型，我们还可以动态地可以展开数组，我们将每个新数组的元素添加到它。</span><span class="sxs-lookup"><span data-stu-id="dfa60-311">Since in this case the source arrays are all small, we can also dynamically expand the array as we add the elements of each new array to it.</span></span> <span data-ttu-id="dfa60-312">以下示例执行该操作。</span><span class="sxs-lookup"><span data-stu-id="dfa60-312">The following example does that.</span></span>

[!code-vb[joining-an-array-dynamically](../../../../../samples/snippets/visualbasic/programming-guide/language-features/arrays/join2.vb)] 

##  <a name="collections-as-an-alternative-to-arrays"></a><span data-ttu-id="dfa60-313">作为数组的替代方法的集合</span><span class="sxs-lookup"><span data-stu-id="dfa60-313">Collections as an alternative to arrays</span></span>  
 <span data-ttu-id="dfa60-314">数组最适用于创建和使用固定数量的强类型化对象。</span><span class="sxs-lookup"><span data-stu-id="dfa60-314">Arrays are most useful for creating and working with a fixed number of strongly typed objects.</span></span> <span data-ttu-id="dfa60-315">集合提供更灵活的方式来使用对象组。</span><span class="sxs-lookup"><span data-stu-id="dfa60-315">Collections provide a more flexible way to work with groups of objects.</span></span> <span data-ttu-id="dfa60-316">与数组不同，这要求你显式更改数组的大小[`ReDim`语句](../../../../visual-basic/language-reference/statements/redim-statement.md)，集合增加和减少动态随着需求的应用程序更改。</span><span class="sxs-lookup"><span data-stu-id="dfa60-316">Unlike arrays, which require that you explicitly change the size of an array with the [`ReDim` Statement](../../../../visual-basic/language-reference/statements/redim-statement.md), collections grow and shrink dynamically as the needs of an application change.</span></span>  
  
 <span data-ttu-id="dfa60-317">当你使用`ReDim`来重新设置其维数的数组，Visual Basic 创建一个新数组和释放前一个。</span><span class="sxs-lookup"><span data-stu-id="dfa60-317">When you use `ReDim` to redimension an array, Visual Basic creates a new array and releases the previous one.</span></span> <span data-ttu-id="dfa60-318">这需要执行时间。</span><span class="sxs-lookup"><span data-stu-id="dfa60-318">This takes execution time.</span></span> <span data-ttu-id="dfa60-319">因此，如果你正在使用频繁变化，或者你的项目数无法预测你需要的项的最大数目，你通常将使用集合获得更好的性能。</span><span class="sxs-lookup"><span data-stu-id="dfa60-319">Therefore, if the number of items you are working with changes frequently, or you cannot predict the maximum number of items you need, you'll usually obtain better performance by using a collection.</span></span>  
  
 <span data-ttu-id="dfa60-320">对于某些集合，你可以为放入集合中的任何对象分配一个密钥，这样你便可以使用该密钥快速检索此对象。</span><span class="sxs-lookup"><span data-stu-id="dfa60-320">For some collections, you can assign a key to any object that you put into the collection so that you can quickly retrieve the object by using the key.</span></span>  
  
 <span data-ttu-id="dfa60-321">如果你的集合中只包含一种数据类型的元素，你可以使用 <xref:System.Collections.Generic?displayProperty=nameWithType> 命名空间中的一个类。</span><span class="sxs-lookup"><span data-stu-id="dfa60-321">If your collection contains elements of only one data type, you can use one of the classes in the <xref:System.Collections.Generic?displayProperty=nameWithType> namespace.</span></span> <span data-ttu-id="dfa60-322">泛型集合强制类型安全，因此无法向其添加任何其他数据类型。</span><span class="sxs-lookup"><span data-stu-id="dfa60-322">A generic collection enforces type safety so that no other data type can be added to it.</span></span>  
  
 <span data-ttu-id="dfa60-323">有关集合的详细信息，请参阅[集合](../../concepts/collections.md)。</span><span class="sxs-lookup"><span data-stu-id="dfa60-323">For more information about collections, see [Collections](../../concepts/collections.md).</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="dfa60-324">相关主题</span><span class="sxs-lookup"><span data-stu-id="dfa60-324">Related Topics</span></span>  
  
|<span data-ttu-id="dfa60-325">术语</span><span class="sxs-lookup"><span data-stu-id="dfa60-325">Term</span></span>|<span data-ttu-id="dfa60-326">定义</span><span class="sxs-lookup"><span data-stu-id="dfa60-326">Definition</span></span>|  
|----------|----------------|  
|[<span data-ttu-id="dfa60-327">Array Dimensions in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="dfa60-327">Array Dimensions in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/arrays/array-dimensions.md)|<span data-ttu-id="dfa60-328">在数组中解释级别和维度。</span><span class="sxs-lookup"><span data-stu-id="dfa60-328">Explains rank and dimensions in arrays.</span></span>|  
|[<span data-ttu-id="dfa60-329">如何：在 Visual Basic 中初始化数组变量</span><span class="sxs-lookup"><span data-stu-id="dfa60-329">How to: Initialize an Array Variable in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/arrays/how-to-initialize-an-array-variable.md)|<span data-ttu-id="dfa60-330">说明如何用初始值填充数组。</span><span class="sxs-lookup"><span data-stu-id="dfa60-330">Describes how to populate arrays with initial values.</span></span>|  
|[<span data-ttu-id="dfa60-331">如何：在 Visual Basic 中对数组进行排序</span><span class="sxs-lookup"><span data-stu-id="dfa60-331">How to: Sort An Array in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/arrays/how-to-sort-an-array.md)|<span data-ttu-id="dfa60-332">显示如何按字母先后顺序对数组元素进行排序。</span><span class="sxs-lookup"><span data-stu-id="dfa60-332">Shows how to sort the elements of an array alphabetically.</span></span>|  
|[<span data-ttu-id="dfa60-333">如何：将一个数组赋给另一个数组</span><span class="sxs-lookup"><span data-stu-id="dfa60-333">How to: Assign One Array to Another Array</span></span>](../../../../visual-basic/programming-guide/language-features/arrays/how-to-assign-one-array-to-another-array.md)|<span data-ttu-id="dfa60-334">说明将数组分配到另一个数组变量的规则和步骤。</span><span class="sxs-lookup"><span data-stu-id="dfa60-334">Describes the rules and steps for assigning an array to another array variable.</span></span>|  
|[<span data-ttu-id="dfa60-335">数组疑难解答</span><span class="sxs-lookup"><span data-stu-id="dfa60-335">Troubleshooting Arrays</span></span>](../../../../visual-basic/programming-guide/language-features/arrays/troubleshooting-arrays.md)|<span data-ttu-id="dfa60-336">讨论在使用数组时出现的一些常见问题。</span><span class="sxs-lookup"><span data-stu-id="dfa60-336">Discusses some common problems that arise when working with arrays.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="dfa60-337">另请参阅</span><span class="sxs-lookup"><span data-stu-id="dfa60-337">See Also</span></span>  
 <xref:System.Array?displayProperty=nameWithType>  
 [<span data-ttu-id="dfa60-338">Dim 语句</span><span class="sxs-lookup"><span data-stu-id="dfa60-338">Dim Statement</span></span>](../../../../visual-basic/language-reference/statements/dim-statement.md)  
 [<span data-ttu-id="dfa60-339">ReDim 语句</span><span class="sxs-lookup"><span data-stu-id="dfa60-339">ReDim Statement</span></span>](../../../../visual-basic/language-reference/statements/redim-statement.md)
