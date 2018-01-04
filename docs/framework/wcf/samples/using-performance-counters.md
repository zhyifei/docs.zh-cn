---
title: "使用性能计数器"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 00a787af-1876-473c-a48d-f52b51e28a3f
caps.latest.revision: "31"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: ef5a499e6d940e45e0c9aab093b0a1c00bb6cc32
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="using-performance-counters"></a><span data-ttu-id="581b0-102">使用性能计数器</span><span class="sxs-lookup"><span data-stu-id="581b0-102">Using Performance Counters</span></span>
<span data-ttu-id="581b0-103">此示例演示如何访问 [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] 性能计数器以及如何创建用户定义的性能计数器。</span><span class="sxs-lookup"><span data-stu-id="581b0-103">This sample demonstrates how to access [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] performance counters and how to create user-defined performance counters.</span></span> <span data-ttu-id="581b0-104">此示例基于[入门](../../../../docs/framework/wcf/samples/getting-started-sample.md)。</span><span class="sxs-lookup"><span data-stu-id="581b0-104">This sample is based on the [Getting Started](../../../../docs/framework/wcf/samples/getting-started-sample.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="581b0-105">本主题的最后介绍了此示例的设置过程和生成说明。</span><span class="sxs-lookup"><span data-stu-id="581b0-105">The setup procedure and build instructions for this sample are located at the end of this topic.</span></span>  
  
 <span data-ttu-id="581b0-106">在此示例中，客户端调用 `ICalculator` 服务的四个方法。</span><span class="sxs-lookup"><span data-stu-id="581b0-106">In this sample, the client calls the four methods of the `ICalculator` service.</span></span> <span data-ttu-id="581b0-107">客户端一直执行该操作，直到被用户中断。</span><span class="sxs-lookup"><span data-stu-id="581b0-107">The client continues to do this until it is interrupted by the user.</span></span> <span data-ttu-id="581b0-108">该服务保持不变。</span><span class="sxs-lookup"><span data-stu-id="581b0-108">The service remains unchanged.</span></span>  
  
 <span data-ttu-id="581b0-109">性能计数器在该服务的 Web.config 文件的诊断节中启用，如下面的示例配置所示。</span><span class="sxs-lookup"><span data-stu-id="581b0-109">Performance counters are enabled in the diagnostics section of the Web.config file for the service, as shown in the following sample configuration.</span></span>  
  
```xml  
<configuration>  
  <system.serviceModel>  
    <diagnostics performanceCounters="All" />   
  </system.serviceModel>  
</configuration>  
```  
  
 <span data-ttu-id="581b0-110">也可以执行此任务使用[配置编辑器工具 (SvcConfigEditor.exe)](../../../../docs/framework/wcf/configuration-editor-tool-svcconfigeditor-exe.md)。</span><span class="sxs-lookup"><span data-stu-id="581b0-110">This task can also be done using the [Configuration Editor Tool (SvcConfigEditor.exe)](../../../../docs/framework/wcf/configuration-editor-tool-svcconfigeditor-exe.md).</span></span>  
  
 <span data-ttu-id="581b0-111">启用性能计数器时，会为该服务启用整套 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 性能计数器。</span><span class="sxs-lookup"><span data-stu-id="581b0-111">When performance counters are enabled, the entire suite of [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] performance counters is enabled for the service.</span></span> <span data-ttu-id="581b0-112">.NET Framework 自动在三个级别维护性能数据：`ServiceModelService`、`ServiceModelEndpoint` 和 `ServiceModelOperation`。</span><span class="sxs-lookup"><span data-stu-id="581b0-112">The .NET Framework automatically maintains performance data at three levels: `ServiceModelService`, `ServiceModelEndpoint` and `ServiceModelOperation`.</span></span> <span data-ttu-id="581b0-113">其中每个级别都有“Calls”（调用）、“Calls per Second”（每秒调用次数）和“Security Calls Not Authorized”（未授权的安全调用次数）等性能计数器。</span><span class="sxs-lookup"><span data-stu-id="581b0-113">Each of these levels has performance counters such as "Calls", "Calls per Second", and "Security Calls Not Authorized".</span></span>  
  
### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="581b0-114">设置、生成和运行示例</span><span class="sxs-lookup"><span data-stu-id="581b0-114">To set up, build, and run the sample</span></span>  
  
1.  <span data-ttu-id="581b0-115">确保已执行[的 Windows Communication Foundation 示例的一次性安装过程](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md)。</span><span class="sxs-lookup"><span data-stu-id="581b0-115">Ensure that you have performed the [One-Time Setup Procedure for the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span></span>  
  
2.  <span data-ttu-id="581b0-116">若要生成 C# 或 Visual Basic .NET 版本的解决方案，请按照 [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md)中的说明进行操作。</span><span class="sxs-lookup"><span data-stu-id="581b0-116">To build the C# or Visual Basic .NET edition of the solution, follow the instructions in [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span></span>  
  
3.  <span data-ttu-id="581b0-117">若要在单或跨计算机配置上运行示例，请按照中的说明[运行 Windows Communication Foundation 示例](../../../../docs/framework/wcf/samples/running-the-samples.md)。</span><span class="sxs-lookup"><span data-stu-id="581b0-117">To run the sample in a single- or cross-computer configuration, follow the instructions in [Running the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/running-the-samples.md).</span></span>  
  
### <a name="to-view-performance-data"></a><span data-ttu-id="581b0-118">查看性能数据</span><span class="sxs-lookup"><span data-stu-id="581b0-118">To view performance data</span></span>  
  
1.  <span data-ttu-id="581b0-119">通过单击启动性能监视器工具**启动**，**运行...**，输入`perfmon`单击**确定，**或者从控制面板中，选择**管理工具**双击**性能**。</span><span class="sxs-lookup"><span data-stu-id="581b0-119">Start the Performance Monitor Tool by clicking **Start**, **Run…**, enter `perfmon` and click **OK,** or from Control Panel, select **Administrative Tools** and double-click **Performance**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="581b0-120">在示例代码运行之前无法添加计数器。</span><span class="sxs-lookup"><span data-stu-id="581b0-120">You cannot add counters until the sample code is running.</span></span>  
  
2.  <span data-ttu-id="581b0-121">选择列出的性能计数器并按 Delete 键以移除它们。</span><span class="sxs-lookup"><span data-stu-id="581b0-121">Remove the performance counters that are listed by selecting them and pressing the Delete key.</span></span>  
  
3.  <span data-ttu-id="581b0-122">添加[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]通过右键单击关系图窗格中选择的计数器**添加计数器**。</span><span class="sxs-lookup"><span data-stu-id="581b0-122">Add [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] counters by right-clicking the graph pane and selecting **Add Counters**.</span></span> <span data-ttu-id="581b0-123">在**添加计数器**对话框中，选择**ServiceModelOperation 3.0.0.0、 ServiceModelEndpoint 3.0.0.0 或 ServiceModelService 3.0.0.0**下拉列表框中的性能对象。</span><span class="sxs-lookup"><span data-stu-id="581b0-123">In the **Add Counters** dialog box, select **ServiceModelOperation 3.0.0.0, ServiceModelEndpoint 3.0.0.0, or ServiceModelService 3.0.0.0** in the Performance object drop down list box.</span></span> <span data-ttu-id="581b0-124">从列表中选择要查看的计数器。</span><span class="sxs-lookup"><span data-stu-id="581b0-124">Select the counters you want to view from the list.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="581b0-125">如果计算机中没有正在运行的 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 服务，则服务没有 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 性能计数器。</span><span class="sxs-lookup"><span data-stu-id="581b0-125">There are no [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] performance counters for a service if there are no [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] services running on the computer.</span></span>  
  
### <a name="to-use-the-configuration-editor-to-enable-counters"></a><span data-ttu-id="581b0-126">使用配置编辑器来启用计数器</span><span class="sxs-lookup"><span data-stu-id="581b0-126">To use the Configuration Editor to enable counters</span></span>  
  
1.  <span data-ttu-id="581b0-127">打开 SvcConfigEditor.exe 的一个实例。</span><span class="sxs-lookup"><span data-stu-id="581b0-127">Open an instance of the SvcConfigEditor.exe.</span></span>  
  
2.  <span data-ttu-id="581b0-128">在文件菜单中，单击**打开**，然后单击**配置文件...**.</span><span class="sxs-lookup"><span data-stu-id="581b0-128">On the File menu, click **Open** and then click **Config file…**.</span></span>  
  
3.  <span data-ttu-id="581b0-129">导航到示例应用程序的服务文件夹并打开 Web.config 文件。</span><span class="sxs-lookup"><span data-stu-id="581b0-129">Navigate to the sample application's service folder and open the Web.config file.</span></span>  
  
4.  <span data-ttu-id="581b0-130">单击**诊断**上配置树。</span><span class="sxs-lookup"><span data-stu-id="581b0-130">Click **Diagnostics** on the Configuration tree.</span></span>  
  
5.  <span data-ttu-id="581b0-131">切换**性能计数器**中**诊断**窗口以显示 'All'。</span><span class="sxs-lookup"><span data-stu-id="581b0-131">Toggle **Performance Counter** in the **Diagnostics** window to show 'All'.</span></span>  
  
6.  <span data-ttu-id="581b0-132">保存该配置文件并退出编辑器。</span><span class="sxs-lookup"><span data-stu-id="581b0-132">Save the configuration file and exit the editor.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="581b0-133">您的计算机上可能已安装这些示例。</span><span class="sxs-lookup"><span data-stu-id="581b0-133">The samples may already be installed on your computer.</span></span> <span data-ttu-id="581b0-134">在继续操作之前，请先检查以下（默认）目录：</span><span class="sxs-lookup"><span data-stu-id="581b0-134">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="581b0-135">如果此目录不存在，请访问 [针对 .NET Framework 4 的 Windows Communication Foundation (WCF) 和 Windows Workflow Foundation (WF) 示例](http://go.microsoft.com/fwlink/?LinkId=150780) 以下载所有 [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] 和 [!INCLUDE[wf1](../../../../includes/wf1-md.md)] 示例。</span><span class="sxs-lookup"><span data-stu-id="581b0-135">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="581b0-136">此示例位于以下目录：</span><span class="sxs-lookup"><span data-stu-id="581b0-136">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Management\PerfCounters`  
  
## <a name="see-also"></a><span data-ttu-id="581b0-137">请参阅</span><span class="sxs-lookup"><span data-stu-id="581b0-137">See Also</span></span>  
 [<span data-ttu-id="581b0-138">AppFabric 监视示例</span><span class="sxs-lookup"><span data-stu-id="581b0-138">AppFabric Monitoring Samples</span></span>](http://go.microsoft.com/fwlink/?LinkId=193959)
