---
title: <peer>of <clientCredentials>元素
ms.date: 03/30/2017
ms.assetid: 505bd987-0042-4622-b68e-94f439729d53
ms.openlocfilehash: dce7ef64de1e3eb248e3553c97cbce8e9b205b4c
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/06/2019
ms.locfileid: "70400101"
---
# <a name="peer-of-clientcredentials-element"></a><span data-ttu-id="22528-102">\<clientCredentials > 元素\<的对等 ></span><span class="sxs-lookup"><span data-stu-id="22528-102">\<peer> of \<clientCredentials> Element</span></span>
<span data-ttu-id="22528-103">指定在向对等客户端进行身份验证时使用的凭据。</span><span class="sxs-lookup"><span data-stu-id="22528-103">Specifies credentials used when authenticating peer-to-peer clients.</span></span>  
  
<span data-ttu-id="22528-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="22528-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="22528-105">&nbsp;&nbsp;[ **\<System.servicemodel >** ](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="22528-105">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="22528-106">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<行为 >** ](behaviors.md)</span><span class="sxs-lookup"><span data-stu-id="22528-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)</span></span>\
<span data-ttu-id="22528-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<endpointBehaviors >** ](endpointbehaviors.md)</span><span class="sxs-lookup"><span data-stu-id="22528-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<endpointBehaviors>**](endpointbehaviors.md)</span></span>\
<span data-ttu-id="22528-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<行为 >** ](behavior-of-endpointbehaviors.md)</span><span class="sxs-lookup"><span data-stu-id="22528-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-endpointbehaviors.md)</span></span>\
<span data-ttu-id="22528-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<clientCredentials >** ](clientcredentials.md)</span><span class="sxs-lookup"><span data-stu-id="22528-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<clientCredentials>**](clientcredentials.md)</span></span>\
<span data-ttu-id="22528-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<对等 >**</span><span class="sxs-lookup"><span data-stu-id="22528-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<peer>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="22528-111">语法</span><span class="sxs-lookup"><span data-stu-id="22528-111">Syntax</span></span>  
  
```xml  
<peer>
  <certificate />
  <peerAuthentication />
  <messageSenderAuthentication />
</peer>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="22528-112">特性和元素</span><span class="sxs-lookup"><span data-stu-id="22528-112">Attributes and Elements</span></span>  
 <span data-ttu-id="22528-113">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="22528-113">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="22528-114">特性</span><span class="sxs-lookup"><span data-stu-id="22528-114">Attributes</span></span>  
 <span data-ttu-id="22528-115">无。</span><span class="sxs-lookup"><span data-stu-id="22528-115">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="22528-116">子元素</span><span class="sxs-lookup"><span data-stu-id="22528-116">Child Elements</span></span>  
  
|<span data-ttu-id="22528-117">元素</span><span class="sxs-lookup"><span data-stu-id="22528-117">Element</span></span>|<span data-ttu-id="22528-118">描述</span><span class="sxs-lookup"><span data-stu-id="22528-118">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="22528-119">\<certificate></span><span class="sxs-lookup"><span data-stu-id="22528-119">\<certificate></span></span>](certificate-element.md)|<span data-ttu-id="22528-120">指定要用于为对等客户端的消息进行签名和加密的 X.509 证书。</span><span class="sxs-lookup"><span data-stu-id="22528-120">Specifies an X.509 certificate to use for signing and encrypting messages for peer-to-peer clients.</span></span> <span data-ttu-id="22528-121">.</span><span class="sxs-lookup"><span data-stu-id="22528-121">.</span></span>|  
|[<span data-ttu-id="22528-122">\<peerAuthentication></span><span class="sxs-lookup"><span data-stu-id="22528-122">\<peerAuthentication></span></span>](peerauthentication-element.md)|<span data-ttu-id="22528-123">指定用于对等客户端的身份验证选项。</span><span class="sxs-lookup"><span data-stu-id="22528-123">Specifies authentication options for peer clients.</span></span>|  
|[<span data-ttu-id="22528-124">\<messageSenderAuthentication></span><span class="sxs-lookup"><span data-stu-id="22528-124">\<messageSenderAuthentication></span></span>](messagesenderauthentication-element.md)|<span data-ttu-id="22528-125">指定用于消息发送方的身份验证选项。</span><span class="sxs-lookup"><span data-stu-id="22528-125">Specifies authentication options for message senders.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="22528-126">父元素</span><span class="sxs-lookup"><span data-stu-id="22528-126">Parent Elements</span></span>  
  
|<span data-ttu-id="22528-127">元素</span><span class="sxs-lookup"><span data-stu-id="22528-127">Element</span></span>|<span data-ttu-id="22528-128">描述</span><span class="sxs-lookup"><span data-stu-id="22528-128">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="22528-129">\<clientCredentials></span><span class="sxs-lookup"><span data-stu-id="22528-129">\<clientCredentials></span></span>](clientcredentials.md)|<span data-ttu-id="22528-130">指定用于向服务验证客户端身份的凭据。</span><span class="sxs-lookup"><span data-stu-id="22528-130">Specifies the credentials used to authenticate a client to a service.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="22528-131">备注</span><span class="sxs-lookup"><span data-stu-id="22528-131">Remarks</span></span>  
 <span data-ttu-id="22528-132">此配置元素指定对等节点用于向网格中的其他节点证明它自己的身份的凭据，以及对等节点用于验证其他对等节点的身份的身份验证设置。</span><span class="sxs-lookup"><span data-stu-id="22528-132">This configuration element specifies the credentials that a peer node uses to authenticate itself to other nodes in the mesh, as well as authentication settings that a peer node uses to authenticate other peer nodes.</span></span> <span data-ttu-id="22528-133">有关详细信息，请参阅[对等通道消息身份验证](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/aa967730(v=vs.90))和[保护对等通道应用程序](../../../wcf/feature-details/securing-peer-channel-applications.md)。</span><span class="sxs-lookup"><span data-stu-id="22528-133">For more information, see [Peer Channel Message Authentication](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/aa967730(v=vs.90)) and [Securing Peer Channel Applications](../../../wcf/feature-details/securing-peer-channel-applications.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="22528-134">请参阅</span><span class="sxs-lookup"><span data-stu-id="22528-134">See also</span></span>

- <xref:System.ServiceModel.Configuration.ClientCredentialsElement>
- <xref:System.ServiceModel.Description.ClientCredentials>
- <xref:System.ServiceModel.Configuration.PeerCredentialElement>
- <xref:System.ServiceModel.Configuration.ClientCredentialsElement.Peer%2A>
- <xref:System.ServiceModel.Description.ClientCredentials>
- <xref:System.ServiceModel.Description.ClientCredentials.Peer%2A>
- <xref:System.ServiceModel.Security.PeerCredential>
- [<span data-ttu-id="22528-135">对等网络</span><span class="sxs-lookup"><span data-stu-id="22528-135">Peer-to-Peer Networking</span></span>](../../../wcf/feature-details/peer-to-peer-networking.md)
- [<span data-ttu-id="22528-136">保护客户端</span><span class="sxs-lookup"><span data-stu-id="22528-136">Securing Clients</span></span>](../../../wcf/securing-clients.md)
- <span data-ttu-id="22528-137">[对等通道消息身份验证](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/aa967730(v=vs.90))</span><span class="sxs-lookup"><span data-stu-id="22528-137">[Peer Channel Message Authentication](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/aa967730(v=vs.90))</span></span>
- <span data-ttu-id="22528-138">[对等通道自定义身份验证](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms751447(v=vs.90))</span><span class="sxs-lookup"><span data-stu-id="22528-138">[Peer Channel Custom Authentication](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms751447(v=vs.90))</span></span>
- [<span data-ttu-id="22528-139">保护对等通道应用程序</span><span class="sxs-lookup"><span data-stu-id="22528-139">Securing Peer Channel Applications</span></span>](../../../wcf/feature-details/securing-peer-channel-applications.md)
- [<span data-ttu-id="22528-140">保护服务和客户端的安全</span><span class="sxs-lookup"><span data-stu-id="22528-140">Securing Services and Clients</span></span>](../../../wcf/feature-details/securing-services-and-clients.md)
