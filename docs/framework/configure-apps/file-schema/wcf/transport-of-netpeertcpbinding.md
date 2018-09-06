---
title: '&lt;netPeerTcpBinding&gt; 的 &lt;transport&gt;'
ms.date: 03/30/2017
ms.assetid: c44d86d2-1160-44d7-9c7a-297b12eccc7f
ms.openlocfilehash: 2b89ae090d24ff6aad1aae1b39a0a18961bd2537
ms.sourcegitcommit: a885cc8c3e444ca6471348893d5373c6e9e49a47
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/06/2018
ms.locfileid: "43869774"
---
# <a name="lttransportgt-of-ltnetpeertcpbindinggt"></a><span data-ttu-id="acd34-102">&lt;netPeerTcpBinding&gt; 的 &lt;transport&gt;</span><span class="sxs-lookup"><span data-stu-id="acd34-102">&lt;transport&gt; of &lt;netPeerTcpBinding&gt;</span></span>
<span data-ttu-id="acd34-103">使用时指定的传输级安全设置[ \<netPeerTcpBinding >](../../../../../docs/framework/configure-apps/file-schema/wcf/netpeertcpbinding.md)。</span><span class="sxs-lookup"><span data-stu-id="acd34-103">Specifies settings for transport level security when using the [\<netPeerTcpBinding>](../../../../../docs/framework/configure-apps/file-schema/wcf/netpeertcpbinding.md).</span></span>  
  
 <span data-ttu-id="acd34-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="acd34-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="acd34-105">\<绑定 ></span><span class="sxs-lookup"><span data-stu-id="acd34-105">\<bindings></span></span>  
<span data-ttu-id="acd34-106">\<netPeerTcpBinding></span><span class="sxs-lookup"><span data-stu-id="acd34-106">\<netPeerTcpBinding></span></span>  
<span data-ttu-id="acd34-107">\<绑定 ></span><span class="sxs-lookup"><span data-stu-id="acd34-107">\<binding></span></span>  
<span data-ttu-id="acd34-108">\<安全 ></span><span class="sxs-lookup"><span data-stu-id="acd34-108">\<security></span></span>  
<span data-ttu-id="acd34-109">\<transport></span><span class="sxs-lookup"><span data-stu-id="acd34-109">\<transport></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="acd34-110">语法</span><span class="sxs-lookup"><span data-stu-id="acd34-110">Syntax</span></span>  
  
```xml  
<netPeerTcpBinding>  
    <binding>  
        <security>  
            <transport credentialType="Certificate/Password" />  
        </security>         
    </binding>  
</netPeerTcpBinding>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="acd34-111">特性和元素</span><span class="sxs-lookup"><span data-stu-id="acd34-111">Attributes and Elements</span></span>  
 <span data-ttu-id="acd34-112">以下几节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="acd34-112">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="acd34-113">特性</span><span class="sxs-lookup"><span data-stu-id="acd34-113">Attributes</span></span>  
  
|<span data-ttu-id="acd34-114">特性</span><span class="sxs-lookup"><span data-stu-id="acd34-114">Attribute</span></span>|<span data-ttu-id="acd34-115">描述</span><span class="sxs-lookup"><span data-stu-id="acd34-115">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="acd34-116">credentialType</span><span class="sxs-lookup"><span data-stu-id="acd34-116">credentialType</span></span>|<span data-ttu-id="acd34-117">可选。</span><span class="sxs-lookup"><span data-stu-id="acd34-117">Optional.</span></span> <span data-ttu-id="acd34-118">指定用于验证通过对等传输发送的消息的凭据的类型。</span><span class="sxs-lookup"><span data-stu-id="acd34-118">Specifies the type of credentials used to verify messages sent with the peer transport.</span></span> <span data-ttu-id="acd34-119">此属性的类型为 <xref:System.ServiceModel.PeerTransportCredentialType>。</span><span class="sxs-lookup"><span data-stu-id="acd34-119">This attribute is of type <xref:System.ServiceModel.PeerTransportCredentialType>.</span></span>|  
  
## <a name="credentialtype-attribute"></a><span data-ttu-id="acd34-120">credentialType 属性</span><span class="sxs-lookup"><span data-stu-id="acd34-120">credentialType Attribute</span></span>  
  
|<span data-ttu-id="acd34-121">值</span><span class="sxs-lookup"><span data-stu-id="acd34-121">Value</span></span>|<span data-ttu-id="acd34-122">描述</span><span class="sxs-lookup"><span data-stu-id="acd34-122">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="acd34-123">证书</span><span class="sxs-lookup"><span data-stu-id="acd34-123">Certificate</span></span>|<span data-ttu-id="acd34-124">对等通道传输的身份验证需要 X509 证书。</span><span class="sxs-lookup"><span data-stu-id="acd34-124">Authentication of the peer channel transport requires an X509 certificate.</span></span>|  
|<span data-ttu-id="acd34-125">密码</span><span class="sxs-lookup"><span data-stu-id="acd34-125">Password</span></span>|<span data-ttu-id="acd34-126">对等通道传输的身份验证需要正确的密码。</span><span class="sxs-lookup"><span data-stu-id="acd34-126">Authentication of the peer channel transport requires a correct password.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="acd34-127">子元素</span><span class="sxs-lookup"><span data-stu-id="acd34-127">Child Elements</span></span>  
 <span data-ttu-id="acd34-128">无</span><span class="sxs-lookup"><span data-stu-id="acd34-128">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="acd34-129">父元素</span><span class="sxs-lookup"><span data-stu-id="acd34-129">Parent Elements</span></span>  
  
|<span data-ttu-id="acd34-130">元素</span><span class="sxs-lookup"><span data-stu-id="acd34-130">Element</span></span>|<span data-ttu-id="acd34-131">描述</span><span class="sxs-lookup"><span data-stu-id="acd34-131">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="acd34-132">\<security></span><span class="sxs-lookup"><span data-stu-id="acd34-132">\<security></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/security-of-netpeerbinding.md)|<span data-ttu-id="acd34-133">定义的安全设置[ \<netPeerTcpBinding >](../../../../../docs/framework/configure-apps/file-schema/wcf/netpeertcpbinding.md)。</span><span class="sxs-lookup"><span data-stu-id="acd34-133">Defines the security settings for the [\<netPeerTcpBinding>](../../../../../docs/framework/configure-apps/file-schema/wcf/netpeertcpbinding.md).</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="acd34-134">请参阅</span><span class="sxs-lookup"><span data-stu-id="acd34-134">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.PeerTransportSecurityElement>  
 <xref:System.ServiceModel.PeerSecuritySettings.Transport%2A>  
 <xref:System.ServiceModel.Configuration.PeerSecurityElement.Transport%2A>  
 <xref:System.ServiceModel.PeerTransportSecuritySettings>  
 [<span data-ttu-id="acd34-135">保护服务和客户端的安全</span><span class="sxs-lookup"><span data-stu-id="acd34-135">Securing Services and Clients</span></span>](../../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)  
 [<span data-ttu-id="acd34-136">绑定</span><span class="sxs-lookup"><span data-stu-id="acd34-136">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)  
 [<span data-ttu-id="acd34-137">配置系统提供的绑定</span><span class="sxs-lookup"><span data-stu-id="acd34-137">Configuring System-Provided Bindings</span></span>](../../../../../docs/framework/wcf/feature-details/configuring-system-provided-bindings.md)  
 [<span data-ttu-id="acd34-138">使用绑定来配置 Windows Communication Foundation 服务和客户端</span><span class="sxs-lookup"><span data-stu-id="acd34-138">Using Bindings to Configure Windows Communication Foundation Services and Clients</span></span>](https://msdn.microsoft.com/library/bd8b277b-932f-472f-a42a-b02bb5257dfb)  
 [<span data-ttu-id="acd34-139">\<绑定 ></span><span class="sxs-lookup"><span data-stu-id="acd34-139">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)
