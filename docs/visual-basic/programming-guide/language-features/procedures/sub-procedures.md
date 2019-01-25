---
title: Sub 过程 (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- Sub procedures [Visual Basic], about Sub procedures
- statement blocks
- Sub procedures [Visual Basic], calling
- procedures [Visual Basic], calling
- Sub procedures [Visual Basic], syntax
- Sub procedures
- procedures [Visual Basic], Sub
- syntax [Visual Basic], Sub procedures
ms.assetid: 6a0a4958-ed0a-4d3d-8d31-0772c82bda58
ms.openlocfilehash: f558c61d2e81471e167e97816ff47bc4465c5f51
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54638114"
---
# <a name="sub-procedures-visual-basic"></a><span data-ttu-id="1571f-102">Sub 过程 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="1571f-102">Sub Procedures (Visual Basic)</span></span>
<span data-ttu-id="1571f-103">一个`Sub`过程是 Visual Basic 语句括在一系列`Sub`和`End Sub`语句。</span><span class="sxs-lookup"><span data-stu-id="1571f-103">A `Sub` procedure is a series of Visual Basic statements enclosed by the `Sub` and `End Sub` statements.</span></span> <span data-ttu-id="1571f-104">`Sub`过程执行一项任务，再将控制权返回到调用代码，但它不会向调用代码返回值。</span><span class="sxs-lookup"><span data-stu-id="1571f-104">The `Sub` procedure performs a task and then returns control to the calling code, but it does not return a value to the calling code.</span></span>  
  
 <span data-ttu-id="1571f-105">每次调用该过程时，其执行语句，开头的第一个可执行语句后`Sub`语句，并与第一个结束`End Sub`， `Exit Sub`，或`Return`遇到语句。</span><span class="sxs-lookup"><span data-stu-id="1571f-105">Each time the procedure is called, its statements are executed, starting with the first executable statement after the `Sub` statement and ending with the first `End Sub`, `Exit Sub`, or `Return` statement encountered.</span></span>  
  
 <span data-ttu-id="1571f-106">您可以定义`Sub`模块、 类和结构中的过程。</span><span class="sxs-lookup"><span data-stu-id="1571f-106">You can define a `Sub` procedure in modules, classes, and structures.</span></span> <span data-ttu-id="1571f-107">默认情况下，它是`Public`，这意味着您可以调用它从任何位置有权访问模块、 类或结构定义它在应用程序中。</span><span class="sxs-lookup"><span data-stu-id="1571f-107">By default, it is `Public`, which means you can call it from anywhere in your application that has access to the module, class, or structure in which you defined it.</span></span> <span data-ttu-id="1571f-108">字词*方法*，介绍`Sub`或`Function`从其定义的外部访问的过程模块、 类或结构。</span><span class="sxs-lookup"><span data-stu-id="1571f-108">The term, *method*, describes a `Sub` or `Function` procedure that is accessed from outside its defining module, class, or structure.</span></span> <span data-ttu-id="1571f-109">有关详细信息，请参阅[过程](./index.md)。</span><span class="sxs-lookup"><span data-stu-id="1571f-109">For more information, see [Procedures](./index.md).</span></span>  
  
 <span data-ttu-id="1571f-110">一个`Sub`过程可以采用自变量，如常量、 变量或表达式，通过调用代码传递给它。</span><span class="sxs-lookup"><span data-stu-id="1571f-110">A `Sub` procedure can take arguments, such as constants, variables, or expressions, which are passed to it by the calling code.</span></span>  
  
## <a name="declaration-syntax"></a><span data-ttu-id="1571f-111">声明语法</span><span class="sxs-lookup"><span data-stu-id="1571f-111">Declaration Syntax</span></span>  
 <span data-ttu-id="1571f-112">声明的语法`Sub`过程如下所示：</span><span class="sxs-lookup"><span data-stu-id="1571f-112">The syntax for declaring a `Sub` procedure is as follows:</span></span>  
  
 <span data-ttu-id="1571f-113">`[` *modifiers* `] Sub`  *subname* `[(` *parameterlist* `)]`</span><span class="sxs-lookup"><span data-stu-id="1571f-113">`[` *modifiers* `] Sub`  *subname* `[(` *parameterlist* `)]`</span></span>  
  
 `' Statements of the Sub procedure.`  
  
 `End Sub`  
  
 <span data-ttu-id="1571f-114">`modifiers`可以指定访问级别和重载、 重写、 共享和隐藏有关的信息。</span><span class="sxs-lookup"><span data-stu-id="1571f-114">The `modifiers` can specify access level and information about overloading, overriding, sharing, and shadowing.</span></span> <span data-ttu-id="1571f-115">有关详细信息，请参阅[Sub 语句](../../../../visual-basic/language-reference/statements/sub-statement.md)。</span><span class="sxs-lookup"><span data-stu-id="1571f-115">For more information, see [Sub Statement](../../../../visual-basic/language-reference/statements/sub-statement.md).</span></span>  
  
## <a name="parameter-declaration"></a><span data-ttu-id="1571f-116">参数声明</span><span class="sxs-lookup"><span data-stu-id="1571f-116">Parameter Declaration</span></span>  
 <span data-ttu-id="1571f-117">声明类似于如何声明一个变量，指定参数名称和数据类型的每个过程参数。</span><span class="sxs-lookup"><span data-stu-id="1571f-117">You declare each procedure parameter similarly to how you declare a variable, specifying the parameter name and data type.</span></span> <span data-ttu-id="1571f-118">此外可以指定的传递机制，和的参数是否可选或参数数组。</span><span class="sxs-lookup"><span data-stu-id="1571f-118">You can also specify the passing mechanism, and whether the parameter is optional or a parameter array.</span></span>  
  
 <span data-ttu-id="1571f-119">在参数列表中每个参数的语法如下所示：</span><span class="sxs-lookup"><span data-stu-id="1571f-119">The syntax for each parameter in the parameter list is as follows:</span></span>  
  
 <span data-ttu-id="1571f-120">`[Optional] [ByVal | ByRef] [ParamArray]`  *parametername*  `As`  *datatype*</span><span class="sxs-lookup"><span data-stu-id="1571f-120">`[Optional] [ByVal | ByRef] [ParamArray]`  *parametername*  `As`  *datatype*</span></span>  
  
 <span data-ttu-id="1571f-121">如果参数是可选的您还必须提供一个默认值作为其声明的一部分。</span><span class="sxs-lookup"><span data-stu-id="1571f-121">If the parameter is optional, you must also supply a default value as part of its declaration.</span></span> <span data-ttu-id="1571f-122">用于指定默认值的语法如下所示：</span><span class="sxs-lookup"><span data-stu-id="1571f-122">The syntax for specifying a default value is as follows:</span></span>  
  
 <span data-ttu-id="1571f-123">`Optional [ByVal | ByRef]`  *parametername*  `As`  *datatype*  `=`  *defaultvalue*</span><span class="sxs-lookup"><span data-stu-id="1571f-123">`Optional [ByVal | ByRef]`  *parametername*  `As`  *datatype*  `=`  *defaultvalue*</span></span>  
  
### <a name="parameters-as-local-variables"></a><span data-ttu-id="1571f-124">为本地变量的参数</span><span class="sxs-lookup"><span data-stu-id="1571f-124">Parameters as Local Variables</span></span>  
 <span data-ttu-id="1571f-125">当控制权传递给该过程时，每个参数被视为本地变量。</span><span class="sxs-lookup"><span data-stu-id="1571f-125">When control passes to the procedure, each parameter is treated as a local variable.</span></span> <span data-ttu-id="1571f-126">也就是说，它的生存期即相同过程，并且其作用域是整个过程。</span><span class="sxs-lookup"><span data-stu-id="1571f-126">This means that its lifetime is the same as that of the procedure, and its scope is the whole procedure.</span></span>  
  
## <a name="calling-syntax"></a><span data-ttu-id="1571f-127">调用语法</span><span class="sxs-lookup"><span data-stu-id="1571f-127">Calling Syntax</span></span>  
 <span data-ttu-id="1571f-128">调用`Sub`显式使用独立的调用语句的过程。</span><span class="sxs-lookup"><span data-stu-id="1571f-128">You invoke a `Sub` procedure explicitly with a stand-alone calling statement.</span></span> <span data-ttu-id="1571f-129">不能在表达式中使用其名称来调用它。</span><span class="sxs-lookup"><span data-stu-id="1571f-129">You cannot call it by using its name in an expression.</span></span> <span data-ttu-id="1571f-130">您必须是不可选的所有自变量提供值，必须将参数列表括在括号中。</span><span class="sxs-lookup"><span data-stu-id="1571f-130">You must provide values for all arguments that are not optional, and you must enclose the argument list in parentheses.</span></span> <span data-ttu-id="1571f-131">如果未不提供任何参数，可以选择性地省略括号。</span><span class="sxs-lookup"><span data-stu-id="1571f-131">If no arguments are supplied, you can optionally omit the parentheses.</span></span> <span data-ttu-id="1571f-132">使用`Call`关键字是可选的但不是建议这样做。</span><span class="sxs-lookup"><span data-stu-id="1571f-132">The use of the `Call` keyword is optional but not recommended.</span></span>  
  
 <span data-ttu-id="1571f-133">对的调用语法`Sub`过程如下所示：</span><span class="sxs-lookup"><span data-stu-id="1571f-133">The syntax for a call to a `Sub` procedure is as follows:</span></span>  
  
 <span data-ttu-id="1571f-134">`[Call]`  *subname* `[(` *argumentlist* `)]`</span><span class="sxs-lookup"><span data-stu-id="1571f-134">`[Call]`  *subname* `[(` *argumentlist* `)]`</span></span>  
  
 <span data-ttu-id="1571f-135">您可以调用`Sub`从外部定义它的类的方法。</span><span class="sxs-lookup"><span data-stu-id="1571f-135">You can call a `Sub` method from outside the class that defines it.</span></span> <span data-ttu-id="1571f-136">首先，您必须使用`New`关键字来创建类的实例或调用的方法返回类的实例。</span><span class="sxs-lookup"><span data-stu-id="1571f-136">First, you have to use the `New` keyword to create an instance of the class, or call a method that returns an instance of the class.</span></span> <span data-ttu-id="1571f-137">有关详细信息，请参阅[New 运算符](../../../../visual-basic/language-reference/operators/new-operator.md)。</span><span class="sxs-lookup"><span data-stu-id="1571f-137">For more information, see [New Operator](../../../../visual-basic/language-reference/operators/new-operator.md).</span></span> <span data-ttu-id="1571f-138">然后，可以使用以下语法来调用`Sub`实例对象上的方法：</span><span class="sxs-lookup"><span data-stu-id="1571f-138">Then, you can use the following syntax to call the `Sub` method on the instance object:</span></span>  
  
 <span data-ttu-id="1571f-139">*对象*。*methodname*`[(`*argumentlist*`)]`</span><span class="sxs-lookup"><span data-stu-id="1571f-139">*Object*.*methodname*`[(`*argumentlist*`)]`</span></span>  
  
### <a name="illustration-of-declaration-and-call"></a><span data-ttu-id="1571f-140">声明和调用的插图</span><span class="sxs-lookup"><span data-stu-id="1571f-140">Illustration of Declaration and Call</span></span>  
 <span data-ttu-id="1571f-141">以下`Sub`过程通知计算机运算符哪个任务应用程序即将执行，并且还显示时间戳。</span><span class="sxs-lookup"><span data-stu-id="1571f-141">The following `Sub` procedure tells the computer operator which task the application is about to perform, and also displays a time stamp.</span></span> <span data-ttu-id="1571f-142">而不是重复的每个任务开始时此代码，应用程序只需调用`tellOperator`从不同位置。</span><span class="sxs-lookup"><span data-stu-id="1571f-142">Instead of duplicating this code at the start of every task, the application just calls `tellOperator` from various locations.</span></span> <span data-ttu-id="1571f-143">每次调用将一个字符串中的传递`task`标识要启动的任务的参数。</span><span class="sxs-lookup"><span data-stu-id="1571f-143">Each call passes a string in the `task` argument that identifies the task being started.</span></span>  
  
 [!code-vb[VbVbcnProcedures#2](./codesnippet/VisualBasic/sub-procedures_1.vb)]  
  
 <span data-ttu-id="1571f-144">下面的示例演示对典型调用`tellOperator`。</span><span class="sxs-lookup"><span data-stu-id="1571f-144">The following example shows a typical call to `tellOperator`.</span></span>  
  
 [!code-vb[VbVbcnProcedures#3](./codesnippet/VisualBasic/sub-procedures_2.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="1571f-145">请参阅</span><span class="sxs-lookup"><span data-stu-id="1571f-145">See also</span></span>
- [<span data-ttu-id="1571f-146">过程</span><span class="sxs-lookup"><span data-stu-id="1571f-146">Procedures</span></span>](./index.md)
- [<span data-ttu-id="1571f-147">Function 过程</span><span class="sxs-lookup"><span data-stu-id="1571f-147">Function Procedures</span></span>](./function-procedures.md)
- [<span data-ttu-id="1571f-148">属性过程</span><span class="sxs-lookup"><span data-stu-id="1571f-148">Property Procedures</span></span>](./property-procedures.md)
- [<span data-ttu-id="1571f-149">运算符过程</span><span class="sxs-lookup"><span data-stu-id="1571f-149">Operator Procedures</span></span>](./operator-procedures.md)
- [<span data-ttu-id="1571f-150">过程参数和自变量</span><span class="sxs-lookup"><span data-stu-id="1571f-150">Procedure Parameters and Arguments</span></span>](./procedure-parameters-and-arguments.md)
- [<span data-ttu-id="1571f-151">Sub 语句</span><span class="sxs-lookup"><span data-stu-id="1571f-151">Sub Statement</span></span>](../../../../visual-basic/language-reference/statements/sub-statement.md)
- [<span data-ttu-id="1571f-152">如何：调用不返回值的过程</span><span class="sxs-lookup"><span data-stu-id="1571f-152">How to: Call a Procedure that Does Not Return a Value</span></span>](./how-to-call-a-procedure-that-does-not-return-a-value.md)
- [<span data-ttu-id="1571f-153">如何：在 Visual Basic 中调用事件处理程序</span><span class="sxs-lookup"><span data-stu-id="1571f-153">How to: Call an Event Handler in Visual Basic</span></span>](./how-to-call-an-event-handler.md)
