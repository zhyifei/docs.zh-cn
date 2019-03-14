---
title: 微调异步应用程序 (C#)
ms.date: 07/20/2015
ms.assetid: 97696eb9-81fc-4940-9655-84daa8eb4d5c
ms.openlocfilehash: 31d9fcf04780d421faa609e06e18e66e0e8b9ce7
ms.sourcegitcommit: 58fc0e6564a37fa1b9b1b140a637e864c4cf696e
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/08/2019
ms.locfileid: "57679160"
---
# <a name="fine-tuning-your-async-application-c"></a><span data-ttu-id="2254a-102">微调异步应用程序 (C#)</span><span class="sxs-lookup"><span data-stu-id="2254a-102">Fine-Tuning Your Async Application (C#)</span></span>
<span data-ttu-id="2254a-103">可以使用由 <xref:System.Threading.Tasks.Task> 类型提供的方法和属性将精度和灵活性添加到异步应用程序。</span><span class="sxs-lookup"><span data-stu-id="2254a-103">You can add precision and flexibility to your async applications by using the methods and properties that the <xref:System.Threading.Tasks.Task> type makes available.</span></span> <span data-ttu-id="2254a-104">本部分中的主题介绍使用 <xref:System.Threading.CancellationToken> 的示例和一些重要的 `Task` 方法，例如 <xref:System.Threading.Tasks.Task.WhenAll%2A?displayProperty=nameWithType> 和 <xref:System.Threading.Tasks.Task.WhenAny%2A?displayProperty=nameWithType>。</span><span class="sxs-lookup"><span data-stu-id="2254a-104">The topics in this section show examples that use <xref:System.Threading.CancellationToken> and important `Task` methods such as <xref:System.Threading.Tasks.Task.WhenAll%2A?displayProperty=nameWithType> and <xref:System.Threading.Tasks.Task.WhenAny%2A?displayProperty=nameWithType>.</span></span>  
  
 <span data-ttu-id="2254a-105">使用 `WhenAny` 和 `WhenAll` 可以更轻松地启动多个任务并通过监视单个任务待其完成。</span><span class="sxs-lookup"><span data-stu-id="2254a-105">By using `WhenAny` and `WhenAll`, you can more easily start multiple tasks and await their completion by monitoring a single task.</span></span>  
  
-   <span data-ttu-id="2254a-106">集合中的任何任务完成时，`WhenAny` 将返回完成的任务。</span><span class="sxs-lookup"><span data-stu-id="2254a-106">`WhenAny` returns a task that completes when any task in a collection is complete.</span></span>  
  
     <span data-ttu-id="2254a-107">有关使用 `WhenAny` 的示例，请参阅[在完成一个异步任务后取消剩余任务 (C#)](../../../../csharp/programming-guide/concepts/async/cancel-remaining-async-tasks-after-one-is-complete.md) 和[启动多个异步任务并在其完成时进行处理 (C#)](../../../../csharp/programming-guide/concepts/async/start-multiple-async-tasks-and-process-them-as-they-complete.md)。</span><span class="sxs-lookup"><span data-stu-id="2254a-107">For examples that use `WhenAny`, see [Cancel Remaining Async Tasks after One Is Complete (C#)](../../../../csharp/programming-guide/concepts/async/cancel-remaining-async-tasks-after-one-is-complete.md) and [Start Multiple Async Tasks and Process Them As They Complete (C#)](../../../../csharp/programming-guide/concepts/async/start-multiple-async-tasks-and-process-them-as-they-complete.md).</span></span>  
  
-   <span data-ttu-id="2254a-108">集合中的所有任务完成时，`WhenAll` 将返回完成的任务。</span><span class="sxs-lookup"><span data-stu-id="2254a-108">`WhenAll` returns a task that completes when all tasks in a collection are complete.</span></span>  
  
     <span data-ttu-id="2254a-109">有关使用 `WhenAll` 的详细信息和示例，请参阅 [如何：使用 Task.WhenAll 扩展异步演练 (C#)](../../../../csharp/programming-guide/concepts/async/how-to-extend-the-async-walkthrough-by-using-task-whenall.md)。</span><span class="sxs-lookup"><span data-stu-id="2254a-109">For more information and an example that uses `WhenAll`, see [How to: Extend the async Walkthrough by Using Task.WhenAll (C#)](../../../../csharp/programming-guide/concepts/async/how-to-extend-the-async-walkthrough-by-using-task-whenall.md).</span></span>  
  
 <span data-ttu-id="2254a-110">本部分包括下列示例。</span><span class="sxs-lookup"><span data-stu-id="2254a-110">This section includes the following examples.</span></span>  
  
-   <span data-ttu-id="2254a-111">[取消一个异步任务或一组任务(C#)](../../../../csharp/programming-guide/concepts/async/cancel-an-async-task-or-a-list-of-tasks.md)。</span><span class="sxs-lookup"><span data-stu-id="2254a-111">[Cancel an Async Task or a List of Tasks (C#)](../../../../csharp/programming-guide/concepts/async/cancel-an-async-task-or-a-list-of-tasks.md).</span></span>  
  
-   [<span data-ttu-id="2254a-112">在一段时间后取消异步任务 (C#)</span><span class="sxs-lookup"><span data-stu-id="2254a-112">Cancel Async Tasks after a Period of Time (C#)</span></span>](../../../../csharp/programming-guide/concepts/async/cancel-async-tasks-after-a-period-of-time.md)  
  
-   [<span data-ttu-id="2254a-113">在完成一个异步任务后取消剩余任务 (C#)</span><span class="sxs-lookup"><span data-stu-id="2254a-113">Cancel Remaining Async Tasks after One Is Complete (C#)</span></span>](../../../../csharp/programming-guide/concepts/async/cancel-remaining-async-tasks-after-one-is-complete.md)  
  
-   [<span data-ttu-id="2254a-114">启动多个异步任务并在其完成时进行处理 (C#)</span><span class="sxs-lookup"><span data-stu-id="2254a-114">Start Multiple Async Tasks and Process Them As They Complete (C#)</span></span>](../../../../csharp/programming-guide/concepts/async/start-multiple-async-tasks-and-process-them-as-they-complete.md)  
  
> [!NOTE]
>  <span data-ttu-id="2254a-115">若要运行该示例，计算机上必须安装有 Visual Studio 2012 或更高版本和 .NET Framework 4.5 或更高版本。</span><span class="sxs-lookup"><span data-stu-id="2254a-115">To run the examples, you must have Visual Studio 2012 or newer and the .NET Framework 4.5 or newer installed on your computer.</span></span>  
  
 <span data-ttu-id="2254a-116">项目将创建一个 UI，其中包含用于启动进程和取消进程的按钮，如下图所示。</span><span class="sxs-lookup"><span data-stu-id="2254a-116">The projects create a UI that contains a button that starts the process and a button that cancels it, as the following image shows.</span></span> <span data-ttu-id="2254a-117">这些按钮名为 `startButton` 和 `cancelButton`。</span><span class="sxs-lookup"><span data-stu-id="2254a-117">The buttons are named `startButton` and `cancelButton`.</span></span>  
  
 <span data-ttu-id="2254a-118">![显示“取消”按钮的 WPF 窗口](./media/fine-tuning-your-async-application/cancellation-and-start-button.png "显示“启动”和“停止”按钮的对话框")</span><span class="sxs-lookup"><span data-stu-id="2254a-118">![WPF window with Cancel button](./media/fine-tuning-your-async-application/cancellation-and-start-button.png "Dialog box with a Start and Stop button")</span></span>  
  
 <span data-ttu-id="2254a-119">要下载完整的 Windows Presentation Foundation (WPF) 项目，请参阅 [Async Sample:Fine Tuning Your Application](https://code.msdn.microsoft.com/Async-Fine-Tuning-Your-a676abea)（异步示例：微调应用程序）。</span><span class="sxs-lookup"><span data-stu-id="2254a-119">You can download the complete Windows Presentation Foundation (WPF) projects from [Async Sample: Fine Tuning Your Application](https://code.msdn.microsoft.com/Async-Fine-Tuning-Your-a676abea).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2254a-120">请参阅</span><span class="sxs-lookup"><span data-stu-id="2254a-120">See also</span></span>

- [<span data-ttu-id="2254a-121">使用 Async 和 Await 的异步编程 (C#)</span><span class="sxs-lookup"><span data-stu-id="2254a-121">Asynchronous Programming with async and await (C#)</span></span>](../../../../csharp/programming-guide/concepts/async/index.md)
