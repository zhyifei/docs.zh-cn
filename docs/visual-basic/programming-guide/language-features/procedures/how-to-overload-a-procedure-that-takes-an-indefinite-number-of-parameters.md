---
title: 如何：重载的参数 (Visual Basic 中) 的数量不确定的过程
ms.date: 07/20/2015
helpviewer_keywords:
- procedures [Visual Basic], parameters
- procedure overloading [Visual Basic], indefinite number of parameters
- procedures [Visual Basic], defining
- Visual Basic code, procedures
- procedure parameters
- procedures [Visual Basic], overloading
- procedures [Visual Basic], multiple versions
ms.assetid: c7042de2-2422-4039-94e8-ac298896af69
ms.openlocfilehash: 3cf75fc6221364704379eb23d308481c34e6c0d6
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "61955735"
---
# <a name="how-to-overload-a-procedure-that-takes-an-indefinite-number-of-parameters-visual-basic"></a><span data-ttu-id="4e953-102">如何：重载的参数 (Visual Basic 中) 的数量不确定的过程</span><span class="sxs-lookup"><span data-stu-id="4e953-102">How to: Overload a Procedure that Takes an Indefinite Number of Parameters (Visual Basic)</span></span>
<span data-ttu-id="4e953-103">如果某个过程带有[ParamArray](../../../../visual-basic/language-reference/modifiers/paramarray.md)参数，不能定义采用一维数组的参数数组的重载的版本。</span><span class="sxs-lookup"><span data-stu-id="4e953-103">If a procedure has a [ParamArray](../../../../visual-basic/language-reference/modifiers/paramarray.md) parameter, you cannot define an overloaded version taking a one-dimensional array for the parameter array.</span></span> <span data-ttu-id="4e953-104">有关详细信息，请参阅"隐式重载为 ParamArray 参数"中[中重载过程注意事项](./considerations-in-overloading-procedures.md)。</span><span class="sxs-lookup"><span data-stu-id="4e953-104">For more information, see "Implicit Overloads for a ParamArray Parameter" in [Considerations in Overloading Procedures](./considerations-in-overloading-procedures.md).</span></span>  
  
### <a name="to-overload-a-procedure-that-takes-a-variable-number-of-parameters"></a><span data-ttu-id="4e953-105">若要重载采用可变数量的参数的过程</span><span class="sxs-lookup"><span data-stu-id="4e953-105">To overload a procedure that takes a variable number of parameters</span></span>  
  
1. <span data-ttu-id="4e953-106">确定该过程，并调用代码逻辑受益于重载从多个版本`ParamArray`参数。</span><span class="sxs-lookup"><span data-stu-id="4e953-106">Ascertain that the procedure and calling code logic benefits from overloaded versions more than from a `ParamArray` parameter.</span></span> <span data-ttu-id="4e953-107">请参阅中"重载和参数"[重载过程注意事项](./considerations-in-overloading-procedures.md)。</span><span class="sxs-lookup"><span data-stu-id="4e953-107">See "Overloads and ParamArrays" in [Considerations in Overloading Procedures](./considerations-in-overloading-procedures.md).</span></span>  
  
2. <span data-ttu-id="4e953-108">确定提供的值的数字应接受过程的参数列表的可变部分中。</span><span class="sxs-lookup"><span data-stu-id="4e953-108">Determine which numbers of supplied values the procedure should accept in the variable part of the parameter list.</span></span> <span data-ttu-id="4e953-109">这可能包括没有值，这种情况，并且它可能包含单个的一维数组的大小写。</span><span class="sxs-lookup"><span data-stu-id="4e953-109">This might include the case of no value, and it might include the case of a single one-dimensional array.</span></span>  
  
3. <span data-ttu-id="4e953-110">对于每个可接受提供的值数，将写入`Sub`或`Function`定义相应的参数列表的声明语句。</span><span class="sxs-lookup"><span data-stu-id="4e953-110">For each acceptable number of supplied values, write a `Sub` or `Function` declaration statement that defines the corresponding parameter list.</span></span> <span data-ttu-id="4e953-111">不使用任一`Optional`或`ParamArray`此重载版本中的关键字。</span><span class="sxs-lookup"><span data-stu-id="4e953-111">Do not use either the `Optional` or the `ParamArray` keyword in this overloaded version.</span></span>  
  
4. <span data-ttu-id="4e953-112">在每个声明中前, 加上`Sub`或`Function`关键字[重载](../../../../visual-basic/language-reference/modifiers/overloads.md)关键字。</span><span class="sxs-lookup"><span data-stu-id="4e953-112">In each declaration, precede the `Sub` or `Function` keyword with the [Overloads](../../../../visual-basic/language-reference/modifiers/overloads.md) keyword.</span></span>  
  
5. <span data-ttu-id="4e953-113">以下每个声明，编写调用代码提供对应于该声明的参数列表的值时应执行的过程代码。</span><span class="sxs-lookup"><span data-stu-id="4e953-113">Following each declaration, write the procedure code that should execute when the calling code supplies values corresponding to that declaration's parameter list.</span></span>  
  
6. <span data-ttu-id="4e953-114">终止与每个过程`End Sub`或`End Function`语句作为相应。</span><span class="sxs-lookup"><span data-stu-id="4e953-114">Terminate each procedure with the `End Sub` or `End Function` statement as appropriate.</span></span>  
  
## <a name="example"></a><span data-ttu-id="4e953-115">示例</span><span class="sxs-lookup"><span data-stu-id="4e953-115">Example</span></span>  
 <span data-ttu-id="4e953-116">下面的示例演示使用定义的过程[ParamArray](../../../../visual-basic/language-reference/modifiers/paramarray.md)参数，然后一组等效的重载的过程。</span><span class="sxs-lookup"><span data-stu-id="4e953-116">The following example shows a procedure defined with a [ParamArray](../../../../visual-basic/language-reference/modifiers/paramarray.md) parameter, and then an equivalent set of overloaded procedures.</span></span>  
  
 [!code-vb[VbVbcnProcedures#69](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#69)]  
  
 [!code-vb[VbVbcnProcedures#70](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#70)]  
  
 <span data-ttu-id="4e953-117">不能重载采用一维数组的参数数组的参数列表的此类的过程。</span><span class="sxs-lookup"><span data-stu-id="4e953-117">You cannot overload such a procedure with a parameter list that takes a one-dimensional array for the parameter array.</span></span> <span data-ttu-id="4e953-118">但是，可以使用其他隐式重载的签名。</span><span class="sxs-lookup"><span data-stu-id="4e953-118">However, you can use the signatures of the other implicit overloads.</span></span> <span data-ttu-id="4e953-119">下面的声明说明这一点。</span><span class="sxs-lookup"><span data-stu-id="4e953-119">The following declarations illustrate this.</span></span>  
  
 [!code-vb[VbVbcnProcedures#71](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#71)]  
  
 <span data-ttu-id="4e953-120">在重载版本中的代码不需要测试调用代码提供的一个或多个值是否`ParamArray`参数，或如果是这样，多少。</span><span class="sxs-lookup"><span data-stu-id="4e953-120">The code in the overloaded versions does not have to test whether the calling code supplied one or more values for the `ParamArray` parameter, or if so, how many.</span></span> <span data-ttu-id="4e953-121">Visual Basic 将控制传递给调用的参数列表匹配的版本。</span><span class="sxs-lookup"><span data-stu-id="4e953-121">Visual Basic passes control to the version matching the calling argument list.</span></span>  
  
## <a name="compiling-the-code"></a><span data-ttu-id="4e953-122">编译代码</span><span class="sxs-lookup"><span data-stu-id="4e953-122">Compiling the Code</span></span>  
 <span data-ttu-id="4e953-123">因为与过程`ParamArray`参数相当于一组重载版本，不能重载带有对应到任何这些隐式重载的参数列表的此类的过程。</span><span class="sxs-lookup"><span data-stu-id="4e953-123">Because a procedure with a `ParamArray` parameter is equivalent to a set of overloaded versions, you cannot overload such a procedure with a parameter list corresponding to any of these implicit overloads.</span></span> <span data-ttu-id="4e953-124">有关详细信息，请参阅[中重载过程注意事项](./considerations-in-overloading-procedures.md)。</span><span class="sxs-lookup"><span data-stu-id="4e953-124">For more information, see [Considerations in Overloading Procedures](./considerations-in-overloading-procedures.md).</span></span>  
  
## <a name="net-framework-security"></a><span data-ttu-id="4e953-125">.NET Framework 安全性</span><span class="sxs-lookup"><span data-stu-id="4e953-125">.NET Framework Security</span></span>  
 <span data-ttu-id="4e953-126">每当处理数组可以是无限期较大，则存在无限大的某种内部容量的应用程序的风险。</span><span class="sxs-lookup"><span data-stu-id="4e953-126">Whenever you deal with an array which can be indefinitely large, there is a risk of overrunning some internal capacity of your application.</span></span> <span data-ttu-id="4e953-127">如果接受一个参数数组时，应测试调用代码传递给它，该数组的长度，并采取相应措施，如果你的应用程序太大。</span><span class="sxs-lookup"><span data-stu-id="4e953-127">If you accept a parameter array, you should test for the length of the array the calling code passed to it, and take appropriate steps if it is too large for your application.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4e953-128">请参阅</span><span class="sxs-lookup"><span data-stu-id="4e953-128">See also</span></span>

- [<span data-ttu-id="4e953-129">过程</span><span class="sxs-lookup"><span data-stu-id="4e953-129">Procedures</span></span>](./index.md)
- [<span data-ttu-id="4e953-130">过程参数和自变量</span><span class="sxs-lookup"><span data-stu-id="4e953-130">Procedure Parameters and Arguments</span></span>](./procedure-parameters-and-arguments.md)
- [<span data-ttu-id="4e953-131">可选参数</span><span class="sxs-lookup"><span data-stu-id="4e953-131">Optional Parameters</span></span>](./optional-parameters.md)
- [<span data-ttu-id="4e953-132">参数数组</span><span class="sxs-lookup"><span data-stu-id="4e953-132">Parameter Arrays</span></span>](./parameter-arrays.md)
- [<span data-ttu-id="4e953-133">过程重载</span><span class="sxs-lookup"><span data-stu-id="4e953-133">Procedure Overloading</span></span>](./procedure-overloading.md)
- [<span data-ttu-id="4e953-134">过程疑难解答</span><span class="sxs-lookup"><span data-stu-id="4e953-134">Troubleshooting Procedures</span></span>](./troubleshooting-procedures.md)
- [<span data-ttu-id="4e953-135">如何：定义一个过程的多个版本</span><span class="sxs-lookup"><span data-stu-id="4e953-135">How to: Define Multiple Versions of a Procedure</span></span>](./how-to-define-multiple-versions-of-a-procedure.md)
- [<span data-ttu-id="4e953-136">如何：调用重载的过程</span><span class="sxs-lookup"><span data-stu-id="4e953-136">How to: Call an Overloaded Procedure</span></span>](./how-to-call-an-overloaded-procedure.md)
- [<span data-ttu-id="4e953-137">如何：重载带有可选参数的过程</span><span class="sxs-lookup"><span data-stu-id="4e953-137">How to: Overload a Procedure that Takes Optional Parameters</span></span>](./how-to-overload-a-procedure-that-takes-optional-parameters.md)
- [<span data-ttu-id="4e953-138">重载决策</span><span class="sxs-lookup"><span data-stu-id="4e953-138">Overload Resolution</span></span>](./overload-resolution.md)
