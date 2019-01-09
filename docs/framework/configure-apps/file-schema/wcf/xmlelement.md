---
title: '&lt;XmlElement&gt;'
ms.date: 03/30/2017
ms.assetid: 395205c2-d8c0-4a5e-90f3-7ce3c085fccd
ms.openlocfilehash: 6a197f7aa29645a08a581bcee103eb94c0e20179
ms.sourcegitcommit: 4ac80713f6faa220e5a119d5165308a58f7ccdc8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/09/2019
ms.locfileid: "54147013"
---
# <a name="ltxmlelementgt"></a><span data-ttu-id="63537-102">&lt;XmlElement&gt;</span><span class="sxs-lookup"><span data-stu-id="63537-102">&lt;xmlElement&gt;</span></span>
<span data-ttu-id="63537-103">指定一个 XML 元素，请求令牌时，该元素在消息正文中发送到安全令牌服务。</span><span class="sxs-lookup"><span data-stu-id="63537-103">Specifies an XML element that is sent in the message body to the Security Token Service when requesting a token.</span></span>  
  
 <span data-ttu-id="63537-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="63537-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="63537-105">\<绑定 ></span><span class="sxs-lookup"><span data-stu-id="63537-105">\<bindings></span></span>  
<span data-ttu-id="63537-106">\<wsFederatedBinding></span><span class="sxs-lookup"><span data-stu-id="63537-106">\<wsFederatedBinding></span></span>  
<span data-ttu-id="63537-107">\<绑定 ></span><span class="sxs-lookup"><span data-stu-id="63537-107">\<binding></span></span>  
<span data-ttu-id="63537-108">\<安全 ></span><span class="sxs-lookup"><span data-stu-id="63537-108">\<security></span></span>  
<span data-ttu-id="63537-109">\<message></span><span class="sxs-lookup"><span data-stu-id="63537-109">\<message></span></span>  
<span data-ttu-id="63537-110">\<tokenRequestParameters ></span><span class="sxs-lookup"><span data-stu-id="63537-110">\<tokenRequestParameters></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="63537-111">语法</span><span class="sxs-lookup"><span data-stu-id="63537-111">Syntax</span></span>  
  
```xml  
<tokenRequestParameters>
  <xmlElement xmlElement="String" />
</tokenRequestParameters>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="63537-112">特性和元素</span><span class="sxs-lookup"><span data-stu-id="63537-112">Attributes and Elements</span></span>  
 <span data-ttu-id="63537-113">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="63537-113">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="63537-114">特性</span><span class="sxs-lookup"><span data-stu-id="63537-114">Attributes</span></span>  
  
|<span data-ttu-id="63537-115">特性</span><span class="sxs-lookup"><span data-stu-id="63537-115">Attribute</span></span>|<span data-ttu-id="63537-116">描述</span><span class="sxs-lookup"><span data-stu-id="63537-116">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="63537-117">xmlElement</span><span class="sxs-lookup"><span data-stu-id="63537-117">xmlElement</span></span>|<span data-ttu-id="63537-118">指定 XML 元素的字符串，请求令牌时，该元素在消息正文中发送到安全令牌服务。</span><span class="sxs-lookup"><span data-stu-id="63537-118">A string specifying an XML element that is sent in the message body to the Security Token Service when requesting a token.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="63537-119">子元素</span><span class="sxs-lookup"><span data-stu-id="63537-119">Child Elements</span></span>  
 <span data-ttu-id="63537-120">无。</span><span class="sxs-lookup"><span data-stu-id="63537-120">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="63537-121">父元素</span><span class="sxs-lookup"><span data-stu-id="63537-121">Parent Elements</span></span>  
  
|<span data-ttu-id="63537-122">元素</span><span class="sxs-lookup"><span data-stu-id="63537-122">Element</span></span>|<span data-ttu-id="63537-123">描述</span><span class="sxs-lookup"><span data-stu-id="63537-123">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="63537-124">\<tokenRequestParameters></span><span class="sxs-lookup"><span data-stu-id="63537-124">\<tokenRequestParameters></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/tokenrequestparameters.md)|<span data-ttu-id="63537-125">令牌请求参数的集合。</span><span class="sxs-lookup"><span data-stu-id="63537-125">A collection of token request parameters.</span></span> <span data-ttu-id="63537-126">每个参数都是一个 XML 元素。</span><span class="sxs-lookup"><span data-stu-id="63537-126">Each parameter is an XML element.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="63537-127">请参阅</span><span class="sxs-lookup"><span data-stu-id="63537-127">See Also</span></span>  
 <xref:System.ServiceModel.FederatedMessageSecurityOverHttp.TokenRequestParameters%2A>  
 <xref:System.ServiceModel.Configuration.FederatedMessageSecurityOverHttpElement.TokenRequestParameters%2A>  
 [<span data-ttu-id="63537-128">服务标识和身份验证</span><span class="sxs-lookup"><span data-stu-id="63537-128">Service Identity and Authentication</span></span>](../../../../../docs/framework/wcf/feature-details/service-identity-and-authentication.md)  
 [<span data-ttu-id="63537-129">联合令牌与颁发的令牌</span><span class="sxs-lookup"><span data-stu-id="63537-129">Federation and Issued Tokens</span></span>](../../../../../docs/framework/wcf/feature-details/federation-and-issued-tokens.md)  
 [<span data-ttu-id="63537-130">使用自定义绑定的安全功能</span><span class="sxs-lookup"><span data-stu-id="63537-130">Security Capabilities with Custom Bindings</span></span>](../../../../../docs/framework/wcf/feature-details/security-capabilities-with-custom-bindings.md)  
 [<span data-ttu-id="63537-131">联合令牌与颁发的令牌</span><span class="sxs-lookup"><span data-stu-id="63537-131">Federation and Issued Tokens</span></span>](../../../../../docs/framework/wcf/feature-details/federation-and-issued-tokens.md)  
 [<span data-ttu-id="63537-132">绑定</span><span class="sxs-lookup"><span data-stu-id="63537-132">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)
