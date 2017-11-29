---
title: "&lt;peerTransport&gt; 的 &lt;transport&gt;"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: d7116240-845c-4b6f-b203-262de6b597ef
caps.latest.revision: "4"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 787d4569416203364e04898c6adcd57fb5a7aec8
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="lttransportgt-of-ltpeertransportgt"></a><span data-ttu-id="b0fa1-102">&lt;peerTransport&gt; 的 &lt;transport&gt;</span><span class="sxs-lookup"><span data-stu-id="b0fa1-102">&lt;transport&gt; of &lt;peerTransport&gt;</span></span>
<span data-ttu-id="b0fa1-103">指定采用此绑定配置的对等方所发送的安全消息的传输类型。</span><span class="sxs-lookup"><span data-stu-id="b0fa1-103">Specifies the transport type for secured messages sent by peers configured with this binding.</span></span>  
  
 <span data-ttu-id="b0fa1-104">\<system.serviceModel ></span><span class="sxs-lookup"><span data-stu-id="b0fa1-104">\<system.serviceModel></span></span>  
<span data-ttu-id="b0fa1-105">\<绑定 ></span><span class="sxs-lookup"><span data-stu-id="b0fa1-105">\<bindings></span></span>  
<span data-ttu-id="b0fa1-106">\<customBinding ></span><span class="sxs-lookup"><span data-stu-id="b0fa1-106">\<customBinding></span></span>  
<span data-ttu-id="b0fa1-107">\<绑定 ></span><span class="sxs-lookup"><span data-stu-id="b0fa1-107">\<binding></span></span>  
<span data-ttu-id="b0fa1-108">\<t ></span><span class="sxs-lookup"><span data-stu-id="b0fa1-108">\<peerTransport></span></span>  
<span data-ttu-id="b0fa1-109">\<安全 ></span><span class="sxs-lookup"><span data-stu-id="b0fa1-109">\<security></span></span>  
<span data-ttu-id="b0fa1-110">\<传输 ></span><span class="sxs-lookup"><span data-stu-id="b0fa1-110">\<transport></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b0fa1-111">语法</span><span class="sxs-lookup"><span data-stu-id="b0fa1-111">Syntax</span></span>  
  
```xml  
<security>  
   <transport credentialType="Certificate/Password" />  
</security>         
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="b0fa1-112">特性和元素</span><span class="sxs-lookup"><span data-stu-id="b0fa1-112">Attributes and Elements</span></span>  
 <span data-ttu-id="b0fa1-113">以下几节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="b0fa1-113">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="b0fa1-114">特性</span><span class="sxs-lookup"><span data-stu-id="b0fa1-114">Attributes</span></span>  
  
|<span data-ttu-id="b0fa1-115">特性</span><span class="sxs-lookup"><span data-stu-id="b0fa1-115">Attribute</span></span>|<span data-ttu-id="b0fa1-116">描述</span><span class="sxs-lookup"><span data-stu-id="b0fa1-116">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="b0fa1-117">credentialType</span><span class="sxs-lookup"><span data-stu-id="b0fa1-117">credentialType</span></span>|<span data-ttu-id="b0fa1-118">可选。</span><span class="sxs-lookup"><span data-stu-id="b0fa1-118">Optional.</span></span> <span data-ttu-id="b0fa1-119">指定用于验证通过对等传输发送的消息的凭据的类型。</span><span class="sxs-lookup"><span data-stu-id="b0fa1-119">Specifies the type of credentials used to verify messages sent with the peer transport.</span></span> <span data-ttu-id="b0fa1-120">此属性的类型为 <xref:System.ServiceModel.PeerTransportCredentialType>。</span><span class="sxs-lookup"><span data-stu-id="b0fa1-120">This attribute is of type <xref:System.ServiceModel.PeerTransportCredentialType>.</span></span>|  
  
## <a name="credentialtype-attribute"></a><span data-ttu-id="b0fa1-121">credentialType 属性</span><span class="sxs-lookup"><span data-stu-id="b0fa1-121">credentialType Attribute</span></span>  
  
|<span data-ttu-id="b0fa1-122">值</span><span class="sxs-lookup"><span data-stu-id="b0fa1-122">Value</span></span>|<span data-ttu-id="b0fa1-123">描述</span><span class="sxs-lookup"><span data-stu-id="b0fa1-123">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="b0fa1-124">证书</span><span class="sxs-lookup"><span data-stu-id="b0fa1-124">Certificate</span></span>|<span data-ttu-id="b0fa1-125">对等通道传输的身份验证需要 X509 证书。</span><span class="sxs-lookup"><span data-stu-id="b0fa1-125">Authentication of the peer channel transport requires an X509 certificate.</span></span>|  
|<span data-ttu-id="b0fa1-126">密码</span><span class="sxs-lookup"><span data-stu-id="b0fa1-126">Password</span></span>|<span data-ttu-id="b0fa1-127">对等通道传输的身份验证需要正确的密码。</span><span class="sxs-lookup"><span data-stu-id="b0fa1-127">Authentication of the peer channel transport requires a correct password.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="b0fa1-128">子元素</span><span class="sxs-lookup"><span data-stu-id="b0fa1-128">Child Elements</span></span>  
 <span data-ttu-id="b0fa1-129">无</span><span class="sxs-lookup"><span data-stu-id="b0fa1-129">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="b0fa1-130">父元素</span><span class="sxs-lookup"><span data-stu-id="b0fa1-130">Parent Elements</span></span>  
  
|<span data-ttu-id="b0fa1-131">元素</span><span class="sxs-lookup"><span data-stu-id="b0fa1-131">Element</span></span>|<span data-ttu-id="b0fa1-132">描述</span><span class="sxs-lookup"><span data-stu-id="b0fa1-132">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="b0fa1-133">\<安全 ></span><span class="sxs-lookup"><span data-stu-id="b0fa1-133">\<security></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/security-of-peertransport.md)|<span data-ttu-id="b0fa1-134">定义对等传输的安全设置。</span><span class="sxs-lookup"><span data-stu-id="b0fa1-134">Defines the security settings for a peer transport.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="b0fa1-135">备注</span><span class="sxs-lookup"><span data-stu-id="b0fa1-135">Remarks</span></span>  
 <span data-ttu-id="b0fa1-136">仅当设置此元素的 mode 属性[\<安全 >](../../../../../docs/framework/configure-apps/file-schema/wcf/security-of-peertransport.md)设置为`Transport`或`TransportWithMessageCredential`。</span><span class="sxs-lookup"><span data-stu-id="b0fa1-136">This element is set only if the mode attribute of [\<security>](../../../../../docs/framework/configure-apps/file-schema/wcf/security-of-peertransport.md) is set to `Transport` or `TransportWithMessageCredential`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b0fa1-137">另请参阅</span><span class="sxs-lookup"><span data-stu-id="b0fa1-137">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.PeerTransportSecurityElement>  
 <xref:System.ServiceModel.PeerSecuritySettings.Transport%2A>  
 <xref:System.ServiceModel.PeerTransportSecuritySettings>  
 <xref:System.ServiceModel.Channels.CustomBinding>  
 [<span data-ttu-id="b0fa1-138">传输安全</span><span class="sxs-lookup"><span data-stu-id="b0fa1-138">Transport Security</span></span>](../../../../../docs/framework/wcf/feature-details/transport-security.md)  
 [<span data-ttu-id="b0fa1-139">传输</span><span class="sxs-lookup"><span data-stu-id="b0fa1-139">Transports</span></span>](../../../../../docs/framework/wcf/feature-details/transports.md)  
 [<span data-ttu-id="b0fa1-140">选择传输</span><span class="sxs-lookup"><span data-stu-id="b0fa1-140">Choosing a Transport</span></span>](../../../../../docs/framework/wcf/feature-details/choosing-a-transport.md)  
 [<span data-ttu-id="b0fa1-141">绑定</span><span class="sxs-lookup"><span data-stu-id="b0fa1-141">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)  
 [<span data-ttu-id="b0fa1-142">扩展绑定</span><span class="sxs-lookup"><span data-stu-id="b0fa1-142">Extending Bindings</span></span>](../../../../../docs/framework/wcf/extending/extending-bindings.md)  
 [<span data-ttu-id="b0fa1-143">自定义绑定</span><span class="sxs-lookup"><span data-stu-id="b0fa1-143">Custom Bindings</span></span>](../../../../../docs/framework/wcf/extending/custom-bindings.md)  
 [<span data-ttu-id="b0fa1-144">\<customBinding ></span><span class="sxs-lookup"><span data-stu-id="b0fa1-144">\<customBinding></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md)
