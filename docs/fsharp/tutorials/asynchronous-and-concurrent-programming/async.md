---
title: 异步编程
description: 了解 F# 如何基于从核心函数编程概念派生的语言级编程模型为异步提供干净的支持。
ms.date: 12/17/2018
ms.openlocfilehash: 9b2e3057c126d84474c21fde653da5bbee32938a
ms.sourcegitcommit: d9470d8b2278b33108332c05224d86049cb9484b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/17/2020
ms.locfileid: "81608031"
---
# <a name="async-programming-in-f"></a>F 中的异步编程\#

异步编程是一种机制，对于现代应用程序来说，由于各种原因至关重要。 大多数开发人员会遇到两个主要用例：

- 显示一个服务器进程，该服务器进程可以服务大量并发传入请求，同时最小化请求处理时占用的系统资源，等待来自该进程外部的系统或服务的输入
- 维护响应灵敏的 UI 或主线程，同时推进后台工作

尽管后台工作通常涉及多个线程的利用，但单独考虑异步和多线程的概念非常重要。 事实上，它们是单独的问题，一个并不意味着另一个。 本文中介绍的内容将更详细地介绍这一点。

## <a name="asynchrony-defined"></a>已定义异步

前一点 -异步与多个线程的利用率无关 - 值得进一步解释一下。 有三个概念有时相关，但严格地相互独立：

- 并发性;在重叠的时间段中执行多个计算时。
- 并行性;当多个计算或单个计算的几个部分完全同时运行时。
- 异步;当一个或多个计算可以独立于主程序流执行时。

这三个概念都是正交概念，但很容易组合，尤其是当它们一起使用时。 例如，您可能需要并行执行多个异步计算。 这并不意味着并行性或异步性相互暗示。

如果考虑"异步"一词的词源，则涉及两个部分：

- "a"，意思是"不"。
- "同步"，意思是"同时"。

将这两个术语放在一起时，您将看到"异步"表示"不是同时"。 就这么简单！ 这个定义中没有并发性或并行性的含义。 在实践中也是如此。

实际上，F# 中的异步计算计划独立于主程序流执行。 这并不意味着并发性或并行性，也不意味着计算总是在后台发生。 事实上，异步计算甚至可以同步执行，具体取决于计算的性质和计算执行的环境。

您应该有的主要要点是异步计算独立于主程序流。 尽管对异步计算执行的时间或方式几乎没有保证，但有一些方法来编排和调度它们。 本文的其余部分将探讨 F# 异步的核心概念以及如何使用 F# 中内置的类型、函数和表达式。

## <a name="core-concepts"></a>核心概念

在 F# 中，异步编程围绕三个核心概念：

- 表示`Async<'T>`可组合异步计算的类型。
- 模块`Async`函数允许您安排异步工作、撰写异步计算并转换异步结果。
- `async { }`[计算表达式](../../language-reference/computation-expressions.md)，为构建和控制异步计算提供了方便的语法。

您可以在以下示例中看到以下三个概念：

```fsharp
open System
open System.IO

let printTotalFileBytes path =
    async {
        let! bytes = File.ReadAllBytesAsync(path) |> Async.AwaitTask
        let fileName = Path.GetFileName(path)
        printfn "File %s has %d bytes" fileName bytes.Length
    }

[<EntryPoint>]
let main argv =
    printTotalFileBytes "path-to-file.txt"
    |> Async.RunSynchronously

    Console.Read() |> ignore
    0
```

在此示例中，`printTotalFileBytes`函数的类型`string -> Async<unit>`为 。 调用函数实际上不会执行异步计算。 相反，它返回`Async<unit>`充当以异步方式执行*的工作规范的*。 它在其`Async.AwaitTask`正文中调用，它将 的结果<xref:System.IO.File.ReadAllBytesAsync%2A>转换为适当的类型。

另一个重要的行是调用`Async.RunSynchronously`。 这是 Async 模块启动函数之一，如果要实际执行 F# 异步计算，则需要调用这些函数。

这与 C#/可视化基本`async`编程风格有根本区别。 在 F# 中，异步计算可以视为**冷任务**。 它们必须显式开始实际执行。 这具有一些优点，因为它允许您比 C# 或 Visual Basic 更容易组合和序列异步工作。

## <a name="combine-asynchronous-computations"></a>合并异步计算

下面是一个通过组合计算构建在前一个示例的基础上的示例：

```fsharp
open System
open System.IO

let printTotalFileBytes path =
    async {
        let! bytes = File.ReadAllBytesAsync(path) |> Async.AwaitTask
        let fileName = Path.GetFileName(path)
        printfn "File %s has %d bytes" fileName bytes.Length
    }

[<EntryPoint>]
let main argv =
    argv
    |> Array.map printTotalFileBytes
    |> Async.Parallel
    |> Async.Ignore
    |> Async.RunSynchronously

    0
```

正如您所看到的，该`main`函数还有更多的调用。 从概念上讲，它执行以下操作：

1. 将命令行参数转换为`Async<unit>`具有`Array.map`的计算。
2. 创建一`Async<'T[]>`个计划并在运行时并行`printTotalFileBytes`运行计算。
3. 创建将`Async<unit>`运行并行计算并忽略其结果的
4. 显式运行最后一个计算`Async.RunSynchronously`与 和 块，直到它完成。

运行此程序时，`printTotalFileBytes`每个命令行参数并行运行。 由于异步计算独立于程序流执行，因此它们无法按顺序打印其信息并完成执行。 计算将并行计划，但不能保证其执行顺序。

## <a name="sequence-asynchronous-computations"></a>序列异步计算

因为`Async<'T>`是工作规范，而不是已经运行的任务，因此可以轻松地执行更复杂的转换。 下面是一个示例，它对一组 Async 计算进行排序，以便它们逐一执行。

```fsharp
let printTotalFileBytes path =
    async {
        let! bytes = File.ReadAllBytesAsync(path) |> Async.AwaitTask
        let fileName = Path.GetFileName(path)
        printfn "File %s has %d bytes" fileName bytes.Length
    }

[<EntryPoint>]
let main argv =
    argv
    |> Array.map printTotalFileBytes
    |> Async.Sequential
    |> Async.Ignore
    |> Async.RunSynchronously
    |> ignore
```

这将按计划`printTotalFileBytes`按 的元素的顺序执行，`argv`而不是并行调度它们。 由于下一项不会计划，直到最后一次计算完成执行后，计算将进行排序，以便其执行中没有重叠。

## <a name="important-async-module-functions"></a>重要的异步模块功能

在 F# 中编写异步代码时，通常会与处理计算计划的框架进行交互。 但是，情况并非总是如此，因此最好了解各种启动函数来安排异步工作。

由于 F# 异步计算是工作_规范_，而不是已执行的工作的表示形式，因此必须显式从启动函数开始。 有许多[Async 启动函数](https://msdn.microsoft.com/library/ee370232.aspx)在不同的上下文中非常有用。 以下部分介绍一些更常见的起始函数。

### <a name="asyncstartchild"></a>异步.开始儿童

在异步计算中启动子计算。 这允许同时执行多个异步计算。 子计算与父计算共享取消令牌。 如果取消父计算，则子计算也会取消。

签名：

```fsharp
computation: Async<'T> * timeout: ?int -> Async<Async<'T>>
```

使用场合：

- 当您要同时执行多个异步计算，而不是一次执行一个异步计算时，却不希望将它们同时计划。
- 当您希望将子计算的生存期与父计算的生存期绑定时。

需要注意的：

- 使用`Async.StartChild`启动多个计算与并行调度计算计算策略不同。 如果要并行计划计算，请使用`Async.Parallel`。
- 取消父计算将触发取消它启动的所有子计算。

### <a name="asyncstartimmediate"></a>异步.立即启动

运行异步计算，立即开始在当前操作系统线程上。 如果您在计算期间需要更新调用线程上的内容，这非常有用。 例如，如果异步计算必须更新 UI（如更新进度栏），则应`Async.StartImmediate`使用。

签名：

```fsharp
computation: Async<unit> - cancellationToken: ?CancellationToken -> unit
```

使用场合：

- 当您需要在异步计算中更新调用线程上的内容时。

需要注意的：

- 异步计算中的代码将在预定的任何线程上运行。 如果该线程在某种程度上是敏感的（如 UI 线程），则可能会有问题。 在这种情况下，`Async.StartImmediate`很可能不适合使用。

### <a name="asyncstartastask"></a>异步.StartAsTask

在线程池中执行计算。 返回将在<xref:System.Threading.Tasks.Task%601>计算终止后在相应状态上完成的 的 返回 （生成结果、引发异常或被取消）。 如果未提供取消令牌，则使用默认取消令牌。

签名：

```fsharp
computation: Async<'T> - taskCreationOptions: ?TaskCreationOptions - cancellationToken: ?CancellationToken -> Task<'T>
```

使用场合：

- 当您需要调用 .NET API 时，该<xref:System.Threading.Tasks.Task%601>API 希望 表示异步计算的结果。

需要注意的：

- 此调用将分配一个`Task`附加对象，如果经常使用，可能会增加开销。

### <a name="asyncparallel"></a>异步.并行

计划要并行执行的异步计算序列。 通过指定`maxDegreesOfParallelism`参数，可以选择调整/限制并行性的程度。

签名：

```fsharp
computations: seq<Async<'T>> - ?maxDegreesOfParallelism: int -> Async<'T[]>
```

何时使用:

- 如果需要同时运行一组计算，并且不依赖于它们的执行顺序。
- 如果不需要并行计划计算的结果，直到它们全部完成。

需要注意的：

- 只有在所有计算完成后，才能访问生成的值数组。
- 计算将运行，但它们最终都会得到计划。 这意味着您不能依赖他们的执行顺序。

### <a name="asyncsequential"></a>异步。顺序

计划一系列异步计算，以便按传递顺序执行。 将执行第一个计算，然后执行下一个计算，等等。 不会并行执行任何计算。

签名：

```fsharp
computations: seq<Async<'T>> -> Async<'T[]>
```

何时使用:

- 如果需要按顺序执行多个计算。

需要注意的：

- 只有在所有计算完成后，才能访问生成的值数组。
- 计算将以传递给此函数的顺序运行，这可能意味着在返回结果之前将经过更多的时间。

### <a name="asyncawaittask"></a>异步.Await任务

返回一个异步计算，该计算等待给定<xref:System.Threading.Tasks.Task%601>的计算完成，并将其结果作为`Async<'T>`

签名：

```fsharp
task: Task<'T>  -> Async<'T>
```

使用场合：

- 使用 .NET API 时，该<xref:System.Threading.Tasks.Task%601>API 在 F# 异步计算中返回 。

需要注意的：

- 异常按照任务并行库<xref:System.AggregateException>的约定进行包装，这与 F# 异步通常显示异常的方式不同。

### <a name="asynccatch"></a>异步.捕获

创建一个异步计算，该计算执行`Async<'T>`给定的`Async<Choice<'T, exn>>`，返回 。 如果给定`Async<'T>`完成成功，则返回具有结果`Choice1Of2`值的 返回 。 如果在异常完成之前引发异常，`Choice2of2`则返回，并引发异常。 如果它用于由许多计算组成的异步计算，并且其中一个计算引发异常，则包罗万象的计算将完全停止。

签名：

```fsharp
computation: Async<'T> -> Async<Choice<'T, exn>>
```

使用场合：

- 执行异步工作时，可能会因异常而失败，并且希望在调用方中处理该异常。

需要注意的：

- 使用组合或序列异步计算时，如果包包含计算的"内部"计算之一引发异常，则包包含计算将完全停止。

### <a name="asyncignore"></a>异步.忽略

创建运行给定计算并忽略其结果的异步计算。

签名：

```fsharp
computation: Async<'T> -> Async<unit>
```

使用场合：

- 当您有不需要结果的异步计算时。 这类似于非异步`ignore`代码的代码。

需要注意的：

- 如果必须使用此，因为您希望使用`Async.Start`或其他需要`Async<unit>`的功能，请考虑丢弃结果是否可以执行。 放弃结果只是为了适合类型签名通常不应该做。

### <a name="asyncrunsynchronously"></a>异步.同步运行

运行异步计算，并在调用线程上等待其结果。 此呼叫已阻塞。

签名：

```fsharp
computation: Async<'T> - timeout: ?int - cancellationToken: ?CancellationToken -> 'T
```

何时使用:

- 如果需要，请仅在应用程序中使用它一次 - 在可执行文件的入口点。
- 当您不关心性能并希望同时执行一组其他异步操作时。

需要注意的：

- 调用`Async.RunSynchronously`阻止调用线程，直到执行完成。

### <a name="asyncstart"></a>异步.开始

在线程池中启动可异步计算，该`unit`计算返回 。 不等待结果。 从`Async.Start`开始嵌套计算完全独立于调用它们的父计算开始。 其生存期不与任何父计算相关联。 如果取消父计算，则不会取消子计算。

签名：

```fsharp
computation: Async<unit> - cancellationToken: ?CancellationToken -> unit
```

仅在：

- 异步计算不会产生结果和/或需要处理一个结果。
- 您无需知道异步计算何时完成。
- 您不关心异步计算运行哪个线程。
- 您无需了解或报告任务产生的异常。

需要注意的：

- 由开始`Async.Start`计算引发的异常不会传播到调用方。 调用堆栈将完全解功能。
- 任何有效的工作（如调用`printfn`）开始`Async.Start`不会导致在程序执行的主线程上发生效果。

## <a name="interoperate-with-net"></a>与 .NET 互操作

您可能正在使用使用[异步/await-](../../../standard/async.md)样式异步编程的 .NET 库或 C# 代码库。 由于 C# 和大多数 .NET 库使用<xref:System.Threading.Tasks.Task%601><xref:System.Threading.Tasks.Task>和 类型作为其核心抽象，而不是`Async<'T>`，您必须跨越这两种异步方法之间的边界。

### <a name="how-to-work-with-net-async-and-taskt"></a>如何使用 .NET 异步和`Task<T>`

使用 .NET 异步库和代码库（<xref:System.Threading.Tasks.Task%601>即具有返回值的异步计算）非常简单，并且具有 F# 的内置支持。

可以使用 函数`Async.AwaitTask`等待 .NET 异步计算：

```fsharp
let getValueFromLibrary param =
    async {
        let! value = DotNetLibrary.GetValueAsync param |> Async.AwaitTask
        return value
    }
```

可以使用 函数`Async.StartAsTask`将异步计算传递给 .NET 调用方：

```fsharp
let computationForCaller param =
    async {
        let! result = getAsyncResult param
        return result
    } |> Async.StartAsTask
```

### <a name="how-to-work-with-net-async-and-task"></a>如何使用 .NET 异步和`Task`

要使用使用的<xref:System.Threading.Tasks.Task>API（即 .NET 异步计算不返回值），您可能需要添加一个将 转换为`Async<'T>`的其他函数： <xref:System.Threading.Tasks.Task>

```fsharp
module Async =
    // Async<unit> -> Task
    let startTaskFromAsyncUnit (comp: Async<unit>) =
        Async.StartAsTask comp :> Task
```

已经有一个`Async.AwaitTask`接受作为<xref:System.Threading.Tasks.Task>输入的。 使用此函数和以前定义的`startTaskFromAsyncUnit`函数，可以从 F# 异<xref:System.Threading.Tasks.Task>步计算开始和等待类型。

## <a name="relationship-to-multi-threading"></a>与多线程的关系

尽管本文中提到了线程，但有两件重要的事情需要记住：

1. 除非在当前线程上显式启动，否则异步计算和线程之间没有关联。
1. F# 中的异步编程不是多线程的抽象。

例如，计算实际上可能在其调用方的线程上运行，具体取决于工作的性质。 计算还可以"跳转"线程之间，借用它们少量时间在"等待"期间（例如网络呼叫传输时）之间执行有用的工作。

尽管 F# 提供了在当前线程（或显式不在当前线程上）启动异步计算的一些功能，但异步通常不与特定的线程策略相关联。

## <a name="see-also"></a>请参阅

- [F# 异步编程模型](https://www.microsoft.com/research/publication/the-f-asynchronous-programming-model)
- [Jet.com 的 F# 异步指南](https://medium.com/jettech/f-async-guide-eb3c8a2d180a)
- [F# 用于娱乐和盈利的异步编程指南](https://fsharpforfunandprofit.com/posts/concurrency-async-and-parallel/)
- [C# 和 F# 中的异步：C 中的异步哥查#](http://tomasp.net/blog/csharp-async-gotchas.aspx/)
