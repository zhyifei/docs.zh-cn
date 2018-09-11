---
title: 使用 InvokePowerShell 活动
ms.date: 03/30/2017
ms.assetid: 956251a0-31ca-4183-bf76-d277c08585df
ms.openlocfilehash: fa42cddd930b755e9938a02a137ee77ee273fad0
ms.sourcegitcommit: 4b6490b2529707627ad77c3a43fbe64120397175
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/10/2018
ms.locfileid: "44269197"
---
# <a name="using-the-invokepowershell-activity"></a><span data-ttu-id="cd7aa-102">使用 InvokePowerShell 活动</span><span class="sxs-lookup"><span data-stu-id="cd7aa-102">Using the InvokePowerShell Activity</span></span>
<span data-ttu-id="cd7aa-103">InvokePowerShell 示例演示如何使用 `InvokePowerShell` 活动调用 Windows PowerShell 命令。</span><span class="sxs-lookup"><span data-stu-id="cd7aa-103">The InvokePowerShell sample demonstrates how to invoke Windows PowerShell commands using the `InvokePowerShell` activity.</span></span>  
  
## <a name="demonstrates"></a><span data-ttu-id="cd7aa-104">演示</span><span class="sxs-lookup"><span data-stu-id="cd7aa-104">Demonstrates</span></span>  
  
-   <span data-ttu-id="cd7aa-105">Windows PowerShell 命令的简单创新。</span><span class="sxs-lookup"><span data-stu-id="cd7aa-105">Simple innovation of Windows PowerShell commands.</span></span>  
  
-   <span data-ttu-id="cd7aa-106">从 Windows PowerShell 输出管道检索值，并将这些值存储在工作流变量中。</span><span class="sxs-lookup"><span data-stu-id="cd7aa-106">Retrieve values from the Windows PowerShell output pipeline and store them in workflow variables.</span></span>  
  
-   <span data-ttu-id="cd7aa-107">将数据作为执行命令的输入管道传入 Windows PowerShell 中。</span><span class="sxs-lookup"><span data-stu-id="cd7aa-107">Pass data into windows PowerShell as input pipeline for an executing command.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="cd7aa-108">您的计算机上可能已安装这些示例。</span><span class="sxs-lookup"><span data-stu-id="cd7aa-108">The samples may already be installed on your machine.</span></span> <span data-ttu-id="cd7aa-109">在继续操作之前，请先检查以下（默认）目录：</span><span class="sxs-lookup"><span data-stu-id="cd7aa-109">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="cd7aa-110">如果此目录不存在，请转到[Windows Communication Foundation (WCF) 和.NET Framework 4 的 Windows Workflow Foundation (WF) 示例](https://go.microsoft.com/fwlink/?LinkId=150780)若要下载所有 Windows Communication Foundation (WCF) 和[!INCLUDE[wf1](../../../../includes/wf1-md.md)]示例。</span><span class="sxs-lookup"><span data-stu-id="cd7aa-110">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="cd7aa-111">此示例位于以下目录：</span><span class="sxs-lookup"><span data-stu-id="cd7aa-111">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Scenario\ActivityLibrary\PowerShell`  
  
## <a name="discussion"></a><span data-ttu-id="cd7aa-112">讨论</span><span class="sxs-lookup"><span data-stu-id="cd7aa-112">Discussion</span></span>  
 <span data-ttu-id="cd7aa-113">此示例包含以下三个项目。</span><span class="sxs-lookup"><span data-stu-id="cd7aa-113">This sample contains the following three projects.</span></span>  
  
|<span data-ttu-id="cd7aa-114">项目名称</span><span class="sxs-lookup"><span data-stu-id="cd7aa-114">Project Name</span></span>|<span data-ttu-id="cd7aa-115">描述</span><span class="sxs-lookup"><span data-stu-id="cd7aa-115">Description</span></span>|<span data-ttu-id="cd7aa-116">主要文件</span><span class="sxs-lookup"><span data-stu-id="cd7aa-116">Main Files</span></span>|  
|------------------|-----------------|----------------|  
|<span data-ttu-id="cd7aa-117">CodedClient</span><span class="sxs-lookup"><span data-stu-id="cd7aa-117">CodedClient</span></span>|<span data-ttu-id="cd7aa-118">使用 PowerShell 活动的示例客户端应用程序。</span><span class="sxs-lookup"><span data-stu-id="cd7aa-118">A sample client application that uses the PowerShell activity.</span></span>|<span data-ttu-id="cd7aa-119">-   **Program.cs**： 以编程方式创建调用 InvokePowerShell 活动的基于序列的工作流。</span><span class="sxs-lookup"><span data-stu-id="cd7aa-119">-   **Program.cs**: Programmatically creates a sequence-based workflow that calls the InvokePowerShell activity.</span></span>|  
|<span data-ttu-id="cd7aa-120">DesignerClient</span><span class="sxs-lookup"><span data-stu-id="cd7aa-120">DesignerClient</span></span>|<span data-ttu-id="cd7aa-121">一个自定义活动集，其中包含 `InvokePowerShell` 自定义活动、其他杂项自定义活动和一个使用这些活动的工作流。</span><span class="sxs-lookup"><span data-stu-id="cd7aa-121">A set of custom activities that contain the `InvokePowerShell` custom activity and other miscellaneous custom activities, and a workflow that uses them.</span></span>|<ul><li><span data-ttu-id="cd7aa-122">活动：</span><span class="sxs-lookup"><span data-stu-id="cd7aa-122">Activities:</span></span><br /><br /> <ul><li><span data-ttu-id="cd7aa-123">**PrintCollection.cs**： 打印到控制台集合中的所有项的帮助器活动。</span><span class="sxs-lookup"><span data-stu-id="cd7aa-123">**PrintCollection.cs**: A helper activity that prints all the items in a collection to the console.</span></span></li><li><span data-ttu-id="cd7aa-124">**ReadLine.cs**： 从控制台读取输入的帮助器活动。</span><span class="sxs-lookup"><span data-stu-id="cd7aa-124">**ReadLine.cs**: A helper activity for reading input from the console.</span></span></li></ul></li><li><span data-ttu-id="cd7aa-125">文件系统：</span><span class="sxs-lookup"><span data-stu-id="cd7aa-125">File System:</span></span><br /><br /> <ul><li><span data-ttu-id="cd7aa-126">**Copy.xaml**： 将文件复制的活动。</span><span class="sxs-lookup"><span data-stu-id="cd7aa-126">**Copy.xaml**: An activity that copies a file.</span></span></li><li><span data-ttu-id="cd7aa-127">**CreateFile.xaml**： 创建一个文件的活动。</span><span class="sxs-lookup"><span data-stu-id="cd7aa-127">**CreateFile.xaml**: An activity that creates a file.</span></span></li><li><span data-ttu-id="cd7aa-128">**DeleteFile.xaml**： 删除的文件的活动。</span><span class="sxs-lookup"><span data-stu-id="cd7aa-128">**DeleteFile.xaml**: An activity that deletes a file.</span></span></li><li><span data-ttu-id="cd7aa-129">**MakeDir.xaml**： 创建目录的活动。</span><span class="sxs-lookup"><span data-stu-id="cd7aa-129">**MakeDir.xaml**: An activity that creates a directory.</span></span></li><li><span data-ttu-id="cd7aa-130">**Move.xaml**： 将文件移动的活动。</span><span class="sxs-lookup"><span data-stu-id="cd7aa-130">**Move.xaml**: An activity that moves a file.</span></span></li><li><span data-ttu-id="cd7aa-131">**ReadFile.xaml**： 读取文件，并返回其内容的活动。</span><span class="sxs-lookup"><span data-stu-id="cd7aa-131">**ReadFile.xaml**: An activity that reads a file and returns its contents.</span></span></li><li><span data-ttu-id="cd7aa-132">**TestPath.xaml**： 一个测试路径是否存在的活动。</span><span class="sxs-lookup"><span data-stu-id="cd7aa-132">**TestPath.xaml**: An activity that tests for the existence of a path.</span></span></li></ul></li><li><span data-ttu-id="cd7aa-133">进程：</span><span class="sxs-lookup"><span data-stu-id="cd7aa-133">Process:</span></span><br /><br /> <ul><li><span data-ttu-id="cd7aa-134">**GetProcess.xaml**： 获取正在运行的进程列表的活动。</span><span class="sxs-lookup"><span data-stu-id="cd7aa-134">**GetProcess.xaml**: An activity that gets a list of running processes.</span></span></li><li><span data-ttu-id="cd7aa-135">**StopProcess.xaml**： 停止特定进程的活动。</span><span class="sxs-lookup"><span data-stu-id="cd7aa-135">**StopProcess.xaml**: An activity that stops a specific process.</span></span></li></ul></li><li><span data-ttu-id="cd7aa-136">**Program.cs**： 调用 Sequence1 工作流。</span><span class="sxs-lookup"><span data-stu-id="cd7aa-136">**Program.cs**: Calls the Sequence1 workflow.</span></span></li><li><span data-ttu-id="cd7aa-137">**Sequence1.xaml**： 基于序列的工作流。</span><span class="sxs-lookup"><span data-stu-id="cd7aa-137">**Sequence1.xaml**: A sequence-based workflow.</span></span></li></ul>|  
|<span data-ttu-id="cd7aa-138">PowerShell</span><span class="sxs-lookup"><span data-stu-id="cd7aa-138">PowerShell</span></span>|<span data-ttu-id="cd7aa-139">`InvokePowerShell` 活动及其关联的设计器。</span><span class="sxs-lookup"><span data-stu-id="cd7aa-139">The `InvokePowerShell` activity and its associated designers.</span></span>|<span data-ttu-id="cd7aa-140">活动文件</span><span class="sxs-lookup"><span data-stu-id="cd7aa-140">Activity Files</span></span><br /><br /> <span data-ttu-id="cd7aa-141">-   **ExecutePowerShell.cs**: 活动的主执行逻辑。</span><span class="sxs-lookup"><span data-stu-id="cd7aa-141">-   **ExecutePowerShell.cs**: The main execution logic of the activity.</span></span><br /><span data-ttu-id="cd7aa-142">-   **InvokePowerShell.cs**： 包含泛型 （返回值） 版本和非泛型 （非返回值） 版本的主执行逻辑周围的包装。</span><span class="sxs-lookup"><span data-stu-id="cd7aa-142">-   **InvokePowerShell.cs**: The wrapper around the main execution logic, which contains a generic (return value) version and a non-generic (non-return value) version.</span></span> <span data-ttu-id="cd7aa-143">这是活动的公共接口。</span><span class="sxs-lookup"><span data-stu-id="cd7aa-143">This is the public interface for the activity.</span></span><br /><span data-ttu-id="cd7aa-144">-   **NoPersistZone.cs**： 此活动可防止任何子活动持久化。</span><span class="sxs-lookup"><span data-stu-id="cd7aa-144">-   **NoPersistZone.cs**: This activity prevents any child activities from persisting.</span></span> <span data-ttu-id="cd7aa-145">在 `InvokePowerShell` 活动实现中使用该类以防止在执行期间将活动持久化。</span><span class="sxs-lookup"><span data-stu-id="cd7aa-145">This class is used within the `InvokePowerShell` activity implementation to prevent the activity from being persisted mid-execution.</span></span><br /><br /> <span data-ttu-id="cd7aa-146">设计器文件：</span><span class="sxs-lookup"><span data-stu-id="cd7aa-146">Designer files:</span></span><br /><br /> <span data-ttu-id="cd7aa-147">1.**ArgumentDictionaryEditor.cs**： 允许用户编辑的参数的 Windows 对话框`InvokePowerShell`活动。</span><span class="sxs-lookup"><span data-stu-id="cd7aa-147">1.  **ArgumentDictionaryEditor.cs**: A Windows dialog that allows the user to edit the arguments of the `InvokePowerShell` activity.</span></span><br /><span data-ttu-id="cd7aa-148">2.**GenericInvokePowerShellDesigner.xaml**并**GenericInvokePowerShellDesigner.xaml.cs**： 定义的泛型外观`InvokePowerShell`中的活动[!INCLUDE[wfd2](../../../../includes/wfd2-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="cd7aa-148">2.  **GenericInvokePowerShellDesigner.xaml** and **GenericInvokePowerShellDesigner.xaml.cs**: Defines the appearance of the generic `InvokePowerShell` activity in [!INCLUDE[wfd2](../../../../includes/wfd2-md.md)].</span></span><br /><span data-ttu-id="cd7aa-149">3.**InvokePowerShellDesigner.xaml**并**InvokePowerShellDesigner.cs**： 定义的非泛型外观`InvokePowerShell`中的活动[!INCLUDE[wfd2](../../../../includes/wfd2-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="cd7aa-149">3.  **InvokePowerShellDesigner.xaml** and **InvokePowerShellDesigner.cs**: Defines the appearance of the non-generic `InvokePowerShell` activity in [!INCLUDE[wfd2](../../../../includes/wfd2-md.md)].</span></span>|  
  
 <span data-ttu-id="cd7aa-150">首先讨论客户端项目，因为在了解 PowerShell 活动的用法之后再了解它的内部功能会更容易一些。</span><span class="sxs-lookup"><span data-stu-id="cd7aa-150">The client projects are discussed first, as it is easier to understand the internal functionality of the PowerShell activity once its use is understood.</span></span>  
  
## <a name="using-this-sample"></a><span data-ttu-id="cd7aa-151">使用此示例</span><span class="sxs-lookup"><span data-stu-id="cd7aa-151">Using This Sample</span></span>  
 <span data-ttu-id="cd7aa-152">以下各节说明如何使用此示例中的三个项目。</span><span class="sxs-lookup"><span data-stu-id="cd7aa-152">The following sections describe how to use the three projects in the sample.</span></span>  
  
### <a name="using-the-coded-client-project"></a><span data-ttu-id="cd7aa-153">使用 CodedClient 项目</span><span class="sxs-lookup"><span data-stu-id="cd7aa-153">Using the Coded Client Project</span></span>  
 <span data-ttu-id="cd7aa-154">示例客户端以编程方式创建一个顺序活动，其中包含几个使用 `InvokePowerShell` 活动的不同的方法的示例。</span><span class="sxs-lookup"><span data-stu-id="cd7aa-154">The sample client programmatically creates a sequence activity, which contains examples of several different methods of using the `InvokePowerShell` activity.</span></span> <span data-ttu-id="cd7aa-155">第一次调用将启动“记事本”。</span><span class="sxs-lookup"><span data-stu-id="cd7aa-155">The first invocation launches Notepad.</span></span>  
  
```  
new InvokePowerShell()  
{  
    CommandText = "notepad"  
},  
```  
  
 <span data-ttu-id="cd7aa-156">第二次调用将获取本地计算机上正在运行的进程的列表。</span><span class="sxs-lookup"><span data-stu-id="cd7aa-156">The second invocation gets a list of the processes running on the local machine.</span></span>  
  
```  
new InvokePowerShell<Process>()  
{  
    CommandText = "Get-Process",  
    Output = processes1,  
},  
```  
  
 <span data-ttu-id="cd7aa-157">`Output` 是用于存储命令输出的变量。</span><span class="sxs-lookup"><span data-stu-id="cd7aa-157">`Output` is the variable used to store the output of the command.</span></span>  
  
 <span data-ttu-id="cd7aa-158">下一次调用将演示如何对 PowerShell 调用的每个单独输出运行后续处理步骤。</span><span class="sxs-lookup"><span data-stu-id="cd7aa-158">The next call demonstrates how to run a post-processing step on each individual output of the PowerShell invocation.</span></span> <span data-ttu-id="cd7aa-159">`InitializationAction` 将设置为输出每个进程的字符串表示形式的函数。</span><span class="sxs-lookup"><span data-stu-id="cd7aa-159">`InitializationAction` is set to the function that outputs a string representation for each process.</span></span> <span data-ttu-id="cd7aa-160">`Output` 活动将在 `InvokePowerShell<string>` 变量中返回这些字符串的集合。</span><span class="sxs-lookup"><span data-stu-id="cd7aa-160">The collection of these strings is returned in the `Output` variable by the `InvokePowerShell<string>` activity.</span></span>  
  
 <span data-ttu-id="cd7aa-161">后续的 `InvokePowerShell` 调用演示如何将数据传入到活动中以及如何显示输出和错误。</span><span class="sxs-lookup"><span data-stu-id="cd7aa-161">The succeeding `InvokePowerShell` calls demonstrate passing data into the activity and getting outputs and errors out.</span></span>  
  
### <a name="using-the-designer-client-project"></a><span data-ttu-id="cd7aa-162">使用 DesignerClient 项目</span><span class="sxs-lookup"><span data-stu-id="cd7aa-162">Using the Designer Client Project</span></span>  
 <span data-ttu-id="cd7aa-163">DesignerClient 项目由一组自定义活动组成，生成的所有这些活动几乎都包含 `InvokePowerShell` 活动。</span><span class="sxs-lookup"><span data-stu-id="cd7aa-163">The DesignerClient project consists of a set of custom activities, almost all of which are built containing the `InvokePowerShell` activity.</span></span> <span data-ttu-id="cd7aa-164">大多数活动都调用非泛型版本的 `InvokePowerShell` 活动，并且不期待返回值。</span><span class="sxs-lookup"><span data-stu-id="cd7aa-164">Most of the activities call the non-generic version of the `InvokePowerShell` activity, and do not expect a return value.</span></span> <span data-ttu-id="cd7aa-165">其他活动使用泛型版本的 `InvokePowerShell` 活动，并使用 `InitializationAction` 参数对结果进行后续处理。</span><span class="sxs-lookup"><span data-stu-id="cd7aa-165">Other activities use the generic version of the `InvokePowerShell` activity, and use the `InitializationAction` argument to post-process the results.</span></span>  
  
## <a name="using-the-powershell-project"></a><span data-ttu-id="cd7aa-166">使用 PowerShell 项目</span><span class="sxs-lookup"><span data-stu-id="cd7aa-166">Using the PowerShell Project</span></span>  
 <span data-ttu-id="cd7aa-167">活动的主要操作是在 `ExecutePowerShell` 类中进行的。</span><span class="sxs-lookup"><span data-stu-id="cd7aa-167">The main action of the activity takes place in the `ExecutePowerShell` class.</span></span> <span data-ttu-id="cd7aa-168">由于执行 PowerShell 命令时将不会阻止主要工作流线程，因此通过从 <xref:System.Activities.AsyncCodeActivity> 类继承可将活动创建为异步活动。</span><span class="sxs-lookup"><span data-stu-id="cd7aa-168">Because the execution of PowerShell commands should not block the main workflow thread, the activity is created to be an asynchronous activity by inheriting from the <xref:System.Activities.AsyncCodeActivity> class.</span></span>  
  
 <span data-ttu-id="cd7aa-169">工作流运行时调用 <xref:System.Activities.AsyncCodeActivity.BeginExecute%2A> 方法以开始运行活动。</span><span class="sxs-lookup"><span data-stu-id="cd7aa-169">The <xref:System.Activities.AsyncCodeActivity.BeginExecute%2A> method is called by the workflow runtime to begin running the activity.</span></span> <span data-ttu-id="cd7aa-170">首先，它通过调用 PowerShell API 来创建 PowerShell 管道。</span><span class="sxs-lookup"><span data-stu-id="cd7aa-170">It starts by calling PowerShell APIs to create a PowerShell pipeline.</span></span>  
  
```  
runspace = RunspaceFactory.CreateRunspace();  
runspace.Open();  
pipeline = runspace.CreatePipeline();  
```  
  
 <span data-ttu-id="cd7aa-171">然后，它创建一个 PowerShell 命令并在此命令中填入参数和变量。</span><span class="sxs-lookup"><span data-stu-id="cd7aa-171">It then creates a PowerShell command and populates it with parameters and variables.</span></span>  
  
```  
Command cmd = new Command(this.CommandText, this.IsScript);   
// loop over parameters and run: cmd.Parameters.Add(...)  
// loop over variables and run: runspace.SessionStateProxy.SetVariable(...)  
pipeline.Commands.Add(cmd);  
```  
  
 <span data-ttu-id="cd7aa-172">此时，已传入的输入也将发送到此管道。</span><span class="sxs-lookup"><span data-stu-id="cd7aa-172">The inputs piped in are also sent to the pipeline at this point.</span></span> <span data-ttu-id="cd7aa-173">最后，此管道将包装在 `PipelineInvokerAsyncResult` 对象中，并会返回此管道。</span><span class="sxs-lookup"><span data-stu-id="cd7aa-173">Finally, the pipeline is wrapped in a `PipelineInvokerAsyncResult` object and returned.</span></span> <span data-ttu-id="cd7aa-174">`PipelineInvokerAsyncResult` 对象注册侦听器并调用此管道。</span><span class="sxs-lookup"><span data-stu-id="cd7aa-174">The `PipelineInvokerAsyncResult` object registers a listener and invokes the pipeline.</span></span>  
  
```  
pipeline.InvokeAsync();  
```  
  
 <span data-ttu-id="cd7aa-175">在完成执行后，输出和错误将存储在同一个 `PipelineInvokerAsyncResult` 对象中，并会通过调用最初传递到 <xref:System.Activities.AsyncCodeActivity.BeginExecute%2A> 的回调方法将控制交还给工作流运行时。</span><span class="sxs-lookup"><span data-stu-id="cd7aa-175">When execution finishes, output and errors are stored within the same `PipelineInvokerAsyncResult` object, and control is handed back to the workflow runtime by calling the callback method originally passed to <xref:System.Activities.AsyncCodeActivity.BeginExecute%2A>.</span></span>  
  
 <span data-ttu-id="cd7aa-176">在方法的执行过程结束时，工作流运行时会调用活动的 <xref:System.Activities.AsyncCodeActivity.EndExecute%2A> 方法。</span><span class="sxs-lookup"><span data-stu-id="cd7aa-176">At the end of the method's execution, the workflow runtime calls the activity’s <xref:System.Activities.AsyncCodeActivity.EndExecute%2A> method.</span></span>  
  
 <span data-ttu-id="cd7aa-177">`InvokePowerShell` 类包装 `ExecutePowerShellCommand` 类并创建活动的两个版本，即泛型版本和非泛型版本。</span><span class="sxs-lookup"><span data-stu-id="cd7aa-177">The `InvokePowerShell` class wraps the `ExecutePowerShellCommand` class and creates two versions of the activity; a generic version and a non-generic version.</span></span> <span data-ttu-id="cd7aa-178">非泛型版本直接返回 PowerShell 执行的输出，而泛型版本会将各个结果转换为泛型类型。</span><span class="sxs-lookup"><span data-stu-id="cd7aa-178">The non-generic version returns the output of the PowerShell execution directly, whereas the generic version transforms the individual results to the generic type.</span></span>  
  
 <span data-ttu-id="cd7aa-179">将泛型版本的活动作为一个顺序工作流实现，这将调用 `ExecutePowerShellCommand` 并对其结果进行后续处理。</span><span class="sxs-lookup"><span data-stu-id="cd7aa-179">The generic version of the activity is implemented as a sequential workflow that calls `ExecutePowerShellCommand` and post-processes its results.</span></span> <span data-ttu-id="cd7aa-180">对于结果集合中的每个元素，后续处理步骤将调用 `InitializationAction`（如果已设置的话）。</span><span class="sxs-lookup"><span data-stu-id="cd7aa-180">For each element in the result collection, the post-processing step calls `InitializationAction` if it is set.</span></span> <span data-ttu-id="cd7aa-181">否则，它将执行一个简单的强制转换。</span><span class="sxs-lookup"><span data-stu-id="cd7aa-181">Otherwise, it does a simple cast.</span></span>  
  
```  
new ForEach<PSObject>  
{  
    Values = psObjects,  
    Body = new ActivityAction<PSObject>  
    {  
        Argument = psObject,  
        Handler = new Sequence  
        {  
            Activities =  
            {  
                new If  
                {  
                    Condition = // Is InitializationAction set?  
                    Then = new InvokeFunc<PSObject, TResult>  
                    {  
                        Argument = psObject,  
                        Result = outputObject,  
                        Func = this.InitializationAction  
                    },  
                    Else = new Assign<TResult>  
                    {  
                        To = outputObject,  
                        Value = new InArgument<TResult>(ctx => (TResult) psObject.Get(ctx).BaseObject),  
                    }  
                },  
                new AddToCollection<TResult>  
                {  
                    Collection = outputObjects,  
                    Item = outputObject  
                },  
            }  
        }  
    }  
},  
```  
  
 <span data-ttu-id="cd7aa-182">已为两个 `InvokePowerShell` 活动（泛型和非泛型）创建了设计器。</span><span class="sxs-lookup"><span data-stu-id="cd7aa-182">For each of the two `InvokePowerShell` activities (generic, and non-generic), a designer was created.</span></span> <span data-ttu-id="cd7aa-183">InvokePowerShellDesigner.xaml 及其关联的 .cs 文件定义非泛型版本的 [!INCLUDE[wfd2](../../../../includes/wfd2-md.md)] 活动在 `InvokePowerShell` 中时的外观。</span><span class="sxs-lookup"><span data-stu-id="cd7aa-183">InvokePowerShellDesigner.xaml and its associated .cs file define the appearance in [!INCLUDE[wfd2](../../../../includes/wfd2-md.md)] for the non-generic version of the `InvokePowerShell` activity.</span></span> <span data-ttu-id="cd7aa-184">在 InvokePowerShellDesigner.xaml 中，将使用 <xref:System.Windows.Controls.DockPanel> 表示图形界面。</span><span class="sxs-lookup"><span data-stu-id="cd7aa-184">Inside InvokePowerShellDesigner.xaml, a <xref:System.Windows.Controls.DockPanel> is used to represent the graphical interface.</span></span>  
  
```  
<DockPanel x:Uid="DockPanel_1" LastChildFill="True">  
        <TextBlock x:Uid="TextBlock_1" Text="CommandText" />  
        <TextBox x:Uid="TextBox_1" Text="{Binding Path=ModelItem.CommandText, Mode=TwoWay}"  
                 TextWrapping="WrapWithOverflow"  AcceptsReturn="True" MinLines="4" MaxLines="4"  
                 Background="{x:Null}" Margin="3" />  
    </DockPanel>  
```  
  
 <span data-ttu-id="cd7aa-185">请注意，文本框的 `Text` 属性是一个双向绑定，它可确保活动的 `CommandText` 属性的值与设计器中输入的值相等。</span><span class="sxs-lookup"><span data-stu-id="cd7aa-185">Note that the `Text` property of the text box is a two-way binding that ensures that the value of the activity’s `CommandText` property is equivalent to the value input into the designer.</span></span>  
  
 <span data-ttu-id="cd7aa-186">GenericInvokePowerShellDesigner.xaml 及其关联的 .cs 文件定义了泛型 `InvokePowerShell` 活动的图形界面。</span><span class="sxs-lookup"><span data-stu-id="cd7aa-186">GenericInvokePowerShellDesigner.xaml and its associated .cs file define the graphical interface for the generic `InvokePowerShell` activity.</span></span> <span data-ttu-id="cd7aa-187">设计器会稍微复杂一些，因为它允许用户设置 `InitializationAction`。</span><span class="sxs-lookup"><span data-stu-id="cd7aa-187">The designer is slightly more complicated because it allows users to set an `InitializationAction`.</span></span> <span data-ttu-id="cd7aa-188">关键在于使用 <xref:System.Activities.Presentation.WorkflowItemPresenter> 以允许将子活动拖放到 `InvokePowerShell` 设计器图面上。</span><span class="sxs-lookup"><span data-stu-id="cd7aa-188">The key element is the usage of <xref:System.Activities.Presentation.WorkflowItemPresenter> to allow drag and drop of child activities onto the `InvokePowerShell` designer surface.</span></span>  
  
```  
<sap:WorkflowItemPresenter x:Uid="sap:WorkflowItemPresenter_1" Margin="0,10,0,10"  
    HintText="Drop Activities Here"  
    AllowedItemType="{x:Type sa:Activity}"  
    Item="{Binding Path=ModelItem.InitializationAction.Handler, Mode=TwoWay}"  
    Grid.Row="1" Grid.Column="1" />  
```  
  
 <span data-ttu-id="cd7aa-189">设计器自定义并不仅限于用于定义活动在设计画布上的外观的 .xaml 文件。</span><span class="sxs-lookup"><span data-stu-id="cd7aa-189">The designer customization does not stop with the .xaml files that define the appearance of the activity on the design canvas.</span></span> <span data-ttu-id="cd7aa-190">还可以自定义用于显示活动参数的对话框。</span><span class="sxs-lookup"><span data-stu-id="cd7aa-190">The dialog boxes used to display the parameters of the activity can also be customized.</span></span> <span data-ttu-id="cd7aa-191">这些参数和 PowerShell 变量将影响 PowerShell 命令的行为。</span><span class="sxs-lookup"><span data-stu-id="cd7aa-191">These parameters and PowerShell variables affect the behavior of PowerShell commands.</span></span> <span data-ttu-id="cd7aa-192">该活动将其作为公开<!--zz <xref:System.Collections.Generic.Dictionary%601>-->`System.Collections.Generic.Dictionary`类型。</span><span class="sxs-lookup"><span data-stu-id="cd7aa-192">The activity exposes them as <!--zz <xref:System.Collections.Generic.Dictionary%601>--> `System.Collections.Generic.Dictionary` types.</span></span> <span data-ttu-id="cd7aa-193">ArgumentDictionaryEditor.cs、PropertyEditorResources.xaml 和 PropertyEditorResources.cs 定义可供你用来编辑这些类型的对话框。</span><span class="sxs-lookup"><span data-stu-id="cd7aa-193">ArgumentDictionaryEditor.cs, PropertyEditorResources.xaml and PropertyEditorResources.cs define the dialog box that allows you to edit these types.</span></span>  
  
## <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="cd7aa-194">设置、生成和运行示例</span><span class="sxs-lookup"><span data-stu-id="cd7aa-194">To set up, build, and run the sample</span></span>  
 <span data-ttu-id="cd7aa-195">必须安装 Windows PowerShell 才能运行此示例。</span><span class="sxs-lookup"><span data-stu-id="cd7aa-195">You must install Windows PowerShell to run this sample.</span></span> <span data-ttu-id="cd7aa-196">可以从以下位置安装 Windows PowerShell: [Windows PowerShell](https://go.microsoft.com/fwlink/?LinkId=150383)。</span><span class="sxs-lookup"><span data-stu-id="cd7aa-196">Windows PowerShell can be installed from this location: [Windows PowerShell](https://go.microsoft.com/fwlink/?LinkId=150383).</span></span>  
  
#### <a name="to-run-the-coded-client"></a><span data-ttu-id="cd7aa-197">运行 CodedClient</span><span class="sxs-lookup"><span data-stu-id="cd7aa-197">To run the coded client</span></span>  
  
1.  <span data-ttu-id="cd7aa-198">使用 [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] 打开 PowerShell.sln。</span><span class="sxs-lookup"><span data-stu-id="cd7aa-198">Open PowerShell.sln using [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)].</span></span>  
  
2.  <span data-ttu-id="cd7aa-199">右击该解决方案并生成它。</span><span class="sxs-lookup"><span data-stu-id="cd7aa-199">Right-click the solution and build it.</span></span>  
  
3.  <span data-ttu-id="cd7aa-200">右键单击**CodedClient**项目，然后选择**设为启动项目**。</span><span class="sxs-lookup"><span data-stu-id="cd7aa-200">Right-click the **CodedClient** project and select **Set as Startup Project**.</span></span>  
  
4.  <span data-ttu-id="cd7aa-201">按 Ctrl+F5 运行应用程序。</span><span class="sxs-lookup"><span data-stu-id="cd7aa-201">Press CTRL+F5 to run the application.</span></span>  
  
#### <a name="to-run-the-designer-client"></a><span data-ttu-id="cd7aa-202">运行 DesignerClient</span><span class="sxs-lookup"><span data-stu-id="cd7aa-202">To run the designer client</span></span>  
  
1.  <span data-ttu-id="cd7aa-203">使用 [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] 打开 PowerShell.sln。</span><span class="sxs-lookup"><span data-stu-id="cd7aa-203">Open PowerShell.sln using [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)].</span></span>  
  
2.  <span data-ttu-id="cd7aa-204">右击该解决方案并生成它。</span><span class="sxs-lookup"><span data-stu-id="cd7aa-204">Right-click the solution and build it.</span></span>  
  
3.  <span data-ttu-id="cd7aa-205">右键单击**DesignerClient**项目，然后选择**设为启动项目**。</span><span class="sxs-lookup"><span data-stu-id="cd7aa-205">Right-click the **DesignerClient** project and select **Set as Startup Project**.</span></span>  
  
4.  <span data-ttu-id="cd7aa-206">按 Ctrl+F5 运行应用程序。</span><span class="sxs-lookup"><span data-stu-id="cd7aa-206">Press CTRL+F5 to run the application.</span></span>  
  
## <a name="known-issues"></a><span data-ttu-id="cd7aa-207">已知问题</span><span class="sxs-lookup"><span data-stu-id="cd7aa-207">Known Issues</span></span>  
  
1.  <span data-ttu-id="cd7aa-208">如果从另一个项目引用 `InvokePowerShell` 活动程序集或项目时导致出现生成错误，则可能需要手动将 `<SpecificVersion>True</SpecificVersion>` 元素添加到该新项目的 .csproj 文件中引用 `InvokePowerShell` 的行下方。</span><span class="sxs-lookup"><span data-stu-id="cd7aa-208">If referencing the `InvokePowerShell` activity assembly or project from another project results in a build error, you may need to manually add the `<SpecificVersion>True</SpecificVersion>` element to the .csproj file of the new project under the line that references `InvokePowerShell`.</span></span>  
  
2.  <span data-ttu-id="cd7aa-209">如果未安装 Windows PowerShell，只要您将添加在 Visual Studio 中显示以下错误消息`InvokePowerShell`到工作流活动： `Workflow Designer encountered problems with your document. Could not load file or assembly ‘System.Management.Automation’ ... or one of its dependencies. The system cannot find the file specified.`</span><span class="sxs-lookup"><span data-stu-id="cd7aa-209">If Windows PowerShell is not installed, the following error message is displayed in Visual Studio as soon as you add an `InvokePowerShell` activity onto a workflow: `Workflow Designer encountered problems with your document. Could not load file or assembly ‘System.Management.Automation’ ... or one of its dependencies. The system cannot find the file specified.`</span></span>  
  
3.  <span data-ttu-id="cd7aa-210">在 Windows PowerShell 2.0 中，以编程方式调用 `$input.MoveNext()` 失败，并且使用 `$input.MoveNext()` 的脚本会产生意外的错误和结果。</span><span class="sxs-lookup"><span data-stu-id="cd7aa-210">In Windows PowerShell 2.0, programmatically calling `$input.MoveNext()` fails and scripts using `$input.MoveNext()` produce unintended errors and results.</span></span> <span data-ttu-id="cd7aa-211">若要解决此问题，请考虑在循环访问数组时使用 PowerShell 谓词 `foreach` 而不是调用 `MoveNext()`。  </span><span class="sxs-lookup"><span data-stu-id="cd7aa-211">To work around this issue, consider using the PowerShell verb `foreach` instead of calling `MoveNext()` when iterating an array.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="cd7aa-212">您的计算机上可能已安装这些示例。</span><span class="sxs-lookup"><span data-stu-id="cd7aa-212">The samples may already be installed on your machine.</span></span> <span data-ttu-id="cd7aa-213">在继续操作之前，请先检查以下（默认）目录：</span><span class="sxs-lookup"><span data-stu-id="cd7aa-213">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="cd7aa-214">如果此目录不存在，请转到[Windows Communication Foundation (WCF) 和.NET Framework 4 的 Windows Workflow Foundation (WF) 示例](https://go.microsoft.com/fwlink/?LinkId=150780)若要下载所有 Windows Communication Foundation (WCF) 和[!INCLUDE[wf1](../../../../includes/wf1-md.md)]示例。</span><span class="sxs-lookup"><span data-stu-id="cd7aa-214">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="cd7aa-215">此示例位于以下目录：</span><span class="sxs-lookup"><span data-stu-id="cd7aa-215">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Scenario\ActivityLibrary\PowerShell`