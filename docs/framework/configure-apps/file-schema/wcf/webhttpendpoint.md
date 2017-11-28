---
title: '&lt;webHttpEndpoint&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: ecaaeb6f-ebd0-411d-8b53-92477cd45347
caps.latest.revision: "2"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 5c8d75c457c4f8ec427480afd0e4d3e7335ff981
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="ltwebhttpendpointgt"></a><span data-ttu-id="19921-102">&lt;webHttpEndpoint&gt;</span><span class="sxs-lookup"><span data-stu-id="19921-102">&lt;webHttpEndpoint&gt;</span></span>
<span data-ttu-id="19921-103">此配置元素定义具有固定的标准终结点[ \<webHttpBinding >](../../../../../docs/framework/configure-apps/file-schema/wcf/webhttpbinding.md)绑定，它自动添加[ \<webHttp >](../../../../../docs/framework/configure-apps/file-schema/wcf/webhttp.md)行为。</span><span class="sxs-lookup"><span data-stu-id="19921-103">This configuration element defines a standard endpoint with a fixed [\<webHttpBinding>](../../../../../docs/framework/configure-apps/file-schema/wcf/webhttpbinding.md) binding that automatically adds the [\<webHttp>](../../../../../docs/framework/configure-apps/file-schema/wcf/webhttp.md) behavior.</span></span> <span data-ttu-id="19921-104">在编写 REST 服务时，请使用此终结点。</span><span class="sxs-lookup"><span data-stu-id="19921-104">Use this endpoint when writing a REST service.</span></span>  
  
<span data-ttu-id="19921-105">\<系统。ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="19921-105">\<system.ServiceModel></span></span>  
<span data-ttu-id="19921-106">\<standardEndpoints ></span><span class="sxs-lookup"><span data-stu-id="19921-106">\<standardEndpoints></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="19921-107">语法</span><span class="sxs-lookup"><span data-stu-id="19921-107">Syntax</span></span>  
  
```xml  
<system.serviceModel>  
  <standardEndpoints>
    <webHttpEndpoint>
      <standardEndpoint automaticFormatSelectionEnabled="String" 
                        defaultOutgoingResponseFormat="Xml/Json" 
                        helpEnabled="Boolean" 
                        webEndpointType="String"/>
    </webHttpEndpoint>
  </standardEndpoints>  
</system.serviceModel>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="19921-108">特性和元素</span><span class="sxs-lookup"><span data-stu-id="19921-108">Attributes and Elements</span></span>  
 <span data-ttu-id="19921-109">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="19921-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="19921-110">特性</span><span class="sxs-lookup"><span data-stu-id="19921-110">Attributes</span></span>  
  
|<span data-ttu-id="19921-111">特性</span><span class="sxs-lookup"><span data-stu-id="19921-111">Attribute</span></span>|<span data-ttu-id="19921-112">描述</span><span class="sxs-lookup"><span data-stu-id="19921-112">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="19921-113">automaticFormatSelectionEnabled</span><span class="sxs-lookup"><span data-stu-id="19921-113">automaticFormatSelectionEnabled</span></span>|<span data-ttu-id="19921-114">一个布尔值，指示是否启用自动格式选择。</span><span class="sxs-lookup"><span data-stu-id="19921-114">A Boolean value that indicates whether automatic format selection is enabled.</span></span><br /><br /> <span data-ttu-id="19921-115">如果启用了自动格式选择，基础结构将分析请求消息的 `Accept` 标头，并确定最适合的响应格式。</span><span class="sxs-lookup"><span data-stu-id="19921-115">When automatic format selection is enabled, the infrastructure parses the `Accept` header of the request message and determines the most appropriate response format.</span></span> <span data-ttu-id="19921-116">如果 `Accept` 标头未指定适合的响应格式，则基础结构将使用请求消息的 `Content-Type`，或使用操作的默认响应格式。</span><span class="sxs-lookup"><span data-stu-id="19921-116">If the `Accept` header does not specify a suitable response format, the infrastructure uses the `Content-Type` of the request message or the default response format of the operation.</span></span>|  
|<span data-ttu-id="19921-117">defaultOutgoingResponseFormat</span><span class="sxs-lookup"><span data-stu-id="19921-117">defaultOutgoingResponseFormat</span></span>|<span data-ttu-id="19921-118">一个指定默认传出响应格式的特性。</span><span class="sxs-lookup"><span data-stu-id="19921-118">An attribute that specifies the default outgoing response format.</span></span> <span data-ttu-id="19921-119">此特性的类型为 <xref:System.ServiceModel.Web.WebMessageFormat></span><span class="sxs-lookup"><span data-stu-id="19921-119">This attribute is of the <xref:System.ServiceModel.Web.WebMessageFormat> type</span></span>|  
|<span data-ttu-id="19921-120">helpEnabled</span><span class="sxs-lookup"><span data-stu-id="19921-120">helpEnabled</span></span>|<span data-ttu-id="19921-121">一个布尔值，指示是否为终结点启用了 HTTP 帮助页。</span><span class="sxs-lookup"><span data-stu-id="19921-121">A Boolean value that indicates whether the HTTP help page is enabled for the endpoint.</span></span>|  
|<span data-ttu-id="19921-122">webEndpointType</span><span class="sxs-lookup"><span data-stu-id="19921-122">webEndpointType</span></span>|<span data-ttu-id="19921-123">一个字符串，指定终结点的类型。</span><span class="sxs-lookup"><span data-stu-id="19921-123">A string that specifies the type of the endpoint.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="19921-124">子元素</span><span class="sxs-lookup"><span data-stu-id="19921-124">Child Elements</span></span>  
 <span data-ttu-id="19921-125">无。</span><span class="sxs-lookup"><span data-stu-id="19921-125">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="19921-126">父元素</span><span class="sxs-lookup"><span data-stu-id="19921-126">Parent Elements</span></span>  
  
|<span data-ttu-id="19921-127">元素</span><span class="sxs-lookup"><span data-stu-id="19921-127">Element</span></span>|<span data-ttu-id="19921-128">描述</span><span class="sxs-lookup"><span data-stu-id="19921-128">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="19921-129">\<standardEndpoints ></span><span class="sxs-lookup"><span data-stu-id="19921-129">\<standardEndpoints></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/standardendpoints.md)|<span data-ttu-id="19921-130">具有一个或多个固定属性（地址、绑定和协定）的预定义终结点的标准终结点集合。</span><span class="sxs-lookup"><span data-stu-id="19921-130">A collection of standard endpoints that are pre-defined endpoints with one or more of their properties (address, binding, contract) fixed.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="19921-131">另请参阅</span><span class="sxs-lookup"><span data-stu-id="19921-131">See Also</span></span>  
 <xref:System.ServiceModel.Description.WebHttpEndpoint>  
 <xref:System.ServiceModel.Configuration.WebHttpEndpointElement>
