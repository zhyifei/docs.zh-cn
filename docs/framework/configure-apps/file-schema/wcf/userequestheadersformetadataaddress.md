---
title: '&lt;useRequestHeadersForMetadataAddress&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 679f0eae-f353-44d1-b42d-a9e247509774
caps.latest.revision: "2"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 1e7f69da871376f83422fb330f8babd56bb1fdcb
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/02/2017
---
# <a name="ltuserequestheadersformetadataaddressgt"></a><span data-ttu-id="8f356-102">&lt;useRequestHeadersForMetadataAddress&gt;</span><span class="sxs-lookup"><span data-stu-id="8f356-102">&lt;useRequestHeadersForMetadataAddress&gt;</span></span>
<span data-ttu-id="8f356-103">允许从请求消息头中检索元数据地址信息。</span><span class="sxs-lookup"><span data-stu-id="8f356-103">Enables the retrieval of metadata address information from the request message headers.</span></span>  
  
<span data-ttu-id="8f356-104">\<系统。ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="8f356-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="8f356-105">\<行为 ></span><span class="sxs-lookup"><span data-stu-id="8f356-105">\<behaviors></span></span>  
<span data-ttu-id="8f356-106">\<serviceBehaviors ></span><span class="sxs-lookup"><span data-stu-id="8f356-106">\<serviceBehaviors></span></span>  
<span data-ttu-id="8f356-107">\<行为 ></span><span class="sxs-lookup"><span data-stu-id="8f356-107">\<behavior></span></span>  
<span data-ttu-id="8f356-108">\<useRequestHeadersForMetadataAddress ></span><span class="sxs-lookup"><span data-stu-id="8f356-108">\<useRequestHeadersForMetadataAddress></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8f356-109">语法</span><span class="sxs-lookup"><span data-stu-id="8f356-109">Syntax</span></span>  
  
```xml  
<useRequestHeadersForMetadataAddress>
  <defaultPorts>
    <add scheme="http" port="integer" />
  </defaultPorts>
</useRequestHeadersForMetadataAddress>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="8f356-110">特性和元素</span><span class="sxs-lookup"><span data-stu-id="8f356-110">Attributes and Elements</span></span>  
 <span data-ttu-id="8f356-111">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="8f356-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="8f356-112">特性</span><span class="sxs-lookup"><span data-stu-id="8f356-112">Attributes</span></span>  
 <span data-ttu-id="8f356-113">无。</span><span class="sxs-lookup"><span data-stu-id="8f356-113">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="8f356-114">子元素</span><span class="sxs-lookup"><span data-stu-id="8f356-114">Child Elements</span></span>  
  
|<span data-ttu-id="8f356-115">元素</span><span class="sxs-lookup"><span data-stu-id="8f356-115">Element</span></span>|<span data-ttu-id="8f356-116">描述</span><span class="sxs-lookup"><span data-stu-id="8f356-116">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="8f356-117">\<d d ></span><span class="sxs-lookup"><span data-stu-id="8f356-117">\<defaultPorts></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/defaultports.md)|<span data-ttu-id="8f356-118">一个默认端口集合，列出客户端应用程序侦听的默认通信终结点。</span><span class="sxs-lookup"><span data-stu-id="8f356-118">A collection of default ports listing the default communications endpoints that the client application listens to.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="8f356-119">父元素</span><span class="sxs-lookup"><span data-stu-id="8f356-119">Parent Elements</span></span>  
  
|<span data-ttu-id="8f356-120">元素</span><span class="sxs-lookup"><span data-stu-id="8f356-120">Element</span></span>|<span data-ttu-id="8f356-121">描述</span><span class="sxs-lookup"><span data-stu-id="8f356-121">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="8f356-122">\<行为 ></span><span class="sxs-lookup"><span data-stu-id="8f356-122">\<behavior></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md)|<span data-ttu-id="8f356-123">指定行为元素。</span><span class="sxs-lookup"><span data-stu-id="8f356-123">Specifies a behavior element.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="8f356-124">另请参阅</span><span class="sxs-lookup"><span data-stu-id="8f356-124">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.UseRequestHeadersForMetadataAddressElement>
