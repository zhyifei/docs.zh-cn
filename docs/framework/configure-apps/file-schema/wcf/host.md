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
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: bded8d718259bf4fc84bfe790db069a77fc2a703
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="lthostgt"></a><span data-ttu-id="8da77-102">&lt;主机&gt;</span><span class="sxs-lookup"><span data-stu-id="8da77-102">&lt;host&gt;</span></span>
<span data-ttu-id="8da77-103">指定服务主机的设置。</span><span class="sxs-lookup"><span data-stu-id="8da77-103">Specifies settings for a service host.</span></span>  
  
 <span data-ttu-id="8da77-104">\<系统。ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="8da77-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="8da77-105">\<服务 ></span><span class="sxs-lookup"><span data-stu-id="8da77-105">\<services></span></span>  
<span data-ttu-id="8da77-106">\<服务 ></span><span class="sxs-lookup"><span data-stu-id="8da77-106">\<service></span></span>  
<span data-ttu-id="8da77-107">\<主机 ></span><span class="sxs-lookup"><span data-stu-id="8da77-107">\<host></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8da77-108">语法</span><span class="sxs-lookup"><span data-stu-id="8da77-108">Syntax</span></span>  
  
```xml  
<host>  
      <baseAddresses>  
         <baseAddress baseAddress="string" />  
      </baseAddresses>  
      <timeOuts closeTimeout="TimeSpan"  
         openTimeout="TimeSpan" >  
</host>  
```  
  
## <a name="type"></a><span data-ttu-id="8da77-109">类型</span><span class="sxs-lookup"><span data-stu-id="8da77-109">Type</span></span>  
 `Type`  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="8da77-110">特性和元素</span><span class="sxs-lookup"><span data-stu-id="8da77-110">Attributes and Elements</span></span>  
 <span data-ttu-id="8da77-111">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="8da77-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="8da77-112">特性</span><span class="sxs-lookup"><span data-stu-id="8da77-112">Attributes</span></span>  
 <span data-ttu-id="8da77-113">无。</span><span class="sxs-lookup"><span data-stu-id="8da77-113">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="8da77-114">子元素</span><span class="sxs-lookup"><span data-stu-id="8da77-114">Child Elements</span></span>  
  
|<span data-ttu-id="8da77-115">元素</span><span class="sxs-lookup"><span data-stu-id="8da77-115">Element</span></span>|<span data-ttu-id="8da77-116">描述</span><span class="sxs-lookup"><span data-stu-id="8da77-116">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="8da77-117">\<基址 ></span><span class="sxs-lookup"><span data-stu-id="8da77-117">\<baseAddresses></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/baseaddresses.md)|<span data-ttu-id="8da77-118">`baseAddress` 元素的集合，指定服务主机所使用的基址。</span><span class="sxs-lookup"><span data-stu-id="8da77-118">A collection of `baseAddress` elements that specifies the base addresses used by the service host.</span></span>|  
|[<span data-ttu-id="8da77-119">\<超时 ></span><span class="sxs-lookup"><span data-stu-id="8da77-119">\<timeOuts></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/timeouts.md)|<span data-ttu-id="8da77-120">一个配置元素，指定为打开或关闭服务主机预留的时间间隔。</span><span class="sxs-lookup"><span data-stu-id="8da77-120">A configuration element that specifies the interval of time allowed for the service host to open or close.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="8da77-121">父元素</span><span class="sxs-lookup"><span data-stu-id="8da77-121">Parent Elements</span></span>  
  
|<span data-ttu-id="8da77-122">元素</span><span class="sxs-lookup"><span data-stu-id="8da77-122">Element</span></span>|<span data-ttu-id="8da77-123">描述</span><span class="sxs-lookup"><span data-stu-id="8da77-123">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="8da77-124">\<服务 ></span><span class="sxs-lookup"><span data-stu-id="8da77-124">\<service></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/service.md)|<span data-ttu-id="8da77-125">指定 [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)] 服务的设置。</span><span class="sxs-lookup"><span data-stu-id="8da77-125">Specifies the settings for a [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)] service.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="8da77-126">另请参阅</span><span class="sxs-lookup"><span data-stu-id="8da77-126">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.HostElement>  
 <xref:System.ServiceModel.ServiceHost>  
 [<span data-ttu-id="8da77-127">承载</span><span class="sxs-lookup"><span data-stu-id="8da77-127">Hosting</span></span>](../../../../../docs/framework/wcf/feature-details/hosting.md)
