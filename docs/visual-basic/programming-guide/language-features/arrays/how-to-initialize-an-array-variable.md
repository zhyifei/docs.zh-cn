---
title: "如何：在 Visual Basic 中初始化数组变量"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- variables [Visual Basic], initializing
- arrays [Visual Basic], variables
- arrays [Visual Basic], initializing
- arrays [Visual Basic], declaring
ms.assetid: aadd7a60-7ca4-4608-b986-091f19e7fc10
caps.latest.revision: "42"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 3ccdbed601d3fa87acb0833bc153c199b17a4eba
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-initialize-an-array-variable-in-visual-basic"></a><span data-ttu-id="89533-102">如何：在 Visual Basic 中初始化数组变量</span><span class="sxs-lookup"><span data-stu-id="89533-102">How to: Initialize an Array Variable in Visual Basic</span></span>
<span data-ttu-id="89533-103">可以通过包括数组文本中初始化数组变量`New`子句和指定数组的初始值。</span><span class="sxs-lookup"><span data-stu-id="89533-103">You initialize an array variable by including an array literal in a `New` clause and specifying the initial values of the array.</span></span> <span data-ttu-id="89533-104">你可以指定的类型，或允许其被推断从数组文本中的值。</span><span class="sxs-lookup"><span data-stu-id="89533-104">You can either specify the type or allow it to be inferred from the values in the array literal.</span></span> <span data-ttu-id="89533-105">有关如何推断出的类型的详细信息，请参见"填充数组与初始值"[数组](../../../../visual-basic/programming-guide/language-features/arrays/index.md)。</span><span class="sxs-lookup"><span data-stu-id="89533-105">For more information about how the type is inferred, see "Populating an Array with Initial Values" in [Arrays](../../../../visual-basic/programming-guide/language-features/arrays/index.md).</span></span>  
  
### <a name="to-initialize-an-array-variable-by-using-an-array-literal"></a><span data-ttu-id="89533-106">若要通过使用数组文本中初始化数组变量</span><span class="sxs-lookup"><span data-stu-id="89533-106">To initialize an array variable by using an array literal</span></span>  
  
-   <span data-ttu-id="89533-107">在`New`子句，或当分配的数组值时，提供在括号内的元素值 (`{}`)。</span><span class="sxs-lookup"><span data-stu-id="89533-107">Either in the `New` clause, or when you assign the array value, supply the element values inside braces (`{}`).</span></span> <span data-ttu-id="89533-108">下面的示例演示通过多种方式来声明、 创建和初始化一个变量来包含具有类型的元素的数组的`Char`。</span><span class="sxs-lookup"><span data-stu-id="89533-108">The following example shows several ways to declare, create, and initialize a variable to contain an array that has elements of type `Char`.</span></span>  
  
     [!code-vb[VbVbalrArrays#16](../../../../visual-basic/programming-guide/language-features/arrays/codesnippet/VisualBasic/how-to-initialize-an-array-variable_1.vb)]  
  
     <span data-ttu-id="89533-109">每个语句执行后，数组创建有长度为 3，与通过索引包含初始值的 2 的索引 0 处的元素。</span><span class="sxs-lookup"><span data-stu-id="89533-109">After each statement executes, the array that's created has a length of 3, with elements at index 0 through index 2 containing the initial values.</span></span> <span data-ttu-id="89533-110">如果你提供的上限和值，则必须包含从 0 到上限的每个元素的值。</span><span class="sxs-lookup"><span data-stu-id="89533-110">If you supply both the upper bound and the values, you must include a value for every element from index 0 through the upper bound.</span></span>  
  
     <span data-ttu-id="89533-111">请注意你无需指定索引上限，如果你提供数组文本中的元素值。</span><span class="sxs-lookup"><span data-stu-id="89533-111">Notice that you do not have to specify the index upper bound if you supply element values in an array literal.</span></span> <span data-ttu-id="89533-112">如果指定没有上限，则数组的大小是基于推断出的数组文本中的值的数目。</span><span class="sxs-lookup"><span data-stu-id="89533-112">If no upper bound is specified, the size of the array is inferred based on the number of values in the array literal.</span></span>  
  
### <a name="to-initialize-a-multidimensional-array-variable-by-using-array-literals"></a><span data-ttu-id="89533-113">若要通过使用数组文本初始化多维数组变量</span><span class="sxs-lookup"><span data-stu-id="89533-113">To initialize a multidimensional array variable by using array literals</span></span>  
  
-   <span data-ttu-id="89533-114">嵌套在括号内的值 (`{}`) 在大括号内。</span><span class="sxs-lookup"><span data-stu-id="89533-114">Nest values inside braces (`{}`) within braces.</span></span> <span data-ttu-id="89533-115">请确保所有推断为相同类型和长度的数组的嵌套的数组文本。</span><span class="sxs-lookup"><span data-stu-id="89533-115">Ensure that the nested array literals all infer as arrays of the same type and length.</span></span> <span data-ttu-id="89533-116">下面的代码示例显示几个示例的多维数组初始化。</span><span class="sxs-lookup"><span data-stu-id="89533-116">The following code example shows several examples of multidimensional array initialization.</span></span>  
  
     [!code-vb[VbVbalrArrays#17](../../../../visual-basic/programming-guide/language-features/arrays/codesnippet/VisualBasic/how-to-initialize-an-array-variable_2.vb)]  
  
-   <span data-ttu-id="89533-117">你可以显式指定数组界限，或省略它们并让编译器推断基于文本数组中的值的数组边界。</span><span class="sxs-lookup"><span data-stu-id="89533-117">You can explicitly specify the array bounds, or leave them out and have the compiler infer the array bounds based on the values in the array literal.</span></span> <span data-ttu-id="89533-118">如果你提供了上限和值，则必须每个维度中包含从 0 到上限的每个元素的值。</span><span class="sxs-lookup"><span data-stu-id="89533-118">If you supply both the upper bounds and the values, you must include a value for every element from index 0 through the upper bound in every dimension.</span></span> <span data-ttu-id="89533-119">下面的示例演示通过多种方式来声明、 创建和初始化一个变量来包含一个具有类型的元素的二维数组`Short`</span><span class="sxs-lookup"><span data-stu-id="89533-119">The following example shows several ways to declare, create, and initialize a variable to contain a two-dimensional array that has elements of type `Short`</span></span>  
  
     [!code-vb[VbVbalrArrays#18](../../../../visual-basic/programming-guide/language-features/arrays/codesnippet/VisualBasic/how-to-initialize-an-array-variable_3.vb)]  
  
     <span data-ttu-id="89533-120">每个语句执行后，创建的数组包含有索引的六个初始化的元素`(0,0)`， `(0,1)`， `(0,2)`， `(1,0)`， `(1,1)`，和`(1,2)`。</span><span class="sxs-lookup"><span data-stu-id="89533-120">After each statement executes, the created array contains six initialized elements that have indexes `(0,0)`, `(0,1)`, `(0,2)`, `(1,0)`, `(1,1)`, and `(1,2)`.</span></span> <span data-ttu-id="89533-121">每个数组位置包含的值`10`。</span><span class="sxs-lookup"><span data-stu-id="89533-121">Each array location contains the value `10`.</span></span>  
  
-   <span data-ttu-id="89533-122">下面的示例循环访问一个多维数组。</span><span class="sxs-lookup"><span data-stu-id="89533-122">The following example iterates through a multidimensional array.</span></span> <span data-ttu-id="89533-123">在 Windows 控制台应用程序在 Visual Basic 中编写的将粘贴内的代码`Sub Main()`方法。</span><span class="sxs-lookup"><span data-stu-id="89533-123">In a Windows console application that is written in Visual Basic, paste the code inside the `Sub Main()` method.</span></span> <span data-ttu-id="89533-124">最后一个注释显示输出。</span><span class="sxs-lookup"><span data-stu-id="89533-124">The last comments show the output.</span></span>  
  
     [!code-vb[VbVbalrArrays#31](../../../../visual-basic/programming-guide/language-features/arrays/codesnippet/VisualBasic/how-to-initialize-an-array-variable_4.vb)]  
  
### <a name="to-initialize-a-jagged-array-variable-by-using-array-literals"></a><span data-ttu-id="89533-125">若要通过使用数组文本初始化交错的数组变量</span><span class="sxs-lookup"><span data-stu-id="89533-125">To initialize a jagged array variable by using array literals</span></span>  
  
-   <span data-ttu-id="89533-126">嵌套在括号内的对象值 (`{}`)。</span><span class="sxs-lookup"><span data-stu-id="89533-126">Nest object values inside braces (`{}`).</span></span> <span data-ttu-id="89533-127">虽然你还可以嵌套数组文本指定数组的不同长度，对于交错数组，请确保嵌套的数组文本括在括号中 (`()`)。</span><span class="sxs-lookup"><span data-stu-id="89533-127">Although you can also nest array literals that specify arrays of different lengths, in the case of a jagged array, make sure that that the nested array literals are enclosed in parentheses (`()`).</span></span> <span data-ttu-id="89533-128">括号强制的嵌套的数组文本中，计算，生成的数组可用作交错数组的初始值。</span><span class="sxs-lookup"><span data-stu-id="89533-128">The parentheses force the evaluation of the nested array literals, and the resulting arrays are used as the initial values of the jagged array.</span></span> <span data-ttu-id="89533-129">下面的代码示例显示交错的数组初始化的两个示例。</span><span class="sxs-lookup"><span data-stu-id="89533-129">The following code example shows two examples of jagged array initialization.</span></span>  
  
     [!code-vb[VbVbalrArrays#19](../../../../visual-basic/programming-guide/language-features/arrays/codesnippet/VisualBasic/how-to-initialize-an-array-variable_5.vb)]  
  
-   <span data-ttu-id="89533-130">下面的示例循环访问一个交错数组。</span><span class="sxs-lookup"><span data-stu-id="89533-130">The following example iterates through a jagged array.</span></span> <span data-ttu-id="89533-131">在 Windows 控制台应用程序在 Visual Basic 中编写的将粘贴内的代码`Sub Main()`方法。</span><span class="sxs-lookup"><span data-stu-id="89533-131">In a Windows console application that is written in Visual Basic, paste the code inside the `Sub Main()` method.</span></span>  <span data-ttu-id="89533-132">在代码中的最后一个注释显示输出。</span><span class="sxs-lookup"><span data-stu-id="89533-132">The last comments in the code show the output.</span></span>  
  
     [!code-vb[VbVbalrArrays#32](../../../../visual-basic/programming-guide/language-features/arrays/codesnippet/VisualBasic/how-to-initialize-an-array-variable_6.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="89533-133">另请参阅</span><span class="sxs-lookup"><span data-stu-id="89533-133">See Also</span></span>  
 [<span data-ttu-id="89533-134">阵列</span><span class="sxs-lookup"><span data-stu-id="89533-134">Arrays</span></span>](../../../../visual-basic/programming-guide/language-features/arrays/index.md)  
 [<span data-ttu-id="89533-135">数组疑难解答</span><span class="sxs-lookup"><span data-stu-id="89533-135">Troubleshooting Arrays</span></span>](../../../../visual-basic/programming-guide/language-features/arrays/troubleshooting-arrays.md)
