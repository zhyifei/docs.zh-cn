---
title: "参数数组 (Visual Basic)"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- parameter arrays [Visual Basic], about parameter arrays
- ParamArray keyword [Visual Basic], parameter arrays
- Visual Basic code, procedures
- parameters [Visual Basic], parameter arrays
- arguments [Visual Basic], parameter arrays
- procedures [Visual Basic], indefinite number of argument values
- arrays [Visual Basic], parameter arrays
ms.assetid: c43edfae-9114-4096-9ebc-8c5c957a1067
caps.latest.revision: "26"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 8ca2b5f02ac4fb3eb613488c8a9852eb2aa4ce5d
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="parameter-arrays-visual-basic"></a><span data-ttu-id="ffc2e-102">参数数组 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="ffc2e-102">Parameter Arrays (Visual Basic)</span></span>
<span data-ttu-id="ffc2e-103">通常情况下，不能调用带多个参数不是过程声明指定的过程。</span><span class="sxs-lookup"><span data-stu-id="ffc2e-103">Usually, you cannot call a procedure with more arguments than the procedure declaration specifies.</span></span> <span data-ttu-id="ffc2e-104">当你需要自变量数量不确定时，可以声明*参数数组*，这样一个过程来接受参数的值的数组。</span><span class="sxs-lookup"><span data-stu-id="ffc2e-104">When you need an indefinite number of arguments, you can declare a *parameter array*, which allows a procedure to accept an array of values for a parameter.</span></span> <span data-ttu-id="ffc2e-105">不需要知道的参数数组中的元素数，当你定义的过程。</span><span class="sxs-lookup"><span data-stu-id="ffc2e-105">You do not have to know the number of elements in the parameter array when you define the procedure.</span></span> <span data-ttu-id="ffc2e-106">数组大小由每个调用的过程单独确定。</span><span class="sxs-lookup"><span data-stu-id="ffc2e-106">The array size is determined individually by each call to the procedure.</span></span>  
  
## <a name="declaring-a-paramarray"></a><span data-ttu-id="ffc2e-107">声明一个参数数组</span><span class="sxs-lookup"><span data-stu-id="ffc2e-107">Declaring a ParamArray</span></span>  
 <span data-ttu-id="ffc2e-108">你使用[ParamArray](../../../../visual-basic/language-reference/modifiers/paramarray.md)关键字来表示参数列表中的参数数组。</span><span class="sxs-lookup"><span data-stu-id="ffc2e-108">You use the [ParamArray](../../../../visual-basic/language-reference/modifiers/paramarray.md) keyword to denote a parameter array in the parameter list.</span></span> <span data-ttu-id="ffc2e-109">适用以下规则：</span><span class="sxs-lookup"><span data-stu-id="ffc2e-109">The following rules apply:</span></span>  
  
-   <span data-ttu-id="ffc2e-110">一个过程只能定义只有一个参数数组，并且它必须在过程定义中的最后一个参数。</span><span class="sxs-lookup"><span data-stu-id="ffc2e-110">A procedure can define only one parameter array, and it must be the last parameter in the procedure definition.</span></span>  
  
-   <span data-ttu-id="ffc2e-111">必须通过值传递参数数组。</span><span class="sxs-lookup"><span data-stu-id="ffc2e-111">The parameter array must be passed by value.</span></span> <span data-ttu-id="ffc2e-112">是一个很好的编程做法显式包括[ByVal](../../../../visual-basic/language-reference/modifiers/byval.md)过程定义中的关键字。</span><span class="sxs-lookup"><span data-stu-id="ffc2e-112">It is good programming practice to explicitly include the [ByVal](../../../../visual-basic/language-reference/modifiers/byval.md) keyword in the procedure definition.</span></span>  
  
-   <span data-ttu-id="ffc2e-113">参数数组是自动可选的。</span><span class="sxs-lookup"><span data-stu-id="ffc2e-113">The parameter array is automatically optional.</span></span> <span data-ttu-id="ffc2e-114">其默认值为参数数组的元素类型的空一维数组。</span><span class="sxs-lookup"><span data-stu-id="ffc2e-114">Its default value is an empty one-dimensional array of the parameter array's element type.</span></span>  
  
-   <span data-ttu-id="ffc2e-115">前面参数数组的所有参数都是必需的。</span><span class="sxs-lookup"><span data-stu-id="ffc2e-115">All parameters preceding the parameter array must be required.</span></span> <span data-ttu-id="ffc2e-116">参数数组必须是唯一的可选参数。</span><span class="sxs-lookup"><span data-stu-id="ffc2e-116">The parameter array must be the only optional parameter.</span></span>  
  
## <a name="calling-a-paramarray"></a><span data-ttu-id="ffc2e-117">调用一个参数数组</span><span class="sxs-lookup"><span data-stu-id="ffc2e-117">Calling a ParamArray</span></span>  
 <span data-ttu-id="ffc2e-118">时调用过程定义参数数组时，你可以用任何一种通过以下方式来提供自变量：</span><span class="sxs-lookup"><span data-stu-id="ffc2e-118">When you call a procedure that defines a parameter array, you can supply the argument in any one of the following ways:</span></span>  
  
-   <span data-ttu-id="ffc2e-119">执行任何操作-即，则可以省略[ParamArray](../../../../visual-basic/language-reference/modifiers/paramarray.md)自变量。</span><span class="sxs-lookup"><span data-stu-id="ffc2e-119">Nothing — that is, you can omit the [ParamArray](../../../../visual-basic/language-reference/modifiers/paramarray.md) argument.</span></span> <span data-ttu-id="ffc2e-120">在这种情况下，将为空数组传递给过程。</span><span class="sxs-lookup"><span data-stu-id="ffc2e-120">In this case, an empty array is passed to the procedure.</span></span> <span data-ttu-id="ffc2e-121">你还可以传递[执行任何操作](../../../../visual-basic/language-reference/nothing.md)关键字，使用相同的效果。</span><span class="sxs-lookup"><span data-stu-id="ffc2e-121">You can also pass the [Nothing](../../../../visual-basic/language-reference/nothing.md) keyword, with the same effect.</span></span>  
  
-   <span data-ttu-id="ffc2e-122">任意数目的自变量，用逗号分隔列表。</span><span class="sxs-lookup"><span data-stu-id="ffc2e-122">A list of an arbitrary number of arguments, separated by commas.</span></span> <span data-ttu-id="ffc2e-123">每个自变量的数据类型必须是隐式转换为`ParamArray`元素类型。</span><span class="sxs-lookup"><span data-stu-id="ffc2e-123">The data type of each argument must be implicitly convertible to the `ParamArray` element type.</span></span>  
  
-   <span data-ttu-id="ffc2e-124">具有相同的元素类型为参数数组的元素类型数组。</span><span class="sxs-lookup"><span data-stu-id="ffc2e-124">An array with the same element type as the parameter array's element type.</span></span>  
  
 <span data-ttu-id="ffc2e-125">在所有情况下，在过程中的代码将参数的数组包含与相同的数据类型的元素的一维数组视为`ParamArray`数据类型。</span><span class="sxs-lookup"><span data-stu-id="ffc2e-125">In all cases, the code within the procedure treats the parameter array as a one-dimensional array with elements of the same data type as the `ParamArray` data type.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="ffc2e-126">每当你处理数组可以是无限期地大型，没有无限大某种内部容量的你的应用程序的风险。</span><span class="sxs-lookup"><span data-stu-id="ffc2e-126">Whenever you deal with an array which can be indefinitely large, there is a risk of overrunning some internal capacity of your application.</span></span> <span data-ttu-id="ffc2e-127">如果你接受一个参数数组，你应进行测试以调用代码传递给它的数组的大小。</span><span class="sxs-lookup"><span data-stu-id="ffc2e-127">If you accept a parameter array, you should test for the size of the array that the calling code passed to it.</span></span> <span data-ttu-id="ffc2e-128">如果你的应用程序太大，请采取适当的措施。</span><span class="sxs-lookup"><span data-stu-id="ffc2e-128">Take appropriate steps if it is too large for your application.</span></span> <span data-ttu-id="ffc2e-129">有关详细信息，请参阅[数组](../../../../visual-basic/programming-guide/language-features/arrays/index.md)。</span><span class="sxs-lookup"><span data-stu-id="ffc2e-129">For more information, see [Arrays](../../../../visual-basic/programming-guide/language-features/arrays/index.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="ffc2e-130">示例</span><span class="sxs-lookup"><span data-stu-id="ffc2e-130">Example</span></span>  
 <span data-ttu-id="ffc2e-131">下面的示例定义和调用函数`calcSum`。</span><span class="sxs-lookup"><span data-stu-id="ffc2e-131">The following example defines and calls the function `calcSum`.</span></span> <span data-ttu-id="ffc2e-132">`ParamArray`参数修饰符`args`启用接受数目可变的参数的函数。</span><span class="sxs-lookup"><span data-stu-id="ffc2e-132">The `ParamArray` modifier for the parameter `args` enables the function to accept a variable number of arguments.</span></span>  
  
 [!code-vb[VbVbalrStatements#26](../../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/parameter-arrays_1.vb)]  
  
 <span data-ttu-id="ffc2e-133">下面的示例定义了一个带有参数数组，并将输出传递给参数数组的所有数组元素的值。</span><span class="sxs-lookup"><span data-stu-id="ffc2e-133">The following example defines a procedure with a parameter array, and outputs the values of all the array elements passed to the parameter array.</span></span>  
  
 [!code-vb[VbVbcnProcedures#48](./codesnippet/VisualBasic/parameter-arrays_2.vb)]  
  
 [!code-vb[VbVbcnProcedures#49](./codesnippet/VisualBasic/parameter-arrays_3.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="ffc2e-134">另请参阅</span><span class="sxs-lookup"><span data-stu-id="ffc2e-134">See Also</span></span>  
 <xref:Microsoft.VisualBasic.Information.UBound%2A>  
 [<span data-ttu-id="ffc2e-135">过程</span><span class="sxs-lookup"><span data-stu-id="ffc2e-135">Procedures</span></span>](./index.md)  
 [<span data-ttu-id="ffc2e-136">过程参数和自变量</span><span class="sxs-lookup"><span data-stu-id="ffc2e-136">Procedure Parameters and Arguments</span></span>](./procedure-parameters-and-arguments.md)  
 [<span data-ttu-id="ffc2e-137">按值和按引用传递自变量</span><span class="sxs-lookup"><span data-stu-id="ffc2e-137">Passing Arguments by Value and by Reference</span></span>](./passing-arguments-by-value-and-by-reference.md)  
 [<span data-ttu-id="ffc2e-138">按位置和按名称传递自变量</span><span class="sxs-lookup"><span data-stu-id="ffc2e-138">Passing Arguments by Position and by Name</span></span>](./passing-arguments-by-position-and-by-name.md)  
 [<span data-ttu-id="ffc2e-139">可选参数</span><span class="sxs-lookup"><span data-stu-id="ffc2e-139">Optional Parameters</span></span>](./optional-parameters.md)  
 [<span data-ttu-id="ffc2e-140">过程重载</span><span class="sxs-lookup"><span data-stu-id="ffc2e-140">Procedure Overloading</span></span>](./procedure-overloading.md)  
 [<span data-ttu-id="ffc2e-141">阵列</span><span class="sxs-lookup"><span data-stu-id="ffc2e-141">Arrays</span></span>](../../../../visual-basic/programming-guide/language-features/arrays/index.md)  
 [<span data-ttu-id="ffc2e-142">Optional</span><span class="sxs-lookup"><span data-stu-id="ffc2e-142">Optional</span></span>](../../../../visual-basic/language-reference/modifiers/optional.md)
