---
title: Function 过程 (Visual Basic)
ms.custom: ''
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- Function procedures
- return values [Visual Basic], function procedures
- Visual Basic code, procedures
- procedures [Visual Basic], calling
- procedures [Visual Basic], Function procedures
- syntax [Visual Basic], function procedures
ms.assetid: 1b9f632c-553b-4cb6-920a-ded117ead8c0
caps.latest.revision: 27
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: ad4f55a9dd9fbd68c36dd53a01f97ddb03c2bb9b
ms.sourcegitcommit: 86adcc06e35390f13c1e372c36d2e044f1fc31ef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/26/2018
---
# <a name="function-procedures-visual-basic"></a><span data-ttu-id="3a315-102">Function 过程 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="3a315-102">Function Procedures (Visual Basic)</span></span>
<span data-ttu-id="3a315-103">A`Function`过程是一系列 Visual Basic 语句括在`Function`和`End Function`语句。</span><span class="sxs-lookup"><span data-stu-id="3a315-103">A `Function` procedure is a series of Visual Basic statements enclosed by the `Function` and `End Function` statements.</span></span> <span data-ttu-id="3a315-104">`Function`过程执行任务，再将控制权返回给调用代码。</span><span class="sxs-lookup"><span data-stu-id="3a315-104">The `Function` procedure performs a task and then returns control to the calling code.</span></span> <span data-ttu-id="3a315-105">当它返回控件时，它还到调用代码返回一个值。</span><span class="sxs-lookup"><span data-stu-id="3a315-105">When it returns control, it also returns a value to the calling code.</span></span>  
  
 <span data-ttu-id="3a315-106">每次调用过程时，运行，其语句开头的第一个可执行语句后`Function`语句和与第一个结束`End Function`， `Exit Function`，或`Return`遇到的语句。</span><span class="sxs-lookup"><span data-stu-id="3a315-106">Each time the procedure is called, its statements run, starting with the first executable statement after the `Function` statement and ending with the first `End Function`, `Exit Function`, or `Return` statement encountered.</span></span>  
  
 <span data-ttu-id="3a315-107">你可以定义`Function`模块、 类或结构中的过程。</span><span class="sxs-lookup"><span data-stu-id="3a315-107">You can define a `Function` procedure in a module, class, or structure.</span></span> <span data-ttu-id="3a315-108">它是`Public`默认情况下，这意味着你可以从任何位置调用它有权访问模块、 类或结构定义它的应用程序中。</span><span class="sxs-lookup"><span data-stu-id="3a315-108">It is `Public` by default, which means you can call it from anywhere in your application that has access to the module, class, or structure in which you defined it.</span></span>  
  
 <span data-ttu-id="3a315-109">A`Function`过程可以采用自变量，如常量、 变量或表达式，通过调用代码传递给它。</span><span class="sxs-lookup"><span data-stu-id="3a315-109">A `Function` procedure can take arguments, such as constants, variables, or expressions, which are passed to it by the calling code.</span></span>  
  
## <a name="declaration-syntax"></a><span data-ttu-id="3a315-110">声明语法</span><span class="sxs-lookup"><span data-stu-id="3a315-110">Declaration Syntax</span></span>  
 <span data-ttu-id="3a315-111">声明的语法`Function`过程是，如下所示：</span><span class="sxs-lookup"><span data-stu-id="3a315-111">The syntax for declaring a `Function` procedure is as follows:</span></span>  
  
```vb  
[Modifiers] Function FunctionName [(ParameterList)] As ReturnType  
    [Statements]  
End Function  
```  
  
 <span data-ttu-id="3a315-112">*修饰符*可以指定访问级别和有关重载、 重写、 共享和隐藏信息。</span><span class="sxs-lookup"><span data-stu-id="3a315-112">The *modifiers* can specify access level and information regarding overloading, overriding, sharing, and shadowing.</span></span> <span data-ttu-id="3a315-113">有关详细信息，请参阅[Function 语句](../../../../visual-basic/language-reference/statements/function-statement.md)。</span><span class="sxs-lookup"><span data-stu-id="3a315-113">For more information, see [Function Statement](../../../../visual-basic/language-reference/statements/function-statement.md).</span></span>  
  
 <span data-ttu-id="3a315-114">声明每个参数使用的相同方式为[Sub 过程](./sub-procedures.md)。</span><span class="sxs-lookup"><span data-stu-id="3a315-114">You declare each parameter the same way you do for [Sub Procedures](./sub-procedures.md).</span></span>  
  
### <a name="data-type"></a><span data-ttu-id="3a315-115">数据类型</span><span class="sxs-lookup"><span data-stu-id="3a315-115">Data Type</span></span>  
 <span data-ttu-id="3a315-116">每个`Function`过程具有数据类型，只需为每个变量一样。</span><span class="sxs-lookup"><span data-stu-id="3a315-116">Every `Function` procedure has a data type, just as every variable does.</span></span> <span data-ttu-id="3a315-117">此数据类型由指定`As`中的子句`Function`语句，并决定该函数返回到调用代码的值的数据类型。</span><span class="sxs-lookup"><span data-stu-id="3a315-117">This data type is specified by the `As` clause in the `Function` statement, and it determines the data type of the value the function returns to the calling code.</span></span> <span data-ttu-id="3a315-118">下面的示例声明说明这一点。</span><span class="sxs-lookup"><span data-stu-id="3a315-118">The following sample declarations illustrate this.</span></span>  
  
```vb  
Function yesterday() As Date  
End Function  
  
Function findSqrt(ByVal radicand As Single) As Single  
End Function  
```  
  
 <span data-ttu-id="3a315-119">有关详细信息，请参阅"部分" [Function 语句](../../../../visual-basic/language-reference/statements/function-statement.md)。</span><span class="sxs-lookup"><span data-stu-id="3a315-119">For more information, see "Parts" in [Function Statement](../../../../visual-basic/language-reference/statements/function-statement.md).</span></span>  
  
## <a name="returning-values"></a><span data-ttu-id="3a315-120">返回值</span><span class="sxs-lookup"><span data-stu-id="3a315-120">Returning Values</span></span>  
 <span data-ttu-id="3a315-121">值`Function`过程将发送回调用代码调用它的返回值。</span><span class="sxs-lookup"><span data-stu-id="3a315-121">The value a `Function` procedure sends back to the calling code is called its return value.</span></span> <span data-ttu-id="3a315-122">此过程返回此值在两种方式之一：</span><span class="sxs-lookup"><span data-stu-id="3a315-122">The procedure returns this value in one of two ways:</span></span>  
  
-   <span data-ttu-id="3a315-123">它使用`Return`语句以指定返回值，并返回给调用程序立即控制。</span><span class="sxs-lookup"><span data-stu-id="3a315-123">It uses the `Return` statement to specify the return value, and returns control immediately to the calling program.</span></span> <span data-ttu-id="3a315-124">下面的示例阐释了这一点。</span><span class="sxs-lookup"><span data-stu-id="3a315-124">The following example illustrates this.</span></span>  
  
```vb  
Function FunctionName [(ParameterList)] As ReturnType  
    ' The following statement immediately transfers control back  
    ' to the calling code and returns the value of Expression.  
    Return Expression  
End Function  
```  
  
-   <span data-ttu-id="3a315-125">它将值分配给它自己在过程的一个或多个语句中的函数名称。</span><span class="sxs-lookup"><span data-stu-id="3a315-125">It assigns a value to its own function name in one or more statements of the procedure.</span></span> <span data-ttu-id="3a315-126">控件不会返回之前调用程序`Exit Function`或`End Function`执行语句。</span><span class="sxs-lookup"><span data-stu-id="3a315-126">Control does not return to the calling program until an `Exit Function` or `End Function` statement is executed.</span></span> <span data-ttu-id="3a315-127">下面的示例阐释了这一点。</span><span class="sxs-lookup"><span data-stu-id="3a315-127">The following example illustrates this.</span></span>  
  
```vb  
Function FunctionName [(ParameterList)] As ReturnType  
    ' The following statement does not transfer control back to the calling code.  
    FunctionName = Expression  
    ' When control returns to the calling code, Expression is the return value.  
End Function  
```  
  
 <span data-ttu-id="3a315-128">返回值分配到函数名称的优点是： 控件未返回从过程直到它遇到`Exit Function`或`End Function`语句。</span><span class="sxs-lookup"><span data-stu-id="3a315-128">The advantage of assigning the return value to the function name is that control does not return from the procedure until it encounters an `Exit Function` or `End Function` statement.</span></span> <span data-ttu-id="3a315-129">这允许您指定一个初步的值，它更高版本在必要时调整。</span><span class="sxs-lookup"><span data-stu-id="3a315-129">This allows you to assign a preliminary value and adjust it later if necessary.</span></span>  
  
 <span data-ttu-id="3a315-130">有关返回值的详细信息，请参阅[Function 语句](../../../../visual-basic/language-reference/statements/function-statement.md)。</span><span class="sxs-lookup"><span data-stu-id="3a315-130">For more information about returning values, see [Function Statement](../../../../visual-basic/language-reference/statements/function-statement.md).</span></span> <span data-ttu-id="3a315-131">有关返回数组的信息，请参阅[数组](../../../../visual-basic/programming-guide/language-features/arrays/index.md)。</span><span class="sxs-lookup"><span data-stu-id="3a315-131">For information about returning arrays, see [Arrays](../../../../visual-basic/programming-guide/language-features/arrays/index.md).</span></span>  
  
## <a name="calling-syntax"></a><span data-ttu-id="3a315-132">调用语法</span><span class="sxs-lookup"><span data-stu-id="3a315-132">Calling Syntax</span></span>  
 <span data-ttu-id="3a315-133">调用`Function`通过包括其名称和参数放在右侧的赋值语句或表达式中的过程。</span><span class="sxs-lookup"><span data-stu-id="3a315-133">You invoke a `Function` procedure by including its name and arguments either on the right side of an assignment statement or in an expression.</span></span> <span data-ttu-id="3a315-134">你必须提供值的所有参数，不是可选的并且必须将自变量列表括在括号中。</span><span class="sxs-lookup"><span data-stu-id="3a315-134">You must provide values for all arguments that are not optional, and you must enclose the argument list in parentheses.</span></span> <span data-ttu-id="3a315-135">如果未不提供任何参数，你可以选择省略括号。</span><span class="sxs-lookup"><span data-stu-id="3a315-135">If no arguments are supplied, you can optionally omit the parentheses.</span></span>  
  
 <span data-ttu-id="3a315-136">针对调用语法`Function`过程是，如下所示：</span><span class="sxs-lookup"><span data-stu-id="3a315-136">The syntax for a call to a `Function` procedure is as follows:</span></span>  
  
 <span data-ttu-id="3a315-137">*左值*`=`*functionname* `[(` *argumentlist*  `)]`</span><span class="sxs-lookup"><span data-stu-id="3a315-137">*lvalue*  `=`  *functionname* `[(` *argumentlist* `)]`</span></span>  
  
 <span data-ttu-id="3a315-138">`If ((` *functionname* `[(` *argumentlist* `)] / 3) <=`*表达式*  `) Then`</span><span class="sxs-lookup"><span data-stu-id="3a315-138">`If ((` *functionname* `[(` *argumentlist* `)] / 3) <=`  *expression* `) Then`</span></span>  
  
 <span data-ttu-id="3a315-139">当调用`Function`过程中，则不需要使用其返回值。</span><span class="sxs-lookup"><span data-stu-id="3a315-139">When you call a `Function` procedure, you do not have to use its return value.</span></span> <span data-ttu-id="3a315-140">如果不这样做，将执行的函数的所有操作，而将忽略返回值。</span><span class="sxs-lookup"><span data-stu-id="3a315-140">If you do not, all the actions of the function are performed, but the return value is ignored.</span></span> <span data-ttu-id="3a315-141"><xref:Microsoft.VisualBasic.Interaction.MsgBox%2A> 通常会调用这种方式。</span><span class="sxs-lookup"><span data-stu-id="3a315-141"><xref:Microsoft.VisualBasic.Interaction.MsgBox%2A> is often called in this manner.</span></span>  
  
### <a name="illustration-of-declaration-and-call"></a><span data-ttu-id="3a315-142">声明和调用图</span><span class="sxs-lookup"><span data-stu-id="3a315-142">Illustration of Declaration and Call</span></span>  
 <span data-ttu-id="3a315-143">以下`Function`过程计算的最长端或斜边直角三角形，其他两条边为给定的值。</span><span class="sxs-lookup"><span data-stu-id="3a315-143">The following `Function` procedure calculates the longest side, or hypotenuse, of a right triangle, given the values for the other two sides.</span></span>  
  
 [!code-vb[VbVbcnProcedures#1](./codesnippet/VisualBasic/function-procedures_1.vb)]  
  
 <span data-ttu-id="3a315-144">下面的示例演示典型调用`hypotenuse`。</span><span class="sxs-lookup"><span data-stu-id="3a315-144">The following example shows a typical call to `hypotenuse`.</span></span>  
  
 [!code-vb[VbVbcnProcedures#6](./codesnippet/VisualBasic/function-procedures_2.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="3a315-145">请参阅</span><span class="sxs-lookup"><span data-stu-id="3a315-145">See Also</span></span>  
 [<span data-ttu-id="3a315-146">过程</span><span class="sxs-lookup"><span data-stu-id="3a315-146">Procedures</span></span>](./index.md)  
 [<span data-ttu-id="3a315-147">Sub 过程</span><span class="sxs-lookup"><span data-stu-id="3a315-147">Sub Procedures</span></span>](./sub-procedures.md)  
 [<span data-ttu-id="3a315-148">属性过程</span><span class="sxs-lookup"><span data-stu-id="3a315-148">Property Procedures</span></span>](./property-procedures.md)  
 [<span data-ttu-id="3a315-149">运算符过程</span><span class="sxs-lookup"><span data-stu-id="3a315-149">Operator Procedures</span></span>](./operator-procedures.md)  
 [<span data-ttu-id="3a315-150">过程参数和自变量</span><span class="sxs-lookup"><span data-stu-id="3a315-150">Procedure Parameters and Arguments</span></span>](./procedure-parameters-and-arguments.md)  
 [<span data-ttu-id="3a315-151">Function 语句</span><span class="sxs-lookup"><span data-stu-id="3a315-151">Function Statement</span></span>](../../../../visual-basic/language-reference/statements/function-statement.md)  
 [<span data-ttu-id="3a315-152">如何：创建返回值的过程</span><span class="sxs-lookup"><span data-stu-id="3a315-152">How to: Create a Procedure that Returns a Value</span></span>](./how-to-create-a-procedure-that-returns-a-value.md)  
 [<span data-ttu-id="3a315-153">如何：从过程返回值</span><span class="sxs-lookup"><span data-stu-id="3a315-153">How to: Return a Value from a Procedure</span></span>](./how-to-return-a-value-from-a-procedure.md)  
 [<span data-ttu-id="3a315-154">如何：调用返回值的过程</span><span class="sxs-lookup"><span data-stu-id="3a315-154">How to: Call a Procedure That Returns a Value</span></span>](./how-to-call-a-procedure-that-returns-a-value.md)
