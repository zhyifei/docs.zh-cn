---
title: "使用基于任务的异步模式"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- .NET Framework, and TAP
- asynchronous design patterns, .NET Framework
- TAP, .NET Framework support for
- Task-based Asynchronous Pattern, .NET Framework support for
- .NET Framework, asynchronous design patterns
ms.assetid: 033cf871-ae24-433d-8939-7a3793e547bf
caps.latest.revision: "15"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 90b2a36f0e6bf06b0fefe2191d5b17c9c07d1588
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="consuming-the-task-based-asynchronous-pattern"></a>使用基于任务的异步模式
使用基于任务的异步模式 (TAP) 处理异步操作时，可以使用回叫实现等待，而不会阻塞。  对于任务，这将通过实现方法如<xref:System.Threading.Tasks.Task.ContinueWith%2A?displayProperty=nameWithType>。 通过允许在正常控制流中等待异步操纵，基于语言的异步支持可隐藏回叫，并且编译器生成的代码可提供此相同 API 级别的支持。  
  
## <a name="suspending-execution-with-await"></a>使用 Await 挂起执行  
 从开始[!INCLUDE[net_v45](../../../includes/net-v45-md.md)]，你可以使用[await](~/docs/csharp/language-reference/keywords/await.md) C# 中的关键字和[Await 运算符](~/docs/visual-basic/language-reference/operators/await-operator.md)在 Visual Basic 中以异步方式等待<xref:System.Threading.Tasks.Task>和<xref:System.Threading.Tasks.Task%601>对象。 当正在等待<xref:System.Threading.Tasks.Task>、`await`表达式是否属于类型`void`。 当正在等待<xref:System.Threading.Tasks.Task%601>、`await`表达式是否属于类型`TResult`。 `await` 表达式必须出现在异步方法的正文内。 若要详细了解 [!INCLUDE[net_v45](../../../includes/net-v45-md.md)] 中的 C# 和 Visual Basic 语言支持，请参阅 C# 和 Visual Basic 语言规范。  
  
 实际上，await 功能通过使用延续任务在任务上安装回叫。  此回叫在挂起点恢复异步方法。 如果等待的操作已成功完成，并且该异步方法恢复<xref:System.Threading.Tasks.Task%601>，将其`TResult`返回。  如果<xref:System.Threading.Tasks.Task>或<xref:System.Threading.Tasks.Task%601>，已等待由于结束<xref:System.Threading.Tasks.TaskStatus.Canceled>状态，<xref:System.OperationCanceledException>引发异常。  如果<xref:System.Threading.Tasks.Task>或<xref:System.Threading.Tasks.Task%601>，已等待由于结束<xref:System.Threading.Tasks.TaskStatus.Faulted>状态时，异常导致错误。 一个 `Task` 可能由于多个异常而出错，但只会传播一个异常。 但是，<xref:System.Threading.Tasks.Task.Exception%2A?displayProperty=nameWithType>属性返回<xref:System.AggregateException>包含的所有错误的异常。  
  
 如果同步上下文 (<xref:System.Threading.SynchronizationContext>对象) 与已在挂起的时间执行的异步方法的线程关联 (例如，如果<xref:System.Threading.SynchronizationContext.Current%2A?displayProperty=nameWithType>属性不是`null`)，异步方法上，将恢复通过使用上下文的相同的同步上下文<xref:System.Threading.SynchronizationContext.Post%2A>方法。 否则，它依赖于任务计划程序 (<xref:System.Threading.Tasks.TaskScheduler>对象)，是时挂起的最新。 通常，这是默认任务计划程序 (<xref:System.Threading.Tasks.TaskScheduler.Default%2A?displayProperty=nameWithType>)，其中针对线程池。 此任务计划程序确定等待的异步操作是否应在该操作完成时恢复，或是否应计划该恢复。 默认计划程序通常允许在完成等待操作的线程上延续任务。  
  
 调用异步方法时，将同步执行函数的正文，直到遇见尚未完成的可等待实例上的第一个 await 表达式，此时调用返回到调用方。 如果异步方法不返回`void`、<xref:System.Threading.Tasks.Task>或<xref:System.Threading.Tasks.Task%601>返回对象来表示正在进行计算。 在非 void 的异步方法，如果遇到的 return 语句或到达方法主体的结尾，将在任务完成中<xref:System.Threading.Tasks.TaskStatus.RanToCompletion>最终状态。 如果未经处理的异常会使控件在保留异步方法的正文的任务结束中<xref:System.Threading.Tasks.TaskStatus.Faulted>状态。 如果该异常是<xref:System.OperationCanceledException>，以改为结束任务<xref:System.Threading.Tasks.TaskStatus.Canceled>状态。 通过此方式，最终将发布结果或异常。  
  
 此行为有几种重要特殊情况。  出于性能原因，如果任务在等待时已完成，则不会生成控件，并且该函数将继续执行。  返回到原始上下文并不总是所需的行为，可对其进行更改；将在下一节中更详细地描述此内容。  
  
### <a name="configuring-suspension-and-resumption-with-yield-and-configureawait"></a>使用 Yield 和 ConfigureAwait 配置挂起和恢复  
 有多种方法可更好地控制异步方法的执行。 例如，你可以使用<xref:System.Threading.Tasks.Task.Yield%2A?displayProperty=nameWithType>yield 点引入的异步方法的方法：  
  
```csharp  
public class Task : …  
{  
    public static YieldAwaitable Yield();  
    …  
}  
```  
  
 这相当于以异步方式发布或计划返回当前上下文。  
  
```csharp  
Task.Run(async delegate  
{  
    for(int i=0; i<1000000; i++)  
    {  
        await Task.Yield(); // fork the continuation into a separate work item  
        ...  
    }  
});  
```  
  
 你还可以使用<xref:System.Threading.Tasks.Task.ConfigureAwait%2A?displayProperty=nameWithType>更好地控制挂起和继续在异步方法的方法。  如前所述，默认情况下，异步方法挂起时会捕获当前上下文，捕获的上下文用于在恢复时调用异步方法的延续。  在多数情况下，这就是你所需的确切行为。  在其他情况下，你可能不关心延续上下文，则可以通过避免此类发布返回原始上下文来获得更好的性能。  若要启用此功能，使用<xref:System.Threading.Tasks.Task.ConfigureAwait%2A?displayProperty=nameWithType>方法，以通知无法捕获和上下文，在继续，但若要继续执行，只要已正在等待异步操作完成等待操作：  
  
```csharp  
await someTask.ConfigureAwait(continueOnCapturedContext:false);  
```  
  
## <a name="canceling-an-asynchronous-operation"></a>取消异步操作  
 从开始[!INCLUDE[net_v40_long](../../../includes/net-v40-long-md.md)]，支持取消的 TAP 方法提供接受取消标记的至少一个重载 (<xref:System.Threading.CancellationToken>对象)。  
  
 通过取消标记源创建一个取消标记 (<xref:System.Threading.CancellationTokenSource>对象)。  源的<xref:System.Threading.CancellationTokenSource.Token%2A>属性返回对其发出信号的取消标记时的源<xref:System.Threading.CancellationTokenSource.Cancel%2A>调用方法。  例如，如果你想要下载单个网页，并且你想要能够取消操作，则创建<xref:System.Threading.CancellationTokenSource>对象，将其标记传递给 TAP 方法，然后调用的源<xref:System.Threading.CancellationTokenSource.Cancel%2A>方法如果你已准备好取消该操作：  
  
```csharp  
var cts = new CancellationTokenSource();  
string result = await DownloadStringAsync(url, cts.Token);  
… // at some point later, potentially on another thread  
cts.Cancel();  
```  
  
 若要取消多个异步调用，可以将相同令牌传递给所有调用：  
  
```csharp  
var cts = new CancellationTokenSource();  
    IList<string> results = await Task.WhenAll(from url in urls select DownloadStringAsync(url, cts.Token));  
    // at some point later, potentially on another thread  
    …  
    cts.Cancel();  
```  
  
 或者，将相同令牌传递给操作的选择性子集：  
  
```csharp  
var cts = new CancellationTokenSource();  
    byte [] data = await DownloadDataAsync(url, cts.Token);  
    await SaveToDiskAsync(outputPath, data, CancellationToken.None);  
    … // at some point later, potentially on another thread  
    cts.Cancel();  
```  
  
 可以从任意线程启动取消请求。  
  
 你可以将传递<xref:System.Threading.CancellationToken.None%2A?displayProperty=nameWithType>到的任何方法都接受取消标记以指示永远不会将请求取消的值。  这将导致<xref:System.Threading.CancellationToken.CanBeCanceled%2A?displayProperty=nameWithType>属性以返回`false`，并调用的方法可以相应地优化。  出于测试目的，还可以通过传入预取消标记（该标记使用接受布尔值的构造函数进行实例化）来指示是否应以已取消或未取消状态启动标记。  
  
 使用此方法进行取消具有以下优点：  
  
-   可以将相同的取消标记传递给任意数量的异步和同步操作。  
  
-   相同的取消请求可能会扩展到任意数量的侦听器。  
  
-   异步 API 的开发人员可完全控制是否可以请求取消以及取消何时生效。  
  
-   使用 API 的代码可以选择性地确定将对其传播取消请求的异步调用。  
  
## <a name="monitoring-progress"></a>监视进度  
 某些异步方法通过传入异步方法的进度接口来公开进度。  例如，设想某个函数以异步方式下载文本字符串，并在该过程中引发包括到目前为止下载完成百分比的进度更新。  此类方法可在 Windows Presentation Foundation (WPF) 应用程序中使用，如下所示：  
  
```csharp  
private async void btnDownload_Click(object sender, RoutedEventArgs e)    
{  
    btnDownload.IsEnabled = false;  
    try  
    {  
        txtResult.Text = await DownloadStringAsync(txtUrl.Text,   
            new Progress<int>(p => pbDownloadProgress.Value = p));  
    }  
    finally { btnDownload.IsEnabled = true; }  
}  
```  
  
<a name="combinators"></a>   
## <a name="using-the-built-in-task-based-combinators"></a>使用内置的基于任务的连结符  
 <xref:System.Threading.Tasks>命名空间包括编写和使用任务的几个方法。  
  
### <a name="taskrun"></a>Task.Run  
 <xref:System.Threading.Tasks.Task>类包括几个<xref:System.Threading.Tasks.Task.Run%2A>方法可让你轻松将作为工作卸载<xref:System.Threading.Tasks.Task>或<xref:System.Threading.Tasks.Task%601>到线程池，例如：  
  
```csharp  
public async void button1_Click(object sender, EventArgs e)  
{  
    textBox1.Text = await Task.Run(() =>  
    {  
        // … do compute-bound work here  
        return answer;  
    });  
}  
```  
  
 其中一些<xref:System.Threading.Tasks.Task.Run%2A>方法，如<xref:System.Threading.Tasks.Task.Run%28System.Func%7BSystem.Threading.Tasks.Task%7D%29?displayProperty=nameWithType>重载中，作为速记存在<xref:System.Threading.Tasks.TaskFactory.StartNew%2A?displayProperty=nameWithType>方法。  其他重载，如<xref:System.Threading.Tasks.Task.Run%28System.Func%7BSystem.Threading.Tasks.Task%7D%29?displayProperty=nameWithType>，启用用于等待中卸载的工作，例如：  
  
```csharp  
public async void button1_Click(object sender, EventArgs e)  
{  
    pictureBox1.Image = await Task.Run(async() =>  
    {  
        using(Bitmap bmp1 = await DownloadFirstImageAsync())  
        using(Bitmap bmp2 = await DownloadSecondImageAsync())  
        return Mashup(bmp1, bmp2);  
    });  
}  
```  
  
 此类重载是逻辑上等效于使用<xref:System.Threading.Tasks.TaskFactory.StartNew%2A?displayProperty=nameWithType>方法结合<xref:System.Threading.Tasks.TaskExtensions.Unwrap%2A>任务并行库中的扩展方法。  
  
### <a name="taskfromresult"></a>Task.FromResult  
 使用<xref:System.Threading.Tasks.Task.FromResult%2A>方法中的方案数据可能已可用，而只是需要返回到提升的返回任务的方法从<xref:System.Threading.Tasks.Task%601>:  
  
```csharp  
public Task<int> GetValueAsync(string key)  
{  
    int cachedValue;  
    return TryGetCachedValue(out cachedValue) ?  
        Task.FromResult(cachedValue) :  
        GetValueAsyncInternal();  
}  
  
private async Task<int> GetValueAsyncInternal(string key)  
{  
    …  
}  
```  
  
### <a name="taskwhenall"></a>Task.WhenAll  
 使用<xref:System.Threading.Tasks.Task.WhenAll%2A>方法异步等待多个表示为任务的异步操作。  该方法所具有的多个重载支持一组非泛型任务或一组不统一的常规任务（如异步等待多个返回 void 的操作，或异步等待多个返回值的方法，其中每个值可能具有不同类型），并支持一组统一的常规任务（如异步等待多个 `TResult` 返回方法）。  
  
 假设你想要向多个客户发送电子邮件。 你可以重叠发送邮件，因此发送邮件时无需等待上一封邮件完成发送。 还可以查看发送操作完成的时间，以及是否发生了错误：  
  
```csharp  
IEnumerable<Task> asyncOps = from addr in addrs select SendMailAsync(addr);  
await Task.WhenAll(asyncOps);  
```  
  
 此代码不显式处理的异常可能会发生，但允许异常传播`await`从生成的任务上<xref:System.Threading.Tasks.Task.WhenAll%2A>。  若要处理该异常，可以使用以下代码：  
  
```csharp  
IEnumerable<Task> asyncOps = from addr in addrs select SendMailAsync(addr);  
try  
{  
    await Task.WhenAll(asyncOps);  
}  
catch(Exception exc)  
{  
    ...  
}  
```  
  
 在这种情况下，如果任何异步操作失败，所有异常将都合并在<xref:System.AggregateException>异常，它存储在<xref:System.Threading.Tasks.Task>从返回<xref:System.Threading.Tasks.Task.WhenAll%2A>方法。  但是，仅通过 `await` 关键字传播其中一个异常。  如果想要检查所有异常，可以重写前面的代码，如下所示：  
  
```csharp  
Task [] asyncOps = (from addr in addrs select SendMailAsync(addr)).ToArray();  
try  
{  
    await Task.WhenAll(asyncOps);  
}  
catch(Exception exc)  
{  
    foreach(Task faulted in asyncOps.Where(t => t.IsFaulted))  
    {  
        … // work with faulted and faulted.Exception  
    }  
}  
```  
  
 让我们考虑一下以异步方式从 Web 下载多个文件的示例。  在此示例中，所有异步操作具有相同的结果类型，并很容易对结果进行访问：  
  
```csharp  
string [] pages = await Task.WhenAll(  
    from url in urls select DownloadStringAsync(url));  
```  
  
 可以使用上一个返回 void 方案中所讨论的异常处理技术：  
  
```csharp  
Task [] asyncOps =   
    (from url in urls select DownloadStringAsync(url)).ToArray();  
try  
{  
    string [] pages = await Task.WhenAll(asyncOps);  
    ...  
}  
catch(Exception exc)  
{  
    foreach(Task<string> faulted in asyncOps.Where(t => t.IsFaulted))  
    {  
        … // work with faulted and faulted.Exception  
    }  
}  
```  
  
### <a name="taskwhenany"></a>Task.WhenAny  
 你可以使用<xref:System.Threading.Tasks.Task.WhenAny%2A>方法以异步方式等待仅仅是一个多个异步操作表示为任务完成。  此方法适用于四个主要用例：  
  
-   冗余：多次执行一个操作并选择最先完成的一次（例如，联系能够生成一个结果的多个股市行情 Web 服务并选择完成最快的一个）。  
  
-   交错：启动多个操作并等待所有这些操作完成，但是在完成这些操作时对其进行处理。  
  
-   限制：允许其他操作完成时开始附加操作。  这是交错方案的扩展。  
  
-   早期释放：例如，用任务 t1 表示的操作可以与任务 t2 组成 <xref:System.Threading.Tasks.Task.WhenAny%2A> 任务，您可以等待 <xref:System.Threading.Tasks.Task.WhenAny%2A> 任务。 任务 t2 可表示超时，或取消或导致的一些其他信号<xref:System.Threading.Tasks.Task.WhenAny%2A>任务 t1 完成之前完成。  
  
#### <a name="redundancy"></a>冗余  
 假设你想要决定是否购买股票。  你信任一些股票建议 Web 服务，但每个服务最终会在不同的时间段变得很慢，具体取决于每日负载。  你可以使用<xref:System.Threading.Tasks.Task.WhenAny%2A>方法以在任何操作完成时接收通知：  
  
```csharp  
var recommendations = new List<Task<bool>>()   
{   
    GetBuyRecommendation1Async(symbol),   
    GetBuyRecommendation2Async(symbol),  
    GetBuyRecommendation3Async(symbol)  
};  
Task<bool> recommendation = await Task.WhenAny(recommendations);  
if (await recommendation) BuyStock(symbol);  
```  
  
 与不同<xref:System.Threading.Tasks.Task.WhenAll%2A>，这会返回已成功完成的所有任务的解包的结果<xref:System.Threading.Tasks.Task.WhenAny%2A>返回完成的任务。 如果任务失败，重要的是知道该任务失败，如果任务成功，重要的是知道返回值与哪个任务相关联。  因此，您需要访问返回任务的结果，或进一步等待，如本示例中所示。  
  
 与<xref:System.Threading.Tasks.Task.WhenAll%2A>，您必须能够容纳异常。  因为接收到完成的任务后，可以等待返回的任务传播错误，并适当地进行 `try/catch`，例如：  
  
```csharp  
Task<bool> [] recommendations = …;  
while(recommendations.Count > 0)  
{   
    Task<bool> recommendation = await Task.WhenAny(recommendations);      
    try  
    {  
        if (await recommendation) BuyStock(symbol);  
        break;  
    }  
    catch(WebException exc)  
    {  
        recommendations.Remove(recommendation);  
    }  
}  
```  
  
 此外，即使第一个任务成功完成，后续任务也可能会失败。  此时，可以有多个选择来处理异常：可以等待所有启动的任务完成，这种情况可以使用 <xref:System.Threading.Tasks.Task.WhenAll%2A> 方法，或者决定所有异常是否重要且必须记录。  为此，可以使用延续任务以在任务异步完成时接收通知：  
  
```csharp  
foreach(Task recommendation in recommendations)  
{  
    var ignored = recommendation.ContinueWith(  
        t => { if (t.IsFaulted) Log(t.Exception); });  
}  
```  
  
 或：  
  
```csharp  
foreach(Task recommendation in recommendations)  
{  
    var ignored = recommendation.ContinueWith(  
        t => Log(t.Exception), TaskContinuationOptions.OnlyOnFaulted);  
}  
```  
  
 或者甚至：  
  
```  
private static async void LogCompletionIfFailed(IEnumerable<Task> tasks)  
{  
    foreach(var task in tasks)  
    {  
        try { await task; }  
        catch(Exception exc) { Log(exc); }  
    }  
}  
…  
LogCompletionIfFailed(recommendations);  
```  
  
 最后，若要取消所有剩余操作：  
  
```csharp  
var cts = new CancellationTokenSource();  
var recommendations = new List<Task<bool>>()   
{   
    GetBuyRecommendation1Async(symbol, cts.Token),   
    GetBuyRecommendation2Async(symbol, cts.Token),  
    GetBuyRecommendation3Async(symbol, cts.Token)  
};  
  
Task<bool> recommendation = await Task.WhenAny(recommendations);  
cts.Cancel();  
if (await recommendation) BuyStock(symbol);  
```  
  
#### <a name="interleaving"></a>交错  
 假设你要从 Web 下载图像，并且处理每个图像（例如，将图像添加到 UI 控件）。  必须在 UI 线程上按顺序对其进行处理，但你希望尽可能同时下载图像。 此外，你不想直到所有图像都下载完成才将图像添加到 UI — 你希望图像下载完成后就进行添加：  
  
```csharp  
List<Task<Bitmap>> imageTasks =   
    (from imageUrl in urls select GetBitmapAsync(imageUrl)).ToList();  
while(imageTasks.Count > 0)  
{  
    try  
    {  
        Task<Bitmap> imageTask = await Task.WhenAny(imageTasks);  
        imageTasks.Remove(imageTask);  
  
        Bitmap image = await imageTask;  
        panel.AddImage(image);  
    }  
    catch{}  
}  
```  
  
 你还可以应用到的方案，在涉及计算密集型处理交错<xref:System.Threading.ThreadPool>下载的图像; 例如：  
  
```csharp  
List<Task<Bitmap>> imageTasks =   
    (from imageUrl in urls select GetBitmapAsync(imageUrl)  
         .ContinueWith(t => ConvertImage(t.Result)).ToList();  
while(imageTasks.Count > 0)  
{  
    try  
    {  
        Task<Bitmap> imageTask = await Task.WhenAny(imageTasks);  
        imageTasks.Remove(imageTask);  
  
        Bitmap image = await imageTask;  
        panel.AddImage(image);  
    }  
    catch{}  
}  
```  
  
#### <a name="throttling"></a>遏制  
 请考虑交错示例，因用户大量下载图像而导致下载必须受到遏制除外；例如，你希望仅能同时下载特定数目的内容。 为此，可以启动异步操作的子集。  操作完成后，你可以启动其他操作对其进行替代：  
  
```csharp  
const int CONCURRENCY_LEVEL = 15;  
Uri [] urls = …;  
int nextIndex = 0;  
var imageTasks = new List<Task<Bitmap>>();  
while(nextIndex < CONCURRENCY_LEVEL && nextIndex < urls.Length)  
{  
    imageTasks.Add(GetBitmapAsync(urls[nextIndex]));  
    nextIndex++;  
}  
  
while(imageTasks.Count > 0)  
{  
    try  
    {  
        Task<Bitmap> imageTask = await Task.WhenAny(imageTasks);  
        imageTasks.Remove(imageTask);  
  
        Bitmap image = await imageTask;  
        panel.AddImage(image);  
    }  
    catch(Exception exc) { Log(exc); }  
  
    if (nextIndex < urls.Length)  
    {  
        imageTasks.Add(GetBitmapAsync(urls[nextIndex]));  
        nextIndex++;  
    }  
}  
```  
  
#### <a name="early-bailout"></a>早期释放  
 假设正在异步等待某个操作完成的同时，对用户的取消请求的进行响应（例如，用户单击取消按钮）。 以下代码阐释了此方案：  
  
```csharp  
private CancellationTokenSource m_cts;   
  
public void btnCancel_Click(object sender, EventArgs e)  
{  
    if (m_cts != null) m_cts.Cancel();  
}  
  
public async void btnRun_Click(object sender, EventArgs e)  
{  
    m_cts = new CancellationTokenSource();  
    btnRun.Enabled = false;  
    try  
    {  
        Task<Bitmap> imageDownload = GetBitmapAsync(txtUrl.Text);   
        await UntilCompletionOrCancellation(imageDownload, m_cts.Token);  
        if (imageDownload.IsCompleted)  
        {  
            Bitmap image = await imageDownload;  
            panel.AddImage(image);  
        }  
        else imageDownload.ContinueWith(t => Log(t));  
    }  
    finally { btnRun.Enabled = true; }  
}  
  
private static async Task UntilCompletionOrCancellation(  
    Task asyncOp, CancellationToken ct)  
{  
    var tcs = new TaskCompletionSource<bool>();  
    using(ct.Register(() => tcs.TrySetResult(true)))  
        await Task.WhenAny(asyncOp, tcs.Task);  
    return asyncOp;  
}  
```  
  
 一旦决定退出，此实现将重新启用用户界面，但不会取消基础异步操作。  另一种选择是决定退出时，取消挂起的操作，但在操作实际完成之前不重新建立用户界面，可能会由于取消请求而提前结束：  
  
```csharp  
private CancellationTokenSource m_cts;  
  
public async void btnRun_Click(object sender, EventArgs e)  
{  
    m_cts = new CancellationTokenSource();  
  
    btnRun.Enabled = false;  
    try  
    {  
        Task<Bitmap> imageDownload = GetBitmapAsync(txtUrl.Text, m_cts.Token);   
        await UntilCompletionOrCancellation(imageDownload, m_cts.Token);  
        Bitmap image = await imageDownload;  
        panel.AddImage(image);  
    }  
    catch(OperationCanceledException) {}  
    finally { btnRun.Enabled = true; }  
}  
```  
  
 早期释放的另一个示例涉及使用<xref:System.Threading.Tasks.Task.WhenAny%2A>方法结合<xref:System.Threading.Tasks.Task.Delay%2A>方法，如在下一节中讨论。  
  
### <a name="taskdelay"></a>Task.Delay  
 你可以使用<xref:System.Threading.Tasks.Task.Delay%2A?displayProperty=nameWithType>方法引入暂停到异步方法的执行。  这对于许多功能都非常有用，包括构建轮询循环和延迟预定时间段的用户输入处理。  <xref:System.Threading.Tasks.Task.Delay%2A?displayProperty=nameWithType>方法也会很有用结合<xref:System.Threading.Tasks.Task.WhenAny%2A?displayProperty=nameWithType>的实现上的超时等待。  
  
 如果某任务属于较大型异步操作（如 ASP.NET Web 服务）中的一部分，由于花费时间过长而不能完成，则整体操作可能会受到影响（尤其是此任务一直不能完成的情况下）。  因此，等待异步操作时可以超时非常重要。  同步<xref:System.Threading.Tasks.Task.Wait%2A?displayProperty=nameWithType>， <xref:System.Threading.Tasks.Task.WaitAll%2A?displayProperty=nameWithType>，和<xref:System.Threading.Tasks.Task.WaitAny%2A?displayProperty=nameWithType>方法接受超时值，但相应<xref:System.Threading.Tasks.TaskFactory.ContinueWhenAll%2A?displayProperty=nameWithType> / <xref:System.Threading.Tasks.Task.WhenAny%2A?displayProperty=nameWithType>和前面所述<xref:System.Threading.Tasks.Task.WhenAll%2A?displayProperty=nameWithType> / <xref:System.Threading.Tasks.Task.WhenAny%2A?displayProperty=nameWithType>方法不这样做。  相反，你可以使用<xref:System.Threading.Tasks.Task.Delay%2A?displayProperty=nameWithType>和<xref:System.Threading.Tasks.Task.WhenAny%2A?displayProperty=nameWithType>结合使用来实现超时。  
  
 例如，在 UI 应用程序中，假设你想要下载图像，并在图像下载期间禁用该 UI。 但是，如果下载时间过长，你希望重新启用 UI 并放弃下载：  
  
```csharp  
public async void btnDownload_Click(object sender, EventArgs e)  
{  
    btnDownload.Enabled = false;  
    try  
    {  
        Task<Bitmap> download = GetBitmapAsync(url);  
        if (download == await Task.WhenAny(download, Task.Delay(3000)))  
        {  
            Bitmap bmp = await download;  
            pictureBox.Image = bmp;  
            status.Text = "Downloaded";  
        }  
        else  
        {  
            pictureBox.Image = null;  
            status.Text = "Timed out";  
            var ignored = download.ContinueWith(  
                t => Trace("Task finally completed"));  
        }  
    }  
    finally { btnDownload.Enabled = true; }  
}  
```  
  
 这同样适用于多个下载，因为<xref:System.Threading.Tasks.Task.WhenAll%2A>返回的任务：  
  
```csharp  
public async void btnDownload_Click(object sender, RoutedEventArgs e)  
{  
    btnDownload.Enabled = false;  
    try  
    {  
        Task<Bitmap[]> downloads =   
            Task.WhenAll(from url in urls select GetBitmapAsync(url));  
        if (downloads == await Task.WhenAny(downloads, Task.Delay(3000)))  
        {  
            foreach(var bmp in downloads) panel.AddImage(bmp);  
            status.Text = "Downloaded";  
        }  
        else  
        {  
            status.Text = "Timed out";  
            downloads.ContinueWith(t => Log(t));  
        }  
    }  
    finally { btnDownload.Enabled = true; }  
}  
```  
  
## <a name="building-task-based-combinators"></a>构建基于任务的连结符  
 因为任务可以完全代表异步操作、提供同步和异步功能来加入操作、检索其结果等，所以可以构建组成任务的连结符的库以构建更大的模式。  如前一部分所述，.NET Framework 包括一些内置连结符，但是，你也可以构建自己的连结符。 以下各节提供了一些潜在的连结符方法和类型的示例。  
  
### <a name="retryonfault"></a>RetryOnFault  
 在许多情况下，如果上次尝试失败，你可能想要重试操作。  对于同步代码，你可能会构建一个帮助器方法来实现此目的，如下例中的 `RetryOnFault`：  
  
```csharp  
public static T RetryOnFault<T>(  
    Func<T> function, int maxTries)  
{  
    for(int i=0; i<maxTries; i++)  
    {  
        try { return function(); }  
        catch { if (i == maxTries-1) throw; }  
    }  
    return default(T);  
}  
```  
  
 你可以为异步操作（使用 TAP 实现，因此返回任务）构建几乎相同的帮助器方法：  
  
```csharp  
public static async Task<T> RetryOnFault<T>(  
    Func<Task<T>> function, int maxTries)  
{  
    for(int i=0; i<maxTries; i++)  
    {  
        try { return await function().ConfigureAwait(false); }  
        catch { if (i == maxTries-1) throw; }  
    }  
    return default(T);  
}  
```  
  
 然后，可以使用此连结符将重试编码到应用程序的逻辑中，例如：  
  
```csharp  
// Download the URL, trying up to three times in case of failure  
string pageContents = await RetryOnFault(  
    () => DownloadStringAsync(url), 3);  
```  
  
 可以进一步扩展 `RetryOnFault` 函数。 例如，该函数可以接受另一个 `Func<Task>`（在重试间隔期间调用以确定何时重试该操作）：  
  
```csharp  
public static async Task<T> RetryOnFault<T>(  
    Func<Task<T>> function, int maxTries, Func<Task> retryWhen)  
{  
    for(int i=0; i<maxTries; i++)  
    {  
        try { return await function().ConfigureAwait(false); }  
        catch { if (i == maxTries-1) throw; }  
        await retryWhen().ConfigureAwait(false);  
    }  
    return default(T);  
}  
```  
  
 重试该操作前，可以使用以下函数等待片刻：  
  
```csharp  
// Download the URL, trying up to three times in case of failure,  
// and delaying for a second between retries  
string pageContents = await RetryOnFault(  
    () => DownloadStringAsync(url), 3, () => Task.Delay(1000));  
```  
  
### <a name="needonlyone"></a>NeedOnlyOne  
 有时，你可以利用冗余改进操作延迟和提高成功的可能性。  假设有多个 Web 服务提供股票报价，但在一天中的不同时间，每个服务可能提供不同级别的质量和响应时间。  为了应对这些波动，你可能会向所有 Web 服务发出请求，并且只要从其中一个获得响应，立刻取消剩余的请求。  你可以通过 helper 函数更轻松地实现此启动多个操作的通用模式：等待任何操作，然后取消其余部分。 以下示例中的 `NeedOnlyOne` 函数阐释了这种方案：  
  
```csharp  
public static async Task<T> NeedOnlyOne(  
    params Func<CancellationToken,Task<T>> [] functions)  
{  
    var cts = new CancellationTokenSource();  
    var tasks = (from function in functions  
                 select function(cts.Token)).ToArray();  
    var completed = await Task.WhenAny(tasks).ConfigureAwait(false);  
    cts.Cancel();  
    foreach(var task in tasks)   
    {  
        var ignored = task.ContinueWith(  
            t => Log(t), TaskContinuationOptions.OnlyOnFaulted);  
    }  
    return completed;  
}  
```  
  
 然后，你可以使用此函数，如下所示：  
  
```csharp  
double currentPrice = await NeedOnlyOne(  
    ct => GetCurrentPriceFromServer1Async("msft", ct),  
    ct => GetCurrentPriceFromServer2Async("msft", ct),  
    ct => GetCurrentPriceFromServer3Async("msft", ct));  
```  
  
### <a name="interleaved-operations"></a>交错操作  
 潜在的性能问题与使用<xref:System.Threading.Tasks.Task.WhenAny%2A>方法，以支持交错方案时你正在使用的任务非常大的集。  对每个调用<xref:System.Threading.Tasks.Task.WhenAny%2A>导致要注册与每个任务的延续任务。 对于 N 个任务，这将导致在交错操作操作期间创建 O(N2) 次延续。  如果处理大型任务集，则可以使用连结符（以下示例中的 `Interleaved`）来解决性能问题：  
  
```csharp  
static IEnumerable<Task<T>> Interleaved<T>(IEnumerable<Task<T>> tasks)  
{  
    var inputTasks = tasks.ToList();  
    var sources = (from _ in Enumerable.Range(0, inputTasks.Count)   
                   select new TaskCompletionSource<T>()).ToList();  
    int nextTaskIndex = -1;  
    foreach (var inputTask in inputTasks)  
    {  
        inputTask.ContinueWith(completed =>  
        {  
            var source = sources[Interlocked.Increment(ref nextTaskIndex)];  
            if (completed.IsFaulted)   
                source.TrySetException(completed.Exception.InnerExceptions);  
            else if (completed.IsCanceled)   
                source.TrySetCanceled();  
            else   
                source.TrySetResult(completed.Result);  
        }, CancellationToken.None,   
           TaskContinuationOptions.ExecuteSynchronously,   
           TaskScheduler.Default);  
    }  
    return from source in sources   
           select source.Task;  
}  
```  
  
 然后，可以在任务完成时，使用连结符来处理任务的结果，例如：  
  
```csharp  
IEnumerable<Task<int>> tasks = ...;  
foreach(var task in Interleaved(tasks))  
{  
    int result = await task;  
    …  
}  
```  
  
### <a name="whenallorfirstexception"></a>WhenAllOrFirstException  
 在特定的分散/集中情况下，你可能想要等待集中的所有任务，除非某个任务发生错误。在这种情况下，你希望在异常发生时停止等待。  你可以通过使用连结符方法（如 `WhenAllOrFirstException`）实现该目的，如下所示：  
  
```csharp  
public static Task<T[]> WhenAllOrFirstException<T>(IEnumerable<Task<T>> tasks)  
{  
    var inputs = tasks.ToList();  
    var ce = new CountdownEvent(inputs.Count);  
    var tcs = new TaskCompletionSource<T[]>();  
  
    Action<Task> onCompleted = (Task completed) =>  
    {  
        if (completed.IsFaulted)   
            tcs.TrySetException(completed.Exception.InnerExceptions);  
        if (ce.Signal() && !tcs.Task.IsCompleted)  
            tcs.TrySetResult(inputs.Select(t => t.Result).ToArray());  
    };  
  
    foreach (var t in inputs) t.ContinueWith(onCompleted);  
    return tcs.Task;  
}  
```  
  
## <a name="building-task-based-data-structures"></a>构建基于任务的数据结构  
 生成基于任务的自定义组合器的功能，除了一种数据结构具有<xref:System.Threading.Tasks.Task>和<xref:System.Threading.Tasks.Task%601>表示异步操作的结果，并需要同步，以使用其加入便于非常强大键入用于生成要在异步方案中使用的自定义数据结构。  
  
### <a name="asynccache"></a>AsyncCache  
 其中一个任务的重要方面是，它可能被分发到多个使用者，全部用户可能会等待，通过该对话框，注册延续获取其结果或异常 (的情况下<xref:System.Threading.Tasks.Task%601>)，依次类推。  这使得<xref:System.Threading.Tasks.Task>和<xref:System.Threading.Tasks.Task%601>完全适合异步的缓存基础结构中使用。  下面是一个较小的一个示例，但功能强大的异步缓存生成的顶部<xref:System.Threading.Tasks.Task%601>:  
  
```csharp  
public class AsyncCache<TKey, TValue>  
{  
    private readonly Func<TKey, Task<TValue>> _valueFactory;  
    private readonly ConcurrentDictionary<TKey, Lazy<Task<TValue>>> _map;  
  
    public AsyncCache(Func<TKey, Task<TValue>> valueFactory)  
    {  
        if (valueFactory == null) throw new ArgumentNullException("loader");  
        _valueFactory = valueFactory;  
        _map = new ConcurrentDictionary<TKey, Lazy<Task<TValue>>>();  
    }  
  
    public Task<TValue> this[TKey key]  
    {  
        get  
        {  
            if (key == null) throw new ArgumentNullException("key");  
            return _map.GetOrAdd(key, toAdd =>   
                new Lazy<Task<TValue>>(() => _valueFactory(toAdd))).Value;  
        }  
    }  
}  
```  
  
 [AsyncCache\<TKey，>](http://go.microsoft.com/fwlink/p/?LinkId=251941)类作为委托给其构造函数采用的函数接受`TKey`并返回<xref:System.Threading.Tasks.Task%601>。  以前从缓存访问的所有值都存储在内部字典中，`AsyncCache` 可以确保每个密钥仅生成一个任务，即便同时访问缓存也是如此。  
  
 例如，你可以生成下载网页的缓存：  
  
```csharp  
private AsyncCache<string,string> m_webPages =   
    new AsyncCache<string,string>(DownloadStringAsync);  
```  
  
 然后可以在任何需要网页内容的时候，以异步方式使用此缓存。 `AsyncCache` 类可确保下载尽可能少的页面，并缓存结果。  
  
```csharp  
private async void btnDownload_Click(object sender, RoutedEventArgs e)   
{  
    btnDownload.IsEnabled = false;  
    try  
    {  
        txtContents.Text = await m_webPages["http://www.microsoft.com"];  
    }  
    finally { btnDownload.IsEnabled = true; }  
}  
```  
  
### <a name="asyncproducerconsumercollection"></a>AsyncProducerConsumerCollection  
 你还可以使用任务来构建协调异步活动的数据结构。  请考虑经典的并行设计模式之一：制造者/使用者。  在此模式下，制造者生成数据，使用者使用数据，制造者和使用者可能会并行运行。 例如，使用者处理之前由制造者生成的第 1 项，而制造者现在正在制造第 2 项。  对于制造者/使用者模式，总是需要某种数据结构来存储制造者创建的工作，以便使用者可以收到新数据的通知并及时发现新数据。  
  
 以下是基于任务构建的简单数据结构，可以将异步方法用作制造者和使用者：  
  
```csharp  
public class AsyncProducerConsumerCollection<T>  
{  
    private readonly Queue<T> m_collection = new Queue<T>();  
    private readonly Queue<TaskCompletionSource<T>> m_waiting =   
        new Queue<TaskCompletionSource<T>>();  
  
    public void Add(T item)  
    {  
        TaskCompletionSource<T> tcs = null;  
        lock (m_collection)  
        {  
            if (m_waiting.Count > 0) tcs = m_waiting.Dequeue();  
            else m_collection.Enqueue(item);  
        }  
        if (tcs != null) tcs.TrySetResult(item);  
    }  
  
    public Task<T> Take()  
    {  
        lock (m_collection)  
        {  
            if (m_collection.Count > 0)   
            {  
                return Task.FromResult(m_collection.Dequeue());   
            }  
            else   
            {  
                var tcs = new TaskCompletionSource<T>();  
                m_waiting.Enqueue(tcs);  
                return tcs.Task;  
            }  
        }  
    }  
}  
```  
  
 通过该数据结构，可以编写如下所示的代码：  
  
```csharp  
private static AsyncProducerConsumerCollection<int> m_data = …;  
…  
private static async Task ConsumerAsync()  
{  
    while(true)  
    {  
        int nextItem = await m_data.Take();  
        ProcessNextItem(nextItem);  
    }  
}  
…  
private static void Produce(int data)  
{  
    m_data.Add(data);  
}  
```  
  
 <xref:System.Threading.Tasks.Dataflow>命名空间包括<xref:System.Threading.Tasks.Dataflow.BufferBlock%601>类型，你可以使用类似的方式，但无需生成自定义集合类型：  
  
```csharp  
private static BufferBlock<int> m_data = …;  
…  
private static async Task ConsumerAsync()  
{  
    while(true)  
    {  
        int nextItem = await m_data.ReceiveAsync();  
        ProcessNextItem(nextItem);  
    }  
}  
…  
private static void Produce(int data)  
{  
    m_data.Post(data);  
}  
```  
  
> [!NOTE]
>  <xref:System.Threading.Tasks.Dataflow>命名空间可用于[!INCLUDE[net_v45](../../../includes/net-v45-md.md)]通过**NuGet**。 若要安装包含的程序集<xref:System.Threading.Tasks.Dataflow>命名空间中，打开你的项目中[!INCLUDE[vs_dev11_long](../../../includes/vs-dev11-long-md.md)]，选择**管理 NuGet 包**从项目菜单中，然后联机搜索 Microsoft.Tpl.Dataflow 包。  
  
## <a name="see-also"></a>另请参阅  
 [基于任务的异步模式 (TAP)](../../../docs/standard/asynchronous-programming-patterns/task-based-asynchronous-pattern-tap.md)  
 [实现基于任务的异步模式](../../../docs/standard/asynchronous-programming-patterns/implementing-the-task-based-asynchronous-pattern.md)  
 [与其他异步模式和类型互操作](../../../docs/standard/asynchronous-programming-patterns/interop-with-other-asynchronous-patterns-and-types.md)
