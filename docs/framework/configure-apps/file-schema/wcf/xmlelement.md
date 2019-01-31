---
title: <xmlElement>
ms.date: 03/30/2017
ms.assetid: 395205c2-d8c0-4a5e-90f3-7ce3c085fccd
ms.openlocfilehash: 648147a7e3977648ac3c26c9dfc469629f3b70c3
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/30/2019
ms.locfileid: "55278286"
---
# <a name="xmlelement"></a><span data-ttu-id="be271-101">\<xmlElement></span><span class="sxs-lookup"><span data-stu-id="be271-101">\<xmlElement></span></span>
<span data-ttu-id="be271-102">指定一个 XML 元素，请求令牌时，该元素在消息正文中发送到安全令牌服务。</span><span class="sxs-lookup"><span data-stu-id="be271-102">Specifies an XML element that is sent in the message body to the Security Token Service when requesting a token.</span></span>  
  
 <span data-ttu-id="be271-103">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="be271-103">\<system.ServiceModel></span></span>  
<span data-ttu-id="be271-104">\<bindings></span><span class="sxs-lookup"><span data-stu-id="be271-104">\<bindings></span></span>  
<span data-ttu-id="be271-105">\<wsFederatedBinding></span><span class="sxs-lookup"><span data-stu-id="be271-105">\<wsFederatedBinding></span></span>  
<span data-ttu-id="be271-106">\<binding></span><span class="sxs-lookup"><span data-stu-id="be271-106">\<binding></span></span>  
<span data-ttu-id="be271-107">\<安全 ></span><span class="sxs-lookup"><span data-stu-id="be271-107">\<security></span></span>  
<span data-ttu-id="be271-108">\<message></span><span class="sxs-lookup"><span data-stu-id="be271-108">\<message></span></span>  
<span data-ttu-id="be271-109">\<tokenRequestParameters></span><span class="sxs-lookup"><span data-stu-id="be271-109">\<tokenRequestParameters></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="be271-110">语法</span><span class="sxs-lookup"><span data-stu-id="be271-110">Syntax</span></span>  
  
```xml  
<tokenRequestParameters>
  <xmlElement xmlElement="String" />
</tokenRequestParameters>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="be271-111">特性和元素</span><span class="sxs-lookup"><span data-stu-id="be271-111">Attributes and Elements</span></span>  
 <span data-ttu-id="be271-112">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="be271-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="be271-113">特性</span><span class="sxs-lookup"><span data-stu-id="be271-113">Attributes</span></span>  
  
|<span data-ttu-id="be271-114">特性</span><span class="sxs-lookup"><span data-stu-id="be271-114">Attribute</span></span>|<span data-ttu-id="be271-115">描述</span><span class="sxs-lookup"><span data-stu-id="be271-115">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="be271-116">xmlElement</span><span class="sxs-lookup"><span data-stu-id="be271-116">xmlElement</span></span>|<span data-ttu-id="be271-117">指定 XML 元素的字符串，请求令牌时，该元素在消息正文中发送到安全令牌服务。</span><span class="sxs-lookup"><span data-stu-id="be271-117">A string specifying an XML element that is sent in the message body to the Security Token Service when requesting a token.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="be271-118">子元素</span><span class="sxs-lookup"><span data-stu-id="be271-118">Child Elements</span></span>  
 <span data-ttu-id="be271-119">无。</span><span class="sxs-lookup"><span data-stu-id="be271-119">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="be271-120">父元素</span><span class="sxs-lookup"><span data-stu-id="be271-120">Parent Elements</span></span>  
  
|<span data-ttu-id="be271-121">元素</span><span class="sxs-lookup"><span data-stu-id="be271-121">Element</span></span>|<span data-ttu-id="be271-122">描述</span><span class="sxs-lookup"><span data-stu-id="be271-122">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="be271-123">\<tokenRequestParameters></span><span class="sxs-lookup"><span data-stu-id="be271-123">\<tokenRequestParameters></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/tokenrequestparameters.md)|<span data-ttu-id="be271-124">令牌请求参数的集合。</span><span class="sxs-lookup"><span data-stu-id="be271-124">A collection of token request parameters.</span></span> <span data-ttu-id="be271-125">每个参数都是一个 XML 元素。</span><span class="sxs-lookup"><span data-stu-id="be271-125">Each parameter is an XML element.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="be271-126">请参阅</span><span class="sxs-lookup"><span data-stu-id="be271-126">See also</span></span>
- <xref:System.ServiceModel.FederatedMessageSecurityOverHttp.TokenRequestParameters%2A>
- <xref:System.ServiceModel.Configuration.FederatedMessageSecurityOverHttpElement.TokenRequestParameters%2A>
- [<span data-ttu-id="be271-127">服务标识和身份验证</span><span class="sxs-lookup"><span data-stu-id="be271-127">Service Identity and Authentication</span></span>](../../../../../docs/framework/wcf/feature-details/service-identity-and-authentication.md)
- [<span data-ttu-id="be271-128">联合令牌与颁发的令牌</span><span class="sxs-lookup"><span data-stu-id="be271-128">Federation and Issued Tokens</span></span>](../../../../../docs/framework/wcf/feature-details/federation-and-issued-tokens.md)
- [<span data-ttu-id="be271-129">使用自定义绑定的安全功能</span><span class="sxs-lookup"><span data-stu-id="be271-129">Security Capabilities with Custom Bindings</span></span>](../../../../../docs/framework/wcf/feature-details/security-capabilities-with-custom-bindings.md)
- [<span data-ttu-id="be271-130">联合令牌与颁发的令牌</span><span class="sxs-lookup"><span data-stu-id="be271-130">Federation and Issued Tokens</span></span>](../../../../../docs/framework/wcf/feature-details/federation-and-issued-tokens.md)
- [<span data-ttu-id="be271-131">绑定</span><span class="sxs-lookup"><span data-stu-id="be271-131">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)
