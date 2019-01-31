---
title: <transport> 的 <peerTransport>
ms.date: 03/30/2017
ms.assetid: d7116240-845c-4b6f-b203-262de6b597ef
ms.openlocfilehash: 3dbeda5d418c30f378515fa83979eaca289370f9
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/30/2019
ms.locfileid: "55284006"
---
# <a name="transport-of-peertransport"></a><span data-ttu-id="8b96c-102">\<传输 > 的\<peerTransport ></span><span class="sxs-lookup"><span data-stu-id="8b96c-102">\<transport> of \<peerTransport></span></span>
<span data-ttu-id="8b96c-103">指定采用此绑定配置的对等方所发送的安全消息的传输类型。</span><span class="sxs-lookup"><span data-stu-id="8b96c-103">Specifies the transport type for secured messages sent by peers configured with this binding.</span></span>  
  
 <span data-ttu-id="8b96c-104">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="8b96c-104">\<system.serviceModel></span></span>  
<span data-ttu-id="8b96c-105">\<bindings></span><span class="sxs-lookup"><span data-stu-id="8b96c-105">\<bindings></span></span>  
<span data-ttu-id="8b96c-106">\<customBinding></span><span class="sxs-lookup"><span data-stu-id="8b96c-106">\<customBinding></span></span>  
<span data-ttu-id="8b96c-107">\<binding></span><span class="sxs-lookup"><span data-stu-id="8b96c-107">\<binding></span></span>  
<span data-ttu-id="8b96c-108">\<peerTransport></span><span class="sxs-lookup"><span data-stu-id="8b96c-108">\<peerTransport></span></span>  
<span data-ttu-id="8b96c-109">\<安全 ></span><span class="sxs-lookup"><span data-stu-id="8b96c-109">\<security></span></span>  
<span data-ttu-id="8b96c-110">\<transport></span><span class="sxs-lookup"><span data-stu-id="8b96c-110">\<transport></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8b96c-111">语法</span><span class="sxs-lookup"><span data-stu-id="8b96c-111">Syntax</span></span>  
  
```xml  
<security>
  <transport credentialType="Certificate/Password" />
</security>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="8b96c-112">特性和元素</span><span class="sxs-lookup"><span data-stu-id="8b96c-112">Attributes and Elements</span></span>  
 <span data-ttu-id="8b96c-113">以下几节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="8b96c-113">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="8b96c-114">特性</span><span class="sxs-lookup"><span data-stu-id="8b96c-114">Attributes</span></span>  
  
|<span data-ttu-id="8b96c-115">特性</span><span class="sxs-lookup"><span data-stu-id="8b96c-115">Attribute</span></span>|<span data-ttu-id="8b96c-116">描述</span><span class="sxs-lookup"><span data-stu-id="8b96c-116">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="8b96c-117">credentialType</span><span class="sxs-lookup"><span data-stu-id="8b96c-117">credentialType</span></span>|<span data-ttu-id="8b96c-118">可选。</span><span class="sxs-lookup"><span data-stu-id="8b96c-118">Optional.</span></span> <span data-ttu-id="8b96c-119">指定用于验证通过对等传输发送的消息的凭据的类型。</span><span class="sxs-lookup"><span data-stu-id="8b96c-119">Specifies the type of credentials used to verify messages sent with the peer transport.</span></span> <span data-ttu-id="8b96c-120">此属性的类型为 <xref:System.ServiceModel.PeerTransportCredentialType>。</span><span class="sxs-lookup"><span data-stu-id="8b96c-120">This attribute is of type <xref:System.ServiceModel.PeerTransportCredentialType>.</span></span>|  
  
## <a name="credentialtype-attribute"></a><span data-ttu-id="8b96c-121">credentialType 属性</span><span class="sxs-lookup"><span data-stu-id="8b96c-121">credentialType Attribute</span></span>  
  
|<span data-ttu-id="8b96c-122">值</span><span class="sxs-lookup"><span data-stu-id="8b96c-122">Value</span></span>|<span data-ttu-id="8b96c-123">描述</span><span class="sxs-lookup"><span data-stu-id="8b96c-123">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="8b96c-124">证书</span><span class="sxs-lookup"><span data-stu-id="8b96c-124">Certificate</span></span>|<span data-ttu-id="8b96c-125">对等通道传输的身份验证需要 X509 证书。</span><span class="sxs-lookup"><span data-stu-id="8b96c-125">Authentication of the peer channel transport requires an X509 certificate.</span></span>|  
|<span data-ttu-id="8b96c-126">密码</span><span class="sxs-lookup"><span data-stu-id="8b96c-126">Password</span></span>|<span data-ttu-id="8b96c-127">对等通道传输的身份验证需要正确的密码。</span><span class="sxs-lookup"><span data-stu-id="8b96c-127">Authentication of the peer channel transport requires a correct password.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="8b96c-128">子元素</span><span class="sxs-lookup"><span data-stu-id="8b96c-128">Child Elements</span></span>  
 <span data-ttu-id="8b96c-129">无</span><span class="sxs-lookup"><span data-stu-id="8b96c-129">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="8b96c-130">父元素</span><span class="sxs-lookup"><span data-stu-id="8b96c-130">Parent Elements</span></span>  
  
|<span data-ttu-id="8b96c-131">元素</span><span class="sxs-lookup"><span data-stu-id="8b96c-131">Element</span></span>|<span data-ttu-id="8b96c-132">描述</span><span class="sxs-lookup"><span data-stu-id="8b96c-132">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="8b96c-133">\<security></span><span class="sxs-lookup"><span data-stu-id="8b96c-133">\<security></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/security-of-peertransport.md)|<span data-ttu-id="8b96c-134">定义对等传输的安全设置。</span><span class="sxs-lookup"><span data-stu-id="8b96c-134">Defines the security settings for a peer transport.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="8b96c-135">备注</span><span class="sxs-lookup"><span data-stu-id="8b96c-135">Remarks</span></span>  
 <span data-ttu-id="8b96c-136">仅当设置此元素的 mode 属性[\<安全 >](../../../../../docs/framework/configure-apps/file-schema/wcf/security-of-peertransport.md)设置为`Transport`或`TransportWithMessageCredential`。</span><span class="sxs-lookup"><span data-stu-id="8b96c-136">This element is set only if the mode attribute of [\<security>](../../../../../docs/framework/configure-apps/file-schema/wcf/security-of-peertransport.md) is set to `Transport` or `TransportWithMessageCredential`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8b96c-137">请参阅</span><span class="sxs-lookup"><span data-stu-id="8b96c-137">See also</span></span>
- <xref:System.ServiceModel.Configuration.PeerTransportSecurityElement>
- <xref:System.ServiceModel.PeerSecuritySettings.Transport%2A>
- <xref:System.ServiceModel.PeerTransportSecuritySettings>
- <xref:System.ServiceModel.Channels.CustomBinding>
- [<span data-ttu-id="8b96c-138">传输安全性</span><span class="sxs-lookup"><span data-stu-id="8b96c-138">Transport Security</span></span>](../../../../../docs/framework/wcf/feature-details/transport-security.md)
- [<span data-ttu-id="8b96c-139">传输</span><span class="sxs-lookup"><span data-stu-id="8b96c-139">Transports</span></span>](../../../../../docs/framework/wcf/feature-details/transports.md)
- [<span data-ttu-id="8b96c-140">选择传输</span><span class="sxs-lookup"><span data-stu-id="8b96c-140">Choosing a Transport</span></span>](../../../../../docs/framework/wcf/feature-details/choosing-a-transport.md)
- [<span data-ttu-id="8b96c-141">绑定</span><span class="sxs-lookup"><span data-stu-id="8b96c-141">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)
- [<span data-ttu-id="8b96c-142">扩展绑定</span><span class="sxs-lookup"><span data-stu-id="8b96c-142">Extending Bindings</span></span>](../../../../../docs/framework/wcf/extending/extending-bindings.md)
- [<span data-ttu-id="8b96c-143">自定义绑定</span><span class="sxs-lookup"><span data-stu-id="8b96c-143">Custom Bindings</span></span>](../../../../../docs/framework/wcf/extending/custom-bindings.md)
- [<span data-ttu-id="8b96c-144">\<customBinding></span><span class="sxs-lookup"><span data-stu-id="8b96c-144">\<customBinding></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md)
