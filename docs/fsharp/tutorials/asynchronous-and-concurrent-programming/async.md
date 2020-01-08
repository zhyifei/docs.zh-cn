---
title: 异步编程
description: 了解如何F#基于从核心函数编程概念派生的语言级编程模型，为异步提供干净支持。
ms.date: 12/17/2018
ms.openlocfilehash: 471566befd69f330fb9254dbd57b19569d9f9ad3
ms.sourcegitcommit: 30a558d23e3ac5a52071121a52c305c85fe15726
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/25/2019
ms.locfileid: "75344658"
---
# <a name="async-programming-in-f"></a>F 中的异步编程\#

异步编程是一种对新式应用程序至关重要的机制，原因多种多样。 大多数开发人员都将遇到两个主要用例：

- 提供可为大量并发传入请求提供服务的服务器进程，同时最大限度地减少在请求处理过程中所占用的系统资源，等待来自该进程外部的系统或服务的输入
- 在并发后台工作的同时维护响应式 UI 或主线程

尽管后台工作通常涉及多个线程的使用率，但请务必分别考虑异步和多线程的概念。 事实上，它们是单独的问题，而另一个则不是。 本文后面的内容对此进行了详细介绍。

## <a name="asynchrony-defined"></a>已定义异步

之前的一点是，异步独立于多个线程的利用率，值得进一步解释。 有时有三个相关概念，但彼此完全独立：

- 能力当多个计算在重叠的时间段内执行时。
- 度当一个计算的多个计算或多个部分在同一时间运行时。
- 异步当一个或多个计算可与主程序流分开执行时。

这三种概念都是直角概念，但可以很容易地与父，尤其是在它们一起使用时。 例如，可能需要并行执行多个异步计算。 这并不意味着并行或异步彼此不同。

如果你考虑 "异步" 一词的 etymology，则涉及两个部分：

- "a"，表示 "not"。
- "同步"，表示 "同时"。

将这两个术语组合在一起后，会看到 "异步" 表示 "不同时"。 就是这样简单！ 此定义中不存在并发或并行性的含义。 实际上也是如此。

在实际情况下，中F#的异步计算计划为独立于主程序流执行。 这并不意味着并发性或并行性，也不意味着计算始终在后台发生。 事实上，异步计算甚至可以同步执行，具体取决于计算的性质和正在执行计算的环境。

应该具有的主要要点在于是异步计算与主程序流无关。 尽管对异步计算的执行时间或方式有一些保证，但还是有一些用于协调和安排这些方法的方法。 本文的其余部分探讨了F#异步的核心概念，以及如何使用中F#内置的类型、函数和表达式。

## <a name="core-concepts"></a>核心概念

在F#中，异步编程围绕三个核心概念：

- `Async<'T>` 类型，它表示可组合的异步计算。
- `Async` 模块函数，可用于计划异步工作、撰写异步计算和转换异步结果。
- `async { }`[计算表达式](../../language-reference/computation-expressions.md)，它提供了一种用于生成和控制异步计算的方便语法。

在以下示例中，可以看到这三个概念：

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

在此示例中，`printTotalFileBytes` 函数的类型为 `string -> Async<unit>`。 调用函数实际上不会执行异步计算。 相反，它会返回一个 `Async<unit>`，它充当要异步执行的工作的*规范*。 它在其正文中调用 `Async.AwaitTask`，这会将 <xref:System.IO.File.WriteAllBytesAsync%2A> 的结果转换为适当的类型。

另一个重要的行是对 `Async.RunSynchronously`的调用。 这是要实际执行F#异步计算时需要调用的异步模块启动函数之一。

这是与 `async` 编程的C#/Visual 基本样式的根本差异。 在F#中，可以将异步计算视为**冷任务**。 它们必须显式启动才能实际执行。 这有一些优点，因为它可让你更轻松 Visual Basic 地C#组合和序列化异步工作。

## <a name="combine-asynchronous-computations"></a>合并异步计算

下面是通过组合计算在上一个示例中生成的示例：

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

正如您所看到的那样，`main` 函数进行了更多调用。 从概念上讲，它执行以下操作：

1. 将命令行参数转换为 `Array.map``Async<unit>` 计算。
2. 创建一个在运行时计划和运行 `printTotalFileBytes` 计算的 `Async<'T[]>`。
3. 创建一个将运行并行计算并忽略其结果的 `Async<unit>`。
4. 在 `Async.RunSynchronously` 和块中显式运行上次计算，直到完成。

运行此程序时，`printTotalFileBytes` 会并行运行每个命令行参数。 由于异步计算独立于程序流执行，因此它们不会打印其信息并完成执行。 将并行计划计算，但不保证其执行顺序。

## <a name="sequence-asynchronous-computations"></a>序列异步计算

由于 `Async<'T>` 是一种规范，而不是已运行的任务，因此你可以轻松地执行更复杂的转换。 下面是一个示例，该示例对一组异步计算进行排序，以便它们逐个执行。

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

这会计划 `printTotalFileBytes` 按 `argv` 元素的顺序执行，而不是并行计划它们。 因为在上一次计算执行完成后将不会计划下一项，所以，计算的顺序就是在执行时没有重叠。

## <a name="important-async-module-functions"></a>重要的异步模块函数

在中F#编写异步代码时，通常会与用于处理计算计划的框架交互。 但是，这并不总是如此，因此最好了解用于计划异步工作的各种开始函数。

因为F#异步计算是一种_规范_，而不是已在执行的工作表示形式，所以必须使用启动函数显式启动它们。 许多[异步启动函数](https://msdn.microsoft.com/library/ee370232.aspx)在不同的上下文中很有用。 以下部分介绍了一些更常见的启动函数。

### <a name="asyncstartchild"></a>StartChild

在异步计算中启动子计算。 这允许并发执行多个异步计算。 子计算与父计算共享取消标记。 如果取消了父计算，则子计算也将被取消。

签名：

```fsharp
computation: Async<'T> - timeout: ?int -> Async<Async<'T>>
```

何时使用：

- 如果要同时执行多个异步计算，而不是一次执行多个异步计算，但不需要并行计划它们。
- 如果希望将子计算的生存期与父计算的生存期关联，则为。

需要注意的事项：

- 用 `Async.StartChild` 启动多个计算与并行计划它们不同。 如果要并行计划计算，请使用 `Async.Parallel`。
- 取消父计算将触发它开始的所有子计算的取消。

### <a name="asyncstartimmediate"></a>StartImmediate

运行异步计算，在当前操作系统线程上立即启动。 如果需要在计算过程中在调用线程上更新某些内容，这会很有帮助。 例如，如果异步计算必须更新 UI （如更新进度栏），则应使用 `Async.StartImmediate`。

签名：

```fsharp
computation: Async<unit> - cancellationToken: ?CancellationToken -> unit
```

何时使用：

- 需要在异步计算的中间对调用线程进行更新时。

需要注意的事项：

- 异步计算中的代码将在要计划的任何线程上运行。 如果该线程以某种方式（例如，UI 线程）进行敏感，则可能会出现问题。 在这种情况下，`Async.StartImmediate` 可能不适合使用。

### <a name="asyncstartastask"></a>Async.startastask

在线程池中执行计算。 返回一个 <xref:System.Threading.Tasks.Task%601>，它将在计算终止后（生成结果、引发异常或取消）在相应的状态下完成。 如果未提供取消标记，则使用默认取消标记。

签名：

```fsharp
computation: Async<'T> - taskCreationOptions: ?TaskCreationOptions - cancellationToken: ?CancellationToken -> Task<'T>
```

何时使用：

- 需要调入需要 <xref:System.Threading.Tasks.Task%601> 来表示异步计算结果的 .NET API 时。

需要注意的事项：

- 此调用将分配其他 `Task` 对象，如果经常使用此对象，则可能会增加开销。

### <a name="asyncparallel"></a>Async 并行

计划要并行执行的异步计算序列。 通过指定 `maxDegreesOfParallelism` 参数，可以选择性地优化/限制并行度。

签名：

```fsharp
computations: seq<Async<'T>> - ?maxDegreesOfParallelism: int -> Async<'T[]>
```

何时使用:

- 如果需要同时运行一组计算，而不依赖于其执行顺序。
- 如果无需并行计划的计算结果，直到它们全部完成。

需要注意的事项：

- 所有计算完成后，只能访问生成的值数组。
- 计算将运行，但最终会得到计划。 这意味着不能依赖其执行顺序。

### <a name="asyncsequential"></a>异步顺序

计划一系列要按其传递顺序执行的异步计算。 将执行第一个计算，然后执行下一次计算，依次类推。 不会并行执行任何计算。

签名：

```fsharp
computations: seq<Async<'T>> -> Async<'T[]>
```

何时使用:

- 如果需要按顺序执行多个计算。

需要注意的事项：

- 所有计算完成后，只能访问生成的值数组。
- 计算将按其传递到此函数的顺序运行，这可能意味着返回结果之前需要更多时间。

### <a name="asyncawaittask"></a>Async.awaittask

返回一个异步计算，该异步计算等待给定的 <xref:System.Threading.Tasks.Task%601> 完成，并将其结果作为 `Async<'T>` 返回

签名：

```fsharp
task: Task<'T>  -> Async<'T>
```

何时使用：

- 当你使用的是在F#异步计算中返回 <xref:System.Threading.Tasks.Task%601> 的 .net API 时。

需要注意的事项：

- 异常按照任务并行库的约定 <xref:System.AggregateException> 包装，这不同于异步显示异常的方式F# 。

### <a name="asynccatch"></a>Async Catch

创建一个异步计算，该计算执行给定的 `Async<'T>`，并返回一个 `Async<Choice<'T, exn>>`。 如果给定 `Async<'T>` 成功完成，则返回具有结果值的 `Choice1Of2`。 如果在异常完成之前引发了异常，则会返回 `Choice2of2`，并引发异常。 如果它用于由多个计算组成的异步计算，并且其中一个计算引发异常，则会完全停止包含计算。

签名：

```fsharp
computation: Async<'T> -> Async<Choice<'T, exn>>
```

何时使用：

- 当你执行的异步工作可能会失败并出现异常，你希望在调用方中处理该异常。

需要注意的事项：

- 使用组合的或序列化的异步计算时，如果其中一个 "内部" 计算引发异常，则会完全停止包含计算。

### <a name="asyncignore"></a>Async。 Ignore

创建一个异步计算，该异步计算将运行给定的计算并忽略其结果。

签名：

```fsharp
computation: Async<'T> -> Async<unit>
```

何时使用：

- 如果具有不需要其结果的异步计算。 这类似于非异步代码的 `ignore` 代码。

需要注意的事项：

- 如果你必须使用此功能，因为你希望使用 `Async.Start` 或需要 `Async<unit>`的其他函数，则请考虑是否放弃结果是可以的。 通常不应丢弃结果来满足类型签名。

### <a name="asyncrunsynchronously"></a>RunSynchronously

运行异步计算，并在调用线程上等待其结果。 此调用正在阻止。

签名：

```fsharp
computation: Async<'T> - timeout: ?int - cancellationToken: ?CancellationToken -> 'T
```

何时使用:

- 如果需要，请在应用程序的入口点（可执行文件）中使用它一次。
- 当你不关心性能并希望同时执行一组其他异步操作时。

需要注意的事项：

- 调用 `Async.RunSynchronously` 会阻止调用线程，直到执行完成。

### <a name="asyncstart"></a>Async. Start

在线程池中启动异步计算，该计算返回 `unit`。 不会等待其结果。 `Async.Start` 启动的嵌套计算完全独立于调用它们的父计算。 它们的生存期未绑定到任何父计算。 如果取消了父计算，则不会取消任何子计算。

签名：

```fsharp
computation: Async<unit> - cancellationToken: ?CancellationToken -> unit
```

仅在以下情况时使用：

- 您有一个异步计算，该计算不产生结果和/或需要处理一个结果。
- 不需要知道异步计算何时完成。
- 您不关心异步计算在哪个线程上运行。
- 您无需注意或报告由任务生成的异常。

需要注意的事项：

- 通过 `Async.Start` 开始的计算引发的异常不会传播到调用方。 调用堆栈将被完全展开。
- 使用 `Async.Start` 启动的任何 effectful 工作（例如调用 `printfn`）都不会导致在程序执行的主线程上发生效果。

## <a name="interoperate-with-net"></a>与 .NET 交互

你可以使用 .NET 库或C#使用[async/await](../../../standard/async.md)样式异步编程的基本代码。 由于C#大多数 .net 库使用 <xref:System.Threading.Tasks.Task%601>，并 <xref:System.Threading.Tasks.Task> 类型作为其核心抽象，而不是 `Async<'T>`，因此必须将这两种方法之间的边界跨越异步。

### <a name="how-to-work-with-net-async-and-taskt"></a>如何使用 .NET async 和 `Task<T>`

使用 <xref:System.Threading.Tasks.Task%601> 的 .NET 异步库和基本代码（即，具有返回值的异步计算）非常简单，并且具有的F#内置支持。

您可以使用 `Async.AwaitTask` 函数来等待 .NET 异步计算：

```fsharp
let getValueFromLibrary param =
    async {
        let! value = DotNetLibrary.GetValueAsync param |> Async.AwaitTask
        return value
    }
```

可以使用 `Async.StartAsTask` 函数将异步计算传递到 .NET 调用方：

```fsharp
let computationForCaller param =
    async {
        let! result = getAsyncResult param
        return result
    } |> Async.StartAsTask
```

### <a name="how-to-work-with-net-async-and-task"></a>如何使用 .NET async 和 `Task`

若要使用 <xref:System.Threading.Tasks.Task> （即，不返回值的 .NET async 计算）的 Api，你可能需要添加一个将 `Async<'T>` 转换为 <xref:System.Threading.Tasks.Task>的其他函数：

```fsharp
module Async =
    // Async<unit> -> Task
    let startTaskFromAsyncUnit (comp: Async<unit>) =
        Async.StartAsTask comp :> Task
```

已存在接受作为输入的 <xref:System.Threading.Tasks.Task> 的 `Async.AwaitTask`。 使用此函数和先前定义的 `startTaskFromAsyncUnit` 函数，可以从F#异步计算启动和等待 <xref:System.Threading.Tasks.Task> 类型。

## <a name="relationship-to-multi-threading"></a>与多线程的关系

尽管本文介绍了线程处理，但要记住以下两个重要事项：

1. 除非在当前线程上显式启动，否则异步计算与线程之间没有关联。
1. 中F#的异步编程不是多线程的抽象。

例如，根据工作的性质，计算实际上可以在其调用方的线程上运行。 计算也可以在线程之间 "跳转"，从而在 "等待" 的时间间隔（例如，当网络调用正在传输时）使用一小段时间完成有用的工作。

尽管F#提供了在当前线程上启动异步计算的某些功能（或不显式在当前线程上），但异步通常不与特定的线程策略相关联。

## <a name="see-also"></a>另请参阅

- [F#异步编程模型](https://www.microsoft.com/research/publication/the-f-asynchronous-programming-model)
- [Jet .com 的F# Async Guide](https://medium.com/jettech/f-async-guide-eb3c8a2d180a)
- [F#获取趣味和利润的异步编程指南](https://fsharpforfunandprofit.com/posts/concurrency-async-and-parallel/)
- [C#和F#中的异步：中的异步陷阱C#](http://tomasp.net/blog/csharp-async-gotchas.aspx/)
