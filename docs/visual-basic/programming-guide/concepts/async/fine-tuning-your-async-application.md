---
title: "微调异步应用程序 (Visual Basic 中) |Microsoft 文档"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
ms.assetid: 4c3e7997-a95f-4fbe-a6ac-60ba042d30b9
caps.latest.revision: 3
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: e031c2e23430a62629424ee57a140a7d8da41777
ms.contentlocale: zh-cn
ms.lasthandoff: 04/12/2017

---
# <a name="fine-tuning-your-async-application-visual-basic"></a><span data-ttu-id="a6d5f-102">微调异步应用程序 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="a6d5f-102">Fine-Tuning Your Async Application (Visual Basic)</span></span>
<span data-ttu-id="a6d5f-103">您可以添加精度和灵活性异步应用程序使用的方法和属性，<xref:System.Threading.Tasks.Task>类型提供。</xref:System.Threading.Tasks.Task></span><span class="sxs-lookup"><span data-stu-id="a6d5f-103">You can add precision and flexibility to your async applications by using the methods and properties that the <xref:System.Threading.Tasks.Task> type makes available.</span></span> <span data-ttu-id="a6d5f-104">本部分中的主题说明使用示例，<xref:System.Threading.CancellationToken>和重要`Task`方法如<xref:System.Threading.Tasks.Task.WhenAll%2A?displayProperty=fullName>和<xref:System.Threading.Tasks.Task.WhenAny%2A?displayProperty=fullName>。</xref:System.Threading.Tasks.Task.WhenAny%2A?displayProperty=fullName> </xref:System.Threading.Tasks.Task.WhenAll%2A?displayProperty=fullName> </xref:System.Threading.CancellationToken></span><span class="sxs-lookup"><span data-stu-id="a6d5f-104">The topics in this section show examples that use <xref:System.Threading.CancellationToken> and important `Task` methods such as <xref:System.Threading.Tasks.Task.WhenAll%2A?displayProperty=fullName> and <xref:System.Threading.Tasks.Task.WhenAny%2A?displayProperty=fullName>.</span></span>  
  
 <span data-ttu-id="a6d5f-105">通过使用`WhenAny`和`WhenAll`，可以更轻松地启动多个任务并等待其完成通过监视单个任务。</span><span class="sxs-lookup"><span data-stu-id="a6d5f-105">By using `WhenAny` and `WhenAll`, you can more easily start multiple tasks and await their completion by monitoring a single task.</span></span>  
  
-   <span data-ttu-id="a6d5f-106">`WhenAny`返回集合中的任何任务完成后完成的任务。</span><span class="sxs-lookup"><span data-stu-id="a6d5f-106">`WhenAny` returns a task that completes when any task in a collection is complete.</span></span>  
  
     <span data-ttu-id="a6d5f-107">有关示例，请使用`WhenAny`，请参阅[一个是否已完成 (Visual Basic 中) 后取消剩余异步任务](../../../../visual-basic/programming-guide/concepts/async/cancel-remaining-async-tasks-after-one-is-complete.md)和[启动多个异步任务和过程它们为它们全部 (Visual Basic 中)](../../../../visual-basic/programming-guide/concepts/async/start-multiple-async-tasks-and-process-them-as-they-complete.md)。</span><span class="sxs-lookup"><span data-stu-id="a6d5f-107">For examples that use `WhenAny`, see  [Cancel Remaining Async Tasks after One Is Complete (Visual Basic)](../../../../visual-basic/programming-guide/concepts/async/cancel-remaining-async-tasks-after-one-is-complete.md)and [Start Multiple Async Tasks and Process Them As They Complete (Visual Basic)](../../../../visual-basic/programming-guide/concepts/async/start-multiple-async-tasks-and-process-them-as-they-complete.md).</span></span>  
  
-   <span data-ttu-id="a6d5f-108">`WhenAll`返回在集合中的所有任务都都已完成时完成的任务。</span><span class="sxs-lookup"><span data-stu-id="a6d5f-108">`WhenAll` returns a task that completes when all tasks in a collection are complete.</span></span>  
  
     <span data-ttu-id="a6d5f-109">有关详细信息和使用的示例， `WhenAll`，请参阅[如何︰ 扩展异步演练使用 Task.WhenAll (Visual Basic 中) 通过](../../../../visual-basic/programming-guide/concepts/async/how-to-extend-the-async-walkthrough-by-using-task-whenall.md)。</span><span class="sxs-lookup"><span data-stu-id="a6d5f-109">For more information and an example that uses `WhenAll`, see [How to: Extend the Async Walkthrough by Using Task.WhenAll (Visual Basic)](../../../../visual-basic/programming-guide/concepts/async/how-to-extend-the-async-walkthrough-by-using-task-whenall.md).</span></span>  
  
 <span data-ttu-id="a6d5f-110">本部分包括下面的示例。</span><span class="sxs-lookup"><span data-stu-id="a6d5f-110">This section includes the following examples.</span></span>  
  
-   <span data-ttu-id="a6d5f-111">[取消一个异步任务或一组任务 (Visual Basic 中)](../../../../visual-basic/programming-guide/concepts/async/cancel-an-async-task-or-a-list-of-tasks.md)。</span><span class="sxs-lookup"><span data-stu-id="a6d5f-111">[Cancel an Async Task or a List of Tasks (Visual Basic)](../../../../visual-basic/programming-guide/concepts/async/cancel-an-async-task-or-a-list-of-tasks.md).</span></span>  
  
-   [<span data-ttu-id="a6d5f-112">在一段时间 (Visual Basic 中) 后取消异步任务</span><span class="sxs-lookup"><span data-stu-id="a6d5f-112">Cancel Async Tasks after a Period of Time (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/async/cancel-async-tasks-after-a-period-of-time.md)  
  
-   [<span data-ttu-id="a6d5f-113">异步任务取消剩余一个后完成 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="a6d5f-113">Cancel Remaining Async Tasks after One Is Complete (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/async/cancel-remaining-async-tasks-after-one-is-complete.md)  
  
-   [<span data-ttu-id="a6d5f-114">启动多个异步任务并在其完成 (Visual Basic 中) 时处理</span><span class="sxs-lookup"><span data-stu-id="a6d5f-114">Start Multiple Async Tasks and Process Them As They Complete (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/async/start-multiple-async-tasks-and-process-them-as-they-complete.md)  
  
> [!NOTE]
>  <span data-ttu-id="a6d5f-115">若要运行的示例，必须具有 Visual Studio 2012 或更高版本和.NET Framework 4.5 或更高版本安装在您的计算机上。</span><span class="sxs-lookup"><span data-stu-id="a6d5f-115">To run the examples, you must have Visual Studio 2012 or newer and the .NET Framework 4.5 or newer installed on your computer.</span></span>  
  
 <span data-ttu-id="a6d5f-116">项目创建一个 UI，其中包含一个按钮用于启动进程和取消与下图显示的按钮。</span><span class="sxs-lookup"><span data-stu-id="a6d5f-116">The projects create a UI that contains a button that starts the process and a button that cancels it, as the following image shows.</span></span> <span data-ttu-id="a6d5f-117">这些按钮被命名为`startButton`和`cancelButton`。</span><span class="sxs-lookup"><span data-stu-id="a6d5f-117">The buttons are named `startButton` and `cancelButton`.</span></span>  
  
 <span data-ttu-id="a6d5f-118">![WPF 窗口与取消按钮](../../../../csharp/programming-guide/concepts/async/media/cancellation.png "取消")</span><span class="sxs-lookup"><span data-stu-id="a6d5f-118">![WPF window with Cancel button](../../../../csharp/programming-guide/concepts/async/media/cancellation.png "Cancellation")</span></span>  
  
 <span data-ttu-id="a6d5f-119">您可以下载完整的 Windows Presentation Foundation (WPF) 项目，从[异步示例︰ 精细优化您的应用程序](http://go.microsoft.com/fwlink/?LinkId=255046)。</span><span class="sxs-lookup"><span data-stu-id="a6d5f-119">You can download the complete Windows Presentation Foundation (WPF) projects from [Async Sample: Fine Tuning Your Application](http://go.microsoft.com/fwlink/?LinkId=255046).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a6d5f-120">另请参阅</span><span class="sxs-lookup"><span data-stu-id="a6d5f-120">See Also</span></span>  
 [<span data-ttu-id="a6d5f-121">异步编程使用 Async 和 Await (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="a6d5f-121">Asynchronous Programming with Async and Await (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/async/index.md)
