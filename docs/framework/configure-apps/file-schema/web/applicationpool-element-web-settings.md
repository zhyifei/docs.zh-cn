---
title: '&lt;applicationPool&gt;元素 （Web 设置）'
ms.date: 03/30/2017
helpviewer_keywords:
- applicationPool element
- <applicationPool> element
ms.assetid: 46d1baaa-e343-4639-b70d-2a43a9f62b2a
ms.openlocfilehash: 3f2e325a05242a028c5bcda3a44a38e7bda77e1b
ms.sourcegitcommit: b351b0781a035616c90c68ccae6dd60aae66a953
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/26/2019
ms.locfileid: "55083998"
---
# <a name="ltapplicationpoolgt-element-web-settings"></a><span data-ttu-id="cdea5-102">&lt;applicationPool&gt;元素 （Web 设置）</span><span class="sxs-lookup"><span data-stu-id="cdea5-102">&lt;applicationPool&gt; Element (Web Settings)</span></span>
<span data-ttu-id="cdea5-103">指定 ASP.NET 用于 ASP.NET 应用程序在中集成模式下运行时管理的进程范围行为的配置设置[!INCLUDE[iisver](../../../../../includes/iisver-md.md)]或更高版本。</span><span class="sxs-lookup"><span data-stu-id="cdea5-103">Specifies configuration settings that are used by ASP.NET to manage process-wide behavior when an ASP.NET application is running in Integrated mode on [!INCLUDE[iisver](../../../../../includes/iisver-md.md)] or a later version.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="cdea5-104">此元素和功能它支持唯一工作，如果 ASP.NET 应用程序承载于[!INCLUDE[iisver](../../../../../includes/iisver-md.md)]或更高版本。</span><span class="sxs-lookup"><span data-stu-id="cdea5-104">This element and the feature it supports only work if your ASP.NET application is hosted on [!INCLUDE[iisver](../../../../../includes/iisver-md.md)] or later versions.</span></span>  
  
 <span data-ttu-id="cdea5-105">\<configuration></span><span class="sxs-lookup"><span data-stu-id="cdea5-105">\<configuration></span></span>  
<span data-ttu-id="cdea5-106">\<system.web > 元素 （Web 设置）</span><span class="sxs-lookup"><span data-stu-id="cdea5-106">\<system.web> Element (Web Settings)</span></span>  
<span data-ttu-id="cdea5-107">\<applicationPool > 元素 （Web 设置）</span><span class="sxs-lookup"><span data-stu-id="cdea5-107">\<applicationPool> Element (Web Settings)</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cdea5-108">语法</span><span class="sxs-lookup"><span data-stu-id="cdea5-108">Syntax</span></span>  
  
```xml  
<applicationPool   
    maxConcurrentRequestsPerCPU="5000"   
    maxConcurrentThreadsPerCPU="0"   
    requestQueueLimit="5000" />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="cdea5-109">特性和元素</span><span class="sxs-lookup"><span data-stu-id="cdea5-109">Attributes and Elements</span></span>  
 <span data-ttu-id="cdea5-110">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="cdea5-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="cdea5-111">特性</span><span class="sxs-lookup"><span data-stu-id="cdea5-111">Attributes</span></span>  
  
|<span data-ttu-id="cdea5-112">特性</span><span class="sxs-lookup"><span data-stu-id="cdea5-112">Attribute</span></span>|<span data-ttu-id="cdea5-113">描述</span><span class="sxs-lookup"><span data-stu-id="cdea5-113">Description</span></span>|  
|---------------|-----------------|  
|`maxConcurrentRequestsPerCPU`|<span data-ttu-id="cdea5-114">指定 ASP.NET 允许每个 CPU 的并发请求数。</span><span class="sxs-lookup"><span data-stu-id="cdea5-114">Specifies how many simultaneous requests ASP.NET allows per CPU.</span></span>|  
|`maxConcurrentThreadsPerCPU`|<span data-ttu-id="cdea5-115">指定为每个 CPU 可以为应用程序池运行并发线程数。</span><span class="sxs-lookup"><span data-stu-id="cdea5-115">Specifies how many simultaneous threads can be running for an application pool for each CPU.</span></span> <span data-ttu-id="cdea5-116">这提供了用于控制 ASP.NET 并发的替代方法，因为您可以限制可每 CPU 用于为请求提供服务的托管线程数。</span><span class="sxs-lookup"><span data-stu-id="cdea5-116">This provides an alternative way to control ASP.NET concurrency, because you can limit the number of managed threads that can be used per CPU to serve requests.</span></span> <span data-ttu-id="cdea5-117">默认情况下此设置为 0，这意味着 ASP.NET 不尽管 CLR 线程池还限制可创建的线程数限制每个 CPU，可以创建的线程数。</span><span class="sxs-lookup"><span data-stu-id="cdea5-117">By default this setting is 0, which means that ASP.NET does not limit the number of threads that can be created per CPU, although the CLR thread pool also limits the number of threads that can be created.</span></span>|  
|`requestQueueLimit`|<span data-ttu-id="cdea5-118">指定的最大可以为 ASP.NET 在单个进程中排队的请求数。</span><span class="sxs-lookup"><span data-stu-id="cdea5-118">Specifies the maximum number of requests that can be queued for ASP.NET in a single process.</span></span> <span data-ttu-id="cdea5-119">当两个或多个 ASP.NET 应用程序运行在单个应用程序池时，向应用程序池的任何应用程序发出的请求的累积一受到此设置。</span><span class="sxs-lookup"><span data-stu-id="cdea5-119">When two or more ASP.NET applications run in a single application pool, the cumulative set of requests being made to any application in the application pool is subject to this setting.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="cdea5-120">子元素</span><span class="sxs-lookup"><span data-stu-id="cdea5-120">Child Elements</span></span>  
 <span data-ttu-id="cdea5-121">无。</span><span class="sxs-lookup"><span data-stu-id="cdea5-121">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="cdea5-122">父元素</span><span class="sxs-lookup"><span data-stu-id="cdea5-122">Parent Elements</span></span>  
  
|<span data-ttu-id="cdea5-123">元素</span><span class="sxs-lookup"><span data-stu-id="cdea5-123">Element</span></span>|<span data-ttu-id="cdea5-124">描述</span><span class="sxs-lookup"><span data-stu-id="cdea5-124">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="cdea5-125">\<system.web></span><span class="sxs-lookup"><span data-stu-id="cdea5-125">\<system.web></span></span>](../../../../../docs/framework/configure-apps/file-schema/web/system-web-element-web-settings.md)|<span data-ttu-id="cdea5-126">包含有关 ASP.NET 如何与主机应用程序进行交互的信息。</span><span class="sxs-lookup"><span data-stu-id="cdea5-126">Contains information about how ASP.NET interacts with a host application.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="cdea5-127">备注</span><span class="sxs-lookup"><span data-stu-id="cdea5-127">Remarks</span></span>  
 <span data-ttu-id="cdea5-128">当你运行[!INCLUDE[iisver](../../../../../includes/iisver-md.md)]或更高版本在集成模式下，此元素组合可让你配置 ASP.NET 如何管理线程和队列请求，当应用程序承载于 IIS 应用程序池。</span><span class="sxs-lookup"><span data-stu-id="cdea5-128">When you run [!INCLUDE[iisver](../../../../../includes/iisver-md.md)] or a later version in Integrated mode, this element combination lets you configure how ASP.NET manages threads and queues requests when the application is hosted in an IIS application pool.</span></span> <span data-ttu-id="cdea5-129">如果运行 IIS 6 也运行[!INCLUDE[iisver](../../../../../includes/iisver-md.md)]在经典模式下或在 ISAPI 模式下，将忽略这些设置。</span><span class="sxs-lookup"><span data-stu-id="cdea5-129">If you run IIS 6 or you run [!INCLUDE[iisver](../../../../../includes/iisver-md.md)] in Classic mode or in ISAPI mode, these settings are ignored.</span></span>  
  
 <span data-ttu-id="cdea5-130">`applicationPool`设置适用于特定版本的.NET Framework 运行的所有应用程序池。</span><span class="sxs-lookup"><span data-stu-id="cdea5-130">The `applicationPool` settings apply to all application pools that run on a particular version of the .NET Framework.</span></span> <span data-ttu-id="cdea5-131">设置包含在 aspnet.config 文件中。</span><span class="sxs-lookup"><span data-stu-id="cdea5-131">The settings are contained in an aspnet.config file.</span></span> <span data-ttu-id="cdea5-132">没有此文件的版本 2.0 和.NET Framework 4.0 版本。</span><span class="sxs-lookup"><span data-stu-id="cdea5-132">There is a version of this file for versions 2.0 and 4.0 of the .NET Framework.</span></span> <span data-ttu-id="cdea5-133">（版本 3.0 和.NET Framework 3.5 的 aspnet.config 文件与共享版本 2.0。）</span><span class="sxs-lookup"><span data-stu-id="cdea5-133">(Versions 3.0 and 3.5 of the .NET Framework share the aspnet.config file with version 2.0.)</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="cdea5-134">如果在运行[!INCLUDE[iisver](../../../../../includes/iisver-md.md)]上[!INCLUDE[win7](../../../../../includes/win7-md.md)]，可以配置每个应用程序池的单独的 aspnet.config 文件。</span><span class="sxs-lookup"><span data-stu-id="cdea5-134">If you run [!INCLUDE[iisver](../../../../../includes/iisver-md.md)] on [!INCLUDE[win7](../../../../../includes/win7-md.md)], you can configure a separate aspnet.config file for every application pool.</span></span> <span data-ttu-id="cdea5-135">这样，你可以定制每个应用程序池的线程的性能。</span><span class="sxs-lookup"><span data-stu-id="cdea5-135">This lets you tailor the performance of the threads for each application pool.</span></span>  
  
 <span data-ttu-id="cdea5-136">有关`maxConcurrentRequestsPerCPU`中的设置，默认值为"5000"[!INCLUDE[net_v40_short](../../../../../includes/net-v40-short-md.md)]有效地将关闭请求限制，它受 ASP.NET 中，除非您真正使用每个 CPU 的 5000 或多个请求。</span><span class="sxs-lookup"><span data-stu-id="cdea5-136">For the `maxConcurrentRequestsPerCPU` setting, the default setting of "5000" in the [!INCLUDE[net_v40_short](../../../../../includes/net-v40-short-md.md)] effectively turns off request throttling that is controlled by ASP.NET, unless you actually have 5000 or more requests per CPU.</span></span> <span data-ttu-id="cdea5-137">默认设置改为依赖于 CLR 线程池来自动管理每个 CPU 的并发。</span><span class="sxs-lookup"><span data-stu-id="cdea5-137">The default setting depends instead on the CLR thread-pool to automatically manage concurrency per CPU.</span></span> <span data-ttu-id="cdea5-138">请广泛使用的异步请求处理，或具有网络 I/O 上阻塞的很多长时间运行请求的应用程序将受益于中的增大的默认限制[!INCLUDE[net_v40_short](../../../../../includes/net-v40-short-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="cdea5-138">Applications that make extensive use of asynchronous request processing, or that have many long-running requests blocked on network I/O, will benefit from the increased default limit in the [!INCLUDE[net_v40_short](../../../../../includes/net-v40-short-md.md)].</span></span> <span data-ttu-id="cdea5-139">设置`maxConcurrentRequestsPerCPU`到用于处理 ASP.NET 请求零将关闭托管线程的使用。</span><span class="sxs-lookup"><span data-stu-id="cdea5-139">Setting `maxConcurrentRequestsPerCPU` to zero turns off the use of managed threads for processing ASP.NET requests.</span></span> <span data-ttu-id="cdea5-140">应用程序中运行时的 IIS 应用程序池，请求将停留在 IIS I/O 线程和线程的 IIS 设置因此阻止并发。</span><span class="sxs-lookup"><span data-stu-id="cdea5-140">When an application runs in an IIS application pool, requests stay on the IIS I/O thread and therefore concurrency is throttled by IIS thread settings.</span></span>  
  
 <span data-ttu-id="cdea5-141">`requestQueueLimit`设置的工作方式相同`requestQueueLimit`的属性[processModel](https://msdn.microsoft.com/library/4b8fe20e-74c8-4566-b72c-ce5f83c8e32d)元素，它在 ASP.NET 应用程序的 Web.config 文件中设置。</span><span class="sxs-lookup"><span data-stu-id="cdea5-141">The `requestQueueLimit` setting works the same way as the `requestQueueLimit` attribute of the [processModel](https://msdn.microsoft.com/library/4b8fe20e-74c8-4566-b72c-ce5f83c8e32d) element, which is set in the Web.config files for ASP.NET applications.</span></span> <span data-ttu-id="cdea5-142">但是， `requestQueueLimit` aspnet.config 文件中的设置将重写`requestQueueLimit`Web.config 文件中的设置。</span><span class="sxs-lookup"><span data-stu-id="cdea5-142">However, the `requestQueueLimit` setting in an aspnet.config file overrides the `requestQueueLimit` setting in a Web.config file.</span></span> <span data-ttu-id="cdea5-143">换而言之，如果将这两个属性都设置 （默认情况下为 true）， `requestQueueLimit` aspnet.config 文件中的设置优先。</span><span class="sxs-lookup"><span data-stu-id="cdea5-143">In other words, if both attributes are set (by default, this is true), the `requestQueueLimit` setting in the aspnet.config file takes precedence.</span></span>  
  
## <a name="example"></a><span data-ttu-id="cdea5-144">示例</span><span class="sxs-lookup"><span data-stu-id="cdea5-144">Example</span></span>  
 <span data-ttu-id="cdea5-145">下面的示例演示如何在以下情况下的 aspnet.config 文件中配置 ASP.NET 进程范围行为：</span><span class="sxs-lookup"><span data-stu-id="cdea5-145">The following example shows how to configure ASP.NET process-wide behavior in the aspnet.config file in the following circumstances:</span></span>  
  
-   <span data-ttu-id="cdea5-146">应用程序托管在[!INCLUDE[iisver](../../../../../includes/iisver-md.md)]应用程序池。</span><span class="sxs-lookup"><span data-stu-id="cdea5-146">The application is hosted in an [!INCLUDE[iisver](../../../../../includes/iisver-md.md)] application pool.</span></span>  
  
-   [!INCLUDE[iisver](../../../../../includes/iisver-md.md)] <span data-ttu-id="cdea5-147">在集成模式下运行。</span><span class="sxs-lookup"><span data-stu-id="cdea5-147">is running in Integrated mode.</span></span>  
  
-   <span data-ttu-id="cdea5-148">应用程序使用[!INCLUDE[net_v35SP1_short](../../../../../includes/net-v35sp1-short-md.md)]或更高版本。</span><span class="sxs-lookup"><span data-stu-id="cdea5-148">The application is using the [!INCLUDE[net_v35SP1_short](../../../../../includes/net-v35sp1-short-md.md)] or a later version.</span></span>  
  
 <span data-ttu-id="cdea5-149">在示例中的值是默认值。</span><span class="sxs-lookup"><span data-stu-id="cdea5-149">The values in the example are the default values.</span></span>  
  
```xml  
<configuration>  
  <system.web>  
    <applicationPool   
        maxConcurrentRequestsPerCPU="5000"  
        maxConcurrentThreadsPerCPU="0"   
        requestQueueLimit="5000" />  
  </system.web>  
</configuration>  
```  
  
## <a name="element-information"></a><span data-ttu-id="cdea5-150">元素信息</span><span class="sxs-lookup"><span data-stu-id="cdea5-150">Element Information</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="cdea5-151">命名空间</span><span class="sxs-lookup"><span data-stu-id="cdea5-151">Namespace</span></span>||  
|<span data-ttu-id="cdea5-152">架构名称</span><span class="sxs-lookup"><span data-stu-id="cdea5-152">Schema Name</span></span>||  
|<span data-ttu-id="cdea5-153">验证文件</span><span class="sxs-lookup"><span data-stu-id="cdea5-153">Validation File</span></span>||  
|<span data-ttu-id="cdea5-154">可以为空</span><span class="sxs-lookup"><span data-stu-id="cdea5-154">Can be Empty</span></span>||  
  
## <a name="see-also"></a><span data-ttu-id="cdea5-155">请参阅</span><span class="sxs-lookup"><span data-stu-id="cdea5-155">See also</span></span>
- [<span data-ttu-id="cdea5-156">\<system.web> 元素（Web 设置）</span><span class="sxs-lookup"><span data-stu-id="cdea5-156">\<system.web> Element (Web Settings)</span></span>](../../../../../docs/framework/configure-apps/file-schema/web/system-web-element-web-settings.md)
