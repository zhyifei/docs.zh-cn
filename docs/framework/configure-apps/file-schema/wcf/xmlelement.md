---
title: '&lt;XmlElement&gt;'
ms.date: 03/30/2017
ms.assetid: 395205c2-d8c0-4a5e-90f3-7ce3c085fccd
ms.openlocfilehash: 70ff9b93bcd59331c5fa5e66bb51dc4cd1e043ff
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/03/2018
ms.locfileid: "32767643"
---
# <a name="ltxmlelementgt"></a><span data-ttu-id="9e5ba-102">&lt;XmlElement&gt;</span><span class="sxs-lookup"><span data-stu-id="9e5ba-102">&lt;xmlElement&gt;</span></span>
<span data-ttu-id="9e5ba-103">指定一个 XML 元素，请求令牌时，该元素在消息正文中发送到安全令牌服务。</span><span class="sxs-lookup"><span data-stu-id="9e5ba-103">Specifies an XML element that is sent in the message body to the Security Token Service when requesting a token.</span></span>  
  
 <span data-ttu-id="9e5ba-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="9e5ba-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="9e5ba-105">\<绑定 ></span><span class="sxs-lookup"><span data-stu-id="9e5ba-105">\<bindings></span></span>  
<span data-ttu-id="9e5ba-106">\<wsFederatedBinding></span><span class="sxs-lookup"><span data-stu-id="9e5ba-106">\<wsFederatedBinding></span></span>  
<span data-ttu-id="9e5ba-107">\<绑定 ></span><span class="sxs-lookup"><span data-stu-id="9e5ba-107">\<binding></span></span>  
<span data-ttu-id="9e5ba-108">\<安全 ></span><span class="sxs-lookup"><span data-stu-id="9e5ba-108">\<security></span></span>  
<span data-ttu-id="9e5ba-109">\<message></span><span class="sxs-lookup"><span data-stu-id="9e5ba-109">\<message></span></span>  
<span data-ttu-id="9e5ba-110">\<tokenRequestParameters ></span><span class="sxs-lookup"><span data-stu-id="9e5ba-110">\<tokenRequestParameters></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9e5ba-111">语法</span><span class="sxs-lookup"><span data-stu-id="9e5ba-111">Syntax</span></span>  
  
```xml  
<tokenRequestParameters>  
      <xmlElement xmlElement="String" />  
</tokenRequestParameters>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="9e5ba-112">特性和元素</span><span class="sxs-lookup"><span data-stu-id="9e5ba-112">Attributes and Elements</span></span>  
 <span data-ttu-id="9e5ba-113">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="9e5ba-113">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="9e5ba-114">特性</span><span class="sxs-lookup"><span data-stu-id="9e5ba-114">Attributes</span></span>  
  
|<span data-ttu-id="9e5ba-115">特性</span><span class="sxs-lookup"><span data-stu-id="9e5ba-115">Attribute</span></span>|<span data-ttu-id="9e5ba-116">描述</span><span class="sxs-lookup"><span data-stu-id="9e5ba-116">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="9e5ba-117">xmlElement</span><span class="sxs-lookup"><span data-stu-id="9e5ba-117">xmlElement</span></span>|<span data-ttu-id="9e5ba-118">指定 XML 元素的字符串，请求令牌时，该元素在消息正文中发送到安全令牌服务。</span><span class="sxs-lookup"><span data-stu-id="9e5ba-118">A string specifying an XML element that is sent in the message body to the Security Token Service when requesting a token.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="9e5ba-119">子元素</span><span class="sxs-lookup"><span data-stu-id="9e5ba-119">Child Elements</span></span>  
 <span data-ttu-id="9e5ba-120">无。</span><span class="sxs-lookup"><span data-stu-id="9e5ba-120">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="9e5ba-121">父元素</span><span class="sxs-lookup"><span data-stu-id="9e5ba-121">Parent Elements</span></span>  
  
|<span data-ttu-id="9e5ba-122">元素</span><span class="sxs-lookup"><span data-stu-id="9e5ba-122">Element</span></span>|<span data-ttu-id="9e5ba-123">描述</span><span class="sxs-lookup"><span data-stu-id="9e5ba-123">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="9e5ba-124">\<tokenRequestParameters></span><span class="sxs-lookup"><span data-stu-id="9e5ba-124">\<tokenRequestParameters></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/tokenrequestparameters.md)|<span data-ttu-id="9e5ba-125">令牌请求参数的集合。</span><span class="sxs-lookup"><span data-stu-id="9e5ba-125">A collection of token request parameters.</span></span> <span data-ttu-id="9e5ba-126">每个参数都是一个 XML 元素。</span><span class="sxs-lookup"><span data-stu-id="9e5ba-126">Each parameter is an XML element.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="9e5ba-127">请参阅</span><span class="sxs-lookup"><span data-stu-id="9e5ba-127">See Also</span></span>  
 <xref:System.ServiceModel.FederatedMessageSecurityOverHttp.TokenRequestParameters%2A>  
 <xref:System.ServiceModel.Configuration.FederatedMessageSecurityOverHttpElement.TokenRequestParameters%2A>  
 [<span data-ttu-id="9e5ba-128">服务标识和身份验证</span><span class="sxs-lookup"><span data-stu-id="9e5ba-128">Service Identity and Authentication</span></span>](../../../../../docs/framework/wcf/feature-details/service-identity-and-authentication.md)  
 [<span data-ttu-id="9e5ba-129">联合令牌与颁发的令牌</span><span class="sxs-lookup"><span data-stu-id="9e5ba-129">Federation and Issued Tokens</span></span>](../../../../../docs/framework/wcf/feature-details/federation-and-issued-tokens.md)  
 [<span data-ttu-id="9e5ba-130">使用自定义绑定的安全功能</span><span class="sxs-lookup"><span data-stu-id="9e5ba-130">Security Capabilities with Custom Bindings</span></span>](../../../../../docs/framework/wcf/feature-details/security-capabilities-with-custom-bindings.md)  
 [<span data-ttu-id="9e5ba-131">联合令牌与颁发的令牌</span><span class="sxs-lookup"><span data-stu-id="9e5ba-131">Federation and Issued Tokens</span></span>](../../../../../docs/framework/wcf/feature-details/federation-and-issued-tokens.md)  
 [<span data-ttu-id="9e5ba-132">绑定</span><span class="sxs-lookup"><span data-stu-id="9e5ba-132">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)
