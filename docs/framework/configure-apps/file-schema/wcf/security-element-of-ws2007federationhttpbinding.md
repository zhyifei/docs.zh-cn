---
title: <security>的元素<ws2007FederationHttpBinding>
ms.date: 03/30/2017
ms.assetid: 826219b4-3a16-45fc-832d-0cd7cbbd3b84
ms.openlocfilehash: 61b56ca1fae5c328cda0bbebef4026f0784095a3
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2019
ms.locfileid: "69936820"
---
# <a name="security-element-of-ws2007federationhttpbinding"></a><span data-ttu-id="f2cad-102">\<ws2007FederationHttpBinding > 的\<security > 元素</span><span class="sxs-lookup"><span data-stu-id="f2cad-102">\<security> element of \<ws2007FederationHttpBinding></span></span>
<span data-ttu-id="f2cad-103">定义 ws2007FederationHttpBinding 的安全设置[ \<>](ws2007federationhttpbinding.md)元素。</span><span class="sxs-lookup"><span data-stu-id="f2cad-103">Defines the security settings of the [\<ws2007FederationHttpBinding>](ws2007federationhttpbinding.md) element.</span></span>  
  
 <span data-ttu-id="f2cad-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="f2cad-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="f2cad-105">\<bindings></span><span class="sxs-lookup"><span data-stu-id="f2cad-105">\<bindings></span></span>  
<span data-ttu-id="f2cad-106">\<ws2007FederationHttpBinding></span><span class="sxs-lookup"><span data-stu-id="f2cad-106">\<ws2007FederationHttpBinding></span></span>  
<span data-ttu-id="f2cad-107">\<绑定 ></span><span class="sxs-lookup"><span data-stu-id="f2cad-107">\<binding></span></span>  
<span data-ttu-id="f2cad-108">\<安全 ></span><span class="sxs-lookup"><span data-stu-id="f2cad-108">\<security></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f2cad-109">语法</span><span class="sxs-lookup"><span data-stu-id="f2cad-109">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="f2cad-110">特性和元素</span><span class="sxs-lookup"><span data-stu-id="f2cad-110">Attributes and Elements</span></span>  
 <span data-ttu-id="f2cad-111">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="f2cad-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="f2cad-112">特性</span><span class="sxs-lookup"><span data-stu-id="f2cad-112">Attributes</span></span>  
  
|<span data-ttu-id="f2cad-113">特性</span><span class="sxs-lookup"><span data-stu-id="f2cad-113">Attribute</span></span>|<span data-ttu-id="f2cad-114">描述</span><span class="sxs-lookup"><span data-stu-id="f2cad-114">Description</span></span>|  
|---------------|-----------------|  
|`mode`|<span data-ttu-id="f2cad-115">可选。</span><span class="sxs-lookup"><span data-stu-id="f2cad-115">Optional.</span></span> <span data-ttu-id="f2cad-116">指定所应用的安全类型。</span><span class="sxs-lookup"><span data-stu-id="f2cad-116">Specifies the type of security that is applied.</span></span> <span data-ttu-id="f2cad-117">默认值为 `Message`。</span><span class="sxs-lookup"><span data-stu-id="f2cad-117">The default value is `Message`.</span></span> <span data-ttu-id="f2cad-118">此属性的类型为 <xref:System.ServiceModel.WSFederationHttpSecurityMode>。</span><span class="sxs-lookup"><span data-stu-id="f2cad-118">This attribute is of type <xref:System.ServiceModel.WSFederationHttpSecurityMode>.</span></span>|  
  
## <a name="mode-attribute"></a><span data-ttu-id="f2cad-119">mode 属性</span><span class="sxs-lookup"><span data-stu-id="f2cad-119">mode Attribute</span></span>  
  
|<span data-ttu-id="f2cad-120">值</span><span class="sxs-lookup"><span data-stu-id="f2cad-120">Value</span></span>|<span data-ttu-id="f2cad-121">描述</span><span class="sxs-lookup"><span data-stu-id="f2cad-121">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="f2cad-122">无</span><span class="sxs-lookup"><span data-stu-id="f2cad-122">None</span></span>|<span data-ttu-id="f2cad-123">SOAP 消息在传输过程中并不安全。</span><span class="sxs-lookup"><span data-stu-id="f2cad-123">The SOAP message is not secure during transfer.</span></span>|  
|<span data-ttu-id="f2cad-124">消息</span><span class="sxs-lookup"><span data-stu-id="f2cad-124">Message</span></span>|<span data-ttu-id="f2cad-125">通过使用 SOAP 消息安全，可以提供完整性、保密性、服务器身份验证和客户端身份验证。</span><span class="sxs-lookup"><span data-stu-id="f2cad-125">Integrity, confidentiality, server authentication and client authentication are provided using SOAP message security.</span></span> <span data-ttu-id="f2cad-126">默认情况下，将对正文进行加密和签名。</span><span class="sxs-lookup"><span data-stu-id="f2cad-126">By default, the body is encrypted and signed.</span></span> <span data-ttu-id="f2cad-127">此服务必须使用证书进行配置。</span><span class="sxs-lookup"><span data-stu-id="f2cad-127">The service must be configured with a certificate.</span></span> <span data-ttu-id="f2cad-128">客户端根据由安全令牌服务颁发给客户端的令牌进行身份验证。</span><span class="sxs-lookup"><span data-stu-id="f2cad-128">Client authentication is based on the token issued to the client by a security token service.</span></span>|  
|<span data-ttu-id="f2cad-129">TransportWithMessageCredential</span><span class="sxs-lookup"><span data-stu-id="f2cad-129">TransportWithMessageCredential</span></span>|<span data-ttu-id="f2cad-130">完整性、保密性和服务器身份验证均由 HTTPS 提供。</span><span class="sxs-lookup"><span data-stu-id="f2cad-130">Integrity, confidentiality and server authentication are provided by HTTPS.</span></span> <span data-ttu-id="f2cad-131">此服务必须使用证书进行配置。</span><span class="sxs-lookup"><span data-stu-id="f2cad-131">The service must be configured with a certificate.</span></span> <span data-ttu-id="f2cad-132">客户端身份验证采用 SOAP 消息安全方式提供，并根据由安全令牌服务颁发给客户端的令牌进行。</span><span class="sxs-lookup"><span data-stu-id="f2cad-132">Client authentication is provided by means of SOAP message security and is based on the token issued to the client by a security token service.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="f2cad-133">子元素</span><span class="sxs-lookup"><span data-stu-id="f2cad-133">Child Elements</span></span>  
  
|<span data-ttu-id="f2cad-134">元素</span><span class="sxs-lookup"><span data-stu-id="f2cad-134">Element</span></span>|<span data-ttu-id="f2cad-135">描述</span><span class="sxs-lookup"><span data-stu-id="f2cad-135">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="f2cad-136">\<message></span><span class="sxs-lookup"><span data-stu-id="f2cad-136">\<message></span></span>](message-of-ws2007httpbinding.md)|<span data-ttu-id="f2cad-137">定义消息级安全性设置。</span><span class="sxs-lookup"><span data-stu-id="f2cad-137">Defines the settings for the message-level security.</span></span> <span data-ttu-id="f2cad-138">此元素的类型为 <xref:System.ServiceModel.Configuration.FederatedMessageSecurityOverHttpElement>。</span><span class="sxs-lookup"><span data-stu-id="f2cad-138">This element is of type <xref:System.ServiceModel.Configuration.FederatedMessageSecurityOverHttpElement>.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="f2cad-139">父元素</span><span class="sxs-lookup"><span data-stu-id="f2cad-139">Parent Elements</span></span>  
  
|<span data-ttu-id="f2cad-140">元素</span><span class="sxs-lookup"><span data-stu-id="f2cad-140">Element</span></span>|<span data-ttu-id="f2cad-141">描述</span><span class="sxs-lookup"><span data-stu-id="f2cad-141">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="f2cad-142">\<binding></span><span class="sxs-lookup"><span data-stu-id="f2cad-142">\<binding></span></span>](../../../misc/binding.md)|<span data-ttu-id="f2cad-143">定义[ \<wsDualHttpBinding >](wsdualhttpbinding.md)的所有绑定功能。</span><span class="sxs-lookup"><span data-stu-id="f2cad-143">Defines all binding capabilities of the [\<wsDualHttpBinding>](wsdualhttpbinding.md).</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="f2cad-144">请参阅</span><span class="sxs-lookup"><span data-stu-id="f2cad-144">See also</span></span>

- <xref:System.ServiceModel.WSFederationHttpSecurity>
- <xref:System.ServiceModel.WSFederationHttpBinding.Security%2A>
- <xref:System.ServiceModel.Configuration.WSFederationHttpBindingElement.Security%2A>
- <xref:System.ServiceModel.Configuration.WSFederationHttpSecurityElement>
- [<span data-ttu-id="f2cad-145">如何：创建 WSFederationHttpBinding</span><span class="sxs-lookup"><span data-stu-id="f2cad-145">How to: Create a WSFederationHttpBinding</span></span>](../../../wcf/feature-details/how-to-create-a-wsfederationhttpbinding.md)
- [<span data-ttu-id="f2cad-146">保护服务和客户端的安全</span><span class="sxs-lookup"><span data-stu-id="f2cad-146">Securing Services and Clients</span></span>](../../../wcf/feature-details/securing-services-and-clients.md)
- [<span data-ttu-id="f2cad-147">选择凭据类型</span><span class="sxs-lookup"><span data-stu-id="f2cad-147">Selecting a Credential Type</span></span>](../../../wcf/feature-details/selecting-a-credential-type.md)
- [<span data-ttu-id="f2cad-148">绑定</span><span class="sxs-lookup"><span data-stu-id="f2cad-148">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="f2cad-149">配置系统提供的绑定</span><span class="sxs-lookup"><span data-stu-id="f2cad-149">Configuring System-Provided Bindings</span></span>](../../../wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="f2cad-150">使用绑定配置服务和客户端</span><span class="sxs-lookup"><span data-stu-id="f2cad-150">Using Bindings to Configure Services and Clients</span></span>](../../../wcf/using-bindings-to-configure-services-and-clients.md)
- [<span data-ttu-id="f2cad-151">\<binding></span><span class="sxs-lookup"><span data-stu-id="f2cad-151">\<binding></span></span>](../../../misc/binding.md)
