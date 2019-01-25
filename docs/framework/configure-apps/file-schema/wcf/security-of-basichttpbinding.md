---
title: '&lt;basicHttpBinding&gt; 的 &lt;security&gt;'
ms.date: 03/30/2017
ms.assetid: 6432708d-5465-4bd9-bfc2-466742db99cb
ms.openlocfilehash: 9e6a0e864dcb83a529a5ac457e2fcffe0435376f
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54701165"
---
# <a name="ltsecuritygt-of-ltbasichttpbindinggt"></a><span data-ttu-id="2a38a-102">&lt;basicHttpBinding&gt; 的 &lt;security&gt;</span><span class="sxs-lookup"><span data-stu-id="2a38a-102">&lt;security&gt; of &lt;basicHttpBinding&gt;</span></span>
<span data-ttu-id="2a38a-103">定义的安全功能[ \<basicHttpBinding >](../../../../../docs/framework/configure-apps/file-schema/wcf/basichttpbinding.md)。</span><span class="sxs-lookup"><span data-stu-id="2a38a-103">Defines the security capabilities of the [\<basicHttpBinding>](../../../../../docs/framework/configure-apps/file-schema/wcf/basichttpbinding.md).</span></span>  
  
 <span data-ttu-id="2a38a-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="2a38a-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="2a38a-105">\<bindings></span><span class="sxs-lookup"><span data-stu-id="2a38a-105">\<bindings></span></span>  
<span data-ttu-id="2a38a-106">\<basicHttpBinding></span><span class="sxs-lookup"><span data-stu-id="2a38a-106">\<basicHttpBinding></span></span>  
<span data-ttu-id="2a38a-107">\<binding></span><span class="sxs-lookup"><span data-stu-id="2a38a-107">\<binding></span></span>  
<span data-ttu-id="2a38a-108">\<安全 ></span><span class="sxs-lookup"><span data-stu-id="2a38a-108">\<security></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2a38a-109">语法</span><span class="sxs-lookup"><span data-stu-id="2a38a-109">Syntax</span></span>  
  
```xml  
<security mode="Message/None/Transport/TransportWithCredential">
  <transport clientCredentialType="Basic/Certificate/Digest/None/Ntlm/Windows"
             proxyCredentialType="Basic/Digest/None/Ntlm/Windows"
             realm="string" />
  <message algorithmSuite="Basic128/Basic192/Basic256/Basic128Rsa15/Basic256Rsa15/TripleDes/TripleDesRsa15/Basic128Sha256/Basic192Sha256/TripleDesSha256/Basic128Sha256Rsa15/Basic192Sha256Rsa15/Basic256Sha256Rsa15/TripleDesSha256Rsa15"
           clientCredentialType="Certificate/IssuedToken/None/UserName/Windows" />
</security>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="2a38a-110">特性和元素</span><span class="sxs-lookup"><span data-stu-id="2a38a-110">Attributes and Elements</span></span>  
 <span data-ttu-id="2a38a-111">以下几节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="2a38a-111">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="2a38a-112">特性</span><span class="sxs-lookup"><span data-stu-id="2a38a-112">Attributes</span></span>  
  
|<span data-ttu-id="2a38a-113">特性</span><span class="sxs-lookup"><span data-stu-id="2a38a-113">Attribute</span></span>|<span data-ttu-id="2a38a-114">描述</span><span class="sxs-lookup"><span data-stu-id="2a38a-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="2a38a-115">mode</span><span class="sxs-lookup"><span data-stu-id="2a38a-115">mode</span></span>|<span data-ttu-id="2a38a-116">可选。</span><span class="sxs-lookup"><span data-stu-id="2a38a-116">Optional.</span></span> <span data-ttu-id="2a38a-117">指定所使用的安全类型。</span><span class="sxs-lookup"><span data-stu-id="2a38a-117">Specifies the type of security that is used.</span></span> <span data-ttu-id="2a38a-118">默认值为 `None`。</span><span class="sxs-lookup"><span data-stu-id="2a38a-118">The default is `None`.</span></span> <span data-ttu-id="2a38a-119">此属性的类型为 <xref:System.ServiceModel.BasicHttpSecurityMode>。</span><span class="sxs-lookup"><span data-stu-id="2a38a-119">This attribute is of type <xref:System.ServiceModel.BasicHttpSecurityMode>.</span></span>|  
  
## <a name="mode-attribute"></a><span data-ttu-id="2a38a-120">mode 属性</span><span class="sxs-lookup"><span data-stu-id="2a38a-120">mode Attribute</span></span>  
  
|<span data-ttu-id="2a38a-121">值</span><span class="sxs-lookup"><span data-stu-id="2a38a-121">Value</span></span>|<span data-ttu-id="2a38a-122">描述</span><span class="sxs-lookup"><span data-stu-id="2a38a-122">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="2a38a-123">无</span><span class="sxs-lookup"><span data-stu-id="2a38a-123">None</span></span>|<span data-ttu-id="2a38a-124">的在传输过程中不是安全消息数。</span><span class="sxs-lookup"><span data-stu-id="2a38a-124">-   Messages are not secured during transfer.</span></span>|  
|<span data-ttu-id="2a38a-125">传输</span><span class="sxs-lookup"><span data-stu-id="2a38a-125">Transport</span></span>|<span data-ttu-id="2a38a-126">使用 HTTPS 传输提供安全性。</span><span class="sxs-lookup"><span data-stu-id="2a38a-126">Security is provided using HTTPS transport.</span></span> <span data-ttu-id="2a38a-127">用 HTTPS 保证 SOAP 消息的安全。</span><span class="sxs-lookup"><span data-stu-id="2a38a-127">The SOAP messages are secured using HTTPS.</span></span> <span data-ttu-id="2a38a-128">使用服务的 X.509 证书向客户端对服务进行身份验证。</span><span class="sxs-lookup"><span data-stu-id="2a38a-128">The service is authenticated to the client using the service's X.509 certificate.</span></span> <span data-ttu-id="2a38a-129">使用所提供的 ClientCredentialType 对客户端进行身份验证。</span><span class="sxs-lookup"><span data-stu-id="2a38a-129">The client is authenticated using the ClientCredentialType supplied.</span></span> <span data-ttu-id="2a38a-130">请参阅[\<传输 >](../../../../../docs/framework/configure-apps/file-schema/wcf/transport-of-basichttpbinding.md)。</span><span class="sxs-lookup"><span data-stu-id="2a38a-130">See the [\<transport>](../../../../../docs/framework/configure-apps/file-schema/wcf/transport-of-basichttpbinding.md).</span></span>|  
|<span data-ttu-id="2a38a-131">消息</span><span class="sxs-lookup"><span data-stu-id="2a38a-131">Message</span></span>|<span data-ttu-id="2a38a-132">使用 SOAP 消息安全提供安全性。</span><span class="sxs-lookup"><span data-stu-id="2a38a-132">Security is provided using SOAP message security.</span></span> <span data-ttu-id="2a38a-133">默认情况下，将对正文进行加密和签名。</span><span class="sxs-lookup"><span data-stu-id="2a38a-133">By default, the body is encrypted and signed.</span></span> <span data-ttu-id="2a38a-134">对于此绑定，系统要求向带外客户端提供服务器证书。</span><span class="sxs-lookup"><span data-stu-id="2a38a-134">For this binding, the system requires that the server certificate be provided to the client out of band.</span></span> <span data-ttu-id="2a38a-135">此绑定仅有的有效 `ClientCredentialType` 为 `Certificate`。</span><span class="sxs-lookup"><span data-stu-id="2a38a-135">The only valid `ClientCredentialType` for this binding is `Certificate`.</span></span>|  
|<span data-ttu-id="2a38a-136">TransportWithMessageCredential</span><span class="sxs-lookup"><span data-stu-id="2a38a-136">TransportWithMessageCredential</span></span>|<span data-ttu-id="2a38a-137">完整性、保密性和服务器身份验证由传输安全来提供。</span><span class="sxs-lookup"><span data-stu-id="2a38a-137">Integrity, confidentiality and server authentication are provided by transport security.</span></span> <span data-ttu-id="2a38a-138">客户端身份验证采用 SOAP 消息安全方式提供。</span><span class="sxs-lookup"><span data-stu-id="2a38a-138">Client authentication is provided by means of SOAP message security.</span></span> <span data-ttu-id="2a38a-139">如果要使用用户名/密码对用户进行身份验证，并且存在用于保护消息传输的现有 HTTP 部署，则适用此模式。</span><span class="sxs-lookup"><span data-stu-id="2a38a-139">This mode is relevant when the user is authenticating using username/password and there is an existing HTTP deployment for securing message transfer.</span></span>|  
|<span data-ttu-id="2a38a-140">TransportCredentialOnly</span><span class="sxs-lookup"><span data-stu-id="2a38a-140">TransportCredentialOnly</span></span>|<span data-ttu-id="2a38a-141">此模式并不提供消息的完整性和保密性，</span><span class="sxs-lookup"><span data-stu-id="2a38a-141">This mode does not provide message integrity and confidentiality.</span></span> <span data-ttu-id="2a38a-142">而是提供基于 http 的客户端身份验证。</span><span class="sxs-lookup"><span data-stu-id="2a38a-142">It provides http-based client authentication.</span></span> <span data-ttu-id="2a38a-143">使用此模式时应当小心。</span><span class="sxs-lookup"><span data-stu-id="2a38a-143">This mode should be used with caution.</span></span> <span data-ttu-id="2a38a-144">它应在其中通过其他方式 （如 IPSec) 提供传输安全和 WCF 基础结构提供仅客户端身份验证的环境中使用。</span><span class="sxs-lookup"><span data-stu-id="2a38a-144">It should be used in environments where the transport security is being provided by other means (such as IPSec) and only client authentication is provided by the WCF infrastructure.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="2a38a-145">子元素</span><span class="sxs-lookup"><span data-stu-id="2a38a-145">Child Elements</span></span>  
  
|<span data-ttu-id="2a38a-146">元素</span><span class="sxs-lookup"><span data-stu-id="2a38a-146">Element</span></span>|<span data-ttu-id="2a38a-147">描述</span><span class="sxs-lookup"><span data-stu-id="2a38a-147">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="2a38a-148">\<transport></span><span class="sxs-lookup"><span data-stu-id="2a38a-148">\<transport></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/transport-of-basichttpbinding.md)|<span data-ttu-id="2a38a-149">定义基本 HTTP 服务的传输安全设置。</span><span class="sxs-lookup"><span data-stu-id="2a38a-149">Defines the transport security settings for a basic HTTP service.</span></span> <span data-ttu-id="2a38a-150">此元素与 <xref:System.ServiceModel.HttpTransportSecurity> 相对应。</span><span class="sxs-lookup"><span data-stu-id="2a38a-150">This element corresponds to <xref:System.ServiceModel.HttpTransportSecurity>.</span></span>|  
|[<span data-ttu-id="2a38a-151">\<message></span><span class="sxs-lookup"><span data-stu-id="2a38a-151">\<message></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/message-of-basichttpbinding.md)|<span data-ttu-id="2a38a-152">定义基本 HTTP 服务的消息安全设置。</span><span class="sxs-lookup"><span data-stu-id="2a38a-152">Defines the message security settings for a basic HTTP service.</span></span> <span data-ttu-id="2a38a-153">此元素与 <xref:System.ServiceModel.BasicHttpMessageSecurity> 相对应。</span><span class="sxs-lookup"><span data-stu-id="2a38a-153">This element corresponds to <xref:System.ServiceModel.BasicHttpMessageSecurity>.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="2a38a-154">父元素</span><span class="sxs-lookup"><span data-stu-id="2a38a-154">Parent Elements</span></span>  
  
|<span data-ttu-id="2a38a-155">元素</span><span class="sxs-lookup"><span data-stu-id="2a38a-155">Element</span></span>|<span data-ttu-id="2a38a-156">描述</span><span class="sxs-lookup"><span data-stu-id="2a38a-156">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="2a38a-157">绑定</span><span class="sxs-lookup"><span data-stu-id="2a38a-157">binding</span></span>|<span data-ttu-id="2a38a-158">绑定元素[ \<basicHttpBinding >](../../../../../docs/framework/configure-apps/file-schema/wcf/basichttpbinding.md)。</span><span class="sxs-lookup"><span data-stu-id="2a38a-158">The binding element of the [\<basicHttpBinding>](../../../../../docs/framework/configure-apps/file-schema/wcf/basichttpbinding.md).</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="2a38a-159">备注</span><span class="sxs-lookup"><span data-stu-id="2a38a-159">Remarks</span></span>  
 <span data-ttu-id="2a38a-160">默认情况下，不会对 SOAP 消息进行保护，也不会对客户端进行身份验证。</span><span class="sxs-lookup"><span data-stu-id="2a38a-160">By default, the SOAP message is not secured and the client is not authenticated.</span></span> <span data-ttu-id="2a38a-161">使用此元素，您可以配置 `basicHttpBinding` 元素的其他安全设置。</span><span class="sxs-lookup"><span data-stu-id="2a38a-161">This element enables you to configure additional security settings for the `basicHttpBinding` element.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2a38a-162">请参阅</span><span class="sxs-lookup"><span data-stu-id="2a38a-162">See also</span></span>
- <xref:System.ServiceModel.BasicHttpBinding.Security%2A>
- <xref:System.ServiceModel.Configuration.BasicHttpBindingElement.Security%2A>
- <xref:System.ServiceModel.Configuration.BasicHttpSecurityElement>
- <xref:System.ServiceModel.BasicHttpSecurity>
- [<span data-ttu-id="2a38a-163">保护服务和客户端的安全</span><span class="sxs-lookup"><span data-stu-id="2a38a-163">Securing Services and Clients</span></span>](../../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)
- [<span data-ttu-id="2a38a-164">选择凭据类型</span><span class="sxs-lookup"><span data-stu-id="2a38a-164">Selecting a Credential Type</span></span>](../../../../../docs/framework/wcf/feature-details/selecting-a-credential-type.md)
- [<span data-ttu-id="2a38a-165">绑定</span><span class="sxs-lookup"><span data-stu-id="2a38a-165">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)
- [<span data-ttu-id="2a38a-166">配置系统提供的绑定</span><span class="sxs-lookup"><span data-stu-id="2a38a-166">Configuring System-Provided Bindings</span></span>](../../../../../docs/framework/wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="2a38a-167">使用绑定配置服务和客户端</span><span class="sxs-lookup"><span data-stu-id="2a38a-167">Using Bindings to Configure Services and Clients</span></span>](../../../../../docs/framework/wcf/using-bindings-to-configure-services-and-clients.md)
- [<span data-ttu-id="2a38a-168">\<binding></span><span class="sxs-lookup"><span data-stu-id="2a38a-168">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)
