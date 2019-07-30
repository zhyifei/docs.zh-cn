---
title: 异步工作流
description: 了解以异步方式执行F#计算所需的编程语言的支持, 该支持在不阻止执行其他工作的情况下执行。
ms.date: 05/16/2016
ms.openlocfilehash: 2d967f6bfe46b4f3916648b3063210d1ba1c210f
ms.sourcegitcommit: f20dd18dbcf2275513281f5d9ad7ece6a62644b4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/30/2019
ms.locfileid: "68629998"
---
# <a name="asynchronous-workflows"></a>异步工作流

> [!NOTE]
> API 参考链接将转至 MSDN。  Docs.microsoft.com API 参考尚未完成。

本主题介绍了中F#的支持异步执行计算, 即, 不阻止执行其他工作。 例如, 异步计算可用于编写应用程序, 这些应用程序具有在应用程序执行其他工作时对用户保持响应的 Ui。

## <a name="syntax"></a>语法

```fsharp
async { expression }
```

## <a name="remarks"></a>备注

在前面的语法中, 由表示`expression`的计算设置为异步运行, 也就是说, 在执行异步睡眠操作、i/o 和其他异步操作时, 不会阻止当前计算线程。 异步计算通常在后台线程上启动, 而在当前线程上继续执行。 表达式的类型为`Async<'T>`, 其中`'T`是使用`return`关键字时表达式返回的类型。 此类表达式中的代码称为*异步块*或*异步块*。

异步编程的方式有多种, [`Async`](https://msdn.microsoft.com/library/03eb4d12-a01a-4565-a077-5e83f17cf6f7)类提供的方法支持多种方案。 一般方法是创建`Async`表示要异步运行的计算或计算的对象, 然后使用其中一个触发函数启动这些计算。 各种触发函数提供不同的方法来运行异步计算, 使用哪种方法取决于你是要使用当前线程、后台线程还是 .NET Framework 任务对象, 以及是否存在继续符应在计算完成时运行的函数。 例如, 若要在当前线程上启动异步计算, 可以使用[`Async.StartImmediate`](https://msdn.microsoft.com/library/2f71d1cc-187f-48cf-ac66-e7fda41c46e3)。 当从 UI 线程启动异步计算时, 您不会阻止用于处理用户操作 (如击键和鼠标活动) 的主事件循环, 因此您的应用程序将保持响应。

## <a name="asynchronous-binding-by-using-let"></a>使用 let 进行异步绑定!

在异步工作流中, 某些表达式和操作是同步的, 而有些则是用于以异步方式返回结果的更长的计算。 以异步方式调用方法, 而不是使用`let` `let!`普通绑定。 的`let!`作用是在执行计算时允许在其他计算或线程上继续执行。 `let!`绑定的右侧返回后, 异步工作流的其余部分将继续执行。

下面的代码演示了和`let` `let!`之间的差异。 使用`let`的代码行只是将异步计算创建为一个对象, 您可以在以后使用来运行该对象, `Async.StartImmediate`例如或[`Async.RunSynchronously`](https://msdn.microsoft.com/library/0a6663a9-50f2-4d38-8bf3-cefd1a51fd6b)。 使用`let!`的代码行开始计算, 然后在结果可用之前挂起线程, 此时将继续执行。

```fsharp
// let just stores the result as an asynchronous operation.
let (result1 : Async<byte[]>) = stream.AsyncRead(bufferSize)
// let! completes the asynchronous operation and returns the data.
let! (result2 : byte[])  = stream.AsyncRead(bufferSize)
```

除了之外`let!`, 还可以使用`use!`来执行异步绑定。 `let!` `let` 与`use`之间的差异与和的差异相同。 `use!` 对于`use!`, 在当前范围结束时释放对象。 请注意, 在当前版本的F#语言中, `use!`不允许将值初始化为`use` null, 即使是这样。

## <a name="asynchronous-primitives"></a>异步基元

执行单个异步任务并返回结果的方法称为*异步基元*, 它们专用于与一起`let!`使用。 F#核心库中定义了多个异步基元。 本模块[`Microsoft.FSharp.Control.WebExtensions`](https://msdn.microsoft.com/library/95ef17bc-ee3f-44ba-8a11-c90fcf4cf003)中定义了两种 Web 应用程序方法: [`WebRequest.AsyncGetResponse`](https://msdn.microsoft.com/library/09a60c31-e6e2-4b5c-ad23-92a86e50060c)和[`WebClient.AsyncDownloadString`](https://msdn.microsoft.com/library/8a85a9b7-f712-4cac-a0ce-0a797f8ea32a)。 在给定 URL 的情况下, 这两个基元都从网页中下载数据。 `AsyncGetResponse`生成一个`System.Net.WebResponse`对象, 并`AsyncDownloadString`生成一个字符串, 该字符串表示网页的 HTML。

[`Microsoft.FSharp.Control.CommonExtensions`](https://msdn.microsoft.com/library/2edb67cb-6814-4a30-849f-b6dbdd042396)模块中包含了用于异步 i/o 操作的几个基元。 `System.IO.Stream`类的这些扩展方法为[`Stream.AsyncRead`](https://msdn.microsoft.com/library/85698aaa-bdda-47e6-abed-3730f59fda5e)和[`Stream.AsyncWrite`](https://msdn.microsoft.com/library/1b0a2751-e42a-47e1-bd27-020224adc618)。

还可以通过定义一个函数, 该函数的完整体包含在异步块中来编写自己的异步基元。

若要在使用F#异步编程模型为其他异步模型设计的 .NET Framework 中使用异步方法, 您需要创建一个返回F# `Async`对象的函数。 F#库具有可使此操作变得简单的函数。

此处包含使用异步工作流的一个示例;对于[异步类](https://msdn.microsoft.com/library/03eb4d12-a01a-4565-a077-5e83f17cf6f7)的方法, 文档中还有许多其他内容。

此示例演示如何使用异步工作流并行执行计算。

在下面的代码示例中, 函数`fetchAsync`将获取从 Web 请求返回的 HTML 文本。 `fetchAsync`函数包含一个异步代码块。 绑定到异步基元的结果时, 在此示例[`AsyncDownloadString`](https://msdn.microsoft.com/library/8a85a9b7-f712-4cac-a0ce-0a797f8ea32a)中, 让我们! 使用而不是 let。

使用函数[`Async.RunSynchronously`](https://msdn.microsoft.com/library/0a6663a9-50f2-4d38-8bf3-cefd1a51fd6b)可执行异步操作, 并等待其结果。 例如, 你可以通过将[`Async.Parallel`](https://msdn.microsoft.com/library/aa9b0355-2d55-4858-b943-cbe428de9dc4)函数`Async.RunSynchronously`与函数结合使用来并行执行多个异步操作。 函数获取`Async`对象的列表, 为每个`Async`任务对象设置要并行运行的代码, 并返回一个`Async`表示并行计算的对象。 `Async.Parallel` 与单个操作一样, 调用`Async.RunSynchronously`开始执行。

`runAll`函数并行启动三个异步工作流, 并等待它们全部完成。

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet8003.fs)]

## <a name="see-also"></a>请参阅

- [F# 语言参考](index.md)
- [计算表达式](computation-expressions.md)
- [Control Async 类](https://msdn.microsoft.com/visualfsharpdocs/conceptual/control.async-class-%5bfsharp%5d)
