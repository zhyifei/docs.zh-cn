---
title: <applicationPool> 元素（网络设置）
ms.date: 03/30/2017
helpviewer_keywords:
- applicationPool element
- <applicationPool> element
ms.assetid: 46d1baaa-e343-4639-b70d-2a43a9f62b2a
ms.openlocfilehash: 6feaa801610fa0ffbbf47575f25aff29fa46a66c
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2020
ms.locfileid: "79152849"
---
# <a name="applicationpool-element-web-settings"></a><span data-ttu-id="644fa-102">\<applicationPool> 元素（Web 设置）</span><span class="sxs-lookup"><span data-stu-id="644fa-102">\<applicationPool> Element (Web Settings)</span></span>
<span data-ttu-id="644fa-103">指定ASP.NET在 IIS 7.0 或更高版本中以集成模式运行ASP.NET应用程序时用于管理进程范围行为的配置设置。</span><span class="sxs-lookup"><span data-stu-id="644fa-103">Specifies configuration settings that are used by ASP.NET to manage process-wide behavior when an ASP.NET application is running in Integrated mode on IIS 7.0 or a later version.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="644fa-104">仅当ASP.NET应用程序托管在 IIS 7.0 或更高版本上时，此元素及其支持的功能才起作用。</span><span class="sxs-lookup"><span data-stu-id="644fa-104">This element and the feature it supports only work if your ASP.NET application is hosted on IIS 7.0 or later versions.</span></span>  
  
[<span data-ttu-id="644fa-105">**\<配置>**</span><span class="sxs-lookup"><span data-stu-id="644fa-105">**\<configuration>**</span></span>](../configuration-element.md)  
<span data-ttu-id="644fa-106">&nbsp;&nbsp;[**\<系统.web>**](system-web-element-web-settings.md)</span><span class="sxs-lookup"><span data-stu-id="644fa-106">&nbsp;&nbsp;[**\<system.web>**](system-web-element-web-settings.md)</span></span>  
<span data-ttu-id="644fa-107">&nbsp;&nbsp;&nbsp;&nbsp;**\<应用程序池>**</span><span class="sxs-lookup"><span data-stu-id="644fa-107">&nbsp;&nbsp;&nbsp;&nbsp;**\<applicationPool>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="644fa-108">语法</span><span class="sxs-lookup"><span data-stu-id="644fa-108">Syntax</span></span>  
  
```xml  
<applicationPool
    maxConcurrentRequestsPerCPU="5000"
    maxConcurrentThreadsPerCPU="0"
    requestQueueLimit="5000" />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="644fa-109">特性和元素</span><span class="sxs-lookup"><span data-stu-id="644fa-109">Attributes and Elements</span></span>  

<span data-ttu-id="644fa-110">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="644fa-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="644fa-111">属性</span><span class="sxs-lookup"><span data-stu-id="644fa-111">Attributes</span></span>  
  
|<span data-ttu-id="644fa-112">Attribute</span><span class="sxs-lookup"><span data-stu-id="644fa-112">Attribute</span></span>|<span data-ttu-id="644fa-113">说明</span><span class="sxs-lookup"><span data-stu-id="644fa-113">Description</span></span>|  
|---------------|-----------------|  
|`maxConcurrentRequestsPerCPU`|<span data-ttu-id="644fa-114">指定每个 CPU ASP.NET允许的同声请求数。</span><span class="sxs-lookup"><span data-stu-id="644fa-114">Specifies how many simultaneous requests ASP.NET allows per CPU.</span></span>|  
|`maxConcurrentThreadsPerCPU`|<span data-ttu-id="644fa-115">指定每个 CPU 的应用程序池可以同时运行多少个线程。</span><span class="sxs-lookup"><span data-stu-id="644fa-115">Specifies how many simultaneous threads can be running for an application pool for each CPU.</span></span> <span data-ttu-id="644fa-116">这提供了一种控制ASP.NET并发的替代方法，因为您可以限制每个 CPU 可用于服务请求的托管线程数。</span><span class="sxs-lookup"><span data-stu-id="644fa-116">This provides an alternative way to control ASP.NET concurrency, because you can limit the number of managed threads that can be used per CPU to serve requests.</span></span> <span data-ttu-id="644fa-117">默认情况下，此设置为 0，这意味着ASP.NET不会限制每个 CPU 可以创建的线程数，尽管 CLR 线程池也限制可创建的线程数。</span><span class="sxs-lookup"><span data-stu-id="644fa-117">By default this setting is 0, which means that ASP.NET does not limit the number of threads that can be created per CPU, although the CLR thread pool also limits the number of threads that can be created.</span></span>|  
|`requestQueueLimit`|<span data-ttu-id="644fa-118">指定可在单个进程中排队等待ASP.NET的最大请求数。</span><span class="sxs-lookup"><span data-stu-id="644fa-118">Specifies the maximum number of requests that can be queued for ASP.NET in a single process.</span></span> <span data-ttu-id="644fa-119">当两个或两个ASP.NET多个应用程序在单个应用程序池中运行时，向应用程序池中的任何应用程序发出的请求的累积集受此设置的约束。</span><span class="sxs-lookup"><span data-stu-id="644fa-119">When two or more ASP.NET applications run in a single application pool, the cumulative set of requests being made to any application in the application pool is subject to this setting.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="644fa-120">子元素</span><span class="sxs-lookup"><span data-stu-id="644fa-120">Child Elements</span></span>  
 <span data-ttu-id="644fa-121">无。</span><span class="sxs-lookup"><span data-stu-id="644fa-121">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="644fa-122">父元素</span><span class="sxs-lookup"><span data-stu-id="644fa-122">Parent Elements</span></span>  
  
|<span data-ttu-id="644fa-123">元素</span><span class="sxs-lookup"><span data-stu-id="644fa-123">Element</span></span>|<span data-ttu-id="644fa-124">说明</span><span class="sxs-lookup"><span data-stu-id="644fa-124">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="644fa-125">\<系统.web></span><span class="sxs-lookup"><span data-stu-id="644fa-125">\<system.web></span></span>](system-web-element-web-settings.md)|<span data-ttu-id="644fa-126">包含有关ASP.NET如何与主机应用程序交互的信息。</span><span class="sxs-lookup"><span data-stu-id="644fa-126">Contains information about how ASP.NET interacts with a host application.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="644fa-127">备注</span><span class="sxs-lookup"><span data-stu-id="644fa-127">Remarks</span></span>  

<span data-ttu-id="644fa-128">在集成模式下运行 IIS 7.0 或更高版本时，此元素组合允许您配置在应用程序托管在 IIS 应用程序池中时ASP.NET如何管理线程和队列请求。</span><span class="sxs-lookup"><span data-stu-id="644fa-128">When you run IIS 7.0 or a later version in Integrated mode, this element combination lets you configure how ASP.NET manages threads and queues requests when the application is hosted in an IIS application pool.</span></span> <span data-ttu-id="644fa-129">如果您运行 IIS 6 或在经典模式或 ISAPI 模式下运行 IIS 7.0，则忽略这些设置。</span><span class="sxs-lookup"><span data-stu-id="644fa-129">If you run IIS 6 or you run IIS 7.0 in Classic mode or in ISAPI mode, these settings are ignored.</span></span>  
  
<span data-ttu-id="644fa-130">这些`applicationPool`设置适用于在 .NET 框架的特定版本上运行的所有应用程序池。</span><span class="sxs-lookup"><span data-stu-id="644fa-130">The `applicationPool` settings apply to all application pools that run on a particular version of the .NET Framework.</span></span> <span data-ttu-id="644fa-131">这些设置包含在 aspnet.config 文件中。</span><span class="sxs-lookup"><span data-stu-id="644fa-131">The settings are contained in an aspnet.config file.</span></span> <span data-ttu-id="644fa-132">对于 .NET Framework 的版本 2.0 和 4.0，有此文件的版本。</span><span class="sxs-lookup"><span data-stu-id="644fa-132">There is a version of this file for versions 2.0 and 4.0 of the .NET Framework.</span></span> <span data-ttu-id="644fa-133">（.NET 框架的版本 3.0 和 3.5 与版本 2.0 共享 aspnet.config 文件。</span><span class="sxs-lookup"><span data-stu-id="644fa-133">(Versions 3.0 and 3.5 of the .NET Framework share the aspnet.config file with version 2.0.)</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="644fa-134">如果在 Windows 7 上运行 IIS 7.0，则可以为每个应用程序池配置单独的 aspnet.config 文件。</span><span class="sxs-lookup"><span data-stu-id="644fa-134">If you run IIS 7.0 on Windows 7, you can configure a separate aspnet.config file for every application pool.</span></span> <span data-ttu-id="644fa-135">这允许您为每个应用程序池定制线程的性能。</span><span class="sxs-lookup"><span data-stu-id="644fa-135">This lets you tailor the performance of the threads for each application pool.</span></span>  
  
<span data-ttu-id="644fa-136">对于`maxConcurrentRequestsPerCPU`此设置，.NET Framework 4 中的默认设置"5000"可有效关闭由ASP.NET控制的请求限制，除非您每个 CPU 实际上有 5000 个或更多的请求。</span><span class="sxs-lookup"><span data-stu-id="644fa-136">For the `maxConcurrentRequestsPerCPU` setting, the default setting of "5000" in the .NET Framework 4 effectively turns off request throttling that is controlled by ASP.NET, unless you actually have 5000 or more requests per CPU.</span></span> <span data-ttu-id="644fa-137">默认设置取决于 CLR 线程池，以自动管理每个 CPU 的并发性。</span><span class="sxs-lookup"><span data-stu-id="644fa-137">The default setting depends instead on the CLR thread-pool to automatically manage concurrency per CPU.</span></span> <span data-ttu-id="644fa-138">大量使用异步请求处理或网络 I/O 上有许多长时间运行的请求的应用程序将受益于 .NET 框架 4 中增加的默认限制。</span><span class="sxs-lookup"><span data-stu-id="644fa-138">Applications that make extensive use of asynchronous request processing, or that have many long-running requests blocked on network I/O, will benefit from the increased default limit in the .NET Framework 4.</span></span> <span data-ttu-id="644fa-139">设置为`maxConcurrentRequestsPerCPU`零将关闭使用托管线程来处理ASP.NET请求。</span><span class="sxs-lookup"><span data-stu-id="644fa-139">Setting `maxConcurrentRequestsPerCPU` to zero turns off the use of managed threads for processing ASP.NET requests.</span></span> <span data-ttu-id="644fa-140">当应用程序在 IIS 应用程序池中运行时，请求将停留在 IIS I/O 线程上，因此 IIS 线程设置会限制并发。</span><span class="sxs-lookup"><span data-stu-id="644fa-140">When an application runs in an IIS application pool, requests stay on the IIS I/O thread and therefore concurrency is throttled by IIS thread settings.</span></span>  
  
<span data-ttu-id="644fa-141">该`requestQueueLimit`设置的工作方式与[processModel](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/7w2sway1(v=vs.100)) `requestQueueLimit`元素的属性相同，该属性在 Web.config 文件中设置为ASP.NET应用程序。</span><span class="sxs-lookup"><span data-stu-id="644fa-141">The `requestQueueLimit` setting works the same way as the `requestQueueLimit` attribute of the [processModel](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/7w2sway1(v=vs.100)) element, which is set in the Web.config files for ASP.NET applications.</span></span> <span data-ttu-id="644fa-142">但是，aspnet.config`requestQueueLimit`文件中的设置将覆盖 Web.config 文件中的`requestQueueLimit`设置。</span><span class="sxs-lookup"><span data-stu-id="644fa-142">However, the `requestQueueLimit` setting in an aspnet.config file overrides the `requestQueueLimit` setting in a Web.config file.</span></span> <span data-ttu-id="644fa-143">换句话说，如果两个属性都设置了（默认情况下，这是 true），则`requestQueueLimit`aspnet.config 文件中的设置优先。</span><span class="sxs-lookup"><span data-stu-id="644fa-143">In other words, if both attributes are set (by default, this is true), the `requestQueueLimit` setting in the aspnet.config file takes precedence.</span></span>  
  
## <a name="example"></a><span data-ttu-id="644fa-144">示例</span><span class="sxs-lookup"><span data-stu-id="644fa-144">Example</span></span>  

<span data-ttu-id="644fa-145">下面的示例演示如何在以下情况下配置 aspnet.config 文件中ASP.NET进程范围的行为：</span><span class="sxs-lookup"><span data-stu-id="644fa-145">The following example shows how to configure ASP.NET process-wide behavior in the aspnet.config file in the following circumstances:</span></span>  
  
- <span data-ttu-id="644fa-146">应用程序托管在 IIS 7.0 应用程序池中。</span><span class="sxs-lookup"><span data-stu-id="644fa-146">The application is hosted in an IIS 7.0 application pool.</span></span>  
  
- <span data-ttu-id="644fa-147">IIS 7.0 以集成模式运行。</span><span class="sxs-lookup"><span data-stu-id="644fa-147">IIS 7.0 is running in Integrated mode.</span></span>  
  
- <span data-ttu-id="644fa-148">应用程序正在使用 .NET 框架 3.5 SP1 或更高版本。</span><span class="sxs-lookup"><span data-stu-id="644fa-148">The application is using the .NET Framework 3.5 SP1 or a later version.</span></span>  
  
<span data-ttu-id="644fa-149">示例中的值是默认值。</span><span class="sxs-lookup"><span data-stu-id="644fa-149">The values in the example are the default values.</span></span>  
  
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
  
## <a name="element-information"></a><span data-ttu-id="644fa-150">元素信息</span><span class="sxs-lookup"><span data-stu-id="644fa-150">Element Information</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="644fa-151">命名空间</span><span class="sxs-lookup"><span data-stu-id="644fa-151">Namespace</span></span>||  
|<span data-ttu-id="644fa-152">架构名称</span><span class="sxs-lookup"><span data-stu-id="644fa-152">Schema Name</span></span>||  
|<span data-ttu-id="644fa-153">验证文件</span><span class="sxs-lookup"><span data-stu-id="644fa-153">Validation File</span></span>||  
|<span data-ttu-id="644fa-154">可以为空</span><span class="sxs-lookup"><span data-stu-id="644fa-154">Can be Empty</span></span>||  
  
## <a name="see-also"></a><span data-ttu-id="644fa-155">另请参阅</span><span class="sxs-lookup"><span data-stu-id="644fa-155">See also</span></span>

- [<span data-ttu-id="644fa-156">\<系统.web>元素（Web 设置）</span><span class="sxs-lookup"><span data-stu-id="644fa-156">\<system.web> Element (Web Settings)</span></span>](system-web-element-web-settings.md)
