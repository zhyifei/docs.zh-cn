---
title: "如何：为应用程序设置基于位置的缓存策略"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- expliciting defining cache behavior
- location-based cache policies
- local cache
- request cache policies
- cache [.NET Framework], location-based policies
ms.assetid: 683bb88e-3411-4f46-9686-3411b6ba511c
caps.latest.revision: "10"
author: mcleblanc
ms.author: markl
manager: markl
ms.openlocfilehash: a145bf30930c9be81dc92f3a9f1eebda046b7e8e
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-set-a-location-based-cache-policy-for-an-application"></a><span data-ttu-id="72038-102">如何：为应用程序设置基于位置的缓存策略</span><span class="sxs-lookup"><span data-stu-id="72038-102">How to: Set a Location-Based Cache Policy for an Application</span></span>
<span data-ttu-id="72038-103">基于位置的缓存策略允许应用程序基于所请求资源的位置显式定义缓存行为。</span><span class="sxs-lookup"><span data-stu-id="72038-103">Location-based cache policies allow an application to explicitly define caching behavior based on the location of the requested resource.</span></span> <span data-ttu-id="72038-104">本主题演示如何以编程方式设置缓存策略。</span><span class="sxs-lookup"><span data-stu-id="72038-104">This topic demonstrates setting the cache policy programmatically.</span></span> <span data-ttu-id="72038-105">有关使用配置文件为应用程序设置策略的信息，请参阅 [ \<requestCaching > 元素（网络设置）](../../../docs/framework/configure-apps/file-schema/network/requestcaching-element-network-settings.md)。</span><span class="sxs-lookup"><span data-stu-id="72038-105">For information on setting the policy for an application using the configuration files, see [\<requestCaching> Element (Network Settings)](../../../docs/framework/configure-apps/file-schema/network/requestcaching-element-network-settings.md).</span></span>  
  
### <a name="to-set-a-location-based-cache-policy-for-an-application"></a><span data-ttu-id="72038-106">为应用程序设置基于位置的缓存策略</span><span class="sxs-lookup"><span data-stu-id="72038-106">To set a location-based cache policy for an application</span></span>  
  
1.  <span data-ttu-id="72038-107">创建 <xref:System.Net.Cache.RequestCachePolicy> 或 <xref:System.Net.Cache.HttpRequestCachePolicy> 对象。</span><span class="sxs-lookup"><span data-stu-id="72038-107">Create a <xref:System.Net.Cache.RequestCachePolicy> or <xref:System.Net.Cache.HttpRequestCachePolicy> object.</span></span>  
  
2.  <span data-ttu-id="72038-108">将策略对象设置为应用程序域的默认对象。</span><span class="sxs-lookup"><span data-stu-id="72038-108">Set the policy object as the default for the application domain.</span></span>  
  
### <a name="to-set-a-policy-that-takes-requested-resources-from-a-cache"></a><span data-ttu-id="72038-109">设置获取来自缓存的请求资源的策略</span><span class="sxs-lookup"><span data-stu-id="72038-109">To set a policy that takes requested resources from a cache</span></span>  
  
-   <span data-ttu-id="72038-110">创建获取来自缓存的请求资源的策略（若可用），否则通过将缓存级别设置为 <xref:System.Net.Cache.HttpRequestCacheLevel.CacheIfAvailable> 向服务器发送请求。</span><span class="sxs-lookup"><span data-stu-id="72038-110">Create a policy that takes requested resources from a cache if available, and otherwise, sends requests to the server, by setting the cache level to <xref:System.Net.Cache.HttpRequestCacheLevel.CacheIfAvailable>.</span></span> <span data-ttu-id="72038-111">可以由客户端和服务器之间的任何缓存实现请求，包括远程缓存。</span><span class="sxs-lookup"><span data-stu-id="72038-111">A request can be fulfilled by any cache between the client and server, including remote caches.</span></span>  
  
    ```csharp  
    public static void UseCacheIfAvailable()  
    {  
        HttpRequestCachePolicy policy = new HttpRequestCachePolicy  
            (HttpRequestCacheLevel.CacheIfAvailable);  
        HttpWebRequest.DefaultCachePolicy = policy;  
    }  
    ```  
  
    ```vb  
    Public Shared Sub UseCacheIfAvailable()  
        Dim policy As New HttpRequestCachePolicy _  
             (HttpRequestCacheLevel.CacheIfAvailable)  
        HttpWebRequest.DefaultCachePolicy = policy  
    End Sub  
    ```  
  
### <a name="to-set-a-policy-that-prevents-any-cache-from-supplying-resources"></a><span data-ttu-id="72038-112">设置防止任何缓存提供资源的策略</span><span class="sxs-lookup"><span data-stu-id="72038-112">To set a policy that prevents any cache from supplying resources</span></span>  
  
-   <span data-ttu-id="72038-113">通过将缓存级别设置为 <xref:System.Net.Cache.HttpRequestCacheLevel.NoCacheNoStore>，创建防止缓存提供请求的资源的策略。</span><span class="sxs-lookup"><span data-stu-id="72038-113">Create a policy that prevents any cache from supplying requested resources by setting the cache level to <xref:System.Net.Cache.HttpRequestCacheLevel.NoCacheNoStore>.</span></span> <span data-ttu-id="72038-114">此策略级别从本地缓存中删除资源（如果存在），并指示远程缓存也应删除资源。</span><span class="sxs-lookup"><span data-stu-id="72038-114">This policy level removes the resource from the local cache if it is present and indicates to remote caches that they should also remove the resource.</span></span>  
  
    ```csharp  
    public static void DoNotUseCache()  
    {  
    HttpRequestCachePolicy policy = new HttpRequestCachePolicy   
            (HttpRequestCacheLevel.NoCacheNoStore);  
        HttpWebRequest.DefaultCachePolicy = policy;  
    }  
    ```  
  
    ```vb  
    Public Shared Sub DoNotUseCache()  
        Dim policy As New HttpRequestCachePolicy _  
            (HttpRequestCacheLevel.NoCacheNoStore)  
        HttpWebRequest.DefaultCachePolicy = policy  
    End Sub  
    ```  
  
### <a name="to-set-a-policy-that-returns-requested-resources-only-if-they-are-in-the-local-cache"></a><span data-ttu-id="72038-115">设置仅当请求的资源在本地缓存中时返回请求的资源的策略</span><span class="sxs-lookup"><span data-stu-id="72038-115">To set a policy that returns requested resources only if they are in the local cache</span></span>  
  
-   <span data-ttu-id="72038-116">通过将缓存级别设置为 <xref:System.Net.Cache.HttpRequestCacheLevel.CacheOnly>，创建仅当请求的资源在本地缓存中时返回请求的资源的策略。</span><span class="sxs-lookup"><span data-stu-id="72038-116">Create a policy that returns requested resources only if they are in the local cache by setting the cache level to <xref:System.Net.Cache.HttpRequestCacheLevel.CacheOnly>.</span></span> <span data-ttu-id="72038-117">如果请求的资源不在缓存中，将引发 <xref:System.Net.WebException> 异常。</span><span class="sxs-lookup"><span data-stu-id="72038-117">If the requested resource is not in the cache, a <xref:System.Net.WebException> exception is thrown.</span></span>  
  
    ```csharp  
    public static void OnlyUseCache()  
    {  
        HttpRequestCachePolicy policy = new HttpRequestCachePolicy   
            (HttpRequestCacheLevel.CacheOnly);  
        HttpWebRequest.DefaultCachePolicy = policy;  
    }  
    ```  
  
    ```vb  
    Public Shared Sub OnlyUseCache()  
        Dim policy As New HttpRequestCachePolicy _  
            (HttpRequestCacheLevel.CacheOnly)  
        HttpWebRequest.DefaultCachePolicy = policy  
    End Sub  
    ```  
  
### <a name="to-set-a-policy-that-prevents-the-local-cache-from-supplying-resources"></a><span data-ttu-id="72038-118">设置防止本地缓存提供资源的策略</span><span class="sxs-lookup"><span data-stu-id="72038-118">To set a policy that prevents the local cache from supplying resources</span></span>  
  
-   <span data-ttu-id="72038-119">通过将缓存级别设置为 <xref:System.Net.Cache.HttpRequestCacheLevel.Refresh>，创建防止本地缓存提供请求的资源的策略。</span><span class="sxs-lookup"><span data-stu-id="72038-119">Create a policy that prevents the local cache from supplying requested resources by setting the cache level to <xref:System.Net.Cache.HttpRequestCacheLevel.Refresh>.</span></span> <span data-ttu-id="72038-120">如果请求的资源是中间缓存并已成功重新验证，中间缓存可提供请求的资源。</span><span class="sxs-lookup"><span data-stu-id="72038-120">If the requested resource is in an intermediate cache and is successfully revalidated, the intermediate cache can supply the requested resource.</span></span>  
  
    ```csharp  
    public static void DoNotUseLocalCache()  
    {  
     HttpRequestCachePolicy policy = new HttpRequestCachePolicy   
            (HttpRequestCacheLevel.Refresh);  
        HttpWebRequest.DefaultCachePolicy = policy;  
    }  
    ```  
  
    ```vb  
    Public Shared Sub DoNotUseLocalCache()  
        Dim policy As New HttpRequestCachePolicy _  
            (HttpRequestCacheLevel.Refresh)  
        HttpWebRequest.DefaultCachePolicy = policy  
    End Sub  
    ```  
  
### <a name="to-set-a-policy-that-prevents-any-cache-from-supplying-requested-resources"></a><span data-ttu-id="72038-121">设置防止任何缓存提供请求的资源的策略</span><span class="sxs-lookup"><span data-stu-id="72038-121">To set a policy that prevents any cache from supplying requested resources</span></span>  
  
-   <span data-ttu-id="72038-122">通过将缓存级别设置为 <xref:System.Net.Cache.HttpRequestCacheLevel.Reload>，创建防止缓存提供请求的资源的策略。</span><span class="sxs-lookup"><span data-stu-id="72038-122">Create a policy that prevents any cache from supplying requested resources by setting the cache level to <xref:System.Net.Cache.HttpRequestCacheLevel.Reload>.</span></span> <span data-ttu-id="72038-123">服务器返回的资源可以存储在缓存中。</span><span class="sxs-lookup"><span data-stu-id="72038-123">The resource returned by the server can be stored in the cache.</span></span>  
  
    ```csharp  
    public static void SendToServer()  
    {  
    HttpRequestCachePolicy policy = new HttpRequestCachePolicy   
            (HttpRequestCacheLevel.Reload);  
        HttpWebRequest.DefaultCachePolicy = policy;  
    }  
    ```  
  
    ```vb  
    Public Shared Sub SendToServer()  
        Dim policy As New HttpRequestCachePolicy _  
            (HttpRequestCacheLevel.Reload)  
        HttpWebRequest.DefaultCachePolicy = policy  
    End Sub  
    ```  
  
### <a name="to-set-a-policy-that-allows-any-cache-to-supply-requested-resources-if-the-resource-on-the-server-is-not-newer-than-the-cached-copy"></a><span data-ttu-id="72038-124">设置当服务器上的资源不比缓存副本新时，允许任何缓存提供请求的资源的策略</span><span class="sxs-lookup"><span data-stu-id="72038-124">To set a policy that allows any cache to supply requested resources if the resource on the server is not newer than the cached copy</span></span>  
  
-   <span data-ttu-id="72038-125">通过将缓存级别设置为 <xref:System.Net.Cache.HttpRequestCacheLevel.Revalidate>，创建当服务器上的资源不比缓存副本新时，允许任何缓存提供请求的资源的策略。</span><span class="sxs-lookup"><span data-stu-id="72038-125">Create a policy that allows any cache to supply requested resources if the resource on the server is not newer than the cached copy by setting the cache level to <xref:System.Net.Cache.HttpRequestCacheLevel.Revalidate>.</span></span>  
  
    ```csharp  
    public static void CheckServer()  
    {  
    HttpRequestCachePolicy policy = new HttpRequestCachePolicy  
             (HttpRequestCacheLevel.Revalidate);  
        HttpWebRequest.DefaultCachePolicy = policy;  
    }  
    ```  
  
    ```vb  
    Public Shared Sub CheckServer()  
        Dim policy As New HttpRequestCachePolicy _  
            (HttpRequestCacheLevel.Revalidate)  
        HttpWebRequest.DefaultCachePolicy = policy  
    End Sub  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="72038-126">另请参阅</span><span class="sxs-lookup"><span data-stu-id="72038-126">See Also</span></span>  
 [<span data-ttu-id="72038-127">网络应用程序的缓存管理</span><span class="sxs-lookup"><span data-stu-id="72038-127">Cache Management for Network Applications</span></span>](../../../docs/framework/network-programming/cache-management-for-network-applications.md)  
 [<span data-ttu-id="72038-128">缓存策略</span><span class="sxs-lookup"><span data-stu-id="72038-128">Cache Policy</span></span>](../../../docs/framework/network-programming/cache-policy.md)  
 [<span data-ttu-id="72038-129">基于位置的缓存策略</span><span class="sxs-lookup"><span data-stu-id="72038-129">Location-Based Cache Policies</span></span>](../../../docs/framework/network-programming/location-based-cache-policies.md)  
 [<span data-ttu-id="72038-130">基于时间的缓存策略</span><span class="sxs-lookup"><span data-stu-id="72038-130">Time-Based Cache Policies</span></span>](../../../docs/framework/network-programming/time-based-cache-policies.md)  
 [<span data-ttu-id="72038-131">\<requestCaching> 元素（网络设置）</span><span class="sxs-lookup"><span data-stu-id="72038-131">\<requestCaching> Element (Network Settings)</span></span>](../../../docs/framework/configure-apps/file-schema/network/requestcaching-element-network-settings.md)
