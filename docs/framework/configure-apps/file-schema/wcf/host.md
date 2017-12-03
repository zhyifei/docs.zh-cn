---
title: "&lt;主机&gt;"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: be566d55-9d50-4b2e-985d-52a5cc26cbbb
caps.latest.revision: "7"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: d498190e7d7c3a6e879c50324e3b973f0f8e8fa6
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/02/2017
---
# <a name="lthostgt"></a><span data-ttu-id="e0fcc-102">&lt;主机&gt;</span><span class="sxs-lookup"><span data-stu-id="e0fcc-102">&lt;host&gt;</span></span>
<span data-ttu-id="e0fcc-103">指定服务主机的设置。</span><span class="sxs-lookup"><span data-stu-id="e0fcc-103">Specifies settings for a service host.</span></span>  
  
 <span data-ttu-id="e0fcc-104">\<系统。ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="e0fcc-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="e0fcc-105">\<服务 ></span><span class="sxs-lookup"><span data-stu-id="e0fcc-105">\<services></span></span>  
<span data-ttu-id="e0fcc-106">\<服务 ></span><span class="sxs-lookup"><span data-stu-id="e0fcc-106">\<service></span></span>  
<span data-ttu-id="e0fcc-107">\<主机 ></span><span class="sxs-lookup"><span data-stu-id="e0fcc-107">\<host></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e0fcc-108">语法</span><span class="sxs-lookup"><span data-stu-id="e0fcc-108">Syntax</span></span>  
  
```xml  
<host>  
      <baseAddresses>  
         <baseAddress baseAddress="string" />  
      </baseAddresses>  
      <timeOuts closeTimeout="TimeSpan"  
         openTimeout="TimeSpan" >  
</host>  
```  
  
## <a name="type"></a><span data-ttu-id="e0fcc-109">类型</span><span class="sxs-lookup"><span data-stu-id="e0fcc-109">Type</span></span>  
 `Type`  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="e0fcc-110">特性和元素</span><span class="sxs-lookup"><span data-stu-id="e0fcc-110">Attributes and Elements</span></span>  
 <span data-ttu-id="e0fcc-111">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="e0fcc-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="e0fcc-112">特性</span><span class="sxs-lookup"><span data-stu-id="e0fcc-112">Attributes</span></span>  
 <span data-ttu-id="e0fcc-113">无。</span><span class="sxs-lookup"><span data-stu-id="e0fcc-113">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="e0fcc-114">子元素</span><span class="sxs-lookup"><span data-stu-id="e0fcc-114">Child Elements</span></span>  
  
|<span data-ttu-id="e0fcc-115">元素</span><span class="sxs-lookup"><span data-stu-id="e0fcc-115">Element</span></span>|<span data-ttu-id="e0fcc-116">描述</span><span class="sxs-lookup"><span data-stu-id="e0fcc-116">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="e0fcc-117">\<基址 ></span><span class="sxs-lookup"><span data-stu-id="e0fcc-117">\<baseAddresses></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/baseaddresses.md)|<span data-ttu-id="e0fcc-118">`baseAddress` 元素的集合，指定服务主机所使用的基址。</span><span class="sxs-lookup"><span data-stu-id="e0fcc-118">A collection of `baseAddress` elements that specifies the base addresses used by the service host.</span></span>|  
|[<span data-ttu-id="e0fcc-119">\<超时 ></span><span class="sxs-lookup"><span data-stu-id="e0fcc-119">\<timeOuts></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/timeouts.md)|<span data-ttu-id="e0fcc-120">一个配置元素，指定为打开或关闭服务主机预留的时间间隔。</span><span class="sxs-lookup"><span data-stu-id="e0fcc-120">A configuration element that specifies the interval of time allowed for the service host to open or close.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="e0fcc-121">父元素</span><span class="sxs-lookup"><span data-stu-id="e0fcc-121">Parent Elements</span></span>  
  
|<span data-ttu-id="e0fcc-122">元素</span><span class="sxs-lookup"><span data-stu-id="e0fcc-122">Element</span></span>|<span data-ttu-id="e0fcc-123">描述</span><span class="sxs-lookup"><span data-stu-id="e0fcc-123">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="e0fcc-124">\<服务 ></span><span class="sxs-lookup"><span data-stu-id="e0fcc-124">\<service></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/service.md)|<span data-ttu-id="e0fcc-125">指定 [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)] 服务的设置。</span><span class="sxs-lookup"><span data-stu-id="e0fcc-125">Specifies the settings for a [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)] service.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="e0fcc-126">另请参阅</span><span class="sxs-lookup"><span data-stu-id="e0fcc-126">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.HostElement>  
 <xref:System.ServiceModel.ServiceHost>  
 [<span data-ttu-id="e0fcc-127">承载</span><span class="sxs-lookup"><span data-stu-id="e0fcc-127">Hosting</span></span>](../../../../../docs/framework/wcf/feature-details/hosting.md)
