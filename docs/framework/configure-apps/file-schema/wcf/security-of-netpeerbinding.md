---
title: <security> 的 <netPeerBinding>
ms.date: 03/30/2017
ms.assetid: 1ef40d8c-f903-4426-9b08-da81462766d8
ms.openlocfilehash: be5ebacec466caf8d8a77bf552f42da1861e77a1
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2019
ms.locfileid: "69936631"
---
# <a name="security-of-netpeerbinding"></a>\<netPeerBinding 的\<安全 > >
定义[ \<netPeerTcpBinding >](netpeertcpbinding.md)的安全设置, 包括使用的身份验证类型和用于消息传输的安全性。  
  
 \<system.ServiceModel>  
\<bindings>  
\<netPeerBinding>  
\<绑定 >  
\<安全 >  
  
## <a name="syntax"></a>语法  
  
```xml  
<netPeerBinding>
  <binding>
    <security mode="Message/None/Transport//TransportWithMessageCredential">
      <transport credentialType="Certificate/Password" />
    </security>
  </binding>
</netPeerBinding>
```  
  
## <a name="attributes-and-elements"></a>特性和元素  
 以下几节描述了特性、子元素和父元素。  
  
### <a name="attributes"></a>特性  
  
|特性|描述|  
|---------------|-----------------|  
|mode|可选。 指定采用此绑定配置的对等端所使用的安全类型。 默认值为 `Message`。 此属性的类型为 <xref:System.ServiceModel.SecurityMode>。|  
  
## <a name="mode-attribute"></a>mode 属性  
  
|值|描述|  
|-----------|-----------------|  
|消息|SOAP 安全提供身份验证、完整性和保密性。|  
|无|禁用安全性。|  
|传输|使用 HTTPS 提供安全性。|  
|TransportWithMessageCredential|HTTPS 提供身份验证和保密性。 SOAP 消息提供丰富的凭据类型。|  
  
### <a name="child-elements"></a>子元素  
  
|元素|描述|  
|-------------|-----------------|  
|[\<transport>](transport-of-netpeertcpbinding.md)|定义采用此绑定配置的对等端所发送的安全消息的传输类型。 此元素的类型为 <xref:System.ServiceModel.Configuration.PeerTransportSecurityElement>。|  
  
### <a name="parent-elements"></a>父元素  
  
|元素|描述|  
|-------------|-----------------|  
|[\<binding>](../../../misc/binding.md)|定义[ \<netPeerTcpBinding >](netpeertcpbinding.md)的所有绑定功能。|  
  
## <a name="remarks"></a>备注  
 安全性可以是特定于消息的，也可以是特定于传输的。  
  
## <a name="see-also"></a>请参阅

- <xref:System.ServiceModel.Configuration.PeerSecurityElement>
- <xref:System.ServiceModel.NetPeerTcpBinding.Security%2A>
- <xref:System.ServiceModel.Configuration.NetPeerTcpBindingElement.Security%2A>
- <xref:System.ServiceModel.PeerSecuritySettings>
- [保护服务和客户端的安全](../../../wcf/feature-details/securing-services-and-clients.md)
- [选择凭据类型](../../../wcf/feature-details/selecting-a-credential-type.md)
- [绑定](../../../wcf/bindings.md)
- [配置系统提供的绑定](../../../wcf/feature-details/configuring-system-provided-bindings.md)
- [使用绑定配置服务和客户端](../../../wcf/using-bindings-to-configure-services-and-clients.md)
- [\<binding>](../../../misc/binding.md)
