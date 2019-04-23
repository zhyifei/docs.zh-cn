---
title: <webHttp>
ms.date: 03/30/2017
ms.assetid: 1f9d0754-d41e-44ce-a298-e51cb3096c64
ms.openlocfilehash: 795e61b9054d2ea9276970988018c50099bcbe17
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/18/2019
ms.locfileid: "59129644"
---
# <a name="webhttp"></a><span data-ttu-id="756e7-101">\<webHttp></span><span class="sxs-lookup"><span data-stu-id="756e7-101">\<webHttp></span></span>
<span data-ttu-id="756e7-102">此元素通过配置指定终结点上的 <xref:System.ServiceModel.Description.WebHttpBehavior>。</span><span class="sxs-lookup"><span data-stu-id="756e7-102">This element specifies the <xref:System.ServiceModel.Description.WebHttpBehavior> on an endpoint through configuration.</span></span> <span data-ttu-id="756e7-103">此行为与结合使用时[ \<webHttpBinding >](../../../../../docs/framework/configure-apps/file-schema/wcf/webhttpbinding.md)标准绑定，使 Windows Communication Foundation (WCF) 服务的 Web 编程模型。</span><span class="sxs-lookup"><span data-stu-id="756e7-103">This behavior, when used in conjunction with the [\<webHttpBinding>](../../../../../docs/framework/configure-apps/file-schema/wcf/webhttpbinding.md) standard binding, enables the Web programming model for a Windows Communication Foundation (WCF) service.</span></span>  
  
 <span data-ttu-id="756e7-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="756e7-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="756e7-105">\<behaviors></span><span class="sxs-lookup"><span data-stu-id="756e7-105">\<behaviors></span></span>  
<span data-ttu-id="756e7-106">\<endpointBehaviors></span><span class="sxs-lookup"><span data-stu-id="756e7-106">\<endpointBehaviors></span></span>  
<span data-ttu-id="756e7-107">\<behavior></span><span class="sxs-lookup"><span data-stu-id="756e7-107">\<behavior></span></span>  
<span data-ttu-id="756e7-108">\<webHttp></span><span class="sxs-lookup"><span data-stu-id="756e7-108">\<webHttp></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="756e7-109">语法</span><span class="sxs-lookup"><span data-stu-id="756e7-109">Syntax</span></span>  
  
```xml  
<webHttp />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="756e7-110">特性和元素</span><span class="sxs-lookup"><span data-stu-id="756e7-110">Attributes and Elements</span></span>  
 <span data-ttu-id="756e7-111">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="756e7-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="756e7-112">特性</span><span class="sxs-lookup"><span data-stu-id="756e7-112">Attributes</span></span>  
  
|<span data-ttu-id="756e7-113">特性</span><span class="sxs-lookup"><span data-stu-id="756e7-113">Attribute</span></span>|<span data-ttu-id="756e7-114">描述</span><span class="sxs-lookup"><span data-stu-id="756e7-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="756e7-115">automaticFormatSelectionEnabled</span><span class="sxs-lookup"><span data-stu-id="756e7-115">automaticFormatSelectionEnabled</span></span>|<span data-ttu-id="756e7-116">如果此属性设置为 `true`，WCF 基础结构将确定要使用的最佳格式。</span><span class="sxs-lookup"><span data-stu-id="756e7-116">When this property is set to `true`, the WCF infrastructure determines the best format to use.</span></span> <span data-ttu-id="756e7-117">默认情况下，禁用自动格式选择，以保证向后兼容性。</span><span class="sxs-lookup"><span data-stu-id="756e7-117">Automatic format selection is disabled by default for backwards compatibility.</span></span> <span data-ttu-id="756e7-118">可以通过编程方式或配置启用自动格式选择。</span><span class="sxs-lookup"><span data-stu-id="756e7-118">Automatic format selection can be enabled programmatically or through configuration.</span></span>|  
|<span data-ttu-id="756e7-119">defaultBodyStyle</span><span class="sxs-lookup"><span data-stu-id="756e7-119">defaultBodyStyle</span></span>|<span data-ttu-id="756e7-120">指定返回的消息的默认正文样式。</span><span class="sxs-lookup"><span data-stu-id="756e7-120">Specifies the default body style of returned messages.</span></span> <span data-ttu-id="756e7-121">有关详细信息，请参阅<xref:System.ServiceModel.Web.WebMessageBodyStyle>并[WCF Web HTTP 格式设置](../../../../../docs/framework/wcf/feature-details/wcf-web-http-formatting.md)。</span><span class="sxs-lookup"><span data-stu-id="756e7-121">For more information, see <xref:System.ServiceModel.Web.WebMessageBodyStyle> and [WCF Web HTTP Formatting](../../../../../docs/framework/wcf/feature-details/wcf-web-http-formatting.md).</span></span>|  
|<span data-ttu-id="756e7-122">defaultOutgoingResponseFormat</span><span class="sxs-lookup"><span data-stu-id="756e7-122">defaultOutgoingResponseFormat</span></span>|<span data-ttu-id="756e7-123">指定消息的默认传出响应格式。</span><span class="sxs-lookup"><span data-stu-id="756e7-123">Specifies the default outgoing response format for messages.</span></span> <span data-ttu-id="756e7-124">有关详细信息，请参阅[WCF Web HTTP 格式设置](../../../../../docs/framework/wcf/feature-details/wcf-web-http-formatting.md)。</span><span class="sxs-lookup"><span data-stu-id="756e7-124">For more information, see [WCF Web HTTP Formatting](../../../../../docs/framework/wcf/feature-details/wcf-web-http-formatting.md).</span></span>|  
|<span data-ttu-id="756e7-125">faultExceptionEnabled</span><span class="sxs-lookup"><span data-stu-id="756e7-125">faultExceptionEnabled</span></span>|<span data-ttu-id="756e7-126">获取或设置用于指定在发生内部服务器错误（HTTP 状态代码：500）时是否生成 FaultException 的标志。</span><span class="sxs-lookup"><span data-stu-id="756e7-126">Gets or sets the flag that specifies whether a FaultException is generated when an internal server error (HTTP status code: 500) occurs.</span></span>|  
|<span data-ttu-id="756e7-127">helpEnabled</span><span class="sxs-lookup"><span data-stu-id="756e7-127">helpEnabled</span></span>|<span data-ttu-id="756e7-128">获取或设置一个值，该值确定是否启用了帮助页。</span><span class="sxs-lookup"><span data-stu-id="756e7-128">Gets or sets a value that determines if the Help page is enabled.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="756e7-129">子元素</span><span class="sxs-lookup"><span data-stu-id="756e7-129">Child Elements</span></span>  
 <span data-ttu-id="756e7-130">无。</span><span class="sxs-lookup"><span data-stu-id="756e7-130">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="756e7-131">父元素</span><span class="sxs-lookup"><span data-stu-id="756e7-131">Parent Elements</span></span>  
  
|<span data-ttu-id="756e7-132">元素</span><span class="sxs-lookup"><span data-stu-id="756e7-132">Element</span></span>|<span data-ttu-id="756e7-133">描述</span><span class="sxs-lookup"><span data-stu-id="756e7-133">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="756e7-134">\<behavior></span><span class="sxs-lookup"><span data-stu-id="756e7-134">\<behavior></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md)|<span data-ttu-id="756e7-135">指定终结点行为集。</span><span class="sxs-lookup"><span data-stu-id="756e7-135">Specifies the set of endpoint behaviors.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="756e7-136">请参阅</span><span class="sxs-lookup"><span data-stu-id="756e7-136">See also</span></span>

- <xref:System.ServiceModel.Configuration.WebHttpElement>
- <xref:System.ServiceModel.Description.WebHttpBehavior>
- [<span data-ttu-id="756e7-137">AJAX 集成和 JSON 支持</span><span class="sxs-lookup"><span data-stu-id="756e7-137">AJAX Integration and JSON Support</span></span>](../../../../../docs/framework/wcf/feature-details/ajax-integration-and-json-support.md)
- [<span data-ttu-id="756e7-138">\<webHttpBinding></span><span class="sxs-lookup"><span data-stu-id="756e7-138">\<webHttpBinding></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/webhttpbinding.md)
