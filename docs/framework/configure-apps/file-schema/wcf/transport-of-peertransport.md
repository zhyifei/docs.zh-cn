---
title: <transport> 的 <peerTransport>
ms.date: 03/30/2017
ms.assetid: d7116240-845c-4b6f-b203-262de6b597ef
ms.openlocfilehash: 5dbc55db25c0c49d72ec2cd8dd1041a3f8705d8e
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2019
ms.locfileid: "69940636"
---
# <a name="transport-of-peertransport"></a>\<peerTransport > 的\<传输 >
指定采用此绑定配置的对等方所发送的安全消息的传输类型。  
  
 \<system.serviceModel>  
\<bindings>  
\<customBinding>  
\<绑定 >  
\<peerTransport>  
\<安全 >  
\<transport>  
  
## <a name="syntax"></a>语法  
  
```xml  
<security>
  <transport credentialType="Certificate/Password" />
</security>
```  
  
## <a name="attributes-and-elements"></a>特性和元素  
 以下几节描述了特性、子元素和父元素。  
  
### <a name="attributes"></a>特性  
  
|特性|描述|  
|---------------|-----------------|  
|credentialType|可选。 指定用于验证通过对等传输发送的消息的凭据的类型。 此属性的类型为 <xref:System.ServiceModel.PeerTransportCredentialType>。|  
  
## <a name="credentialtype-attribute"></a>credentialType 属性  
  
|值|描述|  
|-----------|-----------------|  
|证书|对等通道传输的身份验证需要 X509 证书。|  
|Password|对等通道传输的身份验证需要正确的密码。|  
  
### <a name="child-elements"></a>子元素  
 无  
  
### <a name="parent-elements"></a>父元素  
  
|元素|描述|  
|-------------|-----------------|  
|[\<security>](security-of-peertransport.md)|定义对等传输的安全设置。|  
  
## <a name="remarks"></a>备注  
 仅当[ \<security >](security-of-peertransport.md)的 mode 属性设置为`Transport`或`TransportWithMessageCredential`时, 才设置此元素。  
  
## <a name="see-also"></a>请参阅

- <xref:System.ServiceModel.Configuration.PeerTransportSecurityElement>
- <xref:System.ServiceModel.PeerSecuritySettings.Transport%2A>
- <xref:System.ServiceModel.PeerTransportSecuritySettings>
- <xref:System.ServiceModel.Channels.CustomBinding>
- [传输安全性](../../../wcf/feature-details/transport-security.md)
- [传输](../../../wcf/feature-details/transports.md)
- [选择传输](../../../wcf/feature-details/choosing-a-transport.md)
- [绑定](../../../wcf/bindings.md)
- [扩展绑定](../../../wcf/extending/extending-bindings.md)
- [自定义绑定](../../../wcf/extending/custom-bindings.md)
- [\<customBinding>](custombinding.md)
