---
title: <transport> 的 <peerTransport>
ms.date: 03/30/2017
ms.assetid: d7116240-845c-4b6f-b203-262de6b597ef
ms.openlocfilehash: 3b2c7716727f58abb81bf4d58b13189ac170cf7c
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/06/2019
ms.locfileid: "70399291"
---
# <a name="transport-of-peertransport"></a><span data-ttu-id="70b66-102">\<peerTransport > 的\<传输 ></span><span class="sxs-lookup"><span data-stu-id="70b66-102">\<transport> of \<peerTransport></span></span>
<span data-ttu-id="70b66-103">指定采用此绑定配置的对等方所发送的安全消息的传输类型。</span><span class="sxs-lookup"><span data-stu-id="70b66-103">Specifies the transport type for secured messages sent by peers configured with this binding.</span></span>  
  
<span data-ttu-id="70b66-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="70b66-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="70b66-105">&nbsp;&nbsp;[ **\<System.servicemodel >** ](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="70b66-105">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="70b66-106">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<绑定 >** ](bindings.md)</span><span class="sxs-lookup"><span data-stu-id="70b66-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)</span></span>\
<span data-ttu-id="70b66-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<customBinding >** ](custombinding.md)</span><span class="sxs-lookup"><span data-stu-id="70b66-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<customBinding>**](custombinding.md)</span></span>\
<span data-ttu-id="70b66-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<绑定 >** </span><span class="sxs-lookup"><span data-stu-id="70b66-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**</span></span>\
<span data-ttu-id="70b66-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<peerTransport >** ](peertransport.md)</span><span class="sxs-lookup"><span data-stu-id="70b66-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<peerTransport>**](peertransport.md)</span></span>\
<span data-ttu-id="70b66-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<安全 >** ](security-of-peertransport.md)</span><span class="sxs-lookup"><span data-stu-id="70b66-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<security>**](security-of-peertransport.md)</span></span>\
<span data-ttu-id="70b66-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<传输 >**</span><span class="sxs-lookup"><span data-stu-id="70b66-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<transport>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="70b66-112">语法</span><span class="sxs-lookup"><span data-stu-id="70b66-112">Syntax</span></span>  
  
```xml  
<security>
  <transport credentialType="Certificate/Password" />
</security>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="70b66-113">特性和元素</span><span class="sxs-lookup"><span data-stu-id="70b66-113">Attributes and Elements</span></span>  
 <span data-ttu-id="70b66-114">以下几节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="70b66-114">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="70b66-115">特性</span><span class="sxs-lookup"><span data-stu-id="70b66-115">Attributes</span></span>  
  
|<span data-ttu-id="70b66-116">特性</span><span class="sxs-lookup"><span data-stu-id="70b66-116">Attribute</span></span>|<span data-ttu-id="70b66-117">描述</span><span class="sxs-lookup"><span data-stu-id="70b66-117">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="70b66-118">credentialType</span><span class="sxs-lookup"><span data-stu-id="70b66-118">credentialType</span></span>|<span data-ttu-id="70b66-119">可选。</span><span class="sxs-lookup"><span data-stu-id="70b66-119">Optional.</span></span> <span data-ttu-id="70b66-120">指定用于验证通过对等传输发送的消息的凭据的类型。</span><span class="sxs-lookup"><span data-stu-id="70b66-120">Specifies the type of credentials used to verify messages sent with the peer transport.</span></span> <span data-ttu-id="70b66-121">此属性的类型为 <xref:System.ServiceModel.PeerTransportCredentialType>。</span><span class="sxs-lookup"><span data-stu-id="70b66-121">This attribute is of type <xref:System.ServiceModel.PeerTransportCredentialType>.</span></span>|  
  
## <a name="credentialtype-attribute"></a><span data-ttu-id="70b66-122">credentialType 属性</span><span class="sxs-lookup"><span data-stu-id="70b66-122">credentialType Attribute</span></span>  
  
|<span data-ttu-id="70b66-123">值</span><span class="sxs-lookup"><span data-stu-id="70b66-123">Value</span></span>|<span data-ttu-id="70b66-124">描述</span><span class="sxs-lookup"><span data-stu-id="70b66-124">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="70b66-125">证书</span><span class="sxs-lookup"><span data-stu-id="70b66-125">Certificate</span></span>|<span data-ttu-id="70b66-126">对等通道传输的身份验证需要 X509 证书。</span><span class="sxs-lookup"><span data-stu-id="70b66-126">Authentication of the peer channel transport requires an X509 certificate.</span></span>|  
|<span data-ttu-id="70b66-127">Password</span><span class="sxs-lookup"><span data-stu-id="70b66-127">Password</span></span>|<span data-ttu-id="70b66-128">对等通道传输的身份验证需要正确的密码。</span><span class="sxs-lookup"><span data-stu-id="70b66-128">Authentication of the peer channel transport requires a correct password.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="70b66-129">子元素</span><span class="sxs-lookup"><span data-stu-id="70b66-129">Child Elements</span></span>  
 <span data-ttu-id="70b66-130">无</span><span class="sxs-lookup"><span data-stu-id="70b66-130">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="70b66-131">父元素</span><span class="sxs-lookup"><span data-stu-id="70b66-131">Parent Elements</span></span>  
  
|<span data-ttu-id="70b66-132">元素</span><span class="sxs-lookup"><span data-stu-id="70b66-132">Element</span></span>|<span data-ttu-id="70b66-133">描述</span><span class="sxs-lookup"><span data-stu-id="70b66-133">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="70b66-134">\<security></span><span class="sxs-lookup"><span data-stu-id="70b66-134">\<security></span></span>](security-of-peertransport.md)|<span data-ttu-id="70b66-135">定义对等传输的安全设置。</span><span class="sxs-lookup"><span data-stu-id="70b66-135">Defines the security settings for a peer transport.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="70b66-136">备注</span><span class="sxs-lookup"><span data-stu-id="70b66-136">Remarks</span></span>  
 <span data-ttu-id="70b66-137">仅当[ \<security >](security-of-peertransport.md)的 mode 属性设置为`Transport`或`TransportWithMessageCredential`时，才设置此元素。</span><span class="sxs-lookup"><span data-stu-id="70b66-137">This element is set only if the mode attribute of [\<security>](security-of-peertransport.md) is set to `Transport` or `TransportWithMessageCredential`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="70b66-138">请参阅</span><span class="sxs-lookup"><span data-stu-id="70b66-138">See also</span></span>

- <xref:System.ServiceModel.Configuration.PeerTransportSecurityElement>
- <xref:System.ServiceModel.PeerSecuritySettings.Transport%2A>
- <xref:System.ServiceModel.PeerTransportSecuritySettings>
- <xref:System.ServiceModel.Channels.CustomBinding>
- [<span data-ttu-id="70b66-139">传输安全性</span><span class="sxs-lookup"><span data-stu-id="70b66-139">Transport Security</span></span>](../../../wcf/feature-details/transport-security.md)
- [<span data-ttu-id="70b66-140">传输</span><span class="sxs-lookup"><span data-stu-id="70b66-140">Transports</span></span>](../../../wcf/feature-details/transports.md)
- [<span data-ttu-id="70b66-141">选择传输</span><span class="sxs-lookup"><span data-stu-id="70b66-141">Choosing a Transport</span></span>](../../../wcf/feature-details/choosing-a-transport.md)
- [<span data-ttu-id="70b66-142">绑定</span><span class="sxs-lookup"><span data-stu-id="70b66-142">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="70b66-143">扩展绑定</span><span class="sxs-lookup"><span data-stu-id="70b66-143">Extending Bindings</span></span>](../../../wcf/extending/extending-bindings.md)
- [<span data-ttu-id="70b66-144">自定义绑定</span><span class="sxs-lookup"><span data-stu-id="70b66-144">Custom Bindings</span></span>](../../../wcf/extending/custom-bindings.md)
- [<span data-ttu-id="70b66-145">\<customBinding></span><span class="sxs-lookup"><span data-stu-id="70b66-145">\<customBinding></span></span>](custombinding.md)
