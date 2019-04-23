---
title: <defaultPorts>
ms.date: 03/30/2017
ms.assetid: 725d4ee5-bd46-4f0e-9c20-30ba75d6eb2c
ms.openlocfilehash: 4d7fdfb1cccb14f03d11864f1939cb578c79880a
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/18/2019
ms.locfileid: "59130619"
---
# <a name="defaultports"></a><span data-ttu-id="f946f-101">\<defaultPorts></span><span class="sxs-lookup"><span data-stu-id="f946f-101">\<defaultPorts></span></span>
<span data-ttu-id="f946f-102">一个默认端口集合，列出客户端应用程序侦听的默认通信终结点。</span><span class="sxs-lookup"><span data-stu-id="f946f-102">A collection of default ports listing the default communications endpoints that the client application listens to.</span></span>  
  
<span data-ttu-id="f946f-103">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="f946f-103">\<system.ServiceModel></span></span>  
<span data-ttu-id="f946f-104">\<behaviors></span><span class="sxs-lookup"><span data-stu-id="f946f-104">\<behaviors></span></span>  
<span data-ttu-id="f946f-105">\<serviceBehaviors></span><span class="sxs-lookup"><span data-stu-id="f946f-105">\<serviceBehaviors></span></span>  
<span data-ttu-id="f946f-106">\<behavior></span><span class="sxs-lookup"><span data-stu-id="f946f-106">\<behavior></span></span>  
<span data-ttu-id="f946f-107">\<useRequestHeadersForMetadataAddress></span><span class="sxs-lookup"><span data-stu-id="f946f-107">\<useRequestHeadersForMetadataAddress></span></span>  
<span data-ttu-id="f946f-108">\<defaultPorts></span><span class="sxs-lookup"><span data-stu-id="f946f-108">\<defaultPorts></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f946f-109">语法</span><span class="sxs-lookup"><span data-stu-id="f946f-109">Syntax</span></span>  
  
```xml  
<useRequestHeadersForMetadataAddress>
  <defaultPorts>
    <add scheme="http"
         port="integer" />
  </defaultPorts>
</useRequestHeadersForMetadataAddress>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="f946f-110">特性和元素</span><span class="sxs-lookup"><span data-stu-id="f946f-110">Attributes and Elements</span></span>  
 <span data-ttu-id="f946f-111">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="f946f-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="f946f-112">特性</span><span class="sxs-lookup"><span data-stu-id="f946f-112">Attributes</span></span>  
 <span data-ttu-id="f946f-113">无。</span><span class="sxs-lookup"><span data-stu-id="f946f-113">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="f946f-114">子元素</span><span class="sxs-lookup"><span data-stu-id="f946f-114">Child Elements</span></span>  
  
|<span data-ttu-id="f946f-115">元素</span><span class="sxs-lookup"><span data-stu-id="f946f-115">Element</span></span>|<span data-ttu-id="f946f-116">描述</span><span class="sxs-lookup"><span data-stu-id="f946f-116">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="f946f-117">\<add> of \<defaultPorts></span><span class="sxs-lookup"><span data-stu-id="f946f-117">\<add> of \<defaultPorts></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/add-of-defaultports.md)|<span data-ttu-id="f946f-118">客户端应用程序侦听的默认通信终结点。</span><span class="sxs-lookup"><span data-stu-id="f946f-118">A default communications endpoint that the client application listens to.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="f946f-119">父元素</span><span class="sxs-lookup"><span data-stu-id="f946f-119">Parent Elements</span></span>  
  
|<span data-ttu-id="f946f-120">元素</span><span class="sxs-lookup"><span data-stu-id="f946f-120">Element</span></span>|<span data-ttu-id="f946f-121">描述</span><span class="sxs-lookup"><span data-stu-id="f946f-121">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="f946f-122">\<useRequestHeadersForMetadataAddress></span><span class="sxs-lookup"><span data-stu-id="f946f-122">\<useRequestHeadersForMetadataAddress></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/userequestheadersformetadataaddress.md)|<span data-ttu-id="f946f-123">默认端口列表。</span><span class="sxs-lookup"><span data-stu-id="f946f-123">A list of default ports.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="f946f-124">请参阅</span><span class="sxs-lookup"><span data-stu-id="f946f-124">See also</span></span>

- <xref:System.ServiceModel.Configuration.DefaultPortElementCollection>
