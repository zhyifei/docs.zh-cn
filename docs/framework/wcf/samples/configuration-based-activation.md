---
title: 基于配置的激活
ms.date: 03/30/2017
ms.assetid: 21bb762e-c43e-4b0c-887b-5e434d665838
ms.openlocfilehash: 3ac4edd2a51e4ed8a5c0b7e73d7d1afa31334c33
ms.sourcegitcommit: 15109844229ade1c6449f48f3834db1b26907824
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2018
ms.locfileid: "33809909"
---
# <a name="configuration-based-activation"></a><span data-ttu-id="3266e-102">基于配置的激活</span><span class="sxs-lookup"><span data-stu-id="3266e-102">Configuration-Based Activation</span></span>
<span data-ttu-id="3266e-103">此示例演示如何激活 Windows Communication Foundation (WCF) 服务，而无需.svc 文件。</span><span class="sxs-lookup"><span data-stu-id="3266e-103">This sample demonstrates how to activate Windows Communication Foundation (WCF) services without requiring a .svc file.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="3266e-104">您的计算机上可能已安装这些示例。</span><span class="sxs-lookup"><span data-stu-id="3266e-104">The samples may already be installed on your computer.</span></span> <span data-ttu-id="3266e-105">在继续操作之前，请先检查以下（默认）目录：</span><span class="sxs-lookup"><span data-stu-id="3266e-105">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="3266e-106">如果此目录不存在，请转到[Windows Communication Foundation (WCF) 和针对.NET Framework 4 的 Windows Workflow Foundation (WF) 示例](http://go.microsoft.com/fwlink/?LinkId=150780)下载所有 Windows Communication Foundation (WCF) 和[!INCLUDE[wf1](../../../../includes/wf1-md.md)]示例。</span><span class="sxs-lookup"><span data-stu-id="3266e-106">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="3266e-107">此示例位于以下目录：</span><span class="sxs-lookup"><span data-stu-id="3266e-107">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Services\Hosting\ConfigBasedActivation`  
  
## <a name="sample-details"></a><span data-ttu-id="3266e-108">示例详细信息</span><span class="sxs-lookup"><span data-stu-id="3266e-108">Sample Details</span></span>  
 <span data-ttu-id="3266e-109">在此示例中，客户端 WCF 测试客户端，并且服务承载在 IIS 中。</span><span class="sxs-lookup"><span data-stu-id="3266e-109">In this sample, the client is the WCF test client and the service is hosted in IIS.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="3266e-110">本主题的最后提供了此示例的设置和生成说明。</span><span class="sxs-lookup"><span data-stu-id="3266e-110">The setup and build instructions for this sample are located at the end of this topic.</span></span>  
  
### <a name="activation-of-services-without-requiring-a-svc-file"></a><span data-ttu-id="3266e-111">在不需要 .svc 文件的情况下激活服务</span><span class="sxs-lookup"><span data-stu-id="3266e-111">Activation of services without requiring a .svc file</span></span>  
 <span data-ttu-id="3266e-112">在 [!INCLUDE[netfx35_short](../../../../includes/netfx35-short-md.md)] 中，激活服务需要一个 .svc 文件。</span><span class="sxs-lookup"><span data-stu-id="3266e-112">In [!INCLUDE[netfx35_short](../../../../includes/netfx35-short-md.md)], a .svc file was required for activating a service.</span></span> <span data-ttu-id="3266e-113">这会导致额外的管理开销，因为需要与该应用程序一起部署和维护一个附加文件。</span><span class="sxs-lookup"><span data-stu-id="3266e-113">This caused additional management overhead, because an additional file was required to be deployed and maintained along with the application.</span></span> <span data-ttu-id="3266e-114">[!INCLUDE[netfx40_long](../../../../includes/netfx40-long-md.md)] 发布后，可使用应用程序配置文件来配置激活组件。</span><span class="sxs-lookup"><span data-stu-id="3266e-114">With the release of [!INCLUDE[netfx40_long](../../../../includes/netfx40-long-md.md)], the activation components can be configured using the application configuration file.</span></span>  
  
 [!INCLUDE[netfx40_short](../../../../includes/netfx40-short-md.md)]<span data-ttu-id="3266e-115"> 在应用程序配置文件的 <xref:System.ServiceModel.Configuration.ServiceActivationElement> 中引入了一个新的配置元素 (<xref:System.ServiceModel.Configuration.ServiceHostingEnvironmentSection>)。</span><span class="sxs-lookup"><span data-stu-id="3266e-115"> introduces a new configuration element (<xref:System.ServiceModel.Configuration.ServiceActivationElement>), in the <xref:System.ServiceModel.Configuration.ServiceHostingEnvironmentSection> of the application configuration file.</span></span> <span data-ttu-id="3266e-116"><xref:System.ServiceModel.Configuration.ServiceHostingEnvironmentSection> 集合接受要激活的服务集合，如下面的代码示例所示。</span><span class="sxs-lookup"><span data-stu-id="3266e-116">The <xref:System.ServiceModel.Configuration.ServiceHostingEnvironmentSection> collection accepts a collection of services to activate, as shown in the following code example.</span></span>  
  
```xml  
<serviceActivations>  
   <add relativeAddress="Calculator.svc" service="Microsoft.ServiceModel.Samples.CalculatorService" />  
  
<serviceActivations>  
```  
  
 <span data-ttu-id="3266e-117">观察发现，该配置看上去非常类似于 .svc 文件的配置。</span><span class="sxs-lookup"><span data-stu-id="3266e-117">The observation to make is the configuration looks very similar to the configuration of .svc files.</span></span> <span data-ttu-id="3266e-118">引入的一个附加特性是 `relativeAddress`，它可以提供服务的地址。</span><span class="sxs-lookup"><span data-stu-id="3266e-118">An additional attribute that is introduced is the `relativeAddress` that provides the address of the service.</span></span> <span data-ttu-id="3266e-119">相对地址也是该服务的虚拟路径。</span><span class="sxs-lookup"><span data-stu-id="3266e-119">The relative address is also the virtual path for the service.</span></span> <span data-ttu-id="3266e-120">主机从 `virtualPath` 位置检索该文件的 Web.config 文件（如果存在），否则主机以递归方式搜索其父文件夹。</span><span class="sxs-lookup"><span data-stu-id="3266e-120">The host retrieves the Web.config file of the file from the `virtualPath` location, if present; otherwise the host searches its parent folder recursively.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="3266e-121">此示例需要在 IIS 中承载才能正常工作。</span><span class="sxs-lookup"><span data-stu-id="3266e-121">This sample requires hosting in IIS to function.</span></span>  
  
#### <a name="to-use-this-sample"></a><span data-ttu-id="3266e-122">使用此示例</span><span class="sxs-lookup"><span data-stu-id="3266e-122">To use this sample</span></span>  
  
1.  <span data-ttu-id="3266e-123">使用 [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)] 打开 Service.csproj 文件。</span><span class="sxs-lookup"><span data-stu-id="3266e-123">Using [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)], open the Service.csproj file.</span></span>  
  
2.  <span data-ttu-id="3266e-124">要生成解决方案，按 Ctrl+Shift+B。</span><span class="sxs-lookup"><span data-stu-id="3266e-124">To build the solution, press CTRL+SHIFT+B.</span></span>  
  
3.  <span data-ttu-id="3266e-125">通过运行 WCFTestClient.exe 测试该服务。</span><span class="sxs-lookup"><span data-stu-id="3266e-125">Test the service by running WCFTestClient.exe.</span></span>  
  
4.  <span data-ttu-id="3266e-126">使用 [!INCLUDE[fileExplorer](../../../../includes/fileexplorer-md.md)]，导航到 %SystemDrive%\Program Files\Microsoft Visual Studio 10.0\Common7\IDE 文件夹。</span><span class="sxs-lookup"><span data-stu-id="3266e-126">Using [!INCLUDE[fileExplorer](../../../../includes/fileexplorer-md.md)], navigate to the %SystemDrive%\Program Files\Microsoft Visual Studio 10.0\Common7\IDE folder.</span></span>  
  
5.  <span data-ttu-id="3266e-127">运行 WcfTestClient.exe。</span><span class="sxs-lookup"><span data-stu-id="3266e-127">Run WcfTestClient.exe.</span></span>  
  
6.  <span data-ttu-id="3266e-128">设置该服务的 MEX 地址。</span><span class="sxs-lookup"><span data-stu-id="3266e-128">Set the MEX address of the service.</span></span>  
  
7.  <span data-ttu-id="3266e-129">按 Ctrl+Shift+A 设置服务地址。</span><span class="sxs-lookup"><span data-stu-id="3266e-129">Press CTRL+SHIFT+A to set the service address.</span></span>  
  
8.  <span data-ttu-id="3266e-130">将该地址设置http://localhost/ServiceModelSamples/Calculator.svc。</span><span class="sxs-lookup"><span data-stu-id="3266e-130">Set the address to http://localhost/ServiceModelSamples/Calculator.svc.</span></span>  
  
9. <span data-ttu-id="3266e-131">执行 `Add` 操作。</span><span class="sxs-lookup"><span data-stu-id="3266e-131">Perform the `Add` operation.</span></span> <span data-ttu-id="3266e-132">将 `n1` 参数上的值设置为 10，并将 `n2` 参数上的值设置为 15。</span><span class="sxs-lookup"><span data-stu-id="3266e-132">Set value on the `n1` parameter to 10 and set value on the `n2` parameter to 15.</span></span>  
  
10. <span data-ttu-id="3266e-133">按**调用**。</span><span class="sxs-lookup"><span data-stu-id="3266e-133">Press **Invoke**.</span></span>  
  
     <span data-ttu-id="3266e-134">预期结果为 25。</span><span class="sxs-lookup"><span data-stu-id="3266e-134">The expected result is 25.</span></span>  
  
#### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="3266e-135">设置、生成和运行示例</span><span class="sxs-lookup"><span data-stu-id="3266e-135">To set up, build, and run the sample</span></span>  
  
1.  <span data-ttu-id="3266e-136">请确保已执行[的 Windows Communication Foundation 示例的一次性安装过程](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md)。</span><span class="sxs-lookup"><span data-stu-id="3266e-136">Be sure you have performed the [One-Time Setup Procedure for the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span></span>  
  
2.  <span data-ttu-id="3266e-137">若要生成 C# 或 Visual Basic .NET 版本的解决方案，请按照 [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md)中的说明进行操作。</span><span class="sxs-lookup"><span data-stu-id="3266e-137">To build the C# or Visual Basic .NET edition of the solution, follow the instructions in [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span></span>  
  
3.  <span data-ttu-id="3266e-138">生成解决方案后，运行 Setup.bat 以在 IIS 中设置 ServiceModelSamples 应用程序。</span><span class="sxs-lookup"><span data-stu-id="3266e-138">After the solution has been built, run Setup.bat to set up the ServiceModelSamples Application in IIS.</span></span> <span data-ttu-id="3266e-139">现在，ServiceModelSamples 目录应显示为 IIS 应用程序。</span><span class="sxs-lookup"><span data-stu-id="3266e-139">The ServiceModelSamples directory should now appear as an IIS Application.</span></span>  
  
4.  <span data-ttu-id="3266e-140">若要在单或跨计算机配置上运行示例，请按照中的说明[运行 Windows Communication Foundation 示例](../../../../docs/framework/wcf/samples/running-the-samples.md)。</span><span class="sxs-lookup"><span data-stu-id="3266e-140">To run the sample in a single- or cross-computer configuration, follow the instructions in [Running the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/running-the-samples.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3266e-141">请参阅</span><span class="sxs-lookup"><span data-stu-id="3266e-141">See Also</span></span>  
 [<span data-ttu-id="3266e-142">AppFabric 承载和持久性示例</span><span class="sxs-lookup"><span data-stu-id="3266e-142">AppFabric Hosting and Persistence Samples</span></span>](http://go.microsoft.com/fwlink/?LinkId=193961)
