---
title: <security> 的 <peerTransport>
ms.date: 03/30/2017
ms.assetid: f73634ed-f896-4968-bf74-5e5ac52d3b6b
ms.openlocfilehash: 270ca844f586be256b6483653c868d1cc4396657
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/06/2019
ms.locfileid: "70399757"
---
# <a name="security-of-peertransport"></a><span data-ttu-id="5ca5f-102">\<peerTransport 的\<安全 > ></span><span class="sxs-lookup"><span data-stu-id="5ca5f-102">\<security> of \<peerTransport></span></span>
<span data-ttu-id="5ca5f-103">包含与对等通道相关的安全设置，包括使用的身份验证类型和用于消息传输的安全性。</span><span class="sxs-lookup"><span data-stu-id="5ca5f-103">Contains the security settings associated with a peer channel, including the type of authentication used and the security used for the message transport.</span></span>  
  
<span data-ttu-id="5ca5f-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="5ca5f-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="5ca5f-105">&nbsp;&nbsp;[ **\<System.servicemodel >** ](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="5ca5f-105">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="5ca5f-106">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<绑定 >** ](bindings.md)</span><span class="sxs-lookup"><span data-stu-id="5ca5f-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)</span></span>\
<span data-ttu-id="5ca5f-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<customBinding >** ](custombinding.md)</span><span class="sxs-lookup"><span data-stu-id="5ca5f-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<customBinding>**](custombinding.md)</span></span>\
<span data-ttu-id="5ca5f-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<绑定 >** </span><span class="sxs-lookup"><span data-stu-id="5ca5f-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**</span></span>\
<span data-ttu-id="5ca5f-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<peerTransport >** ](peertransport.md)</span><span class="sxs-lookup"><span data-stu-id="5ca5f-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<peerTransport>**](peertransport.md)</span></span>\
<span data-ttu-id="5ca5f-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<安全 >**</span><span class="sxs-lookup"><span data-stu-id="5ca5f-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<security>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5ca5f-111">语法</span><span class="sxs-lookup"><span data-stu-id="5ca5f-111">Syntax</span></span>  
  
```xml  
<security mode="None/Transport/Message/TransportWithMessageCredential">
  <transport clientCredentialType="None/Windows/UserName/Certificate/CardSpace" />
</security
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="5ca5f-112">特性和元素</span><span class="sxs-lookup"><span data-stu-id="5ca5f-112">Attributes and Elements</span></span>  
 <span data-ttu-id="5ca5f-113">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="5ca5f-113">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="5ca5f-114">特性</span><span class="sxs-lookup"><span data-stu-id="5ca5f-114">Attributes</span></span>  
  
|<span data-ttu-id="5ca5f-115">特性</span><span class="sxs-lookup"><span data-stu-id="5ca5f-115">Attribute</span></span>|<span data-ttu-id="5ca5f-116">描述</span><span class="sxs-lookup"><span data-stu-id="5ca5f-116">Description</span></span>|  
|---------------|-----------------|  
|`mode`|<span data-ttu-id="5ca5f-117">指定要应用的安全类型。</span><span class="sxs-lookup"><span data-stu-id="5ca5f-117">Specifies the type of security to be applied.</span></span> <span data-ttu-id="5ca5f-118">默认值为 Message。</span><span class="sxs-lookup"><span data-stu-id="5ca5f-118">The default value is Message.</span></span> <span data-ttu-id="5ca5f-119">此属性的类型为 <xref:System.ServiceModel.SecurityMode>。</span><span class="sxs-lookup"><span data-stu-id="5ca5f-119">This attribute is of type <xref:System.ServiceModel.SecurityMode>.</span></span>|  
  
## <a name="mode-attribute"></a><span data-ttu-id="5ca5f-120">mode 属性</span><span class="sxs-lookup"><span data-stu-id="5ca5f-120">mode Attribute</span></span>  
  
|<span data-ttu-id="5ca5f-121">值</span><span class="sxs-lookup"><span data-stu-id="5ca5f-121">Value</span></span>|<span data-ttu-id="5ca5f-122">描述</span><span class="sxs-lookup"><span data-stu-id="5ca5f-122">Description</span></span>|  
|-----------|-----------------|  
|`None`|<span data-ttu-id="5ca5f-123">禁用安全性。</span><span class="sxs-lookup"><span data-stu-id="5ca5f-123">Security is disabled.</span></span>|  
|`Transport`|<span data-ttu-id="5ca5f-124">使用 HTTPS 提供安全性。</span><span class="sxs-lookup"><span data-stu-id="5ca5f-124">Security is provided using HTTPS.</span></span>|  
|`Message`|<span data-ttu-id="5ca5f-125">SOAP 安全提供身份验证、完整性和保密性。</span><span class="sxs-lookup"><span data-stu-id="5ca5f-125">SOAP security provides authentication, integrity and confidentiality.</span></span>|  
|`TransportWithMessageCredential`|<span data-ttu-id="5ca5f-126">HTTPS 提供身份验证和保密性。</span><span class="sxs-lookup"><span data-stu-id="5ca5f-126">HTTPS provides authentication and confidentiality.</span></span> <span data-ttu-id="5ca5f-127">SOAP 消息提供丰富的凭据类型。</span><span class="sxs-lookup"><span data-stu-id="5ca5f-127">SOAP messages provide rich credential types.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="5ca5f-128">子元素</span><span class="sxs-lookup"><span data-stu-id="5ca5f-128">Child Elements</span></span>  
  
|<span data-ttu-id="5ca5f-129">元素</span><span class="sxs-lookup"><span data-stu-id="5ca5f-129">Element</span></span>|<span data-ttu-id="5ca5f-130">描述</span><span class="sxs-lookup"><span data-stu-id="5ca5f-130">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="5ca5f-131">\<transport></span><span class="sxs-lookup"><span data-stu-id="5ca5f-131">\<transport></span></span>](transport-of-peertransport.md)|<span data-ttu-id="5ca5f-132">定义自定义绑定的对等传输。</span><span class="sxs-lookup"><span data-stu-id="5ca5f-132">Defines a peer transport for a custom binding.</span></span> <span data-ttu-id="5ca5f-133">此元素具有一个 `clientCredentialType` 属性，可指定与服务进行交互时要使用的凭据。</span><span class="sxs-lookup"><span data-stu-id="5ca5f-133">This element has a `clientCredentialType` attribute that specifies the credentials to be used when interacting with a service.</span></span> <span data-ttu-id="5ca5f-134">此属性的类型为 <xref:System.ServiceModel.PeerTransportCredentialType>。</span><span class="sxs-lookup"><span data-stu-id="5ca5f-134">This attribute is of type <xref:System.ServiceModel.PeerTransportCredentialType>.</span></span><br /><br /> <span data-ttu-id="5ca5f-135">此元素的类型为 <xref:System.ServiceModel.Configuration.PeerTransportSecurityElement>。</span><span class="sxs-lookup"><span data-stu-id="5ca5f-135">This element is of type <xref:System.ServiceModel.Configuration.PeerTransportSecurityElement>.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="5ca5f-136">父元素</span><span class="sxs-lookup"><span data-stu-id="5ca5f-136">Parent Elements</span></span>  
  
|<span data-ttu-id="5ca5f-137">元素</span><span class="sxs-lookup"><span data-stu-id="5ca5f-137">Element</span></span>|<span data-ttu-id="5ca5f-138">描述</span><span class="sxs-lookup"><span data-stu-id="5ca5f-138">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="5ca5f-139">\<peerTransport></span><span class="sxs-lookup"><span data-stu-id="5ca5f-139">\<peerTransport></span></span>](peertransport.md)|<span data-ttu-id="5ca5f-140">定义自定义绑定的对等传输。</span><span class="sxs-lookup"><span data-stu-id="5ca5f-140">Defines a peer transport for a custom binding.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="5ca5f-141">请参阅</span><span class="sxs-lookup"><span data-stu-id="5ca5f-141">See also</span></span>

- <xref:System.ServiceModel.Configuration.PeerSecurityElement>
- <xref:System.ServiceModel.PeerSecuritySettings>
- <xref:System.ServiceModel.Channels.CustomBinding>
- [<span data-ttu-id="5ca5f-142">传输安全性</span><span class="sxs-lookup"><span data-stu-id="5ca5f-142">Transport Security</span></span>](../../../wcf/feature-details/transport-security.md)
- [<span data-ttu-id="5ca5f-143">传输</span><span class="sxs-lookup"><span data-stu-id="5ca5f-143">Transports</span></span>](../../../wcf/feature-details/transports.md)
- [<span data-ttu-id="5ca5f-144">选择传输</span><span class="sxs-lookup"><span data-stu-id="5ca5f-144">Choosing a Transport</span></span>](../../../wcf/feature-details/choosing-a-transport.md)
- [<span data-ttu-id="5ca5f-145">绑定</span><span class="sxs-lookup"><span data-stu-id="5ca5f-145">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="5ca5f-146">扩展绑定</span><span class="sxs-lookup"><span data-stu-id="5ca5f-146">Extending Bindings</span></span>](../../../wcf/extending/extending-bindings.md)
- [<span data-ttu-id="5ca5f-147">自定义绑定</span><span class="sxs-lookup"><span data-stu-id="5ca5f-147">Custom Bindings</span></span>](../../../wcf/extending/custom-bindings.md)
- [<span data-ttu-id="5ca5f-148">\<customBinding></span><span class="sxs-lookup"><span data-stu-id="5ca5f-148">\<customBinding></span></span>](custombinding.md)
