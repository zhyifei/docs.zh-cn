---
title: 异步工作流 (F#)
description: '了解支持在 F # 编程语言以异步方式执行计算执行而不会阻止其他工作的执行。'
ms.date: 05/16/2016
ms.openlocfilehash: 5f7a1a623e143e1bedf51c1a1ed477bb867b280a
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
---
# <a name="asynchronous-workflows"></a>异步工作流

> [!NOTE]
API 参考链接将转至 MSDN。  Docs.microsoft.com API 参考尚未完成。

本主题描述 F # 中的支持用于执行计算以异步方式，即，而不会阻止其他工作的执行。 例如，异步计算可用来编写应用程序保持对用户的响应，因为应用程序会执行其他工作的 ui。

## <a name="syntax"></a>语法

```fsharp
async { expression }
```

## <a name="remarks"></a>备注

在上述语法中，计算由`expression`设置为异步运行，也就是说，而不会阻止当前计算线程执行异步睡眠操作、 I/O 和其他异步操作时。 异步计算通常会在后台线程上启动，同时在当前线程上继续执行。 表达式的类型是`Async<'T>`，其中`'T`是由表达式返回的类型时`return`使用关键字。 此类表达式中的代码称为*异步块*，或*异步块*。

有多种方法的异步编程，和[ `Async` ](https://msdn.microsoft.com/library/03eb4d12-a01a-4565-a077-5e83f17cf6f7)类提供支持多个方案的方法。 常规方法是创建`Async`表示计算或你想要以异步方式运行的计算并使用触发的函数之一，然后启动这些计算的对象。 各种触发函数提供不同的方法来运行异步计算，并使用哪一个取决于是否想要使用当前线程、 后台线程或.NET Framework 任务对象，以及是否有延续在计算完成时，应运行的函数。 例如，若要在当前线程上启动一个异步计算，可以使用[ `Async.StartImmediate` ](https://msdn.microsoft.com/library/2f71d1cc-187f-48cf-ac66-e7fda41c46e3)。 当你启动一个异步计算从 UI 线程时，就不会阻止处理用户操作的键击和鼠标活动，例如，因此你的应用程序保持响应性的主要事件循环。

## <a name="asynchronous-binding-by-using-let"></a>通过使用允许的异步绑定 ！

在异步工作流中，某些表达式和操作是同步的，而有些则旨在异步返回结果的时间计算。 当调用的方法以异步方式，而不是一个普通`let`绑定，你将使用`let!`。 效果`let!`旨在使正在执行计算时，继续在其他计算或线程上执行。 之后的右侧`let!`绑定返回时，异步工作流的剩余部分将继续执行。

下面的代码显示之间的差异`let`和`let!`。 使用的代码行`let`只需创建为一个对象，你可以在以后运行通过使用，例如，一个异步计算`Async.StartImmediate`或[ `Async.RunSynchronously` ](https://msdn.microsoft.com/library/0a6663a9-50f2-4d38-8bf3-cefd1a51fd6b)。 使用的代码行`let!`开始计算，并在结果可用，点执行过程才会继续之前然后挂起线程。

```fsharp
// let just stores the result as an asynchronous operation.
let (result1 : Async<byte[]>) = stream.AsyncRead(bufferSize)
// let! completes the asynchronous operation and returns the data.
let! (result2 : byte[])  = stream.AsyncRead(bufferSize)
```

除了`let!`，你可以使用`use!`执行异步绑定。 之间的差异`let!`和`use!`之间的差异相同`let`和`use`。 有关`use!`，在当前范围的结束位置的释放此对象。 请注意，在当前版本的 F # 语言，`use!`不允许的值初始化为 null，即使`use`未。

## <a name="asynchronous-primitives"></a>异步基元

执行一个异步任务，并返回结果的方法称为*异步基元*，并这些由专用于`let!`。 多个异步基元都在 F # 核心库中定义。 模块中定义为 Web 应用程序的两个此类方法[ `Microsoft.FSharp.Control.WebExtensions` ](https://msdn.microsoft.com/library/95ef17bc-ee3f-44ba-8a11-c90fcf4cf003): [ `WebRequest.AsyncGetResponse` ](https://msdn.microsoft.com/library/09a60c31-e6e2-4b5c-ad23-92a86e50060c)和[ `WebClient.AsyncDownloadString` ](https://msdn.microsoft.com/library/8a85a9b7-f712-4cac-a0ce-0a797f8ea32a)。 这两个基元从 Web 页上，为其提供 URL 下载数据。 `AsyncGetResponse` 生成`System.Net.WebResponse`对象，和`AsyncDownloadString`生成一个字符串，表示用于网页的 HTML。

中包含的异步 I/O 操作的几个基元[ `Microsoft.FSharp.Control.CommonExtensions` ](https://msdn.microsoft.com/library/2edb67cb-6814-4a30-849f-b6dbdd042396)模块。 这些扩展方法的`System.IO.Stream`类[ `Stream.AsyncRead` ](https://msdn.microsoft.com/library/85698aaa-bdda-47e6-abed-3730f59fda5e)和[ `Stream.AsyncWrite` ](https://msdn.microsoft.com/library/1b0a2751-e42a-47e1-bd27-020224adc618)。

其他异步基元位于[F # 增强工具](https://fsprojects.github.io/VisualFSharpPowerTools/)。 你还可以通过定义其完整的主体括在异步块中的函数编写你自己的异步基元。

若要使用的 F # 异步编程模型与其他异步模型设计.NET Framework 中的异步方法，你创建的函数，返回的 F #`Async`对象。 F # 库具有函数，这可以更方便地执行操作。

使用异步工作流的一个示例是为了;还有许多其他的方法的文档中[异步类](https://msdn.microsoft.com/library/03eb4d12-a01a-4565-a077-5e83f17cf6f7)。

此示例演示如何使用异步工作流来并行执行计算。

在下面的代码示例，函数`fetchAsync`获取 Web 请求返回的 HTML 文本。 `fetchAsync`函数包含异步代码块。 当绑定由对结果的异步基元，在这种情况下[ `AsyncDownloadString` ](https://msdn.microsoft.com/library/8a85a9b7-f712-4cac-a0ce-0a797f8ea32a)，但仍使 ！ 而不是让使用。

使用函数[ `Async.RunSynchronously` ](https://msdn.microsoft.com/library/0a6663a9-50f2-4d38-8bf3-cefd1a51fd6b)来执行异步操作并等待其结果。 例如，你可以执行多个异步操作并行使用[ `Async.Parallel` ](https://msdn.microsoft.com/library/aa9b0355-2d55-4858-b943-cbe428de9dc4)函数，`Async.RunSynchronously`函数。 `Async.Parallel`函数的列表`Async`的对象，设置了代码，每个`Async`task 对象以在并行，并返回运行`Async`对象，表示并行计算。 单个操作，情况一样，你调用`Async.RunSynchronously`以开始执行。

`runAll`函数将启动三个并行的异步工作流，并等待，直至它们全部完成。

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet8003.fs)]

## <a name="see-also"></a>请参阅

[F# 语言参考](index.md)

[计算表达式](computation-expressions.md)

[Control.Async 类](https://msdn.microsoft.com/visualfsharpdocs/conceptual/control.async-class-%5bfsharp%5d)
