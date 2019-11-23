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
ms.openlocfilehash: 5c5c857d4494b6d78b819e56bae4213abc5e2035
ms.sourcegitcommit: 3094dcd17141b32a570a82ae3f62a331616e2c9c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/01/2019
ms.locfileid: "71699096"
---
# <a name="systemweb-element-web-settings"></a><span data-ttu-id="2c754-102">\<system.web > 元素（Web 设置）</span><span class="sxs-lookup"><span data-stu-id="2c754-102">\<system.web> Element (Web Settings)</span></span>
<span data-ttu-id="2c754-103">包含有关 ASP.NET 承载层如何管理进程范围的行为的信息。</span><span class="sxs-lookup"><span data-stu-id="2c754-103">Contains information about how the ASP.NET hosting layer manages process-wide behavior.</span></span>  
  
[<span data-ttu-id="2c754-104"> **\<configuration>** </span><span class="sxs-lookup"><span data-stu-id="2c754-104">**\<configuration>**</span></span>](../configuration-element.md)  
<span data-ttu-id="2c754-105">&nbsp;&nbsp; **\<system.web >**</span><span class="sxs-lookup"><span data-stu-id="2c754-105">&nbsp;&nbsp;**\<system.web>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2c754-106">语法</span><span class="sxs-lookup"><span data-stu-id="2c754-106">Syntax</span></span>  
  
```xml  
<system.web>  
</system.web>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="2c754-107">属性和元素</span><span class="sxs-lookup"><span data-stu-id="2c754-107">Attributes and Elements</span></span>  

<span data-ttu-id="2c754-108">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="2c754-108">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="2c754-109">Attributes</span><span class="sxs-lookup"><span data-stu-id="2c754-109">Attributes</span></span>  

<span data-ttu-id="2c754-110">无。</span><span class="sxs-lookup"><span data-stu-id="2c754-110">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="2c754-111">子元素</span><span class="sxs-lookup"><span data-stu-id="2c754-111">Child Elements</span></span>  
  
|<span data-ttu-id="2c754-112">元素</span><span class="sxs-lookup"><span data-stu-id="2c754-112">Element</span></span>|<span data-ttu-id="2c754-113">说明</span><span class="sxs-lookup"><span data-stu-id="2c754-113">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="2c754-114">\<applicationPool></span><span class="sxs-lookup"><span data-stu-id="2c754-114">\<applicationPool></span></span>](applicationpool-element-web-settings.md)|<span data-ttu-id="2c754-115">为 aspnet 文件中的 IIS 应用程序池指定配置设置。</span><span class="sxs-lookup"><span data-stu-id="2c754-115">Specifies configuration settings for IIS application pools in an aspnet.config file.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="2c754-116">父元素</span><span class="sxs-lookup"><span data-stu-id="2c754-116">Parent Elements</span></span>  
  
|<span data-ttu-id="2c754-117">元素</span><span class="sxs-lookup"><span data-stu-id="2c754-117">Element</span></span>|<span data-ttu-id="2c754-118">说明</span><span class="sxs-lookup"><span data-stu-id="2c754-118">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="2c754-119">\<configuration></span><span class="sxs-lookup"><span data-stu-id="2c754-119">\<configuration></span></span>](../configuration-element.md)|<span data-ttu-id="2c754-120">指定公共语言运行时和 .NET Framework 应用程序所使用的每个配置文件中的根元素。</span><span class="sxs-lookup"><span data-stu-id="2c754-120">Specifies the root element in every configuration file that is used by the common language runtime and .NET Framework applications.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="2c754-121">备注</span><span class="sxs-lookup"><span data-stu-id="2c754-121">Remarks</span></span>  

<span data-ttu-id="2c754-122">`system.web` 元素及其子 `applicationPool` 元素已添加到 .NET Framework 3.5 SP1 中的 .NET Framework。</span><span class="sxs-lookup"><span data-stu-id="2c754-122">The `system.web` element and its child `applicationPool` element were added to the .NET Framework as of .NET Framework 3.5 SP1.</span></span> <span data-ttu-id="2c754-123">在集成模式下运行 IIS 7.0 或更高版本时，此元素组合可让你配置 ASP.NET 管理线程的方式，以及在 ASP.NET 托管在 IIS 应用程序池中时，如何将请求排队。</span><span class="sxs-lookup"><span data-stu-id="2c754-123">When you run IIS 7.0 or later versions in Integrated mode, this element combination lets you configure how ASP.NET manages threads and how it queues requests when ASP.NET is hosted in an IIS application pool.</span></span> <span data-ttu-id="2c754-124">如果在经典或 ISAPI 模式下运行 IIS 7.0 或更高版本，则将忽略这些设置。</span><span class="sxs-lookup"><span data-stu-id="2c754-124">If you run IIS 7.0 or later versions in Classic or ISAPI mode, these settings are ignored.</span></span>  
  
## <a name="example"></a><span data-ttu-id="2c754-125">示例</span><span class="sxs-lookup"><span data-stu-id="2c754-125">Example</span></span>  

<span data-ttu-id="2c754-126">下面的示例演示当 ASP.NET 托管在 IIS 应用程序池中时，如何在 ASP.NET 文件中配置进程范围行为。</span><span class="sxs-lookup"><span data-stu-id="2c754-126">The following example shows how to configure ASP.NET process-wide behavior in the aspnet.config file when ASP.NET is hosted in an IIS application pool.</span></span> <span data-ttu-id="2c754-127">该示例假设 IIS 在集成模式下运行，并且该应用程序正在使用 .NET Framework 3.5 SP1 或更高版本。</span><span class="sxs-lookup"><span data-stu-id="2c754-127">The example assumes that IIS is running in Integrated mode and that the application is using the .NET Framework 3.5 SP1 or a later version.</span></span> <span data-ttu-id="2c754-128">此行为不会在早于 .NET Framework 3.5 SP1 的 .NET Framework 版本中发生。</span><span class="sxs-lookup"><span data-stu-id="2c754-128">This behavior does not occur in versions of the .NET Framework earlier than the .NET Framework 3.5 SP1.</span></span> <span data-ttu-id="2c754-129">示例中的值为默认值。</span><span class="sxs-lookup"><span data-stu-id="2c754-129">The values in the example are the default values.</span></span>  
  
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
  
## <a name="element-information"></a><span data-ttu-id="2c754-130">元素信息</span><span class="sxs-lookup"><span data-stu-id="2c754-130">Element Information</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="2c754-131">命名空间</span><span class="sxs-lookup"><span data-stu-id="2c754-131">Namespace</span></span>||  
|<span data-ttu-id="2c754-132">架构名称</span><span class="sxs-lookup"><span data-stu-id="2c754-132">Schema Name</span></span>||  
|<span data-ttu-id="2c754-133">验证文件</span><span class="sxs-lookup"><span data-stu-id="2c754-133">Validation File</span></span>||  
|<span data-ttu-id="2c754-134">可以为空</span><span class="sxs-lookup"><span data-stu-id="2c754-134">Can be Empty</span></span>||  
  
## <a name="see-also"></a><span data-ttu-id="2c754-135">另请参阅</span><span class="sxs-lookup"><span data-stu-id="2c754-135">See also</span></span>

- [<span data-ttu-id="2c754-136">\<applicationPool> 元素（Web 设置）</span><span class="sxs-lookup"><span data-stu-id="2c754-136">\<applicationPool> Element (Web Settings)</span></span>](applicationpool-element-web-settings.md)
