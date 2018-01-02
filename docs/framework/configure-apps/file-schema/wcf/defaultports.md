---
title: '&lt;d d&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 725d4ee5-bd46-4f0e-9c20-30ba75d6eb2c
caps.latest.revision: "2"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: dd4fba4d7d5bcb0adc5a1a638598af2746ad4cf4
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="ltdefaultportsgt"></a><span data-ttu-id="861d0-102">&lt;d d&gt;</span><span class="sxs-lookup"><span data-stu-id="861d0-102">&lt;defaultPorts&gt;</span></span>
<span data-ttu-id="861d0-103">一个默认端口集合，列出客户端应用程序侦听的默认通信终结点。</span><span class="sxs-lookup"><span data-stu-id="861d0-103">A collection of default ports listing the default communications endpoints that the client application listens to.</span></span>  
  
<span data-ttu-id="861d0-104">\<系统。ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="861d0-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="861d0-105">\<行为 ></span><span class="sxs-lookup"><span data-stu-id="861d0-105">\<behaviors></span></span>  
<span data-ttu-id="861d0-106">\<serviceBehaviors ></span><span class="sxs-lookup"><span data-stu-id="861d0-106">\<serviceBehaviors></span></span>  
<span data-ttu-id="861d0-107">\<行为 ></span><span class="sxs-lookup"><span data-stu-id="861d0-107">\<behavior></span></span>  
<span data-ttu-id="861d0-108">\<useRequestHeadersForMetadataAddress ></span><span class="sxs-lookup"><span data-stu-id="861d0-108">\<useRequestHeadersForMetadataAddress></span></span>  
<span data-ttu-id="861d0-109">\<d d ></span><span class="sxs-lookup"><span data-stu-id="861d0-109">\<defaultPorts></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="861d0-110">语法</span><span class="sxs-lookup"><span data-stu-id="861d0-110">Syntax</span></span>  
  
```xml  
<useRequestHeadersForMetadataAddress>
  <defaultPorts>
    <add scheme="http" port="integer" />
  </defaultPorts>
</useRequestHeadersForMetadataAddress>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="861d0-111">特性和元素</span><span class="sxs-lookup"><span data-stu-id="861d0-111">Attributes and Elements</span></span>  
 <span data-ttu-id="861d0-112">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="861d0-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="861d0-113">特性</span><span class="sxs-lookup"><span data-stu-id="861d0-113">Attributes</span></span>  
 <span data-ttu-id="861d0-114">无。</span><span class="sxs-lookup"><span data-stu-id="861d0-114">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="861d0-115">子元素</span><span class="sxs-lookup"><span data-stu-id="861d0-115">Child Elements</span></span>  
  
|<span data-ttu-id="861d0-116">元素</span><span class="sxs-lookup"><span data-stu-id="861d0-116">Element</span></span>|<span data-ttu-id="861d0-117">描述</span><span class="sxs-lookup"><span data-stu-id="861d0-117">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="861d0-118">\<添加 > 的\<d d ></span><span class="sxs-lookup"><span data-stu-id="861d0-118">\<add> of \<defaultPorts></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/add-of-defaultports.md)|<span data-ttu-id="861d0-119">客户端应用程序侦听的默认通信终结点。</span><span class="sxs-lookup"><span data-stu-id="861d0-119">A default communications endpoint that the client application listens to.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="861d0-120">父元素</span><span class="sxs-lookup"><span data-stu-id="861d0-120">Parent Elements</span></span>  
  
|<span data-ttu-id="861d0-121">元素</span><span class="sxs-lookup"><span data-stu-id="861d0-121">Element</span></span>|<span data-ttu-id="861d0-122">描述</span><span class="sxs-lookup"><span data-stu-id="861d0-122">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="861d0-123">\<useRequestHeadersForMetadataAddress ></span><span class="sxs-lookup"><span data-stu-id="861d0-123">\<useRequestHeadersForMetadataAddress></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/userequestheadersformetadataaddress.md)|<span data-ttu-id="861d0-124">默认端口列表。</span><span class="sxs-lookup"><span data-stu-id="861d0-124">A list of default ports.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="861d0-125">请参阅</span><span class="sxs-lookup"><span data-stu-id="861d0-125">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.DefaultPortElementCollection>
