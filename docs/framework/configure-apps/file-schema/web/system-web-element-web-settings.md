---
title: <system.web> 元素（网络设置）
ms.date: 03/30/2017
helpviewer_keywords:
- Web.config configuration file [ASP.NET]
- system.Web element
- <system.Web> element
- ASP.NET configuration system
- configuration files [ASP.NET]
ms.assetid: 24c4cf4f-ad32-42b2-b040-8e4549e2855e
ms.openlocfilehash: b37b05bdf90630251cbfcf86751243a3a8b77663
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2020
ms.locfileid: "79152836"
---
# <a name="systemweb-element-web-settings"></a><span data-ttu-id="a2fac-102">\<system.web> 元素（Web 设置）</span><span class="sxs-lookup"><span data-stu-id="a2fac-102">\<system.web> Element (Web Settings)</span></span>
<span data-ttu-id="a2fac-103">包含有关托管层如何管理进程范围行为ASP.NET的信息。</span><span class="sxs-lookup"><span data-stu-id="a2fac-103">Contains information about how the ASP.NET hosting layer manages process-wide behavior.</span></span>  
  
[<span data-ttu-id="a2fac-104">**\<配置>**</span><span class="sxs-lookup"><span data-stu-id="a2fac-104">**\<configuration>**</span></span>](../configuration-element.md)  
<span data-ttu-id="a2fac-105">&nbsp;&nbsp;**\<系统.web>**</span><span class="sxs-lookup"><span data-stu-id="a2fac-105">&nbsp;&nbsp;**\<system.web>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a2fac-106">语法</span><span class="sxs-lookup"><span data-stu-id="a2fac-106">Syntax</span></span>  
  
```xml  
<system.web>  
</system.web>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="a2fac-107">特性和元素</span><span class="sxs-lookup"><span data-stu-id="a2fac-107">Attributes and Elements</span></span>  

<span data-ttu-id="a2fac-108">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="a2fac-108">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="a2fac-109">属性</span><span class="sxs-lookup"><span data-stu-id="a2fac-109">Attributes</span></span>  

<span data-ttu-id="a2fac-110">无。</span><span class="sxs-lookup"><span data-stu-id="a2fac-110">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="a2fac-111">子元素</span><span class="sxs-lookup"><span data-stu-id="a2fac-111">Child Elements</span></span>  
  
|<span data-ttu-id="a2fac-112">元素</span><span class="sxs-lookup"><span data-stu-id="a2fac-112">Element</span></span>|<span data-ttu-id="a2fac-113">说明</span><span class="sxs-lookup"><span data-stu-id="a2fac-113">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="a2fac-114">\<应用程序池></span><span class="sxs-lookup"><span data-stu-id="a2fac-114">\<applicationPool></span></span>](applicationpool-element-web-settings.md)|<span data-ttu-id="a2fac-115">在 aspnet.config 文件中指定 IIS 应用程序池的配置设置。</span><span class="sxs-lookup"><span data-stu-id="a2fac-115">Specifies configuration settings for IIS application pools in an aspnet.config file.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="a2fac-116">父元素</span><span class="sxs-lookup"><span data-stu-id="a2fac-116">Parent Elements</span></span>  
  
|<span data-ttu-id="a2fac-117">元素</span><span class="sxs-lookup"><span data-stu-id="a2fac-117">Element</span></span>|<span data-ttu-id="a2fac-118">说明</span><span class="sxs-lookup"><span data-stu-id="a2fac-118">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="a2fac-119">\<配置></span><span class="sxs-lookup"><span data-stu-id="a2fac-119">\<configuration></span></span>](../configuration-element.md)|<span data-ttu-id="a2fac-120">指定通用语言运行时和 .NET Framework 应用程序使用的每个配置文件中的根元素。</span><span class="sxs-lookup"><span data-stu-id="a2fac-120">Specifies the root element in every configuration file that is used by the common language runtime and .NET Framework applications.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="a2fac-121">备注</span><span class="sxs-lookup"><span data-stu-id="a2fac-121">Remarks</span></span>  

<span data-ttu-id="a2fac-122">该`system.web`元素及其子`applicationPool`元素从 .NET 框架 3.5 SP1 开始添加到 .NET 框架中。</span><span class="sxs-lookup"><span data-stu-id="a2fac-122">The `system.web` element and its child `applicationPool` element were added to the .NET Framework as of .NET Framework 3.5 SP1.</span></span> <span data-ttu-id="a2fac-123">在集成模式下运行 IIS 7.0 或更高版本时，此元素组合允许您配置ASP.NET如何管理线程以及ASP.NET托管在 IIS 应用程序池中时如何排队请求。</span><span class="sxs-lookup"><span data-stu-id="a2fac-123">When you run IIS 7.0 or later versions in Integrated mode, this element combination lets you configure how ASP.NET manages threads and how it queues requests when ASP.NET is hosted in an IIS application pool.</span></span> <span data-ttu-id="a2fac-124">如果在经典或 ISAPI 模式下运行 IIS 7.0 或更高版本，则忽略这些设置。</span><span class="sxs-lookup"><span data-stu-id="a2fac-124">If you run IIS 7.0 or later versions in Classic or ISAPI mode, these settings are ignored.</span></span>  
  
## <a name="example"></a><span data-ttu-id="a2fac-125">示例</span><span class="sxs-lookup"><span data-stu-id="a2fac-125">Example</span></span>  

<span data-ttu-id="a2fac-126">下面的示例演示如何在 iIS 应用程序池中托管ASP.NET时，如何在 aspnet.config 文件中配置ASP.NET进程范围的行为。</span><span class="sxs-lookup"><span data-stu-id="a2fac-126">The following example shows how to configure ASP.NET process-wide behavior in the aspnet.config file when ASP.NET is hosted in an IIS application pool.</span></span> <span data-ttu-id="a2fac-127">该示例假定 IIS 在集成模式下运行，并且应用程序正在使用 .NET 框架 3.5 SP1 或更高版本。</span><span class="sxs-lookup"><span data-stu-id="a2fac-127">The example assumes that IIS is running in Integrated mode and that the application is using the .NET Framework 3.5 SP1 or a later version.</span></span> <span data-ttu-id="a2fac-128">此行为不会在 .NET 框架 3.5 SP1 之前的版本中发生。</span><span class="sxs-lookup"><span data-stu-id="a2fac-128">This behavior does not occur in versions of the .NET Framework earlier than the .NET Framework 3.5 SP1.</span></span> <span data-ttu-id="a2fac-129">示例中的值是默认值。</span><span class="sxs-lookup"><span data-stu-id="a2fac-129">The values in the example are the default values.</span></span>  
  
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
  
## <a name="element-information"></a><span data-ttu-id="a2fac-130">元素信息</span><span class="sxs-lookup"><span data-stu-id="a2fac-130">Element Information</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="a2fac-131">命名空间</span><span class="sxs-lookup"><span data-stu-id="a2fac-131">Namespace</span></span>||  
|<span data-ttu-id="a2fac-132">架构名称</span><span class="sxs-lookup"><span data-stu-id="a2fac-132">Schema Name</span></span>||  
|<span data-ttu-id="a2fac-133">验证文件</span><span class="sxs-lookup"><span data-stu-id="a2fac-133">Validation File</span></span>||  
|<span data-ttu-id="a2fac-134">可以为空</span><span class="sxs-lookup"><span data-stu-id="a2fac-134">Can be Empty</span></span>||  
  
## <a name="see-also"></a><span data-ttu-id="a2fac-135">另请参阅</span><span class="sxs-lookup"><span data-stu-id="a2fac-135">See also</span></span>

- [<span data-ttu-id="a2fac-136">\<应用程序池>元素（Web 设置）</span><span class="sxs-lookup"><span data-stu-id="a2fac-136">\<applicationPool> Element (Web Settings)</span></span>](applicationpool-element-web-settings.md)
