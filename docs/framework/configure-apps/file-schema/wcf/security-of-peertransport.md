---
title: "&lt;peerTransport&gt; 的 &lt;security&gt;"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: f73634ed-f896-4968-bf74-5e5ac52d3b6b
caps.latest.revision: "7"
author: BrucePerlerMS
ms.author: bruceper
manager: mbaldwin
ms.workload: dotnet
ms.openlocfilehash: d08d839d0eb80c23b96f87cf26d3d68db7d358f6
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="ltsecuritygt-of-ltpeertransportgt"></a>&lt;peerTransport&gt; 的 &lt;security&gt;
包含与对等通道相关的安全设置，包括使用的身份验证类型和用于消息传输的安全性。  
  
 \<system.serviceModel >  
\<绑定 >  
\<customBinding >  
\<绑定 >  
\<t >  
\<安全 >  
  
## <a name="syntax"></a>语法  
  
```xml  
<security mode="None/Transport/Message/TransportWithMessageCredential">  
    <transport clientCredentialType="None/Windows/UserName/Certificate/CardSpace" />  
</security  
```  
  
## <a name="attributes-and-elements"></a>特性和元素  
 下列各节描述了特性、子元素和父元素。  
  
### <a name="attributes"></a>特性  
  
|特性|描述|  
|---------------|-----------------|  
|`mode`|指定要应用的安全类型。 默认值为 Message。 此属性的类型为 <xref:System.ServiceModel.SecurityMode>。|  
  
## <a name="mode-attribute"></a>mode 属性  
  
|值|描述|  
|-----------|-----------------|  
|`None`|禁用安全性。|  
|`Transport`|使用 HTTPS 提供安全性。|  
|`Message`|SOAP 安全提供身份验证、完整性和保密性。|  
|`TransportWithMessageCredential`|HTTPS 提供身份验证和保密性。 SOAP 消息提供丰富的凭据类型。|  
  
### <a name="child-elements"></a>子元素  
  
|元素|描述|  
|-------------|-----------------|  
|[\<传输 >](../../../../../docs/framework/configure-apps/file-schema/wcf/transport-of-peertransport.md)|定义自定义绑定的对等传输。 此元素具有一个 `clientCredentialType` 属性，可指定与服务进行交互时要使用的凭据。 此属性的类型为 <xref:System.ServiceModel.PeerTransportCredentialType>。<br /><br /> 此元素的类型为 <xref:System.ServiceModel.Configuration.PeerTransportSecurityElement>。|  
  
### <a name="parent-elements"></a>父元素  
  
|元素|描述|  
|-------------|-----------------|  
|[\<t >](../../../../../docs/framework/configure-apps/file-schema/wcf/peertransport.md)|定义自定义绑定的对等传输。|  
  
## <a name="see-also"></a>请参阅  
 <xref:System.ServiceModel.Configuration.PeerSecurityElement>  
 <xref:System.ServiceModel.PeerSecuritySettings>  
 <xref:System.ServiceModel.Channels.CustomBinding>  
 [传输安全性](../../../../../docs/framework/wcf/feature-details/transport-security.md)  
 [传输](../../../../../docs/framework/wcf/feature-details/transports.md)  
 [选择传输](../../../../../docs/framework/wcf/feature-details/choosing-a-transport.md)  
 [绑定](../../../../../docs/framework/wcf/bindings.md)  
 [扩展绑定](../../../../../docs/framework/wcf/extending/extending-bindings.md)  
 [自定义绑定](../../../../../docs/framework/wcf/extending/custom-bindings.md)  
 [\<customBinding >](../../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md)
