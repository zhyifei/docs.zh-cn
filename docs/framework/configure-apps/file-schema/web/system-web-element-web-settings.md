---
title: "&lt;system.web&gt;元素 （Web 设置）"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Web.config configuration file [ASP.NET]
- system.Web element
- <system.Web> element
- ASP.NET configuration system
- configuration files [ASP.NET]
ms.assetid: 24c4cf4f-ad32-42b2-b040-8e4549e2855e
caps.latest.revision: "9"
author: mcleblanc
ms.author: markl
manager: markl
ms.openlocfilehash: 44a978eae9ae85e1ba12f117288a3c9ce4db75b4
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="ltsystemwebgt-element-web-settings"></a><span data-ttu-id="38b8b-102">&lt;system.web&gt;元素 （Web 设置）</span><span class="sxs-lookup"><span data-stu-id="38b8b-102">&lt;system.web&gt; Element (Web Settings)</span></span>
<span data-ttu-id="38b8b-103">包含有关如何在 ASP.NET 承载层管理进程范围的行为的信息。</span><span class="sxs-lookup"><span data-stu-id="38b8b-103">Contains information about how the ASP.NET hosting layer manages process-wide behavior.</span></span>  
  
 <span data-ttu-id="38b8b-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="38b8b-104">\<configuration></span></span>  
<span data-ttu-id="38b8b-105">\<.w e b > 元素 （Web 设置）</span><span class="sxs-lookup"><span data-stu-id="38b8b-105">\<system.web> Element (Web Settings)</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="38b8b-106">语法</span><span class="sxs-lookup"><span data-stu-id="38b8b-106">Syntax</span></span>  
  
```xml  
<system.web>  
</system.web>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="38b8b-107">特性和元素</span><span class="sxs-lookup"><span data-stu-id="38b8b-107">Attributes and Elements</span></span>  
 <span data-ttu-id="38b8b-108">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="38b8b-108">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="38b8b-109">特性</span><span class="sxs-lookup"><span data-stu-id="38b8b-109">Attributes</span></span>  
 <span data-ttu-id="38b8b-110">无。</span><span class="sxs-lookup"><span data-stu-id="38b8b-110">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="38b8b-111">子元素</span><span class="sxs-lookup"><span data-stu-id="38b8b-111">Child Elements</span></span>  
  
|<span data-ttu-id="38b8b-112">元素</span><span class="sxs-lookup"><span data-stu-id="38b8b-112">Element</span></span>|<span data-ttu-id="38b8b-113">描述</span><span class="sxs-lookup"><span data-stu-id="38b8b-113">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="38b8b-114">\<applicationPool></span><span class="sxs-lookup"><span data-stu-id="38b8b-114">\<applicationPool></span></span>](../../../../../docs/framework/configure-apps/file-schema/web/applicationpool-element-web-settings.md)|<span data-ttu-id="38b8b-115">在 aspnet.config 文件中指定 IIS 应用程序池配置的设置。</span><span class="sxs-lookup"><span data-stu-id="38b8b-115">Specifies configuration settings for IIS application pools in an aspnet.config file.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="38b8b-116">父元素</span><span class="sxs-lookup"><span data-stu-id="38b8b-116">Parent Elements</span></span>  
  
|<span data-ttu-id="38b8b-117">元素</span><span class="sxs-lookup"><span data-stu-id="38b8b-117">Element</span></span>|<span data-ttu-id="38b8b-118">描述</span><span class="sxs-lookup"><span data-stu-id="38b8b-118">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="38b8b-119">\<configuration></span><span class="sxs-lookup"><span data-stu-id="38b8b-119">\<configuration></span></span>](../../../../../docs/framework/configure-apps/file-schema/configuration-element.md)|<span data-ttu-id="38b8b-120">指定公共语言运行时和 [!INCLUDE[dnprdnshort](../../../../../includes/dnprdnshort-md.md)] 应用程序所使用的每个配置文件中的根元素。</span><span class="sxs-lookup"><span data-stu-id="38b8b-120">Specifies the root element in every configuration file that is used by the common language runtime and [!INCLUDE[dnprdnshort](../../../../../includes/dnprdnshort-md.md)] applications.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="38b8b-121">备注</span><span class="sxs-lookup"><span data-stu-id="38b8b-121">Remarks</span></span>  
 <span data-ttu-id="38b8b-122">`system.web`元素及其子`applicationPool`元素已添加到[!INCLUDE[dnprdnshort](../../../../../includes/dnprdnshort-md.md)]在[!INCLUDE[net_v35SP1_short](../../../../../includes/net-v35sp1-short-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="38b8b-122">The `system.web` element and its child `applicationPool` element were added to the [!INCLUDE[dnprdnshort](../../../../../includes/dnprdnshort-md.md)] as of [!INCLUDE[net_v35SP1_short](../../../../../includes/net-v35sp1-short-md.md)].</span></span> <span data-ttu-id="38b8b-123">当你运行[!INCLUDE[iisver](../../../../../includes/iisver-md.md)]或在集成模式下的更高版本，此元素组合允许你配置 ASP.NET 如何管理线程，以及当 ASP.NET 承载于 IIS 应用程序池进行排队请求的方式。</span><span class="sxs-lookup"><span data-stu-id="38b8b-123">When you run [!INCLUDE[iisver](../../../../../includes/iisver-md.md)] or later versions in Integrated mode, this element combination lets you configure how ASP.NET manages threads and how it queues requests when ASP.NET is hosted in an IIS application pool.</span></span> <span data-ttu-id="38b8b-124">如果你运行[!INCLUDE[iisver](../../../../../includes/iisver-md.md)]或更高版本在经典或 ISAPI 模式下，这些设置将被忽略。</span><span class="sxs-lookup"><span data-stu-id="38b8b-124">If you run [!INCLUDE[iisver](../../../../../includes/iisver-md.md)] or later versions in Classic or ISAPI mode, these settings are ignored.</span></span>  
  
## <a name="example"></a><span data-ttu-id="38b8b-125">示例</span><span class="sxs-lookup"><span data-stu-id="38b8b-125">Example</span></span>  
 <span data-ttu-id="38b8b-126">下面的示例演示如何配置 ASP.NET 进程范围的行为的 aspnet.config 文件中，当 ASP.NET 承载于 IIS 应用程序池。</span><span class="sxs-lookup"><span data-stu-id="38b8b-126">The following example shows how to configure ASP.NET process-wide behavior in the aspnet.config file when ASP.NET is hosted in an IIS application pool.</span></span> <span data-ttu-id="38b8b-127">该示例假设在集成的正在运行 IIS 模式和应用程序正在使用[!INCLUDE[net_v35SP1_short](../../../../../includes/net-v35sp1-short-md.md)]或更高版本。</span><span class="sxs-lookup"><span data-stu-id="38b8b-127">The example assumes that IIS is running in Integrated mode and that the application is using the [!INCLUDE[net_v35SP1_short](../../../../../includes/net-v35sp1-short-md.md)] or a later version.</span></span> <span data-ttu-id="38b8b-128">版本中不会发生此行为[!INCLUDE[dnprdnshort](../../../../../includes/dnprdnshort-md.md)]早于[!INCLUDE[net_v35SP1_short](../../../../../includes/net-v35sp1-short-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="38b8b-128">This behavior does not occur in versions of the [!INCLUDE[dnprdnshort](../../../../../includes/dnprdnshort-md.md)] earlier than the [!INCLUDE[net_v35SP1_short](../../../../../includes/net-v35sp1-short-md.md)].</span></span> <span data-ttu-id="38b8b-129">在示例中的值是默认值。</span><span class="sxs-lookup"><span data-stu-id="38b8b-129">The values in the example are the default values.</span></span>  
  
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
  
## <a name="element-information"></a><span data-ttu-id="38b8b-130">元素信息</span><span class="sxs-lookup"><span data-stu-id="38b8b-130">Element Information</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="38b8b-131">命名空间</span><span class="sxs-lookup"><span data-stu-id="38b8b-131">Namespace</span></span>||  
|<span data-ttu-id="38b8b-132">架构名称</span><span class="sxs-lookup"><span data-stu-id="38b8b-132">Schema Name</span></span>||  
|<span data-ttu-id="38b8b-133">验证文件</span><span class="sxs-lookup"><span data-stu-id="38b8b-133">Validation File</span></span>||  
|<span data-ttu-id="38b8b-134">可以为空</span><span class="sxs-lookup"><span data-stu-id="38b8b-134">Can be Empty</span></span>||  
  
## <a name="see-also"></a><span data-ttu-id="38b8b-135">另请参阅</span><span class="sxs-lookup"><span data-stu-id="38b8b-135">See Also</span></span>  
 [<span data-ttu-id="38b8b-136">\<applicationPool> 元素（Web 设置）</span><span class="sxs-lookup"><span data-stu-id="38b8b-136">\<applicationPool> Element (Web Settings)</span></span>](../../../../../docs/framework/configure-apps/file-schema/web/applicationpool-element-web-settings.md)
