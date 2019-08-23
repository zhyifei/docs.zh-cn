---
title: <transport> 的 <peerTransport>
ms.date: 03/30/2017
ms.assetid: d7116240-845c-4b6f-b203-262de6b597ef
ms.openlocfilehash: 5dbc55db25c0c49d72ec2cd8dd1041a3f8705d8e
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2019
ms.locfileid: "69940636"
---
# <a name="transport-of-peertransport"></a><span data-ttu-id="82a4f-102">\<peerTransport > 的\<传输 ></span><span class="sxs-lookup"><span data-stu-id="82a4f-102">\<transport> of \<peerTransport></span></span>
<span data-ttu-id="82a4f-103">指定采用此绑定配置的对等方所发送的安全消息的传输类型。</span><span class="sxs-lookup"><span data-stu-id="82a4f-103">Specifies the transport type for secured messages sent by peers configured with this binding.</span></span>  
  
 <span data-ttu-id="82a4f-104">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="82a4f-104">\<system.serviceModel></span></span>  
<span data-ttu-id="82a4f-105">\<bindings></span><span class="sxs-lookup"><span data-stu-id="82a4f-105">\<bindings></span></span>  
<span data-ttu-id="82a4f-106">\<customBinding></span><span class="sxs-lookup"><span data-stu-id="82a4f-106">\<customBinding></span></span>  
<span data-ttu-id="82a4f-107">\<绑定 ></span><span class="sxs-lookup"><span data-stu-id="82a4f-107">\<binding></span></span>  
<span data-ttu-id="82a4f-108">\<peerTransport></span><span class="sxs-lookup"><span data-stu-id="82a4f-108">\<peerTransport></span></span>  
<span data-ttu-id="82a4f-109">\<安全 ></span><span class="sxs-lookup"><span data-stu-id="82a4f-109">\<security></span></span>  
<span data-ttu-id="82a4f-110">\<transport></span><span class="sxs-lookup"><span data-stu-id="82a4f-110">\<transport></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="82a4f-111">语法</span><span class="sxs-lookup"><span data-stu-id="82a4f-111">Syntax</span></span>  
  
```xml  
<security>
  <transport credentialType="Certificate/Password" />
</security>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="82a4f-112">特性和元素</span><span class="sxs-lookup"><span data-stu-id="82a4f-112">Attributes and Elements</span></span>  
 <span data-ttu-id="82a4f-113">以下几节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="82a4f-113">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="82a4f-114">特性</span><span class="sxs-lookup"><span data-stu-id="82a4f-114">Attributes</span></span>  
  
|<span data-ttu-id="82a4f-115">特性</span><span class="sxs-lookup"><span data-stu-id="82a4f-115">Attribute</span></span>|<span data-ttu-id="82a4f-116">描述</span><span class="sxs-lookup"><span data-stu-id="82a4f-116">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="82a4f-117">credentialType</span><span class="sxs-lookup"><span data-stu-id="82a4f-117">credentialType</span></span>|<span data-ttu-id="82a4f-118">可选。</span><span class="sxs-lookup"><span data-stu-id="82a4f-118">Optional.</span></span> <span data-ttu-id="82a4f-119">指定用于验证通过对等传输发送的消息的凭据的类型。</span><span class="sxs-lookup"><span data-stu-id="82a4f-119">Specifies the type of credentials used to verify messages sent with the peer transport.</span></span> <span data-ttu-id="82a4f-120">此属性的类型为 <xref:System.ServiceModel.PeerTransportCredentialType>。</span><span class="sxs-lookup"><span data-stu-id="82a4f-120">This attribute is of type <xref:System.ServiceModel.PeerTransportCredentialType>.</span></span>|  
  
## <a name="credentialtype-attribute"></a><span data-ttu-id="82a4f-121">credentialType 属性</span><span class="sxs-lookup"><span data-stu-id="82a4f-121">credentialType Attribute</span></span>  
  
|<span data-ttu-id="82a4f-122">值</span><span class="sxs-lookup"><span data-stu-id="82a4f-122">Value</span></span>|<span data-ttu-id="82a4f-123">描述</span><span class="sxs-lookup"><span data-stu-id="82a4f-123">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="82a4f-124">证书</span><span class="sxs-lookup"><span data-stu-id="82a4f-124">Certificate</span></span>|<span data-ttu-id="82a4f-125">对等通道传输的身份验证需要 X509 证书。</span><span class="sxs-lookup"><span data-stu-id="82a4f-125">Authentication of the peer channel transport requires an X509 certificate.</span></span>|  
|<span data-ttu-id="82a4f-126">Password</span><span class="sxs-lookup"><span data-stu-id="82a4f-126">Password</span></span>|<span data-ttu-id="82a4f-127">对等通道传输的身份验证需要正确的密码。</span><span class="sxs-lookup"><span data-stu-id="82a4f-127">Authentication of the peer channel transport requires a correct password.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="82a4f-128">子元素</span><span class="sxs-lookup"><span data-stu-id="82a4f-128">Child Elements</span></span>  
 <span data-ttu-id="82a4f-129">无</span><span class="sxs-lookup"><span data-stu-id="82a4f-129">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="82a4f-130">父元素</span><span class="sxs-lookup"><span data-stu-id="82a4f-130">Parent Elements</span></span>  
  
|<span data-ttu-id="82a4f-131">元素</span><span class="sxs-lookup"><span data-stu-id="82a4f-131">Element</span></span>|<span data-ttu-id="82a4f-132">描述</span><span class="sxs-lookup"><span data-stu-id="82a4f-132">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="82a4f-133">\<security></span><span class="sxs-lookup"><span data-stu-id="82a4f-133">\<security></span></span>](security-of-peertransport.md)|<span data-ttu-id="82a4f-134">定义对等传输的安全设置。</span><span class="sxs-lookup"><span data-stu-id="82a4f-134">Defines the security settings for a peer transport.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="82a4f-135">备注</span><span class="sxs-lookup"><span data-stu-id="82a4f-135">Remarks</span></span>  
 <span data-ttu-id="82a4f-136">仅当[ \<security >](security-of-peertransport.md)的 mode 属性设置为`Transport`或`TransportWithMessageCredential`时, 才设置此元素。</span><span class="sxs-lookup"><span data-stu-id="82a4f-136">This element is set only if the mode attribute of [\<security>](security-of-peertransport.md) is set to `Transport` or `TransportWithMessageCredential`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="82a4f-137">请参阅</span><span class="sxs-lookup"><span data-stu-id="82a4f-137">See also</span></span>

- <xref:System.ServiceModel.Configuration.PeerTransportSecurityElement>
- <xref:System.ServiceModel.PeerSecuritySettings.Transport%2A>
- <xref:System.ServiceModel.PeerTransportSecuritySettings>
- <xref:System.ServiceModel.Channels.CustomBinding>
- [<span data-ttu-id="82a4f-138">传输安全性</span><span class="sxs-lookup"><span data-stu-id="82a4f-138">Transport Security</span></span>](../../../wcf/feature-details/transport-security.md)
- [<span data-ttu-id="82a4f-139">传输</span><span class="sxs-lookup"><span data-stu-id="82a4f-139">Transports</span></span>](../../../wcf/feature-details/transports.md)
- [<span data-ttu-id="82a4f-140">选择传输</span><span class="sxs-lookup"><span data-stu-id="82a4f-140">Choosing a Transport</span></span>](../../../wcf/feature-details/choosing-a-transport.md)
- [<span data-ttu-id="82a4f-141">绑定</span><span class="sxs-lookup"><span data-stu-id="82a4f-141">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="82a4f-142">扩展绑定</span><span class="sxs-lookup"><span data-stu-id="82a4f-142">Extending Bindings</span></span>](../../../wcf/extending/extending-bindings.md)
- [<span data-ttu-id="82a4f-143">自定义绑定</span><span class="sxs-lookup"><span data-stu-id="82a4f-143">Custom Bindings</span></span>](../../../wcf/extending/custom-bindings.md)
- [<span data-ttu-id="82a4f-144">\<customBinding></span><span class="sxs-lookup"><span data-stu-id="82a4f-144">\<customBinding></span></span>](custombinding.md)
