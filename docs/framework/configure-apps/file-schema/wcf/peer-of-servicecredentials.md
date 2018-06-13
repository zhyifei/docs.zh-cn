---
title: '&lt;serviceCredentials&gt; 的 &lt;peer&gt;'
ms.date: 03/30/2017
ms.assetid: b134e21d-e5b5-458e-9309-626dbf8db4ed
ms.openlocfilehash: f50c192639df7b7ed35e863821d5b7a8d62f29bc
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/03/2018
ms.locfileid: "32747676"
---
# <a name="ltpeergt-of-ltservicecredentialsgt"></a><span data-ttu-id="212fb-102">&lt;serviceCredentials&gt; 的 &lt;peer&gt;</span><span class="sxs-lookup"><span data-stu-id="212fb-102">&lt;peer&gt; of &lt;serviceCredentials&gt;</span></span>
<span data-ttu-id="212fb-103">指定对等节点的当前凭据。</span><span class="sxs-lookup"><span data-stu-id="212fb-103">Specifies the current credentials for a peer node.</span></span>  
  
 <span data-ttu-id="212fb-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="212fb-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="212fb-105">\<行为 ></span><span class="sxs-lookup"><span data-stu-id="212fb-105">\<behaviors></span></span>  
<span data-ttu-id="212fb-106">\<serviceBehaviors></span><span class="sxs-lookup"><span data-stu-id="212fb-106">\<serviceBehaviors></span></span>  
<span data-ttu-id="212fb-107">\<行为 ></span><span class="sxs-lookup"><span data-stu-id="212fb-107">\<behavior></span></span>  
<span data-ttu-id="212fb-108">\<serviceCredentials></span><span class="sxs-lookup"><span data-stu-id="212fb-108">\<serviceCredentials></span></span>  
<span data-ttu-id="212fb-109">\<对等 ></span><span class="sxs-lookup"><span data-stu-id="212fb-109">\<peer></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="212fb-110">语法</span><span class="sxs-lookup"><span data-stu-id="212fb-110">Syntax</span></span>  
  
```xml  
<peer>  
  <certificate/>  
  <peerAuthentication/>  
  <messageSenderAuthentication/>  
</peer>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="212fb-111">特性和元素</span><span class="sxs-lookup"><span data-stu-id="212fb-111">Attributes and Elements</span></span>  
 <span data-ttu-id="212fb-112">以下几节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="212fb-112">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="212fb-113">特性</span><span class="sxs-lookup"><span data-stu-id="212fb-113">Attributes</span></span>  
 <span data-ttu-id="212fb-114">无。</span><span class="sxs-lookup"><span data-stu-id="212fb-114">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="212fb-115">子元素</span><span class="sxs-lookup"><span data-stu-id="212fb-115">Child Elements</span></span>  
  
|<span data-ttu-id="212fb-116">元素</span><span class="sxs-lookup"><span data-stu-id="212fb-116">Element</span></span>|<span data-ttu-id="212fb-117">描述</span><span class="sxs-lookup"><span data-stu-id="212fb-117">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="212fb-118">\<certificate></span><span class="sxs-lookup"><span data-stu-id="212fb-118">\<certificate></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/certificate-of-peer.md)|<span data-ttu-id="212fb-119">指定要用于为对等服务的消息进行签名和加密的 X.509 证书。</span><span class="sxs-lookup"><span data-stu-id="212fb-119">Specifies an X.509 certificate to use for signing and encrypting messages for peer-to-peer services.</span></span> <span data-ttu-id="212fb-120">.</span><span class="sxs-lookup"><span data-stu-id="212fb-120">.</span></span>|  
|[<span data-ttu-id="212fb-121">\<messageSenderAuthentication></span><span class="sxs-lookup"><span data-stu-id="212fb-121">\<messageSenderAuthentication></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/messagesenderauthentication.md)|<span data-ttu-id="212fb-122">指定用于消息发送方的身份验证选项。</span><span class="sxs-lookup"><span data-stu-id="212fb-122">Specifies authentication options for message senders.</span></span>|  
|[<span data-ttu-id="212fb-123">\<peerAuthentication></span><span class="sxs-lookup"><span data-stu-id="212fb-123">\<peerAuthentication></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/peerauthentication.md)|<span data-ttu-id="212fb-124">指定用于对等服务的身份验证选项。</span><span class="sxs-lookup"><span data-stu-id="212fb-124">Specifies authentication options for peer services.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="212fb-125">父元素</span><span class="sxs-lookup"><span data-stu-id="212fb-125">Parent Elements</span></span>  
  
|<span data-ttu-id="212fb-126">元素</span><span class="sxs-lookup"><span data-stu-id="212fb-126">Element</span></span>|<span data-ttu-id="212fb-127">描述</span><span class="sxs-lookup"><span data-stu-id="212fb-127">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="212fb-128">\<serviceCredentials></span><span class="sxs-lookup"><span data-stu-id="212fb-128">\<serviceCredentials></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/servicecredentials.md)|<span data-ttu-id="212fb-129">指定要用于对服务进行身份验证的凭据以及与客户端凭据验证相关的设置。</span><span class="sxs-lookup"><span data-stu-id="212fb-129">Specifies the credential to be used in authenticating the service, and the client credential validation-related settings.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="212fb-130">请参阅</span><span class="sxs-lookup"><span data-stu-id="212fb-130">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.PeerCredentialElement>  
 <xref:System.ServiceModel.Configuration.ServiceCredentialsElement.Peer%2A>  
 <xref:System.ServiceModel.Description.ServiceCredentials.Peer%2A>  
 <xref:System.ServiceModel.Security.PeerCredential>  
 [<span data-ttu-id="212fb-131">对等网络</span><span class="sxs-lookup"><span data-stu-id="212fb-131">Peer-to-Peer Networking</span></span>](../../../../../docs/framework/wcf/feature-details/peer-to-peer-networking.md)  
 [<span data-ttu-id="212fb-132">对等通道消息身份验证</span><span class="sxs-lookup"><span data-stu-id="212fb-132">Peer Channel Message Authentication</span></span>](http://msdn.microsoft.com/library/80e73386-514e-4c30-9e4a-b9ca8c173a95)  
 [<span data-ttu-id="212fb-133">对等通道自定义身份验证</span><span class="sxs-lookup"><span data-stu-id="212fb-133">Peer Channel Custom Authentication</span></span>](http://msdn.microsoft.com/library/4aa8a82e-41a8-48e2-8621-7e1cbabdca7c)  
 [<span data-ttu-id="212fb-134">保护对等通道应用程序</span><span class="sxs-lookup"><span data-stu-id="212fb-134">Securing Peer Channel Applications</span></span>](../../../../../docs/framework/wcf/feature-details/securing-peer-channel-applications.md)  
 [<span data-ttu-id="212fb-135">保护服务和客户端的安全</span><span class="sxs-lookup"><span data-stu-id="212fb-135">Securing Services and Clients</span></span>](../../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)
