---
title: '&lt;clientCredentials&gt; 的 &lt;peer&gt; 元素'
ms.date: 03/30/2017
ms.assetid: 505bd987-0042-4622-b68e-94f439729d53
ms.openlocfilehash: 9846a25a8df165f51290aa8a26f907d40b6b159f
ms.sourcegitcommit: 4ac80713f6faa220e5a119d5165308a58f7ccdc8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/09/2019
ms.locfileid: "54150560"
---
# <a name="ltpeergt-of-ltclientcredentialsgt-element"></a><span data-ttu-id="f7e11-102">&lt;clientCredentials&gt; 的 &lt;peer&gt; 元素</span><span class="sxs-lookup"><span data-stu-id="f7e11-102">&lt;peer&gt; of &lt;clientCredentials&gt; Element</span></span>
<span data-ttu-id="f7e11-103">指定在向对等客户端进行身份验证时使用的凭据。</span><span class="sxs-lookup"><span data-stu-id="f7e11-103">Specifies credentials used when authenticating peer-to-peer clients.</span></span>  
  
 <span data-ttu-id="f7e11-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="f7e11-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="f7e11-105">\<行为 ></span><span class="sxs-lookup"><span data-stu-id="f7e11-105">\<behaviors></span></span>  
<span data-ttu-id="f7e11-106">\<endpointBehaviors></span><span class="sxs-lookup"><span data-stu-id="f7e11-106">\<endpointBehaviors></span></span>  
<span data-ttu-id="f7e11-107">\<行为 ></span><span class="sxs-lookup"><span data-stu-id="f7e11-107">\<behavior></span></span>  
<span data-ttu-id="f7e11-108">\<clientCredentials></span><span class="sxs-lookup"><span data-stu-id="f7e11-108">\<clientCredentials></span></span>  
<span data-ttu-id="f7e11-109">\<对等 ></span><span class="sxs-lookup"><span data-stu-id="f7e11-109">\<peer></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f7e11-110">语法</span><span class="sxs-lookup"><span data-stu-id="f7e11-110">Syntax</span></span>  
  
```xml  
<peer>
  <certificate />
  <peerAuthentication />
  <messageSenderAuthentication />
</peer>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="f7e11-111">特性和元素</span><span class="sxs-lookup"><span data-stu-id="f7e11-111">Attributes and Elements</span></span>  
 <span data-ttu-id="f7e11-112">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="f7e11-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="f7e11-113">特性</span><span class="sxs-lookup"><span data-stu-id="f7e11-113">Attributes</span></span>  
 <span data-ttu-id="f7e11-114">无。</span><span class="sxs-lookup"><span data-stu-id="f7e11-114">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="f7e11-115">子元素</span><span class="sxs-lookup"><span data-stu-id="f7e11-115">Child Elements</span></span>  
  
|<span data-ttu-id="f7e11-116">元素</span><span class="sxs-lookup"><span data-stu-id="f7e11-116">Element</span></span>|<span data-ttu-id="f7e11-117">描述</span><span class="sxs-lookup"><span data-stu-id="f7e11-117">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="f7e11-118">\<certificate></span><span class="sxs-lookup"><span data-stu-id="f7e11-118">\<certificate></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/certificate-element.md)|<span data-ttu-id="f7e11-119">指定要用于为对等客户端的消息进行签名和加密的 X.509 证书。</span><span class="sxs-lookup"><span data-stu-id="f7e11-119">Specifies an X.509 certificate to use for signing and encrypting messages for peer-to-peer clients.</span></span> <span data-ttu-id="f7e11-120">.</span><span class="sxs-lookup"><span data-stu-id="f7e11-120">.</span></span>|  
|[<span data-ttu-id="f7e11-121">\<peerAuthentication></span><span class="sxs-lookup"><span data-stu-id="f7e11-121">\<peerAuthentication></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/peerauthentication-element.md)|<span data-ttu-id="f7e11-122">指定用于对等客户端的身份验证选项。</span><span class="sxs-lookup"><span data-stu-id="f7e11-122">Specifies authentication options for peer clients.</span></span>|  
|[<span data-ttu-id="f7e11-123">\<messageSenderAuthentication></span><span class="sxs-lookup"><span data-stu-id="f7e11-123">\<messageSenderAuthentication></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/messagesenderauthentication-element.md)|<span data-ttu-id="f7e11-124">指定用于消息发送方的身份验证选项。</span><span class="sxs-lookup"><span data-stu-id="f7e11-124">Specifies authentication options for message senders.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="f7e11-125">父元素</span><span class="sxs-lookup"><span data-stu-id="f7e11-125">Parent Elements</span></span>  
  
|<span data-ttu-id="f7e11-126">元素</span><span class="sxs-lookup"><span data-stu-id="f7e11-126">Element</span></span>|<span data-ttu-id="f7e11-127">描述</span><span class="sxs-lookup"><span data-stu-id="f7e11-127">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="f7e11-128">\<clientCredentials></span><span class="sxs-lookup"><span data-stu-id="f7e11-128">\<clientCredentials></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/clientcredentials.md)|<span data-ttu-id="f7e11-129">指定用于向服务验证客户端身份的凭据。</span><span class="sxs-lookup"><span data-stu-id="f7e11-129">Specifies the credentials used to authenticate a client to a service.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="f7e11-130">备注</span><span class="sxs-lookup"><span data-stu-id="f7e11-130">Remarks</span></span>  
 <span data-ttu-id="f7e11-131">此配置元素指定对等节点用于向网格中的其他节点证明它自己的身份的凭据，以及对等节点用于验证其他对等节点的身份的身份验证设置。</span><span class="sxs-lookup"><span data-stu-id="f7e11-131">This configuration element specifies the credentials that a peer node uses to authenticate itself to other nodes in the mesh, as well as authentication settings that a peer node uses to authenticate other peer nodes.</span></span> <span data-ttu-id="f7e11-132">有关详细信息，请参阅[对等通道消息身份验证](https://msdn.microsoft.com/library/80e73386-514e-4c30-9e4a-b9ca8c173a95)并[保护对等通道应用程序](../../../../../docs/framework/wcf/feature-details/securing-peer-channel-applications.md)。</span><span class="sxs-lookup"><span data-stu-id="f7e11-132">For more information, see [Peer Channel Message Authentication](https://msdn.microsoft.com/library/80e73386-514e-4c30-9e4a-b9ca8c173a95) and [Securing Peer Channel Applications](../../../../../docs/framework/wcf/feature-details/securing-peer-channel-applications.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f7e11-133">请参阅</span><span class="sxs-lookup"><span data-stu-id="f7e11-133">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.ClientCredentialsElement>  
 <xref:System.ServiceModel.Description.ClientCredentials>  
 <xref:System.ServiceModel.Configuration.PeerCredentialElement>  
 <xref:System.ServiceModel.Configuration.ClientCredentialsElement.Peer%2A>  
 <xref:System.ServiceModel.Description.ClientCredentials>  
 <xref:System.ServiceModel.Description.ClientCredentials.Peer%2A>  
 <xref:System.ServiceModel.Security.PeerCredential>  
 [<span data-ttu-id="f7e11-134">对等网络</span><span class="sxs-lookup"><span data-stu-id="f7e11-134">Peer-to-Peer Networking</span></span>](../../../../../docs/framework/wcf/feature-details/peer-to-peer-networking.md)  
 [<span data-ttu-id="f7e11-135">保护客户端</span><span class="sxs-lookup"><span data-stu-id="f7e11-135">Securing Clients</span></span>](../../../../../docs/framework/wcf/securing-clients.md)  
 [<span data-ttu-id="f7e11-136">对等通道消息身份验证</span><span class="sxs-lookup"><span data-stu-id="f7e11-136">Peer Channel Message Authentication</span></span>](https://msdn.microsoft.com/library/80e73386-514e-4c30-9e4a-b9ca8c173a95)  
 [<span data-ttu-id="f7e11-137">对等通道自定义身份验证</span><span class="sxs-lookup"><span data-stu-id="f7e11-137">Peer Channel Custom Authentication</span></span>](https://msdn.microsoft.com/library/4aa8a82e-41a8-48e2-8621-7e1cbabdca7c)  
 [<span data-ttu-id="f7e11-138">保护对等通道应用程序</span><span class="sxs-lookup"><span data-stu-id="f7e11-138">Securing Peer Channel Applications</span></span>](../../../../../docs/framework/wcf/feature-details/securing-peer-channel-applications.md)  
 [<span data-ttu-id="f7e11-139">保护服务和客户端的安全</span><span class="sxs-lookup"><span data-stu-id="f7e11-139">Securing Services and Clients</span></span>](../../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)
