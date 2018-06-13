---
title: '&lt;netPeerBinding&gt; 的 &lt;security&gt;'
ms.date: 03/30/2017
ms.assetid: 1ef40d8c-f903-4426-9b08-da81462766d8
author: BrucePerlerMS
manager: mbaldwin
ms.openlocfilehash: 7413820f1a1f38b3d533573715267df3b85c9d9a
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/03/2018
ms.locfileid: "32749135"
---
# <a name="ltsecuritygt-of-ltnetpeerbindinggt"></a><span data-ttu-id="93b0a-102">&lt;netPeerBinding&gt; 的 &lt;security&gt;</span><span class="sxs-lookup"><span data-stu-id="93b0a-102">&lt;security&gt; of &lt;netPeerBinding&gt;</span></span>
<span data-ttu-id="93b0a-103">定义的安全设置[ \<netPeerTcpBinding >](../../../../../docs/framework/configure-apps/file-schema/wcf/netpeertcpbinding.md)，包括身份验证的类型使用，安全用于消息传输。</span><span class="sxs-lookup"><span data-stu-id="93b0a-103">Defines the security settings of the [\<netPeerTcpBinding>](../../../../../docs/framework/configure-apps/file-schema/wcf/netpeertcpbinding.md), including the type of authentication used and the security used for the message transport.</span></span>  
  
 <span data-ttu-id="93b0a-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="93b0a-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="93b0a-105">\<绑定 ></span><span class="sxs-lookup"><span data-stu-id="93b0a-105">\<bindings></span></span>  
<span data-ttu-id="93b0a-106">\<netPeerBinding></span><span class="sxs-lookup"><span data-stu-id="93b0a-106">\<netPeerBinding></span></span>  
<span data-ttu-id="93b0a-107">\<绑定 ></span><span class="sxs-lookup"><span data-stu-id="93b0a-107">\<binding></span></span>  
<span data-ttu-id="93b0a-108">\<安全 ></span><span class="sxs-lookup"><span data-stu-id="93b0a-108">\<security></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="93b0a-109">语法</span><span class="sxs-lookup"><span data-stu-id="93b0a-109">Syntax</span></span>  
  
```xml  
<netPeerBinding>  
    <binding>  
        <security mode="Message/None/Transport//TransportWithMessageCredential">  
            <transport credentialType="Certificate/Password" />  
        </security>  
    </binding>  
</netPeerBinding>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="93b0a-110">特性和元素</span><span class="sxs-lookup"><span data-stu-id="93b0a-110">Attributes and Elements</span></span>  
 <span data-ttu-id="93b0a-111">以下几节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="93b0a-111">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="93b0a-112">特性</span><span class="sxs-lookup"><span data-stu-id="93b0a-112">Attributes</span></span>  
  
|<span data-ttu-id="93b0a-113">特性</span><span class="sxs-lookup"><span data-stu-id="93b0a-113">Attribute</span></span>|<span data-ttu-id="93b0a-114">描述</span><span class="sxs-lookup"><span data-stu-id="93b0a-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="93b0a-115">mode</span><span class="sxs-lookup"><span data-stu-id="93b0a-115">mode</span></span>|<span data-ttu-id="93b0a-116">可选。</span><span class="sxs-lookup"><span data-stu-id="93b0a-116">Optional.</span></span> <span data-ttu-id="93b0a-117">指定采用此绑定配置的对等端所使用的安全类型。</span><span class="sxs-lookup"><span data-stu-id="93b0a-117">Specifies the type of security used by peers configured with this binding.</span></span> <span data-ttu-id="93b0a-118">默认值为 `Message`。</span><span class="sxs-lookup"><span data-stu-id="93b0a-118">The default value is `Message`.</span></span> <span data-ttu-id="93b0a-119">此属性的类型为 <xref:System.ServiceModel.SecurityMode>。</span><span class="sxs-lookup"><span data-stu-id="93b0a-119">This attribute is of type <xref:System.ServiceModel.SecurityMode>.</span></span>|  
  
## <a name="mode-attribute"></a><span data-ttu-id="93b0a-120">mode 属性</span><span class="sxs-lookup"><span data-stu-id="93b0a-120">mode Attribute</span></span>  
  
|<span data-ttu-id="93b0a-121">值</span><span class="sxs-lookup"><span data-stu-id="93b0a-121">Value</span></span>|<span data-ttu-id="93b0a-122">描述</span><span class="sxs-lookup"><span data-stu-id="93b0a-122">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="93b0a-123">消息</span><span class="sxs-lookup"><span data-stu-id="93b0a-123">Message</span></span>|<span data-ttu-id="93b0a-124">SOAP 安全提供身份验证、完整性和保密性。</span><span class="sxs-lookup"><span data-stu-id="93b0a-124">SOAP security provides authentication, integrity and confidentiality.</span></span>|  
|<span data-ttu-id="93b0a-125">无</span><span class="sxs-lookup"><span data-stu-id="93b0a-125">None</span></span>|<span data-ttu-id="93b0a-126">禁用安全性。</span><span class="sxs-lookup"><span data-stu-id="93b0a-126">Security is disabled.</span></span>|  
|<span data-ttu-id="93b0a-127">传输</span><span class="sxs-lookup"><span data-stu-id="93b0a-127">Transport</span></span>|<span data-ttu-id="93b0a-128">使用 HTTPS 提供安全性。</span><span class="sxs-lookup"><span data-stu-id="93b0a-128">Security is provided using HTTPS.</span></span>|  
|<span data-ttu-id="93b0a-129">TransportWithMessageCredential</span><span class="sxs-lookup"><span data-stu-id="93b0a-129">TransportWithMessageCredential</span></span>|<span data-ttu-id="93b0a-130">HTTPS 提供身份验证和保密性。</span><span class="sxs-lookup"><span data-stu-id="93b0a-130">HTTPS provides authentication and confidentiality.</span></span> <span data-ttu-id="93b0a-131">SOAP 消息提供丰富的凭据类型。</span><span class="sxs-lookup"><span data-stu-id="93b0a-131">SOAP messages provide rich credential types.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="93b0a-132">子元素</span><span class="sxs-lookup"><span data-stu-id="93b0a-132">Child Elements</span></span>  
  
|<span data-ttu-id="93b0a-133">元素</span><span class="sxs-lookup"><span data-stu-id="93b0a-133">Element</span></span>|<span data-ttu-id="93b0a-134">描述</span><span class="sxs-lookup"><span data-stu-id="93b0a-134">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="93b0a-135">\<transport></span><span class="sxs-lookup"><span data-stu-id="93b0a-135">\<transport></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/transport-of-netpeertcpbinding.md)|<span data-ttu-id="93b0a-136">定义采用此绑定配置的对等端所发送的安全消息的传输类型。</span><span class="sxs-lookup"><span data-stu-id="93b0a-136">Defines the transport type for secured messages sent by peers configured with this binding.</span></span> <span data-ttu-id="93b0a-137">此元素的类型为 <xref:System.ServiceModel.Configuration.PeerTransportSecurityElement>。</span><span class="sxs-lookup"><span data-stu-id="93b0a-137">This element is of type <xref:System.ServiceModel.Configuration.PeerTransportSecurityElement>.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="93b0a-138">父元素</span><span class="sxs-lookup"><span data-stu-id="93b0a-138">Parent Elements</span></span>  
  
|<span data-ttu-id="93b0a-139">元素</span><span class="sxs-lookup"><span data-stu-id="93b0a-139">Element</span></span>|<span data-ttu-id="93b0a-140">描述</span><span class="sxs-lookup"><span data-stu-id="93b0a-140">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="93b0a-141">\<绑定 ></span><span class="sxs-lookup"><span data-stu-id="93b0a-141">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)|<span data-ttu-id="93b0a-142">定义的所有绑定功能[ \<netPeerTcpBinding >](../../../../../docs/framework/configure-apps/file-schema/wcf/netpeertcpbinding.md)。</span><span class="sxs-lookup"><span data-stu-id="93b0a-142">Defines all binding capabilities of the [\<netPeerTcpBinding>](../../../../../docs/framework/configure-apps/file-schema/wcf/netpeertcpbinding.md).</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="93b0a-143">备注</span><span class="sxs-lookup"><span data-stu-id="93b0a-143">Remarks</span></span>  
 <span data-ttu-id="93b0a-144">安全性可以是特定于消息的，也可以是特定于传输的。</span><span class="sxs-lookup"><span data-stu-id="93b0a-144">Security can be either message- or transport-specific.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="93b0a-145">请参阅</span><span class="sxs-lookup"><span data-stu-id="93b0a-145">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.PeerSecurityElement>  
 <xref:System.ServiceModel.NetPeerTcpBinding.Security%2A>  
 <xref:System.ServiceModel.Configuration.NetPeerTcpBindingElement.Security%2A>  
 <xref:System.ServiceModel.PeerSecuritySettings>  
 [<span data-ttu-id="93b0a-146">保护服务和客户端的安全</span><span class="sxs-lookup"><span data-stu-id="93b0a-146">Securing Services and Clients</span></span>](../../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)  
 [<span data-ttu-id="93b0a-147">选择凭据类型</span><span class="sxs-lookup"><span data-stu-id="93b0a-147">Selecting a Credential Type</span></span>](../../../../../docs/framework/wcf/feature-details/selecting-a-credential-type.md)  
 [<span data-ttu-id="93b0a-148">绑定</span><span class="sxs-lookup"><span data-stu-id="93b0a-148">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)  
 [<span data-ttu-id="93b0a-149">配置系统提供的绑定</span><span class="sxs-lookup"><span data-stu-id="93b0a-149">Configuring System-Provided Bindings</span></span>](../../../../../docs/framework/wcf/feature-details/configuring-system-provided-bindings.md)  
 [<span data-ttu-id="93b0a-150">使用绑定来配置 Windows Communication Foundation 服务和客户端</span><span class="sxs-lookup"><span data-stu-id="93b0a-150">Using Bindings to Configure Windows Communication Foundation Services and Clients</span></span>](http://msdn.microsoft.com/library/bd8b277b-932f-472f-a42a-b02bb5257dfb)  
 [<span data-ttu-id="93b0a-151">\<绑定 ></span><span class="sxs-lookup"><span data-stu-id="93b0a-151">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)
