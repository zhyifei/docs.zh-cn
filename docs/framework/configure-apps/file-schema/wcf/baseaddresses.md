---
title: "&lt;基址&gt;"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 78918102-2898-46e0-9ea8-6b8afe65603e
caps.latest.revision: "9"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 4bf698b64b528b0ea109223a2d94e6725c8ce6b5
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="ltbaseaddressesgt"></a><span data-ttu-id="ce0c8-102">&lt;基址&gt;</span><span class="sxs-lookup"><span data-stu-id="ce0c8-102">&lt;baseAddresses&gt;</span></span>
<span data-ttu-id="ce0c8-103">表示一个 `baseAddress` 元素集合，这些元素是自承载环境中服务主机的基址。</span><span class="sxs-lookup"><span data-stu-id="ce0c8-103">Represents a collection of `baseAddress` elements, which are base addresses for a service host in a self-hosted environment.</span></span> <span data-ttu-id="ce0c8-104">如果存在基址，则可以使用相对于基址的地址配置终结点。</span><span class="sxs-lookup"><span data-stu-id="ce0c8-104">If a base address is present, endpoints can be configured with addresses relative to the base address.</span></span>  
  
 <span data-ttu-id="ce0c8-105">\<系统。ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="ce0c8-105">\<system.ServiceModel></span></span>  
<span data-ttu-id="ce0c8-106">\<客户端 ></span><span class="sxs-lookup"><span data-stu-id="ce0c8-106">\<client></span></span>  
<span data-ttu-id="ce0c8-107">\<终结点 ></span><span class="sxs-lookup"><span data-stu-id="ce0c8-107">\<endpoint></span></span>  
<span data-ttu-id="ce0c8-108">\<主机 ></span><span class="sxs-lookup"><span data-stu-id="ce0c8-108">\<host></span></span>  
<span data-ttu-id="ce0c8-109">\<基址 ></span><span class="sxs-lookup"><span data-stu-id="ce0c8-109">\<baseAddresses></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ce0c8-110">语法</span><span class="sxs-lookup"><span data-stu-id="ce0c8-110">Syntax</span></span>  
  
```xml  
<baseAddresses>  
   <add baseAddress="string" />  
</baseAddresses>  
```  
  
## <a name="type"></a><span data-ttu-id="ce0c8-111">类型</span><span class="sxs-lookup"><span data-stu-id="ce0c8-111">Type</span></span>  
 `Type`  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="ce0c8-112">特性和元素</span><span class="sxs-lookup"><span data-stu-id="ce0c8-112">Attributes and Elements</span></span>  
 <span data-ttu-id="ce0c8-113">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="ce0c8-113">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="ce0c8-114">特性</span><span class="sxs-lookup"><span data-stu-id="ce0c8-114">Attributes</span></span>  
 <span data-ttu-id="ce0c8-115">无。</span><span class="sxs-lookup"><span data-stu-id="ce0c8-115">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="ce0c8-116">子元素</span><span class="sxs-lookup"><span data-stu-id="ce0c8-116">Child Elements</span></span>  
  
|<span data-ttu-id="ce0c8-117">元素</span><span class="sxs-lookup"><span data-stu-id="ce0c8-117">Element</span></span>|<span data-ttu-id="ce0c8-118">说明</span><span class="sxs-lookup"><span data-stu-id="ce0c8-118">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="ce0c8-119">\<add></span><span class="sxs-lookup"><span data-stu-id="ce0c8-119">\<add></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/add-of-baseaddresses.md)|<span data-ttu-id="ce0c8-120">一个配置元素，指定服务主机所使用的基址。</span><span class="sxs-lookup"><span data-stu-id="ce0c8-120">A configuration element that specifies the base addresses used by the service host.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="ce0c8-121">父元素</span><span class="sxs-lookup"><span data-stu-id="ce0c8-121">Parent Elements</span></span>  
  
|<span data-ttu-id="ce0c8-122">元素</span><span class="sxs-lookup"><span data-stu-id="ce0c8-122">Element</span></span>|<span data-ttu-id="ce0c8-123">描述</span><span class="sxs-lookup"><span data-stu-id="ce0c8-123">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="ce0c8-124">\<主机 ></span><span class="sxs-lookup"><span data-stu-id="ce0c8-124">\<host></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/host.md)|<span data-ttu-id="ce0c8-125">一个指定服务主机设置的配置元素。</span><span class="sxs-lookup"><span data-stu-id="ce0c8-125">A configuration element that specifies settings for a service host.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="ce0c8-126">另请参阅</span><span class="sxs-lookup"><span data-stu-id="ce0c8-126">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.HostElement>  
 <xref:System.ServiceModel.ServiceHost>  
 <xref:System.ServiceModel.ServiceHostBase.BaseAddresses%2A>  
 [<span data-ttu-id="ce0c8-127">承载</span><span class="sxs-lookup"><span data-stu-id="ce0c8-127">Hosting</span></span>](../../../../../docs/framework/wcf/feature-details/hosting.md)
