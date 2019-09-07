---
title: <defaultPorts>
ms.date: 03/30/2017
ms.assetid: 725d4ee5-bd46-4f0e-9c20-30ba75d6eb2c
ms.openlocfilehash: 89ebad118c1c9210357d8fd281c9216b7f64b450
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/06/2019
ms.locfileid: "70398072"
---
# <a name="defaultports"></a><span data-ttu-id="1ad25-101">\<defaultPorts></span><span class="sxs-lookup"><span data-stu-id="1ad25-101">\<defaultPorts></span></span>
<span data-ttu-id="1ad25-102">一个默认端口集合，列出客户端应用程序侦听的默认通信终结点。</span><span class="sxs-lookup"><span data-stu-id="1ad25-102">A collection of default ports listing the default communications endpoints that the client application listens to.</span></span>  
  
<span data-ttu-id="1ad25-103">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="1ad25-103">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="1ad25-104">&nbsp;&nbsp;[ **\<System.servicemodel >** ](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="1ad25-104">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="1ad25-105">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<行为 >** ](behaviors.md)</span><span class="sxs-lookup"><span data-stu-id="1ad25-105">&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)</span></span>\
<span data-ttu-id="1ad25-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<serviceBehaviors >** ](servicebehaviors.md)</span><span class="sxs-lookup"><span data-stu-id="1ad25-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceBehaviors>**](servicebehaviors.md)</span></span>\
<span data-ttu-id="1ad25-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<行为 >** ](behavior-of-servicebehaviors.md)</span><span class="sxs-lookup"><span data-stu-id="1ad25-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-servicebehaviors.md)</span></span>\
<span data-ttu-id="1ad25-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<useRequestHeadersForMetadataAddress >** ](userequestheadersformetadataaddress.md)</span><span class="sxs-lookup"><span data-stu-id="1ad25-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<useRequestHeadersForMetadataAddress>**](userequestheadersformetadataaddress.md)</span></span>\
<span data-ttu-id="1ad25-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<defaultPorts >**</span><span class="sxs-lookup"><span data-stu-id="1ad25-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<defaultPorts>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1ad25-110">语法</span><span class="sxs-lookup"><span data-stu-id="1ad25-110">Syntax</span></span>  
  
```xml  
<useRequestHeadersForMetadataAddress>
  <defaultPorts>
    <add scheme="http"
         port="integer" />
  </defaultPorts>
</useRequestHeadersForMetadataAddress>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="1ad25-111">特性和元素</span><span class="sxs-lookup"><span data-stu-id="1ad25-111">Attributes and Elements</span></span>  
 <span data-ttu-id="1ad25-112">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="1ad25-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="1ad25-113">特性</span><span class="sxs-lookup"><span data-stu-id="1ad25-113">Attributes</span></span>  
 <span data-ttu-id="1ad25-114">无。</span><span class="sxs-lookup"><span data-stu-id="1ad25-114">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="1ad25-115">子元素</span><span class="sxs-lookup"><span data-stu-id="1ad25-115">Child Elements</span></span>  
  
|<span data-ttu-id="1ad25-116">元素</span><span class="sxs-lookup"><span data-stu-id="1ad25-116">Element</span></span>|<span data-ttu-id="1ad25-117">描述</span><span class="sxs-lookup"><span data-stu-id="1ad25-117">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="1ad25-118">\<添加 defaultPorts > \<的 ></span><span class="sxs-lookup"><span data-stu-id="1ad25-118">\<add> of \<defaultPorts></span></span>](add-of-defaultports.md)|<span data-ttu-id="1ad25-119">客户端应用程序侦听的默认通信终结点。</span><span class="sxs-lookup"><span data-stu-id="1ad25-119">A default communications endpoint that the client application listens to.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="1ad25-120">父元素</span><span class="sxs-lookup"><span data-stu-id="1ad25-120">Parent Elements</span></span>  
  
|<span data-ttu-id="1ad25-121">元素</span><span class="sxs-lookup"><span data-stu-id="1ad25-121">Element</span></span>|<span data-ttu-id="1ad25-122">描述</span><span class="sxs-lookup"><span data-stu-id="1ad25-122">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="1ad25-123">\<useRequestHeadersForMetadataAddress></span><span class="sxs-lookup"><span data-stu-id="1ad25-123">\<useRequestHeadersForMetadataAddress></span></span>](userequestheadersformetadataaddress.md)|<span data-ttu-id="1ad25-124">默认端口列表。</span><span class="sxs-lookup"><span data-stu-id="1ad25-124">A list of default ports.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="1ad25-125">请参阅</span><span class="sxs-lookup"><span data-stu-id="1ad25-125">See also</span></span>

- <xref:System.ServiceModel.Configuration.DefaultPortElementCollection>
