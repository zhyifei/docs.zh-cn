---
title: <applicationPool> 元素（网络设置）
ms.date: 03/30/2017
helpviewer_keywords:
- applicationPool element
- <applicationPool> element
ms.assetid: 46d1baaa-e343-4639-b70d-2a43a9f62b2a
ms.openlocfilehash: 9783844ff0fe719b0581c1c9e1fb96eb31933b89
ms.sourcegitcommit: 32a575bf4adccc901f00e264f92b759ced633379
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/04/2019
ms.locfileid: "74801871"
---
# <a name="applicationpool-element-web-settings"></a><span data-ttu-id="bdf9b-102">\<applicationPool > 元素（Web 设置）</span><span class="sxs-lookup"><span data-stu-id="bdf9b-102">\<applicationPool> Element (Web Settings)</span></span>
<span data-ttu-id="bdf9b-103">指定 ASP.NET 在 IIS 7.0 或更高版本的集成模式下运行时，用于管理进程范围行为的配置设置。</span><span class="sxs-lookup"><span data-stu-id="bdf9b-103">Specifies configuration settings that are used by ASP.NET to manage process-wide behavior when an ASP.NET application is running in Integrated mode on IIS 7.0 or a later version.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="bdf9b-104">仅当 ASP.NET 应用程序托管在 IIS 7.0 或更高版本上时，此元素和它支持的功能才起作用。</span><span class="sxs-lookup"><span data-stu-id="bdf9b-104">This element and the feature it supports only work if your ASP.NET application is hosted on IIS 7.0 or later versions.</span></span>  
  
[<span data-ttu-id="bdf9b-105"> **\<configuration>** </span><span class="sxs-lookup"><span data-stu-id="bdf9b-105">**\<configuration>**</span></span>](../configuration-element.md)  
<span data-ttu-id="bdf9b-106">&nbsp;&nbsp;[ **\<system.web >** ](system-web-element-web-settings.md)</span><span class="sxs-lookup"><span data-stu-id="bdf9b-106">&nbsp;&nbsp;[**\<system.web>**](system-web-element-web-settings.md)</span></span>  
<span data-ttu-id="bdf9b-107">&nbsp;&nbsp;&nbsp;&nbsp; **\<applicationPool >**</span><span class="sxs-lookup"><span data-stu-id="bdf9b-107">&nbsp;&nbsp;&nbsp;&nbsp;**\<applicationPool>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bdf9b-108">语法</span><span class="sxs-lookup"><span data-stu-id="bdf9b-108">Syntax</span></span>  
  
```xml  
<applicationPool   
    maxConcurrentRequestsPerCPU="5000"   
    maxConcurrentThreadsPerCPU="0"   
    requestQueueLimit="5000" />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="bdf9b-109">属性和元素</span><span class="sxs-lookup"><span data-stu-id="bdf9b-109">Attributes and Elements</span></span>  

<span data-ttu-id="bdf9b-110">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="bdf9b-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="bdf9b-111">特性</span><span class="sxs-lookup"><span data-stu-id="bdf9b-111">Attributes</span></span>  
  
|<span data-ttu-id="bdf9b-112">属性</span><span class="sxs-lookup"><span data-stu-id="bdf9b-112">Attribute</span></span>|<span data-ttu-id="bdf9b-113">描述</span><span class="sxs-lookup"><span data-stu-id="bdf9b-113">Description</span></span>|  
|---------------|-----------------|  
|`maxConcurrentRequestsPerCPU`|<span data-ttu-id="bdf9b-114">指定 ASP.NET 每 CPU 允许的并发请求数。</span><span class="sxs-lookup"><span data-stu-id="bdf9b-114">Specifies how many simultaneous requests ASP.NET allows per CPU.</span></span>|  
|`maxConcurrentThreadsPerCPU`|<span data-ttu-id="bdf9b-115">指定每个 CPU 的应用程序池可以运行的线程数。</span><span class="sxs-lookup"><span data-stu-id="bdf9b-115">Specifies how many simultaneous threads can be running for an application pool for each CPU.</span></span> <span data-ttu-id="bdf9b-116">这提供了一种方法来控制 ASP.NET 并发，因为你可以限制每个 CPU 可用于处理请求的托管线程数。</span><span class="sxs-lookup"><span data-stu-id="bdf9b-116">This provides an alternative way to control ASP.NET concurrency, because you can limit the number of managed threads that can be used per CPU to serve requests.</span></span> <span data-ttu-id="bdf9b-117">默认情况下，此设置为0，这意味着 ASP.NET 不会限制可为每个 CPU 创建的线程数，尽管 CLR 线程池还限制了可创建的线程数。</span><span class="sxs-lookup"><span data-stu-id="bdf9b-117">By default this setting is 0, which means that ASP.NET does not limit the number of threads that can be created per CPU, although the CLR thread pool also limits the number of threads that can be created.</span></span>|  
|`requestQueueLimit`|<span data-ttu-id="bdf9b-118">指定可在单个进程中为 ASP.NET 排队的最大请求数。</span><span class="sxs-lookup"><span data-stu-id="bdf9b-118">Specifies the maximum number of requests that can be queued for ASP.NET in a single process.</span></span> <span data-ttu-id="bdf9b-119">当两个或多个 ASP.NET 应用程序在单个应用程序池中运行时，对应用程序池中的任何应用程序发出的累积请求将受到此设置的限制。</span><span class="sxs-lookup"><span data-stu-id="bdf9b-119">When two or more ASP.NET applications run in a single application pool, the cumulative set of requests being made to any application in the application pool is subject to this setting.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="bdf9b-120">子元素</span><span class="sxs-lookup"><span data-stu-id="bdf9b-120">Child Elements</span></span>  
 <span data-ttu-id="bdf9b-121">无。</span><span class="sxs-lookup"><span data-stu-id="bdf9b-121">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="bdf9b-122">父元素</span><span class="sxs-lookup"><span data-stu-id="bdf9b-122">Parent Elements</span></span>  
  
|<span data-ttu-id="bdf9b-123">元素</span><span class="sxs-lookup"><span data-stu-id="bdf9b-123">Element</span></span>|<span data-ttu-id="bdf9b-124">描述</span><span class="sxs-lookup"><span data-stu-id="bdf9b-124">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="bdf9b-125">\<system.web></span><span class="sxs-lookup"><span data-stu-id="bdf9b-125">\<system.web></span></span>](system-web-element-web-settings.md)|<span data-ttu-id="bdf9b-126">包含有关 ASP.NET 如何与宿主应用程序进行交互的信息。</span><span class="sxs-lookup"><span data-stu-id="bdf9b-126">Contains information about how ASP.NET interacts with a host application.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="bdf9b-127">备注</span><span class="sxs-lookup"><span data-stu-id="bdf9b-127">Remarks</span></span>  

<span data-ttu-id="bdf9b-128">在集成模式下运行 IIS 7.0 或更高版本时，此元素组合可让你配置当应用程序托管在 IIS 应用程序池中时，ASP.NET 如何管理线程和队列请求。</span><span class="sxs-lookup"><span data-stu-id="bdf9b-128">When you run IIS 7.0 or a later version in Integrated mode, this element combination lets you configure how ASP.NET manages threads and queues requests when the application is hosted in an IIS application pool.</span></span> <span data-ttu-id="bdf9b-129">如果运行 IIS 6 或在经典模式下或在 ISAPI 模式下运行 IIS 7.0，则将忽略这些设置。</span><span class="sxs-lookup"><span data-stu-id="bdf9b-129">If you run IIS 6 or you run IIS 7.0 in Classic mode or in ISAPI mode, these settings are ignored.</span></span>  
  
<span data-ttu-id="bdf9b-130">`applicationPool` 设置适用于在 .NET Framework 的特定版本上运行的所有应用程序池。</span><span class="sxs-lookup"><span data-stu-id="bdf9b-130">The `applicationPool` settings apply to all application pools that run on a particular version of the .NET Framework.</span></span> <span data-ttu-id="bdf9b-131">这些设置包含在 aspnet .config 文件中。</span><span class="sxs-lookup"><span data-stu-id="bdf9b-131">The settings are contained in an aspnet.config file.</span></span> <span data-ttu-id="bdf9b-132">此文件的版本2.0 和 4.0 .NET Framework。</span><span class="sxs-lookup"><span data-stu-id="bdf9b-132">There is a version of this file for versions 2.0 and 4.0 of the .NET Framework.</span></span> <span data-ttu-id="bdf9b-133">（版本3.0 和 3.5 .NET Framework 共享包含版本2.0 的 aspnet .config 文件。）</span><span class="sxs-lookup"><span data-stu-id="bdf9b-133">(Versions 3.0 and 3.5 of the .NET Framework share the aspnet.config file with version 2.0.)</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="bdf9b-134">如果在 Windows 7 上运行 IIS 7.0，则可以为每个应用程序池分别配置一个 aspnet .config 文件。</span><span class="sxs-lookup"><span data-stu-id="bdf9b-134">If you run IIS 7.0 on Windows 7, you can configure a separate aspnet.config file for every application pool.</span></span> <span data-ttu-id="bdf9b-135">这使你可以为每个应用程序池定制线程性能。</span><span class="sxs-lookup"><span data-stu-id="bdf9b-135">This lets you tailor the performance of the threads for each application pool.</span></span>  
  
<span data-ttu-id="bdf9b-136">对于 `maxConcurrentRequestsPerCPU` 设置，.NET Framework 4 中的默认设置 "5000" 有效地关闭了由 ASP.NET 控制的请求阻止，除非你实际每个 CPU 有5000或更多请求。</span><span class="sxs-lookup"><span data-stu-id="bdf9b-136">For the `maxConcurrentRequestsPerCPU` setting, the default setting of "5000" in the .NET Framework 4 effectively turns off request throttling that is controlled by ASP.NET, unless you actually have 5000 or more requests per CPU.</span></span> <span data-ttu-id="bdf9b-137">默认设置依赖于 CLR 线程池来自动管理每个 CPU 的并发。</span><span class="sxs-lookup"><span data-stu-id="bdf9b-137">The default setting depends instead on the CLR thread-pool to automatically manage concurrency per CPU.</span></span> <span data-ttu-id="bdf9b-138">对于大量使用异步请求处理的应用程序，或在网络 i/o 上阻塞多个长时间运行的请求的应用程序，将从 .NET Framework 4 中增加的默认限制中受益。</span><span class="sxs-lookup"><span data-stu-id="bdf9b-138">Applications that make extensive use of asynchronous request processing, or that have many long-running requests blocked on network I/O, will benefit from the increased default limit in the .NET Framework 4.</span></span> <span data-ttu-id="bdf9b-139">将 `maxConcurrentRequestsPerCPU` 设置为零将关闭使用托管线程来处理 ASP.NET 请求。</span><span class="sxs-lookup"><span data-stu-id="bdf9b-139">Setting `maxConcurrentRequestsPerCPU` to zero turns off the use of managed threads for processing ASP.NET requests.</span></span> <span data-ttu-id="bdf9b-140">当应用程序在 IIS 应用程序池中运行时，请求将保留在 IIS i/o 线程上，因此并发会受到 IIS 线程设置的限制。</span><span class="sxs-lookup"><span data-stu-id="bdf9b-140">When an application runs in an IIS application pool, requests stay on the IIS I/O thread and therefore concurrency is throttled by IIS thread settings.</span></span>  
  
<span data-ttu-id="bdf9b-141">`requestQueueLimit` 设置的工作方式与在 ASP.NET 应用程序的 web.config 文件中设置的[processModel](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/7w2sway1(v=vs.100))元素的 `requestQueueLimit` 属性相同。</span><span class="sxs-lookup"><span data-stu-id="bdf9b-141">The `requestQueueLimit` setting works the same way as the `requestQueueLimit` attribute of the [processModel](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/7w2sway1(v=vs.100)) element, which is set in the Web.config files for ASP.NET applications.</span></span> <span data-ttu-id="bdf9b-142">但是，aspnet 文件中的 `requestQueueLimit` 设置会覆盖 Web.config 文件中的 `requestQueueLimit` 设置。</span><span class="sxs-lookup"><span data-stu-id="bdf9b-142">However, the `requestQueueLimit` setting in an aspnet.config file overrides the `requestQueueLimit` setting in a Web.config file.</span></span> <span data-ttu-id="bdf9b-143">换句话说，如果同时设置了这两个属性（默认情况下为 true），则将优先使用 aspnet .config 文件中的 `requestQueueLimit` 设置。</span><span class="sxs-lookup"><span data-stu-id="bdf9b-143">In other words, if both attributes are set (by default, this is true), the `requestQueueLimit` setting in the aspnet.config file takes precedence.</span></span>  
  
## <a name="example"></a><span data-ttu-id="bdf9b-144">示例</span><span class="sxs-lookup"><span data-stu-id="bdf9b-144">Example</span></span>  

<span data-ttu-id="bdf9b-145">下面的示例演示如何在以下情况下配置 ASP.NET 中的进程范围行为：</span><span class="sxs-lookup"><span data-stu-id="bdf9b-145">The following example shows how to configure ASP.NET process-wide behavior in the aspnet.config file in the following circumstances:</span></span>  
  
- <span data-ttu-id="bdf9b-146">该应用程序托管在 IIS 7.0 应用程序池中。</span><span class="sxs-lookup"><span data-stu-id="bdf9b-146">The application is hosted in an IIS 7.0 application pool.</span></span>  
  
- <span data-ttu-id="bdf9b-147">IIS 7.0 正在集成模式下运行。</span><span class="sxs-lookup"><span data-stu-id="bdf9b-147">IIS 7.0 is running in Integrated mode.</span></span>  
  
- <span data-ttu-id="bdf9b-148">应用程序使用的是 .NET Framework 3.5 SP1 或更高版本。</span><span class="sxs-lookup"><span data-stu-id="bdf9b-148">The application is using the .NET Framework 3.5 SP1 or a later version.</span></span>  
  
<span data-ttu-id="bdf9b-149">示例中的值为默认值。</span><span class="sxs-lookup"><span data-stu-id="bdf9b-149">The values in the example are the default values.</span></span>  
  
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
  
## <a name="element-information"></a><span data-ttu-id="bdf9b-150">元素信息</span><span class="sxs-lookup"><span data-stu-id="bdf9b-150">Element Information</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="bdf9b-151">命名空间</span><span class="sxs-lookup"><span data-stu-id="bdf9b-151">Namespace</span></span>||  
|<span data-ttu-id="bdf9b-152">架构名</span><span class="sxs-lookup"><span data-stu-id="bdf9b-152">Schema Name</span></span>||  
|<span data-ttu-id="bdf9b-153">验证文件</span><span class="sxs-lookup"><span data-stu-id="bdf9b-153">Validation File</span></span>||  
|<span data-ttu-id="bdf9b-154">可以为空</span><span class="sxs-lookup"><span data-stu-id="bdf9b-154">Can be Empty</span></span>||  
  
## <a name="see-also"></a><span data-ttu-id="bdf9b-155">另请参阅</span><span class="sxs-lookup"><span data-stu-id="bdf9b-155">See also</span></span>

- [<span data-ttu-id="bdf9b-156">\<system.web> 元素（Web 设置）</span><span class="sxs-lookup"><span data-stu-id="bdf9b-156">\<system.web> Element (Web Settings)</span></span>](system-web-element-web-settings.md)
