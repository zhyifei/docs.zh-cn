---
title: <peer> <clientCredentials>元素
ms.date: 03/30/2017
ms.assetid: 505bd987-0042-4622-b68e-94f439729d53
ms.openlocfilehash: 8bdb52ccaaa8b41b3321447d2d68f9021a093481
ms.sourcegitcommit: 01ea420eaa4bf76d5fc47673294c8881379b3369
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/06/2019
ms.locfileid: "55758347"
---
# <a name="peer-of-clientcredentials-element"></a><span data-ttu-id="05c21-102">\<对等方 > 的\<clientCredentials > 元素</span><span class="sxs-lookup"><span data-stu-id="05c21-102">\<peer> of \<clientCredentials> Element</span></span>
<span data-ttu-id="05c21-103">指定在向对等客户端进行身份验证时使用的凭据。</span><span class="sxs-lookup"><span data-stu-id="05c21-103">Specifies credentials used when authenticating peer-to-peer clients.</span></span>  
  
 <span data-ttu-id="05c21-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="05c21-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="05c21-105">\<behaviors></span><span class="sxs-lookup"><span data-stu-id="05c21-105">\<behaviors></span></span>  
<span data-ttu-id="05c21-106">\<endpointBehaviors></span><span class="sxs-lookup"><span data-stu-id="05c21-106">\<endpointBehaviors></span></span>  
<span data-ttu-id="05c21-107">\<behavior></span><span class="sxs-lookup"><span data-stu-id="05c21-107">\<behavior></span></span>  
<span data-ttu-id="05c21-108">\<clientCredentials></span><span class="sxs-lookup"><span data-stu-id="05c21-108">\<clientCredentials></span></span>  
<span data-ttu-id="05c21-109">\<peer></span><span class="sxs-lookup"><span data-stu-id="05c21-109">\<peer></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="05c21-110">语法</span><span class="sxs-lookup"><span data-stu-id="05c21-110">Syntax</span></span>  
  
```xml  
<peer>
  <certificate />
  <peerAuthentication />
  <messageSenderAuthentication />
</peer>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="05c21-111">特性和元素</span><span class="sxs-lookup"><span data-stu-id="05c21-111">Attributes and Elements</span></span>  
 <span data-ttu-id="05c21-112">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="05c21-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="05c21-113">特性</span><span class="sxs-lookup"><span data-stu-id="05c21-113">Attributes</span></span>  
 <span data-ttu-id="05c21-114">无。</span><span class="sxs-lookup"><span data-stu-id="05c21-114">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="05c21-115">子元素</span><span class="sxs-lookup"><span data-stu-id="05c21-115">Child Elements</span></span>  
  
|<span data-ttu-id="05c21-116">元素</span><span class="sxs-lookup"><span data-stu-id="05c21-116">Element</span></span>|<span data-ttu-id="05c21-117">描述</span><span class="sxs-lookup"><span data-stu-id="05c21-117">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="05c21-118">\<certificate></span><span class="sxs-lookup"><span data-stu-id="05c21-118">\<certificate></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/certificate-element.md)|<span data-ttu-id="05c21-119">指定要用于为对等客户端的消息进行签名和加密的 X.509 证书。</span><span class="sxs-lookup"><span data-stu-id="05c21-119">Specifies an X.509 certificate to use for signing and encrypting messages for peer-to-peer clients.</span></span> <span data-ttu-id="05c21-120">.</span><span class="sxs-lookup"><span data-stu-id="05c21-120">.</span></span>|  
|[<span data-ttu-id="05c21-121">\<peerAuthentication></span><span class="sxs-lookup"><span data-stu-id="05c21-121">\<peerAuthentication></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/peerauthentication-element.md)|<span data-ttu-id="05c21-122">指定用于对等客户端的身份验证选项。</span><span class="sxs-lookup"><span data-stu-id="05c21-122">Specifies authentication options for peer clients.</span></span>|  
|[<span data-ttu-id="05c21-123">\<messageSenderAuthentication></span><span class="sxs-lookup"><span data-stu-id="05c21-123">\<messageSenderAuthentication></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/messagesenderauthentication-element.md)|<span data-ttu-id="05c21-124">指定用于消息发送方的身份验证选项。</span><span class="sxs-lookup"><span data-stu-id="05c21-124">Specifies authentication options for message senders.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="05c21-125">父元素</span><span class="sxs-lookup"><span data-stu-id="05c21-125">Parent Elements</span></span>  
  
|<span data-ttu-id="05c21-126">元素</span><span class="sxs-lookup"><span data-stu-id="05c21-126">Element</span></span>|<span data-ttu-id="05c21-127">描述</span><span class="sxs-lookup"><span data-stu-id="05c21-127">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="05c21-128">\<clientCredentials></span><span class="sxs-lookup"><span data-stu-id="05c21-128">\<clientCredentials></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/clientcredentials.md)|<span data-ttu-id="05c21-129">指定用于向服务验证客户端身份的凭据。</span><span class="sxs-lookup"><span data-stu-id="05c21-129">Specifies the credentials used to authenticate a client to a service.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="05c21-130">备注</span><span class="sxs-lookup"><span data-stu-id="05c21-130">Remarks</span></span>  
 <span data-ttu-id="05c21-131">此配置元素指定对等节点用于向网格中的其他节点证明它自己的身份的凭据，以及对等节点用于验证其他对等节点的身份的身份验证设置。</span><span class="sxs-lookup"><span data-stu-id="05c21-131">This configuration element specifies the credentials that a peer node uses to authenticate itself to other nodes in the mesh, as well as authentication settings that a peer node uses to authenticate other peer nodes.</span></span> <span data-ttu-id="05c21-132">有关详细信息，请参阅[对等通道消息身份验证](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/aa967730(v=vs.90))并[保护对等通道应用程序](../../../../../docs/framework/wcf/feature-details/securing-peer-channel-applications.md)。</span><span class="sxs-lookup"><span data-stu-id="05c21-132">For more information, see [Peer Channel Message Authentication](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/aa967730(v=vs.90)) and [Securing Peer Channel Applications](../../../../../docs/framework/wcf/feature-details/securing-peer-channel-applications.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="05c21-133">请参阅</span><span class="sxs-lookup"><span data-stu-id="05c21-133">See also</span></span>
- <xref:System.ServiceModel.Configuration.ClientCredentialsElement>
- <xref:System.ServiceModel.Description.ClientCredentials>
- <xref:System.ServiceModel.Configuration.PeerCredentialElement>
- <xref:System.ServiceModel.Configuration.ClientCredentialsElement.Peer%2A>
- <xref:System.ServiceModel.Description.ClientCredentials>
- <xref:System.ServiceModel.Description.ClientCredentials.Peer%2A>
- <xref:System.ServiceModel.Security.PeerCredential>
- [<span data-ttu-id="05c21-134">对等网络</span><span class="sxs-lookup"><span data-stu-id="05c21-134">Peer-to-Peer Networking</span></span>](../../../../../docs/framework/wcf/feature-details/peer-to-peer-networking.md)
- [<span data-ttu-id="05c21-135">保护客户端</span><span class="sxs-lookup"><span data-stu-id="05c21-135">Securing Clients</span></span>](../../../../../docs/framework/wcf/securing-clients.md)
- <span data-ttu-id="05c21-136">[对等通道消息身份验证](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/aa967730(v=vs.90))</span><span class="sxs-lookup"><span data-stu-id="05c21-136">[Peer Channel Message Authentication](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/aa967730(v=vs.90))</span></span>
- <span data-ttu-id="05c21-137">[对等通道自定义身份验证](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms751447(v=vs.90))</span><span class="sxs-lookup"><span data-stu-id="05c21-137">[Peer Channel Custom Authentication](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms751447(v=vs.90))</span></span>
- [<span data-ttu-id="05c21-138">保护对等通道应用程序</span><span class="sxs-lookup"><span data-stu-id="05c21-138">Securing Peer Channel Applications</span></span>](../../../../../docs/framework/wcf/feature-details/securing-peer-channel-applications.md)
- [<span data-ttu-id="05c21-139">保护服务和客户端的安全</span><span class="sxs-lookup"><span data-stu-id="05c21-139">Securing Services and Clients</span></span>](../../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)
