---
title: "&lt;webHttpBinding&gt; 的 &lt;security&gt;"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 727cf3d2-6f56-48ad-a59f-ba423edb9c83
caps.latest.revision: "9"
author: BrucePerlerMS
ms.author: bruceper
manager: mbaldwin
ms.workload: dotnet
ms.openlocfilehash: 3afd67e7f2d42cec458db7919529e09e4607f1ca
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="ltsecuritygt-of-ltwebhttpbindinggt"></a><span data-ttu-id="c40a9-102">&lt;webHttpBinding&gt; 的 &lt;security&gt;</span><span class="sxs-lookup"><span data-stu-id="c40a9-102">&lt;security&gt; of &lt;webHttpBinding&gt;</span></span>
<span data-ttu-id="c40a9-103">指定与配置的终结点的安全要求[ \<wsHttpBinding >](../../../../../docs/framework/configure-apps/file-schema/wcf/wshttpbinding.md)。</span><span class="sxs-lookup"><span data-stu-id="c40a9-103">Specifies the security requirements for an endpoint configured with a [\<wsHttpBinding>](../../../../../docs/framework/configure-apps/file-schema/wcf/wshttpbinding.md).</span></span>  
  
 <span data-ttu-id="c40a9-104">\<系统。ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="c40a9-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="c40a9-105">\<绑定 ></span><span class="sxs-lookup"><span data-stu-id="c40a9-105">\<bindings></span></span>  
<span data-ttu-id="c40a9-106">\<webHttpBinding ></span><span class="sxs-lookup"><span data-stu-id="c40a9-106">\<webHttpBinding></span></span>  
<span data-ttu-id="c40a9-107">\<绑定 ></span><span class="sxs-lookup"><span data-stu-id="c40a9-107">\<binding></span></span>  
<span data-ttu-id="c40a9-108">\<安全 ></span><span class="sxs-lookup"><span data-stu-id="c40a9-108">\<security></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c40a9-109">语法</span><span class="sxs-lookup"><span data-stu-id="c40a9-109">Syntax</span></span>  
  
```xml  
<system.ServiceModel>  
    <bindings>  
        <webHttpBinding>  
            <binding name = "string">  
              <security mode="None/Transport/TransportCredentialOnly">  
                                    <transport clientCredentialType =   
                                     "Basic/Certificate/Digest/None/Ntlm/Windows"  
                                     proxyCredentialType="Basic/Digest/None/Ntlm/Windows"  
                                     realm="string" />  
              </security>  
        </webHttpBinding>  
    </bindings>  
</system.ServiceModel>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="c40a9-110">特性和元素</span><span class="sxs-lookup"><span data-stu-id="c40a9-110">Attributes and Elements</span></span>  
 <span data-ttu-id="c40a9-111">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="c40a9-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="c40a9-112">特性</span><span class="sxs-lookup"><span data-stu-id="c40a9-112">Attributes</span></span>  
  
|<span data-ttu-id="c40a9-113">特性</span><span class="sxs-lookup"><span data-stu-id="c40a9-113">Attribute</span></span>|<span data-ttu-id="c40a9-114">描述</span><span class="sxs-lookup"><span data-stu-id="c40a9-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="c40a9-115">mode</span><span class="sxs-lookup"><span data-stu-id="c40a9-115">mode</span></span>|<span data-ttu-id="c40a9-116">指定终结点是使用传输级安全模式还是不使用安全模式。</span><span class="sxs-lookup"><span data-stu-id="c40a9-116">Specifies whether transport-level security or no security is used by an endpoint.</span></span> <span data-ttu-id="c40a9-117">默认值为 `None`。</span><span class="sxs-lookup"><span data-stu-id="c40a9-117">The default is `None`.</span></span> <span data-ttu-id="c40a9-118">此属性的类型为 <xref:System.ServiceModel.WebHttpSecurityMode>。</span><span class="sxs-lookup"><span data-stu-id="c40a9-118">This attribute is of type <xref:System.ServiceModel.WebHttpSecurityMode>.</span></span>|  
  
## <a name="mode-attribute"></a><span data-ttu-id="c40a9-119">Mode 属性</span><span class="sxs-lookup"><span data-stu-id="c40a9-119">Mode Attribute</span></span>  
  
|<span data-ttu-id="c40a9-120">值</span><span class="sxs-lookup"><span data-stu-id="c40a9-120">Value</span></span>|<span data-ttu-id="c40a9-121">描述</span><span class="sxs-lookup"><span data-stu-id="c40a9-121">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="c40a9-122">无</span><span class="sxs-lookup"><span data-stu-id="c40a9-122">None</span></span>|<span data-ttu-id="c40a9-123">禁用安全性。</span><span class="sxs-lookup"><span data-stu-id="c40a9-123">Security is disabled.</span></span>|  
|<span data-ttu-id="c40a9-124">传输</span><span class="sxs-lookup"><span data-stu-id="c40a9-124">Transport</span></span>|<span data-ttu-id="c40a9-125">使用 HTTPS 提供安全性。</span><span class="sxs-lookup"><span data-stu-id="c40a9-125">Security is provided using HTTPS.</span></span> <span data-ttu-id="c40a9-126">此服务需要使用 SSL 证书进行配置。</span><span class="sxs-lookup"><span data-stu-id="c40a9-126">The service needs to be configured with SSL certificates.</span></span> <span data-ttu-id="c40a9-127">消息使用 HTTPS 获得全面保护，而且客户端使用服务的 SSL 证书对服务进行身份验证。</span><span class="sxs-lookup"><span data-stu-id="c40a9-127">The message is entirely secured using HTTPS and the service is authenticated by the client using the service’s SSL certificate.</span></span> <span data-ttu-id="c40a9-128">可以通过控制客户端身份验证的`ClientCredentialType`属性[\<传输 >](../../../../../docs/framework/configure-apps/file-schema/wcf/transport-of-webhttpbinding.md)。</span><span class="sxs-lookup"><span data-stu-id="c40a9-128">The client authentication is controlled through the `ClientCredentialType` attribute of the [\<transport>](../../../../../docs/framework/configure-apps/file-schema/wcf/transport-of-webhttpbinding.md).</span></span>|  
|<span data-ttu-id="c40a9-129">TransportCredentialOnly</span><span class="sxs-lookup"><span data-stu-id="c40a9-129">TransportCredentialOnly</span></span>|<span data-ttu-id="c40a9-130">此模式并不提供消息的完整性和保密性，</span><span class="sxs-lookup"><span data-stu-id="c40a9-130">This mode does not provide message integrity and confidentiality.</span></span> <span data-ttu-id="c40a9-131">而是提供基于 HTTP 的客户端身份验证。</span><span class="sxs-lookup"><span data-stu-id="c40a9-131">It provides HTTP-based client authentication.</span></span> <span data-ttu-id="c40a9-132">使用此模式时应当小心。</span><span class="sxs-lookup"><span data-stu-id="c40a9-132">This mode should be used with caution.</span></span> <span data-ttu-id="c40a9-133">在通过其他方式（如 IPSec）提供传输安全并且 [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)] 基础结构只提供客户端身份验证的环境中，应该使用此模式。</span><span class="sxs-lookup"><span data-stu-id="c40a9-133">It should be used in environments where the transport security is being provided by other means (such as IPSec) and only client authentication is provided by the [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)] infrastructure.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="c40a9-134">子元素</span><span class="sxs-lookup"><span data-stu-id="c40a9-134">Child Elements</span></span>  
  
|<span data-ttu-id="c40a9-135">元素</span><span class="sxs-lookup"><span data-stu-id="c40a9-135">Element</span></span>|<span data-ttu-id="c40a9-136">描述</span><span class="sxs-lookup"><span data-stu-id="c40a9-136">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="c40a9-137">\<传输 ></span><span class="sxs-lookup"><span data-stu-id="c40a9-137">\<transport></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/transport-of-webhttpbinding.md)|<span data-ttu-id="c40a9-138">定义传输安全设置。</span><span class="sxs-lookup"><span data-stu-id="c40a9-138">Defines the transport security settings.</span></span> <span data-ttu-id="c40a9-139">此元素与 <xref:System.ServiceModel.Configuration.HttpTransportSecurityElement> 类型相对应。</span><span class="sxs-lookup"><span data-stu-id="c40a9-139">This element corresponds to the <xref:System.ServiceModel.Configuration.HttpTransportSecurityElement> type.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="c40a9-140">父元素</span><span class="sxs-lookup"><span data-stu-id="c40a9-140">Parent Elements</span></span>  
  
|<span data-ttu-id="c40a9-141">元素</span><span class="sxs-lookup"><span data-stu-id="c40a9-141">Element</span></span>|<span data-ttu-id="c40a9-142">描述</span><span class="sxs-lookup"><span data-stu-id="c40a9-142">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="c40a9-143">\<webHttpBinding ></span><span class="sxs-lookup"><span data-stu-id="c40a9-143">\<webHttpBinding></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/webhttpbinding.md)|<span data-ttu-id="c40a9-144">一个绑定元素，可用于为响应 HTTP 请求（而不是 SOAP 消息）的 [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)] Web 服务配置终结点。</span><span class="sxs-lookup"><span data-stu-id="c40a9-144">A binding element that is used to configure endpoints for [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)] Web services that respond to HTTP requests instead of SOAP messages.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="c40a9-145">请参阅</span><span class="sxs-lookup"><span data-stu-id="c40a9-145">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.WebHttpBindingElement>  
 <xref:System.ServiceModel.Configuration.WSHttpSecurityElement>  
 <xref:System.ServiceModel.WebHttpBinding.Security%2A>  
 <xref:System.ServiceModel.Configuration.WebHttpBindingElement.Security%2A>  
 <xref:System.ServiceModel.WebHttpSecurity>  
 [<span data-ttu-id="c40a9-146">保护服务和客户端的安全</span><span class="sxs-lookup"><span data-stu-id="c40a9-146">Securing Services and Clients</span></span>](../../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)  
 [<span data-ttu-id="c40a9-147">选择凭据类型</span><span class="sxs-lookup"><span data-stu-id="c40a9-147">Selecting a Credential Type</span></span>](../../../../../docs/framework/wcf/feature-details/selecting-a-credential-type.md)  
 [<span data-ttu-id="c40a9-148">绑定</span><span class="sxs-lookup"><span data-stu-id="c40a9-148">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)  
 [<span data-ttu-id="c40a9-149">配置系统提供的绑定</span><span class="sxs-lookup"><span data-stu-id="c40a9-149">Configuring System-Provided Bindings</span></span>](../../../../../docs/framework/wcf/feature-details/configuring-system-provided-bindings.md)  
 [<span data-ttu-id="c40a9-150">使用绑定来配置 Windows Communication Foundation 服务和客户端</span><span class="sxs-lookup"><span data-stu-id="c40a9-150">Using Bindings to Configure Windows Communication Foundation Services and Clients</span></span>](http://msdn.microsoft.com/en-us/bd8b277b-932f-472f-a42a-b02bb5257dfb)  
 [<span data-ttu-id="c40a9-151">\<绑定 ></span><span class="sxs-lookup"><span data-stu-id="c40a9-151">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)  
 [<span data-ttu-id="c40a9-152">WCF Web HTTP 编程模型</span><span class="sxs-lookup"><span data-stu-id="c40a9-152">WCF Web HTTP Programming Model</span></span>](../../../../../docs/framework/wcf/feature-details/wcf-web-http-programming-model.md)
