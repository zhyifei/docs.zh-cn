---
title: '&lt;webHttpEndpoint&gt;'
ms.date: 03/30/2017
ms.assetid: ecaaeb6f-ebd0-411d-8b53-92477cd45347
ms.openlocfilehash: 46691a36b62898583132b5668b06de5659926d66
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/03/2018
ms.locfileid: "32767084"
---
# <a name="ltwebhttpendpointgt"></a><span data-ttu-id="d76b4-102">&lt;webHttpEndpoint&gt;</span><span class="sxs-lookup"><span data-stu-id="d76b4-102">&lt;webHttpEndpoint&gt;</span></span>
<span data-ttu-id="d76b4-103">此配置元素定义具有固定的标准终结点[ \<webHttpBinding >](../../../../../docs/framework/configure-apps/file-schema/wcf/webhttpbinding.md)绑定，它自动添加[ \<webHttp >](../../../../../docs/framework/configure-apps/file-schema/wcf/webhttp.md)行为。</span><span class="sxs-lookup"><span data-stu-id="d76b4-103">This configuration element defines a standard endpoint with a fixed [\<webHttpBinding>](../../../../../docs/framework/configure-apps/file-schema/wcf/webhttpbinding.md) binding that automatically adds the [\<webHttp>](../../../../../docs/framework/configure-apps/file-schema/wcf/webhttp.md) behavior.</span></span> <span data-ttu-id="d76b4-104">在编写 REST 服务时，请使用此终结点。</span><span class="sxs-lookup"><span data-stu-id="d76b4-104">Use this endpoint when writing a REST service.</span></span>  
  
<span data-ttu-id="d76b4-105">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="d76b4-105">\<system.ServiceModel></span></span>  
<span data-ttu-id="d76b4-106">\<standardEndpoints ></span><span class="sxs-lookup"><span data-stu-id="d76b4-106">\<standardEndpoints></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d76b4-107">语法</span><span class="sxs-lookup"><span data-stu-id="d76b4-107">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="d76b4-108">特性和元素</span><span class="sxs-lookup"><span data-stu-id="d76b4-108">Attributes and Elements</span></span>  
 <span data-ttu-id="d76b4-109">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="d76b4-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="d76b4-110">特性</span><span class="sxs-lookup"><span data-stu-id="d76b4-110">Attributes</span></span>  
  
|<span data-ttu-id="d76b4-111">特性</span><span class="sxs-lookup"><span data-stu-id="d76b4-111">Attribute</span></span>|<span data-ttu-id="d76b4-112">描述</span><span class="sxs-lookup"><span data-stu-id="d76b4-112">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="d76b4-113">automaticFormatSelectionEnabled</span><span class="sxs-lookup"><span data-stu-id="d76b4-113">automaticFormatSelectionEnabled</span></span>|<span data-ttu-id="d76b4-114">一个布尔值，指示是否启用自动格式选择。</span><span class="sxs-lookup"><span data-stu-id="d76b4-114">A Boolean value that indicates whether automatic format selection is enabled.</span></span><br /><br /> <span data-ttu-id="d76b4-115">如果启用了自动格式选择，基础结构将分析请求消息的 `Accept` 标头，并确定最适合的响应格式。</span><span class="sxs-lookup"><span data-stu-id="d76b4-115">When automatic format selection is enabled, the infrastructure parses the `Accept` header of the request message and determines the most appropriate response format.</span></span> <span data-ttu-id="d76b4-116">如果 `Accept` 标头未指定适合的响应格式，则基础结构将使用请求消息的 `Content-Type`，或使用操作的默认响应格式。</span><span class="sxs-lookup"><span data-stu-id="d76b4-116">If the `Accept` header does not specify a suitable response format, the infrastructure uses the `Content-Type` of the request message or the default response format of the operation.</span></span>|  
|<span data-ttu-id="d76b4-117">defaultOutgoingResponseFormat</span><span class="sxs-lookup"><span data-stu-id="d76b4-117">defaultOutgoingResponseFormat</span></span>|<span data-ttu-id="d76b4-118">一个指定默认传出响应格式的特性。</span><span class="sxs-lookup"><span data-stu-id="d76b4-118">An attribute that specifies the default outgoing response format.</span></span> <span data-ttu-id="d76b4-119">此特性的类型为 <xref:System.ServiceModel.Web.WebMessageFormat></span><span class="sxs-lookup"><span data-stu-id="d76b4-119">This attribute is of the <xref:System.ServiceModel.Web.WebMessageFormat> type</span></span>|  
|<span data-ttu-id="d76b4-120">helpEnabled</span><span class="sxs-lookup"><span data-stu-id="d76b4-120">helpEnabled</span></span>|<span data-ttu-id="d76b4-121">一个布尔值，指示是否为终结点启用了 HTTP 帮助页。</span><span class="sxs-lookup"><span data-stu-id="d76b4-121">A Boolean value that indicates whether the HTTP help page is enabled for the endpoint.</span></span>|  
|<span data-ttu-id="d76b4-122">webEndpointType</span><span class="sxs-lookup"><span data-stu-id="d76b4-122">webEndpointType</span></span>|<span data-ttu-id="d76b4-123">一个字符串，指定终结点的类型。</span><span class="sxs-lookup"><span data-stu-id="d76b4-123">A string that specifies the type of the endpoint.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="d76b4-124">子元素</span><span class="sxs-lookup"><span data-stu-id="d76b4-124">Child Elements</span></span>  
 <span data-ttu-id="d76b4-125">无。</span><span class="sxs-lookup"><span data-stu-id="d76b4-125">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="d76b4-126">父元素</span><span class="sxs-lookup"><span data-stu-id="d76b4-126">Parent Elements</span></span>  
  
|<span data-ttu-id="d76b4-127">元素</span><span class="sxs-lookup"><span data-stu-id="d76b4-127">Element</span></span>|<span data-ttu-id="d76b4-128">描述</span><span class="sxs-lookup"><span data-stu-id="d76b4-128">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="d76b4-129">\<standardEndpoints ></span><span class="sxs-lookup"><span data-stu-id="d76b4-129">\<standardEndpoints></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/standardendpoints.md)|<span data-ttu-id="d76b4-130">具有一个或多个固定属性（地址、绑定和协定）的预定义终结点的标准终结点集合。</span><span class="sxs-lookup"><span data-stu-id="d76b4-130">A collection of standard endpoints that are pre-defined endpoints with one or more of their properties (address, binding, contract) fixed.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="d76b4-131">请参阅</span><span class="sxs-lookup"><span data-stu-id="d76b4-131">See Also</span></span>  
 <xref:System.ServiceModel.Description.WebHttpEndpoint>  
 <xref:System.ServiceModel.Configuration.WebHttpEndpointElement>
