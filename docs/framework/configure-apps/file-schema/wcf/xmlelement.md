---
title: <xmlElement>
ms.date: 03/30/2017
ms.assetid: 395205c2-d8c0-4a5e-90f3-7ce3c085fccd
ms.openlocfilehash: 841331f233bb8c42c25c88ad8e9b4fb1a86faa76
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/06/2019
ms.locfileid: "70398991"
---
# <a name="xmlelement"></a><span data-ttu-id="89a41-101">\<xmlElement></span><span class="sxs-lookup"><span data-stu-id="89a41-101">\<xmlElement></span></span>
<span data-ttu-id="89a41-102">指定一个 XML 元素，请求令牌时，该元素在消息正文中发送到安全令牌服务。</span><span class="sxs-lookup"><span data-stu-id="89a41-102">Specifies an XML element that is sent in the message body to the Security Token Service when requesting a token.</span></span>  
  
<span data-ttu-id="89a41-103">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="89a41-103">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="89a41-104">&nbsp;&nbsp;[ **\<System.servicemodel >** ](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="89a41-104">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="89a41-105">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<绑定 >** ](bindings.md)</span><span class="sxs-lookup"><span data-stu-id="89a41-105">&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)</span></span>\
<span data-ttu-id="89a41-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<wsFederationHttpBinding >** ](wsfederationhttpbinding.md)</span><span class="sxs-lookup"><span data-stu-id="89a41-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<wsFederationHttpBinding>**](wsfederationhttpbinding.md)</span></span>\
<span data-ttu-id="89a41-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<绑定 >** </span><span class="sxs-lookup"><span data-stu-id="89a41-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**</span></span>\
<span data-ttu-id="89a41-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<安全 >** ](security-of-wsfederationhttpbinding.md)</span><span class="sxs-lookup"><span data-stu-id="89a41-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<security>**](security-of-wsfederationhttpbinding.md)</span></span>\
<span data-ttu-id="89a41-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<消息 >** ](message-element-of-wsfederationhttpbinding.md)</span><span class="sxs-lookup"><span data-stu-id="89a41-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<message>**](message-element-of-wsfederationhttpbinding.md)</span></span>\
<span data-ttu-id="89a41-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<tokenRequestParameters >** ](tokenrequestparameters.md)</span><span class="sxs-lookup"><span data-stu-id="89a41-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<tokenRequestParameters>**](tokenrequestparameters.md)</span></span>\
<span data-ttu-id="89a41-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<xmlElement >**</span><span class="sxs-lookup"><span data-stu-id="89a41-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<xmlElement>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="89a41-112">语法</span><span class="sxs-lookup"><span data-stu-id="89a41-112">Syntax</span></span>  
  
```xml  
<tokenRequestParameters>
  <xmlElement xmlElement="String" />
</tokenRequestParameters>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="89a41-113">特性和元素</span><span class="sxs-lookup"><span data-stu-id="89a41-113">Attributes and Elements</span></span>  
 <span data-ttu-id="89a41-114">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="89a41-114">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="89a41-115">特性</span><span class="sxs-lookup"><span data-stu-id="89a41-115">Attributes</span></span>  
  
|<span data-ttu-id="89a41-116">特性</span><span class="sxs-lookup"><span data-stu-id="89a41-116">Attribute</span></span>|<span data-ttu-id="89a41-117">描述</span><span class="sxs-lookup"><span data-stu-id="89a41-117">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="89a41-118">xmlElement</span><span class="sxs-lookup"><span data-stu-id="89a41-118">xmlElement</span></span>|<span data-ttu-id="89a41-119">指定 XML 元素的字符串，请求令牌时，该元素在消息正文中发送到安全令牌服务。</span><span class="sxs-lookup"><span data-stu-id="89a41-119">A string specifying an XML element that is sent in the message body to the Security Token Service when requesting a token.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="89a41-120">子元素</span><span class="sxs-lookup"><span data-stu-id="89a41-120">Child Elements</span></span>  
 <span data-ttu-id="89a41-121">无。</span><span class="sxs-lookup"><span data-stu-id="89a41-121">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="89a41-122">父元素</span><span class="sxs-lookup"><span data-stu-id="89a41-122">Parent Elements</span></span>  
  
|<span data-ttu-id="89a41-123">元素</span><span class="sxs-lookup"><span data-stu-id="89a41-123">Element</span></span>|<span data-ttu-id="89a41-124">描述</span><span class="sxs-lookup"><span data-stu-id="89a41-124">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="89a41-125">\<tokenRequestParameters></span><span class="sxs-lookup"><span data-stu-id="89a41-125">\<tokenRequestParameters></span></span>](tokenrequestparameters.md)|<span data-ttu-id="89a41-126">令牌请求参数的集合。</span><span class="sxs-lookup"><span data-stu-id="89a41-126">A collection of token request parameters.</span></span> <span data-ttu-id="89a41-127">每个参数都是一个 XML 元素。</span><span class="sxs-lookup"><span data-stu-id="89a41-127">Each parameter is an XML element.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="89a41-128">请参阅</span><span class="sxs-lookup"><span data-stu-id="89a41-128">See also</span></span>

- <xref:System.ServiceModel.FederatedMessageSecurityOverHttp.TokenRequestParameters%2A>
- <xref:System.ServiceModel.Configuration.FederatedMessageSecurityOverHttpElement.TokenRequestParameters%2A>
- [<span data-ttu-id="89a41-129">服务标识和身份验证</span><span class="sxs-lookup"><span data-stu-id="89a41-129">Service Identity and Authentication</span></span>](../../../wcf/feature-details/service-identity-and-authentication.md)
- [<span data-ttu-id="89a41-130">联合令牌与颁发的令牌</span><span class="sxs-lookup"><span data-stu-id="89a41-130">Federation and Issued Tokens</span></span>](../../../wcf/feature-details/federation-and-issued-tokens.md)
- [<span data-ttu-id="89a41-131">使用自定义绑定的安全功能</span><span class="sxs-lookup"><span data-stu-id="89a41-131">Security Capabilities with Custom Bindings</span></span>](../../../wcf/feature-details/security-capabilities-with-custom-bindings.md)
- [<span data-ttu-id="89a41-132">联合令牌与颁发的令牌</span><span class="sxs-lookup"><span data-stu-id="89a41-132">Federation and Issued Tokens</span></span>](../../../wcf/feature-details/federation-and-issued-tokens.md)
- [<span data-ttu-id="89a41-133">绑定</span><span class="sxs-lookup"><span data-stu-id="89a41-133">Bindings</span></span>](../../../wcf/bindings.md)
