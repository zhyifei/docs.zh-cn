---
title: <transport> 的 <netPeerTcpBinding>
ms.date: 03/30/2017
ms.assetid: c44d86d2-1160-44d7-9c7a-297b12eccc7f
ms.openlocfilehash: 837d01540fa63579877ab4085bd8034c78f2fbe0
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2019
ms.locfileid: "69915565"
---
# <a name="transport-of-netpeertcpbinding"></a><span data-ttu-id="77506-102">\<netPeerTcpBinding > 的\<传输 ></span><span class="sxs-lookup"><span data-stu-id="77506-102">\<transport> of \<netPeerTcpBinding></span></span>
<span data-ttu-id="77506-103">指定使用[ \<netPeerTcpBinding >](netpeertcpbinding.md)时的传输级安全性设置。</span><span class="sxs-lookup"><span data-stu-id="77506-103">Specifies settings for transport level security when using the [\<netPeerTcpBinding>](netpeertcpbinding.md).</span></span>  
  
 <span data-ttu-id="77506-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="77506-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="77506-105">\<bindings></span><span class="sxs-lookup"><span data-stu-id="77506-105">\<bindings></span></span>  
<span data-ttu-id="77506-106">\<netPeerTcpBinding></span><span class="sxs-lookup"><span data-stu-id="77506-106">\<netPeerTcpBinding></span></span>  
<span data-ttu-id="77506-107">\<绑定 ></span><span class="sxs-lookup"><span data-stu-id="77506-107">\<binding></span></span>  
<span data-ttu-id="77506-108">\<安全 ></span><span class="sxs-lookup"><span data-stu-id="77506-108">\<security></span></span>  
<span data-ttu-id="77506-109">\<transport></span><span class="sxs-lookup"><span data-stu-id="77506-109">\<transport></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="77506-110">语法</span><span class="sxs-lookup"><span data-stu-id="77506-110">Syntax</span></span>  
  
```xml  
<netPeerTcpBinding>
  <binding>
    <security>
      <transport credentialType="Certificate/Password" />
    </security>
  </binding>
</netPeerTcpBinding>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="77506-111">特性和元素</span><span class="sxs-lookup"><span data-stu-id="77506-111">Attributes and Elements</span></span>  
 <span data-ttu-id="77506-112">以下几节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="77506-112">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="77506-113">特性</span><span class="sxs-lookup"><span data-stu-id="77506-113">Attributes</span></span>  
  
|<span data-ttu-id="77506-114">特性</span><span class="sxs-lookup"><span data-stu-id="77506-114">Attribute</span></span>|<span data-ttu-id="77506-115">描述</span><span class="sxs-lookup"><span data-stu-id="77506-115">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="77506-116">credentialType</span><span class="sxs-lookup"><span data-stu-id="77506-116">credentialType</span></span>|<span data-ttu-id="77506-117">可选。</span><span class="sxs-lookup"><span data-stu-id="77506-117">Optional.</span></span> <span data-ttu-id="77506-118">指定用于验证通过对等传输发送的消息的凭据的类型。</span><span class="sxs-lookup"><span data-stu-id="77506-118">Specifies the type of credentials used to verify messages sent with the peer transport.</span></span> <span data-ttu-id="77506-119">此属性的类型为 <xref:System.ServiceModel.PeerTransportCredentialType>。</span><span class="sxs-lookup"><span data-stu-id="77506-119">This attribute is of type <xref:System.ServiceModel.PeerTransportCredentialType>.</span></span>|  
  
## <a name="credentialtype-attribute"></a><span data-ttu-id="77506-120">credentialType 属性</span><span class="sxs-lookup"><span data-stu-id="77506-120">credentialType Attribute</span></span>  
  
|<span data-ttu-id="77506-121">值</span><span class="sxs-lookup"><span data-stu-id="77506-121">Value</span></span>|<span data-ttu-id="77506-122">描述</span><span class="sxs-lookup"><span data-stu-id="77506-122">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="77506-123">证书</span><span class="sxs-lookup"><span data-stu-id="77506-123">Certificate</span></span>|<span data-ttu-id="77506-124">对等通道传输的身份验证需要 X509 证书。</span><span class="sxs-lookup"><span data-stu-id="77506-124">Authentication of the peer channel transport requires an X509 certificate.</span></span>|  
|<span data-ttu-id="77506-125">Password</span><span class="sxs-lookup"><span data-stu-id="77506-125">Password</span></span>|<span data-ttu-id="77506-126">对等通道传输的身份验证需要正确的密码。</span><span class="sxs-lookup"><span data-stu-id="77506-126">Authentication of the peer channel transport requires a correct password.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="77506-127">子元素</span><span class="sxs-lookup"><span data-stu-id="77506-127">Child Elements</span></span>  
 <span data-ttu-id="77506-128">无</span><span class="sxs-lookup"><span data-stu-id="77506-128">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="77506-129">父元素</span><span class="sxs-lookup"><span data-stu-id="77506-129">Parent Elements</span></span>  
  
|<span data-ttu-id="77506-130">元素</span><span class="sxs-lookup"><span data-stu-id="77506-130">Element</span></span>|<span data-ttu-id="77506-131">描述</span><span class="sxs-lookup"><span data-stu-id="77506-131">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="77506-132">\<security></span><span class="sxs-lookup"><span data-stu-id="77506-132">\<security></span></span>](security-of-netpeerbinding.md)|<span data-ttu-id="77506-133">定义[ \<netPeerTcpBinding >](netpeertcpbinding.md)的安全设置。</span><span class="sxs-lookup"><span data-stu-id="77506-133">Defines the security settings for the [\<netPeerTcpBinding>](netpeertcpbinding.md).</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="77506-134">请参阅</span><span class="sxs-lookup"><span data-stu-id="77506-134">See also</span></span>

- <xref:System.ServiceModel.Configuration.PeerTransportSecurityElement>
- <xref:System.ServiceModel.PeerSecuritySettings.Transport%2A>
- <xref:System.ServiceModel.Configuration.PeerSecurityElement.Transport%2A>
- <xref:System.ServiceModel.PeerTransportSecuritySettings>
- [<span data-ttu-id="77506-135">保护服务和客户端的安全</span><span class="sxs-lookup"><span data-stu-id="77506-135">Securing Services and Clients</span></span>](../../../wcf/feature-details/securing-services-and-clients.md)
- [<span data-ttu-id="77506-136">绑定</span><span class="sxs-lookup"><span data-stu-id="77506-136">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="77506-137">配置系统提供的绑定</span><span class="sxs-lookup"><span data-stu-id="77506-137">Configuring System-Provided Bindings</span></span>](../../../wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="77506-138">使用绑定配置服务和客户端</span><span class="sxs-lookup"><span data-stu-id="77506-138">Using Bindings to Configure Services and Clients</span></span>](../../../wcf/using-bindings-to-configure-services-and-clients.md)
- [<span data-ttu-id="77506-139">\<binding></span><span class="sxs-lookup"><span data-stu-id="77506-139">\<binding></span></span>](../../../misc/binding.md)
