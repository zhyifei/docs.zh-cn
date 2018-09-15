---
title: NoPersistScope 活动
ms.date: 03/30/2017
ms.assetid: 9a0baeb7-a05c-4fac-b905-252758cb71bb
ms.openlocfilehash: 6543756594b6734aec39bf22c5ab6215605341b1
ms.sourcegitcommit: 6eac9a01ff5d70c6d18460324c016a3612c5e268
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/15/2018
ms.locfileid: "45649544"
---
# <a name="nopersistscope-activity"></a><span data-ttu-id="d9743-102">NoPersistScope 活动</span><span class="sxs-lookup"><span data-stu-id="d9743-102">NoPersistScope Activity</span></span>
<span data-ttu-id="d9743-103">此示例演示如何操作工作流中的不可序列化且可释放的状态。</span><span class="sxs-lookup"><span data-stu-id="d9743-103">This sample shows how to manipulate a non-serializable and disposable state within a workflow.</span></span> <span data-ttu-id="d9743-104">工作流不会尝试保留不可序列化的状态是很重要的，在工作流中使用过可释放的对象之后清除它们也是很重要的。</span><span class="sxs-lookup"><span data-stu-id="d9743-104">It is important that workflows do not attempt to persist non-serializable state and it is also important for disposable objects to be cleaned up after they are used in workflow.</span></span>  
  
## <a name="demonstrates"></a><span data-ttu-id="d9743-105">演示</span><span class="sxs-lookup"><span data-stu-id="d9743-105">Demonstrates</span></span>  
 <span data-ttu-id="d9743-106">`NoPersistScope` 自定义活动和设计器。</span><span class="sxs-lookup"><span data-stu-id="d9743-106">`NoPersistScope` custom activity and designer.</span></span>  
  
## <a name="using-the-nopersistzone-activity"></a><span data-ttu-id="d9743-107">使用 NoPersistZone 活动</span><span class="sxs-lookup"><span data-stu-id="d9743-107">Using the NoPersistZone activity</span></span>  
 <span data-ttu-id="d9743-108">当示例工作流运行时，一个称为 `CreateTextWriter` 的自定义活动将创建一个 <xref:System.IO.TextWriter> 类型的对象，并将它保存到工作流变量中。</span><span class="sxs-lookup"><span data-stu-id="d9743-108">When the sample workflow runs, a custom activity called `CreateTextWriter` creates an object of type <xref:System.IO.TextWriter> and saves it into a workflow variable.</span></span> <span data-ttu-id="d9743-109"><xref:System.IO.TextWriter> 是一个 <xref:System.IDisposable> 对象。</span><span class="sxs-lookup"><span data-stu-id="d9743-109"><xref:System.IO.TextWriter> is an <xref:System.IDisposable> object.</span></span> <span data-ttu-id="d9743-110">此 <xref:System.IO.TextWriter> 被配置为写入到运行示例的目录中的一个名为“out.txt”的文件，<xref:System.Activities.Statements.WriteLine> 活动将会使用它，因为它可以在控制台中回显您键入的任何文本。</span><span class="sxs-lookup"><span data-stu-id="d9743-110">This <xref:System.IO.TextWriter>, which is configured to write to a file named ‘out.txt’ in the directory in which the sample runs, is used by a <xref:System.Activities.Statements.WriteLine> activity as it echoes any text you type in at the console.</span></span>  
  
 <span data-ttu-id="d9743-111">回显逻辑在 `NoPersistScope` 活动（此活动的代码也是此示例的一部分）中运行，用于防止工作流持久化。</span><span class="sxs-lookup"><span data-stu-id="d9743-111">The echo logic runs within a `NoPersistScope` activity (the code for which is also part of this sample), which prevents the workflow from being persisted.</span></span> <span data-ttu-id="d9743-112">如果您在键入`unload`在控制台中，主机将尝试保留工作流实例，但此操作超时，因为工作流保留在`NoPersistScope`。</span><span class="sxs-lookup"><span data-stu-id="d9743-112">If you type in `unload` at the console, the host attempts to persist the workflow instance but this operation times out because the workflow remains within a `NoPersistScope`.</span></span> <span data-ttu-id="d9743-113">工作流在使用完 `Dispose` 对象之后，还会利用一个名为 <xref:System.IO.TextWriter> 的自定义活动来释放该对象。</span><span class="sxs-lookup"><span data-stu-id="d9743-113">The workflow also utilizes a custom activity called `Dispose` to dispose the <xref:System.IO.TextWriter> object when the workflow is finished using it.</span></span> <span data-ttu-id="d9743-114">将 `Dispose` 活动放在声明 <xref:System.Activities.Statements.TryCatch.Finally%2A> 变量的 <xref:System.Activities.Statements.TryCatch> 活动的 <xref:System.IO.TextWriter> 块中，以确保：即使在执行 Try 块期间应发生异常，也会运行它。</span><span class="sxs-lookup"><span data-stu-id="d9743-114">The `Dispose` activity is placed within the <xref:System.Activities.Statements.TryCatch.Finally%2A> block of the <xref:System.Activities.Statements.TryCatch> activity in which the <xref:System.IO.TextWriter> variable is declared, to ensure that it runs even if an exception should occur during execution of the Try block.</span></span>  
  
 <span data-ttu-id="d9743-115">您可以键入`exit`以完成工作流实例并退出程序。</span><span class="sxs-lookup"><span data-stu-id="d9743-115">You can type in `exit` to complete the workflow instance and exit the program.</span></span>  
  
#### <a name="to-run-the-sample"></a><span data-ttu-id="d9743-116">运行示例</span><span class="sxs-lookup"><span data-stu-id="d9743-116">To run the sample</span></span>  
  
1.  <span data-ttu-id="d9743-117">在 [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] 中打开 NoPersistZone.sln 解决方案。</span><span class="sxs-lookup"><span data-stu-id="d9743-117">Open the NoPersistZone.sln solution in [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)].</span></span>  
  
2.  <span data-ttu-id="d9743-118">若要生成解决方案，请按 CTRL + SHIFT + B 或选择**生成解决方案**从**生成**菜单。</span><span class="sxs-lookup"><span data-stu-id="d9743-118">To build the solution, press CTRL+SHIFT+B or select **Build Solution** from the **Build** menu.</span></span>  
  
3.  <span data-ttu-id="d9743-119">成功生成之后，按 F5 或选择**开始调试**从**调试**菜单或者，可以按 CTRL + F5 或选择**启动但不调试**从**调试**菜单运行而不进行调试。</span><span class="sxs-lookup"><span data-stu-id="d9743-119">Once the build has succeeded, press F5 or select **Start Debugging** from the **Debug** menu alternatively, you can press CTRL+F5 or select **Start Without Debugging** from the **Debug** menu to run without debugging.</span></span>  
  
#### <a name="to-cleanup-optional"></a><span data-ttu-id="d9743-120">清理（可选）</span><span class="sxs-lookup"><span data-stu-id="d9743-120">To cleanup (optional)</span></span>  
  
1.  <span data-ttu-id="d9743-121">若要移除 SQL 实例存储，请运行 Cleanup.cmd。</span><span class="sxs-lookup"><span data-stu-id="d9743-121">To remove the SQL Instance Store, run Cleanup.cmd.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="d9743-122">您的计算机上可能已安装这些示例。</span><span class="sxs-lookup"><span data-stu-id="d9743-122">The samples may already be installed on your machine.</span></span> <span data-ttu-id="d9743-123">在继续操作之前，请先检查以下（默认）目录：</span><span class="sxs-lookup"><span data-stu-id="d9743-123">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="d9743-124">如果此目录不存在，请转到[Windows Communication Foundation (WCF) 和.NET Framework 4 的 Windows Workflow Foundation (WF) 示例](https://go.microsoft.com/fwlink/?LinkId=150780)若要下载所有 Windows Communication Foundation (WCF) 和[!INCLUDE[wf1](../../../../includes/wf1-md.md)]示例。</span><span class="sxs-lookup"><span data-stu-id="d9743-124">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="d9743-125">此示例位于以下目录：</span><span class="sxs-lookup"><span data-stu-id="d9743-125">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Scenario\ActivityLibrary\NoPersistScope`