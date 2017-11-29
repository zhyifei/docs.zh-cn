---
title: "重载过程注意事项 (Visual Basic)"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- signatures [Visual Basic], ParamArray arguments
- ParamArray keyword [Visual Basic], parameter arrays
- ParamArray keyword [Visual Basic], arguments and signatures
- function overloading [Visual Basic], implicit overloads for ParamArray
- ParamArray keyword [Visual Basic], signatures
- Visual Basic code, procedures
- arguments [Visual Basic], parameter arrays
- procedures [Visual Basic], overloading
- parameters [Visual Basic], lists
- function overloading [Visual Basic], typeless programming
- typeless programming
- function overloading [Visual Basic], restrictions
- arguments [Visual Basic], optional
- optional arguments [Visual Basic], overloading
- signatures [Visual Basic], procedure
- parameter lists [Visual Basic]
- parameter arrays [Visual Basic], overloading arguments
- Visual Basic code, parameter lists
- procedure overloading [Visual Basic], considerations
- Option Explicit statement [Visual Basic]
- restrictions [Visual Basic], overloading procedures
- procedures [Visual Basic], parameter lists
ms.assetid: a2001248-10d0-42c5-b0ce-eeedc987319f
caps.latest.revision: "26"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 3c9a9a4759d4ec2dd87778c49c4fd82a08c081a8
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="considerations-in-overloading-procedures-visual-basic"></a><span data-ttu-id="f6110-102">重载过程注意事项 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="f6110-102">Considerations in Overloading Procedures (Visual Basic)</span></span>
<span data-ttu-id="f6110-103">重载过程，你必须使用不同*签名*为每个重载版本。</span><span class="sxs-lookup"><span data-stu-id="f6110-103">When you overload a procedure, you must use a different *signature* for each overloaded version.</span></span> <span data-ttu-id="f6110-104">这通常意味着每个版本，必须指定不同的参数列表。</span><span class="sxs-lookup"><span data-stu-id="f6110-104">This usually means each version must specify a different parameter list.</span></span> <span data-ttu-id="f6110-105">有关详细信息，请参阅"不同的签名"[过程重载](./procedure-overloading.md)。</span><span class="sxs-lookup"><span data-stu-id="f6110-105">For more information, see "Different Signature" in [Procedure Overloading](./procedure-overloading.md).</span></span>  
  
 <span data-ttu-id="f6110-106">您可以重载`Function`具有过程`Sub`过程中，和反之亦然，只要它们具有不同签名。</span><span class="sxs-lookup"><span data-stu-id="f6110-106">You can overload a `Function` procedure with a `Sub` procedure, and vice versa, provided they have different signatures.</span></span> <span data-ttu-id="f6110-107">仅在于其中一个的返回值，另一个不，不能区分两个重载。</span><span class="sxs-lookup"><span data-stu-id="f6110-107">Two overloads cannot differ only in that one has a return value and the other does not.</span></span>  
  
 <span data-ttu-id="f6110-108">您可以重载属性相同的方式重载过程，并采用相同的限制。</span><span class="sxs-lookup"><span data-stu-id="f6110-108">You can overload a property the same way you overload a procedure, and with the same restrictions.</span></span> <span data-ttu-id="f6110-109">但是，不能重载过程具有属性，反之亦然。</span><span class="sxs-lookup"><span data-stu-id="f6110-109">However, you cannot overload a procedure with a property, or vice versa.</span></span>  
  
## <a name="alternatives-to-overloaded-versions"></a><span data-ttu-id="f6110-110">重载版本的替代方法</span><span class="sxs-lookup"><span data-stu-id="f6110-110">Alternatives to Overloaded Versions</span></span>  
 <span data-ttu-id="f6110-111">特别是可选的自变量存在或其数量是变量时，有时需要重载版本的替代方法。</span><span class="sxs-lookup"><span data-stu-id="f6110-111">You sometimes have alternatives to overloaded versions, particularly when the presence of arguments is optional or their number is variable.</span></span>  
  
 <span data-ttu-id="f6110-112">请记住，可选自变量不一定支持的所有语言，以及参数数组仅限于[!INCLUDE[vbprvb](~/includes/vbprvb-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="f6110-112">Keep in mind that optional arguments are not necessarily supported by all languages, and parameter arrays are limited to [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)].</span></span> <span data-ttu-id="f6110-113">如果你正在编写一个可从任何几种语言编写的代码调用的过程，那么重载版本提供最大的灵活性。</span><span class="sxs-lookup"><span data-stu-id="f6110-113">If you are writing a procedure that is likely to be called from code written in any of several different languages, overloaded versions offer the greatest flexibility.</span></span>  
  
### <a name="overloads-and-optional-arguments"></a><span data-ttu-id="f6110-114">重载和可选自变量</span><span class="sxs-lookup"><span data-stu-id="f6110-114">Overloads and Optional Arguments</span></span>  
 <span data-ttu-id="f6110-115">当调用的代码 （可选） 可以提供，或者忽略一个或多个自变量时，可以定义多个重载的版本，或使用可选参数。</span><span class="sxs-lookup"><span data-stu-id="f6110-115">When the calling code can optionally supply or omit one or more arguments, you can define multiple overloaded versions or use optional parameters.</span></span>  
  
#### <a name="when-to-use-overloaded-versions"></a><span data-ttu-id="f6110-116">何时使用重载的版本</span><span class="sxs-lookup"><span data-stu-id="f6110-116">When to Use Overloaded Versions</span></span>  
 <span data-ttu-id="f6110-117">你可以考虑在以下情况下定义一系列的重载版本：</span><span class="sxs-lookup"><span data-stu-id="f6110-117">You can consider defining a series of overloaded versions in the following cases:</span></span>  
  
-   <span data-ttu-id="f6110-118">在过程代码中的逻辑是具体取决于调用代码是否提供可选的参数，或不明显不同。</span><span class="sxs-lookup"><span data-stu-id="f6110-118">The logic in the procedure code is significantly different depending on whether the calling code supplies an optional argument or not.</span></span>  
  
-   <span data-ttu-id="f6110-119">过程代码不能可靠地测试是否调用的代码已提供可选的参数。</span><span class="sxs-lookup"><span data-stu-id="f6110-119">The procedure code cannot reliably test whether the calling code has supplied an optional argument.</span></span> <span data-ttu-id="f6110-120">这是这种情况，例如，如果没有可能的候选对于默认值，调用代码可能不需要提供。</span><span class="sxs-lookup"><span data-stu-id="f6110-120">This is the case, for example, if there is no possible candidate for a default value that the calling code could not be expected to supply.</span></span>  
  
#### <a name="when-to-use-optional-parameters"></a><span data-ttu-id="f6110-121">何时使用可选参数</span><span class="sxs-lookup"><span data-stu-id="f6110-121">When to Use Optional Parameters</span></span>  
 <span data-ttu-id="f6110-122">你可能希望在以下情况下的一个或多个可选参数：</span><span class="sxs-lookup"><span data-stu-id="f6110-122">You might prefer one or more optional parameters in the following cases:</span></span>  
  
-   <span data-ttu-id="f6110-123">唯一的必需的操作时调用的代码不会提供可选的参数是将参数设置为默认值。</span><span class="sxs-lookup"><span data-stu-id="f6110-123">The only required action when the calling code does not supply an optional argument is to set the parameter to a default value.</span></span> <span data-ttu-id="f6110-124">在这种情况下，该过程代码可能会不太复杂如果定义单个版本与一个或多`Optional`参数。</span><span class="sxs-lookup"><span data-stu-id="f6110-124">In such a case, the procedure code can be less complicated if you define a single version with one or more `Optional` parameters.</span></span>  
  
 <span data-ttu-id="f6110-125">有关详细信息，请参阅[可选参数](./optional-parameters.md)。</span><span class="sxs-lookup"><span data-stu-id="f6110-125">For more information, see [Optional Parameters](./optional-parameters.md).</span></span>  
  
### <a name="overloads-and-paramarrays"></a><span data-ttu-id="f6110-126">重载和参数</span><span class="sxs-lookup"><span data-stu-id="f6110-126">Overloads and ParamArrays</span></span>  
 <span data-ttu-id="f6110-127">如果调用代码可以通过数目可变的参数，可以定义多个重载的版本，或使用参数数组。</span><span class="sxs-lookup"><span data-stu-id="f6110-127">When the calling code can pass a variable number of arguments, you can define multiple overloaded versions or use a parameter array.</span></span>  
  
#### <a name="when-to-use-overloaded-versions"></a><span data-ttu-id="f6110-128">何时使用重载的版本</span><span class="sxs-lookup"><span data-stu-id="f6110-128">When to Use Overloaded Versions</span></span>  
 <span data-ttu-id="f6110-129">你可以考虑在以下情况下定义一系列的重载版本：</span><span class="sxs-lookup"><span data-stu-id="f6110-129">You can consider defining a series of overloaded versions in the following cases:</span></span>  
  
-   <span data-ttu-id="f6110-130">你知道，调用代码永远不会将传递多个值一小部分给参数数组。</span><span class="sxs-lookup"><span data-stu-id="f6110-130">You know that the calling code never passes more than a small number of values to the parameter array.</span></span>  
  
-   <span data-ttu-id="f6110-131">在过程代码中的逻辑是明显不同，具体取决于在调用代码传递多少个值。</span><span class="sxs-lookup"><span data-stu-id="f6110-131">The logic in the procedure code is significantly different depending on how many values the calling code passes.</span></span>  
  
-   <span data-ttu-id="f6110-132">调用代码可以将不同数据类型的值传递。</span><span class="sxs-lookup"><span data-stu-id="f6110-132">The calling code can pass values of different data types.</span></span>  
  
#### <a name="when-to-use-a-parameter-array"></a><span data-ttu-id="f6110-133">何时使用参数数组</span><span class="sxs-lookup"><span data-stu-id="f6110-133">When to Use a Parameter Array</span></span>  
 <span data-ttu-id="f6110-134">更好地由`ParamArray`参数在以下情况：</span><span class="sxs-lookup"><span data-stu-id="f6110-134">You are better served by a `ParamArray` parameter in the following cases:</span></span>  
  
-   <span data-ttu-id="f6110-135">你不能预测多少个值调用代码可以将传递给参数数组中，并且它可能有大量。</span><span class="sxs-lookup"><span data-stu-id="f6110-135">You are not able to predict how many values the calling code can pass to the parameter array, and it could be a large number.</span></span>  
  
-   <span data-ttu-id="f6110-136">过程逻辑适于本身进行循环访问所有通过调用代码，执行对每个值实质上是相同的操作的值。</span><span class="sxs-lookup"><span data-stu-id="f6110-136">The procedure logic lends itself to iterating through all the values the calling code passes, performing essentially the same operations on every value.</span></span>  
  
 <span data-ttu-id="f6110-137">有关详细信息，请参阅[参数数组](./parameter-arrays.md)。</span><span class="sxs-lookup"><span data-stu-id="f6110-137">For more information, see [Parameter Arrays](./parameter-arrays.md).</span></span>  
  
## <a name="implicit-overloads-for-optional-parameters"></a><span data-ttu-id="f6110-138">可选参数的的隐式重载</span><span class="sxs-lookup"><span data-stu-id="f6110-138">Implicit Overloads for Optional Parameters</span></span>  
 <span data-ttu-id="f6110-139">使用为过程[可选](../../../../visual-basic/language-reference/modifiers/optional.md)参数相当于两个重载过程，一个使用可选参数，而无需它的一个。</span><span class="sxs-lookup"><span data-stu-id="f6110-139">A procedure with an [Optional](../../../../visual-basic/language-reference/modifiers/optional.md) parameter is equivalent to two overloaded procedures, one with the optional parameter and one without it.</span></span> <span data-ttu-id="f6110-140">无法使用对应其中任一参数列表来重载这样的过程。</span><span class="sxs-lookup"><span data-stu-id="f6110-140">You cannot overload such a procedure with a parameter list corresponding to either of these.</span></span> <span data-ttu-id="f6110-141">以下声明说明这一点。</span><span class="sxs-lookup"><span data-stu-id="f6110-141">The following declarations illustrate this.</span></span>  
  
 [!code-vb[VbVbcnProcedures#58](./codesnippet/VisualBasic/considerations-in-overloading-procedures_1.vb)]  
  
 [!code-vb[VbVbcnProcedures#60](./codesnippet/VisualBasic/considerations-in-overloading-procedures_2.vb)]  
  
 [!code-vb[VbVbcnProcedures#61](./codesnippet/VisualBasic/considerations-in-overloading-procedures_3.vb)]  
  
 <span data-ttu-id="f6110-142">对于带多个可选参数的过程，没有隐式重载，到达由前面的示例中的相似逻辑的一组。</span><span class="sxs-lookup"><span data-stu-id="f6110-142">For a procedure with more than one optional parameter, there is a set of implicit overloads, arrived at by logic similar to that in the preceding example.</span></span>  
  
## <a name="implicit-overloads-for-a-paramarray-parameter"></a><span data-ttu-id="f6110-143">隐式重载 ParamArray 参数</span><span class="sxs-lookup"><span data-stu-id="f6110-143">Implicit Overloads for a ParamArray Parameter</span></span>  
 <span data-ttu-id="f6110-144">编译器将使用的过程视为[ParamArray](../../../../visual-basic/language-reference/modifiers/paramarray.md)参数具有无限数目的重载，不同于彼此中什么调用代码将传递给参数数组，如下所示：</span><span class="sxs-lookup"><span data-stu-id="f6110-144">The compiler considers a procedure with a [ParamArray](../../../../visual-basic/language-reference/modifiers/paramarray.md) parameter to have an infinite number of overloads, differing from each other in what the calling code passes to the parameter array, as follows:</span></span>  
  
-   <span data-ttu-id="f6110-145">当调用的代码不会提供的自变量的一个重载`ParamArray`</span><span class="sxs-lookup"><span data-stu-id="f6110-145">One overload for when the calling code does not supply an argument to the `ParamArray`</span></span>  
  
-   <span data-ttu-id="f6110-146">当调用的代码提供的一维数组的一个重载`ParamArray`元素类型</span><span class="sxs-lookup"><span data-stu-id="f6110-146">One overload for when the calling code supplies a one-dimensional array of the `ParamArray` element type</span></span>  
  
-   <span data-ttu-id="f6110-147">对于每个正整数，一个重载的调用的代码提供该数量的参数，每个时`ParamArray`元素类型</span><span class="sxs-lookup"><span data-stu-id="f6110-147">For every positive integer, one overload for when the calling code supplies that number of arguments, each of the `ParamArray` element type</span></span>  
  
 <span data-ttu-id="f6110-148">以下声明说明了这些隐式重载。</span><span class="sxs-lookup"><span data-stu-id="f6110-148">The following declarations illustrate these implicit overloads.</span></span>  
  
 [!code-vb[VbVbcnProcedures#68](./codesnippet/VisualBasic/considerations-in-overloading-procedures_4.vb)]  
  
 [!code-vb[VbVbcnProcedures#70](./codesnippet/VisualBasic/considerations-in-overloading-procedures_5.vb)]  
  
 <span data-ttu-id="f6110-149">无法重载采用一维数组的参数数组的参数列表的此类的过程。</span><span class="sxs-lookup"><span data-stu-id="f6110-149">You cannot overload such a procedure with a parameter list that takes a one-dimensional array for the parameter array.</span></span> <span data-ttu-id="f6110-150">但是，你可以使用其他隐式重载的签名。</span><span class="sxs-lookup"><span data-stu-id="f6110-150">However, you can use the signatures of the other implicit overloads.</span></span> <span data-ttu-id="f6110-151">以下声明说明这一点。</span><span class="sxs-lookup"><span data-stu-id="f6110-151">The following declarations illustrate this.</span></span>  
  
 [!code-vb[VbVbcnProcedures#71](./codesnippet/VisualBasic/considerations-in-overloading-procedures_6.vb)]  
  
## <a name="typeless-programming-as-an-alternative-to-overloading"></a><span data-ttu-id="f6110-152">作为替代方法重载无类型编程</span><span class="sxs-lookup"><span data-stu-id="f6110-152">Typeless Programming as an Alternative to Overloading</span></span>  
 <span data-ttu-id="f6110-153">如果你想要允许不同的数据类型传递给参数调用的代码，替代方法是无类型编程。</span><span class="sxs-lookup"><span data-stu-id="f6110-153">If you want to allow the calling code to pass different data types to a parameter, an alternative approach is typeless programming.</span></span> <span data-ttu-id="f6110-154">你可以设置类型检查切换到`Off`使用[Option Strict 语句](../../../../visual-basic/language-reference/statements/option-strict-statement.md)或[/optionstrict](../../../../visual-basic/reference/command-line-compiler/optionstrict.md)编译器选项。</span><span class="sxs-lookup"><span data-stu-id="f6110-154">You can set the type checking switch to `Off` with either the [Option Strict Statement](../../../../visual-basic/language-reference/statements/option-strict-statement.md) or the [/optionstrict](../../../../visual-basic/reference/command-line-compiler/optionstrict.md) compiler option.</span></span> <span data-ttu-id="f6110-155">然后无需声明参数的数据类型。</span><span class="sxs-lookup"><span data-stu-id="f6110-155">Then you do not have to declare the parameter's data type.</span></span> <span data-ttu-id="f6110-156">但是，此方法具有以下缺点相比重载：</span><span class="sxs-lookup"><span data-stu-id="f6110-156">However, this approach has the following disadvantages compared to overloading:</span></span>  
  
-   <span data-ttu-id="f6110-157">无类型编程生成效率较低的执行代码。</span><span class="sxs-lookup"><span data-stu-id="f6110-157">Typeless programming produces less efficient execution code.</span></span>  
  
-   <span data-ttu-id="f6110-158">该过程必须测试预期将传递每个数据类型。</span><span class="sxs-lookup"><span data-stu-id="f6110-158">The procedure must test for every data type it anticipates being passed.</span></span>  
  
-   <span data-ttu-id="f6110-159">如果调用代码传递过程不支持的数据类型，编译器无法发出错误。</span><span class="sxs-lookup"><span data-stu-id="f6110-159">The compiler cannot signal an error if the calling code passes a data type that the procedure does not support.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f6110-160">另请参阅</span><span class="sxs-lookup"><span data-stu-id="f6110-160">See Also</span></span>  
 [<span data-ttu-id="f6110-161">过程</span><span class="sxs-lookup"><span data-stu-id="f6110-161">Procedures</span></span>](./index.md)  
 [<span data-ttu-id="f6110-162">过程参数和自变量</span><span class="sxs-lookup"><span data-stu-id="f6110-162">Procedure Parameters and Arguments</span></span>](./procedure-parameters-and-arguments.md)  
 [<span data-ttu-id="f6110-163">过程疑难解答</span><span class="sxs-lookup"><span data-stu-id="f6110-163">Troubleshooting Procedures</span></span>](./troubleshooting-procedures.md)  
 [<span data-ttu-id="f6110-164">如何：定义一个过程的多个版本</span><span class="sxs-lookup"><span data-stu-id="f6110-164">How to: Define Multiple Versions of a Procedure</span></span>](./how-to-define-multiple-versions-of-a-procedure.md)  
 [<span data-ttu-id="f6110-165">如何：调用重载过程</span><span class="sxs-lookup"><span data-stu-id="f6110-165">How to: Call an Overloaded Procedure</span></span>](./how-to-call-an-overloaded-procedure.md)  
 [<span data-ttu-id="f6110-166">如何：重载带有可选参数的过程</span><span class="sxs-lookup"><span data-stu-id="f6110-166">How to: Overload a Procedure that Takes Optional Parameters</span></span>](./how-to-overload-a-procedure-that-takes-optional-parameters.md)  
 [<span data-ttu-id="f6110-167">如何：重载参数数量不确定的过程</span><span class="sxs-lookup"><span data-stu-id="f6110-167">How to: Overload a Procedure that Takes an Indefinite Number of Parameters</span></span>](./how-to-overload-a-procedure-that-takes-an-indefinite-number-of-parameters.md)  
 [<span data-ttu-id="f6110-168">重载决策</span><span class="sxs-lookup"><span data-stu-id="f6110-168">Overload Resolution</span></span>](./overload-resolution.md)  
 [<span data-ttu-id="f6110-169">重载</span><span class="sxs-lookup"><span data-stu-id="f6110-169">Overloads</span></span>](../../../../visual-basic/language-reference/modifiers/overloads.md)
