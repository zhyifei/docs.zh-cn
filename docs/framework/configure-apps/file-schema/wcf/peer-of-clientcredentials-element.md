---
title: "&lt;clientCredentials&gt; 的 &lt;peer&gt; 元素"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 505bd987-0042-4622-b68e-94f439729d53
caps.latest.revision: "10"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: c3479b52c6e06b7b9ebd69d46780e8dca70d2ef7
ms.sourcegitcommit: c0dd436f6f8f44dc80dc43b07f6841a00b74b23f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/19/2018
---
# <a name="ltpeergt-of-ltclientcredentialsgt-element"></a><span data-ttu-id="afa27-102">&lt;clientCredentials&gt; 的 &lt;peer&gt; 元素</span><span class="sxs-lookup"><span data-stu-id="afa27-102">&lt;peer&gt; of &lt;clientCredentials&gt; Element</span></span>
<span data-ttu-id="afa27-103">指定在向对等客户端进行身份验证时使用的凭据。</span><span class="sxs-lookup"><span data-stu-id="afa27-103">Specifies credentials used when authenticating peer-to-peer clients.</span></span>  
  
 <span data-ttu-id="afa27-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="afa27-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="afa27-105">\<behaviors></span><span class="sxs-lookup"><span data-stu-id="afa27-105">\<behaviors></span></span>  
<span data-ttu-id="afa27-106">\<endpointBehaviors></span><span class="sxs-lookup"><span data-stu-id="afa27-106">\<endpointBehaviors></span></span>  
<span data-ttu-id="afa27-107">\<behavior></span><span class="sxs-lookup"><span data-stu-id="afa27-107">\<behavior></span></span>  
<span data-ttu-id="afa27-108">\<clientCredentials></span><span class="sxs-lookup"><span data-stu-id="afa27-108">\<clientCredentials></span></span>  
<span data-ttu-id="afa27-109">\<peer></span><span class="sxs-lookup"><span data-stu-id="afa27-109">\<peer></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="afa27-110">语法</span><span class="sxs-lookup"><span data-stu-id="afa27-110">Syntax</span></span>  
  
```xml  
<peer>  
  <certificate/>  
  <peerAuthentication/>  
  <messageSenderAuthentication/>  
</peer>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="afa27-111">特性和元素</span><span class="sxs-lookup"><span data-stu-id="afa27-111">Attributes and Elements</span></span>  
 <span data-ttu-id="afa27-112">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="afa27-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="afa27-113">特性</span><span class="sxs-lookup"><span data-stu-id="afa27-113">Attributes</span></span>  
 <span data-ttu-id="afa27-114">无。</span><span class="sxs-lookup"><span data-stu-id="afa27-114">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="afa27-115">子元素</span><span class="sxs-lookup"><span data-stu-id="afa27-115">Child Elements</span></span>  
  
|<span data-ttu-id="afa27-116">元素</span><span class="sxs-lookup"><span data-stu-id="afa27-116">Element</span></span>|<span data-ttu-id="afa27-117">描述</span><span class="sxs-lookup"><span data-stu-id="afa27-117">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="afa27-118">\<certificate></span><span class="sxs-lookup"><span data-stu-id="afa27-118">\<certificate></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/certificate-element.md)|<span data-ttu-id="afa27-119">指定要用于为对等客户端的消息进行签名和加密的 X.509 证书。</span><span class="sxs-lookup"><span data-stu-id="afa27-119">Specifies an X.509 certificate to use for signing and encrypting messages for peer-to-peer clients.</span></span> <span data-ttu-id="afa27-120">.</span><span class="sxs-lookup"><span data-stu-id="afa27-120">.</span></span>|  
|[<span data-ttu-id="afa27-121">\<peerAuthentication></span><span class="sxs-lookup"><span data-stu-id="afa27-121">\<peerAuthentication></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/peerauthentication-element.md)|<span data-ttu-id="afa27-122">指定用于对等客户端的身份验证选项。</span><span class="sxs-lookup"><span data-stu-id="afa27-122">Specifies authentication options for peer clients.</span></span>|  
|[<span data-ttu-id="afa27-123">\<messageSenderAuthentication></span><span class="sxs-lookup"><span data-stu-id="afa27-123">\<messageSenderAuthentication></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/messagesenderauthentication-element.md)|<span data-ttu-id="afa27-124">指定用于消息发送方的身份验证选项。</span><span class="sxs-lookup"><span data-stu-id="afa27-124">Specifies authentication options for message senders.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="afa27-125">父元素</span><span class="sxs-lookup"><span data-stu-id="afa27-125">Parent Elements</span></span>  
  
|<span data-ttu-id="afa27-126">元素</span><span class="sxs-lookup"><span data-stu-id="afa27-126">Element</span></span>|<span data-ttu-id="afa27-127">描述</span><span class="sxs-lookup"><span data-stu-id="afa27-127">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="afa27-128">\<clientCredentials></span><span class="sxs-lookup"><span data-stu-id="afa27-128">\<clientCredentials></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/clientcredentials.md)|<span data-ttu-id="afa27-129">指定用于向服务验证客户端身份的凭据。</span><span class="sxs-lookup"><span data-stu-id="afa27-129">Specifies the credentials used to authenticate a client to a service.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="afa27-130">备注</span><span class="sxs-lookup"><span data-stu-id="afa27-130">Remarks</span></span>  
 <span data-ttu-id="afa27-131">此配置元素指定对等节点用于向网格中的其他节点证明它自己的身份的凭据，以及对等节点用于验证其他对等节点的身份的身份验证设置。</span><span class="sxs-lookup"><span data-stu-id="afa27-131">This configuration element specifies the credentials that a peer node uses to authenticate itself to other nodes in the mesh, as well as authentication settings that a peer node uses to authenticate other peer nodes.</span></span> <span data-ttu-id="afa27-132">有关详细信息，请参阅[对等通道消息身份验证](http://msdn.microsoft.com/library/80e73386-514e-4c30-9e4a-b9ca8c173a95)和[保护对等通道应用程序](../../../../../docs/framework/wcf/feature-details/securing-peer-channel-applications.md)。</span><span class="sxs-lookup"><span data-stu-id="afa27-132">For more information, see [Peer Channel Message Authentication](http://msdn.microsoft.com/library/80e73386-514e-4c30-9e4a-b9ca8c173a95) and [Securing Peer Channel Applications](../../../../../docs/framework/wcf/feature-details/securing-peer-channel-applications.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="afa27-133">请参阅</span><span class="sxs-lookup"><span data-stu-id="afa27-133">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.ClientCredentialsElement>  
 <xref:System.ServiceModel.Description.ClientCredentials>  
 <xref:System.ServiceModel.Configuration.PeerCredentialElement>  
 <xref:System.ServiceModel.Configuration.ClientCredentialsElement.Peer%2A>  
 <xref:System.ServiceModel.Description.ClientCredentials>  
 <xref:System.ServiceModel.Description.ClientCredentials.Peer%2A>  
 <xref:System.ServiceModel.Security.PeerCredential>  
 [<span data-ttu-id="afa27-134">对等网络</span><span class="sxs-lookup"><span data-stu-id="afa27-134">Peer-to-Peer Networking</span></span>](../../../../../docs/framework/wcf/feature-details/peer-to-peer-networking.md)  
 [<span data-ttu-id="afa27-135">保护客户端</span><span class="sxs-lookup"><span data-stu-id="afa27-135">Securing Clients</span></span>](../../../../../docs/framework/wcf/securing-clients.md)  
 [<span data-ttu-id="afa27-136">对等通道消息身份验证</span><span class="sxs-lookup"><span data-stu-id="afa27-136">Peer Channel Message Authentication</span></span>](http://msdn.microsoft.com/library/80e73386-514e-4c30-9e4a-b9ca8c173a95)  
 [<span data-ttu-id="afa27-137">对等通道自定义身份验证</span><span class="sxs-lookup"><span data-stu-id="afa27-137">Peer Channel Custom Authentication</span></span>](http://msdn.microsoft.com/library/4aa8a82e-41a8-48e2-8621-7e1cbabdca7c)  
 [<span data-ttu-id="afa27-138">保护对等通道应用程序</span><span class="sxs-lookup"><span data-stu-id="afa27-138">Securing Peer Channel Applications</span></span>](../../../../../docs/framework/wcf/feature-details/securing-peer-channel-applications.md)  
 [<span data-ttu-id="afa27-139">保护服务和客户端的安全</span><span class="sxs-lookup"><span data-stu-id="afa27-139">Securing Services and Clients</span></span>](../../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)
