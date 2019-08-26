---
title: <peer> 的 <serviceCredentials>
ms.date: 03/30/2017
ms.assetid: b134e21d-e5b5-458e-9309-626dbf8db4ed
ms.openlocfilehash: 50415cb9b35d2a2053efa3313a415de518b7e36e
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2019
ms.locfileid: "69933772"
---
# <a name="peer-of-servicecredentials"></a>\<serviceCredentials > 的\<对等 >
指定对等节点的当前凭据。  
  
 \<system.ServiceModel>  
\<行为 >  
\<serviceBehaviors>  
\<行为 >  
\<serviceCredentials>  
\<对等 >  
  
## <a name="syntax"></a>语法  
  
```xml  
<peer>
  <certificate />
  <peerAuthentication />
  <messageSenderAuthentication />
</peer>
```  
  
## <a name="attributes-and-elements"></a>特性和元素  
 以下几节描述了特性、子元素和父元素。  
  
### <a name="attributes"></a>特性  
 无。  
  
### <a name="child-elements"></a>子元素  
  
|元素|描述|  
|-------------|-----------------|  
|[\<certificate>](certificate-of-peer.md)|指定要用于为对等服务的消息进行签名和加密的 X.509 证书。 .|  
|[\<messageSenderAuthentication>](messagesenderauthentication.md)|指定用于消息发送方的身份验证选项。|  
|[\<peerAuthentication>](peerauthentication.md)|指定用于对等服务的身份验证选项。|  
  
### <a name="parent-elements"></a>父元素  
  
|元素|描述|  
|-------------|-----------------|  
|[\<serviceCredentials>](servicecredentials.md)|指定要用于对服务进行身份验证的凭据以及与客户端凭据验证相关的设置。|  
  
## <a name="see-also"></a>请参阅

- <xref:System.ServiceModel.Configuration.PeerCredentialElement>
- <xref:System.ServiceModel.Configuration.ServiceCredentialsElement.Peer%2A>
- <xref:System.ServiceModel.Description.ServiceCredentials.Peer%2A>
- <xref:System.ServiceModel.Security.PeerCredential>
- [对等网络](../../../wcf/feature-details/peer-to-peer-networking.md)
- [对等通道消息身份验证](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/aa967730(v=vs.90))
- [对等通道自定义身份验证](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms751447(v=vs.90))
- [保护对等通道应用程序](../../../wcf/feature-details/securing-peer-channel-applications.md)
- [保护服务和客户端的安全](../../../wcf/feature-details/securing-services-and-clients.md)
