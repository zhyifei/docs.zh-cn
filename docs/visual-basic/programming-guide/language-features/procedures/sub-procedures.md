---
title: Sub 过程 (Visual Basic)
ms.custom: ''
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
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
caps.latest.revision: 21
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 7258d57d2677042a2020097893a4f7a0adb35508
ms.sourcegitcommit: 86adcc06e35390f13c1e372c36d2e044f1fc31ef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/26/2018
---
# <a name="sub-procedures-visual-basic"></a><span data-ttu-id="998e3-102">Sub 过程 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="998e3-102">Sub Procedures (Visual Basic)</span></span>
<span data-ttu-id="998e3-103">A`Sub`过程是一系列 Visual Basic 语句括在`Sub`和`End Sub`语句。</span><span class="sxs-lookup"><span data-stu-id="998e3-103">A `Sub` procedure is a series of Visual Basic statements enclosed by the `Sub` and `End Sub` statements.</span></span> <span data-ttu-id="998e3-104">`Sub`过程执行任务，再将控制权返回给调用代码，但是它不会返回一个值调用的代码。</span><span class="sxs-lookup"><span data-stu-id="998e3-104">The `Sub` procedure performs a task and then returns control to the calling code, but it does not return a value to the calling code.</span></span>  
  
 <span data-ttu-id="998e3-105">每次调用过程时，其执行语句，从第一个可执行之后的语句开始`Sub`语句和与第一个结束`End Sub`， `Exit Sub`，或`Return`遇到的语句。</span><span class="sxs-lookup"><span data-stu-id="998e3-105">Each time the procedure is called, its statements are executed, starting with the first executable statement after the `Sub` statement and ending with the first `End Sub`, `Exit Sub`, or `Return` statement encountered.</span></span>  
  
 <span data-ttu-id="998e3-106">你可以定义`Sub`模块、 类和结构中的过程。</span><span class="sxs-lookup"><span data-stu-id="998e3-106">You can define a `Sub` procedure in modules, classes, and structures.</span></span> <span data-ttu-id="998e3-107">默认情况下，它是`Public`，这意味着你可以调用它从任意位置有权访问模块、 类或结构定义它的应用程序中。</span><span class="sxs-lookup"><span data-stu-id="998e3-107">By default, it is `Public`, which means you can call it from anywhere in your application that has access to the module, class, or structure in which you defined it.</span></span> <span data-ttu-id="998e3-108">术语，*方法*，描述`Sub`或`Function`从其定义的外部访问的过程模块、 类或结构。</span><span class="sxs-lookup"><span data-stu-id="998e3-108">The term, *method*, describes a `Sub` or `Function` procedure that is accessed from outside its defining module, class, or structure.</span></span> <span data-ttu-id="998e3-109">有关详细信息，请参阅[过程](./index.md)。</span><span class="sxs-lookup"><span data-stu-id="998e3-109">For more information, see [Procedures](./index.md).</span></span>  
  
 <span data-ttu-id="998e3-110">A`Sub`过程可以采用自变量，如常量、 变量或表达式，通过调用代码传递给它。</span><span class="sxs-lookup"><span data-stu-id="998e3-110">A `Sub` procedure can take arguments, such as constants, variables, or expressions, which are passed to it by the calling code.</span></span>  
  
## <a name="declaration-syntax"></a><span data-ttu-id="998e3-111">声明语法</span><span class="sxs-lookup"><span data-stu-id="998e3-111">Declaration Syntax</span></span>  
 <span data-ttu-id="998e3-112">声明的语法`Sub`过程是，如下所示：</span><span class="sxs-lookup"><span data-stu-id="998e3-112">The syntax for declaring a `Sub` procedure is as follows:</span></span>  
  
 <span data-ttu-id="998e3-113">`[` *修饰符* `] Sub` *subname* `[(` *parameterlist*  `)]`</span><span class="sxs-lookup"><span data-stu-id="998e3-113">`[` *modifiers* `] Sub`  *subname* `[(` *parameterlist* `)]`</span></span>  
  
 `' Statements of the Sub procedure.`  
  
 `End Sub`  
  
 <span data-ttu-id="998e3-114">`modifiers`可以指定访问级别和有关重载、 重写、 共享和隐藏信息。</span><span class="sxs-lookup"><span data-stu-id="998e3-114">The `modifiers` can specify access level and information about overloading, overriding, sharing, and shadowing.</span></span> <span data-ttu-id="998e3-115">有关详细信息，请参阅[Sub 语句](../../../../visual-basic/language-reference/statements/sub-statement.md)。</span><span class="sxs-lookup"><span data-stu-id="998e3-115">For more information, see [Sub Statement](../../../../visual-basic/language-reference/statements/sub-statement.md).</span></span>  
  
## <a name="parameter-declaration"></a><span data-ttu-id="998e3-116">参数声明</span><span class="sxs-lookup"><span data-stu-id="998e3-116">Parameter Declaration</span></span>  
 <span data-ttu-id="998e3-117">声明类似于如何声明变量时，指定的参数名称和数据类型的每个过程参数。</span><span class="sxs-lookup"><span data-stu-id="998e3-117">You declare each procedure parameter similarly to how you declare a variable, specifying the parameter name and data type.</span></span> <span data-ttu-id="998e3-118">你还可以指定的传递机制，并指示参数是可选或参数数组。</span><span class="sxs-lookup"><span data-stu-id="998e3-118">You can also specify the passing mechanism, and whether the parameter is optional or a parameter array.</span></span>  
  
 <span data-ttu-id="998e3-119">在参数列表中每个参数的语法如下所示：</span><span class="sxs-lookup"><span data-stu-id="998e3-119">The syntax for each parameter in the parameter list is as follows:</span></span>  
  
 <span data-ttu-id="998e3-120">`[Optional] [ByVal | ByRef] [ParamArray]`  *parametername*`As`*数据类型* </span><span class="sxs-lookup"><span data-stu-id="998e3-120">`[Optional] [ByVal | ByRef] [ParamArray]`  *parametername*  `As`  *datatype*</span></span>  
  
 <span data-ttu-id="998e3-121">如果参数是可选的你还必须提供默认值作为其声明的一部分。</span><span class="sxs-lookup"><span data-stu-id="998e3-121">If the parameter is optional, you must also supply a default value as part of its declaration.</span></span> <span data-ttu-id="998e3-122">用于指定默认值的语法如下所示：</span><span class="sxs-lookup"><span data-stu-id="998e3-122">The syntax for specifying a default value is as follows:</span></span>  
  
 <span data-ttu-id="998e3-123">`Optional [ByVal | ByRef]`  *parametername*`As`*datatype*`=`*defaultvalue* </span><span class="sxs-lookup"><span data-stu-id="998e3-123">`Optional [ByVal | ByRef]`  *parametername*  `As`  *datatype*  `=`  *defaultvalue*</span></span>  
  
### <a name="parameters-as-local-variables"></a><span data-ttu-id="998e3-124">作为本地变量的参数</span><span class="sxs-lookup"><span data-stu-id="998e3-124">Parameters as Local Variables</span></span>  
 <span data-ttu-id="998e3-125">当控制权传递给该过程时，每个参数被视为本地变量。</span><span class="sxs-lookup"><span data-stu-id="998e3-125">When control passes to the procedure, each parameter is treated as a local variable.</span></span> <span data-ttu-id="998e3-126">这意味着它的生存期即相同的过程，并且其作用域是整个过程。</span><span class="sxs-lookup"><span data-stu-id="998e3-126">This means that its lifetime is the same as that of the procedure, and its scope is the whole procedure.</span></span>  
  
## <a name="calling-syntax"></a><span data-ttu-id="998e3-127">调用语法</span><span class="sxs-lookup"><span data-stu-id="998e3-127">Calling Syntax</span></span>  
 <span data-ttu-id="998e3-128">调用`Sub`显式使用独立的调用语句的过程。</span><span class="sxs-lookup"><span data-stu-id="998e3-128">You invoke a `Sub` procedure explicitly with a stand-alone calling statement.</span></span> <span data-ttu-id="998e3-129">不能在表达式中使用其名称调用它。</span><span class="sxs-lookup"><span data-stu-id="998e3-129">You cannot call it by using its name in an expression.</span></span> <span data-ttu-id="998e3-130">你必须提供值的所有参数，不是可选的并且必须将自变量列表括在括号中。</span><span class="sxs-lookup"><span data-stu-id="998e3-130">You must provide values for all arguments that are not optional, and you must enclose the argument list in parentheses.</span></span> <span data-ttu-id="998e3-131">如果未不提供任何参数，你可以选择省略括号。</span><span class="sxs-lookup"><span data-stu-id="998e3-131">If no arguments are supplied, you can optionally omit the parentheses.</span></span> <span data-ttu-id="998e3-132">使用`Call`关键字是可选的但不是建议这样做。</span><span class="sxs-lookup"><span data-stu-id="998e3-132">The use of the `Call` keyword is optional but not recommended.</span></span>  
  
 <span data-ttu-id="998e3-133">针对调用语法`Sub`过程是，如下所示：</span><span class="sxs-lookup"><span data-stu-id="998e3-133">The syntax for a call to a `Sub` procedure is as follows:</span></span>  
  
 <span data-ttu-id="998e3-134">`[Call]`  *subname* `[(` *argumentlist* `)]`</span><span class="sxs-lookup"><span data-stu-id="998e3-134">`[Call]`  *subname* `[(` *argumentlist* `)]`</span></span>  
  
 <span data-ttu-id="998e3-135">你可以调用`Sub`从定义它在类外部的方法。</span><span class="sxs-lookup"><span data-stu-id="998e3-135">You can call a `Sub` method from outside the class that defines it.</span></span> <span data-ttu-id="998e3-136">首先，你必须使用`New`关键字来创建类的实例，或调用的方法返回类的实例。</span><span class="sxs-lookup"><span data-stu-id="998e3-136">First, you have to use the `New` keyword to create an instance of the class, or call a method that returns an instance of the class.</span></span> <span data-ttu-id="998e3-137">有关详细信息，请参阅[New 运算符](../../../../visual-basic/language-reference/operators/new-operator.md)。</span><span class="sxs-lookup"><span data-stu-id="998e3-137">For more information, see [New Operator](../../../../visual-basic/language-reference/operators/new-operator.md).</span></span> <span data-ttu-id="998e3-138">然后，使用以下语法来调用`Sub`实例对象上的方法：</span><span class="sxs-lookup"><span data-stu-id="998e3-138">Then, you can use the following syntax to call the `Sub` method on the instance object:</span></span>  
  
 <span data-ttu-id="998e3-139">*对象*。*methodname*`[(`*argumentlist*`)]`</span><span class="sxs-lookup"><span data-stu-id="998e3-139">*Object*.*methodname*`[(`*argumentlist*`)]`</span></span>  
  
### <a name="illustration-of-declaration-and-call"></a><span data-ttu-id="998e3-140">声明和调用图</span><span class="sxs-lookup"><span data-stu-id="998e3-140">Illustration of Declaration and Call</span></span>  
 <span data-ttu-id="998e3-141">以下`Sub`过程通知计算机运算符哪个任务应用程序即将执行，并且还显示时间戳。</span><span class="sxs-lookup"><span data-stu-id="998e3-141">The following `Sub` procedure tells the computer operator which task the application is about to perform, and also displays a time stamp.</span></span> <span data-ttu-id="998e3-142">而不是复制此代码开头的每个任务时，应用程序只调用`tellOperator`从不同位置。</span><span class="sxs-lookup"><span data-stu-id="998e3-142">Instead of duplicating this code at the start of every task, the application just calls `tellOperator` from various locations.</span></span> <span data-ttu-id="998e3-143">每个调用将一个字符串中的传递`task`标识开始执行的任务的自变量。</span><span class="sxs-lookup"><span data-stu-id="998e3-143">Each call passes a string in the `task` argument that identifies the task being started.</span></span>  
  
 [!code-vb[VbVbcnProcedures#2](./codesnippet/VisualBasic/sub-procedures_1.vb)]  
  
 <span data-ttu-id="998e3-144">下面的示例演示典型调用`tellOperator`。</span><span class="sxs-lookup"><span data-stu-id="998e3-144">The following example shows a typical call to `tellOperator`.</span></span>  
  
 [!code-vb[VbVbcnProcedures#3](./codesnippet/VisualBasic/sub-procedures_2.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="998e3-145">请参阅</span><span class="sxs-lookup"><span data-stu-id="998e3-145">See Also</span></span>  
 [<span data-ttu-id="998e3-146">过程</span><span class="sxs-lookup"><span data-stu-id="998e3-146">Procedures</span></span>](./index.md)  
 [<span data-ttu-id="998e3-147">Function 过程</span><span class="sxs-lookup"><span data-stu-id="998e3-147">Function Procedures</span></span>](./function-procedures.md)  
 [<span data-ttu-id="998e3-148">属性过程</span><span class="sxs-lookup"><span data-stu-id="998e3-148">Property Procedures</span></span>](./property-procedures.md)  
 [<span data-ttu-id="998e3-149">运算符过程</span><span class="sxs-lookup"><span data-stu-id="998e3-149">Operator Procedures</span></span>](./operator-procedures.md)  
 [<span data-ttu-id="998e3-150">过程参数和自变量</span><span class="sxs-lookup"><span data-stu-id="998e3-150">Procedure Parameters and Arguments</span></span>](./procedure-parameters-and-arguments.md)  
 [<span data-ttu-id="998e3-151">Sub 语句</span><span class="sxs-lookup"><span data-stu-id="998e3-151">Sub Statement</span></span>](../../../../visual-basic/language-reference/statements/sub-statement.md)  
 [<span data-ttu-id="998e3-152">如何：调用不返回值的过程</span><span class="sxs-lookup"><span data-stu-id="998e3-152">How to: Call a Procedure that Does Not Return a Value</span></span>](./how-to-call-a-procedure-that-does-not-return-a-value.md)  
 [<span data-ttu-id="998e3-153">如何： 在 Visual Basic 中调用事件处理程序</span><span class="sxs-lookup"><span data-stu-id="998e3-153">How to: Call an Event Handler in Visual Basic</span></span>](./how-to-call-an-event-handler.md)
