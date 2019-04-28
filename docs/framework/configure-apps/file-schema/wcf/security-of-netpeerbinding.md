---
title: <security> 的 <netPeerBinding>
ms.date: 03/30/2017
ms.assetid: 1ef40d8c-f903-4426-9b08-da81462766d8
ms.openlocfilehash: 6348bc6f6c0d3a9656fbe57bf71f531d1287a949
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "61670477"
---
# <a name="security-of-netpeerbinding"></a><span data-ttu-id="16b10-102">\<security> of \<netPeerBinding></span><span class="sxs-lookup"><span data-stu-id="16b10-102">\<security> of \<netPeerBinding></span></span>
<span data-ttu-id="16b10-103">定义的安全设置[ \<netPeerTcpBinding >](../../../../../docs/framework/configure-apps/file-schema/wcf/netpeertcpbinding.md)，包括身份验证的类型使用，安全使用消息传输。</span><span class="sxs-lookup"><span data-stu-id="16b10-103">Defines the security settings of the [\<netPeerTcpBinding>](../../../../../docs/framework/configure-apps/file-schema/wcf/netpeertcpbinding.md), including the type of authentication used and the security used for the message transport.</span></span>  
  
 <span data-ttu-id="16b10-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="16b10-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="16b10-105">\<bindings></span><span class="sxs-lookup"><span data-stu-id="16b10-105">\<bindings></span></span>  
<span data-ttu-id="16b10-106">\<netPeerBinding></span><span class="sxs-lookup"><span data-stu-id="16b10-106">\<netPeerBinding></span></span>  
<span data-ttu-id="16b10-107">\<binding></span><span class="sxs-lookup"><span data-stu-id="16b10-107">\<binding></span></span>  
<span data-ttu-id="16b10-108">\<安全 ></span><span class="sxs-lookup"><span data-stu-id="16b10-108">\<security></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="16b10-109">语法</span><span class="sxs-lookup"><span data-stu-id="16b10-109">Syntax</span></span>  
  
```xml  
<netPeerBinding>
  <binding>
    <security mode="Message/None/Transport//TransportWithMessageCredential">
      <transport credentialType="Certificate/Password" />
    </security>
  </binding>
</netPeerBinding>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="16b10-110">特性和元素</span><span class="sxs-lookup"><span data-stu-id="16b10-110">Attributes and Elements</span></span>  
 <span data-ttu-id="16b10-111">以下几节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="16b10-111">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="16b10-112">特性</span><span class="sxs-lookup"><span data-stu-id="16b10-112">Attributes</span></span>  
  
|<span data-ttu-id="16b10-113">特性</span><span class="sxs-lookup"><span data-stu-id="16b10-113">Attribute</span></span>|<span data-ttu-id="16b10-114">描述</span><span class="sxs-lookup"><span data-stu-id="16b10-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="16b10-115">mode</span><span class="sxs-lookup"><span data-stu-id="16b10-115">mode</span></span>|<span data-ttu-id="16b10-116">可选。</span><span class="sxs-lookup"><span data-stu-id="16b10-116">Optional.</span></span> <span data-ttu-id="16b10-117">指定采用此绑定配置的对等端所使用的安全类型。</span><span class="sxs-lookup"><span data-stu-id="16b10-117">Specifies the type of security used by peers configured with this binding.</span></span> <span data-ttu-id="16b10-118">默认值为 `Message`。</span><span class="sxs-lookup"><span data-stu-id="16b10-118">The default value is `Message`.</span></span> <span data-ttu-id="16b10-119">此属性的类型为 <xref:System.ServiceModel.SecurityMode>。</span><span class="sxs-lookup"><span data-stu-id="16b10-119">This attribute is of type <xref:System.ServiceModel.SecurityMode>.</span></span>|  
  
## <a name="mode-attribute"></a><span data-ttu-id="16b10-120">mode 属性</span><span class="sxs-lookup"><span data-stu-id="16b10-120">mode Attribute</span></span>  
  
|<span data-ttu-id="16b10-121">“值”</span><span class="sxs-lookup"><span data-stu-id="16b10-121">Value</span></span>|<span data-ttu-id="16b10-122">描述</span><span class="sxs-lookup"><span data-stu-id="16b10-122">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="16b10-123">消息</span><span class="sxs-lookup"><span data-stu-id="16b10-123">Message</span></span>|<span data-ttu-id="16b10-124">SOAP 安全提供身份验证、完整性和保密性。</span><span class="sxs-lookup"><span data-stu-id="16b10-124">SOAP security provides authentication, integrity and confidentiality.</span></span>|  
|<span data-ttu-id="16b10-125">None</span><span class="sxs-lookup"><span data-stu-id="16b10-125">None</span></span>|<span data-ttu-id="16b10-126">禁用安全性。</span><span class="sxs-lookup"><span data-stu-id="16b10-126">Security is disabled.</span></span>|  
|<span data-ttu-id="16b10-127">传输</span><span class="sxs-lookup"><span data-stu-id="16b10-127">Transport</span></span>|<span data-ttu-id="16b10-128">使用 HTTPS 提供安全性。</span><span class="sxs-lookup"><span data-stu-id="16b10-128">Security is provided using HTTPS.</span></span>|  
|<span data-ttu-id="16b10-129">TransportWithMessageCredential</span><span class="sxs-lookup"><span data-stu-id="16b10-129">TransportWithMessageCredential</span></span>|<span data-ttu-id="16b10-130">HTTPS 提供身份验证和保密性。</span><span class="sxs-lookup"><span data-stu-id="16b10-130">HTTPS provides authentication and confidentiality.</span></span> <span data-ttu-id="16b10-131">SOAP 消息提供丰富的凭据类型。</span><span class="sxs-lookup"><span data-stu-id="16b10-131">SOAP messages provide rich credential types.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="16b10-132">子元素</span><span class="sxs-lookup"><span data-stu-id="16b10-132">Child Elements</span></span>  
  
|<span data-ttu-id="16b10-133">元素</span><span class="sxs-lookup"><span data-stu-id="16b10-133">Element</span></span>|<span data-ttu-id="16b10-134">描述</span><span class="sxs-lookup"><span data-stu-id="16b10-134">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="16b10-135">\<transport></span><span class="sxs-lookup"><span data-stu-id="16b10-135">\<transport></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/transport-of-netpeertcpbinding.md)|<span data-ttu-id="16b10-136">定义采用此绑定配置的对等端所发送的安全消息的传输类型。</span><span class="sxs-lookup"><span data-stu-id="16b10-136">Defines the transport type for secured messages sent by peers configured with this binding.</span></span> <span data-ttu-id="16b10-137">此元素的类型为 <xref:System.ServiceModel.Configuration.PeerTransportSecurityElement>。</span><span class="sxs-lookup"><span data-stu-id="16b10-137">This element is of type <xref:System.ServiceModel.Configuration.PeerTransportSecurityElement>.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="16b10-138">父元素</span><span class="sxs-lookup"><span data-stu-id="16b10-138">Parent Elements</span></span>  
  
|<span data-ttu-id="16b10-139">元素</span><span class="sxs-lookup"><span data-stu-id="16b10-139">Element</span></span>|<span data-ttu-id="16b10-140">描述</span><span class="sxs-lookup"><span data-stu-id="16b10-140">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="16b10-141">\<binding></span><span class="sxs-lookup"><span data-stu-id="16b10-141">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)|<span data-ttu-id="16b10-142">定义的所有绑定功能[ \<netPeerTcpBinding >](../../../../../docs/framework/configure-apps/file-schema/wcf/netpeertcpbinding.md)。</span><span class="sxs-lookup"><span data-stu-id="16b10-142">Defines all binding capabilities of the [\<netPeerTcpBinding>](../../../../../docs/framework/configure-apps/file-schema/wcf/netpeertcpbinding.md).</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="16b10-143">备注</span><span class="sxs-lookup"><span data-stu-id="16b10-143">Remarks</span></span>  
 <span data-ttu-id="16b10-144">安全性可以是特定于消息的，也可以是特定于传输的。</span><span class="sxs-lookup"><span data-stu-id="16b10-144">Security can be either message- or transport-specific.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="16b10-145">请参阅</span><span class="sxs-lookup"><span data-stu-id="16b10-145">See also</span></span>

- <xref:System.ServiceModel.Configuration.PeerSecurityElement>
- <xref:System.ServiceModel.NetPeerTcpBinding.Security%2A>
- <xref:System.ServiceModel.Configuration.NetPeerTcpBindingElement.Security%2A>
- <xref:System.ServiceModel.PeerSecuritySettings>
- [<span data-ttu-id="16b10-146">保护服务和客户端的安全</span><span class="sxs-lookup"><span data-stu-id="16b10-146">Securing Services and Clients</span></span>](../../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)
- [<span data-ttu-id="16b10-147">选择凭据类型</span><span class="sxs-lookup"><span data-stu-id="16b10-147">Selecting a Credential Type</span></span>](../../../../../docs/framework/wcf/feature-details/selecting-a-credential-type.md)
- [<span data-ttu-id="16b10-148">绑定</span><span class="sxs-lookup"><span data-stu-id="16b10-148">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)
- [<span data-ttu-id="16b10-149">配置系统提供的绑定</span><span class="sxs-lookup"><span data-stu-id="16b10-149">Configuring System-Provided Bindings</span></span>](../../../../../docs/framework/wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="16b10-150">使用绑定配置服务和客户端</span><span class="sxs-lookup"><span data-stu-id="16b10-150">Using Bindings to Configure Services and Clients</span></span>](../../../../../docs/framework/wcf/using-bindings-to-configure-services-and-clients.md)
- [<span data-ttu-id="16b10-151">\<binding></span><span class="sxs-lookup"><span data-stu-id="16b10-151">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)
