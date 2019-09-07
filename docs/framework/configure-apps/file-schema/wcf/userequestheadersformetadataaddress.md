---
title: <useRequestHeadersForMetadataAddress>
ms.date: 03/30/2017
ms.assetid: 679f0eae-f353-44d1-b42d-a9e247509774
ms.openlocfilehash: e0b46953924a3825420b719085e1210981da643a
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/06/2019
ms.locfileid: "70399207"
---
# <a name="userequestheadersformetadataaddress"></a><span data-ttu-id="c5f88-101">\<useRequestHeadersForMetadataAddress></span><span class="sxs-lookup"><span data-stu-id="c5f88-101">\<useRequestHeadersForMetadataAddress></span></span>
<span data-ttu-id="c5f88-102">允许从请求消息头中检索元数据地址信息。</span><span class="sxs-lookup"><span data-stu-id="c5f88-102">Enables the retrieval of metadata address information from the request message headers.</span></span>  
  
<span data-ttu-id="c5f88-103">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="c5f88-103">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="c5f88-104">&nbsp;&nbsp;[ **\<System.servicemodel >** ](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="c5f88-104">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="c5f88-105">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<行为 >** ](behaviors.md)</span><span class="sxs-lookup"><span data-stu-id="c5f88-105">&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)</span></span>\
<span data-ttu-id="c5f88-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<serviceBehaviors >** ](servicebehaviors.md)</span><span class="sxs-lookup"><span data-stu-id="c5f88-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceBehaviors>**](servicebehaviors.md)</span></span>\
<span data-ttu-id="c5f88-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<行为 >** ](behavior-of-servicebehaviors.md)</span><span class="sxs-lookup"><span data-stu-id="c5f88-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-servicebehaviors.md)</span></span>\
<span data-ttu-id="c5f88-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<useRequestHeadersForMetadataAddress >**</span><span class="sxs-lookup"><span data-stu-id="c5f88-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<useRequestHeadersForMetadataAddress>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c5f88-109">语法</span><span class="sxs-lookup"><span data-stu-id="c5f88-109">Syntax</span></span>  
  
```xml  
<useRequestHeadersForMetadataAddress>
  <defaultPorts>
    <add scheme="http"
         port="integer" />
  </defaultPorts>
</useRequestHeadersForMetadataAddress>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="c5f88-110">特性和元素</span><span class="sxs-lookup"><span data-stu-id="c5f88-110">Attributes and Elements</span></span>  
 <span data-ttu-id="c5f88-111">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="c5f88-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="c5f88-112">特性</span><span class="sxs-lookup"><span data-stu-id="c5f88-112">Attributes</span></span>  
 <span data-ttu-id="c5f88-113">无。</span><span class="sxs-lookup"><span data-stu-id="c5f88-113">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="c5f88-114">子元素</span><span class="sxs-lookup"><span data-stu-id="c5f88-114">Child Elements</span></span>  
  
|<span data-ttu-id="c5f88-115">元素</span><span class="sxs-lookup"><span data-stu-id="c5f88-115">Element</span></span>|<span data-ttu-id="c5f88-116">描述</span><span class="sxs-lookup"><span data-stu-id="c5f88-116">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="c5f88-117">\<defaultPorts></span><span class="sxs-lookup"><span data-stu-id="c5f88-117">\<defaultPorts></span></span>](defaultports.md)|<span data-ttu-id="c5f88-118">一个默认端口集合，列出客户端应用程序侦听的默认通信终结点。</span><span class="sxs-lookup"><span data-stu-id="c5f88-118">A collection of default ports listing the default communications endpoints that the client application listens to.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="c5f88-119">父元素</span><span class="sxs-lookup"><span data-stu-id="c5f88-119">Parent Elements</span></span>  
  
|<span data-ttu-id="c5f88-120">元素</span><span class="sxs-lookup"><span data-stu-id="c5f88-120">Element</span></span>|<span data-ttu-id="c5f88-121">描述</span><span class="sxs-lookup"><span data-stu-id="c5f88-121">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="c5f88-122">\<behavior></span><span class="sxs-lookup"><span data-stu-id="c5f88-122">\<behavior></span></span>](behavior-of-endpointbehaviors.md)|<span data-ttu-id="c5f88-123">指定行为元素。</span><span class="sxs-lookup"><span data-stu-id="c5f88-123">Specifies a behavior element.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="c5f88-124">请参阅</span><span class="sxs-lookup"><span data-stu-id="c5f88-124">See also</span></span>

- <xref:System.ServiceModel.Configuration.UseRequestHeadersForMetadataAddressElement>
