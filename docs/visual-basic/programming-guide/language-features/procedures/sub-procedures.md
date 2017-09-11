---
title: "Sub 过程 (Visual Basic) |Microsoft 文档"
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
- Sub procedures, about Sub procedures
- statement blocks
- Sub procedures, calling
- procedures, calling
- Sub procedures, syntax
- Sub procedures
- procedures, Sub
- syntax, Sub procedures
ms.assetid: 6a0a4958-ed0a-4d3d-8d31-0772c82bda58
caps.latest.revision: 21
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
ms.openlocfilehash: 83f0a16498accf383da96d702c4e3a4b7de1c861
ms.contentlocale: zh-cn
ms.lasthandoff: 04/12/2017

---
# <a name="sub-procedures-visual-basic"></a><span data-ttu-id="37b99-102">Sub 过程 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="37b99-102">Sub Procedures (Visual Basic)</span></span>
<span data-ttu-id="37b99-103">一个`Sub`过程是一系列[!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]语句括`Sub`和`End Sub`语句。</span><span class="sxs-lookup"><span data-stu-id="37b99-103">A `Sub` procedure is a series of [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] statements enclosed by the `Sub` and `End Sub` statements.</span></span> <span data-ttu-id="37b99-104">`Sub`过程执行一项任务，然后将控件返回到调用代码中，但是它不到调用代码返回一个值。</span><span class="sxs-lookup"><span data-stu-id="37b99-104">The `Sub` procedure performs a task and then returns control to the calling code, but it does not return a value to the calling code.</span></span>  
  
 <span data-ttu-id="37b99-105">每次调用该过程，其执行语句，开头的第一个可执行语句后`Sub`语句，并与第一个结束`End Sub`， `Exit Sub`，或`Return`遇到的语句。</span><span class="sxs-lookup"><span data-stu-id="37b99-105">Each time the procedure is called, its statements are executed, starting with the first executable statement after the `Sub` statement and ending with the first `End Sub`, `Exit Sub`, or `Return` statement encountered.</span></span>  
  
 <span data-ttu-id="37b99-106">您可以定义`Sub`模块、 类和结构中的过程。</span><span class="sxs-lookup"><span data-stu-id="37b99-106">You can define a `Sub` procedure in modules, classes, and structures.</span></span> <span data-ttu-id="37b99-107">默认情况下，它是`Public`，这意味着您可以调用它从任意位置的应用程序有权访问模块、 类或结构在其中定义中。</span><span class="sxs-lookup"><span data-stu-id="37b99-107">By default, it is `Public`, which means you can call it from anywhere in your application that has access to the module, class, or structure in which you defined it.</span></span> <span data-ttu-id="37b99-108">术语，*方法*，描述`Sub`或`Function`从外部其定义访问的过程模块、 类或结构。</span><span class="sxs-lookup"><span data-stu-id="37b99-108">The term, *method*, describes a `Sub` or `Function` procedure that is accessed from outside its defining module, class, or structure.</span></span> <span data-ttu-id="37b99-109">有关详细信息，请参阅[过程](./index.md)。</span><span class="sxs-lookup"><span data-stu-id="37b99-109">For more information, see [Procedures](./index.md).</span></span>  
  
 <span data-ttu-id="37b99-110">一个`Sub`过程可以采用参数，如常量、 变量或表达式，通过调用代码传递给它。</span><span class="sxs-lookup"><span data-stu-id="37b99-110">A `Sub` procedure can take arguments, such as constants, variables, or expressions, which are passed to it by the calling code.</span></span>  
  
## <a name="declaration-syntax"></a><span data-ttu-id="37b99-111">声明语法</span><span class="sxs-lookup"><span data-stu-id="37b99-111">Declaration Syntax</span></span>  
 <span data-ttu-id="37b99-112">声明的语法`Sub`过程是，如下所示︰</span><span class="sxs-lookup"><span data-stu-id="37b99-112">The syntax for declaring a `Sub` procedure is as follows:</span></span>  
  
 <span data-ttu-id="37b99-113">`[`*modifiers* `] Sub`*subname* `[(` *parameterlist*  `)]`</span><span class="sxs-lookup"><span data-stu-id="37b99-113">`[` *modifiers* `] Sub`  *subname* `[(` *parameterlist* `)]`</span></span>  
  
 `' Statements of the Sub procedure.`  
  
 `End Sub`  
  
 <span data-ttu-id="37b99-114">`modifiers`可以指定访问级别和重载、 重写、 共享和隐藏有关的信息。</span><span class="sxs-lookup"><span data-stu-id="37b99-114">The `modifiers` can specify access level and information about overloading, overriding, sharing, and shadowing.</span></span> <span data-ttu-id="37b99-115">有关详细信息，请参阅[Sub 语句](../../../../visual-basic/language-reference/statements/sub-statement.md)。</span><span class="sxs-lookup"><span data-stu-id="37b99-115">For more information, see [Sub Statement](../../../../visual-basic/language-reference/statements/sub-statement.md).</span></span>  
  
## <a name="parameter-declaration"></a><span data-ttu-id="37b99-116">参数声明</span><span class="sxs-lookup"><span data-stu-id="37b99-116">Parameter Declaration</span></span>  
 <span data-ttu-id="37b99-117">声明类似于如何声明变量时，指定参数名称和数据类型的每个过程参数。</span><span class="sxs-lookup"><span data-stu-id="37b99-117">You declare each procedure parameter similarly to how you declare a variable, specifying the parameter name and data type.</span></span> <span data-ttu-id="37b99-118">您还可以指定传递机制，并指示参数是可选或参数数组。</span><span class="sxs-lookup"><span data-stu-id="37b99-118">You can also specify the passing mechanism, and whether the parameter is optional or a parameter array.</span></span>  
  
 <span data-ttu-id="37b99-119">参数列表中每个参数的语法是，如下所示︰</span><span class="sxs-lookup"><span data-stu-id="37b99-119">The syntax for each parameter in the parameter list is as follows:</span></span>  
  
 <span data-ttu-id="37b99-120">`[Optional] [ByVal | ByRef] [ParamArray]`  *parametername*`As`*数据类型    *</span><span class="sxs-lookup"><span data-stu-id="37b99-120">`[Optional] [ByVal | ByRef] [ParamArray]`  *parametername*  `As`  *datatype*</span></span>  
  
 <span data-ttu-id="37b99-121">如果该参数是可选的您还必须提供默认值作为其声明的一部分。</span><span class="sxs-lookup"><span data-stu-id="37b99-121">If the parameter is optional, you must also supply a default value as part of its declaration.</span></span> <span data-ttu-id="37b99-122">用于指定默认值的语法如下所示︰</span><span class="sxs-lookup"><span data-stu-id="37b99-122">The syntax for specifying a default value is as follows:</span></span>  
  
 <span data-ttu-id="37b99-123">`Optional [ByVal | ByRef]`  *parametername*`As`*datatype*`=`*默认值        *</span><span class="sxs-lookup"><span data-stu-id="37b99-123">`Optional [ByVal | ByRef]`  *parametername*  `As`  *datatype*  `=`  *defaultvalue*</span></span>  
  
### <a name="parameters-as-local-variables"></a><span data-ttu-id="37b99-124">作为本地变量的参数</span><span class="sxs-lookup"><span data-stu-id="37b99-124">Parameters as Local Variables</span></span>  
 <span data-ttu-id="37b99-125">当控制权传递给该过程时，每个参数被视为本地变量。</span><span class="sxs-lookup"><span data-stu-id="37b99-125">When control passes to the procedure, each parameter is treated as a local variable.</span></span> <span data-ttu-id="37b99-126">也就是说，它的生存期即相同过程，并且其作用域为整个过程。</span><span class="sxs-lookup"><span data-stu-id="37b99-126">This means that its lifetime is the same as that of the procedure, and its scope is the whole procedure.</span></span>  
  
## <a name="calling-syntax"></a><span data-ttu-id="37b99-127">调用语法</span><span class="sxs-lookup"><span data-stu-id="37b99-127">Calling Syntax</span></span>  
 <span data-ttu-id="37b99-128">您可以调用`Sub`显式使用独立的调用语句的过程。</span><span class="sxs-lookup"><span data-stu-id="37b99-128">You invoke a `Sub` procedure explicitly with a stand-alone calling statement.</span></span> <span data-ttu-id="37b99-129">不能在表达式中使用其名称来调用它。</span><span class="sxs-lookup"><span data-stu-id="37b99-129">You cannot call it by using its name in an expression.</span></span> <span data-ttu-id="37b99-130">您必须提供值的所有参数，不是可选的并且必须将参数列表括在括号中。</span><span class="sxs-lookup"><span data-stu-id="37b99-130">You must provide values for all arguments that are not optional, and you must enclose the argument list in parentheses.</span></span> <span data-ttu-id="37b99-131">如果未不提供任何参数，可以选择省略括号。</span><span class="sxs-lookup"><span data-stu-id="37b99-131">If no arguments are supplied, you can optionally omit the parentheses.</span></span> <span data-ttu-id="37b99-132">使用`Call`关键字是可选的但不是建议这样做。</span><span class="sxs-lookup"><span data-stu-id="37b99-132">The use of the `Call` keyword is optional but not recommended.</span></span>  
  
 <span data-ttu-id="37b99-133">对的调用语法`Sub`过程是，如下所示︰</span><span class="sxs-lookup"><span data-stu-id="37b99-133">The syntax for a call to a `Sub` procedure is as follows:</span></span>  
  
 <span data-ttu-id="37b99-134">`[Call]`  *子命名* `[(` *argumentlist*`)]`</span><span class="sxs-lookup"><span data-stu-id="37b99-134">`[Call]`  *subname* `[(` *argumentlist* `)]`</span></span>  
  
 <span data-ttu-id="37b99-135">您可以调用`Sub`从定义它的类之外的方法。</span><span class="sxs-lookup"><span data-stu-id="37b99-135">You can call a `Sub` method from outside the class that defines it.</span></span> <span data-ttu-id="37b99-136">首先，您必须使用`New`关键字来创建类的实例，或调用一个方法返回类的实例。</span><span class="sxs-lookup"><span data-stu-id="37b99-136">First, you have to use the `New` keyword to create an instance of the class, or call a method that returns an instance of the class.</span></span> <span data-ttu-id="37b99-137">有关详细信息，请参阅[New 运算符](../../../../visual-basic/language-reference/operators/new-operator.md)。</span><span class="sxs-lookup"><span data-stu-id="37b99-137">For more information, see [New Operator](../../../../visual-basic/language-reference/operators/new-operator.md).</span></span> <span data-ttu-id="37b99-138">然后，使用以下语法来调用`Sub`实例对象的方法︰</span><span class="sxs-lookup"><span data-stu-id="37b99-138">Then, you can use the following syntax to call the `Sub` method on the instance object:</span></span>  
  
 <span data-ttu-id="37b99-139">*Object*.*methodname*`[(`*argumentlist*`)]`</span><span class="sxs-lookup"><span data-stu-id="37b99-139">*Object*.*methodname*`[(`*argumentlist*`)]`</span></span>  
  
### <a name="illustration-of-declaration-and-call"></a><span data-ttu-id="37b99-140">声明和调用的插图</span><span class="sxs-lookup"><span data-stu-id="37b99-140">Illustration of Declaration and Call</span></span>  
 <span data-ttu-id="37b99-141">以下`Sub`过程通知计算机操作员哪个任务应用程序即将执行，并且还显示时间戳。</span><span class="sxs-lookup"><span data-stu-id="37b99-141">The following `Sub` procedure tells the computer operator which task the application is about to perform, and also displays a time stamp.</span></span> <span data-ttu-id="37b99-142">而不是重复这段代码开头的每个任务，该应用程序只调用`tellOperator`从不同位置。</span><span class="sxs-lookup"><span data-stu-id="37b99-142">Instead of duplicating this code at the start of every task, the application just calls `tellOperator` from various locations.</span></span> <span data-ttu-id="37b99-143">每次调用将一个字符串中的传递`task`标识开始执行的任务的参数。</span><span class="sxs-lookup"><span data-stu-id="37b99-143">Each call passes a string in the `task` argument that identifies the task being started.</span></span>  
  
 <span data-ttu-id="37b99-144">[!code-vb[VbVbcnProcedures #&2;](./codesnippet/VisualBasic/sub-procedures_1.vb)]</span><span class="sxs-lookup"><span data-stu-id="37b99-144">[!code-vb[VbVbcnProcedures#2](./codesnippet/VisualBasic/sub-procedures_1.vb)]</span></span>  
  
 <span data-ttu-id="37b99-145">下面的示例演示如何调用典型`tellOperator`。</span><span class="sxs-lookup"><span data-stu-id="37b99-145">The following example shows a typical call to `tellOperator`.</span></span>  
  
 <span data-ttu-id="37b99-146">[!code-vb[VbVbcnProcedures #&3;](./codesnippet/VisualBasic/sub-procedures_2.vb)]</span><span class="sxs-lookup"><span data-stu-id="37b99-146">[!code-vb[VbVbcnProcedures#3](./codesnippet/VisualBasic/sub-procedures_2.vb)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="37b99-147">另请参阅</span><span class="sxs-lookup"><span data-stu-id="37b99-147">See Also</span></span>  
 <span data-ttu-id="37b99-148">[过程](./index.md) </span><span class="sxs-lookup"><span data-stu-id="37b99-148">[Procedures](./index.md) </span></span>  
<span data-ttu-id="37b99-149"> [Function 过程](./function-procedures.md) </span><span class="sxs-lookup"><span data-stu-id="37b99-149"> [Function Procedures](./function-procedures.md) </span></span>  
<span data-ttu-id="37b99-150"> [属性过程](./property-procedures.md) </span><span class="sxs-lookup"><span data-stu-id="37b99-150"> [Property Procedures](./property-procedures.md) </span></span>  
<span data-ttu-id="37b99-151"> [运算符过程](./operator-procedures.md) </span><span class="sxs-lookup"><span data-stu-id="37b99-151"> [Operator Procedures](./operator-procedures.md) </span></span>  
<span data-ttu-id="37b99-152"> [过程参数和变量](./procedure-parameters-and-arguments.md) </span><span class="sxs-lookup"><span data-stu-id="37b99-152"> [Procedure Parameters and Arguments](./procedure-parameters-and-arguments.md) </span></span>  
<span data-ttu-id="37b99-153"> [Sub 语句](../../../../visual-basic/language-reference/statements/sub-statement.md) </span><span class="sxs-lookup"><span data-stu-id="37b99-153"> [Sub Statement](../../../../visual-basic/language-reference/statements/sub-statement.md) </span></span>  
<span data-ttu-id="37b99-154"> [如何︰ 调用不返回值的过程](./how-to-call-a-procedure-that-does-not-return-a-value.md) </span><span class="sxs-lookup"><span data-stu-id="37b99-154"> [How to: Call a Procedure that Does Not Return a Value](./how-to-call-a-procedure-that-does-not-return-a-value.md) </span></span>  
<span data-ttu-id="37b99-155"> [如何︰ 在 Visual Basic 中调用事件处理程序](./how-to-call-an-event-handler.md)</span><span class="sxs-lookup"><span data-stu-id="37b99-155"> [How to: Call an Event Handler in Visual Basic](./how-to-call-an-event-handler.md)</span></span>
