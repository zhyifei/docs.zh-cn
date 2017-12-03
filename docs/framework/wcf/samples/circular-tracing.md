---
title: "循环跟踪"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 5ff139f9-8806-47bc-8f33-47fe6c436b92
caps.latest.revision: "21"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 21a455c0fcb7a6b4164da6f7fdc7efaa007273ae
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/02/2017
---
# <a name="circular-tracing"></a><span data-ttu-id="ec2aa-102">循环跟踪</span><span class="sxs-lookup"><span data-stu-id="ec2aa-102">Circular Tracing</span></span>
<span data-ttu-id="ec2aa-103">此示例演示如何实现循环缓冲区跟踪侦听器。</span><span class="sxs-lookup"><span data-stu-id="ec2aa-103">This sample demonstrates the implementation of a circular buffer trace listener.</span></span> <span data-ttu-id="ec2aa-104">生产服务的一个常见方案是，拥有可以长时间使用的服务，并在较低级别启用跟踪日志记录。</span><span class="sxs-lookup"><span data-stu-id="ec2aa-104">A common scenario for production services is to have services that are available for long periods of time and to have trace logging enabled at a low level.</span></span> <span data-ttu-id="ec2aa-105">这些服务占用大量磁盘空间。</span><span class="sxs-lookup"><span data-stu-id="ec2aa-105">These services consume a lot of disk space.</span></span> <span data-ttu-id="ec2aa-106">在对某个服务进行疑难解答时，跟踪日志中的最新数据与解决问题相关。</span><span class="sxs-lookup"><span data-stu-id="ec2aa-106">When troubleshooting a service, the most recent data in the trace log is relevant to solving a problem.</span></span> <span data-ttu-id="ec2aa-107">此示例演示如何实现一个循环缓冲区跟踪侦听器，在该侦听器中，磁盘上仅保留最新的跟踪数据，最多可以保存可配置的数据量。</span><span class="sxs-lookup"><span data-stu-id="ec2aa-107">This sample demonstrates an implementation of a circular buffer trace listener in which only the most recent traces are kept on disk up to a configurable amount of data.</span></span> <span data-ttu-id="ec2aa-108">此示例基于[入门](../../../../docs/framework/wcf/samples/getting-started-sample.md)和包括自定义跟踪侦听器。</span><span class="sxs-lookup"><span data-stu-id="ec2aa-108">This sample is based on the [Getting Started](../../../../docs/framework/wcf/samples/getting-started-sample.md) and includes a custom tracing listener.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="ec2aa-109">本主题的最后介绍了此示例的设置过程和生成说明。</span><span class="sxs-lookup"><span data-stu-id="ec2aa-109">The setup procedure and build instructions for this sample are located at the end of this topic.</span></span>  
  
 <span data-ttu-id="ec2aa-110">此示例假定你熟悉[跟踪和消息日志记录](../../../../docs/framework/wcf/samples/tracing-and-message-logging.md)具有读取为提供的文档和示例[跟踪和消息日志记录](../../../../docs/framework/wcf/samples/tracing-and-message-logging.md)示例。</span><span class="sxs-lookup"><span data-stu-id="ec2aa-110">This sample assumes that you are familiar with the [Tracing and Message Logging](../../../../docs/framework/wcf/samples/tracing-and-message-logging.md) sample and have read the documentation provided for the [Tracing and Message Logging](../../../../docs/framework/wcf/samples/tracing-and-message-logging.md) sample.</span></span>  
  
## <a name="circular-buffer-trace-listener"></a><span data-ttu-id="ec2aa-111">循环缓冲区跟踪侦听器</span><span class="sxs-lookup"><span data-stu-id="ec2aa-111">Circular Buffer Trace Listener</span></span>  
 <span data-ttu-id="ec2aa-112">实现循环缓冲区跟踪侦听器所涉及的概念是：拥有两个文件，每个文件最多可以存储所需跟踪日志总数据量的一半。</span><span class="sxs-lookup"><span data-stu-id="ec2aa-112">The concept behind the implementation of the Circular Buffer Trace Listener is to have two files that can each store up to half of the total desired trace log data.</span></span> <span data-ttu-id="ec2aa-113">侦听器创建一个文件并写入该文件，直到它达到其限制（即数据大小的一半），之后侦听器将切换到第二个文件。</span><span class="sxs-lookup"><span data-stu-id="ec2aa-113">The listener creates one file and writes to that file until it reaches the limit of half of the data size, at which point it switches to a second file.</span></span> <span data-ttu-id="ec2aa-114">当侦听器达到第二个文件的限制时，它会用新跟踪数据覆盖第一个文件。</span><span class="sxs-lookup"><span data-stu-id="ec2aa-114">When the listener reaches the limit for the second file - it overwrites the first file with new traces.</span></span>  
  
 <span data-ttu-id="ec2aa-115">此侦听器派生自`XmlWriteTraceListener`，并允许日志以查看与[服务跟踪查看器工具 (SvcTraceViewer.exe)](../../../../docs/framework/wcf/service-trace-viewer-tool-svctraceviewer-exe.md)。</span><span class="sxs-lookup"><span data-stu-id="ec2aa-115">This listener derives from the `XmlWriteTraceListener` and allows the logs to be viewed with the [Service Trace Viewer Tool (SvcTraceViewer.exe)](../../../../docs/framework/wcf/service-trace-viewer-tool-svctraceviewer-exe.md).</span></span> <span data-ttu-id="ec2aa-116">在尝试查看日志时，可以通过在服务跟踪查看器工具中同时打开这两个日志文件来方便地进行重新合并。</span><span class="sxs-lookup"><span data-stu-id="ec2aa-116">When attempting to view the logs, the two log files can be easily recombined by opening both of the log files at the same time in the Service Trace Viewer tool.</span></span> <span data-ttu-id="ec2aa-117">服务跟踪查看器工具会自动负责对跟踪数据进行排序，以便它们按照正确的顺序显示。</span><span class="sxs-lookup"><span data-stu-id="ec2aa-117">The Service Trace Viewer tool automatically takes care of sorting the traces so that they appear in the correct order.</span></span>  
  
## <a name="configuration"></a><span data-ttu-id="ec2aa-118">配置</span><span class="sxs-lookup"><span data-stu-id="ec2aa-118">Configuration</span></span>  
 <span data-ttu-id="ec2aa-119">通过为侦听器和源元素添加下面的代码可以将服务配置为使用循环缓冲区跟踪侦听器。</span><span class="sxs-lookup"><span data-stu-id="ec2aa-119">A service can be configured to use the Circular Buffer Trace Listener by adding the following code for a listener and source elements.</span></span> <span data-ttu-id="ec2aa-120">最大文件大小是通过在循环跟踪侦听器的配置中设置 `maxFileSizeKB` 属性来指定的。</span><span class="sxs-lookup"><span data-stu-id="ec2aa-120">The max file size is specified by setting the `maxFileSizeKB` attribute in the circular trace listener's configuration.</span></span> <span data-ttu-id="ec2aa-121">下面的代码对此进行了演示。</span><span class="sxs-lookup"><span data-stu-id="ec2aa-121">This is demonstrated in the following code.</span></span>  
  
```xml  
<system.diagnostics>  
  <sources>  
    <source name="System.ServiceModel" switchValue="Information,ActivityTracing" propagateActivity="true">  
      <listeners>  
        <add name="CircularTraceListener" />  
      </listeners>  
    </source>  
  </sources>  
  <sharedListeners>  
    <add name="CircularTraceListener" type="Microsoft. Samples.ServiceModel.CircularTraceListener,CircularTraceListener"   
         initializeData="c:\logs\CircularTracing-service.svclog" maxFileSizeKB="100" />  
  </sharedListeners>  
  <trace autoflush="true" />  
</system.diagnostics>  
```  
  
#### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="ec2aa-122">设置、生成和运行示例</span><span class="sxs-lookup"><span data-stu-id="ec2aa-122">To set up, build, and run the sample</span></span>  
  
1.  <span data-ttu-id="ec2aa-123">请确保已执行[的 Windows Communication Foundation 示例的一次性安装过程](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md)。</span><span class="sxs-lookup"><span data-stu-id="ec2aa-123">Be sure you have performed the [One-Time Setup Procedure for the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span></span>  
  
2.  <span data-ttu-id="ec2aa-124">若要生成 C# 或 Visual Basic .NET 版本的解决方案，请按照 [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md)中的说明进行操作。</span><span class="sxs-lookup"><span data-stu-id="ec2aa-124">To build the C# or Visual Basic .NET edition of the solution, follow the instructions in [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span></span>  
  
3.  <span data-ttu-id="ec2aa-125">若要在单或跨计算机配置上运行示例，请按照中的说明[运行 Windows Communication Foundation 示例](../../../../docs/framework/wcf/samples/running-the-samples.md)。</span><span class="sxs-lookup"><span data-stu-id="ec2aa-125">To run the sample in a single- or cross-computer configuration, follow the instructions in [Running the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/running-the-samples.md).</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="ec2aa-126">您的计算机上可能已安装这些示例。</span><span class="sxs-lookup"><span data-stu-id="ec2aa-126">The samples may already be installed on your computer.</span></span> <span data-ttu-id="ec2aa-127">在继续操作之前，请先检查以下（默认）目录：</span><span class="sxs-lookup"><span data-stu-id="ec2aa-127">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="ec2aa-128">如果此目录不存在，请访问 [针对 .NET Framework 4 的 Windows Communication Foundation (WCF) 和 Windows Workflow Foundation (WF) 示例](http://go.microsoft.com/fwlink/?LinkId=150780) 以下载所有 [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] 和 [!INCLUDE[wf1](../../../../includes/wf1-md.md)] 示例。</span><span class="sxs-lookup"><span data-stu-id="ec2aa-128">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="ec2aa-129">此示例位于以下目录：</span><span class="sxs-lookup"><span data-stu-id="ec2aa-129">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Management\CircularTracing`  
  
## <a name="see-also"></a><span data-ttu-id="ec2aa-130">另请参阅</span><span class="sxs-lookup"><span data-stu-id="ec2aa-130">See Also</span></span>  
 [<span data-ttu-id="ec2aa-131">AppFabric 监视示例</span><span class="sxs-lookup"><span data-stu-id="ec2aa-131">AppFabric Monitoring Samples</span></span>](http://go.microsoft.com/fwlink/?LinkId=193959)
