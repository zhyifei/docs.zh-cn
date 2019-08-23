---
title: <webHttp>
ms.date: 03/30/2017
ms.assetid: 1f9d0754-d41e-44ce-a298-e51cb3096c64
ms.openlocfilehash: 366def5d0f4cc82b0ff0a5127701b0b5a6adb6a0
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2019
ms.locfileid: "69940493"
---
# <a name="webhttp"></a><span data-ttu-id="cc99e-101">\<webHttp></span><span class="sxs-lookup"><span data-stu-id="cc99e-101">\<webHttp></span></span>
<span data-ttu-id="cc99e-102">此元素通过配置指定终结点上的 <xref:System.ServiceModel.Description.WebHttpBehavior>。</span><span class="sxs-lookup"><span data-stu-id="cc99e-102">This element specifies the <xref:System.ServiceModel.Description.WebHttpBehavior> on an endpoint through configuration.</span></span> <span data-ttu-id="cc99e-103">此行为与[ \<webHttpBinding >](webhttpbinding.md)标准绑定结合使用时, 将为 Windows Communication Foundation (WCF) 服务启用 Web 编程模型。</span><span class="sxs-lookup"><span data-stu-id="cc99e-103">This behavior, when used in conjunction with the [\<webHttpBinding>](webhttpbinding.md) standard binding, enables the Web programming model for a Windows Communication Foundation (WCF) service.</span></span>  
  
 <span data-ttu-id="cc99e-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="cc99e-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="cc99e-105">\<行为 ></span><span class="sxs-lookup"><span data-stu-id="cc99e-105">\<behaviors></span></span>  
<span data-ttu-id="cc99e-106">\<endpointBehaviors></span><span class="sxs-lookup"><span data-stu-id="cc99e-106">\<endpointBehaviors></span></span>  
<span data-ttu-id="cc99e-107">\<行为 ></span><span class="sxs-lookup"><span data-stu-id="cc99e-107">\<behavior></span></span>  
<span data-ttu-id="cc99e-108">\<webHttp></span><span class="sxs-lookup"><span data-stu-id="cc99e-108">\<webHttp></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cc99e-109">语法</span><span class="sxs-lookup"><span data-stu-id="cc99e-109">Syntax</span></span>  
  
```xml  
<webHttp />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="cc99e-110">特性和元素</span><span class="sxs-lookup"><span data-stu-id="cc99e-110">Attributes and Elements</span></span>  
 <span data-ttu-id="cc99e-111">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="cc99e-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="cc99e-112">特性</span><span class="sxs-lookup"><span data-stu-id="cc99e-112">Attributes</span></span>  
  
|<span data-ttu-id="cc99e-113">特性</span><span class="sxs-lookup"><span data-stu-id="cc99e-113">Attribute</span></span>|<span data-ttu-id="cc99e-114">描述</span><span class="sxs-lookup"><span data-stu-id="cc99e-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="cc99e-115">automaticFormatSelectionEnabled</span><span class="sxs-lookup"><span data-stu-id="cc99e-115">automaticFormatSelectionEnabled</span></span>|<span data-ttu-id="cc99e-116">如果此属性设置为 `true`，WCF 基础结构将确定要使用的最佳格式。</span><span class="sxs-lookup"><span data-stu-id="cc99e-116">When this property is set to `true`, the WCF infrastructure determines the best format to use.</span></span> <span data-ttu-id="cc99e-117">默认情况下，禁用自动格式选择，以保证向后兼容性。</span><span class="sxs-lookup"><span data-stu-id="cc99e-117">Automatic format selection is disabled by default for backwards compatibility.</span></span> <span data-ttu-id="cc99e-118">可以通过编程方式或配置启用自动格式选择。</span><span class="sxs-lookup"><span data-stu-id="cc99e-118">Automatic format selection can be enabled programmatically or through configuration.</span></span>|  
|<span data-ttu-id="cc99e-119">defaultBodyStyle</span><span class="sxs-lookup"><span data-stu-id="cc99e-119">defaultBodyStyle</span></span>|<span data-ttu-id="cc99e-120">指定返回的消息的默认正文样式。</span><span class="sxs-lookup"><span data-stu-id="cc99e-120">Specifies the default body style of returned messages.</span></span> <span data-ttu-id="cc99e-121">有关详细信息, 请<xref:System.ServiceModel.Web.WebMessageBodyStyle>参阅和[WCF Web HTTP 格式设置](../../../wcf/feature-details/wcf-web-http-formatting.md)。</span><span class="sxs-lookup"><span data-stu-id="cc99e-121">For more information, see <xref:System.ServiceModel.Web.WebMessageBodyStyle> and [WCF Web HTTP Formatting](../../../wcf/feature-details/wcf-web-http-formatting.md).</span></span>|  
|<span data-ttu-id="cc99e-122">defaultOutgoingResponseFormat</span><span class="sxs-lookup"><span data-stu-id="cc99e-122">defaultOutgoingResponseFormat</span></span>|<span data-ttu-id="cc99e-123">指定消息的默认传出响应格式。</span><span class="sxs-lookup"><span data-stu-id="cc99e-123">Specifies the default outgoing response format for messages.</span></span> <span data-ttu-id="cc99e-124">有关详细信息, 请参阅[WCF WEB HTTP 格式设置](../../../wcf/feature-details/wcf-web-http-formatting.md)。</span><span class="sxs-lookup"><span data-stu-id="cc99e-124">For more information, see [WCF Web HTTP Formatting](../../../wcf/feature-details/wcf-web-http-formatting.md).</span></span>|  
|<span data-ttu-id="cc99e-125">faultExceptionEnabled</span><span class="sxs-lookup"><span data-stu-id="cc99e-125">faultExceptionEnabled</span></span>|<span data-ttu-id="cc99e-126">获取或设置用于指定在发生内部服务器错误（HTTP 状态代码：500）时是否生成 FaultException 的标志。</span><span class="sxs-lookup"><span data-stu-id="cc99e-126">Gets or sets the flag that specifies whether a FaultException is generated when an internal server error (HTTP status code: 500) occurs.</span></span>|  
|<span data-ttu-id="cc99e-127">helpEnabled</span><span class="sxs-lookup"><span data-stu-id="cc99e-127">helpEnabled</span></span>|<span data-ttu-id="cc99e-128">获取或设置一个值，该值确定是否启用了帮助页。</span><span class="sxs-lookup"><span data-stu-id="cc99e-128">Gets or sets a value that determines if the Help page is enabled.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="cc99e-129">子元素</span><span class="sxs-lookup"><span data-stu-id="cc99e-129">Child Elements</span></span>  
 <span data-ttu-id="cc99e-130">无。</span><span class="sxs-lookup"><span data-stu-id="cc99e-130">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="cc99e-131">父元素</span><span class="sxs-lookup"><span data-stu-id="cc99e-131">Parent Elements</span></span>  
  
|<span data-ttu-id="cc99e-132">元素</span><span class="sxs-lookup"><span data-stu-id="cc99e-132">Element</span></span>|<span data-ttu-id="cc99e-133">描述</span><span class="sxs-lookup"><span data-stu-id="cc99e-133">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="cc99e-134">\<behavior></span><span class="sxs-lookup"><span data-stu-id="cc99e-134">\<behavior></span></span>](behavior-of-endpointbehaviors.md)|<span data-ttu-id="cc99e-135">指定终结点行为集。</span><span class="sxs-lookup"><span data-stu-id="cc99e-135">Specifies the set of endpoint behaviors.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="cc99e-136">请参阅</span><span class="sxs-lookup"><span data-stu-id="cc99e-136">See also</span></span>

- <xref:System.ServiceModel.Configuration.WebHttpElement>
- <xref:System.ServiceModel.Description.WebHttpBehavior>
- [<span data-ttu-id="cc99e-137">AJAX 集成和 JSON 支持</span><span class="sxs-lookup"><span data-stu-id="cc99e-137">AJAX Integration and JSON Support</span></span>](../../../wcf/feature-details/ajax-integration-and-json-support.md)
- [<span data-ttu-id="cc99e-138">\<webHttpBinding></span><span class="sxs-lookup"><span data-stu-id="cc99e-138">\<webHttpBinding></span></span>](webhttpbinding.md)
