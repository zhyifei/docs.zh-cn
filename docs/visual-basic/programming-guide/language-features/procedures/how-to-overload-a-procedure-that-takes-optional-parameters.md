---
title: "如何：重载带有可选参数的过程 (Visual Basic)"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- procedures [Visual Basic], parameters
- procedure overloading [Visual Basic], optional parameters
- procedures [Visual Basic], defining
- Visual Basic code, procedures
- procedure parameters
- procedures [Visual Basic], overloading
- procedures [Visual Basic], multiple versions
ms.assetid: 825f9d56-4cde-43fd-993a-b9171717e2eb
caps.latest.revision: "17"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: b4a863944d4f9ab265aab52578fbb704ca376de5
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-overload-a-procedure-that-takes-optional-parameters-visual-basic"></a><span data-ttu-id="9e30b-102">如何：重载带有可选参数的过程 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="9e30b-102">How to: Overload a Procedure that Takes Optional Parameters (Visual Basic)</span></span>
<span data-ttu-id="9e30b-103">如果过程有一个或多个[可选](../../../../visual-basic/language-reference/modifiers/optional.md)参数，不能定义匹配任何其隐式重载的重载的版本。</span><span class="sxs-lookup"><span data-stu-id="9e30b-103">If a procedure has one or more [Optional](../../../../visual-basic/language-reference/modifiers/optional.md) parameters, you cannot define an overloaded version matching any of its implicit overloads.</span></span> <span data-ttu-id="9e30b-104">有关详细信息，请参见"隐式重载为可选参数"[中重载过程注意事项](./considerations-in-overloading-procedures.md)。</span><span class="sxs-lookup"><span data-stu-id="9e30b-104">For more information, see "Implicit Overloads for Optional Parameters" in [Considerations in Overloading Procedures](./considerations-in-overloading-procedures.md).</span></span>  
  
## <a name="one-optional-parameter"></a><span data-ttu-id="9e30b-105">一个可选参数</span><span class="sxs-lookup"><span data-stu-id="9e30b-105">One Optional Parameter</span></span>  
  
#### <a name="to-overload-a-procedure-that-takes-one-optional-parameter"></a><span data-ttu-id="9e30b-106">若要重载采用一个可选参数的过程</span><span class="sxs-lookup"><span data-stu-id="9e30b-106">To overload a procedure that takes one optional parameter</span></span>  
  
1.  <span data-ttu-id="9e30b-107">编写`Sub`或`Function`参数列表中包含的可选参数的声明语句。</span><span class="sxs-lookup"><span data-stu-id="9e30b-107">Write a `Sub` or `Function` declaration statement that includes the optional parameter in the parameter list.</span></span> <span data-ttu-id="9e30b-108">不要使用`Optional`此重载版本中的关键字。</span><span class="sxs-lookup"><span data-stu-id="9e30b-108">Do not use the `Optional` keyword in this overloaded version.</span></span>  
  
2.  <span data-ttu-id="9e30b-109">位于之前`Sub`或`Function`关键字后的跟[重载](../../../../visual-basic/language-reference/modifiers/overloads.md)关键字。</span><span class="sxs-lookup"><span data-stu-id="9e30b-109">Precede the `Sub` or `Function` keyword with the [Overloads](../../../../visual-basic/language-reference/modifiers/overloads.md) keyword.</span></span>  
  
3.  <span data-ttu-id="9e30b-110">编写调用的代码提供的可选参数时应执行的过程代码。</span><span class="sxs-lookup"><span data-stu-id="9e30b-110">Write the procedure code that should execute when the calling code supplies the optional argument.</span></span>  
  
4.  <span data-ttu-id="9e30b-111">终止与过程`End Sub`或`End Function`作为适当的语句。</span><span class="sxs-lookup"><span data-stu-id="9e30b-111">Terminate the procedure with the `End Sub` or `End Function` statement as appropriate.</span></span>  
  
5.  <span data-ttu-id="9e30b-112">编写等同于第一个声明，只不过它不包括可选的参数在参数列表中的第二个声明语句。</span><span class="sxs-lookup"><span data-stu-id="9e30b-112">Write a second declaration statement that is identical to the first declaration except that it does not include the optional parameter in the parameter list.</span></span>  
  
6.  <span data-ttu-id="9e30b-113">写入时调用的代码不会提供可选自变量应执行该过程代码。</span><span class="sxs-lookup"><span data-stu-id="9e30b-113">Write the procedure code that should execute when the calling code does not supply the optional argument.</span></span> <span data-ttu-id="9e30b-114">终止与过程`End Sub`或`End Function`作为适当的语句。</span><span class="sxs-lookup"><span data-stu-id="9e30b-114">Terminate the procedure with the `End Sub` or `End Function` statement as appropriate.</span></span>  
  
     <span data-ttu-id="9e30b-115">下面的示例演示一个定义带可选参数，一组等效的两个重载的过程，最后的和示例无效且有效的重载版本的过程。</span><span class="sxs-lookup"><span data-stu-id="9e30b-115">The following example shows a procedure defined with an optional parameter,  an equivalent set of two overloaded procedures, and finally examples of both invalid and valid overloaded versions.</span></span>  
  
     [!code-vb[VbVbcnProcedures#59](./codesnippet/VisualBasic/how-to-overload-a-procedure-that-takes-optional-parameters_1.vb)]  
  
     [!code-vb[VbVbcnProcedures#60](./codesnippet/VisualBasic/how-to-overload-a-procedure-that-takes-optional-parameters_2.vb)]  
  
     [!code-vb[VbVbcnProcedures#61](./codesnippet/VisualBasic/how-to-overload-a-procedure-that-takes-optional-parameters_3.vb)]  
  
## <a name="multiple-optional-parameters"></a><span data-ttu-id="9e30b-116">多个可选参数</span><span class="sxs-lookup"><span data-stu-id="9e30b-116">Multiple Optional Parameters</span></span>  
 <span data-ttu-id="9e30b-117">对于带多个可选参数的过程，你通常需要两个以上的重载的版本。</span><span class="sxs-lookup"><span data-stu-id="9e30b-117">For a procedure with more than one optional parameter, you normally need more than two overloaded versions.</span></span> <span data-ttu-id="9e30b-118">例如，如果有两个可选参数，并且调用代码可以提供或省略相互独立的每一个，则需要四个重载的版本，分别针对每个可能提供的自变量的组合。</span><span class="sxs-lookup"><span data-stu-id="9e30b-118">For example, if there are two optional parameters, and the calling code can supply or omit each one independently of the other, you need four overloaded versions, one for each possible combination of supplied arguments.</span></span>  
  
 <span data-ttu-id="9e30b-119">当可选参数的数目增加时，会增加重载的复杂性。</span><span class="sxs-lookup"><span data-stu-id="9e30b-119">As the number of optional parameters increases, the complexity of the overloading increases.</span></span> <span data-ttu-id="9e30b-120">除非不接受提供的自变量的某些组合，为 N 可选参数中需要 2 ^ N 重载版本。</span><span class="sxs-lookup"><span data-stu-id="9e30b-120">Unless some combinations of supplied arguments are not acceptable, for N optional parameters you need 2 ^ N overloaded versions.</span></span> <span data-ttu-id="9e30b-121">根据过程的性质，你可能会发现的逻辑清晰度对齐定义所有重载的版本的额外工作。</span><span class="sxs-lookup"><span data-stu-id="9e30b-121">Depending on the nature of the procedure, you might find that the clarity of logic justifies the extra effort of defining all the overloaded versions.</span></span>  
  
#### <a name="to-overload-a-procedure-that-takes-more-than-one-optional-parameter"></a><span data-ttu-id="9e30b-122">若要重载采用多个可选参数的过程</span><span class="sxs-lookup"><span data-stu-id="9e30b-122">To overload a procedure that takes more than one optional parameter</span></span>  
  
1.  <span data-ttu-id="9e30b-123">确定提供的可选自变量的组合可接受的过程的逻辑。</span><span class="sxs-lookup"><span data-stu-id="9e30b-123">Determine which combinations of supplied optional arguments are acceptable to the logic of the procedure.</span></span> <span data-ttu-id="9e30b-124">如果依赖于另一个可选参数，则可能会出现不可接受的组合。</span><span class="sxs-lookup"><span data-stu-id="9e30b-124">An unacceptable combination might arise if one optional parameter depends on another.</span></span> <span data-ttu-id="9e30b-125">例如，如果一个参数接受一个配偶的姓名，另一个接受配偶的年龄是不可接受的自变量提供年龄但省略名称组合。</span><span class="sxs-lookup"><span data-stu-id="9e30b-125">For example, if one parameter accepts a spouse's name and another accepts the spouse's age, a combination of arguments supplying the age but omitting the name is unacceptable.</span></span>  
  
2.  <span data-ttu-id="9e30b-126">对于提供的可选自变量的每个可接受组合，编写`Sub`或`Function`定义相应的参数列表的声明语句。</span><span class="sxs-lookup"><span data-stu-id="9e30b-126">For each acceptable combination of supplied optional arguments, write a `Sub` or `Function` declaration statement that defines the corresponding parameter list.</span></span> <span data-ttu-id="9e30b-127">不要使用`Optional`关键字。</span><span class="sxs-lookup"><span data-stu-id="9e30b-127">Do not use the `Optional` keyword.</span></span>  
  
3.  <span data-ttu-id="9e30b-128">在每个声明，位于之前`Sub`或`Function`关键字后的跟[重载](../../../../visual-basic/language-reference/modifiers/overloads.md)关键字。</span><span class="sxs-lookup"><span data-stu-id="9e30b-128">In each declaration, precede the `Sub` or `Function` keyword with the [Overloads](../../../../visual-basic/language-reference/modifiers/overloads.md) keyword.</span></span>  
  
4.  <span data-ttu-id="9e30b-129">以下每个声明，编写调用的代码提供对应于该声明的参数列表的自变量列表时应执行该过程代码。</span><span class="sxs-lookup"><span data-stu-id="9e30b-129">Following each declaration, write the procedure code that should execute when the calling code supplies an argument list corresponding to that declaration's parameter list.</span></span>  
  
5.  <span data-ttu-id="9e30b-130">终止与每个过程`End Sub`或`End Function`作为适当的语句。</span><span class="sxs-lookup"><span data-stu-id="9e30b-130">Terminate each procedure with the `End Sub` or `End Function` statement as appropriate.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9e30b-131">另请参阅</span><span class="sxs-lookup"><span data-stu-id="9e30b-131">See Also</span></span>  
 [<span data-ttu-id="9e30b-132">过程</span><span class="sxs-lookup"><span data-stu-id="9e30b-132">Procedures</span></span>](./index.md)  
 [<span data-ttu-id="9e30b-133">过程参数和自变量</span><span class="sxs-lookup"><span data-stu-id="9e30b-133">Procedure Parameters and Arguments</span></span>](./procedure-parameters-and-arguments.md)  
 [<span data-ttu-id="9e30b-134">可选参数</span><span class="sxs-lookup"><span data-stu-id="9e30b-134">Optional Parameters</span></span>](./optional-parameters.md)  
 [<span data-ttu-id="9e30b-135">参数数组</span><span class="sxs-lookup"><span data-stu-id="9e30b-135">Parameter Arrays</span></span>](./parameter-arrays.md)  
 [<span data-ttu-id="9e30b-136">过程重载</span><span class="sxs-lookup"><span data-stu-id="9e30b-136">Procedure Overloading</span></span>](./procedure-overloading.md)  
 [<span data-ttu-id="9e30b-137">过程疑难解答</span><span class="sxs-lookup"><span data-stu-id="9e30b-137">Troubleshooting Procedures</span></span>](./troubleshooting-procedures.md)  
 [<span data-ttu-id="9e30b-138">如何：定义一个过程的多个版本</span><span class="sxs-lookup"><span data-stu-id="9e30b-138">How to: Define Multiple Versions of a Procedure</span></span>](./how-to-define-multiple-versions-of-a-procedure.md)  
 [<span data-ttu-id="9e30b-139">如何：调用重载过程</span><span class="sxs-lookup"><span data-stu-id="9e30b-139">How to: Call an Overloaded Procedure</span></span>](./how-to-call-an-overloaded-procedure.md)  
 [<span data-ttu-id="9e30b-140">如何：重载参数数量不确定的过程</span><span class="sxs-lookup"><span data-stu-id="9e30b-140">How to: Overload a Procedure that Takes an Indefinite Number of Parameters</span></span>](./how-to-overload-a-procedure-that-takes-an-indefinite-number-of-parameters.md)  
 [<span data-ttu-id="9e30b-141">重载决策</span><span class="sxs-lookup"><span data-stu-id="9e30b-141">Overload Resolution</span></span>](./overload-resolution.md)
