---
title: <webHttp>
ms.date: 03/30/2017
ms.assetid: 1f9d0754-d41e-44ce-a298-e51cb3096c64
ms.openlocfilehash: 00644d248e6fb85d7cf712620e6ac74405e6b0c3
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/06/2019
ms.locfileid: "70399168"
---
# <a name="webhttp"></a><span data-ttu-id="6ccb4-101">\<webHttp></span><span class="sxs-lookup"><span data-stu-id="6ccb4-101">\<webHttp></span></span>
<span data-ttu-id="6ccb4-102">此元素通过配置指定终结点上的 <xref:System.ServiceModel.Description.WebHttpBehavior>。</span><span class="sxs-lookup"><span data-stu-id="6ccb4-102">This element specifies the <xref:System.ServiceModel.Description.WebHttpBehavior> on an endpoint through configuration.</span></span> <span data-ttu-id="6ccb4-103">此行为与[ \<webHttpBinding >](webhttpbinding.md)标准绑定结合使用时，将为 Windows Communication Foundation （WCF）服务启用 Web 编程模型。</span><span class="sxs-lookup"><span data-stu-id="6ccb4-103">This behavior, when used in conjunction with the [\<webHttpBinding>](webhttpbinding.md) standard binding, enables the Web programming model for a Windows Communication Foundation (WCF) service.</span></span>  
  
<span data-ttu-id="6ccb4-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="6ccb4-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="6ccb4-105">&nbsp;&nbsp;[ **\<System.servicemodel >** ](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="6ccb4-105">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="6ccb4-106">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<行为 >** ](behaviors.md)</span><span class="sxs-lookup"><span data-stu-id="6ccb4-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)</span></span>\
<span data-ttu-id="6ccb4-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<endpointBehaviors >** ](endpointbehaviors.md)</span><span class="sxs-lookup"><span data-stu-id="6ccb4-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<endpointBehaviors>**](endpointbehaviors.md)</span></span>\
<span data-ttu-id="6ccb4-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<行为 >** ](behavior-of-endpointbehaviors.md)</span><span class="sxs-lookup"><span data-stu-id="6ccb4-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-endpointbehaviors.md)</span></span>\
<span data-ttu-id="6ccb4-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<Wcf-webhttp >**</span><span class="sxs-lookup"><span data-stu-id="6ccb4-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<webHttp>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6ccb4-110">语法</span><span class="sxs-lookup"><span data-stu-id="6ccb4-110">Syntax</span></span>  
  
```xml  
<webHttp />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="6ccb4-111">特性和元素</span><span class="sxs-lookup"><span data-stu-id="6ccb4-111">Attributes and Elements</span></span>  
 <span data-ttu-id="6ccb4-112">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="6ccb4-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="6ccb4-113">特性</span><span class="sxs-lookup"><span data-stu-id="6ccb4-113">Attributes</span></span>  
  
|<span data-ttu-id="6ccb4-114">特性</span><span class="sxs-lookup"><span data-stu-id="6ccb4-114">Attribute</span></span>|<span data-ttu-id="6ccb4-115">描述</span><span class="sxs-lookup"><span data-stu-id="6ccb4-115">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="6ccb4-116">automaticFormatSelectionEnabled</span><span class="sxs-lookup"><span data-stu-id="6ccb4-116">automaticFormatSelectionEnabled</span></span>|<span data-ttu-id="6ccb4-117">如果此属性设置为 `true`，WCF 基础结构将确定要使用的最佳格式。</span><span class="sxs-lookup"><span data-stu-id="6ccb4-117">When this property is set to `true`, the WCF infrastructure determines the best format to use.</span></span> <span data-ttu-id="6ccb4-118">默认情况下，禁用自动格式选择，以保证向后兼容性。</span><span class="sxs-lookup"><span data-stu-id="6ccb4-118">Automatic format selection is disabled by default for backwards compatibility.</span></span> <span data-ttu-id="6ccb4-119">可以通过编程方式或配置启用自动格式选择。</span><span class="sxs-lookup"><span data-stu-id="6ccb4-119">Automatic format selection can be enabled programmatically or through configuration.</span></span>|  
|<span data-ttu-id="6ccb4-120">defaultBodyStyle</span><span class="sxs-lookup"><span data-stu-id="6ccb4-120">defaultBodyStyle</span></span>|<span data-ttu-id="6ccb4-121">指定返回的消息的默认正文样式。</span><span class="sxs-lookup"><span data-stu-id="6ccb4-121">Specifies the default body style of returned messages.</span></span> <span data-ttu-id="6ccb4-122">有关详细信息，请<xref:System.ServiceModel.Web.WebMessageBodyStyle>参阅和[WCF Web HTTP 格式设置](../../../wcf/feature-details/wcf-web-http-formatting.md)。</span><span class="sxs-lookup"><span data-stu-id="6ccb4-122">For more information, see <xref:System.ServiceModel.Web.WebMessageBodyStyle> and [WCF Web HTTP Formatting](../../../wcf/feature-details/wcf-web-http-formatting.md).</span></span>|  
|<span data-ttu-id="6ccb4-123">defaultOutgoingResponseFormat</span><span class="sxs-lookup"><span data-stu-id="6ccb4-123">defaultOutgoingResponseFormat</span></span>|<span data-ttu-id="6ccb4-124">指定消息的默认传出响应格式。</span><span class="sxs-lookup"><span data-stu-id="6ccb4-124">Specifies the default outgoing response format for messages.</span></span> <span data-ttu-id="6ccb4-125">有关详细信息，请参阅[WCF WEB HTTP 格式设置](../../../wcf/feature-details/wcf-web-http-formatting.md)。</span><span class="sxs-lookup"><span data-stu-id="6ccb4-125">For more information, see [WCF Web HTTP Formatting](../../../wcf/feature-details/wcf-web-http-formatting.md).</span></span>|  
|<span data-ttu-id="6ccb4-126">faultExceptionEnabled</span><span class="sxs-lookup"><span data-stu-id="6ccb4-126">faultExceptionEnabled</span></span>|<span data-ttu-id="6ccb4-127">获取或设置用于指定在发生内部服务器错误（HTTP 状态代码：500）时是否生成 FaultException 的标志。</span><span class="sxs-lookup"><span data-stu-id="6ccb4-127">Gets or sets the flag that specifies whether a FaultException is generated when an internal server error (HTTP status code: 500) occurs.</span></span>|  
|<span data-ttu-id="6ccb4-128">helpEnabled</span><span class="sxs-lookup"><span data-stu-id="6ccb4-128">helpEnabled</span></span>|<span data-ttu-id="6ccb4-129">获取或设置一个值，该值确定是否启用了帮助页。</span><span class="sxs-lookup"><span data-stu-id="6ccb4-129">Gets or sets a value that determines if the Help page is enabled.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="6ccb4-130">子元素</span><span class="sxs-lookup"><span data-stu-id="6ccb4-130">Child Elements</span></span>  
 <span data-ttu-id="6ccb4-131">无。</span><span class="sxs-lookup"><span data-stu-id="6ccb4-131">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="6ccb4-132">父元素</span><span class="sxs-lookup"><span data-stu-id="6ccb4-132">Parent Elements</span></span>  
  
|<span data-ttu-id="6ccb4-133">元素</span><span class="sxs-lookup"><span data-stu-id="6ccb4-133">Element</span></span>|<span data-ttu-id="6ccb4-134">描述</span><span class="sxs-lookup"><span data-stu-id="6ccb4-134">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="6ccb4-135">\<behavior></span><span class="sxs-lookup"><span data-stu-id="6ccb4-135">\<behavior></span></span>](behavior-of-endpointbehaviors.md)|<span data-ttu-id="6ccb4-136">指定终结点行为集。</span><span class="sxs-lookup"><span data-stu-id="6ccb4-136">Specifies the set of endpoint behaviors.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="6ccb4-137">请参阅</span><span class="sxs-lookup"><span data-stu-id="6ccb4-137">See also</span></span>

- <xref:System.ServiceModel.Configuration.WebHttpElement>
- <xref:System.ServiceModel.Description.WebHttpBehavior>
- [<span data-ttu-id="6ccb4-138">AJAX 集成和 JSON 支持</span><span class="sxs-lookup"><span data-stu-id="6ccb4-138">AJAX Integration and JSON Support</span></span>](../../../wcf/feature-details/ajax-integration-and-json-support.md)
- [<span data-ttu-id="6ccb4-139">\<webHttpBinding></span><span class="sxs-lookup"><span data-stu-id="6ccb4-139">\<webHttpBinding></span></span>](webhttpbinding.md)
