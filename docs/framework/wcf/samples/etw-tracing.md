---
title: ETW 跟踪
ms.date: 03/30/2017
ms.assetid: ac99a063-e2d2-40cc-b659-d23c2f783f92
ms.openlocfilehash: 2329ebc8b98b0d34b5acc7861a7e691a31e3ba15
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54700281"
---
# <a name="etw-tracing"></a><span data-ttu-id="4b225-102">ETW 跟踪</span><span class="sxs-lookup"><span data-stu-id="4b225-102">ETW Tracing</span></span>
<span data-ttu-id="4b225-103">本示例演示如何通过使用 Windows 事件跟踪 (ETW) 和本示例提供的 `ETWTraceListener` 来实现端对端 (E2E) 跟踪。</span><span class="sxs-lookup"><span data-stu-id="4b225-103">This sample demonstrates how to implement End-to-End (E2E) tracing using Event Tracing for Windows (ETW) and the `ETWTraceListener` that is provided with this sample.</span></span> <span data-ttu-id="4b225-104">该示例基于[Getting Started](../../../../docs/framework/wcf/samples/getting-started-sample.md)并包括 ETW 跟踪。</span><span class="sxs-lookup"><span data-stu-id="4b225-104">The sample is based on the [Getting Started](../../../../docs/framework/wcf/samples/getting-started-sample.md) and includes ETW tracing.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="4b225-105">本主题的最后介绍了此示例的设置过程和生成说明。</span><span class="sxs-lookup"><span data-stu-id="4b225-105">The set-up procedure and build instructions for this sample are located at the end of this topic.</span></span>  
  
 <span data-ttu-id="4b225-106">此示例假定你熟悉[跟踪和消息日志记录](../../../../docs/framework/wcf/samples/tracing-and-message-logging.md)。</span><span class="sxs-lookup"><span data-stu-id="4b225-106">This sample assumes that you are familiar with [Tracing and Message Logging](../../../../docs/framework/wcf/samples/tracing-and-message-logging.md).</span></span>  
  
 <span data-ttu-id="4b225-107"><xref:System.Diagnostics> 跟踪模型中的每个跟踪源都可以具有多个跟踪侦听器，这些侦听器确定跟踪数据的位置和方式。</span><span class="sxs-lookup"><span data-stu-id="4b225-107">Each trace source in the <xref:System.Diagnostics> tracing model can have multiple trace listeners that determine where and how the data is traced.</span></span> <span data-ttu-id="4b225-108">侦听器的类型定义记录跟踪数据的格式。</span><span class="sxs-lookup"><span data-stu-id="4b225-108">The type of listener defines the format in which trace data is logged.</span></span> <span data-ttu-id="4b225-109">下面的代码示例演示如何向配置中添加侦听器。</span><span class="sxs-lookup"><span data-stu-id="4b225-109">The following code sample shows how to add the listener to configuration.</span></span>  
  
```xml  
<system.diagnostics>  
    <sources>  
        <source name="System.ServiceModel"   
             switchValue="Verbose,ActivityTracing"  
             propagateActivity="true">  
            <listeners>  
                <add type=  
                   "System.Diagnostics.DefaultTraceListener"  
                   name="Default">  
                   <filter type="" />  
                </add>  
                <add name="ETW">  
                    <filter type="" />  
                </add>  
            </listeners>  
        </source>  
    </sources>  
    <sharedListeners>  
        <add type=  
            "Microsoft.ServiceModel.Samples.EtwTraceListener, ETWTraceListener"  
            name="ETW" traceOutputOptions="Timestamp">  
            <filter type="" />  
       </add>  
    </sharedListeners>  
</system.diagnostics>  
```  
  
 <span data-ttu-id="4b225-110">在使用此侦听器之前，必须启动 ETW 跟踪会话。</span><span class="sxs-lookup"><span data-stu-id="4b225-110">Before using this listener, an ETW Trace Session must be started.</span></span> <span data-ttu-id="4b225-111">可以通过使用 Logman.exe 或 Tracelog.exe 来启动此会话。</span><span class="sxs-lookup"><span data-stu-id="4b225-111">This session can be started by using Logman.exe or Tracelog.exe.</span></span> <span data-ttu-id="4b225-112">本示例随附一个 SetupETW.bat 文件，您可以和 CleanupETW.bat 文件一起使用此文件来设置 ETW 跟踪会话，以便关闭会话并完成日志文件。</span><span class="sxs-lookup"><span data-stu-id="4b225-112">A SetupETW.bat file is included with this sample so that you can set up the ETW Trace Session along with a CleanupETW.bat file for closing the session and completing the log file.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="4b225-113">本主题的最后介绍了此示例的设置过程和生成说明。</span><span class="sxs-lookup"><span data-stu-id="4b225-113">The setup procedure and build instructions for this sample are located at the end of this topic.</span></span> <span data-ttu-id="4b225-114">有关这些工具的详细信息，请参阅 [https://go.microsoft.com/fwlink/?LinkId=56580](https://go.microsoft.com/fwlink/?LinkId=56580)</span><span class="sxs-lookup"><span data-stu-id="4b225-114">For more information about these tools, see [https://go.microsoft.com/fwlink/?LinkId=56580](https://go.microsoft.com/fwlink/?LinkId=56580)</span></span>  
  
 <span data-ttu-id="4b225-115">使用 ETWTraceListener 时，将在二进制 .etl 文件中记录跟踪。</span><span class="sxs-lookup"><span data-stu-id="4b225-115">When using the ETWTraceListener, traces are logged in binary .etl files.</span></span> <span data-ttu-id="4b225-116">在打开 ServiceModel 跟踪的情况下，所有生成的跟踪都显示在同一个文件中。</span><span class="sxs-lookup"><span data-stu-id="4b225-116">With ServiceModel tracing turned on, all generated traces appear in the same file.</span></span> <span data-ttu-id="4b225-117">使用[Service Trace Viewer Tool (SvcTraceViewer.exe)](../../../../docs/framework/wcf/service-trace-viewer-tool-svctraceviewer-exe.md)用于查看.etl 和.svclog 日志文件。</span><span class="sxs-lookup"><span data-stu-id="4b225-117">Use [Service Trace Viewer Tool (SvcTraceViewer.exe)](../../../../docs/framework/wcf/service-trace-viewer-tool-svctraceviewer-exe.md) for viewing .etl and .svclog log files.</span></span> <span data-ttu-id="4b225-118">该查看器可创建系统的端对端视图，可以从消息源到消息目标和使用点来跟踪消息。</span><span class="sxs-lookup"><span data-stu-id="4b225-118">The viewer creates an end-to-end view of the system that makes it possible to trace a message from its source to its destination and point of consumption.</span></span>  
  
 <span data-ttu-id="4b225-119">ETW 跟踪侦听器支持循环记录。</span><span class="sxs-lookup"><span data-stu-id="4b225-119">The ETW Trace Listener supports circular logging.</span></span> <span data-ttu-id="4b225-120">若要启用此功能，请转到**启动**，**运行**并键入`cmd`以启动命令控制台。</span><span class="sxs-lookup"><span data-stu-id="4b225-120">To enable this feature, go to **Start**, **Run** and type `cmd` to start a command console.</span></span> <span data-ttu-id="4b225-121">在下面的命令中，用日志文件的名称替换 `<logfilename>` 参数。</span><span class="sxs-lookup"><span data-stu-id="4b225-121">In the following command, replace the `<logfilename>` parameter with the name of your log file.</span></span>  
  
```  
logman create trace Wcf -o <logfilename> -p "{411a0819-c24b-428c-83e2-26b41091702e}" -f bincirc -max 1000  
```  
  
 <span data-ttu-id="4b225-122">`-f` 和 `-max` 开关是可选的。</span><span class="sxs-lookup"><span data-stu-id="4b225-122">The `-f` and `-max` switches are optional.</span></span> <span data-ttu-id="4b225-123">它们分别指定二进制循环格式和 1000 MB 的最大日志大小。</span><span class="sxs-lookup"><span data-stu-id="4b225-123">They specify the binary circular format and max log size of 1000MB respectively.</span></span> <span data-ttu-id="4b225-124">`-p` 开关用于指定跟踪提供程序。</span><span class="sxs-lookup"><span data-stu-id="4b225-124">The `-p` switch is used to specify the trace provider.</span></span> <span data-ttu-id="4b225-125">在我们的示例中，`"{411a0819-c24b-428c-83e2-26b41091702e}"` 是“XML ETW 示例提供程序”的 GUID。</span><span class="sxs-lookup"><span data-stu-id="4b225-125">In our example, `"{411a0819-c24b-428c-83e2-26b41091702e}"` is the GUID for "XML ETW Sample Provider".</span></span>  
  
 <span data-ttu-id="4b225-126">若要启动会话，请键入以下命令。</span><span class="sxs-lookup"><span data-stu-id="4b225-126">To start the session, type in the following command.</span></span>  
  
```  
Logman start Wcf  
```  
  
 <span data-ttu-id="4b225-127">在完成日志记录后，可以用下面的命令停止会话。</span><span class="sxs-lookup"><span data-stu-id="4b225-127">After you have finished logging, you can stop the session with the following command.</span></span>  
  
```  
Logman stop Wcf  
```  
  
 <span data-ttu-id="4b225-128">此过程会生成与所选的工具可以处理的二进制循环日志包括[Service Trace Viewer Tool (SvcTraceViewer.exe)](../../../../docs/framework/wcf/service-trace-viewer-tool-svctraceviewer-exe.md)或 Tracerpt。</span><span class="sxs-lookup"><span data-stu-id="4b225-128">This process generates binary circular logs that you can process with your tool of choice, including [Service Trace Viewer Tool (SvcTraceViewer.exe)](../../../../docs/framework/wcf/service-trace-viewer-tool-svctraceviewer-exe.md) or Tracerpt.</span></span>  
  
 <span data-ttu-id="4b225-129">此外可以查看[循环跟踪](../../../../docs/framework/wcf/samples/circular-tracing.md)示例执行循环日志记录的替代侦听器的详细信息。</span><span class="sxs-lookup"><span data-stu-id="4b225-129">You can also review the [Circular Tracing](../../../../docs/framework/wcf/samples/circular-tracing.md) sample for more information on an alternative listener to perform circular logging.</span></span>  
  
### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="4b225-130">设置、生成和运行示例</span><span class="sxs-lookup"><span data-stu-id="4b225-130">To set up, build, and run the sample</span></span>  
  
1.  <span data-ttu-id="4b225-131">确保您已执行了[的 Windows Communication Foundation 示例的一次性安装过程](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md)。</span><span class="sxs-lookup"><span data-stu-id="4b225-131">Be sure you have performed the [One-Time Setup Procedure for the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span></span>  
  
2.  <span data-ttu-id="4b225-132">若要生成解决方案，请按照中的说明[生成 Windows Communication Foundation 示例](../../../../docs/framework/wcf/samples/building-the-samples.md)。</span><span class="sxs-lookup"><span data-stu-id="4b225-132">To build the solution, follow the instructions in [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="4b225-133">若要使用 RegisterProvider.bat、SetupETW.bat 和 CleanupETW.bat 命令，必须在本地管理员帐户下运行。</span><span class="sxs-lookup"><span data-stu-id="4b225-133">To use the RegisterProvider.bat, SetupETW.bat and CleanupETW.bat commands, you must run under a local administrator account.</span></span> <span data-ttu-id="4b225-134">如果使用的是 [!INCLUDE[wv](../../../../includes/wv-md.md)] 或更高版本，则还必须用提升的特权运行命令提示。</span><span class="sxs-lookup"><span data-stu-id="4b225-134">If you are using [!INCLUDE[wv](../../../../includes/wv-md.md)] or later, you must also run the command prompt with elevated privileges.</span></span> <span data-ttu-id="4b225-135">为此，请右键单击命令提示符图标，然后单击**以管理员身份运行**。</span><span class="sxs-lookup"><span data-stu-id="4b225-135">To do so, right-click the command prompt icon, then click **Run as administrator**.</span></span>  
  
3.  <span data-ttu-id="4b225-136">运行示例之前，在客户端和服务器上运行 RegisterProvider.bat。</span><span class="sxs-lookup"><span data-stu-id="4b225-136">Before running the sample, run RegisterProvider.bat on the client and server.</span></span> <span data-ttu-id="4b225-137">这会设置生成的 ETWTracingSampleLog.etl 文件以生成可由服务跟踪查看器读取的跟踪。</span><span class="sxs-lookup"><span data-stu-id="4b225-137">This sets up the resulting ETWTracingSampleLog.etl file to generate traces that can be read by the Service Trace Viewer.</span></span> <span data-ttu-id="4b225-138">此文件可以在 C:\logs 文件夹中找到。</span><span class="sxs-lookup"><span data-stu-id="4b225-138">This file can be found in the C:\logs folder.</span></span> <span data-ttu-id="4b225-139">如果此文件夹不存在，则必须创建此文件夹；否则将不会生成跟踪。</span><span class="sxs-lookup"><span data-stu-id="4b225-139">If this folder does not exist, it must be created or no traces are generated.</span></span> <span data-ttu-id="4b225-140">然后，在客户端和服务器计算机上运行 SetupETW.bat 以开始 ETW 跟踪会话。</span><span class="sxs-lookup"><span data-stu-id="4b225-140">Then, run SetupETW.bat on the client and server computers to begin the ETW Trace Session.</span></span> <span data-ttu-id="4b225-141">SetupETW.bat 文件可以在 CS\Client 文件夹下找到。</span><span class="sxs-lookup"><span data-stu-id="4b225-141">The SetupETW.bat file can be found under the CS\Client folder.</span></span>  
  
4.  <span data-ttu-id="4b225-142">若要在单或跨计算机配置中运行示例，请按照中的说明[运行 Windows Communication Foundation 示例](../../../../docs/framework/wcf/samples/running-the-samples.md)。</span><span class="sxs-lookup"><span data-stu-id="4b225-142">To run the sample in a single- or cross-computer configuration, follow the instructions in [Running the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/running-the-samples.md).</span></span>  
  
5.  <span data-ttu-id="4b225-143">示例完成后，运行 CleanupETW.bat 以完成 ETWTracingSampleLog.etl 文件的创建。</span><span class="sxs-lookup"><span data-stu-id="4b225-143">When the sample is completed, run CleanupETW.bat to complete the creation of the ETWTracingSampleLog.etl file.</span></span>  
  
6.  <span data-ttu-id="4b225-144">在服务跟踪查看器中打开 ETWTracingSampleLog.etl 文件。</span><span class="sxs-lookup"><span data-stu-id="4b225-144">Open the ETWTracingSampleLog.etl file from within the Service Trace Viewer.</span></span> <span data-ttu-id="4b225-145">系统会提示您将二进制格式的文件另存为 .svclog 文件。</span><span class="sxs-lookup"><span data-stu-id="4b225-145">You will be prompted to save the binary formatted file as a .svclog file.</span></span>  
  
7.  <span data-ttu-id="4b225-146">从服务跟踪查看器中打开新创建的 .svclog 文件以查看 ETW 和 ServiceModel 跟踪。</span><span class="sxs-lookup"><span data-stu-id="4b225-146">Open the newly created .svclog file from within the Service Trace Viewer to view the ETW and ServiceModel traces.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="4b225-147">您的计算机上可能已安装这些示例。</span><span class="sxs-lookup"><span data-stu-id="4b225-147">The samples may already be installed on your computer.</span></span> <span data-ttu-id="4b225-148">在继续操作之前，请先检查以下（默认）目录：</span><span class="sxs-lookup"><span data-stu-id="4b225-148">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="4b225-149">如果此目录不存在，请转到[Windows Communication Foundation (WCF) 和.NET Framework 4 的 Windows Workflow Foundation (WF) 示例](https://go.microsoft.com/fwlink/?LinkId=150780)若要下载所有 Windows Communication Foundation (WCF) 和[!INCLUDE[wf1](../../../../includes/wf1-md.md)]示例。</span><span class="sxs-lookup"><span data-stu-id="4b225-149">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="4b225-150">此示例位于以下目录：</span><span class="sxs-lookup"><span data-stu-id="4b225-150">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Management\AnalyticTrace`  
  
## <a name="see-also"></a><span data-ttu-id="4b225-151">请参阅</span><span class="sxs-lookup"><span data-stu-id="4b225-151">See also</span></span>
- [<span data-ttu-id="4b225-152">AppFabric 监视示例</span><span class="sxs-lookup"><span data-stu-id="4b225-152">AppFabric Monitoring Samples</span></span>](https://go.microsoft.com/fwlink/?LinkId=193959)
