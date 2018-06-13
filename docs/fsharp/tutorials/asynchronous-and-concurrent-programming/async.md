---
title: 'F # 中的异步编程'
description: '了解如何通过是易于使用和自然语言的语言级别编程模型实现 F # 异步编程。'
ms.date: 06/20/2016
ms.openlocfilehash: 93ecd05efc493489435214dcd7ae78fffcccec1f
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33566868"
---
# <a name="async-programming-in-f"></a>F # 中的异步编程 #

> [!NOTE]
> 已在本文中发现了一些不精确性。  它是正在重写。  请参阅[问题 #666](https://github.com/dotnet/docs/issues/666)若要了解有关所做的更改。

异步编程 F # 中可以通过设计为易于使用和自然语言的语言级别编程模型来完成。

F # 中的异步编程的核心是`Async<'T>`，可以触发在后台中运行的工作的表示其中`'T`通过这两个特殊返回的任一类型`return`关键字或`unit`如果异步工作流未包含任何若要返回的结果。

若要了解的关键概念是一个异步表达式的类型是`Async<'T>`，即仅_规范_进行异步上下文中工作。 它不执行显式启动之前与起始函数之一 (如`Async.RunSynchronously`)。 虽然这是另一种执行工作的考虑，它最终正在实际上非常简单。

例如，假设你想要从 dotnetfoundation.org 下载 HTML，而不会阻止主线程。 你可以实现它如下：

```fsharp
open System
open System.Net

let fetchHtmlAsync url = 
    async {
        let uri = Uri(url)
        use webClient = new WebClient()

        // Execution of fetchHtmlAsync won't continue until the result
        // of AsyncDownloadString is bound.
        let! html = webClient.AsyncDownloadString(uri)
        return html
    }

let html = "https://dotnetfoundation.org" |> fetchHtmlAsync |> Async.RunSynchronously
printfn "%s" html
```

就是这么简单！ 除了使用外`async`， `let!`，和`return`，这是仅正常 F # 代码。

有几个语法构造该数据类型值得注意：

*   `let!` 将绑定 （它运行在另一个上下文） 异步表达式的结果。
*   `use!` 工作方式就像`let!`，但在超出范围时释放其绑定的资源。
*   `do!` 将等待异步工作流，它不返回任何内容。
*   `return` 只需从一个异步表达式将返回结果。
*   `return!` 执行另一个异步工作流并返回其返回值作为结果。

此外，普通`let`， `use`，和`do`关键字可以与异步版本一起使用，就像一个常规函数中。

## <a name="how-to-start-async-code-in-f"></a>如何启动 F # 中的异步代码 #

如前所述，异步代码是的需要显式启动另一个上下文中进行工作的规范。 以下是两种主要方式来实现此目的：

1.  `Async.RunSynchronously` 将在另一个线程上启动的异步工作流，并等待其结果。

```fsharp
open System
open System.Net

let fetchHtmlAsync url = 
    async {
        let uri = Uri(url)
        use webClient = new WebClient()
        let! html = webClient.AsyncDownloadString(uri)
        return html
    }

 // Execution will pause until fetchHtmlAsync finishes
 let html = "https://dotnetfoundation.org" |> fetchHtmlAsync |> Async.RunSynchronously

 // you actually have the result from fetchHtmlAsync now!
 printfn "%s" html
 ```

2.  `Async.Start` 将在另一个线程上启动的异步工作流并将**不**等待其结果。

```fsharp
open System
open System.Net
  
let uploadDataAsync url data = 
    async {
        let uri = Uri(url)
        use webClient = new WebClient()
        webClient.UploadStringAsync(uri, data)
    }

let workflow = uploadDataAsync "https://url-to-upload-to.com" "hello, world!"

// Execution will continue after calling this!
Async.Start(workflow)

printfn "%s" "uploadDataAsync is running in the background..."
 ```

还有其他方法来启动异步工作流可用于更具体的方案。 对其进行详细[异步引用中](https://msdn.microsoft.com/library/ee370232.aspx)。

### <a name="a-note-on-threads"></a>在线程上注释

上述"在另一个线程"短语，但务必要知道**这并不意味着异步工作流是的外观的多线程处理**。 工作流实际上"跳转"之间线程，借贷它们对于少量的时间来执行有用的工作。 时的异步工作流有效地"等待"（例如，等待为返回的内容的网络调用），它已在时间借贷任何线程将被释放到转有用的工作上其他内容。 这允许的系统在其运行尽可能情况下，有效地利用异步工作流，并使它们尤其是对于大量 I/O 方案强。

## <a name="how-to-add-parallelism-to-async-code"></a>如何将并行添加到异步代码

有时你可能需要并行执行多个异步作业收集其结果和解释它们以某种方式。 `Async.Parallel` 允许你执行此操作而无需使用任务并行库，这将涉及到无需强制`Task<'T>`和`Async<'T>`类型。

下面的示例将使用`Async.Parallel`若要从并行的四个流行网站下载的 HTML，等待这些任务完成，然后输出下载的 HTML。

```fsharp
open System
open System.Net

let urlList = 
    [ "https://www.microsoft.com"
      "https://www.google.com"
      "https://www.amazon.com"
      "https://www.facebook.com" ]

let fetchHtmlAsync url = 
    async {
        let uri = Uri(url)
        use webClient = new WebClient()
        let! html = webClient.AsyncDownloadString(uri)
        return html
    }

let getHtmlList urls =
    urls
    |> Seq.map fetchHtmlAsync   // Build an Async<'T> for each site
    |> Async.Parallel           // Returns an Async<'T []>
    |> Async.RunSynchronously   // Wait for the result of the parallel work

let htmlList = getHtmlList urlList

// We now have the downloaded HTML for each site!
for html in htmlList do
    printfn "%s" html
```

## <a name="important-info-and-advice"></a>重要信息和建议

*   将"Async"追加到你将使用的任何函数的末尾

 尽管这是命名约定，但它确实使 API 可发现性等更容易。 特别是如果有相同的例程的同步和异步版本，则这是异步通过名称来显式声明一个好办法。

*   侦听编译器 ！

 F # 编译器是非常严格，使几乎不可能执行其他操作如 troubling 同步运行"async"代码。 如果您遇到一条警告，则代码不会执行你认为它将一个符号。 如果编译器可以为取悦，你的代码将很可能会按预期方式执行。

## <a name="for-the-cvb-programmer-looking-into-f"></a>为 C# /VB 程序员研究 F # #

本部分假定你熟悉 C# 中的异步模型 / VB. 如果你不可以， [C# 中的异步编程](../../../csharp/async.md)是一个起始点。

没有本质上 C# /VB 异步模型和 F # 异步模型之间的区别。

当调用返回的函数`Task`或`Task<'T>`，该作业是否已经开始执行。 返回的句柄表示已在运行异步作业。 与此相反，当你调用的异步函数在 F # 中，`Async<'a>`返回表示一个作业，它将**生成**在某个时间点。 了解此模型是功能强大，因为它允许 F # 中的异步作业可以链接在一起变得更容易，有条件地执行和入门的更细粒度的控制。

有几个其他的相似之处和值得注意的区别。

### <a name="similarities"></a>相似之处

*   `let!``use!`，和`do!`类似于`await`内调用异步作业时`async{ }`块。

 三个关键字只能在`async { }`块，类似于如何`await`仅会在内部进行调用`async`方法。 简单地说，`let!`是为了确保你想要捕获和使用的结果时`use!`内容应会清理其资源，使用它之后, 是同一但和`do!`适用于你想要等待的异步工作流完成不返回值再继续。

*   F # 支持类似的方式的数据并行。

 虽然它的操作方式差别很大，`Async.Parallel`对应于`Task.WhenAll`了所需的一组异步作业的结果，它们都完成时的方案。

### <a name="differences"></a>差异

*   嵌套`let!`不允许，与不同嵌套 `await`

 与不同`await`，可以嵌套; 如果无限期，`let!`无法，并且必须绑定使用在另一个内部之前其结果`let!`， `do!`，或`use!`。

*   取消支持为在 F # 中比在 C# 中更简单 / VB.

 在 C# /VB 中支持的中途其执行任务的取消需要检查`IsCancellationRequested`属性或调用`ThrowIfCancellationRequested()`上`CancellationToken`传递给异步方法的对象。

与此相反，F # 异步工作流是更自然可取消的。 取消是一个简单的三个步骤过程。

1.  创建一个新的 `CancellationTokenSource`。
2.  将它传递到起始函数。
3.  调用`Cancel`令牌上。

示例:

```fsharp
open System
open System.Net

let uploadDataAsync url data = 
    async {
        let uri = Uri(url)
        use webClient = new WebClient()
        webClient.UploadStringAsync(uri, data)
    }

let workflow = uploadDataAsync "https://url-to-upload-to.com" "hello, world!"

let token = new CancellationTokenSource()
Async.Start (workflow, token)

// Immediately cancel uploadDataAsync after it's been started.
token.Cancel()
```

就是这么简单！

## <a name="further-resources"></a>其他资源：

*   [MSDN 上的异步工作流](https://msdn.microsoft.com/library/dd233250.aspx)
*   [F # 的异步序列](https://fsprojects.github.io/FSharp.Control.AsyncSeq/library/AsyncSeq.html)
*   [F # 数据 HTTP 实用程序](https://fsharp.github.io/FSharp.Data/library/Http.html)
