---
title: '&lt;localIssuer&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 26bdd0df-0e7d-4b9e-bbeb-f28c53769385
caps.latest.revision: "13"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 2c7e5c28325326d838da851ff4add12f8ae612c3
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="ltlocalissuergt"></a>&lt;localIssuer&gt;
指定要用于颁发安全令牌的本地颁发者的地址和绑定。  
  
 \<系统。ServiceModel >  
\<行为 >  
endpointBehaviors 部分  
\<行为 >  
\<c a t e >  
\<k e n >  
\<localIssuer >  
  
## <a name="syntax"></a>语法  
  
```xml  
<localIssuer address="string"  
      binding="string"  
      bindingConfiguration="string" />  
```  
  
## <a name="attributes-and-elements"></a>特性和元素  
 以下几节描述了特性、子元素和父元素。  
  
### <a name="attributes"></a>特性  
  
|特性|描述|  
|---------------|-----------------|  
|address|必选字符串。 指定本地颁发者的 URI。|  
|绑定|可选的字符串。 系统提供的一个绑定。 有关列表，请参阅[系统提供的绑定](../../../../../docs/framework/wcf/system-provided-bindings.md)。|  
|bindingConfiguration|可选的字符串。 指定在配置文件中找到的绑定配置。|  
  
### <a name="child-elements"></a>子元素  
  
|元素|描述|  
|-------------|-----------------|  
|[\<标识 >](../../../../../docs/framework/configure-apps/file-schema/wcf/identity.md)|指定此本地颁发者的标识信息。|  
|[\<标头 >](../../../../../docs/framework/configure-apps/file-schema/wcf/headers-element.md)|地址头的集合，要正确书写本地颁发者的地址必须使用这些地址头。 可以使用 `add` 关键字向此集合添加标头。|  
  
### <a name="parent-elements"></a>父元素  
  
|元素|描述|  
|-------------|-----------------|  
|[\<k e n >](../../../../../docs/framework/configure-apps/file-schema/wcf/issuedtoken.md)|指定用于向服务验证客户端身份的自定义令牌。|  
  
## <a name="remarks"></a>备注  
 从安全令牌服务 (STS) 获取已颁发的令牌时，必须使用地址和绑定配置客户端应用程序，以将其用于与 STS 进行通信。 如果 <xref:System.ServiceModel.WSFederationHttpBinding> 没有为安全令牌服务提供 URL，或者联合绑定的颁发者地址为 http://schemas.microsoft.com/2005/12/ServiceModel/Addressing/Anonymous 或 `null`，则客户端的 [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)] 通道使用由 `address` 和 `binding` 指定的值与 STS 进行通信，以获取颁发的令牌。 配置本地颁发者的详细信息，请参阅[如何： 配置本地颁发者](../../../../../docs/framework/wcf/feature-details/how-to-configure-a-local-issuer.md)。  
  
## <a name="example"></a>示例  
 下面的示例设置 `address` 元素的 `binding`、`bindingConfiguration` 和 `localIssuer` 属性。  
  
```xml  
<system.serviceModel>  
 <behaviors>  
 <endpointBehaviors>  
  <behavior name="MyEndpointBehavior">  
   <clientCredentials>  
    <issuedToken cacheIssuedTokens="false"   
                 defaultKeyEntropyMode="ClientEntropy">  
     <localIssuer address="net.tcp://cohowinery/tokens"   
                  binding="netTcpBinding"  
                  bindingConfiguration="myTcpBindingConfig" />  
    </issuedToken>  
   </clientCredentials>  
  </behavior>  
  </endpointBehaviors>  
  </behaviors>  
</system.serviceModel>  
```  
  
## <a name="see-also"></a>请参阅  
 <xref:System.ServiceModel.Configuration.IssuedTokenClientElement.LocalIssuer%2A>  
 <xref:System.ServiceModel.Configuration.IssuedTokenParametersEndpointAddressElement>  
 <xref:System.ServiceModel.Security.IssuedTokenClientCredential>  
 [安全行为](../../../../../docs/framework/wcf/feature-details/security-behaviors-in-wcf.md)  
 [如何：配置本地证书颁发者](../../../../../docs/framework/wcf/feature-details/how-to-configure-a-local-issuer.md)  
 [服务标识和身份验证](../../../../../docs/framework/wcf/feature-details/service-identity-and-authentication.md)  
 [安全行为](../../../../../docs/framework/wcf/feature-details/security-behaviors-in-wcf.md)  
 [联合令牌与颁发的令牌](../../../../../docs/framework/wcf/feature-details/federation-and-issued-tokens.md)  
 [保护服务和客户端的安全](../../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)  
 [保护客户端](../../../../../docs/framework/wcf/securing-clients.md)  
 [如何：创建联合客户端](../../../../../docs/framework/wcf/feature-details/how-to-create-a-federated-client.md)  
 [联合令牌与颁发的令牌](../../../../../docs/framework/wcf/feature-details/federation-and-issued-tokens.md)
