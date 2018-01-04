---
title: "通过范围进行发现的示例"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 6a37a754-6b8c-4ebe-bdf2-d4f0520271d5
caps.latest.revision: "15"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: aa762df1dbfe92102f8cd719613099b23986ed0c
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="discovery-with-scopes-sample"></a><span data-ttu-id="e9ccc-102">通过范围进行发现的示例</span><span class="sxs-lookup"><span data-stu-id="e9ccc-102">Discovery with Scopes Sample</span></span>
<span data-ttu-id="e9ccc-103">此示例演示如何使用范围对可发现的终结点进行分类，以及如何使用 <xref:System.ServiceModel.Discovery.DiscoveryClient> 来执行终结点的异步搜索。</span><span class="sxs-lookup"><span data-stu-id="e9ccc-103">This sample shows how to use scopes to categorize discoverable endpoints as well how to use <xref:System.ServiceModel.Discovery.DiscoveryClient> to perform an asynchronous search for endpoints.</span></span> <span data-ttu-id="e9ccc-104">对于服务，此示例演示如何通过以下方法为每个终结点自定义发现：添加一个终结点发现行为并使用它将一个范围添加到该终结点，以及控制该终结点的可发现性。</span><span class="sxs-lookup"><span data-stu-id="e9ccc-104">On the service, this sample shows how to customize discovery for each endpoint by adding an endpoint discovery behavior and using it to add a scope to the endpoint as well as controlling the endpoint’s discoverability.</span></span> <span data-ttu-id="e9ccc-105">对于客户端，此示例演示客户端如何创建 <xref:System.ServiceModel.Discovery.DiscoveryClient>，以及如何通过将范围添加到 <xref:System.ServiceModel.Discovery.FindCriteria> 对搜索参数进行精细调整以包含范围。</span><span class="sxs-lookup"><span data-stu-id="e9ccc-105">On the client, the sample goes over how clients can create a <xref:System.ServiceModel.Discovery.DiscoveryClient> and fine tune search parameters to include scopes by adding scopes to the <xref:System.ServiceModel.Discovery.FindCriteria>.</span></span> <span data-ttu-id="e9ccc-106">此示例还演示客户端如何通过添加终止条件来限制响应。</span><span class="sxs-lookup"><span data-stu-id="e9ccc-106">This sample also shows how clients can restrict responses by adding a termination criterion.</span></span>  
  
## <a name="service-features"></a><span data-ttu-id="e9ccc-107">服务功能</span><span class="sxs-lookup"><span data-stu-id="e9ccc-107">Service Features</span></span>  
 <span data-ttu-id="e9ccc-108">此项目演示添加到 <xref:System.ServiceModel.ServiceHost> 的两个服务终结点。</span><span class="sxs-lookup"><span data-stu-id="e9ccc-108">This project shows two service endpoints being added to a <xref:System.ServiceModel.ServiceHost>.</span></span> <span data-ttu-id="e9ccc-109">每个终结点都具有一个与之关联的 <xref:System.ServiceModel.Discovery.EndpointDiscoveryBehavior>。</span><span class="sxs-lookup"><span data-stu-id="e9ccc-109">Each endpoint has a <xref:System.ServiceModel.Discovery.EndpointDiscoveryBehavior> associated with it.</span></span> <span data-ttu-id="e9ccc-110">此行为用于添加这两个终结点的 URI 范围。</span><span class="sxs-lookup"><span data-stu-id="e9ccc-110">This behavior is used to add URI scopes for both endpoints.</span></span> <span data-ttu-id="e9ccc-111">范围用于区分每个终结点，以便客户端可以对搜索进行精细调整。</span><span class="sxs-lookup"><span data-stu-id="e9ccc-111">Scopes are used to distinguish each of these endpoints so that the clients can fine tune the search.</span></span> <span data-ttu-id="e9ccc-112">对于第二个终结点，可通过将 <xref:System.ServiceModel.Discovery.EndpointDiscoveryBehavior.Enabled%2A> 属性设置为 `false` 来禁用可发现性。</span><span class="sxs-lookup"><span data-stu-id="e9ccc-112">For the second endpoint, the discoverability can be disabled by setting the <xref:System.ServiceModel.Discovery.EndpointDiscoveryBehavior.Enabled%2A> property to `false`.</span></span> <span data-ttu-id="e9ccc-113">这将确保与此终结点关联的发现元数据不会作为任何发现消息的一部分发送。</span><span class="sxs-lookup"><span data-stu-id="e9ccc-113">This ensures that the discovery metadata associated with this endpoint is not sent as part of any discovery messages.</span></span>  
  
## <a name="client-features"></a><span data-ttu-id="e9ccc-114">客户端功能</span><span class="sxs-lookup"><span data-stu-id="e9ccc-114">Client Features</span></span>  
 <span data-ttu-id="e9ccc-115">`FindCalculatorServiceAddress()` 方法演示如何使用 <xref:System.ServiceModel.Discovery.DiscoveryClient> 并传入具有两个限制的 <xref:System.ServiceModel.Discovery.FindCriteria>。</span><span class="sxs-lookup"><span data-stu-id="e9ccc-115">The `FindCalculatorServiceAddress()` method shows how to use a <xref:System.ServiceModel.Discovery.DiscoveryClient> and pass in a <xref:System.ServiceModel.Discovery.FindCriteria> with two restrictions.</span></span> <span data-ttu-id="e9ccc-116">将一个范围添加到条件，并将 <xref:System.ServiceModel.Discovery.FindCriteria.MaxResults%2A> 属性设置为 1。</span><span class="sxs-lookup"><span data-stu-id="e9ccc-116">A scope is added to the criteria and the <xref:System.ServiceModel.Discovery.FindCriteria.MaxResults%2A> property is set to 1.</span></span> <span data-ttu-id="e9ccc-117">此范围将结果限制为仅发布相同范围的服务。</span><span class="sxs-lookup"><span data-stu-id="e9ccc-117">The scope limits the results to only the services that publish the same scope.</span></span> <span data-ttu-id="e9ccc-118">将 <xref:System.ServiceModel.Discovery.FindCriteria.MaxResults%2A> 设置为 1 可将 <xref:System.ServiceModel.Discovery.DiscoveryClient> 等待的响应限制为最多 1 个终结点。</span><span class="sxs-lookup"><span data-stu-id="e9ccc-118">Setting <xref:System.ServiceModel.Discovery.FindCriteria.MaxResults%2A> to 1 limits the responses the <xref:System.ServiceModel.Discovery.DiscoveryClient> waits for to, at most, 1 endpoint.</span></span> <span data-ttu-id="e9ccc-119"><xref:System.ServiceModel.Discovery.DiscoveryClient.Find%2A> 调用是一个同步操作，在达到超时或找到一个终结点之前，该同步操作将阻止该线程。</span><span class="sxs-lookup"><span data-stu-id="e9ccc-119">The <xref:System.ServiceModel.Discovery.DiscoveryClient.Find%2A> call is a synchronous operation that blocks the thread until a timeout is reached or one endpoint is found.</span></span>  
  
#### <a name="to-use-this-sample"></a><span data-ttu-id="e9ccc-120">使用此示例</span><span class="sxs-lookup"><span data-stu-id="e9ccc-120">To use this sample</span></span>  
  
1.  <span data-ttu-id="e9ccc-121">此示例使用 HTTP 终结点，若要运行此示例，必须添加正确的 URL ACL。</span><span class="sxs-lookup"><span data-stu-id="e9ccc-121">This sample uses HTTP endpoints and to run this sample, proper URL ACLs must be added.</span></span> <span data-ttu-id="e9ccc-122">请参阅[配置 HTTP 和 HTTPS](http://go.microsoft.com/fwlink/?LinkId=70353)有关详细信息。</span><span class="sxs-lookup"><span data-stu-id="e9ccc-122">See [Configuring HTTP and HTTPS](http://go.microsoft.com/fwlink/?LinkId=70353) for details.</span></span> <span data-ttu-id="e9ccc-123">使用提升的特权执行下面的命令应添加相应的 ACL。</span><span class="sxs-lookup"><span data-stu-id="e9ccc-123">Executing the following command at an elevated privilege should add the appropriate ACLs.</span></span> <span data-ttu-id="e9ccc-124">如果该命令无效，则可能需要使用您的域和用户名替换以下参数：`netsh http add urlacl url=http://+:8000/ user=%DOMAIN%\%UserName%`</span><span class="sxs-lookup"><span data-stu-id="e9ccc-124">You may want to substitute your Domain and Username for the following arguments if the command does not work as is: `netsh http add urlacl url=http://+:8000/ user=%DOMAIN%\%UserName%`</span></span>  
  
2.  <span data-ttu-id="e9ccc-125">生成解决方案。</span><span class="sxs-lookup"><span data-stu-id="e9ccc-125">Build the solution.</span></span>  
  
3.  <span data-ttu-id="e9ccc-126">从生成目录运行服务可执行文件。</span><span class="sxs-lookup"><span data-stu-id="e9ccc-126">Run the service executable from the build directory.</span></span>  
  
4.  <span data-ttu-id="e9ccc-127">运行客户端可执行文件。</span><span class="sxs-lookup"><span data-stu-id="e9ccc-127">Run the client executable.</span></span> <span data-ttu-id="e9ccc-128">请注意，客户端能够查找该服务。</span><span class="sxs-lookup"><span data-stu-id="e9ccc-128">Note that the client is able to locate the service.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="e9ccc-129">您的计算机上可能已安装这些示例。</span><span class="sxs-lookup"><span data-stu-id="e9ccc-129">The samples may already be installed on your machine.</span></span> <span data-ttu-id="e9ccc-130">在继续操作之前，请先检查以下（默认）目录：</span><span class="sxs-lookup"><span data-stu-id="e9ccc-130">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="e9ccc-131">如果此目录不存在，请访问 [针对 .NET Framework 4 的 Windows Communication Foundation (WCF) 和 Windows Workflow Foundation (WF) 示例](http://go.microsoft.com/fwlink/?LinkId=150780) 以下载所有 [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] 和 [!INCLUDE[wf1](../../../../includes/wf1-md.md)] 示例。</span><span class="sxs-lookup"><span data-stu-id="e9ccc-131">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="e9ccc-132">此示例位于以下目录：</span><span class="sxs-lookup"><span data-stu-id="e9ccc-132">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Discovery\DiscoveryWithScopes`  
  
## <a name="see-also"></a><span data-ttu-id="e9ccc-133">请参阅</span><span class="sxs-lookup"><span data-stu-id="e9ccc-133">See Also</span></span>
