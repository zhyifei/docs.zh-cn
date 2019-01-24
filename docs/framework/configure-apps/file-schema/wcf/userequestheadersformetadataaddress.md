---
title: '&lt;useRequestHeadersForMetadataAddress&gt;'
ms.date: 03/30/2017
ms.assetid: 679f0eae-f353-44d1-b42d-a9e247509774
ms.openlocfilehash: 6c03057fca23b037702c702b9a574045ebb302b4
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54656617"
---
# <a name="ltuserequestheadersformetadataaddressgt"></a><span data-ttu-id="ba3bb-102">&lt;useRequestHeadersForMetadataAddress&gt;</span><span class="sxs-lookup"><span data-stu-id="ba3bb-102">&lt;useRequestHeadersForMetadataAddress&gt;</span></span>
<span data-ttu-id="ba3bb-103">允许从请求消息头中检索元数据地址信息。</span><span class="sxs-lookup"><span data-stu-id="ba3bb-103">Enables the retrieval of metadata address information from the request message headers.</span></span>  
  
<span data-ttu-id="ba3bb-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="ba3bb-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="ba3bb-105">\<behaviors></span><span class="sxs-lookup"><span data-stu-id="ba3bb-105">\<behaviors></span></span>  
<span data-ttu-id="ba3bb-106">\<serviceBehaviors></span><span class="sxs-lookup"><span data-stu-id="ba3bb-106">\<serviceBehaviors></span></span>  
<span data-ttu-id="ba3bb-107">\<behavior></span><span class="sxs-lookup"><span data-stu-id="ba3bb-107">\<behavior></span></span>  
<span data-ttu-id="ba3bb-108">\<useRequestHeadersForMetadataAddress></span><span class="sxs-lookup"><span data-stu-id="ba3bb-108">\<useRequestHeadersForMetadataAddress></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ba3bb-109">语法</span><span class="sxs-lookup"><span data-stu-id="ba3bb-109">Syntax</span></span>  
  
```xml  
<useRequestHeadersForMetadataAddress>
  <defaultPorts>
    <add scheme="http"
         port="integer" />
  </defaultPorts>
</useRequestHeadersForMetadataAddress>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="ba3bb-110">特性和元素</span><span class="sxs-lookup"><span data-stu-id="ba3bb-110">Attributes and Elements</span></span>  
 <span data-ttu-id="ba3bb-111">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="ba3bb-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="ba3bb-112">特性</span><span class="sxs-lookup"><span data-stu-id="ba3bb-112">Attributes</span></span>  
 <span data-ttu-id="ba3bb-113">无。</span><span class="sxs-lookup"><span data-stu-id="ba3bb-113">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="ba3bb-114">子元素</span><span class="sxs-lookup"><span data-stu-id="ba3bb-114">Child Elements</span></span>  
  
|<span data-ttu-id="ba3bb-115">元素</span><span class="sxs-lookup"><span data-stu-id="ba3bb-115">Element</span></span>|<span data-ttu-id="ba3bb-116">描述</span><span class="sxs-lookup"><span data-stu-id="ba3bb-116">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="ba3bb-117">\<defaultPorts></span><span class="sxs-lookup"><span data-stu-id="ba3bb-117">\<defaultPorts></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/defaultports.md)|<span data-ttu-id="ba3bb-118">一个默认端口集合，列出客户端应用程序侦听的默认通信终结点。</span><span class="sxs-lookup"><span data-stu-id="ba3bb-118">A collection of default ports listing the default communications endpoints that the client application listens to.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="ba3bb-119">父元素</span><span class="sxs-lookup"><span data-stu-id="ba3bb-119">Parent Elements</span></span>  
  
|<span data-ttu-id="ba3bb-120">元素</span><span class="sxs-lookup"><span data-stu-id="ba3bb-120">Element</span></span>|<span data-ttu-id="ba3bb-121">描述</span><span class="sxs-lookup"><span data-stu-id="ba3bb-121">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="ba3bb-122">\<behavior></span><span class="sxs-lookup"><span data-stu-id="ba3bb-122">\<behavior></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md)|<span data-ttu-id="ba3bb-123">指定行为元素。</span><span class="sxs-lookup"><span data-stu-id="ba3bb-123">Specifies a behavior element.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="ba3bb-124">请参阅</span><span class="sxs-lookup"><span data-stu-id="ba3bb-124">See also</span></span>
- <xref:System.ServiceModel.Configuration.UseRequestHeadersForMetadataAddressElement>
