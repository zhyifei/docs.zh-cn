---
title: '&lt;system.web&gt;元素 （Web 设置）'
ms.date: 03/30/2017
helpviewer_keywords:
- Web.config configuration file [ASP.NET]
- system.Web element
- <system.Web> element
- ASP.NET configuration system
- configuration files [ASP.NET]
ms.assetid: 24c4cf4f-ad32-42b2-b040-8e4549e2855e
author: mcleblanc
ms.author: markl
ms.openlocfilehash: 39d305d429490380c76e15bdcdde434f0d75457b
ms.sourcegitcommit: 213292dfbb0c37d83f62709959ff55c50af5560d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/25/2018
ms.locfileid: "47083132"
---
# <a name="ltsystemwebgt-element-web-settings"></a><span data-ttu-id="5c7a8-102">&lt;system.web&gt;元素 （Web 设置）</span><span class="sxs-lookup"><span data-stu-id="5c7a8-102">&lt;system.web&gt; Element (Web Settings)</span></span>
<span data-ttu-id="5c7a8-103">包含有关 ASP.NET 托管层管理进程范围的行为方式的信息。</span><span class="sxs-lookup"><span data-stu-id="5c7a8-103">Contains information about how the ASP.NET hosting layer manages process-wide behavior.</span></span>  
  
 <span data-ttu-id="5c7a8-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="5c7a8-104">\<configuration></span></span>  
<span data-ttu-id="5c7a8-105">\<system.web > 元素 （Web 设置）</span><span class="sxs-lookup"><span data-stu-id="5c7a8-105">\<system.web> Element (Web Settings)</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5c7a8-106">语法</span><span class="sxs-lookup"><span data-stu-id="5c7a8-106">Syntax</span></span>  
  
```xml  
<system.web>  
</system.web>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="5c7a8-107">特性和元素</span><span class="sxs-lookup"><span data-stu-id="5c7a8-107">Attributes and Elements</span></span>  
 <span data-ttu-id="5c7a8-108">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="5c7a8-108">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="5c7a8-109">特性</span><span class="sxs-lookup"><span data-stu-id="5c7a8-109">Attributes</span></span>  
 <span data-ttu-id="5c7a8-110">无。</span><span class="sxs-lookup"><span data-stu-id="5c7a8-110">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="5c7a8-111">子元素</span><span class="sxs-lookup"><span data-stu-id="5c7a8-111">Child Elements</span></span>  
  
|<span data-ttu-id="5c7a8-112">元素</span><span class="sxs-lookup"><span data-stu-id="5c7a8-112">Element</span></span>|<span data-ttu-id="5c7a8-113">描述</span><span class="sxs-lookup"><span data-stu-id="5c7a8-113">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="5c7a8-114">\<applicationPool></span><span class="sxs-lookup"><span data-stu-id="5c7a8-114">\<applicationPool></span></span>](../../../../../docs/framework/configure-apps/file-schema/web/applicationpool-element-web-settings.md)|<span data-ttu-id="5c7a8-115">在 aspnet.config 文件中指定 IIS 应用程序池配置的设置。</span><span class="sxs-lookup"><span data-stu-id="5c7a8-115">Specifies configuration settings for IIS application pools in an aspnet.config file.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="5c7a8-116">父元素</span><span class="sxs-lookup"><span data-stu-id="5c7a8-116">Parent Elements</span></span>  
  
|<span data-ttu-id="5c7a8-117">元素</span><span class="sxs-lookup"><span data-stu-id="5c7a8-117">Element</span></span>|<span data-ttu-id="5c7a8-118">描述</span><span class="sxs-lookup"><span data-stu-id="5c7a8-118">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="5c7a8-119">\<configuration></span><span class="sxs-lookup"><span data-stu-id="5c7a8-119">\<configuration></span></span>](../../../../../docs/framework/configure-apps/file-schema/configuration-element.md)|<span data-ttu-id="5c7a8-120">指定公共语言运行时和 [!INCLUDE[dnprdnshort](../../../../../includes/dnprdnshort-md.md)] 应用程序所使用的每个配置文件中的根元素。</span><span class="sxs-lookup"><span data-stu-id="5c7a8-120">Specifies the root element in every configuration file that is used by the common language runtime and [!INCLUDE[dnprdnshort](../../../../../includes/dnprdnshort-md.md)] applications.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="5c7a8-121">备注</span><span class="sxs-lookup"><span data-stu-id="5c7a8-121">Remarks</span></span>  
 <span data-ttu-id="5c7a8-122">`system.web`元素及其子`applicationPool`元素添加到[!INCLUDE[dnprdnshort](../../../../../includes/dnprdnshort-md.md)]在[!INCLUDE[net_v35SP1_short](../../../../../includes/net-v35sp1-short-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="5c7a8-122">The `system.web` element and its child `applicationPool` element were added to the [!INCLUDE[dnprdnshort](../../../../../includes/dnprdnshort-md.md)] as of [!INCLUDE[net_v35SP1_short](../../../../../includes/net-v35sp1-short-md.md)].</span></span> <span data-ttu-id="5c7a8-123">当你运行[!INCLUDE[iisver](../../../../../includes/iisver-md.md)]或更高版本中集成模式下，此元素组合可让你配置 ASP.NET 如何管理线程以及当 ASP.NET 承载于 IIS 应用程序池进行排队请求的方式。</span><span class="sxs-lookup"><span data-stu-id="5c7a8-123">When you run [!INCLUDE[iisver](../../../../../includes/iisver-md.md)] or later versions in Integrated mode, this element combination lets you configure how ASP.NET manages threads and how it queues requests when ASP.NET is hosted in an IIS application pool.</span></span> <span data-ttu-id="5c7a8-124">如果您运行[!INCLUDE[iisver](../../../../../includes/iisver-md.md)]或更高版本在经典或 ISAPI 模式下，将忽略这些设置。</span><span class="sxs-lookup"><span data-stu-id="5c7a8-124">If you run [!INCLUDE[iisver](../../../../../includes/iisver-md.md)] or later versions in Classic or ISAPI mode, these settings are ignored.</span></span>  
  
## <a name="example"></a><span data-ttu-id="5c7a8-125">示例</span><span class="sxs-lookup"><span data-stu-id="5c7a8-125">Example</span></span>  
 <span data-ttu-id="5c7a8-126">下面的示例演示如何配置 ASP.NET 进程范围行为的 aspnet.config 文件中，当 ASP.NET 承载于 IIS 应用程序池。</span><span class="sxs-lookup"><span data-stu-id="5c7a8-126">The following example shows how to configure ASP.NET process-wide behavior in the aspnet.config file when ASP.NET is hosted in an IIS application pool.</span></span> <span data-ttu-id="5c7a8-127">该示例假定 IIS 正在运行以集成模式和应用程序使用[!INCLUDE[net_v35SP1_short](../../../../../includes/net-v35sp1-short-md.md)]或更高版本。</span><span class="sxs-lookup"><span data-stu-id="5c7a8-127">The example assumes that IIS is running in Integrated mode and that the application is using the [!INCLUDE[net_v35SP1_short](../../../../../includes/net-v35sp1-short-md.md)] or a later version.</span></span> <span data-ttu-id="5c7a8-128">版本中，此行为不会发生[!INCLUDE[dnprdnshort](../../../../../includes/dnprdnshort-md.md)]早于[!INCLUDE[net_v35SP1_short](../../../../../includes/net-v35sp1-short-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="5c7a8-128">This behavior does not occur in versions of the [!INCLUDE[dnprdnshort](../../../../../includes/dnprdnshort-md.md)] earlier than the [!INCLUDE[net_v35SP1_short](../../../../../includes/net-v35sp1-short-md.md)].</span></span> <span data-ttu-id="5c7a8-129">在示例中的值是默认值。</span><span class="sxs-lookup"><span data-stu-id="5c7a8-129">The values in the example are the default values.</span></span>  
  
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
  
## <a name="element-information"></a><span data-ttu-id="5c7a8-130">元素信息</span><span class="sxs-lookup"><span data-stu-id="5c7a8-130">Element Information</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="5c7a8-131">命名空间</span><span class="sxs-lookup"><span data-stu-id="5c7a8-131">Namespace</span></span>||  
|<span data-ttu-id="5c7a8-132">架构名称</span><span class="sxs-lookup"><span data-stu-id="5c7a8-132">Schema Name</span></span>||  
|<span data-ttu-id="5c7a8-133">验证文件</span><span class="sxs-lookup"><span data-stu-id="5c7a8-133">Validation File</span></span>||  
|<span data-ttu-id="5c7a8-134">可以为空</span><span class="sxs-lookup"><span data-stu-id="5c7a8-134">Can be Empty</span></span>||  
  
## <a name="see-also"></a><span data-ttu-id="5c7a8-135">请参阅</span><span class="sxs-lookup"><span data-stu-id="5c7a8-135">See Also</span></span>  
 [<span data-ttu-id="5c7a8-136">\<applicationPool> 元素（Web 设置）</span><span class="sxs-lookup"><span data-stu-id="5c7a8-136">\<applicationPool> Element (Web Settings)</span></span>](../../../../../docs/framework/configure-apps/file-schema/web/applicationpool-element-web-settings.md)
