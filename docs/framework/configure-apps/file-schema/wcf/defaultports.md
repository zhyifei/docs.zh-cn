---
title: <defaultPorts>
ms.date: 03/30/2017
ms.assetid: 725d4ee5-bd46-4f0e-9c20-30ba75d6eb2c
ms.openlocfilehash: 462a06e5a773310b6364838ae2ebc14da0a2ee1b
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2019
ms.locfileid: "69925890"
---
# <a name="defaultports"></a><span data-ttu-id="c1130-101">\<defaultPorts></span><span class="sxs-lookup"><span data-stu-id="c1130-101">\<defaultPorts></span></span>
<span data-ttu-id="c1130-102">一个默认端口集合，列出客户端应用程序侦听的默认通信终结点。</span><span class="sxs-lookup"><span data-stu-id="c1130-102">A collection of default ports listing the default communications endpoints that the client application listens to.</span></span>  
  
<span data-ttu-id="c1130-103">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="c1130-103">\<system.ServiceModel></span></span>  
<span data-ttu-id="c1130-104">\<行为 ></span><span class="sxs-lookup"><span data-stu-id="c1130-104">\<behaviors></span></span>  
<span data-ttu-id="c1130-105">\<serviceBehaviors></span><span class="sxs-lookup"><span data-stu-id="c1130-105">\<serviceBehaviors></span></span>  
<span data-ttu-id="c1130-106">\<行为 ></span><span class="sxs-lookup"><span data-stu-id="c1130-106">\<behavior></span></span>  
<span data-ttu-id="c1130-107">\<useRequestHeadersForMetadataAddress></span><span class="sxs-lookup"><span data-stu-id="c1130-107">\<useRequestHeadersForMetadataAddress></span></span>  
<span data-ttu-id="c1130-108">\<defaultPorts></span><span class="sxs-lookup"><span data-stu-id="c1130-108">\<defaultPorts></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c1130-109">语法</span><span class="sxs-lookup"><span data-stu-id="c1130-109">Syntax</span></span>  
  
```xml  
<useRequestHeadersForMetadataAddress>
  <defaultPorts>
    <add scheme="http"
         port="integer" />
  </defaultPorts>
</useRequestHeadersForMetadataAddress>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="c1130-110">特性和元素</span><span class="sxs-lookup"><span data-stu-id="c1130-110">Attributes and Elements</span></span>  
 <span data-ttu-id="c1130-111">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="c1130-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="c1130-112">特性</span><span class="sxs-lookup"><span data-stu-id="c1130-112">Attributes</span></span>  
 <span data-ttu-id="c1130-113">无。</span><span class="sxs-lookup"><span data-stu-id="c1130-113">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="c1130-114">子元素</span><span class="sxs-lookup"><span data-stu-id="c1130-114">Child Elements</span></span>  
  
|<span data-ttu-id="c1130-115">元素</span><span class="sxs-lookup"><span data-stu-id="c1130-115">Element</span></span>|<span data-ttu-id="c1130-116">描述</span><span class="sxs-lookup"><span data-stu-id="c1130-116">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="c1130-117">\<添加 defaultPorts > \<的 ></span><span class="sxs-lookup"><span data-stu-id="c1130-117">\<add> of \<defaultPorts></span></span>](add-of-defaultports.md)|<span data-ttu-id="c1130-118">客户端应用程序侦听的默认通信终结点。</span><span class="sxs-lookup"><span data-stu-id="c1130-118">A default communications endpoint that the client application listens to.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="c1130-119">父元素</span><span class="sxs-lookup"><span data-stu-id="c1130-119">Parent Elements</span></span>  
  
|<span data-ttu-id="c1130-120">元素</span><span class="sxs-lookup"><span data-stu-id="c1130-120">Element</span></span>|<span data-ttu-id="c1130-121">描述</span><span class="sxs-lookup"><span data-stu-id="c1130-121">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="c1130-122">\<useRequestHeadersForMetadataAddress></span><span class="sxs-lookup"><span data-stu-id="c1130-122">\<useRequestHeadersForMetadataAddress></span></span>](userequestheadersformetadataaddress.md)|<span data-ttu-id="c1130-123">默认端口列表。</span><span class="sxs-lookup"><span data-stu-id="c1130-123">A list of default ports.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="c1130-124">请参阅</span><span class="sxs-lookup"><span data-stu-id="c1130-124">See also</span></span>

- <xref:System.ServiceModel.Configuration.DefaultPortElementCollection>
