---
title: Lambda 表达式
ms.date: 07/20/2015
f1_keywords:
- vb.LambdaFunction
helpviewer_keywords:
- functions [Visual Basic], lambda expressions
- lambda expressions [Visual Basic]
- expressions [Visual Basic], lambda
- inline functions [Visual Basic]
ms.assetid: 137064b0-3928-4bfa-ba71-c3f9cbd951e2
ms.openlocfilehash: 1827eb5630ed217527de25fc9d9c2bb8994b9aff
ms.sourcegitcommit: 99b153b93bf94d0fecf7c7bcecb58ac424dfa47c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/25/2020
ms.locfileid: "80249664"
---
# <a name="lambda-expressions-visual-basic"></a><span data-ttu-id="a04ed-102">Lambda 表达式 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="a04ed-102">Lambda Expressions (Visual Basic)</span></span>

<span data-ttu-id="a04ed-103">*lambda 表达式*是一个函数或子例程，没有名称，可以在委托有效的地方使用。</span><span class="sxs-lookup"><span data-stu-id="a04ed-103">A *lambda expression* is a function or subroutine without a name that can be used wherever a delegate is valid.</span></span> <span data-ttu-id="a04ed-104">Lambda 表达式可以是函数或子例程，可以是单行表达式或多行表达式。</span><span class="sxs-lookup"><span data-stu-id="a04ed-104">Lambda expressions can be functions or subroutines and can be single-line or multi-line.</span></span> <span data-ttu-id="a04ed-105">可以将值从当前作用域传递到 lambda 表达式。</span><span class="sxs-lookup"><span data-stu-id="a04ed-105">You can pass values from the current scope to a lambda expression.</span></span>

> [!NOTE]
> <span data-ttu-id="a04ed-106">该`RemoveHandler`语句是一个例外。</span><span class="sxs-lookup"><span data-stu-id="a04ed-106">The `RemoveHandler` statement is an exception.</span></span> <span data-ttu-id="a04ed-107">不能为 的委托参数传递 lambda 表达式`RemoveHandler`。</span><span class="sxs-lookup"><span data-stu-id="a04ed-107">You cannot pass a lambda expression in for the delegate parameter of `RemoveHandler`.</span></span>

<span data-ttu-id="a04ed-108">使用`Function`or`Sub`关键字创建 lambda 表达式，就像创建标准函数或子例程一样。</span><span class="sxs-lookup"><span data-stu-id="a04ed-108">You create lambda expressions by using the `Function` or `Sub` keyword, just as you create a standard function or subroutine.</span></span> <span data-ttu-id="a04ed-109">但是，lambda 表达式包含在语句中。</span><span class="sxs-lookup"><span data-stu-id="a04ed-109">However, lambda expressions are included in a statement.</span></span>

<span data-ttu-id="a04ed-110">下面的示例是 lambda 表达式，该表达式递增其参数并返回值。</span><span class="sxs-lookup"><span data-stu-id="a04ed-110">The following example is a lambda expression that increments its argument and returns the value.</span></span> <span data-ttu-id="a04ed-111">该示例显示了函数的单行和多行 lambda 表达式语法。</span><span class="sxs-lookup"><span data-stu-id="a04ed-111">The example shows both the single-line and multi-line lambda expression syntax for a function.</span></span>

[!code-vb[VbVbalrLambdas#14](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrLambdas/VB/Class1.vb#14)]

<span data-ttu-id="a04ed-112">下面的示例是 lambda 表达式，该表达式将值写入控制台。</span><span class="sxs-lookup"><span data-stu-id="a04ed-112">The following example is a lambda expression that writes a value to the console.</span></span> <span data-ttu-id="a04ed-113">该示例显示了子例程的单行和多行 lambda 表达式语法。</span><span class="sxs-lookup"><span data-stu-id="a04ed-113">The example shows both the single-line and multi-line lambda expression syntax for a subroutine.</span></span>

[!code-vb[VbVbalrLambdas#15](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrLambdas/VB/Class1.vb#15)]

<span data-ttu-id="a04ed-114">请注意，在前面的示例中，lambda 表达式被分配给一个变量名称。</span><span class="sxs-lookup"><span data-stu-id="a04ed-114">Notice that in the previous examples the lambda expressions are assigned to a variable name.</span></span> <span data-ttu-id="a04ed-115">每当引用变量时，都会调用 lambda 表达式。</span><span class="sxs-lookup"><span data-stu-id="a04ed-115">Whenever you refer to the variable, you invoke the lambda expression.</span></span> <span data-ttu-id="a04ed-116">您还可以同时声明和调用 lambda 表达式，如以下示例所示。</span><span class="sxs-lookup"><span data-stu-id="a04ed-116">You can also declare and invoke a lambda expression at the same time, as shown in the following example.</span></span>

[!code-vb[VbVbalrLambdas#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrLambdas/VB/Class1.vb#3)]

<span data-ttu-id="a04ed-117">lambda 表达式可以作为函数调用的值返回（如本主题后面的["上下文](#context)"部分中的示例中所示），也可以作为参数传递给采用委托类型的参数，如以下示例所示。</span><span class="sxs-lookup"><span data-stu-id="a04ed-117">A lambda expression can be returned as the value of a function call (as is shown in the example in the [Context](#context) section later in this topic), or passed in as an argument to a parameter that takes a delegate type, as shown in the following example.</span></span>

[!code-vb[VbVbalrLambdas#8](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrLambdas/VB/Class2.vb#8)]

## <a name="lambda-expression-syntax"></a><span data-ttu-id="a04ed-118">Lambda 表达式语法</span><span class="sxs-lookup"><span data-stu-id="a04ed-118">Lambda Expression Syntax</span></span>

<span data-ttu-id="a04ed-119">lambda 表达式的语法类似于标准函数或子例程的语法。</span><span class="sxs-lookup"><span data-stu-id="a04ed-119">The syntax of a lambda expression resembles that of a standard function or subroutine.</span></span> <span data-ttu-id="a04ed-120">不同之处如下：</span><span class="sxs-lookup"><span data-stu-id="a04ed-120">The differences are as follows:</span></span>

- <span data-ttu-id="a04ed-121">lambda 表达式没有名称。</span><span class="sxs-lookup"><span data-stu-id="a04ed-121">A lambda expression does not have a name.</span></span>

- <span data-ttu-id="a04ed-122">Lambda 表达式不能具有修饰符，如`Overloads`或`Overrides`。</span><span class="sxs-lookup"><span data-stu-id="a04ed-122">Lambda expressions cannot have modifiers, such as `Overloads` or `Overrides`.</span></span>

- <span data-ttu-id="a04ed-123">单行 lambda 函数不使用子句`As`来指定返回类型。</span><span class="sxs-lookup"><span data-stu-id="a04ed-123">Single-line lambda functions do not use an `As` clause to designate the return type.</span></span> <span data-ttu-id="a04ed-124">相反，类型是从 lambda 表达式的正文计算到的值推断的。</span><span class="sxs-lookup"><span data-stu-id="a04ed-124">Instead, the type is inferred from the value that the body of the lambda expression evaluates to.</span></span> <span data-ttu-id="a04ed-125">例如，如果 lambda 表达式的正文为`cust.City = "London"`，则其返回类型`Boolean`为 。</span><span class="sxs-lookup"><span data-stu-id="a04ed-125">For example, if the body of the lambda expression is `cust.City = "London"`, its return type is `Boolean`.</span></span>

- <span data-ttu-id="a04ed-126">在多行 lambda 函数中，可以使用`As`子句指定返回类型，或者省略`As`子句，以便推断返回类型。</span><span class="sxs-lookup"><span data-stu-id="a04ed-126">In multi-line lambda functions, you can either specify a return type by using an `As` clause, or omit the `As` clause so that the return type is inferred.</span></span> <span data-ttu-id="a04ed-127">当多`As`行 lambda 函数省略子句时，返回类型被推断为多行 lambda 函数中所有`Return`语句中的主要类型。</span><span class="sxs-lookup"><span data-stu-id="a04ed-127">When the `As` clause is omitted for a multi-line lambda function, the return type is inferred to be the dominant type from all the `Return` statements in the multi-line lambda function.</span></span> <span data-ttu-id="a04ed-128">*主导类型*是所有其他类型都可以扩展到的唯一类型。</span><span class="sxs-lookup"><span data-stu-id="a04ed-128">The *dominant type* is a unique type that all other types can widen to.</span></span> <span data-ttu-id="a04ed-129">如果无法确定此唯一类型，则主导类型是数组中所有其他类型都可以缩小到的唯一类型。</span><span class="sxs-lookup"><span data-stu-id="a04ed-129">If this unique type cannot be determined, the dominant type is the unique type that all other types in the array can narrow to.</span></span> <span data-ttu-id="a04ed-130">如果无法确定为这两种唯一类型之一，则基准类型是 `Object`。</span><span class="sxs-lookup"><span data-stu-id="a04ed-130">If neither of these unique types can be determined, the dominant type is `Object`.</span></span> <span data-ttu-id="a04ed-131">在这种情况下，如果`Option Strict`设置为`On`，则会发生编译器错误。</span><span class="sxs-lookup"><span data-stu-id="a04ed-131">In this case, if `Option Strict` is set to `On`, a compiler error occurs.</span></span>

     <span data-ttu-id="a04ed-132">例如`Return`，如果提供给语句的表达式包含 类型`Integer`的值 ，`Long`和`Double`， 生成的数组的类型`Double`为 。</span><span class="sxs-lookup"><span data-stu-id="a04ed-132">For example, if the expressions supplied to the `Return` statement contain values of type `Integer`, `Long`, and `Double`, the resulting array is of type `Double`.</span></span> <span data-ttu-id="a04ed-133">两`Integer`者`Long`加宽`Double`至和`Double`仅。</span><span class="sxs-lookup"><span data-stu-id="a04ed-133">Both `Integer` and `Long` widen to `Double` and only `Double`.</span></span> <span data-ttu-id="a04ed-134">因此， `Double` 是基准类型。</span><span class="sxs-lookup"><span data-stu-id="a04ed-134">Therefore, `Double` is the dominant type.</span></span> <span data-ttu-id="a04ed-135">有关详细信息，请参阅 [Widening and Narrowing Conversions](../../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md)。</span><span class="sxs-lookup"><span data-stu-id="a04ed-135">For more information, see [Widening and Narrowing Conversions](../../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md).</span></span>

- <span data-ttu-id="a04ed-136">单行函数的正文必须是返回值的表达式，而不是语句。</span><span class="sxs-lookup"><span data-stu-id="a04ed-136">The body of a single-line function must be an expression that returns a value, not a statement.</span></span> <span data-ttu-id="a04ed-137">单行函数`Return`没有语句。</span><span class="sxs-lookup"><span data-stu-id="a04ed-137">There is no `Return` statement for single-line functions.</span></span> <span data-ttu-id="a04ed-138">单行函数返回的值是函数正文中表达式的值。</span><span class="sxs-lookup"><span data-stu-id="a04ed-138">The value returned by the single-line function is the value of the expression in the body of the function.</span></span>

- <span data-ttu-id="a04ed-139">单行子例程的正文必须是单行语句。</span><span class="sxs-lookup"><span data-stu-id="a04ed-139">The body of a single-line subroutine must be single-line statement.</span></span>

- <span data-ttu-id="a04ed-140">单行函数和子例程不包括 或`End Function``End Sub`语句。</span><span class="sxs-lookup"><span data-stu-id="a04ed-140">Single-line functions and subroutines do not include an `End Function` or `End Sub` statement.</span></span>

- <span data-ttu-id="a04ed-141">可以使用`As`关键字指定 lambda 表达式参数的数据类型，也可以推断参数的数据类型。</span><span class="sxs-lookup"><span data-stu-id="a04ed-141">You can specify the data type of a lambda expression parameter by using the `As` keyword, or the data type of the parameter can be inferred.</span></span> <span data-ttu-id="a04ed-142">所有参数都必须具有指定的数据类型，或者必须推断所有参数。</span><span class="sxs-lookup"><span data-stu-id="a04ed-142">Either all parameters must have specified data types or all must be inferred.</span></span>

- <span data-ttu-id="a04ed-143">`Optional`不允许`Paramarray`和参数。</span><span class="sxs-lookup"><span data-stu-id="a04ed-143">`Optional` and `Paramarray` parameters are not permitted.</span></span>

- <span data-ttu-id="a04ed-144">不允许使用通用参数。</span><span class="sxs-lookup"><span data-stu-id="a04ed-144">Generic parameters are not permitted.</span></span>

## <a name="async-lambdas"></a><span data-ttu-id="a04ed-145">异步 lambda</span><span class="sxs-lookup"><span data-stu-id="a04ed-145">Async Lambdas</span></span>

<span data-ttu-id="a04ed-146">通过使用[Async](../../../../visual-basic/language-reference/modifiers/async.md)和[Await 运算符](../../../../visual-basic/language-reference/operators/await-operator.md)关键字，可以轻松地创建包含异步处理的 lambda 表达式和语句。</span><span class="sxs-lookup"><span data-stu-id="a04ed-146">You can easily create lambda expressions and statements that incorporate asynchronous processing by using the [Async](../../../../visual-basic/language-reference/modifiers/async.md) and [Await Operator](../../../../visual-basic/language-reference/operators/await-operator.md) keywords.</span></span> <span data-ttu-id="a04ed-147">例如，下面的 Windows 窗体示例包含一个调用和等待异步方法 `ExampleMethodAsync`的事件处理程序。</span><span class="sxs-lookup"><span data-stu-id="a04ed-147">For example, the following Windows Forms example contains an event handler that calls and awaits an async method, `ExampleMethodAsync`.</span></span>

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

<span data-ttu-id="a04ed-148">您可以通过在[AddHandler 语句](../../../../visual-basic/language-reference/statements/addhandler-statement.md)中使用异步 lambda 来添加相同的事件处理程序。</span><span class="sxs-lookup"><span data-stu-id="a04ed-148">You can add the same event handler by using an async lambda in an [AddHandler Statement](../../../../visual-basic/language-reference/statements/addhandler-statement.md).</span></span> <span data-ttu-id="a04ed-149">若要添加此处理程序，请在 lambda 参数列表前添加一个 `Async` 修饰符，如下例所示。</span><span class="sxs-lookup"><span data-stu-id="a04ed-149">To add this handler, add an `Async` modifier before the lambda parameter list, as the following example shows.</span></span>

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

<span data-ttu-id="a04ed-150">有关如何创建和使用异步方法的详细信息，请参阅[使用异步和 Await 进行异步编程](../../../../visual-basic/programming-guide/concepts/async/index.md)。</span><span class="sxs-lookup"><span data-stu-id="a04ed-150">For more information about how to create and use async methods, see [Asynchronous Programming with Async and Await](../../../../visual-basic/programming-guide/concepts/async/index.md).</span></span>

## <a name="context"></a><span data-ttu-id="a04ed-151">上下文</span><span class="sxs-lookup"><span data-stu-id="a04ed-151">Context</span></span>

<span data-ttu-id="a04ed-152">lambda 表达式与其定义上下文的范围共享上下文。</span><span class="sxs-lookup"><span data-stu-id="a04ed-152">A lambda expression shares its context with the scope within which it is defined.</span></span> <span data-ttu-id="a04ed-153">它具有与在包含作用域中编写的任何代码相同的访问权限。</span><span class="sxs-lookup"><span data-stu-id="a04ed-153">It has the same access rights as any code written in the containing scope.</span></span> <span data-ttu-id="a04ed-154">这包括访问包含作用域中的成员变量、函数和子以及`Me`参数和局部变量。</span><span class="sxs-lookup"><span data-stu-id="a04ed-154">This includes access to member variables, functions and subs, `Me`, and parameters and local variables in the containing scope.</span></span>

<span data-ttu-id="a04ed-155">对包含作用域中的局部变量和参数的访问可以超出该作用域的生存期。</span><span class="sxs-lookup"><span data-stu-id="a04ed-155">Access to local variables and parameters in the containing scope can extend beyond the lifetime of that scope.</span></span> <span data-ttu-id="a04ed-156">只要引用 lambda 表达式的委托不能用于垃圾回收，则将保留对原始环境中变量的访问。</span><span class="sxs-lookup"><span data-stu-id="a04ed-156">As long as a delegate referring to a lambda expression is not available to garbage collection, access to the variables in the original environment is retained.</span></span> <span data-ttu-id="a04ed-157">在下面的示例中，变量`target`是 局部的`makeTheGame`， 在 其中定义 lambda 表达式`playTheGame`的方法。</span><span class="sxs-lookup"><span data-stu-id="a04ed-157">In the following example, variable `target` is local to `makeTheGame`, the method in which the lambda expression `playTheGame` is defined.</span></span> <span data-ttu-id="a04ed-158">请注意，分配给`takeAGuess``Main`的返回 lambda 表达式仍有权访问局部变量`target`。</span><span class="sxs-lookup"><span data-stu-id="a04ed-158">Note that the returned lambda expression, assigned to `takeAGuess` in `Main`, still has access to the local variable `target`.</span></span>

[!code-vb[VbVbalrLambdas#12](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrLambdas/VB/Class6.vb#12)]

<span data-ttu-id="a04ed-159">下面的示例演示嵌套 lambda 表达式的广泛访问权限。</span><span class="sxs-lookup"><span data-stu-id="a04ed-159">The following example demonstrates the wide range of access rights of the nested lambda expression.</span></span> <span data-ttu-id="a04ed-160">当返回的 lambda 表达式从`Main``aDel`执行 时，它将访问以下元素：</span><span class="sxs-lookup"><span data-stu-id="a04ed-160">When the returned lambda expression is executed from `Main` as `aDel`, it accesses these elements:</span></span>

- <span data-ttu-id="a04ed-161">在其中定义它的类的字段：`aField`</span><span class="sxs-lookup"><span data-stu-id="a04ed-161">A field of the class in which it is defined: `aField`</span></span>

- <span data-ttu-id="a04ed-162">定义它的类的属性：`aProp`</span><span class="sxs-lookup"><span data-stu-id="a04ed-162">A property of the class in which it is defined: `aProp`</span></span>

- <span data-ttu-id="a04ed-163">方法`functionWithNestedLambda`的参数，`level1`</span><span class="sxs-lookup"><span data-stu-id="a04ed-163">A parameter of method `functionWithNestedLambda`, in which it is defined: `level1`</span></span>

- <span data-ttu-id="a04ed-164">的`functionWithNestedLambda`局部变量：`localVar`</span><span class="sxs-lookup"><span data-stu-id="a04ed-164">A local variable of `functionWithNestedLambda`: `localVar`</span></span>

- <span data-ttu-id="a04ed-165">嵌套在 lambda 表达式中的参数：`level2`</span><span class="sxs-lookup"><span data-stu-id="a04ed-165">A parameter of the lambda expression in which it is nested: `level2`</span></span>

 [!code-vb[VbVbalrLambdas#9](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrLambdas/VB/Class3.vb#9)]

## <a name="converting-to-a-delegate-type"></a><span data-ttu-id="a04ed-166">转换为委托类型</span><span class="sxs-lookup"><span data-stu-id="a04ed-166">Converting to a Delegate Type</span></span>

<span data-ttu-id="a04ed-167">lambda 表达式可以隐式转换为兼容的委托类型。</span><span class="sxs-lookup"><span data-stu-id="a04ed-167">A lambda expression can be implicitly converted to a compatible delegate type.</span></span> <span data-ttu-id="a04ed-168">有关兼容性的一般要求的信息，请参阅[放宽委托转换](../../../../visual-basic/programming-guide/language-features/delegates/relaxed-delegate-conversion.md)。</span><span class="sxs-lookup"><span data-stu-id="a04ed-168">For information about the general requirements for compatibility, see [Relaxed Delegate Conversion](../../../../visual-basic/programming-guide/language-features/delegates/relaxed-delegate-conversion.md).</span></span> <span data-ttu-id="a04ed-169">例如，以下代码示例显示隐式转换为`Func(Of Integer, Boolean)`或匹配委托签名的 lambda 表达式。</span><span class="sxs-lookup"><span data-stu-id="a04ed-169">For example, the following code example shows a lambda expression that implicitly converts to `Func(Of Integer, Boolean)` or a matching delegate signature.</span></span>

[!code-vb[VbVbalrLambdas#16](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrLambdas/VB/Class1.vb#16)]

<span data-ttu-id="a04ed-170">下面的代码示例显示隐式转换为`Sub(Of Double, String, Double)`或匹配委托签名的 lambda 表达式。</span><span class="sxs-lookup"><span data-stu-id="a04ed-170">The following code example shows a lambda expression that implicitly converts to `Sub(Of Double, String, Double)` or a matching delegate signature.</span></span>

[!code-vb[VbVbalrLambdas#23](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrLambdas/VB/class7.vb#23)]

<span data-ttu-id="a04ed-171">将 lambda 表达式分配给委托或将它们作为参数传递给过程时，可以指定参数名称，但省略其数据类型，允许从委托获取类型。</span><span class="sxs-lookup"><span data-stu-id="a04ed-171">When you assign lambda expressions to delegates or pass them as arguments to procedures, you can specify the parameter names but omit their data types, letting the types be taken from the delegate.</span></span>

## <a name="examples"></a><span data-ttu-id="a04ed-172">示例</span><span class="sxs-lookup"><span data-stu-id="a04ed-172">Examples</span></span>

- <span data-ttu-id="a04ed-173">下面的示例定义 lambda 表达式，如果空`True`值类型参数具有赋值，并且`False`其值为`Nothing`，则返回该表达式。</span><span class="sxs-lookup"><span data-stu-id="a04ed-173">The following example defines a lambda expression that returns `True` if the nullable value type argument has an assigned value, and `False` if its value is `Nothing`.</span></span>

     [!code-vb[VbVbalrLambdas#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrLambdas/VB/Class1.vb#4)]

- <span data-ttu-id="a04ed-174">下面的示例定义一个 lambda 表达式，该表达式返回数组中最后一个元素的索引。</span><span class="sxs-lookup"><span data-stu-id="a04ed-174">The following example defines a lambda expression that returns the index of the last element in an array.</span></span>

     [!code-vb[VbVbalrLambdas#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrLambdas/VB/Class1.vb#5)]

## <a name="see-also"></a><span data-ttu-id="a04ed-175">请参阅</span><span class="sxs-lookup"><span data-stu-id="a04ed-175">See also</span></span>

- [<span data-ttu-id="a04ed-176">过程</span><span class="sxs-lookup"><span data-stu-id="a04ed-176">Procedures</span></span>](./index.md)
- [<span data-ttu-id="a04ed-177">Visual Basic 中的 LINQ 简介</span><span class="sxs-lookup"><span data-stu-id="a04ed-177">Introduction to LINQ in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)
- [<span data-ttu-id="a04ed-178">委托</span><span class="sxs-lookup"><span data-stu-id="a04ed-178">Delegates</span></span>](../../../../visual-basic/programming-guide/language-features/delegates/index.md)
- [<span data-ttu-id="a04ed-179">Function 语句</span><span class="sxs-lookup"><span data-stu-id="a04ed-179">Function Statement</span></span>](../../../../visual-basic/language-reference/statements/function-statement.md)
- [<span data-ttu-id="a04ed-180">Sub 语句</span><span class="sxs-lookup"><span data-stu-id="a04ed-180">Sub Statement</span></span>](../../../../visual-basic/language-reference/statements/sub-statement.md)
- [<span data-ttu-id="a04ed-181">可以为 null 的值类型</span><span class="sxs-lookup"><span data-stu-id="a04ed-181">Nullable Value Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/nullable-value-types.md)
- [<span data-ttu-id="a04ed-182">如何：在 Visual Basic 中将过程传递给另一过程</span><span class="sxs-lookup"><span data-stu-id="a04ed-182">How to: Pass Procedures to Another Procedure in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/delegates/how-to-pass-procedures-to-another-procedure.md)
- [<span data-ttu-id="a04ed-183">如何：创建 lambda 表达式</span><span class="sxs-lookup"><span data-stu-id="a04ed-183">How to: Create a Lambda Expression</span></span>](./how-to-create-a-lambda-expression.md)
- [<span data-ttu-id="a04ed-184">宽松委托转换</span><span class="sxs-lookup"><span data-stu-id="a04ed-184">Relaxed Delegate Conversion</span></span>](../../../../visual-basic/programming-guide/language-features/delegates/relaxed-delegate-conversion.md)
