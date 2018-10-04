---
title: '&lt;netPeerTcpBinding&gt; 的 &lt;transport&gt;'
ms.date: 03/30/2017
ms.assetid: c44d86d2-1160-44d7-9c7a-297b12eccc7f
ms.openlocfilehash: 62ba3b27b10afe182623f3be0f6738940e194579
ms.sourcegitcommit: 69229651598b427c550223d3c58aba82e47b3f82
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/04/2018
ms.locfileid: "48579785"
---
# <a name="lttransportgt-of-ltnetpeertcpbindinggt"></a><span data-ttu-id="9ba94-102">&lt;netPeerTcpBinding&gt; 的 &lt;transport&gt;</span><span class="sxs-lookup"><span data-stu-id="9ba94-102">&lt;transport&gt; of &lt;netPeerTcpBinding&gt;</span></span>
<span data-ttu-id="9ba94-103">使用时指定的传输级安全设置[ \<netPeerTcpBinding >](../../../../../docs/framework/configure-apps/file-schema/wcf/netpeertcpbinding.md)。</span><span class="sxs-lookup"><span data-stu-id="9ba94-103">Specifies settings for transport level security when using the [\<netPeerTcpBinding>](../../../../../docs/framework/configure-apps/file-schema/wcf/netpeertcpbinding.md).</span></span>  
  
 <span data-ttu-id="9ba94-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="9ba94-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="9ba94-105">\<绑定 ></span><span class="sxs-lookup"><span data-stu-id="9ba94-105">\<bindings></span></span>  
<span data-ttu-id="9ba94-106">\<netPeerTcpBinding></span><span class="sxs-lookup"><span data-stu-id="9ba94-106">\<netPeerTcpBinding></span></span>  
<span data-ttu-id="9ba94-107">\<绑定 ></span><span class="sxs-lookup"><span data-stu-id="9ba94-107">\<binding></span></span>  
<span data-ttu-id="9ba94-108">\<安全 ></span><span class="sxs-lookup"><span data-stu-id="9ba94-108">\<security></span></span>  
<span data-ttu-id="9ba94-109">\<transport></span><span class="sxs-lookup"><span data-stu-id="9ba94-109">\<transport></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9ba94-110">语法</span><span class="sxs-lookup"><span data-stu-id="9ba94-110">Syntax</span></span>  
  
```xml  
<netPeerTcpBinding>  
    <binding>  
        <security>  
            <transport credentialType="Certificate/Password" />  
        </security>         
    </binding>  
</netPeerTcpBinding>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="9ba94-111">特性和元素</span><span class="sxs-lookup"><span data-stu-id="9ba94-111">Attributes and Elements</span></span>  
 <span data-ttu-id="9ba94-112">以下几节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="9ba94-112">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="9ba94-113">特性</span><span class="sxs-lookup"><span data-stu-id="9ba94-113">Attributes</span></span>  
  
|<span data-ttu-id="9ba94-114">特性</span><span class="sxs-lookup"><span data-stu-id="9ba94-114">Attribute</span></span>|<span data-ttu-id="9ba94-115">描述</span><span class="sxs-lookup"><span data-stu-id="9ba94-115">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="9ba94-116">credentialType</span><span class="sxs-lookup"><span data-stu-id="9ba94-116">credentialType</span></span>|<span data-ttu-id="9ba94-117">可选。</span><span class="sxs-lookup"><span data-stu-id="9ba94-117">Optional.</span></span> <span data-ttu-id="9ba94-118">指定用于验证通过对等传输发送的消息的凭据的类型。</span><span class="sxs-lookup"><span data-stu-id="9ba94-118">Specifies the type of credentials used to verify messages sent with the peer transport.</span></span> <span data-ttu-id="9ba94-119">此属性的类型为 <xref:System.ServiceModel.PeerTransportCredentialType>。</span><span class="sxs-lookup"><span data-stu-id="9ba94-119">This attribute is of type <xref:System.ServiceModel.PeerTransportCredentialType>.</span></span>|  
  
## <a name="credentialtype-attribute"></a><span data-ttu-id="9ba94-120">credentialType 属性</span><span class="sxs-lookup"><span data-stu-id="9ba94-120">credentialType Attribute</span></span>  
  
|<span data-ttu-id="9ba94-121">值</span><span class="sxs-lookup"><span data-stu-id="9ba94-121">Value</span></span>|<span data-ttu-id="9ba94-122">描述</span><span class="sxs-lookup"><span data-stu-id="9ba94-122">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="9ba94-123">证书</span><span class="sxs-lookup"><span data-stu-id="9ba94-123">Certificate</span></span>|<span data-ttu-id="9ba94-124">对等通道传输的身份验证需要 X509 证书。</span><span class="sxs-lookup"><span data-stu-id="9ba94-124">Authentication of the peer channel transport requires an X509 certificate.</span></span>|  
|<span data-ttu-id="9ba94-125">密码</span><span class="sxs-lookup"><span data-stu-id="9ba94-125">Password</span></span>|<span data-ttu-id="9ba94-126">对等通道传输的身份验证需要正确的密码。</span><span class="sxs-lookup"><span data-stu-id="9ba94-126">Authentication of the peer channel transport requires a correct password.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="9ba94-127">子元素</span><span class="sxs-lookup"><span data-stu-id="9ba94-127">Child Elements</span></span>  
 <span data-ttu-id="9ba94-128">无</span><span class="sxs-lookup"><span data-stu-id="9ba94-128">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="9ba94-129">父元素</span><span class="sxs-lookup"><span data-stu-id="9ba94-129">Parent Elements</span></span>  
  
|<span data-ttu-id="9ba94-130">元素</span><span class="sxs-lookup"><span data-stu-id="9ba94-130">Element</span></span>|<span data-ttu-id="9ba94-131">描述</span><span class="sxs-lookup"><span data-stu-id="9ba94-131">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="9ba94-132">\<security></span><span class="sxs-lookup"><span data-stu-id="9ba94-132">\<security></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/security-of-netpeerbinding.md)|<span data-ttu-id="9ba94-133">定义的安全设置[ \<netPeerTcpBinding >](../../../../../docs/framework/configure-apps/file-schema/wcf/netpeertcpbinding.md)。</span><span class="sxs-lookup"><span data-stu-id="9ba94-133">Defines the security settings for the [\<netPeerTcpBinding>](../../../../../docs/framework/configure-apps/file-schema/wcf/netpeertcpbinding.md).</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="9ba94-134">请参阅</span><span class="sxs-lookup"><span data-stu-id="9ba94-134">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.PeerTransportSecurityElement>  
 <xref:System.ServiceModel.PeerSecuritySettings.Transport%2A>  
 <xref:System.ServiceModel.Configuration.PeerSecurityElement.Transport%2A>  
 <xref:System.ServiceModel.PeerTransportSecuritySettings>  
 [<span data-ttu-id="9ba94-135">保护服务和客户端的安全</span><span class="sxs-lookup"><span data-stu-id="9ba94-135">Securing Services and Clients</span></span>](../../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)  
 [<span data-ttu-id="9ba94-136">绑定</span><span class="sxs-lookup"><span data-stu-id="9ba94-136">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)  
 [<span data-ttu-id="9ba94-137">配置系统提供的绑定</span><span class="sxs-lookup"><span data-stu-id="9ba94-137">Configuring System-Provided Bindings</span></span>](../../../../../docs/framework/wcf/feature-details/configuring-system-provided-bindings.md)  
 [<span data-ttu-id="9ba94-138">使用绑定配置服务和客户端</span><span class="sxs-lookup"><span data-stu-id="9ba94-138">Using Bindings to Configure Services and Clients</span></span>](../../../../../docs/framework/wcf/using-bindings-to-configure-services-and-clients.md)  
 [<span data-ttu-id="9ba94-139">\<绑定 ></span><span class="sxs-lookup"><span data-stu-id="9ba94-139">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)
