---
title: "如何︰ 重载参数 (Visual Basic 中) 的数量不确定的过程 |Microsoft 文档"
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
- procedures, parameters
- procedure overloading, indefinite number of parameters
- procedures, defining
- Visual Basic code, procedures
- procedure parameters
- procedures, overloading
- procedures, multiple versions
ms.assetid: c7042de2-2422-4039-94e8-ac298896af69
caps.latest.revision: 18
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
ms.openlocfilehash: 3e4ef81049f3b0d3ab1271fb709f07c37f274a88
ms.contentlocale: zh-cn
ms.lasthandoff: 04/12/2017

---
# <a name="how-to-overload-a-procedure-that-takes-an-indefinite-number-of-parameters-visual-basic"></a><span data-ttu-id="ffb37-102">如何：重载参数数量不确定的过程 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="ffb37-102">How to: Overload a Procedure that Takes an Indefinite Number of Parameters (Visual Basic)</span></span>
<span data-ttu-id="ffb37-103">如果过程具有[ParamArray](../../../../visual-basic/language-reference/modifiers/paramarray.md)参数，不能定义带有参数数组的一维数组的重载的版本。</span><span class="sxs-lookup"><span data-stu-id="ffb37-103">If a procedure has a [ParamArray](../../../../visual-basic/language-reference/modifiers/paramarray.md) parameter, you cannot define an overloaded version taking a one-dimensional array for the parameter array.</span></span> <span data-ttu-id="ffb37-104">有关详细信息，请参阅"隐式重载为 ParamArray 参数"[中重载过程注意事项](./considerations-in-overloading-procedures.md)。</span><span class="sxs-lookup"><span data-stu-id="ffb37-104">For more information, see "Implicit Overloads for a ParamArray Parameter" in [Considerations in Overloading Procedures](./considerations-in-overloading-procedures.md).</span></span>  
  
### <a name="to-overload-a-procedure-that-takes-a-variable-number-of-parameters"></a><span data-ttu-id="ffb37-105">若要重载采用可变数目的参数的过程</span><span class="sxs-lookup"><span data-stu-id="ffb37-105">To overload a procedure that takes a variable number of parameters</span></span>  
  
1.  <span data-ttu-id="ffb37-106">确定该过程，并调用代码逻辑受益于重载版本多于`ParamArray`参数。</span><span class="sxs-lookup"><span data-stu-id="ffb37-106">Ascertain that the procedure and calling code logic benefits from overloaded versions more than from a `ParamArray` parameter.</span></span> <span data-ttu-id="ffb37-107">请参阅中的"重载和参数"[重载过程注意事项](./considerations-in-overloading-procedures.md)。</span><span class="sxs-lookup"><span data-stu-id="ffb37-107">See "Overloads and ParamArrays" in [Considerations in Overloading Procedures](./considerations-in-overloading-procedures.md).</span></span>  
  
2.  <span data-ttu-id="ffb37-108">确定的第几个提供的值，则过程应接受的参数列表的可变部分中。</span><span class="sxs-lookup"><span data-stu-id="ffb37-108">Determine which numbers of supplied values the procedure should accept in the variable part of the parameter list.</span></span> <span data-ttu-id="ffb37-109">这可能包括没有值，这种情况，并且它可能包含一个一维数组的大小写。</span><span class="sxs-lookup"><span data-stu-id="ffb37-109">This might include the case of no value, and it might include the case of a single one-dimensional array.</span></span>  
  
3.  <span data-ttu-id="ffb37-110">对于每个可接受提供的值数目，编写`Sub`或`Function`定义相应的参数列表的声明语句。</span><span class="sxs-lookup"><span data-stu-id="ffb37-110">For each acceptable number of supplied values, write a `Sub` or `Function` declaration statement that defines the corresponding parameter list.</span></span> <span data-ttu-id="ffb37-111">请不要使用`Optional`或`ParamArray`关键字在此重载版本。</span><span class="sxs-lookup"><span data-stu-id="ffb37-111">Do not use either the `Optional` or the `ParamArray` keyword in this overloaded version.</span></span>  
  
4.  <span data-ttu-id="ffb37-112">在每个声明，前面`Sub`或`Function`关键字与[重载](../../../../visual-basic/language-reference/modifiers/overloads.md)关键字。</span><span class="sxs-lookup"><span data-stu-id="ffb37-112">In each declaration, precede the `Sub` or `Function` keyword with the [Overloads](../../../../visual-basic/language-reference/modifiers/overloads.md) keyword.</span></span>  
  
5.  <span data-ttu-id="ffb37-113">每个声明之后编写调用代码提供对应于该声明的参数列表值时应执行该过程代码。</span><span class="sxs-lookup"><span data-stu-id="ffb37-113">Following each declaration, write the procedure code that should execute when the calling code supplies values corresponding to that declaration's parameter list.</span></span>  
  
6.  <span data-ttu-id="ffb37-114">终止与每个过程`End Sub`或`End Function`根据语句。</span><span class="sxs-lookup"><span data-stu-id="ffb37-114">Terminate each procedure with the `End Sub` or `End Function` statement as appropriate.</span></span>  
  
## <a name="example"></a><span data-ttu-id="ffb37-115">示例</span><span class="sxs-lookup"><span data-stu-id="ffb37-115">Example</span></span>  
 <span data-ttu-id="ffb37-116">下面的示例演示用定义的过程[ParamArray](../../../../visual-basic/language-reference/modifiers/paramarray.md)参数，然后一组等效的重载过程。</span><span class="sxs-lookup"><span data-stu-id="ffb37-116">The following example shows a procedure defined with a [ParamArray](../../../../visual-basic/language-reference/modifiers/paramarray.md) parameter, and then an equivalent set of overloaded procedures.</span></span>  
  
 <span data-ttu-id="ffb37-117">[!code-vb[VbVbcnProcedures #&69;](./codesnippet/VisualBasic/how-to-overload-a-procedure-that-takes-an-indefinite-number-of-parameters_1.vb)]</span><span class="sxs-lookup"><span data-stu-id="ffb37-117">[!code-vb[VbVbcnProcedures#69](./codesnippet/VisualBasic/how-to-overload-a-procedure-that-takes-an-indefinite-number-of-parameters_1.vb)]</span></span>  
  
 <span data-ttu-id="ffb37-118">[!code-vb[VbVbcnProcedures #&70;](./codesnippet/VisualBasic/how-to-overload-a-procedure-that-takes-an-indefinite-number-of-parameters_2.vb)]</span><span class="sxs-lookup"><span data-stu-id="ffb37-118">[!code-vb[VbVbcnProcedures#70](./codesnippet/VisualBasic/how-to-overload-a-procedure-that-takes-an-indefinite-number-of-parameters_2.vb)]</span></span>  
  
 <span data-ttu-id="ffb37-119">无法重载这种过程，将一维数组的参数数组的参数列表。</span><span class="sxs-lookup"><span data-stu-id="ffb37-119">You cannot overload such a procedure with a parameter list that takes a one-dimensional array for the parameter array.</span></span> <span data-ttu-id="ffb37-120">但是，您可以使用其他隐式重载的签名。</span><span class="sxs-lookup"><span data-stu-id="ffb37-120">However, you can use the signatures of the other implicit overloads.</span></span> <span data-ttu-id="ffb37-121">下面的声明说明这一点。</span><span class="sxs-lookup"><span data-stu-id="ffb37-121">The following declarations illustrate this.</span></span>  
  
 <span data-ttu-id="ffb37-122">[!code-vb[VbVbcnProcedures #&71;](./codesnippet/VisualBasic/how-to-overload-a-procedure-that-takes-an-indefinite-number-of-parameters_3.vb)]</span><span class="sxs-lookup"><span data-stu-id="ffb37-122">[!code-vb[VbVbcnProcedures#71](./codesnippet/VisualBasic/how-to-overload-a-procedure-that-takes-an-indefinite-number-of-parameters_3.vb)]</span></span>  
  
 <span data-ttu-id="ffb37-123">不需要测试是否调用代码提供一个或多个值中的重载版本的代码`ParamArray`参数，或如果是这样，多少。</span><span class="sxs-lookup"><span data-stu-id="ffb37-123">The code in the overloaded versions does not have to test whether the calling code supplied one or more values for the `ParamArray` parameter, or if so, how many.</span></span> [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]<span data-ttu-id="ffb37-124">将控制权传递给调用的参数列表匹配的版本。</span><span class="sxs-lookup"><span data-stu-id="ffb37-124"> passes control to the version matching the calling argument list.</span></span>  
  
## <a name="compiling-the-code"></a><span data-ttu-id="ffb37-125">编译代码</span><span class="sxs-lookup"><span data-stu-id="ffb37-125">Compiling the Code</span></span>  
 <span data-ttu-id="ffb37-126">因为与过程`ParamArray`参数相当于一组重载版本，不能重载带有对应于任何这些隐式重载的参数列表的此类的过程。</span><span class="sxs-lookup"><span data-stu-id="ffb37-126">Because a procedure with a `ParamArray` parameter is equivalent to a set of overloaded versions, you cannot overload such a procedure with a parameter list corresponding to any of these implicit overloads.</span></span> <span data-ttu-id="ffb37-127">有关详细信息，请参阅[中重载过程注意事项](./considerations-in-overloading-procedures.md)。</span><span class="sxs-lookup"><span data-stu-id="ffb37-127">For more information, see [Considerations in Overloading Procedures](./considerations-in-overloading-procedures.md).</span></span>  
  
## <a name="net-framework-security"></a><span data-ttu-id="ffb37-128">.NET Framework 安全性</span><span class="sxs-lookup"><span data-stu-id="ffb37-128">.NET Framework Security</span></span>  
 <span data-ttu-id="ffb37-129">每当您处理的可能会无限期地大数组，都无限大某种内部容量的您的应用程序的风险。</span><span class="sxs-lookup"><span data-stu-id="ffb37-129">Whenever you deal with an array which can be indefinitely large, there is a risk of overrunning some internal capacity of your application.</span></span> <span data-ttu-id="ffb37-130">如果接受一个参数数组时，应测试调用代码传递给它，该数组的长度，并采取相应的措施，如果对于您的应用程序来说太大。</span><span class="sxs-lookup"><span data-stu-id="ffb37-130">If you accept a parameter array, you should test for the length of the array the calling code passed to it, and take appropriate steps if it is too large for your application.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ffb37-131">另请参阅</span><span class="sxs-lookup"><span data-stu-id="ffb37-131">See Also</span></span>  
 <span data-ttu-id="ffb37-132">[过程](./index.md) </span><span class="sxs-lookup"><span data-stu-id="ffb37-132">[Procedures](./index.md) </span></span>  
<span data-ttu-id="ffb37-133"> [过程参数和变量](./procedure-parameters-and-arguments.md) </span><span class="sxs-lookup"><span data-stu-id="ffb37-133"> [Procedure Parameters and Arguments](./procedure-parameters-and-arguments.md) </span></span>  
<span data-ttu-id="ffb37-134"> [可选参数](./optional-parameters.md) </span><span class="sxs-lookup"><span data-stu-id="ffb37-134"> [Optional Parameters](./optional-parameters.md) </span></span>  
<span data-ttu-id="ffb37-135"> [参数数组](./parameter-arrays.md) </span><span class="sxs-lookup"><span data-stu-id="ffb37-135"> [Parameter Arrays](./parameter-arrays.md) </span></span>  
<span data-ttu-id="ffb37-136"> [过程重载](./procedure-overloading.md) </span><span class="sxs-lookup"><span data-stu-id="ffb37-136"> [Procedure Overloading](./procedure-overloading.md) </span></span>  
<span data-ttu-id="ffb37-137"> [故障排除过程](./troubleshooting-procedures.md) </span><span class="sxs-lookup"><span data-stu-id="ffb37-137"> [Troubleshooting Procedures](./troubleshooting-procedures.md) </span></span>  
<span data-ttu-id="ffb37-138"> [如何︰ 定义一个过程的多个版本](./how-to-define-multiple-versions-of-a-procedure.md) </span><span class="sxs-lookup"><span data-stu-id="ffb37-138"> [How to: Define Multiple Versions of a Procedure](./how-to-define-multiple-versions-of-a-procedure.md) </span></span>  
<span data-ttu-id="ffb37-139"> [如何︰ 调用重载的过程](./how-to-call-an-overloaded-procedure.md) </span><span class="sxs-lookup"><span data-stu-id="ffb37-139"> [How to: Call an Overloaded Procedure](./how-to-call-an-overloaded-procedure.md) </span></span>  
<span data-ttu-id="ffb37-140"> [如何︰ 重载带有可选参数的过程](./how-to-overload-a-procedure-that-takes-optional-parameters.md) </span><span class="sxs-lookup"><span data-stu-id="ffb37-140"> [How to: Overload a Procedure that Takes Optional Parameters](./how-to-overload-a-procedure-that-takes-optional-parameters.md) </span></span>  
<span data-ttu-id="ffb37-141"> [重载决策](./overload-resolution.md)</span><span class="sxs-lookup"><span data-stu-id="ffb37-141"> [Overload Resolution](./overload-resolution.md)</span></span>
