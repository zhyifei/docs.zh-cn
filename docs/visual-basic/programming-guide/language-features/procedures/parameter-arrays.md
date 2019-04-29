---
title: 参数数组 (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- parameter arrays [Visual Basic], about parameter arrays
- ParamArray keyword [Visual Basic], parameter arrays
- Visual Basic code, procedures
- parameters [Visual Basic], parameter arrays
- arguments [Visual Basic], parameter arrays
- procedures [Visual Basic], indefinite number of argument values
- arrays [Visual Basic], parameter arrays
ms.assetid: c43edfae-9114-4096-9ebc-8c5c957a1067
ms.openlocfilehash: 8ea4c77056701b8f61c1ed5a53cf20d98ae913bc
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "61791945"
---
# <a name="parameter-arrays-visual-basic"></a><span data-ttu-id="2caab-102">参数数组 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="2caab-102">Parameter Arrays (Visual Basic)</span></span>
<span data-ttu-id="2caab-103">通常情况下，不能调用有更多参数不是过程声明指定的过程。</span><span class="sxs-lookup"><span data-stu-id="2caab-103">Usually, you cannot call a procedure with more arguments than the procedure declaration specifies.</span></span> <span data-ttu-id="2caab-104">当您需要的参数数量不确定时，可以声明*参数数组*，它允许过程接受一个参数的值的数组。</span><span class="sxs-lookup"><span data-stu-id="2caab-104">When you need an indefinite number of arguments, you can declare a *parameter array*, which allows a procedure to accept an array of values for a parameter.</span></span> <span data-ttu-id="2caab-105">无需知道何时定义过程的参数数组中的元素数。</span><span class="sxs-lookup"><span data-stu-id="2caab-105">You do not have to know the number of elements in the parameter array when you define the procedure.</span></span> <span data-ttu-id="2caab-106">数组大小由该过程每次调用单独确定。</span><span class="sxs-lookup"><span data-stu-id="2caab-106">The array size is determined individually by each call to the procedure.</span></span>  
  
## <a name="declaring-a-paramarray"></a><span data-ttu-id="2caab-107">声明一个参数数组</span><span class="sxs-lookup"><span data-stu-id="2caab-107">Declaring a ParamArray</span></span>  
 <span data-ttu-id="2caab-108">您使用[ParamArray](../../../../visual-basic/language-reference/modifiers/paramarray.md)关键字来表示的参数列表中的参数数组。</span><span class="sxs-lookup"><span data-stu-id="2caab-108">You use the [ParamArray](../../../../visual-basic/language-reference/modifiers/paramarray.md) keyword to denote a parameter array in the parameter list.</span></span> <span data-ttu-id="2caab-109">适用以下规则：</span><span class="sxs-lookup"><span data-stu-id="2caab-109">The following rules apply:</span></span>  
  
- <span data-ttu-id="2caab-110">一个过程可以定义只有一个参数数组，并且它必须在过程定义中的最后一个参数。</span><span class="sxs-lookup"><span data-stu-id="2caab-110">A procedure can define only one parameter array, and it must be the last parameter in the procedure definition.</span></span>  
  
- <span data-ttu-id="2caab-111">必须通过值传递参数数组。</span><span class="sxs-lookup"><span data-stu-id="2caab-111">The parameter array must be passed by value.</span></span> <span data-ttu-id="2caab-112">它是一个良好的编程做法中显式包括[ByVal](../../../../visual-basic/language-reference/modifiers/byval.md)过程定义中的关键字。</span><span class="sxs-lookup"><span data-stu-id="2caab-112">It is good programming practice to explicitly include the [ByVal](../../../../visual-basic/language-reference/modifiers/byval.md) keyword in the procedure definition.</span></span>  
  
- <span data-ttu-id="2caab-113">参数数组是自动可选的。</span><span class="sxs-lookup"><span data-stu-id="2caab-113">The parameter array is automatically optional.</span></span> <span data-ttu-id="2caab-114">其默认值为空的参数数组的元素类型的一维数组。</span><span class="sxs-lookup"><span data-stu-id="2caab-114">Its default value is an empty one-dimensional array of the parameter array's element type.</span></span>  
  
- <span data-ttu-id="2caab-115">前面的参数数组的所有参数都是必需的。</span><span class="sxs-lookup"><span data-stu-id="2caab-115">All parameters preceding the parameter array must be required.</span></span> <span data-ttu-id="2caab-116">参数数组必须是唯一的可选参数。</span><span class="sxs-lookup"><span data-stu-id="2caab-116">The parameter array must be the only optional parameter.</span></span>  
  
## <a name="calling-a-paramarray"></a><span data-ttu-id="2caab-117">调用参数数组</span><span class="sxs-lookup"><span data-stu-id="2caab-117">Calling a ParamArray</span></span>  
 <span data-ttu-id="2caab-118">时调用定义的参数数组的过程，可以通过以下方式之一提供参数：</span><span class="sxs-lookup"><span data-stu-id="2caab-118">When you call a procedure that defines a parameter array, you can supply the argument in any one of the following ways:</span></span>  
  
- <span data-ttu-id="2caab-119">执行任何操作-即，则可以省略[ParamArray](../../../../visual-basic/language-reference/modifiers/paramarray.md)参数。</span><span class="sxs-lookup"><span data-stu-id="2caab-119">Nothing — that is, you can omit the [ParamArray](../../../../visual-basic/language-reference/modifiers/paramarray.md) argument.</span></span> <span data-ttu-id="2caab-120">在这种情况下，将一个空数组传递给过程。</span><span class="sxs-lookup"><span data-stu-id="2caab-120">In this case, an empty array is passed to the procedure.</span></span> <span data-ttu-id="2caab-121">你还可以传递[Nothing](../../../../visual-basic/language-reference/nothing.md)关键字，使用相同的效果。</span><span class="sxs-lookup"><span data-stu-id="2caab-121">You can also pass the [Nothing](../../../../visual-basic/language-reference/nothing.md) keyword, with the same effect.</span></span>  
  
- <span data-ttu-id="2caab-122">任意数量的参数，由逗号分隔列表。</span><span class="sxs-lookup"><span data-stu-id="2caab-122">A list of an arbitrary number of arguments, separated by commas.</span></span> <span data-ttu-id="2caab-123">每个自变量的数据类型必须是隐式转换为`ParamArray`元素类型。</span><span class="sxs-lookup"><span data-stu-id="2caab-123">The data type of each argument must be implicitly convertible to the `ParamArray` element type.</span></span>  
  
- <span data-ttu-id="2caab-124">包含与参数数组的元素类型相同的元素类型的数组。</span><span class="sxs-lookup"><span data-stu-id="2caab-124">An array with the same element type as the parameter array's element type.</span></span>  
  
 <span data-ttu-id="2caab-125">在所有情况下，该过程中的代码将参数的数组视为与相同的数据类型的元素的一维数组`ParamArray`数据类型。</span><span class="sxs-lookup"><span data-stu-id="2caab-125">In all cases, the code within the procedure treats the parameter array as a one-dimensional array with elements of the same data type as the `ParamArray` data type.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="2caab-126">每当处理数组可以是无限期较大，则存在无限大的某种内部容量的应用程序的风险。</span><span class="sxs-lookup"><span data-stu-id="2caab-126">Whenever you deal with an array which can be indefinitely large, there is a risk of overrunning some internal capacity of your application.</span></span> <span data-ttu-id="2caab-127">如果接受一个参数数组时，你应测试调用代码传递给它的数组的大小。</span><span class="sxs-lookup"><span data-stu-id="2caab-127">If you accept a parameter array, you should test for the size of the array that the calling code passed to it.</span></span> <span data-ttu-id="2caab-128">如果你的应用程序太大，请采取适当的措施。</span><span class="sxs-lookup"><span data-stu-id="2caab-128">Take appropriate steps if it is too large for your application.</span></span> <span data-ttu-id="2caab-129">有关详细信息，请参阅[数组](../../../../visual-basic/programming-guide/language-features/arrays/index.md)。</span><span class="sxs-lookup"><span data-stu-id="2caab-129">For more information, see [Arrays](../../../../visual-basic/programming-guide/language-features/arrays/index.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="2caab-130">示例</span><span class="sxs-lookup"><span data-stu-id="2caab-130">Example</span></span>  
 <span data-ttu-id="2caab-131">下面的示例定义并调用该函数`calcSum`。</span><span class="sxs-lookup"><span data-stu-id="2caab-131">The following example defines and calls the function `calcSum`.</span></span> <span data-ttu-id="2caab-132">`ParamArray`的参数修饰符`args`使函数能够接受数目可变的参数。</span><span class="sxs-lookup"><span data-stu-id="2caab-132">The `ParamArray` modifier for the parameter `args` enables the function to accept a variable number of arguments.</span></span>  
  
 [!code-vb[VbVbalrStatements#26](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#26)]  
  
 <span data-ttu-id="2caab-133">下面的示例定义了一个使用参数数组，并输出传递给参数数组的所有数组元素的值。</span><span class="sxs-lookup"><span data-stu-id="2caab-133">The following example defines a procedure with a parameter array, and outputs the values of all the array elements passed to the parameter array.</span></span>  
  
 [!code-vb[VbVbcnProcedures#48](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#48)]  
  
 [!code-vb[VbVbcnProcedures#49](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#49)]  
  
## <a name="see-also"></a><span data-ttu-id="2caab-134">请参阅</span><span class="sxs-lookup"><span data-stu-id="2caab-134">See also</span></span>

- <xref:Microsoft.VisualBasic.Information.UBound%2A>
- [<span data-ttu-id="2caab-135">过程</span><span class="sxs-lookup"><span data-stu-id="2caab-135">Procedures</span></span>](./index.md)
- [<span data-ttu-id="2caab-136">过程参数和自变量</span><span class="sxs-lookup"><span data-stu-id="2caab-136">Procedure Parameters and Arguments</span></span>](./procedure-parameters-and-arguments.md)
- [<span data-ttu-id="2caab-137">按值和按引用传递自变量</span><span class="sxs-lookup"><span data-stu-id="2caab-137">Passing Arguments by Value and by Reference</span></span>](./passing-arguments-by-value-and-by-reference.md)
- [<span data-ttu-id="2caab-138">按位置和按名称传递自变量</span><span class="sxs-lookup"><span data-stu-id="2caab-138">Passing Arguments by Position and by Name</span></span>](./passing-arguments-by-position-and-by-name.md)
- [<span data-ttu-id="2caab-139">可选参数</span><span class="sxs-lookup"><span data-stu-id="2caab-139">Optional Parameters</span></span>](./optional-parameters.md)
- [<span data-ttu-id="2caab-140">过程重载</span><span class="sxs-lookup"><span data-stu-id="2caab-140">Procedure Overloading</span></span>](./procedure-overloading.md)
- [<span data-ttu-id="2caab-141">数组</span><span class="sxs-lookup"><span data-stu-id="2caab-141">Arrays</span></span>](../../../../visual-basic/programming-guide/language-features/arrays/index.md)
- [<span data-ttu-id="2caab-142">Optional</span><span class="sxs-lookup"><span data-stu-id="2caab-142">Optional</span></span>](../../../../visual-basic/language-reference/modifiers/optional.md)
