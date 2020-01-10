---
title: 尝试 .。。Catch .。。Finally 语句
description: 了解如何对 Visual Basic Try/Catch/Finally 语句使用异常处理。
ms.date: 12/07/2018
f1_keywords:
- vb.Try...Catch...Finally
- vb.when
- vb.Finally
- vb.Catch
- vb.Try
helpviewer_keywords:
- Try...Catch...Finally statements
- Try statement [Visual Basic]
- try-catch exception handling, Try...Catch...Finally statements
- error handling, while running code
- Try statement [Visual Basic], Try...Catch...Finally
- Finally keyword [Visual Basic], Try...Catch...Finally
- Catch statement [Visual Basic]
- When keyword [Visual Basic]
- Visual Basic code, handling errors while running
- structured exception handling, Try...Catch...Finally statements
ms.assetid: d6488026-ccb3-42b8-a810-0d97b9d6472b
ms.openlocfilehash: bb6f17f7ce88caea0b9d30ec880194f2bb71c6a6
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/07/2020
ms.locfileid: "75705764"
---
# <a name="trycatchfinally-statement-visual-basic"></a>Try...Catch...Finally 语句 (Visual Basic)

提供了一种方法，用于处理给定代码块中可能发生的一些或所有可能的错误，同时仍在运行代码。

## <a name="syntax"></a>语法

```vb
Try
    [ tryStatements ]
    [ Exit Try ]
[ Catch [ exception [ As type ] ] [ When expression ]
    [ catchStatements ]
    [ Exit Try ] ]
[ Catch ... ]
[ Finally
    [ finallyStatements ] ]
End Try
```

## <a name="parts"></a>部件

|术语|Definition|
|---|---|
|`tryStatements`|可选。 可能发生错误的语句。 可以是复合语句。|
|`Catch`|可选。 允许多个 `Catch` 块。 如果在处理 `Try` 块时发生异常，则会以文本顺序检查每个 `Catch` 语句，以确定它是否处理异常，`exception` 表示已引发的异常。|
|`exception`|可选。 任何变量名称。 `exception` 的初始值是引发的错误的值。 与 `Catch` 一起使用，以指定捕获的错误。 如果省略，则 `Catch` 语句将捕获任何异常。|
|`type`|可选。 指定类筛选器的类型。 如果 `exception` 的值是 `type` 或派生类型指定的类型，则该标识符将绑定到 exception 对象。|
|`When`|可选。 带有 `When` 子句的 `Catch` 语句仅在 `expression` 计算结果为 `True`时才捕获异常。 `When` 子句仅在检查异常类型后应用，`expression` 可以引用表示异常的标识符。|
|`expression`|可选。 必须能够隐式转换为 `Boolean`。 描述泛型筛选器的任何表达式。 通常用于按错误号进行筛选。 与 `When` 关键字一起使用，以指定捕获错误的情况。|
|`catchStatements`|可选。 用于处理关联 `Try` 块中发生的错误的语句。 可以是复合语句。|
|`Exit Try`|可选。 用于中断 `Try...Catch...Finally` 结构的关键字。 继续执行，并在 `End Try` 语句之后立即执行。 `Finally` 语句仍将被执行。 不允许在 `Finally` 块中使用。|
|`Finally`|可选。 当执行离开 `Try...Catch` 语句的任何部分时，始终会执行 `Finally` 块。|
|`finallyStatements`|可选。 在所有其他错误处理发生之后执行的语句。|
|`End Try`|终止 `Try...Catch...Finally` 结构。|

## <a name="remarks"></a>备注

如果预计在代码的特定部分中可能出现特定的异常，请将代码放在 `Try` 块中，并使用 `Catch` 块保留控件并处理发生的异常（如果发生）。

`Try…Catch` 语句由一个 `Try` 块后跟一个或多个 `Catch` 子句组成，这些子句指定不同异常的处理程序。 当在 `Try` 块中引发异常时，Visual Basic 将查找处理异常的 `Catch` 语句。 如果找不到匹配的 `Catch` 语句，Visual Basic 检查调用当前方法的方法，并在调用堆栈上向上进行。 如果找不到 `Catch` 块，Visual Basic 向用户显示未处理的异常消息，并停止执行程序。

可以在 `Try…Catch` 语句中使用多个 `Catch` 语句。 如果这样做，`Catch` 子句的顺序很重要，因为它们是按顺序进行检查的。 在使用更笼统的子句之前获取特定性更强的异常。

下面的 `Catch` 语句条件是最不具体的，将捕获派生自 <xref:System.Exception> 类的所有异常。 在捕获所需的所有特定异常后，通常应将这些变体中的最后一个 `Catch` 块作为 `Try...Catch...Finally` 结构中的最后一个块。 控制流永远不会到达遵循这些变化之一的 `Catch` 块。

- `type` 是 `Exception`的，例如： `Catch ex As Exception`

- 语句没有 `exception` 变量，例如： `Catch`

如果 `Try…Catch…Finally` 语句嵌套在另一个 `Try` 块中，则 Visual Basic 首先检查最内层 `Try` 块中的每个 `Catch` 语句。 如果未找到匹配的 `Catch` 语句，搜索将继续执行外部 `Try…Catch…Finally` 块的 `Catch` 语句。

`Try` 块中的局部变量在 `Catch` 块中不可用，因为它们是单独的块。 如果要在多个块中使用变量，请在 `Try...Catch...Finally` 结构外声明变量。

> [!TIP]
> `Try…Catch…Finally` 语句作为 IntelliSense 代码段提供。 在 "代码片段管理器" 中，展开 "**代码模式"-如果为，则依次尝试 Catch、Property**等，然后进行**错误处理（异常）** 。 有关详细信息，请参阅[代码片段](/visualstudio/ide/code-snippets)。

## <a name="finally-block"></a>Finally 块

如果有一个或多个必须在退出 `Try` 结构之前运行的语句，请使用 `Finally` 块。 控件在传递到 `Try…Catch` 结构之前，会立即传递到 `Finally` 块。 即使 `Try` 结构内的任何位置发生异常，也是如此。

`Finally` 块适用于运行任何必须执行的代码，即使存在异常也是如此。 无论 `Try...Catch` 块的退出方式如何，都将控制传递到 `Finally` 块。

即使您的代码在 `Try` 或 `Catch` 块中遇到 `Return` 语句，也会运行 `Finally` 块中的代码。 在以下情况下，控件不会从 `Try` 或 `Catch` 块传递到相应的 `Finally` 块：

- 在 `Try` 或 `Catch` 块中遇到[结束语句](end-statement.md)。

- `Try` 或 `Catch` 块中引发 <xref:System.StackOverflowException>。

将执行显式传输到 `Finally` 块中是无效的。 除了通过异常以外，从 `Finally` 块传输执行无效。

如果 `Try` 语句不包含至少一个 `Catch` 块，则它必须包含一个 `Finally` 块。

> [!TIP]
> 如果不必捕获特定的异常，则 `Using` 语句的行为类似于 `Try…Finally` 块，并保证资源的处置，无论退出块的方式如何。 即使出现未经处理的异常也是如此。 有关详细信息，请参阅 [Using 语句](using-statement.md)。

## <a name="exception-argument"></a>异常参数

`Catch` 块 `exception` 参数是 <xref:System.Exception> 类的实例，或从 `Exception` 类派生的类的实例。 `Exception` 类实例对应于 `Try` 块中发生的错误。

`Exception` 对象的属性可帮助确定异常的原因和位置。 例如，<xref:System.Exception.StackTrace%2A> 属性列出导致异常的被调用方法，帮助你查找代码中发生错误的位置。 <xref:System.Exception.Message%2A> 返回描述异常的消息。 <xref:System.Exception.HelpLink%2A> 返回指向关联帮助文件的链接。 <xref:System.Exception.InnerException%2A> 返回导致当前异常的 `Exception` 对象，如果不存在原始 `Exception`，则返回 `Nothing`。

## <a name="considerations-when-using-a-trycatch-statement"></a>使用 Try ... 时的注意事项Catch 语句

仅使用 `Try…Catch` 语句，以指示出现异常或意外的程序事件。 原因如下：

- 在运行时捕获异常将产生额外的开销，并且可能比预检查更慢，以避免异常。

- 如果未正确处理 `Catch` 块，则异常可能不会正确地报告给用户。

- 异常处理使程序更复杂。

并非始终需要 `Try…Catch` 语句来检查可能出现的情况。 下面的示例检查文件是否存在，然后再尝试打开它。 这减少了捕获由 <xref:System.IO.File.OpenText%2A> 方法引发的异常的需求。

[!code-vb[VbVbalrStatements#94](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#94)]

确保 `Catch` 块中的代码可以正确地向用户报告异常，无论是通过线程安全日志记录还是适当的消息。 否则，例外可能仍然未知。

## <a name="async-methods"></a>异步方法

如果用[Async](../modifiers/async.md)修饰符标记方法，可以在方法中使用[Await](../operators/await-operator.md)运算符。 带有 `Await` 运算符的语句挂起了方法的执行，直到等待的任务完成。 任务表示正在进行的工作。 当与 `Await` 运算符关联的任务完成时，将在同一方法中恢复执行。 有关详细信息，请参阅[异步程序中的控制流](../../../visual-basic/programming-guide/concepts/async/control-flow-in-async-programs.md)。

异步方法返回的任务可能会以错误状态结束，这表示它由于未处理的异常而完成。 任务还可以以 "已取消" 状态结束，导致从 await 表达式引发 `OperationCanceledException`。 若要捕获任一类型的异常，请将与任务关联的 `Await` 表达式放在 `Try` 块中，并在 `Catch` 块中捕获该异常。 本主题后面提供了一个示例。

任务可能处于错误状态，因为多个异常负责错误的发生。 例如，任务可能是对 <xref:System.Threading.Tasks.Task.WhenAll%2A?displayProperty=nameWithType> 调用的结果。 当你等待此类任务时，捕获的异常只是异常之一，你无法预测将捕获的异常。 本主题后面提供了一个示例。

`Await` 表达式不能位于 `Catch` 块或 `Finally` 块内。

## <a name="iterators"></a>Iterators

迭代器函数或 `Get` 访问器对集合执行自定义迭代。 迭代器使用[Yield](yield-statement.md)语句每次返回集合中的每个元素。 您可以通过[对每个 .。。下一语句](for-each-next-statement.md)。

`Yield` 语句可以位于 `Try` 块内。 包含 `Yield` 语句的 `Try` 块可以具有 `Catch` 块，并且可以具有 `Finally` 块。 有关示例，请参阅[迭代](../../programming-guide/concepts/iterators.md)器中的 "Try 块 Visual Basic" 部分。

`Yield` 语句不能位于 `Catch` 块或 `Finally` 块内。

如果 `For Each` 体（位于 iterator 函数之外）引发异常，则不会执行迭代器函数中的 `Catch` 块，但会执行迭代器函数中的一个 `Finally` 块。 Iterator 函数内的 `Catch` 块仅捕获 iterator 函数内发生的异常。

## <a name="partial-trust-situations"></a>部分信任情况

在部分信任的情况下（例如在网络共享上托管的应用程序），`Try...Catch...Finally` 不会捕获在调用包含调用的方法之前出现的安全异常。 在以下示例中，当你将其放在服务器共享上并从该位置运行时，将产生错误 "SecurityException：请求失败"。 有关安全异常的详细信息，请参阅 <xref:System.Security.SecurityException> 类。

[!code-vb[VbVbalrStatements#85](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#85)]

在这种部分信任情况下，必须将 `Process.Start` 语句置于单独的 `Sub`中。 对 `Sub` 的初始调用将失败。 这使 `Try...Catch` 可以在启动包含 `Process.Start` 的 `Sub` 和生成安全异常之前捕获该功能。

## <a name="examples"></a>示例

### <a name="the-structure-of-trycatchfinally"></a>Try ... 的结构Catch .。。最后

下面的示例说明 `Try...Catch...Finally` 语句的结构。

[!code-vb[VbVbalrStatements#86](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#86)]  

### <a name="exception-in-a-method-called-from-a-try-block"></a>从 Try 块调用的方法中的异常

在下面的示例中，`CreateException` 方法引发 `NullReferenceException`。 生成异常的代码不在 `Try` 块中。 因此，`CreateException` 方法不会处理异常。 `RunSample` 方法将处理异常，因为对 `CreateException` 方法的调用在 `Try` 块中。

该示例包括多种类型的异常的 `Catch` 语句，按从最具体到最常见的顺序排列。

[!code-vb[VbVbalrStatements#91](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#91)]

### <a name="the-catch-when-statement"></a>Catch When 语句

下面的示例演示如何使用 `Catch When` 语句根据条件表达式进行筛选。 如果条件表达式的计算结果为 `True`，则 `Catch` 块中的代码将运行。

[!code-vb[VbVbalrStatements#92](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#92)]

### <a name="nested-try-statements"></a>嵌套 Try 语句

下面的示例包含一个包含在 `Try` 块中的 `Try…Catch` 语句。 内部 `Catch` 块引发了一个异常，该异常的 `InnerException` 属性设置为原始异常。 外部 `Catch` 块报告其自己的异常和内部异常。

[!code-vb[VbVbalrStatements#93](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#93)]

### <a name="exception-handling-for-async-methods"></a>异步方法的异常处理

下面的示例阐释异步方法的异常处理。 若要捕获适用于异步任务的异常，`Await` 表达式位于调用方的 `Try` 块中，而在 `Catch` 块中捕获该异常。

在示例中取消注释 `Throw New Exception` 行以演示异常处理。 在 `Catch` 块中捕获该异常，任务的 `IsFaulted` 属性设置为 `True`，任务的 `Exception.InnerException` 属性设置为异常。

取消注释 `Throw New OperationCancelledException` 行以演示在取消异步进程时发生的情况。 在 `Catch` 块中捕获到异常，任务的 `IsCanceled` 属性设置为 `True`。 但是，在某些不适用于此示例的情况下，`IsFaulted` 设置为 `True` 并且 `IsCanceled` 设置为 `False`。

[!code-vb[csAsyncExceptions#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/csasyncexceptions/vb/class1.vb#1)]

### <a name="handling-multiple-exceptions-in-async-methods"></a>在异步方法中处理多个异常

下面的示例阐释了在多个任务可能导致多个异常的情况中的异常处理。 `Try` 块具有 <xref:System.Threading.Tasks.Task.WhenAll%2A?displayProperty=nameWithType> 返回的任务的 `Await` 表达式。 当应用 <xref:System.Threading.Tasks.Task.WhenAll%2A?displayProperty=nameWithType> 的三个任务完成时，该任务完成。

三个任务中的每一个都会导致异常。 `Catch` 块遍历异常，这些异常在 `Task.WhenAll` 返回的任务的 `Exception.InnerExceptions` 属性中找到。

[!code-vb[csAsyncExceptions#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/csasyncexceptions/vb/class1.vb#3)]

## <a name="see-also"></a>另请参阅

- <xref:Microsoft.VisualBasic.Information.Err%2A>
- <xref:System.Exception>
- [Exit 语句](exit-statement.md)
- [On Error 语句](on-error-statement.md)
- [有关使用代码片段的最佳做法](/visualstudio/ide/best-practices-for-using-code-snippets)
- [异常处理](../../../standard/parallel-programming/exception-handling-task-parallel-library.md)
- [Throw 语句](throw-statement.md)
