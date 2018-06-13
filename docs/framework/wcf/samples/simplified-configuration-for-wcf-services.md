---
title: WCF 服务的简化配置
ms.date: 03/30/2017
ms.assetid: 1e39ec25-18a3-4fdc-b6a3-9dfafbd60112
ms.openlocfilehash: 80e2ac83ec0e07176d6afe6d34c63fb4d8e836d1
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33502259"
---
# <a name="simplified-configuration-for-wcf-services"></a><span data-ttu-id="489f1-102">WCF 服务的简化配置</span><span class="sxs-lookup"><span data-stu-id="489f1-102">Simplified Configuration for WCF Services</span></span>
<span data-ttu-id="489f1-103">此示例演示如何实现和配置典型的服务和客户端使用 Windows Communication Foundation (WCF)。</span><span class="sxs-lookup"><span data-stu-id="489f1-103">This sample demonstrates how to implement and configure a typical service and client using Windows Communication Foundation (WCF).</span></span> <span data-ttu-id="489f1-104">此示例是所有其他基本技术示例的基础。</span><span class="sxs-lookup"><span data-stu-id="489f1-104">This sample is the basis for all other basic technology samples.</span></span>  
  
 <span data-ttu-id="489f1-105">此服务公开一个终结点与服务进行通信，它使用 [!INCLUDE[netfx40_long](../../../../includes/netfx40-long-md.md)] 中的简化配置。</span><span class="sxs-lookup"><span data-stu-id="489f1-105">This service, which exposes an endpoint for communicating with the service, uses the simplified configuration in [!INCLUDE[netfx40_long](../../../../includes/netfx40-long-md.md)].</span></span> <span data-ttu-id="489f1-106">在 [!INCLUDE[netfx40_short](../../../../includes/netfx40-short-md.md)] 之前，通常在配置文件 (Web.config) 中定义终结点，如以下示例配置代码所示。</span><span class="sxs-lookup"><span data-stu-id="489f1-106">Prior to [!INCLUDE[netfx40_short](../../../../includes/netfx40-short-md.md)], the endpoint is typically defined in a configuration file (Web.config), as shown in the following example configuration code.</span></span>  
  
```xml  
<?xml version="1.0" encoding="utf-8" ?>  
<!-- Copyright ©) Microsoft Corporation.  All Rights Reserved. -->  
<configuration>  
  <system.serviceModel>  
    <behaviors>  
      <serviceBehaviors>  
        <behavior name="CalculatorServiceBehavior">  
          <serviceMetadata httpGetEnabled="True"/>  
        </behavior>  
      </serviceBehaviors>  
    </behaviors>  
    <services>  
      <service name="Microsoft.Samples.GettingStarted.CalculatorService"  
               behaviorConfiguration="CalculatorServiceBehavior">  
        <endpoint address="" binding="basicHttpBinding" contract="ICalculator"/>  
        <endpoint address="mex" binding="mexHttpBinding" contract="IMetadataExchange"/>  
      </service>  
    </services>  
  </system.serviceModel>  
</configuration>  
```  
  
 <span data-ttu-id="489f1-107">在 [!INCLUDE[netfx40_short](../../../../includes/netfx40-short-md.md)] 中，`<service>` 元素是可选的。</span><span class="sxs-lookup"><span data-stu-id="489f1-107">In [!INCLUDE[netfx40_short](../../../../includes/netfx40-short-md.md)], the `<service>` element is optional.</span></span> <span data-ttu-id="489f1-108">当一个服务未定义任何终结点时，会将已实现的每个基址和协定的终结点添加到该服务。</span><span class="sxs-lookup"><span data-stu-id="489f1-108">When a service does not define any endpoints, an endpoint for each base address and contract implemented are added to the service.</span></span> <span data-ttu-id="489f1-109">基址将追加到协定名称后面以确定终结点，该地址方案将确定绑定。</span><span class="sxs-lookup"><span data-stu-id="489f1-109">The base address is appended to the contract name to determine the endpoint and the binding is determined by the address scheme.</span></span> <span data-ttu-id="489f1-110">以下代码示例演示一个简化的配置文件。</span><span class="sxs-lookup"><span data-stu-id="489f1-110">The following code example demonstrates a simplified configuration file.</span></span> <span data-ttu-id="489f1-111">经过配置之后，可以在访问服务http://localhost/servicemodelsamples/service.svc通过同一台计算机上的客户端。</span><span class="sxs-lookup"><span data-stu-id="489f1-111">As configured, the service can be accessed at http://localhost/servicemodelsamples/service.svc by a client on the same computer.</span></span> <span data-ttu-id="489f1-112">若要使远程计算机上的客户端能够访问该服务，必须指定完全限定域名，而不是本地主机。</span><span class="sxs-lookup"><span data-stu-id="489f1-112">For clients on remote computers to access the service, a fully-qualified domain name must be specified instead of localhost.</span></span> <span data-ttu-id="489f1-113">默认情况下，该服务不公开元数据。</span><span class="sxs-lookup"><span data-stu-id="489f1-113">The service does not expose metadata by default.</span></span> <span data-ttu-id="489f1-114">因此，该服务将打开 <xref:System.ServiceModel.Description.ServiceMetadataBehavior> 行为。</span><span class="sxs-lookup"><span data-stu-id="489f1-114">As such, the service turns on the <xref:System.ServiceModel.Description.ServiceMetadataBehavior> behavior.</span></span>  
  
```xml  
<?xml version="1.0" encoding="utf-8" ?>  
<!-- Copyright © Microsoft Corporation.  All Rights Reserved. -->  
<configuration>  
  <system.serviceModel>  
    <behaviors>  
      <serviceBehaviors>  
        <behavior name="">  
          <serviceMetadata httpGetEnabled="True"/>  
        </behavior>  
      </serviceBehaviors>  
    </behaviors>  
  </system.serviceModel>  
</configuration>  
```  
  
### <a name="to-use-this-sample"></a><span data-ttu-id="489f1-115">使用此示例</span><span class="sxs-lookup"><span data-stu-id="489f1-115">To use this sample</span></span>  
  
1.  <span data-ttu-id="489f1-116">确保已执行[的 Windows Communication Foundation 示例的一次性安装过程](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md)。</span><span class="sxs-lookup"><span data-stu-id="489f1-116">Ensure that you have performed the [One-Time Setup Procedure for the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span></span>  
  
2.  <span data-ttu-id="489f1-117">若要生成解决方案，请按照中的说明[生成 Windows Communication Foundation 示例](../../../../docs/framework/wcf/samples/building-the-samples.md)。</span><span class="sxs-lookup"><span data-stu-id="489f1-117">To build the solution, follow the instructions in [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span></span>  
  
3.  <span data-ttu-id="489f1-118">按照以下步骤运行示例：</span><span class="sxs-lookup"><span data-stu-id="489f1-118">Run the sample by following these steps:</span></span>  
  
    1.  <span data-ttu-id="489f1-119">右键单击**服务**项目，然后选择**设为启动项目**，然后按**Ctrl + F5**。</span><span class="sxs-lookup"><span data-stu-id="489f1-119">Right click the **Service** project and select **Set as StartUp project**, then press **Ctrl+F5**.</span></span>  
  
    2.  <span data-ttu-id="489f1-120">等待确认服务已准备好并且正在运行的控制台输出。</span><span class="sxs-lookup"><span data-stu-id="489f1-120">Wait for the console output confirming that the service is up and running.</span></span>  
  
    3.  <span data-ttu-id="489f1-121">右键单击**客户端**项目，然后选择**设为启动项目**，然后按**Ctrl + F5**。</span><span class="sxs-lookup"><span data-stu-id="489f1-121">Right click the **Client** project and select **Set as StartUp project**, then press **Ctrl+F5**.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="489f1-122">您的计算机上可能已安装这些示例。</span><span class="sxs-lookup"><span data-stu-id="489f1-122">The samples may already be installed on your computer.</span></span> <span data-ttu-id="489f1-123">在继续操作之前，请先检查以下（默认）目录：</span><span class="sxs-lookup"><span data-stu-id="489f1-123">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="489f1-124">如果此目录不存在，请转到[Windows Communication Foundation (WCF) 和针对.NET Framework 4 的 Windows Workflow Foundation (WF) 示例](http://go.microsoft.com/fwlink/?LinkId=150780)下载所有 Windows Communication Foundation (WCF) 和[!INCLUDE[wf1](../../../../includes/wf1-md.md)]示例。</span><span class="sxs-lookup"><span data-stu-id="489f1-124">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="489f1-125">此示例位于以下目录：</span><span class="sxs-lookup"><span data-stu-id="489f1-125">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Services\ConfigSimplificationIn40`  
  
## <a name="see-also"></a><span data-ttu-id="489f1-126">请参阅</span><span class="sxs-lookup"><span data-stu-id="489f1-126">See Also</span></span>  
 [<span data-ttu-id="489f1-127">AppFabric 管理示例</span><span class="sxs-lookup"><span data-stu-id="489f1-127">AppFabric Management Samples</span></span>](http://go.microsoft.com/fwlink/?LinkId=193960)  
 [<span data-ttu-id="489f1-128">简化配置</span><span class="sxs-lookup"><span data-stu-id="489f1-128">Simplified Configuration</span></span>](../../../../docs/framework/wcf/simplified-configuration.md)
