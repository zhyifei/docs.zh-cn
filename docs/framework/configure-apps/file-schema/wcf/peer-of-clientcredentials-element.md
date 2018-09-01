---
title: '&lt;clientCredentials&gt; 的 &lt;peer&gt; 元素'
ms.date: 03/30/2017
ms.assetid: 505bd987-0042-4622-b68e-94f439729d53
ms.openlocfilehash: 9d63aaaa6404b791559d1288730098075f1fd8eb
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/01/2018
ms.locfileid: "43385471"
---
# <a name="ltpeergt-of-ltclientcredentialsgt-element"></a><span data-ttu-id="de145-102">&lt;clientCredentials&gt; 的 &lt;peer&gt; 元素</span><span class="sxs-lookup"><span data-stu-id="de145-102">&lt;peer&gt; of &lt;clientCredentials&gt; Element</span></span>
<span data-ttu-id="de145-103">指定在向对等客户端进行身份验证时使用的凭据。</span><span class="sxs-lookup"><span data-stu-id="de145-103">Specifies credentials used when authenticating peer-to-peer clients.</span></span>  
  
 <span data-ttu-id="de145-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="de145-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="de145-105">\<行为 ></span><span class="sxs-lookup"><span data-stu-id="de145-105">\<behaviors></span></span>  
<span data-ttu-id="de145-106">\<endpointBehaviors></span><span class="sxs-lookup"><span data-stu-id="de145-106">\<endpointBehaviors></span></span>  
<span data-ttu-id="de145-107">\<行为 ></span><span class="sxs-lookup"><span data-stu-id="de145-107">\<behavior></span></span>  
<span data-ttu-id="de145-108">\<clientCredentials></span><span class="sxs-lookup"><span data-stu-id="de145-108">\<clientCredentials></span></span>  
<span data-ttu-id="de145-109">\<对等 ></span><span class="sxs-lookup"><span data-stu-id="de145-109">\<peer></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="de145-110">语法</span><span class="sxs-lookup"><span data-stu-id="de145-110">Syntax</span></span>  
  
```xml  
<peer>  
  <certificate/>  
  <peerAuthentication/>  
  <messageSenderAuthentication/>  
</peer>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="de145-111">特性和元素</span><span class="sxs-lookup"><span data-stu-id="de145-111">Attributes and Elements</span></span>  
 <span data-ttu-id="de145-112">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="de145-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="de145-113">特性</span><span class="sxs-lookup"><span data-stu-id="de145-113">Attributes</span></span>  
 <span data-ttu-id="de145-114">无。</span><span class="sxs-lookup"><span data-stu-id="de145-114">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="de145-115">子元素</span><span class="sxs-lookup"><span data-stu-id="de145-115">Child Elements</span></span>  
  
|<span data-ttu-id="de145-116">元素</span><span class="sxs-lookup"><span data-stu-id="de145-116">Element</span></span>|<span data-ttu-id="de145-117">描述</span><span class="sxs-lookup"><span data-stu-id="de145-117">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="de145-118">\<certificate></span><span class="sxs-lookup"><span data-stu-id="de145-118">\<certificate></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/certificate-element.md)|<span data-ttu-id="de145-119">指定要用于为对等客户端的消息进行签名和加密的 X.509 证书。</span><span class="sxs-lookup"><span data-stu-id="de145-119">Specifies an X.509 certificate to use for signing and encrypting messages for peer-to-peer clients.</span></span> <span data-ttu-id="de145-120">.</span><span class="sxs-lookup"><span data-stu-id="de145-120">.</span></span>|  
|[<span data-ttu-id="de145-121">\<peerAuthentication></span><span class="sxs-lookup"><span data-stu-id="de145-121">\<peerAuthentication></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/peerauthentication-element.md)|<span data-ttu-id="de145-122">指定用于对等客户端的身份验证选项。</span><span class="sxs-lookup"><span data-stu-id="de145-122">Specifies authentication options for peer clients.</span></span>|  
|[<span data-ttu-id="de145-123">\<messageSenderAuthentication></span><span class="sxs-lookup"><span data-stu-id="de145-123">\<messageSenderAuthentication></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/messagesenderauthentication-element.md)|<span data-ttu-id="de145-124">指定用于消息发送方的身份验证选项。</span><span class="sxs-lookup"><span data-stu-id="de145-124">Specifies authentication options for message senders.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="de145-125">父元素</span><span class="sxs-lookup"><span data-stu-id="de145-125">Parent Elements</span></span>  
  
|<span data-ttu-id="de145-126">元素</span><span class="sxs-lookup"><span data-stu-id="de145-126">Element</span></span>|<span data-ttu-id="de145-127">描述</span><span class="sxs-lookup"><span data-stu-id="de145-127">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="de145-128">\<clientCredentials></span><span class="sxs-lookup"><span data-stu-id="de145-128">\<clientCredentials></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/clientcredentials.md)|<span data-ttu-id="de145-129">指定用于向服务验证客户端身份的凭据。</span><span class="sxs-lookup"><span data-stu-id="de145-129">Specifies the credentials used to authenticate a client to a service.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="de145-130">备注</span><span class="sxs-lookup"><span data-stu-id="de145-130">Remarks</span></span>  
 <span data-ttu-id="de145-131">此配置元素指定对等节点用于向网格中的其他节点证明它自己的身份的凭据，以及对等节点用于验证其他对等节点的身份的身份验证设置。</span><span class="sxs-lookup"><span data-stu-id="de145-131">This configuration element specifies the credentials that a peer node uses to authenticate itself to other nodes in the mesh, as well as authentication settings that a peer node uses to authenticate other peer nodes.</span></span> <span data-ttu-id="de145-132">有关详细信息，请参阅[对等通道消息身份验证](https://msdn.microsoft.com/library/80e73386-514e-4c30-9e4a-b9ca8c173a95)并[保护对等通道应用程序](../../../../../docs/framework/wcf/feature-details/securing-peer-channel-applications.md)。</span><span class="sxs-lookup"><span data-stu-id="de145-132">For more information, see [Peer Channel Message Authentication](https://msdn.microsoft.com/library/80e73386-514e-4c30-9e4a-b9ca8c173a95) and [Securing Peer Channel Applications](../../../../../docs/framework/wcf/feature-details/securing-peer-channel-applications.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="de145-133">请参阅</span><span class="sxs-lookup"><span data-stu-id="de145-133">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.ClientCredentialsElement>  
 <xref:System.ServiceModel.Description.ClientCredentials>  
 <xref:System.ServiceModel.Configuration.PeerCredentialElement>  
 <xref:System.ServiceModel.Configuration.ClientCredentialsElement.Peer%2A>  
 <xref:System.ServiceModel.Description.ClientCredentials>  
 <xref:System.ServiceModel.Description.ClientCredentials.Peer%2A>  
 <xref:System.ServiceModel.Security.PeerCredential>  
 [<span data-ttu-id="de145-134">对等网络</span><span class="sxs-lookup"><span data-stu-id="de145-134">Peer-to-Peer Networking</span></span>](../../../../../docs/framework/wcf/feature-details/peer-to-peer-networking.md)  
 [<span data-ttu-id="de145-135">保护客户端</span><span class="sxs-lookup"><span data-stu-id="de145-135">Securing Clients</span></span>](../../../../../docs/framework/wcf/securing-clients.md)  
 [<span data-ttu-id="de145-136">对等通道消息身份验证</span><span class="sxs-lookup"><span data-stu-id="de145-136">Peer Channel Message Authentication</span></span>](https://msdn.microsoft.com/library/80e73386-514e-4c30-9e4a-b9ca8c173a95)  
 [<span data-ttu-id="de145-137">对等通道自定义身份验证</span><span class="sxs-lookup"><span data-stu-id="de145-137">Peer Channel Custom Authentication</span></span>](https://msdn.microsoft.com/library/4aa8a82e-41a8-48e2-8621-7e1cbabdca7c)  
 [<span data-ttu-id="de145-138">保护对等通道应用程序</span><span class="sxs-lookup"><span data-stu-id="de145-138">Securing Peer Channel Applications</span></span>](../../../../../docs/framework/wcf/feature-details/securing-peer-channel-applications.md)  
 [<span data-ttu-id="de145-139">保护服务和客户端的安全</span><span class="sxs-lookup"><span data-stu-id="de145-139">Securing Services and Clients</span></span>](../../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)
