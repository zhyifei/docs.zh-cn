---
title: 自定义查找条件
ms.date: 03/30/2017
ms.assetid: b2723929-8829-424d-8015-a37ba2ab4f68
ms.openlocfilehash: 699260fcef7680710f721d213dbf1126ebf7a896
ms.sourcegitcommit: ba5c189bf44d44204a3e8838e59ec378a62d82f3
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/13/2018
ms.locfileid: "44757206"
---
# <a name="custom-find-criteria"></a><span data-ttu-id="e959d-102">自定义查找条件</span><span class="sxs-lookup"><span data-stu-id="e959d-102">Custom Find Criteria</span></span>
<span data-ttu-id="e959d-103">本示例演示如何使用逻辑来创建自定义范围匹配以及如何实现自定义发现服务。</span><span class="sxs-lookup"><span data-stu-id="e959d-103">This sample demonstrates how to create a custom scope match using logic and how to implement a custom discovery service.</span></span> <span data-ttu-id="e959d-104">客户端使用自定义范围匹配功能在系统提供的 WCF Discovery 查找功能基础之上进行优化并进一步生成。</span><span class="sxs-lookup"><span data-stu-id="e959d-104">Clients use custom scope matching functionality to refine and further build on top of the system-provided find functionality of WCF Discovery.</span></span> <span data-ttu-id="e959d-105">本示例包含的方案如下所示：</span><span class="sxs-lookup"><span data-stu-id="e959d-105">The scenario this sample covers is as follows:</span></span>  
  
1.  <span data-ttu-id="e959d-106">客户端查找计算器服务。</span><span class="sxs-lookup"><span data-stu-id="e959d-106">A client is looking for a calculator service.</span></span>  
  
2.  <span data-ttu-id="e959d-107">若要优化其搜索，客户端必须使用自定义范围匹配规则。</span><span class="sxs-lookup"><span data-stu-id="e959d-107">To refine its search, the client must use a custom scope matching rule.</span></span>  
  
3.  <span data-ttu-id="e959d-108">根据此规则，如果服务的终结点与客户端指定的任何范围匹配，则服务响应回客户端。</span><span class="sxs-lookup"><span data-stu-id="e959d-108">According to this rule, a service responds back to the client if its endpoint matches any of the scopes specified by the client.</span></span>  
  
## <a name="demonstrates"></a><span data-ttu-id="e959d-109">演示</span><span class="sxs-lookup"><span data-stu-id="e959d-109">Demonstrates</span></span>  
  
-   <span data-ttu-id="e959d-110">创建自定义发现服务。</span><span class="sxs-lookup"><span data-stu-id="e959d-110">Creating a custom discovery service.</span></span>  
  
-   <span data-ttu-id="e959d-111">通过算法实现自定义范围匹配。</span><span class="sxs-lookup"><span data-stu-id="e959d-111">Implementing a custom scope match by algorithm.</span></span>  
  
## <a name="discussion"></a><span data-ttu-id="e959d-112">讨论</span><span class="sxs-lookup"><span data-stu-id="e959d-112">Discussion</span></span>  
 <span data-ttu-id="e959d-113">客户端查找条件匹配的"OR"类型。</span><span class="sxs-lookup"><span data-stu-id="e959d-113">The client is looking for "OR" type matching criteria.</span></span> <span data-ttu-id="e959d-114">如果服务终结点上的范围与客户端提供的任何范围匹配，则服务响应回客户端。</span><span class="sxs-lookup"><span data-stu-id="e959d-114">A service responds back if the scopes on its endpoints match any of the scopes provided by the client.</span></span> <span data-ttu-id="e959d-115">在本例中，客户端查找具有下面列表中任何范围的计算器服务：</span><span class="sxs-lookup"><span data-stu-id="e959d-115">In this case, the client is looking for a calculator service that has any of the scopes in the following list:</span></span>  
  
1.  `net.tcp://Microsoft.Samples.Discovery/RedmondLocation`  
  
2.  `net.tcp://Microsoft.Samples.Discovery/SeattleLocation`  
  
3.  `net.tcp://Microsoft.Samples.Discovery/PortlandLocation`  
  
 <span data-ttu-id="e959d-116">为实现此功能，客户端指示服务通过按 URI 传入自定义范围匹配来使用自定义范围匹配规则。</span><span class="sxs-lookup"><span data-stu-id="e959d-116">To accomplish this, the client directs services to use a custom scope matching rule by passing in a custom scope match by URI.</span></span> <span data-ttu-id="e959d-117">为便于进行自定义范围匹配，服务必须使用了解自定义范围匹配规则并实现关联匹配逻辑的自定义发现服务。</span><span class="sxs-lookup"><span data-stu-id="e959d-117">To facilitate the custom scope matching, the service must use a custom discovery service that understands the custom scope match rule and implements the associated matching logic.</span></span>  
  
 <span data-ttu-id="e959d-118">在客户端项目中，打开 Program.cs 文件。</span><span class="sxs-lookup"><span data-stu-id="e959d-118">In the client project, open the Program.cs file.</span></span> <span data-ttu-id="e959d-119">请注意，`ScopeMatchBy` 对象的 `FindCriteria` 字段设置为特定 URI。</span><span class="sxs-lookup"><span data-stu-id="e959d-119">Note that the `ScopeMatchBy` field of the `FindCriteria` object is set to a specific URI.</span></span> <span data-ttu-id="e959d-120">此标识符会发送给服务。</span><span class="sxs-lookup"><span data-stu-id="e959d-120">This identifier is sent to the service.</span></span> <span data-ttu-id="e959d-121">如果服务不了解此规则，则会忽略客户端的查找请求。</span><span class="sxs-lookup"><span data-stu-id="e959d-121">If the service does not understand this rule, it ignores the client’s find request.</span></span>  
  
 <span data-ttu-id="e959d-122">打开服务项目。</span><span class="sxs-lookup"><span data-stu-id="e959d-122">Open the service project.</span></span> <span data-ttu-id="e959d-123">有三个文件用于实现自定义发现服务：</span><span class="sxs-lookup"><span data-stu-id="e959d-123">Three files are used to implement the Custom Discovery Service:</span></span>  
  
1.  <span data-ttu-id="e959d-124">**AsyncResult.cs**： 这是实现`AsyncResult`所要求的发现方法。</span><span class="sxs-lookup"><span data-stu-id="e959d-124">**AsyncResult.cs**: This is the implementation of the `AsyncResult` that is required by Discovery methods.</span></span>  
  
2.  <span data-ttu-id="e959d-125">**CustomDiscoveryService.cs**： 此文件实现自定义发现服务。</span><span class="sxs-lookup"><span data-stu-id="e959d-125">**CustomDiscoveryService.cs**: This file implements the custom discovery service.</span></span> <span data-ttu-id="e959d-126">该实现扩展 <xref:System.ServiceModel.Discovery.DiscoveryService> 类并重写必需的方法。</span><span class="sxs-lookup"><span data-stu-id="e959d-126">The implementation extends the <xref:System.ServiceModel.Discovery.DiscoveryService> class and overrides the necessary methods.</span></span> <span data-ttu-id="e959d-127">请注意 <xref:System.ServiceModel.Discovery.DiscoveryService.OnBeginFind%2A> 方法的实现。</span><span class="sxs-lookup"><span data-stu-id="e959d-127">Note the implementation of the <xref:System.ServiceModel.Discovery.DiscoveryService.OnBeginFind%2A> method.</span></span> <span data-ttu-id="e959d-128">该方法进行检查以确定客户端是否指定了按规则进行的自定义范围匹配。</span><span class="sxs-lookup"><span data-stu-id="e959d-128">The method checks to see whether the custom scope match by rule was specified by the client.</span></span> <span data-ttu-id="e959d-129">这与客户端之前指定的自定义 URI 相同。</span><span class="sxs-lookup"><span data-stu-id="e959d-129">This is the same custom URI that the client specified previously.</span></span> <span data-ttu-id="e959d-130">如果指定的自定义规则，则遵循实现"OR"匹配逻辑的代码路径。</span><span class="sxs-lookup"><span data-stu-id="e959d-130">If the custom rule is specified, the code path that implements the "OR" match logic is followed.</span></span>  
  
     <span data-ttu-id="e959d-131">此自定义逻辑遍历服务具有的每个终结点上的所有范围。</span><span class="sxs-lookup"><span data-stu-id="e959d-131">This custom logic goes through all of the scopes on each of the endpoints that the service has.</span></span> <span data-ttu-id="e959d-132">如果有任何终结点的范围与客户端提供的任何范围匹配，则发现服务会将该终结点添加到发送回客户端的响应中。</span><span class="sxs-lookup"><span data-stu-id="e959d-132">If any of the endpoint's scopes match any of the scopes provided by the client, the discovery service adds that endpoint to the response that is sent back to the client.</span></span>  
  
3.  <span data-ttu-id="e959d-133">**CustomDiscoveryExtension.cs**： 实现发现服务的最后一步是连接此实现的自定义发现服务到服务主机。</span><span class="sxs-lookup"><span data-stu-id="e959d-133">**CustomDiscoveryExtension.cs**: The last step in implementing the discovery service is to connect this implementation of the custom discover service to the service host.</span></span> <span data-ttu-id="e959d-134">此处使用的帮助程序类是 `CustomDiscoveryExtension` 类。</span><span class="sxs-lookup"><span data-stu-id="e959d-134">The helper class used here is the `CustomDiscoveryExtension` class.</span></span> <span data-ttu-id="e959d-135">此类扩展 <xref:System.ServiceModel.Discovery.DiscoveryServiceExtension> 类。</span><span class="sxs-lookup"><span data-stu-id="e959d-135">This class extends the <xref:System.ServiceModel.Discovery.DiscoveryServiceExtension> class.</span></span> <span data-ttu-id="e959d-136">用户必须重写 <xref:System.ServiceModel.Discovery.DiscoveryServiceExtension.GetDiscoveryService%2A> 方法。</span><span class="sxs-lookup"><span data-stu-id="e959d-136">The user must override the <xref:System.ServiceModel.Discovery.DiscoveryServiceExtension.GetDiscoveryService%2A> method.</span></span> <span data-ttu-id="e959d-137">在这种情况中，方法返回之前创建的自定义发现服务的实例。</span><span class="sxs-lookup"><span data-stu-id="e959d-137">In this case, the method returns an instance of the custom discovery service that was created before.</span></span> <span data-ttu-id="e959d-138">`PublishedEndpoints` 是 <xref:System.Collections.ObjectModel.ReadOnlyCollection%601>，它包含要添加到 <xref:System.ServiceModel.ServiceHost> 的所有应用程序终结点。</span><span class="sxs-lookup"><span data-stu-id="e959d-138">`PublishedEndpoints` is a <xref:System.Collections.ObjectModel.ReadOnlyCollection%601> that contains all of the application endpoints that are added to the <xref:System.ServiceModel.ServiceHost>.</span></span> <span data-ttu-id="e959d-139">自定义发现服务用此填充其内部列表。</span><span class="sxs-lookup"><span data-stu-id="e959d-139">The custom discovery service uses this to populate its internal list.</span></span> <span data-ttu-id="e959d-140">用户也可以添加其他终结点元数据。</span><span class="sxs-lookup"><span data-stu-id="e959d-140">A user can to add other endpoint metadata as well.</span></span>  
  
 <span data-ttu-id="e959d-141">最后，打开 Program.cs。</span><span class="sxs-lookup"><span data-stu-id="e959d-141">Lastly, open Program.cs.</span></span> <span data-ttu-id="e959d-142">请注意，<xref:System.ServiceModel.Discovery.ServiceDiscoveryBehavior> 和 `CustomDiscoveryExtension` 都添加到主机中。</span><span class="sxs-lookup"><span data-stu-id="e959d-142">Note that both the <xref:System.ServiceModel.Discovery.ServiceDiscoveryBehavior> and `CustomDiscoveryExtension` are added to the host.</span></span> <span data-ttu-id="e959d-143">在此操作完成，并且主机具有可用于接收发现消息的终结点后，应用程序便可以使用自定义发现服务。</span><span class="sxs-lookup"><span data-stu-id="e959d-143">Once this is done and the host has an endpoint over which to receive discovery messages, the application can use the custom discovery service.</span></span>  
  
 <span data-ttu-id="e959d-144">观察客户端是否能够在不知道服务地址的情况下找到服务。</span><span class="sxs-lookup"><span data-stu-id="e959d-144">Observe that the client is able to find the service without knowing its address.</span></span>  
  
#### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="e959d-145">设置、生成和运行示例</span><span class="sxs-lookup"><span data-stu-id="e959d-145">To set up, build, and run the sample</span></span>  
  
1.  <span data-ttu-id="e959d-146">打开包含项目的解决方案。</span><span class="sxs-lookup"><span data-stu-id="e959d-146">Open the solution that contains the project.</span></span>  
  
2.  <span data-ttu-id="e959d-147">生成项目。</span><span class="sxs-lookup"><span data-stu-id="e959d-147">Build the project.</span></span>  
  
3.  <span data-ttu-id="e959d-148">运行服务应用程序。</span><span class="sxs-lookup"><span data-stu-id="e959d-148">Run the service application.</span></span>  
  
4.  <span data-ttu-id="e959d-149">运行客户端应用程序。</span><span class="sxs-lookup"><span data-stu-id="e959d-149">Run the client application.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="e959d-150">您的计算机上可能已安装这些示例。</span><span class="sxs-lookup"><span data-stu-id="e959d-150">The samples may already be installed on your machine.</span></span> <span data-ttu-id="e959d-151">在继续操作之前，请先检查以下（默认）目录：</span><span class="sxs-lookup"><span data-stu-id="e959d-151">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="e959d-152">如果此目录不存在，请转到[Windows Communication Foundation (WCF) 和.NET Framework 4 的 Windows Workflow Foundation (WF) 示例](https://go.microsoft.com/fwlink/?LinkId=150780)若要下载所有 Windows Communication Foundation (WCF) 和[!INCLUDE[wf1](../../../../includes/wf1-md.md)]示例。</span><span class="sxs-lookup"><span data-stu-id="e959d-152">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="e959d-153">此示例位于以下目录：</span><span class="sxs-lookup"><span data-stu-id="e959d-153">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Discovery\CustomFindCriteria`
