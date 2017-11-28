---
title: "&lt;peerTransport&gt; 的 &lt;security&gt;"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: f73634ed-f896-4968-bf74-5e5ac52d3b6b
caps.latest.revision: "7"
author: BrucePerlerMS
ms.author: bruceper
manager: mbaldwin
ms.openlocfilehash: f7f85a1d0d5ca720c82d513c7d51ac6ddaf5afb1
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="ltsecuritygt-of-ltpeertransportgt"></a><span data-ttu-id="04d1d-102">&lt;peerTransport&gt; 的 &lt;security&gt;</span><span class="sxs-lookup"><span data-stu-id="04d1d-102">&lt;security&gt; of &lt;peerTransport&gt;</span></span>
<span data-ttu-id="04d1d-103">包含与对等通道相关的安全设置，包括使用的身份验证类型和用于消息传输的安全性。</span><span class="sxs-lookup"><span data-stu-id="04d1d-103">Contains the security settings associated with a peer channel, including the type of authentication used and the security used for the message transport.</span></span>  
  
 <span data-ttu-id="04d1d-104">\<system.serviceModel ></span><span class="sxs-lookup"><span data-stu-id="04d1d-104">\<system.serviceModel></span></span>  
<span data-ttu-id="04d1d-105">\<绑定 ></span><span class="sxs-lookup"><span data-stu-id="04d1d-105">\<bindings></span></span>  
<span data-ttu-id="04d1d-106">\<customBinding ></span><span class="sxs-lookup"><span data-stu-id="04d1d-106">\<customBinding></span></span>  
<span data-ttu-id="04d1d-107">\<绑定 ></span><span class="sxs-lookup"><span data-stu-id="04d1d-107">\<binding></span></span>  
<span data-ttu-id="04d1d-108">\<t ></span><span class="sxs-lookup"><span data-stu-id="04d1d-108">\<peerTransport></span></span>  
<span data-ttu-id="04d1d-109">\<安全 ></span><span class="sxs-lookup"><span data-stu-id="04d1d-109">\<security></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="04d1d-110">语法</span><span class="sxs-lookup"><span data-stu-id="04d1d-110">Syntax</span></span>  
  
```xml  
<security mode="None/Transport/Message/TransportWithMessageCredential">  
    <transport clientCredentialType="None/Windows/UserName/Certificate/CardSpace" />  
</security  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="04d1d-111">特性和元素</span><span class="sxs-lookup"><span data-stu-id="04d1d-111">Attributes and Elements</span></span>  
 <span data-ttu-id="04d1d-112">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="04d1d-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="04d1d-113">特性</span><span class="sxs-lookup"><span data-stu-id="04d1d-113">Attributes</span></span>  
  
|<span data-ttu-id="04d1d-114">特性</span><span class="sxs-lookup"><span data-stu-id="04d1d-114">Attribute</span></span>|<span data-ttu-id="04d1d-115">描述</span><span class="sxs-lookup"><span data-stu-id="04d1d-115">Description</span></span>|  
|---------------|-----------------|  
|`mode`|<span data-ttu-id="04d1d-116">指定要应用的安全类型。</span><span class="sxs-lookup"><span data-stu-id="04d1d-116">Specifies the type of security to be applied.</span></span> <span data-ttu-id="04d1d-117">默认值为 Message。</span><span class="sxs-lookup"><span data-stu-id="04d1d-117">The default value is Message.</span></span> <span data-ttu-id="04d1d-118">此属性的类型为 <xref:System.ServiceModel.SecurityMode>。</span><span class="sxs-lookup"><span data-stu-id="04d1d-118">This attribute is of type <xref:System.ServiceModel.SecurityMode>.</span></span>|  
  
## <a name="mode-attribute"></a><span data-ttu-id="04d1d-119">mode 属性</span><span class="sxs-lookup"><span data-stu-id="04d1d-119">mode Attribute</span></span>  
  
|<span data-ttu-id="04d1d-120">值</span><span class="sxs-lookup"><span data-stu-id="04d1d-120">Value</span></span>|<span data-ttu-id="04d1d-121">描述</span><span class="sxs-lookup"><span data-stu-id="04d1d-121">Description</span></span>|  
|-----------|-----------------|  
|`None`|<span data-ttu-id="04d1d-122">禁用安全性。</span><span class="sxs-lookup"><span data-stu-id="04d1d-122">Security is disabled.</span></span>|  
|`Transport`|<span data-ttu-id="04d1d-123">使用 HTTPS 提供安全性。</span><span class="sxs-lookup"><span data-stu-id="04d1d-123">Security is provided using HTTPS.</span></span>|  
|`Message`|<span data-ttu-id="04d1d-124">SOAP 安全提供身份验证、完整性和保密性。</span><span class="sxs-lookup"><span data-stu-id="04d1d-124">SOAP security provides authentication, integrity and confidentiality.</span></span>|  
|`TransportWithMessageCredential`|<span data-ttu-id="04d1d-125">HTTPS 提供身份验证和保密性。</span><span class="sxs-lookup"><span data-stu-id="04d1d-125">HTTPS provides authentication and confidentiality.</span></span> <span data-ttu-id="04d1d-126">SOAP 消息提供丰富的凭据类型。</span><span class="sxs-lookup"><span data-stu-id="04d1d-126">SOAP messages provide rich credential types.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="04d1d-127">子元素</span><span class="sxs-lookup"><span data-stu-id="04d1d-127">Child Elements</span></span>  
  
|<span data-ttu-id="04d1d-128">元素</span><span class="sxs-lookup"><span data-stu-id="04d1d-128">Element</span></span>|<span data-ttu-id="04d1d-129">描述</span><span class="sxs-lookup"><span data-stu-id="04d1d-129">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="04d1d-130">\<传输 ></span><span class="sxs-lookup"><span data-stu-id="04d1d-130">\<transport></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/transport-of-peertransport.md)|<span data-ttu-id="04d1d-131">定义自定义绑定的对等传输。</span><span class="sxs-lookup"><span data-stu-id="04d1d-131">Defines a peer transport for a custom binding.</span></span> <span data-ttu-id="04d1d-132">此元素具有一个 `clientCredentialType` 属性，可指定与服务进行交互时要使用的凭据。</span><span class="sxs-lookup"><span data-stu-id="04d1d-132">This element has a `clientCredentialType` attribute that specifies the credentials to be used when interacting with a service.</span></span> <span data-ttu-id="04d1d-133">此属性的类型为 <xref:System.ServiceModel.PeerTransportCredentialType>。</span><span class="sxs-lookup"><span data-stu-id="04d1d-133">This attribute is of type <xref:System.ServiceModel.PeerTransportCredentialType>.</span></span><br /><br /> <span data-ttu-id="04d1d-134">此元素的类型为 <xref:System.ServiceModel.Configuration.PeerTransportSecurityElement>。</span><span class="sxs-lookup"><span data-stu-id="04d1d-134">This element is of type <xref:System.ServiceModel.Configuration.PeerTransportSecurityElement>.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="04d1d-135">父元素</span><span class="sxs-lookup"><span data-stu-id="04d1d-135">Parent Elements</span></span>  
  
|<span data-ttu-id="04d1d-136">元素</span><span class="sxs-lookup"><span data-stu-id="04d1d-136">Element</span></span>|<span data-ttu-id="04d1d-137">描述</span><span class="sxs-lookup"><span data-stu-id="04d1d-137">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="04d1d-138">\<t ></span><span class="sxs-lookup"><span data-stu-id="04d1d-138">\<peerTransport></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/peertransport.md)|<span data-ttu-id="04d1d-139">定义自定义绑定的对等传输。</span><span class="sxs-lookup"><span data-stu-id="04d1d-139">Defines a peer transport for a custom binding.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="04d1d-140">另请参阅</span><span class="sxs-lookup"><span data-stu-id="04d1d-140">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.PeerSecurityElement>  
 <xref:System.ServiceModel.PeerSecuritySettings>  
 <xref:System.ServiceModel.Channels.CustomBinding>  
 [<span data-ttu-id="04d1d-141">传输安全</span><span class="sxs-lookup"><span data-stu-id="04d1d-141">Transport Security</span></span>](../../../../../docs/framework/wcf/feature-details/transport-security.md)  
 [<span data-ttu-id="04d1d-142">传输</span><span class="sxs-lookup"><span data-stu-id="04d1d-142">Transports</span></span>](../../../../../docs/framework/wcf/feature-details/transports.md)  
 [<span data-ttu-id="04d1d-143">选择传输</span><span class="sxs-lookup"><span data-stu-id="04d1d-143">Choosing a Transport</span></span>](../../../../../docs/framework/wcf/feature-details/choosing-a-transport.md)  
 [<span data-ttu-id="04d1d-144">绑定</span><span class="sxs-lookup"><span data-stu-id="04d1d-144">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)  
 [<span data-ttu-id="04d1d-145">扩展绑定</span><span class="sxs-lookup"><span data-stu-id="04d1d-145">Extending Bindings</span></span>](../../../../../docs/framework/wcf/extending/extending-bindings.md)  
 [<span data-ttu-id="04d1d-146">自定义绑定</span><span class="sxs-lookup"><span data-stu-id="04d1d-146">Custom Bindings</span></span>](../../../../../docs/framework/wcf/extending/custom-bindings.md)  
 [<span data-ttu-id="04d1d-147">\<customBinding ></span><span class="sxs-lookup"><span data-stu-id="04d1d-147">\<customBinding></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md)
