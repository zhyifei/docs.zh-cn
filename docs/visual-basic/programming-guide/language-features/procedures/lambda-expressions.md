---
title: Lambda 表达式 (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.LambdaFunction
helpviewer_keywords:
- functions [Visual Basic], lambda expressions
- lambda expressions [Visual Basic]
- expressions [Visual Basic], lambda
- inline functions [Visual Basic]
ms.assetid: 137064b0-3928-4bfa-ba71-c3f9cbd951e2
ms.openlocfilehash: 02377b0765144064df8d51fa63768412ca4b606a
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/05/2019
ms.locfileid: "57363471"
---
# <a name="lambda-expressions-visual-basic"></a><span data-ttu-id="e258e-102">Lambda 表达式 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="e258e-102">Lambda Expressions (Visual Basic)</span></span>
<span data-ttu-id="e258e-103">一个*lambda 表达式*是函数或子例程没有可用于任何委托是有效的名称。</span><span class="sxs-lookup"><span data-stu-id="e258e-103">A *lambda expression* is a function or subroutine without a name that can be used wherever a delegate is valid.</span></span> <span data-ttu-id="e258e-104">Lambda 表达式可以是函数或子例程，并且可以是单行或多行。</span><span class="sxs-lookup"><span data-stu-id="e258e-104">Lambda expressions can be functions or subroutines and can be single-line or multi-line.</span></span> <span data-ttu-id="e258e-105">可以将值从当前作用域传递到 lambda 表达式中。</span><span class="sxs-lookup"><span data-stu-id="e258e-105">You can pass values from the current scope to a lambda expression.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="e258e-106">`RemoveHandler`语句是一个例外。</span><span class="sxs-lookup"><span data-stu-id="e258e-106">The `RemoveHandler` statement is an exception.</span></span> <span data-ttu-id="e258e-107">不能将传递的委托参数的 lambda 表达式中`RemoveHandler`。</span><span class="sxs-lookup"><span data-stu-id="e258e-107">You cannot pass a lambda expression in for the delegate parameter of `RemoveHandler`.</span></span>  
  
 <span data-ttu-id="e258e-108">使用创建 lambda 表达式`Function`或`Sub`关键字，就像创建标准函数或子例程。</span><span class="sxs-lookup"><span data-stu-id="e258e-108">You create lambda expressions by using the `Function` or `Sub` keyword, just as you create a standard function or subroutine.</span></span> <span data-ttu-id="e258e-109">但是，lambda 表达式包含在一个语句。</span><span class="sxs-lookup"><span data-stu-id="e258e-109">However, lambda expressions are included in a statement.</span></span>  
  
 <span data-ttu-id="e258e-110">下面的示例是递增其参数和返回值的 lambda 表达式。</span><span class="sxs-lookup"><span data-stu-id="e258e-110">The following example is a lambda expression that increments its argument and returns the value.</span></span> <span data-ttu-id="e258e-111">该示例显示了函数的这两个单行和多行 lambda 表达式语法。</span><span class="sxs-lookup"><span data-stu-id="e258e-111">The example shows both the single-line and multi-line lambda expression syntax for a function.</span></span>  
  
 [!code-vb[VbVbalrLambdas#14](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrLambdas/VB/Class1.vb#14)]  
  
 <span data-ttu-id="e258e-112">下面的示例是向控制台写入值的 lambda 表达式。</span><span class="sxs-lookup"><span data-stu-id="e258e-112">The following example is a lambda expression that writes a value to the console.</span></span> <span data-ttu-id="e258e-113">该示例显示了一个子例程的这两个单行和多行 lambda 表达式语法。</span><span class="sxs-lookup"><span data-stu-id="e258e-113">The example shows both the single-line and multi-line lambda expression syntax for a subroutine.</span></span>  
  
 [!code-vb[VbVbalrLambdas#15](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrLambdas/VB/Class1.vb#15)]  
  
 <span data-ttu-id="e258e-114">请注意，在前面的示例中的 lambda 表达式将分配给变量的名称。</span><span class="sxs-lookup"><span data-stu-id="e258e-114">Notice that in the previous examples the lambda expressions are assigned to a variable name.</span></span> <span data-ttu-id="e258e-115">引用的变量，每当您调用 lambda 表达式。</span><span class="sxs-lookup"><span data-stu-id="e258e-115">Whenever you refer to the variable, you invoke the lambda expression.</span></span> <span data-ttu-id="e258e-116">您可以声明和调用 lambda 表达式在相同时，如下面的示例中所示。</span><span class="sxs-lookup"><span data-stu-id="e258e-116">You can also declare and invoke a lambda expression at the same time, as shown in the following example.</span></span>  
  
 [!code-vb[VbVbalrLambdas#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrLambdas/VB/Class1.vb#3)]  
  
 <span data-ttu-id="e258e-117">Lambda 表达式可以返回作为函数调用的值 (如示例中所示[上下文](#context)本主题后面的部分)，或作为参数传递给参数接受一个委托类型，如以下所示示例。</span><span class="sxs-lookup"><span data-stu-id="e258e-117">A lambda expression can be returned as the value of a function call (as is shown in the example in the [Context](#context) section later in this topic), or passed in as an argument to a parameter that takes a delegate type, as shown in the following example.</span></span>  
  
 [!code-vb[VbVbalrLambdas#8](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrLambdas/VB/Class2.vb#8)]  
  
## <a name="lambda-expression-syntax"></a><span data-ttu-id="e258e-118">Lambda 表达式语法</span><span class="sxs-lookup"><span data-stu-id="e258e-118">Lambda Expression Syntax</span></span>  
 <span data-ttu-id="e258e-119">Lambda 表达式的语法类似于标准函数或子例程。</span><span class="sxs-lookup"><span data-stu-id="e258e-119">The syntax of a lambda expression resembles that of a standard function or subroutine.</span></span> <span data-ttu-id="e258e-120">差异如下所示：</span><span class="sxs-lookup"><span data-stu-id="e258e-120">The differences are as follows:</span></span>  
  
-   <span data-ttu-id="e258e-121">Lambda 表达式没有名称。</span><span class="sxs-lookup"><span data-stu-id="e258e-121">A lambda expression does not have a name.</span></span>  
  
-   <span data-ttu-id="e258e-122">Lambda 表达式不能有修饰符，如`Overloads`或`Overrides`。</span><span class="sxs-lookup"><span data-stu-id="e258e-122">Lambda expressions cannot have modifiers, such as `Overloads` or `Overrides`.</span></span>  
  
-   <span data-ttu-id="e258e-123">单行 lambda 函数不使用`As`子句指定返回类型。</span><span class="sxs-lookup"><span data-stu-id="e258e-123">Single-line lambda functions do not use an `As` clause to designate the return type.</span></span> <span data-ttu-id="e258e-124">相反，从 lambda 表达式的主体的计算结果为的值推断类型。</span><span class="sxs-lookup"><span data-stu-id="e258e-124">Instead, the type is inferred from the value that the body of the lambda expression evaluates to.</span></span> <span data-ttu-id="e258e-125">例如，如果 lambda 表达式的正文`cust.City = "London"`，其返回类型是`Boolean`。</span><span class="sxs-lookup"><span data-stu-id="e258e-125">For example, if the body of the lambda expression is `cust.City = "London"`, its return type is `Boolean`.</span></span>  
  
-   <span data-ttu-id="e258e-126">在多行 lambda 函数中，您也可以指定返回类型通过使用`As`子句，或忽略`As`子句，以便推断返回类型。</span><span class="sxs-lookup"><span data-stu-id="e258e-126">In multi-line lambda functions, you can either specify a return type by using an `As` clause, or omit the `As` clause so that the return type is inferred.</span></span> <span data-ttu-id="e258e-127">当`As`子句省略对于多行 lambda 函数、 返回类型被推断为从所有的基准类型`Return`中多行 lambda 函数的语句。</span><span class="sxs-lookup"><span data-stu-id="e258e-127">When the `As` clause is omitted for a multi-line lambda function, the return type is inferred to be the dominant type from all the `Return` statements in the multi-line lambda function.</span></span> <span data-ttu-id="e258e-128">*基准类型*是所有其他类型可以扩大到的唯一类型。</span><span class="sxs-lookup"><span data-stu-id="e258e-128">The *dominant type* is a unique type that all other types can widen to.</span></span> <span data-ttu-id="e258e-129">如果无法确定此唯一类型，基准类型是数组中的所有其他类型可以缩小到的唯一类型。</span><span class="sxs-lookup"><span data-stu-id="e258e-129">If this unique type cannot be determined, the dominant type is the unique type that all other types in the array can narrow to.</span></span> <span data-ttu-id="e258e-130">如果无法确定为这两种唯一类型之一，则基准类型是 `Object`。</span><span class="sxs-lookup"><span data-stu-id="e258e-130">If neither of these unique types can be determined, the dominant type is `Object`.</span></span> <span data-ttu-id="e258e-131">在这种情况下，如果`Option Strict`设置为`On`，会发生编译器错误。</span><span class="sxs-lookup"><span data-stu-id="e258e-131">In this case, if `Option Strict` is set to `On`, a compiler error occurs.</span></span>  
  
     <span data-ttu-id="e258e-132">例如，如果表达式提供给`Return`语句包含类型的值`Integer`， `Long`，和`Double`，生成的数组类型是`Double`。</span><span class="sxs-lookup"><span data-stu-id="e258e-132">For example, if the expressions supplied to the `Return` statement contain values of type `Integer`, `Long`, and `Double`, the resulting array is of type `Double`.</span></span> <span data-ttu-id="e258e-133">这两`Integer`并`Long`扩大到`Double`和仅`Double`。</span><span class="sxs-lookup"><span data-stu-id="e258e-133">Both `Integer` and `Long` widen to `Double` and only `Double`.</span></span> <span data-ttu-id="e258e-134">因此， `Double` 是基准类型。</span><span class="sxs-lookup"><span data-stu-id="e258e-134">Therefore, `Double` is the dominant type.</span></span> <span data-ttu-id="e258e-135">有关详细信息，请参阅 [Widening and Narrowing Conversions](../../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md)。</span><span class="sxs-lookup"><span data-stu-id="e258e-135">For more information, see [Widening and Narrowing Conversions](../../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md).</span></span>  
  
-   <span data-ttu-id="e258e-136">单行函数的主体必须是返回一个值，而不是语句表达式。</span><span class="sxs-lookup"><span data-stu-id="e258e-136">The body of a single-line function must be an expression that returns a value, not a statement.</span></span> <span data-ttu-id="e258e-137">没有任何`Return`单行函数的语句。</span><span class="sxs-lookup"><span data-stu-id="e258e-137">There is no `Return` statement for single-line functions.</span></span> <span data-ttu-id="e258e-138">单行函数返回的值是表达式的函数的正文中的值。</span><span class="sxs-lookup"><span data-stu-id="e258e-138">The value returned by the single-line function is the value of the expression in the body of the function.</span></span>  
  
-   <span data-ttu-id="e258e-139">单行子例程的主体必须是单行语句。</span><span class="sxs-lookup"><span data-stu-id="e258e-139">The body of a single-line subroutine must be single-line statement.</span></span>  
  
-   <span data-ttu-id="e258e-140">不包括的单行函数和子例程`End Function`或`End Sub`语句。</span><span class="sxs-lookup"><span data-stu-id="e258e-140">Single-line functions and subroutines do not include an `End Function` or `End Sub` statement.</span></span>  
  
-   <span data-ttu-id="e258e-141">可以通过使用指定的 lambda 表达式参数的数据类型`As`关键字或该参数的数据类型可以推断出。</span><span class="sxs-lookup"><span data-stu-id="e258e-141">You can specify the data type of a lambda expression parameter by using the `As` keyword, or the data type of the parameter can be inferred.</span></span> <span data-ttu-id="e258e-142">必须必须推断数据类型或全部指定或者所有参数。</span><span class="sxs-lookup"><span data-stu-id="e258e-142">Either all parameters must have specified data types or all must be inferred.</span></span>  
  
-   <span data-ttu-id="e258e-143">`Optional` 和`Paramarray`不允许使用参数。</span><span class="sxs-lookup"><span data-stu-id="e258e-143">`Optional` and `Paramarray` parameters are not permitted.</span></span>  
  
-   <span data-ttu-id="e258e-144">不允许使用泛型参数。</span><span class="sxs-lookup"><span data-stu-id="e258e-144">Generic parameters are not permitted.</span></span>  
  
## <a name="async-lambdas"></a><span data-ttu-id="e258e-145">异步 lambda</span><span class="sxs-lookup"><span data-stu-id="e258e-145">Async Lambdas</span></span>  
 <span data-ttu-id="e258e-146">您可以轻松创建的包含异步处理通过使用 lambda 表达式和语句[异步](../../../../visual-basic/language-reference/modifiers/async.md)并[Await 运算符](../../../../visual-basic/language-reference/operators/await-operator.md)关键字。</span><span class="sxs-lookup"><span data-stu-id="e258e-146">You can easily create lambda expressions and statements that incorporate asynchronous processing by using the [Async](../../../../visual-basic/language-reference/modifiers/async.md) and [Await Operator](../../../../visual-basic/language-reference/operators/await-operator.md) keywords.</span></span> <span data-ttu-id="e258e-147">例如，下面的 Windows 窗体示例包含一个调用和等待异步方法 `ExampleMethodAsync`的事件处理程序。</span><span class="sxs-lookup"><span data-stu-id="e258e-147">For example, the following Windows Forms example contains an event handler that calls and awaits an async method, `ExampleMethodAsync`.</span></span>  
  
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
  
 <span data-ttu-id="e258e-148">可以通过使用在异步 lambda 添加同一事件处理程序[AddHandler 语句](../../../../visual-basic/language-reference/statements/addhandler-statement.md)。</span><span class="sxs-lookup"><span data-stu-id="e258e-148">You can add the same event handler by using an async lambda in an [AddHandler Statement](../../../../visual-basic/language-reference/statements/addhandler-statement.md).</span></span> <span data-ttu-id="e258e-149">若要添加此处理程序，请在 lambda 参数列表前添加一个 `Async` 修饰符，如下例所示。</span><span class="sxs-lookup"><span data-stu-id="e258e-149">To add this handler, add an `Async` modifier before the lambda parameter list, as the following example shows.</span></span>  
  
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
  
 <span data-ttu-id="e258e-150">有关如何创建和使用异步方法的详细信息，请参阅[使用 Async 和 Await 的异步编程](../../../../visual-basic/programming-guide/concepts/async/index.md)。</span><span class="sxs-lookup"><span data-stu-id="e258e-150">For more information about how to create and use async methods, see [Asynchronous Programming with Async and Await](../../../../visual-basic/programming-guide/concepts/async/index.md).</span></span>  
  
## <a name="context"></a> <span data-ttu-id="e258e-151">上下文</span><span class="sxs-lookup"><span data-stu-id="e258e-151">Context</span></span>  
 <span data-ttu-id="e258e-152">Lambda 表达式与在其中定义它的作用域共享其上下文。</span><span class="sxs-lookup"><span data-stu-id="e258e-152">A lambda expression shares its context with the scope within which it is defined.</span></span> <span data-ttu-id="e258e-153">它具有与包含作用域中编写任何代码的相同访问权限。</span><span class="sxs-lookup"><span data-stu-id="e258e-153">It has the same access rights as any code written in the containing scope.</span></span> <span data-ttu-id="e258e-154">这包括访问成员变量、 函数和子例程， `Me`，包含作用域中的局部变量和参数。</span><span class="sxs-lookup"><span data-stu-id="e258e-154">This includes access to member variables, functions and subs, `Me`, and parameters and local variables in the containing scope.</span></span>  
  
 <span data-ttu-id="e258e-155">访问本地变量和参数中包含的作用域可以扩展该作用域生存期。</span><span class="sxs-lookup"><span data-stu-id="e258e-155">Access to local variables and parameters in the containing scope can extend beyond the lifetime of that scope.</span></span> <span data-ttu-id="e258e-156">只要引用 lambda 表达式的委托不能进行垃圾回收，会保留在原始环境变量的访问权限。</span><span class="sxs-lookup"><span data-stu-id="e258e-156">As long as a delegate referring to a lambda expression is not available to garbage collection, access to the variables in the original environment is retained.</span></span> <span data-ttu-id="e258e-157">在以下示例中，变量`target`本地`makeTheGame`，在其中的方法的 lambda 表达式`playTheGame`定义。</span><span class="sxs-lookup"><span data-stu-id="e258e-157">In the following example, variable `target` is local to `makeTheGame`, the method in which the lambda expression `playTheGame` is defined.</span></span> <span data-ttu-id="e258e-158">请注意，返回的 lambda 表达式中，分配给`takeAGuess`中`Main`，仍有权访问本地变量`target`。</span><span class="sxs-lookup"><span data-stu-id="e258e-158">Note that the returned lambda expression, assigned to `takeAGuess` in `Main`, still has access to the local variable `target`.</span></span>  
  
 [!code-vb[VbVbalrLambdas#12](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrLambdas/VB/Class6.vb#12)]  
  
 <span data-ttu-id="e258e-159">下面的示例演示了广泛的嵌套的 lambda 表达式的访问权限。</span><span class="sxs-lookup"><span data-stu-id="e258e-159">The following example demonstrates the wide range of access rights of the nested lambda expression.</span></span> <span data-ttu-id="e258e-160">从执行返回的 lambda 表达式时`Main`作为`aDel`，它将访问这些元素：</span><span class="sxs-lookup"><span data-stu-id="e258e-160">When the returned lambda expression is executed from `Main` as `aDel`, it accesses these elements:</span></span>  
  
-   <span data-ttu-id="e258e-161">在其中定义类的字段： `aField`</span><span class="sxs-lookup"><span data-stu-id="e258e-161">A field of the class in which it is defined: `aField`</span></span>  
  
-   <span data-ttu-id="e258e-162">在其中定义类的一个属性： `aProp`</span><span class="sxs-lookup"><span data-stu-id="e258e-162">A property of the class in which it is defined: `aProp`</span></span>  
  
-   <span data-ttu-id="e258e-163">方法的参数`functionWithNestedLambda`，在其中定义： `level1`</span><span class="sxs-lookup"><span data-stu-id="e258e-163">A parameter of method `functionWithNestedLambda`, in which it is defined: `level1`</span></span>  
  
-   <span data-ttu-id="e258e-164">局部变量的`functionWithNestedLambda`: `localVar`</span><span class="sxs-lookup"><span data-stu-id="e258e-164">A local variable of `functionWithNestedLambda`: `localVar`</span></span>  
  
-   <span data-ttu-id="e258e-165">在其中嵌套 lambda 表达式的参数： `level2`</span><span class="sxs-lookup"><span data-stu-id="e258e-165">A parameter of the lambda expression in which it is nested: `level2`</span></span>  
  
 [!code-vb[VbVbalrLambdas#9](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrLambdas/VB/Class3.vb#9)]  
  
## <a name="converting-to-a-delegate-type"></a><span data-ttu-id="e258e-166">将转换为委托类型</span><span class="sxs-lookup"><span data-stu-id="e258e-166">Converting to a Delegate Type</span></span>  
 <span data-ttu-id="e258e-167">Lambda 表达式可以隐式转换为兼容的委托类型。</span><span class="sxs-lookup"><span data-stu-id="e258e-167">A lambda expression can be implicitly converted to a compatible delegate type.</span></span> <span data-ttu-id="e258e-168">有关兼容性的一般要求的信息，请参阅[宽松委托转换](../../../../visual-basic/programming-guide/language-features/delegates/relaxed-delegate-conversion.md)。</span><span class="sxs-lookup"><span data-stu-id="e258e-168">For information about the general requirements for compatibility, see [Relaxed Delegate Conversion](../../../../visual-basic/programming-guide/language-features/delegates/relaxed-delegate-conversion.md).</span></span> <span data-ttu-id="e258e-169">例如，下面的代码示例显示了 lambda 表达式隐式转换为`Func(Of Integer, Boolean)`或匹配的委托签名。</span><span class="sxs-lookup"><span data-stu-id="e258e-169">For example, the following code example shows a lambda expression that implicitly converts to `Func(Of Integer, Boolean)` or a matching delegate signature.</span></span>  
  
 [!code-vb[VbVbalrLambdas#16](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrLambdas/VB/Class1.vb#16)]  
  
 <span data-ttu-id="e258e-170">下面的代码示例显示了 lambda 表达式隐式转换为`Sub(Of Double, String, Double)`或匹配的委托签名。</span><span class="sxs-lookup"><span data-stu-id="e258e-170">The following code example shows a lambda expression that implicitly converts to `Sub(Of Double, String, Double)` or a matching delegate signature.</span></span>  
  
 [!code-vb[VbVbalrLambdas#23](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrLambdas/VB/class7.vb#23)]  
  
 <span data-ttu-id="e258e-171">当您将 lambda 表达式分配给委托，或将它们作为参数传递给过程时，可以指定参数名称，但省略其数据类型，以便从委托中获取的类型。</span><span class="sxs-lookup"><span data-stu-id="e258e-171">When you assign lambda expressions to delegates or pass them as arguments to procedures, you can specify the parameter names but omit their data types, letting the types be taken from the delegate.</span></span>  
  
## <a name="examples"></a><span data-ttu-id="e258e-172">示例</span><span class="sxs-lookup"><span data-stu-id="e258e-172">Examples</span></span>  
  
-   <span data-ttu-id="e258e-173">下面的示例定义返回的 lambda 表达式`True`如果可以为 null 的参数分配的值，并`False`如果其值为`Nothing`。</span><span class="sxs-lookup"><span data-stu-id="e258e-173">The following example defines a lambda expression that returns `True` if the nullable argument has an assigned value, and `False` if its value is `Nothing`.</span></span>  
  
     [!code-vb[VbVbalrLambdas#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrLambdas/VB/Class1.vb#4)]  
  
-   <span data-ttu-id="e258e-174">下面的示例定义返回数组中的最后一个元素索引的 lambda 表达式。</span><span class="sxs-lookup"><span data-stu-id="e258e-174">The following example defines a lambda expression that returns the index of the last element in an array.</span></span>  
  
     [!code-vb[VbVbalrLambdas#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrLambdas/VB/Class1.vb#5)]  
  
## <a name="see-also"></a><span data-ttu-id="e258e-175">请参阅</span><span class="sxs-lookup"><span data-stu-id="e258e-175">See also</span></span>
- [<span data-ttu-id="e258e-176">过程</span><span class="sxs-lookup"><span data-stu-id="e258e-176">Procedures</span></span>](./index.md)
- [<span data-ttu-id="e258e-177">Visual Basic 中的 LINQ 简介</span><span class="sxs-lookup"><span data-stu-id="e258e-177">Introduction to LINQ in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)
- [<span data-ttu-id="e258e-178">委托</span><span class="sxs-lookup"><span data-stu-id="e258e-178">Delegates</span></span>](../../../../visual-basic/programming-guide/language-features/delegates/index.md)
- [<span data-ttu-id="e258e-179">Function 语句</span><span class="sxs-lookup"><span data-stu-id="e258e-179">Function Statement</span></span>](../../../../visual-basic/language-reference/statements/function-statement.md)
- [<span data-ttu-id="e258e-180">Sub 语句</span><span class="sxs-lookup"><span data-stu-id="e258e-180">Sub Statement</span></span>](../../../../visual-basic/language-reference/statements/sub-statement.md)
- [<span data-ttu-id="e258e-181">可以为 null 的值类型</span><span class="sxs-lookup"><span data-stu-id="e258e-181">Nullable Value Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/nullable-value-types.md)
- [<span data-ttu-id="e258e-182">如何：将过程传递给 Visual Basic 中的另一个过程</span><span class="sxs-lookup"><span data-stu-id="e258e-182">How to: Pass Procedures to Another Procedure in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/delegates/how-to-pass-procedures-to-another-procedure.md)
- [<span data-ttu-id="e258e-183">如何：创建一个 Lambda 表达式</span><span class="sxs-lookup"><span data-stu-id="e258e-183">How to: Create a Lambda Expression</span></span>](./how-to-create-a-lambda-expression.md)
- [<span data-ttu-id="e258e-184">宽松委托转换</span><span class="sxs-lookup"><span data-stu-id="e258e-184">Relaxed Delegate Conversion</span></span>](../../../../visual-basic/programming-guide/language-features/delegates/relaxed-delegate-conversion.md)
