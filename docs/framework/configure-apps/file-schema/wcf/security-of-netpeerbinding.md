---
title: <security> 的 <netPeerBinding>
ms.date: 03/30/2017
ms.assetid: 1ef40d8c-f903-4426-9b08-da81462766d8
ms.openlocfilehash: 88aa2898472c20c9e52cfd5830c0e41e8ea9ba21
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/06/2019
ms.locfileid: "70399808"
---
# <a name="security-of-netpeerbinding"></a><span data-ttu-id="a8809-102">\<netPeerBinding 的\<安全 > ></span><span class="sxs-lookup"><span data-stu-id="a8809-102">\<security> of \<netPeerBinding></span></span>
<span data-ttu-id="a8809-103">定义[ \<netPeerTcpBinding >](netpeertcpbinding.md)的安全设置，包括使用的身份验证类型和用于消息传输的安全性。</span><span class="sxs-lookup"><span data-stu-id="a8809-103">Defines the security settings of the [\<netPeerTcpBinding>](netpeertcpbinding.md), including the type of authentication used and the security used for the message transport.</span></span>  
  
<span data-ttu-id="a8809-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="a8809-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="a8809-105">&nbsp;&nbsp;[ **\<System.servicemodel >** ](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="a8809-105">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="a8809-106">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<绑定 >** ](bindings.md)</span><span class="sxs-lookup"><span data-stu-id="a8809-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)</span></span>\
<span data-ttu-id="a8809-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<netPeerTcpBinding >** ](netpeertcpbinding.md)</span><span class="sxs-lookup"><span data-stu-id="a8809-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<netPeerTcpBinding>**](netpeertcpbinding.md)</span></span>\
<span data-ttu-id="a8809-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<绑定 >** </span><span class="sxs-lookup"><span data-stu-id="a8809-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**</span></span>\
<span data-ttu-id="a8809-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<安全 >**</span><span class="sxs-lookup"><span data-stu-id="a8809-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<security>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a8809-110">语法</span><span class="sxs-lookup"><span data-stu-id="a8809-110">Syntax</span></span>  
  
```xml  
<netPeerBinding>
  <binding>
    <security mode="Message/None/Transport//TransportWithMessageCredential">
      <transport credentialType="Certificate/Password" />
    </security>
  </binding>
</netPeerBinding>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="a8809-111">特性和元素</span><span class="sxs-lookup"><span data-stu-id="a8809-111">Attributes and Elements</span></span>  
 <span data-ttu-id="a8809-112">以下几节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="a8809-112">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="a8809-113">特性</span><span class="sxs-lookup"><span data-stu-id="a8809-113">Attributes</span></span>  
  
|<span data-ttu-id="a8809-114">特性</span><span class="sxs-lookup"><span data-stu-id="a8809-114">Attribute</span></span>|<span data-ttu-id="a8809-115">描述</span><span class="sxs-lookup"><span data-stu-id="a8809-115">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="a8809-116">mode</span><span class="sxs-lookup"><span data-stu-id="a8809-116">mode</span></span>|<span data-ttu-id="a8809-117">可选。</span><span class="sxs-lookup"><span data-stu-id="a8809-117">Optional.</span></span> <span data-ttu-id="a8809-118">指定采用此绑定配置的对等端所使用的安全类型。</span><span class="sxs-lookup"><span data-stu-id="a8809-118">Specifies the type of security used by peers configured with this binding.</span></span> <span data-ttu-id="a8809-119">默认值为 `Message`。</span><span class="sxs-lookup"><span data-stu-id="a8809-119">The default value is `Message`.</span></span> <span data-ttu-id="a8809-120">此属性的类型为 <xref:System.ServiceModel.SecurityMode>。</span><span class="sxs-lookup"><span data-stu-id="a8809-120">This attribute is of type <xref:System.ServiceModel.SecurityMode>.</span></span>|  
  
## <a name="mode-attribute"></a><span data-ttu-id="a8809-121">mode 属性</span><span class="sxs-lookup"><span data-stu-id="a8809-121">mode Attribute</span></span>  
  
|<span data-ttu-id="a8809-122">值</span><span class="sxs-lookup"><span data-stu-id="a8809-122">Value</span></span>|<span data-ttu-id="a8809-123">描述</span><span class="sxs-lookup"><span data-stu-id="a8809-123">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="a8809-124">消息</span><span class="sxs-lookup"><span data-stu-id="a8809-124">Message</span></span>|<span data-ttu-id="a8809-125">SOAP 安全提供身份验证、完整性和保密性。</span><span class="sxs-lookup"><span data-stu-id="a8809-125">SOAP security provides authentication, integrity and confidentiality.</span></span>|  
|<span data-ttu-id="a8809-126">无</span><span class="sxs-lookup"><span data-stu-id="a8809-126">None</span></span>|<span data-ttu-id="a8809-127">禁用安全性。</span><span class="sxs-lookup"><span data-stu-id="a8809-127">Security is disabled.</span></span>|  
|<span data-ttu-id="a8809-128">传输</span><span class="sxs-lookup"><span data-stu-id="a8809-128">Transport</span></span>|<span data-ttu-id="a8809-129">使用 HTTPS 提供安全性。</span><span class="sxs-lookup"><span data-stu-id="a8809-129">Security is provided using HTTPS.</span></span>|  
|<span data-ttu-id="a8809-130">TransportWithMessageCredential</span><span class="sxs-lookup"><span data-stu-id="a8809-130">TransportWithMessageCredential</span></span>|<span data-ttu-id="a8809-131">HTTPS 提供身份验证和保密性。</span><span class="sxs-lookup"><span data-stu-id="a8809-131">HTTPS provides authentication and confidentiality.</span></span> <span data-ttu-id="a8809-132">SOAP 消息提供丰富的凭据类型。</span><span class="sxs-lookup"><span data-stu-id="a8809-132">SOAP messages provide rich credential types.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="a8809-133">子元素</span><span class="sxs-lookup"><span data-stu-id="a8809-133">Child Elements</span></span>  
  
|<span data-ttu-id="a8809-134">元素</span><span class="sxs-lookup"><span data-stu-id="a8809-134">Element</span></span>|<span data-ttu-id="a8809-135">描述</span><span class="sxs-lookup"><span data-stu-id="a8809-135">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="a8809-136">\<transport></span><span class="sxs-lookup"><span data-stu-id="a8809-136">\<transport></span></span>](transport-of-netpeertcpbinding.md)|<span data-ttu-id="a8809-137">定义采用此绑定配置的对等端所发送的安全消息的传输类型。</span><span class="sxs-lookup"><span data-stu-id="a8809-137">Defines the transport type for secured messages sent by peers configured with this binding.</span></span> <span data-ttu-id="a8809-138">此元素的类型为 <xref:System.ServiceModel.Configuration.PeerTransportSecurityElement>。</span><span class="sxs-lookup"><span data-stu-id="a8809-138">This element is of type <xref:System.ServiceModel.Configuration.PeerTransportSecurityElement>.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="a8809-139">父元素</span><span class="sxs-lookup"><span data-stu-id="a8809-139">Parent Elements</span></span>  
  
|<span data-ttu-id="a8809-140">元素</span><span class="sxs-lookup"><span data-stu-id="a8809-140">Element</span></span>|<span data-ttu-id="a8809-141">描述</span><span class="sxs-lookup"><span data-stu-id="a8809-141">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="a8809-142">\<binding></span><span class="sxs-lookup"><span data-stu-id="a8809-142">\<binding></span></span>](../../../misc/binding.md)|<span data-ttu-id="a8809-143">定义[ \<netPeerTcpBinding >](netpeertcpbinding.md)的所有绑定功能。</span><span class="sxs-lookup"><span data-stu-id="a8809-143">Defines all binding capabilities of the [\<netPeerTcpBinding>](netpeertcpbinding.md).</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="a8809-144">备注</span><span class="sxs-lookup"><span data-stu-id="a8809-144">Remarks</span></span>  
 <span data-ttu-id="a8809-145">安全性可以是特定于消息的，也可以是特定于传输的。</span><span class="sxs-lookup"><span data-stu-id="a8809-145">Security can be either message- or transport-specific.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a8809-146">请参阅</span><span class="sxs-lookup"><span data-stu-id="a8809-146">See also</span></span>

- <xref:System.ServiceModel.Configuration.PeerSecurityElement>
- <xref:System.ServiceModel.NetPeerTcpBinding.Security%2A>
- <xref:System.ServiceModel.Configuration.NetPeerTcpBindingElement.Security%2A>
- <xref:System.ServiceModel.PeerSecuritySettings>
- [<span data-ttu-id="a8809-147">保护服务和客户端的安全</span><span class="sxs-lookup"><span data-stu-id="a8809-147">Securing Services and Clients</span></span>](../../../wcf/feature-details/securing-services-and-clients.md)
- [<span data-ttu-id="a8809-148">选择凭据类型</span><span class="sxs-lookup"><span data-stu-id="a8809-148">Selecting a Credential Type</span></span>](../../../wcf/feature-details/selecting-a-credential-type.md)
- [<span data-ttu-id="a8809-149">绑定</span><span class="sxs-lookup"><span data-stu-id="a8809-149">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="a8809-150">配置系统提供的绑定</span><span class="sxs-lookup"><span data-stu-id="a8809-150">Configuring System-Provided Bindings</span></span>](../../../wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="a8809-151">使用绑定配置服务和客户端</span><span class="sxs-lookup"><span data-stu-id="a8809-151">Using Bindings to Configure Services and Clients</span></span>](../../../wcf/using-bindings-to-configure-services-and-clients.md)
- [<span data-ttu-id="a8809-152">\<binding></span><span class="sxs-lookup"><span data-stu-id="a8809-152">\<binding></span></span>](../../../misc/binding.md)
