---
title: '&lt;netHttpBinding 的 &gt;security&lt;'
ms.date: 03/30/2017
ms.assetid: dc41f6f7-cabc-4a64-9fa0-ceabf861b348
ms.openlocfilehash: 71157413ba10aa6b45006235d3de69628fce75f9
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/03/2018
---
# <a name="ltsecuritygt-of-ltnethttpbinding"></a><span data-ttu-id="abd2e-102">&lt;netHttpBinding 的 &gt;security&lt;</span><span class="sxs-lookup"><span data-stu-id="abd2e-102">&lt;security&gt; of &lt;netHttpBinding</span></span>
<span data-ttu-id="abd2e-103">定义的安全功能[ \<basicHttpBinding >](../../../../../docs/framework/configure-apps/file-schema/wcf/basichttpbinding.md)。</span><span class="sxs-lookup"><span data-stu-id="abd2e-103">Defines the security capabilities of the [\<basicHttpBinding>](../../../../../docs/framework/configure-apps/file-schema/wcf/basichttpbinding.md).</span></span>  
  
 <span data-ttu-id="abd2e-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="abd2e-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="abd2e-105">\<绑定 ></span><span class="sxs-lookup"><span data-stu-id="abd2e-105">\<bindings></span></span>  
<span data-ttu-id="abd2e-106">\<netHttpBinding></span><span class="sxs-lookup"><span data-stu-id="abd2e-106">\<netHttpBinding></span></span>  
<span data-ttu-id="abd2e-107">\<绑定 ></span><span class="sxs-lookup"><span data-stu-id="abd2e-107">\<binding></span></span>  
<span data-ttu-id="abd2e-108">\<安全 ></span><span class="sxs-lookup"><span data-stu-id="abd2e-108">\<security></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="abd2e-109">语法</span><span class="sxs-lookup"><span data-stu-id="abd2e-109">Syntax</span></span>  
  
```xml  
<security mode="Message/None/Transport/TransportWithCredential">  
   <transport  
      clientCredentialType="Basic/Certificate/Digest/None/Ntlm/Windows"  
      proxyCredentialType="Basic/Digest/None/Ntlm/Windows"  
      realm="string" />  
   <message  
      algorithmSuite="Basic128/Basic192/Basic256/Basic128Rsa15/Basic256Rsa15/TripleDes/TripleDesRsa15/Basic128Sha256/Basic192Sha256/TripleDesSha256/Basic128Sha256Rsa15/Basic192Sha256Rsa15/Basic256Sha256Rsa15/TripleDesSha256Rsa15"  
            clientCredentialType="Certificate/IssuedToken/None/UserName/Windows" />  
</security>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="abd2e-110">特性和元素</span><span class="sxs-lookup"><span data-stu-id="abd2e-110">Attributes and Elements</span></span>  
 <span data-ttu-id="abd2e-111">以下几节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="abd2e-111">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="abd2e-112">特性</span><span class="sxs-lookup"><span data-stu-id="abd2e-112">Attributes</span></span>  
  
|<span data-ttu-id="abd2e-113">特性</span><span class="sxs-lookup"><span data-stu-id="abd2e-113">Attribute</span></span>|<span data-ttu-id="abd2e-114">描述</span><span class="sxs-lookup"><span data-stu-id="abd2e-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="abd2e-115">mode</span><span class="sxs-lookup"><span data-stu-id="abd2e-115">mode</span></span>|<span data-ttu-id="abd2e-116">可选。</span><span class="sxs-lookup"><span data-stu-id="abd2e-116">Optional.</span></span> <span data-ttu-id="abd2e-117">指定所使用的安全类型。</span><span class="sxs-lookup"><span data-stu-id="abd2e-117">Specifies the type of security that is used.</span></span> <span data-ttu-id="abd2e-118">默认值为 `None`。</span><span class="sxs-lookup"><span data-stu-id="abd2e-118">The default is `None`.</span></span> <span data-ttu-id="abd2e-119">此属性的类型是<!--zz <xref:System.ServiceModel.NetHttpSecurityMode> --> `System.ServiceModel.NetHttpSecurityMode`。</span><span class="sxs-lookup"><span data-stu-id="abd2e-119">This attribute is of type <!--zz <xref:System.ServiceModel.NetHttpSecurityMode> -->`System.ServiceModel.NetHttpSecurityMode`.</span></span>|
  
## <a name="mode-attribute"></a><span data-ttu-id="abd2e-120">mode 属性</span><span class="sxs-lookup"><span data-stu-id="abd2e-120">mode Attribute</span></span>  
  
|<span data-ttu-id="abd2e-121">值</span><span class="sxs-lookup"><span data-stu-id="abd2e-121">Value</span></span>|<span data-ttu-id="abd2e-122">描述</span><span class="sxs-lookup"><span data-stu-id="abd2e-122">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="abd2e-123">无</span><span class="sxs-lookup"><span data-stu-id="abd2e-123">None</span></span>|<span data-ttu-id="abd2e-124">的在传输过程中不是安全消息。</span><span class="sxs-lookup"><span data-stu-id="abd2e-124">-   Messages are not secured during transfer.</span></span>|  
|<span data-ttu-id="abd2e-125">传输</span><span class="sxs-lookup"><span data-stu-id="abd2e-125">Transport</span></span>|<span data-ttu-id="abd2e-126">使用 HTTPS 传输提供安全性。</span><span class="sxs-lookup"><span data-stu-id="abd2e-126">Security is provided using HTTPS transport.</span></span> <span data-ttu-id="abd2e-127">用 HTTPS 保证 SOAP 消息的安全。</span><span class="sxs-lookup"><span data-stu-id="abd2e-127">The SOAP messages are secured using HTTPS.</span></span> <span data-ttu-id="abd2e-128">使用服务的 X.509 证书向客户端对服务进行身份验证。</span><span class="sxs-lookup"><span data-stu-id="abd2e-128">The service is authenticated to the client using the service's X.509 certificate.</span></span> <span data-ttu-id="abd2e-129">使用所提供的 ClientCredentialType 对客户端进行身份验证。</span><span class="sxs-lookup"><span data-stu-id="abd2e-129">The client is authenticated using the ClientCredentialType supplied.</span></span>|  
|<span data-ttu-id="abd2e-130">消息</span><span class="sxs-lookup"><span data-stu-id="abd2e-130">Message</span></span>|<span data-ttu-id="abd2e-131">使用 SOAP 消息安全提供安全性。</span><span class="sxs-lookup"><span data-stu-id="abd2e-131">Security is provided using SOAP message security.</span></span> <span data-ttu-id="abd2e-132">默认情况下，将对正文进行加密和签名。</span><span class="sxs-lookup"><span data-stu-id="abd2e-132">By default, the body is encrypted and signed.</span></span> <span data-ttu-id="abd2e-133">对于此绑定，系统要求向带外客户端提供服务器证书。</span><span class="sxs-lookup"><span data-stu-id="abd2e-133">For this binding, the system requires that the server certificate be provided to the client out of band.</span></span> <span data-ttu-id="abd2e-134">此绑定仅有的有效 `ClientCredentialType` 为 `Certificate`。</span><span class="sxs-lookup"><span data-stu-id="abd2e-134">The only valid `ClientCredentialType` for this binding is `Certificate`.</span></span>|  
|<span data-ttu-id="abd2e-135">TransportWithMessageCredential</span><span class="sxs-lookup"><span data-stu-id="abd2e-135">TransportWithMessageCredential</span></span>|<span data-ttu-id="abd2e-136">完整性、保密性和服务器身份验证由传输安全来提供。</span><span class="sxs-lookup"><span data-stu-id="abd2e-136">Integrity, confidentiality and server authentication are provided by transport security.</span></span> <span data-ttu-id="abd2e-137">客户端身份验证采用 SOAP 消息安全方式提供。</span><span class="sxs-lookup"><span data-stu-id="abd2e-137">Client authentication is provided by means of SOAP message security.</span></span> <span data-ttu-id="abd2e-138">如果要使用用户名/密码对用户进行身份验证，并且存在用于保护消息传输的现有 HTTP 部署，则适用此模式。</span><span class="sxs-lookup"><span data-stu-id="abd2e-138">This mode is relevant when the user is authenticating using username/password and there is an existing HTTP deployment for securing message transfer.</span></span>|  
|<span data-ttu-id="abd2e-139">TransportCredentialOnly</span><span class="sxs-lookup"><span data-stu-id="abd2e-139">TransportCredentialOnly</span></span>|<span data-ttu-id="abd2e-140">此模式并不提供消息的完整性和保密性，</span><span class="sxs-lookup"><span data-stu-id="abd2e-140">This mode does not provide message integrity and confidentiality.</span></span> <span data-ttu-id="abd2e-141">而是提供基于 http 的客户端身份验证。</span><span class="sxs-lookup"><span data-stu-id="abd2e-141">It provides http-based client authentication.</span></span> <span data-ttu-id="abd2e-142">使用此模式时应当小心。</span><span class="sxs-lookup"><span data-stu-id="abd2e-142">This mode should be used with caution.</span></span> <span data-ttu-id="abd2e-143">在通过其他方式（如 IPSec）提供传输安全并且 [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)] 基础结构只提供客户端身份验证的环境中，应该使用此模式。</span><span class="sxs-lookup"><span data-stu-id="abd2e-143">It should be used in environments where the transport security is being provided by other means (such as IPSec) and only client authentication is provided by the [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)] infrastructure.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="abd2e-144">子元素</span><span class="sxs-lookup"><span data-stu-id="abd2e-144">Child Elements</span></span>  
  
|<span data-ttu-id="abd2e-145">元素</span><span class="sxs-lookup"><span data-stu-id="abd2e-145">Element</span></span>|<span data-ttu-id="abd2e-146">描述</span><span class="sxs-lookup"><span data-stu-id="abd2e-146">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="abd2e-147">\<transport></span><span class="sxs-lookup"><span data-stu-id="abd2e-147">\<transport></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/transport-of-nethttpbinding.md)|<span data-ttu-id="abd2e-148">定义基本 HTTP 服务的传输安全设置。</span><span class="sxs-lookup"><span data-stu-id="abd2e-148">Defines the transport security settings for a basic HTTP service.</span></span> <span data-ttu-id="abd2e-149">此元素与 <xref:System.ServiceModel.HttpTransportSecurity> 相对应。</span><span class="sxs-lookup"><span data-stu-id="abd2e-149">This element corresponds to <xref:System.ServiceModel.HttpTransportSecurity>.</span></span>|  
|[<span data-ttu-id="abd2e-150">\<message></span><span class="sxs-lookup"><span data-stu-id="abd2e-150">\<message></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/message-of-nethttpbinding.md)|<span data-ttu-id="abd2e-151">定义基本 HTTP 服务的消息安全设置。</span><span class="sxs-lookup"><span data-stu-id="abd2e-151">Defines the message security settings for a basic HTTP service.</span></span> <span data-ttu-id="abd2e-152">此元素对应于<!--zz <xref:System.ServiceModel.NetHttpMessageSecurity> --> `System.ServiceModel.NetHttpMessageSecurity`。</span><span class="sxs-lookup"><span data-stu-id="abd2e-152">This element corresponds to <!--zz <xref:System.ServiceModel.NetHttpMessageSecurity> --> `System.ServiceModel.NetHttpMessageSecurity`.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="abd2e-153">父元素</span><span class="sxs-lookup"><span data-stu-id="abd2e-153">Parent Elements</span></span>  
  
|<span data-ttu-id="abd2e-154">元素</span><span class="sxs-lookup"><span data-stu-id="abd2e-154">Element</span></span>|<span data-ttu-id="abd2e-155">描述</span><span class="sxs-lookup"><span data-stu-id="abd2e-155">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="abd2e-156">绑定</span><span class="sxs-lookup"><span data-stu-id="abd2e-156">binding</span></span>|<span data-ttu-id="abd2e-157">绑定元素[ \<basicHttpBinding >](../../../../../docs/framework/configure-apps/file-schema/wcf/basichttpbinding.md)。</span><span class="sxs-lookup"><span data-stu-id="abd2e-157">The binding element of the [\<basicHttpBinding>](../../../../../docs/framework/configure-apps/file-schema/wcf/basichttpbinding.md).</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="abd2e-158">备注</span><span class="sxs-lookup"><span data-stu-id="abd2e-158">Remarks</span></span>  
 <span data-ttu-id="abd2e-159">默认情况下，不会对 SOAP 消息进行保护，也不会对客户端进行身份验证。</span><span class="sxs-lookup"><span data-stu-id="abd2e-159">By default, the SOAP message is not secured and the client is not authenticated.</span></span> <span data-ttu-id="abd2e-160">使用此元素，您可以配置 `netHttpBinding` 元素的其他安全设置。</span><span class="sxs-lookup"><span data-stu-id="abd2e-160">This element enables you to configure additional security settings for the `netHttpBinding` element.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="abd2e-161">请参阅</span><span class="sxs-lookup"><span data-stu-id="abd2e-161">See Also</span></span>  
 <xref:System.ServiceModel.NetHttpBinding.Security%2A>  
 <xref:System.ServiceModel.Configuration.NetHttpBindingElement.Security%2A>    
 [<span data-ttu-id="abd2e-162">保护服务和客户端的安全</span><span class="sxs-lookup"><span data-stu-id="abd2e-162">Securing Services and Clients</span></span>](../../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)  
 [<span data-ttu-id="abd2e-163">选择凭据类型</span><span class="sxs-lookup"><span data-stu-id="abd2e-163">Selecting a Credential Type</span></span>](../../../../../docs/framework/wcf/feature-details/selecting-a-credential-type.md)  
 [<span data-ttu-id="abd2e-164">绑定</span><span class="sxs-lookup"><span data-stu-id="abd2e-164">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)  
 [<span data-ttu-id="abd2e-165">配置系统提供的绑定</span><span class="sxs-lookup"><span data-stu-id="abd2e-165">Configuring System-Provided Bindings</span></span>](../../../../../docs/framework/wcf/feature-details/configuring-system-provided-bindings.md)  
 [<span data-ttu-id="abd2e-166">使用绑定来配置 Windows Communication Foundation 服务和客户端</span><span class="sxs-lookup"><span data-stu-id="abd2e-166">Using Bindings to Configure Windows Communication Foundation Services and Clients</span></span>](http://msdn.microsoft.com/library/bd8b277b-932f-472f-a42a-b02bb5257dfb)  
 [<span data-ttu-id="abd2e-167">\<绑定 ></span><span class="sxs-lookup"><span data-stu-id="abd2e-167">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)
