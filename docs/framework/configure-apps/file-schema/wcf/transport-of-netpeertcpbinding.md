---
title: <transport> 的 <netPeerTcpBinding>
ms.date: 03/30/2017
ms.assetid: c44d86d2-1160-44d7-9c7a-297b12eccc7f
ms.openlocfilehash: 49b31a889d192d190125214e89ba09305114eb7f
ms.sourcegitcommit: 22be09204266253d45ece46f51cc6f080f2b3fd6
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/07/2019
ms.locfileid: "73735975"
---
# <a name="transport-of-netpeertcpbinding"></a>\<netPeerTcpBinding 的 \<传输 > >
指定使用[\<netPeerTcpBinding >](netpeertcpbinding.md)时的传输级安全性设置。  
  
[ **\<configuration>** ](../configuration-element.md)\
\<system &nbsp; &nbsp;[ **>** ](system-servicemodel.md) \
&nbsp;&nbsp;&nbsp;&nbsp;[ **\<绑定**](bindings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<netPeerTcpBinding >** ](netpeertcpbinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<绑定 >** \
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<** ](security-of-netpeerbinding.md) >\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<传输 >**  
  
## <a name="syntax"></a>语法  
  
```xml  
<netPeerTcpBinding>
  <binding>
    <security>
      <transport credentialType="Certificate/Password" />
    </security>
  </binding>
</netPeerTcpBinding>
```  
  
## <a name="attributes-and-elements"></a>特性和元素  
 以下几节描述了特性、子元素和父元素。  
  
### <a name="attributes"></a>特性  
  
|特性|描述|  
|---------------|-----------------|  
|credentialType|可选。 指定用于验证通过对等传输发送的消息的凭据的类型。 此属性的类型为 <xref:System.ServiceModel.PeerTransportCredentialType>。|  
  
## <a name="credentialtype-attribute"></a>credentialType 属性  
  
|“值”|描述|  
|-----------|-----------------|  
|证书|对等通道传输的身份验证需要 X509 证书。|  
|Password|对等通道传输的身份验证需要正确的密码。|  
  
### <a name="child-elements"></a>子元素  
 None  
  
### <a name="parent-elements"></a>父元素  
  
|元素|描述|  
|-------------|-----------------|  
|[\<security >](security-of-netpeerbinding.md)|定义[\<netPeerTcpBinding >](netpeertcpbinding.md)的安全设置。|  
  
## <a name="see-also"></a>请参阅

- <xref:System.ServiceModel.Configuration.PeerTransportSecurityElement>
- <xref:System.ServiceModel.PeerSecuritySettings.Transport%2A>
- <xref:System.ServiceModel.Configuration.PeerSecurityElement.Transport%2A>
- <xref:System.ServiceModel.PeerTransportSecuritySettings>
- [保护服务和客户端的安全](../../../wcf/feature-details/securing-services-and-clients.md)
- [绑定](../../../wcf/bindings.md)
- [配置系统提供的绑定](../../../wcf/feature-details/configuring-system-provided-bindings.md)
- [使用绑定配置服务和客户端](../../../wcf/using-bindings-to-configure-services-and-clients.md)
- [\<binding >](bindings.md)
