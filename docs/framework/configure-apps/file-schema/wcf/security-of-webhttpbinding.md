---
title: <security> 的 <webHttpBinding>
ms.date: 03/30/2017
ms.assetid: 727cf3d2-6f56-48ad-a59f-ba423edb9c83
ms.openlocfilehash: 806cf8524ed1a1439ca85a4b918e8e486e5dc94b
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2019
ms.locfileid: "69936588"
---
# <a name="security-of-webhttpbinding"></a><span data-ttu-id="3b5aa-102">\<webHttpBinding 的\<安全 > ></span><span class="sxs-lookup"><span data-stu-id="3b5aa-102">\<security> of \<webHttpBinding></span></span>
<span data-ttu-id="3b5aa-103">指定配置了[ \<webHttpBinding >](webhttpbinding.md)的终结点的安全要求。</span><span class="sxs-lookup"><span data-stu-id="3b5aa-103">Specifies the security requirements for an endpoint configured with a [\<webHttpBinding>](webhttpbinding.md).</span></span>  
  
 <span data-ttu-id="3b5aa-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="3b5aa-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="3b5aa-105">\<bindings></span><span class="sxs-lookup"><span data-stu-id="3b5aa-105">\<bindings></span></span>  
<span data-ttu-id="3b5aa-106">\<webHttpBinding></span><span class="sxs-lookup"><span data-stu-id="3b5aa-106">\<webHttpBinding></span></span>  
<span data-ttu-id="3b5aa-107">\<绑定 ></span><span class="sxs-lookup"><span data-stu-id="3b5aa-107">\<binding></span></span>  
<span data-ttu-id="3b5aa-108">\<安全 ></span><span class="sxs-lookup"><span data-stu-id="3b5aa-108">\<security></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3b5aa-109">语法</span><span class="sxs-lookup"><span data-stu-id="3b5aa-109">Syntax</span></span>  
  
```xml  
<system.ServiceModel>
  <bindings>
    <webHttpBinding>
      <binding name = "String">
        <security mode="None/Transport/TransportCredentialOnly">
          <transport clientCredentialType="Basic/Certificate/Digest/None/Ntlm/Windows"
                     proxyCredentialType="Basic/Digest/None/Ntlm/Windows"
                     realm="String" />
        </security>
      </binding>
    </webHttpBinding>
  </bindings>
</system.ServiceModel>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="3b5aa-110">特性和元素</span><span class="sxs-lookup"><span data-stu-id="3b5aa-110">Attributes and Elements</span></span>  
 <span data-ttu-id="3b5aa-111">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="3b5aa-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="3b5aa-112">特性</span><span class="sxs-lookup"><span data-stu-id="3b5aa-112">Attributes</span></span>  
  
|<span data-ttu-id="3b5aa-113">特性</span><span class="sxs-lookup"><span data-stu-id="3b5aa-113">Attribute</span></span>|<span data-ttu-id="3b5aa-114">描述</span><span class="sxs-lookup"><span data-stu-id="3b5aa-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="3b5aa-115">mode</span><span class="sxs-lookup"><span data-stu-id="3b5aa-115">mode</span></span>|<span data-ttu-id="3b5aa-116">指定终结点是使用传输级安全模式还是不使用安全模式。</span><span class="sxs-lookup"><span data-stu-id="3b5aa-116">Specifies whether transport-level security or no security is used by an endpoint.</span></span> <span data-ttu-id="3b5aa-117">默认值为 `None`。</span><span class="sxs-lookup"><span data-stu-id="3b5aa-117">The default is `None`.</span></span> <span data-ttu-id="3b5aa-118">此属性的类型为 <xref:System.ServiceModel.WebHttpSecurityMode>。</span><span class="sxs-lookup"><span data-stu-id="3b5aa-118">This attribute is of type <xref:System.ServiceModel.WebHttpSecurityMode>.</span></span>|  
  
## <a name="mode-attribute"></a><span data-ttu-id="3b5aa-119">Mode 属性</span><span class="sxs-lookup"><span data-stu-id="3b5aa-119">Mode Attribute</span></span>  
  
|<span data-ttu-id="3b5aa-120">值</span><span class="sxs-lookup"><span data-stu-id="3b5aa-120">Value</span></span>|<span data-ttu-id="3b5aa-121">描述</span><span class="sxs-lookup"><span data-stu-id="3b5aa-121">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="3b5aa-122">无</span><span class="sxs-lookup"><span data-stu-id="3b5aa-122">None</span></span>|<span data-ttu-id="3b5aa-123">禁用安全性。</span><span class="sxs-lookup"><span data-stu-id="3b5aa-123">Security is disabled.</span></span>|  
|<span data-ttu-id="3b5aa-124">传输</span><span class="sxs-lookup"><span data-stu-id="3b5aa-124">Transport</span></span>|<span data-ttu-id="3b5aa-125">使用 HTTPS 提供安全性。</span><span class="sxs-lookup"><span data-stu-id="3b5aa-125">Security is provided using HTTPS.</span></span> <span data-ttu-id="3b5aa-126">此服务需要使用 SSL 证书进行配置。</span><span class="sxs-lookup"><span data-stu-id="3b5aa-126">The service needs to be configured with SSL certificates.</span></span> <span data-ttu-id="3b5aa-127">消息使用 HTTPS 获得全面保护，而且客户端使用服务的 SSL 证书对服务进行身份验证。</span><span class="sxs-lookup"><span data-stu-id="3b5aa-127">The message is entirely secured using HTTPS and the service is authenticated by the client using the service’s SSL certificate.</span></span> <span data-ttu-id="3b5aa-128">客户端身份验证通过`ClientCredentialType` [ \<传输 >](transport-of-webhttpbinding.md)的属性进行控制。</span><span class="sxs-lookup"><span data-stu-id="3b5aa-128">The client authentication is controlled through the `ClientCredentialType` attribute of the [\<transport>](transport-of-webhttpbinding.md).</span></span>|  
|<span data-ttu-id="3b5aa-129">TransportCredentialOnly</span><span class="sxs-lookup"><span data-stu-id="3b5aa-129">TransportCredentialOnly</span></span>|<span data-ttu-id="3b5aa-130">此模式并不提供消息的完整性和保密性，</span><span class="sxs-lookup"><span data-stu-id="3b5aa-130">This mode does not provide message integrity and confidentiality.</span></span> <span data-ttu-id="3b5aa-131">而是提供基于 HTTP 的客户端身份验证。</span><span class="sxs-lookup"><span data-stu-id="3b5aa-131">It provides HTTP-based client authentication.</span></span> <span data-ttu-id="3b5aa-132">使用此模式时应当小心。</span><span class="sxs-lookup"><span data-stu-id="3b5aa-132">This mode should be used with caution.</span></span> <span data-ttu-id="3b5aa-133">在通过其他方式 (如 IPSec) 提供传输安全, 并且 WCF 基础结构仅提供客户端身份验证的环境中, 应使用此方法。</span><span class="sxs-lookup"><span data-stu-id="3b5aa-133">It should be used in environments where the transport security is being provided by other means (such as IPSec) and only client authentication is provided by the WCF infrastructure.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="3b5aa-134">子元素</span><span class="sxs-lookup"><span data-stu-id="3b5aa-134">Child Elements</span></span>  
  
|<span data-ttu-id="3b5aa-135">元素</span><span class="sxs-lookup"><span data-stu-id="3b5aa-135">Element</span></span>|<span data-ttu-id="3b5aa-136">描述</span><span class="sxs-lookup"><span data-stu-id="3b5aa-136">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="3b5aa-137">\<transport></span><span class="sxs-lookup"><span data-stu-id="3b5aa-137">\<transport></span></span>](transport-of-webhttpbinding.md)|<span data-ttu-id="3b5aa-138">定义传输安全设置。</span><span class="sxs-lookup"><span data-stu-id="3b5aa-138">Defines the transport security settings.</span></span> <span data-ttu-id="3b5aa-139">此元素与 <xref:System.ServiceModel.Configuration.HttpTransportSecurityElement> 类型相对应。</span><span class="sxs-lookup"><span data-stu-id="3b5aa-139">This element corresponds to the <xref:System.ServiceModel.Configuration.HttpTransportSecurityElement> type.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="3b5aa-140">父元素</span><span class="sxs-lookup"><span data-stu-id="3b5aa-140">Parent Elements</span></span>  
  
|<span data-ttu-id="3b5aa-141">元素</span><span class="sxs-lookup"><span data-stu-id="3b5aa-141">Element</span></span>|<span data-ttu-id="3b5aa-142">描述</span><span class="sxs-lookup"><span data-stu-id="3b5aa-142">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="3b5aa-143">\<webHttpBinding></span><span class="sxs-lookup"><span data-stu-id="3b5aa-143">\<webHttpBinding></span></span>](webhttpbinding.md)|<span data-ttu-id="3b5aa-144">一个绑定元素, 用于为响应 HTTP 请求 (而不是 SOAP 消息) 的 Windows Communication Foundation (WCF) Web 服务配置终结点。</span><span class="sxs-lookup"><span data-stu-id="3b5aa-144">A binding element that is used to configure endpoints for Windows Communication Foundation (WCF) Web services that respond to HTTP requests instead of SOAP messages.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="3b5aa-145">请参阅</span><span class="sxs-lookup"><span data-stu-id="3b5aa-145">See also</span></span>

- <xref:System.ServiceModel.Configuration.WebHttpBindingElement>
- <xref:System.ServiceModel.Configuration.WSHttpSecurityElement>
- <xref:System.ServiceModel.WebHttpBinding.Security%2A>
- <xref:System.ServiceModel.Configuration.WebHttpBindingElement.Security%2A>
- <xref:System.ServiceModel.WebHttpSecurity>
- [<span data-ttu-id="3b5aa-146">保护服务和客户端的安全</span><span class="sxs-lookup"><span data-stu-id="3b5aa-146">Securing Services and Clients</span></span>](../../../wcf/feature-details/securing-services-and-clients.md)
- [<span data-ttu-id="3b5aa-147">选择凭据类型</span><span class="sxs-lookup"><span data-stu-id="3b5aa-147">Selecting a Credential Type</span></span>](../../../wcf/feature-details/selecting-a-credential-type.md)
- [<span data-ttu-id="3b5aa-148">绑定</span><span class="sxs-lookup"><span data-stu-id="3b5aa-148">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="3b5aa-149">配置系统提供的绑定</span><span class="sxs-lookup"><span data-stu-id="3b5aa-149">Configuring System-Provided Bindings</span></span>](../../../wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="3b5aa-150">使用绑定配置服务和客户端</span><span class="sxs-lookup"><span data-stu-id="3b5aa-150">Using Bindings to Configure Services and Clients</span></span>](../../../wcf/using-bindings-to-configure-services-and-clients.md)
- [<span data-ttu-id="3b5aa-151">\<binding></span><span class="sxs-lookup"><span data-stu-id="3b5aa-151">\<binding></span></span>](../../../misc/binding.md)
- [<span data-ttu-id="3b5aa-152">WCF Web HTTP 编程模型</span><span class="sxs-lookup"><span data-stu-id="3b5aa-152">WCF Web HTTP Programming Model</span></span>](../../../wcf/feature-details/wcf-web-http-programming-model.md)
