---
title: '&lt;webHttp&gt;'
ms.date: 03/30/2017
ms.assetid: 1f9d0754-d41e-44ce-a298-e51cb3096c64
ms.openlocfilehash: b52259af5e05de5bf5dd42a2cd0bf4b01f3e46f9
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54597549"
---
# <a name="ltwebhttpgt"></a><span data-ttu-id="40096-102">&lt;webHttp&gt;</span><span class="sxs-lookup"><span data-stu-id="40096-102">&lt;webHttp&gt;</span></span>
<span data-ttu-id="40096-103">此元素通过配置指定终结点上的 <xref:System.ServiceModel.Description.WebHttpBehavior>。</span><span class="sxs-lookup"><span data-stu-id="40096-103">This element specifies the <xref:System.ServiceModel.Description.WebHttpBehavior> on an endpoint through configuration.</span></span> <span data-ttu-id="40096-104">此行为与结合使用时[ \<webHttpBinding >](../../../../../docs/framework/configure-apps/file-schema/wcf/webhttpbinding.md)标准绑定，使 Windows Communication Foundation (WCF) 服务的 Web 编程模型。</span><span class="sxs-lookup"><span data-stu-id="40096-104">This behavior, when used in conjunction with the [\<webHttpBinding>](../../../../../docs/framework/configure-apps/file-schema/wcf/webhttpbinding.md) standard binding, enables the Web programming model for a Windows Communication Foundation (WCF) service.</span></span>  
  
 <span data-ttu-id="40096-105">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="40096-105">\<system.ServiceModel></span></span>  
<span data-ttu-id="40096-106">\<behaviors></span><span class="sxs-lookup"><span data-stu-id="40096-106">\<behaviors></span></span>  
<span data-ttu-id="40096-107">\<endpointBehaviors></span><span class="sxs-lookup"><span data-stu-id="40096-107">\<endpointBehaviors></span></span>  
<span data-ttu-id="40096-108">\<behavior></span><span class="sxs-lookup"><span data-stu-id="40096-108">\<behavior></span></span>  
<span data-ttu-id="40096-109">\<webHttp></span><span class="sxs-lookup"><span data-stu-id="40096-109">\<webHttp></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="40096-110">语法</span><span class="sxs-lookup"><span data-stu-id="40096-110">Syntax</span></span>  
  
```xml  
<webHttp />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="40096-111">特性和元素</span><span class="sxs-lookup"><span data-stu-id="40096-111">Attributes and Elements</span></span>  
 <span data-ttu-id="40096-112">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="40096-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="40096-113">特性</span><span class="sxs-lookup"><span data-stu-id="40096-113">Attributes</span></span>  
  
|<span data-ttu-id="40096-114">特性</span><span class="sxs-lookup"><span data-stu-id="40096-114">Attribute</span></span>|<span data-ttu-id="40096-115">描述</span><span class="sxs-lookup"><span data-stu-id="40096-115">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="40096-116">automaticFormatSelectionEnabled</span><span class="sxs-lookup"><span data-stu-id="40096-116">automaticFormatSelectionEnabled</span></span>|<span data-ttu-id="40096-117">如果此属性设置为 `true`，WCF 基础结构将确定要使用的最佳格式。</span><span class="sxs-lookup"><span data-stu-id="40096-117">When this property is set to `true`, the WCF infrastructure determines the best format to use.</span></span> <span data-ttu-id="40096-118">默认情况下，禁用自动格式选择，以保证向后兼容性。</span><span class="sxs-lookup"><span data-stu-id="40096-118">Automatic format selection is disabled by default for backwards compatibility.</span></span> <span data-ttu-id="40096-119">可以通过编程方式或配置启用自动格式选择。</span><span class="sxs-lookup"><span data-stu-id="40096-119">Automatic format selection can be enabled programmatically or through configuration.</span></span>|  
|<span data-ttu-id="40096-120">defaultBodyStyle</span><span class="sxs-lookup"><span data-stu-id="40096-120">defaultBodyStyle</span></span>|<span data-ttu-id="40096-121">指定返回的消息的默认正文样式。</span><span class="sxs-lookup"><span data-stu-id="40096-121">Specifies the default body style of returned messages.</span></span> <span data-ttu-id="40096-122">有关详细信息，请参阅<xref:System.ServiceModel.Web.WebMessageBodyStyle>并[WCF Web HTTP 格式设置](../../../../../docs/framework/wcf/feature-details/wcf-web-http-formatting.md)。</span><span class="sxs-lookup"><span data-stu-id="40096-122">For more information, see <xref:System.ServiceModel.Web.WebMessageBodyStyle> and [WCF Web HTTP Formatting](../../../../../docs/framework/wcf/feature-details/wcf-web-http-formatting.md).</span></span>|  
|<span data-ttu-id="40096-123">defaultOutgoingResponseFormat</span><span class="sxs-lookup"><span data-stu-id="40096-123">defaultOutgoingResponseFormat</span></span>|<span data-ttu-id="40096-124">指定消息的默认传出响应格式。</span><span class="sxs-lookup"><span data-stu-id="40096-124">Specifies the default outgoing response format for messages.</span></span> <span data-ttu-id="40096-125">有关详细信息，请参阅[WCF Web HTTP 格式设置](../../../../../docs/framework/wcf/feature-details/wcf-web-http-formatting.md)。</span><span class="sxs-lookup"><span data-stu-id="40096-125">For more information, see [WCF Web HTTP Formatting](../../../../../docs/framework/wcf/feature-details/wcf-web-http-formatting.md).</span></span>|  
|<span data-ttu-id="40096-126">faultExceptionEnabled</span><span class="sxs-lookup"><span data-stu-id="40096-126">faultExceptionEnabled</span></span>|<span data-ttu-id="40096-127">获取或设置用于指定在发生内部服务器错误（HTTP 状态代码：500）时是否生成 FaultException 的标志。</span><span class="sxs-lookup"><span data-stu-id="40096-127">Gets or sets the flag that specifies whether a FaultException is generated when an internal server error (HTTP status code: 500) occurs.</span></span>|  
|<span data-ttu-id="40096-128">helpEnabled</span><span class="sxs-lookup"><span data-stu-id="40096-128">helpEnabled</span></span>|<span data-ttu-id="40096-129">获取或设置一个值，该值确定是否启用了帮助页。</span><span class="sxs-lookup"><span data-stu-id="40096-129">Gets or sets a value that determines if the Help page is enabled.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="40096-130">子元素</span><span class="sxs-lookup"><span data-stu-id="40096-130">Child Elements</span></span>  
 <span data-ttu-id="40096-131">无。</span><span class="sxs-lookup"><span data-stu-id="40096-131">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="40096-132">父元素</span><span class="sxs-lookup"><span data-stu-id="40096-132">Parent Elements</span></span>  
  
|<span data-ttu-id="40096-133">元素</span><span class="sxs-lookup"><span data-stu-id="40096-133">Element</span></span>|<span data-ttu-id="40096-134">描述</span><span class="sxs-lookup"><span data-stu-id="40096-134">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="40096-135">\<behavior></span><span class="sxs-lookup"><span data-stu-id="40096-135">\<behavior></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md)|<span data-ttu-id="40096-136">指定终结点行为集。</span><span class="sxs-lookup"><span data-stu-id="40096-136">Specifies the set of endpoint behaviors.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="40096-137">请参阅</span><span class="sxs-lookup"><span data-stu-id="40096-137">See also</span></span>
- <xref:System.ServiceModel.Configuration.WebHttpElement>
- <xref:System.ServiceModel.Description.WebHttpBehavior>
- [<span data-ttu-id="40096-138">AJAX 集成和 JSON 支持</span><span class="sxs-lookup"><span data-stu-id="40096-138">AJAX Integration and JSON Support</span></span>](../../../../../docs/framework/wcf/feature-details/ajax-integration-and-json-support.md)
- [<span data-ttu-id="40096-139">\<webHttpBinding></span><span class="sxs-lookup"><span data-stu-id="40096-139">\<webHttpBinding></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/webhttpbinding.md)
