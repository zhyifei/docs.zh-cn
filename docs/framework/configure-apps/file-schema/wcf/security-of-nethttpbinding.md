---
title: "&lt;netHttpBinding 的 &gt;security&lt;"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: dc41f6f7-cabc-4a64-9fa0-ceabf861b348
caps.latest.revision: "3"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 1caae9411ca0ba8896613a38b446a3f0d190bb18
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="ltsecuritygt-of-ltnethttpbinding"></a><span data-ttu-id="d1796-102">&lt;netHttpBinding 的 &gt;security&lt;</span><span class="sxs-lookup"><span data-stu-id="d1796-102">&lt;security&gt; of &lt;netHttpBinding</span></span>
<span data-ttu-id="d1796-103">定义的安全功能[ \<basicHttpBinding >](../../../../../docs/framework/configure-apps/file-schema/wcf/basichttpbinding.md)。</span><span class="sxs-lookup"><span data-stu-id="d1796-103">Defines the security capabilities of the [\<basicHttpBinding>](../../../../../docs/framework/configure-apps/file-schema/wcf/basichttpbinding.md).</span></span>  
  
 <span data-ttu-id="d1796-104">\<系统。ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="d1796-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="d1796-105">\<绑定 ></span><span class="sxs-lookup"><span data-stu-id="d1796-105">\<bindings></span></span>  
<span data-ttu-id="d1796-106">\<netHttpBinding ></span><span class="sxs-lookup"><span data-stu-id="d1796-106">\<netHttpBinding></span></span>  
<span data-ttu-id="d1796-107">\<绑定 ></span><span class="sxs-lookup"><span data-stu-id="d1796-107">\<binding></span></span>  
<span data-ttu-id="d1796-108">\<安全 ></span><span class="sxs-lookup"><span data-stu-id="d1796-108">\<security></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d1796-109">语法</span><span class="sxs-lookup"><span data-stu-id="d1796-109">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="d1796-110">特性和元素</span><span class="sxs-lookup"><span data-stu-id="d1796-110">Attributes and Elements</span></span>  
 <span data-ttu-id="d1796-111">以下几节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="d1796-111">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="d1796-112">特性</span><span class="sxs-lookup"><span data-stu-id="d1796-112">Attributes</span></span>  
  
|<span data-ttu-id="d1796-113">特性</span><span class="sxs-lookup"><span data-stu-id="d1796-113">Attribute</span></span>|<span data-ttu-id="d1796-114">描述</span><span class="sxs-lookup"><span data-stu-id="d1796-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="d1796-115">mode</span><span class="sxs-lookup"><span data-stu-id="d1796-115">mode</span></span>|<span data-ttu-id="d1796-116">可选。</span><span class="sxs-lookup"><span data-stu-id="d1796-116">Optional.</span></span> <span data-ttu-id="d1796-117">指定所使用的安全类型。</span><span class="sxs-lookup"><span data-stu-id="d1796-117">Specifies the type of security that is used.</span></span> <span data-ttu-id="d1796-118">默认值为 `None`。</span><span class="sxs-lookup"><span data-stu-id="d1796-118">The default is `None`.</span></span> <span data-ttu-id="d1796-119">此属性的类型是<!--zz <xref:System.ServiceModel.NetHttpSecurityMode> --> `System.ServiceModel.NetHttpSecurityMode`。</span><span class="sxs-lookup"><span data-stu-id="d1796-119">This attribute is of type <!--zz <xref:System.ServiceModel.NetHttpSecurityMode> -->`System.ServiceModel.NetHttpSecurityMode`.</span></span>|
  
## <a name="mode-attribute"></a><span data-ttu-id="d1796-120">mode 属性</span><span class="sxs-lookup"><span data-stu-id="d1796-120">mode Attribute</span></span>  
  
|<span data-ttu-id="d1796-121">值</span><span class="sxs-lookup"><span data-stu-id="d1796-121">Value</span></span>|<span data-ttu-id="d1796-122">描述</span><span class="sxs-lookup"><span data-stu-id="d1796-122">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="d1796-123">无</span><span class="sxs-lookup"><span data-stu-id="d1796-123">None</span></span>|<span data-ttu-id="d1796-124">的在传输过程中不是安全消息。</span><span class="sxs-lookup"><span data-stu-id="d1796-124">-   Messages are not secured during transfer.</span></span>|  
|<span data-ttu-id="d1796-125">传输</span><span class="sxs-lookup"><span data-stu-id="d1796-125">Transport</span></span>|<span data-ttu-id="d1796-126">使用 HTTPS 传输提供安全性。</span><span class="sxs-lookup"><span data-stu-id="d1796-126">Security is provided using HTTPS transport.</span></span> <span data-ttu-id="d1796-127">用 HTTPS 保证 SOAP 消息的安全。</span><span class="sxs-lookup"><span data-stu-id="d1796-127">The SOAP messages are secured using HTTPS.</span></span> <span data-ttu-id="d1796-128">使用服务的 X.509 证书向客户端对服务进行身份验证。</span><span class="sxs-lookup"><span data-stu-id="d1796-128">The service is authenticated to the client using the service's X.509 certificate.</span></span> <span data-ttu-id="d1796-129">使用所提供的 ClientCredentialType 对客户端进行身份验证。</span><span class="sxs-lookup"><span data-stu-id="d1796-129">The client is authenticated using the ClientCredentialType supplied.</span></span>|  
|<span data-ttu-id="d1796-130">消息</span><span class="sxs-lookup"><span data-stu-id="d1796-130">Message</span></span>|<span data-ttu-id="d1796-131">使用 SOAP 消息安全提供安全性。</span><span class="sxs-lookup"><span data-stu-id="d1796-131">Security is provided using SOAP message security.</span></span> <span data-ttu-id="d1796-132">默认情况下，将对正文进行加密和签名。</span><span class="sxs-lookup"><span data-stu-id="d1796-132">By default, the body is encrypted and signed.</span></span> <span data-ttu-id="d1796-133">对于此绑定，系统要求向带外客户端提供服务器证书。</span><span class="sxs-lookup"><span data-stu-id="d1796-133">For this binding, the system requires that the server certificate be provided to the client out of band.</span></span> <span data-ttu-id="d1796-134">此绑定仅有的有效 `ClientCredentialType` 为 `Certificate`。</span><span class="sxs-lookup"><span data-stu-id="d1796-134">The only valid `ClientCredentialType` for this binding is `Certificate`.</span></span>|  
|<span data-ttu-id="d1796-135">TransportWithMessageCredential</span><span class="sxs-lookup"><span data-stu-id="d1796-135">TransportWithMessageCredential</span></span>|<span data-ttu-id="d1796-136">完整性、保密性和服务器身份验证由传输安全来提供。</span><span class="sxs-lookup"><span data-stu-id="d1796-136">Integrity, confidentiality and server authentication are provided by transport security.</span></span> <span data-ttu-id="d1796-137">客户端身份验证采用 SOAP 消息安全方式提供。</span><span class="sxs-lookup"><span data-stu-id="d1796-137">Client authentication is provided by means of SOAP message security.</span></span> <span data-ttu-id="d1796-138">如果要使用用户名/密码对用户进行身份验证，并且存在用于保护消息传输的现有 HTTP 部署，则适用此模式。</span><span class="sxs-lookup"><span data-stu-id="d1796-138">This mode is relevant when the user is authenticating using username/password and there is an existing HTTP deployment for securing message transfer.</span></span>|  
|<span data-ttu-id="d1796-139">TransportCredentialOnly</span><span class="sxs-lookup"><span data-stu-id="d1796-139">TransportCredentialOnly</span></span>|<span data-ttu-id="d1796-140">此模式并不提供消息的完整性和保密性，</span><span class="sxs-lookup"><span data-stu-id="d1796-140">This mode does not provide message integrity and confidentiality.</span></span> <span data-ttu-id="d1796-141">而是提供基于 http 的客户端身份验证。</span><span class="sxs-lookup"><span data-stu-id="d1796-141">It provides http-based client authentication.</span></span> <span data-ttu-id="d1796-142">使用此模式时应当小心。</span><span class="sxs-lookup"><span data-stu-id="d1796-142">This mode should be used with caution.</span></span> <span data-ttu-id="d1796-143">在通过其他方式（如 IPSec）提供传输安全并且 [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)] 基础结构只提供客户端身份验证的环境中，应该使用此模式。</span><span class="sxs-lookup"><span data-stu-id="d1796-143">It should be used in environments where the transport security is being provided by other means (such as IPSec) and only client authentication is provided by the [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)] infrastructure.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="d1796-144">子元素</span><span class="sxs-lookup"><span data-stu-id="d1796-144">Child Elements</span></span>  
  
|<span data-ttu-id="d1796-145">元素</span><span class="sxs-lookup"><span data-stu-id="d1796-145">Element</span></span>|<span data-ttu-id="d1796-146">描述</span><span class="sxs-lookup"><span data-stu-id="d1796-146">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="d1796-147">\<传输 ></span><span class="sxs-lookup"><span data-stu-id="d1796-147">\<transport></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/transport-of-nethttpbinding.md)|<span data-ttu-id="d1796-148">定义基本 HTTP 服务的传输安全设置。</span><span class="sxs-lookup"><span data-stu-id="d1796-148">Defines the transport security settings for a basic HTTP service.</span></span> <span data-ttu-id="d1796-149">此元素与 <xref:System.ServiceModel.HttpTransportSecurity> 相对应。</span><span class="sxs-lookup"><span data-stu-id="d1796-149">This element corresponds to <xref:System.ServiceModel.HttpTransportSecurity>.</span></span>|  
|[<span data-ttu-id="d1796-150">\<消息 ></span><span class="sxs-lookup"><span data-stu-id="d1796-150">\<message></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/message-of-nethttpbinding.md)|<span data-ttu-id="d1796-151">定义基本 HTTP 服务的消息安全设置。</span><span class="sxs-lookup"><span data-stu-id="d1796-151">Defines the message security settings for a basic HTTP service.</span></span> <span data-ttu-id="d1796-152">此元素对应于<!--zz <xref:System.ServiceModel.NetHttpMessageSecurity> --> `System.ServiceModel.NetHttpMessageSecurity`。</span><span class="sxs-lookup"><span data-stu-id="d1796-152">This element corresponds to <!--zz <xref:System.ServiceModel.NetHttpMessageSecurity> --> `System.ServiceModel.NetHttpMessageSecurity`.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="d1796-153">父元素</span><span class="sxs-lookup"><span data-stu-id="d1796-153">Parent Elements</span></span>  
  
|<span data-ttu-id="d1796-154">元素</span><span class="sxs-lookup"><span data-stu-id="d1796-154">Element</span></span>|<span data-ttu-id="d1796-155">描述</span><span class="sxs-lookup"><span data-stu-id="d1796-155">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="d1796-156">绑定</span><span class="sxs-lookup"><span data-stu-id="d1796-156">binding</span></span>|<span data-ttu-id="d1796-157">绑定元素[ \<basicHttpBinding >](../../../../../docs/framework/configure-apps/file-schema/wcf/basichttpbinding.md)。</span><span class="sxs-lookup"><span data-stu-id="d1796-157">The binding element of the [\<basicHttpBinding>](../../../../../docs/framework/configure-apps/file-schema/wcf/basichttpbinding.md).</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="d1796-158">备注</span><span class="sxs-lookup"><span data-stu-id="d1796-158">Remarks</span></span>  
 <span data-ttu-id="d1796-159">默认情况下，不会对 SOAP 消息进行保护，也不会对客户端进行身份验证。</span><span class="sxs-lookup"><span data-stu-id="d1796-159">By default, the SOAP message is not secured and the client is not authenticated.</span></span> <span data-ttu-id="d1796-160">使用此元素，您可以配置 `netHttpBinding` 元素的其他安全设置。</span><span class="sxs-lookup"><span data-stu-id="d1796-160">This element enables you to configure additional security settings for the `netHttpBinding` element.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d1796-161">请参阅</span><span class="sxs-lookup"><span data-stu-id="d1796-161">See Also</span></span>  
 <xref:System.ServiceModel.NetHttpBinding.Security%2A>  
 <span data-ttu-id="d1796-162"><xref:System.ServiceModel.Configuration.NetHttpBindingElement.Security%2A></span><span class="sxs-lookup"><span data-stu-id="d1796-162"><xref:System.ServiceModel.Configuration.NetHttpBindingElement.Security%2A></span></span>    
 [<span data-ttu-id="d1796-163">保护服务和客户端的安全</span><span class="sxs-lookup"><span data-stu-id="d1796-163">Securing Services and Clients</span></span>](../../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)  
 [<span data-ttu-id="d1796-164">选择凭据类型</span><span class="sxs-lookup"><span data-stu-id="d1796-164">Selecting a Credential Type</span></span>](../../../../../docs/framework/wcf/feature-details/selecting-a-credential-type.md)  
 [<span data-ttu-id="d1796-165">绑定</span><span class="sxs-lookup"><span data-stu-id="d1796-165">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)  
 [<span data-ttu-id="d1796-166">配置系统提供的绑定</span><span class="sxs-lookup"><span data-stu-id="d1796-166">Configuring System-Provided Bindings</span></span>](../../../../../docs/framework/wcf/feature-details/configuring-system-provided-bindings.md)  
 [<span data-ttu-id="d1796-167">使用绑定来配置 Windows Communication Foundation 服务和客户端</span><span class="sxs-lookup"><span data-stu-id="d1796-167">Using Bindings to Configure Windows Communication Foundation Services and Clients</span></span>](http://msdn.microsoft.com/en-us/bd8b277b-932f-472f-a42a-b02bb5257dfb)  
 [<span data-ttu-id="d1796-168">\<绑定 ></span><span class="sxs-lookup"><span data-stu-id="d1796-168">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)
