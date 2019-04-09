---
title: <useRequestHeadersForMetadataAddress>
ms.date: 03/30/2017
ms.assetid: 679f0eae-f353-44d1-b42d-a9e247509774
ms.openlocfilehash: 969461d0e5bdc9f8c49b7a019a6000af5af77eec
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/08/2019
ms.locfileid: "59121181"
---
# <a name="userequestheadersformetadataaddress"></a><span data-ttu-id="9773c-101">\<useRequestHeadersForMetadataAddress></span><span class="sxs-lookup"><span data-stu-id="9773c-101">\<useRequestHeadersForMetadataAddress></span></span>
<span data-ttu-id="9773c-102">允许从请求消息头中检索元数据地址信息。</span><span class="sxs-lookup"><span data-stu-id="9773c-102">Enables the retrieval of metadata address information from the request message headers.</span></span>  
  
<span data-ttu-id="9773c-103">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="9773c-103">\<system.ServiceModel></span></span>  
<span data-ttu-id="9773c-104">\<behaviors></span><span class="sxs-lookup"><span data-stu-id="9773c-104">\<behaviors></span></span>  
<span data-ttu-id="9773c-105">\<serviceBehaviors></span><span class="sxs-lookup"><span data-stu-id="9773c-105">\<serviceBehaviors></span></span>  
<span data-ttu-id="9773c-106">\<behavior></span><span class="sxs-lookup"><span data-stu-id="9773c-106">\<behavior></span></span>  
<span data-ttu-id="9773c-107">\<useRequestHeadersForMetadataAddress></span><span class="sxs-lookup"><span data-stu-id="9773c-107">\<useRequestHeadersForMetadataAddress></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9773c-108">语法</span><span class="sxs-lookup"><span data-stu-id="9773c-108">Syntax</span></span>  
  
```xml  
<useRequestHeadersForMetadataAddress>
  <defaultPorts>
    <add scheme="http"
         port="integer" />
  </defaultPorts>
</useRequestHeadersForMetadataAddress>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="9773c-109">特性和元素</span><span class="sxs-lookup"><span data-stu-id="9773c-109">Attributes and Elements</span></span>  
 <span data-ttu-id="9773c-110">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="9773c-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="9773c-111">特性</span><span class="sxs-lookup"><span data-stu-id="9773c-111">Attributes</span></span>  
 <span data-ttu-id="9773c-112">无。</span><span class="sxs-lookup"><span data-stu-id="9773c-112">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="9773c-113">子元素</span><span class="sxs-lookup"><span data-stu-id="9773c-113">Child Elements</span></span>  
  
|<span data-ttu-id="9773c-114">元素</span><span class="sxs-lookup"><span data-stu-id="9773c-114">Element</span></span>|<span data-ttu-id="9773c-115">描述</span><span class="sxs-lookup"><span data-stu-id="9773c-115">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="9773c-116">\<defaultPorts></span><span class="sxs-lookup"><span data-stu-id="9773c-116">\<defaultPorts></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/defaultports.md)|<span data-ttu-id="9773c-117">一个默认端口集合，列出客户端应用程序侦听的默认通信终结点。</span><span class="sxs-lookup"><span data-stu-id="9773c-117">A collection of default ports listing the default communications endpoints that the client application listens to.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="9773c-118">父元素</span><span class="sxs-lookup"><span data-stu-id="9773c-118">Parent Elements</span></span>  
  
|<span data-ttu-id="9773c-119">元素</span><span class="sxs-lookup"><span data-stu-id="9773c-119">Element</span></span>|<span data-ttu-id="9773c-120">描述</span><span class="sxs-lookup"><span data-stu-id="9773c-120">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="9773c-121">\<behavior></span><span class="sxs-lookup"><span data-stu-id="9773c-121">\<behavior></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md)|<span data-ttu-id="9773c-122">指定行为元素。</span><span class="sxs-lookup"><span data-stu-id="9773c-122">Specifies a behavior element.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="9773c-123">请参阅</span><span class="sxs-lookup"><span data-stu-id="9773c-123">See also</span></span>

- <xref:System.ServiceModel.Configuration.UseRequestHeadersForMetadataAddressElement>
