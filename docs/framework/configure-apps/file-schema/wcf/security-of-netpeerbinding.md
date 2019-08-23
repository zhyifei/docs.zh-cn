---
title: <security> 的 <netPeerBinding>
ms.date: 03/30/2017
ms.assetid: 1ef40d8c-f903-4426-9b08-da81462766d8
ms.openlocfilehash: be5ebacec466caf8d8a77bf552f42da1861e77a1
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2019
ms.locfileid: "69936631"
---
# <a name="security-of-netpeerbinding"></a><span data-ttu-id="7d135-102">\<netPeerBinding 的\<安全 > ></span><span class="sxs-lookup"><span data-stu-id="7d135-102">\<security> of \<netPeerBinding></span></span>
<span data-ttu-id="7d135-103">定义[ \<netPeerTcpBinding >](netpeertcpbinding.md)的安全设置, 包括使用的身份验证类型和用于消息传输的安全性。</span><span class="sxs-lookup"><span data-stu-id="7d135-103">Defines the security settings of the [\<netPeerTcpBinding>](netpeertcpbinding.md), including the type of authentication used and the security used for the message transport.</span></span>  
  
 <span data-ttu-id="7d135-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="7d135-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="7d135-105">\<bindings></span><span class="sxs-lookup"><span data-stu-id="7d135-105">\<bindings></span></span>  
<span data-ttu-id="7d135-106">\<netPeerBinding></span><span class="sxs-lookup"><span data-stu-id="7d135-106">\<netPeerBinding></span></span>  
<span data-ttu-id="7d135-107">\<绑定 ></span><span class="sxs-lookup"><span data-stu-id="7d135-107">\<binding></span></span>  
<span data-ttu-id="7d135-108">\<安全 ></span><span class="sxs-lookup"><span data-stu-id="7d135-108">\<security></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7d135-109">语法</span><span class="sxs-lookup"><span data-stu-id="7d135-109">Syntax</span></span>  
  
```xml  
<netPeerBinding>
  <binding>
    <security mode="Message/None/Transport//TransportWithMessageCredential">
      <transport credentialType="Certificate/Password" />
    </security>
  </binding>
</netPeerBinding>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="7d135-110">特性和元素</span><span class="sxs-lookup"><span data-stu-id="7d135-110">Attributes and Elements</span></span>  
 <span data-ttu-id="7d135-111">以下几节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="7d135-111">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="7d135-112">特性</span><span class="sxs-lookup"><span data-stu-id="7d135-112">Attributes</span></span>  
  
|<span data-ttu-id="7d135-113">特性</span><span class="sxs-lookup"><span data-stu-id="7d135-113">Attribute</span></span>|<span data-ttu-id="7d135-114">描述</span><span class="sxs-lookup"><span data-stu-id="7d135-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="7d135-115">mode</span><span class="sxs-lookup"><span data-stu-id="7d135-115">mode</span></span>|<span data-ttu-id="7d135-116">可选。</span><span class="sxs-lookup"><span data-stu-id="7d135-116">Optional.</span></span> <span data-ttu-id="7d135-117">指定采用此绑定配置的对等端所使用的安全类型。</span><span class="sxs-lookup"><span data-stu-id="7d135-117">Specifies the type of security used by peers configured with this binding.</span></span> <span data-ttu-id="7d135-118">默认值为 `Message`。</span><span class="sxs-lookup"><span data-stu-id="7d135-118">The default value is `Message`.</span></span> <span data-ttu-id="7d135-119">此属性的类型为 <xref:System.ServiceModel.SecurityMode>。</span><span class="sxs-lookup"><span data-stu-id="7d135-119">This attribute is of type <xref:System.ServiceModel.SecurityMode>.</span></span>|  
  
## <a name="mode-attribute"></a><span data-ttu-id="7d135-120">mode 属性</span><span class="sxs-lookup"><span data-stu-id="7d135-120">mode Attribute</span></span>  
  
|<span data-ttu-id="7d135-121">值</span><span class="sxs-lookup"><span data-stu-id="7d135-121">Value</span></span>|<span data-ttu-id="7d135-122">描述</span><span class="sxs-lookup"><span data-stu-id="7d135-122">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="7d135-123">消息</span><span class="sxs-lookup"><span data-stu-id="7d135-123">Message</span></span>|<span data-ttu-id="7d135-124">SOAP 安全提供身份验证、完整性和保密性。</span><span class="sxs-lookup"><span data-stu-id="7d135-124">SOAP security provides authentication, integrity and confidentiality.</span></span>|  
|<span data-ttu-id="7d135-125">无</span><span class="sxs-lookup"><span data-stu-id="7d135-125">None</span></span>|<span data-ttu-id="7d135-126">禁用安全性。</span><span class="sxs-lookup"><span data-stu-id="7d135-126">Security is disabled.</span></span>|  
|<span data-ttu-id="7d135-127">传输</span><span class="sxs-lookup"><span data-stu-id="7d135-127">Transport</span></span>|<span data-ttu-id="7d135-128">使用 HTTPS 提供安全性。</span><span class="sxs-lookup"><span data-stu-id="7d135-128">Security is provided using HTTPS.</span></span>|  
|<span data-ttu-id="7d135-129">TransportWithMessageCredential</span><span class="sxs-lookup"><span data-stu-id="7d135-129">TransportWithMessageCredential</span></span>|<span data-ttu-id="7d135-130">HTTPS 提供身份验证和保密性。</span><span class="sxs-lookup"><span data-stu-id="7d135-130">HTTPS provides authentication and confidentiality.</span></span> <span data-ttu-id="7d135-131">SOAP 消息提供丰富的凭据类型。</span><span class="sxs-lookup"><span data-stu-id="7d135-131">SOAP messages provide rich credential types.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="7d135-132">子元素</span><span class="sxs-lookup"><span data-stu-id="7d135-132">Child Elements</span></span>  
  
|<span data-ttu-id="7d135-133">元素</span><span class="sxs-lookup"><span data-stu-id="7d135-133">Element</span></span>|<span data-ttu-id="7d135-134">描述</span><span class="sxs-lookup"><span data-stu-id="7d135-134">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="7d135-135">\<transport></span><span class="sxs-lookup"><span data-stu-id="7d135-135">\<transport></span></span>](transport-of-netpeertcpbinding.md)|<span data-ttu-id="7d135-136">定义采用此绑定配置的对等端所发送的安全消息的传输类型。</span><span class="sxs-lookup"><span data-stu-id="7d135-136">Defines the transport type for secured messages sent by peers configured with this binding.</span></span> <span data-ttu-id="7d135-137">此元素的类型为 <xref:System.ServiceModel.Configuration.PeerTransportSecurityElement>。</span><span class="sxs-lookup"><span data-stu-id="7d135-137">This element is of type <xref:System.ServiceModel.Configuration.PeerTransportSecurityElement>.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="7d135-138">父元素</span><span class="sxs-lookup"><span data-stu-id="7d135-138">Parent Elements</span></span>  
  
|<span data-ttu-id="7d135-139">元素</span><span class="sxs-lookup"><span data-stu-id="7d135-139">Element</span></span>|<span data-ttu-id="7d135-140">描述</span><span class="sxs-lookup"><span data-stu-id="7d135-140">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="7d135-141">\<binding></span><span class="sxs-lookup"><span data-stu-id="7d135-141">\<binding></span></span>](../../../misc/binding.md)|<span data-ttu-id="7d135-142">定义[ \<netPeerTcpBinding >](netpeertcpbinding.md)的所有绑定功能。</span><span class="sxs-lookup"><span data-stu-id="7d135-142">Defines all binding capabilities of the [\<netPeerTcpBinding>](netpeertcpbinding.md).</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="7d135-143">备注</span><span class="sxs-lookup"><span data-stu-id="7d135-143">Remarks</span></span>  
 <span data-ttu-id="7d135-144">安全性可以是特定于消息的，也可以是特定于传输的。</span><span class="sxs-lookup"><span data-stu-id="7d135-144">Security can be either message- or transport-specific.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7d135-145">请参阅</span><span class="sxs-lookup"><span data-stu-id="7d135-145">See also</span></span>

- <xref:System.ServiceModel.Configuration.PeerSecurityElement>
- <xref:System.ServiceModel.NetPeerTcpBinding.Security%2A>
- <xref:System.ServiceModel.Configuration.NetPeerTcpBindingElement.Security%2A>
- <xref:System.ServiceModel.PeerSecuritySettings>
- [<span data-ttu-id="7d135-146">保护服务和客户端的安全</span><span class="sxs-lookup"><span data-stu-id="7d135-146">Securing Services and Clients</span></span>](../../../wcf/feature-details/securing-services-and-clients.md)
- [<span data-ttu-id="7d135-147">选择凭据类型</span><span class="sxs-lookup"><span data-stu-id="7d135-147">Selecting a Credential Type</span></span>](../../../wcf/feature-details/selecting-a-credential-type.md)
- [<span data-ttu-id="7d135-148">绑定</span><span class="sxs-lookup"><span data-stu-id="7d135-148">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="7d135-149">配置系统提供的绑定</span><span class="sxs-lookup"><span data-stu-id="7d135-149">Configuring System-Provided Bindings</span></span>](../../../wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="7d135-150">使用绑定配置服务和客户端</span><span class="sxs-lookup"><span data-stu-id="7d135-150">Using Bindings to Configure Services and Clients</span></span>](../../../wcf/using-bindings-to-configure-services-and-clients.md)
- [<span data-ttu-id="7d135-151">\<binding></span><span class="sxs-lookup"><span data-stu-id="7d135-151">\<binding></span></span>](../../../misc/binding.md)
