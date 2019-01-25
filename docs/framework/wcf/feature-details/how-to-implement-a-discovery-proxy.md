---
title: 如何：实现发现代理
ms.date: 03/30/2017
ms.assetid: 78d70e0a-f6c3-4cfb-a7ca-f66ebddadde0
ms.openlocfilehash: 12adc7215e929bb56aafe104546eb6e58af52ddb
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54608909"
---
# <a name="how-to-implement-a-discovery-proxy"></a><span data-ttu-id="fa3d8-102">如何：实现发现代理</span><span class="sxs-lookup"><span data-stu-id="fa3d8-102">How to: Implement a Discovery Proxy</span></span>
<span data-ttu-id="fa3d8-103">本主题介绍如何实现发现代理。</span><span class="sxs-lookup"><span data-stu-id="fa3d8-103">This topic explains how to implement a discovery proxy.</span></span> <span data-ttu-id="fa3d8-104">有关 Windows Communication Foundation (WCF) 中的发现功能的详细信息，请参阅[WCF 发现概述](../../../../docs/framework/wcf/feature-details/wcf-discovery-overview.md)。</span><span class="sxs-lookup"><span data-stu-id="fa3d8-104">For more information about the discovery feature in Windows Communication Foundation (WCF), see [WCF Discovery Overview](../../../../docs/framework/wcf/feature-details/wcf-discovery-overview.md).</span></span> <span data-ttu-id="fa3d8-105">可以通过创建一个扩展 <xref:System.ServiceModel.Discovery.DiscoveryProxy> 抽象类的类来实现发现代理。</span><span class="sxs-lookup"><span data-stu-id="fa3d8-105">A discovery proxy can be implemented by creating a class that extends the <xref:System.ServiceModel.Discovery.DiscoveryProxy> abstract class.</span></span> <span data-ttu-id="fa3d8-106">此示例中定义并使用了多个其他支持类。</span><span class="sxs-lookup"><span data-stu-id="fa3d8-106">There are a number of other support classes defined and used in this sample.</span></span> <span data-ttu-id="fa3d8-107">`OnResolveAsyncResult`、`OnFindAsyncResult` 和 `AsyncResult`。</span><span class="sxs-lookup"><span data-stu-id="fa3d8-107">`OnResolveAsyncResult`, `OnFindAsyncResult`, and `AsyncResult`.</span></span> <span data-ttu-id="fa3d8-108">这些类实现 <xref:System.IAsyncResult> 接口。</span><span class="sxs-lookup"><span data-stu-id="fa3d8-108">These classes implement the <xref:System.IAsyncResult> interface.</span></span> <span data-ttu-id="fa3d8-109">有关详细信息<xref:System.IAsyncResult>请参阅[System.IAsyncResult 接口](xref:System.IAsyncResult)。</span><span class="sxs-lookup"><span data-stu-id="fa3d8-109">For more information about <xref:System.IAsyncResult> see [System.IAsyncResult interface](xref:System.IAsyncResult).</span></span>

 <span data-ttu-id="fa3d8-110">本主题分三个主要部分来讨论如何实现发现代理：</span><span class="sxs-lookup"><span data-stu-id="fa3d8-110">Implementing a discovery proxy is broken down into three main parts in this topic:</span></span>

-   <span data-ttu-id="fa3d8-111">定义一个包含数据存储并扩展抽象 <xref:System.ServiceModel.Discovery.DiscoveryProxy> 类的类。</span><span class="sxs-lookup"><span data-stu-id="fa3d8-111">Define a class that contains a data store and extends the abstract <xref:System.ServiceModel.Discovery.DiscoveryProxy> class.</span></span>

-   <span data-ttu-id="fa3d8-112">实现帮助器 `AsyncResult` 类。</span><span class="sxs-lookup"><span data-stu-id="fa3d8-112">Implement the helper `AsyncResult` class.</span></span>

-   <span data-ttu-id="fa3d8-113">承载发现代理。</span><span class="sxs-lookup"><span data-stu-id="fa3d8-113">Host the Discovery Proxy.</span></span>

### <a name="to-create-a-new-console-application-project"></a><span data-ttu-id="fa3d8-114">创建新的控制台应用程序项目</span><span class="sxs-lookup"><span data-stu-id="fa3d8-114">To create a new console application project</span></span>

1.  <span data-ttu-id="fa3d8-115">启动 Visual Studio 2012。</span><span class="sxs-lookup"><span data-stu-id="fa3d8-115">Start Visual Studio 2012.</span></span>

2.  <span data-ttu-id="fa3d8-116">创建新的控制台应用程序项目。</span><span class="sxs-lookup"><span data-stu-id="fa3d8-116">Create a new console application project.</span></span> <span data-ttu-id="fa3d8-117">将项目命名为 `DiscoveryProxy`，并将解决方案命名为 `DiscoveryProxyExample`。</span><span class="sxs-lookup"><span data-stu-id="fa3d8-117">Name the project `DiscoveryProxy` and the name the solution `DiscoveryProxyExample`.</span></span>

3.  <span data-ttu-id="fa3d8-118">添加对项目的以下引用</span><span class="sxs-lookup"><span data-stu-id="fa3d8-118">Add the following references to the project</span></span>

    1.  <span data-ttu-id="fa3d8-119">System.ServiceModel.dll</span><span class="sxs-lookup"><span data-stu-id="fa3d8-119">System.ServiceModel.dll</span></span>

    2.  <span data-ttu-id="fa3d8-120">System.Servicemodel.Discovery.dll</span><span class="sxs-lookup"><span data-stu-id="fa3d8-120">System.Servicemodel.Discovery.dll</span></span>

    > [!CAUTION]
    >  <span data-ttu-id="fa3d8-121">确保引用这些程序集的版本 4.0 或更高版本。</span><span class="sxs-lookup"><span data-stu-id="fa3d8-121">Ensure that you reference version 4.0 or greater of these assemblies.</span></span>

### <a name="to-implement-the-proxydiscoveryservice-class"></a><span data-ttu-id="fa3d8-122">实现 ProxyDiscoveryService 类</span><span class="sxs-lookup"><span data-stu-id="fa3d8-122">To implement the ProxyDiscoveryService class</span></span>

1.  <span data-ttu-id="fa3d8-123">向项目添加新代码文件并将其命名为 DiscoveryProxy.cs。</span><span class="sxs-lookup"><span data-stu-id="fa3d8-123">Add a new code file to your project and name it DiscoveryProxy.cs.</span></span>

2.  <span data-ttu-id="fa3d8-124">将以下 `using` 语句添加到 DiscoveryProxy.cs。</span><span class="sxs-lookup"><span data-stu-id="fa3d8-124">Add the following `using` statements to DiscoveryProxy.cs.</span></span>

    ```
    using System;
    using System.Collections.Generic;
    using System.ServiceModel;
    using System.ServiceModel.Discovery;
    using System.Xml;
    ```

3.  <span data-ttu-id="fa3d8-125">从 `DiscoveryProxyService` 派生 <xref:System.ServiceModel.Discovery.DiscoveryProxy>。</span><span class="sxs-lookup"><span data-stu-id="fa3d8-125">Derive the `DiscoveryProxyService` from <xref:System.ServiceModel.Discovery.DiscoveryProxy>.</span></span> <span data-ttu-id="fa3d8-126">将 `ServiceBehavior` 特性应用到下面的示例所示的类。</span><span class="sxs-lookup"><span data-stu-id="fa3d8-126">Apply the `ServiceBehavior` attribute to the class as shown in the following example.</span></span>

    ```
    // Implement DiscoveryProxy by extending the DiscoveryProxy class and overriding the abstract methods
    [ServiceBehavior(InstanceContextMode = InstanceContextMode.Single, ConcurrencyMode = ConcurrencyMode.Multiple)]
    public class DiscoveryProxyService : DiscoveryProxy
    {
    }
    ```

4.  <span data-ttu-id="fa3d8-127">在 `DiscoveryProxy` 类内，定义一个字典以保存注册的服务。</span><span class="sxs-lookup"><span data-stu-id="fa3d8-127">Inside the `DiscoveryProxy` class define a dictionary to hold the registered services.</span></span>

    ```
    // Repository to store EndpointDiscoveryMetadata.
    Dictionary<EndpointAddress, EndpointDiscoveryMetadata> onlineServices;
    ```

5.  <span data-ttu-id="fa3d8-128">定义一个初始化该字典的构造函数。</span><span class="sxs-lookup"><span data-stu-id="fa3d8-128">Define a constructor that initializes the dictionary.</span></span>

    ```
    public DiscoveryProxyService()
            {
                this.onlineServices = new Dictionary<EndpointAddress, EndpointDiscoveryMetadata>();
            }
    ```

### <a name="to-define-the-methods-used-to-update-the-discovery-proxy-cache"></a><span data-ttu-id="fa3d8-129">定义用于更新发现代理缓存的方法</span><span class="sxs-lookup"><span data-stu-id="fa3d8-129">To define the methods used to update the discovery proxy cache</span></span>

1.  <span data-ttu-id="fa3d8-130">实现 `AddOnlineservice` 方法以向缓存中添加服务。</span><span class="sxs-lookup"><span data-stu-id="fa3d8-130">Implement the `AddOnlineservice` method to add services to the cache.</span></span> <span data-ttu-id="fa3d8-131">每次代理接收到公告消息时，都会调用此方法。</span><span class="sxs-lookup"><span data-stu-id="fa3d8-131">This is called every time the proxy receives an announcement message.</span></span>

    ```
    void AddOnlineService(EndpointDiscoveryMetadata endpointDiscoveryMetadata)
            {
                lock (this.onlineServices)
                {
                    this.onlineServices[endpointDiscoveryMetadata.Address] = endpointDiscoveryMetadata;
                }

                PrintDiscoveryMetadata(endpointDiscoveryMetadata, "Adding");
            }
    ```

2.  <span data-ttu-id="fa3d8-132">实现 `RemoveOnlineService` 方法，该方法用于从缓存删除服务。</span><span class="sxs-lookup"><span data-stu-id="fa3d8-132">Implement the `RemoveOnlineService` method that is used to remove services from the cache.</span></span>

    ```
    void RemoveOnlineService(EndpointDiscoveryMetadata endpointDiscoveryMetadata)
            {
                if (endpointDiscoveryMetadata != null)
                {
                    lock (this.onlineServices)
                    {
                        this.onlineServices.Remove(endpointDiscoveryMetadata.Address);
                    }

                    PrintDiscoveryMetadata(endpointDiscoveryMetadata, "Removing");
                }
            }
    ```

3.  <span data-ttu-id="fa3d8-133">实现 `MatchFromOnlineService` 方法，这些方法尝试将一个服务与字典中的服务相匹配。</span><span class="sxs-lookup"><span data-stu-id="fa3d8-133">Implement the `MatchFromOnlineService` methods that attempt to match a service with a service in the dictionary.</span></span>

    ```
    void MatchFromOnlineService(FindRequestContext findRequestContext)
            {
                lock (this.onlineServices)
                {
                    foreach (EndpointDiscoveryMetadata endpointDiscoveryMetadata in this.onlineServices.Values)
                    {
                        if (findRequestContext.Criteria.IsMatch(endpointDiscoveryMetadata))
                        {
                            findRequestContext.AddMatchingEndpoint(endpointDiscoveryMetadata);
                        }
                    }
                }
            }
    ```

    ```
    EndpointDiscoveryMetadata MatchFromOnlineService(ResolveCriteria criteria)
            {
                EndpointDiscoveryMetadata matchingEndpoint = null;
                lock (this.onlineServices)
                {
                    foreach (EndpointDiscoveryMetadata endpointDiscoveryMetadata in this.onlineServices.Values)
                    {
                        if (criteria.Address == endpointDiscoveryMetadata.Address)
                        {
                            matchingEndpoint = endpointDiscoveryMetadata;
                        }
                    }
                }
                return matchingEndpoint;
            }
    ```

4.  <span data-ttu-id="fa3d8-134">实现 `PrintDiscoveryMetadata` 方法，该方法为用户提供发现代理所执行的操作的控制台文本输出。</span><span class="sxs-lookup"><span data-stu-id="fa3d8-134">Implement the `PrintDiscoveryMetadata` method that provides the user with console text output of what the discovery proxy is doing.</span></span>

    ```
    void PrintDiscoveryMetadata(EndpointDiscoveryMetadata endpointDiscoveryMetadata, string verb)
            {
                Console.WriteLine("\n**** " + verb + " service of the following type from cache. ");
                foreach (XmlQualifiedName contractName in endpointDiscoveryMetadata.ContractTypeNames)
                {
                    Console.WriteLine("** " + contractName.ToString());
                    break;
                }
                Console.WriteLine("**** Operation Completed");
            }
    ```

5.  <span data-ttu-id="fa3d8-135">将以下 AsyncResult 类添加到 DiscoveryProxyService。</span><span class="sxs-lookup"><span data-stu-id="fa3d8-135">Add the following AsyncResult classes to the DiscoveryProxyService.</span></span> <span data-ttu-id="fa3d8-136">这些类用于区分不同的异步操作结果。</span><span class="sxs-lookup"><span data-stu-id="fa3d8-136">These classes are used to differentiate between the different asynchronous operation results.</span></span>

    ```
    sealed class OnOnlineAnnouncementAsyncResult : AsyncResult
            {
                public OnOnlineAnnouncementAsyncResult(AsyncCallback callback, object state)
                    : base(callback, state)
                {
                    this.Complete(true);
                }

                public static void End(IAsyncResult result)
                {
                    AsyncResult.End<OnOnlineAnnouncementAsyncResult>(result);
                }
            }

            sealed class OnOfflineAnnouncementAsyncResult : AsyncResult
            {
                public OnOfflineAnnouncementAsyncResult(AsyncCallback callback, object state)
                    : base(callback, state)
                {
                    this.Complete(true);
                }

                public static void End(IAsyncResult result)
                {
                    AsyncResult.End<OnOfflineAnnouncementAsyncResult>(result);
                }
            }

            sealed class OnFindAsyncResult : AsyncResult
            {
                public OnFindAsyncResult(AsyncCallback callback, object state)
                    : base(callback, state)
                {
                    this.Complete(true);
                }

                public static void End(IAsyncResult result)
                {
                    AsyncResult.End<OnFindAsyncResult>(result);
                }
            }

            sealed class OnResolveAsyncResult : AsyncResult
            {
                EndpointDiscoveryMetadata matchingEndpoint;

                public OnResolveAsyncResult(EndpointDiscoveryMetadata matchingEndpoint, AsyncCallback callback, object state)
                    : base(callback, state)
                {
                    this.matchingEndpoint = matchingEndpoint;
                    this.Complete(true);
                }

                public static EndpointDiscoveryMetadata End(IAsyncResult result)
                {
                    OnResolveAsyncResult thisPtr = AsyncResult.End<OnResolveAsyncResult>(result);
                    return thisPtr.matchingEndpoint;
                }
            }
    ```

### <a name="to-define-the-methods-that-implement-the-discovery-proxy-functionality"></a><span data-ttu-id="fa3d8-137">定义实现发现代理功能的方法</span><span class="sxs-lookup"><span data-stu-id="fa3d8-137">To define the methods that implement the discovery proxy functionality</span></span>

1.  <span data-ttu-id="fa3d8-138">重写 <xref:System.ServiceModel.Discovery.DiscoveryProxy.OnBeginOnlineAnnouncement%2A?displayProperty=nameWithType> 方法。</span><span class="sxs-lookup"><span data-stu-id="fa3d8-138">Override the <xref:System.ServiceModel.Discovery.DiscoveryProxy.OnBeginOnlineAnnouncement%2A?displayProperty=nameWithType> method.</span></span> <span data-ttu-id="fa3d8-139">当发现代理接收到联机公告消息时，将调用此方法。</span><span class="sxs-lookup"><span data-stu-id="fa3d8-139">This method is called when the discovery proxy receives an online announcement message.</span></span>

    ```
    // OnBeginOnlineAnnouncement method is called when a Hello message is received by the Proxy
            protected override IAsyncResult OnBeginOnlineAnnouncement(DiscoveryMessageSequence messageSequence, EndpointDiscoveryMetadata endpointDiscoveryMetadata, AsyncCallback callback, object state)
            {
                this.AddOnlineService(endpointDiscoveryMetadata);
                return new OnOnlineAnnouncementAsyncResult(callback, state);
            }
    ```

2.  <span data-ttu-id="fa3d8-140">重写 <xref:System.ServiceModel.Discovery.DiscoveryProxy.OnEndOnlineAnnouncement%2A?displayProperty=nameWithType> 方法。</span><span class="sxs-lookup"><span data-stu-id="fa3d8-140">Override the <xref:System.ServiceModel.Discovery.DiscoveryProxy.OnEndOnlineAnnouncement%2A?displayProperty=nameWithType> method.</span></span> <span data-ttu-id="fa3d8-141">当发现代理完成处理公告消息时，将调用此方法。</span><span class="sxs-lookup"><span data-stu-id="fa3d8-141">This method is called when the discovery proxy finishes processing an announcement message.</span></span>

    ```
    protected override void OnEndOnlineAnnouncement(IAsyncResult result)
            {
                OnOnlineAnnouncementAsyncResult.End(result);
            }
    ```

3.  <span data-ttu-id="fa3d8-142">重写 <xref:System.ServiceModel.Discovery.DiscoveryProxy.OnBeginOfflineAnnouncement%2A?displayProperty=nameWithType> 方法。</span><span class="sxs-lookup"><span data-stu-id="fa3d8-142">Override the <xref:System.ServiceModel.Discovery.DiscoveryProxy.OnBeginOfflineAnnouncement%2A?displayProperty=nameWithType> method.</span></span> <span data-ttu-id="fa3d8-143">当发现代理接收到脱机公告消息时，将调用此方法。</span><span class="sxs-lookup"><span data-stu-id="fa3d8-143">This method is called with the discovery proxy receives an offline announcement message.</span></span>

    ```
    // OnBeginOfflineAnnouncement method is called when a Bye message is received by the Proxy
            protected override IAsyncResult OnBeginOfflineAnnouncement(DiscoveryMessageSequence messageSequence, EndpointDiscoveryMetadata endpointDiscoveryMetadata, AsyncCallback callback, object state)
            {
                this.RemoveOnlineService(endpointDiscoveryMetadata);
                return new OnOfflineAnnouncementAsyncResult(callback, state);
            }
    ```

4.  <span data-ttu-id="fa3d8-144">重写 <xref:System.ServiceModel.Discovery.DiscoveryProxy.OnEndOfflineAnnouncement%2A?displayProperty=nameWithType> 方法。</span><span class="sxs-lookup"><span data-stu-id="fa3d8-144">Override the <xref:System.ServiceModel.Discovery.DiscoveryProxy.OnEndOfflineAnnouncement%2A?displayProperty=nameWithType> method.</span></span> <span data-ttu-id="fa3d8-145">当发现代理完成处理脱机公告消息时，将调用此方法。</span><span class="sxs-lookup"><span data-stu-id="fa3d8-145">This method is called when the discovery proxy finishes processing an offline announcement message.</span></span>

    ```
    protected override void OnEndOfflineAnnouncement(IAsyncResult result)
            {
                OnOfflineAnnouncementAsyncResult.End(result);
            }
    ```

5.  <span data-ttu-id="fa3d8-146">重写 <xref:System.ServiceModel.Discovery.DiscoveryProxy.OnBeginFind%2A?displayProperty=nameWithType> 方法。</span><span class="sxs-lookup"><span data-stu-id="fa3d8-146">Override the <xref:System.ServiceModel.Discovery.DiscoveryProxy.OnBeginFind%2A?displayProperty=nameWithType> method.</span></span> <span data-ttu-id="fa3d8-147">当发现代理接收到查找请求时，将调用此方法。</span><span class="sxs-lookup"><span data-stu-id="fa3d8-147">This method is called when the discovery proxy receives a find request.</span></span>

    ```
    // OnBeginFind method is called when a Probe request message is received by the Proxy
            protected override IAsyncResult OnBeginFind(FindRequestContext findRequestContext, AsyncCallback callback, object state)
            {
                this.MatchFromOnlineService(findRequestContext);
                return new OnFindAsyncResult(callback, state);
            }
    protected override IAsyncResult OnBeginFind(FindRequest findRequest, AsyncCallback callback, object state)
    {
        Collection<EndpointDiscoveryMetadata> matchingEndpoints = MatchFromCache(findRequest.Criteria);
        return new OnFindAsyncResult(
                    matchingEndpoints,
                    callback,
                    state);
    }
    ```

6.  <span data-ttu-id="fa3d8-148">重写 <xref:System.ServiceModel.Discovery.DiscoveryProxy.OnEndFind%2A?displayProperty=nameWithType> 方法。</span><span class="sxs-lookup"><span data-stu-id="fa3d8-148">Override the <xref:System.ServiceModel.Discovery.DiscoveryProxy.OnEndFind%2A?displayProperty=nameWithType> method.</span></span> <span data-ttu-id="fa3d8-149">当发现代理完成查找请求的处理时，将调用此方法。</span><span class="sxs-lookup"><span data-stu-id="fa3d8-149">This method is called when the discovery proxy finishes processing a find request.</span></span>

    ```
    protected override void OnEndFind(IAsyncResult result)
            {
                OnFindAsyncResult.End(result);
            }
    ```

7.  <span data-ttu-id="fa3d8-150">重写 <xref:System.ServiceModel.Discovery.DiscoveryProxy.OnBeginResolve%2A?displayProperty=nameWithType> 方法。</span><span class="sxs-lookup"><span data-stu-id="fa3d8-150">Override the <xref:System.ServiceModel.Discovery.DiscoveryProxy.OnBeginResolve%2A?displayProperty=nameWithType> method.</span></span> <span data-ttu-id="fa3d8-151">当发现代理接收到解决消息时，将调用此方法。</span><span class="sxs-lookup"><span data-stu-id="fa3d8-151">This method is called when the discovery proxy receives a resolve message.</span></span>

    ```
    // OnBeginFind method is called when a Resolve request message is received by the Proxy
            protected override IAsyncResult OnBeginResolve(ResolveCriteria resolveCriteria, AsyncCallback callback, object state)
            {
                return new OnResolveAsyncResult(this.MatchFromOnlineService(resolveCriteria), callback, state);
            }
    protected override IAsyncResult OnBeginResolve(ResolveRequest resolveRequest, AsyncCallback callback, object state)
    {
        return new OnResolveAsyncResult(
            this.proxy.MatchFromOnlineService(resolveRequest.Criteria),
            callback,
            state);
    }
    ```

8.  <span data-ttu-id="fa3d8-152">重写 <xref:System.ServiceModel.Discovery.DiscoveryProxy.OnEndResolve%2A?displayProperty=nameWithType> 方法。</span><span class="sxs-lookup"><span data-stu-id="fa3d8-152">Override the <xref:System.ServiceModel.Discovery.DiscoveryProxy.OnEndResolve%2A?displayProperty=nameWithType> method.</span></span> <span data-ttu-id="fa3d8-153">当发现代理完成处理解决消息时，将调用此方法。</span><span class="sxs-lookup"><span data-stu-id="fa3d8-153">This method is called when the discovery proxy finishes processing a resolve message.</span></span>

    ```
    protected override EndpointDiscoveryMetadata OnEndResolve(IAsyncResult result)
    {
        return OnResolveAsyncResult.End(result);
    }
    ```

 <span data-ttu-id="fa3d8-154">OnBegin.</span><span class="sxs-lookup"><span data-stu-id="fa3d8-154">The OnBegin..</span></span> <span data-ttu-id="fa3d8-155">/ OnEnd.</span><span class="sxs-lookup"><span data-stu-id="fa3d8-155">/ OnEnd..</span></span> <span data-ttu-id="fa3d8-156">方法提供后续发现操作的逻辑。</span><span class="sxs-lookup"><span data-stu-id="fa3d8-156">methods provide the logic for the subsequent discovery operations.</span></span> <span data-ttu-id="fa3d8-157">例如，<xref:System.ServiceModel.Discovery.DiscoveryProxy.OnBeginFind%2A> 和 <xref:System.ServiceModel.Discovery.DiscoveryProxy.OnEndFind%2A> 方法实现发现代理的查找逻辑。</span><span class="sxs-lookup"><span data-stu-id="fa3d8-157">For example the <xref:System.ServiceModel.Discovery.DiscoveryProxy.OnBeginFind%2A> and <xref:System.ServiceModel.Discovery.DiscoveryProxy.OnEndFind%2A> methods implement the find logic for discovery proxy.</span></span> <span data-ttu-id="fa3d8-158">当发现代理接收到探测消息时，将执行这些方法以便向客户端回发响应。</span><span class="sxs-lookup"><span data-stu-id="fa3d8-158">When the discovery proxy receives a probe message these methods are executed to send a response back to the client.</span></span> <span data-ttu-id="fa3d8-159">您可以根据需要修改查找逻辑，例如，可以将按算法实现的自定义范围匹配或应用程序特定 XML 元数据分析合并到查找操作中。</span><span class="sxs-lookup"><span data-stu-id="fa3d8-159">You may modify the find logic as you wish, for example you can incorporate custom scope matching by algorithms or application specific XML metadata parsing as part of your find operation.</span></span>

### <a name="to-implement-the-asyncresult-class"></a><span data-ttu-id="fa3d8-160">实现 AsyncResult 类</span><span class="sxs-lookup"><span data-stu-id="fa3d8-160">To implement the AsyncResult class</span></span>

1.  <span data-ttu-id="fa3d8-161">定义用于派生各种异步结果类的抽象基类 AsyncResult。</span><span class="sxs-lookup"><span data-stu-id="fa3d8-161">Define the abstract base class AsyncResult which is used to derive the various async result classes.</span></span>

2.  <span data-ttu-id="fa3d8-162">创建一个名为 AsyncResult.cs 的新代码文件。</span><span class="sxs-lookup"><span data-stu-id="fa3d8-162">Create a new code file called AsyncResult.cs.</span></span>

3.  <span data-ttu-id="fa3d8-163">将以下 `using` 语句添加到 AsyncResult.cs。</span><span class="sxs-lookup"><span data-stu-id="fa3d8-163">Add the following `using` statements to AsyncResult.cs.</span></span>

    ```
    using System;
    using System.Threading;
    ```

4.  <span data-ttu-id="fa3d8-164">添加以下 AsyncResult 类。</span><span class="sxs-lookup"><span data-stu-id="fa3d8-164">Add the following AsyncResult class.</span></span>

    ```
    abstract class AsyncResult : IAsyncResult
        {
            AsyncCallback callback;
            bool completedSynchronously;
            bool endCalled;
            Exception exception;
            bool isCompleted;
            ManualResetEvent manualResetEvent;
            object state;
            object thisLock;

            protected AsyncResult(AsyncCallback callback, object state)
            {
                this.callback = callback;
                this.state = state;
                this.thisLock = new object();
            }

            public object AsyncState
            {
                get
                {
                    return state;
                }
            }

            public WaitHandle AsyncWaitHandle
            {
                get
                {
                    if (manualResetEvent != null)
                    {
                        return manualResetEvent;
                    }
                    lock (ThisLock)
                    {
                        if (manualResetEvent == null)
                        {
                            manualResetEvent = new ManualResetEvent(isCompleted);
                        }
                    }
                    return manualResetEvent;
                }
            }

            public bool CompletedSynchronously
            {
                get
                {
                    return completedSynchronously;
                }
            }

            public bool IsCompleted
            {
                get
                {
                    return isCompleted;
                }
            }

            object ThisLock
            {
                get
                {
                    return this.thisLock;
                }
            }

            protected static TAsyncResult End<TAsyncResult>(IAsyncResult result)
                where TAsyncResult : AsyncResult
            {
                if (result == null)
                {
                    throw new ArgumentNullException("result");
                }

                TAsyncResult asyncResult = result as TAsyncResult;

                if (asyncResult == null)
                {
                    throw new ArgumentException("Invalid async result.", "result");
                }

                if (asyncResult.endCalled)
                {
                    throw new InvalidOperationException("Async object already ended.");
                }

                asyncResult.endCalled = true;

                if (!asyncResult.isCompleted)
                {
                    asyncResult.AsyncWaitHandle.WaitOne();
                }

                if (asyncResult.manualResetEvent != null)
                {
                    asyncResult.manualResetEvent.Close();
                }

                if (asyncResult.exception != null)
                {
                    throw asyncResult.exception;
                }

                return asyncResult;
            }

            protected void Complete(bool completedSynchronously)
            {
                if (isCompleted)
                {
                    throw new InvalidOperationException("This async result is already completed.");
                }

                this.completedSynchronously = completedSynchronously;

                if (completedSynchronously)
                {
                    this.isCompleted = true;
                }
                else
                {
                    lock (ThisLock)
                    {
                        this.isCompleted = true;
                        if (this.manualResetEvent != null)
                        {
                            this.manualResetEvent.Set();
                        }
                    }
                }

                if (callback != null)
                {
                    callback(this);
                }
            }

            protected void Complete(bool completedSynchronously, Exception exception)
            {
                this.exception = exception;
                Complete(completedSynchronously);
            }
        }
    ```

### <a name="to-host-the-discoveryproxy"></a><span data-ttu-id="fa3d8-165">承载 DiscoveryProxy</span><span class="sxs-lookup"><span data-stu-id="fa3d8-165">To host the DiscoveryProxy</span></span>

1.  <span data-ttu-id="fa3d8-166">打开 DiscoveryProxyExample 项目中的 Program.cs 文件。</span><span class="sxs-lookup"><span data-stu-id="fa3d8-166">Open the Program.cs file in the DiscoveryProxyExample project.</span></span>

2.  <span data-ttu-id="fa3d8-167">添加下面的 `using` 语句。</span><span class="sxs-lookup"><span data-stu-id="fa3d8-167">Add the following `using` statements.</span></span>

    ```
    using System;
    using System.ServiceModel;
    using System.ServiceModel.Discovery;
    ```

3.  <span data-ttu-id="fa3d8-168">在 `Main()` 方法中，添加下面的代码。</span><span class="sxs-lookup"><span data-stu-id="fa3d8-168">Within the `Main()` method, add the following code.</span></span> <span data-ttu-id="fa3d8-169">这将创建 `DiscoveryProxy` 类的一个实例。</span><span class="sxs-lookup"><span data-stu-id="fa3d8-169">This creates an instance of the `DiscoveryProxy` class.</span></span>

    ```
    Uri probeEndpointAddress = new Uri("net.tcp://localhost:8001/Probe");
                Uri announcementEndpointAddress = new Uri("net.tcp://localhost:9021/Announcement");

                // Host the DiscoveryProxy service
                ServiceHost proxyServiceHost = new ServiceHost(new DiscoveryProxyService());
    ```

4.  <span data-ttu-id="fa3d8-170">接下来，将以下代码添加到发现终结点和公告终结点。</span><span class="sxs-lookup"><span data-stu-id="fa3d8-170">Next add the following code to add a discovery endpoint and an announcement endpoint.</span></span>

    ```
    try
              {
                  // Add DiscoveryEndpoint to receive Probe and Resolve messages
                  DiscoveryEndpoint discoveryEndpoint = new DiscoveryEndpoint(new NetTcpBinding(), new EndpointAddress(probeEndpointAddress));
                  discoveryEndpoint.IsSystemEndpoint = false;

                  // Add AnnouncementEndpoint to receive Hello and Bye announcement messages
                  AnnouncementEndpoint announcementEndpoint = new AnnouncementEndpoint(new NetTcpBinding(), new EndpointAddress(announcementEndpointAddress));

                  proxyServiceHost.AddServiceEndpoint(discoveryEndpoint);
                  proxyServiceHost.AddServiceEndpoint(announcementEndpoint);

                  proxyServiceHost.Open();

                  Console.WriteLine("Proxy Service started.");
                  Console.WriteLine();
                  Console.WriteLine("Press <ENTER> to terminate the service.");
                  Console.WriteLine();
                  Console.ReadLine();

                  proxyServiceHost.Close();
              }
              catch (CommunicationException e)
              {
                  Console.WriteLine(e.Message);
              }
              catch (TimeoutException e)
              {
                  Console.WriteLine(e.Message);
              }

              if (proxyServiceHost.State != CommunicationState.Closed)
              {
                  Console.WriteLine("Aborting the service...");
                  proxyServiceHost.Abort();
              }
    ```

 <span data-ttu-id="fa3d8-171">您已完成实现发现代理。</span><span class="sxs-lookup"><span data-stu-id="fa3d8-171">You have completed implementing the discovery proxy.</span></span> <span data-ttu-id="fa3d8-172">继续阅读[如何：实现向发现代理注册的可发现服务](../../../../docs/framework/wcf/feature-details/discoverable-service-that-registers-with-the-discovery-proxy.md)。</span><span class="sxs-lookup"><span data-stu-id="fa3d8-172">Continue on to [How to: Implement a Discoverable Service that Registers with the Discovery Proxy](../../../../docs/framework/wcf/feature-details/discoverable-service-that-registers-with-the-discovery-proxy.md).</span></span>

## <a name="example"></a><span data-ttu-id="fa3d8-173">示例</span><span class="sxs-lookup"><span data-stu-id="fa3d8-173">Example</span></span>
 <span data-ttu-id="fa3d8-174">下面是本主题中使用的代码的完整清单。</span><span class="sxs-lookup"><span data-stu-id="fa3d8-174">This is the full listing of the code used in this topic.</span></span>

```
// DiscoveryProxy.cs
//----------------------------------------------------------------
// Copyright (c) Microsoft Corporation.  All rights reserved.
//----------------------------------------------------------------

using System;
using System.Collections.Generic;
using System.ServiceModel;
using System.ServiceModel.Discovery;
using System.Xml;

namespace Microsoft.Samples.Discovery
{
    // Implement DiscoveryProxy by extending the DiscoveryProxy class and overriding the abstract methods
    [ServiceBehavior(InstanceContextMode = InstanceContextMode.Single, ConcurrencyMode = ConcurrencyMode.Multiple)]
    public class DiscoveryProxyService : DiscoveryProxy
    {
        // Repository to store EndpointDiscoveryMetadata. A database or a flat file could also be used instead.
        Dictionary<EndpointAddress, EndpointDiscoveryMetadata> onlineServices;

        public DiscoveryProxyService()
        {
            this.onlineServices = new Dictionary<EndpointAddress, EndpointDiscoveryMetadata>();
        }

        // OnBeginOnlineAnnouncement method is called when a Hello message is received by the Proxy
        protected override IAsyncResult OnBeginOnlineAnnouncement(DiscoveryMessageSequence messageSequence, EndpointDiscoveryMetadata endpointDiscoveryMetadata, AsyncCallback callback, object state)
        {
            this.AddOnlineService(endpointDiscoveryMetadata);
            return new OnOnlineAnnouncementAsyncResult(callback, state);
        }

        protected override void OnEndOnlineAnnouncement(IAsyncResult result)
        {
            OnOnlineAnnouncementAsyncResult.End(result);
        }

        // OnBeginOfflineAnnouncement method is called when a Bye message is received by the Proxy
        protected override IAsyncResult OnBeginOfflineAnnouncement(DiscoveryMessageSequence messageSequence, EndpointDiscoveryMetadata endpointDiscoveryMetadata, AsyncCallback callback, object state)
        {
            this.RemoveOnlineService(endpointDiscoveryMetadata);
            return new OnOfflineAnnouncementAsyncResult(callback, state);
        }

        protected override void OnEndOfflineAnnouncement(IAsyncResult result)
        {
            OnOfflineAnnouncementAsyncResult.End(result);
        }

        // OnBeginFind method is called when a Probe request message is received by the Proxy
        protected override IAsyncResult OnBeginFind(FindRequestContext findRequestContext, AsyncCallback callback, object state)
        {
            this.MatchFromOnlineService(findRequestContext);
            return new OnFindAsyncResult(callback, state);
        }

        protected override void OnEndFind(IAsyncResult result)
        {
            OnFindAsyncResult.End(result);
        }

        // OnBeginFind method is called when a Resolve request message is received by the Proxy
        protected override IAsyncResult OnBeginResolve(ResolveCriteria resolveCriteria, AsyncCallback callback, object state)
        {
            return new OnResolveAsyncResult(this.MatchFromOnlineService(resolveCriteria), callback, state);
        }

        protected override EndpointDiscoveryMetadata OnEndResolve(IAsyncResult result)
        {
            return OnResolveAsyncResult.End(result);
        }

        // The following are helper methods required by the Proxy implementation
        void AddOnlineService(EndpointDiscoveryMetadata endpointDiscoveryMetadata)
        {
            lock (this.onlineServices)
            {
                this.onlineServices[endpointDiscoveryMetadata.Address] = endpointDiscoveryMetadata;
            }

            PrintDiscoveryMetadata(endpointDiscoveryMetadata, "Adding");
        }

        void RemoveOnlineService(EndpointDiscoveryMetadata endpointDiscoveryMetadata)
        {
            if (endpointDiscoveryMetadata != null)
            {
                lock (this.onlineServices)
                {
                    this.onlineServices.Remove(endpointDiscoveryMetadata.Address);
                }

                PrintDiscoveryMetadata(endpointDiscoveryMetadata, "Removing");
            }
        }

        void MatchFromOnlineService(FindRequestContext findRequestContext)
        {
            lock (this.onlineServices)
            {
                foreach (EndpointDiscoveryMetadata endpointDiscoveryMetadata in this.onlineServices.Values)
                {
                    if (findRequestContext.Criteria.IsMatch(endpointDiscoveryMetadata))
                    {
                        findRequestContext.AddMatchingEndpoint(endpointDiscoveryMetadata);
                    }
                }
            }
        }

        EndpointDiscoveryMetadata MatchFromOnlineService(ResolveCriteria criteria)
        {
            EndpointDiscoveryMetadata matchingEndpoint = null;
            lock (this.onlineServices)
            {
                foreach (EndpointDiscoveryMetadata endpointDiscoveryMetadata in this.onlineServices.Values)
                {
                    if (criteria.Address == endpointDiscoveryMetadata.Address)
                    {
                        matchingEndpoint = endpointDiscoveryMetadata;
                    }
                }
            }
            return matchingEndpoint;
        }

        void PrintDiscoveryMetadata(EndpointDiscoveryMetadata endpointDiscoveryMetadata, string verb)
        {
            Console.WriteLine("\n**** " + verb + " service of the following type from cache. ");
            foreach (XmlQualifiedName contractName in endpointDiscoveryMetadata.ContractTypeNames)
            {
                Console.WriteLine("** " + contractName.ToString());
                break;
            }
            Console.WriteLine("**** Operation Completed");
        }

        sealed class OnOnlineAnnouncementAsyncResult : AsyncResult
        {
            public OnOnlineAnnouncementAsyncResult(AsyncCallback callback, object state)
                : base(callback, state)
            {
                this.Complete(true);
            }

            public static void End(IAsyncResult result)
            {
                AsyncResult.End<OnOnlineAnnouncementAsyncResult>(result);
            }
        }

        sealed class OnOfflineAnnouncementAsyncResult : AsyncResult
        {
            public OnOfflineAnnouncementAsyncResult(AsyncCallback callback, object state)
                : base(callback, state)
            {
                this.Complete(true);
            }

            public static void End(IAsyncResult result)
            {
                AsyncResult.End<OnOfflineAnnouncementAsyncResult>(result);
            }
        }

        sealed class OnFindAsyncResult : AsyncResult
        {
            public OnFindAsyncResult(AsyncCallback callback, object state)
                : base(callback, state)
            {
                this.Complete(true);
            }

            public static void End(IAsyncResult result)
            {
                AsyncResult.End<OnFindAsyncResult>(result);
            }
        }

        sealed class OnResolveAsyncResult : AsyncResult
        {
            EndpointDiscoveryMetadata matchingEndpoint;

            public OnResolveAsyncResult(EndpointDiscoveryMetadata matchingEndpoint, AsyncCallback callback, object state)
                : base(callback, state)
            {
                this.matchingEndpoint = matchingEndpoint;
                this.Complete(true);
            }

            public static EndpointDiscoveryMetadata End(IAsyncResult result)
            {
                OnResolveAsyncResult thisPtr = AsyncResult.End<OnResolveAsyncResult>(result);
                return thisPtr.matchingEndpoint;
            }
        }
    }
}
```

```
// AsyncResult.cs
//----------------------------------------------------------------
// Copyright (c) Microsoft Corporation.  All rights reserved.
//----------------------------------------------------------------

using System;
using System.Threading;

namespace Microsoft.Samples.Discovery
{
    abstract class AsyncResult : IAsyncResult
    {
        AsyncCallback callback;
        bool completedSynchronously;
        bool endCalled;
        Exception exception;
        bool isCompleted;
        ManualResetEvent manualResetEvent;
        object state;
        object thisLock;

        protected AsyncResult(AsyncCallback callback, object state)
        {
            this.callback = callback;
            this.state = state;
            this.thisLock = new object();
        }

        public object AsyncState
        {
            get
            {
                return state;
            }
        }

        public WaitHandle AsyncWaitHandle
        {
            get
            {
                if (manualResetEvent != null)
                {
                    return manualResetEvent;
                }
                lock (ThisLock)
                {
                    if (manualResetEvent == null)
                    {
                        manualResetEvent = new ManualResetEvent(isCompleted);
                    }
                }
                return manualResetEvent;
            }
        }

        public bool CompletedSynchronously
        {
            get
            {
                return completedSynchronously;
            }
        }

        public bool IsCompleted
        {
            get
            {
                return isCompleted;
            }
        }

        object ThisLock
        {
            get
            {
                return this.thisLock;
            }
        }

        protected static TAsyncResult End<TAsyncResult>(IAsyncResult result)
            where TAsyncResult : AsyncResult
        {
            if (result == null)
            {
                throw new ArgumentNullException("result");
            }

            TAsyncResult asyncResult = result as TAsyncResult;

            if (asyncResult == null)
            {
                throw new ArgumentException("Invalid async result.", "result");
            }

            if (asyncResult.endCalled)
            {
                throw new InvalidOperationException("Async object already ended.");
            }

            asyncResult.endCalled = true;

            if (!asyncResult.isCompleted)
            {
                asyncResult.AsyncWaitHandle.WaitOne();
            }

            if (asyncResult.manualResetEvent != null)
            {
                asyncResult.manualResetEvent.Close();
            }

            if (asyncResult.exception != null)
            {
                throw asyncResult.exception;
            }

            return asyncResult;
        }

        protected void Complete(bool completedSynchronously)
        {
            if (isCompleted)
            {
                throw new InvalidOperationException("This async result is already completed.");
            }

            this.completedSynchronously = completedSynchronously;

            if (completedSynchronously)
            {
                this.isCompleted = true;
            }
            else
            {
                lock (ThisLock)
                {
                    this.isCompleted = true;
                    if (this.manualResetEvent != null)
                    {
                        this.manualResetEvent.Set();
                    }
                }
            }

            if (callback != null)
            {
                callback(this);
            }
        }

        protected void Complete(bool completedSynchronously, Exception exception)
        {
            this.exception = exception;
            Complete(completedSynchronously);
        }
    }
}
```

```
// program.cs
//----------------------------------------------------------------
// Copyright (c) Microsoft Corporation.  All rights reserved.
//----------------------------------------------------------------

using System;
using System.ServiceModel;
using System.ServiceModel.Discovery;

namespace Microsoft.Samples.Discovery
{
    class Program
    {
        public static void Main()
        {
            Uri probeEndpointAddress = new Uri("net.tcp://localhost:8001/Probe");
            Uri announcementEndpointAddress = new Uri("net.tcp://localhost:9021/Announcement");

            // Host the DiscoveryProxy service
            ServiceHost proxyServiceHost = new ServiceHost(new DiscoveryProxyService());

            try
            {
                // Add DiscoveryEndpoint to receive Probe and Resolve messages
                DiscoveryEndpoint discoveryEndpoint = new DiscoveryEndpoint(new NetTcpBinding(), new EndpointAddress(probeEndpointAddress));
                discoveryEndpoint.IsSystemEndpoint = false;

                // Add AnnouncementEndpoint to receive Hello and Bye announcement messages
                AnnouncementEndpoint announcementEndpoint = new AnnouncementEndpoint(new NetTcpBinding(), new EndpointAddress(announcementEndpointAddress));

                proxyServiceHost.AddServiceEndpoint(discoveryEndpoint);
                proxyServiceHost.AddServiceEndpoint(announcementEndpoint);

                proxyServiceHost.Open();

                Console.WriteLine("Proxy Service started.");
                Console.WriteLine();
                Console.WriteLine("Press <ENTER> to terminate the service.");
                Console.WriteLine();
                Console.ReadLine();

                proxyServiceHost.Close();
            }
            catch (CommunicationException e)
            {
                Console.WriteLine(e.Message);
            }
            catch (TimeoutException e)
            {
                Console.WriteLine(e.Message);
            }

            if (proxyServiceHost.State != CommunicationState.Closed)
            {
                Console.WriteLine("Aborting the service...");
                proxyServiceHost.Abort();
            }
        }
    }
}
```

## <a name="see-also"></a><span data-ttu-id="fa3d8-175">请参阅</span><span class="sxs-lookup"><span data-stu-id="fa3d8-175">See also</span></span>

- [<span data-ttu-id="fa3d8-176">WCF 发现概述</span><span class="sxs-lookup"><span data-stu-id="fa3d8-176">WCF Discovery Overview</span></span>](../../../../docs/framework/wcf/feature-details/wcf-discovery-overview.md)
- [<span data-ttu-id="fa3d8-177">如何：实现向发现代理注册的可发现服务</span><span class="sxs-lookup"><span data-stu-id="fa3d8-177">How to: Implement a Discoverable Service that Registers with the Discovery Proxy</span></span>](../../../../docs/framework/wcf/feature-details/discoverable-service-that-registers-with-the-discovery-proxy.md)
- [<span data-ttu-id="fa3d8-178">如何：实现使用发现代理查找服务的客户端应用程序</span><span class="sxs-lookup"><span data-stu-id="fa3d8-178">How to: Implement a Client Application that Uses the Discovery Proxy to Find a Service</span></span>](../../../../docs/framework/wcf/feature-details/client-app-discovery-proxy-to-find-a-service.md)
- [<span data-ttu-id="fa3d8-179">如何：测试发现代理</span><span class="sxs-lookup"><span data-stu-id="fa3d8-179">How to: Test the Discovery Proxy</span></span>](../../../../docs/framework/wcf/feature-details/how-to-test-the-discovery-proxy.md)