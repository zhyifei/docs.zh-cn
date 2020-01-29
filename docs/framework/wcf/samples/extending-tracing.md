---
title: 추적 확장
ms.date: 03/30/2017
ms.assetid: 2b971a99-16ec-4949-ad2e-b0c8731a873f
ms.openlocfilehash: c6d62f6c334261b0dc897a1c1a2cd71d40ee4f51
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/24/2020
ms.locfileid: "76734922"
---
# <a name="extending-tracing"></a><span data-ttu-id="9eb8c-102">추적 확장</span><span class="sxs-lookup"><span data-stu-id="9eb8c-102">Extending Tracing</span></span>
<span data-ttu-id="9eb8c-103">此示例演示如何通过在客户端和服务代码中编写用户定义的活动跟踪来扩展 Windows Communication Foundation （WCF）跟踪功能。</span><span class="sxs-lookup"><span data-stu-id="9eb8c-103">This sample demonstrates how to extend the Windows Communication Foundation (WCF) tracing feature by writing user-defined activity traces in client and service code.</span></span> <span data-ttu-id="9eb8c-104">이렇게 하면 사용자가 작업의 논리 단위에 대한 추적 동작 및 그룹 추적을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9eb8c-104">This allows the user to create trace activities and group traces into logical units of work.</span></span> <span data-ttu-id="9eb8c-105">전송(같은 엔드포인트 내)과 전파(엔드포인트 사이)를 통해 동작을 상호 연결시킬 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9eb8c-105">It is also possible to correlate activities through transfers (within the same endpoint) and propagation (across endpoints).</span></span> <span data-ttu-id="9eb8c-106">이 샘플에서는 클라이언트와 서버 모두에 대해 추적이 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="9eb8c-106">In this sample, tracing is enabled for both the client and the service.</span></span> <span data-ttu-id="9eb8c-107">有关如何在客户端和服务配置文件中启用跟踪的详细信息，请参阅[跟踪和消息日志记录](../../../../docs/framework/wcf/samples/tracing-and-message-logging.md)。</span><span class="sxs-lookup"><span data-stu-id="9eb8c-107">For more information about how to enable tracing in client and service configuration files, see [Tracing and Message Logging](../../../../docs/framework/wcf/samples/tracing-and-message-logging.md).</span></span>  
  
 <span data-ttu-id="9eb8c-108">此示例基于[入门](../../../../docs/framework/wcf/samples/getting-started-sample.md)。</span><span class="sxs-lookup"><span data-stu-id="9eb8c-108">This sample is based on the [Getting Started](../../../../docs/framework/wcf/samples/getting-started-sample.md).</span></span>  
  
> [!NOTE]
> <span data-ttu-id="9eb8c-109">이 샘플의 설치 절차 및 빌드 지침은 이 항목의 끝부분에 나와 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9eb8c-109">The set-up procedure and build instructions for this sample are located at the end of this topic.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="9eb8c-110">컴퓨터에 이 샘플이 이미 설치되어 있을 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9eb8c-110">The samples may already be installed on your computer.</span></span> <span data-ttu-id="9eb8c-111">계속하기 전에 다음(기본) 디렉터리를 확인하세요.</span><span class="sxs-lookup"><span data-stu-id="9eb8c-111">Check for the following (default) directory before continuing.</span></span>  
>   
> `<InstallDrive>:\WF_WCF_Samples`  
>   
> <span data-ttu-id="9eb8c-112">如果此目录不存在，请参阅[.NET Framework 4 的 Windows Communication Foundation （wcf）和 Windows Workflow Foundation （WF）示例](https://www.microsoft.com/download/details.aspx?id=21459)以下载所有 WINDOWS COMMUNICATION FOUNDATION （wcf）和 [!INCLUDE[wf1](../../../../includes/wf1-md.md)] 示例。</span><span class="sxs-lookup"><span data-stu-id="9eb8c-112">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="9eb8c-113">이 샘플은 다음 디렉터리에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9eb8c-113">This sample is located in the following directory.</span></span>  
>   
> `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Management\ExtendingTracing`  
  
## <a name="tracing-and-activity-propagation"></a><span data-ttu-id="9eb8c-114">추적 및 동작 전파</span><span class="sxs-lookup"><span data-stu-id="9eb8c-114">Tracing and Activity Propagation</span></span>  
 <span data-ttu-id="9eb8c-115">用户定义的活动跟踪允许用户创建自己的跟踪活动，以便将跟踪分组为逻辑工作单元，通过传输和传播关联活动，并降低 WCF 跟踪的性能成本（例如，磁盘空间成本日志文件）。</span><span class="sxs-lookup"><span data-stu-id="9eb8c-115">User-defined activity tracing allows the user to create their own trace activities to group traces into logical units of work, correlate activities through transfers and propagation, and lessen the performance cost of WCF tracing (for example, the disk space cost of a log file).</span></span>  
  
### <a name="adding-custom-sources"></a><span data-ttu-id="9eb8c-116">사용자 지정 소스 추가</span><span class="sxs-lookup"><span data-stu-id="9eb8c-116">Adding Custom Sources</span></span>  
 <span data-ttu-id="9eb8c-117">사용자 정의 추적은 클라이언트와 서비스 코드 모두에 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9eb8c-117">User-defined traces can be added to both client and service code.</span></span> <span data-ttu-id="9eb8c-118">将跟踪源添加到客户端或服务配置文件允许记录这些自定义跟踪并将其显示在[服务跟踪查看器工具（svctraceviewer.exe）](../../../../docs/framework/wcf/service-trace-viewer-tool-svctraceviewer-exe.md)中。</span><span class="sxs-lookup"><span data-stu-id="9eb8c-118">Adding trace sources to the client or service configuration files allow for these custom traces to be recorded and displayed in the [Service Trace Viewer Tool (SvcTraceViewer.exe)](../../../../docs/framework/wcf/service-trace-viewer-tool-svctraceviewer-exe.md).</span></span> <span data-ttu-id="9eb8c-119">다음 코드에서는 `ServerCalculatorTraceSource`라는 사용자 정의 추적 소스를 구성 파일에 추가하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="9eb8c-119">The following code shows how to add a user-defined trace source named `ServerCalculatorTraceSource` to the configuration file.</span></span>  
  
```xml  
<system.diagnostics>  
    <sources>  
        <source name="System.ServiceModel" switchValue="Warning" propagateActivity="true">  
            <listeners>  
                <add type="System.Diagnostics.DefaultTraceListener" name="Default">  
                    <filter type="" />  
                </add>  
                <add name="xml">  
                    <filter type="" />  
                </add>  
            </listeners>  
        </source>  
        <source name="ServerCalculatorTraceSource" switchValue="Information,ActivityTracing">  
            <listeners>  
                <add type="System.Diagnostics.DefaultTraceListener" name="Default">  
                    <filter type="" />  
                </add>  
                <add name="xml">  
                    <filter type="" />  
                </add>  
            </listeners>  
        </source>  
    </sources>  
    <sharedListeners>  
       <add initializeData="C:\logs\ServerTraces.svclog" type="System.Diagnostics.XmlWriterTraceListener"  
        name="xml" traceOutputOptions="Callstack">  
            <filter type="" />  
        </add>  
    </sharedListeners>  
    <trace autoflush="true" />  
</system.diagnostics>....  
....  
```  
  
### <a name="correlating-activities"></a><span data-ttu-id="9eb8c-120">동작 상호 연결</span><span class="sxs-lookup"><span data-stu-id="9eb8c-120">Correlating Activities</span></span>  
 <span data-ttu-id="9eb8c-121">엔드포인트 사이에서 직접 동작을 상호 연결하려면 `propagateActivity` 추적 소스에서 `true` 특성을 `System.ServiceModel`로 설정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9eb8c-121">To correlate activities directly across endpoints, the `propagateActivity` attribute must be set to `true` in the `System.ServiceModel` trace source.</span></span> <span data-ttu-id="9eb8c-122">此外，若要传播跟踪而无需执行 WCF 活动，则必须关闭 "一起活动跟踪"。</span><span class="sxs-lookup"><span data-stu-id="9eb8c-122">Also, to propagate traces without going through WCF activities, ServiceModel Activity Tracing must be turned off.</span></span> <span data-ttu-id="9eb8c-123">다음 코드 예제에서 이를 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9eb8c-123">This can be seen in the following code example.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="9eb8c-124">ServiceModel 동작 추적을 끄는 것은 `switchValue` 속성으로 표시되는 추적 수준을 off로 설정하는 것과 같지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="9eb8c-124">Turning off ServiceModel Activity Tracing is not the same as having the trace level, denoted by the `switchValue` property, set to off.</span></span>  
  
```xml  
<system.diagnostics>  
    <sources>  
      <source name="System.ServiceModel" switchValue="Warning" propagateActivity="true">  
  
    ...  
  
       </source>  
    </sources>  
</system.diagnostics>  
```  
  
### <a name="lessening-performance-cost"></a><span data-ttu-id="9eb8c-125">수행 비용 절감</span><span class="sxs-lookup"><span data-stu-id="9eb8c-125">Lessening Performance Cost</span></span>  
 <span data-ttu-id="9eb8c-126">`ActivityTracing` 추적 소스에서 `System.ServiceModel`을 off로 설정하면 ServiceModel 동작 추적이 포함되지 않고 사용자 정의 동작 추적만 포함된 추적 파일이 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="9eb8c-126">Setting `ActivityTracing` to off in the `System.ServiceModel` trace source generates a trace file that contains only user-defined activity traces, without any of the ServiceModel activity traces included.</span></span> <span data-ttu-id="9eb8c-127">그러면 로그 파일의 크기가 훨씬 작아집니다.</span><span class="sxs-lookup"><span data-stu-id="9eb8c-127">This results in a log file of much smaller size.</span></span> <span data-ttu-id="9eb8c-128">但会丢失关联 WCF 处理跟踪的机会。</span><span class="sxs-lookup"><span data-stu-id="9eb8c-128">However, the opportunity to correlate WCF processing traces is lost.</span></span>  
  
##### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="9eb8c-129">샘플을 설치, 빌드 및 실행하려면</span><span class="sxs-lookup"><span data-stu-id="9eb8c-129">To set up, build, and run the sample</span></span>  
  
1. <span data-ttu-id="9eb8c-130">确保已对[Windows Communication Foundation 示例执行了一次性安装过程](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md)。</span><span class="sxs-lookup"><span data-stu-id="9eb8c-130">Ensure that you have performed the [One-Time Setup Procedure for the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span></span>  
  
2. <span data-ttu-id="9eb8c-131">C# 또는 Visual Basic .NET 버전의 솔루션을 빌드하려면 [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md)의 지침을 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="9eb8c-131">To build the C# or Visual Basic .NET edition of the solution, follow the instructions in [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span></span>  
  
3. <span data-ttu-id="9eb8c-132">若要以单机配置或跨计算机配置来运行示例，请按照[运行 Windows Communication Foundation 示例](../../../../docs/framework/wcf/samples/running-the-samples.md)中的说明进行操作。</span><span class="sxs-lookup"><span data-stu-id="9eb8c-132">To run the sample in a single- or cross-computer configuration, follow the instructions in [Running the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/running-the-samples.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9eb8c-133">另请参阅</span><span class="sxs-lookup"><span data-stu-id="9eb8c-133">See also</span></span>

- <span data-ttu-id="9eb8c-134">[AppFabric 监视示例](https://docs.microsoft.com/previous-versions/appfabric/ff383407(v=azure.10))</span><span class="sxs-lookup"><span data-stu-id="9eb8c-134">[AppFabric Monitoring Samples](https://docs.microsoft.com/previous-versions/appfabric/ff383407(v=azure.10))</span></span>
