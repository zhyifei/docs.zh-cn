---
title: Visual Basic 中的数组
ms.date: 12/06/2017
f1_keywords:
- vb.Array
helpviewer_keywords:
- arrays [Visual Basic]
- Visual Basic, arrays
ms.assetid: dbf29737-b589-4443-bee6-a27588d9c67e
ms.openlocfilehash: bb6cb846a305e618a4a0cbf1d4b3d2510df14cf7
ms.sourcegitcommit: c93fd5139f9efcf6db514e3474301738a6d1d649
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2018
ms.locfileid: "50183823"
---
# <a name="arrays-in-visual-basic"></a><span data-ttu-id="48ff1-102">Visual Basic 中的数组</span><span class="sxs-lookup"><span data-stu-id="48ff1-102">Arrays in Visual Basic</span></span>
<span data-ttu-id="48ff1-103">数组是一组值，术语上称之为*元素*，逻辑上彼此相关的。</span><span class="sxs-lookup"><span data-stu-id="48ff1-103">An array is a set of values, which are termed *elements*, that are logically related to each other.</span></span> <span data-ttu-id="48ff1-104">例如，数组可能包含的语法学校; 中的每个年级的学生数量数组的每个元素是单个年级的学生数量。</span><span class="sxs-lookup"><span data-stu-id="48ff1-104">For example, an array may consist of the number of students in each grade in a grammar school; each element of the array is the number of students in a single grade.</span></span> <span data-ttu-id="48ff1-105">同样，数组可能包含的一个类; 的学生的成绩数组的每个元素是一个单一的等级。</span><span class="sxs-lookup"><span data-stu-id="48ff1-105">Similarly, an array may consist of a student's grades for a class; each element of the array is a single grade.</span></span>    

<span data-ttu-id="48ff1-106">它是可能的各个变量来存储每个数据项。</span><span class="sxs-lookup"><span data-stu-id="48ff1-106">It is possible individual variables to store each of our data items.</span></span> <span data-ttu-id="48ff1-107">例如，如果我们的应用程序分析学生成绩，我们可以使用一个单独的变量的每个学生的等级，如`englishGrade1`， `englishGrade2`，等等。此方法具有三个主要的限制：</span><span class="sxs-lookup"><span data-stu-id="48ff1-107">For example, if our application analyzes student grades, we can use a separate variable for each student's grade, such as `englishGrade1`, `englishGrade2`, etc. This approach has three major limitations:</span></span>
- <span data-ttu-id="48ff1-108">我们必须知道在设计时我们需要处理完全数目的成绩。</span><span class="sxs-lookup"><span data-stu-id="48ff1-108">We have to know at design time exactly how many grades we have to handle.</span></span>
- <span data-ttu-id="48ff1-109">快速处理大量的成绩变得难以处理。</span><span class="sxs-lookup"><span data-stu-id="48ff1-109">Handling large numbers of grades quickly becomes unwieldy.</span></span> <span data-ttu-id="48ff1-110">反过来，这使得应用程序更有可能有严重的 bug。</span><span class="sxs-lookup"><span data-stu-id="48ff1-110">This in turn makes an application much more likely to have serious bugs.</span></span>
- <span data-ttu-id="48ff1-111">很难维护。</span><span class="sxs-lookup"><span data-stu-id="48ff1-111">It is difficult to maintain.</span></span> <span data-ttu-id="48ff1-112">我们添加的每个新级别要求应用程序进行修改、 重新编译和重新部署。</span><span class="sxs-lookup"><span data-stu-id="48ff1-112">Each new grade that we add requires that the application be modified, recompiled, and redeployed.</span></span>  
 
 <span data-ttu-id="48ff1-113">通过使用一个数组，可以通过相同的名称，请参阅这些相关的值并使用一个数字，称为*索引*或*下标*用于标识各个元素根据其数组中的位置。</span><span class="sxs-lookup"><span data-stu-id="48ff1-113">By using an array, you can refer to these related values by the same name, and use a number that’s called an *index* or *subscript* to identify an individual element based on its position in the array.</span></span> <span data-ttu-id="48ff1-114">数组范围从 0 到数组中元素的总数减 1 所得的索引。</span><span class="sxs-lookup"><span data-stu-id="48ff1-114">The indexes of an array range from 0 to one less than the total number of elements in the array.</span></span> <span data-ttu-id="48ff1-115">当您使用 Visual Basic 语法来定义数组的大小时，指定其最高的索引，不在数组中元素的总数。</span><span class="sxs-lookup"><span data-stu-id="48ff1-115">When you use Visual Basic syntax to define the size of an array, you specify its highest index, not the total number of elements in the array.</span></span> <span data-ttu-id="48ff1-116">您可以使用数组作为一个单元，并循环访问其元素的功能使您无需了解它包含在设计时完全多少个元素。</span><span class="sxs-lookup"><span data-stu-id="48ff1-116">You can work with the array as a unit, and the ability to iterate its elements frees you from needing to know exactly how many elements it contains at design time.</span></span>
  
 <span data-ttu-id="48ff1-117">在进行说明之前，请看几个简单的示例：</span><span class="sxs-lookup"><span data-stu-id="48ff1-117">Some quick examples before explanation:</span></span>  
  
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
  
 ## <a name="in-this-article"></a><span data-ttu-id="48ff1-118">本文内容</span><span class="sxs-lookup"><span data-stu-id="48ff1-118">In this article</span></span>
  
- [<span data-ttu-id="48ff1-119">简单数组中的数组元素</span><span class="sxs-lookup"><span data-stu-id="48ff1-119">Array elements in a simple array</span></span>](#array-elements-in-a-simple-array)  
  
- [<span data-ttu-id="48ff1-120">创建数组</span><span class="sxs-lookup"><span data-stu-id="48ff1-120">Creating an array</span></span>](#creating-an-array)  
  
- [<span data-ttu-id="48ff1-121">将值存储在数组</span><span class="sxs-lookup"><span data-stu-id="48ff1-121">Storing values in an array</span></span>](#storing-values-in-an-array)  
  
- [<span data-ttu-id="48ff1-122">使用数组文本填充数组</span><span class="sxs-lookup"><span data-stu-id="48ff1-122">Populating an array with array literals</span></span>](#populating-an-array-with-array-literals)  
  
- [<span data-ttu-id="48ff1-123">循环访问数组</span><span class="sxs-lookup"><span data-stu-id="48ff1-123">Iterating through an array</span></span>](#iterating-through-an-array)  
  
- [<span data-ttu-id="48ff1-124">数组大小</span><span class="sxs-lookup"><span data-stu-id="48ff1-124">Array size</span></span>](#BKMK_ArraySize)  

- [<span data-ttu-id="48ff1-125">数组类型</span><span class="sxs-lookup"><span data-stu-id="48ff1-125">The array type</span></span>](#the-array-type)  
  
- [<span data-ttu-id="48ff1-126">作为返回值和参数的数组</span><span class="sxs-lookup"><span data-stu-id="48ff1-126">Arrays as return values and parameters</span></span>](#arrays-as-return-values-and-parameters)  
- [<span data-ttu-id="48ff1-127">交错的数组</span><span class="sxs-lookup"><span data-stu-id="48ff1-127">Jagged arrays</span></span>](#jagged-arrays)  
  
- [<span data-ttu-id="48ff1-128">零长度数组</span><span class="sxs-lookup"><span data-stu-id="48ff1-128">Zero-length arrays</span></span>](#zero-length-arrays)  

- [<span data-ttu-id="48ff1-129">拆分数组</span><span class="sxs-lookup"><span data-stu-id="48ff1-129">Splitting an array</span></span>](#splitting-an-array)
  
- [<span data-ttu-id="48ff1-130">作为数组的替代方法的集合</span><span class="sxs-lookup"><span data-stu-id="48ff1-130">Collections as an alternative to arrays</span></span>](#collections-as-an-alternative-to-arrays)  
  
##  <a name="array-elements-in-a-simple-array"></a><span data-ttu-id="48ff1-131">简单数组中的数组元素</span><span class="sxs-lookup"><span data-stu-id="48ff1-131">Array elements in a simple array</span></span>  

<span data-ttu-id="48ff1-132">让我们创建一个名为数组`students`存储语法学校中每个年级的学生数量。</span><span class="sxs-lookup"><span data-stu-id="48ff1-132">Let's create an array named `students` to store the number of students in each grade in a grammar school.</span></span> <span data-ttu-id="48ff1-133">这些元素的索引范围为 0 到 6。</span><span class="sxs-lookup"><span data-stu-id="48ff1-133">The indexes of the elements range from 0 through 6.</span></span> <span data-ttu-id="48ff1-134">使用此数组是比声明七个变量更简单。</span><span class="sxs-lookup"><span data-stu-id="48ff1-134">Using this array is simpler than declaring seven variables.</span></span>

<span data-ttu-id="48ff1-135">下图显示`students`数组。</span><span class="sxs-lookup"><span data-stu-id="48ff1-135">The following illustration shows the `students` array.</span></span> <span data-ttu-id="48ff1-136">对于数组的每个元素：</span><span class="sxs-lookup"><span data-stu-id="48ff1-136">For each element of the array:</span></span>  
  
-   <span data-ttu-id="48ff1-137">元素索引表示年级（索引 0 表示幼儿园）。</span><span class="sxs-lookup"><span data-stu-id="48ff1-137">The index of the element represents the grade (index 0 represents kindergarten).</span></span>
  
-   <span data-ttu-id="48ff1-138">元素中包含的值表示每个年级的学生数量。</span><span class="sxs-lookup"><span data-stu-id="48ff1-138">The value that’s contained in the element represents the number of students in that grade.</span></span>
  
 <span data-ttu-id="48ff1-139">![显示学生人数的数组图片](../../../../visual-basic/programming-guide/language-features/arrays/media/arrayexampleschool.gif " ArrayExampleSchool ")</span><span class="sxs-lookup"><span data-stu-id="48ff1-139">![Picture of array showing numbers of students](../../../../visual-basic/programming-guide/language-features/arrays/media/arrayexampleschool.gif "ArrayExampleSchool")</span></span>  
<span data-ttu-id="48ff1-140">“学生”数组中的元素</span><span class="sxs-lookup"><span data-stu-id="48ff1-140">Elements of the "students" array</span></span>  
 
<span data-ttu-id="48ff1-141">下面的示例包含用于创建和使用数组的 Visual Basic 代码：</span><span class="sxs-lookup"><span data-stu-id="48ff1-141">The following example contains the Visual Basic code that creates and uses the array:</span></span>

 [!code-vb[simple-array](../../../../../samples/snippets/visualbasic/programming-guide/language-features/arrays/simple-array.vb)]  

<span data-ttu-id="48ff1-142">该示例执行三项操作：</span><span class="sxs-lookup"><span data-stu-id="48ff1-142">The example does three things:</span></span>

- <span data-ttu-id="48ff1-143">它声明了`students`具有七个元素的数组。</span><span class="sxs-lookup"><span data-stu-id="48ff1-143">It declares a `students` array with seven elements.</span></span> <span data-ttu-id="48ff1-144">数`6`声明数组中表示数组中的最后一个索引; 它是一个小于数组中的元素数。</span><span class="sxs-lookup"><span data-stu-id="48ff1-144">The number `6` in the array declaration indicates the last index in the array; it is one less than the number of elements in the array.</span></span>
- <span data-ttu-id="48ff1-145">它将值分配给数组中的每个元素。</span><span class="sxs-lookup"><span data-stu-id="48ff1-145">It assigns values to each element in the array.</span></span> <span data-ttu-id="48ff1-146">通过使用数组名称并在括号中包含单个元素的索引访问数组元素。</span><span class="sxs-lookup"><span data-stu-id="48ff1-146">Array elements are accessed by using the array name and including the index of the individual element in parentheses.</span></span>
- <span data-ttu-id="48ff1-147">它列出了数组的每个值。</span><span class="sxs-lookup"><span data-stu-id="48ff1-147">It lists each value of the array.</span></span> <span data-ttu-id="48ff1-148">该示例使用[ `For` ](../../../language-reference/statements/for-next-statement.md)语句来访问数组的每个元素按索引号。</span><span class="sxs-lookup"><span data-stu-id="48ff1-148">The example uses a [`For`](../../../language-reference/statements/for-next-statement.md) statement to access each element of the array by its index number.</span></span>
  
 <span data-ttu-id="48ff1-149">`students`前面的示例中的数组是一维数组，因为它使用一个索引。</span><span class="sxs-lookup"><span data-stu-id="48ff1-149">The `students` array in the preceding example is a one-dimensional array because it uses one index.</span></span> <span data-ttu-id="48ff1-150">使用多个索引或下标的数组称为*多维*。</span><span class="sxs-lookup"><span data-stu-id="48ff1-150">An array that uses more than one index or subscript is called *multidimensional*.</span></span> <span data-ttu-id="48ff1-151">有关详细信息，请参阅本文的其余部分和[在 Visual Basic 中的数组维数](../../../../visual-basic/programming-guide/language-features/arrays/array-dimensions.md)。</span><span class="sxs-lookup"><span data-stu-id="48ff1-151">For more information, see the rest of this article and [Array Dimensions in Visual Basic](../../../../visual-basic/programming-guide/language-features/arrays/array-dimensions.md).</span></span>  
  
##  <a name="creating-an-array"></a><span data-ttu-id="48ff1-152">创建数组</span><span class="sxs-lookup"><span data-stu-id="48ff1-152">Creating an Array</span></span>  
 
<span data-ttu-id="48ff1-153">以下几种方式，可以定义数组的大小：</span><span class="sxs-lookup"><span data-stu-id="48ff1-153">You can define the size of an array in several ways:</span></span> 

- <span data-ttu-id="48ff1-154">当声明数组时，可以指定大小：</span><span class="sxs-lookup"><span data-stu-id="48ff1-154">You can specify the size when the array is declared:</span></span>
  
    [!code-vb[creating1](../../../../../samples/snippets/visualbasic/programming-guide/language-features/arrays/create-array.vb#1)]  
  
 - <span data-ttu-id="48ff1-155">可以使用`New`子句提供数组大小，在创建时：</span><span class="sxs-lookup"><span data-stu-id="48ff1-155">You can use a `New` clause to supply the size of an array when it’s created:</span></span>  
  
    [!code-vb[creating2](../../../../../samples/snippets/visualbasic/programming-guide/language-features/arrays/create-array.vb#2)]  
  
 <span data-ttu-id="48ff1-156">如果具有现有数组，您可以通过使用来重新定义其大小[ `Redim` ](../../../../visual-basic/language-reference/statements/redim-statement.md)语句。</span><span class="sxs-lookup"><span data-stu-id="48ff1-156">If you have an existing array, you can redefine its size by using the [`Redim`](../../../../visual-basic/language-reference/statements/redim-statement.md) statement.</span></span> <span data-ttu-id="48ff1-157">您可以指定`Redim`语句保留数组中的值，也可以指定它创建一个空数组。</span><span class="sxs-lookup"><span data-stu-id="48ff1-157">You can specify that the `Redim` statement keep the values that are in the array, or you can specify that it create an empty array.</span></span> <span data-ttu-id="48ff1-158">下面的示例演示了用 `Redim` 语句来修改现有数组的大小的不同用法。</span><span class="sxs-lookup"><span data-stu-id="48ff1-158">The following example shows different uses of the `Redim` statement to modify the size of an existing array.</span></span>  
  
 [!code-vb[redimensioning](../../../../../samples/snippets/visualbasic/programming-guide/language-features/arrays/create-array.vb#3)]  
  
 <span data-ttu-id="48ff1-159">有关详细信息，请参阅[ReDim 语句](../../../../visual-basic/language-reference/statements/redim-statement.md)。</span><span class="sxs-lookup"><span data-stu-id="48ff1-159">For more information, see the [ReDim Statement](../../../../visual-basic/language-reference/statements/redim-statement.md).</span></span>  
  
##  <a name="storing-values-in-an-array"></a><span data-ttu-id="48ff1-160">存储数组中的值</span><span class="sxs-lookup"><span data-stu-id="48ff1-160">Storing Values in an Array</span></span>
 
 <span data-ttu-id="48ff1-161">你可以通过使用类型 `Integer` 的索引访问数组中的每个位置。</span><span class="sxs-lookup"><span data-stu-id="48ff1-161">You can access each location in an array by using an index of type `Integer`.</span></span> <span data-ttu-id="48ff1-162">你可以使用括号内的索引来引用每个数组位置，从而存储和检索数组中的值。</span><span class="sxs-lookup"><span data-stu-id="48ff1-162">You can store and retrieve values in an array by referencing each array location by using its index enclosed in parentheses.</span></span> <span data-ttu-id="48ff1-163">对于多维数组的索引用逗号 （，） 分隔。</span><span class="sxs-lookup"><span data-stu-id="48ff1-163">Indexes for multidimensional arrays are separated by commas (,).</span></span> <span data-ttu-id="48ff1-164">每个数组维度都需要一个索引。</span><span class="sxs-lookup"><span data-stu-id="48ff1-164">You need one index for each array dimension.</span></span> 

<span data-ttu-id="48ff1-165">下面的示例演示用于存储和检索值在数组中的一些语句。</span><span class="sxs-lookup"><span data-stu-id="48ff1-165">The following example shows some statements that store and retrieve values in arrays.</span></span>
  
 [!code-vb[store-and-retrieve](../../../../../samples/snippets/visualbasic/programming-guide/language-features/arrays/store-and-retrieve.vb)]  
  
## <a name="populating-an-array-with-array-literals"></a><span data-ttu-id="48ff1-166">使用数组文本填充数组</span><span class="sxs-lookup"><span data-stu-id="48ff1-166">Populating an array with array literals</span></span>
 <span data-ttu-id="48ff1-167">通过使用数组文本，可以创建它时填充具有一组初始的值的数组。</span><span class="sxs-lookup"><span data-stu-id="48ff1-167">By using an array literal, you can populate an array with an initial set of values at the same time that you create it.</span></span> <span data-ttu-id="48ff1-168">数组文本包含用逗号分隔的值列表，这些值被括在括号内 (`{}`)。</span><span class="sxs-lookup"><span data-stu-id="48ff1-168">An array literal consists of a list of comma-separated values that are enclosed in braces (`{}`).</span></span>  
  
 <span data-ttu-id="48ff1-169">通过使用数组文本创建数组时，可以提供数组类型或使用类型推理功能来确定数组类型。</span><span class="sxs-lookup"><span data-stu-id="48ff1-169">When you create an array by using an array literal, you can either supply the array type or use type inference to determine the array type.</span></span> <span data-ttu-id="48ff1-170">下面的示例显示了这两个选项。</span><span class="sxs-lookup"><span data-stu-id="48ff1-170">The following example shows both options.</span></span>  
  
 [!code-vb[create-with-literals](../../../../../samples/snippets/visualbasic/programming-guide/language-features/arrays/create-array.vb#4)]  
  
 <span data-ttu-id="48ff1-171">使用类型推理时，该数组的类型由*基准类型*中的文本值列表。</span><span class="sxs-lookup"><span data-stu-id="48ff1-171">When you use type inference, the type of the array is determined by the *dominant type* in the list of literal values.</span></span> <span data-ttu-id="48ff1-172">基准类型是数组中的所有其他类型可以扩大到的类型。</span><span class="sxs-lookup"><span data-stu-id="48ff1-172">The dominant type is the type to which all other types in the array can widen.</span></span> <span data-ttu-id="48ff1-173">如果无法确定此唯一类型，基准类型是数组中所有其他类型可以缩小到的唯一类型。</span><span class="sxs-lookup"><span data-stu-id="48ff1-173">If this unique type can’t be determined, the dominant type is the unique type to which all other types in the array can narrow.</span></span> <span data-ttu-id="48ff1-174">如果无法确定为这两种唯一类型之一，则基准类型是 `Object`。</span><span class="sxs-lookup"><span data-stu-id="48ff1-174">If neither of these unique types can be determined, the dominant type is `Object`.</span></span> <span data-ttu-id="48ff1-175">例如，如果提供给数组文本的值的列表包含 `Integer`、 `Long`和 `Double`类型的值，则生成的数组类型是 `Double`。</span><span class="sxs-lookup"><span data-stu-id="48ff1-175">For example, if the list of values that’s supplied to the array literal contains values of type `Integer`, `Long`, and `Double`, the resulting array is of type `Double`.</span></span> <span data-ttu-id="48ff1-176">因为`Integer`并`Long`仅扩大到`Double`，`Double`是基准类型。</span><span class="sxs-lookup"><span data-stu-id="48ff1-176">Because `Integer` and `Long` widen only to `Double`, `Double` is the dominant type.</span></span> <span data-ttu-id="48ff1-177">有关详细信息，请参阅 [Widening and Narrowing Conversions](../../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md)。</span><span class="sxs-lookup"><span data-stu-id="48ff1-177">For more information, see [Widening and Narrowing Conversions](../../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md).</span></span> 
 
> [!NOTE] 
> <span data-ttu-id="48ff1-178">仅对定义为本地变量的类型成员的数组，可以使用类型推理。</span><span class="sxs-lookup"><span data-stu-id="48ff1-178">You can use type inference only for arrays that are defined as local variables in a type member.</span></span> <span data-ttu-id="48ff1-179">如果缺少显式类型定义，则数组使用数组文本在类级别定义的类型是`Object[]`。</span><span class="sxs-lookup"><span data-stu-id="48ff1-179">If an explicit type definition is absent, arrays defined with array literals at the class level are of type `Object[]`.</span></span> <span data-ttu-id="48ff1-180">有关详细信息，请参阅[局部类型推理](../variables/local-type-inference.md)。</span><span class="sxs-lookup"><span data-stu-id="48ff1-180">For more information, see [Local type inference](../variables/local-type-inference.md).</span></span> 

<span data-ttu-id="48ff1-181">请注意，上面的示例定义`values`作为类型的数组`Double`即使所有数组文本都属于类型`Integer`。</span><span class="sxs-lookup"><span data-stu-id="48ff1-181">Note that the previous example defines `values` as an array of type `Double` even though all the array literals are of type `Integer`.</span></span> <span data-ttu-id="48ff1-182">您可以创建此数组，因为数组文本中的值可以扩大到`Double`值。</span><span class="sxs-lookup"><span data-stu-id="48ff1-182">You can create this array because the values in the array literal can widen to `Double` values.</span></span> 
  
 <span data-ttu-id="48ff1-183">此外可以创建并使用填充多维数组*嵌套数组文本*。</span><span class="sxs-lookup"><span data-stu-id="48ff1-183">You can also create and populate a multidimensional array by using *nested array literals*.</span></span> <span data-ttu-id="48ff1-184">嵌套的数组文本必须具有与生成的数组保持一致维度的数。</span><span class="sxs-lookup"><span data-stu-id="48ff1-184">Nested array literals must have a number of dimensions that’s consistent with the resulting array.</span></span> <span data-ttu-id="48ff1-185">下面的示例使用嵌套的数组文本创建一个二维整数的数组。</span><span class="sxs-lookup"><span data-stu-id="48ff1-185">The following example creates a two-dimensional array of integers by using nested array literals.</span></span>  
  
 [!code-vb[nested-array-literals](../../../../../samples/snippets/visualbasic/programming-guide/language-features/arrays/create-array.vb#5)]  
  
<span data-ttu-id="48ff1-186">在使用嵌套的数组文本创建并填充数组，如果嵌套的数组文本中的元素数不匹配，就会出错。</span><span class="sxs-lookup"><span data-stu-id="48ff1-186">When using nested array literals to create and populate an array, an error occurs if the number of elements in the nested array literals don't match.</span></span> <span data-ttu-id="48ff1-187">如果显式声明数组变量具有不同数量的维度比数组文本，也会发生错误。</span><span class="sxs-lookup"><span data-stu-id="48ff1-187">An error also occurs if you explicitly declare the array variable to have a different number of dimensions than the array literals.</span></span> 
  
<span data-ttu-id="48ff1-188">正如您可以对一维数组，可以使用嵌套的数组文本创建多维数组时依赖类型推断。</span><span class="sxs-lookup"><span data-stu-id="48ff1-188">Just as you can for one-dimensional arrays, you can rely on type inference when creating a multidimensional array with nested array literals.</span></span> <span data-ttu-id="48ff1-189">推断出的类型是所有的嵌套级别的所有数组文本中的所有值的基准类型。</span><span class="sxs-lookup"><span data-stu-id="48ff1-189">The inferred type is the dominant type for all the values in all the array literals for all nesting level.</span></span> <span data-ttu-id="48ff1-190">下面的示例创建类型的一个二维数组`Double[,]`属于类型的值从`Integer`和`Double`。</span><span class="sxs-lookup"><span data-stu-id="48ff1-190">The following example creates a two-dimensional array of type `Double[,]` from values that are of type `Integer` and `Double`.</span></span>  
  
 [!code-vb[nested-type-inference](../../../../../samples/snippets/visualbasic/programming-guide/language-features/arrays/create-array.vb#6)]  
  
 <span data-ttu-id="48ff1-191">有关其他示例，请参阅[如何：在 Visual Basic 中初始化数组变量](../../../../visual-basic/programming-guide/language-features/arrays/how-to-initialize-an-array-variable.md)。</span><span class="sxs-lookup"><span data-stu-id="48ff1-191">For additional examples, see [How to: Initialize an Array Variable in Visual Basic](../../../../visual-basic/programming-guide/language-features/arrays/how-to-initialize-an-array-variable.md).</span></span>  
  
##  <a name="iterating-through-an-array"></a><span data-ttu-id="48ff1-192">循环访问数组</span><span class="sxs-lookup"><span data-stu-id="48ff1-192">Iterating through an array</span></span>  
 <span data-ttu-id="48ff1-193">当循环访问数组时，访问数组中的每个元素，从最低到最高或从最高到低的顺序。</span><span class="sxs-lookup"><span data-stu-id="48ff1-193">When you iterate through an array, you access each element in the array from the lowest index to the highest or from the highest to the lowest.</span></span> <span data-ttu-id="48ff1-194">通常情况下，使用两种[为...下一条语句](../../../../visual-basic/language-reference/statements/for-next-statement.md)或[为每个...下一条语句](../../../../visual-basic/language-reference/statements/for-each-next-statement.md)循环访问数组的元素。</span><span class="sxs-lookup"><span data-stu-id="48ff1-194">Typically, use either the [For...Next Statement](../../../../visual-basic/language-reference/statements/for-next-statement.md) or the [For Each...Next Statement](../../../../visual-basic/language-reference/statements/for-each-next-statement.md) to iterate through the elements of an array.</span></span> <span data-ttu-id="48ff1-195">如果不知道数组的上限，您可以调用<xref:System.Array.GetUpperBound%2A?displayProperty=nameWithType>方法以获取索引的最高的值。</span><span class="sxs-lookup"><span data-stu-id="48ff1-195">When you don't know the upper bounds of the array, you can call the <xref:System.Array.GetUpperBound%2A?displayProperty=nameWithType> method to get the highest value of the index.</span></span> <span data-ttu-id="48ff1-196">尽管最小索引值是几乎始终为 0，可以调用<xref:System.Array.GetLowerBound%2A?displayProperty=nameWithType>方法以获取索引的最小值。</span><span class="sxs-lookup"><span data-stu-id="48ff1-196">Although lowest index value is almost always 0, you can call the <xref:System.Array.GetLowerBound%2A?displayProperty=nameWithType> method to get the lowest value of the index.</span></span>   
  
 <span data-ttu-id="48ff1-197">下面的示例循环访问一维数组，通过使用[ `For...Next` ](../../../../visual-basic/language-reference/statements/for-next-statement.md)语句。</span><span class="sxs-lookup"><span data-stu-id="48ff1-197">The following example iterates through a one-dimensional array by using the [`For...Next`](../../../../visual-basic/language-reference/statements/for-next-statement.md) statement.</span></span> 
  
 [!code-vb[iterate-one-dimensional-array](../../../../../samples/snippets/visualbasic/programming-guide/language-features/arrays/iterate1d.vb)]  
  
 <span data-ttu-id="48ff1-198">下面的示例循环访问通过使用多维数组[ `For...Next` ](../../../../visual-basic/language-reference/statements/for-next-statement.md)语句。</span><span class="sxs-lookup"><span data-stu-id="48ff1-198">The following example iterates through a multidimensional array by using a [`For...Next`](../../../../visual-basic/language-reference/statements/for-next-statement.md) statement.</span></span> <span data-ttu-id="48ff1-199"><xref:System.Array.GetUpperBound%2A> 方法具有用于指定维度的参数。</span><span class="sxs-lookup"><span data-stu-id="48ff1-199">The <xref:System.Array.GetUpperBound%2A> method has a parameter that specifies the dimension.</span></span> <span data-ttu-id="48ff1-200">`GetUpperBound(0)` 返回的最高的第一个维的索引和`GetUpperBound(1)`返回第二个维度的最高的索引。</span><span class="sxs-lookup"><span data-stu-id="48ff1-200">`GetUpperBound(0)` returns the highest index of the first dimension, and `GetUpperBound(1)` returns the highest index of the second dimension.</span></span>
  
 [!code-vb[iterate-two-dimensional-array](../../../../../samples/snippets/visualbasic/programming-guide/language-features/arrays/iterate2d.vb)]  
  
 <span data-ttu-id="48ff1-201">下面的示例使用[为每个...下一条语句](../../../../visual-basic/language-reference/statements/for-each-next-statement.md)循环访问一个一维数组和一个二维数组。</span><span class="sxs-lookup"><span data-stu-id="48ff1-201">The following example uses a [For Each...Next Statement](../../../../visual-basic/language-reference/statements/for-each-next-statement.md)to iterate through a one-dimensional array and a two-dimensional array.</span></span>  
  
 [!code-vb[iterate-for-each-next](../../../../../samples/snippets/visualbasic/programming-guide/language-features/arrays/iterate-for-each-next.vb)]  
  
## <a name="array-size"></a><span data-ttu-id="48ff1-202">数组大小</span><span class="sxs-lookup"><span data-stu-id="48ff1-202">Array Size</span></span>  

 <span data-ttu-id="48ff1-203">数组的大小是数组所有维度的长度的产物。</span><span class="sxs-lookup"><span data-stu-id="48ff1-203">The size of an array is the product of the lengths of all its dimensions.</span></span> <span data-ttu-id="48ff1-204">它表示数组中当前所包含的元素总数。</span><span class="sxs-lookup"><span data-stu-id="48ff1-204">It represents the total number of elements currently contained in the array.</span></span>  <span data-ttu-id="48ff1-205">例如，下面的示例声明包含每个维度中的四个元素的二维数组。</span><span class="sxs-lookup"><span data-stu-id="48ff1-205">For example, the following example declares a 2-dimensional array with four elements in each dimension.</span></span> <span data-ttu-id="48ff1-206">如示例输出所示，该数组的大小为 16 (或 (3 + 1) \* (3 + 1)。</span><span class="sxs-lookup"><span data-stu-id="48ff1-206">As the output from the example shows, the array's size is 16 (or (3 + 1) \* (3 + 1).</span></span>

 [!code-vb[array-size](../../../../../samples/snippets/visualbasic/programming-guide/language-features/arrays/array-size.vb)]  

> [!NOTE] 
> <span data-ttu-id="48ff1-207">数组大小的这一讨论不适用于交错数组。</span><span class="sxs-lookup"><span data-stu-id="48ff1-207">This discussion of array size does not apply to jagged arrays.</span></span> <span data-ttu-id="48ff1-208">交错的数组并确定交错数组的大小的信息，请参阅[交错数组](#jagged-arrays)部分。</span><span class="sxs-lookup"><span data-stu-id="48ff1-208">For information on jagged arrays and determining the size of a jagged array, see the [Jagged arrays](#jagged-arrays) section.</span></span>
  
  <span data-ttu-id="48ff1-209">可以通过使用 <xref:System.Array.Length%2A?displayProperty=nameWithType> 属性查找数组大小。</span><span class="sxs-lookup"><span data-stu-id="48ff1-209">You can find the size of an array by using the <xref:System.Array.Length%2A?displayProperty=nameWithType> property.</span></span> <span data-ttu-id="48ff1-210">你可以通过使用查找多维数组中的每个维的长度<xref:System.Array.GetLength%2A?displayProperty=nameWithType>方法。</span><span class="sxs-lookup"><span data-stu-id="48ff1-210">You can find the length of each dimension of a multidimensional array by using the <xref:System.Array.GetLength%2A?displayProperty=nameWithType> method.</span></span>  
  
 <span data-ttu-id="48ff1-211">通过将分配给它一个新数组对象，或可以调整大小的数组变量[`ReDim`语句](../../../../visual-basic/language-reference/statements/redim-statement.md)语句。</span><span class="sxs-lookup"><span data-stu-id="48ff1-211">You can resize an array variable by assigning a new array object to it or by using the [`ReDim` Statement](../../../../visual-basic/language-reference/statements/redim-statement.md) statement.</span></span> <span data-ttu-id="48ff1-212">下面的示例使用`ReDim`语句更改为 51 元素数组的一个 100 元素的数组。</span><span class="sxs-lookup"><span data-stu-id="48ff1-212">The following example uses the `ReDim` statement to change a 100-element array to a 51-element array.</span></span>

 [!code-vb[resize-an-array](../../../../../samples/snippets/visualbasic/programming-guide/language-features/arrays/array-size2.vb)]  
  
 <span data-ttu-id="48ff1-213">当处理数组大小时，需要记住几件事情。</span><span class="sxs-lookup"><span data-stu-id="48ff1-213">There are several things to keep in mind when dealing with the size of an array.</span></span>  
  
|||  
|---|---|  
|<span data-ttu-id="48ff1-214">维度长度</span><span class="sxs-lookup"><span data-stu-id="48ff1-214">Dimension Length</span></span>|<span data-ttu-id="48ff1-215">每个维度的索引是基于 0 的这意味着其范围为 0 到其上限之间。</span><span class="sxs-lookup"><span data-stu-id="48ff1-215">The index of each dimension is 0-based, which means it ranges from 0 to its upper bound.</span></span> <span data-ttu-id="48ff1-216">因此，给定维度的长度为一个大于该维度的声明的上限。</span><span class="sxs-lookup"><span data-stu-id="48ff1-216">Therefore, the length of a given dimension is one greater than the declared upper bound of that dimension.</span></span>|  
|<span data-ttu-id="48ff1-217">长度限制</span><span class="sxs-lookup"><span data-stu-id="48ff1-217">Length Limits</span></span>|<span data-ttu-id="48ff1-218">每一维数组的长度限制为的最大值`Integer`数据类型，即<xref:System.Int32.MaxValue?displayProperty=nameWithType>或 (2 ^31)-1。</span><span class="sxs-lookup"><span data-stu-id="48ff1-218">The length of every dimension of an array is limited to the maximum value of the `Integer` data type, which is <xref:System.Int32.MaxValue?displayProperty=nameWithType> or (2 ^ 31) - 1.</span></span> <span data-ttu-id="48ff1-219">但是，数组的总大小还受到系统上可用的内存限制。</span><span class="sxs-lookup"><span data-stu-id="48ff1-219">However, the total size of an array is also limited by the memory available on your system.</span></span> <span data-ttu-id="48ff1-220">如果尝试初始化数组超出可用内存量，则运行时会引发<xref:System.OutOfMemoryException>。</span><span class="sxs-lookup"><span data-stu-id="48ff1-220">If you attempt to initialize an array that exceeds the amount of available memory, the runtime throws an <xref:System.OutOfMemoryException>.</span></span>|  
|<span data-ttu-id="48ff1-221">大小和元素大小</span><span class="sxs-lookup"><span data-stu-id="48ff1-221">Size and Element Size</span></span>|<span data-ttu-id="48ff1-222">数组的大小独立于其元素的数据类型。</span><span class="sxs-lookup"><span data-stu-id="48ff1-222">An array's size is independent of the data type of its elements.</span></span> <span data-ttu-id="48ff1-223">大小始终表示元素 （不所占用的内存的字节数） 的总数。</span><span class="sxs-lookup"><span data-stu-id="48ff1-223">The size always represents the total number of elements, not the number of bytes that they consume in memory.</span></span>|  
|<span data-ttu-id="48ff1-224">内存消耗</span><span class="sxs-lookup"><span data-stu-id="48ff1-224">Memory Consumption</span></span>|<span data-ttu-id="48ff1-225">做出关于数组如何存储在内存中的假设是不可靠的。</span><span class="sxs-lookup"><span data-stu-id="48ff1-225">It is not safe to make any assumptions regarding how an array is stored in memory.</span></span> <span data-ttu-id="48ff1-226">由于不同数据宽度的平台上的存储会有所变化，因此同一数组在 64 位系统上可以占用比在 32 位系统上更多的内存。</span><span class="sxs-lookup"><span data-stu-id="48ff1-226">Storage varies on platforms of different data widths, so the same array can consume more memory on a 64-bit system than on a 32-bit system.</span></span> <span data-ttu-id="48ff1-227">具体取决于数组初始化时的系统配置，公共语言运行时 (CLR) 可以尽可能地将存储分配到靠近包元素的地方，或者将它们全部在自然硬件边界上对齐。</span><span class="sxs-lookup"><span data-stu-id="48ff1-227">Depending on system configuration when you initialize an array, the common language runtime (CLR) can assign storage either to pack elements as close together as possible, or to align them all on natural hardware boundaries.</span></span> <span data-ttu-id="48ff1-228">此外，数组需要存储开销的控制信息，而且每添加一个维度，这种开销随之增加。</span><span class="sxs-lookup"><span data-stu-id="48ff1-228">Also, an array requires a storage overhead for its control information, and this overhead increases with each added dimension.</span></span>|  

## <a name="the-array-type"></a><span data-ttu-id="48ff1-229">数组类型</span><span class="sxs-lookup"><span data-stu-id="48ff1-229">The array type</span></span> 
 <span data-ttu-id="48ff1-230">每个数组具有不同于它的元素的数据类型的数据类型。</span><span class="sxs-lookup"><span data-stu-id="48ff1-230">Every array has a data type, which differs from the data type of its elements.</span></span> <span data-ttu-id="48ff1-231">没有一种数据类型能用于所有数组。</span><span class="sxs-lookup"><span data-stu-id="48ff1-231">There is no single data type for all arrays.</span></span> <span data-ttu-id="48ff1-232">相反，数组的数据类型由数组的维度数量或 *“排名”*，以及数组中元素的数据类型确定。</span><span class="sxs-lookup"><span data-stu-id="48ff1-232">Instead, the data type of an array is determined by the number of dimensions, or *rank*, of the array, and the data type of the elements in the array.</span></span> <span data-ttu-id="48ff1-233">两个数组变量属于相同的数据，仅当它们具有相同的排名并且其元素具有相同的数据类型。</span><span class="sxs-lookup"><span data-stu-id="48ff1-233">Two array variables are of the same data type only when they have the same rank and their elements have the same data type.</span></span> <span data-ttu-id="48ff1-234">数组的维度的长度不会影响数组数据类型。</span><span class="sxs-lookup"><span data-stu-id="48ff1-234">The lengths of the dimensions of an array do not influence the array data type.</span></span>  
  
 <span data-ttu-id="48ff1-235">每个数组都继承自 <xref:System.Array?displayProperty=nameWithType> 类，并且你可以声明一个类型为 `Array` 的变量，但不能创建一个类型为 `Array` 的数组。</span><span class="sxs-lookup"><span data-stu-id="48ff1-235">Every array inherits from the <xref:System.Array?displayProperty=nameWithType> class, and you can declare a variable to be of type `Array`, but you cannot create an array of type `Array`.</span></span> <span data-ttu-id="48ff1-236">例如，虽然下面的代码声明`arr`变量的类型为`Array`，并调用<xref:System.Array.CreateInstance%2A?displayProperty=nameWithType>方法可实例化的数组，该数组类型的事实证明，Object []。</span><span class="sxs-lookup"><span data-stu-id="48ff1-236">For example, although the following code declares the `arr` variable to be of type `Array` and calls the <xref:System.Array.CreateInstance%2A?displayProperty=nameWithType> method to instantiate the array, the array's type proves to be Object[].</span></span>

 [!code-vb[array-class](../../../../../samples/snippets/visualbasic/programming-guide/language-features/arrays/array-class.vb)] 

<span data-ttu-id="48ff1-237">此外，[ReDim 语句](../../../../visual-basic/language-reference/statements/redim-statement.md)无法对声明为类型 `Array` 的变量执行运算。</span><span class="sxs-lookup"><span data-stu-id="48ff1-237">Also, the [ReDim Statement](../../../../visual-basic/language-reference/statements/redim-statement.md) cannot operate on a variable declared as type `Array`.</span></span> <span data-ttu-id="48ff1-238">出于这些原因，以及为类型安全，则最好声明为特定类型的每个数组。</span><span class="sxs-lookup"><span data-stu-id="48ff1-238">For these reasons, and for type safety, it is advisable to declare every array as a specific type.</span></span>  
  
 <span data-ttu-id="48ff1-239">你可以通过几种方式了解到数组及其元素的数据类型。</span><span class="sxs-lookup"><span data-stu-id="48ff1-239">You can find out the data type of either an array or its elements in several ways.</span></span> 
  
-   <span data-ttu-id="48ff1-240">您可以调用<xref:System.Object.GetType%2A>方法以获取对变量<xref:System.Type>表示变量的运行时类型的对象。</span><span class="sxs-lookup"><span data-stu-id="48ff1-240">You can call the <xref:System.Object.GetType%2A> method on the variable to get a <xref:System.Type> object that represents the run-time type of the variable.</span></span> <span data-ttu-id="48ff1-241"><xref:System.Type> 对象可在其属性和方法中保存大量信息。</span><span class="sxs-lookup"><span data-stu-id="48ff1-241">The <xref:System.Type> object holds extensive information in its properties and methods.</span></span>  
  
-   <span data-ttu-id="48ff1-242">您可以将该变量传递到<xref:Microsoft.VisualBasic.Information.TypeName%2A>函数以获取`String`与运行时类型的名称。</span><span class="sxs-lookup"><span data-stu-id="48ff1-242">You can pass the variable to the <xref:Microsoft.VisualBasic.Information.TypeName%2A> function to get a `String` with the name of run-time type.</span></span>  
  
 <span data-ttu-id="48ff1-243">下面的示例调用两`GetType`方法和`TypeName`函数来确定数组的类型。</span><span class="sxs-lookup"><span data-stu-id="48ff1-243">The following example calls the both the `GetType` method and the `TypeName` function to determine the type of an array.</span></span> <span data-ttu-id="48ff1-244">数组类型是`Byte(,)`。</span><span class="sxs-lookup"><span data-stu-id="48ff1-244">The array type is `Byte(,)`.</span></span> <span data-ttu-id="48ff1-245">请注意，<xref:System.Type.BaseType%2A?displayProperty=nameWithType>属性还指示字节数组的基类型是<xref:System.Array>类。</span><span class="sxs-lookup"><span data-stu-id="48ff1-245">Note that the <xref:System.Type.BaseType%2A?displayProperty=nameWithType> property also indicates that the base type of the byte array is the <xref:System.Array> class.</span></span>  
  
 [!code-vb[array-type](../../../../../samples/snippets/visualbasic/programming-guide/language-features/arrays/array-type.vb)]  
  
##  <a name="arrays-as-return-values-and-parameters"></a><span data-ttu-id="48ff1-246">作为返回值和参数的数组</span><span class="sxs-lookup"><span data-stu-id="48ff1-246">Arrays as return values and parameters</span></span>  
 <span data-ttu-id="48ff1-247">若要通过 `Function` 过程返回数组，请将数组数据类型和维度数指定为 [Function 语句](../../../../visual-basic/language-reference/statements/function-statement.md)的返回类型。</span><span class="sxs-lookup"><span data-stu-id="48ff1-247">To return an array from a `Function` procedure, specify the array data type and the number of dimensions as the return type of the [Function Statement](../../../../visual-basic/language-reference/statements/function-statement.md).</span></span> <span data-ttu-id="48ff1-248">在函数内，声明一个具有相同数据类型和维度数的本地数组变量。</span><span class="sxs-lookup"><span data-stu-id="48ff1-248">Within the function, declare a local array variable with same data type and number of dimensions.</span></span> <span data-ttu-id="48ff1-249">在 [Return 语句](../../../../visual-basic/language-reference/statements/return-statement.md)中，添加不带括号的局部数组变量。</span><span class="sxs-lookup"><span data-stu-id="48ff1-249">In the [Return Statement](../../../../visual-basic/language-reference/statements/return-statement.md), include the local array variable without parentheses.</span></span>  
  
 <span data-ttu-id="48ff1-250">若要将作为参数的数组指定到 `Sub` 或 `Function` 步骤中，可将此参数定义为具有指定数据类型和维度数量的数组。</span><span class="sxs-lookup"><span data-stu-id="48ff1-250">To specify an array as a parameter to a `Sub` or `Function` procedure, define the parameter as an array with a specified data type and number of dimensions.</span></span> <span data-ttu-id="48ff1-251">在过程调用中，将传递一个数组变量具有相同的数据类型和维度数。</span><span class="sxs-lookup"><span data-stu-id="48ff1-251">In the call to the procedure, pass an array variable with the same data type and number of dimensions.</span></span>  
  
 <span data-ttu-id="48ff1-252">在以下示例中，`GetNumbers`函数返回`Integer()`，类型的一维数组`Integer`。</span><span class="sxs-lookup"><span data-stu-id="48ff1-252">In the following example, the `GetNumbers` function returns an `Integer()`, a one-dimensional array of type `Integer`.</span></span> <span data-ttu-id="48ff1-253">`ShowNumbers` 过程接受 `Integer()` 参数。</span><span class="sxs-lookup"><span data-stu-id="48ff1-253">The `ShowNumbers` procedure accepts an `Integer()` argument.</span></span> 
  
 [!code-vb[return-value-and-params](../../../../../samples/snippets/visualbasic/programming-guide/language-features/arrays/return-values-and-params.vb)]  
  
 <span data-ttu-id="48ff1-254">在以下示例中，`GetNumbersMultiDim`函数返回`Integer(,)`，类型的二维数组`Integer`。</span><span class="sxs-lookup"><span data-stu-id="48ff1-254">In the following example, the `GetNumbersMultiDim` function returns an `Integer(,)`, a two-dimensional array of type `Integer`.</span></span>  <span data-ttu-id="48ff1-255">`ShowNumbersMultiDim` 过程接受 `Integer(,)` 参数。</span><span class="sxs-lookup"><span data-stu-id="48ff1-255">The `ShowNumbersMultiDim` procedure accepts an `Integer(,)` argument.</span></span>  
  
 [!code-vb[multidimensional-return-value](../../../../../samples/snippets/visualbasic/programming-guide/language-features/arrays/return-values-and-params-2d.vb)]  
  
## <a name="jagged-arrays"></a><span data-ttu-id="48ff1-256">交错数组</span><span class="sxs-lookup"><span data-stu-id="48ff1-256">Jagged Arrays</span></span>  
 
<span data-ttu-id="48ff1-257">有时应用程序中的数据结构是二维而不是矩形。</span><span class="sxs-lookup"><span data-stu-id="48ff1-257">Sometimes the data structure in your application is two-dimensional but not rectangular.</span></span> <span data-ttu-id="48ff1-258">例如，可能会使用数组来存储有关每一天的月份的高温度数据。</span><span class="sxs-lookup"><span data-stu-id="48ff1-258">For example, you might use an array to store data about the high temperature of each day of the month.</span></span> <span data-ttu-id="48ff1-259">数组的第一个维度表示月份，但第二个维度表示的天数，并在一个月的天数不均匀。</span><span class="sxs-lookup"><span data-stu-id="48ff1-259">The first dimension of the array represents the month, but the second dimension represents the number of days, and the number of days in a month is not uniform.</span></span> <span data-ttu-id="48ff1-260">一个*交错的数组*，这也称为*数组的数组*，专为此类方案。</span><span class="sxs-lookup"><span data-stu-id="48ff1-260">A *jagged array*, which is also called an *array of arrays*, is designed for such scenarios.</span></span> <span data-ttu-id="48ff1-261">交错的数组是一个数组，其元素也是数组。</span><span class="sxs-lookup"><span data-stu-id="48ff1-261">A jagged array is an array whose elements are also arrays.</span></span> <span data-ttu-id="48ff1-262">交错数组和交错数组中的每个元素都可以具有一个或多个维度。</span><span class="sxs-lookup"><span data-stu-id="48ff1-262">A jagged array and each element in a jagged array can have one or more dimensions.</span></span>  
  
 <span data-ttu-id="48ff1-263">以下示例使用月份数组，其中每个元素是天数数组。</span><span class="sxs-lookup"><span data-stu-id="48ff1-263">The following example uses an array of months, each element of which is an array of days.</span></span> <span data-ttu-id="48ff1-264">该示例使用交错的数组，因为不同月份有不同的天数。</span><span class="sxs-lookup"><span data-stu-id="48ff1-264">The example uses a jagged array because different months have different numbers of days.</span></span>  <span data-ttu-id="48ff1-265">示例演示如何创建交错的数组，将值分配给它，并检索和显示它的值。</span><span class="sxs-lookup"><span data-stu-id="48ff1-265">The example shows how to create a jagged array, assign values to it, and retrieve and display its values.</span></span>
  
 [!code-vb[jagged-arrays](../../../../../samples/snippets/visualbasic/programming-guide/language-features/arrays/jagged.vb)]  

<span data-ttu-id="48ff1-266">前面的示例通过将值分配给交错数组元素的元素按`For...Next`循环。</span><span class="sxs-lookup"><span data-stu-id="48ff1-266">The previous example assigns values to the jagged array on an element-by-element basis by using a `For...Next` loop.</span></span> <span data-ttu-id="48ff1-267">通过使用嵌套的数组文本，还可以将值分配到交错数组的元素。</span><span class="sxs-lookup"><span data-stu-id="48ff1-267">You can also assign values to the elements of a jagged array by using nested array literals.</span></span> <span data-ttu-id="48ff1-268">但是，尝试使用嵌套数组文本 (例如， ```Dim valuesjagged = {{1, 2}, {2, 3, 4}}```) 会生成编译器错误[BC30568](../../../,,/../misc/bc30568.md)。</span><span class="sxs-lookup"><span data-stu-id="48ff1-268">However, the attempt to use nested array literals (for example, ```Dim valuesjagged = {{1, 2}, {2, 3, 4}}```) generates compiler error [BC30568](../../../,,/../misc/bc30568.md).</span></span> <span data-ttu-id="48ff1-269">若要更正此错误，请用括号括起来将内部数组文本。</span><span class="sxs-lookup"><span data-stu-id="48ff1-269">To correct the error, enclose the inner array literals in parentheses.</span></span> <span data-ttu-id="48ff1-270">圆括号会强制进行计算的数组文本表达式和生成的值用于外部数组文本，如以下示例所示。</span><span class="sxs-lookup"><span data-stu-id="48ff1-270">The parentheses force the array literal expression to be evaluated, and the resulting values are used with the outer array literal, as the following example shows.</span></span>  
  
 [!code-vb[jagged-array-initialization](../../../../../samples/snippets/visualbasic/programming-guide/language-features/arrays/jagged-assign.vb)] 

<span data-ttu-id="48ff1-271">交错的数组是一维数组，其元素包含的数组。</span><span class="sxs-lookup"><span data-stu-id="48ff1-271">A jagged array is a one-dimensional array whose elements contain arrays.</span></span> <span data-ttu-id="48ff1-272">因此，<xref:System.Array.Length%2A?displayProperty=nameWithType>属性和`Array.GetLength(0)`方法返回的元素数中的一维数组，并`Array.GetLength(1)`引发<xref:System.IndexOutOfRangeException>因为交错的数组不是多维。</span><span class="sxs-lookup"><span data-stu-id="48ff1-272">Therefore, the <xref:System.Array.Length%2A?displayProperty=nameWithType> property and the `Array.GetLength(0)` method return the number of elements in the one-dimensional array, and `Array.GetLength(1)` throws an <xref:System.IndexOutOfRangeException> because a jagged array is not multidimensional.</span></span> <span data-ttu-id="48ff1-273">检索的每个子数组的值来确定每个子数组中的元素数<xref:System.Array.Length%2A?displayProperty=nameWithType>属性。</span><span class="sxs-lookup"><span data-stu-id="48ff1-273">You determine the number of elements in each subarray by retrieving the value of each subarray's <xref:System.Array.Length%2A?displayProperty=nameWithType> property.</span></span> <span data-ttu-id="48ff1-274">下面的示例说明了如何确定交错数组中的元素数。</span><span class="sxs-lookup"><span data-stu-id="48ff1-274">The following example illustrates how to determine the number of elements in a jagged array.</span></span>

[!code-vb[jagged-array-size](../../../../../samples/snippets/visualbasic/programming-guide/language-features/arrays/jagged-length.vb)] 

## <a name="zero-length-arrays"></a><span data-ttu-id="48ff1-275">零长度数组</span><span class="sxs-lookup"><span data-stu-id="48ff1-275">Zero-length arrays</span></span>  
<span data-ttu-id="48ff1-276">Visual Basic 区分未初始化的数组 (其值是一个数组`Nothing`) 和一个*零长度数组*或空数组 （不包含任何元素的数组。）未初始化的数组是不确定维度或向其分配任何值。</span><span class="sxs-lookup"><span data-stu-id="48ff1-276">Visual Basic differentiates between a uninitialized array (an array whose value is `Nothing`) and a *zero-length array* or empty array (an array that has no elements.) An uninitialized array is one that has not been dimensioned or had any values assigned to it.</span></span> <span data-ttu-id="48ff1-277">例如：</span><span class="sxs-lookup"><span data-stu-id="48ff1-277">For example:</span></span>

```vb
Dim arr() As String
```
<span data-ttu-id="48ff1-278">声明为-1 维的长度为零的数组。</span><span class="sxs-lookup"><span data-stu-id="48ff1-278">A zero-length array is declared with a dimension of -1.</span></span> <span data-ttu-id="48ff1-279">例如：</span><span class="sxs-lookup"><span data-stu-id="48ff1-279">For example:</span></span>

```vb
Dim arrZ(-1) As String
```
<span data-ttu-id="48ff1-280">在下列情况下，你可能需要创建一个零长度数组：</span><span class="sxs-lookup"><span data-stu-id="48ff1-280">You might need to create a zero-length array under the following circumstances:</span></span>  
  
-   <span data-ttu-id="48ff1-281">不会有风险的情况下<xref:System.NullReferenceException>异常，你的代码必须访问的成员<xref:System.Array>类，如<xref:System.Array.Length%2A>或<xref:System.Array.Rank%2A>，或调用 Visual Basic 函数，例如<xref:Microsoft.VisualBasic.Information.UBound%2A>。</span><span class="sxs-lookup"><span data-stu-id="48ff1-281">Without risking a <xref:System.NullReferenceException> exception, your code must access members of the <xref:System.Array> class, such as <xref:System.Array.Length%2A> or <xref:System.Array.Rank%2A>, or call a Visual Basic function such as <xref:Microsoft.VisualBasic.Information.UBound%2A>.</span></span>  
  
-   <span data-ttu-id="48ff1-282">你想要保留您的代码，而不必检查简单`Nothing`作为一种特殊情况。</span><span class="sxs-lookup"><span data-stu-id="48ff1-282">You want to keep your code simple by not having to check for `Nothing` as a special case.</span></span>  
  
-   <span data-ttu-id="48ff1-283">你的代码与应用程序编程接口 (API) 交互，该接口要求你将一个零长度数组传递到一个或多个过程，或将一个零长度数组返回到一个或多个过程。</span><span class="sxs-lookup"><span data-stu-id="48ff1-283">Your code interacts with an application programming interface (API) that either requires you to pass a zero-length array to one or more procedures or returns a zero-length array from one or more procedures.</span></span>

## <a name="splitting-an-array"></a><span data-ttu-id="48ff1-284">拆分数组</span><span class="sxs-lookup"><span data-stu-id="48ff1-284">Splitting an array</span></span>

<span data-ttu-id="48ff1-285">在某些情况下，可能需要拆分为多个数组的单个数组。</span><span class="sxs-lookup"><span data-stu-id="48ff1-285">In some cases, you may need to split a single array into multiple arrays.</span></span> <span data-ttu-id="48ff1-286">这涉及到确定的点或点的数组将被拆分，并为两个或多个单独的数组，然后快速数组。</span><span class="sxs-lookup"><span data-stu-id="48ff1-286">This involves identifying the point or points at which the array is to be split, and then spitting the array into two or more separate arrays.</span></span> 

> [!NOTE] 
> <span data-ttu-id="48ff1-287">本部分不讨论如何将单个字符串拆分为基于某些分隔符的字符串数组。</span><span class="sxs-lookup"><span data-stu-id="48ff1-287">This section does not discuss splitting a single string into a string array based on some delimiter.</span></span> <span data-ttu-id="48ff1-288">有关将字符串拆分的信息，请参阅<xref:System.String.Split%2A?displayProperty=nameWithType>方法。</span><span class="sxs-lookup"><span data-stu-id="48ff1-288">For information on splitting a string, see the <xref:System.String.Split%2A?displayProperty=nameWithType> method.</span></span>

<span data-ttu-id="48ff1-289">用于拆分数组的最常见条件是：</span><span class="sxs-lookup"><span data-stu-id="48ff1-289">The most common criteria for splitting an array are:</span></span>

- <span data-ttu-id="48ff1-290">数组中的元素数。</span><span class="sxs-lookup"><span data-stu-id="48ff1-290">The number of elements in the array.</span></span> <span data-ttu-id="48ff1-291">例如，您可能想要为多个相等部分大约拆分数超过了指定的元素的数组。</span><span class="sxs-lookup"><span data-stu-id="48ff1-291">For example, you might want to split an array of more than a specified number of elements into a number of approximately equal parts.</span></span> <span data-ttu-id="48ff1-292">为此，可以使用通过以下任一方法返回的值<xref:System.Array.Length%2A?displayProperty=nameWithType>或<xref:System.Array.GetLength%2A?displayProperty=nameWithType>方法。</span><span class="sxs-lookup"><span data-stu-id="48ff1-292">For this purpose, you can use the value returned by either the <xref:System.Array.Length%2A?displayProperty=nameWithType> or <xref:System.Array.GetLength%2A?displayProperty=nameWithType> method.</span></span>

- <span data-ttu-id="48ff1-293">用作分隔符，该值指示应在何处拆分数组的元素的值。</span><span class="sxs-lookup"><span data-stu-id="48ff1-293">The value of an element, which serves as a delimiter that indicates where the array should be split.</span></span> <span data-ttu-id="48ff1-294">您可以通过调用来搜索特定值<xref:System.Array.FindIndex%2A?displayProperty=nameWithType>和<xref:System.Array.FindLastIndex%2A?displayProperty=nameWithType>方法。</span><span class="sxs-lookup"><span data-stu-id="48ff1-294">You can search for a specific value by calling the <xref:System.Array.FindIndex%2A?displayProperty=nameWithType> and <xref:System.Array.FindLastIndex%2A?displayProperty=nameWithType> methods.</span></span>
 
<span data-ttu-id="48ff1-295">一旦确定了应在其中拆分数组的索引，然后可以通过调用创建个人数组<xref:System.Array.Copy%2A?displayProperty=nameWithType>方法。</span><span class="sxs-lookup"><span data-stu-id="48ff1-295">Once you've determined the index or indexes at which the array should be split, you can then create the individual arrays by calling the <xref:System.Array.Copy%2A?displayProperty=nameWithType> method.</span></span> 

<span data-ttu-id="48ff1-296">下面的示例将数组拆分成两个数组大小大致相等。</span><span class="sxs-lookup"><span data-stu-id="48ff1-296">The following example splits an array into two arrays of approximately equal size.</span></span> <span data-ttu-id="48ff1-297">（如果数组元素的总数为奇数，第一个数组具有多个元素的第二个。）</span><span class="sxs-lookup"><span data-stu-id="48ff1-297">(If the total number of array elements is odd, the first array has one more element than the second.)</span></span> 

[!code-vb[splitting-an-array-by-length](../../../../../samples/snippets/visualbasic/programming-guide/language-features/arrays/split1.vb)] 

<span data-ttu-id="48ff1-298">下面的示例将一个字符串数组拆分成两个数组根据其值为"zzz"，可作为数组分隔符的元素存在。</span><span class="sxs-lookup"><span data-stu-id="48ff1-298">The following example splits a string array into two arrays based on the presence of an element whose value is "zzz", which serves as the array delimiter.</span></span> <span data-ttu-id="48ff1-299">新数组不包括包含分隔符的元素。</span><span class="sxs-lookup"><span data-stu-id="48ff1-299">The new arrays do not include the element that contains the delimiter.</span></span>

[!code-vb[splitting-an-array-by-delimiter](../../../../../samples/snippets/visualbasic/programming-guide/language-features/arrays/split2.vb)] 

## <a name="joining-arrays"></a><span data-ttu-id="48ff1-300">加入数组</span><span class="sxs-lookup"><span data-stu-id="48ff1-300">Joining arrays</span></span>

<span data-ttu-id="48ff1-301">此外可以组合多个数组合并为一个更大数组。</span><span class="sxs-lookup"><span data-stu-id="48ff1-301">You can also combine a number of arrays into a single larger array.</span></span> <span data-ttu-id="48ff1-302">若要执行此操作，还使用<xref:System.Array.Copy%2A?displayProperty=nameWithType>方法。</span><span class="sxs-lookup"><span data-stu-id="48ff1-302">To do this, you also use the <xref:System.Array.Copy%2A?displayProperty=nameWithType> method.</span></span> 

> [!NOTE] 
> <span data-ttu-id="48ff1-303">本部分不讨论联接成单个字符串的字符串数组。</span><span class="sxs-lookup"><span data-stu-id="48ff1-303">This section does not discuss joining a string array into a single string.</span></span> <span data-ttu-id="48ff1-304">有关联接的字符串数组的信息，请参阅<xref:System.String.Join%2A?displayProperty=nameWithType>方法。</span><span class="sxs-lookup"><span data-stu-id="48ff1-304">For information on joining a string array, see the <xref:System.String.Join%2A?displayProperty=nameWithType> method.</span></span>

<span data-ttu-id="48ff1-305">然后再将每个数组的元素复制到新数组，您首先必须确保，这样就足够大到 accompodate 新数组初始化数组。</span><span class="sxs-lookup"><span data-stu-id="48ff1-305">Before copying the elements of each array into the new array, you must first ensure that you have initialized the array so that it is large enough to accompodate the new array.</span></span> <span data-ttu-id="48ff1-306">可以通过两种方法执行此操作：</span><span class="sxs-lookup"><span data-stu-id="48ff1-306">You can do this in one of two ways:</span></span>

- <span data-ttu-id="48ff1-307">使用[ `ReDim Preserve` ](../../../../visual-basic/language-reference/statements/redim-statement.md)语句，以便动态地将新元素添加到它之前展开数组。</span><span class="sxs-lookup"><span data-stu-id="48ff1-307">Use the [`ReDim Preserve`](../../../../visual-basic/language-reference/statements/redim-statement.md) statement to dynamically expand the array before adding new elements to it.</span></span> <span data-ttu-id="48ff1-308">这是最简单的技术，但它可能会导致性能下降并占用过多内存时要复制大型数组。</span><span class="sxs-lookup"><span data-stu-id="48ff1-308">This is the easiest technique, but it can result in performance degradation and excessive memory consumption when you are copying large arrays.</span></span>
- <span data-ttu-id="48ff1-309">计算所需的新的大型数组的元素的总数，然后将每个源数组的元素添加到它。</span><span class="sxs-lookup"><span data-stu-id="48ff1-309">Calculate the total number of elements needed for the new large array, then add the elements of each source array to it.</span></span>

<span data-ttu-id="48ff1-310">以下示例使用第二种方法将具有 10 个元素的四个数组添加到单个数组。</span><span class="sxs-lookup"><span data-stu-id="48ff1-310">The following example uses the second approach to add four arrays with ten elements each to a single array.</span></span>  

[!code-vb[joining-an-array](../../../../../samples/snippets/visualbasic/programming-guide/language-features/arrays/join.vb)] 

<span data-ttu-id="48ff1-311">因为在这种情况下源数组也是所有小型，我们还可以动态地可以展开数组，我们将每个新数组的元素添加到它。</span><span class="sxs-lookup"><span data-stu-id="48ff1-311">Since in this case the source arrays are all small, we can also dynamically expand the array as we add the elements of each new array to it.</span></span> <span data-ttu-id="48ff1-312">以下示例执行该操作。</span><span class="sxs-lookup"><span data-stu-id="48ff1-312">The following example does that.</span></span>

[!code-vb[joining-an-array-dynamically](../../../../../samples/snippets/visualbasic/programming-guide/language-features/arrays/join2.vb)] 

##  <a name="collections-as-an-alternative-to-arrays"></a><span data-ttu-id="48ff1-313">作为数组的替代方法的集合</span><span class="sxs-lookup"><span data-stu-id="48ff1-313">Collections as an alternative to arrays</span></span>  
 <span data-ttu-id="48ff1-314">数组最适用于创建和使用固定数量的强类型化对象。</span><span class="sxs-lookup"><span data-stu-id="48ff1-314">Arrays are most useful for creating and working with a fixed number of strongly typed objects.</span></span> <span data-ttu-id="48ff1-315">集合提供更灵活的方式来使用对象组。</span><span class="sxs-lookup"><span data-stu-id="48ff1-315">Collections provide a more flexible way to work with groups of objects.</span></span> <span data-ttu-id="48ff1-316">与数组不同，这需要明确地更改与数组的大小[`ReDim`语句](../../../../visual-basic/language-reference/statements/redim-statement.md)，集合增加和减少动态随着需求的应用程序更改。</span><span class="sxs-lookup"><span data-stu-id="48ff1-316">Unlike arrays, which require that you explicitly change the size of an array with the [`ReDim` Statement](../../../../visual-basic/language-reference/statements/redim-statement.md), collections grow and shrink dynamically as the needs of an application change.</span></span>  
  
 <span data-ttu-id="48ff1-317">当你使用`ReDim`来重新设置其维数的数组，Visual Basic 创建一个新数组，并释放上一个。</span><span class="sxs-lookup"><span data-stu-id="48ff1-317">When you use `ReDim` to redimension an array, Visual Basic creates a new array and releases the previous one.</span></span> <span data-ttu-id="48ff1-318">这需要执行时间。</span><span class="sxs-lookup"><span data-stu-id="48ff1-318">This takes execution time.</span></span> <span data-ttu-id="48ff1-319">因此，如果你正在使用频繁变化，或者您的项目数不能预测所需的最大项数，您通常将使用集合来获得更好的性能。</span><span class="sxs-lookup"><span data-stu-id="48ff1-319">Therefore, if the number of items you are working with changes frequently, or you cannot predict the maximum number of items you need, you'll usually obtain better performance by using a collection.</span></span>  
  
 <span data-ttu-id="48ff1-320">对于某些集合，你可以为放入集合中的任何对象分配一个密钥，这样你便可以使用该密钥快速检索此对象。</span><span class="sxs-lookup"><span data-stu-id="48ff1-320">For some collections, you can assign a key to any object that you put into the collection so that you can quickly retrieve the object by using the key.</span></span>  
  
 <span data-ttu-id="48ff1-321">如果你的集合中只包含一种数据类型的元素，你可以使用 <xref:System.Collections.Generic?displayProperty=nameWithType> 命名空间中的一个类。</span><span class="sxs-lookup"><span data-stu-id="48ff1-321">If your collection contains elements of only one data type, you can use one of the classes in the <xref:System.Collections.Generic?displayProperty=nameWithType> namespace.</span></span> <span data-ttu-id="48ff1-322">泛型集合强制类型安全，因此无法向其添加任何其他数据类型。</span><span class="sxs-lookup"><span data-stu-id="48ff1-322">A generic collection enforces type safety so that no other data type can be added to it.</span></span>  
  
 <span data-ttu-id="48ff1-323">有关集合的详细信息，请参阅[集合](../../concepts/collections.md)。</span><span class="sxs-lookup"><span data-stu-id="48ff1-323">For more information about collections, see [Collections](../../concepts/collections.md).</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="48ff1-324">相关主题</span><span class="sxs-lookup"><span data-stu-id="48ff1-324">Related Topics</span></span>  
  
|<span data-ttu-id="48ff1-325">术语</span><span class="sxs-lookup"><span data-stu-id="48ff1-325">Term</span></span>|<span data-ttu-id="48ff1-326">定义</span><span class="sxs-lookup"><span data-stu-id="48ff1-326">Definition</span></span>|  
|----------|----------------|  
|[<span data-ttu-id="48ff1-327">Array Dimensions in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="48ff1-327">Array Dimensions in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/arrays/array-dimensions.md)|<span data-ttu-id="48ff1-328">在数组中解释级别和维度。</span><span class="sxs-lookup"><span data-stu-id="48ff1-328">Explains rank and dimensions in arrays.</span></span>|  
|[<span data-ttu-id="48ff1-329">如何：在 Visual Basic 中初始化数组变量</span><span class="sxs-lookup"><span data-stu-id="48ff1-329">How to: Initialize an Array Variable in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/arrays/how-to-initialize-an-array-variable.md)|<span data-ttu-id="48ff1-330">说明如何用初始值填充数组。</span><span class="sxs-lookup"><span data-stu-id="48ff1-330">Describes how to populate arrays with initial values.</span></span>|  
|[<span data-ttu-id="48ff1-331">如何：在 Visual Basic 中对数组进行排序</span><span class="sxs-lookup"><span data-stu-id="48ff1-331">How to: Sort An Array in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/arrays/how-to-sort-an-array.md)|<span data-ttu-id="48ff1-332">显示如何按字母先后顺序对数组元素进行排序。</span><span class="sxs-lookup"><span data-stu-id="48ff1-332">Shows how to sort the elements of an array alphabetically.</span></span>|  
|[<span data-ttu-id="48ff1-333">如何：将一个数组赋给另一个数组</span><span class="sxs-lookup"><span data-stu-id="48ff1-333">How to: Assign One Array to Another Array</span></span>](../../../../visual-basic/programming-guide/language-features/arrays/how-to-assign-one-array-to-another-array.md)|<span data-ttu-id="48ff1-334">说明将数组分配到另一个数组变量的规则和步骤。</span><span class="sxs-lookup"><span data-stu-id="48ff1-334">Describes the rules and steps for assigning an array to another array variable.</span></span>|  
|[<span data-ttu-id="48ff1-335">数组疑难解答</span><span class="sxs-lookup"><span data-stu-id="48ff1-335">Troubleshooting Arrays</span></span>](../../../../visual-basic/programming-guide/language-features/arrays/troubleshooting-arrays.md)|<span data-ttu-id="48ff1-336">讨论在使用数组时出现的一些常见问题。</span><span class="sxs-lookup"><span data-stu-id="48ff1-336">Discusses some common problems that arise when working with arrays.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="48ff1-337">请参阅</span><span class="sxs-lookup"><span data-stu-id="48ff1-337">See Also</span></span>  
 <xref:System.Array?displayProperty=nameWithType>  
 [<span data-ttu-id="48ff1-338">Dim 语句</span><span class="sxs-lookup"><span data-stu-id="48ff1-338">Dim Statement</span></span>](../../../../visual-basic/language-reference/statements/dim-statement.md)  
 [<span data-ttu-id="48ff1-339">ReDim 语句</span><span class="sxs-lookup"><span data-stu-id="48ff1-339">ReDim Statement</span></span>](../../../../visual-basic/language-reference/statements/redim-statement.md)
