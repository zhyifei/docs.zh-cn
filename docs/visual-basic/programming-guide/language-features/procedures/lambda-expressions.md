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
ms.openlocfilehash: e688beac18e782367bf39ddec8339df2b2735225
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2019
ms.locfileid: "69928904"
---
# <a name="lambda-expressions-visual-basic"></a>Lambda 表达式 (Visual Basic)
*Lambda 表达式*是没有名称的函数或子例程, 只要委托有效, 就可以使用该函数。 Lambda 表达式可以是函数或子例程, 可以是单行或多行。 可以将值从当前作用域传递到 lambda 表达式。  
  
> [!NOTE]
> `RemoveHandler`语句是一个异常。 不能为的委托参数`RemoveHandler`传递中的 lambda 表达式。  
  
 您可以使用`Function`或`Sub`关键字创建 lambda 表达式, 就像创建标准函数或子例程一样。 但是, lambda 表达式包含在语句中。  
  
 下面的示例是一个 lambda 表达式, 它递增其参数并返回值。 该示例显示函数的单行和多行 lambda 表达式语法。  
  
 [!code-vb[VbVbalrLambdas#14](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrLambdas/VB/Class1.vb#14)]  
  
 下面的示例是一个将值写入控制台的 lambda 表达式。 该示例显示了子程序的单行和多行 lambda 表达式语法。  
  
 [!code-vb[VbVbalrLambdas#15](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrLambdas/VB/Class1.vb#15)]  
  
 请注意, 在前面的示例中, lambda 表达式被分配给变量名。 只要引用变量, 就会调用 lambda 表达式。 还可以同时声明和调用 lambda 表达式, 如下例所示。  
  
 [!code-vb[VbVbalrLambdas#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrLambdas/VB/Class1.vb#3)]  
  
 Lambda 表达式可以作为函数调用的值返回 (如本主题后面的[上下文](#context)部分的示例中所示), 或者作为参数传递给采用委托类型的参数, 如下面的示例中所示。  
  
 [!code-vb[VbVbalrLambdas#8](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrLambdas/VB/Class2.vb#8)]  
  
## <a name="lambda-expression-syntax"></a>Lambda 表达式语法  
 Lambda 表达式的语法与标准函数或子例程的语法相似。 不同之处如下:  
  
- Lambda 表达式没有名称。  
  
- Lambda 表达式不能具有修饰符, 如`Overloads`或`Overrides`。  
  
- 单行 lambda 函数不使用`As`子句来指定返回类型。 相反, 该类型是从 lambda 表达式体的计算结果为的值推断出来的。 例如, 如果 lambda 表达式的主体为`cust.City = "London"`, 则其返回类型为。 `Boolean`  
  
- 在多行 lambda 函数中, 可以使用`As`子句指定返回类型, 或`As`省略子句以便推断返回类型。 如果为多行 lambda 函数省略`Return` 子句,则会将返回类型推断为来自多行lambda函数中所有语句的基准类型。`As` *主导类型*是所有其他类型可以扩大到的唯一类型。 如果无法确定此唯一类型, 则主导类型是数组中所有其他类型可以缩小到的唯一类型。 如果这两种唯一类型都无法确定，则基准类型是 `Object`。 在这种情况下`Option Strict` , 如果将`On`设置为, 则会发生编译器错误。  
  
     例如`Return` , 如果提供给语句的表达式包含类型`Integer`为、 `Long`和`Double`的值, 则生成的数组的类型`Double`为。 和`Integer` 都`Long`仅`Double`扩大到和。 `Double` 因此， `Double` 是基准类型。 有关详细信息，请参阅[扩大和缩小转换](../../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md)。  
  
- 单行函数的主体必须是返回值的表达式, 而不是语句。 没有适用于单行函数的语句。`Return` 单行函数返回的值是函数体中表达式的值。  
  
- 单行子例程的主体必须是单行语句。  
  
- 单行函数和子例程不包含`End Function`或`End Sub`语句。  
  
- 您可以使用`As`关键字指定 lambda 表达式参数的数据类型, 也可以推断参数的数据类型。 所有参数都必须具有指定的数据类型, 或者都必须被推断。  
  
- `Optional`不`Paramarray`允许使用和参数。  
  
- 不允许使用泛型参数。  
  
## <a name="async-lambdas"></a>异步 lambda  
 通过使用[Async](../../../../visual-basic/language-reference/modifiers/async.md)和[Await 运算符](../../../../visual-basic/language-reference/operators/await-operator.md)关键字, 你可以轻松创建包含异步处理的 lambda 表达式和语句。 例如，下面的 Windows 窗体示例包含一个调用和等待异步方法 `ExampleMethodAsync`的事件处理程序。  
  
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
  
 可以通过在[AddHandler 语句](../../../../visual-basic/language-reference/statements/addhandler-statement.md)中使用 async lambda 来添加同一事件处理程序。 若要添加此处理程序，请在 lambda 参数列表前添加一个 `Async` 修饰符，如下例所示。  
  
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
  
 有关如何创建和使用异步方法的详细信息, 请参阅[使用 async 和 Await 进行异步编程](../../../../visual-basic/programming-guide/concepts/async/index.md)。  
  
## <a name="context"></a>快捷  
 Lambda 表达式将其上下文与定义它的范围共享。 它与在包含范围内编写的任何代码具有相同的访问权限。 这包括访问包含作用域中的成员变量、 `Me`函数和 sub、以及参数和局部变量。  
  
 对包含作用域中的局部变量和参数的访问可以超出该范围的生存期。 只要引用 lambda 表达式的委托不可用于垃圾回收, 就会保留对原始环境中的变量的访问。 在下面的示例中, `target`变量是的`makeTheGame`局部变量, 其中定义了 lambda 表达式`playTheGame`的方法。 请注意, 分配`takeAGuess`给中`Main`的返回的 lambda 表达式仍有权访问本地变量`target`。  
  
 [!code-vb[VbVbalrLambdas#12](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrLambdas/VB/Class6.vb#12)]  
  
 下面的示例演示了嵌套 lambda 表达式的各种访问权限。 当从`Main` `aDel`执行返回的 lambda 表达式时, 它将访问这些元素:  
  
- 定义它的类的字段:`aField`  
  
- 定义它的类的属性:`aProp`  
  
- 定义它的方法`functionWithNestedLambda`的参数:`level1`  
  
- 的`functionWithNestedLambda`局部变量:`localVar`  
  
- 它在其中进行嵌套的 lambda 表达式的参数:`level2`  
  
 [!code-vb[VbVbalrLambdas#9](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrLambdas/VB/Class3.vb#9)]  
  
## <a name="converting-to-a-delegate-type"></a>转换为委托类型  
 Lambda 表达式可隐式转换为兼容的委托类型。 有关兼容性的一般要求的信息, 请参阅[宽松委托转换](../../../../visual-basic/programming-guide/language-features/delegates/relaxed-delegate-conversion.md)。 例如, 下面的代码示例演示一个隐式转换为`Func(Of Integer, Boolean)`或匹配的委托签名的 lambda 表达式。  
  
 [!code-vb[VbVbalrLambdas#16](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrLambdas/VB/Class1.vb#16)]  
  
 下面的代码示例演示一个隐式转换为`Sub(Of Double, String, Double)`或匹配的委托签名的 lambda 表达式。  
  
 [!code-vb[VbVbalrLambdas#23](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrLambdas/VB/class7.vb#23)]  
  
 当你将 lambda 表达式分配给委托或将其作为参数传递给过程时, 可以指定参数名称但省略其数据类型, 从而使类型从委托中获取。  
  
## <a name="examples"></a>示例  
  
- 下面的示例定义一个 lambda 表达式, 该`True`表达式在可以为 null 的参数具有分配的`False`值时返回, `Nothing`如果其值为, 则返回。  
  
     [!code-vb[VbVbalrLambdas#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrLambdas/VB/Class1.vb#4)]  
  
- 下面的示例定义了一个 lambda 表达式, 该表达式返回数组中最后一个元素的索引。  
  
     [!code-vb[VbVbalrLambdas#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrLambdas/VB/Class1.vb#5)]  
  
## <a name="see-also"></a>请参阅

- [过程](./index.md)
- [Visual Basic 中的 LINQ 简介](../../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)
- [委托](../../../../visual-basic/programming-guide/language-features/delegates/index.md)
- [Function 语句](../../../../visual-basic/language-reference/statements/function-statement.md)
- [Sub 语句](../../../../visual-basic/language-reference/statements/sub-statement.md)
- [可以为 null 的值类型](../../../../visual-basic/programming-guide/language-features/data-types/nullable-value-types.md)
- [如何：将过程传递到 Visual Basic 中的其他过程](../../../../visual-basic/programming-guide/language-features/delegates/how-to-pass-procedures-to-another-procedure.md)
- [如何：创建 Lambda 表达式](./how-to-create-a-lambda-expression.md)
- [宽松委托转换](../../../../visual-basic/programming-guide/language-features/delegates/relaxed-delegate-conversion.md)
