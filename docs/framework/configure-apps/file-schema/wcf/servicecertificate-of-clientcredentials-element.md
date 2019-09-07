---
title: <serviceCertificate>of <clientCredentials>元素
ms.date: 03/30/2017
ms.assetid: e50c0ac5-f0df-4c90-b54b-fc602c1f84ea
ms.openlocfilehash: 4c7489a171bdd5cb4b747ca99f1b7ff6dd65517b
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/06/2019
ms.locfileid: "70399687"
---
# <a name="servicecertificate-of-clientcredentials-element"></a>\<clientCredentials > 元素\<的 serviceCertificate >
指定客户端对服务进行身份验证时使用的证书。  
  
[ **\<configuration>** ](../configuration-element.md)\
&nbsp;&nbsp;[ **\<System.servicemodel >** ](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[ **\<行为 >** ](behaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<endpointBehaviors >** ](endpointbehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<行为 >** ](behavior-of-endpointbehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<clientCredentials >** ](clientcredentials.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<serviceCertificate >**  
  
## <a name="syntax"></a>语法  
  
```xml  
<serviceCertificate />
```  
  
## <a name="attributes-and-elements"></a>特性和元素  
 下列各节描述了特性、子元素和父元素。  
  
### <a name="attributes"></a>特性  
 无。  
  
### <a name="child-elements"></a>子元素  
  
|元素|描述|  
|-------------|-----------------|  
|[\<defaultCertificate>](defaultcertificate-element.md)|指定在服务或 STS 未通过协商协议提供证书时要使用的 X.509 证书。|  
|[\<scopedCertificates>](scopedcertificates-element.md)|表示特定服务为身份验证提供的 X.509（作用域）证书的集合。 此集合通常用于指定联合方案中安全令牌服务的服务证书。|  
|[\<authentication>](authentication-of-servicecertificate-element.md)|指定客户端使用的服务证书的身份验证行为。|  
  
### <a name="parent-elements"></a>父元素  
  
|元素|描述|  
|-------------|-----------------|  
|[\<clientCredentials>](clientcredentials.md)|指定客户端用于向服务证明自己的身份的凭据。|  
  
## <a name="remarks"></a>备注  
 此配置元素指定客户端在验证使用 SSL 身份验证的服务所出示的证书时使用的设置。 它还包含在客户端上显式配置为对发送给使用消息安全的服务的消息进行加密的服务的所有证书。  
  
 `serviceCertificate`元素的特性与[ \<clientCertificate >](clientcertificate-of-clientcredentials-element.md)的特性相同。  
  
## <a name="see-also"></a>请参阅

- <xref:System.ServiceModel.Configuration.ClientCredentialsElement>
- <xref:System.ServiceModel.Configuration.ClientCredentialsElement.ServiceCertificate%2A>
- <xref:System.ServiceModel.Description.ClientCredentials>
- <xref:System.ServiceModel.Description.ClientCredentials.ServiceCertificate%2A>
- <xref:System.ServiceModel.Configuration.X509RecipientCertificateClientElement>
- <xref:System.ServiceModel.Security.X509CertificateRecipientClientCredential>
- [安全行为](../../../wcf/feature-details/security-behaviors-in-wcf.md)
- [保护客户端](../../../wcf/securing-clients.md)
- [使用证书](../../../wcf/feature-details/working-with-certificates.md)
- [保护服务和客户端的安全](../../../wcf/feature-details/securing-services-and-clients.md)
