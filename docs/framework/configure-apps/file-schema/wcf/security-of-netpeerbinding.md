---
title: <security> 的 <netPeerBinding>
ms.date: 03/30/2017
ms.assetid: 1ef40d8c-f903-4426-9b08-da81462766d8
ms.openlocfilehash: 3d1ac85073c44f683fe0c054737c5ec7ed1cbf52
ms.sourcegitcommit: 22be09204266253d45ece46f51cc6f080f2b3fd6
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/07/2019
ms.locfileid: "73738656"
---
# <a name="security-of-netpeerbinding"></a><span data-ttu-id="33dcb-102">\<netPeerBinding 的安全 > \<</span><span class="sxs-lookup"><span data-stu-id="33dcb-102">\<security> of \<netPeerBinding></span></span>
<span data-ttu-id="33dcb-103">定义[\<netPeerTcpBinding >](netpeertcpbinding.md)的安全设置，包括使用的身份验证类型和用于消息传输的安全性。</span><span class="sxs-lookup"><span data-stu-id="33dcb-103">Defines the security settings of the [\<netPeerTcpBinding>](netpeertcpbinding.md), including the type of authentication used and the security used for the message transport.</span></span>  
  
<span data-ttu-id="33dcb-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="33dcb-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="33dcb-105">\<system &nbsp; &nbsp;[ **>** ](system-servicemodel.md) </span><span class="sxs-lookup"><span data-stu-id="33dcb-105">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="33dcb-106">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<绑定**](bindings.md)</span><span class="sxs-lookup"><span data-stu-id="33dcb-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)</span></span>\
<span data-ttu-id="33dcb-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<netPeerTcpBinding >** ](netpeertcpbinding.md)</span><span class="sxs-lookup"><span data-stu-id="33dcb-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<netPeerTcpBinding>**](netpeertcpbinding.md)</span></span>\
<span data-ttu-id="33dcb-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<绑定 >** </span><span class="sxs-lookup"><span data-stu-id="33dcb-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**</span></span>\
<span data-ttu-id="33dcb-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<** ></span><span class="sxs-lookup"><span data-stu-id="33dcb-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<security>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="33dcb-110">语法</span><span class="sxs-lookup"><span data-stu-id="33dcb-110">Syntax</span></span>  
  
```xml  
<netPeerBinding>
  <binding>
    <security mode="Message/None/Transport//TransportWithMessageCredential">
      <transport credentialType="Certificate/Password" />
    </security>
  </binding>
</netPeerBinding>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="33dcb-111">特性和元素</span><span class="sxs-lookup"><span data-stu-id="33dcb-111">Attributes and Elements</span></span>  
 <span data-ttu-id="33dcb-112">以下几节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="33dcb-112">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="33dcb-113">特性</span><span class="sxs-lookup"><span data-stu-id="33dcb-113">Attributes</span></span>  
  
|<span data-ttu-id="33dcb-114">特性</span><span class="sxs-lookup"><span data-stu-id="33dcb-114">Attribute</span></span>|<span data-ttu-id="33dcb-115">描述</span><span class="sxs-lookup"><span data-stu-id="33dcb-115">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="33dcb-116">mode</span><span class="sxs-lookup"><span data-stu-id="33dcb-116">mode</span></span>|<span data-ttu-id="33dcb-117">可选。</span><span class="sxs-lookup"><span data-stu-id="33dcb-117">Optional.</span></span> <span data-ttu-id="33dcb-118">指定采用此绑定配置的对等端所使用的安全类型。</span><span class="sxs-lookup"><span data-stu-id="33dcb-118">Specifies the type of security used by peers configured with this binding.</span></span> <span data-ttu-id="33dcb-119">默认值为 `Message`。</span><span class="sxs-lookup"><span data-stu-id="33dcb-119">The default value is `Message`.</span></span> <span data-ttu-id="33dcb-120">此属性的类型为 <xref:System.ServiceModel.SecurityMode>。</span><span class="sxs-lookup"><span data-stu-id="33dcb-120">This attribute is of type <xref:System.ServiceModel.SecurityMode>.</span></span>|  
  
## <a name="mode-attribute"></a><span data-ttu-id="33dcb-121">mode 属性</span><span class="sxs-lookup"><span data-stu-id="33dcb-121">mode Attribute</span></span>  
  
|<span data-ttu-id="33dcb-122">“值”</span><span class="sxs-lookup"><span data-stu-id="33dcb-122">Value</span></span>|<span data-ttu-id="33dcb-123">描述</span><span class="sxs-lookup"><span data-stu-id="33dcb-123">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="33dcb-124">消息</span><span class="sxs-lookup"><span data-stu-id="33dcb-124">Message</span></span>|<span data-ttu-id="33dcb-125">SOAP 安全提供身份验证、完整性和保密性。</span><span class="sxs-lookup"><span data-stu-id="33dcb-125">SOAP security provides authentication, integrity and confidentiality.</span></span>|  
|<span data-ttu-id="33dcb-126">None</span><span class="sxs-lookup"><span data-stu-id="33dcb-126">None</span></span>|<span data-ttu-id="33dcb-127">禁用安全性。</span><span class="sxs-lookup"><span data-stu-id="33dcb-127">Security is disabled.</span></span>|  
|<span data-ttu-id="33dcb-128">传输</span><span class="sxs-lookup"><span data-stu-id="33dcb-128">Transport</span></span>|<span data-ttu-id="33dcb-129">使用 HTTPS 提供安全性。</span><span class="sxs-lookup"><span data-stu-id="33dcb-129">Security is provided using HTTPS.</span></span>|  
|<span data-ttu-id="33dcb-130">TransportWithMessageCredential</span><span class="sxs-lookup"><span data-stu-id="33dcb-130">TransportWithMessageCredential</span></span>|<span data-ttu-id="33dcb-131">HTTPS 提供身份验证和保密性。</span><span class="sxs-lookup"><span data-stu-id="33dcb-131">HTTPS provides authentication and confidentiality.</span></span> <span data-ttu-id="33dcb-132">SOAP 消息提供丰富的凭据类型。</span><span class="sxs-lookup"><span data-stu-id="33dcb-132">SOAP messages provide rich credential types.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="33dcb-133">子元素</span><span class="sxs-lookup"><span data-stu-id="33dcb-133">Child Elements</span></span>  
  
|<span data-ttu-id="33dcb-134">元素</span><span class="sxs-lookup"><span data-stu-id="33dcb-134">Element</span></span>|<span data-ttu-id="33dcb-135">描述</span><span class="sxs-lookup"><span data-stu-id="33dcb-135">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="33dcb-136">\<传输 ></span><span class="sxs-lookup"><span data-stu-id="33dcb-136">\<transport></span></span>](transport-of-netpeertcpbinding.md)|<span data-ttu-id="33dcb-137">定义采用此绑定配置的对等端所发送的安全消息的传输类型。</span><span class="sxs-lookup"><span data-stu-id="33dcb-137">Defines the transport type for secured messages sent by peers configured with this binding.</span></span> <span data-ttu-id="33dcb-138">此元素的类型为 <xref:System.ServiceModel.Configuration.PeerTransportSecurityElement>。</span><span class="sxs-lookup"><span data-stu-id="33dcb-138">This element is of type <xref:System.ServiceModel.Configuration.PeerTransportSecurityElement>.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="33dcb-139">父元素</span><span class="sxs-lookup"><span data-stu-id="33dcb-139">Parent Elements</span></span>  
  
|<span data-ttu-id="33dcb-140">元素</span><span class="sxs-lookup"><span data-stu-id="33dcb-140">Element</span></span>|<span data-ttu-id="33dcb-141">描述</span><span class="sxs-lookup"><span data-stu-id="33dcb-141">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="33dcb-142">\<binding ></span><span class="sxs-lookup"><span data-stu-id="33dcb-142">\<binding></span></span>](bindings.md)|<span data-ttu-id="33dcb-143">定义[\<netPeerTcpBinding >](netpeertcpbinding.md)的所有绑定功能。</span><span class="sxs-lookup"><span data-stu-id="33dcb-143">Defines all binding capabilities of the [\<netPeerTcpBinding>](netpeertcpbinding.md).</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="33dcb-144">备注</span><span class="sxs-lookup"><span data-stu-id="33dcb-144">Remarks</span></span>  
 <span data-ttu-id="33dcb-145">安全性可以是特定于消息的，也可以是特定于传输的。</span><span class="sxs-lookup"><span data-stu-id="33dcb-145">Security can be either message- or transport-specific.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="33dcb-146">请参阅</span><span class="sxs-lookup"><span data-stu-id="33dcb-146">See also</span></span>

- <xref:System.ServiceModel.Configuration.PeerSecurityElement>
- <xref:System.ServiceModel.NetPeerTcpBinding.Security%2A>
- <xref:System.ServiceModel.Configuration.NetPeerTcpBindingElement.Security%2A>
- <xref:System.ServiceModel.PeerSecuritySettings>
- [<span data-ttu-id="33dcb-147">保护服务和客户端的安全</span><span class="sxs-lookup"><span data-stu-id="33dcb-147">Securing Services and Clients</span></span>](../../../wcf/feature-details/securing-services-and-clients.md)
- [<span data-ttu-id="33dcb-148">选择凭据类型</span><span class="sxs-lookup"><span data-stu-id="33dcb-148">Selecting a Credential Type</span></span>](../../../wcf/feature-details/selecting-a-credential-type.md)
- [<span data-ttu-id="33dcb-149">绑定</span><span class="sxs-lookup"><span data-stu-id="33dcb-149">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="33dcb-150">配置系统提供的绑定</span><span class="sxs-lookup"><span data-stu-id="33dcb-150">Configuring System-Provided Bindings</span></span>](../../../wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="33dcb-151">使用绑定配置服务和客户端</span><span class="sxs-lookup"><span data-stu-id="33dcb-151">Using Bindings to Configure Services and Clients</span></span>](../../../wcf/using-bindings-to-configure-services-and-clients.md)
- [<span data-ttu-id="33dcb-152">\<binding ></span><span class="sxs-lookup"><span data-stu-id="33dcb-152">\<binding></span></span>](bindings.md)
