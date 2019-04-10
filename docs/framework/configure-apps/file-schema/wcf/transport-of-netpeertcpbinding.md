---
title: <transport> 的 <netPeerTcpBinding>
ms.date: 03/30/2017
ms.assetid: c44d86d2-1160-44d7-9c7a-297b12eccc7f
ms.openlocfilehash: 157637615abafbd5913e4d90b702bb0224d5f121
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/08/2019
ms.locfileid: "59204868"
---
# <a name="transport-of-netpeertcpbinding"></a><span data-ttu-id="6e80f-102">\<transport> of \<netPeerTcpBinding></span><span class="sxs-lookup"><span data-stu-id="6e80f-102">\<transport> of \<netPeerTcpBinding></span></span>
<span data-ttu-id="6e80f-103">使用时指定的传输级安全设置[ \<netPeerTcpBinding >](../../../../../docs/framework/configure-apps/file-schema/wcf/netpeertcpbinding.md)。</span><span class="sxs-lookup"><span data-stu-id="6e80f-103">Specifies settings for transport level security when using the [\<netPeerTcpBinding>](../../../../../docs/framework/configure-apps/file-schema/wcf/netpeertcpbinding.md).</span></span>  
  
 <span data-ttu-id="6e80f-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="6e80f-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="6e80f-105">\<bindings></span><span class="sxs-lookup"><span data-stu-id="6e80f-105">\<bindings></span></span>  
<span data-ttu-id="6e80f-106">\<netPeerTcpBinding></span><span class="sxs-lookup"><span data-stu-id="6e80f-106">\<netPeerTcpBinding></span></span>  
<span data-ttu-id="6e80f-107">\<binding></span><span class="sxs-lookup"><span data-stu-id="6e80f-107">\<binding></span></span>  
<span data-ttu-id="6e80f-108">\<安全 ></span><span class="sxs-lookup"><span data-stu-id="6e80f-108">\<security></span></span>  
<span data-ttu-id="6e80f-109">\<transport></span><span class="sxs-lookup"><span data-stu-id="6e80f-109">\<transport></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6e80f-110">语法</span><span class="sxs-lookup"><span data-stu-id="6e80f-110">Syntax</span></span>  
  
```xml  
<netPeerTcpBinding>
  <binding>
    <security>
      <transport credentialType="Certificate/Password" />
    </security>
  </binding>
</netPeerTcpBinding>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="6e80f-111">特性和元素</span><span class="sxs-lookup"><span data-stu-id="6e80f-111">Attributes and Elements</span></span>  
 <span data-ttu-id="6e80f-112">以下几节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="6e80f-112">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="6e80f-113">特性</span><span class="sxs-lookup"><span data-stu-id="6e80f-113">Attributes</span></span>  
  
|<span data-ttu-id="6e80f-114">特性</span><span class="sxs-lookup"><span data-stu-id="6e80f-114">Attribute</span></span>|<span data-ttu-id="6e80f-115">描述</span><span class="sxs-lookup"><span data-stu-id="6e80f-115">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="6e80f-116">credentialType</span><span class="sxs-lookup"><span data-stu-id="6e80f-116">credentialType</span></span>|<span data-ttu-id="6e80f-117">可选。</span><span class="sxs-lookup"><span data-stu-id="6e80f-117">Optional.</span></span> <span data-ttu-id="6e80f-118">指定用于验证通过对等传输发送的消息的凭据的类型。</span><span class="sxs-lookup"><span data-stu-id="6e80f-118">Specifies the type of credentials used to verify messages sent with the peer transport.</span></span> <span data-ttu-id="6e80f-119">此属性的类型为 <xref:System.ServiceModel.PeerTransportCredentialType>。</span><span class="sxs-lookup"><span data-stu-id="6e80f-119">This attribute is of type <xref:System.ServiceModel.PeerTransportCredentialType>.</span></span>|  
  
## <a name="credentialtype-attribute"></a><span data-ttu-id="6e80f-120">credentialType 属性</span><span class="sxs-lookup"><span data-stu-id="6e80f-120">credentialType Attribute</span></span>  
  
|<span data-ttu-id="6e80f-121">“值”</span><span class="sxs-lookup"><span data-stu-id="6e80f-121">Value</span></span>|<span data-ttu-id="6e80f-122">描述</span><span class="sxs-lookup"><span data-stu-id="6e80f-122">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="6e80f-123">证书</span><span class="sxs-lookup"><span data-stu-id="6e80f-123">Certificate</span></span>|<span data-ttu-id="6e80f-124">对等通道传输的身份验证需要 X509 证书。</span><span class="sxs-lookup"><span data-stu-id="6e80f-124">Authentication of the peer channel transport requires an X509 certificate.</span></span>|  
|<span data-ttu-id="6e80f-125">Password</span><span class="sxs-lookup"><span data-stu-id="6e80f-125">Password</span></span>|<span data-ttu-id="6e80f-126">对等通道传输的身份验证需要正确的密码。</span><span class="sxs-lookup"><span data-stu-id="6e80f-126">Authentication of the peer channel transport requires a correct password.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="6e80f-127">子元素</span><span class="sxs-lookup"><span data-stu-id="6e80f-127">Child Elements</span></span>  
 <span data-ttu-id="6e80f-128">None</span><span class="sxs-lookup"><span data-stu-id="6e80f-128">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="6e80f-129">父元素</span><span class="sxs-lookup"><span data-stu-id="6e80f-129">Parent Elements</span></span>  
  
|<span data-ttu-id="6e80f-130">元素</span><span class="sxs-lookup"><span data-stu-id="6e80f-130">Element</span></span>|<span data-ttu-id="6e80f-131">描述</span><span class="sxs-lookup"><span data-stu-id="6e80f-131">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="6e80f-132">\<安全 ></span><span class="sxs-lookup"><span data-stu-id="6e80f-132">\<security></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/security-of-netpeerbinding.md)|<span data-ttu-id="6e80f-133">定义的安全设置[ \<netPeerTcpBinding >](../../../../../docs/framework/configure-apps/file-schema/wcf/netpeertcpbinding.md)。</span><span class="sxs-lookup"><span data-stu-id="6e80f-133">Defines the security settings for the [\<netPeerTcpBinding>](../../../../../docs/framework/configure-apps/file-schema/wcf/netpeertcpbinding.md).</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="6e80f-134">请参阅</span><span class="sxs-lookup"><span data-stu-id="6e80f-134">See also</span></span>

- <xref:System.ServiceModel.Configuration.PeerTransportSecurityElement>
- <xref:System.ServiceModel.PeerSecuritySettings.Transport%2A>
- <xref:System.ServiceModel.Configuration.PeerSecurityElement.Transport%2A>
- <xref:System.ServiceModel.PeerTransportSecuritySettings>
- [<span data-ttu-id="6e80f-135">保护服务和客户端的安全</span><span class="sxs-lookup"><span data-stu-id="6e80f-135">Securing Services and Clients</span></span>](../../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)
- [<span data-ttu-id="6e80f-136">绑定</span><span class="sxs-lookup"><span data-stu-id="6e80f-136">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)
- [<span data-ttu-id="6e80f-137">配置系统提供的绑定</span><span class="sxs-lookup"><span data-stu-id="6e80f-137">Configuring System-Provided Bindings</span></span>](../../../../../docs/framework/wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="6e80f-138">使用绑定配置服务和客户端</span><span class="sxs-lookup"><span data-stu-id="6e80f-138">Using Bindings to Configure Services and Clients</span></span>](../../../../../docs/framework/wcf/using-bindings-to-configure-services-and-clients.md)
- [<span data-ttu-id="6e80f-139">\<binding></span><span class="sxs-lookup"><span data-stu-id="6e80f-139">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)
