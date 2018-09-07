---
title: '&lt;netHttpBinding 的 &gt;security&lt;'
ms.date: 03/30/2017
ms.assetid: dc41f6f7-cabc-4a64-9fa0-ceabf861b348
ms.openlocfilehash: 6357593be17c2d008204598d51610fa3dbf77c27
ms.sourcegitcommit: a885cc8c3e444ca6471348893d5373c6e9e49a47
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/07/2018
ms.locfileid: "44061073"
---
# <a name="ltsecuritygt-of-ltnethttpbinding"></a><span data-ttu-id="fdcb8-102">&lt;netHttpBinding 的 &gt;security&lt;</span><span class="sxs-lookup"><span data-stu-id="fdcb8-102">&lt;security&gt; of &lt;netHttpBinding</span></span>
<span data-ttu-id="fdcb8-103">定义的安全功能[ \<basicHttpBinding >](../../../../../docs/framework/configure-apps/file-schema/wcf/basichttpbinding.md)。</span><span class="sxs-lookup"><span data-stu-id="fdcb8-103">Defines the security capabilities of the [\<basicHttpBinding>](../../../../../docs/framework/configure-apps/file-schema/wcf/basichttpbinding.md).</span></span>  
  
 <span data-ttu-id="fdcb8-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="fdcb8-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="fdcb8-105">\<绑定 ></span><span class="sxs-lookup"><span data-stu-id="fdcb8-105">\<bindings></span></span>  
<span data-ttu-id="fdcb8-106">\<netHttpBinding></span><span class="sxs-lookup"><span data-stu-id="fdcb8-106">\<netHttpBinding></span></span>  
<span data-ttu-id="fdcb8-107">\<绑定 ></span><span class="sxs-lookup"><span data-stu-id="fdcb8-107">\<binding></span></span>  
<span data-ttu-id="fdcb8-108">\<安全 ></span><span class="sxs-lookup"><span data-stu-id="fdcb8-108">\<security></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fdcb8-109">语法</span><span class="sxs-lookup"><span data-stu-id="fdcb8-109">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="fdcb8-110">特性和元素</span><span class="sxs-lookup"><span data-stu-id="fdcb8-110">Attributes and Elements</span></span>  
 <span data-ttu-id="fdcb8-111">以下几节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="fdcb8-111">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="fdcb8-112">特性</span><span class="sxs-lookup"><span data-stu-id="fdcb8-112">Attributes</span></span>  
  
|<span data-ttu-id="fdcb8-113">特性</span><span class="sxs-lookup"><span data-stu-id="fdcb8-113">Attribute</span></span>|<span data-ttu-id="fdcb8-114">描述</span><span class="sxs-lookup"><span data-stu-id="fdcb8-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="fdcb8-115">mode</span><span class="sxs-lookup"><span data-stu-id="fdcb8-115">mode</span></span>|<span data-ttu-id="fdcb8-116">可选。</span><span class="sxs-lookup"><span data-stu-id="fdcb8-116">Optional.</span></span> <span data-ttu-id="fdcb8-117">指定所使用的安全类型。</span><span class="sxs-lookup"><span data-stu-id="fdcb8-117">Specifies the type of security that is used.</span></span> <span data-ttu-id="fdcb8-118">默认值为 `None`。</span><span class="sxs-lookup"><span data-stu-id="fdcb8-118">The default is `None`.</span></span> <span data-ttu-id="fdcb8-119">此属性的类型是<!--zz <xref:System.ServiceModel.NetHttpSecurityMode> --> `System.ServiceModel.NetHttpSecurityMode`。</span><span class="sxs-lookup"><span data-stu-id="fdcb8-119">This attribute is of type <!--zz <xref:System.ServiceModel.NetHttpSecurityMode> -->`System.ServiceModel.NetHttpSecurityMode`.</span></span>|
  
## <a name="mode-attribute"></a><span data-ttu-id="fdcb8-120">mode 属性</span><span class="sxs-lookup"><span data-stu-id="fdcb8-120">mode Attribute</span></span>  
  
|<span data-ttu-id="fdcb8-121">值</span><span class="sxs-lookup"><span data-stu-id="fdcb8-121">Value</span></span>|<span data-ttu-id="fdcb8-122">描述</span><span class="sxs-lookup"><span data-stu-id="fdcb8-122">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="fdcb8-123">无</span><span class="sxs-lookup"><span data-stu-id="fdcb8-123">None</span></span>|<span data-ttu-id="fdcb8-124">的在传输过程中不是安全消息数。</span><span class="sxs-lookup"><span data-stu-id="fdcb8-124">-   Messages are not secured during transfer.</span></span>|  
|<span data-ttu-id="fdcb8-125">传输</span><span class="sxs-lookup"><span data-stu-id="fdcb8-125">Transport</span></span>|<span data-ttu-id="fdcb8-126">使用 HTTPS 传输提供安全性。</span><span class="sxs-lookup"><span data-stu-id="fdcb8-126">Security is provided using HTTPS transport.</span></span> <span data-ttu-id="fdcb8-127">用 HTTPS 保证 SOAP 消息的安全。</span><span class="sxs-lookup"><span data-stu-id="fdcb8-127">The SOAP messages are secured using HTTPS.</span></span> <span data-ttu-id="fdcb8-128">使用服务的 X.509 证书向客户端对服务进行身份验证。</span><span class="sxs-lookup"><span data-stu-id="fdcb8-128">The service is authenticated to the client using the service's X.509 certificate.</span></span> <span data-ttu-id="fdcb8-129">使用所提供的 ClientCredentialType 对客户端进行身份验证。</span><span class="sxs-lookup"><span data-stu-id="fdcb8-129">The client is authenticated using the ClientCredentialType supplied.</span></span>|  
|<span data-ttu-id="fdcb8-130">消息</span><span class="sxs-lookup"><span data-stu-id="fdcb8-130">Message</span></span>|<span data-ttu-id="fdcb8-131">使用 SOAP 消息安全提供安全性。</span><span class="sxs-lookup"><span data-stu-id="fdcb8-131">Security is provided using SOAP message security.</span></span> <span data-ttu-id="fdcb8-132">默认情况下，将对正文进行加密和签名。</span><span class="sxs-lookup"><span data-stu-id="fdcb8-132">By default, the body is encrypted and signed.</span></span> <span data-ttu-id="fdcb8-133">对于此绑定，系统要求向带外客户端提供服务器证书。</span><span class="sxs-lookup"><span data-stu-id="fdcb8-133">For this binding, the system requires that the server certificate be provided to the client out of band.</span></span> <span data-ttu-id="fdcb8-134">此绑定仅有的有效 `ClientCredentialType` 为 `Certificate`。</span><span class="sxs-lookup"><span data-stu-id="fdcb8-134">The only valid `ClientCredentialType` for this binding is `Certificate`.</span></span>|  
|<span data-ttu-id="fdcb8-135">TransportWithMessageCredential</span><span class="sxs-lookup"><span data-stu-id="fdcb8-135">TransportWithMessageCredential</span></span>|<span data-ttu-id="fdcb8-136">完整性、保密性和服务器身份验证由传输安全来提供。</span><span class="sxs-lookup"><span data-stu-id="fdcb8-136">Integrity, confidentiality and server authentication are provided by transport security.</span></span> <span data-ttu-id="fdcb8-137">客户端身份验证采用 SOAP 消息安全方式提供。</span><span class="sxs-lookup"><span data-stu-id="fdcb8-137">Client authentication is provided by means of SOAP message security.</span></span> <span data-ttu-id="fdcb8-138">如果要使用用户名/密码对用户进行身份验证，并且存在用于保护消息传输的现有 HTTP 部署，则适用此模式。</span><span class="sxs-lookup"><span data-stu-id="fdcb8-138">This mode is relevant when the user is authenticating using username/password and there is an existing HTTP deployment for securing message transfer.</span></span>|  
|<span data-ttu-id="fdcb8-139">TransportCredentialOnly</span><span class="sxs-lookup"><span data-stu-id="fdcb8-139">TransportCredentialOnly</span></span>|<span data-ttu-id="fdcb8-140">此模式并不提供消息的完整性和保密性，</span><span class="sxs-lookup"><span data-stu-id="fdcb8-140">This mode does not provide message integrity and confidentiality.</span></span> <span data-ttu-id="fdcb8-141">而是提供基于 http 的客户端身份验证。</span><span class="sxs-lookup"><span data-stu-id="fdcb8-141">It provides http-based client authentication.</span></span> <span data-ttu-id="fdcb8-142">使用此模式时应当小心。</span><span class="sxs-lookup"><span data-stu-id="fdcb8-142">This mode should be used with caution.</span></span> <span data-ttu-id="fdcb8-143">它应在其中通过其他方式 （如 IPSec) 提供传输安全和 WCF 基础结构提供仅客户端身份验证的环境中使用。</span><span class="sxs-lookup"><span data-stu-id="fdcb8-143">It should be used in environments where the transport security is being provided by other means (such as IPSec) and only client authentication is provided by the WCF infrastructure.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="fdcb8-144">子元素</span><span class="sxs-lookup"><span data-stu-id="fdcb8-144">Child Elements</span></span>  
  
|<span data-ttu-id="fdcb8-145">元素</span><span class="sxs-lookup"><span data-stu-id="fdcb8-145">Element</span></span>|<span data-ttu-id="fdcb8-146">描述</span><span class="sxs-lookup"><span data-stu-id="fdcb8-146">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="fdcb8-147">\<transport></span><span class="sxs-lookup"><span data-stu-id="fdcb8-147">\<transport></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/transport-of-nethttpbinding.md)|<span data-ttu-id="fdcb8-148">定义基本 HTTP 服务的传输安全设置。</span><span class="sxs-lookup"><span data-stu-id="fdcb8-148">Defines the transport security settings for a basic HTTP service.</span></span> <span data-ttu-id="fdcb8-149">此元素与 <xref:System.ServiceModel.HttpTransportSecurity> 相对应。</span><span class="sxs-lookup"><span data-stu-id="fdcb8-149">This element corresponds to <xref:System.ServiceModel.HttpTransportSecurity>.</span></span>|  
|[<span data-ttu-id="fdcb8-150">\<message></span><span class="sxs-lookup"><span data-stu-id="fdcb8-150">\<message></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/message-of-nethttpbinding.md)|<span data-ttu-id="fdcb8-151">定义基本 HTTP 服务的消息安全设置。</span><span class="sxs-lookup"><span data-stu-id="fdcb8-151">Defines the message security settings for a basic HTTP service.</span></span> <span data-ttu-id="fdcb8-152">此元素对应于<!--zz <xref:System.ServiceModel.NetHttpMessageSecurity> --> `System.ServiceModel.NetHttpMessageSecurity`。</span><span class="sxs-lookup"><span data-stu-id="fdcb8-152">This element corresponds to <!--zz <xref:System.ServiceModel.NetHttpMessageSecurity> --> `System.ServiceModel.NetHttpMessageSecurity`.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="fdcb8-153">父元素</span><span class="sxs-lookup"><span data-stu-id="fdcb8-153">Parent Elements</span></span>  
  
|<span data-ttu-id="fdcb8-154">元素</span><span class="sxs-lookup"><span data-stu-id="fdcb8-154">Element</span></span>|<span data-ttu-id="fdcb8-155">描述</span><span class="sxs-lookup"><span data-stu-id="fdcb8-155">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="fdcb8-156">绑定</span><span class="sxs-lookup"><span data-stu-id="fdcb8-156">binding</span></span>|<span data-ttu-id="fdcb8-157">绑定元素[ \<basicHttpBinding >](../../../../../docs/framework/configure-apps/file-schema/wcf/basichttpbinding.md)。</span><span class="sxs-lookup"><span data-stu-id="fdcb8-157">The binding element of the [\<basicHttpBinding>](../../../../../docs/framework/configure-apps/file-schema/wcf/basichttpbinding.md).</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="fdcb8-158">备注</span><span class="sxs-lookup"><span data-stu-id="fdcb8-158">Remarks</span></span>  
 <span data-ttu-id="fdcb8-159">默认情况下，不会对 SOAP 消息进行保护，也不会对客户端进行身份验证。</span><span class="sxs-lookup"><span data-stu-id="fdcb8-159">By default, the SOAP message is not secured and the client is not authenticated.</span></span> <span data-ttu-id="fdcb8-160">使用此元素，您可以配置 `netHttpBinding` 元素的其他安全设置。</span><span class="sxs-lookup"><span data-stu-id="fdcb8-160">This element enables you to configure additional security settings for the `netHttpBinding` element.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fdcb8-161">请参阅</span><span class="sxs-lookup"><span data-stu-id="fdcb8-161">See Also</span></span>  
 <xref:System.ServiceModel.NetHttpBinding.Security%2A>  
 <xref:System.ServiceModel.Configuration.NetHttpBindingElement.Security%2A>    
 [<span data-ttu-id="fdcb8-162">保护服务和客户端的安全</span><span class="sxs-lookup"><span data-stu-id="fdcb8-162">Securing Services and Clients</span></span>](../../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)  
 [<span data-ttu-id="fdcb8-163">选择凭据类型</span><span class="sxs-lookup"><span data-stu-id="fdcb8-163">Selecting a Credential Type</span></span>](../../../../../docs/framework/wcf/feature-details/selecting-a-credential-type.md)  
 [<span data-ttu-id="fdcb8-164">绑定</span><span class="sxs-lookup"><span data-stu-id="fdcb8-164">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)  
 [<span data-ttu-id="fdcb8-165">配置系统提供的绑定</span><span class="sxs-lookup"><span data-stu-id="fdcb8-165">Configuring System-Provided Bindings</span></span>](../../../../../docs/framework/wcf/feature-details/configuring-system-provided-bindings.md)  
 [<span data-ttu-id="fdcb8-166">使用绑定来配置 Windows Communication Foundation 服务和客户端</span><span class="sxs-lookup"><span data-stu-id="fdcb8-166">Using Bindings to Configure Windows Communication Foundation Services and Clients</span></span>](https://msdn.microsoft.com/library/bd8b277b-932f-472f-a42a-b02bb5257dfb)  
 [<span data-ttu-id="fdcb8-167">\<绑定 ></span><span class="sxs-lookup"><span data-stu-id="fdcb8-167">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)
