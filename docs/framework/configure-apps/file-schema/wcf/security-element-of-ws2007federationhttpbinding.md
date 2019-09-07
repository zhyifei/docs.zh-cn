---
title: <security>的元素<ws2007FederationHttpBinding>
ms.date: 03/30/2017
ms.assetid: 826219b4-3a16-45fc-832d-0cd7cbbd3b84
ms.openlocfilehash: 450b2403b8cd4ec43a41fd27bccb3b77202820bb
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/06/2019
ms.locfileid: "70399908"
---
# <a name="security-element-of-ws2007federationhttpbinding"></a><span data-ttu-id="34e7d-102">\<ws2007FederationHttpBinding > 的\<security > 元素</span><span class="sxs-lookup"><span data-stu-id="34e7d-102">\<security> element of \<ws2007FederationHttpBinding></span></span>
<span data-ttu-id="34e7d-103">定义 ws2007FederationHttpBinding 的安全设置[ \<>](ws2007federationhttpbinding.md)元素。</span><span class="sxs-lookup"><span data-stu-id="34e7d-103">Defines the security settings of the [\<ws2007FederationHttpBinding>](ws2007federationhttpbinding.md) element.</span></span>  
  
<span data-ttu-id="34e7d-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="34e7d-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="34e7d-105">&nbsp;&nbsp;[ **\<System.servicemodel >** ](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="34e7d-105">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="34e7d-106">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<绑定 >** ](bindings.md)</span><span class="sxs-lookup"><span data-stu-id="34e7d-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)</span></span>\
<span data-ttu-id="34e7d-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<ws2007FederationHttpBinding >** ](ws2007federationhttpbinding.md)</span><span class="sxs-lookup"><span data-stu-id="34e7d-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<ws2007FederationHttpBinding>**](ws2007federationhttpbinding.md)</span></span>\
<span data-ttu-id="34e7d-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<绑定 >** </span><span class="sxs-lookup"><span data-stu-id="34e7d-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**</span></span>\
<span data-ttu-id="34e7d-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<安全 >**</span><span class="sxs-lookup"><span data-stu-id="34e7d-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<security>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="34e7d-110">语法</span><span class="sxs-lookup"><span data-stu-id="34e7d-110">Syntax</span></span>  
  
```xml  
<ws2007FederationBinding>
  <binding>
    <security mode="None/Message/TransportWithMessageCredential">
      <message negotiateServiceCredential="Boolean"
               algorithmSuite="Basic128/Basic192/Basic256/Basic128Rsa15/  Basic256Rsa15/TripleDes/TripleDesRsa15/Basic128Sha256/Basic192Sha256/TripleDesSha256/Basic128Sha256Rsa15/Basic192Sha256Rsa15/Basic256Sha256Rsa15/TripleDesSha256Rsa15"
               defaultProtectionLevel="none/sign/EncryptAndSign"
               issuedTokenType="string"
               issuedKeyType="SymmetricKey/PublicKey">
      </message>
    </security>
  </binding>
</ws2007FederationBinding>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="34e7d-111">特性和元素</span><span class="sxs-lookup"><span data-stu-id="34e7d-111">Attributes and Elements</span></span>  
 <span data-ttu-id="34e7d-112">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="34e7d-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="34e7d-113">特性</span><span class="sxs-lookup"><span data-stu-id="34e7d-113">Attributes</span></span>  
  
|<span data-ttu-id="34e7d-114">特性</span><span class="sxs-lookup"><span data-stu-id="34e7d-114">Attribute</span></span>|<span data-ttu-id="34e7d-115">描述</span><span class="sxs-lookup"><span data-stu-id="34e7d-115">Description</span></span>|  
|---------------|-----------------|  
|`mode`|<span data-ttu-id="34e7d-116">可选。</span><span class="sxs-lookup"><span data-stu-id="34e7d-116">Optional.</span></span> <span data-ttu-id="34e7d-117">指定所应用的安全类型。</span><span class="sxs-lookup"><span data-stu-id="34e7d-117">Specifies the type of security that is applied.</span></span> <span data-ttu-id="34e7d-118">默认值为 `Message`。</span><span class="sxs-lookup"><span data-stu-id="34e7d-118">The default value is `Message`.</span></span> <span data-ttu-id="34e7d-119">此属性的类型为 <xref:System.ServiceModel.WSFederationHttpSecurityMode>。</span><span class="sxs-lookup"><span data-stu-id="34e7d-119">This attribute is of type <xref:System.ServiceModel.WSFederationHttpSecurityMode>.</span></span>|  
  
## <a name="mode-attribute"></a><span data-ttu-id="34e7d-120">mode 属性</span><span class="sxs-lookup"><span data-stu-id="34e7d-120">mode Attribute</span></span>  
  
|<span data-ttu-id="34e7d-121">值</span><span class="sxs-lookup"><span data-stu-id="34e7d-121">Value</span></span>|<span data-ttu-id="34e7d-122">描述</span><span class="sxs-lookup"><span data-stu-id="34e7d-122">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="34e7d-123">无</span><span class="sxs-lookup"><span data-stu-id="34e7d-123">None</span></span>|<span data-ttu-id="34e7d-124">SOAP 消息在传输过程中并不安全。</span><span class="sxs-lookup"><span data-stu-id="34e7d-124">The SOAP message is not secure during transfer.</span></span>|  
|<span data-ttu-id="34e7d-125">消息</span><span class="sxs-lookup"><span data-stu-id="34e7d-125">Message</span></span>|<span data-ttu-id="34e7d-126">通过使用 SOAP 消息安全，可以提供完整性、保密性、服务器身份验证和客户端身份验证。</span><span class="sxs-lookup"><span data-stu-id="34e7d-126">Integrity, confidentiality, server authentication and client authentication are provided using SOAP message security.</span></span> <span data-ttu-id="34e7d-127">默认情况下，将对正文进行加密和签名。</span><span class="sxs-lookup"><span data-stu-id="34e7d-127">By default, the body is encrypted and signed.</span></span> <span data-ttu-id="34e7d-128">此服务必须使用证书进行配置。</span><span class="sxs-lookup"><span data-stu-id="34e7d-128">The service must be configured with a certificate.</span></span> <span data-ttu-id="34e7d-129">客户端根据由安全令牌服务颁发给客户端的令牌进行身份验证。</span><span class="sxs-lookup"><span data-stu-id="34e7d-129">Client authentication is based on the token issued to the client by a security token service.</span></span>|  
|<span data-ttu-id="34e7d-130">TransportWithMessageCredential</span><span class="sxs-lookup"><span data-stu-id="34e7d-130">TransportWithMessageCredential</span></span>|<span data-ttu-id="34e7d-131">完整性、保密性和服务器身份验证均由 HTTPS 提供。</span><span class="sxs-lookup"><span data-stu-id="34e7d-131">Integrity, confidentiality and server authentication are provided by HTTPS.</span></span> <span data-ttu-id="34e7d-132">此服务必须使用证书进行配置。</span><span class="sxs-lookup"><span data-stu-id="34e7d-132">The service must be configured with a certificate.</span></span> <span data-ttu-id="34e7d-133">客户端身份验证采用 SOAP 消息安全方式提供，并根据由安全令牌服务颁发给客户端的令牌进行。</span><span class="sxs-lookup"><span data-stu-id="34e7d-133">Client authentication is provided by means of SOAP message security and is based on the token issued to the client by a security token service.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="34e7d-134">子元素</span><span class="sxs-lookup"><span data-stu-id="34e7d-134">Child Elements</span></span>  
  
|<span data-ttu-id="34e7d-135">元素</span><span class="sxs-lookup"><span data-stu-id="34e7d-135">Element</span></span>|<span data-ttu-id="34e7d-136">描述</span><span class="sxs-lookup"><span data-stu-id="34e7d-136">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="34e7d-137">\<message></span><span class="sxs-lookup"><span data-stu-id="34e7d-137">\<message></span></span>](message-of-ws2007httpbinding.md)|<span data-ttu-id="34e7d-138">定义消息级安全性设置。</span><span class="sxs-lookup"><span data-stu-id="34e7d-138">Defines the settings for the message-level security.</span></span> <span data-ttu-id="34e7d-139">此元素的类型为 <xref:System.ServiceModel.Configuration.FederatedMessageSecurityOverHttpElement>。</span><span class="sxs-lookup"><span data-stu-id="34e7d-139">This element is of type <xref:System.ServiceModel.Configuration.FederatedMessageSecurityOverHttpElement>.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="34e7d-140">父元素</span><span class="sxs-lookup"><span data-stu-id="34e7d-140">Parent Elements</span></span>  
  
|<span data-ttu-id="34e7d-141">元素</span><span class="sxs-lookup"><span data-stu-id="34e7d-141">Element</span></span>|<span data-ttu-id="34e7d-142">描述</span><span class="sxs-lookup"><span data-stu-id="34e7d-142">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="34e7d-143">\<binding></span><span class="sxs-lookup"><span data-stu-id="34e7d-143">\<binding></span></span>](../../../misc/binding.md)|<span data-ttu-id="34e7d-144">定义[ \<wsDualHttpBinding >](wsdualhttpbinding.md)的所有绑定功能。</span><span class="sxs-lookup"><span data-stu-id="34e7d-144">Defines all binding capabilities of the [\<wsDualHttpBinding>](wsdualhttpbinding.md).</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="34e7d-145">请参阅</span><span class="sxs-lookup"><span data-stu-id="34e7d-145">See also</span></span>

- <xref:System.ServiceModel.WSFederationHttpSecurity>
- <xref:System.ServiceModel.WSFederationHttpBinding.Security%2A>
- <xref:System.ServiceModel.Configuration.WSFederationHttpBindingElement.Security%2A>
- <xref:System.ServiceModel.Configuration.WSFederationHttpSecurityElement>
- [<span data-ttu-id="34e7d-146">如何：创建 WSFederationHttpBinding</span><span class="sxs-lookup"><span data-stu-id="34e7d-146">How to: Create a WSFederationHttpBinding</span></span>](../../../wcf/feature-details/how-to-create-a-wsfederationhttpbinding.md)
- [<span data-ttu-id="34e7d-147">保护服务和客户端的安全</span><span class="sxs-lookup"><span data-stu-id="34e7d-147">Securing Services and Clients</span></span>](../../../wcf/feature-details/securing-services-and-clients.md)
- [<span data-ttu-id="34e7d-148">选择凭据类型</span><span class="sxs-lookup"><span data-stu-id="34e7d-148">Selecting a Credential Type</span></span>](../../../wcf/feature-details/selecting-a-credential-type.md)
- [<span data-ttu-id="34e7d-149">绑定</span><span class="sxs-lookup"><span data-stu-id="34e7d-149">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="34e7d-150">配置系统提供的绑定</span><span class="sxs-lookup"><span data-stu-id="34e7d-150">Configuring System-Provided Bindings</span></span>](../../../wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="34e7d-151">使用绑定配置服务和客户端</span><span class="sxs-lookup"><span data-stu-id="34e7d-151">Using Bindings to Configure Services and Clients</span></span>](../../../wcf/using-bindings-to-configure-services-and-clients.md)
- [<span data-ttu-id="34e7d-152">\<binding></span><span class="sxs-lookup"><span data-stu-id="34e7d-152">\<binding></span></span>](../../../misc/binding.md)
