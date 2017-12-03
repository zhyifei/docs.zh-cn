---
title: "&lt;issuerChannelBehaviors&gt; 的 &lt;add&gt;"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 50710506-e28f-45dd-ab7e-bff6f44173db
caps.latest.revision: "5"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 5ea76a96597796b10c97ea57ca38c3bda453468c
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/02/2017
---
# <a name="ltaddgt-of-ltissuerchannelbehaviorsgt"></a>&lt;issuerChannelBehaviors&gt; 的 &lt;add&gt;
添加在与 STS 进行通信时要使用的终结点行为。  
  
> [!NOTE]
>  如果任何终结点行为包含[ \<c a t e >](../../../../../docs/framework/configure-apps/file-schema/wcf/clientcredentials.md)元素，将引发异常。  
  
 \<系统。ServiceModel >  
\<行为 >  
endpointBehaviors 部分  
\<行为 >  
\<c a t e >  
\<k e n >  
\<issuerChannelBehaviors > 元素  
\<add>  
  
## <a name="syntax"></a>语法  
  
```xml  
<add issuerAddress="string"  
     behaviorConfiguraton="string" />  
```  
  
## <a name="attributes-and-elements"></a>特性和元素  
 以下几节描述了特性、子元素和父元素。  
  
### <a name="attributes"></a>特性  
  
|特性|描述|  
|---------------|-----------------|  
|issuerAddress|要与之通信的安全令牌颁发者的 URI。|  
|behaviorConfiguration|在同一个配置文件中定义的终结点行为的名称。|  
  
### <a name="child-elements"></a>子元素  
 无。  
  
### <a name="parent-elements"></a>父元素  
  
|元素|描述|  
|-------------|-----------------|  
|[\<issuerChannelBehaviors >](../../../../../docs/framework/configure-apps/file-schema/wcf/issuerchannelbehaviors-element.md)|包含与指定的服务令牌服务通信时要使用的 [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)] 客户端终结点行为的集合。|  
  
## <a name="remarks"></a>备注  
 `issuerAddress` 包含客户端希望与之进行通信的安全令牌服务的 URI。 `behaviorConfiguration` 指向终结点行为，应用程序会在由 [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)] 创建的通道中使用它，以从本地安全令牌服务获取已颁发的令牌。  
  
## <a name="see-also"></a>另请参阅  
 <xref:System.ServiceModel.Configuration.IssuedTokenClientElement.IssuerChannelBehaviors%2A>  
 <xref:System.ServiceModel.Configuration.IssuedTokenClientBehaviorsElement>  
 <xref:System.ServiceModel.Configuration.IssuedTokenClientBehaviorsElementCollection>  
 <xref:System.ServiceModel.Security.IssuedTokenClientCredential.IssuerChannelBehaviors%2A>  
 [服务标识和身份验证](../../../../../docs/framework/wcf/feature-details/service-identity-and-authentication.md)  
 [安全行为](../../../../../docs/framework/wcf/feature-details/security-behaviors-in-wcf.md)  
 [联合身份验证和已颁发的令牌](../../../../../docs/framework/wcf/feature-details/federation-and-issued-tokens.md)  
 [保护服务和客户端](../../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)  
 [保护客户端](../../../../../docs/framework/wcf/securing-clients.md)  
 [如何： 创建联合客户端](../../../../../docs/framework/wcf/feature-details/how-to-create-a-federated-client.md)  
 [如何： 配置本地颁发者](../../../../../docs/framework/wcf/feature-details/how-to-configure-a-local-issuer.md)  
 [联合身份验证和已颁发的令牌](../../../../../docs/framework/wcf/feature-details/federation-and-issued-tokens.md)  
 [\<issuerChannelBehaviors >](../../../../../docs/framework/configure-apps/file-schema/wcf/issuerchannelbehaviors-element.md)
