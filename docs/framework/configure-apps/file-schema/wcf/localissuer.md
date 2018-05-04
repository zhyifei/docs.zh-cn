---
title: '&lt;localIssuer&gt;'
ms.date: 03/30/2017
ms.assetid: 26bdd0df-0e7d-4b9e-bbeb-f28c53769385
ms.openlocfilehash: 9118d1462d4790bb457fc8dc2f7c74b6e69de43a
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/03/2018
---
# <a name="ltlocalissuergt"></a>&lt;localIssuer&gt;
指定要用于颁发安全令牌的本地颁发者的地址和绑定。  
  
 \<system.ServiceModel>  
\<行为 >  
endpointBehaviors 部分  
\<行为 >  
\<clientCredentials>  
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
|[\<headers>](../../../../../docs/framework/configure-apps/file-schema/wcf/headers-element.md)|地址头的集合，要正确书写本地颁发者的地址必须使用这些地址头。 可以使用 `add` 关键字向此集合添加标头。|  
  
### <a name="parent-elements"></a>父元素  
  
|元素|描述|  
|-------------|-----------------|  
|[\<k e n >](../../../../../docs/framework/configure-apps/file-schema/wcf/issuedtoken.md)|指定用于向服务验证客户端身份的自定义令牌。|  
  
## <a name="remarks"></a>备注  
 从安全令牌服务 (STS) 获取已颁发的令牌时，必须使用地址和绑定配置客户端应用程序，以将其用于与 STS 进行通信。 当<xref:System.ServiceModel.WSFederationHttpBinding>不提供的 URL 的安全令牌服务，或者联合绑定的颁发者地址为http://schemas.microsoft.com/2005/12/ServiceModel/Addressing/Anonymous或`null`，客户端的 Windows Communication Foundation (WCF) 通道使用指定的值`address`和`binding`与以获取颁发的令牌的 STS 进行通信。 配置本地颁发者的详细信息，请参阅[如何： 配置本地颁发者](../../../../../docs/framework/wcf/feature-details/how-to-configure-a-local-issuer.md)。  
  
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
