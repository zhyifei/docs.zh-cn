---
title: 如何：在 Visual Basic 中初始化数组变量
ms.date: 07/20/2015
helpviewer_keywords:
- variables [Visual Basic], initializing
- arrays [Visual Basic], variables
- arrays [Visual Basic], initializing
- arrays [Visual Basic], declaring
ms.assetid: aadd7a60-7ca4-4608-b986-091f19e7fc10
ms.openlocfilehash: 4ce2e061c5f523fae3020b08034875422a0062a7
ms.sourcegitcommit: 9bd8f213b50f0e1a73e03bd1e840c917fbd6d20a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2018
ms.locfileid: "50170167"
---
# <a name="how-to-initialize-an-array-variable-in-visual-basic"></a><span data-ttu-id="4057c-102">如何：在 Visual Basic 中初始化数组变量</span><span class="sxs-lookup"><span data-stu-id="4057c-102">How to: Initialize an Array Variable in Visual Basic</span></span>
<span data-ttu-id="4057c-103">通过包括数组文本中初始化数组变量`New`子句并指定数组的初始值。</span><span class="sxs-lookup"><span data-stu-id="4057c-103">You initialize an array variable by including an array literal in a `New` clause and specifying the initial values of the array.</span></span> <span data-ttu-id="4057c-104">你可以指定的类型，或允许其从数组文本中的值推断出来。</span><span class="sxs-lookup"><span data-stu-id="4057c-104">You can either specify the type or allow it to be inferred from the values in the array literal.</span></span> <span data-ttu-id="4057c-105">有关如何推断出的类型的详细信息，请参阅"填充数组初始值"中[数组](../../../../visual-basic/programming-guide/language-features/arrays/index.md)。</span><span class="sxs-lookup"><span data-stu-id="4057c-105">For more information about how the type is inferred, see "Populating an Array with Initial Values" in [Arrays](../../../../visual-basic/programming-guide/language-features/arrays/index.md).</span></span>  
  
### <a name="to-initialize-an-array-variable-by-using-an-array-literal"></a><span data-ttu-id="4057c-106">若要通过使用数组文本初始化数组变量</span><span class="sxs-lookup"><span data-stu-id="4057c-106">To initialize an array variable by using an array literal</span></span>  
  
-   <span data-ttu-id="4057c-107">在`New`子句，或分配的数组值时，提供在大括号内的元素值 (`{}`)。</span><span class="sxs-lookup"><span data-stu-id="4057c-107">Either in the `New` clause, or when you assign the array value, supply the element values inside braces (`{}`).</span></span> <span data-ttu-id="4057c-108">下面的示例演示如何声明、 创建和初始化一个变量来包含包含类型的元素的数组的几个`Char`。</span><span class="sxs-lookup"><span data-stu-id="4057c-108">The following example shows several ways to declare, create, and initialize a variable to contain an array that has elements of type `Char`.</span></span>  
  
     [!code-vb[VbVbalrArrays#16](../../../../visual-basic/programming-guide/language-features/arrays/codesnippet/VisualBasic/how-to-initialize-an-array-variable_1.vb)]  
  
     <span data-ttu-id="4057c-109">每个语句执行后，创建的数组长度为 3，在索引 0 到 2 包含初始值的元素。</span><span class="sxs-lookup"><span data-stu-id="4057c-109">After each statement executes, the array that's created has a length of 3, with elements at index 0 through index 2 containing the initial values.</span></span> <span data-ttu-id="4057c-110">如果你提供上限和值，则必须包含从 0 到上限的每个元素的值。</span><span class="sxs-lookup"><span data-stu-id="4057c-110">If you supply both the upper bound and the values, you must include a value for every element from index 0 through the upper bound.</span></span>  
  
     <span data-ttu-id="4057c-111">请注意，不需要指定索引上限，如果您提供了数组文本中的元素值。</span><span class="sxs-lookup"><span data-stu-id="4057c-111">Notice that you do not have to specify the index upper bound if you supply element values in an array literal.</span></span> <span data-ttu-id="4057c-112">如果指定没有上限，则根据数组文本中的值的数量推断数组的大小。</span><span class="sxs-lookup"><span data-stu-id="4057c-112">If no upper bound is specified, the size of the array is inferred based on the number of values in the array literal.</span></span>  
  
### <a name="to-initialize-a-multidimensional-array-variable-by-using-array-literals"></a><span data-ttu-id="4057c-113">若要使用数组文本初始化多维数组变量</span><span class="sxs-lookup"><span data-stu-id="4057c-113">To initialize a multidimensional array variable by using array literals</span></span>  
  
-   <span data-ttu-id="4057c-114">嵌套在括号内的值 (`{}`) 大括号内。</span><span class="sxs-lookup"><span data-stu-id="4057c-114">Nest values inside braces (`{}`) within braces.</span></span> <span data-ttu-id="4057c-115">请确保嵌套的数组文本全都推断为相同类型和长度的数组。</span><span class="sxs-lookup"><span data-stu-id="4057c-115">Ensure that the nested array literals all infer as arrays of the same type and length.</span></span> <span data-ttu-id="4057c-116">下面的代码示例显示了多维数组初始化的几个示例。</span><span class="sxs-lookup"><span data-stu-id="4057c-116">The following code example shows several examples of multidimensional array initialization.</span></span>  
  
     [!code-vb[VbVbalrArrays#17](../../../../visual-basic/programming-guide/language-features/arrays/codesnippet/VisualBasic/how-to-initialize-an-array-variable_2.vb)]  
  
-   <span data-ttu-id="4057c-117">可以显式指定数组界限或省略这些并让编译器推断数组界限的数组文本中的值。</span><span class="sxs-lookup"><span data-stu-id="4057c-117">You can explicitly specify the array bounds, or leave them out and have the compiler infer the array bounds based on the values in the array literal.</span></span> <span data-ttu-id="4057c-118">如果你提供上限和值，则必须在每个维度中包含从 0 到上限的每个元素的值。</span><span class="sxs-lookup"><span data-stu-id="4057c-118">If you supply both the upper bounds and the values, you must include a value for every element from index 0 through the upper bound in every dimension.</span></span> <span data-ttu-id="4057c-119">下面的示例演示几种方法声明、 创建和初始化一个变量来包含一个二维数组具有类型的元素。 `Short`</span><span class="sxs-lookup"><span data-stu-id="4057c-119">The following example shows several ways to declare, create, and initialize a variable to contain a two-dimensional array that has elements of type `Short`</span></span>  
  
     [!code-vb[VbVbalrArrays#18](../../../../visual-basic/programming-guide/language-features/arrays/codesnippet/VisualBasic/how-to-initialize-an-array-variable_3.vb)]  
  
     <span data-ttu-id="4057c-120">每个语句执行后，创建的数组包含六个初始化的元素的索引`(0,0)`， `(0,1)`， `(0,2)`， `(1,0)`， `(1,1)`，并`(1,2)`。</span><span class="sxs-lookup"><span data-stu-id="4057c-120">After each statement executes, the created array contains six initialized elements that have indexes `(0,0)`, `(0,1)`, `(0,2)`, `(1,0)`, `(1,1)`, and `(1,2)`.</span></span> <span data-ttu-id="4057c-121">每个数组位置都包含值`10`。</span><span class="sxs-lookup"><span data-stu-id="4057c-121">Each array location contains the value `10`.</span></span>  
  
-   <span data-ttu-id="4057c-122">下面的示例循环访问多维数组。</span><span class="sxs-lookup"><span data-stu-id="4057c-122">The following example iterates through a multidimensional array.</span></span> <span data-ttu-id="4057c-123">在用 Visual Basic 编写的 Windows 控制台应用程序，将粘贴的代码将在`Sub Main()`方法。</span><span class="sxs-lookup"><span data-stu-id="4057c-123">In a Windows console application that is written in Visual Basic, paste the code inside the `Sub Main()` method.</span></span> <span data-ttu-id="4057c-124">最后一个注释显示输出。</span><span class="sxs-lookup"><span data-stu-id="4057c-124">The last comments show the output.</span></span>  
  
     [!code-vb[VbVbalrArrays#31](../../../../visual-basic/programming-guide/language-features/arrays/codesnippet/VisualBasic/how-to-initialize-an-array-variable_4.vb)]  
  
### <a name="to-initialize-a-jagged-array-variable-by-using-array-literals"></a><span data-ttu-id="4057c-125">若要使用数组文本初始化交错的数组变量</span><span class="sxs-lookup"><span data-stu-id="4057c-125">To initialize a jagged array variable by using array literals</span></span>  
  
-   <span data-ttu-id="4057c-126">将大括号内的对象值嵌套 (`{}`)。</span><span class="sxs-lookup"><span data-stu-id="4057c-126">Nest object values inside braces (`{}`).</span></span> <span data-ttu-id="4057c-127">尽管您还可以嵌套指定不同长度，对于交错数组的数组的数组文本，但请确保嵌套的数组文本括在小括号 (`()`)。</span><span class="sxs-lookup"><span data-stu-id="4057c-127">Although you can also nest array literals that specify arrays of different lengths, in the case of a jagged array, make sure that the nested array literals are enclosed in parentheses (`()`).</span></span> <span data-ttu-id="4057c-128">括号强制先计算嵌套的数组文本，并生成数组将用作交错数组的初始值。</span><span class="sxs-lookup"><span data-stu-id="4057c-128">The parentheses force the evaluation of the nested array literals, and the resulting arrays are used as the initial values of the jagged array.</span></span> <span data-ttu-id="4057c-129">下面的代码示例演示了交错的数组初始化的两个示例。</span><span class="sxs-lookup"><span data-stu-id="4057c-129">The following code example shows two examples of jagged array initialization.</span></span>  
  
     [!code-vb[VbVbalrArrays#19](../../../../visual-basic/programming-guide/language-features/arrays/codesnippet/VisualBasic/how-to-initialize-an-array-variable_5.vb)]  
  
-   <span data-ttu-id="4057c-130">下面的示例循环访问交错数组。</span><span class="sxs-lookup"><span data-stu-id="4057c-130">The following example iterates through a jagged array.</span></span> <span data-ttu-id="4057c-131">在用 Visual Basic 编写的 Windows 控制台应用程序，将粘贴的代码将在`Sub Main()`方法。</span><span class="sxs-lookup"><span data-stu-id="4057c-131">In a Windows console application that is written in Visual Basic, paste the code inside the `Sub Main()` method.</span></span>  <span data-ttu-id="4057c-132">在代码中的最后一个注释显示输出。</span><span class="sxs-lookup"><span data-stu-id="4057c-132">The last comments in the code show the output.</span></span>  
  
     [!code-vb[VbVbalrArrays#32](../../../../visual-basic/programming-guide/language-features/arrays/codesnippet/VisualBasic/how-to-initialize-an-array-variable_6.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="4057c-133">请参阅</span><span class="sxs-lookup"><span data-stu-id="4057c-133">See Also</span></span>  
 [<span data-ttu-id="4057c-134">数组</span><span class="sxs-lookup"><span data-stu-id="4057c-134">Arrays</span></span>](../../../../visual-basic/programming-guide/language-features/arrays/index.md)  
 [<span data-ttu-id="4057c-135">数组疑难解答</span><span class="sxs-lookup"><span data-stu-id="4057c-135">Troubleshooting Arrays</span></span>](../../../../visual-basic/programming-guide/language-features/arrays/troubleshooting-arrays.md)
