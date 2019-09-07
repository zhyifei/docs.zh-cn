---
title: <peer> 的 <serviceCredentials>
ms.date: 03/30/2017
ms.assetid: b134e21d-e5b5-458e-9309-626dbf8db4ed
ms.openlocfilehash: ca97be7b1ab562382895fea4f1d1fc716151b70b
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/06/2019
ms.locfileid: "70397644"
---
# <a name="peer-of-servicecredentials"></a><span data-ttu-id="80445-102">\<serviceCredentials > 的\<对等 ></span><span class="sxs-lookup"><span data-stu-id="80445-102">\<peer> of \<serviceCredentials></span></span>
<span data-ttu-id="80445-103">指定对等节点的当前凭据。</span><span class="sxs-lookup"><span data-stu-id="80445-103">Specifies the current credentials for a peer node.</span></span>  
  
<span data-ttu-id="80445-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="80445-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="80445-105">&nbsp;&nbsp;[ **\<System.servicemodel >** ](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="80445-105">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="80445-106">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<行为 >** ](behaviors.md)</span><span class="sxs-lookup"><span data-stu-id="80445-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)</span></span>\
<span data-ttu-id="80445-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<serviceBehaviors >** ](servicebehaviors.md)</span><span class="sxs-lookup"><span data-stu-id="80445-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceBehaviors>**](servicebehaviors.md)</span></span>\
<span data-ttu-id="80445-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<行为 >** ](behavior-of-servicebehaviors.md)</span><span class="sxs-lookup"><span data-stu-id="80445-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-servicebehaviors.md)</span></span>\
<span data-ttu-id="80445-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<serviceCredentials >** ](servicecredentials.md)</span><span class="sxs-lookup"><span data-stu-id="80445-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceCredentials>**](servicecredentials.md)</span></span>\
<span data-ttu-id="80445-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<对等 >**</span><span class="sxs-lookup"><span data-stu-id="80445-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<peer>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="80445-111">语法</span><span class="sxs-lookup"><span data-stu-id="80445-111">Syntax</span></span>  
  
```xml  
<peer>
  <certificate />
  <peerAuthentication />
  <messageSenderAuthentication />
</peer>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="80445-112">特性和元素</span><span class="sxs-lookup"><span data-stu-id="80445-112">Attributes and Elements</span></span>  
 <span data-ttu-id="80445-113">以下几节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="80445-113">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="80445-114">特性</span><span class="sxs-lookup"><span data-stu-id="80445-114">Attributes</span></span>  
 <span data-ttu-id="80445-115">无。</span><span class="sxs-lookup"><span data-stu-id="80445-115">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="80445-116">子元素</span><span class="sxs-lookup"><span data-stu-id="80445-116">Child Elements</span></span>  
  
|<span data-ttu-id="80445-117">元素</span><span class="sxs-lookup"><span data-stu-id="80445-117">Element</span></span>|<span data-ttu-id="80445-118">描述</span><span class="sxs-lookup"><span data-stu-id="80445-118">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="80445-119">\<certificate></span><span class="sxs-lookup"><span data-stu-id="80445-119">\<certificate></span></span>](certificate-of-peer.md)|<span data-ttu-id="80445-120">指定要用于为对等服务的消息进行签名和加密的 X.509 证书。</span><span class="sxs-lookup"><span data-stu-id="80445-120">Specifies an X.509 certificate to use for signing and encrypting messages for peer-to-peer services.</span></span> <span data-ttu-id="80445-121">.</span><span class="sxs-lookup"><span data-stu-id="80445-121">.</span></span>|  
|[<span data-ttu-id="80445-122">\<messageSenderAuthentication></span><span class="sxs-lookup"><span data-stu-id="80445-122">\<messageSenderAuthentication></span></span>](messagesenderauthentication.md)|<span data-ttu-id="80445-123">指定用于消息发送方的身份验证选项。</span><span class="sxs-lookup"><span data-stu-id="80445-123">Specifies authentication options for message senders.</span></span>|  
|[<span data-ttu-id="80445-124">\<peerAuthentication></span><span class="sxs-lookup"><span data-stu-id="80445-124">\<peerAuthentication></span></span>](peerauthentication.md)|<span data-ttu-id="80445-125">指定用于对等服务的身份验证选项。</span><span class="sxs-lookup"><span data-stu-id="80445-125">Specifies authentication options for peer services.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="80445-126">父元素</span><span class="sxs-lookup"><span data-stu-id="80445-126">Parent Elements</span></span>  
  
|<span data-ttu-id="80445-127">元素</span><span class="sxs-lookup"><span data-stu-id="80445-127">Element</span></span>|<span data-ttu-id="80445-128">描述</span><span class="sxs-lookup"><span data-stu-id="80445-128">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="80445-129">\<serviceCredentials></span><span class="sxs-lookup"><span data-stu-id="80445-129">\<serviceCredentials></span></span>](servicecredentials.md)|<span data-ttu-id="80445-130">指定要用于对服务进行身份验证的凭据以及与客户端凭据验证相关的设置。</span><span class="sxs-lookup"><span data-stu-id="80445-130">Specifies the credential to be used in authenticating the service, and the client credential validation-related settings.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="80445-131">请参阅</span><span class="sxs-lookup"><span data-stu-id="80445-131">See also</span></span>

- <xref:System.ServiceModel.Configuration.PeerCredentialElement>
- <xref:System.ServiceModel.Configuration.ServiceCredentialsElement.Peer%2A>
- <xref:System.ServiceModel.Description.ServiceCredentials.Peer%2A>
- <xref:System.ServiceModel.Security.PeerCredential>
- [<span data-ttu-id="80445-132">对等网络</span><span class="sxs-lookup"><span data-stu-id="80445-132">Peer-to-Peer Networking</span></span>](../../../wcf/feature-details/peer-to-peer-networking.md)
- <span data-ttu-id="80445-133">[对等通道消息身份验证](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/aa967730(v=vs.90))</span><span class="sxs-lookup"><span data-stu-id="80445-133">[Peer Channel Message Authentication](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/aa967730(v=vs.90))</span></span>
- <span data-ttu-id="80445-134">[对等通道自定义身份验证](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms751447(v=vs.90))</span><span class="sxs-lookup"><span data-stu-id="80445-134">[Peer Channel Custom Authentication](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms751447(v=vs.90))</span></span>
- [<span data-ttu-id="80445-135">保护对等通道应用程序</span><span class="sxs-lookup"><span data-stu-id="80445-135">Securing Peer Channel Applications</span></span>](../../../wcf/feature-details/securing-peer-channel-applications.md)
- [<span data-ttu-id="80445-136">保护服务和客户端的安全</span><span class="sxs-lookup"><span data-stu-id="80445-136">Securing Services and Clients</span></span>](../../../wcf/feature-details/securing-services-and-clients.md)
