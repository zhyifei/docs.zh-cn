---
title: "重载过程 (Visual Basic 中) 注意事项 |Microsoft 文档"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- signatures, ParamArray arguments
- ParamArray keyword, parameter arrays
- ParamArray keyword, arguments and signatures
- function overloading, implicit overloads for ParamArray
- ParamArray keyword, signatures
- Visual Basic code, procedures
- arguments [Visual Basic], parameter arrays
- procedures, overloading
- parameters, lists
- function overloading, typeless programming
- typeless programming
- function overloading, restrictions
- arguments [Visual Basic], optional
- optional arguments, overloading
- signatures, procedure
- parameter lists
- parameter arrays, overloading arguments
- Visual Basic code, parameter lists
- procedure overloading, considerations
- Option Explicit statement
- restrictions, overloading procedures
- procedures, parameter lists
ms.assetid: a2001248-10d0-42c5-b0ce-eeedc987319f
caps.latest.revision: 26
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: 486e6c08fe6284cc9b5856fb848f7307a5651120
ms.contentlocale: zh-cn
ms.lasthandoff: 04/12/2017

---
# <a name="considerations-in-overloading-procedures-visual-basic"></a><span data-ttu-id="138a7-102">重载过程注意事项 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="138a7-102">Considerations in Overloading Procedures (Visual Basic)</span></span>
<span data-ttu-id="138a7-103">重载过程，您必须使用不同*签名*对每个重载版本。</span><span class="sxs-lookup"><span data-stu-id="138a7-103">When you overload a procedure, you must use a different *signature* for each overloaded version.</span></span> <span data-ttu-id="138a7-104">这通常意味着每个版本都必须指定不同的参数列表。</span><span class="sxs-lookup"><span data-stu-id="138a7-104">This usually means each version must specify a different parameter list.</span></span> <span data-ttu-id="138a7-105">有关详细信息，请参阅"不同的签名"[过程重载](./procedure-overloading.md)。</span><span class="sxs-lookup"><span data-stu-id="138a7-105">For more information, see "Different Signature" in [Procedure Overloading](./procedure-overloading.md).</span></span>  
  
 <span data-ttu-id="138a7-106">您可以重载`Function`过程`Sub`的过程中，反之亦然，只要它们具有不同的签名和。</span><span class="sxs-lookup"><span data-stu-id="138a7-106">You can overload a `Function` procedure with a `Sub` procedure, and vice versa, provided they have different signatures.</span></span> <span data-ttu-id="138a7-107">两个重载的不能区别仅在于其中一个具有一个返回值，而另一个不。</span><span class="sxs-lookup"><span data-stu-id="138a7-107">Two overloads cannot differ only in that one has a return value and the other does not.</span></span>  
  
 <span data-ttu-id="138a7-108">可重载属性相同的方式重载的过程，并采用相同的限制。</span><span class="sxs-lookup"><span data-stu-id="138a7-108">You can overload a property the same way you overload a procedure, and with the same restrictions.</span></span> <span data-ttu-id="138a7-109">但是，不能重载的过程与属性，反之亦然。</span><span class="sxs-lookup"><span data-stu-id="138a7-109">However, you cannot overload a procedure with a property, or vice versa.</span></span>  
  
## <a name="alternatives-to-overloaded-versions"></a><span data-ttu-id="138a7-110">重载版本的替代方法</span><span class="sxs-lookup"><span data-stu-id="138a7-110">Alternatives to Overloaded Versions</span></span>  
 <span data-ttu-id="138a7-111">特别是可选的参数存在或其数量是变量时，有时需要重载版本的替代方法。</span><span class="sxs-lookup"><span data-stu-id="138a7-111">You sometimes have alternatives to overloaded versions, particularly when the presence of arguments is optional or their number is variable.</span></span>  
  
 <span data-ttu-id="138a7-112">请记住，可选参数不是支持所有语言和参数数组仅限于[!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]。</span><span class="sxs-lookup"><span data-stu-id="138a7-112">Keep in mind that optional arguments are not necessarily supported by all languages, and parameter arrays are limited to [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)].</span></span> <span data-ttu-id="138a7-113">如果您正在编写一个过程，可能会以任何若干不同的语言编写的代码中调用，那么重载版本提供最大的灵活性。</span><span class="sxs-lookup"><span data-stu-id="138a7-113">If you are writing a procedure that is likely to be called from code written in any of several different languages, overloaded versions offer the greatest flexibility.</span></span>  
  
### <a name="overloads-and-optional-arguments"></a><span data-ttu-id="138a7-114">重载和可选参数</span><span class="sxs-lookup"><span data-stu-id="138a7-114">Overloads and Optional Arguments</span></span>  
 <span data-ttu-id="138a7-115">当调用的代码 （可选） 可以提供，或者忽略一个或多个参数时，可以定义多个重载的版本，或使用可选参数。</span><span class="sxs-lookup"><span data-stu-id="138a7-115">When the calling code can optionally supply or omit one or more arguments, you can define multiple overloaded versions or use optional parameters.</span></span>  
  
#### <a name="when-to-use-overloaded-versions"></a><span data-ttu-id="138a7-116">何时使用重载的版本</span><span class="sxs-lookup"><span data-stu-id="138a7-116">When to Use Overloaded Versions</span></span>  
 <span data-ttu-id="138a7-117">您可以考虑在以下情况下定义一系列的重载版本︰</span><span class="sxs-lookup"><span data-stu-id="138a7-117">You can consider defining a series of overloaded versions in the following cases:</span></span>  
  
-   <span data-ttu-id="138a7-118">在过程代码中的逻辑是明显不同，具体取决于是否，调用代码是否提供一个可选参数。</span><span class="sxs-lookup"><span data-stu-id="138a7-118">The logic in the procedure code is significantly different depending on whether the calling code supplies an optional argument or not.</span></span>  
  
-   <span data-ttu-id="138a7-119">过程代码不能可靠地测试是否调用代码提供一个可选参数。</span><span class="sxs-lookup"><span data-stu-id="138a7-119">The procedure code cannot reliably test whether the calling code has supplied an optional argument.</span></span> <span data-ttu-id="138a7-120">这是这种情况，例如，如果没有可能的候选对于默认值调用的代码可能不会提供。</span><span class="sxs-lookup"><span data-stu-id="138a7-120">This is the case, for example, if there is no possible candidate for a default value that the calling code could not be expected to supply.</span></span>  
  
#### <a name="when-to-use-optional-parameters"></a><span data-ttu-id="138a7-121">何时使用可选参数</span><span class="sxs-lookup"><span data-stu-id="138a7-121">When to Use Optional Parameters</span></span>  
 <span data-ttu-id="138a7-122">您可能更愿意在以下情况下的一个或多个可选参数︰</span><span class="sxs-lookup"><span data-stu-id="138a7-122">You might prefer one or more optional parameters in the following cases:</span></span>  
  
-   <span data-ttu-id="138a7-123">唯一必需的操作时调用的代码不会提供一个可选参数是将参数设置为默认值。</span><span class="sxs-lookup"><span data-stu-id="138a7-123">The only required action when the calling code does not supply an optional argument is to set the parameter to a default value.</span></span> <span data-ttu-id="138a7-124">在这种情况下，该过程代码可以降低复杂程度如果定义一个或多个单个版本`Optional`参数。</span><span class="sxs-lookup"><span data-stu-id="138a7-124">In such a case, the procedure code can be less complicated if you define a single version with one or more `Optional` parameters.</span></span>  
  
 <span data-ttu-id="138a7-125">有关详细信息，请参阅[可选参数](./optional-parameters.md)。</span><span class="sxs-lookup"><span data-stu-id="138a7-125">For more information, see [Optional Parameters](./optional-parameters.md).</span></span>  
  
### <a name="overloads-and-paramarrays"></a><span data-ttu-id="138a7-126">参数和重载</span><span class="sxs-lookup"><span data-stu-id="138a7-126">Overloads and ParamArrays</span></span>  
 <span data-ttu-id="138a7-127">如果调用代码可以通过可变数量的参数，可以定义多个重载的版本，或者使用参数数组。</span><span class="sxs-lookup"><span data-stu-id="138a7-127">When the calling code can pass a variable number of arguments, you can define multiple overloaded versions or use a parameter array.</span></span>  
  
#### <a name="when-to-use-overloaded-versions"></a><span data-ttu-id="138a7-128">何时使用重载的版本</span><span class="sxs-lookup"><span data-stu-id="138a7-128">When to Use Overloaded Versions</span></span>  
 <span data-ttu-id="138a7-129">您可以考虑在以下情况下定义一系列的重载版本︰</span><span class="sxs-lookup"><span data-stu-id="138a7-129">You can consider defining a series of overloaded versions in the following cases:</span></span>  
  
-   <span data-ttu-id="138a7-130">您知道，调用代码永远不会传递多个值一小部分给参数数组。</span><span class="sxs-lookup"><span data-stu-id="138a7-130">You know that the calling code never passes more than a small number of values to the parameter array.</span></span>  
  
-   <span data-ttu-id="138a7-131">在过程代码中的逻辑是明显不同，具体取决于调用代码传递的多少个值。</span><span class="sxs-lookup"><span data-stu-id="138a7-131">The logic in the procedure code is significantly different depending on how many values the calling code passes.</span></span>  
  
-   <span data-ttu-id="138a7-132">调用代码可以通过不同的数据类型的值。</span><span class="sxs-lookup"><span data-stu-id="138a7-132">The calling code can pass values of different data types.</span></span>  
  
#### <a name="when-to-use-a-parameter-array"></a><span data-ttu-id="138a7-133">何时使用参数数组</span><span class="sxs-lookup"><span data-stu-id="138a7-133">When to Use a Parameter Array</span></span>  
 <span data-ttu-id="138a7-134">您可能会更好的`ParamArray`参数在以下情况︰</span><span class="sxs-lookup"><span data-stu-id="138a7-134">You are better served by a `ParamArray` parameter in the following cases:</span></span>  
  
-   <span data-ttu-id="138a7-135">您不能预测多少个值调用代码可以传递给参数数组，它可能是大量。</span><span class="sxs-lookup"><span data-stu-id="138a7-135">You are not able to predict how many values the calling code can pass to the parameter array, and it could be a large number.</span></span>  
  
-   <span data-ttu-id="138a7-136">过程逻辑人士遍历所有通过调用代码，执行对每个值实质上是相同的操作的值。</span><span class="sxs-lookup"><span data-stu-id="138a7-136">The procedure logic lends itself to iterating through all the values the calling code passes, performing essentially the same operations on every value.</span></span>  
  
 <span data-ttu-id="138a7-137">有关详细信息，请参阅[参数数组](./parameter-arrays.md)。</span><span class="sxs-lookup"><span data-stu-id="138a7-137">For more information, see [Parameter Arrays](./parameter-arrays.md).</span></span>  
  
## <a name="implicit-overloads-for-optional-parameters"></a><span data-ttu-id="138a7-138">可选参数的隐式重载</span><span class="sxs-lookup"><span data-stu-id="138a7-138">Implicit Overloads for Optional Parameters</span></span>  
 <span data-ttu-id="138a7-139">使用过程[可选](../../../../visual-basic/language-reference/modifiers/optional.md)参数等效于两个重载过程，一个带有可选参数，如果没有该软件的一个。</span><span class="sxs-lookup"><span data-stu-id="138a7-139">A procedure with an [Optional](../../../../visual-basic/language-reference/modifiers/optional.md) parameter is equivalent to two overloaded procedures, one with the optional parameter and one without it.</span></span> <span data-ttu-id="138a7-140">您不能具有参数列表对应于其中任何一种重载这样的过程。</span><span class="sxs-lookup"><span data-stu-id="138a7-140">You cannot overload such a procedure with a parameter list corresponding to either of these.</span></span> <span data-ttu-id="138a7-141">下面的声明说明这一点。</span><span class="sxs-lookup"><span data-stu-id="138a7-141">The following declarations illustrate this.</span></span>  
  
 <span data-ttu-id="138a7-142">[!code-vb[VbVbcnProcedures #&58; 页](./codesnippet/VisualBasic/considerations-in-overloading-procedures_1.vb)]</span><span class="sxs-lookup"><span data-stu-id="138a7-142">[!code-vb[VbVbcnProcedures#58](./codesnippet/VisualBasic/considerations-in-overloading-procedures_1.vb)]</span></span>  
  
 <span data-ttu-id="138a7-143">[!code-vb[VbVbcnProcedures #&60;](./codesnippet/VisualBasic/considerations-in-overloading-procedures_2.vb)]</span><span class="sxs-lookup"><span data-stu-id="138a7-143">[!code-vb[VbVbcnProcedures#60](./codesnippet/VisualBasic/considerations-in-overloading-procedures_2.vb)]</span></span>  
  
 <span data-ttu-id="138a7-144">[!code-vb[VbVbcnProcedures #&61;](./codesnippet/VisualBasic/considerations-in-overloading-procedures_3.vb)]</span><span class="sxs-lookup"><span data-stu-id="138a7-144">[!code-vb[VbVbcnProcedures#61](./codesnippet/VisualBasic/considerations-in-overloading-procedures_3.vb)]</span></span>  
  
 <span data-ttu-id="138a7-145">对于带多个可选参数的过程，没有隐式重载，到达由逻辑类似于前面的示例中的一组。</span><span class="sxs-lookup"><span data-stu-id="138a7-145">For a procedure with more than one optional parameter, there is a set of implicit overloads, arrived at by logic similar to that in the preceding example.</span></span>  
  
## <a name="implicit-overloads-for-a-paramarray-parameter"></a><span data-ttu-id="138a7-146">ParamArray 参数的隐式重载</span><span class="sxs-lookup"><span data-stu-id="138a7-146">Implicit Overloads for a ParamArray Parameter</span></span>  
 <span data-ttu-id="138a7-147">编译器会考虑使用为过程[ParamArray](../../../../visual-basic/language-reference/modifiers/paramarray.md)参数具有无限数目的重载，不同于彼此中新增功能调用代码将传递给参数数组，如下所示︰</span><span class="sxs-lookup"><span data-stu-id="138a7-147">The compiler considers a procedure with a [ParamArray](../../../../visual-basic/language-reference/modifiers/paramarray.md) parameter to have an infinite number of overloads, differing from each other in what the calling code passes to the parameter array, as follows:</span></span>  
  
-   <span data-ttu-id="138a7-148">当调用的代码不会提供的参数的一个重载`ParamArray`</span><span class="sxs-lookup"><span data-stu-id="138a7-148">One overload for when the calling code does not supply an argument to the `ParamArray`</span></span>  
  
-   <span data-ttu-id="138a7-149">调用代码时提供的一维数组的一个重载`ParamArray`元素类型</span><span class="sxs-lookup"><span data-stu-id="138a7-149">One overload for when the calling code supplies a one-dimensional array of the `ParamArray` element type</span></span>  
  
-   <span data-ttu-id="138a7-150">对于每个正整数时, 的重载调用的代码提供该数量的参数，每个`ParamArray`元素类型</span><span class="sxs-lookup"><span data-stu-id="138a7-150">For every positive integer, one overload for when the calling code supplies that number of arguments, each of the `ParamArray` element type</span></span>  
  
 <span data-ttu-id="138a7-151">下面的声明说明了这些隐式重载。</span><span class="sxs-lookup"><span data-stu-id="138a7-151">The following declarations illustrate these implicit overloads.</span></span>  
  
 <span data-ttu-id="138a7-152">[!code-vb[VbVbcnProcedures #&68;](./codesnippet/VisualBasic/considerations-in-overloading-procedures_4.vb)]</span><span class="sxs-lookup"><span data-stu-id="138a7-152">[!code-vb[VbVbcnProcedures#68](./codesnippet/VisualBasic/considerations-in-overloading-procedures_4.vb)]</span></span>  
  
 <span data-ttu-id="138a7-153">[!code-vb[VbVbcnProcedures #&70;](./codesnippet/VisualBasic/considerations-in-overloading-procedures_5.vb)]</span><span class="sxs-lookup"><span data-stu-id="138a7-153">[!code-vb[VbVbcnProcedures#70](./codesnippet/VisualBasic/considerations-in-overloading-procedures_5.vb)]</span></span>  
  
 <span data-ttu-id="138a7-154">无法重载这种过程，将一维数组的参数数组的参数列表。</span><span class="sxs-lookup"><span data-stu-id="138a7-154">You cannot overload such a procedure with a parameter list that takes a one-dimensional array for the parameter array.</span></span> <span data-ttu-id="138a7-155">但是，您可以使用其他隐式重载的签名。</span><span class="sxs-lookup"><span data-stu-id="138a7-155">However, you can use the signatures of the other implicit overloads.</span></span> <span data-ttu-id="138a7-156">下面的声明说明这一点。</span><span class="sxs-lookup"><span data-stu-id="138a7-156">The following declarations illustrate this.</span></span>  
  
 <span data-ttu-id="138a7-157">[!code-vb[VbVbcnProcedures #&71;](./codesnippet/VisualBasic/considerations-in-overloading-procedures_6.vb)]</span><span class="sxs-lookup"><span data-stu-id="138a7-157">[!code-vb[VbVbcnProcedures#71](./codesnippet/VisualBasic/considerations-in-overloading-procedures_6.vb)]</span></span>  
  
## <a name="typeless-programming-as-an-alternative-to-overloading"></a><span data-ttu-id="138a7-158">作为重载的替代方法的无类型编程</span><span class="sxs-lookup"><span data-stu-id="138a7-158">Typeless Programming as an Alternative to Overloading</span></span>  
 <span data-ttu-id="138a7-159">如果您想要使调用代码将不同的数据类型传递给一个参数，另一种方法是无类型编程。</span><span class="sxs-lookup"><span data-stu-id="138a7-159">If you want to allow the calling code to pass different data types to a parameter, an alternative approach is typeless programming.</span></span> <span data-ttu-id="138a7-160">您可以设置类型检查切换到`Off`与[Option Strict 语句](../../../../visual-basic/language-reference/statements/option-strict-statement.md)或[/optionstrict](../../../../visual-basic/reference/command-line-compiler/optionstrict.md)编译器选项。</span><span class="sxs-lookup"><span data-stu-id="138a7-160">You can set the type checking switch to `Off` with either the [Option Strict Statement](../../../../visual-basic/language-reference/statements/option-strict-statement.md) or the [/optionstrict](../../../../visual-basic/reference/command-line-compiler/optionstrict.md) compiler option.</span></span> <span data-ttu-id="138a7-161">然后您不需要声明参数的数据类型。</span><span class="sxs-lookup"><span data-stu-id="138a7-161">Then you do not have to declare the parameter's data type.</span></span> <span data-ttu-id="138a7-162">但是，此方法具有以下缺点相比重载︰</span><span class="sxs-lookup"><span data-stu-id="138a7-162">However, this approach has the following disadvantages compared to overloading:</span></span>  
  
-   <span data-ttu-id="138a7-163">无类型编程生成效率较低的执行代码。</span><span class="sxs-lookup"><span data-stu-id="138a7-163">Typeless programming produces less efficient execution code.</span></span>  
  
-   <span data-ttu-id="138a7-164">该过程必须测试预期将传递每个数据类型。</span><span class="sxs-lookup"><span data-stu-id="138a7-164">The procedure must test for every data type it anticipates being passed.</span></span>  
  
-   <span data-ttu-id="138a7-165">如果调用代码传递过程不支持的数据类型，编译器不能发出错误。</span><span class="sxs-lookup"><span data-stu-id="138a7-165">The compiler cannot signal an error if the calling code passes a data type that the procedure does not support.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="138a7-166">另请参阅</span><span class="sxs-lookup"><span data-stu-id="138a7-166">See Also</span></span>  
 <span data-ttu-id="138a7-167">[过程](./index.md) </span><span class="sxs-lookup"><span data-stu-id="138a7-167">[Procedures](./index.md) </span></span>  
<span data-ttu-id="138a7-168"> [过程参数和变量](./procedure-parameters-and-arguments.md) </span><span class="sxs-lookup"><span data-stu-id="138a7-168"> [Procedure Parameters and Arguments](./procedure-parameters-and-arguments.md) </span></span>  
<span data-ttu-id="138a7-169"> [故障排除过程](./troubleshooting-procedures.md) </span><span class="sxs-lookup"><span data-stu-id="138a7-169"> [Troubleshooting Procedures](./troubleshooting-procedures.md) </span></span>  
<span data-ttu-id="138a7-170"> [如何︰ 定义一个过程的多个版本](./how-to-define-multiple-versions-of-a-procedure.md) </span><span class="sxs-lookup"><span data-stu-id="138a7-170"> [How to: Define Multiple Versions of a Procedure](./how-to-define-multiple-versions-of-a-procedure.md) </span></span>  
<span data-ttu-id="138a7-171"> [如何︰ 调用重载的过程](./how-to-call-an-overloaded-procedure.md) </span><span class="sxs-lookup"><span data-stu-id="138a7-171"> [How to: Call an Overloaded Procedure](./how-to-call-an-overloaded-procedure.md) </span></span>  
<span data-ttu-id="138a7-172"> [如何︰ 重载带有可选参数的过程](./how-to-overload-a-procedure-that-takes-optional-parameters.md) </span><span class="sxs-lookup"><span data-stu-id="138a7-172"> [How to: Overload a Procedure that Takes Optional Parameters](./how-to-overload-a-procedure-that-takes-optional-parameters.md) </span></span>  
<span data-ttu-id="138a7-173"> [如何︰ 重载参数数量不确定的过程](./how-to-overload-a-procedure-that-takes-an-indefinite-number-of-parameters.md) </span><span class="sxs-lookup"><span data-stu-id="138a7-173"> [How to: Overload a Procedure that Takes an Indefinite Number of Parameters](./how-to-overload-a-procedure-that-takes-an-indefinite-number-of-parameters.md) </span></span>  
<span data-ttu-id="138a7-174"> [重载决策](./overload-resolution.md) </span><span class="sxs-lookup"><span data-stu-id="138a7-174"> [Overload Resolution](./overload-resolution.md) </span></span>  
<span data-ttu-id="138a7-175"> [重载](../../../../visual-basic/language-reference/modifiers/overloads.md)</span><span class="sxs-lookup"><span data-stu-id="138a7-175"> [Overloads](../../../../visual-basic/language-reference/modifiers/overloads.md)</span></span>
