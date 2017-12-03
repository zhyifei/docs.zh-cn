---
title: CustomDiscoveryMetadata
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: c42455fd-3652-4b7e-b698-ab3a2bb52e48
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 4b4a68204d8ae5d2a338d60498522810a557e575
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/02/2017
---
# <a name="customdiscoverymetadata"></a><span data-ttu-id="9f245-102">CustomDiscoveryMetadata</span><span class="sxs-lookup"><span data-stu-id="9f245-102">CustomDiscoveryMetadata</span></span>
<span data-ttu-id="9f245-103">此示例演示如何在发现元数据中针对服务公开的可发现终结点插入自定义 XML 元数据。</span><span class="sxs-lookup"><span data-stu-id="9f245-103">This sample shows how to insert custom XML metadata into the discovery metadata for a discoverable endpoint exposed by a service.</span></span> <span data-ttu-id="9f245-104">示例随后演示客户端如何搜索服务和提取此自定义数据。</span><span class="sxs-lookup"><span data-stu-id="9f245-104">The sample then shows how a client can search for the service and extract this custom data.</span></span> <span data-ttu-id="9f245-105">此示例由两个项目组成，即服务项目和客户端项目。</span><span class="sxs-lookup"><span data-stu-id="9f245-105">This sample consists of two projects, service and client.</span></span>  
  
## <a name="service"></a><span data-ttu-id="9f245-106">服务</span><span class="sxs-lookup"><span data-stu-id="9f245-106">Service</span></span>  
 <span data-ttu-id="9f245-107">在 `main` 方法中，示例演示一个 <xref:System.Xml.Linq.XElement> 类型的对象填充为所需的字段并添加到 <xref:System.ServiceModel.Discovery.EndpointDiscoveryBehavior> 中。</span><span class="sxs-lookup"><span data-stu-id="9f245-107">In the `main` method, the sample shows that an object of type <xref:System.Xml.Linq.XElement> is populated with the desired fields and is added to the <xref:System.ServiceModel.Discovery.EndpointDiscoveryBehavior>.</span></span> <span data-ttu-id="9f245-108">此 <xref:System.ServiceModel.Discovery.EndpointDiscoveryBehavior> 会添加到特定终结点。</span><span class="sxs-lookup"><span data-stu-id="9f245-108">This <xref:System.ServiceModel.Discovery.EndpointDiscoveryBehavior> is added to a particular endpoint.</span></span> <span data-ttu-id="9f245-109">当发现该特定终结点时，发现元数据会包含此处添加的自定义数据。</span><span class="sxs-lookup"><span data-stu-id="9f245-109">When that particular endpoint is discovered, the discovery metadata contains the custom data that was added here.</span></span>  
  
## <a name="client"></a><span data-ttu-id="9f245-110">客户端</span><span class="sxs-lookup"><span data-stu-id="9f245-110">Client</span></span>  
 <span data-ttu-id="9f245-111">本示例演示对 <xref:System.ServiceModel.Discovery.DiscoveryClient.Find%2A> 调用的 <xref:System.ServiceModel.Discovery.DiscoveryClient> 方法。</span><span class="sxs-lookup"><span data-stu-id="9f245-111">The sample shows the <xref:System.ServiceModel.Discovery.DiscoveryClient.Find%2A> method being called on a <xref:System.ServiceModel.Discovery.DiscoveryClient>.</span></span> <span data-ttu-id="9f245-112">随后对得到的 <xref:System.ServiceModel.Discovery.FindResponse> 进行查询以获得所需的合适 XML 元素。</span><span class="sxs-lookup"><span data-stu-id="9f245-112">The resulting <xref:System.ServiceModel.Discovery.FindResponse> is then queried for the appropriate and expected XML elements.</span></span> <span data-ttu-id="9f245-113">这些元素随后会打印到控制台。</span><span class="sxs-lookup"><span data-stu-id="9f245-113">These elements are then printed to the console.</span></span>  
  
#### <a name="to-use-this-sample"></a><span data-ttu-id="9f245-114">使用此示例</span><span class="sxs-lookup"><span data-stu-id="9f245-114">To use this sample</span></span>  
  
1.  <span data-ttu-id="9f245-115">在 [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)] 中加载项目解决方案，然后生成项目。</span><span class="sxs-lookup"><span data-stu-id="9f245-115">Load the project solution in [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)] and build the project.</span></span>  
  
2.  <span data-ttu-id="9f245-116">首先运行在 [解决方案基目录]\service\bin\debug 中生成的服务应用程序，然后运行在 [解决方案基目录]\Client\bin\debug 中生成的客户端应用程序</span><span class="sxs-lookup"><span data-stu-id="9f245-116">First run the Service application, generated in [solution base directory]\service\bin\debug, and then run the Client application, generated in [solution base directory]\Client\bin\debug</span></span>  
  
3.  <span data-ttu-id="9f245-117">请注意，服务会处于脱机状态，客户端定位服务并打印在终结点发布的元数据。</span><span class="sxs-lookup"><span data-stu-id="9f245-117">Note that the service comes online, the client locates the service and prints the metadata published in the endpoint.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="9f245-118">您的计算机上可能已安装这些示例。</span><span class="sxs-lookup"><span data-stu-id="9f245-118">The samples may already be installed on your machine.</span></span> <span data-ttu-id="9f245-119">在继续操作之前，请先检查以下（默认）目录：</span><span class="sxs-lookup"><span data-stu-id="9f245-119">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="9f245-120">如果此目录不存在，请访问 [针对 .NET Framework 4 的 Windows Communication Foundation (WCF) 和 Windows Workflow Foundation (WF) 示例](http://go.microsoft.com/fwlink/?LinkId=150780) 以下载所有 [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] 和 [!INCLUDE[wf1](../../../../includes/wf1-md.md)] 示例。</span><span class="sxs-lookup"><span data-stu-id="9f245-120">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="9f245-121">此示例位于以下目录：</span><span class="sxs-lookup"><span data-stu-id="9f245-121">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Extensibility\DiscoveryExtensibility\CustomDiscoveryMetadata`  
  
## <a name="see-also"></a><span data-ttu-id="9f245-122">另请参阅</span><span class="sxs-lookup"><span data-stu-id="9f245-122">See Also</span></span>
