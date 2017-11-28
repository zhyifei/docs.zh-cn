---
title: "发现代理示例"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 1dfa02df-15b1-4e97-9c8e-f5f2772711b0
caps.latest.revision: "14"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: f16cf2ffc9e03308ce3b8a5e967c29e624ffd1af
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="discovery-proxy-sample"></a><span data-ttu-id="9a03d-102">发现代理示例</span><span class="sxs-lookup"><span data-stu-id="9a03d-102">Discovery Proxy Sample</span></span>
<span data-ttu-id="9a03d-103">此示例演示如何创建发现代理的实现以存储有关现有服务的信息，并演示客户端如何可以查询该代理以获取信息。</span><span class="sxs-lookup"><span data-stu-id="9a03d-103">This sample shows how to create an implementation of a Discovery proxy to store information about existing services and how clients can query that proxy for information.</span></span> <span data-ttu-id="9a03d-104">此示例由三个项目组成：</span><span class="sxs-lookup"><span data-stu-id="9a03d-104">This sample consists of three projects:</span></span>  
  
-   <span data-ttu-id="9a03d-105">**服务**： 一个简单[!INCLUDE[indigo1](../../../../includes/indigo1-md.md)]向发现代理注册自身的计算器服务。</span><span class="sxs-lookup"><span data-stu-id="9a03d-105">**Service**: A simple [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] calculator service that registers itself with the discovery proxy.</span></span>  
  
-   <span data-ttu-id="9a03d-106">**发现代理**： 发现代理服务的实现。</span><span class="sxs-lookup"><span data-stu-id="9a03d-106">**Discovery Proxy**: The implementation of a discovery proxy service.</span></span>  
  
-   <span data-ttu-id="9a03d-107">**客户端**： 要搜索的发现代理调用服务的 WCF 客户端应用程序。</span><span class="sxs-lookup"><span data-stu-id="9a03d-107">**Client**: A WCF client application that calls the discovery proxy to search for services.</span></span>  
  
## <a name="demonstrates"></a><span data-ttu-id="9a03d-108">演示</span><span class="sxs-lookup"><span data-stu-id="9a03d-108">Demonstrates</span></span>  
 <span data-ttu-id="9a03d-109">发现代理实现</span><span class="sxs-lookup"><span data-stu-id="9a03d-109">Discovery proxy implementation</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="9a03d-110">您的计算机上可能已安装这些示例。</span><span class="sxs-lookup"><span data-stu-id="9a03d-110">The samples may already be installed on your machine.</span></span> <span data-ttu-id="9a03d-111">在继续操作之前，请先检查以下（默认）目录：</span><span class="sxs-lookup"><span data-stu-id="9a03d-111">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="9a03d-112">如果此目录不存在，请访问 [针对 .NET Framework 4 的 Windows Communication Foundation (WCF) 和 Windows Workflow Foundation (WF) 示例](http://go.microsoft.com/fwlink/?LinkId=150780) 以下载所有 [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] 和 [!INCLUDE[wf1](../../../../includes/wf1-md.md)] 示例。</span><span class="sxs-lookup"><span data-stu-id="9a03d-112">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="9a03d-113">此示例位于以下目录：</span><span class="sxs-lookup"><span data-stu-id="9a03d-113">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Discovery\DiscoveryProxy`  
  
## <a name="discoveryproxy"></a><span data-ttu-id="9a03d-114">DiscoveryProxy</span><span class="sxs-lookup"><span data-stu-id="9a03d-114">DiscoveryProxy</span></span>  
 <span data-ttu-id="9a03d-115">在 Program.cs 文件的 `Main`方法中，该示例演示如何承载 <xref:System.ServiceModel.Discovery.DiscoveryProxy> 类型的服务。</span><span class="sxs-lookup"><span data-stu-id="9a03d-115">In the `Main` method of the Program.cs file, the sample shows how a service of type <xref:System.ServiceModel.Discovery.DiscoveryProxy> is hosted.</span></span> <span data-ttu-id="9a03d-116">它公开两个终结点，一个终结点为 <xref:System.ServiceModel.Discovery.DiscoveryEndpoint> 类型，另一个终结点为 <xref:System.ServiceModel.Discovery.AnnouncementEndpoint> 类型。</span><span class="sxs-lookup"><span data-stu-id="9a03d-116">It exposes two endpoints, one of type <xref:System.ServiceModel.Discovery.DiscoveryEndpoint> and another of type <xref:System.ServiceModel.Discovery.AnnouncementEndpoint>.</span></span> <span data-ttu-id="9a03d-117">两个终结点都将 TCP 用作传输。</span><span class="sxs-lookup"><span data-stu-id="9a03d-117">Both of the endpoints use TCP as a transport.</span></span> <span data-ttu-id="9a03d-118"><xref:System.ServiceModel.Discovery.DiscoveryEndpoint> 正在侦听 `probeEndpointAddress` 参数指定的 URI，客户端可以在此处发送探测消息以向代理查询其数据。</span><span class="sxs-lookup"><span data-stu-id="9a03d-118">The <xref:System.ServiceModel.Discovery.DiscoveryEndpoint> is listening at the URI specified by the `probeEndpointAddress` parameter, this is where clients can send probe messages to query the proxy for its data.</span></span> <span data-ttu-id="9a03d-119"><xref:System.ServiceModel.Discovery.AnnouncementEndpoint> 正在侦听 `announcementEndpointAddress` 参数指定的 URI。</span><span class="sxs-lookup"><span data-stu-id="9a03d-119">The <xref:System.ServiceModel.Discovery.AnnouncementEndpoint> is listening at the URI specified by the `announcementEndpointAddress` parameter.</span></span> <span data-ttu-id="9a03d-120">代理将在这里侦听公告。</span><span class="sxs-lookup"><span data-stu-id="9a03d-120">This is where the proxy listens to for announcements.</span></span> <span data-ttu-id="9a03d-121">接收到联机公告时，代理将服务添加到其缓存；当接收到脱机公告时，代理从其缓存移除服务。</span><span class="sxs-lookup"><span data-stu-id="9a03d-121">When an online announcement is received, the proxy adds the service to its cache and when an offline announcement is received it removes the service from its cache.</span></span>  
  
 <span data-ttu-id="9a03d-122">DiscoveryProxy.cs 包含 <xref:System.ServiceModel.Discovery.DiscoveryProxy> 的实现。</span><span class="sxs-lookup"><span data-stu-id="9a03d-122">The DiscoveryProxy.cs contains the implementation of the <xref:System.ServiceModel.Discovery.DiscoveryProxy>.</span></span> <span data-ttu-id="9a03d-123">代理必须从 <xref:System.Object> 类继承，并需要 <xref:System.Runtime.Remoting.Messaging.AsyncResult> 的实现。</span><span class="sxs-lookup"><span data-stu-id="9a03d-123">The Proxy must inherit from the <xref:System.Object> class and requires an implementation of <xref:System.Runtime.Remoting.Messaging.AsyncResult>.</span></span> <span data-ttu-id="9a03d-124">在进行实例化时，代理将创建一个新的 <xref:System.Collections.Generic.Dictionary%602>，用于存储它所知道的元素。</span><span class="sxs-lookup"><span data-stu-id="9a03d-124">At instantiation, the Proxy creates a new <xref:System.Collections.Generic.Dictionary%602>, which it uses to store elements it knows about.</span></span>  
  
 <span data-ttu-id="9a03d-125">该文件分为两个区域：代理缓存方法区域和发现代理实现区域。</span><span class="sxs-lookup"><span data-stu-id="9a03d-125">The file is divided into two regions, Proxy Cache Methods and Discovery Proxy Implementation.</span></span> <span data-ttu-id="9a03d-126">代理缓存方法区域包含用于更新 <xref:System.Collections.Generic.Dictionary%602>、对 <xref:System.Collections.Generic.Dictionary%602> 执行查询和打印用户数据的方法。</span><span class="sxs-lookup"><span data-stu-id="9a03d-126">The Proxy Cache Methods region contains methods used to update the <xref:System.Collections.Generic.Dictionary%602>, perform queries against the <xref:System.Collections.Generic.Dictionary%602>, and print the data for users.</span></span> <span data-ttu-id="9a03d-127">发现代理实现区域包含公告和探测功能所需的重写方法。</span><span class="sxs-lookup"><span data-stu-id="9a03d-127">The Discovery Proxy Implementation region contains the overridden methods required for the Announcement and Probe functionality.</span></span> <span data-ttu-id="9a03d-128">这些方法定义在接收到联机公告、脱机公告或探测消息后代理执行的操作。</span><span class="sxs-lookup"><span data-stu-id="9a03d-128">They define the actions taken by a proxy after receiving an Online Announcement, an Offline Announcement, or a Probe message.</span></span>  
  
## <a name="service"></a><span data-ttu-id="9a03d-129">服务</span><span class="sxs-lookup"><span data-stu-id="9a03d-129">Service</span></span>  
 <span data-ttu-id="9a03d-130">在服务项目中的 Program.cs 文件中，相同的 URI 将用于其公告终结点以作为发现代理。</span><span class="sxs-lookup"><span data-stu-id="9a03d-130">In the Program.cs file in the Service project, the same URI is used for its announcement endpoint as the discovery proxy.</span></span> <span data-ttu-id="9a03d-131">这是因为服务使用该终结点发送公告，而代理使用该终结点接收公告。</span><span class="sxs-lookup"><span data-stu-id="9a03d-131">This is because service uses the endpoint for sending the announcements, while the proxy uses it for receiving them.</span></span> <span data-ttu-id="9a03d-132">服务使用 <xref:System.ServiceModel.Discovery.EndpointDiscoveryBehavior>，并向其添加一个公告终结点。</span><span class="sxs-lookup"><span data-stu-id="9a03d-132">The service uses the <xref:System.ServiceModel.Discovery.EndpointDiscoveryBehavior> and adds an announcement endpoint to it.</span></span>  
  
## <a name="client"></a><span data-ttu-id="9a03d-133">客户端</span><span class="sxs-lookup"><span data-stu-id="9a03d-133">Client</span></span>  
 <span data-ttu-id="9a03d-134">客户端项目针对其探测终结点使用相同的 URI 作为代理。</span><span class="sxs-lookup"><span data-stu-id="9a03d-134">The Client project uses the same URI for its probe endpoint as the Proxy.</span></span> <span data-ttu-id="9a03d-135">这是因为此方案中的探测还特别单播到代理上可用的终结点。</span><span class="sxs-lookup"><span data-stu-id="9a03d-135">This is because the probes in this scenario are also being unicast specifically to the endpoint available on the proxy.</span></span> <span data-ttu-id="9a03d-136">客户端连接到此已知地址，然后查询该地址以获取服务。</span><span class="sxs-lookup"><span data-stu-id="9a03d-136">The Client connects to this well-known address and then queries it for the service.</span></span> <span data-ttu-id="9a03d-137">一旦发现服务，它就会连接到该服务。</span><span class="sxs-lookup"><span data-stu-id="9a03d-137">Once it has found the service it connects to it.</span></span>  
  
#### <a name="to-use-this-sample"></a><span data-ttu-id="9a03d-138">使用此示例</span><span class="sxs-lookup"><span data-stu-id="9a03d-138">To use this sample</span></span>  
  
1.  <span data-ttu-id="9a03d-139">在 [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)] 中加载项目解决方案，然后生成项目。</span><span class="sxs-lookup"><span data-stu-id="9a03d-139">Load the project solution in [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)] and build the project.</span></span>  
  
2.  <span data-ttu-id="9a03d-140">首先运行 [解决方案基目录]\DiscoveryProxy\bin\debug 中生成的发现代理应用程序。</span><span class="sxs-lookup"><span data-stu-id="9a03d-140">First run the Discovery Proxy application, generated in [solution base directory]\DiscoveryProxy\bin\debug.</span></span> <span data-ttu-id="9a03d-141">首先必须运行发现代理，因为 TCP 公告终结点必须做好让服务发送其公告的准备。</span><span class="sxs-lookup"><span data-stu-id="9a03d-141">The Discovery Proxy must run first because TCP announcement endpoints must be up for the service to send its announcements.</span></span>  
  
3.  <span data-ttu-id="9a03d-142">然后运行 [解决方案基目录]\Service\bin\debug 中生成的服务应用程序。</span><span class="sxs-lookup"><span data-stu-id="9a03d-142">Second, run the service application generated in [solution base directory]\Service\bin\debug.</span></span> <span data-ttu-id="9a03d-143">启动时，该服务将公告发送到发现代理的公告终结点，并在该代理的缓存中注册。</span><span class="sxs-lookup"><span data-stu-id="9a03d-143">At start-up, the service sends an announcement to the announcement endpoint of the discovery proxy and is registered in the proxy’s cache.</span></span>  
  
4.  <span data-ttu-id="9a03d-144">接下来运行 [解决方案基目录]\Client\bin\debug 中生成的客户端应用程序。</span><span class="sxs-lookup"><span data-stu-id="9a03d-144">Next, run the client application, generated in [solution base directory]\Client\bin\debug.</span></span> <span data-ttu-id="9a03d-145">客户端查询该代理，获取服务地址，然后连接到该服务。</span><span class="sxs-lookup"><span data-stu-id="9a03d-145">The client queries the proxy, gets the service address and then connects to the service.</span></span>  
  
5.  <span data-ttu-id="9a03d-146">最后终止客户端、服务和代理。</span><span class="sxs-lookup"><span data-stu-id="9a03d-146">Lastly, terminate the client, service and then the proxy.</span></span> <span data-ttu-id="9a03d-147">代理必须运行，以便它能接收服务的脱机公告。</span><span class="sxs-lookup"><span data-stu-id="9a03d-147">The proxy must be running for it to receive the service's offline announcement.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9a03d-148">另请参阅</span><span class="sxs-lookup"><span data-stu-id="9a03d-148">See Also</span></span>
