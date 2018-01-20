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
ms.openlocfilehash: 6cc5e0b2aa52c8fa37e6148f66dc24fca273a640
ms.sourcegitcommit: c0dd436f6f8f44dc80dc43b07f6841a00b74b23f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/19/2018
---
# <a name="lttransportgt-of-ltnetpeertcpbindinggt"></a><span data-ttu-id="78ca0-102">&lt;netPeerTcpBinding&gt; 的 &lt;transport&gt;</span><span class="sxs-lookup"><span data-stu-id="78ca0-102">&lt;transport&gt; of &lt;netPeerTcpBinding&gt;</span></span>
<span data-ttu-id="78ca0-103">指定的传输级安全设置时使用[ \<netPeerTcpBinding >](../../../../../docs/framework/configure-apps/file-schema/wcf/netpeertcpbinding.md)。</span><span class="sxs-lookup"><span data-stu-id="78ca0-103">Specifies settings for transport level security when using the [\<netPeerTcpBinding>](../../../../../docs/framework/configure-apps/file-schema/wcf/netpeertcpbinding.md).</span></span>  
  
 <span data-ttu-id="78ca0-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="78ca0-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="78ca0-105">\<bindings></span><span class="sxs-lookup"><span data-stu-id="78ca0-105">\<bindings></span></span>  
<span data-ttu-id="78ca0-106">\<netPeerTcpBinding></span><span class="sxs-lookup"><span data-stu-id="78ca0-106">\<netPeerTcpBinding></span></span>  
<span data-ttu-id="78ca0-107">\<binding></span><span class="sxs-lookup"><span data-stu-id="78ca0-107">\<binding></span></span>  
<span data-ttu-id="78ca0-108">\<security></span><span class="sxs-lookup"><span data-stu-id="78ca0-108">\<security></span></span>  
<span data-ttu-id="78ca0-109">\<transport></span><span class="sxs-lookup"><span data-stu-id="78ca0-109">\<transport></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="78ca0-110">语法</span><span class="sxs-lookup"><span data-stu-id="78ca0-110">Syntax</span></span>  
  
```xml  
<netPeerTcpBinding>  
    <binding>  
        <security>  
            <transport credentialType="Certificate/Password" />  
        </security>         
    </binding>  
</netPeerTcpBinding>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="78ca0-111">特性和元素</span><span class="sxs-lookup"><span data-stu-id="78ca0-111">Attributes and Elements</span></span>  
 <span data-ttu-id="78ca0-112">以下几节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="78ca0-112">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="78ca0-113">特性</span><span class="sxs-lookup"><span data-stu-id="78ca0-113">Attributes</span></span>  
  
|<span data-ttu-id="78ca0-114">特性</span><span class="sxs-lookup"><span data-stu-id="78ca0-114">Attribute</span></span>|<span data-ttu-id="78ca0-115">描述</span><span class="sxs-lookup"><span data-stu-id="78ca0-115">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="78ca0-116">credentialType</span><span class="sxs-lookup"><span data-stu-id="78ca0-116">credentialType</span></span>|<span data-ttu-id="78ca0-117">可选。</span><span class="sxs-lookup"><span data-stu-id="78ca0-117">Optional.</span></span> <span data-ttu-id="78ca0-118">指定用于验证通过对等传输发送的消息的凭据的类型。</span><span class="sxs-lookup"><span data-stu-id="78ca0-118">Specifies the type of credentials used to verify messages sent with the peer transport.</span></span> <span data-ttu-id="78ca0-119">此属性的类型为 <xref:System.ServiceModel.PeerTransportCredentialType>。</span><span class="sxs-lookup"><span data-stu-id="78ca0-119">This attribute is of type <xref:System.ServiceModel.PeerTransportCredentialType>.</span></span>|  
  
## <a name="credentialtype-attribute"></a><span data-ttu-id="78ca0-120">credentialType 属性</span><span class="sxs-lookup"><span data-stu-id="78ca0-120">credentialType Attribute</span></span>  
  
|<span data-ttu-id="78ca0-121">值</span><span class="sxs-lookup"><span data-stu-id="78ca0-121">Value</span></span>|<span data-ttu-id="78ca0-122">描述</span><span class="sxs-lookup"><span data-stu-id="78ca0-122">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="78ca0-123">证书</span><span class="sxs-lookup"><span data-stu-id="78ca0-123">Certificate</span></span>|<span data-ttu-id="78ca0-124">对等通道传输的身份验证需要 X509 证书。</span><span class="sxs-lookup"><span data-stu-id="78ca0-124">Authentication of the peer channel transport requires an X509 certificate.</span></span>|  
|<span data-ttu-id="78ca0-125">密码</span><span class="sxs-lookup"><span data-stu-id="78ca0-125">Password</span></span>|<span data-ttu-id="78ca0-126">对等通道传输的身份验证需要正确的密码。</span><span class="sxs-lookup"><span data-stu-id="78ca0-126">Authentication of the peer channel transport requires a correct password.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="78ca0-127">子元素</span><span class="sxs-lookup"><span data-stu-id="78ca0-127">Child Elements</span></span>  
 <span data-ttu-id="78ca0-128">无</span><span class="sxs-lookup"><span data-stu-id="78ca0-128">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="78ca0-129">父元素</span><span class="sxs-lookup"><span data-stu-id="78ca0-129">Parent Elements</span></span>  
  
|<span data-ttu-id="78ca0-130">元素</span><span class="sxs-lookup"><span data-stu-id="78ca0-130">Element</span></span>|<span data-ttu-id="78ca0-131">描述</span><span class="sxs-lookup"><span data-stu-id="78ca0-131">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="78ca0-132">\<security></span><span class="sxs-lookup"><span data-stu-id="78ca0-132">\<security></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/security-of-netpeerbinding.md)|<span data-ttu-id="78ca0-133">定义的安全设置[ \<netPeerTcpBinding >](../../../../../docs/framework/configure-apps/file-schema/wcf/netpeertcpbinding.md)。</span><span class="sxs-lookup"><span data-stu-id="78ca0-133">Defines the security settings for the [\<netPeerTcpBinding>](../../../../../docs/framework/configure-apps/file-schema/wcf/netpeertcpbinding.md).</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="78ca0-134">请参阅</span><span class="sxs-lookup"><span data-stu-id="78ca0-134">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.PeerTransportSecurityElement>  
 <xref:System.ServiceModel.PeerSecuritySettings.Transport%2A>  
 <xref:System.ServiceModel.Configuration.PeerSecurityElement.Transport%2A>  
 <xref:System.ServiceModel.PeerTransportSecuritySettings>  
 [<span data-ttu-id="78ca0-135">保护服务和客户端的安全</span><span class="sxs-lookup"><span data-stu-id="78ca0-135">Securing Services and Clients</span></span>](../../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)  
 [<span data-ttu-id="78ca0-136">绑定</span><span class="sxs-lookup"><span data-stu-id="78ca0-136">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)  
 [<span data-ttu-id="78ca0-137">配置系统提供的绑定</span><span class="sxs-lookup"><span data-stu-id="78ca0-137">Configuring System-Provided Bindings</span></span>](../../../../../docs/framework/wcf/feature-details/configuring-system-provided-bindings.md)  
 [<span data-ttu-id="78ca0-138">使用绑定来配置 Windows Communication Foundation 服务和客户端</span><span class="sxs-lookup"><span data-stu-id="78ca0-138">Using Bindings to Configure Windows Communication Foundation Services and Clients</span></span>](http://msdn.microsoft.com/library/bd8b277b-932f-472f-a42a-b02bb5257dfb)  
 [<span data-ttu-id="78ca0-139">\<binding></span><span class="sxs-lookup"><span data-stu-id="78ca0-139">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)
