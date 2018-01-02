---
title: "&lt;netPeerTcpBinding&gt; 的 &lt;transport&gt;"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: c44d86d2-1160-44d7-9c7a-297b12eccc7f
caps.latest.revision: "16"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: ed3e933e1c3468a09b1d6b089b4abf52dad85017
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="lttransportgt-of-ltnetpeertcpbindinggt"></a><span data-ttu-id="2924c-102">&lt;netPeerTcpBinding&gt; 的 &lt;transport&gt;</span><span class="sxs-lookup"><span data-stu-id="2924c-102">&lt;transport&gt; of &lt;netPeerTcpBinding&gt;</span></span>
<span data-ttu-id="2924c-103">指定的传输级安全设置时使用[ \<netPeerTcpBinding >](../../../../../docs/framework/configure-apps/file-schema/wcf/netpeertcpbinding.md)。</span><span class="sxs-lookup"><span data-stu-id="2924c-103">Specifies settings for transport level security when using the [\<netPeerTcpBinding>](../../../../../docs/framework/configure-apps/file-schema/wcf/netpeertcpbinding.md).</span></span>  
  
 <span data-ttu-id="2924c-104">\<系统。ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="2924c-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="2924c-105">\<绑定 ></span><span class="sxs-lookup"><span data-stu-id="2924c-105">\<bindings></span></span>  
<span data-ttu-id="2924c-106">\<netPeerTcpBinding ></span><span class="sxs-lookup"><span data-stu-id="2924c-106">\<netPeerTcpBinding></span></span>  
<span data-ttu-id="2924c-107">\<绑定 ></span><span class="sxs-lookup"><span data-stu-id="2924c-107">\<binding></span></span>  
<span data-ttu-id="2924c-108">\<安全 ></span><span class="sxs-lookup"><span data-stu-id="2924c-108">\<security></span></span>  
<span data-ttu-id="2924c-109">\<传输 ></span><span class="sxs-lookup"><span data-stu-id="2924c-109">\<transport></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2924c-110">语法</span><span class="sxs-lookup"><span data-stu-id="2924c-110">Syntax</span></span>  
  
```xml  
<netPeerTcpBinding>  
    <binding>  
        <security>  
            <transport credentialType="Certificate/Password" />  
        </security>         
    </binding>  
</netPeerTcpBinding>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="2924c-111">特性和元素</span><span class="sxs-lookup"><span data-stu-id="2924c-111">Attributes and Elements</span></span>  
 <span data-ttu-id="2924c-112">以下几节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="2924c-112">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="2924c-113">特性</span><span class="sxs-lookup"><span data-stu-id="2924c-113">Attributes</span></span>  
  
|<span data-ttu-id="2924c-114">特性</span><span class="sxs-lookup"><span data-stu-id="2924c-114">Attribute</span></span>|<span data-ttu-id="2924c-115">描述</span><span class="sxs-lookup"><span data-stu-id="2924c-115">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="2924c-116">credentialType</span><span class="sxs-lookup"><span data-stu-id="2924c-116">credentialType</span></span>|<span data-ttu-id="2924c-117">可选。</span><span class="sxs-lookup"><span data-stu-id="2924c-117">Optional.</span></span> <span data-ttu-id="2924c-118">指定用于验证通过对等传输发送的消息的凭据的类型。</span><span class="sxs-lookup"><span data-stu-id="2924c-118">Specifies the type of credentials used to verify messages sent with the peer transport.</span></span> <span data-ttu-id="2924c-119">此属性的类型为 <xref:System.ServiceModel.PeerTransportCredentialType>。</span><span class="sxs-lookup"><span data-stu-id="2924c-119">This attribute is of type <xref:System.ServiceModel.PeerTransportCredentialType>.</span></span>|  
  
## <a name="credentialtype-attribute"></a><span data-ttu-id="2924c-120">credentialType 属性</span><span class="sxs-lookup"><span data-stu-id="2924c-120">credentialType Attribute</span></span>  
  
|<span data-ttu-id="2924c-121">值</span><span class="sxs-lookup"><span data-stu-id="2924c-121">Value</span></span>|<span data-ttu-id="2924c-122">描述</span><span class="sxs-lookup"><span data-stu-id="2924c-122">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="2924c-123">证书</span><span class="sxs-lookup"><span data-stu-id="2924c-123">Certificate</span></span>|<span data-ttu-id="2924c-124">对等通道传输的身份验证需要 X509 证书。</span><span class="sxs-lookup"><span data-stu-id="2924c-124">Authentication of the peer channel transport requires an X509 certificate.</span></span>|  
|<span data-ttu-id="2924c-125">密码</span><span class="sxs-lookup"><span data-stu-id="2924c-125">Password</span></span>|<span data-ttu-id="2924c-126">对等通道传输的身份验证需要正确的密码。</span><span class="sxs-lookup"><span data-stu-id="2924c-126">Authentication of the peer channel transport requires a correct password.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="2924c-127">子元素</span><span class="sxs-lookup"><span data-stu-id="2924c-127">Child Elements</span></span>  
 <span data-ttu-id="2924c-128">无</span><span class="sxs-lookup"><span data-stu-id="2924c-128">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="2924c-129">父元素</span><span class="sxs-lookup"><span data-stu-id="2924c-129">Parent Elements</span></span>  
  
|<span data-ttu-id="2924c-130">元素</span><span class="sxs-lookup"><span data-stu-id="2924c-130">Element</span></span>|<span data-ttu-id="2924c-131">描述</span><span class="sxs-lookup"><span data-stu-id="2924c-131">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="2924c-132">\<安全 ></span><span class="sxs-lookup"><span data-stu-id="2924c-132">\<security></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/security-of-netpeerbinding.md)|<span data-ttu-id="2924c-133">定义的安全设置[ \<netPeerTcpBinding >](../../../../../docs/framework/configure-apps/file-schema/wcf/netpeertcpbinding.md)。</span><span class="sxs-lookup"><span data-stu-id="2924c-133">Defines the security settings for the [\<netPeerTcpBinding>](../../../../../docs/framework/configure-apps/file-schema/wcf/netpeertcpbinding.md).</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="2924c-134">请参阅</span><span class="sxs-lookup"><span data-stu-id="2924c-134">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.PeerTransportSecurityElement>  
 <xref:System.ServiceModel.PeerSecuritySettings.Transport%2A>  
 <xref:System.ServiceModel.Configuration.PeerSecurityElement.Transport%2A>  
 <xref:System.ServiceModel.PeerTransportSecuritySettings>  
 [<span data-ttu-id="2924c-135">保护服务和客户端的安全</span><span class="sxs-lookup"><span data-stu-id="2924c-135">Securing Services and Clients</span></span>](../../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)  
 [<span data-ttu-id="2924c-136">绑定</span><span class="sxs-lookup"><span data-stu-id="2924c-136">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)  
 [<span data-ttu-id="2924c-137">配置系统提供的绑定</span><span class="sxs-lookup"><span data-stu-id="2924c-137">Configuring System-Provided Bindings</span></span>](../../../../../docs/framework/wcf/feature-details/configuring-system-provided-bindings.md)  
 [<span data-ttu-id="2924c-138">使用绑定来配置 Windows Communication Foundation 服务和客户端</span><span class="sxs-lookup"><span data-stu-id="2924c-138">Using Bindings to Configure Windows Communication Foundation Services and Clients</span></span>](http://msdn.microsoft.com/en-us/bd8b277b-932f-472f-a42a-b02bb5257dfb)  
 [<span data-ttu-id="2924c-139">\<绑定 ></span><span class="sxs-lookup"><span data-stu-id="2924c-139">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)
