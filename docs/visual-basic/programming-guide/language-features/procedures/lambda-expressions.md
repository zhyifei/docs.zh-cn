---
title: "Lambda 表达式 (Visual Basic 中) |Microsoft 文档"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vb.LambdaFunction
dev_langs:
- VB
helpviewer_keywords:
- functions [Visual Basic], lambda expressions
- lambda expressions [Visual Basic]
- expressions [Visual Basic], lambda
- inline functions [Visual Basic]
ms.assetid: 137064b0-3928-4bfa-ba71-c3f9cbd951e2
caps.latest.revision: 52
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
ms.sourcegitcommit: 14abadaf548e228244a1ff7ca72fa3896ef4eb5d
ms.openlocfilehash: e4624e5f20beeebf85656c893043030566200557
ms.contentlocale: zh-cn
ms.lasthandoff: 05/23/2017

---
# <a name="lambda-expressions-visual-basic"></a><span data-ttu-id="ed8f7-102">Lambda 表达式 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="ed8f7-102">Lambda Expressions (Visual Basic)</span></span>
<span data-ttu-id="ed8f7-103">一个*lambda 表达式*是没有程序可以委托有效的任何地方使用的名称的函数或子例程。</span><span class="sxs-lookup"><span data-stu-id="ed8f7-103">A *lambda expression* is a function or subroutine without a name that can be used wherever a delegate is valid.</span></span> <span data-ttu-id="ed8f7-104">Lambda 表达式可以是函数或子例程，可以为单行或多行。</span><span class="sxs-lookup"><span data-stu-id="ed8f7-104">Lambda expressions can be functions or subroutines and can be single-line or multi-line.</span></span> <span data-ttu-id="ed8f7-105">可以将值从当前作用域传递到 lambda 表达式中。</span><span class="sxs-lookup"><span data-stu-id="ed8f7-105">You can pass values from the current scope to a lambda expression.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="ed8f7-106">`RemoveHandler`语句是一个例外。</span><span class="sxs-lookup"><span data-stu-id="ed8f7-106">The `RemoveHandler` statement is an exception.</span></span> <span data-ttu-id="ed8f7-107">不能将传递的委托参数的 lambda 表达式中`RemoveHandler`。</span><span class="sxs-lookup"><span data-stu-id="ed8f7-107">You cannot pass a lambda expression in for the delegate parameter of `RemoveHandler`.</span></span>  
  
 <span data-ttu-id="ed8f7-108">使用创建 lambda 表达式`Function`或`Sub`关键字，就像创建标准函数或子例程。</span><span class="sxs-lookup"><span data-stu-id="ed8f7-108">You create lambda expressions by using the `Function` or `Sub` keyword, just as you create a standard function or subroutine.</span></span> <span data-ttu-id="ed8f7-109">但是，lambda 表达式包含在一个语句。</span><span class="sxs-lookup"><span data-stu-id="ed8f7-109">However, lambda expressions are included in a statement.</span></span>  
  
 <span data-ttu-id="ed8f7-110">下面的示例是递增其参数并返回的值的 lambda 表达式。</span><span class="sxs-lookup"><span data-stu-id="ed8f7-110">The following example is a lambda expression that increments its argument and returns the value.</span></span> <span data-ttu-id="ed8f7-111">该示例同时显示的单行和多行 lambda 表达式语法的函数。</span><span class="sxs-lookup"><span data-stu-id="ed8f7-111">The example shows both the single-line and multi-line lambda expression syntax for a function.</span></span>  
  
 <span data-ttu-id="ed8f7-112">[!code-vb[VbVbalrLambdas #&14;](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/lambda-expressions_1.vb)]</span><span class="sxs-lookup"><span data-stu-id="ed8f7-112">[!code-vb[VbVbalrLambdas#14](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/lambda-expressions_1.vb)]</span></span>  
  
 <span data-ttu-id="ed8f7-113">下面的示例是一个向控制台写入一个值的 lambda 表达式。</span><span class="sxs-lookup"><span data-stu-id="ed8f7-113">The following example is a lambda expression that writes a value to the console.</span></span> <span data-ttu-id="ed8f7-114">该示例显示一个子例程这两个单行和多行 lambda 表达式语法。</span><span class="sxs-lookup"><span data-stu-id="ed8f7-114">The example shows both the single-line and multi-line lambda expression syntax for a subroutine.</span></span>  
  
 <span data-ttu-id="ed8f7-115">[!code-vb[VbVbalrLambdas #&15;](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/lambda-expressions_2.vb)]</span><span class="sxs-lookup"><span data-stu-id="ed8f7-115">[!code-vb[VbVbalrLambdas#15](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/lambda-expressions_2.vb)]</span></span>  
  
 <span data-ttu-id="ed8f7-116">请注意，前面示例中的 lambda 表达式分配给变量的名称。</span><span class="sxs-lookup"><span data-stu-id="ed8f7-116">Notice that in the previous examples the lambda expressions are assigned to a variable name.</span></span> <span data-ttu-id="ed8f7-117">只要您引用该变量，则调用 lambda 表达式。</span><span class="sxs-lookup"><span data-stu-id="ed8f7-117">Whenever you refer to the variable, you invoke the lambda expression.</span></span> <span data-ttu-id="ed8f7-118">您还可以声明并调用 lambda 表达式在同一时间，如下面的示例中所示。</span><span class="sxs-lookup"><span data-stu-id="ed8f7-118">You can also declare and invoke a lambda expression at the same time, as shown in the following example.</span></span>  
  
 <span data-ttu-id="ed8f7-119">[!code-vb[VbVbalrLambdas #&3;](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/lambda-expressions_3.vb)]</span><span class="sxs-lookup"><span data-stu-id="ed8f7-119">[!code-vb[VbVbalrLambdas#3](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/lambda-expressions_3.vb)]</span></span>  
  
 <span data-ttu-id="ed8f7-120">Lambda 表达式可以返回作为函数调用的值 (如示例中所示[上下文](#context)在本主题后面的部分)，或作为参数传递给参数接受一个委托类型，如下面的示例中所示。</span><span class="sxs-lookup"><span data-stu-id="ed8f7-120">A lambda expression can be returned as the value of a function call (as is shown in the example in the [Context](#context) section later in this topic), or passed in as an argument to a parameter that takes a delegate type, as shown in the following example.</span></span>  
  
 <span data-ttu-id="ed8f7-121">[!code-vb[VbVbalrLambdas #&8;](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/lambda-expressions_4.vb)]</span><span class="sxs-lookup"><span data-stu-id="ed8f7-121">[!code-vb[VbVbalrLambdas#8](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/lambda-expressions_4.vb)]</span></span>  
  
## <a name="lambda-expression-syntax"></a><span data-ttu-id="ed8f7-122">Lambda 表达式语法</span><span class="sxs-lookup"><span data-stu-id="ed8f7-122">Lambda Expression Syntax</span></span>  
 <span data-ttu-id="ed8f7-123">Lambda 表达式的语法类似于标准函数或子例程。</span><span class="sxs-lookup"><span data-stu-id="ed8f7-123">The syntax of a lambda expression resembles that of a standard function or subroutine.</span></span> <span data-ttu-id="ed8f7-124">区别，如下所示如下︰</span><span class="sxs-lookup"><span data-stu-id="ed8f7-124">The differences are as follows:</span></span>  
  
-   <span data-ttu-id="ed8f7-125">Lambda 表达式不具有一个名称。</span><span class="sxs-lookup"><span data-stu-id="ed8f7-125">A lambda expression does not have a name.</span></span>  
  
-   <span data-ttu-id="ed8f7-126">Lambda 表达式不能具有修饰符，如`Overloads`或`Overrides`。</span><span class="sxs-lookup"><span data-stu-id="ed8f7-126">Lambda expressions cannot have modifiers, such as `Overloads` or `Overrides`.</span></span>  
  
-   <span data-ttu-id="ed8f7-127">单行 lambda 函数不使用`As`子句指定返回类型。</span><span class="sxs-lookup"><span data-stu-id="ed8f7-127">Single-line lambda functions do not use an `As` clause to designate the return type.</span></span> <span data-ttu-id="ed8f7-128">相反，该类型是从推断 lambda 表达式的主体的计算结果为的值。</span><span class="sxs-lookup"><span data-stu-id="ed8f7-128">Instead, the type is inferred from the value that the body of the lambda expression evaluates to.</span></span> <span data-ttu-id="ed8f7-129">例如，如果 lambda 表达式的主体是`cust.City = "London"`，其返回类型是`Boolean`。</span><span class="sxs-lookup"><span data-stu-id="ed8f7-129">For example, if the body of the lambda expression is `cust.City = "London"`, its return type is `Boolean`.</span></span>  
  
-   <span data-ttu-id="ed8f7-130">在多行 lambda 函数中，您可以指定返回类型使用`As`子句，或忽略`As`子句以便推断返回类型。</span><span class="sxs-lookup"><span data-stu-id="ed8f7-130">In multi-line lambda functions, you can either specify a return type by using an `As` clause, or omit the `As` clause so that the return type is inferred.</span></span> <span data-ttu-id="ed8f7-131">当`As`子句被省略对于多行 lambda 函数、 返回类型推断为从所有的主要类型`Return`多行 lambda 函数中的语句。</span><span class="sxs-lookup"><span data-stu-id="ed8f7-131">When the `As` clause is omitted for a multi-line lambda function, the return type is inferred to be the dominant type from all the `Return` statements in the multi-line lambda function.</span></span> <span data-ttu-id="ed8f7-132">*主导类型*是所有其他类型都可以扩大到的唯一类型。</span><span class="sxs-lookup"><span data-stu-id="ed8f7-132">The *dominant type* is a unique type that all other types can widen to.</span></span> <span data-ttu-id="ed8f7-133">如果无法确定此唯一类型，主导类型是数组中的所有其他类型可以收缩到的唯一类型。</span><span class="sxs-lookup"><span data-stu-id="ed8f7-133">If this unique type cannot be determined, the dominant type is the unique type that all other types in the array can narrow to.</span></span> <span data-ttu-id="ed8f7-134">如果无法确定为这两种唯一类型之一，则基准类型是 `Object`。</span><span class="sxs-lookup"><span data-stu-id="ed8f7-134">If neither of these unique types can be determined, the dominant type is `Object`.</span></span> <span data-ttu-id="ed8f7-135">在这种情况下，如果`Option Strict`设置为`On`，会发生编译错误。</span><span class="sxs-lookup"><span data-stu-id="ed8f7-135">In this case, if `Option Strict` is set to `On`, a compiler error occurs.</span></span>  
  
     <span data-ttu-id="ed8f7-136">例如，如果表达式提供给`Return`语句包含类型的值`Integer`， `Long`，和`Double`，得到的数组的类型是`Double`。</span><span class="sxs-lookup"><span data-stu-id="ed8f7-136">For example, if the expressions supplied to the `Return` statement contain values of type `Integer`, `Long`, and `Double`, the resulting array is of type `Double`.</span></span> <span data-ttu-id="ed8f7-137">同时`Integer`和`Long`扩大到`Double`和仅`Double`。</span><span class="sxs-lookup"><span data-stu-id="ed8f7-137">Both `Integer` and `Long` widen to `Double` and only `Double`.</span></span> <span data-ttu-id="ed8f7-138">因此， `Double` 是基准类型。</span><span class="sxs-lookup"><span data-stu-id="ed8f7-138">Therefore, `Double` is the dominant type.</span></span> <span data-ttu-id="ed8f7-139">有关详细信息，请参阅[扩大和收缩转换](../../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md)。</span><span class="sxs-lookup"><span data-stu-id="ed8f7-139">For more information, see [Widening and Narrowing Conversions](../../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md).</span></span>  
  
-   <span data-ttu-id="ed8f7-140">单行函数的主体必须是一个表达式，返回一个值，而不是语句。</span><span class="sxs-lookup"><span data-stu-id="ed8f7-140">The body of a single-line function must be an expression that returns a value, not a statement.</span></span> <span data-ttu-id="ed8f7-141">有没有`Return`单行函数的语句。</span><span class="sxs-lookup"><span data-stu-id="ed8f7-141">There is no `Return` statement for single-line functions.</span></span> <span data-ttu-id="ed8f7-142">单行函数返回的值是表达式的函数的正文中的值。</span><span class="sxs-lookup"><span data-stu-id="ed8f7-142">The value returned by the single-line function is the value of the expression in the body of the function.</span></span>  
  
-   <span data-ttu-id="ed8f7-143">单行子例程的主体必须是单行语句。</span><span class="sxs-lookup"><span data-stu-id="ed8f7-143">The body of a single-line subroutine must be single-line statement.</span></span>  
  
-   <span data-ttu-id="ed8f7-144">不包括的单行函数和子例程`End Function`或`End Sub`语句。</span><span class="sxs-lookup"><span data-stu-id="ed8f7-144">Single-line functions and subroutines do not include an `End Function` or `End Sub` statement.</span></span>  
  
-   <span data-ttu-id="ed8f7-145">可以通过指定 lambda 表达式参数的数据类型`As`可以推断关键字或该参数的数据类型。</span><span class="sxs-lookup"><span data-stu-id="ed8f7-145">You can specify the data type of a lambda expression parameter by using the `As` keyword, or the data type of the parameter can be inferred.</span></span> <span data-ttu-id="ed8f7-146">必须必须推断数据类型或所有已经指定所有参数。</span><span class="sxs-lookup"><span data-stu-id="ed8f7-146">Either all parameters must have specified data types or all must be inferred.</span></span>  
  
-   <span data-ttu-id="ed8f7-147">`Optional`和`Paramarray`不允许使用参数。</span><span class="sxs-lookup"><span data-stu-id="ed8f7-147">`Optional` and `Paramarray` parameters are not permitted.</span></span>  
  
-   <span data-ttu-id="ed8f7-148">不允许泛型参数。</span><span class="sxs-lookup"><span data-stu-id="ed8f7-148">Generic parameters are not permitted.</span></span>  
  
## <a name="async-lambdas"></a><span data-ttu-id="ed8f7-149">异步 lambda</span><span class="sxs-lookup"><span data-stu-id="ed8f7-149">Async Lambdas</span></span>  
 <span data-ttu-id="ed8f7-150">您可以轻松创建 lambda 表达式和语句通过使用包含异步处理[异步](../../../../visual-basic/language-reference/modifiers/async.md)和[Await 运算符](../../../../visual-basic/language-reference/operators/await-operator.md)关键字。</span><span class="sxs-lookup"><span data-stu-id="ed8f7-150">You can easily create lambda expressions and statements that incorporate asynchronous processing by using the [Async](../../../../visual-basic/language-reference/modifiers/async.md) and [Await Operator](../../../../visual-basic/language-reference/operators/await-operator.md) keywords.</span></span> <span data-ttu-id="ed8f7-151">例如，下面的 Windows 窗体示例包含一个调用和等待异步方法 `ExampleMethodAsync`的事件处理程序。</span><span class="sxs-lookup"><span data-stu-id="ed8f7-151">For example, the following Windows Forms example contains an event handler that calls and awaits an async method, `ExampleMethodAsync`.</span></span>  
  
```vb  
Public Class Form1  
  
    Async Sub Button1_Click(sender As Object, e As EventArgs) Handles Button1.Click  
        ' ExampleMethodAsync returns a Task.  
        Await ExampleMethodAsync()  
        TextBox1.Text = vbCrLf & "Control returned to button1_Click."  
    End Sub  
  
    Async Function ExampleMethodAsync() As Task  
        ' The following line simulates a task-returning asynchronous process.  
        Await Task.Delay(1000)  
    End Function  
  
End Class  
```  
  
 <span data-ttu-id="ed8f7-152">可以通过使用在异步 lambda 添加同一事件处理程序[AddHandler 语句](../../../../visual-basic/language-reference/statements/addhandler-statement.md)。</span><span class="sxs-lookup"><span data-stu-id="ed8f7-152">You can add the same event handler by using an async lambda in an [AddHandler Statement](../../../../visual-basic/language-reference/statements/addhandler-statement.md).</span></span> <span data-ttu-id="ed8f7-153">若要添加此处理程序，请在 lambda 参数列表前添加一个 `Async` 修饰符，如下例所示。</span><span class="sxs-lookup"><span data-stu-id="ed8f7-153">To add this handler, add an `Async` modifier before the lambda parameter list, as the following example shows.</span></span>  
  
```vb  
Public Class Form1  
  
    Private Sub Form1_Load(sender As Object, e As EventArgs) Handles MyBase.Load  
        AddHandler Button1.Click,   
            Async Sub(sender1, e1)  
                ' ExampleMethodAsync returns a Task.  
                Await ExampleMethodAsync()  
                TextBox1.Text = vbCrLf & "Control returned to Button1_ Click."  
            End Sub  
    End Sub  
  
    Async Function ExampleMethodAsync() As Task  
        ' The following line simulates a task-returning asynchronous process.  
        Await Task.Delay(1000)  
    End Function  
  
End Class  
```  
  
 <span data-ttu-id="ed8f7-154">有关如何创建和使用异步方法的详细信息，请参阅[使用 Async 和 Await 的异步编程](../../../../visual-basic/programming-guide/concepts/async/index.md)。</span><span class="sxs-lookup"><span data-stu-id="ed8f7-154">For more information about how to create and use async methods, see [Asynchronous Programming with Async and Await](../../../../visual-basic/programming-guide/concepts/async/index.md).</span></span>  
  
##  <span data-ttu-id="ed8f7-155"><a name="context"></a>上下文</span><span class="sxs-lookup"><span data-stu-id="ed8f7-155"><a name="context"></a> Context</span></span>  
 <span data-ttu-id="ed8f7-156">Lambda 表达式与在其中定义的范围共享其上下文。</span><span class="sxs-lookup"><span data-stu-id="ed8f7-156">A lambda expression shares its context with the scope within which it is defined.</span></span> <span data-ttu-id="ed8f7-157">它具有相同的访问权限，在编写包含作用域中的任何代码。</span><span class="sxs-lookup"><span data-stu-id="ed8f7-157">It has the same access rights as any code written in the containing scope.</span></span> <span data-ttu-id="ed8f7-158">这包括对成员变量、 函数和子例程，访问`Me`，以及参数和包含作用域中的局部变量。</span><span class="sxs-lookup"><span data-stu-id="ed8f7-158">This includes access to member variables, functions and subs, `Me`, and parameters and local variables in the containing scope.</span></span>  
  
 <span data-ttu-id="ed8f7-159">包含作用域中的局部变量和参数的访问可以超出该范围的生存期。</span><span class="sxs-lookup"><span data-stu-id="ed8f7-159">Access to local variables and parameters in the containing scope can extend beyond the lifetime of that scope.</span></span> <span data-ttu-id="ed8f7-160">只要引用 lambda 表达式的委托不能进行垃圾回收，就将保留与原始环境中的变量的访问。</span><span class="sxs-lookup"><span data-stu-id="ed8f7-160">As long as a delegate referring to a lambda expression is not available to garbage collection, access to the variables in the original environment is retained.</span></span> <span data-ttu-id="ed8f7-161">在以下示例中，变量`target`本地`makeTheGame`的方法的 lambda 表达式`playTheGame`定义。</span><span class="sxs-lookup"><span data-stu-id="ed8f7-161">In the following example, variable `target` is local to `makeTheGame`, the method in which the lambda expression `playTheGame` is defined.</span></span> <span data-ttu-id="ed8f7-162">请注意，返回的 lambda 表达式中，分配给`takeAGuess`中`Main`，仍有权访问本地变量`target`。</span><span class="sxs-lookup"><span data-stu-id="ed8f7-162">Note that the returned lambda expression, assigned to `takeAGuess` in `Main`, still has access to the local variable `target`.</span></span>  
  
 <span data-ttu-id="ed8f7-163">[!code-vb[VbVbalrLambdas #&12;](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/lambda-expressions_5.vb)]</span><span class="sxs-lookup"><span data-stu-id="ed8f7-163">[!code-vb[VbVbalrLambdas#12](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/lambda-expressions_5.vb)]</span></span>  
  
 <span data-ttu-id="ed8f7-164">下面的示例演示了广泛的嵌套的 lambda 表达式的访问权限。</span><span class="sxs-lookup"><span data-stu-id="ed8f7-164">The following example demonstrates the wide range of access rights of the nested lambda expression.</span></span> <span data-ttu-id="ed8f7-165">返回的 lambda 表达式中的执行时`Main`作为`aDel`，它能够访问下列元素︰</span><span class="sxs-lookup"><span data-stu-id="ed8f7-165">When the returned lambda expression is executed from `Main` as `aDel`, it accesses these elements:</span></span>  
  
-   <span data-ttu-id="ed8f7-166">在其中定义的类的字段︰`aField`</span><span class="sxs-lookup"><span data-stu-id="ed8f7-166">A field of the class in which it is defined: `aField`</span></span>  
  
-   <span data-ttu-id="ed8f7-167">在其中定义的类的属性︰`aProp`</span><span class="sxs-lookup"><span data-stu-id="ed8f7-167">A property of the class in which it is defined: `aProp`</span></span>  
  
-   <span data-ttu-id="ed8f7-168">方法的一个参数`functionWithNestedLambda`，在其中定义︰`level1`</span><span class="sxs-lookup"><span data-stu-id="ed8f7-168">A parameter of method `functionWithNestedLambda`, in which it is defined: `level1`</span></span>  
  
-   <span data-ttu-id="ed8f7-169">本地变量`functionWithNestedLambda`:`localVar`</span><span class="sxs-lookup"><span data-stu-id="ed8f7-169">A local variable of `functionWithNestedLambda`: `localVar`</span></span>  
  
-   <span data-ttu-id="ed8f7-170">在其中嵌套 lambda 表达式的参数︰`level2`</span><span class="sxs-lookup"><span data-stu-id="ed8f7-170">A parameter of the lambda expression in which it is nested: `level2`</span></span>  
  
 <span data-ttu-id="ed8f7-171">[!code-vb[VbVbalrLambdas #&9;](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/lambda-expressions_6.vb)]</span><span class="sxs-lookup"><span data-stu-id="ed8f7-171">[!code-vb[VbVbalrLambdas#9](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/lambda-expressions_6.vb)]</span></span>  
  
## <a name="converting-to-a-delegate-type"></a><span data-ttu-id="ed8f7-172">将转换为委托类型</span><span class="sxs-lookup"><span data-stu-id="ed8f7-172">Converting to a Delegate Type</span></span>  
 <span data-ttu-id="ed8f7-173">Lambda 表达式可以隐式转换为兼容的委托类型。</span><span class="sxs-lookup"><span data-stu-id="ed8f7-173">A lambda expression can be implicitly converted to a compatible delegate type.</span></span> <span data-ttu-id="ed8f7-174">有关兼容性的常规要求的信息，请参阅[宽松委托转换](../../../../visual-basic/programming-guide/language-features/delegates/relaxed-delegate-conversion.md)。</span><span class="sxs-lookup"><span data-stu-id="ed8f7-174">For information about the general requirements for compatibility, see [Relaxed Delegate Conversion](../../../../visual-basic/programming-guide/language-features/delegates/relaxed-delegate-conversion.md).</span></span> <span data-ttu-id="ed8f7-175">例如，下面的代码示例显示了 lambda 表达式隐式转换为`Func(Of Integer, Boolean)`或匹配委托签名。</span><span class="sxs-lookup"><span data-stu-id="ed8f7-175">For example, the following code example shows a lambda expression that implicitly converts to `Func(Of Integer, Boolean)` or a matching delegate signature.</span></span>  
  
 <span data-ttu-id="ed8f7-176">[!code-vb[VbVbalrLambdas #&16;](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/lambda-expressions_7.vb)]</span><span class="sxs-lookup"><span data-stu-id="ed8f7-176">[!code-vb[VbVbalrLambdas#16](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/lambda-expressions_7.vb)]</span></span>  
  
 <span data-ttu-id="ed8f7-177">下面的代码示例显示了 lambda 表达式隐式转换为`Sub(Of Double, String, Double)`或匹配委托签名。</span><span class="sxs-lookup"><span data-stu-id="ed8f7-177">The following code example shows a lambda expression that implicitly converts to `Sub(Of Double, String, Double)` or a matching delegate signature.</span></span>  
  
 <span data-ttu-id="ed8f7-178">[!code-vb[VbVbalrLambdas 第&23;](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/lambda-expressions_8.vb)]</span><span class="sxs-lookup"><span data-stu-id="ed8f7-178">[!code-vb[VbVbalrLambdas#23](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/lambda-expressions_8.vb)]</span></span>  
  
 <span data-ttu-id="ed8f7-179">当将 lambda 表达式分配给的代理，或将它们作为参数传递给过程时，您可以指定参数名称，但省略其数据类型，以便从委托中获取的类型。</span><span class="sxs-lookup"><span data-stu-id="ed8f7-179">When you assign lambda expressions to delegates or pass them as arguments to procedures, you can specify the parameter names but omit their data types, letting the types be taken from the delegate.</span></span>  
  
## <a name="examples"></a><span data-ttu-id="ed8f7-180">示例</span><span class="sxs-lookup"><span data-stu-id="ed8f7-180">Examples</span></span>  
  
-   <span data-ttu-id="ed8f7-181">下面的示例定义返回的 lambda 表达式`True`如果可以为 null 的参数已被赋值，和`False`如果其值为`Nothing`。</span><span class="sxs-lookup"><span data-stu-id="ed8f7-181">The following example defines a lambda expression that returns `True` if the nullable argument has an assigned value, and `False` if its value is `Nothing`.</span></span>  
  
     <span data-ttu-id="ed8f7-182">[!code-vb[VbVbalrLambdas #&4;](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/lambda-expressions_9.vb)]</span><span class="sxs-lookup"><span data-stu-id="ed8f7-182">[!code-vb[VbVbalrLambdas#4](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/lambda-expressions_9.vb)]</span></span>  
  
-   <span data-ttu-id="ed8f7-183">下面的示例定义返回数组中的最后一个元素的索引的 lambda 表达式。</span><span class="sxs-lookup"><span data-stu-id="ed8f7-183">The following example defines a lambda expression that returns the index of the last element in an array.</span></span>  
  
     <span data-ttu-id="ed8f7-184">[!code-vb[VbVbalrLambdas #&5;](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/lambda-expressions_10.vb)]</span><span class="sxs-lookup"><span data-stu-id="ed8f7-184">[!code-vb[VbVbalrLambdas#5](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/lambda-expressions_10.vb)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ed8f7-185">另请参阅</span><span class="sxs-lookup"><span data-stu-id="ed8f7-185">See Also</span></span>  
 <span data-ttu-id="ed8f7-186">[过程](./index.md) </span><span class="sxs-lookup"><span data-stu-id="ed8f7-186">[Procedures](./index.md) </span></span>  
<span data-ttu-id="ed8f7-187"> [在 Visual Basic 中的 LINQ 简介](../../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md) </span><span class="sxs-lookup"><span data-stu-id="ed8f7-187"> [Introduction to LINQ in Visual Basic](../../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md) </span></span>  
<span data-ttu-id="ed8f7-188"> [委托](../../../../visual-basic/programming-guide/language-features/delegates/index.md) </span><span class="sxs-lookup"><span data-stu-id="ed8f7-188"> [Delegates](../../../../visual-basic/programming-guide/language-features/delegates/index.md) </span></span>  
<span data-ttu-id="ed8f7-189"> [Function 语句](../../../../visual-basic/language-reference/statements/function-statement.md) </span><span class="sxs-lookup"><span data-stu-id="ed8f7-189"> [Function Statement](../../../../visual-basic/language-reference/statements/function-statement.md) </span></span>  
<span data-ttu-id="ed8f7-190"> [Sub 语句](../../../../visual-basic/language-reference/statements/sub-statement.md) </span><span class="sxs-lookup"><span data-stu-id="ed8f7-190"> [Sub Statement](../../../../visual-basic/language-reference/statements/sub-statement.md) </span></span>  
<span data-ttu-id="ed8f7-191"> [可以为 null 的值类型](../../../../visual-basic/programming-guide/language-features/data-types/nullable-value-types.md) </span><span class="sxs-lookup"><span data-stu-id="ed8f7-191"> [Nullable Value Types](../../../../visual-basic/programming-guide/language-features/data-types/nullable-value-types.md) </span></span>  
<span data-ttu-id="ed8f7-192"> [如何︰ 将过程传递给在 Visual Basic 中的另一个过程](../../../../visual-basic/programming-guide/language-features/delegates/how-to-pass-procedures-to-another-procedure.md) </span><span class="sxs-lookup"><span data-stu-id="ed8f7-192"> [How to: Pass Procedures to Another Procedure in Visual Basic](../../../../visual-basic/programming-guide/language-features/delegates/how-to-pass-procedures-to-another-procedure.md) </span></span>  
<span data-ttu-id="ed8f7-193"> [如何︰ 创建 Lambda 表达式](./how-to-create-a-lambda-expression.md) </span><span class="sxs-lookup"><span data-stu-id="ed8f7-193"> [How to: Create a Lambda Expression](./how-to-create-a-lambda-expression.md) </span></span>  
<span data-ttu-id="ed8f7-194"> [宽松委托转换](../../../../visual-basic/programming-guide/language-features/delegates/relaxed-delegate-conversion.md)</span><span class="sxs-lookup"><span data-stu-id="ed8f7-194"> [Relaxed Delegate Conversion](../../../../visual-basic/programming-guide/language-features/delegates/relaxed-delegate-conversion.md)</span></span>

