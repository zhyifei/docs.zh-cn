---
title: <useRequestHeadersForMetadataAddress>
ms.date: 03/30/2017
ms.assetid: 679f0eae-f353-44d1-b42d-a9e247509774
ms.openlocfilehash: 84310d4ae5e04e76e4484f4fc606c9896239c776
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2019
ms.locfileid: "69940555"
---
# <a name="userequestheadersformetadataaddress"></a><span data-ttu-id="24b31-101">\<useRequestHeadersForMetadataAddress></span><span class="sxs-lookup"><span data-stu-id="24b31-101">\<useRequestHeadersForMetadataAddress></span></span>
<span data-ttu-id="24b31-102">允许从请求消息头中检索元数据地址信息。</span><span class="sxs-lookup"><span data-stu-id="24b31-102">Enables the retrieval of metadata address information from the request message headers.</span></span>  
  
<span data-ttu-id="24b31-103">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="24b31-103">\<system.ServiceModel></span></span>  
<span data-ttu-id="24b31-104">\<行为 ></span><span class="sxs-lookup"><span data-stu-id="24b31-104">\<behaviors></span></span>  
<span data-ttu-id="24b31-105">\<serviceBehaviors></span><span class="sxs-lookup"><span data-stu-id="24b31-105">\<serviceBehaviors></span></span>  
<span data-ttu-id="24b31-106">\<行为 ></span><span class="sxs-lookup"><span data-stu-id="24b31-106">\<behavior></span></span>  
<span data-ttu-id="24b31-107">\<useRequestHeadersForMetadataAddress></span><span class="sxs-lookup"><span data-stu-id="24b31-107">\<useRequestHeadersForMetadataAddress></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="24b31-108">语法</span><span class="sxs-lookup"><span data-stu-id="24b31-108">Syntax</span></span>  
  
```xml  
<useRequestHeadersForMetadataAddress>
  <defaultPorts>
    <add scheme="http"
         port="integer" />
  </defaultPorts>
</useRequestHeadersForMetadataAddress>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="24b31-109">特性和元素</span><span class="sxs-lookup"><span data-stu-id="24b31-109">Attributes and Elements</span></span>  
 <span data-ttu-id="24b31-110">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="24b31-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="24b31-111">特性</span><span class="sxs-lookup"><span data-stu-id="24b31-111">Attributes</span></span>  
 <span data-ttu-id="24b31-112">无。</span><span class="sxs-lookup"><span data-stu-id="24b31-112">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="24b31-113">子元素</span><span class="sxs-lookup"><span data-stu-id="24b31-113">Child Elements</span></span>  
  
|<span data-ttu-id="24b31-114">元素</span><span class="sxs-lookup"><span data-stu-id="24b31-114">Element</span></span>|<span data-ttu-id="24b31-115">描述</span><span class="sxs-lookup"><span data-stu-id="24b31-115">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="24b31-116">\<defaultPorts></span><span class="sxs-lookup"><span data-stu-id="24b31-116">\<defaultPorts></span></span>](defaultports.md)|<span data-ttu-id="24b31-117">一个默认端口集合，列出客户端应用程序侦听的默认通信终结点。</span><span class="sxs-lookup"><span data-stu-id="24b31-117">A collection of default ports listing the default communications endpoints that the client application listens to.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="24b31-118">父元素</span><span class="sxs-lookup"><span data-stu-id="24b31-118">Parent Elements</span></span>  
  
|<span data-ttu-id="24b31-119">元素</span><span class="sxs-lookup"><span data-stu-id="24b31-119">Element</span></span>|<span data-ttu-id="24b31-120">描述</span><span class="sxs-lookup"><span data-stu-id="24b31-120">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="24b31-121">\<behavior></span><span class="sxs-lookup"><span data-stu-id="24b31-121">\<behavior></span></span>](behavior-of-endpointbehaviors.md)|<span data-ttu-id="24b31-122">指定行为元素。</span><span class="sxs-lookup"><span data-stu-id="24b31-122">Specifies a behavior element.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="24b31-123">请参阅</span><span class="sxs-lookup"><span data-stu-id="24b31-123">See also</span></span>

- <xref:System.ServiceModel.Configuration.UseRequestHeadersForMetadataAddressElement>
