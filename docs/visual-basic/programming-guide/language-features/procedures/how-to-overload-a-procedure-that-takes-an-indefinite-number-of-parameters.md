---
title: "如何：重载参数数量不确定的过程 (Visual Basic)"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- procedures [Visual Basic], parameters
- procedure overloading [Visual Basic], indefinite number of parameters
- procedures [Visual Basic], defining
- Visual Basic code, procedures
- procedure parameters
- procedures [Visual Basic], overloading
- procedures [Visual Basic], multiple versions
ms.assetid: c7042de2-2422-4039-94e8-ac298896af69
caps.latest.revision: "18"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 37d5b47f06bad1c2a8871168c5642663aedcccf2
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-overload-a-procedure-that-takes-an-indefinite-number-of-parameters-visual-basic"></a><span data-ttu-id="f3faa-102">如何：重载参数数量不确定的过程 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="f3faa-102">How to: Overload a Procedure that Takes an Indefinite Number of Parameters (Visual Basic)</span></span>
<span data-ttu-id="f3faa-103">如果过程有[ParamArray](../../../../visual-basic/language-reference/modifiers/paramarray.md)参数，不能定义采用一维数组的参数数组的重载的版本。</span><span class="sxs-lookup"><span data-stu-id="f3faa-103">If a procedure has a [ParamArray](../../../../visual-basic/language-reference/modifiers/paramarray.md) parameter, you cannot define an overloaded version taking a one-dimensional array for the parameter array.</span></span> <span data-ttu-id="f3faa-104">有关详细信息，请参阅"隐式重载为 ParamArray 参数"中[中重载过程注意事项](./considerations-in-overloading-procedures.md)。</span><span class="sxs-lookup"><span data-stu-id="f3faa-104">For more information, see "Implicit Overloads for a ParamArray Parameter" in [Considerations in Overloading Procedures](./considerations-in-overloading-procedures.md).</span></span>  
  
### <a name="to-overload-a-procedure-that-takes-a-variable-number-of-parameters"></a><span data-ttu-id="f3faa-105">若要重载采用数量可变的参数的过程</span><span class="sxs-lookup"><span data-stu-id="f3faa-105">To overload a procedure that takes a variable number of parameters</span></span>  
  
1.  <span data-ttu-id="f3faa-106">确定该过程，并调用代码逻辑受益于重载从多个版本`ParamArray`参数。</span><span class="sxs-lookup"><span data-stu-id="f3faa-106">Ascertain that the procedure and calling code logic benefits from overloaded versions more than from a `ParamArray` parameter.</span></span> <span data-ttu-id="f3faa-107">请参阅中的"重载和参数"[重载过程注意事项](./considerations-in-overloading-procedures.md)。</span><span class="sxs-lookup"><span data-stu-id="f3faa-107">See "Overloads and ParamArrays" in [Considerations in Overloading Procedures](./considerations-in-overloading-procedures.md).</span></span>  
  
2.  <span data-ttu-id="f3faa-108">确定的第几个提供的值，则过程应接受在参数列表的变量部分。</span><span class="sxs-lookup"><span data-stu-id="f3faa-108">Determine which numbers of supplied values the procedure should accept in the variable part of the parameter list.</span></span> <span data-ttu-id="f3faa-109">这可能包括的任何值，这种情况，并且它可能包含一个单一的一维数组的大小写。</span><span class="sxs-lookup"><span data-stu-id="f3faa-109">This might include the case of no value, and it might include the case of a single one-dimensional array.</span></span>  
  
3.  <span data-ttu-id="f3faa-110">为每个可接受提供的值数，编写`Sub`或`Function`定义相应的参数列表的声明语句。</span><span class="sxs-lookup"><span data-stu-id="f3faa-110">For each acceptable number of supplied values, write a `Sub` or `Function` declaration statement that defines the corresponding parameter list.</span></span> <span data-ttu-id="f3faa-111">请勿使用`Optional`或`ParamArray`此重载版本中的关键字。</span><span class="sxs-lookup"><span data-stu-id="f3faa-111">Do not use either the `Optional` or the `ParamArray` keyword in this overloaded version.</span></span>  
  
4.  <span data-ttu-id="f3faa-112">在每个声明，位于之前`Sub`或`Function`关键字后的跟[重载](../../../../visual-basic/language-reference/modifiers/overloads.md)关键字。</span><span class="sxs-lookup"><span data-stu-id="f3faa-112">In each declaration, precede the `Sub` or `Function` keyword with the [Overloads](../../../../visual-basic/language-reference/modifiers/overloads.md) keyword.</span></span>  
  
5.  <span data-ttu-id="f3faa-113">以下每个声明，编写调用的代码提供对应于该声明的参数列表值时应执行该过程代码。</span><span class="sxs-lookup"><span data-stu-id="f3faa-113">Following each declaration, write the procedure code that should execute when the calling code supplies values corresponding to that declaration's parameter list.</span></span>  
  
6.  <span data-ttu-id="f3faa-114">终止与每个过程`End Sub`或`End Function`作为适当的语句。</span><span class="sxs-lookup"><span data-stu-id="f3faa-114">Terminate each procedure with the `End Sub` or `End Function` statement as appropriate.</span></span>  
  
## <a name="example"></a><span data-ttu-id="f3faa-115">示例</span><span class="sxs-lookup"><span data-stu-id="f3faa-115">Example</span></span>  
 <span data-ttu-id="f3faa-116">下面的示例演示用定义的过程[ParamArray](../../../../visual-basic/language-reference/modifiers/paramarray.md)参数，然后一组等效的重载过程。</span><span class="sxs-lookup"><span data-stu-id="f3faa-116">The following example shows a procedure defined with a [ParamArray](../../../../visual-basic/language-reference/modifiers/paramarray.md) parameter, and then an equivalent set of overloaded procedures.</span></span>  
  
 [!code-vb[VbVbcnProcedures#69](./codesnippet/VisualBasic/how-to-overload-a-procedure-that-takes-an-indefinite-number-of-parameters_1.vb)]  
  
 [!code-vb[VbVbcnProcedures#70](./codesnippet/VisualBasic/how-to-overload-a-procedure-that-takes-an-indefinite-number-of-parameters_2.vb)]  
  
 <span data-ttu-id="f3faa-117">无法重载采用一维数组的参数数组的参数列表的此类的过程。</span><span class="sxs-lookup"><span data-stu-id="f3faa-117">You cannot overload such a procedure with a parameter list that takes a one-dimensional array for the parameter array.</span></span> <span data-ttu-id="f3faa-118">但是，你可以使用其他隐式重载的签名。</span><span class="sxs-lookup"><span data-stu-id="f3faa-118">However, you can use the signatures of the other implicit overloads.</span></span> <span data-ttu-id="f3faa-119">以下声明说明这一点。</span><span class="sxs-lookup"><span data-stu-id="f3faa-119">The following declarations illustrate this.</span></span>  
  
 [!code-vb[VbVbcnProcedures#71](./codesnippet/VisualBasic/how-to-overload-a-procedure-that-takes-an-indefinite-number-of-parameters_3.vb)]  
  
 <span data-ttu-id="f3faa-120">这些重载版本中的代码不需要测试是否调用的代码提供的一个或多个值`ParamArray`参数，或如果是这样，多少。</span><span class="sxs-lookup"><span data-stu-id="f3faa-120">The code in the overloaded versions does not have to test whether the calling code supplied one or more values for the `ParamArray` parameter, or if so, how many.</span></span> [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)]<span data-ttu-id="f3faa-121">将控制权传递给匹配调用实参列表的版本。</span><span class="sxs-lookup"><span data-stu-id="f3faa-121"> passes control to the version matching the calling argument list.</span></span>  
  
## <a name="compiling-the-code"></a><span data-ttu-id="f3faa-122">编译代码</span><span class="sxs-lookup"><span data-stu-id="f3faa-122">Compiling the Code</span></span>  
 <span data-ttu-id="f3faa-123">因为使用为过程`ParamArray`参数的值等效于一组重载版本，你无法使用与这些隐式重载任一对应的参数列表来重载这样的过程。</span><span class="sxs-lookup"><span data-stu-id="f3faa-123">Because a procedure with a `ParamArray` parameter is equivalent to a set of overloaded versions, you cannot overload such a procedure with a parameter list corresponding to any of these implicit overloads.</span></span> <span data-ttu-id="f3faa-124">有关详细信息，请参阅[中重载过程注意事项](./considerations-in-overloading-procedures.md)。</span><span class="sxs-lookup"><span data-stu-id="f3faa-124">For more information, see [Considerations in Overloading Procedures](./considerations-in-overloading-procedures.md).</span></span>  
  
## <a name="net-framework-security"></a><span data-ttu-id="f3faa-125">.NET Framework 安全性</span><span class="sxs-lookup"><span data-stu-id="f3faa-125">.NET Framework Security</span></span>  
 <span data-ttu-id="f3faa-126">每当你处理数组可以是无限期地大型，没有无限大某种内部容量的你的应用程序的风险。</span><span class="sxs-lookup"><span data-stu-id="f3faa-126">Whenever you deal with an array which can be indefinitely large, there is a risk of overrunning some internal capacity of your application.</span></span> <span data-ttu-id="f3faa-127">如果你接受一个参数数组，你应测试调用代码传递给它，该数组的长度，并采取适当的措施，如果你的应用程序太大。</span><span class="sxs-lookup"><span data-stu-id="f3faa-127">If you accept a parameter array, you should test for the length of the array the calling code passed to it, and take appropriate steps if it is too large for your application.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f3faa-128">另请参阅</span><span class="sxs-lookup"><span data-stu-id="f3faa-128">See Also</span></span>  
 [<span data-ttu-id="f3faa-129">过程</span><span class="sxs-lookup"><span data-stu-id="f3faa-129">Procedures</span></span>](./index.md)  
 [<span data-ttu-id="f3faa-130">过程参数和自变量</span><span class="sxs-lookup"><span data-stu-id="f3faa-130">Procedure Parameters and Arguments</span></span>](./procedure-parameters-and-arguments.md)  
 [<span data-ttu-id="f3faa-131">可选参数</span><span class="sxs-lookup"><span data-stu-id="f3faa-131">Optional Parameters</span></span>](./optional-parameters.md)  
 [<span data-ttu-id="f3faa-132">参数数组</span><span class="sxs-lookup"><span data-stu-id="f3faa-132">Parameter Arrays</span></span>](./parameter-arrays.md)  
 [<span data-ttu-id="f3faa-133">过程重载</span><span class="sxs-lookup"><span data-stu-id="f3faa-133">Procedure Overloading</span></span>](./procedure-overloading.md)  
 [<span data-ttu-id="f3faa-134">过程疑难解答</span><span class="sxs-lookup"><span data-stu-id="f3faa-134">Troubleshooting Procedures</span></span>](./troubleshooting-procedures.md)  
 [<span data-ttu-id="f3faa-135">如何：定义一个过程的多个版本</span><span class="sxs-lookup"><span data-stu-id="f3faa-135">How to: Define Multiple Versions of a Procedure</span></span>](./how-to-define-multiple-versions-of-a-procedure.md)  
 [<span data-ttu-id="f3faa-136">如何：调用重载过程</span><span class="sxs-lookup"><span data-stu-id="f3faa-136">How to: Call an Overloaded Procedure</span></span>](./how-to-call-an-overloaded-procedure.md)  
 [<span data-ttu-id="f3faa-137">如何：重载带有可选参数的过程</span><span class="sxs-lookup"><span data-stu-id="f3faa-137">How to: Overload a Procedure that Takes Optional Parameters</span></span>](./how-to-overload-a-procedure-that-takes-optional-parameters.md)  
 [<span data-ttu-id="f3faa-138">重载决策</span><span class="sxs-lookup"><span data-stu-id="f3faa-138">Overload Resolution</span></span>](./overload-resolution.md)
