---
title: ETW 추적
ms.date: 03/30/2017
ms.assetid: ac99a063-e2d2-40cc-b659-d23c2f783f92
ms.openlocfilehash: a62403e61e0566d5e7b753ff951bf4b316209b6f
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/24/2020
ms.locfileid: "76742112"
---
# <a name="etw-tracing"></a><span data-ttu-id="27586-102">ETW 추적</span><span class="sxs-lookup"><span data-stu-id="27586-102">ETW Tracing</span></span>
<span data-ttu-id="27586-103">이 샘플에서는 ETW(Windows용 이벤트 추적) 및 이 샘플과 함께 제공된 `ETWTraceListener`를 사용하여 E2E(엔드투엔드) 추적을 구현하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="27586-103">This sample demonstrates how to implement End-to-End (E2E) tracing using Event Tracing for Windows (ETW) and the `ETWTraceListener` that is provided with this sample.</span></span> <span data-ttu-id="27586-104">该示例基于[入门](../../../../docs/framework/wcf/samples/getting-started-sample.md)，并包括 ETW 跟踪。</span><span class="sxs-lookup"><span data-stu-id="27586-104">The sample is based on the [Getting Started](../../../../docs/framework/wcf/samples/getting-started-sample.md) and includes ETW tracing.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="27586-105">이 샘플의 설치 절차 및 빌드 지침은 이 항목의 끝부분에 나와 있습니다.</span><span class="sxs-lookup"><span data-stu-id="27586-105">The set-up procedure and build instructions for this sample are located at the end of this topic.</span></span>  
  
 <span data-ttu-id="27586-106">本示例假定您熟悉[跟踪和消息日志记录](../../../../docs/framework/wcf/samples/tracing-and-message-logging.md)。</span><span class="sxs-lookup"><span data-stu-id="27586-106">This sample assumes that you are familiar with [Tracing and Message Logging](../../../../docs/framework/wcf/samples/tracing-and-message-logging.md).</span></span>  
  
 <span data-ttu-id="27586-107"><xref:System.Diagnostics> 추적 모델의 추적 소스마다 데이터가 추적되는 위치와 방법을 결정하는 추적 수신기가 여러 개씩 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="27586-107">Each trace source in the <xref:System.Diagnostics> tracing model can have multiple trace listeners that determine where and how the data is traced.</span></span> <span data-ttu-id="27586-108">수신기의 형식에 따라 추적 데이터가 기록되는 형식이 정의됩니다.</span><span class="sxs-lookup"><span data-stu-id="27586-108">The type of listener defines the format in which trace data is logged.</span></span> <span data-ttu-id="27586-109">다음 코드 샘플에서는 수신기를 구성에 추가하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="27586-109">The following code sample shows how to add the listener to configuration.</span></span>  
  
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
  
 <span data-ttu-id="27586-110">이 수신기를 사용하기 전에 ETW 추적 세션이 시작되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="27586-110">Before using this listener, an ETW Trace Session must be started.</span></span> <span data-ttu-id="27586-111">이 세션은 Logman.exe 또는 Tracelog.exe를 사용하여 시작할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="27586-111">This session can be started by using Logman.exe or Tracelog.exe.</span></span> <span data-ttu-id="27586-112">SetupETW.bat 파일이 이 샘플에 포함되어 있으므로 ETW 추적 세션을 닫고 로그 파일을 완료하는 CleanupETW.bat 파일과 함께 세션을 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="27586-112">A SetupETW.bat file is included with this sample so that you can set up the ETW Trace Session along with a CleanupETW.bat file for closing the session and completing the log file.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="27586-113">이 샘플의 설치 절차 및 빌드 지침은 이 항목의 끝부분에 나와 있습니다.</span><span class="sxs-lookup"><span data-stu-id="27586-113">The setup procedure and build instructions for this sample are located at the end of this topic.</span></span> <span data-ttu-id="27586-114">有关这些工具的详细信息，请参阅 <https://go.microsoft.com/fwlink/?LinkId=56580></span><span class="sxs-lookup"><span data-stu-id="27586-114">For more information about these tools, see <https://go.microsoft.com/fwlink/?LinkId=56580></span></span>  
  
 <span data-ttu-id="27586-115">ETWTraceListener를 사용할 경우 추적은 이진 .etl 파일에 기록됩니다.</span><span class="sxs-lookup"><span data-stu-id="27586-115">When using the ETWTraceListener, traces are logged in binary .etl files.</span></span> <span data-ttu-id="27586-116">ServiceModel 추적이 설정된 상태에서 생성된 모든 추적은 동일한 파일에 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="27586-116">With ServiceModel tracing turned on, all generated traces appear in the same file.</span></span> <span data-ttu-id="27586-117">使用[服务跟踪查看器工具（svctraceviewer.exe）](../../../../docs/framework/wcf/service-trace-viewer-tool-svctraceviewer-exe.md)来查看 .etl 和 .svclog 日志文件。</span><span class="sxs-lookup"><span data-stu-id="27586-117">Use [Service Trace Viewer Tool (SvcTraceViewer.exe)](../../../../docs/framework/wcf/service-trace-viewer-tool-svctraceviewer-exe.md) for viewing .etl and .svclog log files.</span></span> <span data-ttu-id="27586-118">이 뷰어는 해당 소스에서 해당 대상 및 소비 지점까지 메시지를 추적하는 데 사용할 수 있는 시스템의 엔드투엔드 보기를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="27586-118">The viewer creates an end-to-end view of the system that makes it possible to trace a message from its source to its destination and point of consumption.</span></span>  
  
 <span data-ttu-id="27586-119">ETW 추적 수신기는 순환 로깅을 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="27586-119">The ETW Trace Listener supports circular logging.</span></span> <span data-ttu-id="27586-120">若要启用此功能，请参阅**开始**，**运行**，然后键入 `cmd` 以启动命令控制台。</span><span class="sxs-lookup"><span data-stu-id="27586-120">To enable this feature, go to **Start**, **Run** and type `cmd` to start a command console.</span></span> <span data-ttu-id="27586-121">다음 명령에서 `<logfilename>` 매개 변수를 로그 파일의 이름으로 바꿉니다.</span><span class="sxs-lookup"><span data-stu-id="27586-121">In the following command, replace the `<logfilename>` parameter with the name of your log file.</span></span>  
  
```console  
logman create trace Wcf -o <logfilename> -p "{411a0819-c24b-428c-83e2-26b41091702e}" -f bincirc -max 1000  
```  
  
 <span data-ttu-id="27586-122">`-f` 및 `-max` 스위치는 선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="27586-122">The `-f` and `-max` switches are optional.</span></span> <span data-ttu-id="27586-123">이러한 스위치는 각각 이진 순환 형식과 1000MB의 최대 로그 크기를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="27586-123">They specify the binary circular format and max log size of 1000MB respectively.</span></span> <span data-ttu-id="27586-124">`-p` 스위치는 추적 공급자를 지정하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="27586-124">The `-p` switch is used to specify the trace provider.</span></span> <span data-ttu-id="27586-125">위 예제에서 `"{411a0819-c24b-428c-83e2-26b41091702e}"`는 "XML ETW 샘플 공급자"의 GUID입니다.</span><span class="sxs-lookup"><span data-stu-id="27586-125">In our example, `"{411a0819-c24b-428c-83e2-26b41091702e}"` is the GUID for "XML ETW Sample Provider".</span></span>  
  
 <span data-ttu-id="27586-126">세션을 시작하려면 다음 명령을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="27586-126">To start the session, type in the following command.</span></span>  
  
```console  
logman start Wcf  
```  
  
 <span data-ttu-id="27586-127">로깅을 완료한 후 다음 명령을 사용하여 세션을 중지할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="27586-127">After you have finished logging, you can stop the session with the following command.</span></span>  
  
```console  
logman stop Wcf  
```  
  
 <span data-ttu-id="27586-128">此过程将生成二进制循环日志，可以通过所选的工具[（包括服务跟踪查看器工具（svctraceviewer.exe）](../../../../docs/framework/wcf/service-trace-viewer-tool-svctraceviewer-exe.md)或 Tracerpt）进行处理。</span><span class="sxs-lookup"><span data-stu-id="27586-128">This process generates binary circular logs that you can process with your tool of choice, including [Service Trace Viewer Tool (SvcTraceViewer.exe)](../../../../docs/framework/wcf/service-trace-viewer-tool-svctraceviewer-exe.md) or Tracerpt.</span></span>  
  
 <span data-ttu-id="27586-129">若要详细了解如何执行循环日志记录，还可以查看[循环跟踪](../../../../docs/framework/wcf/samples/circular-tracing.md)示例。</span><span class="sxs-lookup"><span data-stu-id="27586-129">You can also review the [Circular Tracing](../../../../docs/framework/wcf/samples/circular-tracing.md) sample for more information on an alternative listener to perform circular logging.</span></span>  
  
### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="27586-130">샘플을 설치, 빌드 및 실행하려면</span><span class="sxs-lookup"><span data-stu-id="27586-130">To set up, build, and run the sample</span></span>  
  
1. <span data-ttu-id="27586-131">请确保已[为 Windows Communication Foundation 示例执行了一次性安装过程](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md)。</span><span class="sxs-lookup"><span data-stu-id="27586-131">Be sure you have performed the [One-Time Setup Procedure for the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span></span>  
  
2. <span data-ttu-id="27586-132">若要生成解决方案，请按照[生成 Windows Communication Foundation 示例](../../../../docs/framework/wcf/samples/building-the-samples.md)中的说明进行操作。</span><span class="sxs-lookup"><span data-stu-id="27586-132">To build the solution, follow the instructions in [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span></span>  
  
    > [!NOTE]
    > <span data-ttu-id="27586-133">RegisterProvider.bat, SetupETW.bat 및 CleanupETW.bat 명령을 사용하려면 로컬 관리자 계정으로 실행해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="27586-133">To use the RegisterProvider.bat, SetupETW.bat and CleanupETW.bat commands, you must run under a local administrator account.</span></span> <span data-ttu-id="27586-134">如果你使用的是 Windows Vista 或更高版本，则还必须使用提升的权限运行命令提示符。</span><span class="sxs-lookup"><span data-stu-id="27586-134">If you are using Windows Vista or later, you must also run the command prompt with elevated privileges.</span></span> <span data-ttu-id="27586-135">为此，请右键单击 "命令提示符" 图标，然后单击 "以**管理员身份运行**"。</span><span class="sxs-lookup"><span data-stu-id="27586-135">To do so, right-click the command prompt icon, then click **Run as administrator**.</span></span>  
  
3. <span data-ttu-id="27586-136">샘플을 실행하기 전에 RegisterProvider.bat를 클라이언트와 서버에서 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="27586-136">Before running the sample, run RegisterProvider.bat on the client and server.</span></span> <span data-ttu-id="27586-137">이렇게 하면 Service Trace Viewer에서 읽을 수 있는 추적을 생성하도록 결과 ETWTracingSampleLog.etl 파일이 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="27586-137">This sets up the resulting ETWTracingSampleLog.etl file to generate traces that can be read by the Service Trace Viewer.</span></span> <span data-ttu-id="27586-138">이 파일은 C:\logs 폴더에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="27586-138">This file can be found in the C:\logs folder.</span></span> <span data-ttu-id="27586-139">이 폴더가 없을 경우 만들어야 하며 그렇지 않으면 추적이 생성되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="27586-139">If this folder does not exist, it must be created or no traces are generated.</span></span> <span data-ttu-id="27586-140">그런 다음 클라이언트 및 서버 컴퓨터에서 SetupETW.bat를 실행하여 ETW 추적 세션을 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="27586-140">Then, run SetupETW.bat on the client and server computers to begin the ETW Trace Session.</span></span> <span data-ttu-id="27586-141">SetupETW.bat 파일은 CS\Client 폴더에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="27586-141">The SetupETW.bat file can be found under the CS\Client folder.</span></span>  
  
4. <span data-ttu-id="27586-142">若要以单机配置或跨计算机配置来运行示例，请按照[运行 Windows Communication Foundation 示例](../../../../docs/framework/wcf/samples/running-the-samples.md)中的说明进行操作。</span><span class="sxs-lookup"><span data-stu-id="27586-142">To run the sample in a single- or cross-computer configuration, follow the instructions in [Running the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/running-the-samples.md).</span></span>  
  
5. <span data-ttu-id="27586-143">샘플이 완료되면 CleanupETW.bat를 실행하여 ETWTracingSampleLog.etl 파일 만들기를 완료합니다.</span><span class="sxs-lookup"><span data-stu-id="27586-143">When the sample is completed, run CleanupETW.bat to complete the creation of the ETWTracingSampleLog.etl file.</span></span>  
  
6. <span data-ttu-id="27586-144">Service Trace Viewer 내에서 ETWTracingSampleLog.etl 파일을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="27586-144">Open the ETWTracingSampleLog.etl file from within the Service Trace Viewer.</span></span> <span data-ttu-id="27586-145">이진 형식 파일을 .svclog 파일로 저장하라는 메시지가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="27586-145">You will be prompted to save the binary formatted file as a .svclog file.</span></span>  
  
7. <span data-ttu-id="27586-146">서비스 추적 뷰어 내에서 새로 만든 .svclog 파일을 열어 ETW 및 ServiceModel 추적을 봅니다.</span><span class="sxs-lookup"><span data-stu-id="27586-146">Open the newly created .svclog file from within the Service Trace Viewer to view the ETW and ServiceModel traces.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="27586-147">컴퓨터에 이 샘플이 이미 설치되어 있을 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="27586-147">The samples may already be installed on your computer.</span></span> <span data-ttu-id="27586-148">계속하기 전에 다음(기본) 디렉터리를 확인하세요.</span><span class="sxs-lookup"><span data-stu-id="27586-148">Check for the following (default) directory before continuing.</span></span>  
>   
> `<InstallDrive>:\WF_WCF_Samples`  
>   
> <span data-ttu-id="27586-149">如果此目录不存在，请参阅[.NET Framework 4 的 Windows Communication Foundation （wcf）和 Windows Workflow Foundation （WF）示例](https://www.microsoft.com/download/details.aspx?id=21459)以下载所有 WINDOWS COMMUNICATION FOUNDATION （wcf）和 [!INCLUDE[wf1](../../../../includes/wf1-md.md)] 示例。</span><span class="sxs-lookup"><span data-stu-id="27586-149">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="27586-150">이 샘플은 다음 디렉터리에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="27586-150">This sample is located in the following directory.</span></span>  
>   
> `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Management\AnalyticTrace`  
  
## <a name="see-also"></a><span data-ttu-id="27586-151">另请参阅</span><span class="sxs-lookup"><span data-stu-id="27586-151">See also</span></span>

- <span data-ttu-id="27586-152">[AppFabric 监视示例](https://docs.microsoft.com/previous-versions/appfabric/ff383407(v=azure.10))</span><span class="sxs-lookup"><span data-stu-id="27586-152">[AppFabric Monitoring Samples](https://docs.microsoft.com/previous-versions/appfabric/ff383407(v=azure.10))</span></span>
