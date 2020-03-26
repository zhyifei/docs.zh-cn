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
# <a name="lambda-expressions-visual-basic"></a>Lambda 表达式 (Visual Basic)

*lambda 表达式*是一个函数或子例程，没有名称，可以在委托有效的地方使用。 Lambda 表达式可以是函数或子例程，可以是单行表达式或多行表达式。 可以将值从当前作用域传递到 lambda 表达式。

> [!NOTE]
> 该`RemoveHandler`语句是一个例外。 不能为 的委托参数传递 lambda 表达式`RemoveHandler`。

使用`Function`or`Sub`关键字创建 lambda 表达式，就像创建标准函数或子例程一样。 但是，lambda 表达式包含在语句中。

下面的示例是 lambda 表达式，该表达式递增其参数并返回值。 该示例显示了函数的单行和多行 lambda 表达式语法。

[!code-vb[VbVbalrLambdas#14](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrLambdas/VB/Class1.vb#14)]

下面的示例是 lambda 表达式，该表达式将值写入控制台。 该示例显示了子例程的单行和多行 lambda 表达式语法。

[!code-vb[VbVbalrLambdas#15](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrLambdas/VB/Class1.vb#15)]

请注意，在前面的示例中，lambda 表达式被分配给一个变量名称。 每当引用变量时，都会调用 lambda 表达式。 您还可以同时声明和调用 lambda 表达式，如以下示例所示。

[!code-vb[VbVbalrLambdas#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrLambdas/VB/Class1.vb#3)]

lambda 表达式可以作为函数调用的值返回（如本主题后面的["上下文](#context)"部分中的示例中所示），也可以作为参数传递给采用委托类型的参数，如以下示例所示。

[!code-vb[VbVbalrLambdas#8](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrLambdas/VB/Class2.vb#8)]

## <a name="lambda-expression-syntax"></a>Lambda 表达式语法

lambda 表达式的语法类似于标准函数或子例程的语法。 不同之处如下：

- lambda 表达式没有名称。

- Lambda 表达式不能具有修饰符，如`Overloads`或`Overrides`。

- 单行 lambda 函数不使用子句`As`来指定返回类型。 相反，类型是从 lambda 表达式的正文计算到的值推断的。 例如，如果 lambda 表达式的正文为`cust.City = "London"`，则其返回类型`Boolean`为 。

- 在多行 lambda 函数中，可以使用`As`子句指定返回类型，或者省略`As`子句，以便推断返回类型。 当多`As`行 lambda 函数省略子句时，返回类型被推断为多行 lambda 函数中所有`Return`语句中的主要类型。 *主导类型*是所有其他类型都可以扩展到的唯一类型。 如果无法确定此唯一类型，则主导类型是数组中所有其他类型都可以缩小到的唯一类型。 如果无法确定为这两种唯一类型之一，则基准类型是 `Object`。 在这种情况下，如果`Option Strict`设置为`On`，则会发生编译器错误。

     例如`Return`，如果提供给语句的表达式包含 类型`Integer`的值 ，`Long`和`Double`， 生成的数组的类型`Double`为 。 两`Integer`者`Long`加宽`Double`至和`Double`仅。 因此， `Double` 是基准类型。 有关详细信息，请参阅 [Widening and Narrowing Conversions](../../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md)。

- 单行函数的正文必须是返回值的表达式，而不是语句。 单行函数`Return`没有语句。 单行函数返回的值是函数正文中表达式的值。

- 单行子例程的正文必须是单行语句。

- 单行函数和子例程不包括 或`End Function``End Sub`语句。

- 可以使用`As`关键字指定 lambda 表达式参数的数据类型，也可以推断参数的数据类型。 所有参数都必须具有指定的数据类型，或者必须推断所有参数。

- `Optional`不允许`Paramarray`和参数。

- 不允许使用通用参数。

## <a name="async-lambdas"></a>异步 lambda

通过使用[Async](../../../../visual-basic/language-reference/modifiers/async.md)和[Await 运算符](../../../../visual-basic/language-reference/operators/await-operator.md)关键字，可以轻松地创建包含异步处理的 lambda 表达式和语句。 例如，下面的 Windows 窗体示例包含一个调用和等待异步方法 `ExampleMethodAsync`的事件处理程序。

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

您可以通过在[AddHandler 语句](../../../../visual-basic/language-reference/statements/addhandler-statement.md)中使用异步 lambda 来添加相同的事件处理程序。 若要添加此处理程序，请在 lambda 参数列表前添加一个 `Async` 修饰符，如下例所示。

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

有关如何创建和使用异步方法的详细信息，请参阅[使用异步和 Await 进行异步编程](../../../../visual-basic/programming-guide/concepts/async/index.md)。

## <a name="context"></a>上下文

lambda 表达式与其定义上下文的范围共享上下文。 它具有与在包含作用域中编写的任何代码相同的访问权限。 这包括访问包含作用域中的成员变量、函数和子以及`Me`参数和局部变量。

对包含作用域中的局部变量和参数的访问可以超出该作用域的生存期。 只要引用 lambda 表达式的委托不能用于垃圾回收，则将保留对原始环境中变量的访问。 在下面的示例中，变量`target`是 局部的`makeTheGame`， 在 其中定义 lambda 表达式`playTheGame`的方法。 请注意，分配给`takeAGuess``Main`的返回 lambda 表达式仍有权访问局部变量`target`。

[!code-vb[VbVbalrLambdas#12](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrLambdas/VB/Class6.vb#12)]

下面的示例演示嵌套 lambda 表达式的广泛访问权限。 当返回的 lambda 表达式从`Main``aDel`执行 时，它将访问以下元素：

- 在其中定义它的类的字段：`aField`

- 定义它的类的属性：`aProp`

- 方法`functionWithNestedLambda`的参数，`level1`

- 的`functionWithNestedLambda`局部变量：`localVar`

- 嵌套在 lambda 表达式中的参数：`level2`

 [!code-vb[VbVbalrLambdas#9](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrLambdas/VB/Class3.vb#9)]

## <a name="converting-to-a-delegate-type"></a>转换为委托类型

lambda 表达式可以隐式转换为兼容的委托类型。 有关兼容性的一般要求的信息，请参阅[放宽委托转换](../../../../visual-basic/programming-guide/language-features/delegates/relaxed-delegate-conversion.md)。 例如，以下代码示例显示隐式转换为`Func(Of Integer, Boolean)`或匹配委托签名的 lambda 表达式。

[!code-vb[VbVbalrLambdas#16](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrLambdas/VB/Class1.vb#16)]

下面的代码示例显示隐式转换为`Sub(Of Double, String, Double)`或匹配委托签名的 lambda 表达式。

[!code-vb[VbVbalrLambdas#23](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrLambdas/VB/class7.vb#23)]

将 lambda 表达式分配给委托或将它们作为参数传递给过程时，可以指定参数名称，但省略其数据类型，允许从委托获取类型。

## <a name="examples"></a>示例

- 下面的示例定义 lambda 表达式，如果空`True`值类型参数具有赋值，并且`False`其值为`Nothing`，则返回该表达式。

     [!code-vb[VbVbalrLambdas#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrLambdas/VB/Class1.vb#4)]

- 下面的示例定义一个 lambda 表达式，该表达式返回数组中最后一个元素的索引。

     [!code-vb[VbVbalrLambdas#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrLambdas/VB/Class1.vb#5)]

## <a name="see-also"></a>请参阅

- [过程](./index.md)
- [Visual Basic 中的 LINQ 简介](../../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)
- [委托](../../../../visual-basic/programming-guide/language-features/delegates/index.md)
- [Function 语句](../../../../visual-basic/language-reference/statements/function-statement.md)
- [Sub 语句](../../../../visual-basic/language-reference/statements/sub-statement.md)
- [可以为 null 的值类型](../../../../visual-basic/programming-guide/language-features/data-types/nullable-value-types.md)
- [如何：在 Visual Basic 中将过程传递给另一过程](../../../../visual-basic/programming-guide/language-features/delegates/how-to-pass-procedures-to-another-procedure.md)
- [如何：创建 lambda 表达式](./how-to-create-a-lambda-expression.md)
- [宽松委托转换](../../../../visual-basic/programming-guide/language-features/delegates/relaxed-delegate-conversion.md)
